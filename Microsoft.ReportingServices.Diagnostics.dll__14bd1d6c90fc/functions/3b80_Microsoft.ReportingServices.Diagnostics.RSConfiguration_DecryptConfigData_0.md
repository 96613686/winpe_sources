# Microsoft.ReportingServices.Diagnostics.RSConfiguration::DecryptConfigData_0

- ea: `0x3b80`
- end: `0x3b99`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::DecryptConfigData_0`
- size: `25`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3b60`
- `0x3bb0`
- `0x3c10`
- `0x3c40`
- `0x3c70`
- `0x3e90`
- `0x3eb0`
- `0x3ed0`

## callees

- `0x3b80`
- `0x9e90`
- `0xa560`
- `0xaf00`

## pseudocode

```c

```

## disassembly

```asm
0x3b80  ldnull
0x3b81  stloc.0
0x3b82  call     class Microsoft.ReportingServices.Diagnostics.Encryption Microsoft.ReportingServices.Diagnostics.MachineKeyEncryption::get_Instance()
0x3b87  ldarg.0
0x3b88  callvirt instance string Microsoft.ReportingServices.Diagnostics.Encryption::DecryptToString(string protectedData)
0x3b8d  stloc.0
0x3b8e  leave.s  loc_3B97
0x3b90  ldarg.1
0x3b91  newobj   instance void Microsoft.ReportingServices.Diagnostics.FailedToDecryptConfigInformationException::.ctor(class [mscorlib]System.Exception innerException, string configElement)
0x3b96  throw
0x3b97  ldloc.0
0x3b98  ret
```
