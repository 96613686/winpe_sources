# System.Xml.Schema.DatatypeImplementation::CreateBuiltinTypes

- ea: `0xb81a0`
- end: `0xb846b`
- name: `System.Xml.Schema.DatatypeImplementation::CreateBuiltinTypes`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0xb7560`

## callees

- `0x132e0`
- `0x13320`
- `0xb8090`
- `0xb80b0`
- `0xb80e0`
- `0xb81a0`
- `0xd2270`
- `0x123580`
- `0x123590`

## string_xrefs

- `0xb81af`: `http://www.w3.org/2001/XMLSchema`
- `0xb8207`: `http://www.w3.org/2001/XMLSchema`
- `0xb8281`: `http://www.w3.org/2001/XMLSchema`
- `0xb82c5`: `http://www.w3.org/2001/XMLSchema`
- `0xb82fd`: `http://www.w3.org/2003/11/xpath-datatypes`
- `0xb8358`: `http://www.w3.org/2003/11/xpath-datatypes`
- `0xb83b3`: `http://www.w3.org/2003/11/xpath-datatypes`
- `0xb8411`: `http://www.w3.org/2003/11/xpath-datatypes`

## pseudocode

```c

```

## disassembly

```asm
0xb81a0  ldsfld   class SchemaDatatypeMap[] System.Xml.Schema.DatatypeImplementation::c_XsdTypes
0xb81a5  ldc.i4.s 0xB
0xb81a7  ldelem.ref
0xb81a8  stloc.1
0xb81a9  ldloc.1
0xb81aa  callvirt instance string SchemaDatatypeMap::get_Name()
0xb81af  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xb81b4  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xb81b9  stloc.0
0xb81ba  ldloc.0
0xb81bb  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0xb81c0  call     class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::FromTypeName(string name)
0xb81c5  stloc.2
0xb81c6  ldloc.0
0xb81c7  ldloc.2
0xb81c8  call     class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::StartBuiltinType(class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaDatatype dataType)
0xb81cd  stsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::anySimpleType
0xb81d2  ldloc.2
0xb81d3  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::anySimpleType
0xb81d8  stfld    class System.Xml.Schema.XmlSchemaType System.Xml.Schema.DatatypeImplementation::parentSchemaType
0xb81dd  ldsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Schema.DatatypeImplementation::builtinTypes
0xb81e2  ldloc.0
0xb81e3  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::anySimpleType
0xb81e8  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xb81ed  ldc.i4.0
0xb81ee  stloc.s  4
0xb81f0  br.s     loc_B8254
0xb81f2  ldloc.s  4
0xb81f4  ldc.i4.s 0xB
0xb81f6  beq.s    loc_B824E
0xb81f8  ldsfld   class SchemaDatatypeMap[] System.Xml.Schema.DatatypeImplementation::c_XsdTypes
0xb81fd  ldloc.s  4
0xb81ff  ldelem.ref
0xb8200  stloc.1
0xb8201  ldloc.1
0xb8202  callvirt instance string SchemaDatatypeMap::get_Name()
0xb8207  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xb820c  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xb8211  stloc.0
0xb8212  ldloc.0
0xb8213  callvirt instance string System.Xml.XmlQualifiedName::get_Name()
0xb8218  call     class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::FromTypeName(string name)
0xb821d  stloc.2
0xb821e  ldloc.0
0xb821f  ldloc.2
0xb8220  call     class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::StartBuiltinType(class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaDatatype dataType)
0xb8225  stloc.3
0xb8226  ldloc.2
0xb8227  ldloc.3
0xb8228  stfld    class System.Xml.Schema.XmlSchemaType System.Xml.Schema.DatatypeImplementation::parentSchemaType
0xb822d  ldsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Schema.DatatypeImplementation::builtinTypes
0xb8232  ldloc.0
0xb8233  ldloc.3
0xb8234  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xb8239  ldloc.2
0xb823a  ldfld    valuetype System.Xml.Schema.XmlSchemaDatatypeVariety System.Xml.Schema.DatatypeImplementation::variety
0xb823f  brtrue.s loc_B824E
0xb8241  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType[] System.Xml.Schema.DatatypeImplementation::enumToTypeCode
0xb8246  ldloc.2
0xb8247  callvirt instance valuetype System.Xml.Schema.XmlTypeCode System.Xml.Schema.XmlSchemaDatatype::get_TypeCode()
0xb824c  ldloc.3
0xb824d  stelem.ref
0xb824e  ldloc.s  4
0xb8250  ldc.i4.1
0xb8251  add
0xb8252  stloc.s  4
0xb8254  ldloc.s  4
0xb8256  ldsfld   class SchemaDatatypeMap[] System.Xml.Schema.DatatypeImplementation::c_XsdTypes
0xb825b  ldlen
0xb825c  conv.i4
0xb825d  blt.s    loc_B81F2
0xb825f  ldc.i4.0
0xb8260  stloc.s  5
0xb8262  br       loc_B82EA
0xb8267  ldloc.s  5
0xb8269  ldc.i4.s 0xB
0xb826b  beq.s    loc_B82E4
0xb826d  ldsfld   class SchemaDatatypeMap[] System.Xml.Schema.DatatypeImplementation::c_XsdTypes
0xb8272  ldloc.s  5
0xb8274  ldelem.ref
0xb8275  stloc.1
0xb8276  ldsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Schema.DatatypeImplementation::builtinTypes
0xb827b  ldloc.1
0xb827c  callvirt instance string SchemaDatatypeMap::get_Name()
0xb8281  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xb8286  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xb828b  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xb8290  castclass System.Xml.Schema.XmlSchemaSimpleType
0xb8295  stloc.s  6
0xb8297  ldloc.1
0xb8298  callvirt instance int32 SchemaDatatypeMap::get_ParentIndex()
0xb829d  ldc.i4.s 0xB
0xb829f  bne.un.s loc_B82AF
0xb82a1  ldloc.s  6
0xb82a3  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::anySimpleType
0xb82a8  call     void System.Xml.Schema.DatatypeImplementation::FinishBuiltinType(class System.Xml.Schema.XmlSchemaSimpleType derivedType, class System.Xml.Schema.XmlSchemaSimpleType baseType)
0xb82ad  br.s     loc_B82E4
0xb82af  ldsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Schema.DatatypeImplementation::builtinTypes
0xb82b4  ldsfld   class SchemaDatatypeMap[] System.Xml.Schema.DatatypeImplementation::c_XsdTypes
0xb82b9  ldloc.1
0xb82ba  callvirt instance int32 SchemaDatatypeMap::get_ParentIndex()
0xb82bf  ldelem.ref
0xb82c0  callvirt instance string SchemaDatatypeMap::get_Name()
0xb82c5  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0xb82ca  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xb82cf  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xb82d4  castclass System.Xml.Schema.XmlSchemaSimpleType
0xb82d9  stloc.s  7
0xb82db  ldloc.s  6
0xb82dd  ldloc.s  7
0xb82df  call     void System.Xml.Schema.DatatypeImplementation::FinishBuiltinType(class System.Xml.Schema.XmlSchemaSimpleType derivedType, class System.Xml.Schema.XmlSchemaSimpleType baseType)
0xb82e4  ldloc.s  5
0xb82e6  ldc.i4.1
0xb82e7  add
0xb82e8  stloc.s  5
0xb82ea  ldloc.s  5
0xb82ec  ldsfld   class SchemaDatatypeMap[] System.Xml.Schema.DatatypeImplementation::c_XsdTypes
0xb82f1  ldlen
0xb82f2  conv.i4
0xb82f3  blt      loc_B8267
0xb82f8  ldstr    aAnyatomictype// "anyAtomicType"
0xb82fd  ldstr    aHttpWwwW3Org20_6// "http://www.w3.org/2003/11/xpath-datatyp"...
0xb8302  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xb8307  stloc.0
0xb8308  ldloc.0
0xb8309  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_anyAtomicType
0xb830e  call     class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::StartBuiltinType(class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaDatatype dataType)
0xb8313  stsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::anyAtomicType
0xb8318  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_anyAtomicType
0xb831d  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::anyAtomicType
0xb8322  stfld    class System.Xml.Schema.XmlSchemaType System.Xml.Schema.DatatypeImplementation::parentSchemaType
0xb8327  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::anyAtomicType
0xb832c  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::anySimpleType
0xb8331  call     void System.Xml.Schema.DatatypeImplementation::FinishBuiltinType(class System.Xml.Schema.XmlSchemaSimpleType derivedType, class System.Xml.Schema.XmlSchemaSimpleType baseType)
0xb8336  ldsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Schema.DatatypeImplementation::builtinTypes
0xb833b  ldloc.0
0xb833c  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::anyAtomicType
0xb8341  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xb8346  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType[] System.Xml.Schema.DatatypeImplementation::enumToTypeCode
0xb834b  ldc.i4.s 0xA
0xb834d  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::anyAtomicType
0xb8352  stelem.ref
0xb8353  ldstr    aUntypedatomic// "untypedAtomic"
0xb8358  ldstr    aHttpWwwW3Org20_6// "http://www.w3.org/2003/11/xpath-datatyp"...
0xb835d  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xb8362  stloc.0
0xb8363  ldloc.0
0xb8364  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_untypedAtomicType
0xb8369  call     class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::StartBuiltinType(class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaDatatype dataType)
0xb836e  stsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::untypedAtomicType
0xb8373  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_untypedAtomicType
0xb8378  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::untypedAtomicType
0xb837d  stfld    class System.Xml.Schema.XmlSchemaType System.Xml.Schema.DatatypeImplementation::parentSchemaType
0xb8382  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::untypedAtomicType
0xb8387  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::anyAtomicType
0xb838c  call     void System.Xml.Schema.DatatypeImplementation::FinishBuiltinType(class System.Xml.Schema.XmlSchemaSimpleType derivedType, class System.Xml.Schema.XmlSchemaSimpleType baseType)
0xb8391  ldsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Schema.DatatypeImplementation::builtinTypes
0xb8396  ldloc.0
0xb8397  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::untypedAtomicType
0xb839c  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xb83a1  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType[] System.Xml.Schema.DatatypeImplementation::enumToTypeCode
0xb83a6  ldc.i4.s 0xB
0xb83a8  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::untypedAtomicType
0xb83ad  stelem.ref
0xb83ae  ldstr    aYearmonthdurat// "yearMonthDuration"
0xb83b3  ldstr    aHttpWwwW3Org20_6// "http://www.w3.org/2003/11/xpath-datatyp"...
0xb83b8  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xb83bd  stloc.0
0xb83be  ldloc.0
0xb83bf  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_yearMonthDuration
0xb83c4  call     class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::StartBuiltinType(class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaDatatype dataType)
0xb83c9  stsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::yearMonthDurationType
0xb83ce  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_yearMonthDuration
0xb83d3  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::yearMonthDurationType
0xb83d8  stfld    class System.Xml.Schema.XmlSchemaType System.Xml.Schema.DatatypeImplementation::parentSchemaType
0xb83dd  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::yearMonthDurationType
0xb83e2  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType[] System.Xml.Schema.DatatypeImplementation::enumToTypeCode
0xb83e7  ldc.i4.s 0x11
0xb83e9  ldelem.ref
0xb83ea  call     void System.Xml.Schema.DatatypeImplementation::FinishBuiltinType(class System.Xml.Schema.XmlSchemaSimpleType derivedType, class System.Xml.Schema.XmlSchemaSimpleType baseType)
0xb83ef  ldsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Schema.DatatypeImplementation::builtinTypes
0xb83f4  ldloc.0
0xb83f5  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::yearMonthDurationType
0xb83fa  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xb83ff  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType[] System.Xml.Schema.DatatypeImplementation::enumToTypeCode
0xb8404  ldc.i4.s 0x35
0xb8406  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::yearMonthDurationType
0xb840b  stelem.ref
0xb840c  ldstr    aDaytimeduratio// "dayTimeDuration"
0xb8411  ldstr    aHttpWwwW3Org20_6// "http://www.w3.org/2003/11/xpath-datatyp"...
0xb8416  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xb841b  stloc.0
0xb841c  ldloc.0
0xb841d  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_dayTimeDuration
0xb8422  call     class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::StartBuiltinType(class System.Xml.XmlQualifiedName qname, class System.Xml.Schema.XmlSchemaDatatype dataType)
0xb8427  stsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::dayTimeDurationType
0xb842c  ldsfld   class System.Xml.Schema.DatatypeImplementation System.Xml.Schema.DatatypeImplementation::c_dayTimeDuration
0xb8431  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::dayTimeDurationType
0xb8436  stfld    class System.Xml.Schema.XmlSchemaType System.Xml.Schema.DatatypeImplementation::parentSchemaType
0xb843b  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::dayTimeDurationType
0xb8440  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType[] System.Xml.Schema.DatatypeImplementation::enumToTypeCode
0xb8445  ldc.i4.s 0x11
0xb8447  ldelem.ref
0xb8448  call     void System.Xml.Schema.DatatypeImplementation::FinishBuiltinType(class System.Xml.Schema.XmlSchemaSimpleType derivedType, class System.Xml.Schema.XmlSchemaSimpleType baseType)
0xb844d  ldsfld   class [mscorlib]System.Collections.Hashtable System.Xml.Schema.DatatypeImplementation::builtinTypes
0xb8452  ldloc.0
0xb8453  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::dayTimeDurationType
0xb8458  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xb845d  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType[] System.Xml.Schema.DatatypeImplementation::enumToTypeCode
0xb8462  ldc.i4.s 0x36
0xb8464  ldsfld   class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.DatatypeImplementation::dayTimeDurationType
0xb8469  stelem.ref
0xb846a  ret
```
