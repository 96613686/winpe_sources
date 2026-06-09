# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadByteArray

- ea: `0x2d690`
- end: `0x2d6da`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadByteArray`
- size: `74`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d6e0`
- `0x2e800`
- `0x2e8e0`

## callees

- `0x16f10`
- `0x2d690`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x30760`

## string_xrefs

- `0x2d6b4`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d690  ldarg.0
0x2d691  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d696  stloc.0
0x2d697  ldloc.0
0x2d698  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d69d  ldc.i4.s 0xB
0x2d69f  bne.un.s loc_2D6A3
0x2d6a1  ldnull
0x2d6a2  ret
0x2d6a3  ldloc.0
0x2d6a4  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d6a9  ldc.i4.s 0xD
0x2d6ab  bne.un.s loc_2D6B4
0x2d6ad  ldloc.0
0x2d6ae  callvirt instance unsigned int8[] Token::get_ByteArrayValue()
0x2d6b3  ret
0x2d6b4  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d6b9  ldc.i4.1
0x2d6ba  newarr   [mscorlib]System.Object
0x2d6bf  stloc.1
0x2d6c0  ldloc.1
0x2d6c1  ldc.i4.0
0x2d6c2  ldloc.0
0x2d6c3  callvirt instance int32 Token::get_Position()
0x2d6c8  box      [mscorlib]System.Int32
0x2d6cd  stelem.ref
0x2d6ce  ldloc.1
0x2d6cf  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d6d4  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d6d9  throw
```
