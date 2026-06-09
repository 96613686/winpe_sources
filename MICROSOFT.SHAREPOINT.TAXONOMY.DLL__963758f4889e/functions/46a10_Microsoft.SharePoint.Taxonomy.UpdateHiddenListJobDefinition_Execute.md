# Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::Execute

- ea: `0x46a10`
- end: `0x46b7d`
- name: `Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::Execute`
- size: `365`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x46a10`
- `0x46b90`
- `0x47a50`
- `0x66710`

## string_xrefs

- `0x46a10`: `UpdateHiddenListJobDefinition.Execute`
- `0x46ac8`: `UpdateHiddenList timer job executing`
- `0x46b4e`: `Exception occured while hidden list being updated: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x46a10  ldstr    aUpdatehiddenli_1// "UpdateHiddenListJobDefinition.Execute"
0x46a15  ldc.i4   0x756309
0x46a1a  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x46a1f  ldc.i4   0x75630A
0x46a24  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x46a29  ldc.i4   0x75630B
0x46a2e  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x46a33  ldc.i4.0
0x46a34  ldnull
0x46a35  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor::.ctor(string, unsigned int32, unsigned int32, unsigned int32, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPLogType, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x46a3a  stloc.0
0x46a3b  ldarg.0
0x46a3c  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x46a41  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPSiteCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication::get_Sites()
0x46a46  ldc.i4.0
0x46a47  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPSiteCollection::get_Item(int32)
0x46a4c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::GetContext(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite)
0x46a51  stloc.1
0x46a52  ldloc.1
0x46a53  call     void Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::EnsureHubTimerJob(class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext serviceContext)
0x46a58  leave.s  loc_46A8C
0x46a5a  stloc.2
0x46a5b  ldloc.0
0x46a5c  ldc.i4   0x75630C
0x46a61  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x46a66  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x46a6b  ldstr    aExceptionOccur_2// "Exception occured while updating the me"...
0x46a70  ldc.i4.1
0x46a71  newarr   [mscorlib]System.Object
0x46a76  stloc.s  7
0x46a78  ldloc.s  7
0x46a7a  ldc.i4.0
0x46a7b  ldloc.2
0x46a7c  stelem.ref
0x46a7d  ldloc.s  7
0x46a7f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x46a84  ldnull
0x46a85  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x46a8a  leave.s  loc_46A8C
0x46a8c  ldarg.0
0x46a8d  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x46a92  call     void Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::EnsureHiddenListFullSyncTimerJob(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x46a97  ldarg.0
0x46a98  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x46a9d  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPObjectStatus [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Status()
0x46aa2  ldc.i4.2
0x46aa3  beq.s    loc_46AB7
0x46aa5  ldarg.0
0x46aa6  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x46aab  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPSiteCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication::get_Sites()
0x46ab0  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseCollection::get_Count()
0x46ab5  brtrue.s loc_46ABC
0x46ab7  leave    loc_46B7C
0x46abc  ldc.i4   0x32636B6C
0x46ac1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x46ac6  ldc.i4.s 0x64
0x46ac8  ldstr    aUpdatehiddenli_2// "UpdateHiddenList timer job executing"
0x46acd  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x46ad2  ldarg.0
0x46ad3  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x46ad8  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPSiteCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication::get_Sites()
0x46add  ldc.i4.0
0x46ade  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPSiteCollection::get_Item(int32)
0x46ae3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::GetContext(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite)
0x46ae8  stloc.3
0x46ae9  ldloc.3
0x46aea  ldtoken  Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy
0x46aef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46af4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy> [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::GetProxies(class [mscorlib]System.Type)
0x46af9  stloc.s  4
0x46afb  ldloc.s  4
0x46afd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy>::GetEnumerator()
0x46b02  stloc.s  8
0x46b04  br.s     loc_46B1C
0x46b06  ldloc.s  8
0x46b08  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy>::get_Current()
0x46b0d  castclass Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy
0x46b12  stloc.s  5
0x46b14  ldarg.0
0x46b15  ldloc.s  5
0x46b17  call     instance void Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::ProcessProxy(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy)
0x46b1c  ldloc.s  8
0x46b1e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x46b23  brtrue.s loc_46B06
0x46b25  leave.s  loc_46B33
0x46b27  ldloc.s  8
0x46b29  brfalse.s loc_46B32
0x46b2b  ldloc.s  8
0x46b2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x46b32  endfinally
0x46b33  ldloc.0
0x46b34  ldnull
0x46b35  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::Success(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x46b3a  leave.s  loc_46B70
0x46b3c  stloc.s  6
0x46b3e  ldloc.0
0x46b3f  ldc.i4   0x75630D
0x46b44  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x46b49  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x46b4e  ldstr    aExceptionOccur_3// "Exception occured while hidden list bei"...
0x46b53  ldc.i4.1
0x46b54  newarr   [mscorlib]System.Object
0x46b59  stloc.s  9
0x46b5b  ldloc.s  9
0x46b5d  ldc.i4.0
0x46b5e  ldloc.s  6
0x46b60  stelem.ref
0x46b61  ldloc.s  9
0x46b63  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x46b68  ldnull
0x46b69  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x46b6e  leave.s  loc_46B70
0x46b70  leave.s  loc_46B7C
0x46b72  ldloc.0
0x46b73  brfalse.s loc_46B7B
0x46b75  ldloc.0
0x46b76  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x46b7b  endfinally
0x46b7c  ret
```
