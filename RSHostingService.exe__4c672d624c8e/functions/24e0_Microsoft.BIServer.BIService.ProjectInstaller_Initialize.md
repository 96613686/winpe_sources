# Microsoft.BIServer.BIService.ProjectInstaller::Initialize

- ea: `0x24e0`
- end: `0x25c3`
- name: `Microsoft.BIServer.BIService.ProjectInstaller::Initialize`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2490`
- `0x24a0`

## callees

- `0x24e0`

## string_xrefs

- `0x2519`: `servicename`
- `0x2537`: `servicename`

## pseudocode

```c

```

## disassembly

```asm
0x24e0  ldarg.0
0x24e1  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller::.ctor()
0x24e6  stfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.BIServer.BIService.ProjectInstaller::serviceProcessInstaller
0x24eb  ldarg.0
0x24ec  newobj   instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::.ctor()
0x24f1  stfld    class [System.ServiceProcess]System.ServiceProcess.ServiceInstaller Microsoft.BIServer.BIService.ProjectInstaller::serviceInstaller
0x24f6  ldarg.0
0x24f7  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.BIServer.BIService.ProjectInstaller::serviceProcessInstaller
0x24fc  ldc.i4.2
0x24fd  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller::set_Account(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceAccount)
0x2502  ldarg.0
0x2503  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceInstaller Microsoft.BIServer.BIService.ProjectInstaller::serviceInstaller
0x2508  ldc.i4.2
0x2509  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_StartType(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceStartMode)
0x250e  ldarg.0
0x250f  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x2514  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x2519  ldstr    aServicename// "servicename"
0x251e  callvirt instance bool [System]System.Collections.Specialized.StringDictionary::ContainsKey(string)
0x2523  brtrue.s loc_252C
0x2525  ldstr    aPowerbireports// "PowerBIReportServer"
0x252a  br.s     loc_2541
0x252c  ldarg.0
0x252d  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x2532  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x2537  ldstr    aServicename// "servicename"
0x253c  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x2541  stloc.0
0x2542  ldarg.0
0x2543  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x2548  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x254d  ldstr    aProductname// "productname"
0x2552  callvirt instance bool [System]System.Collections.Specialized.StringDictionary::ContainsKey(string)
0x2557  brtrue.s loc_2560
0x2559  ldstr    aPowerBiReportS// "Power BI Report Server"
0x255e  br.s     loc_2575
0x2560  ldarg.0
0x2561  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x2566  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x256b  ldstr    aProductname// "productname"
0x2570  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x2575  stloc.1
0x2576  ldarg.0
0x2577  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceInstaller Microsoft.BIServer.BIService.ProjectInstaller::serviceInstaller
0x257c  ldstr    aManagesExecute// "Manages, executes, renders, schedules, "...
0x2581  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_Description(string)
0x2586  ldarg.0
0x2587  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceInstaller Microsoft.BIServer.BIService.ProjectInstaller::serviceInstaller
0x258c  ldloc.1
0x258d  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_DisplayName(string)
0x2592  ldarg.0
0x2593  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceInstaller Microsoft.BIServer.BIService.ProjectInstaller::serviceInstaller
0x2598  ldloc.0
0x2599  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_ServiceName(string)
0x259e  ldarg.0
0x259f  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallerCollection [System.Configuration.Install]System.Configuration.Install.Installer::get_Installers()
0x25a4  ldarg.0
0x25a5  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceProcessInstaller Microsoft.BIServer.BIService.ProjectInstaller::serviceProcessInstaller
0x25aa  callvirt instance int32 [System.Configuration.Install]System.Configuration.Install.InstallerCollection::Add(class [System.Configuration.Install]System.Configuration.Install.Installer)
0x25af  pop
0x25b0  ldarg.0
0x25b1  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallerCollection [System.Configuration.Install]System.Configuration.Install.Installer::get_Installers()
0x25b6  ldarg.0
0x25b7  ldfld    class [System.ServiceProcess]System.ServiceProcess.ServiceInstaller Microsoft.BIServer.BIService.ProjectInstaller::serviceInstaller
0x25bc  callvirt instance int32 [System.Configuration.Install]System.Configuration.Install.InstallerCollection::Add(class [System.Configuration.Install]System.Configuration.Install.Installer)
0x25c1  pop
0x25c2  ret
```
