# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt16Array

- ea: `0x2dac0`
- end: `0x2db31`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt16Array`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2db40`

## callees

- `0x16f10`
- `0x2d250`
- `0x2d8f0`
- `0x2dac0`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2dae2`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2dac0  ldarg.0
0x2dac1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2dac6  stloc.0
0x2dac7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int16>::.ctor()
0x2dacc  stloc.1
0x2dacd  ldloc.0
0x2dace  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dad3  ldc.i4.s 0xB
0x2dad5  bne.un.s loc_2DAD9
0x2dad7  ldnull
0x2dad8  ret
0x2dad9  ldloc.0
0x2dada  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dadf  ldc.i4.2
0x2dae0  beq.s    loc_2DB14
0x2dae2  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2dae7  ldc.i4.1
0x2dae8  newarr   [mscorlib]System.Object
0x2daed  stloc.2
0x2daee  ldloc.2
0x2daef  ldc.i4.0
0x2daf0  ldloc.0
0x2daf1  callvirt instance int32 Token::get_Position()
0x2daf6  box      [mscorlib]System.Int32
0x2dafb  stelem.ref
0x2dafc  ldloc.2
0x2dafd  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2db02  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2db07  throw
0x2db08  ldloc.1
0x2db09  ldarg.0
0x2db0a  call     instance int16 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt16()
0x2db0f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int16>::Add(var<u1>)
0x2db14  ldarg.0
0x2db15  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2db1a  dup
0x2db1b  stloc.0
0x2db1c  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2db21  ldc.i4.3
0x2db22  bne.un.s loc_2DB08
0x2db24  ldarg.0
0x2db25  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2db2a  ldloc.1
0x2db2b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<int16>::ToArray()
0x2db30  ret
```
