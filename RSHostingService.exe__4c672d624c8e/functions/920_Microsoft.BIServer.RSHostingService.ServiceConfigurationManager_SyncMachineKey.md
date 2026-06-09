# Microsoft.BIServer.RSHostingService.ServiceConfigurationManager::SyncMachineKey

- ea: `0x920`
- end: `0x9bf`
- name: `Microsoft.BIServer.RSHostingService.ServiceConfigurationManager::SyncMachineKey`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8f0`

## callees

- `0x40`
- `0x170`
- `0x920`
- `0x2130`
- `0x2320`

## string_xrefs

- `0x920`: `Syncing service machine key`

## pseudocode

```c

```

## disassembly

```asm
0x920  ldstr    aSyncingService// "Syncing service machine key"
0x925  call     T0x2B000001
0x92a  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x92f  newobj   instance void Microsoft.BIServer.RSHostingService.ConfigurationFileEditor::.ctor()
0x934  stloc.0
0x935  ldarg.0
0x936  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.RSHostingService.ServiceConfigurationManager::serviceConfig
0x93b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.BIServer.BIService.ProcessConfig> Microsoft.BIServer.BIService.ServiceConfig::get_ManagedProcesses()
0x940  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.BIService.ProcessConfig>::GetEnumerator()
0x945  stloc.1
0x946  br.s     loc_9AA
0x948  ldloc.1
0x949  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.BIServer.BIService.ProcessConfig>::get_Current()
0x94e  stloc.2
0x94f  ldloc.2
0x950  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_AspSettingsFile()
0x955  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x95a  brtrue.s loc_9AA
0x95c  call     string [mscorlib]System.IO.Directory::GetCurrentDirectory()
0x961  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::GetParent(string)
0x966  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x96b  ldloc.2
0x96c  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_AspSettingsFile()
0x971  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x976  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x97b  stloc.3
0x97c  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x981  stloc.s  4
0x983  ldloc.s  4
0x985  ldloc.3
0x986  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(string)
0x98b  ldloc.0
0x98c  ldloc.s  4
0x98e  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0x993  callvirt instance class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_ServerConfiguration()
0x998  callvirt instance class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.MachineKeySettings [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ServerConfiguration::get_MachineKey()
0x99d  callvirt instance void Microsoft.BIServer.RSHostingService.ConfigurationFileEditor::UpdateMachineKey(class [System.Xml]System.Xml.XmlDocument configToModify, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.MachineKeySettings machineKey)
0x9a2  ldloc.s  4
0x9a4  ldloc.3
0x9a5  callvirt instance void [System.Xml]System.Xml.XmlDocument::Save(string)
0x9aa  ldloc.1
0x9ab  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9b0  brtrue.s loc_948
0x9b2  leave.s  loc_9BE
0x9b4  ldloc.1
0x9b5  brfalse.s loc_9BD
0x9b7  ldloc.1
0x9b8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9bd  endfinally
0x9be  ret
```
