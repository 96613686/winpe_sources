# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt16Array

- ea: `0x2db50`
- end: `0x2dbc1`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt16Array`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2dbd0`

## callees

- `0x16f10`
- `0x2d2a0`
- `0x2d8f0`
- `0x2db50`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2db72`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2db50  ldarg.0
0x2db51  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2db56  stloc.0
0x2db57  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int16>::.ctor()
0x2db5c  stloc.1
0x2db5d  ldloc.0
0x2db5e  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2db63  ldc.i4.s 0xB
0x2db65  bne.un.s loc_2DB69
0x2db67  ldnull
0x2db68  ret
0x2db69  ldloc.0
0x2db6a  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2db6f  ldc.i4.2
0x2db70  beq.s    loc_2DBA4
0x2db72  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2db77  ldc.i4.1
0x2db78  newarr   [mscorlib]System.Object
0x2db7d  stloc.2
0x2db7e  ldloc.2
0x2db7f  ldc.i4.0
0x2db80  ldloc.0
0x2db81  callvirt instance int32 Token::get_Position()
0x2db86  box      [mscorlib]System.Int32
0x2db8b  stelem.ref
0x2db8c  ldloc.2
0x2db8d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2db92  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2db97  throw
0x2db98  ldloc.1
0x2db99  ldarg.0
0x2db9a  call     instance unsigned int16 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt16()
0x2db9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int16>::Add(var<u1>)
0x2dba4  ldarg.0
0x2dba5  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2dbaa  dup
0x2dbab  stloc.0
0x2dbac  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dbb1  ldc.i4.3
0x2dbb2  bne.un.s loc_2DB98
0x2dbb4  ldarg.0
0x2dbb5  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2dbba  ldloc.1
0x2dbbb  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<unsigned int16>::ToArray()
0x2dbc0  ret
```
