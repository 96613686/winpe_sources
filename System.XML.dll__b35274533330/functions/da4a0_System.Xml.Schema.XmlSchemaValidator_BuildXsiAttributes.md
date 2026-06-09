# System.Xml.Schema.XmlSchemaValidator::BuildXsiAttributes

- ea: `0xda4a0`
- end: `0xda5c8`
- name: `System.Xml.Schema.XmlSchemaValidator::BuildXsiAttributes`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0xd8ff0`

## callees

- `0x132e0`
- `0xd0930`
- `0xd0a90`
- `0xd0aa0`
- `0xd0b50`
- `0xd6a80`
- `0xda4a0`

## string_xrefs

- `0xda4be`: `http://www.w3.org/2001/XMLSchema-instance`
- `0xda505`: `http://www.w3.org/2001/XMLSchema-instance`
- `0xda554`: `http://www.w3.org/2001/XMLSchema-instance`
- `0xda5a1`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0xda4a0  ldsfld   class System.Xml.Schema.XmlSchemaAttribute System.Xml.Schema.XmlSchemaValidator::xsiTypeSO
0xda4a5  brtrue.s loc_DA4E7
0xda4a7  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0xda4ac  stloc.0
0xda4ad  ldloc.0
0xda4ae  ldstr    aType// "type"
0xda4b3  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Name(string value)
0xda4b8  ldloc.0
0xda4b9  ldstr    aType// "type"
0xda4be  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2001/XMLSchema-instan"...
0xda4c3  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xda4c8  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::SetQualifiedName(class System.Xml.XmlQualifiedName value)
0xda4cd  ldloc.0
0xda4ce  ldc.i4.s 0x1D
0xda4d0  call     class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.XmlSchemaType::GetBuiltInSimpleType(valuetype System.Xml.Schema.XmlTypeCode typeCode)
0xda4d5  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::SetAttributeType(class System.Xml.Schema.XmlSchemaSimpleType value)
0xda4da  ldsflda  class System.Xml.Schema.XmlSchemaAttribute System.Xml.Schema.XmlSchemaValidator::xsiTypeSO
0xda4df  ldloc.0
0xda4e0  ldnull
0xda4e1  call     T0x2B000141
0xda4e6  pop
0xda4e7  ldsfld   class System.Xml.Schema.XmlSchemaAttribute System.Xml.Schema.XmlSchemaValidator::xsiNilSO
0xda4ec  brtrue.s loc_DA52E
0xda4ee  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0xda4f3  stloc.1
0xda4f4  ldloc.1
0xda4f5  ldstr    aNil// "nil"
0xda4fa  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Name(string value)
0xda4ff  ldloc.1
0xda500  ldstr    aNil// "nil"
0xda505  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2001/XMLSchema-instan"...
0xda50a  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xda50f  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::SetQualifiedName(class System.Xml.XmlQualifiedName value)
0xda514  ldloc.1
0xda515  ldc.i4.s 0xD
0xda517  call     class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.XmlSchemaType::GetBuiltInSimpleType(valuetype System.Xml.Schema.XmlTypeCode typeCode)
0xda51c  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::SetAttributeType(class System.Xml.Schema.XmlSchemaSimpleType value)
0xda521  ldsflda  class System.Xml.Schema.XmlSchemaAttribute System.Xml.Schema.XmlSchemaValidator::xsiNilSO
0xda526  ldloc.1
0xda527  ldnull
0xda528  call     T0x2B000141
0xda52d  pop
0xda52e  ldsfld   class System.Xml.Schema.XmlSchemaAttribute System.Xml.Schema.XmlSchemaValidator::xsiSLSO
0xda533  brtrue.s loc_DA577
0xda535  ldc.i4.s 0xC
0xda537  call     class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.XmlSchemaType::GetBuiltInSimpleType(valuetype System.Xml.Schema.XmlTypeCode typeCode)
0xda53c  stloc.2
0xda53d  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0xda542  stloc.3
0xda543  ldloc.3
0xda544  ldstr    aSchemalocation// "schemaLocation"
0xda549  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Name(string value)
0xda54e  ldloc.3
0xda54f  ldstr    aSchemalocation// "schemaLocation"
0xda554  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2001/XMLSchema-instan"...
0xda559  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xda55e  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::SetQualifiedName(class System.Xml.XmlQualifiedName value)
0xda563  ldloc.3
0xda564  ldloc.2
0xda565  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::SetAttributeType(class System.Xml.Schema.XmlSchemaSimpleType value)
0xda56a  ldsflda  class System.Xml.Schema.XmlSchemaAttribute System.Xml.Schema.XmlSchemaValidator::xsiSLSO
0xda56f  ldloc.3
0xda570  ldnull
0xda571  call     T0x2B000141
0xda576  pop
0xda577  ldsfld   class System.Xml.Schema.XmlSchemaAttribute System.Xml.Schema.XmlSchemaValidator::xsiNoNsSLSO
0xda57c  brtrue.s loc_DA5C7
0xda57e  ldc.i4.s 0xC
0xda580  call     class System.Xml.Schema.XmlSchemaSimpleType System.Xml.Schema.XmlSchemaType::GetBuiltInSimpleType(valuetype System.Xml.Schema.XmlTypeCode typeCode)
0xda585  stloc.s  4
0xda587  newobj   instance void System.Xml.Schema.XmlSchemaAttribute::.ctor()
0xda58c  stloc.s  5
0xda58e  ldloc.s  5
0xda590  ldstr    aNonamespacesch// "noNamespaceSchemaLocation"
0xda595  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::set_Name(string value)
0xda59a  ldloc.s  5
0xda59c  ldstr    aNonamespacesch// "noNamespaceSchemaLocation"
0xda5a1  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2001/XMLSchema-instan"...
0xda5a6  newobj   instance void System.Xml.XmlQualifiedName::.ctor(string name, string ns)
0xda5ab  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::SetQualifiedName(class System.Xml.XmlQualifiedName value)
0xda5b0  ldloc.s  5
0xda5b2  ldloc.s  4
0xda5b4  callvirt instance void System.Xml.Schema.XmlSchemaAttribute::SetAttributeType(class System.Xml.Schema.XmlSchemaSimpleType value)
0xda5b9  ldsflda  class System.Xml.Schema.XmlSchemaAttribute System.Xml.Schema.XmlSchemaValidator::xsiNoNsSLSO
0xda5be  ldloc.s  5
0xda5c0  ldnull
0xda5c1  call     T0x2B000141
0xda5c6  pop
0xda5c7  ret
```
