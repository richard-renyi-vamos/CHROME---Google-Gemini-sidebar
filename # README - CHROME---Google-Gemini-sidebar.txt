🧭 Add Google Gemini to Your Chrome Sidebar
✅ Summary:
This Chrome Extension lets you use Google Gemini directly in your browser's side panel. It's lightweight, easy to set up, and gives you quick access to Gemini without switching tabs.

🗂️ Folder Structure

gemini-sidebar-extension/
├── manifest.json
├── sidebar.html
├── sidebar.js
└── icon.png     (optional)

------------

🔧 manifest.json
json

{
  "manifest_version": 3,
  "name": "Gemini Sidebar",
  "version": "1.0",
  "description": "Access Google Gemini in the Chrome sidebar.",
  "icons": {
    "16": "icon.png",
    "48": "icon.png",
    "128": "icon.png"
  },
  "permissions": ["sidePanel"],
  "action": {
    "default_title": "Gemini Sidebar"
  },
  "side_panel": {
    "default_path": "sidebar.html"
  },
  "background": {
    "service_worker": "sidebar.js"
  }
}

------------

🌐 sidebar.html
html
Copy
Edit
<!DOCTYPE html>
<html>
<head>
  <title>Gemini Sidebar</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      overflow: hidden;
    }
    iframe {
      width: 100%;
      height: 100%;
      border: none;
    }
  </style>
</head>
<body>
  <iframe src="https://gemini.google.com/app" title="Google Gemini"></iframe>
</body>
</html>
This loads the Gemini web app inside an iframe. Make sure you’re logged into your Google account.

------------

⚙️ sidebar.js
js
Copy
Edit
chrome.runtime.onInstalled.addListener(() => {
  chrome.sidePanel.setPanelBehavior({ openPanelOnActionClick: true });
});
This registers the side panel behavior so clicking the extension icon opens the sidebar.

------------

🛠️ How to Install It in Chrome
Open chrome://extensions/

Enable Developer mode

Click "Load unpacked"

Select the gemini-sidebar-extension folder

Click the extension icon to open Gemini in the sidebar!
