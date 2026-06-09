# System.Xml.Serialization.XmlCustomFormatter::ToDefaultValue

- ea: `0x78b70`
- end: `0x78c25`
- name: `System.Xml.Serialization.XmlCustomFormatter::ToDefaultValue`
- size: `181`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x76740`
- `0x84140`

## callees

- `0x622f0`
- `0x78b70`
- `0x78c30`
- `0x78c60`
- `0x78c70`
- `0x78cb0`
- `0x78cc0`
- `0x78cd0`
- `0x78ce0`

## string_xrefs

- `0x78bbc`: `XmlName`
- `0x78bd0`: `XmlNCName`
- `0x78be4`: `XmlNmToken`
- `0x78bf8`: `XmlNmTokens`
- `0x78c0b`: `XmlUnsupportedDefaultValue`

## pseudocode

```c

```

## disassembly

```asm
0x78b70  ldarg.1
0x78b71  ldstr    aDatetime// "DateTime"
0x78b76  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78b7b  brfalse.s loc_78B89
0x78b7d  ldarg.0
0x78b7e  call     valuetype [mscorlib]System.DateTime System.Xml.Serialization.XmlCustomFormatter::ToDateTime(string value)
0x78b83  box      [mscorlib]System.DateTime
0x78b88  ret
0x78b89  ldarg.1
0x78b8a  ldstr    aDate_0// "Date"
0x78b8f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78b94  brfalse.s loc_78BA2
0x78b96  ldarg.0
0x78b97  call     valuetype [mscorlib]System.DateTime System.Xml.Serialization.XmlCustomFormatter::ToDate(string value)
0x78b9c  box      [mscorlib]System.DateTime
0x78ba1  ret
0x78ba2  ldarg.1
0x78ba3  ldstr    aTime_0// "Time"
0x78ba8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78bad  brfalse.s loc_78BBB
0x78baf  ldarg.0
0x78bb0  call     valuetype [mscorlib]System.DateTime System.Xml.Serialization.XmlCustomFormatter::ToTime(string value)
0x78bb5  box      [mscorlib]System.DateTime
0x78bba  ret
0x78bbb  ldarg.1
0x78bbc  ldstr    aXmlname// "XmlName"
0x78bc1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78bc6  brfalse.s loc_78BCF
0x78bc8  ldarg.0
0x78bc9  call     string System.Xml.Serialization.XmlCustomFormatter::ToXmlName(string value)
0x78bce  ret
0x78bcf  ldarg.1
0x78bd0  ldstr    aXmlncname// "XmlNCName"
0x78bd5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78bda  brfalse.s loc_78BE3
0x78bdc  ldarg.0
0x78bdd  call     string System.Xml.Serialization.XmlCustomFormatter::ToXmlNCName(string value)
0x78be2  ret
0x78be3  ldarg.1
0x78be4  ldstr    aXmlnmtoken// "XmlNmToken"
0x78be9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78bee  brfalse.s loc_78BF7
0x78bf0  ldarg.0
0x78bf1  call     string System.Xml.Serialization.XmlCustomFormatter::ToXmlNmToken(string value)
0x78bf6  ret
0x78bf7  ldarg.1
0x78bf8  ldstr    aXmlnmtokens// "XmlNmTokens"
0x78bfd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78c02  brfalse.s loc_78C0B
0x78c04  ldarg.0
0x78c05  call     string System.Xml.Serialization.XmlCustomFormatter::ToXmlNmTokens(string value)
0x78c0a  ret
0x78c0b  ldstr    aXmlunsupported_9// "XmlUnsupportedDefaultValue"
0x78c10  ldc.i4.1
0x78c11  newarr   [mscorlib]System.Object
0x78c16  dup
0x78c17  ldc.i4.0
0x78c18  ldarg.1
0x78c19  stelem.ref
0x78c1a  call     string System.Xml.Res::GetString(string name, object[] args)
0x78c1f  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x78c24  throw
```
