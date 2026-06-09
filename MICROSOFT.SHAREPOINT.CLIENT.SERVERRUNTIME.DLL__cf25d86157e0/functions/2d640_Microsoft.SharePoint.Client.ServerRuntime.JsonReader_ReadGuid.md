# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadGuid

- ea: `0x2d640`
- end: `0x2d67e`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadGuid`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d680`
- `0x2e0f0`

## callees

- `0x16f10`
- `0x2d640`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x30720`

## string_xrefs

- `0x2d658`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d640  ldarg.0
0x2d641  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d646  stloc.0
0x2d647  ldloc.0
0x2d648  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d64d  ldc.i4.s 0xA
0x2d64f  bne.un.s loc_2D658
0x2d651  ldloc.0
0x2d652  callvirt instance valuetype [mscorlib]System.Guid Token::get_GuidValue()
0x2d657  ret
0x2d658  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d65d  ldc.i4.1
0x2d65e  newarr   [mscorlib]System.Object
0x2d663  stloc.1
0x2d664  ldloc.1
0x2d665  ldc.i4.0
0x2d666  ldloc.0
0x2d667  callvirt instance int32 Token::get_Position()
0x2d66c  box      [mscorlib]System.Int32
0x2d671  stelem.ref
0x2d672  ldloc.1
0x2d673  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d678  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d67d  throw
```
