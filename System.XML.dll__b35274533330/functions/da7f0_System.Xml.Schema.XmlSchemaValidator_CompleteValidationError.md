# System.Xml.Schema.XmlSchemaValidator::CompleteValidationError

- ea: `0xda7f0`
- end: `0xda934`
- name: `System.Xml.Schema.XmlSchemaValidator::CompleteValidationError`
- size: `324`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbbc20`
- `0xce2e0`
- `0xd86a0`
- `0xe7890`

## callees

- `0x62370`
- `0xb5b90`
- `0xb5ba0`
- `0xc9600`
- `0xd6ea0`
- `0xd6ed0`
- `0xda7f0`
- `0xda940`
- `0xdace0`
- `0xdaf80`

## string_xrefs

- `0xda863`: `Sch_ComplexContentModel`
- `0xda8dc`: `Sch_ComplexContentModel`
- `0xda842`: `Sch_IncompleteContentComplex`
- `0xda880`: `Sch_IncompleteContent`
- `0xda8b1`: `Sch_IncompleteContentExpectingComplex`
- `0xda8fa`: `Sch_IncompleteContentExpecting`

## pseudocode

```c

```

## disassembly

```asm
0xda7f0  ldnull
0xda7f1  stloc.0
0xda7f2  ldarg.s  6
0xda7f4  ldnull
0xda7f5  cgt.un
0xda7f7  stloc.1
0xda7f8  ldarg.0
0xda7f9  ldfld    class System.Xml.Schema.SchemaElementDecl System.Xml.Schema.ValidationState::ElementDecl
0xda7fe  brfalse.s loc_DA82D
0xda800  ldloc.1
0xda801  brfalse.s loc_DA81A
0xda803  ldarg.0
0xda804  ldfld    class System.Xml.Schema.SchemaElementDecl System.Xml.Schema.ValidationState::ElementDecl
0xda809  callvirt instance class System.Xml.Schema.ContentValidator System.Xml.Schema.SchemaElementDecl::get_ContentValidator()
0xda80e  ldarg.0
0xda80f  ldc.i4.1
0xda810  ldarg.s  6
0xda812  callvirt instance class [mscorlib]System.Collections.ArrayList System.Xml.Schema.ContentValidator::ExpectedParticles(class System.Xml.Schema.ValidationState context, bool isRequiredOnly, class System.Xml.Schema.XmlSchemaSet schemaSet)
0xda817  stloc.0
0xda818  br.s     loc_DA82D
0xda81a  ldarg.0
0xda81b  ldfld    class System.Xml.Schema.SchemaElementDecl System.Xml.Schema.ValidationState::ElementDecl
0xda820  callvirt instance class System.Xml.Schema.ContentValidator System.Xml.Schema.SchemaElementDecl::get_ContentValidator()
0xda825  ldarg.0
0xda826  ldc.i4.1
0xda827  callvirt instance class [mscorlib]System.Collections.ArrayList System.Xml.Schema.ContentValidator::ExpectedElements(class System.Xml.Schema.ValidationState context, bool isRequiredOnly)
0xda82c  stloc.0
0xda82d  ldloc.0
0xda82e  brfalse.s loc_DA838
0xda830  ldloc.0
0xda831  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xda836  brtrue.s loc_DA8A7
0xda838  ldarg.0
0xda839  ldfld    bool System.Xml.Schema.ValidationState::TooComplex
0xda83e  brfalse.s loc_DA87E
0xda840  ldarg.1
0xda841  ldarg.2
0xda842  ldstr    aSchIncompletec// "Sch_IncompleteContentComplex"
0xda847  ldc.i4.2
0xda848  newarr   [mscorlib]System.String
0xda84d  dup
0xda84e  ldc.i4.0
0xda84f  ldarg.0
0xda850  ldfld    string System.Xml.Schema.ValidationState::LocalName
0xda855  ldarg.0
0xda856  ldfld    string System.Xml.Schema.ValidationState::Namespace
0xda85b  call     string System.Xml.Schema.XmlSchemaValidator::BuildElementName(string localName, string ns)
0xda860  stelem.ref
0xda861  dup
0xda862  ldc.i4.1
0xda863  ldstr    aSchComplexcont// "Sch_ComplexContentModel"
0xda868  call     string System.Xml.Res::GetString(string name)
0xda86d  stelem.ref
0xda86e  ldarg.3
0xda86f  ldarg.s  4
0xda871  ldarg.s  5
0xda873  newobj   instance void System.Xml.Schema.XmlSchemaValidationException::.ctor(string res, string[] args, string sourceUri, int32 lineNumber, int32 linePosition)
0xda878  ldc.i4.0
0xda879  call     void System.Xml.Schema.XmlSchemaValidator::SendValidationEvent(class System.Xml.Schema.ValidationEventHandler eventHandler, object sender, class System.Xml.Schema.XmlSchemaValidationException e, valuetype System.Xml.Schema.XmlSeverityType severity)
0xda87e  ldarg.1
0xda87f  ldarg.2
0xda880  ldstr    aSchIncompletec_0// "Sch_IncompleteContent"
0xda885  ldarg.0
0xda886  ldfld    string System.Xml.Schema.ValidationState::LocalName
0xda88b  ldarg.0
0xda88c  ldfld    string System.Xml.Schema.ValidationState::Namespace
0xda891  call     string System.Xml.Schema.XmlSchemaValidator::BuildElementName(string localName, string ns)
0xda896  ldarg.3
0xda897  ldarg.s  4
0xda899  ldarg.s  5
0xda89b  newobj   instance void System.Xml.Schema.XmlSchemaValidationException::.ctor(string res, string arg, string sourceUri, int32 lineNumber, int32 linePosition)
0xda8a0  ldc.i4.0
0xda8a1  call     void System.Xml.Schema.XmlSchemaValidator::SendValidationEvent(class System.Xml.Schema.ValidationEventHandler eventHandler, object sender, class System.Xml.Schema.XmlSchemaValidationException e, valuetype System.Xml.Schema.XmlSeverityType severity)
0xda8a6  ret
0xda8a7  ldarg.0
0xda8a8  ldfld    bool System.Xml.Schema.ValidationState::TooComplex
0xda8ad  brfalse.s loc_DA8F8
0xda8af  ldarg.1
0xda8b0  ldarg.2
0xda8b1  ldstr    aSchIncompletec_1// "Sch_IncompleteContentExpectingComplex"
0xda8b6  ldc.i4.3
0xda8b7  newarr   [mscorlib]System.String
0xda8bc  dup
0xda8bd  ldc.i4.0
0xda8be  ldarg.0
0xda8bf  ldfld    string System.Xml.Schema.ValidationState::LocalName
0xda8c4  ldarg.0
0xda8c5  ldfld    string System.Xml.Schema.ValidationState::Namespace
0xda8ca  call     string System.Xml.Schema.XmlSchemaValidator::BuildElementName(string localName, string ns)
0xda8cf  stelem.ref
0xda8d0  dup
0xda8d1  ldc.i4.1
0xda8d2  ldloc.0
0xda8d3  ldloc.1
0xda8d4  call     string System.Xml.Schema.XmlSchemaValidator::PrintExpectedElements(class [mscorlib]System.Collections.ArrayList expected, bool getParticles)
0xda8d9  stelem.ref
0xda8da  dup
0xda8db  ldc.i4.2
0xda8dc  ldstr    aSchComplexcont// "Sch_ComplexContentModel"
0xda8e1  call     string System.Xml.Res::GetString(string name)
0xda8e6  stelem.ref
0xda8e7  ldarg.3
0xda8e8  ldarg.s  4
0xda8ea  ldarg.s  5
0xda8ec  newobj   instance void System.Xml.Schema.XmlSchemaValidationException::.ctor(string res, string[] args, string sourceUri, int32 lineNumber, int32 linePosition)
0xda8f1  ldc.i4.0
0xda8f2  call     void System.Xml.Schema.XmlSchemaValidator::SendValidationEvent(class System.Xml.Schema.ValidationEventHandler eventHandler, object sender, class System.Xml.Schema.XmlSchemaValidationException e, valuetype System.Xml.Schema.XmlSeverityType severity)
0xda8f7  ret
0xda8f8  ldarg.1
0xda8f9  ldarg.2
0xda8fa  ldstr    aSchIncompletec_2// "Sch_IncompleteContentExpecting"
0xda8ff  ldc.i4.2
0xda900  newarr   [mscorlib]System.String
0xda905  dup
0xda906  ldc.i4.0
0xda907  ldarg.0
0xda908  ldfld    string System.Xml.Schema.ValidationState::LocalName
0xda90d  ldarg.0
0xda90e  ldfld    string System.Xml.Schema.ValidationState::Namespace
0xda913  call     string System.Xml.Schema.XmlSchemaValidator::BuildElementName(string localName, string ns)
0xda918  stelem.ref
0xda919  dup
0xda91a  ldc.i4.1
0xda91b  ldloc.0
0xda91c  ldloc.1
0xda91d  call     string System.Xml.Schema.XmlSchemaValidator::PrintExpectedElements(class [mscorlib]System.Collections.ArrayList expected, bool getParticles)
0xda922  stelem.ref
0xda923  ldarg.3
0xda924  ldarg.s  4
0xda926  ldarg.s  5
0xda928  newobj   instance void System.Xml.Schema.XmlSchemaValidationException::.ctor(string res, string[] args, string sourceUri, int32 lineNumber, int32 linePosition)
0xda92d  ldc.i4.0
0xda92e  call     void System.Xml.Schema.XmlSchemaValidator::SendValidationEvent(class System.Xml.Schema.ValidationEventHandler eventHandler, object sender, class System.Xml.Schema.XmlSchemaValidationException e, valuetype System.Xml.Schema.XmlSeverityType severity)
0xda933  ret
```
