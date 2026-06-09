# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::validateInputXML

- ea: `0x1580`
- end: `0x15ec`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::validateInputXML`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0xb50`

## callees

- `0x1580`
- `0x15f0`

## pseudocode

```c

```

## disassembly

```asm
0x1580  ldarg.0
0x1581  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1586  brfalse.s loc_158A
0x1588  ldc.i4.1
0x1589  ret
0x158a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x158f  ldarg.1
0x1590  ldc.i4.1
0x1591  newarr   [mscorlib]System.Object
0x1596  stloc.2
0x1597  ldloc.2
0x1598  ldc.i4.0
0x1599  ldarg.0
0x159a  stelem.ref
0x159b  ldloc.2
0x159c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15a1  stloc.0
0x15a2  newobj   instance void [System.Xml]System.Xml.XmlReaderSettings::.ctor()
0x15a7  stloc.1
0x15a8  ldloc.1
0x15a9  ldc.i4.2
0x15aa  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_ConformanceLevel(valuetype [System.Xml]System.Xml.ConformanceLevel)
0x15af  ldloc.1
0x15b0  ldc.i4.4
0x15b1  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_ValidationType(valuetype [System.Xml]System.Xml.ValidationType)
0x15b6  ldloc.1
0x15b7  ldc.i4.1
0x15b8  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_IgnoreWhitespace(bool)
0x15bd  ldloc.1
0x15be  ldnull
0x15bf  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x15c4  ldloc.1
0x15c5  ldnull
0x15c6  ldftn    void Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::validationHandler(object sender, class [System.Xml]System.Xml.Schema.ValidationEventArgs args)
0x15cc  newobj   instance void [System.Xml]System.Xml.Schema.ValidationEventHandler::.ctor(object, native int)
0x15d1  callvirt instance void [System.Xml]System.Xml.XmlReaderSettings::add_ValidationEventHandler(class [System.Xml]System.Xml.Schema.ValidationEventHandler)
0x15d6  ldloc.1
0x15d7  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaSet [System.Xml]System.Xml.XmlReaderSettings::get_Schemas()
0x15dc  ldnull
0x15dd  ldarg.2
0x15de  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchema [System.Xml]System.Xml.Schema.XmlSchemaSet::Add(string, string)
0x15e3  pop
0x15e4  ldloc.0
0x15e5  ldloc.1
0x15e6  call     bool Microsoft.SharePoint.Spx.WebSite.ApplicationPages.ServiceHandler::validateXML(string xmlString, class [System.Xml]System.Xml.XmlReaderSettings validationSettings)
0x15eb  ret
```
