# Microsoft.SharePoint.Library.SPRequest::SetHttpParameters

- ea: `0x37390`
- end: `0x37e38`
- name: `Microsoft.SharePoint.Library.SPRequest::SetHttpParameters`
- size: `2728`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x472f10`

## callees

- `0x30b0`
- `0x37390`
- `0x4727e0`
- `0x472800`
- `0x4729d0`
- `0x472c90`
- `0x472d60`

## string_xrefs

- `0x37489`: `bInvalidateCachedConfigurationProperties`
- `0x3768f`: `bInvalidateCachedConfigurationProperties`
- `0x37896`: `bInvalidateCachedConfigurationProperties`
- `0x37ab4`: `bInvalidateCachedConfigurationProperties`
- `0x37cc7`: `bInvalidateCachedConfigurationProperties`
- `0x374cf`: `bstrUserAgent`
- `0x376d5`: `bstrUserAgent`
- `0x378dc`: `bstrUserAgent`
- `0x37afa`: `bstrUserAgent`
- `0x37d0d`: `bstrUserAgent`
- `0x374ed`: `bstrSharingLinkSessionId`
- `0x376f3`: `bstrSharingLinkSessionId`
- `0x378fa`: `bstrSharingLinkSessionId`
- `0x37b18`: `bstrSharingLinkSessionId`
- `0x37d2b`: `bstrSharingLinkSessionId`

## pseudocode

```c

