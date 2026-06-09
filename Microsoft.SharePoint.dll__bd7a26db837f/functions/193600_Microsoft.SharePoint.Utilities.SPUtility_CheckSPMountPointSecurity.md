# Microsoft.SharePoint.Utilities.SPUtility::CheckSPMountPointSecurity

- ea: `0x193600`
- end: `0x19396f`
- name: `Microsoft.SharePoint.Utilities.SPUtility::CheckSPMountPointSecurity`
- size: `879`
- prototype: ``
- caller_count: `6`
- callee_count: `20`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x193a00`
- `0x193c70`
- `0x193ed0`
- `0x57db30`
- `0x731580`
- `0x73ae10`

## callees

- `0x1935e0`
- `0x193600`
- `0x1b7de0`
- `0x1b7df0`
- `0x420920`
- `0x4cd8e0`
- `0x4cddc0`
- `0x5c24f0`
- `0x5c57f0`
- `0x678580`
- `0x7be4d0`
- `0x7be510`
- `0x7be570`
- `0x7be580`
- `0x7beb40`
- `0x8ecdb0`
- `0x93dab0`
- `0x93dae0`
- `0x957470`
- `0x957bd0`

## string_xrefs

- `0x193606`: `CheckSPMountPointSecurity`
- `0x193656`: `CheckSPMountPointSecurity: HttpContext.Current is marked as an OAuth request. Bypassing NoScript check.`
- `0x1936a6`: `CheckSPMountPointSecurity - Current web template : {0}, ByPassNoScriptCheck : {1}`
- `0x1936e4`: `CheckSPMountPointSecurity : AllowUnSafeRemoteWebs flight is off`
- `0x193713`: `SPSMSITEHOST`
- `0x19372a`: `CheckSPMountPointSecurity : BypassNoScriptCheck is set to true but the web template is not personal site host.`
- `0x193735`: `BypassNoScriptCheck is set to true but the web template is not personal site host.`
- `0x19376c`: `MountPoint security error: NoScript isn't enabled on the host site. QueryString:({0})`
- `0x1937b0`: `[Uri is null]`
- `0x193830`: `[Uri is null]`
- `0x1938b2`: `[Uri is null]`
- `0x193931`: `[Uri is null]`
- `0x1937d7`: `MountPoint security error: NoScript isn't enabled on the host site`
- `0x1937ec`: `MountPoint security error: AllowUnSafeRemoteWebs is off and host web isn't a personal site. QueryString:({0})`
- `0x193859`: `MountPoint security error: AllowUnSafeRemoteWebs is off and host web isn't a personal site.`
- `0x19386e`: `MountPoint security error: spContext is null. QueryString:({0})`
- `0x1938db`: `MountPoint security error: spContext is null`
- `0x1938ed`: `MountPoint security error: exception thrown. QueryString:({0}). e:({1})`

## pseudocode

```c

```

## disassembly

