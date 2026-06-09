# Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_BaseConnectionString

- ea: `0x3bb0`
- end: `0x3bda`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_BaseConnectionString`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3b80`
- `0x3bb0`

## string_xrefs

- `0x3bbe`: `No DSN present in configuration file`

## pseudocode

```c

```

## disassembly

```asm
0x3bb0  ldarg.0
0x3bb1  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_dsn
0x3bb6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3bbb  brfalse.s loc_3BC9
0x3bbd  ldnull
0x3bbe  ldstr    aNoDsnPresentIn// "No DSN present in configuration file"
0x3bc3  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x3bc8  throw
0x3bc9  ldarg.0
0x3bca  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_dsn
0x3bcf  ldstr    aDsn// "Dsn"
0x3bd4  call     string Microsoft.ReportingServices.Diagnostics.RSConfiguration::DecryptConfigData(string encryptedData, string element)
0x3bd9  ret
```
