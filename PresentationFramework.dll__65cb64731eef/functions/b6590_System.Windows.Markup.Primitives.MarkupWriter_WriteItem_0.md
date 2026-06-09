# System.Windows.Markup.Primitives.MarkupWriter::WriteItem_0

- ea: `0xb6590`
- end: `0xb6f98`
- name: `System.Windows.Markup.Primitives.MarkupWriter::WriteItem_0`
- size: `2568`
- prototype: ``
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, loader_planting`

## callers

- `0xb6530`
- `0xb6590`

## callees

- `0x38c40`
- `0x38c70`
- `0xb6380`
- `0xb6590`
- `0xb6fa0`
- `0xb7080`
- `0xb7110`
- `0xb71b0`
- `0xb7220`
- `0xb7230`
- `0xb7240`
- `0xb7250`
- `0xb72a0`
- `0xb7310`
- `0xb73e0`
- `0xb7420`
- `0xb7460`
- `0xb7490`
- `0x266b60`
- `0x266b70`
- `0x266ba0`
- `0x266bb0`
- `0x266bf0`
- `0x266cc0`
- `0x266cf0`
- `0x266d00`
- `0x266d40`
- `0x266d90`

## string_xrefs

- `0xb6a04`: `xmlns`
- `0xb65e2`: `Extension`

## pseudocode

```c

