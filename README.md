# Rebels-Botnet
Remote Imports: 
remotely import third-party packages from the server without writing them to the disk or downloading/installing them

Nothing Written To The Disk: clients never write anything to the disk - not even temporary files (zero IO system calls are made) 

because remote imports allow arbitrary code to be dynamically loaded into memory and directly imported into the currently running process

Zero Dependencies (Not Even Python Itself):

 client runs with just the python standard library, remotely imports any non-standard packages/modules from the server, and can be compiled with a standalone python interpreter into a portable binary executable formatted for any platform/architecture, allowing it to run on anything, even when Python itself is missing on the target host
Add New Features With Just 1 Click:

 any python script, module, or package you copy to the ./byob/modules/ directory automatically becomes remotely importable & directly usable by every client while your command & control server is running
Write Your Own Modules: a basic module template is provided in ./byob/modules/ directory to make writing your own modules a straight-forward, hassle-free process
Run Unlimited Modules Without Bloating File Size: use remote imports to add unlimited features without adding a single byte to the client's file size
Fully Updatable: each client will periodically check the server for new content available for remote import, and will dynamically update its in-memory resources if anything has been added/removed
Platform Independent: everything is written in Python (a platform-agnostic language) and the clients generated can optionally be compiled into a portable executable 

(Windows) or bundled into a standalone application (macOS)
Bypass Firewalls: clients connect to the command & control server via reverse TCP connections, which will bypass most firewalls because the default filter configurations primarily block incoming connections


Counter-Measure Against Antivirus: avoids being analyzed by antivirus by blocking processes with names of known antivirus products from spawning

Encrypt Payloads To Prevent Analysis: the main client payload is encrypted with a random 256-bit key which exists solely in the payload stager which is generated along with it
Prevent Reverse-Engineering: by default, clients will abort execution if a virtual machine or sandbox is detected
Modules

Post-exploitation modules that are remotely importable by clients

Console-Based 
User-Interface: streamlined console interface for controlling client host machines remotely via reverse TCP shells which provide direct terminal access to the client host machines

Persistent SQLite Database:
lightweight database that stores identifying information about client host machines, allowing reverse TCP shell sessions to persist through disconnections of arbitrary duration and enabling long-term reconnaissance

Client-Server Architecture: all python packages/modules installed locally are automatically made available for clients to remotely import without writing them to the disk of the target machines, allowing clients to use modules which require packages not installed on the target machines
