# Microsoft.ReportingServices.Library.ServerConfigInfo::ThisArrayToXml

- ea: `0x4e0`
- end: `0x5bc`
- name: `Microsoft.ReportingServices.Library.ServerConfigInfo::ThisArrayToXml`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x42750`

## callees

- `0x4e0`

## string_xrefs

- `0x4f8`: `ServerConfigInfo`
- `0x561`: `ServiceAccountName`

## pseudocode

```c

```

## disassembly

```asm
0x4e0  ldarg.0
0x4e1  brtrue.s loc_4E5
0x4e3  ldnull
0x4e4  ret
0x4e5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_CatalogCulture()
0x4ea  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x4ef  stloc.0
0x4f0  ldloc.0
0x4f1  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x4f6  stloc.1
0x4f7  ldloc.1
0x4f8  ldstr    aServerconfigin// "ServerConfigInfo"
0x4fd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x502  ldc.i4.0
0x503  stloc.2
0x504  br       loc_59A
0x509  ldarg.0
0x50a  ldloc.2
0x50b  ldelem.ref
0x50c  brfalse  loc_596
0x511  ldloc.1
0x512  ldstr    aServer// "Server"
0x517  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x51c  ldarg.0
0x51d  ldloc.2
0x51e  ldelem.ref
0x51f  ldfld    string Microsoft.ReportingServices.Library.ServerConfigInfo::MachineName
0x524  brfalse.s loc_539
0x526  ldloc.1
0x527  ldstr    aMachinename// "MachineName"
0x52c  ldarg.0
0x52d  ldloc.2
0x52e  ldelem.ref
0x52f  ldfld    string Microsoft.ReportingServices.Library.ServerConfigInfo::MachineName
0x534  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x539  ldarg.0
0x53a  ldloc.2
0x53b  ldelem.ref
0x53c  ldfld    string Microsoft.ReportingServices.Library.ServerConfigInfo::InstanceName
0x541  brfalse.s loc_556
0x543  ldloc.1
0x544  ldstr    aInstancename// "InstanceName"
0x549  ldarg.0
0x54a  ldloc.2
0x54b  ldelem.ref
0x54c  ldfld    string Microsoft.ReportingServices.Library.ServerConfigInfo::InstanceName
0x551  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x556  ldarg.0
0x557  ldloc.2
0x558  ldelem.ref
0x559  ldfld    string Microsoft.ReportingServices.Library.ServerConfigInfo::ServiceAccountName
0x55e  brfalse.s loc_573
0x560  ldloc.1
0x561  ldstr    aServiceaccount// "ServiceAccountName"
0x566  ldarg.0
0x567  ldloc.2
0x568  ldelem.ref
0x569  ldfld    string Microsoft.ReportingServices.Library.ServerConfigInfo::ServiceAccountName
0x56e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x573  ldarg.0
0x574  ldloc.2
0x575  ldelem.ref
0x576  ldfld    string Microsoft.ReportingServices.Library.ServerConfigInfo::ReportServerUrlItem
0x57b  brfalse.s loc_590
0x57d  ldloc.1
0x57e  ldstr    aReportserverur// "ReportServerUrlItem"
0x583  ldarg.0
0x584  ldloc.2
0x585  ldelem.ref
0x586  ldfld    string Microsoft.ReportingServices.Library.ServerConfigInfo::ReportServerUrlItem
0x58b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x590  ldloc.1
0x591  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x596  ldloc.2
0x597  ldc.i4.1
0x598  add
0x599  stloc.2
0x59a  ldloc.2
0x59b  ldarg.0
0x59c  ldlen
0x59d  conv.i4
0x59e  blt      loc_509
0x5a3  ldloc.1
0x5a4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x5a9  ldloc.1
0x5aa  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x5af  ldloc.1
0x5b0  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x5b5  ldloc.0
0x5b6  callvirt instance string [mscorlib]System.Object::ToString()
0x5bb  ret
```