```asm
0x193600  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x193605  stloc.0
0x193606  ldstr    aCheckspmountpo// "CheckSPMountPointSecurity"
0x19360b  ldc.i4   0x5C4284
0x193610  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x193615  ldc.i4   0x5C4285
0x19361a  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x19361f  ldc.i4   0x5C4286
0x193624  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x193629  ldc.i4.0
0x19362a  ldnull
0x19362b  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x193630  stloc.1
0x193631  ldloc.0
0x193632  brfalse  loc_193869
0x193637  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x19363c  brfalse.s loc_19366F
0x19363e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x193643  call     bool Microsoft.SharePoint.ApplicationServices.SPApplicationRequestHelper::IsOAuthRequest(class [System.Web]System.Web.HttpContext context)
0x193648  brfalse.s loc_19366F
0x19364a  ldc.i4   0x12958C6
0x19364f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_RESTfulListData()
0x193654  ldc.i4.s 0x32
0x193656  ldstr    aCheckspmountpo_0// "CheckSPMountPointSecurity: HttpContext."...
0x19365b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x193660  ldloc.1
0x193661  ldnull
0x193662  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x193667  ldc.i4.1
0x193668  stloc.s  8
0x19366a  leave    loc_19396C
0x19366f  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x193674  ldc.i4   0x2B19
0x193679  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsExpFeatureToggleEnabled(class Microsoft.SharePoint.SPContext spContext, valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x19367e  stloc.2
0x19367f  ldloc.0
0x193680  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0x193685  brfalse  loc_1937E7
0x19368a  ldloc.0
0x19368b  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0x193690  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x193695  brfalse  loc_1937E7
0x19369a  ldc.i4   0x1010211
0x19369f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x1936a4  ldc.i4.s 0x32
0x1936a6  ldstr    aCheckspmountpo_1// "CheckSPMountPointSecurity - Current web"...
0x1936ab  ldc.i4.2
0x1936ac  newarr   [mscorlib]System.Object
0x1936b1  stloc.s  9
0x1936b3  ldloc.s  9
0x1936b5  ldc.i4.0
0x1936b6  ldloc.0
0x1936b7  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0x1936bc  callvirt instance string Microsoft.SharePoint.SPWeb::get_WebTemplate()
0x1936c1  stelem.ref
0x1936c2  ldloc.s  9
0x1936c4  ldc.i4.1
0x1936c5  ldarg.1
0x1936c6  box      [mscorlib]System.Boolean
0x1936cb  stelem.ref
0x1936cc  ldloc.s  9
0x1936ce  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x1936d3  ldloc.2
0x1936d4  brtrue.s loc_1936FA
0x1936d6  ldarg.1
0x1936d7  brfalse.s loc_1936FA
0x1936d9  ldloc.1
0x1936da  ldc.i4   0x1010212
0x1936df  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x1936e4  ldstr    aCheckspmountpo_2// "CheckSPMountPointSecurity : AllowUnSafe"...
0x1936e9  ldnull
0x1936ea  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x1936ef  ldstr    aAllowunsaferem// "AllowUnSafeRemoteWebs flight is disable"...
0x1936f4  newobj   instance void [mscorlib]System.NotImplementedException::.ctor(string)
0x1936f9  throw
0x1936fa  ldloc.2
0x1936fb  brfalse.s loc_193740
0x1936fd  ldarg.1
0x1936fe  brfalse.s loc_193740
0x193700  ldloc.0
0x193701  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0x193706  brfalse.s loc_193740
0x193708  ldloc.0
0x193709  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0x19370e  callvirt instance string Microsoft.SharePoint.SPWeb::get_WebTemplate()
0x193713  ldstr    aSpsmsitehost// "SPSMSITEHOST"
0x193718  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x19371d  brfalse.s loc_193740
0x19371f  ldloc.1
0x193720  ldc.i4   0x1010210
0x193725  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x19372a  ldstr    aCheckspmountpo_3// "CheckSPMountPointSecurity : BypassNoScr"...
0x19372f  ldnull
0x193730  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x193735  ldstr    aBypassnoscript// "BypassNoScriptCheck is set to true but "...
0x19373a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x19373f  throw
0x193740  ldloc.2
0x193741  brfalse.s loc_193746
0x193743  ldarg.1
0x193744  brtrue.s loc_193758
0x193746  ldloc.0
0x193747  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPContext::get_Web()
0x19374c  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x193751  call     bool Microsoft.SharePoint.Utilities.SPUtility::IsNoScriptEnabled(class Microsoft.SharePoint.SPSite site)
0x193756  brfalse.s loc_193767
0x193758  ldloc.1
0x193759  ldnull
0x19375a  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x19375f  ldc.i4.1
0x193760  stloc.s  8
0x193762  leave    loc_19396C
0x193767  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19376c  ldstr    aMountpointSecu// "MountPoint security error: NoScript isn"...
0x193771  ldc.i4.1
0x193772  newarr   [mscorlib]System.Object
0x193777  stloc.s  0xA
0x193779  ldloc.s  0xA
0x19377b  ldc.i4.0
0x19377c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x193781  brfalse.s loc_1937B7
0x193783  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x193788  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x19378d  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x193792  ldnull
0x193793  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x193798  brtrue.s loc_1937B0
0x19379a  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x19379f  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1937a4  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x1937a9  callvirt instance string [System]System.Uri::get_Query()
0x1937ae  br.s     loc_1937BC
0x1937b0  ldstr    aUriIsNull// "[Uri is null]"
0x1937b5  br.s     loc_1937BC
0x1937b7  ldstr    aHttpcontextIsN// "[HttpContext is null]"
0x1937bc  stelem.ref
0x1937bd  ldloc.s  0xA
0x1937bf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1937c4  stloc.3
0x1937c5  ldloc.1
0x1937c6  ldc.i4   0x5C4287
0x1937cb  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x1937d0  ldloc.3
0x1937d1  ldnull
0x1937d2  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x1937d7  ldstr    aMountpointSecu_0// "MountPoint security error: NoScript isn"...
0x1937dc  ldc.i4   0x810200DD
0x1937e1  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage, int32 errorCode)
0x1937e6  throw
0x1937e7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1937ec  ldstr    aMountpointSecu_1// "MountPoint security error: AllowUnSafeR"...
0x1937f1  ldc.i4.1
0x1937f2  newarr   [mscorlib]System.Object
0x1937f7  stloc.s  0xB
0x1937f9  ldloc.s  0xB
0x1937fb  ldc.i4.0
0x1937fc  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x193801  brfalse.s loc_193837
0x193803  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x193808  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x19380d  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x193812  ldnull
0x193813  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x193818  brtrue.s loc_193830
0x19381a  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x19381f  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x193824  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x193829  callvirt instance string [System]System.Uri::get_Query()
0x19382e  br.s     loc_19383C
0x193830  ldstr    aUriIsNull// "[Uri is null]"
0x193835  br.s     loc_19383C
0x193837  ldstr    aHttpcontextIsN// "[HttpContext is null]"
0x19383c  stelem.ref
0x19383d  ldloc.s  0xB
0x19383f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x193844  stloc.s  4
0x193846  ldloc.1
0x193847  ldc.i4   0x5C4288
0x19384c  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x193851  ldloc.s  4
0x193853  ldnull
0x193854  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x193859  ldstr    aMountpointSecu_2// "MountPoint security error: AllowUnSafeR"...
0x19385e  ldc.i4   0x810200DE
0x193863  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage, int32 errorCode)
0x193868  throw
0x193869  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19386e  ldstr    aMountpointSecu_3// "MountPoint security error: spContext is"...
0x193873  ldc.i4.1
0x193874  newarr   [mscorlib]System.Object
0x193879  stloc.s  0xC
0x19387b  ldloc.s  0xC
0x19387d  ldc.i4.0
0x19387e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x193883  brfalse.s loc_1938B9
0x193885  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x19388a  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x19388f  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x193894  ldnull
0x193895  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x19389a  brtrue.s loc_1938B2
0x19389c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1938a1  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1938a6  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x1938ab  callvirt instance string [System]System.Uri::get_Query()
0x1938b0  br.s     loc_1938BE
0x1938b2  ldstr    aUriIsNull// "[Uri is null]"
0x1938b7  br.s     loc_1938BE
0x1938b9  ldstr    aHttpcontextIsN// "[HttpContext is null]"
0x1938be  stelem.ref
0x1938bf  ldloc.s  0xC
0x1938c1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1938c6  stloc.s  5
0x1938c8  ldloc.1
0x1938c9  ldc.i4   0x5C428A
0x1938ce  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x1938d3  ldloc.s  5
0x1938d5  ldnull
0x1938d6  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32 tag, string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x1938db  ldstr    aMountpointSecu_4// "MountPoint security error: spContext is"...
0x1938e0  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x1938e5  throw
0x1938e6  stloc.s  6
0x1938e8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1938ed  ldstr    aMountpointSecu_5// "MountPoint security error: exception th"...
0x1938f2  ldc.i4.2
0x1938f3  newarr   [mscorlib]System.Object
0x1938f8  stloc.s  0xD
0x1938fa  ldloc.s  0xD
0x1938fc  ldc.i4.0
0x1938fd  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x193902  brfalse.s loc_193938
0x193904  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x193909  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x19390e  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x193913  ldnull
0x193914  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x193919  brtrue.s loc_193931
0x19391b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x193920  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x193925  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x19392a  callvirt instance string [System]System.Uri::get_Query()
0x19392f  br.s     loc_19393D
0x193931  ldstr    aUriIsNull// "[Uri is null]"
0x193936  br.s     loc_19393D
0x193938  ldstr    aHttpcontextIsN// "[HttpContext is null]"
0x19393d  stelem.ref
0x19393e  ldloc.s  0xD
0x193940  ldc.i4.1
0x193941  ldloc.s  6
0x193943  stelem.ref
0x193944  ldloc.s  0xD
0x193946  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19394b  stloc.s  7
0x19394d  ldloc.1
0x19394e  ldloc.s  7
0x193950  ldnull
0x193951  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(string message, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x193956  ldarg.0
0x193957  brfalse.s loc_19395B
0x193959  rethrow
0x19395b  leave.s  loc_19395D
0x19395d  ldc.i4.0
0x19395e  stloc.s  8
0x193960  leave.s  loc_19396C
0x193962  ldloc.1
0x193963  brfalse.s loc_19396B
0x193965  ldloc.1
0x193966  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19396b  endfinally
0x19396c  ldloc.s  8
0x19396e  ret
```
