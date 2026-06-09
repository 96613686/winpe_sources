# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekObjectType

- ea: `0x2d7d0`
- end: `0x2d89c`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekObjectType`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x16f10`
- `0x2d7d0`
- `0x2eb10`
- `0x30550`
- `0x30560`
- `0x30570`

## string_xrefs

- `0x2d7e3`: `JsonDataTypeNotMatch`
- `0x2d81b`: `JsonDataTypeNotMatch`
- `0x2d867`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d7d0  ldarg.1
0x2d7d1  ldnull
0x2d7d2  stind.ref
0x2d7d3  ldarg.0
0x2d7d4  ldc.i4.0
0x2d7d5  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken(int32 tokenPosition)
0x2d7da  stloc.0
0x2d7db  ldloc.0
0x2d7dc  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d7e1  brfalse.s loc_2D809
0x2d7e3  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d7e8  ldc.i4.1
0x2d7e9  newarr   [mscorlib]System.Object
0x2d7ee  stloc.3
0x2d7ef  ldloc.3
0x2d7f0  ldc.i4.0
0x2d7f1  ldloc.0
0x2d7f2  callvirt instance int32 Token::get_Position()
0x2d7f7  box      [mscorlib]System.Int32
0x2d7fc  stelem.ref
0x2d7fd  ldloc.3
0x2d7fe  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d803  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d808  throw
0x2d809  ldarg.0
0x2d80a  ldc.i4.1
0x2d80b  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken(int32 tokenPosition)
0x2d810  stloc.1
0x2d811  ldloc.1
0x2d812  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d817  ldc.i4.s 0xC
0x2d819  beq.s    loc_2D844
0x2d81b  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d820  ldc.i4.1
0x2d821  newarr   [mscorlib]System.Object
0x2d826  stloc.s  4
0x2d828  ldloc.s  4
0x2d82a  ldc.i4.0
0x2d82b  ldloc.1
0x2d82c  callvirt instance int32 Token::get_Position()
0x2d831  box      [mscorlib]System.Int32
0x2d836  stelem.ref
0x2d837  ldloc.s  4
0x2d839  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d83e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d843  throw
0x2d844  ldloc.1
0x2d845  callvirt instance string Token::get_StringValue()
0x2d84a  ldstr    aObjecttype// "_ObjectType_"
0x2d84f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d854  brfalse.s loc_2D89A
0x2d856  ldarg.0
0x2d857  ldc.i4.2
0x2d858  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken(int32 tokenPosition)
0x2d85d  stloc.2
0x2d85e  ldloc.2
0x2d85f  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d864  ldc.i4.4
0x2d865  beq.s    loc_2D890
0x2d867  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d86c  ldc.i4.1
0x2d86d  newarr   [mscorlib]System.Object
0x2d872  stloc.s  5
0x2d874  ldloc.s  5
0x2d876  ldc.i4.0
0x2d877  ldloc.2
0x2d878  callvirt instance int32 Token::get_Position()
0x2d87d  box      [mscorlib]System.Int32
0x2d882  stelem.ref
0x2d883  ldloc.s  5
0x2d885  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d88a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d88f  throw
0x2d890  ldarg.1
0x2d891  ldloc.2
0x2d892  callvirt instance string Token::get_StringValue()
0x2d897  stind.ref
0x2d898  ldc.i4.1
0x2d899  ret
0x2d89a  ldc.i4.0
0x2d89b  ret
```
