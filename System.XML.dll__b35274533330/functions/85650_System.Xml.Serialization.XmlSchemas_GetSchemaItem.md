# System.Xml.Serialization.XmlSchemas::GetSchemaItem

- ea: `0x85650`
- end: `0x859c2`
- name: `System.Xml.Serialization.XmlSchemas::GetSchemaItem`
- size: `882`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x85a30`
- `0x85db0`

## callees

- `0x13310`
- `0x13320`
- `0x622f0`
- `0x85600`
- `0x85650`
- `0xcfd30`
- `0xd0920`
- `0xd0940`
- `0xd0ba0`
- `0xd29f0`
- `0xd2a50`
- `0xd3540`
- `0xd3c30`
- `0xd3d60`
- `0xd6af0`

## string_xrefs

- `0x8597e`: `XmlSchema`
- `0x857e2`: `complexType`
- `0x856af`: `XmlSchemaNamedItem`
- `0x856eb`: `XmlSchemaNamedItem`
- `0x85783`: `XmlSchemaNamedItem`
- `0x857ba`: `XmlSchemaNamedItem`
- `0x85810`: `XmlSchemaNamedItem`
- `0x858aa`: `XmlSchemaNamedItem`
- `0x85999`: `XmlSchemaNamedItem`
- `0x8574d`: `XmlSchemaElementReference`
- `0x85876`: `XmlSchemaAttributeReference`
- `0x858ea`: `XmlSchemaContentDef`
- `0x85956`: `XmlSchemaItem`

## pseudocode

```c

