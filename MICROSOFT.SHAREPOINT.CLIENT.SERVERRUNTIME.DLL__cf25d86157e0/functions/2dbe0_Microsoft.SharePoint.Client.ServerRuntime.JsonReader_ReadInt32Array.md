# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt32Array

- ea: `0x2dbe0`
- end: `0x2dc51`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt32Array`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2dc60`

## callees

- `0x16f10`
- `0x2d2f0`
- `0x2d8f0`
- `0x2dbe0`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2dc02`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2dbe0  ldarg.0
0x2dbe1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2dbe6  stloc.0
0x2dbe7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x2dbec  stloc.1
0x2dbed  ldloc.0
0x2dbee  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dbf3  ldc.i4.s 0xB
0x2dbf5  bne.un.s loc_2DBF9
0x2dbf7  ldnull
0x2dbf8  ret
0x2dbf9  ldloc.0
0x2dbfa  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dbff  ldc.i4.2
0x2dc00  beq.s    loc_2DC34
0x2dc02  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2dc07  ldc.i4.1
0x2dc08  newarr   [mscorlib]System.Object
0x2dc0d  stloc.2
0x2dc0e  ldloc.2
0x2dc0f  ldc.i4.0
0x2dc10  ldloc.0
0x2dc11  callvirt instance int32 Token::get_Position()
0x2dc16  box      [mscorlib]System.Int32
0x2dc1b  stelem.ref
0x2dc1c  ldloc.2
0x2dc1d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2dc22  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2dc27  throw
0x2dc28  ldloc.1
0x2dc29  ldarg.0
0x2dc2a  call     instance int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt32()
0x2dc2f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x2dc34  ldarg.0
0x2dc35  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2dc3a  dup
0x2dc3b  stloc.0
0x2dc3c  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dc41  ldc.i4.3
0x2dc42  bne.un.s loc_2DC28
0x2dc44  ldarg.0
0x2dc45  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2dc4a  ldloc.1
0x2dc4b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<int32>::ToArray()
0x2dc50  ret
```
