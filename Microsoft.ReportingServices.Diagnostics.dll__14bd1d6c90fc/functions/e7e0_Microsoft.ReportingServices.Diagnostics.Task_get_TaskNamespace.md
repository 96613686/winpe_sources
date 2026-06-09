# Microsoft.ReportingServices.Diagnostics.Task::get_TaskNamespace

- ea: `0xe7e0`
- end: `0xe7f8`
- name: `Microsoft.ReportingServices.Diagnostics.Task::get_TaskNamespace`
- size: `24`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe800`
- `0xed50`
- `0xee10`
- `0xef10`
- `0xf030`
- `0xf290`

## callees

- `0xe7e0`

## pseudocode

```c

```

## disassembly

```asm
0xe7e0  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RequestContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext()
0xe7e5  brfalse.s loc_E7F2
0xe7e7  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RequestContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext()
0xe7ec  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RequestContext::get_Namespace()
0xe7f1  ret
0xe7f2  ldsfld   string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Common.XmlConsts::DefaultNamespace
0xe7f7  ret
```