```

## disassembly

```asm
0x85650  ldarg.0
0x85651  brtrue.s loc_8565D
0x85653  ldnull
0x85654  ret
0x85655  ldarg.0
0x85656  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObject::get_Parent()
0x8565b  starg.s  0
0x8565d  ldarg.0
0x8565e  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObject::get_Parent()
0x85663  brfalse.s loc_85672
0x85665  ldarg.0
0x85666  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObject::get_Parent()
0x8566b  isinst   System.Xml.Schema.XmlSchema
0x85670  brfalse.s loc_85655
0x85672  ldarg.1
0x85673  brfalse.s loc_8567D
0x85675  ldarg.1
0x85676  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8567b  brtrue.s loc_856A5
0x8567d  ldarg.0
0x8567e  stloc.1
0x8567f  br.s     loc_85688
0x85681  ldloc.1
0x85682  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObject::get_Parent()
0x85687  stloc.1
0x85688  ldloc.1
0x85689  callvirt instance class System.Xml.Schema.XmlSchemaObject System.Xml.Schema.XmlSchemaObject::get_Parent()
0x8568e  brtrue.s loc_85681
0x85690  ldloc.1
0x85691  isinst   System.Xml.Schema.XmlSchema
0x85696  brfalse.s loc_856A5
0x85698  ldloc.1
0x85699  castclass System.Xml.Schema.XmlSchema
0x8569e  callvirt instance string System.Xml.Schema.XmlSchema::get_TargetNamespace()
0x856a3  starg.s  1
0x856a5  ldnull
0x856a6  stloc.0
0x856a7  ldarg.0
0x856a8  isinst   System.Xml.Schema.XmlSchemaNotation
0x856ad  brfalse.s loc_856E3
0x856af  ldstr    aXmlschemanamed// "XmlSchemaNamedItem"
0x856b4  ldc.i4.4
0x856b5  newarr   [mscorlib]System.Object
0x856ba  dup
0x856bb  ldc.i4.0
0x856bc  ldarg.1
0x856bd  stelem.ref
0x856be  dup
0x856bf  ldc.i4.1
0x856c0  ldstr    aNotation// "notation"
0x856c5  stelem.ref
0x856c6  dup
0x856c7  ldc.i4.2
0x856c8  ldarg.0
0x856c9  castclass System.Xml.Schema.XmlSchemaNotation
0x856ce  callvirt instance string System.Xml.Schema.XmlSchemaNotation::get_Name()
0x856d3  stelem.ref
0x856d4  dup
0x856d5  ldc.i4.3
0x856d6  ldarg.2
0x856d7  stelem.ref
0x856d8  call     string System.Xml.Res::GetString(string name, object[] args)
0x856dd  stloc.0
0x856de  br       loc_859C0
0x856e3  ldarg.0
0x856e4  isinst   System.Xml.Schema.XmlSchemaGroup
0x856e9  brfalse.s loc_8571F
0x856eb  ldstr    aXmlschemanamed// "XmlSchemaNamedItem"
0x856f0  ldc.i4.4
0x856f1  newarr   [mscorlib]System.Object
0x856f6  dup
0x856f7  ldc.i4.0
0x856f8  ldarg.1
0x856f9  stelem.ref
0x856fa  dup
0x856fb  ldc.i4.1
0x856fc  ldstr    aGroup// "group"
0x85701  stelem.ref
0x85702  dup
0x85703  ldc.i4.2
0x85704  ldarg.0
0x85705  castclass System.Xml.Schema.XmlSchemaGroup
0x8570a  callvirt instance string System.Xml.Schema.XmlSchemaGroup::get_Name()
0x8570f  stelem.ref
0x85710  dup
0x85711  ldc.i4.3
0x85712  ldarg.2
0x85713  stelem.ref
0x85714  call     string System.Xml.Res::GetString(string name, object[] args)
0x85719  stloc.0
0x8571a  br       loc_859C0
0x8571f  ldarg.0
0x85720  isinst   System.Xml.Schema.XmlSchemaElement
0x85725  brfalse  loc_857B2
0x8572a  ldarg.0
0x8572b  castclass System.Xml.Schema.XmlSchemaElement
0x85730  stloc.2
0x85731  ldloc.2
0x85732  callvirt instance string System.Xml.Schema.XmlSchemaElement::get_Name()
0x85737  brfalse.s loc_85746
0x85739  ldloc.2
0x8573a  callvirt instance string System.Xml.Schema.XmlSchemaElement::get_Name()
0x8573f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x85744  brtrue.s loc_85783
0x85746  ldarg.0
0x85747  call     class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSchemas::GetParentName(class System.Xml.Schema.XmlSchemaObject item)
0x8574c  stloc.3
0x8574d  ldstr    aXmlschemaeleme// "XmlSchemaElementReference"
0x85752  ldc.i4.3
0x85753  newarr   [mscorlib]System.Object
0x85758  dup
0x85759  ldc.i4.0
0x8575a  ldloc.2
0x8575b  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaElement::get_RefName()
0x85760  callvirt instance string [mscorlib]System.Object::ToString()
0x85765  stelem.ref
0x85766  dup
0x85767  ldc.i4.1
0x85768  ldloc.3
0x85769  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x8576e  stelem.ref
0x8576f  dup
0x85770  ldc.i4.2
0x85771  ldloc.3
0x85772  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x85777  stelem.ref
0x85778  call     string System.Xml.Res::GetString(string name, object[] args)
0x8577d  stloc.0
0x8577e  br       loc_859C0
0x85783  ldstr    aXmlschemanamed// "XmlSchemaNamedItem"
0x85788  ldc.i4.4
0x85789  newarr   [mscorlib]System.Object
0x8578e  dup
0x8578f  ldc.i4.0
0x85790  ldarg.1
0x85791  stelem.ref
0x85792  dup
0x85793  ldc.i4.1
0x85794  ldstr    aElement_0// "element"
0x85799  stelem.ref
0x8579a  dup
0x8579b  ldc.i4.2
0x8579c  ldloc.2
0x8579d  callvirt instance string System.Xml.Schema.XmlSchemaElement::get_Name()
0x857a2  stelem.ref
0x857a3  dup
0x857a4  ldc.i4.3
0x857a5  ldarg.2
0x857a6  stelem.ref
0x857a7  call     string System.Xml.Res::GetString(string name, object[] args)
0x857ac  stloc.0
0x857ad  br       loc_859C0
0x857b2  ldarg.0
0x857b3  isinst   System.Xml.Schema.XmlSchemaType
0x857b8  brfalse.s loc_85808
0x857ba  ldstr    aXmlschemanamed// "XmlSchemaNamedItem"
0x857bf  ldc.i4.4
0x857c0  newarr   [mscorlib]System.Object
0x857c5  dup
0x857c6  ldc.i4.0
0x857c7  ldarg.1
0x857c8  stelem.ref
0x857c9  dup
0x857ca  ldc.i4.1
0x857cb  ldarg.0
0x857cc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x857d1  ldtoken  System.Xml.Schema.XmlSchemaSimpleType
0x857d6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x857db  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x857e0  brtrue.s loc_857E9
0x857e2  ldstr    aComplextype// "complexType"
0x857e7  br.s     loc_857EE
0x857e9  ldstr    aSimpletype// "simpleType"
0x857ee  stelem.ref
0x857ef  dup
0x857f0  ldc.i4.2
0x857f1  ldarg.0
0x857f2  castclass System.Xml.Schema.XmlSchemaType
0x857f7  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x857fc  stelem.ref
0x857fd  call     string System.Xml.Res::GetString(string name, object[] args)
0x85802  stloc.0
0x85803  br       loc_859C0
0x85808  ldarg.0
0x85809  isinst   System.Xml.Schema.XmlSchemaAttributeGroup
0x8580e  brfalse.s loc_85844
0x85810  ldstr    aXmlschemanamed// "XmlSchemaNamedItem"
0x85815  ldc.i4.4
0x85816  newarr   [mscorlib]System.Object
0x8581b  dup
0x8581c  ldc.i4.0
0x8581d  ldarg.1
0x8581e  stelem.ref
0x8581f  dup
0x85820  ldc.i4.1
0x85821  ldstr    aAttributegroup// "attributeGroup"
0x85826  stelem.ref
0x85827  dup
0x85828  ldc.i4.2
0x85829  ldarg.0
0x8582a  castclass System.Xml.Schema.XmlSchemaAttributeGroup
0x8582f  callvirt instance string System.Xml.Schema.XmlSchemaAttributeGroup::get_Name()
0x85834  stelem.ref
0x85835  dup
0x85836  ldc.i4.3
0x85837  ldarg.2
0x85838  stelem.ref
0x85839  call     string System.Xml.Res::GetString(string name, object[] args)
0x8583e  stloc.0
0x8583f  br       loc_859C0
0x85844  ldarg.0
0x85845  isinst   System.Xml.Schema.XmlSchemaAttribute
0x8584a  brfalse  loc_858DA
0x8584f  ldarg.0
0x85850  castclass System.Xml.Schema.XmlSchemaAttribute
0x85855  stloc.s  4
0x85857  ldloc.s  4
0x85859  callvirt instance string System.Xml.Schema.XmlSchemaAttribute::get_Name()
0x8585e  brfalse.s loc_8586E
0x85860  ldloc.s  4
0x85862  callvirt instance string System.Xml.Schema.XmlSchemaAttribute::get_Name()
0x85867  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8586c  brtrue.s loc_858AA
0x8586e  ldarg.0
0x8586f  call     class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSchemas::GetParentName(class System.Xml.Schema.XmlSchemaObject item)
0x85874  stloc.s  5
0x85876  ldstr    aXmlschemaattri// "XmlSchemaAttributeReference"
0x8587b  ldc.i4.3
0x8587c  newarr   [mscorlib]System.Object
0x85881  dup
0x85882  ldc.i4.0
0x85883  ldloc.s  4
0x85885  callvirt instance class System.Xml.XmlQualifiedName System.Xml.Schema.XmlSchemaAttribute::get_RefName()
0x8588a  callvirt instance string [mscorlib]System.Object::ToString()
0x8588f  stelem.ref
0x85890  dup
0x85891  ldc.i4.1
0x85892  ldloc.s  5
0x85894  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x85899  stelem.ref
0x8589a  dup
0x8589b  ldc.i4.2
0x8589c  ldloc.s  5
0x8589e  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x858a3  stelem.ref
0x858a4  call     string System.Xml.Res::GetString(string name, object[] args)
0x858a9  ret
0x858aa  ldstr    aXmlschemanamed// "XmlSchemaNamedItem"
0x858af  ldc.i4.4
0x858b0  newarr   [mscorlib]System.Object
0x858b5  dup
0x858b6  ldc.i4.0
0x858b7  ldarg.1
0x858b8  stelem.ref
0x858b9  dup
0x858ba  ldc.i4.1
0x858bb  ldstr    aAttribute// "attribute"
0x858c0  stelem.ref
0x858c1  dup
0x858c2  ldc.i4.2
0x858c3  ldloc.s  4
0x858c5  callvirt instance string System.Xml.Schema.XmlSchemaAttribute::get_Name()
0x858ca  stelem.ref
0x858cb  dup
0x858cc  ldc.i4.3
0x858cd  ldarg.2
0x858ce  stelem.ref
0x858cf  call     string System.Xml.Res::GetString(string name, object[] args)
0x858d4  stloc.0
0x858d5  br       loc_859C0
0x858da  ldarg.0
0x858db  isinst   System.Xml.Schema.XmlSchemaContent
0x858e0  brfalse.s loc_85914
0x858e2  ldarg.0
0x858e3  call     class System.Xml.XmlQualifiedName System.Xml.Serialization.XmlSchemas::GetParentName(class System.Xml.Schema.XmlSchemaObject item)
0x858e8  stloc.s  6
0x858ea  ldstr    aXmlschemaconte_0// "XmlSchemaContentDef"
0x858ef  ldc.i4.3
0x858f0  newarr   [mscorlib]System.Object
0x858f5  dup
0x858f6  ldc.i4.0
0x858f7  ldloc.s  6
0x858f9  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0x858fe  stelem.ref
0x858ff  dup
0x85900  ldc.i4.1
0x85901  ldloc.s  6
0x85903  callvirt instance string System.Xml.XmlQualifiedName::get_Namespace()
0x85908  stelem.ref
0x85909  call     string System.Xml.Res::GetString(string name, object[] args)
0x8590e  stloc.0
0x8590f  br       loc_859C0
0x85914  ldarg.0
0x85915  isinst   System.Xml.Schema.XmlSchemaExternal
0x8591a  brfalse.s loc_85976
0x8591c  ldarg.0
0x8591d  isinst   System.Xml.Schema.XmlSchemaImport
0x85922  brtrue.s loc_8594F
0x85924  ldarg.0
0x85925  isinst   System.Xml.Schema.XmlSchemaInclude
  ... truncated ...
```
