# System.Windows.Markup.BamlWriter::WriteProperty

- ea: `0x9a610`
- end: `0x9a86e`
- name: `System.Windows.Markup.BamlWriter::WriteProperty`
- size: `606`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: ``

## callers

- `0x213240`

## callees

- `0x38c70`
- `0x89bb0`
- `0x8af70`
- `0x94e70`
- `0x95050`
- `0x95310`
- `0x95c60`
- `0x9a610`
- `0x9b0e0`
- `0x9b270`
- `0x9b3c0`
- `0xaa130`
- `0xaaaa0`
- `0xaac60`
- `0xab610`
- `0xabc20`
- `0xad4d0`
- `0xb0620`
- `0xb06e0`
- `0xb0770`
- `0xb07a0`
- `0xb07d0`
- `0xb0800`
- `0xb0830`
- `0xb0850`
- `0xb08b0`

## string_xrefs

- `0x9a621`: `BamlWriterNoInElement`
- `0x9a62e`: `WriteProperty`

## pseudocode

```c

```

## disassembly

```asm
0x9a610  ldarg.0
0x9a611  call     instance void System.Windows.Markup.BamlWriter::VerifyWriteState()
0x9a616  ldarg.0
0x9a617  call     instance valuetype System.Windows.Markup.BamlRecordType System.Windows.Markup.BamlWriter::PeekRecordType()
0x9a61c  stloc.0
0x9a61d  ldloc.0
0x9a61e  ldc.i4.3
0x9a61f  beq.s    loc_9A64F
0x9a621  ldstr    aBamlwriternoin// "BamlWriterNoInElement"
0x9a626  ldc.i4.2
0x9a627  newarr   [mscorlib]System.Object
0x9a62c  dup
0x9a62d  ldc.i4.0
0x9a62e  ldstr    aWriteproperty// "WriteProperty"
0x9a633  stelem.ref
0x9a634  dup
0x9a635  ldc.i4.1
0x9a636  ldloca.s 0
0x9a638  constrained. System.Windows.Markup.BamlRecordType
0x9a63e  callvirt instance string [mscorlib]System.Object::ToString()
0x9a643  stelem.ref
0x9a644  call     string System.Windows.SR::Get(string id, object[] args)
0x9a649  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x9a64e  throw
0x9a64f  ldarg.0
0x9a650  ldarg.1
0x9a651  ldarg.2
0x9a652  ldarg.3
0x9a653  ldloca.s 1
0x9a655  ldloca.s 2
0x9a657  call     instance void System.Windows.Markup.BamlWriter::GetDpOrPi(string assemblyName, string ownerTypeFullName, string propName, [out] object& dpOrPi, [out] class [mscorlib]System.Type& ownerType)
0x9a65c  ldarg.0
0x9a65d  ldfld    class System.Windows.Markup.MarkupExtensionParser System.Windows.Markup.BamlWriter::_extensionParser
0x9a662  ldloc.2
0x9a663  ldarg.3
0x9a664  ldarga.s 4
0x9a666  ldc.i4.0
0x9a667  ldc.i4.0
0x9a668  ldc.i4.0
0x9a669  ldloc.1
0x9a66a  callvirt instance class System.Windows.Markup.AttributeData System.Windows.Markup.MarkupExtensionParser::IsMarkupExtensionAttribute(class [mscorlib]System.Type declaringType, string propIdName, string& attrValue, int32 lineNumber, int32 linePosition, int32 depth, object info)
0x9a66f  stloc.3
0x9a670  ldloc.3
0x9a671  brtrue   loc_9A7B5
0x9a676  ldc.i4.0
0x9a677  ldc.i4.0
0x9a678  ldarg.0
0x9a679  ldfld    int32 System.Windows.Markup.BamlWriter::_depth
0x9a67e  ldloc.1
0x9a67f  ldarg.1
0x9a680  ldarg.2
0x9a681  ldarg.3
0x9a682  ldarg.s  4
0x9a684  ldarg.s  5
0x9a686  ldc.i4.0
0x9a687  newobj   instance void System.Windows.Markup.XamlPropertyNode::.ctor(int32 lineNumber, int32 linePosition, int32 depth, object propertyMember, string assemblyName, string typeFullName, string propertyName, string value, valuetype System.Windows.Markup.BamlAttributeUsage attributeUsage, bool complexAsSimple)
0x9a68c  stloc.s  4
0x9a68e  ldloc.1
0x9a68f  call     class [mscorlib]System.Type System.Windows.Markup.XamlTypeMapper::GetPropertyType(object propertyMember)
0x9a694  stloc.s  5
0x9a696  ldloc.s  5
0x9a698  ldtoken  [WindowsBase]System.Windows.DependencyProperty
0x9a69d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9a6a2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9a6a7  brfalse  loc_9A73E
0x9a6ac  ldnull
0x9a6ad  stloc.s  6
0x9a6af  ldarg.0
0x9a6b0  ldarg.0
0x9a6b1  ldfld    class System.Windows.Markup.ParserContext System.Windows.Markup.BamlWriter::_parserContext
0x9a6b6  ldarg.s  4
0x9a6b8  ldloca.s 6
0x9a6ba  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.XamlTypeMapper::ParsePropertyName(class System.Windows.Markup.ParserContext parserContext, string propertyName, class [mscorlib]System.Type& ownerType)
0x9a6bf  stfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlWriter::_dpProperty
0x9a6c4  ldarg.0
0x9a6c5  ldfld    class System.Windows.Markup.BamlRecordWriter System.Windows.Markup.BamlWriter::_bamlRecordWriter
0x9a6ca  brfalse  loc_9A7A7
0x9a6cf  ldarg.0
0x9a6d0  ldfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlWriter::_dpProperty
0x9a6d5  brfalse  loc_9A7A7
0x9a6da  ldarg.0
0x9a6db  ldfld    class System.Windows.Markup.ParserContext System.Windows.Markup.BamlWriter::_parserContext
0x9a6e0  callvirt instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.ParserContext::get_MapTable()
0x9a6e5  ldarg.0
0x9a6e6  ldfld    class System.Windows.Markup.BamlRecordWriter System.Windows.Markup.BamlWriter::_bamlRecordWriter
0x9a6eb  callvirt instance class System.Windows.Markup.BamlBinaryWriter System.Windows.Markup.BamlRecordWriter::get_BinaryWriter()
0x9a6f0  ldloc.s  6
0x9a6f2  ldarg.0
0x9a6f3  ldfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlWriter::_dpProperty
0x9a6f8  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x9a6fd  ldloca.s 7
0x9a6ff  callvirt instance int16 System.Windows.Markup.BamlMapTable::GetAttributeOrTypeId(class [mscorlib]System.IO.BinaryWriter binaryWriter, class [mscorlib]System.Type declaringType, string memberName, [out] int16& typeId)
0x9a704  stloc.s  8
0x9a706  ldloc.s  8
0x9a708  ldc.i4.0
0x9a709  bge.s    loc_9A721
0x9a70b  ldloc.s  4
0x9a70d  ldloc.s  8
0x9a70f  callvirt instance void System.Windows.Markup.XamlPropertyNode::set_ValueId(int16 value)
0x9a714  ldloc.s  4
0x9a716  ldnull
0x9a717  callvirt instance void System.Windows.Markup.XamlPropertyNode::set_MemberName(string value)
0x9a71c  br       loc_9A7A7
0x9a721  ldloc.s  4
0x9a723  ldloc.s  7
0x9a725  callvirt instance void System.Windows.Markup.XamlPropertyNode::set_ValueId(int16 value)
0x9a72a  ldloc.s  4
0x9a72c  ldarg.0
0x9a72d  ldfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlWriter::_dpProperty
0x9a732  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x9a737  callvirt instance void System.Windows.Markup.XamlPropertyNode::set_MemberName(string value)
0x9a73c  br.s     loc_9A7A7
0x9a73e  ldarg.0
0x9a73f  ldfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlWriter::_dpProperty
0x9a744  brfalse.s loc_9A7A7
0x9a746  ldloc.s  4
0x9a748  ldarg.0
0x9a749  ldfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlWriter::_dpProperty
0x9a74e  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_PropertyType()
0x9a753  callvirt instance void System.Windows.Markup.XamlPropertyNode::set_ValuePropertyType(class [mscorlib]System.Type value)
0x9a758  ldloc.s  4
0x9a75a  ldarg.0
0x9a75b  ldfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlWriter::_dpProperty
0x9a760  callvirt instance void System.Windows.Markup.XamlPropertyNode::set_ValuePropertyMember(object value)
0x9a765  ldloc.s  4
0x9a767  ldarg.0
0x9a768  ldfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlWriter::_dpProperty
0x9a76d  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x9a772  callvirt instance void System.Windows.Markup.XamlPropertyNode::set_ValuePropertyName(string value)
0x9a777  ldloc.s  4
0x9a779  ldarg.0
0x9a77a  ldfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlWriter::_dpProperty
0x9a77f  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_OwnerType()
0x9a784  callvirt instance void System.Windows.Markup.XamlPropertyNode::set_ValueDeclaringType(class [mscorlib]System.Type value)
0x9a789  ldarg.0
0x9a78a  ldfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlWriter::_dpProperty
0x9a78f  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_OwnerType()
0x9a794  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x9a799  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x9a79e  stloc.s  9
0x9a7a0  ldarg.0
0x9a7a1  ldnull
0x9a7a2  stfld    class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.BamlWriter::_dpProperty
0x9a7a7  ldarg.0
0x9a7a8  ldfld    class System.Windows.Markup.BamlRecordWriter System.Windows.Markup.BamlWriter::_bamlRecordWriter
0x9a7ad  ldloc.s  4
0x9a7af  callvirt instance void System.Windows.Markup.BamlRecordWriter::WriteProperty(class System.Windows.Markup.XamlPropertyNode xamlProperty)
0x9a7b4  ret
0x9a7b5  ldloc.3
0x9a7b6  ldfld    bool System.Windows.Markup.DefAttributeData::IsSimple
0x9a7bb  brfalse  loc_9A85B
0x9a7c0  ldloc.3
0x9a7c1  callvirt instance bool System.Windows.Markup.AttributeData::get_IsTypeExtension()
0x9a7c6  brfalse.s loc_9A822
0x9a7c8  ldarg.0
0x9a7c9  ldfld    class System.Windows.Markup.XamlTypeMapper System.Windows.Markup.BamlWriter::_xamlTypeMapper
0x9a7ce  ldloc.3
0x9a7cf  ldfld    string System.Windows.Markup.DefAttributeData::Args
0x9a7d4  ldarg.0
0x9a7d5  ldfld    class System.Windows.Markup.ParserContext System.Windows.Markup.BamlWriter::_parserContext
0x9a7da  ldc.i4.1
0x9a7db  callvirt instance class [mscorlib]System.Type System.Windows.Markup.XamlTypeMapper::GetTypeFromBaseString(string typeString, class System.Windows.Markup.ParserContext context, bool throwOnError)
0x9a7e0  stloc.s  0xA
0x9a7e2  ldc.i4.0
0x9a7e3  ldc.i4.0
0x9a7e4  ldarg.0
0x9a7e5  ldfld    int32 System.Windows.Markup.BamlWriter::_depth
0x9a7ea  ldloc.1
0x9a7eb  ldarg.1
0x9a7ec  ldarg.2
0x9a7ed  ldarg.3
0x9a7ee  ldloc.s  0xA
0x9a7f0  callvirt instance string [mscorlib]System.Type::get_FullName()
0x9a7f5  ldloc.s  0xA
0x9a7f7  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x9a7fc  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x9a801  ldloc.s  0xA
0x9a803  ldsfld   string [mscorlib]System.String::Empty
0x9a808  ldsfld   string [mscorlib]System.String::Empty
0x9a80d  newobj   instance void System.Windows.Markup.XamlPropertyWithTypeNode::.ctor(int32 lineNumber, int32 linePosition, int32 depth, object propertyMember, string assemblyName, string typeFullName, string propertyName, string valueTypeFullName, string valueAssemblyName, class [mscorlib]System.Type valueElementType, string valueSerializerTypeFullName, string valueSerializerTypeAssemblyName)
0x9a812  stloc.s  0xB
0x9a814  ldarg.0
0x9a815  ldfld    class System.Windows.Markup.BamlRecordWriter System.Windows.Markup.BamlWriter::_bamlRecordWriter
0x9a81a  ldloc.s  0xB
0x9a81c  callvirt instance void System.Windows.Markup.BamlRecordWriter::WritePropertyWithType(class System.Windows.Markup.XamlPropertyWithTypeNode xamlPropertyWithType)
0x9a821  ret
0x9a822  ldc.i4.0
0x9a823  ldc.i4.0
0x9a824  ldarg.0
0x9a825  ldfld    int32 System.Windows.Markup.BamlWriter::_depth
0x9a82a  ldloc.1
0x9a82b  ldarg.1
0x9a82c  ldarg.2
0x9a82d  ldarg.3
0x9a82e  ldloc.3
0x9a82f  ldfld    string System.Windows.Markup.DefAttributeData::Args
0x9a834  ldloc.3
0x9a835  ldfld    int16 System.Windows.Markup.AttributeData::ExtensionTypeId
0x9a83a  ldloc.3
0x9a83b  ldfld    bool System.Windows.Markup.AttributeData::IsValueNestedExtension
0x9a840  ldloc.3
0x9a841  ldfld    bool System.Windows.Markup.AttributeData::IsValueTypeExtension
0x9a846  newobj   instance void System.Windows.Markup.XamlPropertyWithExtensionNode::.ctor(int32 lineNumber, int32 linePosition, int32 depth, object propertyMember, string assemblyName, string typeFullName, string propertyName, string value, int16 extensionTypeId, bool isValueNestedExtension, bool isValueTypeExtension)
0x9a84b  stloc.s  0xC
0x9a84d  ldarg.0
0x9a84e  ldfld    class System.Windows.Markup.BamlRecordWriter System.Windows.Markup.BamlWriter::_bamlRecordWriter
0x9a853  ldloc.s  0xC
0x9a855  callvirt instance void System.Windows.Markup.BamlRecordWriter::WritePropertyWithExtension(class System.Windows.Markup.XamlPropertyWithExtensionNode xamlPropertyNode)
0x9a85a  ret
0x9a85b  ldarg.0
0x9a85c  ldfld    class System.Windows.Markup.MarkupExtensionParser System.Windows.Markup.BamlWriter::_extensionParser
0x9a861  ldarg.0
0x9a862  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Markup.BamlWriter::_markupExtensionNodes
0x9a867  ldloc.3
0x9a868  callvirt instance void System.Windows.Markup.MarkupExtensionParser::CompileAttribute(class [mscorlib]System.Collections.ArrayList xamlNodes, class System.Windows.Markup.AttributeData data)
0x9a86d  ret
```
