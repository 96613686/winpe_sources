# Microsoft.ReportingServices.Library.SetSystemPropertiesAction::OnSetEnableMyReports

- ea: `0x21d00`
- end: `0x21f01`
- name: `Microsoft.ReportingServices.Library.SetSystemPropertiesAction::OnSetEnableMyReports`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x21a30`

## callees

- `0xcd40`
- `0xd120`
- `0xd130`
- `0xd150`
- `0xf590`
- `0xf5a0`
- `0x1e0d0`
- `0x1e210`
- `0x1e2e0`
- `0x1e570`
- `0x21d00`
- `0x48db0`
- `0x49b10`

## string_xrefs

- `0x21e88`: `Couldn't create Users Folders but it doesn't exist.`
- `0x21eca`: `OnSetEnableMyReports: AllUsersFolder already exists on enabling of My Reports`

## pseudocode

```c

```

## disassembly

```asm
0x21d00  ldarg.1
0x21d01  brtrue.s loc_21D06
0x21d03  ldc.i4.0
0x21d04  br.s     loc_21D0C
0x21d06  ldarg.1
0x21d07  call     bool [mscorlib]System.Boolean::Parse(string)
0x21d0c  stloc.0
0x21d0d  ldarg.2
0x21d0e  call     bool [mscorlib]System.Boolean::Parse(string)
0x21d13  stloc.1
0x21d14  leave.s  loc_21D22
0x21d16  pop
0x21d17  ldstr    aEnablemyreport// "EnableMyReports"
0x21d1c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ElementTypeMismatchException::.ctor(string)
0x21d21  throw
0x21d22  ldloc.0
0x21d23  ldloc.1
0x21d24  bne.un.s loc_21D52
0x21d26  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x21d2b  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x21d30  brfalse.s loc_21D51
0x21d32  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x21d37  ldc.i4.4
0x21d38  ldstr    aEnablemyreport_0// "EnableMyReports value unchanged ({0})"
0x21d3d  ldc.i4.1
0x21d3e  newarr   [mscorlib]System.Object
0x21d43  dup
0x21d44  ldc.i4.0
0x21d45  ldloc.0
0x21d46  box      [mscorlib]System.Boolean
0x21d4b  stelem.ref
0x21d4c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x21d51  ret
0x21d52  ldloc.1
0x21d53  brfalse  loc_21EE4
0x21d58  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x21d5d  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x21d62  brfalse.s loc_21D74
0x21d64  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x21d69  ldc.i4.3
0x21d6a  ldstr    aOnsetenablemyr// "OnSetEnableMyReports: Enabling My Repor"...
0x21d6f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x21d74  ldarg.0
0x21d75  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSystemPropertiesActionParameters>::get_Service()
0x21d7a  callvirt instance class Microsoft.ReportingServices.Library.Security Microsoft.ReportingServices.Library.RSService::get_SecMgr()
0x21d7f  ldarg.0
0x21d80  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSystemPropertiesActionParameters>::get_Service()
0x21d85  callvirt instance string Microsoft.ReportingServices.Library.RSService::get_MyReportsRole()
0x21d8a  callvirt instance bool Microsoft.ReportingServices.Library.Security::RoleExists(string roleName)
0x21d8f  brtrue.s loc_21DA2
0x21d91  ldarg.0
0x21d92  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSystemPropertiesActionParameters>::get_Service()
0x21d97  callvirt instance string Microsoft.ReportingServices.Library.RSService::get_MyReportsRole()
0x21d9c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RoleNotFoundException::.ctor(string)
0x21da1  throw
0x21da2  ldarg.0
0x21da3  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSystemPropertiesActionParameters>::get_Service()
0x21da8  callvirt instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x21dad  ldsfld   string Microsoft.ReportingServices.Library.Global::VirtualMyReportsPath
0x21db2  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::.ctor(string)
0x21db7  callvirt instance bool Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath objectName)
0x21dbc  brfalse.s loc_21DC9
0x21dbe  ldsfld   string Microsoft.ReportingServices.Library.Global::VirtualMyReportsPath
0x21dc3  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemAlreadyExistsException::.ctor(string)
0x21dc8  throw
0x21dc9  ldsfld   class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::Empty
0x21dce  stloc.s  5
0x21dd0  ldarg.0
0x21dd1  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSystemPropertiesActionParameters>::get_Service()
0x21dd6  callvirt instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x21ddb  ldloc.s  5
0x21ddd  ldloca.s 2
0x21ddf  ldloca.s 3
0x21de1  ldloca.s 4
0x21de3  callvirt instance bool Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath objectName, [out] valuetype Microsoft.ReportingServices.Library.ItemType& type, [out] valuetype [mscorlib]System.Guid& id, [out] unsigned int8[]& secDesc)
0x21de8  pop
0x21de9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x21dee  pop
0x21def  ldarg.0
0x21df0  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSystemPropertiesActionParameters>::get_Service()
0x21df5  callvirt instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x21dfa  ldsfld   string Microsoft.ReportingServices.Library.Global::AllUsersFolderPath
0x21dff  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::.ctor(string)
0x21e04  ldloca.s 6
0x21e06  callvirt instance bool Microsoft.ReportingServices.Library.IDBInterface::ObjectExists(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath objectName, [out] valuetype Microsoft.ReportingServices.Library.ItemType& type)
0x21e0b  brtrue   loc_21EB8
0x21e10  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x21e15  stloc.s  7
0x21e17  ldarg.0
0x21e18  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSystemPropertiesActionParameters>::get_Service()
0x21e1d  callvirt instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x21e22  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x21e27  ldsfld   string Microsoft.ReportingServices.Library.Global::AllUsersFolderName
0x21e2c  ldsfld   string Microsoft.ReportingServices.Library.Global::AllUsersFolderPath
0x21e31  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath::.ctor(string)
0x21e36  ldloc.s  5
0x21e38  ldloc.3
0x21e39  ldc.i4.1
0x21e3a  ldnull
0x21e3b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x21e40  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x21e45  ldnull
0x21e46  ldnull
0x21e47  ldnull
0x21e48  ldarg.0
0x21e49  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSystemPropertiesActionParameters>::get_Service()
0x21e4e  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x21e53  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x21e58  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::GetSystemSid(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType authType)
0x21e5d  ldarg.0
0x21e5e  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSystemPropertiesActionParameters>::get_Service()
0x21e63  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x21e68  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x21e6d  call     string Microsoft.ReportingServices.Library.Global::GetSystemUserName(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType authType)
0x21e72  ldloc.s  7
0x21e74  ldloc.s  7
0x21e76  ldnull
0x21e77  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.IDBInterface::CreateObject(valuetype [mscorlib]System.Guid id, string shortName, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath fullPath, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath parentPath, valuetype [mscorlib]System.Guid parentId, valuetype Microsoft.ReportingServices.Library.ItemType objectType, unsigned int8[] objectContent, valuetype [mscorlib]System.Guid intermediateSnapshotID, valuetype [mscorlib]System.Guid link, string linkPath, class Microsoft.ReportingServices.Library.ItemProperties objectProperties, string parameters, unsigned int8[] createdBySid, string createdBy, valuetype [mscorlib]System.DateTime creationDate, valuetype [mscorlib]System.DateTime modificationDate, string mimeType)
0x21e7c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x21e81  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21e86  brfalse.s loc_21E93
0x21e88  ldstr    aCouldnTCreateU// "Couldn't create Users Folders but it do"...
0x21e8d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x21e92  throw
0x21e93  ldstr    aPoliciesPolici// "<Policies></Policies>"
0x21e98  stloc.s  8
0x21e9a  ldarg.0
0x21e9b  call     instance class Microsoft.ReportingServices.Library.RSService class Microsoft.ReportingServices.Library.RSSoapAction`1<class Microsoft.ReportingServices.Library.SetSystemPropertiesActionParameters>::get_Service()
0x21ea0  callvirt instance class Microsoft.ReportingServices.Library.Security Microsoft.ReportingServices.Library.RSService::get_SecMgr()
0x21ea5  ldsfld   string Microsoft.ReportingServices.Library.Global::AllUsersFolderPath
0x21eaa  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::.ctor(string)
0x21eaf  ldc.i4.1
0x21eb0  ldloc.s  8
0x21eb2  callvirt instance void Microsoft.ReportingServices.Library.Security::SetCatalogItemPolicies(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath catalogItemPath, valuetype Microsoft.ReportingServices.Library.ItemType catItemType, string xmlPolicy)
0x21eb7  ret
0x21eb8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x21ebd  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x21ec2  brfalse.s loc_21ED4
0x21ec4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x21ec9  ldc.i4.2
0x21eca  ldstr    aOnsetenablemyr_0// "OnSetEnableMyReports: AllUsersFolder al"...
0x21ecf  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x21ed4  ldloc.s  6
0x21ed6  ldc.i4.1
0x21ed7  beq.s    loc_21F00
0x21ed9  ldsfld   string Microsoft.ReportingServices.Library.Global::AllUsersFolderPath
0x21ede  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.WrongItemTypeException::.ctor(string)
0x21ee3  throw
0x21ee4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x21ee9  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x21eee  brfalse.s loc_21F00
0x21ef0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x21ef5  ldc.i4.3
0x21ef6  ldstr    aOnsetenablemyr_1// "OnSetEnableMyReports: Disabling My Repo"...
0x21efb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x21f00  ret
```
