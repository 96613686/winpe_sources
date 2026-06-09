# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadEnum

- ea: `0x2d750`
- end: `0x2d7b4`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadEnum`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x16f10`
- `0x2d750`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x305e0`

## string_xrefs

- `0x2d78e`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d750  ldarg.0
0x2d751  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d756  stloc.0
0x2d757  ldloc.0
0x2d758  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d75d  ldc.i4.5
0x2d75e  bne.un.s loc_2D78E
0x2d760  ldtoken  mvar<u1>
0x2d765  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d76a  call     class [mscorlib]System.Type [mscorlib]System.Enum::GetUnderlyingType(class [mscorlib]System.Type)
0x2d76f  stloc.1
0x2d770  ldloc.0
0x2d771  callvirt instance int64 Token::get_LongValue()
0x2d776  box      [mscorlib]System.Int64
0x2d77b  ldloc.1
0x2d77c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2d781  call     object [mscorlib]System.Convert::ChangeType(object, class [mscorlib]System.Type, class [mscorlib]System.IFormatProvider)
0x2d786  stloc.2
0x2d787  ldloc.2
0x2d788  unbox.any mvar<u1>
0x2d78d  ret
0x2d78e  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d793  ldc.i4.1
0x2d794  newarr   [mscorlib]System.Object
0x2d799  stloc.3
0x2d79a  ldloc.3
0x2d79b  ldc.i4.0
0x2d79c  ldloc.0
0x2d79d  callvirt instance int32 Token::get_Position()
0x2d7a2  box      [mscorlib]System.Int32
0x2d7a7  stelem.ref
0x2d7a8  ldloc.3
0x2d7a9  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d7ae  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d7b3  throw
```
