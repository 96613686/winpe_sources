# Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_UrlRootCalculated

- ea: `0x6c70`
- end: `0x6c93`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_UrlRootCalculated`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x330`

## callees

- `0x6c70`

## string_xrefs

- `0x6c7f`: `The report server has found no valid URLs for the operation you are performing. Verify the <UrlRoot> entry in the �RSReportServer.config� file is configured correctly.`

## pseudocode

```c

```

## disassembly

```asm
0x6c70  ldnull
0x6c71  stloc.0
0x6c72  ldarg.0
0x6c73  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_urlRootCalculated
0x6c78  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6c7d  brfalse.s loc_6C8A
0x6c7f  ldstr    aTheReportServe// "The report server has found no valid UR"...
0x6c84  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(string)
0x6c89  throw
0x6c8a  ldarg.0
0x6c8b  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_urlRootCalculated
0x6c90  stloc.0
0x6c91  ldloc.0
0x6c92  ret
```
