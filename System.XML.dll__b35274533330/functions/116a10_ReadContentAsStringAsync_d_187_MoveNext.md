# <ReadContentAsStringAsync>d__187::MoveNext

- ea: `0x116a10`
- end: `0x116b4a`
- name: `<ReadContentAsStringAsync>d__187::MoveNext`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22910`
- `0x22a30`
- `0x43f60`
- `0x43f70`
- `0x455e0`
- `0xd6c00`
- `0xdb680`
- `0x116a10`

## string_xrefs

- `0x116adf`: `Xml_ReadContentAsFormatException`
- `0x116af4`: `Xml_ReadContentAsFormatException`
- `0x116b09`: `Xml_ReadContentAsFormatException`
- `0x116a2f`: `ReadContentAsString`

## pseudocode

```c

```

## disassembly

```asm
0x116a10  ldarg.0
0x116a11  ldfld    int32 <ReadContentAsStringAsync>d__187::<>1__state
0x116a16  stloc.0
0x116a17  ldarg.0
0x116a18  ldfld    class System.Xml.XsdValidatingReader <ReadContentAsStringAsync>d__187::<>4__this
0x116a1d  stloc.1
0x116a1e  ldloc.0
0x116a1f  brfalse.s loc_116A7E
0x116a21  ldloc.1
0x116a22  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x116a27  call     bool System.Xml.XmlReader::CanReadContentAs(valuetype System.Xml.XmlNodeType nodeType)
0x116a2c  brtrue.s loc_116A3A
0x116a2e  ldloc.1
0x116a2f  ldstr    aReadcontentass// "ReadContentAsString"
0x116a34  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadContentAsException(string methodName)
0x116a39  throw
0x116a3a  ldloc.1
0x116a3b  call     instance class [mscorlib]System.Threading.Tasks.Task`1<object> System.Xml.XsdValidatingReader::InternalReadContentAsObjectAsync()
0x116a40  ldc.i4.0
0x116a41  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<object>::ConfigureAwait(!!T0)
0x116a46  stloc.s  7
0x116a48  ldloca.s 7
0x116a4a  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<object>::GetAwaiter()
0x116a4f  stloc.s  6
0x116a51  ldloca.s 6
0x116a53  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<object>::get_IsCompleted()
0x116a58  brtrue.s loc_116A9B
0x116a5a  ldarg.0
0x116a5b  ldc.i4.0
0x116a5c  dup
0x116a5d  stloc.0
0x116a5e  stfld    int32 <ReadContentAsStringAsync>d__187::<>1__state
0x116a63  ldarg.0
0x116a64  ldloc.s  6
0x116a66  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<object> <ReadContentAsStringAsync>d__187::<>u__1
0x116a6b  ldarg.0
0x116a6c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <ReadContentAsStringAsync>d__187::<>t__builder
0x116a71  ldloca.s 6
0x116a73  ldarg.0
0x116a74  call     T0x2B000282
0x116a79  leave    loc_116B49
0x116a7e  ldarg.0
0x116a7f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<object> <ReadContentAsStringAsync>d__187::<>u__1
0x116a84  stloc.s  6
0x116a86  ldarg.0
0x116a87  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<object> <ReadContentAsStringAsync>d__187::<>u__1
0x116a8c  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<object>
0x116a92  ldarg.0
0x116a93  ldc.i4.m1
0x116a94  dup
0x116a95  stloc.0
0x116a96  stfld    int32 <ReadContentAsStringAsync>d__187::<>1__state
0x116a9b  ldloca.s 6
0x116a9d  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<object>::GetResult()
0x116aa2  stloc.s  5
0x116aa4  ldloc.s  5
0x116aa6  stloc.3
0x116aa7  ldloc.1
0x116aa8  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x116aad  ldc.i4.2
0x116aae  beq.s    loc_116AB8
0x116ab0  ldloc.1
0x116ab1  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_ElementXmlType()
0x116ab6  br.s     loc_116ABE
0x116ab8  ldloc.1
0x116ab9  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_AttributeXmlType()
0x116abe  stloc.s  4
0x116ac0  ldloc.s  4
0x116ac2  brfalse.s loc_116AD4
0x116ac4  ldloc.s  4
0x116ac6  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x116acb  ldloc.3
0x116acc  callvirt instance string System.Xml.Schema.XmlValueConverter::ToString(object value)
0x116ad1  stloc.2
0x116ad2  leave.s  loc_116B35
0x116ad4  ldloc.3
0x116ad5  isinst   [mscorlib]System.String
0x116ada  stloc.2
0x116adb  leave.s  loc_116B35
0x116add  stloc.s  8
0x116adf  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x116ae4  ldstr    aString_0// "String"
0x116ae9  ldloc.s  8
0x116aeb  ldloc.1
0x116aec  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x116af1  throw
0x116af2  stloc.s  9
0x116af4  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x116af9  ldstr    aString_0// "String"
0x116afe  ldloc.s  9
0x116b00  ldloc.1
0x116b01  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x116b06  throw
0x116b07  stloc.s  0xA
0x116b09  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x116b0e  ldstr    aString_0// "String"
0x116b13  ldloc.s  0xA
0x116b15  ldloc.1
0x116b16  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x116b1b  throw
0x116b1c  stloc.s  0xB
0x116b1e  ldarg.0
0x116b1f  ldc.i4.s 0xFE
0x116b21  stfld    int32 <ReadContentAsStringAsync>d__187::<>1__state
0x116b26  ldarg.0
0x116b27  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <ReadContentAsStringAsync>d__187::<>t__builder
0x116b2c  ldloc.s  0xB
0x116b2e  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x116b33  leave.s  loc_116B49
0x116b35  ldarg.0
0x116b36  ldc.i4.s 0xFE
0x116b38  stfld    int32 <ReadContentAsStringAsync>d__187::<>1__state
0x116b3d  ldarg.0
0x116b3e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <ReadContentAsStringAsync>d__187::<>t__builder
0x116b43  ldloc.2
0x116b44  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x116b49  ret
```
