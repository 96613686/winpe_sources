# System.Xml.Serialization.XmlCustomFormatter::FromDefaultValue

- ea: `0x78850`
- end: `0x78951`
- name: `System.Xml.Serialization.XmlCustomFormatter::FromDefaultValue`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x80380`

## callees

- `0x622f0`
- `0x78850`
- `0x78960`
- `0x78970`
- `0x789c0`
- `0x789f0`
- `0x78a00`
- `0x78a10`
- `0x78a20`

## string_xrefs

- `0x788cf`: `XmlName`
- `0x788e8`: `XmlNCName`
- `0x78901`: `XmlNmToken`
- `0x7891a`: `XmlNmTokens`
- `0x78932`: `XmlUnsupportedDefaultType`

## pseudocode

```c

```

## disassembly

```asm
0x78850  ldarg.0
0x78851  brtrue.s loc_78855
0x78853  ldnull
0x78854  ret
0x78855  ldarg.0
0x78856  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x7885b  stloc.0
0x7885c  ldloc.0
0x7885d  ldtoken  [mscorlib]System.DateTime
0x78862  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x78867  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x7886c  brfalse.s loc_788BC
0x7886e  ldarg.1
0x7886f  ldstr    aDatetime// "DateTime"
0x78874  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78879  brfalse.s loc_78887
0x7887b  ldarg.0
0x7887c  unbox.any [mscorlib]System.DateTime
0x78881  call     string System.Xml.Serialization.XmlCustomFormatter::FromDateTime(valuetype [mscorlib]System.DateTime value)
0x78886  ret
0x78887  ldarg.1
0x78888  ldstr    aDate_0// "Date"
0x7888d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78892  brfalse.s loc_788A0
0x78894  ldarg.0
0x78895  unbox.any [mscorlib]System.DateTime
0x7889a  call     string System.Xml.Serialization.XmlCustomFormatter::FromDate(valuetype [mscorlib]System.DateTime value)
0x7889f  ret
0x788a0  ldarg.1
0x788a1  ldstr    aTime_0// "Time"
0x788a6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x788ab  brfalse  loc_78932
0x788b0  ldarg.0
0x788b1  unbox.any [mscorlib]System.DateTime
0x788b6  call     string System.Xml.Serialization.XmlCustomFormatter::FromTime(valuetype [mscorlib]System.DateTime value)
0x788bb  ret
0x788bc  ldloc.0
0x788bd  ldtoken  [mscorlib]System.String
0x788c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x788c7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x788cc  brfalse.s loc_78932
0x788ce  ldarg.1
0x788cf  ldstr    aXmlname// "XmlName"
0x788d4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x788d9  brfalse.s loc_788E7
0x788db  ldarg.0
0x788dc  castclass [mscorlib]System.String
0x788e1  call     string System.Xml.Serialization.XmlCustomFormatter::FromXmlName(string name)
0x788e6  ret
0x788e7  ldarg.1
0x788e8  ldstr    aXmlncname// "XmlNCName"
0x788ed  call     bool [mscorlib]System.String::op_Equality(string, string)
0x788f2  brfalse.s loc_78900
0x788f4  ldarg.0
0x788f5  castclass [mscorlib]System.String
0x788fa  call     string System.Xml.Serialization.XmlCustomFormatter::FromXmlNCName(string ncName)
0x788ff  ret
0x78900  ldarg.1
0x78901  ldstr    aXmlnmtoken// "XmlNmToken"
0x78906  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7890b  brfalse.s loc_78919
0x7890d  ldarg.0
0x7890e  castclass [mscorlib]System.String
0x78913  call     string System.Xml.Serialization.XmlCustomFormatter::FromXmlNmToken(string nmToken)
0x78918  ret
0x78919  ldarg.1
0x7891a  ldstr    aXmlnmtokens// "XmlNmTokens"
0x7891f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x78924  brfalse.s loc_78932
0x78926  ldarg.0
0x78927  castclass [mscorlib]System.String
0x7892c  call     string System.Xml.Serialization.XmlCustomFormatter::FromXmlNmTokens(string nmTokens)
0x78931  ret
0x78932  ldstr    aXmlunsupported_8// "XmlUnsupportedDefaultType"
0x78937  ldc.i4.1
0x78938  newarr   [mscorlib]System.Object
0x7893d  dup
0x7893e  ldc.i4.0
0x7893f  ldloc.0
0x78940  callvirt instance string [mscorlib]System.Type::get_FullName()
0x78945  stelem.ref
0x78946  call     string System.Xml.Res::GetString(string name, object[] args)
0x7894b  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x78950  throw
```
