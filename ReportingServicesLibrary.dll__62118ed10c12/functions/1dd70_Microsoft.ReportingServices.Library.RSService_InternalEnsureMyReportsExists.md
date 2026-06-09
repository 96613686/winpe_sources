# Microsoft.ReportingServices.Library.RSService::InternalEnsureMyReportsExists

- ea: `0x1dd70`
- end: `0x1dfd4`
- name: `Microsoft.ReportingServices.Library.RSService::InternalEnsureMyReportsExists`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1dd40`

## callees

- `0xcd40`
- `0xd120`
- `0xd130`
- `0xd150`
- `0xf590`
- `0xf5a0`
- `0x1d860`
- `0x1dcc0`
- `0x1dd70`
- `0x1e0d0`
- `0x1e0e0`
- `0x1e210`
- `0x1e2e0`
- `0x1e510`
- `0x1e570`
- `0x49b10`

## string_xrefs

- `0x1ddd7`: `EnsureMyReportsExists: Users folder not found when My Reports accessed.`
- `0x1def8`: `EnsureMyReportsExists: Users home folder does not exist but can not be created.`
- `0x1dfba`: `EnsureMyReportsExists: created My Reports folder '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x1dd70  ldarg.0
0x1dd71  ldarg.0
0x1dd72  call     instance string Microsoft.ReportingServices.Library.RSService::get_UserName()
0x1dd77  call     instance string Microsoft.ReportingServices.Library.RSService::UserNameToFolderName(string user)
0x1dd7c  stloc.0
0x1dd7d  ldsfld   string Microsoft.ReportingServices.Library.Global::AllUsersFolderPathSlash
0x1dd82  ldloc.0
0x1dd83  call     string [mscorlib]System.String::Concat(string, string)
0x1dd88  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::.ctor(string)
0x1dd8d  stloc.1
0x1dd8e  ldloc.1
0x1dd8f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x1dd94  ldstr    asc_96832// "/"
0x1dd99  ldsfld   string Microsoft.ReportingServices.Library.Global::PhysicalMyReportsName
0x1dd9e  call     string [mscorlib]System.String::Concat(string, string, string)
0x1dda3  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::.ctor(string)
0x1dda8  stloc.2
0x1dda9  ldarg.0
0x1ddaa  call     instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x1ddaf  ldloc.2
0x1ddb0  callvirt instance bool Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath objectName)
0x1ddb5  brtrue   loc_1DFD3
0x1ddba  ldarg.0
0x1ddbb  call     instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x1ddc0  ldsfld   string Microsoft.ReportingServices.Library.Global::AllUsersFolderPath
0x1ddc5  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::.ctor(string)
0x1ddca  ldloca.s 3
0x1ddcc  ldloca.s 4
0x1ddce  ldloca.s 5
0x1ddd0  callvirt instance bool Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath objectName, [out] valuetype Microsoft.ReportingServices.Library.ItemType& type, [out] valuetype [mscorlib]System.Guid& id, [out] unsigned int8[]& secDesc)
0x1ddd5  brtrue.s loc_1DDE2
0x1ddd7  ldstr    aEnsuremyreport// "EnsureMyReportsExists: Users folder not"...
0x1dddc  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x1dde1  throw
0x1dde2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1dde7  stloc.s  6
0x1dde9  ldarg.0
0x1ddea  call     instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x1ddef  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1ddf4  ldloc.0
0x1ddf5  ldloc.1
0x1ddf6  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::get_NativeCatalogItemPath()
0x1ddfb  ldsfld   string Microsoft.ReportingServices.Library.Global::AllUsersFolderPath
0x1de00  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::.ctor(string)
0x1de05  ldloc.s  4
0x1de07  ldc.i4.1
0x1de08  ldnull
0x1de09  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1de0e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1de13  ldnull
0x1de14  ldnull
0x1de15  ldnull
0x1de16  ldarg.0
0x1de17  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x1de1c  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x1de21  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::GetSystemSid(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType authType)
0x1de26  ldarg.0
0x1de27  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x1de2c  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x1de31  call     string Microsoft.ReportingServices.Library.Global::GetSystemUserName(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType authType)
0x1de36  ldloc.s  6
0x1de38  ldloc.s  6
0x1de3a  ldnull
0x1de3b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.IDBInterface::CreateObject(valuetype [mscorlib]System.Guid id, string shortName, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath fullPath, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath parentPath, valuetype [mscorlib]System.Guid parentId, valuetype Microsoft.ReportingServices.Library.ItemType objectType, unsigned int8[] objectContent, valuetype [mscorlib]System.Guid intermediateSnapshotID, valuetype [mscorlib]System.Guid link, string linkPath, class Microsoft.ReportingServices.Library.ItemProperties objectProperties, string parameters, unsigned int8[] createdBySid, string createdBy, valuetype [mscorlib]System.DateTime creationDate, valuetype [mscorlib]System.DateTime modificationDate, string mimeType)
0x1de40  stloc.s  7
0x1de42  ldloc.s  7
0x1de44  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1de49  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1de4e  brfalse.s loc_1DE86
0x1de50  ldarg.0
0x1de51  call     instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x1de56  ldloc.1
0x1de57  ldloca.s 9
0x1de59  ldloca.s 7
0x1de5b  ldloca.s 0xA
0x1de5d  callvirt instance bool Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath objectName, [out] valuetype Microsoft.ReportingServices.Library.ItemType& type, [out] valuetype [mscorlib]System.Guid& id, [out] unsigned int8[]& secDesc)
0x1de62  brtrue.s loc_1DE6F
0x1de64  ldstr    aEnsuremyreport_0// "EnsureMyReportsExists: Creation of user"...
0x1de69  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x1de6e  throw
0x1de6f  ldloc.s  9
0x1de71  ldloc.1
0x1de72  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x1de77  ldc.i4.1
0x1de78  newarr   Microsoft.ReportingServices.Library.ItemType
0x1de7d  dup
0x1de7e  ldc.i4.0
0x1de7f  ldc.i4.1
0x1de80  stelem.i4
0x1de81  call     void Microsoft.ReportingServices.Library.RSService::EnsureItemType(valuetype Microsoft.ReportingServices.Library.ItemType actualType, string path, valuetype Microsoft.ReportingServices.Library.ItemType[] expectedTypes)
0x1de86  ldarg.0
0x1de87  call     instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x1de8c  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1de91  ldsfld   string Microsoft.ReportingServices.Library.Global::PhysicalMyReportsName
0x1de96  ldloc.2
0x1de97  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::get_NativeCatalogItemPath()
0x1de9c  ldloc.1
0x1de9d  ldloc.s  7
0x1de9f  ldc.i4.1
0x1dea0  ldnull
0x1dea1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1dea6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1deab  ldnull
0x1deac  ldnull
0x1dead  ldnull
0x1deae  ldarg.0
0x1deaf  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x1deb4  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x1deb9  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::GetSystemSid(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType authType)
0x1debe  ldarg.0
0x1debf  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x1dec4  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x1dec9  call     string Microsoft.ReportingServices.Library.Global::GetSystemUserName(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType authType)
0x1dece  ldloc.s  6
0x1ded0  ldloc.s  6
0x1ded2  ldnull
0x1ded3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.IDBInterface::CreateObject(valuetype [mscorlib]System.Guid id, string shortName, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath fullPath, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath parentPath, valuetype [mscorlib]System.Guid parentId, valuetype Microsoft.ReportingServices.Library.ItemType objectType, unsigned int8[] objectContent, valuetype [mscorlib]System.Guid intermediateSnapshotID, valuetype [mscorlib]System.Guid link, string linkPath, class Microsoft.ReportingServices.Library.ItemProperties objectProperties, string parameters, unsigned int8[] createdBySid, string createdBy, valuetype [mscorlib]System.DateTime creationDate, valuetype [mscorlib]System.DateTime modificationDate, string mimeType)
0x1ded8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1dedd  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1dee2  stloc.s  8
0x1dee4  ldloc.s  8
0x1dee6  brtrue.s loc_1DF1A
0x1dee8  ldarg.0
0x1dee9  call     instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x1deee  ldloc.2
0x1deef  ldloca.s 0xB
0x1def1  callvirt instance bool Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath objectName, [out] valuetype Microsoft.ReportingServices.Library.ItemType& type)
0x1def6  brtrue.s loc_1DF03
0x1def8  ldstr    aEnsuremyreport_1// "EnsureMyReportsExists: Users home folde"...
0x1defd  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x1df02  throw
0x1df03  ldloc.s  0xB
0x1df05  ldloc.2
0x1df06  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x1df0b  ldc.i4.1
0x1df0c  newarr   Microsoft.ReportingServices.Library.ItemType
0x1df11  dup
0x1df12  ldc.i4.0
0x1df13  ldc.i4.1
0x1df14  stelem.i4
0x1df15  call     void Microsoft.ReportingServices.Library.RSService::EnsureItemType(valuetype Microsoft.ReportingServices.Library.ItemType actualType, string path, valuetype Microsoft.ReportingServices.Library.ItemType[] expectedTypes)
0x1df1a  ldloc.s  8
0x1df1c  brfalse  loc_1DFD3
0x1df21  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_CatalogCulture()
0x1df26  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x1df2b  stloc.s  0xC
0x1df2d  ldloc.s  0xC
0x1df2f  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x1df34  dup
0x1df35  ldstr    aPolicies// "Policies"
0x1df3a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1df3f  dup
0x1df40  ldstr    aPolicy// "Policy"
0x1df45  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1df4a  dup
0x1df4b  ldstr    aGroupusername// "GroupUserName"
0x1df50  ldarg.0
0x1df51  call     instance string Microsoft.ReportingServices.Library.RSService::get_UserName()
0x1df56  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1df5b  dup
0x1df5c  ldstr    aRoles// "Roles"
0x1df61  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1df66  dup
0x1df67  ldstr    aRole// "Role"
0x1df6c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1df71  dup
0x1df72  ldstr    aName// "Name"
0x1df77  ldarg.0
0x1df78  call     instance string Microsoft.ReportingServices.Library.RSService::get_MyReportsRole()
0x1df7d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x1df82  dup
0x1df83  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1df88  dup
0x1df89  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1df8e  dup
0x1df8f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1df94  dup
0x1df95  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1df9a  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1df9f  ldarg.0
0x1dfa0  call     instance class Microsoft.ReportingServices.Library.Security Microsoft.ReportingServices.Library.RSService::get_SecMgr()
0x1dfa5  ldloc.2
0x1dfa6  ldc.i4.1
0x1dfa7  ldloc.s  0xC
0x1dfa9  callvirt instance string [mscorlib]System.Object::ToString()
0x1dfae  callvirt instance void Microsoft.ReportingServices.Library.Security::SetCatalogItemPolicies(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath catalogItemPath, valuetype Microsoft.ReportingServices.Library.ItemType catItemType, string xmlPolicy)
0x1dfb3  ldarg.0
0x1dfb4  call     instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.RSService::get_Tracer()
0x1dfb9  ldc.i4.3
0x1dfba  ldstr    aEnsuremyreport_2// "EnsureMyReportsExists: created My Repor"...
0x1dfbf  ldc.i4.1
0x1dfc0  newarr   [mscorlib]System.Object
0x1dfc5  dup
0x1dfc6  ldc.i4.0
0x1dfc7  ldloc.2
0x1dfc8  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x1dfcd  stelem.ref
0x1dfce  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1dfd3  ret
```
