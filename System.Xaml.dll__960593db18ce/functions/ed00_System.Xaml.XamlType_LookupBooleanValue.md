# System.Xaml.XamlType::LookupBooleanValue

- ea: `0xed00`
- end: `0xee0a`
- name: `System.Xaml.XamlType::LookupBooleanValue`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0xe910`

## callees

- `0x87c0`
- `0xd150`
- `0xdbe0`
- `0xdd80`
- `0xde30`
- `0xde40`
- `0xde50`
- `0xdeb0`
- `0xe360`
- `0xe380`
- `0xe390`
- `0xe590`
- `0xe5e0`
- `0xe990`
- `0xed00`
- `0x11f50`

## string_xrefs

- `0xedca`: `UsableDuringInitializationOnME`

## pseudocode

```c

```

## disassembly

```asm
0xed00  ldarg.1
0xed01  ldc.i4.s 0x20
0xed03  bgt.s    loc_ED39
0xed05  ldarg.1
0xed06  ldc.i4.8
0xed07  bgt.s    loc_ED2A
0xed09  ldarg.1
0xed0a  ldc.i4.1
0xed0b  sub
0xed0c  switch   loc_ED76, loc_EDEF, loc_EE01, loc_ED8B
0xed21  ldarg.1
0xed22  ldc.i4.8
0xed23  beq.s    loc_ED94
0xed25  br       loc_EE01
0xed2a  ldarg.1
0xed2b  ldc.i4.s 0x10
0xed2d  beq.s    loc_ED9D
0xed2f  ldarg.1
0xed30  ldc.i4.s 0x20
0xed32  beq.s    loc_ED82
0xed34  br       loc_EE01
0xed39  ldarg.1
0xed3a  ldc.i4   0x1000
0xed3f  bgt.s    loc_ED53
0xed41  ldarg.1
0xed42  ldc.i4.s 0x40
0xed44  beq.s    loc_EDA6
0xed46  ldarg.1
0xed47  ldc.i4   0x1000
0xed4c  beq.s    loc_EDAF
0xed4e  br       loc_EE01
0xed53  ldarg.1
0xed54  ldc.i4   0x2000
0xed59  beq      loc_EDE6
0xed5e  ldarg.1
0xed5f  ldc.i4   0x4000
0xed64  beq.s    loc_EDB8
0xed66  ldarg.1
0xed67  ldc.i4   0x8000
0xed6c  beq      loc_EDF8
0xed71  br       loc_EE01
0xed76  ldarg.0
0xed77  callvirt instance bool System.Xaml.XamlType::LookupIsConstructible()
0xed7c  stloc.0
0xed7d  br       loc_EE08
0xed82  ldarg.0
0xed83  callvirt instance bool System.Xaml.XamlType::LookupConstructionRequiresArguments()
0xed88  stloc.0
0xed89  br.s     loc_EE08
0xed8b  ldarg.0
0xed8c  callvirt instance bool System.Xaml.XamlType::LookupIsMarkupExtension()
0xed91  stloc.0
0xed92  br.s     loc_EE08
0xed94  ldarg.0
0xed95  callvirt instance bool System.Xaml.XamlType::LookupIsNullable()
0xed9a  stloc.0
0xed9b  br.s     loc_EE08
0xed9d  ldarg.0
0xed9e  callvirt instance bool System.Xaml.XamlType::LookupIsNameScope()
0xeda3  stloc.0
0xeda4  br.s     loc_EE08
0xeda6  ldarg.0
0xeda7  callvirt instance bool System.Xaml.XamlType::LookupIsPublic()
0xedac  stloc.0
0xedad  br.s     loc_EE08
0xedaf  ldarg.0
0xedb0  callvirt instance bool System.Xaml.XamlType::LookupTrimSurroundingWhitespace()
0xedb5  stloc.0
0xedb6  br.s     loc_EE08
0xedb8  ldarg.0
0xedb9  callvirt instance bool System.Xaml.XamlType::LookupUsableDuringInitialization()
0xedbe  stloc.0
0xedbf  ldloc.0
0xedc0  brfalse.s loc_EE08
0xedc2  ldarg.0
0xedc3  call     instance bool System.Xaml.XamlType::get_IsMarkupExtension()
0xedc8  brfalse.s loc_EE08
0xedca  ldstr    aUsableduringin// "UsableDuringInitializationOnME"
0xedcf  ldc.i4.1
0xedd0  newarr   [mscorlib]System.Object
0xedd5  dup
0xedd6  ldc.i4.0
0xedd7  ldarg.0
0xedd8  stelem.ref
0xedd9  call     string System.Xaml.SR::Get(string id, object[] args)
0xedde  stloc.1
0xeddf  ldloc.1
0xede0  newobj   instance void System.Xaml.XamlSchemaException::.ctor(string message)
0xede5  throw
0xede6  ldarg.0
0xede7  callvirt instance bool System.Xaml.XamlType::LookupIsWhitespaceSignificantCollection()
0xedec  stloc.0
0xeded  br.s     loc_EE08
0xedef  ldarg.0
0xedf0  callvirt instance bool System.Xaml.XamlType::LookupIsXData()
0xedf5  stloc.0
0xedf6  br.s     loc_EE08
0xedf8  ldarg.0
0xedf9  callvirt instance bool System.Xaml.XamlType::LookupIsAmbient()
0xedfe  stloc.0
0xedff  br.s     loc_EE08
0xee01  ldarg.1
0xee02  call     bool System.Xaml.XamlType::GetDefaultFlag(valuetype System.Xaml.BoolTypeBits flagBit)
0xee07  stloc.0
0xee08  ldloc.0
0xee09  ret
```
