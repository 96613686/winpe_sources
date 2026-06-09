# Microsoft.Reporting.WebForms.WebConfigReader::get_ViewerMessages

- ea: `0x1bbe0`
- end: `0x1bbec`
- name: `Microsoft.Reporting.WebForms.WebConfigReader::get_ViewerMessages`
- size: `12`
- prototype: ``
- caller_count: `47`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4100`
- `0x4110`
- `0x4120`
- `0x4130`
- `0x4140`
- `0x4170`
- `0x41a0`
- `0x41d0`
- `0x4200`
- `0x4230`
- `0x4260`
- `0x4290`
- `0x42c0`
- `0x42f0`
- `0x4320`
- `0x4350`
- `0x4380`
- `0x43b0`
- `0x43e0`
- `0x4410`
- `0x4440`
- `0x4470`
- `0x44a0`
- `0x44d0`
- `0x4500`
- `0x4530`
- `0x4560`
- `0x4590`
- `0x45c0`
- `0x45f0`
- `0x4620`
- `0x4650`
- `0x4680`
- `0x46b0`
- `0x46e0`
- `0x4710`
- `0x4740`
- `0x4770`
- `0x47a0`
- `0x47d0`
- `0x4800`
- `0x4830`
- `0x4860`
- `0x4890`
- `0x48c0`
- `0x48f0`
- `0x4920`

## pseudocode

```c

```

## disassembly

```asm
0x1bbe0  ldarg.0
0x1bbe1  ldfld    class Microsoft.Reporting.WebForms.ConfigFilePropertyInterface`1<class Microsoft.Reporting.WebForms.IReportViewerMessages> Microsoft.Reporting.WebForms.WebConfigReader::m_viewerMessages
0x1bbe6  callvirt instance var<u1> class Microsoft.Reporting.WebForms.ConfigFilePropertyInterface`1<class Microsoft.Reporting.WebForms.IReportViewerMessages>::GetInstance()
0x1bbeb  ret
```
