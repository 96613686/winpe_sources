# Microsoft.SharePoint.BusinessData.Runtime.FieldValueHelpers::CreateElementAnnotations

- ea: `0xb3f0e0`
- end: `0xb3f49b`
- name: `Microsoft.SharePoint.BusinessData.Runtime.FieldValueHelpers::CreateElementAnnotations`
- size: `955`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb3f4a0`

## callees

- `0xb3f0e0`
- `0xb3fd50`
- `0xb69610`

## string_xrefs

- `0xb3f11c`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f12c`: `http://www.w3.org/2001/XMLSchema`
- `0xb3f410`: `http://www.w3.org/2001/XMLSchema-instance`
- `0xb3f168`: `ReadOnly`
- `0xb3f13c`: `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog/Annotations`
- `0xb3f15b`: `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog/Annotations`
- `0xb3f1c6`: `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog/Annotations`
- `0xb3f201`: `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog/Annotations`
- `0xb3f253`: `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog/Annotations`
- `0xb3f265`: `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog/Annotations`
- `0xb3f2fc`: `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog/Annotations`
- `0xb3f324`: `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog/Annotations`
- `0xb3f3f7`: `http://schemas.microsoft.com/windows/2007/BusinessDataCatalog/Annotations`
- `0xb3f438`: `ApplicationRegistry_FieldValueDictionary_Serialization_InvalidCast`

## pseudocode

```c

```

## disassembly

