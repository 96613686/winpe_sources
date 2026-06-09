# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt64

- ea: `0x2d3e0`
- end: `0x2d42d`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt64`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d430`
- `0x2dd90`

## callees

- `0x16f10`
- `0x2d3e0`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x305e0`
- `0x30620`

## string_xrefs

- `0x2d407`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d3e0  ldarg.0
0x2d3e1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d3e6  stloc.0
0x2d3e7  ldloc.0
0x2d3e8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d3ed  ldc.i4.5
0x2d3ee  bne.un.s loc_2D3F7
0x2d3f0  ldloc.0
0x2d3f1  callvirt instance int64 Token::get_LongValue()
0x2d3f6  ret
0x2d3f7  ldloc.0
0x2d3f8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d3fd  ldc.i4.6
0x2d3fe  bne.un.s loc_2D407
0x2d400  ldloc.0
0x2d401  callvirt instance unsigned int64 Token::get_ULongValue()
0x2d406  ret
0x2d407  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d40c  ldc.i4.1
0x2d40d  newarr   [mscorlib]System.Object
0x2d412  stloc.1
0x2d413  ldloc.1
0x2d414  ldc.i4.0
0x2d415  ldloc.0
0x2d416  callvirt instance int32 Token::get_Position()
0x2d41b  box      [mscorlib]System.Int32
0x2d420  stelem.ref
0x2d421  ldloc.1
0x2d422  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d427  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d42c  throw
```
