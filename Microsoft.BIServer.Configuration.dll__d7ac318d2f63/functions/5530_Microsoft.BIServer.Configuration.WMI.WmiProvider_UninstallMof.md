# Microsoft.BIServer.Configuration.WMI.WmiProvider::UninstallMof

- ea: `0x5530`
- end: `0x5560`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::UninstallMof`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x5530`
- `0x55e0`
- `0x5bf0`

## string_xrefs

- `0x5530`: `Attempting to uninstall MOF file for namespace {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5530  ldstr    aAttemptingToUn// "Attempting to uninstall MOF file for na"...
0x5535  ldc.i4.1
0x5536  newarr   [mscorlib]System.Object
0x553b  dup
0x553c  ldc.i4.0
0x553d  ldarg.1
0x553e  stelem.ref
0x553f  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x5544  ldarg.1
0x5545  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x554a  brtrue.s loc_5553
0x554c  ldarg.0
0x554d  ldarg.1
0x554e  call     instance void Microsoft.BIServer.Configuration.WMI.WmiProvider::RemoveWmiNamespaceWithParents(string wmiPath)
0x5553  ldarg.0
0x5554  ldarg.0
0x5555  ldfld    string Microsoft.BIServer.Configuration.WMI.WmiProvider::_mofFile
0x555a  call     instance void Microsoft.BIServer.Configuration.WMI.WmiProvider::RemoveAutoRecoverMofSetting(string mofFileWithPath)
0x555f  ret
```
