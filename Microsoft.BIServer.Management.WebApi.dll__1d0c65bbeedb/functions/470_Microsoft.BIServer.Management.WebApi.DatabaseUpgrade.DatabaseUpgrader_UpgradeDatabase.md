# Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::UpgradeDatabase

- ea: `0x470`
- end: `0x484`
- name: `Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::UpgradeDatabase`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x2f0`

## pseudocode

```c

```

## disassembly

```asm
0x470  ldarg.0
0x471  callvirt instance string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::get_DatabaseName()
0x476  call     string [Microsoft.ReportingServices.UpgradeScripts]Microsoft.ReportingServices.UpgradeScripts::GetUpgradeScript(string)
0x47b  stloc.0
0x47c  ldarg.0
0x47d  ldloc.0
0x47e  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::ExecuteBatchScript(string)
0x483  ret
```
