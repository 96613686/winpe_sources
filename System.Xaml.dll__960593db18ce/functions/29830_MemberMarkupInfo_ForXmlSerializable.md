# MemberMarkupInfo::ForXmlSerializable

- ea: `0x29830`
- end: `0x29913`
- name: `MemberMarkupInfo::ForXmlSerializable`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x296e0`

## callees

- `0x2100`
- `0x89f0`
- `0xd430`
- `0x202a0`
- `0x291e0`
- `0x29240`
- `0x29830`
- `0x29f70`
- `0x29fb0`
- `0x2a0f0`
- `0x2b9a0`
- `0x2bc60`

## pseudocode

```c

```

## disassembly

```asm
0x29830  ldarg.2
0x29831  callvirt instance class MS.Internal.Xaml.Runtime.ClrObjectRuntime SerializerContext::get_Runtime()
0x29836  ldarg.0
0x29837  ldarg.1
0x29838  callvirt instance object MS.Internal.Xaml.Runtime.XamlRuntime::GetValue(object obj, class System.Xaml.XamlMember property)
0x2983d  castclass [System.Xml]System.Xml.Serialization.IXmlSerializable
0x29842  stloc.0
0x29843  ldloc.0
0x29844  brtrue.s loc_29848
0x29846  ldnull
0x29847  ret
0x29848  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2984d  stloc.1
0x2984e  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x29853  dup
0x29854  ldc.i4.0
0x29855  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_ConformanceLevel(valuetype [System.Xml]System.Xml.ConformanceLevel)
0x2985a  dup
0x2985b  ldc.i4.1
0x2985c  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x29861  dup
0x29862  ldc.i4.1
0x29863  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x29868  stloc.2
0x29869  ldloc.1
0x2986a  ldloc.2
0x2986b  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x29870  stloc.3
0x29871  ldloc.0
0x29872  ldloc.3
0x29873  callvirt instance void [System.Xml]System.Xml.Serialization.IXmlSerializable::WriteXml(class [System.Xml]System.Xml.XmlWriter)
0x29878  leave.s  loc_29884
0x2987a  ldloc.3
0x2987b  brfalse.s loc_29883
0x2987d  ldloc.3
0x2987e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29883  endfinally
0x29884  ldloc.1
0x29885  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x2988a  ldc.i4.0
0x2988b  ble      loc_29911
0x29890  newobj   instance void MemberMarkupInfo::.ctor()
0x29895  dup
0x29896  ldc.i4.4
0x29897  ldarg.1
0x29898  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x2989d  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x298a2  dup
0x298a3  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x298a8  newobj   instance void ObjectMarkupInfo::.ctor()
0x298ad  dup
0x298ae  ldc.i4.1
0x298af  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_XData()
0x298b4  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x298b9  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x298be  dup
0x298bf  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> ObjectMarkupInfo::get_Properties()
0x298c4  newobj   instance void MemberMarkupInfo::.ctor()
0x298c9  dup
0x298ca  ldc.i4.4
0x298cb  call     class System.Xaml.XamlType System.Xaml.XamlLanguage::get_XData()
0x298d0  ldstr    aText// "Text"
0x298d5  callvirt instance class System.Xaml.XamlMember System.Xaml.XamlType::GetMember(string name)
0x298da  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x298df  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x298e4  dup
0x298e5  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> MemberMarkupInfo::get_Children()
0x298ea  newobj   instance void ValueMarkupInfo::.ctor()
0x298ef  dup
0x298f0  ldc.i4.6
0x298f1  ldloc.1
0x298f2  callvirt instance string [mscorlib]System.Object::ToString()
0x298f7  newobj   instance void System.Xaml.XamlNode::.ctor(valuetype System.Xaml.XamlNodeType nodeType, object data)
0x298fc  callvirt instance void MarkupInfo::set_XamlNode(valuetype System.Xaml.XamlNode value)
0x29901  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x29906  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x2990b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::Add(var<u1>)
0x29910  ret
0x29911  ldnull
0x29912  ret
```