```

## disassembly

```asm
0xb6590  ldarg.1
0xb6591  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.Markup.Primitives.MarkupObject::get_ObjectType()
0xb6596  call     void System.Windows.Markup.Primitives.MarkupWriter::VerifyTypeIsSerializable(class [mscorlib]System.Type type)
0xb659b  ldarg.2
0xb659c  newobj   instance void MarkupWriterContext::.ctor(class Scope scope)
0xb65a1  stloc.0
0xb65a2  ldarg.1
0xb65a3  ldloc.0
0xb65a4  callvirt instance void [WindowsBase]System.Windows.Markup.Primitives.MarkupObject::AssignRootContext(class [System.Xaml]System.Windows.Markup.IValueSerializerContext)
0xb65a9  ldarg.2
0xb65aa  ldarg.1
0xb65ab  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.Markup.Primitives.MarkupObject::get_ObjectType()
0xb65b0  callvirt instance string Scope::MakeAddressable(class [mscorlib]System.Type type)
0xb65b5  stloc.1
0xb65b6  ldarg.2
0xb65b7  ldloc.1
0xb65b8  callvirt instance string Scope::GetPrefixOf(string uri)
0xb65bd  stloc.2
0xb65be  ldarg.1
0xb65bf  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.Markup.Primitives.MarkupObject::get_ObjectType()
0xb65c4  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xb65c9  stloc.3
0xb65ca  ldtoken  [System.Xaml]System.Windows.Markup.MarkupExtension
0xb65cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb65d4  ldarg.1
0xb65d5  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.Markup.Primitives.MarkupObject::get_ObjectType()
0xb65da  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0xb65df  brfalse.s loc_B6600
0xb65e1  ldloc.3
0xb65e2  ldstr    aExtension// "Extension"
0xb65e7  ldc.i4.4
0xb65e8  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xb65ed  brfalse.s loc_B6600
0xb65ef  ldloc.3
0xb65f0  ldc.i4.0
0xb65f1  ldloc.3
0xb65f2  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb65f7  ldc.i4.s 9
0xb65f9  sub
0xb65fa  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xb65ff  stloc.3
0xb6600  ldarg.0
0xb6601  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Markup.Primitives.MarkupWriter::_writer
0xb6606  ldloc.2
0xb6607  ldloc.3
0xb6608  ldloc.1
0xb6609  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0xb660e  ldarg.1
0xb660f  callvirt instance class [System]System.ComponentModel.AttributeCollection [WindowsBase]System.Windows.Markup.Primitives.MarkupObject::get_Attributes()
0xb6614  ldtoken  [System.Xaml]System.Windows.Markup.ContentPropertyAttribute
0xb6619  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb661e  callvirt instance class [mscorlib]System.Attribute [System]System.ComponentModel.AttributeCollection::get_Item(class [mscorlib]System.Type)
0xb6623  isinst   [System.Xaml]System.Windows.Markup.ContentPropertyAttribute
0xb6628  stloc.s  4
0xb662a  ldarg.1
0xb662b  callvirt instance class [System]System.ComponentModel.AttributeCollection [WindowsBase]System.Windows.Markup.Primitives.MarkupObject::get_Attributes()
0xb6630  ldtoken  [System.Xaml]System.Windows.Markup.XmlLangPropertyAttribute
0xb6635  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb663a  callvirt instance class [mscorlib]System.Attribute [System]System.ComponentModel.AttributeCollection::get_Item(class [mscorlib]System.Type)
0xb663f  isinst   [System.Xaml]System.Windows.Markup.XmlLangPropertyAttribute
0xb6644  stloc.s  5
0xb6646  ldarg.1
0xb6647  callvirt instance class [System]System.ComponentModel.AttributeCollection [WindowsBase]System.Windows.Markup.Primitives.MarkupObject::get_Attributes()
0xb664c  ldtoken  [System.Xaml]System.Windows.Markup.UidPropertyAttribute
0xb6651  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb6656  callvirt instance class [mscorlib]System.Attribute [System]System.ComponentModel.AttributeCollection::get_Item(class [mscorlib]System.Type)
0xb665b  isinst   [System.Xaml]System.Windows.Markup.UidPropertyAttribute
0xb6660  stloc.s  6
0xb6662  ldnull
0xb6663  stloc.s  7
0xb6665  ldc.i4.1
0xb6666  stloc.s  8
0xb6668  ldc.i4.0
0xb6669  stloc.s  9
0xb666b  ldnull
0xb666c  stloc.s  0xA
0xb666e  ldc.i4.0
0xb666f  stloc.s  0xB
0xb6671  ldnull
0xb6672  stloc.s  0xC
0xb6674  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xb6679  stloc.s  0xD
0xb667b  ldnull
0xb667c  stloc.s  0xE
0xb667e  ldarg.0
0xb667f  ldfld    class [System.Xml]System.Xml.XmlTextWriter System.Windows.Markup.Primitives.MarkupWriter::_xmlTextWriter
0xb6684  brtrue.s loc_B6689
0xb6686  ldc.i4.0
0xb6687  br.s     loc_B6694
0xb6689  ldarg.0
0xb668a  ldfld    class [System.Xml]System.Xml.XmlTextWriter System.Windows.Markup.Primitives.MarkupWriter::_xmlTextWriter
0xb668f  callvirt instance valuetype [System.Xml]System.Xml.Formatting [System.Xml]System.Xml.XmlTextWriter::get_Formatting()
0xb6694  stloc.s  0xF
0xb6696  ldarg.1
0xb6697  ldc.i4.0
0xb6698  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty> [WindowsBase]System.Windows.Markup.Primitives.MarkupObject::GetProperties(bool)
0xb669d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty>::GetEnumerator()
0xb66a2  stloc.s  0x10
0xb66a4  br       loc_B69CC
0xb66a9  ldloc.s  0x10
0xb66ab  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty>::get_Current()
0xb66b0  stloc.s  0x11
0xb66b2  ldloc.s  0x11
0xb66b4  callvirt instance bool [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_IsConstructorArgument()
0xb66b9  brfalse.s loc_B66CB
0xb66bb  ldstr    aUnserializable// "UnserializableKeyValue"
0xb66c0  call     string System.Windows.SR::Get(string id)
0xb66c5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb66ca  throw
0xb66cb  ldarg.0
0xb66cc  ldloc.s  0x11
0xb66ce  ldloc.s  4
0xb66d0  ldloca.s 7
0xb66d2  call     instance bool System.Windows.Markup.Primitives.MarkupWriter::IsContentProperty(class [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty property, class [System.Xaml]System.Windows.Markup.ContentPropertyAttribute cpa, class [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty& contentProperty)
0xb66d7  brfalse.s loc_B66E1
0xb66d9  ldc.i4.0
0xb66da  stloc.s  8
0xb66dc  br       loc_B69CC
0xb66e1  ldarg.0
0xb66e2  ldloc.s  0x11
0xb66e4  ldloc.s  0xD
0xb66e6  ldloca.s 0xE
0xb66e8  call     instance bool System.Windows.Markup.Primitives.MarkupWriter::IsDeferredProperty(class [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty property, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> writtenAttributes, class PartiallyOrderedList`2<string, class [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty>& deferredProperties)
0xb66ed  brtrue   loc_B69CC
0xb66f2  ldloc.s  0x11
0xb66f4  callvirt instance bool [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_IsComposite()
0xb66f9  brtrue   loc_B6957
0xb66fe  ldloc.s  0x11
0xb6700  callvirt instance bool [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_IsAttached()
0xb6705  brtrue.s loc_B6713
0xb6707  ldloc.s  0x11
0xb6709  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_PropertyDescriptor()
0xb670e  brtrue   loc_B6885
0xb6713  ldloc.s  0x11
0xb6715  callvirt instance bool [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_IsValueAsString()
0xb671a  brfalse.s loc_B672B
0xb671c  ldloc.s  0x11
0xb671e  stloc.s  7
0xb6720  ldc.i4.1
0xb6721  stloc.s  0xB
0xb6723  ldc.i4.0
0xb6724  stloc.s  8
0xb6726  br       loc_B69CC
0xb672b  ldloc.s  0x11
0xb672d  callvirt instance bool [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_IsKey()
0xb6732  brfalse.s loc_B676C
0xb6734  ldarg.2
0xb6735  ldsfld   string NamespaceCache::XamlNamespace
0xb673a  callvirt instance string Scope::MakeAddressable(string uri)
0xb673f  pop
0xb6740  ldarg.0
0xb6741  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Markup.Primitives.MarkupWriter::_writer
0xb6746  ldarg.2
0xb6747  ldsfld   string NamespaceCache::XamlNamespace
0xb674c  callvirt instance string Scope::GetPrefixOf(string uri)
0xb6751  ldstr    aKey// "Key"
0xb6756  ldsfld   string NamespaceCache::XamlNamespace
0xb675b  ldloc.s  0x11
0xb675d  callvirt instance string [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_StringValue()
0xb6762  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xb6767  br       loc_B69CC
0xb676c  ldloc.s  0x11
0xb676e  callvirt instance class [WindowsBase]System.Windows.DependencyProperty [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_DependencyProperty()
0xb6773  stloc.s  0x12
0xb6775  ldarg.2
0xb6776  ldloc.s  0x12
0xb6778  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_OwnerType()
0xb677d  callvirt instance string Scope::MakeAddressable(class [mscorlib]System.Type type)
0xb6782  stloc.s  0x13
0xb6784  ldarg.2
0xb6785  ldloc.s  0x11
0xb6787  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type> [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_TypeReferences()
0xb678c  callvirt instance void Scope::MakeAddressable(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Type> types)
0xb6791  ldloc.s  0x11
0xb6793  callvirt instance class [System]System.ComponentModel.AttributeCollection [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_Attributes()
0xb6798  ldtoken  [WindowsBase]System.Windows.Markup.DesignerSerializationOptionsAttribute
0xb679d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb67a2  callvirt instance class [mscorlib]System.Attribute [System]System.ComponentModel.AttributeCollection::get_Item(class [mscorlib]System.Type)
0xb67a7  brfalse.s loc_B6816
0xb67a9  ldloc.s  0x11
0xb67ab  callvirt instance class [System]System.ComponentModel.AttributeCollection [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_Attributes()
0xb67b0  ldtoken  [WindowsBase]System.Windows.Markup.DesignerSerializationOptionsAttribute
0xb67b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb67ba  callvirt instance class [mscorlib]System.Attribute [System]System.ComponentModel.AttributeCollection::get_Item(class [mscorlib]System.Type)
0xb67bf  isinst   [WindowsBase]System.Windows.Markup.DesignerSerializationOptionsAttribute
0xb67c4  stloc.s  0x16
0xb67c6  ldloc.s  0x16
0xb67c8  callvirt instance valuetype [WindowsBase]System.Windows.Markup.DesignerSerializationOptions [WindowsBase]System.Windows.Markup.DesignerSerializationOptionsAttribute::get_DesignerSerializationOptions()
0xb67cd  ldc.i4.1
0xb67ce  bne.un.s loc_B6816
0xb67d0  ldloc.s  0x12
0xb67d2  ldsfld   class [WindowsBase]System.Windows.DependencyProperty [PresentationCore]System.Windows.UIElement::UidProperty
0xb67d7  bne.un   loc_B69CC
0xb67dc  ldarg.2
0xb67dd  ldtoken  [System.Xaml]System.Windows.Markup.TypeExtension
0xb67e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb67e7  callvirt instance string Scope::MakeAddressable(class [mscorlib]System.Type type)
0xb67ec  stloc.s  0x17
0xb67ee  ldarg.0
0xb67ef  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Markup.Primitives.MarkupWriter::_writer
0xb67f4  ldarg.2
0xb67f5  ldloc.s  0x17
0xb67f7  callvirt instance string Scope::GetPrefixOf(string uri)
0xb67fc  ldloc.s  0x12
0xb67fe  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0xb6803  ldloc.s  0x17
0xb6805  ldloc.s  0x11
0xb6807  callvirt instance string [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_StringValue()
0xb680c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xb6811  br       loc_B69CC
0xb6816  ldloc.s  0x11
0xb6818  callvirt instance void [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::VerifyOnlySerializableTypes()
0xb681d  ldarg.2
0xb681e  ldloc.s  0x13
0xb6820  callvirt instance string Scope::GetPrefixOf(string uri)
0xb6825  stloc.s  0x14
0xb6827  ldloc.s  0x12
0xb6829  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_OwnerType()
0xb682e  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xb6833  ldstr    asc_28A756// "."
0xb6838  ldloc.s  0x12
0xb683a  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0xb683f  call     string [mscorlib]System.String::Concat(string, string, string)
0xb6844  stloc.s  0x15
0xb6846  ldloc.s  0x14
0xb6848  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb684d  brfalse.s loc_B6868
0xb684f  ldarg.0
0xb6850  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Markup.Primitives.MarkupWriter::_writer
0xb6855  ldloc.s  0x15
0xb6857  ldloc.s  0x11
0xb6859  callvirt instance string [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_StringValue()
0xb685e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb6863  br       loc_B69CC
0xb6868  ldarg.0
0xb6869  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Markup.Primitives.MarkupWriter::_writer
0xb686e  ldloc.s  0x14
0xb6870  ldloc.s  0x15
0xb6872  ldloc.s  0x13
0xb6874  ldloc.s  0x11
0xb6876  callvirt instance string [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_StringValue()
0xb687b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xb6880  br       loc_B69CC
0xb6885  ldloc.s  0x11
0xb6887  callvirt instance void [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::VerifyOnlySerializableTypes()
0xb688c  ldloc.s  5
0xb688e  brfalse.s loc_B68CD
0xb6890  ldloc.s  5
0xb6892  callvirt instance string [System.Xaml]System.Windows.Markup.XmlLangPropertyAttribute::get_Name()
0xb6897  ldloc.s  0x11
0xb6899  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_PropertyDescriptor()
0xb689e  callvirt instance string [System]System.ComponentModel.MemberDescriptor::get_Name()
0xb68a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb68a8  brfalse.s loc_B68CD
0xb68aa  ldarg.0
0xb68ab  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Markup.Primitives.MarkupWriter::_writer
0xb68b0  ldstr    aXml// "xml"
0xb68b5  ldstr    aLang// "lang"
0xb68ba  ldsfld   string NamespaceCache::XmlNamespace
0xb68bf  ldloc.s  0x11
0xb68c1  callvirt instance string [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_StringValue()
0xb68c6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xb68cb  br.s     loc_B6940
0xb68cd  ldloc.s  6
0xb68cf  brfalse.s loc_B6922
0xb68d1  ldloc.s  6
0xb68d3  callvirt instance string [System.Xaml]System.Windows.Markup.UidPropertyAttribute::get_Name()
0xb68d8  ldloc.s  0x11
0xb68da  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_PropertyDescriptor()
0xb68df  callvirt instance string [System]System.ComponentModel.MemberDescriptor::get_Name()
0xb68e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb68e9  brfalse.s loc_B6922
0xb68eb  ldarg.2
0xb68ec  ldsfld   string NamespaceCache::XamlNamespace
0xb68f1  callvirt instance string Scope::MakeAddressable(string uri)
0xb68f6  stloc.s  0x18
0xb68f8  ldarg.0
0xb68f9  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Markup.Primitives.MarkupWriter::_writer
0xb68fe  ldarg.2
0xb68ff  ldloc.s  0x18
0xb6901  callvirt instance string Scope::GetPrefixOf(string uri)
0xb6906  ldloc.s  0x11
0xb6908  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_PropertyDescriptor()
0xb690d  callvirt instance string [System]System.ComponentModel.MemberDescriptor::get_Name()
0xb6912  ldloc.s  0x18
0xb6914  ldloc.s  0x11
0xb6916  callvirt instance string [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_StringValue()
0xb691b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xb6920  br.s     loc_B6940
0xb6922  ldarg.0
0xb6923  ldfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Markup.Primitives.MarkupWriter::_writer
0xb6928  ldloc.s  0x11
0xb692a  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_PropertyDescriptor()
0xb692f  callvirt instance string [System]System.ComponentModel.MemberDescriptor::get_Name()
0xb6934  ldloc.s  0x11
0xb6936  callvirt instance string [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_StringValue()
0xb693b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb6940  ldloc.s  0xD
0xb6942  ldloc.s  0x11
0xb6944  callvirt instance string [WindowsBase]System.Windows.Markup.Primitives.MarkupProperty::get_Name()
  ... truncated ...
```
