# System.Xml.Schema.XmlSchema::Write_4

- ea: `0xcfa30`
- end: `0xcfbb5`
- name: `System.Xml.Schema.XmlSchema::Write_4`
- size: `389`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0xcf9d0`
- `0xcfa00`
- `0xcfa20`

## callees

- `0x12e80`
- `0x12fb0`
- `0x130a0`
- `0xa9e60`
- `0xaa110`
- `0xab0b0`
- `0xab110`
- `0xab180`
- `0xab210`
- `0xcfa30`
- `0xd3d80`

## string_xrefs

- `0xcfad9`: `xmlns`
- `0xcfa78`: `http://www.w3.org/2001/XMLSchema`
- `0xcfa8a`: `http://www.w3.org/2001/XMLSchema`
- `0xcfaa9`: `http://www.w3.org/2001/XMLSchema`
- `0xcfb49`: `http://www.w3.org/2001/XMLSchema`
- `0xcfb5c`: `http://www.w3.org/2001/XMLSchema`
- `0xcfb7b`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c

```

## disassembly

```asm
0xcfa30  ldtoken  System.Xml.Schema.XmlSchema
0xcfa35  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcfa3a  newobj   instance void System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type type)
0xcfa3f  stloc.0
0xcfa40  ldarg.2
0xcfa41  brfalse  loc_CFB16
0xcfa46  newobj   instance void System.Xml.Serialization.XmlSerializerNamespaces::.ctor()
0xcfa4b  stloc.1
0xcfa4c  ldc.i4.0
0xcfa4d  stloc.2
0xcfa4e  ldarg.0
0xcfa4f  call     instance class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Schema.XmlSchemaObject::get_Namespaces()
0xcfa54  brfalse.s loc_CFA86
0xcfa56  ldarg.0
0xcfa57  call     instance class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Schema.XmlSchemaObject::get_Namespaces()
0xcfa5c  callvirt instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializerNamespaces::get_Namespaces()
0xcfa61  ldstr    aXs// "xs"
0xcfa66  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xcfa6b  brtrue.s loc_CFA84
0xcfa6d  ldarg.0
0xcfa6e  call     instance class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Schema.XmlSchemaObject::get_Namespaces()
0xcfa73  callvirt instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializerNamespaces::get_Namespaces()
0xcfa78  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xcfa7d  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsValue(object)
0xcfa82  br.s     loc_CFA85
0xcfa84  ldc.i4.1
0xcfa85  stloc.2
0xcfa86  ldloc.2
0xcfa87  brtrue.s loc_CFAB3
0xcfa89  ldarg.2
0xcfa8a  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xcfa8f  callvirt instance string System.Xml.XmlNamespaceManager::LookupPrefix(string uri)
0xcfa94  brtrue.s loc_CFAB3
0xcfa96  ldarg.2
0xcfa97  ldstr    aXs// "xs"
0xcfa9c  callvirt instance string System.Xml.XmlNamespaceManager::LookupNamespace(string prefix)
0xcfaa1  brtrue.s loc_CFAB3
0xcfaa3  ldloc.1
0xcfaa4  ldstr    aXs// "xs"
0xcfaa9  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xcfaae  callvirt instance void System.Xml.Serialization.XmlSerializerNamespaces::Add(string prefix, string ns)
0xcfab3  ldarg.2
0xcfab4  callvirt instance class [mscorlib]System.Collections.IEnumerator System.Xml.XmlNamespaceManager::GetEnumerator()
0xcfab9  stloc.3
0xcfaba  br.s     loc_CFAF5
0xcfabc  ldloc.3
0xcfabd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xcfac2  castclass [mscorlib]System.String
0xcfac7  stloc.s  4
0xcfac9  ldloc.s  4
0xcfacb  ldstr    aXml// "xml"
0xcfad0  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xcfad5  brfalse.s loc_CFAF5
0xcfad7  ldloc.s  4
0xcfad9  ldstr    aXmlns// "xmlns"
0xcfade  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xcfae3  brfalse.s loc_CFAF5
0xcfae5  ldloc.1
0xcfae6  ldloc.s  4
0xcfae8  ldarg.2
0xcfae9  ldloc.s  4
0xcfaeb  callvirt instance string System.Xml.XmlNamespaceManager::LookupNamespace(string prefix)
0xcfaf0  callvirt instance void System.Xml.Serialization.XmlSerializerNamespaces::Add(string prefix, string ns)
0xcfaf5  ldloc.3
0xcfaf6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcfafb  brtrue.s loc_CFABC
0xcfafd  leave    loc_CFBAB
0xcfb02  ldloc.3
0xcfb03  isinst   [mscorlib]System.IDisposable
0xcfb08  stloc.s  5
0xcfb0a  ldloc.s  5
0xcfb0c  brfalse.s loc_CFB15
0xcfb0e  ldloc.s  5
0xcfb10  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcfb15  endfinally
0xcfb16  ldarg.0
0xcfb17  call     instance class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Schema.XmlSchemaObject::get_Namespaces()
0xcfb1c  brfalse.s loc_CFB6F
0xcfb1e  ldarg.0
0xcfb1f  call     instance class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Schema.XmlSchemaObject::get_Namespaces()
0xcfb24  callvirt instance int32 System.Xml.Serialization.XmlSerializerNamespaces::get_Count()
0xcfb29  ldc.i4.0
0xcfb2a  ble.s    loc_CFB6F
0xcfb2c  ldarg.0
0xcfb2d  call     instance class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Schema.XmlSchemaObject::get_Namespaces()
0xcfb32  callvirt instance class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.XmlSerializerNamespaces::get_Namespaces()
0xcfb37  stloc.s  6
0xcfb39  ldloc.s  6
0xcfb3b  ldstr    aXs// "xs"
0xcfb40  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xcfb45  brtrue.s loc_CFB66
0xcfb47  ldloc.s  6
0xcfb49  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xcfb4e  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsValue(object)
0xcfb53  brtrue.s loc_CFB66
0xcfb55  ldloc.s  6
0xcfb57  ldstr    aXs// "xs"
0xcfb5c  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xcfb61  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xcfb66  ldarg.0
0xcfb67  call     instance class System.Xml.Serialization.XmlSerializerNamespaces System.Xml.Schema.XmlSchemaObject::get_Namespaces()
0xcfb6c  stloc.1
0xcfb6d  br.s     loc_CFBAB
0xcfb6f  newobj   instance void System.Xml.Serialization.XmlSerializerNamespaces::.ctor()
0xcfb74  stloc.1
0xcfb75  ldloc.1
0xcfb76  ldstr    aXs// "xs"
0xcfb7b  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xcfb80  callvirt instance void System.Xml.Serialization.XmlSerializerNamespaces::Add(string prefix, string ns)
0xcfb85  ldarg.0
0xcfb86  ldfld    string System.Xml.Schema.XmlSchema::targetNs
0xcfb8b  brfalse.s loc_CFBAB
0xcfb8d  ldarg.0
0xcfb8e  ldfld    string System.Xml.Schema.XmlSchema::targetNs
0xcfb93  callvirt instance int32 [mscorlib]System.String::get_Length()
0xcfb98  brfalse.s loc_CFBAB
0xcfb9a  ldloc.1
0xcfb9b  ldstr    aTns// "tns"
0xcfba0  ldarg.0
0xcfba1  ldfld    string System.Xml.Schema.XmlSchema::targetNs
0xcfba6  callvirt instance void System.Xml.Serialization.XmlSerializerNamespaces::Add(string prefix, string ns)
0xcfbab  ldloc.0
0xcfbac  ldarg.1
0xcfbad  ldarg.0
0xcfbae  ldloc.1
0xcfbaf  callvirt instance void System.Xml.Serialization.XmlSerializer::Serialize(class System.Xml.XmlWriter xmlWriter, object o, class System.Xml.Serialization.XmlSerializerNamespaces namespaces)
0xcfbb4  ret
```
