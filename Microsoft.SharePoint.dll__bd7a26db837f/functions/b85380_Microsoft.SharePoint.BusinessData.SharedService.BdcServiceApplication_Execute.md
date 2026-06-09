# Microsoft.SharePoint.BusinessData.SharedService.BdcServiceApplication::Execute

- ea: `0xb85380`
- end: `0xb8592a`
- name: `Microsoft.SharePoint.BusinessData.SharedService.BdcServiceApplication::Execute`
- size: `1450`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1c8480`
- `0x232000`
- `0x232440`
- `0x93dab0`
- `0x953df0`
- `0x9582b0`
- `0xb06000`
- `0xb060d0`
- `0xb19f70`
- `0xb1a0a0`
- `0xb2e030`
- `0xb2e0c0`
- `0xb69610`
- `0xb852d0`
- `0xb85380`

## string_xrefs

- `0xb858a3`: `ApplicationRegistry_BdcServiceApplication_UnknownException`
- `0xb857f4`: `ApplicationRegistry_BdcServiceApplication_SqlException`
- `0xb8539a`: `' in BdcServiceApplication.`
- `0xb8540a`: `' in BdcServiceApplication.`
- `0xb85404`: `Completed Bdc '`
- `0xb85451`: `' BdcServiceApplication logging server side `
- `0xb854c8`: `' BdcServiceApplication logging server side `
- `0xb8553f`: `' BdcServiceApplication logging server side `
- `0xb855b7`: `' BdcServiceApplication logging server side `
- `0xb85621`: `' BdcServiceApplication logging server side `
- `0xb8568b`: `' BdcServiceApplication logging server side `
- `0xb85713`: `' BdcServiceApplication logging server side `
- `0xb8577d`: `' BdcServiceApplication logging server side `
- `0xb85863`: `' BdcServiceApplication logging server side `
- `0xb85469`: ` before marshalling and rethrowing on client side: `
- `0xb854e0`: ` before marshalling and rethrowing on client side: `
- `0xb85557`: ` before marshalling and rethrowing on client side: `
- `0xb855d0`: ` before marshalling and rethrowing on client side: `
- `0xb8563a`: ` before marshalling and rethrowing on client side: `
- `0xb856a4`: ` before marshalling and rethrowing on client side: `
- `0xb8572c`: ` before marshalling and rethrowing on client side: `
- `0xb85796`: ` before marshalling and rethrowing on client side: `
- `0xb8587c`: ` before marshalling and rethrowing on client side: `

## pseudocode

```c

```

## disassembly

