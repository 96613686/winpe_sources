# Microsoft.Reporting.WebForms.WebConfigReader::.ctor

- ea: `0x1bb30`
- end: `0x1bb72`
- name: `Microsoft.Reporting.WebForms.WebConfigReader::.ctor`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1bb80`

## string_xrefs

- `0x1bb42`: `ReportViewerTemporaryStorage`
- `0x1bb47`: `ITemporaryStorage`

## pseudocode

```c

```

## disassembly

```asm
0x1bb30  ldarg.0
0x1bb31  ldnull
0x1bb32  ldstr    aIreportserverc// "IReportServerConnection"
0x1bb37  newobj   instance void class Microsoft.Reporting.WebForms.ConfigFilePropertyInterface`1<class Microsoft.Reporting.WebForms.IReportServerConnection>::.ctor(string, string)
0x1bb3c  stfld    class Microsoft.Reporting.WebForms.ConfigFilePropertyInterface`1<class Microsoft.Reporting.WebForms.IReportServerConnection> Microsoft.Reporting.WebForms.WebConfigReader::m_serverConnection
0x1bb41  ldarg.0
0x1bb42  ldstr    aReportviewerte// "ReportViewerTemporaryStorage"
0x1bb47  ldstr    aItemporarystor// "ITemporaryStorage"
0x1bb4c  newobj   instance void class Microsoft.Reporting.WebForms.ConfigFilePropertyInterface`1<class Microsoft.Reporting.WebForms.ITemporaryStorage>::.ctor(string, string)
0x1bb51  stfld    class Microsoft.Reporting.WebForms.ConfigFilePropertyInterface`1<class Microsoft.Reporting.WebForms.ITemporaryStorage> Microsoft.Reporting.WebForms.WebConfigReader::m_tempStorage
0x1bb56  ldarg.0
0x1bb57  ldstr    aReportviewerme// "ReportViewerMessages"
0x1bb5c  ldstr    aIreportviewerm// "IReportViewerMessages"
0x1bb61  newobj   instance void class Microsoft.Reporting.WebForms.ConfigFilePropertyInterface`1<class Microsoft.Reporting.WebForms.IReportViewerMessages>::.ctor(string, string)
0x1bb66  stfld    class Microsoft.Reporting.WebForms.ConfigFilePropertyInterface`1<class Microsoft.Reporting.WebForms.IReportViewerMessages> Microsoft.Reporting.WebForms.WebConfigReader::m_viewerMessages
0x1bb6b  ldarg.0
0x1bb6c  call     instance void [mscorlib]System.Object::.ctor()
0x1bb71  ret
```
