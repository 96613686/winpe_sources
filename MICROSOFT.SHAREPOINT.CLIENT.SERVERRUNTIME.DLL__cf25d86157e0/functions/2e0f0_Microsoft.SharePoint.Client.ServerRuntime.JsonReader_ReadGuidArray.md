# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadGuidArray

- ea: `0x2e0f0`
- end: `0x2e161`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadGuidArray`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e170`

## callees

- `0x16f10`
- `0x2d640`
- `0x2d8f0`
- `0x2e0f0`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2e112`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2e0f0  ldarg.0
0x2e0f1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e0f6  stloc.0
0x2e0f7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x2e0fc  stloc.1
0x2e0fd  ldloc.0
0x2e0fe  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e103  ldc.i4.s 0xB
0x2e105  bne.un.s loc_2E109
0x2e107  ldnull
0x2e108  ret
0x2e109  ldloc.0
0x2e10a  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e10f  ldc.i4.2
0x2e110  beq.s    loc_2E144
0x2e112  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2e117  ldc.i4.1
0x2e118  newarr   [mscorlib]System.Object
0x2e11d  stloc.2
0x2e11e  ldloc.2
0x2e11f  ldc.i4.0
0x2e120  ldloc.0
0x2e121  callvirt instance int32 Token::get_Position()
0x2e126  box      [mscorlib]System.Int32
0x2e12b  stelem.ref
0x2e12c  ldloc.2
0x2e12d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2e132  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e137  throw
0x2e138  ldloc.1
0x2e139  ldarg.0
0x2e13a  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadGuid()
0x2e13f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x2e144  ldarg.0
0x2e145  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2e14a  dup
0x2e14b  stloc.0
0x2e14c  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e151  ldc.i4.3
0x2e152  bne.un.s loc_2E138
0x2e154  ldarg.0
0x2e155  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2e15a  ldloc.1
0x2e15b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x2e160  ret
```
