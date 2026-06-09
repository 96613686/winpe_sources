# System.Xml.Schema.XmlSchemaValidator::ElementValidationError

- ea: `0xda5d0`
- end: `0xda7f0`
- name: `System.Xml.Schema.XmlSchemaValidator::ElementValidationError`
- size: `544`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbb890`
- `0xce120`
- `0xd8980`
- `0xe7480`

## callees

- `0x62370`
- `0xb5ae0`
- `0xb5b20`
- `0xb5b90`
- `0xb5ba0`
- `0xc9600`
- `0xd6ed0`
- `0xda5d0`
- `0xda940`
- `0xdaca0`
- `0xdacc0`
- `0xdace0`
- `0xdaf80`

## string_xrefs

- `0xda672`: `Sch_ComplexContentModel`
- `0xda709`: `Sch_ComplexContentModel`
- `0xda648`: `Sch_InvalidElementContentComplex`
- `0xda6d5`: `Sch_InvalidElementContentExpectingComplex`

## pseudocode

```c

```

## disassembly

```asm
0xda5d0  ldnull
0xda5d1  stloc.0
0xda5d2  ldarg.1
0xda5d3  ldfld    class System.Xml.Schema.SchemaElementDecl System.Xml.Schema.ValidationState::ElementDecl
0xda5d8  brfalse  loc_DA7EF
0xda5dd  ldarg.1
0xda5de  ldfld    class System.Xml.Schema.SchemaElementDecl System.Xml.Schema.ValidationState::ElementDecl
0xda5e3  callvirt instance class System.Xml.Schema.ContentValidator System.Xml.Schema.SchemaElementDecl::get_ContentValidator()
0xda5e8  stloc.1
0xda5e9  ldloc.1
0xda5ea  callvirt instance valuetype System.Xml.Schema.XmlSchemaContentType System.Xml.Schema.ContentValidator::get_ContentType()
0xda5ef  stloc.2
0xda5f0  ldloc.2
0xda5f1  ldc.i4.2
0xda5f2  beq.s    loc_DA611
0xda5f4  ldloc.2
0xda5f5  ldc.i4.3
0xda5f6  bne.un   loc_DA76C
0xda5fb  ldloc.1
0xda5fc  ldsfld   class System.Xml.Schema.ContentValidator System.Xml.Schema.ContentValidator::Mixed
0xda601  beq      loc_DA76C
0xda606  ldloc.1
0xda607  ldsfld   class System.Xml.Schema.ContentValidator System.Xml.Schema.ContentValidator::Any
0xda60c  beq      loc_DA76C
0xda611  ldarg.s  7
0xda613  ldnull
0xda614  cgt.un
0xda616  stloc.3
0xda617  ldloc.3
0xda618  brfalse.s loc_DA627
0xda61a  ldloc.1
0xda61b  ldarg.1
0xda61c  ldc.i4.0
0xda61d  ldarg.s  7
0xda61f  callvirt instance class [mscorlib]System.Collections.ArrayList System.Xml.Schema.ContentValidator::ExpectedParticles(class System.Xml.Schema.ValidationState context, bool isRequiredOnly, class System.Xml.Schema.XmlSchemaSet schemaSet)
0xda624  stloc.0
0xda625  br.s     loc_DA630
0xda627  ldloc.1
0xda628  ldarg.1
0xda629  ldc.i4.0
0xda62a  callvirt instance class [mscorlib]System.Collections.ArrayList System.Xml.Schema.ContentValidator::ExpectedElements(class System.Xml.Schema.ValidationState context, bool isRequiredOnly)
0xda62f  stloc.0
0xda630  ldloc.0
0xda631  brfalse.s loc_DA63E
0xda633  ldloc.0
0xda634  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xda639  brtrue   loc_DA6CB
0xda63e  ldarg.1
0xda63f  ldfld    bool System.Xml.Schema.ValidationState::TooComplex
0xda644  brfalse.s loc_DA68F
0xda646  ldarg.2
0xda647  ldarg.3
0xda648  ldstr    aSchInvalidelem_4// "Sch_InvalidElementContentComplex"
0xda64d  ldc.i4.3
0xda64e  newarr   [mscorlib]System.String
0xda653  dup
0xda654  ldc.i4.0
0xda655  ldarg.1
0xda656  ldfld    string System.Xml.Schema.ValidationState::LocalName
0xda65b  ldarg.1
0xda65c  ldfld    string System.Xml.Schema.ValidationState::Namespace
0xda661  call     string System.Xml.Schema.XmlSchemaValidator::BuildElementName(string localName, string ns)
0xda666  stelem.ref
0xda667  dup
0xda668  ldc.i4.1
0xda669  ldarg.0
0xda66a  call     string System.Xml.Schema.XmlSchemaValidator::BuildElementName(class System.Xml.XmlQualifiedName qname)
0xda66f  stelem.ref
0xda670  dup
0xda671  ldc.i4.2
0xda672  ldstr    aSchComplexcont// "Sch_ComplexContentModel"
0xda677  call     string System.Xml.Res::GetString(string name)
0xda67c  stelem.ref
0xda67d  ldarg.s  4
0xda67f  ldarg.s  5
0xda681  ldarg.s  6
0xda683  newobj   instance void System.Xml.Schema.XmlSchemaValidationException::.ctor(string res, string[] args, string sourceUri, int32 lineNumber, int32 linePosition)
0xda688  ldc.i4.0
0xda689  call     void System.Xml.Schema.XmlSchemaValidator::SendValidationEvent(class System.Xml.Schema.ValidationEventHandler eventHandler, object sender, class System.Xml.Schema.XmlSchemaValidationException e, valuetype System.Xml.Schema.XmlSeverityType severity)
0xda68e  ret
0xda68f  ldarg.2
0xda690  ldarg.3
0xda691  ldstr    aSchInvalidelem_5// "Sch_InvalidElementContent"
0xda696  ldc.i4.2
0xda697  newarr   [mscorlib]System.String
0xda69c  dup
0xda69d  ldc.i4.0
0xda69e  ldarg.1
0xda69f  ldfld    string System.Xml.Schema.ValidationState::LocalName
0xda6a4  ldarg.1
0xda6a5  ldfld    string System.Xml.Schema.ValidationState::Namespace
0xda6aa  call     string System.Xml.Schema.XmlSchemaValidator::BuildElementName(string localName, string ns)
0xda6af  stelem.ref
0xda6b0  dup
0xda6b1  ldc.i4.1
0xda6b2  ldarg.0
0xda6b3  call     string System.Xml.Schema.XmlSchemaValidator::BuildElementName(class System.Xml.XmlQualifiedName qname)
0xda6b8  stelem.ref
0xda6b9  ldarg.s  4
0xda6bb  ldarg.s  5
0xda6bd  ldarg.s  6
0xda6bf  newobj   instance void System.Xml.Schema.XmlSchemaValidationException::.ctor(string res, string[] args, string sourceUri, int32 lineNumber, int32 linePosition)
0xda6c4  ldc.i4.0
0xda6c5  call     void System.Xml.Schema.XmlSchemaValidator::SendValidationEvent(class System.Xml.Schema.ValidationEventHandler eventHandler, object sender, class System.Xml.Schema.XmlSchemaValidationException e, valuetype System.Xml.Schema.XmlSeverityType severity)
0xda6ca  ret
0xda6cb  ldarg.1
0xda6cc  ldfld    bool System.Xml.Schema.ValidationState::TooComplex
0xda6d1  brfalse.s loc_DA726
0xda6d3  ldarg.2
0xda6d4  ldarg.3
0xda6d5  ldstr    aSchInvalidelem_6// "Sch_InvalidElementContentExpectingCompl"...
0xda6da  ldc.i4.4
0xda6db  newarr   [mscorlib]System.String
0xda6e0  dup
0xda6e1  ldc.i4.0
0xda6e2  ldarg.1
0xda6e3  ldfld    string System.Xml.Schema.ValidationState::LocalName
0xda6e8  ldarg.1
0xda6e9  ldfld    string System.Xml.Schema.ValidationState::Namespace
0xda6ee  call     string System.Xml.Schema.XmlSchemaValidator::BuildElementName(string localName, string ns)
0xda6f3  stelem.ref
0xda6f4  dup
0xda6f5  ldc.i4.1
0xda6f6  ldarg.0
0xda6f7  call     string System.Xml.Schema.XmlSchemaValidator::BuildElementName(class System.Xml.XmlQualifiedName qname)
0xda6fc  stelem.ref
0xda6fd  dup
0xda6fe  ldc.i4.2
0xda6ff  ldloc.0
0xda700  ldloc.3
0xda701  call     string System.Xml.Schema.XmlSchemaValidator::PrintExpectedElements(class [mscorlib]System.Collections.ArrayList expected, bool getParticles)
0xda706  stelem.ref
0xda707  dup
0xda708  ldc.i4.3
0xda709  ldstr    aSchComplexcont// "Sch_ComplexContentModel"
0xda70e  call     string System.Xml.Res::GetString(string name)
0xda713  stelem.ref
0xda714  ldarg.s  4
0xda716  ldarg.s  5
0xda718  ldarg.s  6
0xda71a  newobj   instance void System.Xml.Schema.XmlSchemaValidationException::.ctor(string res, string[] args, string sourceUri, int32 lineNumber, int32 linePosition)
0xda71f  ldc.i4.0
0xda720  call     void System.Xml.Schema.XmlSchemaValidator::SendValidationEvent(class System.Xml.Schema.ValidationEventHandler eventHandler, object sender, class System.Xml.Schema.XmlSchemaValidationException e, valuetype System.Xml.Schema.XmlSeverityType severity)
0xda725  ret
0xda726  ldarg.2
0xda727  ldarg.3
0xda728  ldstr    aSchInvalidelem_7// "Sch_InvalidElementContentExpecting"
0xda72d  ldc.i4.3
0xda72e  newarr   [mscorlib]System.String
0xda733  dup
0xda734  ldc.i4.0
0xda735  ldarg.1
0xda736  ldfld    string System.Xml.Schema.ValidationState::LocalName
0xda73b  ldarg.1
0xda73c  ldfld    string System.Xml.Schema.ValidationState::Namespace
0xda741  call     string System.Xml.Schema.XmlSchemaValidator::BuildElementName(string localName, string ns)
0xda746  stelem.ref
0xda747  dup
0xda748  ldc.i4.1
0xda749  ldarg.0
0xda74a  call     string System.Xml.Schema.XmlSchemaValidator::BuildElementName(class System.Xml.XmlQualifiedName qname)
0xda74f  stelem.ref
0xda750  dup
0xda751  ldc.i4.2
0xda752  ldloc.0
0xda753  ldloc.3
0xda754  call     string System.Xml.Schema.XmlSchemaValidator::PrintExpectedElements(class [mscorlib]System.Collections.ArrayList expected, bool getParticles)
0xda759  stelem.ref
0xda75a  ldarg.s  4
0xda75c  ldarg.s  5
0xda75e  ldarg.s  6
0xda760  newobj   instance void System.Xml.Schema.XmlSchemaValidationException::.ctor(string res, string[] args, string sourceUri, int32 lineNumber, int32 linePosition)
0xda765  ldc.i4.0
0xda766  call     void System.Xml.Schema.XmlSchemaValidator::SendValidationEvent(class System.Xml.Schema.ValidationEventHandler eventHandler, object sender, class System.Xml.Schema.XmlSchemaValidationException e, valuetype System.Xml.Schema.XmlSeverityType severity)
0xda76b  ret
0xda76c  ldloc.2
0xda76d  ldc.i4.1
0xda76e  bne.un.s loc_DA7AC
0xda770  ldarg.2
0xda771  ldarg.3
0xda772  ldstr    aSchInvalidelem_8// "Sch_InvalidElementInEmptyEx"
0xda777  ldc.i4.2
0xda778  newarr   [mscorlib]System.String
0xda77d  dup
0xda77e  ldc.i4.0
0xda77f  ldarg.1
0xda780  ldfld    string System.Xml.Schema.ValidationState::LocalName
0xda785  ldarg.1
0xda786  ldfld    string System.Xml.Schema.ValidationState::Namespace
0xda78b  call     string System.Xml.Schema.XmlSchemaValidator::QNameString(string localName, string ns)
0xda790  stelem.ref
0xda791  dup
0xda792  ldc.i4.1
0xda793  ldarg.0
0xda794  callvirt instance string [mscorlib]System.Object::ToString()
0xda799  stelem.ref
0xda79a  ldarg.s  4
0xda79c  ldarg.s  5
0xda79e  ldarg.s  6
0xda7a0  newobj   instance void System.Xml.Schema.XmlSchemaValidationException::.ctor(string res, string[] args, string sourceUri, int32 lineNumber, int32 linePosition)
0xda7a5  ldc.i4.0
0xda7a6  call     void System.Xml.Schema.XmlSchemaValidator::SendValidationEvent(class System.Xml.Schema.ValidationEventHandler eventHandler, object sender, class System.Xml.Schema.XmlSchemaValidationException e, valuetype System.Xml.Schema.XmlSeverityType severity)
0xda7ab  ret
0xda7ac  ldloc.1
0xda7ad  callvirt instance bool System.Xml.Schema.ContentValidator::get_IsOpen()
0xda7b2  brtrue.s loc_DA7EF
0xda7b4  ldarg.2
0xda7b5  ldarg.3
0xda7b6  ldstr    aSchInvalidelem_9// "Sch_InvalidElementInTextOnlyEx"
0xda7bb  ldc.i4.2
0xda7bc  newarr   [mscorlib]System.String
0xda7c1  dup
0xda7c2  ldc.i4.0
0xda7c3  ldarg.1
0xda7c4  ldfld    string System.Xml.Schema.ValidationState::LocalName
0xda7c9  ldarg.1
0xda7ca  ldfld    string System.Xml.Schema.ValidationState::Namespace
0xda7cf  call     string System.Xml.Schema.XmlSchemaValidator::QNameString(string localName, string ns)
0xda7d4  stelem.ref
0xda7d5  dup
0xda7d6  ldc.i4.1
0xda7d7  ldarg.0
0xda7d8  callvirt instance string [mscorlib]System.Object::ToString()
0xda7dd  stelem.ref
0xda7de  ldarg.s  4
0xda7e0  ldarg.s  5
0xda7e2  ldarg.s  6
0xda7e4  newobj   instance void System.Xml.Schema.XmlSchemaValidationException::.ctor(string res, string[] args, string sourceUri, int32 lineNumber, int32 linePosition)
0xda7e9  ldc.i4.0
0xda7ea  call     void System.Xml.Schema.XmlSchemaValidator::SendValidationEvent(class System.Xml.Schema.ValidationEventHandler eventHandler, object sender, class System.Xml.Schema.XmlSchemaValidationException e, valuetype System.Xml.Schema.XmlSeverityType severity)
0xda7ef  ret
```
