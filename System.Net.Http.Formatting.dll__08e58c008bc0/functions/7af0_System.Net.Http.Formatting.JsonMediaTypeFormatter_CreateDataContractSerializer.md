# System.Net.Http.Formatting.JsonMediaTypeFormatter::CreateDataContractSerializer

- ea: `0x7af0`
- end: `0x7b73`
- name: `System.Net.Http.Formatting.JsonMediaTypeFormatter::CreateDataContractSerializer`
- size: `131`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x7c10`
- `0x7c20`
- `0xd670`

## callees

- `0x39b0`
- `0x7af0`
- `0x7b80`
- `0xb4b0`
- `0xb4c0`

## pseudocode

```c

```

## disassembly

```asm
0x7af0  ldnull
0x7af1  stloc.0
0x7af2  ldnull
0x7af3  stloc.1
0x7af4  ldsfld   class [System.Runtime.Serialization]System.Runtime.Serialization.XsdDataContractExporter System.Net.Http.FormattingUtilities::XsdDataContractExporter
0x7af9  ldarg.1
0x7afa  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Runtime.Serialization]System.Runtime.Serialization.XsdDataContractExporter::GetRootElementName(class [mscorlib]System.Type)
0x7aff  pop
0x7b00  ldarg.0
0x7b01  ldarg.1
0x7b02  callvirt instance class [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer System.Net.Http.Formatting.JsonMediaTypeFormatter::CreateDataContractSerializer(class [mscorlib]System.Type type)
0x7b07  stloc.0
0x7b08  leave.s  loc_7B0D
0x7b0a  stloc.1
0x7b0b  leave.s  loc_7B0D
0x7b0d  ldloc.0
0x7b0e  ldnull
0x7b0f  ceq
0x7b11  ldarg.2
0x7b12  and
0x7b13  brfalse.s loc_7B71
0x7b15  ldloc.1
0x7b16  brfalse.s loc_7B45
0x7b18  ldloc.1
0x7b19  call     string System.Net.Http.Properties.Resources::get_SerializerCannotSerializeType()
0x7b1e  ldc.i4.2
0x7b1f  newarr   [mscorlib]System.Object
0x7b24  dup
0x7b25  ldc.i4.0
0x7b26  ldtoken  [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer
0x7b2b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7b30  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7b35  stelem.ref
0x7b36  dup
0x7b37  ldc.i4.1
0x7b38  ldarg.1
0x7b39  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7b3e  stelem.ref
0x7b3f  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(class [mscorlib]System.Exception innerException, string messageFormat, object[] messageArgs)
0x7b44  throw
0x7b45  call     string System.Net.Http.Properties.Resources::get_SerializerCannotSerializeType()
0x7b4a  ldc.i4.2
0x7b4b  newarr   [mscorlib]System.Object
0x7b50  dup
0x7b51  ldc.i4.0
0x7b52  ldtoken  [System.Runtime.Serialization]System.Runtime.Serialization.Json.DataContractJsonSerializer
0x7b57  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7b5c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7b61  stelem.ref
0x7b62  dup
0x7b63  ldc.i4.1
0x7b64  ldarg.1
0x7b65  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7b6a  stelem.ref
0x7b6b  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x7b70  throw
0x7b71  ldloc.0
0x7b72  ret
```
