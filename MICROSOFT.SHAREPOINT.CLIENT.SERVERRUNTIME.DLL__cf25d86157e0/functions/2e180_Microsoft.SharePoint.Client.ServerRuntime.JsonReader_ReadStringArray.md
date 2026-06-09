# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadStringArray

- ea: `0x2e180`
- end: `0x2e1f1`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadStringArray`
- size: `113`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e200`
- `0x2e290`

## callees

- `0x16f10`
- `0x2d6f0`
- `0x2d8f0`
- `0x2e180`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2e1a2`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2e180  ldarg.0
0x2e181  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e186  stloc.0
0x2e187  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2e18c  stloc.1
0x2e18d  ldloc.0
0x2e18e  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e193  ldc.i4.s 0xB
0x2e195  bne.un.s loc_2E199
0x2e197  ldnull
0x2e198  ret
0x2e199  ldloc.0
0x2e19a  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e19f  ldc.i4.2
0x2e1a0  beq.s    loc_2E1D4
0x2e1a2  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2e1a7  ldc.i4.1
0x2e1a8  newarr   [mscorlib]System.Object
0x2e1ad  stloc.2
0x2e1ae  ldloc.2
0x2e1af  ldc.i4.0
0x2e1b0  ldloc.0
0x2e1b1  callvirt instance int32 Token::get_Position()
0x2e1b6  box      [mscorlib]System.Int32
0x2e1bb  stelem.ref
0x2e1bc  ldloc.2
0x2e1bd  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2e1c2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e1c7  throw
0x2e1c8  ldloc.1
0x2e1c9  ldarg.0
0x2e1ca  call     instance string Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadString()
0x2e1cf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2e1d4  ldarg.0
0x2e1d5  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2e1da  dup
0x2e1db  stloc.0
0x2e1dc  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e1e1  ldc.i4.3
0x2e1e2  bne.un.s loc_2E1C8
0x2e1e4  ldarg.0
0x2e1e5  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2e1ea  ldloc.1
0x2e1eb  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x2e1f0  ret
```
