# Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_ResourceManager

- ea: `0x144c0`
- end: `0x144eb`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_ResourceManager`
- size: `43`
- prototype: ``
- caller_count: `70`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14510`
- `0x14530`
- `0x14550`
- `0x14570`
- `0x14590`
- `0x145b0`
- `0x145d0`
- `0x145f0`
- `0x14610`
- `0x14630`
- `0x14650`
- `0x14670`
- `0x14690`
- `0x146b0`
- `0x146d0`
- `0x146f0`
- `0x14710`
- `0x14730`
- `0x14750`
- `0x14770`
- `0x14790`
- `0x147b0`
- `0x147d0`
- `0x147f0`
- `0x14810`
- `0x14830`
- `0x14850`
- `0x14870`
- `0x14890`
- `0x148b0`
- `0x148d0`
- `0x148f0`
- `0x14910`
- `0x14930`
- `0x14950`
- `0x14970`
- `0x14990`
- `0x149b0`
- `0x149d0`
- `0x149f0`
- `0x14a10`
- `0x14a30`
- `0x14a50`
- `0x14a70`
- `0x14a90`
- `0x14ab0`
- `0x14ad0`
- `0x14af0`
- `0x14b10`
- `0x14b30`

## callees

- `0x144c0`

## string_xrefs

- `0x144c7`: `Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes`

## pseudocode

```c

```

## disassembly

```asm
0x144c0  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::resourceMan
0x144c5  brtrue.s loc_144E5
0x144c7  ldstr    aMicrosoftRepor_52// "Microsoft.ReportingServices.ProcessingR"...
0x144cc  ldtoken  Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes
0x144d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x144d6  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x144db  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x144e0  stsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::resourceMan
0x144e5  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::resourceMan
0x144ea  ret
```
