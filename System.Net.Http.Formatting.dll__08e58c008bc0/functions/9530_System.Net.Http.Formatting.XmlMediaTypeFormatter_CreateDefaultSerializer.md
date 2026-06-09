# System.Net.Http.Formatting.XmlMediaTypeFormatter::CreateDefaultSerializer

- ea: `0x9530`
- end: `0x95fa`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::CreateDefaultSerializer`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x9600`

## callees

- `0x39b0`
- `0x90f0`
- `0x94d0`
- `0x94e0`
- `0x9530`
- `0xb4b0`
- `0xb4c0`

## pseudocode

```c

```

## disassembly

```asm
0x9530  ldnull
0x9531  stloc.0
0x9532  ldnull
0x9533  stloc.1
0x9534  ldarg.0
0x9535  call     instance bool System.Net.Http.Formatting.XmlMediaTypeFormatter::get_UseXmlSerializer()
0x953a  brfalse.s loc_9546
0x953c  ldarg.0
0x953d  ldarg.1
0x953e  callvirt instance class [System.Xml]System.Xml.Serialization.XmlSerializer System.Net.Http.Formatting.XmlMediaTypeFormatter::CreateXmlSerializer(class [mscorlib]System.Type type)
0x9543  stloc.1
0x9544  br.s     loc_955A
0x9546  ldsfld   class [System.Runtime.Serialization]System.Runtime.Serialization.XsdDataContractExporter System.Net.Http.FormattingUtilities::XsdDataContractExporter
0x954b  ldarg.1
0x954c  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Runtime.Serialization]System.Runtime.Serialization.XsdDataContractExporter::GetRootElementName(class [mscorlib]System.Type)
0x9551  pop
0x9552  ldarg.0
0x9553  ldarg.1
0x9554  callvirt instance class [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer System.Net.Http.Formatting.XmlMediaTypeFormatter::CreateDataContractSerializer(class [mscorlib]System.Type type)
0x9559  stloc.1
0x955a  leave.s  loc_955F
0x955c  stloc.0
0x955d  leave.s  loc_955F
0x955f  ldloc.1
0x9560  ldnull
0x9561  ceq
0x9563  ldarg.2
0x9564  and
0x9565  brfalse  loc_95F8
0x956a  ldloc.0
0x956b  brfalse.s loc_95B3
0x956d  ldloc.0
0x956e  call     string System.Net.Http.Properties.Resources::get_SerializerCannotSerializeType()
0x9573  ldc.i4.2
0x9574  newarr   [mscorlib]System.Object
0x9579  dup
0x957a  ldc.i4.0
0x957b  ldarg.0
0x957c  call     instance bool System.Net.Http.Formatting.XmlMediaTypeFormatter::get_UseXmlSerializer()
0x9581  brtrue.s loc_9594
0x9583  ldtoken  [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer
0x9588  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x958d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x9592  br.s     loc_95A3
0x9594  ldtoken  [System.Xml]System.Xml.Serialization.XmlSerializer
0x9599  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x959e  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x95a3  stelem.ref
0x95a4  dup
0x95a5  ldc.i4.1
0x95a6  ldarg.1
0x95a7  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x95ac  stelem.ref
0x95ad  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(class [mscorlib]System.Exception innerException, string messageFormat, object[] messageArgs)
0x95b2  throw
0x95b3  call     string System.Net.Http.Properties.Resources::get_SerializerCannotSerializeType()
0x95b8  ldc.i4.2
0x95b9  newarr   [mscorlib]System.Object
0x95be  dup
0x95bf  ldc.i4.0
0x95c0  ldarg.0
0x95c1  call     instance bool System.Net.Http.Formatting.XmlMediaTypeFormatter::get_UseXmlSerializer()
0x95c6  brtrue.s loc_95D9
0x95c8  ldtoken  [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer
0x95cd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x95d2  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x95d7  br.s     loc_95E8
0x95d9  ldtoken  [System.Xml]System.Xml.Serialization.XmlSerializer
0x95de  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x95e3  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x95e8  stelem.ref
0x95e9  dup
0x95ea  ldc.i4.1
0x95eb  ldarg.1
0x95ec  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x95f1  stelem.ref
0x95f2  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x95f7  throw
0x95f8  ldloc.1
0x95f9  ret
```
