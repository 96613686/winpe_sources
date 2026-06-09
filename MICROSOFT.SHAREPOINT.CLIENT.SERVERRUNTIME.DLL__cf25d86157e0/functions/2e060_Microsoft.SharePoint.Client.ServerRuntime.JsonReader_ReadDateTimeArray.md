# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDateTimeArray

- ea: `0x2e060`
- end: `0x2e0d1`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDateTimeArray`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e0e0`

## callees

- `0x16f10`
- `0x2d5f0`
- `0x2d8f0`
- `0x2e060`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2e082`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2e060  ldarg.0
0x2e061  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e066  stloc.0
0x2e067  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.DateTime>::.ctor()
0x2e06c  stloc.1
0x2e06d  ldloc.0
0x2e06e  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e073  ldc.i4.s 0xB
0x2e075  bne.un.s loc_2E079
0x2e077  ldnull
0x2e078  ret
0x2e079  ldloc.0
0x2e07a  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e07f  ldc.i4.2
0x2e080  beq.s    loc_2E0B4
0x2e082  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2e087  ldc.i4.1
0x2e088  newarr   [mscorlib]System.Object
0x2e08d  stloc.2
0x2e08e  ldloc.2
0x2e08f  ldc.i4.0
0x2e090  ldloc.0
0x2e091  callvirt instance int32 Token::get_Position()
0x2e096  box      [mscorlib]System.Int32
0x2e09b  stelem.ref
0x2e09c  ldloc.2
0x2e09d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2e0a2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e0a7  throw
0x2e0a8  ldloc.1
0x2e0a9  ldarg.0
0x2e0aa  call     instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDateTime()
0x2e0af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.DateTime>::Add(var<u1>)
0x2e0b4  ldarg.0
0x2e0b5  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2e0ba  dup
0x2e0bb  stloc.0
0x2e0bc  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e0c1  ldc.i4.3
0x2e0c2  bne.un.s loc_2E0A8
0x2e0c4  ldarg.0
0x2e0c5  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2e0ca  ldloc.1
0x2e0cb  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.DateTime>::ToArray()
0x2e0d0  ret
```
