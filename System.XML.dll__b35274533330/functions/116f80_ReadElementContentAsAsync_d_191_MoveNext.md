# <ReadElementContentAsAsync>d__191::MoveNext

- ea: `0x116f80`
- end: `0x117113`
- name: `<ReadElementContentAsAsync>d__191::MoveNext`
- size: `403`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22a50`
- `0x456c0`
- `0xd6bb0`
- `0xd6c00`
- `0xdb750`
- `0x116f80`

## string_xrefs

- `0x117096`: `Xml_ReadContentAsFormatException`
- `0x1170b1`: `Xml_ReadContentAsFormatException`
- `0x1170cc`: `Xml_ReadContentAsFormatException`
- `0x116f9b`: `ReadElementContentAs`

## pseudocode

```c

```

## disassembly

```asm
0x116f80  ldarg.0
0x116f81  ldfld    int32 <ReadElementContentAsAsync>d__191::<>1__state
0x116f86  stloc.0
0x116f87  ldarg.0
0x116f88  ldfld    class System.Xml.XsdValidatingReader <ReadElementContentAsAsync>d__191::<>4__this
0x116f8d  stloc.1
0x116f8e  ldloc.0
0x116f8f  brfalse.s loc_116FEB
0x116f91  ldloc.1
0x116f92  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x116f97  ldc.i4.1
0x116f98  beq.s    loc_116FA6
0x116f9a  ldloc.1
0x116f9b  ldstr    aReadelementcon_10// "ReadElementContentAs"
0x116fa0  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadElementContentAsException(string methodName)
0x116fa5  throw
0x116fa6  ldloc.1
0x116fa7  ldc.i4.0
0x116fa8  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`3<class System.Xml.Schema.XmlSchemaType, string, object>> System.Xml.XsdValidatingReader::InternalReadElementContentAsObjectTupleAsync(bool unwrapTypedValue)
0x116fad  ldc.i4.0
0x116fae  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`3<class System.Xml.Schema.XmlSchemaType, string, object>>::ConfigureAwait(!!T0)
0x116fb3  stloc.s  9
0x116fb5  ldloca.s 9
0x116fb7  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Tuple`3<class System.Xml.Schema.XmlSchemaType, string, object>>::GetAwaiter()
0x116fbc  stloc.s  8
0x116fbe  ldloca.s 8
0x116fc0  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`3<class System.Xml.Schema.XmlSchemaType, string, object>>::get_IsCompleted()
0x116fc5  brtrue.s loc_117008
0x116fc7  ldarg.0
0x116fc8  ldc.i4.0
0x116fc9  dup
0x116fca  stloc.0
0x116fcb  stfld    int32 <ReadElementContentAsAsync>d__191::<>1__state
0x116fd0  ldarg.0
0x116fd1  ldloc.s  8
0x116fd3  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`3<class System.Xml.Schema.XmlSchemaType, string, object>> <ReadElementContentAsAsync>d__191::<>u__1
0x116fd8  ldarg.0
0x116fd9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object> <ReadElementContentAsAsync>d__191::<>t__builder
0x116fde  ldloca.s 8
0x116fe0  ldarg.0
0x116fe1  call     T0x2B000286
0x116fe6  leave    loc_117112
0x116feb  ldarg.0
0x116fec  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`3<class System.Xml.Schema.XmlSchemaType, string, object>> <ReadElementContentAsAsync>d__191::<>u__1
0x116ff1  stloc.s  8
0x116ff3  ldarg.0
0x116ff4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`3<class System.Xml.Schema.XmlSchemaType, string, object>> <ReadElementContentAsAsync>d__191::<>u__1
0x116ff9  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`3<class System.Xml.Schema.XmlSchemaType, string, object>>
0x116fff  ldarg.0
0x117000  ldc.i4.m1
0x117001  dup
0x117002  stloc.0
0x117003  stfld    int32 <ReadElementContentAsAsync>d__191::<>1__state
0x117008  ldloca.s 8
0x11700a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`3<class System.Xml.Schema.XmlSchemaType, string, object>>::GetResult()
0x11700f  stloc.s  7
0x117011  ldloc.s  7
0x117013  stloc.s  5
0x117015  ldloc.s  5
0x117017  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class System.Xml.Schema.XmlSchemaType, string, object>::get_Item1()
0x11701c  stloc.3
0x11701d  ldloc.s  5
0x11701f  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class System.Xml.Schema.XmlSchemaType, string, object>::get_Item2()
0x117024  stloc.s  4
0x117026  ldloc.s  5
0x117028  callvirt instance var<u1> class [mscorlib]System.Tuple`3<class System.Xml.Schema.XmlSchemaType, string, object>::get_Item3()
0x11702d  stloc.s  6
0x11702f  ldloc.3
0x117030  brfalse.s loc_117079
0x117032  ldarg.0
0x117033  ldfld    class [mscorlib]System.Type <ReadElementContentAsAsync>d__191::returnType
0x117038  ldtoken  [mscorlib]System.DateTimeOffset
0x11703d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x117042  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x117047  brfalse.s loc_11705A
0x117049  ldloc.3
0x11704a  callvirt instance class System.Xml.Schema.XmlSchemaDatatype System.Xml.Schema.XmlSchemaType::get_Datatype()
0x11704f  isinst   System.Xml.Schema.Datatype_dateTimeBase
0x117054  brfalse.s loc_11705A
0x117056  ldloc.s  4
0x117058  stloc.s  6
0x11705a  ldloc.3
0x11705b  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x117060  ldloc.s  6
0x117062  ldarg.0
0x117063  ldfld    class [mscorlib]System.Type <ReadElementContentAsAsync>d__191::returnType
0x117068  ldarg.0
0x117069  ldfld    class System.Xml.IXmlNamespaceResolver <ReadElementContentAsAsync>d__191::namespaceResolver
0x11706e  callvirt instance object System.Xml.Schema.XmlValueConverter::ChangeType(object value, class [mscorlib]System.Type destinationType, class System.Xml.IXmlNamespaceResolver nsResolver)
0x117073  stloc.2
0x117074  leave    loc_1170FE
0x117079  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x11707e  ldloc.s  6
0x117080  ldarg.0
0x117081  ldfld    class [mscorlib]System.Type <ReadElementContentAsAsync>d__191::returnType
0x117086  ldarg.0
0x117087  ldfld    class System.Xml.IXmlNamespaceResolver <ReadElementContentAsAsync>d__191::namespaceResolver
0x11708c  callvirt instance object System.Xml.Schema.XmlValueConverter::ChangeType(object value, class [mscorlib]System.Type destinationType, class System.Xml.IXmlNamespaceResolver nsResolver)
0x117091  stloc.2
0x117092  leave.s  loc_1170FE
0x117094  stloc.s  0xA
0x117096  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x11709b  ldarg.0
0x11709c  ldfld    class [mscorlib]System.Type <ReadElementContentAsAsync>d__191::returnType
0x1170a1  callvirt instance string [mscorlib]System.Object::ToString()
0x1170a6  ldloc.s  0xA
0x1170a8  ldloc.1
0x1170a9  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x1170ae  throw
0x1170af  stloc.s  0xB
0x1170b1  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x1170b6  ldarg.0
0x1170b7  ldfld    class [mscorlib]System.Type <ReadElementContentAsAsync>d__191::returnType
0x1170bc  callvirt instance string [mscorlib]System.Object::ToString()
0x1170c1  ldloc.s  0xB
0x1170c3  ldloc.1
0x1170c4  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x1170c9  throw
0x1170ca  stloc.s  0xC
0x1170cc  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x1170d1  ldarg.0
0x1170d2  ldfld    class [mscorlib]System.Type <ReadElementContentAsAsync>d__191::returnType
0x1170d7  callvirt instance string [mscorlib]System.Object::ToString()
0x1170dc  ldloc.s  0xC
0x1170de  ldloc.1
0x1170df  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x1170e4  throw
0x1170e5  stloc.s  0xD
0x1170e7  ldarg.0
0x1170e8  ldc.i4.s 0xFE
0x1170ea  stfld    int32 <ReadElementContentAsAsync>d__191::<>1__state
0x1170ef  ldarg.0
0x1170f0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object> <ReadElementContentAsAsync>d__191::<>t__builder
0x1170f5  ldloc.s  0xD
0x1170f7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object>::SetException(class [mscorlib]System.Exception)
0x1170fc  leave.s  loc_117112
0x1170fe  ldarg.0
0x1170ff  ldc.i4.s 0xFE
0x117101  stfld    int32 <ReadElementContentAsAsync>d__191::<>1__state
0x117106  ldarg.0
0x117107  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object> <ReadElementContentAsAsync>d__191::<>t__builder
0x11710c  ldloc.2
0x11710d  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object>::SetResult(var<u1>)
0x117112  ret
```
