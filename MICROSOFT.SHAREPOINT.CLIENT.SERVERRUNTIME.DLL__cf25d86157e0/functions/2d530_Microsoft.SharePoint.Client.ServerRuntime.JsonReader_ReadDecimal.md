# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDecimal

- ea: `0x2d530`
- end: `0x2d577`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDecimal`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d580`
- `0x2df40`

## callees

- `0x16f10`
- `0x2d530`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x30570`

## string_xrefs

- `0x2d551`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d530  ldarg.0
0x2d531  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d536  stloc.0
0x2d537  ldloc.0
0x2d538  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d53d  ldc.i4.4
0x2d53e  bne.un.s loc_2D551
0x2d540  ldloc.0
0x2d541  callvirt instance string Token::get_StringValue()
0x2d546  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2d54b  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::Parse(string, class [mscorlib]System.IFormatProvider)
0x2d550  ret
0x2d551  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d556  ldc.i4.1
0x2d557  newarr   [mscorlib]System.Object
0x2d55c  stloc.1
0x2d55d  ldloc.1
0x2d55e  ldc.i4.0
0x2d55f  ldloc.0
0x2d560  callvirt instance int32 Token::get_Position()
0x2d565  box      [mscorlib]System.Int32
0x2d56a  stelem.ref
0x2d56b  ldloc.1
0x2d56c  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d571  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d576  throw
```