```

## disassembly

```asm
0x37390  ldarg.0
0x37391  dup
0x37392  ldfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x37397  ldc.i4.1
0x37398  add
0x37399  stfld    int32 Microsoft.SharePoint.Library.SPRequest::m_UnmanagedStackCount
0x3739e  ldarg.0
0x3739f  call     instance void Microsoft.SharePoint.Library.SPRequest::EnsureRightsPropagated()
0x373a4  ldarg.0
0x373a5  ldfld    class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass Microsoft.SharePoint.Library.SPRequest::m_SPRequest
0x373aa  ldarg.1
0x373ab  ldarg.2
0x373ac  ldarg.3
0x373ad  ldarg.s  4
0x373af  ldarg.s  5
0x373b1  ldarg.s  6
0x373b3  ldarg.s  7
0x373b5  ldarg.s  8
0x373b7  ldarg.s  9
0x373b9  ldarg.s  0xA
0x373bb  ldarg.s  0xB
0x373bd  ldarg.s  0xC
0x373bf  ldarg.s  0xD
0x373c1  ldarg.s  0xE
0x373c3  ldarg.s  0xF
0x373c5  ldarg.s  0x10
0x373c7  ldarg.s  0x11
0x373c9  ldarg.s  0x12
0x373cb  ldarg.s  0x13
0x373cd  ldarg.s  0x14
0x373cf  ldarg.s  0x15
0x373d1  ldarg.s  0x16
0x373d3  ldarg.s  0x17
0x373d5  ldarg.s  0x18
0x373d7  ldarg.s  0x19
0x373d9  ldarg.s  0x1A
0x373db  ldarg.s  0x1B
0x373dd  callvirt instance void [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.SPRequestInternalClass::SetHttpParameters(string, string, unsigned int32, valuetype [mscorlib]System.Guid, unsigned int8[]&, bool, string, string, unsigned int32, string, bool, string, string, bool, string, valuetype [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ApplicationPrincipalInfo&, bool, int32, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISPManagedObjectFactory, bool, class [Microsoft.SharePoint.Library]Microsoft.SharePoint.Library.ISPDataCallback, valuetype [mscorlib]System.Guid, string, string, int64, int64, string)
0x373e2  leave    loc_37E26
0x373e7  stloc.0
0x373e8  ldstr    aSethttpparamet// "SetHttpParameters"
0x373ed  ldarg.0
0x373ee  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x373f3  ldarg.0
0x373f4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x373f9  ldc.i4.s 0x19
0x373fb  newarr   [mscorlib]System.String
0x37400  stloc.s  5
0x37402  ldloc.s  5
0x37404  ldc.i4.0
0x37405  ldstr    aBstrhttpmethod// "bstrHttpMethod"
0x3740a  stelem.ref
0x3740b  ldloc.s  5
0x3740d  ldc.i4.1
0x3740e  ldstr    aBstrrequestdig// "bstrRequestDigest"
0x37413  stelem.ref
0x37414  ldloc.s  5
0x37416  ldc.i4.2
0x37417  ldstr    aFlags// "flags"
0x3741c  stelem.ref
0x3741d  ldloc.s  5
0x3741f  ldc.i4.3
0x37420  ldstr    aGtranlockerid// "gTranLockerId"
0x37425  stelem.ref
0x37426  ldloc.s  5
0x37428  ldc.i4.4
0x37429  ldstr    aBignoretimeout// "bIgnoreTimeout"
0x3742e  stelem.ref
0x3742f  ldloc.s  5
0x37431  ldc.i4.5
0x37432  ldstr    aBstruserlogin// "bstrUserLogin"
0x37437  stelem.ref
0x37438  ldloc.s  5
0x3743a  ldc.i4.6
0x3743b  ldstr    aBstruserkey// "bstrUserKey"
0x37440  stelem.ref
0x37441  ldloc.s  5
0x37443  ldc.i4.7
0x37444  ldstr    aUlrolecount// "ulRoleCount"
0x37449  stelem.ref
0x3744a  ldloc.s  5
0x3744c  ldc.i4.8
0x3744d  ldstr    aBstrroles// "bstrRoles"
0x37452  stelem.ref
0x37453  ldloc.s  5
0x37455  ldc.i4.s 9
0x37457  ldstr    aBwindowsmode// "bWindowsMode"
0x3745c  stelem.ref
0x3745d  ldloc.s  5
0x3745f  ldc.i4.s 0xA
0x37461  ldstr    aBstrappprincip// "bstrAppPrincipalName"
0x37466  stelem.ref
0x37467  ldloc.s  5
0x37469  ldc.i4.s 0xB
0x3746b  ldstr    aBstrappprincip_0// "bstrAppPrincipalPerms"
0x37470  stelem.ref
0x37471  ldloc.s  5
0x37473  ldc.i4.s 0xC
0x37475  ldstr    aBishostheadera// "bIsHostHeaderAppPrincipal"
0x3747a  stelem.ref
0x3747b  ldloc.s  5
0x3747d  ldc.i4.s 0xD
0x3747f  ldstr    aBstroriginalap// "bstrOriginalAppPrincipalIdentifier"
0x37484  stelem.ref
0x37485  ldloc.s  5
0x37487  ldc.i4.s 0xE
0x37489  ldstr    aBinvalidatecac// "bInvalidateCachedConfigurationPropertie"...
0x3748e  stelem.ref
0x3748f  ldloc.s  5
0x37491  ldc.i4.s 0xF
0x37493  ldstr    aLappdomainid// "lAppDomainId"
0x37498  stelem.ref
0x37499  ldloc.s  5
0x3749b  ldc.i4.s 0x10
0x3749d  ldstr    aPfactory// "pFactory"
0x374a2  stelem.ref
0x374a3  ldloc.s  5
0x374a5  ldc.i4.s 0x11
0x374a7  ldstr    aBcallstack// "bCallstack"
0x374ac  stelem.ref
0x374ad  ldloc.s  5
0x374af  ldc.i4.s 0x12
0x374b1  ldstr    aPcanarycallbac// "pCanaryCallback"
0x374b6  stelem.ref
0x374b7  ldloc.s  5
0x374b9  ldc.i4.s 0x13
0x374bb  ldstr    aGusersubscript// "gUserSubscriptionId"
0x374c0  stelem.ref
0x374c1  ldloc.s  5
0x374c3  ldc.i4.s 0x14
0x374c5  ldstr    aBstrclaimsuser// "bstrClaimsUserEmail"
0x374ca  stelem.ref
0x374cb  ldloc.s  5
0x374cd  ldc.i4.s 0x15
0x374cf  ldstr    aBstruseragent// "bstrUserAgent"
0x374d4  stelem.ref
0x374d5  ldloc.s  5
0x374d7  ldc.i4.s 0x16
0x374d9  ldstr    aPolicybehavior// "policyBehaviors"
0x374de  stelem.ref
0x374df  ldloc.s  5
0x374e1  ldc.i4.s 0x17
0x374e3  ldstr    aSessionattribu// "sessionAttributes"
0x374e8  stelem.ref
0x374e9  ldloc.s  5
0x374eb  ldc.i4.s 0x18
0x374ed  ldstr    aBstrsharinglin// "bstrSharingLinkSessionId"
0x374f2  stelem.ref
0x374f3  ldloc.s  5
0x374f5  ldc.i4.s 0x19
0x374f7  newarr   [mscorlib]System.Object
0x374fc  stloc.s  6
0x374fe  ldloc.s  6
0x37500  ldc.i4.0
0x37501  ldarg.1
0x37502  stelem.ref
0x37503  ldloc.s  6
0x37505  ldc.i4.1
0x37506  ldarg.2
0x37507  stelem.ref
0x37508  ldloc.s  6
0x3750a  ldc.i4.2
0x3750b  ldarg.3
0x3750c  box      [mscorlib]System.UInt32
0x37511  stelem.ref
0x37512  ldloc.s  6
0x37514  ldc.i4.3
0x37515  ldarg.s  4
0x37517  box      [mscorlib]System.Guid
0x3751c  stelem.ref
0x3751d  ldloc.s  6
0x3751f  ldc.i4.4
0x37520  ldarg.s  6
0x37522  box      [mscorlib]System.Boolean
0x37527  stelem.ref
0x37528  ldloc.s  6
0x3752a  ldc.i4.5
0x3752b  ldarg.s  7
0x3752d  stelem.ref
0x3752e  ldloc.s  6
0x37530  ldc.i4.6
0x37531  ldarg.s  8
0x37533  stelem.ref
0x37534  ldloc.s  6
0x37536  ldc.i4.7
0x37537  ldarg.s  9
0x37539  box      [mscorlib]System.UInt32
0x3753e  stelem.ref
0x3753f  ldloc.s  6
0x37541  ldc.i4.8
0x37542  ldarg.s  0xA
0x37544  stelem.ref
0x37545  ldloc.s  6
0x37547  ldc.i4.s 9
0x37549  ldarg.s  0xB
0x3754b  box      [mscorlib]System.Boolean
0x37550  stelem.ref
0x37551  ldloc.s  6
0x37553  ldc.i4.s 0xA
0x37555  ldarg.s  0xC
0x37557  stelem.ref
0x37558  ldloc.s  6
0x3755a  ldc.i4.s 0xB
0x3755c  ldarg.s  0xD
0x3755e  stelem.ref
0x3755f  ldloc.s  6
0x37561  ldc.i4.s 0xC
0x37563  ldarg.s  0xE
0x37565  box      [mscorlib]System.Boolean
0x3756a  stelem.ref
0x3756b  ldloc.s  6
0x3756d  ldc.i4.s 0xD
0x3756f  ldarg.s  0xF
0x37571  stelem.ref
0x37572  ldloc.s  6
0x37574  ldc.i4.s 0xE
0x37576  ldarg.s  0x11
0x37578  box      [mscorlib]System.Boolean
0x3757d  stelem.ref
0x3757e  ldloc.s  6
0x37580  ldc.i4.s 0xF
0x37582  ldarg.s  0x12
0x37584  box      [mscorlib]System.Int32
0x37589  stelem.ref
0x3758a  ldloc.s  6
0x3758c  ldc.i4.s 0x10
0x3758e  ldarg.s  0x13
0x37590  stelem.ref
0x37591  ldloc.s  6
0x37593  ldc.i4.s 0x11
0x37595  ldarg.s  0x14
0x37597  box      [mscorlib]System.Boolean
0x3759c  stelem.ref
0x3759d  ldloc.s  6
0x3759f  ldc.i4.s 0x12
0x375a1  ldarg.s  0x15
0x375a3  stelem.ref
0x375a4  ldloc.s  6
0x375a6  ldc.i4.s 0x13
0x375a8  ldarg.s  0x16
0x375aa  box      [mscorlib]System.Guid
0x375af  stelem.ref
0x375b0  ldloc.s  6
0x375b2  ldc.i4.s 0x14
0x375b4  ldarg.s  0x17
0x375b6  stelem.ref
0x375b7  ldloc.s  6
0x375b9  ldc.i4.s 0x15
0x375bb  ldarg.s  0x18
0x375bd  stelem.ref
0x375be  ldloc.s  6
0x375c0  ldc.i4.s 0x16
0x375c2  ldarg.s  0x19
0x375c4  box      [mscorlib]System.Int64
0x375c9  stelem.ref
0x375ca  ldloc.s  6
0x375cc  ldc.i4.s 0x17
0x375ce  ldarg.s  0x1A
0x375d0  box      [mscorlib]System.Int64
0x375d5  stelem.ref
0x375d6  ldloc.s  6
0x375d8  ldc.i4.s 0x18
0x375da  ldarg.s  0x1B
0x375dc  stelem.ref
0x375dd  ldloc.s  6
0x375df  ldloc.0
0x375e0  call     void Microsoft.SharePoint.SPGlobal::LogSPRequestMethodParametersOnException(string methodName, string userPrincipalName, string appPrincipalName, string[] parameterNames, object[] parameterValues, class [mscorlib]System.Exception ex)
0x375e5  ldloc.0
0x375e6  call     void Microsoft.SharePoint.SPGlobal::HandleComException(class [mscorlib]System.Runtime.InteropServices.COMException comEx)
0x375eb  rethrow
0x375ed  stloc.1
0x375ee  ldstr    aSethttpparamet// "SetHttpParameters"
0x375f3  ldarg.0
0x375f4  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_UserPrincipalName
0x375f9  ldarg.0
0x375fa  ldfld    string Microsoft.SharePoint.Library.SPRequest::m_AppPrincipalName
0x375ff  ldc.i4.s 0x19
0x37601  newarr   [mscorlib]System.String
0x37606  stloc.s  7
0x37608  ldloc.s  7
0x3760a  ldc.i4.0
0x3760b  ldstr    aBstrhttpmethod// "bstrHttpMethod"
0x37610  stelem.ref
0x37611  ldloc.s  7
0x37613  ldc.i4.1
0x37614  ldstr    aBstrrequestdig// "bstrRequestDigest"
0x37619  stelem.ref
0x3761a  ldloc.s  7
0x3761c  ldc.i4.2
0x3761d  ldstr    aFlags// "flags"
0x37622  stelem.ref
0x37623  ldloc.s  7
0x37625  ldc.i4.3
0x37626  ldstr    aGtranlockerid// "gTranLockerId"
0x3762b  stelem.ref
0x3762c  ldloc.s  7
0x3762e  ldc.i4.4
0x3762f  ldstr    aBignoretimeout// "bIgnoreTimeout"
0x37634  stelem.ref
0x37635  ldloc.s  7
  ... truncated ...
```
