# Microsoft.SharePoint.Administration.SPWebApplication::CreateDefaultInstance_0

- ea: `0x3227f0`
- end: `0x32349c`
- name: `Microsoft.SharePoint.Administration.SPWebApplication::CreateDefaultInstance_0`
- size: `3244`
- prototype: ``
- caller_count: `2`
- callee_count: `85`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x322730`
- `0x32b500`

## callees

- `0x189150`
- `0x1b7e00`
- `0x1c8480`
- `0x1c8530`
- `0x1c8540`
- `0x1c8550`
- `0x1c8640`
- `0x1c8850`
- `0x1c89b0`
- `0x1c89e0`
- `0x1c8a20`
- `0x1c8e40`
- `0x1c9d50`
- `0x1f9e20`
- `0x2229e0`
- `0x223b70`
- `0x223b90`
- `0x223bd0`
- `0x224400`
- `0x227020`
- `0x2270e0`
- `0x227320`
- `0x228390`
- `0x232050`
- `0x232440`
- `0x237b40`
- `0x2474e0`
- `0x28bf40`
- `0x28bf60`
- `0x28d2a0`
- `0x29d110`
- `0x29d1e0`
- `0x29d250`
- `0x29d520`
- `0x29ffd0`
- `0x2a01d0`
- `0x2ab770`
- `0x2abaf0`
- `0x2abc30`
- `0x2af7a0`
- `0x2b08f0`
- `0x2c0640`
- `0x2c0980`
- `0x2c0a10`
- `0x2c0bf0`
- `0x2c0c10`
- `0x2dc970`
- `0x2dc9a0`
- `0x2dc9f0`
- `0x305b50`

## string_xrefs

- `0x322861`: `Validating the server comment, {0}.`
- `0x3228a5`: `Validating the iis root directory, {0}.`
- `0x32292f`: `IisRootDirectoryInUse`
- `0x3229c0`: `defaultZoneUri`
- `0x322a23`: `NetworkServiceCannotBeApplicationPoolAccount`
- `0x322c66`: `The application pool named {0} already exists on the local machine.  , was successfully created.`
- `0x3230cb`: `) because it has already been activated.`
- `0x3231f0`: `The web application, {0}, was successfully created.`
- `0x32329e`: `Web Application rollback failed with the following error: {0}`
- `0x3232d3`: `Rolling back the creation of the alternate access mapping, {0}.`
- `0x323313`: `Alternate access mapping rollback failed with the following error: {0}`
- `0x323384`: `Application Pool rollback failed with the following error: {0}`
- `0x323424`: `Content Database rollback failed with the following error.  This may be expected if the database was an existing, clean database. {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3227f0  ldstr    aWebApplication_3// "Web Application Creation: "
0x3227f5  ldarg.s  4
0x3227f7  call     string [mscorlib]System.String::Concat(string, string)
0x3227fc  ldc.i4.s 0x14
0x3227fe  ldc.i4.3
0x3227ff  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x322804  stloc.s  0x2E
0x322806  ldloc.s  0x2E
0x322808  ldc.i4.0
0x322809  ldc.i4   0x7530
0x32280e  newobj   instance void Microsoft.SharePoint.Utilities.SPExecutionTimeCounter::.ctor(unsigned int32 maxValue)
0x322813  stelem.ref
0x322814  ldloc.s  0x2E
0x322816  ldc.i4.1
0x322817  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x32281c  stelem.ref
0x32281d  ldloc.s  0x2E
0x32281f  ldc.i4.2
0x322820  ldc.i4.3
0x322821  newobj   instance void Microsoft.SharePoint.Utilities.SPRequestUsageCounter::.ctor(int32 maxValue)
0x322826  stelem.ref
0x322827  ldloc.s  0x2E
0x322829  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x32282e  stloc.0
0x32282f  ldc.i4   0x39317166
0x322834  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x322839  ldc.i4.s 0x14
0x32283b  ldstr    aCreatingTheWeb// "Creating the WebApplication, {0}."
0x322840  ldc.i4.1
0x322841  newarr   [mscorlib]System.Object
0x322846  stloc.s  0x2F
0x322848  ldloc.s  0x2F
0x32284a  ldc.i4.0
0x32284b  ldarg.s  4
0x32284d  stelem.ref
0x32284e  ldloc.s  0x2F
0x322850  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x322855  ldc.i4   0x39317167
0x32285a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x32285f  ldc.i4.s 0x64
0x322861  ldstr    aValidatingTheS_0// "Validating the server comment, {0}."
0x322866  ldc.i4.1
0x322867  newarr   [mscorlib]System.Object
0x32286c  stloc.s  0x30
0x32286e  ldloc.s  0x30
0x322870  ldc.i4.0
0x322871  ldarg.s  4
0x322873  stelem.ref
0x322874  ldloc.s  0x30
0x322876  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x32287b  ldarg.s  4
0x32287d  ldsfld   char[] Microsoft.SharePoint.Administration.SPIisWebSite::s_IllegalServerCommentCharacters
0x322882  call     void Microsoft.SharePoint.Utilities.SPUtilityInternal::ValidateString(string stringToValidate, char[] illegalCharacters)
0x322887  ldarg.s  6
0x322889  brtrue.s loc_322892
0x32288b  ldsfld   string [mscorlib]System.String::Empty
0x322890  starg.s  6
0x322892  ldarg.s  9
0x322894  brfalse  loc_3229A1
0x322899  ldc.i4   0x39317168
0x32289e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3228a3  ldc.i4.s 0x64
0x3228a5  ldstr    aValidatingTheI// "Validating the iis root directory, {0}."
0x3228aa  ldc.i4.1
0x3228ab  newarr   [mscorlib]System.Object
0x3228b0  stloc.s  0x31
0x3228b2  ldloc.s  0x31
0x3228b4  ldc.i4.0
0x3228b5  ldarg.s  9
0x3228b7  stelem.ref
0x3228b8  ldloc.s  0x31
0x3228ba  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x3228bf  ldarg.0
0x3228c0  callvirt instance class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPPersistedObject::get_Farm()
0x3228c5  newobj   instance void Microsoft.SharePoint.Administration.SPWebServiceCollection::.ctor(class Microsoft.SharePoint.Administration.SPFarm farm)
0x3228ca  stloc.1
0x3228cb  ldloc.1
0x3228cc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPWebService>::GetEnumerator()
0x3228d1  stloc.s  0x32
0x3228d3  br       loc_322987
0x3228d8  ldloc.s  0x32
0x3228da  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPWebService>::get_Current()
0x3228df  stloc.2
0x3228e0  ldloc.2
0x3228e1  callvirt instance class Microsoft.SharePoint.Administration.SPWebApplicationCollection Microsoft.SharePoint.Administration.SPWebService::get_WebApplications()
0x3228e6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPWebApplication>::GetEnumerator()
0x3228eb  stloc.s  0x33
0x3228ed  br.s     loc_32296D
0x3228ef  ldloc.s  0x33
0x3228f1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPWebApplication>::get_Current()
0x3228f6  stloc.3
0x3228f7  ldloc.3
0x3228f8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.SharePoint.Administration.SPUrlZone, class Microsoft.SharePoint.Administration.SPIisSettings> Microsoft.SharePoint.Administration.SPWebApplication::get_IisSettings()
0x3228fd  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.SharePoint.Administration.SPUrlZone, class Microsoft.SharePoint.Administration.SPIisSettings>::get_Values()
0x322902  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype Microsoft.SharePoint.Administration.SPUrlZone, class Microsoft.SharePoint.Administration.SPIisSettings>::GetEnumerator()
0x322907  stloc.s  0x34
0x322909  br.s     loc_322954
0x32290b  ldloca.s 0x34
0x32290d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype Microsoft.SharePoint.Administration.SPUrlZone, class Microsoft.SharePoint.Administration.SPIisSettings>::get_Current()
0x322912  stloc.s  4
0x322914  ldloc.s  4
0x322916  callvirt instance class [mscorlib]System.IO.DirectoryInfo Microsoft.SharePoint.Administration.SPIisSettings::get_Path()
0x32291b  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x322920  ldarg.s  9
0x322922  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x322927  ldc.i4.1
0x322928  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x32292d  brfalse.s loc_322954
0x32292f  ldstr    aIisrootdirecto// "IisRootDirectoryInUse"
0x322934  ldc.i4.1
0x322935  newarr   [mscorlib]System.Object
0x32293a  stloc.s  0x35
0x32293c  ldloc.s  0x35
0x32293e  ldc.i4.0
0x32293f  ldarg.s  9
0x322941  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x322946  stelem.ref
0x322947  ldloc.s  0x35
0x322949  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x32294e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x322953  throw
0x322954  ldloca.s 0x34
0x322956  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype Microsoft.SharePoint.Administration.SPUrlZone, class Microsoft.SharePoint.Administration.SPIisSettings>::MoveNext()
0x32295b  brtrue.s loc_32290B
0x32295d  leave.s  loc_32296D
0x32295f  ldloca.s 0x34
0x322961  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype Microsoft.SharePoint.Administration.SPUrlZone, class Microsoft.SharePoint.Administration.SPIisSettings>
0x322967  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32296c  endfinally
0x32296d  ldloc.s  0x33
0x32296f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x322974  brtrue   loc_3228EF
0x322979  leave.s  loc_322987
0x32297b  ldloc.s  0x33
0x32297d  brfalse.s loc_322986
0x32297f  ldloc.s  0x33
0x322981  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x322986  endfinally
0x322987  ldloc.s  0x32
0x322989  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32298e  brtrue   loc_3228D8
0x322993  leave.s  loc_3229A1
0x322995  ldloc.s  0x32
0x322997  brfalse.s loc_3229A0
0x322999  ldloc.s  0x32
0x32299b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3229a0  endfinally
0x3229a1  ldarg.s  0xB
0x3229a3  brtrue.s loc_3229B6
0x3229a5  call     class Microsoft.SharePoint.Diagnostics.ULSEventTemplates.ULSEvent_s Microsoft.SharePoint.Diagnostics.ULSEvent::get_eventWSSAppPoolUsingKerberos()
0x3229aa  ldarg.s  0xA
0x3229ac  callvirt instance string [mscorlib]System.Object::ToString()
0x3229b1  callvirt instance void Microsoft.SharePoint.Diagnostics.ULSEventTemplates.ULSEvent_s::Send(string string0)
0x3229b6  ldarg.s  0xA
0x3229b8  ldnull
0x3229b9  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x3229be  brfalse.s loc_3229CB
0x3229c0  ldstr    aDefaultzoneuri// "defaultZoneUri"
0x3229c5  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3229ca  throw
0x3229cb  ldarg.2
0x3229cc  brtrue.s loc_3229D2
0x3229ce  ldarg.s  4
0x3229d0  starg.s  2
0x3229d2  ldc.i4   0x39317169
0x3229d7  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x3229dc  ldc.i4.s 0x64
0x3229de  ldstr    aValidatingTheA// "Validating the application pool, {0}."
0x3229e3  ldc.i4.1
0x3229e4  newarr   [mscorlib]System.Object
0x3229e9  stloc.s  0x36
0x3229eb  ldloc.s  0x36
0x3229ed  ldc.i4.0
0x3229ee  ldarg.2
0x3229ef  stelem.ref
0x3229f0  ldloc.s  0x36
0x3229f2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x3229f7  ldarg.3
0x3229f8  callvirt instance valuetype Microsoft.SharePoint.Administration.IdentityType Microsoft.SharePoint.Administration.SPProcessAccount::get_IdentityType()
0x3229fd  stloc.s  5
0x3229ff  ldloc.s  5
0x322a01  brfalse.s loc_322A08
0x322a03  ldloc.s  5
0x322a05  ldc.i4.1
0x322a06  bne.un.s loc_322A1E
0x322a08  ldstr    aLocalsystemcan// "LocalSystemCannotBeApplicationPoolAccou"...
0x322a0d  ldc.i4.0
0x322a0e  newarr   [mscorlib]System.Object
0x322a13  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x322a18  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x322a1d  throw
0x322a1e  ldloc.s  5
0x322a20  ldc.i4.2
0x322a21  bne.un.s loc_322A39
0x322a23  ldstr    aNetworkservice_0// "NetworkServiceCannotBeApplicationPoolAc"...
0x322a28  ldc.i4.0
0x322a29  newarr   [mscorlib]System.Object
0x322a2e  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x322a33  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x322a38  throw
0x322a39  ldarg.3
0x322a3a  callvirt instance string Microsoft.SharePoint.Administration.SPProcessAccount::LookupName()
0x322a3f  stloc.s  6
0x322a41  ldloc.s  5
0x322a43  ldc.i4.3
0x322a44  bne.un.s loc_322A55
0x322a46  ldloc.s  6
0x322a48  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x322a4d  brtrue.s loc_322A55
0x322a4f  ldarg.3
0x322a50  callvirt instance void Microsoft.SharePoint.Administration.SPProcessAccount::ValidateLogonAccount()
0x322a55  ldarg.2
0x322a56  ldsfld   char[] Microsoft.SharePoint.Administration.SPIisApplicationPool::s_IllegalApplicationPoolNameCharacters
0x322a5b  call     void Microsoft.SharePoint.Utilities.SPUtilityInternal::ValidateString(string stringToValidate, char[] illegalCharacters)
0x322a60  ldarg.2
0x322a61  newobj   instance void Microsoft.SharePoint.Administration.SPIisApplicationPool::.ctor(string name)
0x322a66  stloc.s  7
0x322a68  ldloc.s  7
0x322a6a  callvirt instance string Microsoft.SharePoint.Administration.SPIisApplicationPool::get_ManagedRuntimeVersion()
0x322a6f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x322a74  brtrue.s loc_322AA8
0x322a76  ldloc.s  7
0x322a78  callvirt instance string Microsoft.SharePoint.Administration.SPIisApplicationPool::get_ManagedRuntimeVersion()
0x322a7d  ldstr    aV11// "v1.1"
0x322a82  call     bool Microsoft.SharePoint.Utilities.SPUtility::StsCompareStrings(string str1, string str2)
0x322a87  brfalse.s loc_322AA8
0x322a89  ldstr    aInvalidapplica_0// "InvalidApplicatonPoolClr"
0x322a8e  ldc.i4.1
0x322a8f  newarr   [mscorlib]System.Object
0x322a94  stloc.s  0x37
0x322a96  ldloc.s  0x37
0x322a98  ldc.i4.0
0x322a99  ldarg.2
0x322a9a  stelem.ref
0x322a9b  ldloc.s  0x37
0x322a9d  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x322aa2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x322aa7  throw
0x322aa8  leave.s  loc_322AB6
0x322aaa  ldloc.s  7
0x322aac  brfalse.s loc_322AB5
0x322aae  ldloc.s  7
0x322ab0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x322ab5  endfinally
0x322ab6  ldarg.s  0xC
0x322ab8  brfalse  loc_322BF3
0x322abd  ldc.i4   0x3931716A
0x322ac2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x322ac7  ldc.i4.s 0x64
0x322ac9  ldstr    aValidatingData// "Validating database parameters."
0x322ace  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x322ad3  ldarg.s  0xD
0x322ad5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x322ada  brfalse.s loc_322AE9
0x322adc  ldarg.0
0x322add  callvirt instance class Microsoft.SharePoint.Administration.SPDatabaseServiceInstance Microsoft.SharePoint.Administration.SPWebService::get_DefaultDatabaseInstance()
0x322ae2  callvirt instance string Microsoft.SharePoint.Administration.SPDatabaseServiceInstance::get_NormalizedDataSource()
0x322ae7  starg.s  0xD
0x322ae9  ldarg.s  0xF
0x322aeb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x322af0  brfalse.s loc_322AF5
0x322af2  ldnull
0x322af3  starg.s  0xF
0x322af5  ldarg.s  0x10
0x322af7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x322afc  brfalse.s loc_322B01
0x322afe  ldnull
0x322aff  starg.s  0x10
0x322b01  newobj   instance void [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::.ctor()
0x322b06  stloc.s  8
0x322b08  ldloc.s  8
0x322b0a  ldarg.s  0xD
0x322b0c  callvirt instance void [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::set_DataSource(string)
0x322b11  ldarg.s  0xF
0x322b13  brfalse.s loc_322B31
0x322b15  ldloc.s  8
0x322b17  ldc.i4.0
0x322b18  callvirt instance void [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::set_IntegratedSecurity(bool)
0x322b1d  ldloc.s  8
0x322b1f  ldarg.s  0xF
0x322b21  callvirt instance void [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::set_UserID(string)
0x322b26  ldloc.s  8
0x322b28  ldarg.s  0x10
0x322b2a  callvirt instance void [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::set_Password(string)
0x322b2f  br.s     loc_322B39
0x322b31  ldloc.s  8
0x322b33  ldc.i4.1
0x322b34  callvirt instance void [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::set_IntegratedSecurity(bool)
0x322b39  ldarg.s  0xE
0x322b3b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x322b40  brfalse.s loc_322B63
0x322b42  ldloc.s  8
0x322b44  ldstr    aWssContent// "WSS_Content"
0x322b49  callvirt instance void [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::set_InitialCatalog(string)
0x322b4e  ldloca.s 8
0x322b50  call     void Microsoft.SharePoint.Administration.SPDatabase::GenerateRandomName(class [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder& suggestedConnectionString)
0x322b55  ldloc.s  8
0x322b57  callvirt instance string [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder::get_InitialCatalog()
0x322b5c  starg.s  0xE
0x322b5e  br       loc_322BF3
  ... truncated ...
```
