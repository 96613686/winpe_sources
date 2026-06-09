# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt64Array

- ea: `0x2dd00`
- end: `0x2dd71`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt64Array`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2dd80`

## callees

- `0x16f10`
- `0x2d390`
- `0x2d8f0`
- `0x2dd00`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2dd22`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2dd00  ldarg.0
0x2dd01  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2dd06  stloc.0
0x2dd07  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int64>::.ctor()
0x2dd0c  stloc.1
0x2dd0d  ldloc.0
0x2dd0e  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dd13  ldc.i4.s 0xB
0x2dd15  bne.un.s loc_2DD19
0x2dd17  ldnull
0x2dd18  ret
0x2dd19  ldloc.0
0x2dd1a  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dd1f  ldc.i4.2
0x2dd20  beq.s    loc_2DD54
0x2dd22  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2dd27  ldc.i4.1
0x2dd28  newarr   [mscorlib]System.Object
0x2dd2d  stloc.2
0x2dd2e  ldloc.2
0x2dd2f  ldc.i4.0
0x2dd30  ldloc.0
0x2dd31  callvirt instance int32 Token::get_Position()
0x2dd36  box      [mscorlib]System.Int32
0x2dd3b  stelem.ref
0x2dd3c  ldloc.2
0x2dd3d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2dd42  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2dd47  throw
0x2dd48  ldloc.1
0x2dd49  ldarg.0
0x2dd4a  call     instance int64 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt64()
0x2dd4f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int64>::Add(var<u1>)
0x2dd54  ldarg.0
0x2dd55  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2dd5a  dup
0x2dd5b  stloc.0
0x2dd5c  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dd61  ldc.i4.3
0x2dd62  bne.un.s loc_2DD48
0x2dd64  ldarg.0
0x2dd65  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2dd6a  ldloc.1
0x2dd6b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<int64>::ToArray()
0x2dd70  ret
```
