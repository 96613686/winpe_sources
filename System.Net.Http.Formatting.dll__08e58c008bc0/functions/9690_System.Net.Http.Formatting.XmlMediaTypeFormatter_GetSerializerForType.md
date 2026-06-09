# System.Net.Http.Formatting.XmlMediaTypeFormatter::GetSerializerForType

- ea: `0x9690`
- end: `0x96e3`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::GetSerializerForType`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x9370`
- `0x9490`

## callees

- `0x39b0`
- `0x90f0`
- `0x9600`
- `0x9690`
- `0xb4b0`

## pseudocode

```c

```

## disassembly

```asm
0x9690  ldarg.0
0x9691  ldarg.1
0x9692  ldc.i4.1
0x9693  call     instance object System.Net.Http.Formatting.XmlMediaTypeFormatter::GetCachedSerializer(class [mscorlib]System.Type type, bool throwOnError)
0x9698  stloc.0
0x9699  ldloc.0
0x969a  brtrue.s loc_96E1
0x969c  call     string System.Net.Http.Properties.Resources::get_SerializerCannotSerializeType()
0x96a1  ldc.i4.2
0x96a2  newarr   [mscorlib]System.Object
0x96a7  dup
0x96a8  ldc.i4.0
0x96a9  ldarg.0
0x96aa  call     instance bool System.Net.Http.Formatting.XmlMediaTypeFormatter::get_UseXmlSerializer()
0x96af  brtrue.s loc_96C2
0x96b1  ldtoken  [System.Runtime.Serialization]System.Runtime.Serialization.DataContractSerializer
0x96b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x96bb  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x96c0  br.s     loc_96D1
0x96c2  ldtoken  [System.Xml]System.Xml.Serialization.XmlSerializer
0x96c7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x96cc  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x96d1  stelem.ref
0x96d2  dup
0x96d3  ldc.i4.1
0x96d4  ldarg.1
0x96d5  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x96da  stelem.ref
0x96db  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x96e0  throw
0x96e1  ldloc.0
0x96e2  ret
```
