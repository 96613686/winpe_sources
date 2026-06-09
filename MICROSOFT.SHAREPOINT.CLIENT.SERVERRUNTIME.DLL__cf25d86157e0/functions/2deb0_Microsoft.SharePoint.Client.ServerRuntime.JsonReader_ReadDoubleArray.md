# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDoubleArray

- ea: `0x2deb0`
- end: `0x2df21`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDoubleArray`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2df30`

## callees

- `0x16f10`
- `0x2d4c0`
- `0x2d8f0`
- `0x2deb0`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2ded2`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2deb0  ldarg.0
0x2deb1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2deb6  stloc.0
0x2deb7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<float64>::.ctor()
0x2debc  stloc.1
0x2debd  ldloc.0
0x2debe  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dec3  ldc.i4.s 0xB
0x2dec5  bne.un.s loc_2DEC9
0x2dec7  ldnull
0x2dec8  ret
0x2dec9  ldloc.0
0x2deca  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2decf  ldc.i4.2
0x2ded0  beq.s    loc_2DF04
0x2ded2  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2ded7  ldc.i4.1
0x2ded8  newarr   [mscorlib]System.Object
0x2dedd  stloc.2
0x2dede  ldloc.2
0x2dedf  ldc.i4.0
0x2dee0  ldloc.0
0x2dee1  callvirt instance int32 Token::get_Position()
0x2dee6  box      [mscorlib]System.Int32
0x2deeb  stelem.ref
0x2deec  ldloc.2
0x2deed  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2def2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2def7  throw
0x2def8  ldloc.1
0x2def9  ldarg.0
0x2defa  call     instance float64 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDouble()
0x2deff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<float64>::Add(var<u1>)
0x2df04  ldarg.0
0x2df05  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2df0a  dup
0x2df0b  stloc.0
0x2df0c  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2df11  ldc.i4.3
0x2df12  bne.un.s loc_2DEF8
0x2df14  ldarg.0
0x2df15  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2df1a  ldloc.1
0x2df1b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<float64>::ToArray()
0x2df20  ret
```
