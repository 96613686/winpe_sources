# Microsoft.SharePoint.Utilities.SPUtility::MakeBrowserCacheSafeLayoutsUrl_2

- ea: `0x1a2860`
- end: `0x1a31d9`
- name: `Microsoft.SharePoint.Utilities.SPUtility::MakeBrowserCacheSafeLayoutsUrl_2`
- size: `2425`
- prototype: ``
- caller_count: `4`
- callee_count: `31`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1a2830`
- `0x1a2840`
- `0x1a2850`
- `0x806470`

## callees

- `0x199cc0`
- `0x19a390`
- `0x19a550`
- `0x19a570`
- `0x19b090`
- `0x19b0b0`
- `0x19b0d0`
- `0x19b260`
- `0x19b610`
- `0x19bce0`
- `0x1a1f20`
- `0x1a2260`
- `0x1a27e0`
- `0x1a2860`
- `0x1b7de0`
- `0x1c89e0`
- `0x26dc40`
- `0x32cb80`
- `0x32d960`
- `0x32f0f0`
- `0x3e5560`
- `0x577060`
- `0x5c24f0`
- `0x6c9890`
- `0x7899a0`
- `0x7bea00`
- `0x7c99d0`
- `0x93dae0`
- `0x957470`
- `0x957550`
- `0xa134b0`

## string_xrefs

- `0x1a2bbd`: `Template\layouts`
- `0x1a2bea`: `Template\layouts`
- `0x1a289b`: `MakeBrowserCacheSafeLayoutsUrl: either an layouts or AxdReference name: {0}, StackTrace: {1}`
- `0x1a28ce`: `Defensive detection of cases not to MakeBrowserCacheSafeLayoutsUrl`
- `0x1a28f4`: `MakeBrowserCacheSafeLayoutsUrl: name appears to be a full URL: {0}, StackTrace: {1}`
- `0x1a292c`: `MakeBrowserCacheSafeLayoutsUrl: name should not contain SideBySideToken already: {0}, StackTrace: {1}`
- `0x1a2a6f`: `MakeBrowserCacheSafeLayoutsUrl: start computing localizable url for key=[{0}], name=[{1}]`
- `0x1a2ad9`: `Canonicalize paths before feeding them to File.Exists.`
- `0x1a2c25`: `Canonicalize paths before feeding them to File.Exists.`
- `0x1a2d73`: `Canonicalize paths before feeding them to File.Exists.`
- `0x1a2b03`: `MakeBrowserCacheSafeLayoutsUrl: Resource is unsafe. Resource: {0}, StackTrace: {1}`
- `0x1a2c4f`: `MakeBrowserCacheSafeLayoutsUrl: Resource is unsafe. Resource: {0}, StackTrace: {1}`
- `0x1a2d9d`: `MakeBrowserCacheSafeLayoutsUrl: Resource is unsafe. Resource: {0}, StackTrace: {1}`
- `0x1a2b3c`: `CannotMakeBrowserCacheSafeLayoutsUrl unknown resource: {0}, StackTrace: {1}`
- `0x1a2dd6`: `CannotMakeBrowserCacheSafeLayoutsUrl unknown resource: {0}, StackTrace: {1}`
- `0x1a2b97`: `MakeBrowserCacheSafeLayoutsUrl: start computing relative url for key=[{0}], name=[{1}]`
- `0x1a2c88`: `MakeBrowserCacheSafeLayoutsUrl: Unknown resource: {0}, StackTrace: {1}`
- `0x1a2cd0`: `MakeBrowserCacheSafeLayoutsUrl: start computing other types of url for key=[{0}], name=[{1}]`
- `0x1a2e20`: `CannotMakeBrowserCacheSafeLayoutsUrl NotSupportedException: {0}, exception: {1}, StackTrace: {2}`
- `0x1a2e5b`: `CannotMakeBrowserCacheSafeLayoutsUrl NotSupportedException: {0}, StackTrace: {1}`
- `0x1a2e8d`: `CannotMakeBrowserCacheSafeLayoutsUrl`
- `0x1a2f3f`: `CannotMakeBrowserCacheSafeLayoutsUrl`
- `0x1a2ff1`: `CannotMakeBrowserCacheSafeLayoutsUrl`
- `0x1a31b1`: `CannotMakeBrowserCacheSafeLayoutsUrl`
- `0x1a2ed2`: `CannotMakeBrowserCacheSafeLayoutsUrl IOException: {0}, exception: {1}, StackTrace: {2}`
- `0x1a2f0d`: `CannotMakeBrowserCacheSafeLayoutsUrl IOException: {0}, StackTrace: {1}`
- `0x1a2f84`: `CannotMakeBrowserCacheSafeLayoutsUrl ArgumentException: {0}, exception: {1}, StackTrace: {2}`
- `0x1a2fbf`: `CannotMakeBrowserCacheSafeLayoutsUrl ArgumentException: {0}, StackTrace: {1}`
- `0x1a3080`: `MakeBrowserCacheSafeLayoutsUrl: finished computing url, key=[{0}], name=[{1}], url=[{2}], hash=[{3}]`
- `0x1a30fd`: `CannotMakeBrowserCacheSafeLayoutsUrl: resource not available on the FE and CDN is not working either! key=[{0}], EnableCdn=[{1}], CdnPrefix=[{2}], EnableSideBySide=[{3}], SideBySideToken=[{4}]. StackTrace: {5}`
- `0x1a3185`: `CannotMakeBrowserCacheSafeLayoutsUrl: {0}, StackTrace: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1a2860  ldloca.s 0
0x1a2862  ldstr    a1a2fef51C68d4d// "1A2FEF51-C68D-4D95-9FB2-01D3151086C0"
0x1a2867  call     instance void [mscorlib]System.Guid::.ctor(string)
0x1a286c  ldarg.0
0x1a286d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a2872  brfalse.s loc_1A287F
0x1a2874  ldstr    aName// "name"
0x1a2879  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1a287e  throw
0x1a287f  ldarg.0
0x1a2880  call     bool Microsoft.SharePoint.Utilities.SPUtility::IsLayoutsUrl(string name)
0x1a2885  brtrue.s loc_1A288F
0x1a2887  ldarg.0
0x1a2888  call     bool Microsoft.SharePoint.Utilities.SPUtility::IsAxdReference(string name)
0x1a288d  brfalse.s loc_1A28BF
0x1a288f  ldc.i4   0x10557D0
0x1a2894  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Upgrade()
0x1a2899  ldc.i4.s 0x64
0x1a289b  ldstr    aMakebrowsercac// "MakeBrowserCacheSafeLayoutsUrl: either "...
0x1a28a0  ldc.i4.2
0x1a28a1  newarr   [mscorlib]System.Object
0x1a28a6  stloc.s  0x10
0x1a28a8  ldloc.s  0x10
0x1a28aa  ldc.i4.0
0x1a28ab  ldarg.0
0x1a28ac  stelem.ref
0x1a28ad  ldloc.s  0x10
0x1a28af  ldc.i4.1
0x1a28b0  call     string [mscorlib]System.Environment::get_StackTrace()
0x1a28b5  stelem.ref
0x1a28b6  ldloc.s  0x10
0x1a28b8  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x1a28bd  ldarg.0
0x1a28be  ret
0x1a28bf  ldstr    a1c7e15fb236c40// "1C7E15FB-236C-40FD-AE4F-67FADFA24994"
0x1a28c4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1a28c9  ldstr    a10302015// "10/30/2015"
0x1a28ce  ldstr    aDefensiveDetec// "Defensive detection of cases not to Mak"...
0x1a28d3  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x1a28d8  brtrue.s loc_1A2950
0x1a28da  ldarg.0
0x1a28db  ldstr    aHttp_1// "http"
0x1a28e0  ldc.i4.5
0x1a28e1  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1a28e6  brtrue.s loc_1A2918
0x1a28e8  ldc.i4   0x10557D1
0x1a28ed  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Upgrade()
0x1a28f2  ldc.i4.s 0x64
0x1a28f4  ldstr    aMakebrowsercac_0// "MakeBrowserCacheSafeLayoutsUrl: name ap"...
0x1a28f9  ldc.i4.2
0x1a28fa  newarr   [mscorlib]System.Object
0x1a28ff  stloc.s  0x11
0x1a2901  ldloc.s  0x11
0x1a2903  ldc.i4.0
0x1a2904  ldarg.0
0x1a2905  stelem.ref
0x1a2906  ldloc.s  0x11
0x1a2908  ldc.i4.1
0x1a2909  call     string [mscorlib]System.Environment::get_StackTrace()
0x1a290e  stelem.ref
0x1a290f  ldloc.s  0x11
0x1a2911  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x1a2916  ldarg.0
0x1a2917  ret
0x1a2918  ldarg.0
0x1a2919  call     bool Microsoft.SharePoint.Administration.SPWebService::ContainsSideBySideTokenPattern(string token)
0x1a291e  brfalse.s loc_1A2950
0x1a2920  ldc.i4   0x10557D2
0x1a2925  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Upgrade()
0x1a292a  ldc.i4.s 0x64
0x1a292c  ldstr    aMakebrowsercac_1// "MakeBrowserCacheSafeLayoutsUrl: name sh"...
0x1a2931  ldc.i4.2
0x1a2932  newarr   [mscorlib]System.Object
0x1a2937  stloc.s  0x12
0x1a2939  ldloc.s  0x12
0x1a293b  ldc.i4.0
0x1a293c  ldarg.0
0x1a293d  stelem.ref
0x1a293e  ldloc.s  0x12
0x1a2940  ldc.i4.1
0x1a2941  call     string [mscorlib]System.Environment::get_StackTrace()
0x1a2946  stelem.ref
0x1a2947  ldloc.s  0x12
0x1a2949  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x1a294e  ldarg.0
0x1a294f  ret
0x1a2950  ldc.i4.0
0x1a2951  stloc.1
0x1a2952  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1a2957  call     class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.WebControls.SPControl::GetContextWeb(class [System.Web]System.Web.HttpContext context)
0x1a295c  stloc.2
0x1a295d  ldarg.3
0x1a295e  brtrue.s loc_1A299E
0x1a2960  ldloc.2
0x1a2961  brfalse.s loc_1A2970
0x1a2963  ldloc.2
0x1a2964  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x1a2969  callvirt instance int32 Microsoft.SharePoint.SPSite::get_CompatibilityLevel()
0x1a296e  br.s     loc_1A2972
0x1a2970  ldc.i4.s 0xF
0x1a2972  starg.s  3
0x1a2974  ldc.i4   0x200207
0x1a2979  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Upgrade()
0x1a297e  ldc.i4.s 0x64
0x1a2980  ldstr    aDesiredversion// "desiredVersion: {0}"
0x1a2985  ldc.i4.1
0x1a2986  newarr   [mscorlib]System.Object
0x1a298b  stloc.s  0x13
0x1a298d  ldloc.s  0x13
0x1a298f  ldc.i4.0
0x1a2990  ldarg.3
0x1a2991  box      [mscorlib]System.Int32
0x1a2996  stelem.ref
0x1a2997  ldloc.s  0x13
0x1a2999  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x1a299e  ldarg.3
0x1a299f  ldc.i4.s 0xF
0x1a29a1  bge.s    loc_1A29A6
0x1a29a3  ldnull
0x1a29a4  starg.s  1
0x1a29a6  ldarg.2
0x1a29a7  brfalse.s loc_1A29B9
0x1a29a9  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1a29ae  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0x1a29b3  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1a29b8  stloc.1
0x1a29b9  ldarg.3
0x1a29ba  box      [mscorlib]System.Int32
0x1a29bf  ldstr    asc_C7604A// "/"
0x1a29c4  call     string [mscorlib]System.String::Concat(object, object)
0x1a29c9  stloc.3
0x1a29ca  ldsfld   string [mscorlib]System.String::Empty
0x1a29cf  stloc.s  4
0x1a29d1  call     class Microsoft.SharePoint.Administration.SPWebService Microsoft.SharePoint.Administration.SPWebService::get_ContentService()
0x1a29d6  stloc.s  5
0x1a29d8  ldnull
0x1a29d9  ldloc.s  5
0x1a29db  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x1a29e0  brfalse.s loc_1A29F9
0x1a29e2  ldloc.s  5
0x1a29e4  callvirt instance unsigned int32 Microsoft.SharePoint.Administration.SPWebService::get_ResourceTag()
0x1a29e9  stloc.s  0x14
0x1a29eb  ldloca.s 0x14
0x1a29ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a29f2  call     instance string [mscorlib]System.UInt32::ToString(class [mscorlib]System.IFormatProvider)
0x1a29f7  stloc.s  4
0x1a29f9  ldarg.1
0x1a29fa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a29ff  brtrue.s loc_1A2A10
0x1a2a01  ldloc.3
0x1a2a02  ldarg.1
0x1a2a03  ldstr    asc_C7604A// "/"
0x1a2a08  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a2a0d  stloc.3
0x1a2a0e  br.s     loc_1A2A1E
0x1a2a10  ldloc.3
0x1a2a11  ldloc.s  4
0x1a2a13  ldstr    asc_C7604A// "/"
0x1a2a18  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a2a1d  stloc.3
0x1a2a1e  ldloc.3
0x1a2a1f  ldloca.s 1
0x1a2a21  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a2a26  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1a2a2b  ldstr    asc_C7604A// "/"
0x1a2a30  ldarg.0
0x1a2a31  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1a2a36  stloc.3
0x1a2a37  ldsfld   class Microsoft.SharePoint.Administration.SPVolatileCache`2<string, string> Microsoft.SharePoint.Utilities.SPUtility::s_layoutsFileHashCache
0x1a2a3c  ldloc.3
0x1a2a3d  callvirt instance var<u1> class Microsoft.SharePoint.Administration.SPCache`2<string, string>::get_Item(void)
0x1a2a42  stloc.s  6
0x1a2a44  ldloc.s  6
0x1a2a46  brtrue   loc_1A30BC
0x1a2a4b  ldarg.2
0x1a2a4c  brfalse  loc_1A2B66
0x1a2a51  ldloc.0
0x1a2a52  ldstr    a09202016// "09/20/2016"
0x1a2a57  ldstr    aSev1Investigat// "Sev-1 investigation of empty url"
0x1a2a5c  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x1a2a61  brtrue.s loc_1A2A8D
0x1a2a63  ldc.i4   0x13451A0
0x1a2a68  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Upgrade()
0x1a2a6d  ldc.i4.s 0x32
0x1a2a6f  ldstr    aMakebrowsercac_2// "MakeBrowserCacheSafeLayoutsUrl: start c"...
0x1a2a74  ldc.i4.2
0x1a2a75  newarr   [mscorlib]System.Object
0x1a2a7a  stloc.s  0x15
0x1a2a7c  ldloc.s  0x15
0x1a2a7e  ldc.i4.0
0x1a2a7f  ldloc.3
0x1a2a80  stelem.ref
0x1a2a81  ldloc.s  0x15
0x1a2a83  ldc.i4.1
0x1a2a84  ldarg.0
0x1a2a85  stelem.ref
0x1a2a86  ldloc.s  0x15
0x1a2a88  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x1a2a8d  ldloca.s 1
0x1a2a8f  ldarg.0
0x1a2a90  ldarg.1
0x1a2a91  ldarg.3
0x1a2a92  call     string Microsoft.SharePoint.Utilities.SPUtility::GetFilePathForLocalizedLayoutsUrl(int32& lcidUI, string name, string sideBySideToken, int32 desiredVersion)
0x1a2a97  stloc.s  8
0x1a2a99  ldloc.1
0x1a2a9a  brtrue.s loc_1A2A9F
0x1a2a9c  ldc.i4.0
0x1a2a9d  starg.s  2
0x1a2a9f  ldloc.s  8
0x1a2aa1  ldarg.3
0x1a2aa2  call     string Microsoft.SharePoint.Utilities.SPUtility::GetTemplatesSetupPath(int32 desiredPathVersion)
0x1a2aa7  call     bool Microsoft.SharePoint.Utilities.SPUtility::IsPathSubsumed(string pathSubsumed, string pathSubsumer)
0x1a2aac  brtrue.s loc_1A2AB9
0x1a2aae  ldstr    aName// "name"
0x1a2ab3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1a2ab8  throw
0x1a2ab9  ldarg.1
0x1a2aba  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a2abf  brfalse.s loc_1A2ACF
0x1a2ac1  ldloc.s  8
0x1a2ac3  call     string Microsoft.SharePoint.Utilities.SPUtility::ComputeFileHash(string filePath)
0x1a2ac8  stloc.s  7
0x1a2aca  br       loc_1A2DFB
0x1a2acf  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.SPUtility::CanonicalizeLayoutsPaths
0x1a2ad4  ldstr    a9192017// "9/19/2017"
0x1a2ad9  ldstr    aCanonicalizePa// "Canonicalize paths before feeding them "...
0x1a2ade  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x1a2ae3  brtrue.s loc_1A2B27
0x1a2ae5  ldloc.s  8
0x1a2ae7  ldc.i4.0
0x1a2ae8  call     string Microsoft.SharePoint.WebPartPages.Utility::CanonicalizeFullOrRelativeUrl(string fullOrRelativeUrl, bool includeQueryString)
0x1a2aed  ldloc.s  8
0x1a2aef  ldc.i4.5
0x1a2af0  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1a2af5  brtrue.s loc_1A2B27
0x1a2af7  ldc.i4   0x17C2507
0x1a2afc  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x1a2b01  ldc.i4.s 0xA
0x1a2b03  ldstr    aMakebrowsercac_3// "MakeBrowserCacheSafeLayoutsUrl: Resourc"...
0x1a2b08  ldc.i4.2
0x1a2b09  newarr   [mscorlib]System.Object
0x1a2b0e  stloc.s  0x16
0x1a2b10  ldloc.s  0x16
0x1a2b12  ldc.i4.0
0x1a2b13  ldloc.3
0x1a2b14  stelem.ref
0x1a2b15  ldloc.s  0x16
0x1a2b17  ldc.i4.1
0x1a2b18  call     string [mscorlib]System.Environment::get_StackTrace()
0x1a2b1d  stelem.ref
0x1a2b1e  ldloc.s  0x16
0x1a2b20  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x1a2b25  br.s     loc_1A2B5E
0x1a2b27  ldloc.s  8
0x1a2b29  call     bool [mscorlib]System.IO.File::Exists(string)
0x1a2b2e  brtrue.s loc_1A2B5E
0x1a2b30  ldc.i4   0x4C9150
0x1a2b35  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x1a2b3a  ldc.i4.s 0xA
0x1a2b3c  ldstr    aCannotmakebrow_0// "CannotMakeBrowserCacheSafeLayoutsUrl un"...
0x1a2b41  ldc.i4.2
0x1a2b42  newarr   [mscorlib]System.Object
0x1a2b47  stloc.s  0x17
0x1a2b49  ldloc.s  0x17
0x1a2b4b  ldc.i4.0
0x1a2b4c  ldloc.3
0x1a2b4d  stelem.ref
0x1a2b4e  ldloc.s  0x17
0x1a2b50  ldc.i4.1
0x1a2b51  call     string [mscorlib]System.Environment::get_StackTrace()
0x1a2b56  stelem.ref
0x1a2b57  ldloc.s  0x17
0x1a2b59  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x1a2b5e  ldarg.1
0x1a2b5f  stloc.s  7
0x1a2b61  br       loc_1A2DFB
0x1a2b66  ldarg.0
0x1a2b67  ldstr    asc_C7604A// "/"
0x1a2b6c  ldc.i4.0
0x1a2b6d  ldc.i4.5
0x1a2b6e  callvirt instance int32 [mscorlib]System.String::IndexOf(string, int32, valuetype [mscorlib]System.StringComparison)
0x1a2b73  ldc.i4.m1
0x1a2b74  bne.un   loc_1A2CB2
0x1a2b79  ldloc.0
0x1a2b7a  ldstr    a09202016// "09/20/2016"
0x1a2b7f  ldstr    aSev1Investigat// "Sev-1 investigation of empty url"
0x1a2b84  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x1a2b89  brtrue.s loc_1A2BB5
0x1a2b8b  ldc.i4   0x13451A1
0x1a2b90  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Upgrade()
0x1a2b95  ldc.i4.s 0x32
0x1a2b97  ldstr    aMakebrowsercac_4// "MakeBrowserCacheSafeLayoutsUrl: start c"...
0x1a2b9c  ldc.i4.2
0x1a2b9d  newarr   [mscorlib]System.Object
0x1a2ba2  stloc.s  0x18
0x1a2ba4  ldloc.s  0x18
0x1a2ba6  ldc.i4.0
0x1a2ba7  ldloc.3
0x1a2ba8  stelem.ref
0x1a2ba9  ldloc.s  0x18
  ... truncated ...
```
