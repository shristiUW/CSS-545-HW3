# state_management_app

Key Features of Implementation
Data Persistence:
My app uses SharedPreferences to persist data. When text is entered into the TextField, it is automatically saved to SharedPreferences through the _saveData() function, which is triggered every time the text changes (_saveDataOnChange()). This ensures that all data entered is captured and saved immediately.
Lifecycle Management:
My app uses WidgetsBindingObserver to observe changes in the app's lifecycle. When the app goes into the paused or detached state, it explicitly calls _saveData(), ensuring that any last-minute changes are saved before the app is suspended or terminated.
State Restoration:
Upon restarting or resuming the app, _loadData() is called during initState(), which retrieves the saved data from SharedPreferences and sets it as the current text in the TextField. This ensures that when a user returns to the app after it has been paused or killed, they find it in the same state as they left it.

Compliance with Tombstone Requirements:

Tombstone Scenario Handling:
When a user navigates away from the app (causing it to pause or detach), and then returns, the text they had previously entered will still be present in the TextField. This behavior is exactly what tombstoning is about—preserving and then restoring the app state.

Automatic Saving:
The automatic saving feature does not require user interaction (like pressing a save button), which is crucial for handling real-world use cases where users might not remember to manually save their progress. This approach minimizes data loss and enhances the user experience by ensuring the app is resilient to unexpected interruptions.

<img width="376" alt="image" src="https://github.com/shristiUW/CSS-545-HW3/assets/148150150/7a79d1d5-01f0-4f14-b89d-177fdffbd8b4">

<img width="376" alt="image" src="https://github.com/shristiUW/CSS-545-HW3/assets/148150150/c42c28f2-b839-4c98-b716-02bcf92a2815">


<img width="451" alt="image" src="https://github.com/shristiUW/CSS-545-HW3/assets/148150150/135fc36e-1345-4b0a-81a7-d1e10dfc8696">

After stopping and restarting the app, the text data remains the same

<img width="376" alt="image" src="https://github.com/shristiUW/CSS-545-HW3/assets/148150150/1e01c40d-3d12-4df4-bb3a-3625ca787a2d">

