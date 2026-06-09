# GraphNodeComparer::Equals

- ea: `0x2330`
- end: `0x2348`
- name: `GraphNodeComparer::Equals`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xc40`
- `0x2330`

## pseudocode

```c

```

## disassembly

```asm
0x2330  ldarg.1
0x2331  ldarg.2
0x2332  bne.un.s loc_2336
0x2334  ldc.i4.1
0x2335  ret
0x2336  ldarg.1
0x2337  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::get_Dependency()
0x233c  ldarg.2
0x233d  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.GraphNode::get_Dependency()
0x2342  bne.un.s loc_2346
0x2344  ldc.i4.1
0x2345  ret
0x2346  ldc.i4.0
0x2347  ret
```
