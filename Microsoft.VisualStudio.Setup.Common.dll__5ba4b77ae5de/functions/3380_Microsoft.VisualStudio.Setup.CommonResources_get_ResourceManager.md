# Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager

- ea: `0x3380`
- end: `0x33ab`
- name: `Microsoft.VisualStudio.Setup.CommonResources::get_ResourceManager`
- size: `43`
- prototype: ``
- caller_count: `79`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x33d0`
- `0x33f0`
- `0x3410`
- `0x3430`
- `0x3450`
- `0x3470`
- `0x3490`
- `0x34b0`
- `0x34d0`
- `0x34f0`
- `0x3510`
- `0x3530`
- `0x3550`
- `0x3570`
- `0x3590`
- `0x35b0`
- `0x35d0`
- `0x35f0`
- `0x3610`
- `0x3630`
- `0x3650`
- `0x3670`
- `0x3690`
- `0x36b0`
- `0x36d0`
- `0x36f0`
- `0x3710`
- `0x3730`
- `0x3750`
- `0x3770`
- `0x3790`
- `0x37b0`
- `0x37d0`
- `0x37f0`
- `0x3810`
- `0x3830`
- `0x3850`
- `0x3870`
- `0x3890`
- `0x38b0`
- `0x38d0`
- `0x38f0`
- `0x3910`
- `0x3930`
- `0x3950`
- `0x3970`
- `0x3990`
- `0x39b0`
- `0x39d0`
- `0x39f0`

## callees

- `0x3380`

## string_xrefs

- `0x3387`: `Microsoft.VisualStudio.Setup.CommonResources`

## pseudocode

```c

```

## disassembly

```asm
0x3380  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::resourceMan
0x3385  brtrue.s loc_33A5
0x3387  ldstr    aMicrosoftVisua// "Microsoft.VisualStudio.Setup.CommonReso"...
0x338c  ldtoken  Microsoft.VisualStudio.Setup.CommonResources
0x3391  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3396  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x339b  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x33a0  stsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::resourceMan
0x33a5  ldsfld   class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.CommonResources::resourceMan
0x33aa  ret
```