```asm
0xb85380  ldnull
0xb85381  stloc.0
0xb85382  ldarg.0
0xb85383  call     instance void Microsoft.SharePoint.BusinessData.SharedService.BdcServiceApplication::RetrieveHeadersInfo()
0xb85388  ldc.i4   0x6630716B
0xb8538d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb85392  ldc.i4.s 0x64
0xb85394  ldstr    aEnteringBdc// "Entering Bdc '"
0xb85399  ldarg.1
0xb8539a  ldstr    aInBdcserviceap// "' in BdcServiceApplication."
0xb8539f  call     string [mscorlib]System.String::Concat(string, string, string)
0xb853a4  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0xb853a9  ldarg.2
0xb853aa  ldc.i4.m1
0xb853ab  bne.un.s loc_B853CF
0xb853ad  ldarg.1
0xb853ae  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0xb853b3  stloc.s  0xF
0xb853b5  ldarg.3
0xb853b6  callvirt instance var<u1> class ExecuteDelegate`1<mvar<u1>>::Invoke()
0xb853bb  box      mvar<u1>
0xb853c0  stloc.0
0xb853c1  leave.s  loc_B853F8
0xb853c3  ldloc.s  0xF
0xb853c5  brfalse.s loc_B853CE
0xb853c7  ldloc.s  0xF
0xb853c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb853ce  endfinally
0xb853cf  ldarg.1
0xb853d0  ldarg.2
0xb853d1  ldc.i4.0
0xb853d2  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0xb853d7  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, unsigned int32 maximumExecutionTime, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0xb853dc  stloc.s  0x10
0xb853de  ldarg.3
0xb853df  callvirt instance var<u1> class ExecuteDelegate`1<mvar<u1>>::Invoke()
0xb853e4  box      mvar<u1>
0xb853e9  stloc.0
0xb853ea  leave.s  loc_B853F8
0xb853ec  ldloc.s  0x10
0xb853ee  brfalse.s loc_B853F7
0xb853f0  ldloc.s  0x10
0xb853f2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb853f7  endfinally
0xb853f8  ldc.i4   0x6630716C
0xb853fd  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb85402  ldc.i4.s 0x64
0xb85404  ldstr    aCompletedBdc// "Completed Bdc '"
0xb85409  ldarg.1
0xb8540a  ldstr    aInBdcserviceap// "' in BdcServiceApplication."
0xb8540f  call     string [mscorlib]System.String::Concat(string, string, string)
0xb85414  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0xb85419  ldloc.0
0xb8541a  unbox.any mvar<u1>
0xb8541f  stloc.s  0xE
0xb85421  leave    loc_B85927
0xb85426  stloc.1
0xb85427  ldc.i4   0x39663463
0xb8542c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb85431  ldc.i4.s 0xA
0xb85433  ldc.i4.6
0xb85434  newarr   [mscorlib]System.String
0xb85439  stloc.s  0x11
0xb8543b  ldloc.s  0x11
0xb8543d  ldc.i4.0
0xb8543e  ldstr    asc_C6AA32// "'"
0xb85443  stelem.ref
0xb85444  ldloc.s  0x11
0xb85446  ldc.i4.1
0xb85447  ldarg.0
0xb85448  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xb8544d  stelem.ref
0xb8544e  ldloc.s  0x11
0xb85450  ldc.i4.2
0xb85451  ldstr    aBdcserviceappl_2// "' BdcServiceApplication logging server "...
0xb85456  stelem.ref
0xb85457  ldloc.s  0x11
0xb85459  ldc.i4.3
0xb8545a  ldloc.1
0xb8545b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xb85460  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xb85465  stelem.ref
0xb85466  ldloc.s  0x11
0xb85468  ldc.i4.4
0xb85469  ldstr    aBeforeMarshall// " before marshalling and rethrowing on c"...
0xb8546e  stelem.ref
0xb8546f  ldloc.s  0x11
0xb85471  ldc.i4.5
0xb85472  ldloc.1
0xb85473  callvirt instance string [mscorlib]System.Object::ToString()
0xb85478  stelem.ref
0xb85479  ldloc.s  0x11
0xb8547b  call     string [mscorlib]System.String::Concat(string[])
0xb85480  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0xb85485  ldloc.1
0xb85486  ldloc.1
0xb85487  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0xb8548c  callvirt instance void [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.BdcException::set_ServerStackTrace(string)
0xb85491  ldloc.1
0xb85492  callvirt instance class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.BdcExceptionState [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.BdcException::get_State()
0xb85497  newobj   instance void class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.BusinessData]Microsoft.BusinessData.Infrastructure.BdcExceptionState>::.ctor(var<u1>)
0xb8549c  throw
0xb8549d  stloc.2
0xb8549e  ldc.i4   0x39663464
0xb854a3  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb854a8  ldc.i4.s 0x14
0xb854aa  ldc.i4.6
0xb854ab  newarr   [mscorlib]System.String
0xb854b0  stloc.s  0x12
0xb854b2  ldloc.s  0x12
0xb854b4  ldc.i4.0
0xb854b5  ldstr    asc_C6AA32// "'"
0xb854ba  stelem.ref
0xb854bb  ldloc.s  0x12
0xb854bd  ldc.i4.1
0xb854be  ldarg.0
0xb854bf  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xb854c4  stelem.ref
0xb854c5  ldloc.s  0x12
0xb854c7  ldc.i4.2
0xb854c8  ldstr    aBdcserviceappl_2// "' BdcServiceApplication logging server "...
0xb854cd  stelem.ref
0xb854ce  ldloc.s  0x12
0xb854d0  ldc.i4.3
0xb854d1  ldloc.2
0xb854d2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xb854d7  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xb854dc  stelem.ref
0xb854dd  ldloc.s  0x12
0xb854df  ldc.i4.4
0xb854e0  ldstr    aBeforeMarshall// " before marshalling and rethrowing on c"...
0xb854e5  stelem.ref
0xb854e6  ldloc.s  0x12
0xb854e8  ldc.i4.5
0xb854e9  ldloc.2
0xb854ea  callvirt instance string [mscorlib]System.Object::ToString()
0xb854ef  stelem.ref
0xb854f0  ldloc.s  0x12
0xb854f2  call     string [mscorlib]System.String::Concat(string[])
0xb854f7  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0xb854fc  ldloc.2
0xb854fd  ldloc.2
0xb854fe  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0xb85503  callvirt instance void Microsoft.SharePoint.BusinessData.Administration.MetadataException::set_ServerStackTrace(string value)
0xb85508  ldloc.2
0xb85509  callvirt instance class Microsoft.SharePoint.BusinessData.Administration.MetadataExceptionState Microsoft.SharePoint.BusinessData.Administration.MetadataException::get_State()
0xb8550e  newobj   instance void class [System.ServiceModel]System.ServiceModel.FaultException`1<class Microsoft.SharePoint.BusinessData.Administration.MetadataExceptionState>::.ctor(var<u1>)
0xb85513  throw
0xb85514  stloc.3
0xb85515  ldc.i4   0x39663465
0xb8551a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb8551f  ldc.i4.s 0xA
0xb85521  ldc.i4.6
0xb85522  newarr   [mscorlib]System.String
0xb85527  stloc.s  0x13
0xb85529  ldloc.s  0x13
0xb8552b  ldc.i4.0
0xb8552c  ldstr    asc_C6AA32// "'"
0xb85531  stelem.ref
0xb85532  ldloc.s  0x13
0xb85534  ldc.i4.1
0xb85535  ldarg.0
0xb85536  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xb8553b  stelem.ref
0xb8553c  ldloc.s  0x13
0xb8553e  ldc.i4.2
0xb8553f  ldstr    aBdcserviceappl_2// "' BdcServiceApplication logging server "...
0xb85544  stelem.ref
0xb85545  ldloc.s  0x13
0xb85547  ldc.i4.3
0xb85548  ldloc.3
0xb85549  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xb8554e  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xb85553  stelem.ref
0xb85554  ldloc.s  0x13
0xb85556  ldc.i4.4
0xb85557  ldstr    aBeforeMarshall// " before marshalling and rethrowing on c"...
0xb8555c  stelem.ref
0xb8555d  ldloc.s  0x13
0xb8555f  ldc.i4.5
0xb85560  ldloc.3
0xb85561  callvirt instance string [mscorlib]System.Object::ToString()
0xb85566  stelem.ref
0xb85567  ldloc.s  0x13
0xb85569  call     string [mscorlib]System.String::Concat(string[])
0xb8556e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0xb85573  ldloc.3
0xb85574  ldloc.3
0xb85575  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0xb8557a  callvirt instance void Microsoft.SharePoint.BusinessData.Parser.PackageFormatException::set_ServerStackTrace(string value)
0xb8557f  ldloc.3
0xb85580  callvirt instance class Microsoft.SharePoint.BusinessData.Parser.PackageFormatExceptionState Microsoft.SharePoint.BusinessData.Parser.PackageFormatException::get_State()
0xb85585  newobj   instance void class [System.ServiceModel]System.ServiceModel.FaultException`1<class Microsoft.SharePoint.BusinessData.Parser.PackageFormatExceptionState>::.ctor(var<u1>)
0xb8558a  throw
0xb8558b  stloc.s  4
0xb8558d  ldc.i4   0x39663466
0xb85592  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb85597  ldc.i4.s 0x14
0xb85599  ldc.i4.6
0xb8559a  newarr   [mscorlib]System.String
0xb8559f  stloc.s  0x14
0xb855a1  ldloc.s  0x14
0xb855a3  ldc.i4.0
0xb855a4  ldstr    asc_C6AA32// "'"
0xb855a9  stelem.ref
0xb855aa  ldloc.s  0x14
0xb855ac  ldc.i4.1
0xb855ad  ldarg.0
0xb855ae  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xb855b3  stelem.ref
0xb855b4  ldloc.s  0x14
0xb855b6  ldc.i4.2
0xb855b7  ldstr    aBdcserviceappl_2// "' BdcServiceApplication logging server "...
0xb855bc  stelem.ref
0xb855bd  ldloc.s  0x14
0xb855bf  ldc.i4.3
0xb855c0  ldloc.s  4
0xb855c2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xb855c7  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xb855cc  stelem.ref
0xb855cd  ldloc.s  0x14
0xb855cf  ldc.i4.4
0xb855d0  ldstr    aBeforeMarshall// " before marshalling and rethrowing on c"...
0xb855d5  stelem.ref
0xb855d6  ldloc.s  0x14
0xb855d8  ldc.i4.5
0xb855d9  ldloc.s  4
0xb855db  callvirt instance string [mscorlib]System.Object::ToString()
0xb855e0  stelem.ref
0xb855e1  ldloc.s  0x14
0xb855e3  call     string [mscorlib]System.String::Concat(string[])
0xb855e8  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0xb855ed  ldloc.s  4
0xb855ef  newobj   instance void class [System.ServiceModel]System.ServiceModel.FaultException`1<class [mscorlib]System.ArgumentNullException>::.ctor(var<u1>)
0xb855f4  throw
0xb855f5  stloc.s  5
0xb855f7  ldc.i4   0x39663467
0xb855fc  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb85601  ldc.i4.s 0xA
0xb85603  ldc.i4.6
0xb85604  newarr   [mscorlib]System.String
0xb85609  stloc.s  0x15
0xb8560b  ldloc.s  0x15
0xb8560d  ldc.i4.0
0xb8560e  ldstr    asc_C6AA32// "'"
0xb85613  stelem.ref
0xb85614  ldloc.s  0x15
0xb85616  ldc.i4.1
0xb85617  ldarg.0
0xb85618  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xb8561d  stelem.ref
0xb8561e  ldloc.s  0x15
0xb85620  ldc.i4.2
0xb85621  ldstr    aBdcserviceappl_2// "' BdcServiceApplication logging server "...
0xb85626  stelem.ref
0xb85627  ldloc.s  0x15
0xb85629  ldc.i4.3
0xb8562a  ldloc.s  5
0xb8562c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xb85631  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xb85636  stelem.ref
0xb85637  ldloc.s  0x15
0xb85639  ldc.i4.4
0xb8563a  ldstr    aBeforeMarshall// " before marshalling and rethrowing on c"...
0xb8563f  stelem.ref
0xb85640  ldloc.s  0x15
0xb85642  ldc.i4.5
0xb85643  ldloc.s  5
0xb85645  callvirt instance string [mscorlib]System.Object::ToString()
0xb8564a  stelem.ref
0xb8564b  ldloc.s  0x15
0xb8564d  call     string [mscorlib]System.String::Concat(string[])
0xb85652  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0xb85657  ldloc.s  5
0xb85659  newobj   instance void class [System.ServiceModel]System.ServiceModel.FaultException`1<class [mscorlib]System.ArgumentOutOfRangeException>::.ctor(var<u1>)
0xb8565e  throw
0xb8565f  stloc.s  6
0xb85661  ldc.i4   0x39663468
0xb85666  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_SPS_BusinessData()
0xb8566b  ldc.i4.s 0xA
0xb8566d  ldc.i4.6
0xb8566e  newarr   [mscorlib]System.String
0xb85673  stloc.s  0x16
0xb85675  ldloc.s  0x16
0xb85677  ldc.i4.0
0xb85678  ldstr    asc_C6AA32// "'"
0xb8567d  stelem.ref
0xb8567e  ldloc.s  0x16
0xb85680  ldc.i4.1
0xb85681  ldarg.0
0xb85682  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xb85687  stelem.ref
0xb85688  ldloc.s  0x16
0xb8568a  ldc.i4.2
0xb8568b  ldstr    aBdcserviceappl_2// "' BdcServiceApplication logging server "...
0xb85690  stelem.ref
0xb85691  ldloc.s  0x16
0xb85693  ldc.i4.3
0xb85694  ldloc.s  6
0xb85696  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
  ... truncated ...
```
