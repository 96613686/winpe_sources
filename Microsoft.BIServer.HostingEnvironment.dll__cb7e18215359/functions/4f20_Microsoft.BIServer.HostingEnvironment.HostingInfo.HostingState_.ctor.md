# Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::.ctor

- ea: `0x4f20`
- end: `0x4f5b`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::.ctor`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4e30`
- `0x4ee0`

## callees

- `0x1550`

## pseudocode

```c

```

## disassembly

```asm
0x4f20  ldarg.0
0x4f21  call     instance void [mscorlib]System.Object::.ctor()
0x4f26  ldstr    aSettingUpHoste// "Setting up Hosted Process State"
0x4f2b  call     T0x2B00000A
0x4f30  call     void Microsoft.BIServer.HostingEnvironment.Logger::Info(string formatString, object[] formatParams)
0x4f35  ldarg.0
0x4f36  ldarg.1
0x4f37  stfld    string Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::_rsConfigFilePath
0x4f3c  ldarg.0
0x4f3d  ldarg.2
0x4f3e  stfld    class Microsoft.BIServer.HostingEnvironment.Cryptography.ICrypto Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::_catalogCrypto
0x4f43  ldarg.0
0x4f44  ldarg.3
0x4f45  stfld    valuetype Microsoft.BIServer.HostingEnvironment.HostingInfo.DatabaseValidationStatus Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::_databaseValidationStatus
0x4f4a  ldarg.0
0x4f4b  ldarg.s  5
0x4f4d  stfld    class [System]System.Uri Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::_portalUrl
0x4f52  ldarg.0
0x4f53  ldarg.s  4
0x4f55  stfld    class Microsoft.BIServer.HostingEnvironment.ManagementAdapter.IManagementService Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::_managementService
0x4f5a  ret
```
