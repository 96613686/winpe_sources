# Microsoft.ReportingServices.DataRendering.StringResources::get_ResourceManager

- ea: `0x30`
- end: `0x5b`
- name: `Microsoft.ReportingServices.DataRendering.StringResources::get_ResourceManager`
- size: `43`
- prototype: ``
- caller_count: `23`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x80`
- `0xa0`
- `0xc0`
- `0xe0`
- `0x100`
- `0x120`
- `0x140`
- `0x160`
- `0x180`
- `0x1a0`
- `0x1c0`
- `0x1e0`
- `0x200`
- `0x220`
- `0x240`
- `0x260`
- `0x280`
- `0x2a0`
- `0x2c0`
- `0x2e0`
- `0x300`
- `0x320`
- `0xccd0`

## callees

- `0x30`

## string_xrefs

- `0x37`: `Microsoft.ReportingServices.DataRendering.StringResources`

## pseudocode

```c

```

## disassembly

```asm
0x30  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.DataRendering.StringResources::resourceMan
0x35  brtrue.s loc_55
0x37  ldstr    aMicrosoftRepor// "Microsoft.ReportingServices.DataRenderi"...
0x3c  ldtoken  Microsoft.ReportingServices.DataRendering.StringResources
0x41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x4b  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x50  stsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.DataRendering.StringResources::resourceMan
0x55  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.DataRendering.StringResources::resourceMan
0x5a  ret
```
