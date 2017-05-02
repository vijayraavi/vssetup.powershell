﻿# VSSetup
## about_VSSetup

# SHORT DESCRIPTION
Enumerate and select instances of Visual Studio.

# LONG DESCRIPTION
Visual Studio 2017 introduced a new setup engine capable of installing multiple instances of Visual Studio and other products in the Visual Studio family. This module provides commands to enumerate those instances and select instances that meet your criteria. For example, in a development environment you might have a script that finds an instance of Visual Studio with the the Managed Desktop workload for writing projects targeting the .NET Framework. See below for more examples.

# EXAMPLES
You can enumerate all instances - even those with errors that require a repair - with the following command.

```powershell
Get-VSSetupInstance -All
```

If you want to select all launchable instances of Visual Studio products that have the Managed Desktop workload, use the following command.

```powershell
Get-VSSetupInstance | Get-VSSetupInstance `
    -Require 'Microsoft.VisualStudio.Workload.ManagedDesktop'
```

You can also get the instance for an installation directory if you want to discover more about what is installed to that directory.

```powershell
Get-VSSetupInstance 'C:\Program Files (x86)\Microsoft Visual Studio\2017\Community'
```

# SEE ALSO
https://github.com/Microsoft/vssetup.powershell