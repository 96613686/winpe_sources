# Microsoft.ReportingServices.Modeling.ModelItem::get_Model

- ea: `0x13af0`
- end: `0x13b06`
- name: `Microsoft.ReportingServices.Modeling.ModelItem::get_Model`
- size: `22`
- prototype: ``
- caller_count: `23`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xf0e0`
- `0xf1b0`
- `0x106b0`
- `0x10770`
- `0x107a0`
- `0x107d0`
- `0x10830`
- `0x10860`
- `0x10920`
- `0x10980`
- `0x126f0`
- `0x130d0`
- `0x13a20`
- `0x13ae0`
- `0x13af0`
- `0x13e10`
- `0x14a30`
- `0x14f60`
- `0x14fb0`
- `0x15010`
- `0x15960`
- `0x173d0`
- `0x17440`

## callees

- `0x13af0`

## pseudocode

```c

```

## disassembly

```asm
0x13af0  ldarg.0
0x13af1  ldfld    class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.ModelItem::m_parentItem
0x13af6  brfalse.s loc_13B04
0x13af8  ldarg.0
0x13af9  ldfld    class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.ModelItem::m_parentItem
0x13afe  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelItem::get_Model()
0x13b03  ret
0x13b04  ldnull
0x13b05  ret
```
