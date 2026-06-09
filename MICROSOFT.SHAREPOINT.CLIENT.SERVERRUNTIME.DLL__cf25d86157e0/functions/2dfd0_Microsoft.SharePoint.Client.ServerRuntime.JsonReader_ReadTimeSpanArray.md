# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTimeSpanArray

- ea: `0x2dfd0`
- end: `0x2e041`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTimeSpanArray`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e050`

## callees

- `0x16f10`
- `0x2d590`
- `0x2d8f0`
- `0x2dfd0`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2dff2`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2dfd0  ldarg.0
0x2dfd1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2dfd6  stloc.0
0x2dfd7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TimeSpan>::.ctor()
0x2dfdc  stloc.1
0x2dfdd  ldloc.0
0x2dfde  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dfe3  ldc.i4.s 0xB
0x2dfe5  bne.un.s loc_2DFE9
0x2dfe7  ldnull
0x2dfe8  ret
0x2dfe9  ldloc.0
0x2dfea  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dfef  ldc.i4.2
0x2dff0  beq.s    loc_2E024
0x2dff2  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2dff7  ldc.i4.1
0x2dff8  newarr   [mscorlib]System.Object
0x2dffd  stloc.2
0x2dffe  ldloc.2
0x2dfff  ldc.i4.0
0x2e000  ldloc.0
0x2e001  callvirt instance int32 Token::get_Position()
0x2e006  box      [mscorlib]System.Int32
0x2e00b  stelem.ref
0x2e00c  ldloc.2
0x2e00d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2e012  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2e017  throw
0x2e018  ldloc.1
0x2e019  ldarg.0
0x2e01a  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTimeSpan()
0x2e01f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TimeSpan>::Add(var<u1>)
0x2e024  ldarg.0
0x2e025  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2e02a  dup
0x2e02b  stloc.0
0x2e02c  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e031  ldc.i4.3
0x2e032  bne.un.s loc_2E018
0x2e034  ldarg.0
0x2e035  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2e03a  ldloc.1
0x2e03b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.TimeSpan>::ToArray()
0x2e040  ret
```
