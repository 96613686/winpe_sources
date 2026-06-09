# Microsoft.BIServer.Configuration.WMI.WmiProvider::RemoveAutoRecoverMofSetting

- ea: `0x5bf0`
- end: `0x5c09`
- name: `Microsoft.BIServer.Configuration.WMI.WmiProvider::RemoveAutoRecoverMofSetting`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x5530`

## callees

- `0x5bf0`

## string_xrefs

- `0x5bf8`: `No Mof file specified Autorecover MOFs registry is not updated.`

## pseudocode

```c

```

## disassembly

```asm
0x5bf0  ldarg.1
0x5bf1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5bf6  brfalse.s loc_5C08
0x5bf8  ldstr    aNoMofFileSpeci// "No Mof file specified Autorecover MOFs "...
0x5bfd  call     T0x2B000015
0x5c02  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x5c07  ret
0x5c08  ret
```
