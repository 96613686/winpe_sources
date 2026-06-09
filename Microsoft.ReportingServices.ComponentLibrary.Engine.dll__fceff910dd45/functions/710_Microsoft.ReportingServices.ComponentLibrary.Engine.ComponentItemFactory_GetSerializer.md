# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItemFactory::GetSerializer

- ea: `0x710`
- end: `0x784`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItemFactory::GetSerializer`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x350`
- `0x580`

## callees

- `0x710`
- `0x1e60`

## string_xrefs

- `0x734`: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentDefinition.xsd`

## pseudocode

```c

```

## disassembly

```asm
0x710  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializerSettings::.ctor()
0x715  dup
0x716  newobj   instance void ClSerializerHost::.ctor()
0x71b  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializerSettings::set_Host(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.ISerializerHost)
0x720  dup
0x721  ldc.i4.1
0x722  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializerSettings::set_IgnoreWhitespace(bool)
0x727  dup
0x728  ldc.i4.1
0x729  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializerSettings::set_ValidateXml(bool)
0x72e  dup
0x72f  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x734  ldstr    aMicrosoftRepor// "Microsoft.ReportingServices.ComponentLi"...
0x739  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x73e  ldnull
0x73f  call     class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchema::Read(class [mscorlib]System.IO.Stream, class [System.Xml]System.Xml.Schema.ValidationEventHandler)
0x744  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializerSettings::set_XmlSchema(class [System.Xml]System.Xml.Schema.XmlSchema)
0x749  dup
0x74a  dup
0x74b  callvirt instance class [System.Xml]System.Xml.Schema.ValidationEventHandler [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializerSettings::get_XmlValidationEventHandler()
0x750  ldsfld   class [System.Xml]System.Xml.Schema.ValidationEventHandler <>c::<>9__3_0
0x755  dup
0x756  brtrue.s loc_76F
0x758  pop
0x759  ldsfld   class <>c <>c::<>9
0x75e  ldftn    instance void <>c::<GetSerializer>b__3_0(object sender, class [System.Xml]System.Xml.Schema.ValidationEventArgs e)
0x764  newobj   instance void [System.Xml]System.Xml.Schema.ValidationEventHandler::.ctor(object, native int)
0x769  dup
0x76a  stsfld   class [System.Xml]System.Xml.Schema.ValidationEventHandler <>c::<>9__3_0
0x76f  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x774  castclass [System.Xml]System.Xml.Schema.ValidationEventHandler
0x779  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializerSettings::set_XmlValidationEventHandler(class [System.Xml]System.Xml.Schema.ValidationEventHandler)
0x77e  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializer::.ctor(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Serialization.RdlSerializerSettings)
0x783  ret
```
