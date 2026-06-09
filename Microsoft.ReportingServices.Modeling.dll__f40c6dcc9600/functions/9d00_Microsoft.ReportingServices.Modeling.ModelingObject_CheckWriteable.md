# Microsoft.ReportingServices.Modeling.ModelingObject::CheckWriteable

- ea: `0x9d00`
- end: `0x9d14`
- name: `Microsoft.ReportingServices.Modeling.ModelingObject::CheckWriteable`
- size: `20`
- prototype: ``
- caller_count: `98`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9d30`
- `0x9ee0`
- `0xcd70`
- `0xce90`
- `0xd670`
- `0xd6a0`
- `0xd6c0`
- `0xd6e0`
- `0xd700`
- `0xee60`
- `0xeea0`
- `0xeec0`
- `0xeee0`
- `0xef00`
- `0xef20`
- `0xefa0`
- `0xf020`
- `0xf060`
- `0xf090`
- `0xf0c0`
- `0xf110`
- `0xf150`
- `0xf170`
- `0xf190`
- `0xf210`
- `0xf230`
- `0xf260`
- `0x105a0`
- `0x10670`
- `0x106a0`
- `0x10710`
- `0x10750`
- `0x108b0`
- `0x108d0`
- `0x117b0`
- `0x11fa0`
- `0x11fd0`
- `0x12990`
- `0x13080`
- `0x138f0`
- `0x13a20`
- `0x13a70`
- `0x13aa0`
- `0x13ad0`
- `0x13e10`
- `0x13e80`
- `0x14590`
- `0x15300`
- `0x15360`
- `0x153a0`

## callees

- `0x95e0`
- `0x9d00`

## pseudocode

```c

```

## disassembly

```asm
0x9d00  ldarg.0
0x9d01  ldfld    bool Microsoft.ReportingServices.Modeling.ModelingObject::m_compiled
0x9d06  brfalse.s loc_9D13
0x9d08  call     string Microsoft.ReportingServices.Modeling.DevExceptionMessages::get_ReadOnly()
0x9d0d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9d12  throw
0x9d13  ret
```
