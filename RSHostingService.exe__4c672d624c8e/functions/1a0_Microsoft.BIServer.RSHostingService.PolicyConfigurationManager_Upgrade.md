# Microsoft.BIServer.RSHostingService.PolicyConfigurationManager::Upgrade

- ea: `0x1a0`
- end: `0x221`
- name: `Microsoft.BIServer.RSHostingService.PolicyConfigurationManager::Upgrade`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb80`

## callees

- `0x1a0`
- `0x240`
- `0x2150`
- `0x2320`

## string_xrefs

- `0x20f`: `Error updating policy configuration`

## pseudocode

```c

```

## disassembly

```asm
0x1a0  ldarg.0
0x1a1  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.RSHostingService.PolicyConfigurationManager::serviceConfig
0x1a6  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.BIServer.BIService.ProcessConfig> Microsoft.BIServer.BIService.ServiceConfig::get_ManagedProcesses()
0x1ab  ldsfld   class [mscorlib]System.Func`2<class Microsoft.BIServer.BIService.ProcessConfig, bool> <>c::<>9__2_0
0x1b0  dup
0x1b1  brtrue.s loc_1CA
0x1b3  pop
0x1b4  ldsfld   class <>c <>c::<>9
0x1b9  ldftn    instance bool <>c::<Upgrade>b__2_0(class Microsoft.BIServer.BIService.ProcessConfig x)
0x1bf  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.BIServer.BIService.ProcessConfig, bool>::.ctor(object, native int)
0x1c4  dup
0x1c5  stsfld   class [mscorlib]System.Func`2<class Microsoft.BIServer.BIService.ProcessConfig, bool> <>c::<>9__2_0
0x1ca  call     T0x2B000002
0x1cf  call     T0x2B000003
0x1d4  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_PolicySettingsFile()
0x1d9  stloc.0
0x1da  call     string [mscorlib]System.IO.Directory::GetCurrentDirectory()
0x1df  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::GetParent(string)
0x1e4  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x1e9  ldloc.0
0x1ea  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1ef  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x1f4  stloc.1
0x1f5  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1fa  dup
0x1fb  ldloc.1
0x1fc  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(string)
0x201  dup
0x202  call     void Microsoft.BIServer.RSHostingService.PolicyFileEditor::Upgrade(class [System.Xml]System.Xml.XmlDocument configToModify)
0x207  ldloc.1
0x208  callvirt instance void [System.Xml]System.Xml.XmlDocument::Save(string)
0x20d  leave.s  loc_220
0x20f  ldstr    aErrorUpdatingP// "Error updating policy configuration"
0x214  call     T0x2B000001
0x219  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception, string, object[])
0x21e  leave.s  loc_220
0x220  ret
```
