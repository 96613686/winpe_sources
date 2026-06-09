# <ReadElementContentAsStringAsync>d__190::MoveNext

- ea: `0x116e30`
- end: `0x116f5f`
- name: `<ReadElementContentAsStringAsync>d__190::MoveNext`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22a50`
- `0x45670`
- `0xd6c00`
- `0xdb680`
- `0x116e30`

## string_xrefs

- `0x116ef4`: `Xml_ReadContentAsFormatException`
- `0x116f09`: `Xml_ReadContentAsFormatException`
- `0x116f1e`: `Xml_ReadContentAsFormatException`
- `0x116e4b`: `ReadElementContentAsString`

## pseudocode

```c

```

## disassembly

```asm
0x116e30  ldarg.0
0x116e31  ldfld    int32 <ReadElementContentAsStringAsync>d__190::<>1__state
0x116e36  stloc.0
0x116e37  ldarg.0
0x116e38  ldfld    class System.Xml.XsdValidatingReader <ReadElementContentAsStringAsync>d__190::<>4__this
0x116e3d  stloc.1
0x116e3e  ldloc.0
0x116e3f  brfalse.s loc_116E9A
0x116e41  ldloc.1
0x116e42  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x116e47  ldc.i4.1
0x116e48  beq.s    loc_116E56
0x116e4a  ldloc.1
0x116e4b  ldstr    aReadelementcon_9// "ReadElementContentAsString"
0x116e50  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadElementContentAsException(string methodName)
0x116e55  throw
0x116e56  ldloc.1
0x116e57  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<class System.Xml.Schema.XmlSchemaType, object>> System.Xml.XsdValidatingReader::InternalReadElementContentAsObjectAsync()
0x116e5c  ldc.i4.0
0x116e5d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<class System.Xml.Schema.XmlSchemaType, object>>::ConfigureAwait(!!T0)
0x116e62  stloc.s  8
0x116e64  ldloca.s 8
0x116e66  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Tuple`2<class System.Xml.Schema.XmlSchemaType, object>>::GetAwaiter()
0x116e6b  stloc.s  7
0x116e6d  ldloca.s 7
0x116e6f  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<class System.Xml.Schema.XmlSchemaType, object>>::get_IsCompleted()
0x116e74  brtrue.s loc_116EB7
0x116e76  ldarg.0
0x116e77  ldc.i4.0
0x116e78  dup
0x116e79  stloc.0
0x116e7a  stfld    int32 <ReadElementContentAsStringAsync>d__190::<>1__state
0x116e7f  ldarg.0
0x116e80  ldloc.s  7
0x116e82  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<class System.Xml.Schema.XmlSchemaType, object>> <ReadElementContentAsStringAsync>d__190::<>u__1
0x116e87  ldarg.0
0x116e88  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <ReadElementContentAsStringAsync>d__190::<>t__builder
0x116e8d  ldloca.s 7
0x116e8f  ldarg.0
0x116e90  call     T0x2B000285
0x116e95  leave    loc_116F5E
0x116e9a  ldarg.0
0x116e9b  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<class System.Xml.Schema.XmlSchemaType, object>> <ReadElementContentAsStringAsync>d__190::<>u__1
0x116ea0  stloc.s  7
0x116ea2  ldarg.0
0x116ea3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<class System.Xml.Schema.XmlSchemaType, object>> <ReadElementContentAsStringAsync>d__190::<>u__1
0x116ea8  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<class System.Xml.Schema.XmlSchemaType, object>>
0x116eae  ldarg.0
0x116eaf  ldc.i4.m1
0x116eb0  dup
0x116eb1  stloc.0
0x116eb2  stfld    int32 <ReadElementContentAsStringAsync>d__190::<>1__state
0x116eb7  ldloca.s 7
0x116eb9  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<class System.Xml.Schema.XmlSchemaType, object>>::GetResult()
0x116ebe  stloc.s  6
0x116ec0  ldloc.s  6
0x116ec2  stloc.s  4
0x116ec4  ldloc.s  4
0x116ec6  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class System.Xml.Schema.XmlSchemaType, object>::get_Item1()
0x116ecb  stloc.3
0x116ecc  ldloc.s  4
0x116ece  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class System.Xml.Schema.XmlSchemaType, object>::get_Item2()
0x116ed3  stloc.s  5
0x116ed5  ldloc.3
0x116ed6  brfalse.s loc_116EE8
0x116ed8  ldloc.3
0x116ed9  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x116ede  ldloc.s  5
0x116ee0  callvirt instance string System.Xml.Schema.XmlValueConverter::ToString(object value)
0x116ee5  stloc.2
0x116ee6  leave.s  loc_116F4A
0x116ee8  ldloc.s  5
0x116eea  isinst   [mscorlib]System.String
0x116eef  stloc.2
0x116ef0  leave.s  loc_116F4A
0x116ef2  stloc.s  9
0x116ef4  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x116ef9  ldstr    aString_0// "String"
0x116efe  ldloc.s  9
0x116f00  ldloc.1
0x116f01  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x116f06  throw
0x116f07  stloc.s  0xA
0x116f09  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x116f0e  ldstr    aString_0// "String"
0x116f13  ldloc.s  0xA
0x116f15  ldloc.1
0x116f16  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x116f1b  throw
0x116f1c  stloc.s  0xB
0x116f1e  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x116f23  ldstr    aString_0// "String"
0x116f28  ldloc.s  0xB
0x116f2a  ldloc.1
0x116f2b  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x116f30  throw
0x116f31  stloc.s  0xC
0x116f33  ldarg.0
0x116f34  ldc.i4.s 0xFE
0x116f36  stfld    int32 <ReadElementContentAsStringAsync>d__190::<>1__state
0x116f3b  ldarg.0
0x116f3c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <ReadElementContentAsStringAsync>d__190::<>t__builder
0x116f41  ldloc.s  0xC
0x116f43  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x116f48  leave.s  loc_116F5E
0x116f4a  ldarg.0
0x116f4b  ldc.i4.s 0xFE
0x116f4d  stfld    int32 <ReadElementContentAsStringAsync>d__190::<>1__state
0x116f52  ldarg.0
0x116f53  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <ReadElementContentAsStringAsync>d__190::<>t__builder
0x116f58  ldloc.2
0x116f59  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x116f5e  ret
```