```asm
0xb3f0e0  ldarg.0
0xb3f0e1  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.Collections.ILocalizedNameDictionary [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataObject::GetLocalizedNames()
0xb3f0e6  stloc.0
0xb3f0e7  ldarg.0
0xb3f0e8  callvirt instance bool [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::get_IsIdentifierSet()
0xb3f0ed  brtrue.s loc_B3F10E
0xb3f0ef  ldarg.0
0xb3f0f0  callvirt instance bool [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::get_IsReadOnly()
0xb3f0f5  brtrue.s loc_B3F10E
0xb3f0f7  ldloc.0
0xb3f0f8  callvirt instance int32 class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Collections.IReadOnlyCollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, string>>::get_Count()
0xb3f0fd  ldc.i4.0
0xb3f0fe  bgt.s    loc_B3F10E
0xb3f100  ldarg.2
0xb3f101  brfalse.s loc_B3F10B
0xb3f103  ldarg.0
0xb3f104  callvirt instance bool [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::IsLeaf()
0xb3f109  br.s     loc_B3F10F
0xb3f10b  ldc.i4.0
0xb3f10c  br.s     loc_B3F10F
0xb3f10e  ldc.i4.1
0xb3f10f  stloc.1
0xb3f110  ldloc.1
0xb3f111  brfalse  loc_B3F49A
0xb3f116  ldarg.1
0xb3f117  ldstr    aAnnotation// "annotation"
0xb3f11c  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f121  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f126  ldarg.1
0xb3f127  ldstr    aAppinfo_0// "appinfo"
0xb3f12c  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema"
0xb3f131  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f136  ldarg.1
0xb3f137  ldstr    aSource_4// "source"
0xb3f13c  ldstr    aHttpSchemasMic_174// "http://schemas.microsoft.com/windows/20"...
0xb3f141  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f146  ldc.i4.0
0xb3f147  stloc.2
0xb3f148  ldarg.0
0xb3f149  callvirt instance bool [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::get_IsReadOnly()
0xb3f14e  brfalse.s loc_B3F177
0xb3f150  ldarg.1
0xb3f151  ldstr    aBdc_0// "bdc"
0xb3f156  ldstr    aFieldinfo// "FieldInfo"
0xb3f15b  ldstr    aHttpSchemasMic_174// "http://schemas.microsoft.com/windows/20"...
0xb3f160  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0xb3f165  ldc.i4.1
0xb3f166  stloc.2
0xb3f167  ldarg.1
0xb3f168  ldstr    aReadonly// "ReadOnly"
0xb3f16d  ldstr    aTrue// "true"
0xb3f172  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f177  ldarg.0
0xb3f178  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.Collections.INamedPropertyDictionary [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataObject::GetProperties()
0xb3f17d  stloc.3
0xb3f17e  ldloc.3
0xb3f17f  ldstr    aSize// "Size"
0xb3f184  ldloca.s 4
0xb3f186  callvirt instance bool class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Collections.IReadOnlyDictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0xb3f18b  brfalse.s loc_B3F1E4
0xb3f18d  ldarg.0
0xb3f18e  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetParameter()
0xb3f193  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.ITypeReflector [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::get_TypeReflector()
0xb3f198  ldarg.0
0xb3f199  callvirt instance class [mscorlib]System.Type [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.ITypeReflector::GetDotNetType(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor)
0xb3f19e  ldtoken  [mscorlib]System.String
0xb3f1a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb3f1a8  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xb3f1ad  brfalse.s loc_B3F1E4
0xb3f1af  ldloc.s  4
0xb3f1b1  isinst   [mscorlib]System.Int32
0xb3f1b6  brfalse.s loc_B3F1E4
0xb3f1b8  ldloc.2
0xb3f1b9  brtrue.s loc_B3F1D2
0xb3f1bb  ldarg.1
0xb3f1bc  ldstr    aBdc_0// "bdc"
0xb3f1c1  ldstr    aFieldinfo// "FieldInfo"
0xb3f1c6  ldstr    aHttpSchemasMic_174// "http://schemas.microsoft.com/windows/20"...
0xb3f1cb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0xb3f1d0  ldc.i4.1
0xb3f1d1  stloc.2
0xb3f1d2  ldarg.1
0xb3f1d3  ldstr    aSize// "Size"
0xb3f1d8  ldloc.s  4
0xb3f1da  callvirt instance string [mscorlib]System.Object::ToString()
0xb3f1df  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f1e4  ldloc.3
0xb3f1e5  ldstr    aNullequivalent// "NullEquivalentValueInForms"
0xb3f1ea  ldloca.s 4
0xb3f1ec  callvirt instance bool class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Collections.IReadOnlyDictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0xb3f1f1  brfalse.s loc_B3F231
0xb3f1f3  ldloc.2
0xb3f1f4  brtrue.s loc_B3F20D
0xb3f1f6  ldarg.1
0xb3f1f7  ldstr    aBdc_0// "bdc"
0xb3f1fc  ldstr    aFieldinfo// "FieldInfo"
0xb3f201  ldstr    aHttpSchemasMic_174// "http://schemas.microsoft.com/windows/20"...
0xb3f206  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string, string)
0xb3f20b  ldc.i4.1
0xb3f20c  stloc.2
0xb3f20d  ldarg.1
0xb3f20e  ldstr    aNullequivalent_0// "NullEquivalentValue"
0xb3f213  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartAttribute(string)
0xb3f218  ldloc.s  4
0xb3f21a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xb3f21f  stloc.s  5
0xb3f221  ldloc.s  4
0xb3f223  ldloc.s  5
0xb3f225  ldarg.1
0xb3f226  call     void Microsoft.SharePoint.BusinessData.Runtime.FieldValueHelpers::SerializeSimpleElement(object element, class [mscorlib]System.Type type, class [System.Xml]System.Xml.XmlWriter xw)
0xb3f22b  ldarg.1
0xb3f22c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndAttribute()
0xb3f231  ldloc.2
0xb3f232  brfalse.s loc_B3F23A
0xb3f234  ldarg.1
0xb3f235  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f23a  ldarg.0
0xb3f23b  callvirt instance bool [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::get_IsIdentifierSet()
0xb3f240  brfalse  loc_B3F2EA
0xb3f245  ldarg.0
0xb3f246  callvirt instance bool [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::get_IsAssociationSet()
0xb3f24b  brfalse.s loc_B3F25F
0xb3f24d  ldarg.1
0xb3f24e  ldstr    aForeignkeyinfo// "ForeignKeyInfo"
0xb3f253  ldstr    aHttpSchemasMic_174// "http://schemas.microsoft.com/windows/20"...
0xb3f258  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f25d  br.s     loc_B3F26F
0xb3f25f  ldarg.1
0xb3f260  ldstr    aKeyinfo_0// "KeyInfo"
0xb3f265  ldstr    aHttpSchemasMic_174// "http://schemas.microsoft.com/windows/20"...
0xb3f26a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f26f  ldarg.0
0xb3f270  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IIdentifier [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetIdentifier()
0xb3f275  stloc.s  6
0xb3f277  ldloc.s  6
0xb3f279  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IEntity [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IIdentifier::GetEntity()
0xb3f27e  stloc.s  7
0xb3f280  ldarg.1
0xb3f281  ldstr    aEntitynamespac// "EntityNamespace"
0xb3f286  ldloc.s  7
0xb3f288  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IDataClass::get_Namespace()
0xb3f28d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f292  ldarg.1
0xb3f293  ldstr    aEntityname// "EntityName"
0xb3f298  ldloc.s  7
0xb3f29a  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb3f29f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f2a4  ldarg.1
0xb3f2a5  ldstr    aIdentifierinde// "IdentifierIndex"
0xb3f2aa  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartAttribute(string)
0xb3f2af  ldarg.1
0xb3f2b0  ldloc.s  6
0xb3f2b2  callvirt instance unsigned int8 [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IIdentifier::get_OrdinalNumber()
0xb3f2b7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(int32)
0xb3f2bc  ldarg.1
0xb3f2bd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndAttribute()
0xb3f2c2  ldarg.0
0xb3f2c3  callvirt instance bool [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::get_IsAssociationSet()
0xb3f2c8  brfalse.s loc_B3F2E4
0xb3f2ca  ldarg.0
0xb3f2cb  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IAssociation [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetAssociation()
0xb3f2d0  stloc.s  8
0xb3f2d2  ldarg.1
0xb3f2d3  ldstr    aAssociationnam// "AssociationName"
0xb3f2d8  ldloc.s  8
0xb3f2da  callvirt instance string [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Name()
0xb3f2df  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0xb3f2e4  ldarg.1
0xb3f2e5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f2ea  ldloc.0
0xb3f2eb  callvirt instance int32 class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Collections.IReadOnlyCollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, string>>::get_Count()
0xb3f2f0  ldc.i4.0
0xb3f2f1  ble      loc_B3F378
0xb3f2f6  ldarg.1
0xb3f2f7  ldstr    aLocalizednames// "LocalizedNames"
0xb3f2fc  ldstr    aHttpSchemasMic_174// "http://schemas.microsoft.com/windows/20"...
0xb3f301  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f306  ldloc.0
0xb3f307  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Collections.IReadOnlyDictionary`2<int32, string>::get_Keys()
0xb3f30c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<int32>::GetEnumerator()
0xb3f311  stloc.s  0xD
0xb3f313  br.s     loc_B3F35B
0xb3f315  ldloc.s  0xD
0xb3f317  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<int32>::get_Current()
0xb3f31c  stloc.s  9
0xb3f31e  ldarg.1
0xb3f31f  ldstr    aLocalizedname// "LocalizedName"
0xb3f324  ldstr    aHttpSchemasMic_174// "http://schemas.microsoft.com/windows/20"...
0xb3f329  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f32e  ldarg.1
0xb3f32f  ldstr    aLcid_4// "LCID"
0xb3f334  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartAttribute(string)
0xb3f339  ldarg.1
0xb3f33a  ldloc.s  9
0xb3f33c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(int32)
0xb3f341  ldarg.1
0xb3f342  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndAttribute()
0xb3f347  ldarg.1
0xb3f348  ldloc.0
0xb3f349  ldloc.s  9
0xb3f34b  callvirt instance var<u1> class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.Collections.IReadOnlyDictionary`2<int32, string>::get_Item(void)
0xb3f350  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0xb3f355  ldarg.1
0xb3f356  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f35b  ldloc.s  0xD
0xb3f35d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb3f362  brtrue.s loc_B3F315
0xb3f364  leave.s  loc_B3F372
0xb3f366  ldloc.s  0xD
0xb3f368  brfalse.s loc_B3F371
0xb3f36a  ldloc.s  0xD
0xb3f36c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb3f371  endfinally
0xb3f372  ldarg.1
0xb3f373  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb3f378  ldarg.2
0xb3f379  brfalse  loc_B3F48E
0xb3f37e  ldarg.0
0xb3f37f  callvirt instance bool [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::IsLeaf()
0xb3f384  brfalse  loc_B3F48E
0xb3f389  ldarg.0
0xb3f38a  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor::GetParameter()
0xb3f38f  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.ITypeReflector [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IParameter::get_TypeReflector()
0xb3f394  stloc.s  0xA
0xb3f396  ldloc.s  0xA
0xb3f398  ldarg.0
0xb3f399  callvirt instance class [mscorlib]System.Type [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.ITypeReflector::GetDotNetType(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor)
0xb3f39e  stloc.s  0xB
0xb3f3a0  ldloc.s  0xB
0xb3f3a2  callvirt instance bool [mscorlib]System.Type::get_IsGenericType()
0xb3f3a7  brfalse.s loc_B3F3CC
0xb3f3a9  ldloc.s  0xB
0xb3f3ab  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetGenericTypeDefinition()
0xb3f3b0  ldtoken  [mscorlib]System.Nullable`1
0xb3f3b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb3f3ba  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xb3f3bf  brfalse.s loc_B3F3CC
0xb3f3c1  ldloc.s  0xB
0xb3f3c3  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Type::GetGenericArguments()
0xb3f3c8  ldc.i4.0
0xb3f3c9  ldelem.ref
0xb3f3ca  stloc.s  0xB
0xb3f3cc  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, string> Microsoft.SharePoint.BusinessData.Runtime.FieldValueHelpers::simpleTypes
0xb3f3d1  ldloc.s  0xB
0xb3f3d3  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Type, string>::ContainsKey(var<u1>)
0xb3f3d8  brtrue.s loc_B3F3E6
0xb3f3da  ldloc.s  0xB
0xb3f3dc  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0xb3f3e1  brfalse  loc_B3F48E
0xb3f3e6  ldloc.s  0xA
0xb3f3e8  ldarg.0
0xb3f3e9  ldarg.2
0xb3f3ea  callvirt instance object [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.ITypeReflector::Instantiate(class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.ITypeDescriptor, class [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMethodInstance)
0xb3f3ef  stloc.s  0xC
0xb3f3f1  ldarg.1
0xb3f3f2  ldstr    aDefaultvalue// "DefaultValue"
0xb3f3f7  ldstr    aHttpSchemasMic_174// "http://schemas.microsoft.com/windows/20"...
0xb3f3fc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xb3f401  ldloc.s  0xC
0xb3f403  brtrue.s loc_B3F421
0xb3f405  ldarg.1
0xb3f406  ldstr    aXsi// "xsi"
0xb3f40b  ldstr    aNil// "nil"
0xb3f410  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema-instan"...
0xb3f415  ldstr    aTrue// "true"
0xb3f41a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0xb3f41f  br.s     loc_B3F488
0xb3f421  ldloc.s  0xC
0xb3f423  ldloc.s  0xB
0xb3f425  ldarg.1
0xb3f426  call     void Microsoft.SharePoint.BusinessData.Runtime.FieldValueHelpers::SerializeSimpleElement(object element, class [mscorlib]System.Type type, class [System.Xml]System.Xml.XmlWriter xw)
0xb3f42b  leave.s  loc_B3F488
0xb3f42d  pop
0xb3f42e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xb3f433  call     class [mscorlib]System.Resources.ResourceManager Microsoft.BusinessData.Resources::get_ResourceManager()
0xb3f438  ldstr    aApplicationreg_391// "ApplicationRegistry_FieldValueDictionar"...
0xb3f43d  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xb3f442  ldc.i4.4
0xb3f443  newarr   [mscorlib]System.Object
0xb3f448  stloc.s  0xE
0xb3f44a  ldloc.s  0xE
0xb3f44c  ldc.i4.0
0xb3f44d  ldloc.s  0xC
0xb3f44f  brfalse.s loc_B3F45A
0xb3f451  ldloc.s  0xC
0xb3f453  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xb3f458  br.s     loc_B3F45B
0xb3f45a  ldnull
0xb3f45b  stelem.ref
0xb3f45c  ldloc.s  0xE
0xb3f45e  ldc.i4.1
0xb3f45f  ldloc.s  0xB
0xb3f461  stelem.ref
0xb3f462  ldloc.s  0xE
0xb3f464  ldc.i4.2
0xb3f465  ldarg.0
0xb3f466  callvirt instance int64 [Microsoft.BusinessData]Microsoft.BusinessData.MetadataModel.IMetadataStruct::get_Id()
0xb3f46b  box      [mscorlib]System.Int64
0xb3f470  stelem.ref
0xb3f471  ldloc.s  0xE
  ... truncated ...
```
