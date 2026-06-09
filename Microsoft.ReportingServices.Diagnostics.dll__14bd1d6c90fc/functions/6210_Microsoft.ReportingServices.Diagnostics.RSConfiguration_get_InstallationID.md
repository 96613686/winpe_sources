# Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_InstallationID

- ea: `0x6210`
- end: `0x6238`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_InstallationID`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x6210`

## string_xrefs

- `0x621f`: `InstallationID is not specified in the config file.`
- `0x622b`: `InstallationID specified in the config file is not a GUID.`

## pseudocode

```c

```

## disassembly

```asm
0x6210  ldarg.0
0x6211  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_installationID
0x6216  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x621b  stloc.0
0x621c  leave.s  loc_6236
0x621e  pop
0x621f  ldstr    aInstallationid// "InstallationID is not specified in the "...
0x6224  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x6229  throw
0x622a  pop
0x622b  ldstr    aInstallationid_0// "InstallationID specified in the config "...
0x6230  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x6235  throw
0x6236  ldloc.0
0x6237  ret
```
