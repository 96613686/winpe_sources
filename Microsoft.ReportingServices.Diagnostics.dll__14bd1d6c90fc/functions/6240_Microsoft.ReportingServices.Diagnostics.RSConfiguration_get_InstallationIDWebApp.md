# Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_InstallationIDWebApp

- ea: `0x6240`
- end: `0x6268`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_InstallationIDWebApp`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x6240`

## string_xrefs

- `0x624f`: `InstallationID is not specified in the config file.`
- `0x625b`: `InstallationID specified in the config file is not a GUID.`

## pseudocode

```c

```

## disassembly

```asm
0x6240  ldarg.0
0x6241  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_installationIDWebApp
0x6246  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x624b  stloc.0
0x624c  leave.s  loc_6266
0x624e  pop
0x624f  ldstr    aInstallationid// "InstallationID is not specified in the "...
0x6254  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x6259  throw
0x625a  pop
0x625b  ldstr    aInstallationid_0// "InstallationID specified in the config "...
0x6260  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x6265  throw
0x6266  ldloc.0
0x6267  ret
```
