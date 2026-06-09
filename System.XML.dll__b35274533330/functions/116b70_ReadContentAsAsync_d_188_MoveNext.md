# <ReadContentAsAsync>d__188::MoveNext

- ea: `0x116b70`
- end: `0x116d13`
- name: `<ReadContentAsAsync>d__188::MoveNext`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config`

## callees

- `0x126e0`
- `0x214b0`
- `0x22910`
- `0x22a30`
- `0x43f60`
- `0x43f70`
- `0x45630`
- `0xd6bb0`
- `0xd6c00`
- `0xdb740`
- `0xdb750`
- `0x116b70`

## string_xrefs

- `0x116c96`: `Xml_ReadContentAsFormatException`
- `0x116cb1`: `Xml_ReadContentAsFormatException`
- `0x116ccc`: `Xml_ReadContentAsFormatException`
- `0x116b8f`: `ReadContentAs`

## pseudocode

```c

```

## disassembly

```asm
0x116b70  ldarg.0
0x116b71  ldfld    int32 <ReadContentAsAsync>d__188::<>1__state
0x116b76  stloc.0
0x116b77  ldarg.0
0x116b78  ldfld    class System.Xml.XsdValidatingReader <ReadContentAsAsync>d__188::<>4__this
0x116b7d  stloc.1
0x116b7e  ldloc.0
0x116b7f  brfalse.s loc_116BDF
0x116b81  ldloc.1
0x116b82  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x116b87  call     bool System.Xml.XmlReader::CanReadContentAs(valuetype System.Xml.XmlNodeType nodeType)
0x116b8c  brtrue.s loc_116B9A
0x116b8e  ldloc.1
0x116b8f  ldstr    aReadcontentas// "ReadContentAs"
0x116b94  call     instance class [mscorlib]System.Exception System.Xml.XmlReader::CreateReadContentAsException(string methodName)
0x116b99  throw
0x116b9a  ldloc.1
0x116b9b  ldc.i4.0
0x116b9c  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<string, object>> System.Xml.XsdValidatingReader::InternalReadContentAsObjectTupleAsync(bool unwrapTypedValue)
0x116ba1  ldc.i4.0
0x116ba2  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<string, object>>::ConfigureAwait(!!T0)
0x116ba7  stloc.s  9
0x116ba9  ldloca.s 9
0x116bab  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Tuple`2<string, object>>::GetAwaiter()
0x116bb0  stloc.s  8
0x116bb2  ldloca.s 8
0x116bb4  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<string, object>>::get_IsCompleted()
0x116bb9  brtrue.s loc_116BFC
0x116bbb  ldarg.0
0x116bbc  ldc.i4.0
0x116bbd  dup
0x116bbe  stloc.0
0x116bbf  stfld    int32 <ReadContentAsAsync>d__188::<>1__state
0x116bc4  ldarg.0
0x116bc5  ldloc.s  8
0x116bc7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<string, object>> <ReadContentAsAsync>d__188::<>u__1
0x116bcc  ldarg.0
0x116bcd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object> <ReadContentAsAsync>d__188::<>t__builder
0x116bd2  ldloca.s 8
0x116bd4  ldarg.0
0x116bd5  call     T0x2B000283
0x116bda  leave    loc_116D12
0x116bdf  ldarg.0
0x116be0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<string, object>> <ReadContentAsAsync>d__188::<>u__1
0x116be5  stloc.s  8
0x116be7  ldarg.0
0x116be8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<string, object>> <ReadContentAsAsync>d__188::<>u__1
0x116bed  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<string, object>>
0x116bf3  ldarg.0
0x116bf4  ldc.i4.m1
0x116bf5  dup
0x116bf6  stloc.0
0x116bf7  stfld    int32 <ReadContentAsAsync>d__188::<>1__state
0x116bfc  ldloca.s 8
0x116bfe  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<string, object>>::GetResult()
0x116c03  stloc.s  7
0x116c05  ldloc.s  7
0x116c07  stloc.s  4
0x116c09  ldloc.s  4
0x116c0b  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, object>::get_Item1()
0x116c10  stloc.3
0x116c11  ldloc.s  4
0x116c13  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, object>::get_Item2()
0x116c18  stloc.s  5
0x116c1a  ldloc.1
0x116c1b  callvirt instance valuetype System.Xml.XmlNodeType System.Xml.XmlReader::get_NodeType()
0x116c20  ldc.i4.2
0x116c21  beq.s    loc_116C2B
0x116c23  ldloc.1
0x116c24  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_ElementXmlType()
0x116c29  br.s     loc_116C31
0x116c2b  ldloc.1
0x116c2c  call     instance class System.Xml.Schema.XmlSchemaType System.Xml.XsdValidatingReader::get_AttributeXmlType()
0x116c31  stloc.s  6
0x116c33  ldloc.s  6
0x116c35  brfalse.s loc_116C79
0x116c37  ldarg.0
0x116c38  ldfld    class [mscorlib]System.Type <ReadContentAsAsync>d__188::returnType
0x116c3d  ldtoken  [mscorlib]System.DateTimeOffset
0x116c42  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x116c47  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x116c4c  brfalse.s loc_116C5F
0x116c4e  ldloc.s  6
0x116c50  callvirt instance class System.Xml.Schema.XmlSchemaDatatype System.Xml.Schema.XmlSchemaType::get_Datatype()
0x116c55  isinst   System.Xml.Schema.Datatype_dateTimeBase
0x116c5a  brfalse.s loc_116C5F
0x116c5c  ldloc.3
0x116c5d  stloc.s  5
0x116c5f  ldloc.s  6
0x116c61  callvirt instance class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlSchemaType::get_ValueConverter()
0x116c66  ldloc.s  5
0x116c68  ldarg.0
0x116c69  ldfld    class [mscorlib]System.Type <ReadContentAsAsync>d__188::returnType
0x116c6e  callvirt instance object System.Xml.Schema.XmlValueConverter::ChangeType(object value, class [mscorlib]System.Type destinationType)
0x116c73  stloc.2
0x116c74  leave    loc_116CFE
0x116c79  ldsfld   class System.Xml.Schema.XmlValueConverter System.Xml.Schema.XmlUntypedConverter::Untyped
0x116c7e  ldloc.s  5
0x116c80  ldarg.0
0x116c81  ldfld    class [mscorlib]System.Type <ReadContentAsAsync>d__188::returnType
0x116c86  ldarg.0
0x116c87  ldfld    class System.Xml.IXmlNamespaceResolver <ReadContentAsAsync>d__188::namespaceResolver
0x116c8c  callvirt instance object System.Xml.Schema.XmlValueConverter::ChangeType(object value, class [mscorlib]System.Type destinationType, class System.Xml.IXmlNamespaceResolver nsResolver)
0x116c91  stloc.2
0x116c92  leave.s  loc_116CFE
0x116c94  stloc.s  0xA
0x116c96  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x116c9b  ldarg.0
0x116c9c  ldfld    class [mscorlib]System.Type <ReadContentAsAsync>d__188::returnType
0x116ca1  callvirt instance string [mscorlib]System.Object::ToString()
0x116ca6  ldloc.s  0xA
0x116ca8  ldloc.1
0x116ca9  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x116cae  throw
0x116caf  stloc.s  0xB
0x116cb1  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x116cb6  ldarg.0
0x116cb7  ldfld    class [mscorlib]System.Type <ReadContentAsAsync>d__188::returnType
0x116cbc  callvirt instance string [mscorlib]System.Object::ToString()
0x116cc1  ldloc.s  0xB
0x116cc3  ldloc.1
0x116cc4  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x116cc9  throw
0x116cca  stloc.s  0xC
0x116ccc  ldstr    aXmlReadcontent// "Xml_ReadContentAsFormatException"
0x116cd1  ldarg.0
0x116cd2  ldfld    class [mscorlib]System.Type <ReadContentAsAsync>d__188::returnType
0x116cd7  callvirt instance string [mscorlib]System.Object::ToString()
0x116cdc  ldloc.s  0xC
0x116cde  ldloc.1
0x116cdf  newobj   instance void System.Xml.XmlException::.ctor(string res, string arg, class [mscorlib]System.Exception innerException, class System.Xml.IXmlLineInfo lineInfo)
0x116ce4  throw
0x116ce5  stloc.s  0xD
0x116ce7  ldarg.0
0x116ce8  ldc.i4.s 0xFE
0x116cea  stfld    int32 <ReadContentAsAsync>d__188::<>1__state
0x116cef  ldarg.0
0x116cf0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object> <ReadContentAsAsync>d__188::<>t__builder
0x116cf5  ldloc.s  0xD
0x116cf7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object>::SetException(class [mscorlib]System.Exception)
0x116cfc  leave.s  loc_116D12
0x116cfe  ldarg.0
0x116cff  ldc.i4.s 0xFE
0x116d01  stfld    int32 <ReadContentAsAsync>d__188::<>1__state
0x116d06  ldarg.0
0x116d07  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object> <ReadContentAsAsync>d__188::<>t__builder
0x116d0c  ldloc.2
0x116d0d  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<object>::SetResult(var<u1>)
0x116d12  ret
```
