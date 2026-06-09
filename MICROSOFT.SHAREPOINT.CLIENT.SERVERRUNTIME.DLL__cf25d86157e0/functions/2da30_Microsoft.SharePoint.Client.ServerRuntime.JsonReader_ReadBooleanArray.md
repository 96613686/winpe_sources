# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadBooleanArray

- ea: `0x2da30`
- end: `0x2daa1`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadBooleanArray`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2dab0`

## callees

- `0x16f10`
- `0x2d150`
- `0x2d8f0`
- `0x2da30`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2da52`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2da30  ldarg.0
0x2da31  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2da36  stloc.0
0x2da37  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<bool>::.ctor()
0x2da3c  stloc.1
0x2da3d  ldloc.0
0x2da3e  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2da43  ldc.i4.s 0xB
0x2da45  bne.un.s loc_2DA49
0x2da47  ldnull
0x2da48  ret
0x2da49  ldloc.0
0x2da4a  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2da4f  ldc.i4.2
0x2da50  beq.s    loc_2DA84
0x2da52  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2da57  ldc.i4.1
0x2da58  newarr   [mscorlib]System.Object
0x2da5d  stloc.2
0x2da5e  ldloc.2
0x2da5f  ldc.i4.0
0x2da60  ldloc.0
0x2da61  callvirt instance int32 Token::get_Position()
0x2da66  box      [mscorlib]System.Int32
0x2da6b  stelem.ref
0x2da6c  ldloc.2
0x2da6d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2da72  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2da77  throw
0x2da78  ldloc.1
0x2da79  ldarg.0
0x2da7a  call     instance bool Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadBoolean()
0x2da7f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<bool>::Add(var<u1>)
0x2da84  ldarg.0
0x2da85  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2da8a  dup
0x2da8b  stloc.0
0x2da8c  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2da91  ldc.i4.3
0x2da92  bne.un.s loc_2DA78
0x2da94  ldarg.0
0x2da95  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2da9a  ldloc.1
0x2da9b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<bool>::ToArray()
0x2daa0  ret
```
