# Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer

- ea: `0x10310`
- end: `0x10316`
- name: `Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer`
- size: `6`
- prototype: ``
- caller_count: `21`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xaea0`
- `0xb030`
- `0xb100`
- `0xd460`
- `0xd4a0`
- `0xd510`
- `0xd9a0`
- `0xda50`
- `0xdad0`
- `0xdc10`
- `0xddd0`
- `0xe0f0`
- `0xe120`
- `0xe140`
- `0xe160`
- `0xe1c0`
- `0xe540`
- `0xe6f0`
- `0xe780`
- `0xe810`
- `0xe880`

## pseudocode

```c

```

## disassembly

```asm
0x10310  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::m_jobsTracer
0x10315  ret
```
