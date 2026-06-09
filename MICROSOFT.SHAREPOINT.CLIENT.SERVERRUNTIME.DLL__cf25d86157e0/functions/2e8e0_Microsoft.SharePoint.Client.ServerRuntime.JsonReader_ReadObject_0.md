# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObject_0

- ea: `0x2e8e0`
- end: `0x2ea68`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObject_0`
- size: `392`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e680`
- `0x2e8d0`
- `0x2ea80`

## callees

- `0x16f10`
- `0x2cf30`
- `0x2d690`
- `0x2e5e0`
- `0x2e8e0`
- `0x2ea80`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x30570`
- `0x305e0`
- `0x30620`
- `0x30660`
- `0x306a0`
- `0x306e0`
- `0x30720`

## string_xrefs

- `0x2ea42`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2e8e0  ldarg.0
0x2e8e1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2e8e6  stloc.0
0x2e8e7  ldloc.0
0x2e8e8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2e8ed  stloc.2
0x2e8ee  ldloc.2
0x2e8ef  switch   loc_2EA25, loc_2EA42, loc_2E9E7, loc_2EA42, loc_2E9D9, loc_2E99D, loc_2E98A, loc_2E977, loc_2E935, loc_2E964, loc_2E951, loc_2E948, loc_2EA42, loc_2EA2D, loc_2EA34
0x2e930  br       loc_2EA42
0x2e935  ldarg.0
0x2e936  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e93b  pop
0x2e93c  ldloc.0
0x2e93d  callvirt instance bool Token::get_BoolValue()
0x2e942  box      [mscorlib]System.Boolean
0x2e947  ret
0x2e948  ldarg.0
0x2e949  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e94e  pop
0x2e94f  ldnull
0x2e950  ret
0x2e951  ldarg.0
0x2e952  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e957  pop
0x2e958  ldloc.0
0x2e959  callvirt instance valuetype [mscorlib]System.Guid Token::get_GuidValue()
0x2e95e  box      [mscorlib]System.Guid
0x2e963  ret
0x2e964  ldarg.0
0x2e965  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e96a  pop
0x2e96b  ldloc.0
0x2e96c  callvirt instance valuetype [mscorlib]System.DateTime Token::get_DateTimeValue()
0x2e971  box      [mscorlib]System.DateTime
0x2e976  ret
0x2e977  ldarg.0
0x2e978  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e97d  pop
0x2e97e  ldloc.0
0x2e97f  callvirt instance float64 Token::get_DoubleValue()
0x2e984  box      [mscorlib]System.Double
0x2e989  ret
0x2e98a  ldarg.0
0x2e98b  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e990  pop
0x2e991  ldloc.0
0x2e992  callvirt instance unsigned int64 Token::get_ULongValue()
0x2e997  box      [mscorlib]System.UInt64
0x2e99c  ret
0x2e99d  ldarg.0
0x2e99e  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e9a3  pop
0x2e9a4  ldloc.0
0x2e9a5  callvirt instance int64 Token::get_LongValue()
0x2e9aa  ldc.i4   0x80000000
0x2e9af  conv.i8
0x2e9b0  blt.s    loc_2E9CD
0x2e9b2  ldloc.0
0x2e9b3  callvirt instance int64 Token::get_LongValue()
0x2e9b8  ldc.i4   0x7FFFFFFF
0x2e9bd  conv.i8
0x2e9be  bgt.s    loc_2E9CD
0x2e9c0  ldloc.0
0x2e9c1  callvirt instance int64 Token::get_LongValue()
0x2e9c6  conv.i4
0x2e9c7  box      [mscorlib]System.Int32
0x2e9cc  ret
0x2e9cd  ldloc.0
0x2e9ce  callvirt instance int64 Token::get_LongValue()
0x2e9d3  box      [mscorlib]System.Int64
0x2e9d8  ret
0x2e9d9  ldarg.0
0x2e9da  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2e9df  pop
0x2e9e0  ldloc.0
0x2e9e1  callvirt instance string Token::get_StringValue()
0x2e9e6  ret
0x2e9e7  ldnull
0x2e9e8  stloc.1
0x2e9e9  ldarg.1
0x2e9ea  ldnull
0x2e9eb  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2e9f0  brfalse.s loc_2EA1D
0x2e9f2  ldarg.1
0x2e9f3  ldtoken  [mscorlib]System.Object
0x2e9f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e9fd  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2ea02  brfalse.s loc_2EA1D
0x2ea04  ldtoken  [mscorlib]System.Collections.IEnumerable
0x2ea09  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ea0e  ldarg.1
0x2ea0f  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x2ea14  brfalse.s loc_2EA1D
0x2ea16  ldarg.1
0x2ea17  call     class [mscorlib]System.Type Microsoft.SharePoint.Utilities.ExpressionUtility::GetElementType(class [mscorlib]System.Type seqType)
0x2ea1c  stloc.1
0x2ea1d  ldarg.0
0x2ea1e  ldloc.1
0x2ea1f  call     instance object[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObjectArray(class [mscorlib]System.Type fallbackElementType)
0x2ea24  ret
0x2ea25  ldarg.0
0x2ea26  ldarg.1
0x2ea27  call     instance object Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadJsonObject(class [mscorlib]System.Type fallbackType)
0x2ea2c  ret
0x2ea2d  ldarg.0
0x2ea2e  call     instance unsigned int8[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadByteArray()
0x2ea33  ret
0x2ea34  ldarg.0
0x2ea35  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2ea3a  pop
0x2ea3b  ldloc.0
0x2ea3c  callvirt instance string Token::get_StringValue()
0x2ea41  ret
0x2ea42  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2ea47  ldc.i4.1
0x2ea48  newarr   [mscorlib]System.Object
0x2ea4d  stloc.3
0x2ea4e  ldloc.3
0x2ea4f  ldc.i4.0
0x2ea50  ldloc.0
0x2ea51  callvirt instance int32 Token::get_Position()
0x2ea56  box      [mscorlib]System.Int32
0x2ea5b  stelem.ref
0x2ea5c  ldloc.3
0x2ea5d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2ea62  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2ea67  throw
```
