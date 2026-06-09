# Microsoft.ReportingServices.Modeling.ModelEntity::WriteXmlElements

- ea: `0x11060`
- end: `0x11173`
- name: `Microsoft.ReportingServices.Modeling.ModelEntity::WriteXmlElements`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb3b0`
- `0xb480`
- `0xb4a0`
- `0xb4b0`
- `0xbd60`
- `0x106b0`
- `0x10760`
- `0x10770`
- `0x107a0`
- `0x107d0`
- `0x10800`
- `0x10830`
- `0x10860`
- `0x11060`
- `0x11880`
- `0x11d60`
- `0x12330`
- `0x126b0`
- `0x14290`
- `0x142d0`

## string_xrefs

- `0x1113a`: `DefaultSecurityFilter`
- `0x11127`: `SecurityFilters`

## pseudocode

```c

```

## disassembly

```asm
0x11060  ldarg.0
0x11061  ldarg.1
0x11062  call     instance void Microsoft.ReportingServices.Modeling.ModelItem::WriteName(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw)
0x11067  ldarg.1
0x11068  ldstr    aCollectionname// "CollectionName"
0x1106d  ldarg.0
0x1106e  ldfld    string Microsoft.ReportingServices.Modeling.ModelEntity::m_collectionName
0x11073  callvirt T0x2B00004C
0x11078  ldarg.0
0x11079  ldarg.1
0x1107a  call     instance void Microsoft.ReportingServices.Modeling.ModelItem::WriteXmlElements(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw)
0x1107f  ldarg.0
0x11080  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_IdentifyingAttributes()
0x11085  ldarg.1
0x11086  ldstr    aIdentifyingatt// "IdentifyingAttributes"
0x1108b  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::WriteTo(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw, string collectionElementName)
0x11090  ldarg.0
0x11091  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultDetailAttributes()
0x11096  ldarg.1
0x11097  ldstr    aDefaultdetaila// "DefaultDetailAttributes"
0x1109c  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::WriteTo(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw, string collectionElementName)
0x110a1  ldarg.0
0x110a2  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultAggregateAttributes()
0x110a7  ldarg.1
0x110a8  ldstr    aDefaultaggrega_0// "DefaultAggregateAttributes"
0x110ad  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::WriteTo(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw, string collectionElementName)
0x110b2  ldarg.0
0x110b3  call     instance class Microsoft.ReportingServices.Modeling.SortAttributeCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SortAttributes()
0x110b8  ldarg.1
0x110b9  ldstr    aSortattributes// "SortAttributes"
0x110be  callvirt instance void Microsoft.ReportingServices.Modeling.SortAttributeCollection::WriteTo(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw, string collectionElementName)
0x110c3  ldarg.1
0x110c4  ldstr    aInstanceselect// "InstanceSelection"
0x110c9  ldarg.0
0x110ca  ldfld    valuetype Microsoft.ReportingServices.Modeling.EntityInstanceSelection Microsoft.ReportingServices.Modeling.ModelEntity::m_instanceSelection
0x110cf  box      Microsoft.ReportingServices.Modeling.EntityInstanceSelection
0x110d4  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteElement(string name, object value)
0x110d9  ldarg.1
0x110da  ldstr    aIslookup// "IsLookup"
0x110df  ldarg.0
0x110e0  ldfld    bool Microsoft.ReportingServices.Modeling.ModelEntity::m_lookup
0x110e5  callvirt T0x2B000048
0x110ea  ldarg.0
0x110eb  call     instance class Microsoft.ReportingServices.Modeling.EntityInheritance Microsoft.ReportingServices.Modeling.ModelEntity::get_Inheritance()
0x110f0  brfalse.s loc_110FE
0x110f2  ldarg.0
0x110f3  call     instance class Microsoft.ReportingServices.Modeling.EntityInheritance Microsoft.ReportingServices.Modeling.ModelEntity::get_Inheritance()
0x110f8  ldarg.1
0x110f9  callvirt instance void Microsoft.ReportingServices.Modeling.EntityInheritance::WriteTo(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw)
0x110fe  ldarg.1
0x110ff  ldstr    aDisjointinheri// "DisjointInheritance"
0x11104  ldarg.0
0x11105  ldfld    bool Microsoft.ReportingServices.Modeling.ModelEntity::m_disjointInheritance
0x1110a  callvirt T0x2B000048
0x1110f  ldarg.0
0x11110  call     instance class Microsoft.ReportingServices.Modeling.ModelFieldFolderItemCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_Fields()
0x11115  ldarg.1
0x11116  ldstr    aFields// "Fields"
0x1111b  callvirt instance void class Microsoft.ReportingServices.Modeling.OwnedModelItemCollection`1<class Microsoft.ReportingServices.Modeling.ModelFieldFolderItem>::WriteTo(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter, string)
0x11120  ldarg.0
0x11121  call     instance class Microsoft.ReportingServices.Modeling.AttributeReferenceCollection Microsoft.ReportingServices.Modeling.ModelEntity::get_SecurityFilters()
0x11126  ldarg.1
0x11127  ldstr    aSecurityfilter// "SecurityFilters"
0x1112c  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReferenceCollection::WriteTo(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw, string collectionElementName)
0x11131  ldarg.0
0x11132  call     instance class Microsoft.ReportingServices.Modeling.AttributeReference Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultSecurityFilter()
0x11137  brfalse.s loc_11156
0x11139  ldarg.1
0x1113a  ldstr    aDefaultsecurit// "DefaultSecurityFilter"
0x1113f  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteStartElement(string name)
0x11144  ldarg.0
0x11145  call     instance class Microsoft.ReportingServices.Modeling.AttributeReference Microsoft.ReportingServices.Modeling.ModelEntity::get_DefaultSecurityFilter()
0x1114a  ldarg.1
0x1114b  callvirt instance void Microsoft.ReportingServices.Modeling.AttributeReference::WriteTo(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw)
0x11150  ldarg.1
0x11151  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteEndElement()
0x11156  ldarg.0
0x11157  ldfld    class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::m_binding
0x1115c  brfalse.s loc_11172
0x1115e  ldarg.1
0x1115f  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlWriter::get_ShouldWriteBindings()
0x11164  brfalse.s loc_11172
0x11166  ldarg.0
0x11167  ldfld    class Microsoft.ReportingServices.Modeling.Binding Microsoft.ReportingServices.Modeling.ModelEntity::m_binding
0x1116c  ldarg.1
0x1116d  callvirt instance void Microsoft.ReportingServices.Modeling.Binding::WriteTo(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw)
0x11172  ret
```
