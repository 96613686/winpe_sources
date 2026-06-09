# System.Xml.Serialization.XmlCodeExporter::AddDefaultValueAttribute

- ea: `0x76940`
- end: `0x76ca3`
- name: `System.Xml.Serialization.XmlCodeExporter::AddDefaultValueAttribute`
- size: `867`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config`

## callers

- `0x771f0`

## callees

- `0x622f0`
- `0x62790`
- `0x68660`
- `0x68710`
- `0x68730`
- `0x68c10`
- `0x68c30`
- `0x68c50`
- `0x68c90`
- `0x72b60`
- `0x72b70`
- `0x72b90`
- `0x72cd0`
- `0x72dd0`
- `0x762a0`
- `0x766b0`
- `0x76940`
- `0x76cb0`
- `0x76cf0`
- `0xad3f0`
- `0xad6c0`

## string_xrefs

- `0x7697d`: `XmlDropAttributeValue`
- `0x76b9f`: `XmlDropAttributeValue`
- `0x769da`: `XmlDropArrayAttributeValue`
- `0x76aae`: `XmlNotKnownDefaultValue`
- `0x76b33`: `XmlDropNonPrimitiveAttributeValue`

## pseudocode

```c

```

## disassembly

```asm
0x76940  ldarg.s  7
0x76942  callvirt instance bool System.Xml.Serialization.Accessor::get_IsFixed()
0x76947  brtrue.s loc_76950
0x76949  ldstr    aDefault// "default"
0x7694e  br.s     loc_76955
0x76950  ldstr    aFixed// "fixed"
0x76955  stloc.0
0x76956  ldarg.s  6
0x76958  callvirt instance bool System.Xml.Serialization.TypeDesc::get_HasDefaultSupport()
0x7695d  brtrue.s loc_769AA
0x7695f  ldarg.s  5
0x76961  brfalse.s loc_769A9
0x76963  ldarg.3
0x76964  isinst   [mscorlib]System.String
0x76969  brfalse.s loc_769A9
0x7696b  ldarg.s  7
0x7696d  ldarg.s  5
0x7696f  ldarg.s  6
0x76971  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x76976  call     void System.Xml.Serialization.XmlCodeExporter::DropDefaultAttribute(class System.Xml.Serialization.Accessor accessor, class [System]System.CodeDom.CodeCommentStatementCollection comments, string type)
0x7697b  ldarg.s  5
0x7697d  ldstr    aXmldropattribu// "XmlDropAttributeValue"
0x76982  ldc.i4.3
0x76983  newarr   [mscorlib]System.Object
0x76988  dup
0x76989  ldc.i4.0
0x7698a  ldloc.0
0x7698b  stelem.ref
0x7698c  dup
0x7698d  ldc.i4.1
0x7698e  ldarg.s  4
0x76990  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x76995  stelem.ref
0x76996  dup
0x76997  ldc.i4.2
0x76998  ldarg.3
0x76999  callvirt instance string [mscorlib]System.Object::ToString()
0x7699e  stelem.ref
0x7699f  call     string System.Xml.Res::GetString(string name, object[] args)
0x769a4  call     void System.Xml.Serialization.CodeExporter::AddWarningComment(class [System]System.CodeDom.CodeCommentStatementCollection comments, string text)
0x769a9  ret
0x769aa  ldarg.s  6
0x769ac  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsArrayLike()
0x769b1  brfalse.s loc_76A0C
0x769b3  ldarg.s  7
0x769b5  isinst   System.Xml.Serialization.ElementAccessor
0x769ba  brfalse.s loc_76A0C
0x769bc  ldarg.s  5
0x769be  brfalse.s loc_76A0B
0x769c0  ldarg.3
0x769c1  isinst   [mscorlib]System.String
0x769c6  brfalse.s loc_76A0B
0x769c8  ldarg.s  7
0x769ca  ldarg.s  5
0x769cc  ldarg.s  6
0x769ce  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x769d3  call     void System.Xml.Serialization.XmlCodeExporter::DropDefaultAttribute(class System.Xml.Serialization.Accessor accessor, class [System]System.CodeDom.CodeCommentStatementCollection comments, string type)
0x769d8  ldarg.s  5
0x769da  ldstr    aXmldroparrayat// "XmlDropArrayAttributeValue"
0x769df  ldc.i4.3
0x769e0  newarr   [mscorlib]System.Object
0x769e5  dup
0x769e6  ldc.i4.0
0x769e7  ldloc.0
0x769e8  stelem.ref
0x769e9  dup
0x769ea  ldc.i4.1
0x769eb  ldarg.3
0x769ec  callvirt instance string [mscorlib]System.Object::ToString()
0x769f1  stelem.ref
0x769f2  dup
0x769f3  ldc.i4.2
0x769f4  ldarg.s  7
0x769f6  castclass System.Xml.Serialization.ElementAccessor
0x769fb  callvirt instance string System.Xml.Serialization.Accessor::get_Name()
0x76a00  stelem.ref
0x76a01  call     string System.Xml.Res::GetString(string name, object[] args)
0x76a06  call     void System.Xml.Serialization.CodeExporter::AddWarningComment(class [System]System.CodeDom.CodeCommentStatementCollection comments, string text)
0x76a0b  ret
0x76a0c  ldarg.s  4
0x76a0e  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x76a13  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsMappedType()
0x76a18  brfalse  loc_76AF4
0x76a1d  ldarg.1
0x76a1e  brfalse  loc_76AF4
0x76a23  ldarg.3
0x76a24  isinst   [mscorlib]System.String
0x76a29  brfalse  loc_76AF4
0x76a2e  ldarg.s  4
0x76a30  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x76a35  callvirt instance class System.Xml.Serialization.Advanced.MappedTypeDesc System.Xml.Serialization.TypeDesc::get_ExtendedType()
0x76a3a  callvirt instance class System.Xml.Serialization.Advanced.SchemaImporterExtension System.Xml.Serialization.Advanced.MappedTypeDesc::get_Extension()
0x76a3f  stloc.s  5
0x76a41  ldloc.s  5
0x76a43  ldarg.3
0x76a44  castclass [mscorlib]System.String
0x76a49  ldarg.s  4
0x76a4b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x76a50  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x76a55  callvirt instance class [System]System.CodeDom.CodeExpression System.Xml.Serialization.Advanced.SchemaImporterExtension::ImportDefaultValue(string value, string type)
0x76a5a  stloc.s  6
0x76a5c  ldloc.s  6
0x76a5e  brfalse.s loc_76A8F
0x76a60  ldarg.s  8
0x76a62  brfalse.s loc_76A70
0x76a64  ldarg.s  8
0x76a66  ldarg.1
0x76a67  ldloc.s  6
0x76a69  call     void System.Xml.Serialization.XmlCodeExporter::AddInitializationStatement(class [System]System.CodeDom.CodeConstructor ctor, class [System]System.CodeDom.CodeMemberField field, class [System]System.CodeDom.CodeExpression init)
0x76a6e  br.s     loc_76A8F
0x76a70  ldarg.1
0x76a71  ldloc.s  5
0x76a73  ldarg.3
0x76a74  castclass [mscorlib]System.String
0x76a79  ldarg.s  4
0x76a7b  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x76a80  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x76a85  callvirt instance class [System]System.CodeDom.CodeExpression System.Xml.Serialization.Advanced.SchemaImporterExtension::ImportDefaultValue(string value, string type)
0x76a8a  callvirt instance void [System]System.CodeDom.CodeMemberField::set_InitExpression(class [System]System.CodeDom.CodeExpression)
0x76a8f  ldarg.s  5
0x76a91  brfalse.s loc_76AF3
0x76a93  ldarg.s  7
0x76a95  ldarg.s  5
0x76a97  ldarg.s  4
0x76a99  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x76a9e  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x76aa3  call     void System.Xml.Serialization.XmlCodeExporter::DropDefaultAttribute(class System.Xml.Serialization.Accessor accessor, class [System]System.CodeDom.CodeCommentStatementCollection comments, string type)
0x76aa8  ldloc.s  6
0x76aaa  brtrue.s loc_76AF3
0x76aac  ldarg.s  5
0x76aae  ldstr    aXmlnotknowndef// "XmlNotKnownDefaultValue"
0x76ab3  ldc.i4.5
0x76ab4  newarr   [mscorlib]System.Object
0x76ab9  dup
0x76aba  ldc.i4.0
0x76abb  ldloc.s  5
0x76abd  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x76ac2  callvirt instance string [mscorlib]System.Type::get_FullName()
0x76ac7  stelem.ref
0x76ac8  dup
0x76ac9  ldc.i4.1
0x76aca  ldloc.0
0x76acb  stelem.ref
0x76acc  dup
0x76acd  ldc.i4.2
0x76ace  ldarg.3
0x76acf  castclass [mscorlib]System.String
0x76ad4  stelem.ref
0x76ad5  dup
0x76ad6  ldc.i4.3
0x76ad7  ldarg.s  4
0x76ad9  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x76ade  stelem.ref
0x76adf  dup
0x76ae0  ldc.i4.4
0x76ae1  ldarg.s  4
0x76ae3  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x76ae8  stelem.ref
0x76ae9  call     string System.Xml.Res::GetString(string name, object[] args)
0x76aee  call     void System.Xml.Serialization.CodeExporter::AddWarningComment(class [System]System.CodeDom.CodeCommentStatementCollection comments, string text)
0x76af3  ret
0x76af4  ldnull
0x76af5  stloc.1
0x76af6  ldarg.3
0x76af7  isinst   [mscorlib]System.String
0x76afc  brtrue.s loc_76B01
0x76afe  ldarg.3
0x76aff  brtrue.s loc_76B10
0x76b01  ldarg.0
0x76b02  ldarg.s  4
0x76b04  ldarg.3
0x76b05  castclass [mscorlib]System.String
0x76b0a  call     instance object System.Xml.Serialization.XmlCodeExporter::ImportDefault(class System.Xml.Serialization.TypeMapping mapping, string defaultValue)
0x76b0f  stloc.1
0x76b10  ldloc.1
0x76b11  brtrue.s loc_76B14
0x76b13  ret
0x76b14  ldarg.s  4
0x76b16  isinst   System.Xml.Serialization.PrimitiveMapping
0x76b1b  brtrue.s loc_76B56
0x76b1d  ldarg.s  5
0x76b1f  brfalse.s loc_76B55
0x76b21  ldarg.s  7
0x76b23  ldarg.s  5
0x76b25  ldarg.s  6
0x76b27  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x76b2c  call     void System.Xml.Serialization.XmlCodeExporter::DropDefaultAttribute(class System.Xml.Serialization.Accessor accessor, class [System]System.CodeDom.CodeCommentStatementCollection comments, string type)
0x76b31  ldarg.s  5
0x76b33  ldstr    aXmldropnonprim// "XmlDropNonPrimitiveAttributeValue"
0x76b38  ldc.i4.2
0x76b39  newarr   [mscorlib]System.Object
0x76b3e  dup
0x76b3f  ldc.i4.0
0x76b40  ldloc.0
0x76b41  stelem.ref
0x76b42  dup
0x76b43  ldc.i4.1
0x76b44  ldarg.3
0x76b45  callvirt instance string [mscorlib]System.Object::ToString()
0x76b4a  stelem.ref
0x76b4b  call     string System.Xml.Res::GetString(string name, object[] args)
0x76b50  call     void System.Xml.Serialization.CodeExporter::AddWarningComment(class [System]System.CodeDom.CodeCommentStatementCollection comments, string text)
0x76b55  ret
0x76b56  ldarg.s  4
0x76b58  castclass System.Xml.Serialization.PrimitiveMapping
0x76b5d  stloc.2
0x76b5e  ldarg.s  5
0x76b60  brfalse.s loc_76B91
0x76b62  ldloc.2
0x76b63  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x76b68  callvirt instance bool System.Xml.Serialization.TypeDesc::get_HasDefaultSupport()
0x76b6d  brtrue.s loc_76B91
0x76b6f  ldloc.2
0x76b70  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x76b75  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsMappedType()
0x76b7a  brfalse.s loc_76B91
0x76b7c  ldarg.s  7
0x76b7e  ldarg.s  5
0x76b80  ldloc.2
0x76b81  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x76b86  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x76b8b  call     void System.Xml.Serialization.XmlCodeExporter::DropDefaultAttribute(class System.Xml.Serialization.Accessor accessor, class [System]System.CodeDom.CodeCommentStatementCollection comments, string type)
0x76b90  ret
0x76b91  ldloc.1
0x76b92  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x76b97  bne.un.s loc_76BCB
0x76b99  ldarg.s  5
0x76b9b  brfalse.s loc_76BCA
0x76b9d  ldarg.s  5
0x76b9f  ldstr    aXmldropattribu// "XmlDropAttributeValue"
0x76ba4  ldc.i4.3
0x76ba5  newarr   [mscorlib]System.Object
0x76baa  dup
0x76bab  ldc.i4.0
0x76bac  ldloc.0
0x76bad  stelem.ref
0x76bae  dup
0x76baf  ldc.i4.1
0x76bb0  ldloc.2
0x76bb1  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x76bb6  stelem.ref
0x76bb7  dup
0x76bb8  ldc.i4.2
0x76bb9  ldarg.3
0x76bba  callvirt instance string [mscorlib]System.Object::ToString()
0x76bbf  stelem.ref
0x76bc0  call     string System.Xml.Res::GetString(string name, object[] args)
0x76bc5  call     void System.Xml.Serialization.CodeExporter::AddWarningComment(class [System]System.CodeDom.CodeCommentStatementCollection comments, string text)
0x76bca  ret
0x76bcb  ldnull
0x76bcc  stloc.3
0x76bcd  ldnull
0x76bce  stloc.s  4
0x76bd0  ldloc.2
0x76bd1  callvirt instance bool System.Xml.Serialization.TypeMapping::get_IsList()
0x76bd6  brfalse.s loc_76C25
0x76bd8  ldloc.1
0x76bd9  castclass object[]
0x76bde  stloc.s  7
0x76be0  ldloc.s  7
0x76be2  ldlen
0x76be3  conv.i4
0x76be4  newarr   [System]System.CodeDom.CodeExpression
0x76be9  stloc.s  8
0x76beb  ldc.i4.0
0x76bec  stloc.s  9
0x76bee  br.s     loc_76C0C
0x76bf0  ldarg.0
0x76bf1  ldloc.2
0x76bf2  ldloc.s  7
0x76bf4  ldloc.s  9
0x76bf6  ldelem.ref
0x76bf7  ldloc.s  8
0x76bf9  ldloc.s  9
0x76bfb  ldelema  [System]System.CodeDom.CodeExpression
0x76c00  call     instance class [System]System.CodeDom.CodeAttributeArgument[] System.Xml.Serialization.XmlCodeExporter::GetDefaultValueArguments(class System.Xml.Serialization.PrimitiveMapping mapping, object value, [out] class [System]System.CodeDom.CodeExpression& initExpression)
0x76c05  pop
0x76c06  ldloc.s  9
0x76c08  ldc.i4.1
0x76c09  add
0x76c0a  stloc.s  9
0x76c0c  ldloc.s  9
0x76c0e  ldloc.s  7
0x76c10  ldlen
0x76c11  conv.i4
0x76c12  blt.s    loc_76BF0
0x76c14  ldarg.1
0x76c15  callvirt instance class [System]System.CodeDom.CodeTypeReference [System]System.CodeDom.CodeMemberField::get_Type()
0x76c1a  ldloc.s  8
0x76c1c  newobj   instance void [System]System.CodeDom.CodeArrayCreateExpression::.ctor(class [System]System.CodeDom.CodeTypeReference, class [System]System.CodeDom.CodeExpression[])
0x76c21  stloc.s  4
0x76c23  br.s     loc_76C30
0x76c25  ldarg.0
0x76c26  ldloc.2
0x76c27  ldloc.1
0x76c28  ldloca.s 4
0x76c2a  call     instance class [System]System.CodeDom.CodeAttributeArgument[] System.Xml.Serialization.XmlCodeExporter::GetDefaultValueArguments(class System.Xml.Serialization.PrimitiveMapping mapping, object value, [out] class [System]System.CodeDom.CodeExpression& initExpression)
0x76c2f  stloc.3
0x76c30  ldarg.1
0x76c31  brfalse.s loc_76C4B
  ... truncated ...
```
