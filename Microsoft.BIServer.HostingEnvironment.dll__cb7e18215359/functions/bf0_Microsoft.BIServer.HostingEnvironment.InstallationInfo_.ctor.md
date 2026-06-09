# Microsoft.BIServer.HostingEnvironment.InstallationInfo::.ctor

- ea: `0xbf0`
- end: `0xc14`
- name: `Microsoft.BIServer.HostingEnvironment.InstallationInfo::.ctor`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xbf0  ldarg.0
0xbf1  call     instance void [mscorlib]System.Object::.ctor()
0xbf6  ldarg.0
0xbf7  ldarg.1
0xbf8  stfld    valuetype [mscorlib]System.Guid Microsoft.BIServer.HostingEnvironment.InstallationInfo::_installationId
0xbfd  ldarg.0
0xbfe  ldarg.2
0xbff  stfld    string Microsoft.BIServer.HostingEnvironment.InstallationInfo::_machineName
0xc04  ldarg.0
0xc05  ldarg.3
0xc06  stfld    string Microsoft.BIServer.HostingEnvironment.InstallationInfo::_instanceName
0xc0b  ldarg.0
0xc0c  ldarg.s  4
0xc0e  stfld    unsigned int8[] Microsoft.BIServer.HostingEnvironment.InstallationInfo::_publicKey
0xc13  ret
```
