# Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::TryResolveRedirectUriUsingFlags

- ea: `0x2830`
- end: `0x2992`
- name: `Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::TryResolveRedirectUriUsingFlags`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1be0`

## callees

- `0x2830`

## string_xrefs

- `0x2847`: `ProofTokenSignIn: There is no RedirectUriFlag`
- `0x286f`: `ProofTokenSignIn: RedirectUriFlag={0} and it's not valid`
- `0x28a3`: `ProofTokenSignIn: RedirectUri after Base64UrlDecode is {0}`
- `0x28d5`: `ProofTokenSignIn: Unable to decode the redirect uri {0}`
- `0x290a`: `ProofTokenSignIn: Use web-relative redirect url {0}`
- `0x293e`: `The redirect uri is web relative, but there is no context web`
- `0x296f`: `The redirect uri not a valid uri. Value={0}`

## pseudocode

```c

```

## disassembly

```asm
0x2830  ldarg.3
0x2831  ldarg.1
0x2832  stind.ref
0x2833  ldarg.2
0x2834  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2839  brfalse.s loc_2853
0x283b  ldc.i4   0x49C403
0x2840  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2845  ldc.i4.s 0x32
0x2847  ldstr    aProoftokensign_31// "ProofTokenSignIn: There is no RedirectU"...
0x284c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2851  ldc.i4.0
0x2852  ret
0x2853  ldarg.2
0x2854  ldc.i4.7
0x2855  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x285a  ldloca.s 0
0x285c  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x2861  brtrue.s loc_288A
0x2863  ldc.i4   0x49C404
0x2868  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x286d  ldc.i4.s 0x14
0x286f  ldstr    aProoftokensign_32// "ProofTokenSignIn: RedirectUriFlag={0} a"...
0x2874  ldc.i4.1
0x2875  newarr   [mscorlib]System.Object
0x287a  stloc.s  5
0x287c  ldloc.s  5
0x287e  ldc.i4.0
0x287f  ldarg.2
0x2880  stelem.ref
0x2881  ldloc.s  5
0x2883  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2888  ldc.i4.0
0x2889  ret
0x288a  ldc.i4.2
0x288b  ldloc.0
0x288c  and
0x288d  brfalse.s loc_28F6
0x288f  ldarg.1
0x2890  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::Base64UrlDecode(string)
0x2895  starg.s  1
0x2897  ldc.i4   0x49C405
0x289c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x28a1  ldc.i4.s 0x32
0x28a3  ldstr    aProoftokensign_33// "ProofTokenSignIn: RedirectUri after Bas"...
0x28a8  ldc.i4.1
0x28a9  newarr   [mscorlib]System.Object
0x28ae  stloc.s  6
0x28b0  ldloc.s  6
0x28b2  ldc.i4.0
0x28b3  ldarg.1
0x28b4  stelem.ref
0x28b5  ldloc.s  6
0x28b7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x28bc  leave.s  loc_28F6
0x28be  stloc.1
0x28bf  ldloc.1
0x28c0  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::FIsFatalException(class [mscorlib]System.Exception)
0x28c5  brfalse.s loc_28C9
0x28c7  rethrow
0x28c9  ldc.i4   0x49C406
0x28ce  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x28d3  ldc.i4.s 0x14
0x28d5  ldstr    aProoftokensign_34// "ProofTokenSignIn: Unable to decode the "...
0x28da  ldc.i4.1
0x28db  newarr   [mscorlib]System.Object
0x28e0  stloc.s  7
0x28e2  ldloc.s  7
0x28e4  ldc.i4.0
0x28e5  ldarg.1
0x28e6  stelem.ref
0x28e7  ldloc.s  7
0x28e9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x28ee  ldc.i4.0
0x28ef  stloc.s  4
0x28f1  leave    loc_298F
0x28f6  ldc.i4.1
0x28f7  ldloc.0
0x28f8  and
0x28f9  brfalse  loc_298A
0x28fe  ldc.i4   0x49C407
0x2903  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2908  ldc.i4.s 0x32
0x290a  ldstr    aProoftokensign_35// "ProofTokenSignIn: Use web-relative redi"...
0x290f  ldc.i4.1
0x2910  newarr   [mscorlib]System.Object
0x2915  stloc.s  8
0x2917  ldloc.s  8
0x2919  ldc.i4.0
0x291a  ldarg.1
0x291b  stelem.ref
0x291c  ldloc.s  8
0x291e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2923  ldarg.0
0x2924  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0x2929  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.SPControl::GetContextWeb(class [System.Web]System.Web.HttpContext)
0x292e  stloc.2
0x292f  ldloc.2
0x2930  brtrue.s loc_294A
0x2932  ldc.i4   0x49C408
0x2937  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x293c  ldc.i4.s 0x14
0x293e  ldstr    aTheRedirectUri// "The redirect uri is web relative, but t"...
0x2943  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2948  ldc.i4.0
0x2949  ret
0x294a  ldloc.2
0x294b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Url()
0x2950  ldarg.1
0x2951  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUrlUtility::CombineUrl(string, string)
0x2956  starg.s  1
0x2958  ldarg.1
0x2959  ldc.i4.1
0x295a  ldloca.s 3
0x295c  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x2961  brtrue.s loc_298A
0x2963  ldc.i4   0x49C409
0x2968  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x296d  ldc.i4.s 0x14
0x296f  ldstr    aTheRedirectUri_0// "The redirect uri not a valid uri. Value"...
0x2974  ldc.i4.1
0x2975  newarr   [mscorlib]System.Object
0x297a  stloc.s  9
0x297c  ldloc.s  9
0x297e  ldc.i4.0
0x297f  ldarg.1
0x2980  stelem.ref
0x2981  ldloc.s  9
0x2983  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2988  ldc.i4.0
0x2989  ret
0x298a  ldarg.3
0x298b  ldarg.1
0x298c  stind.ref
0x298d  ldc.i4.1
0x298e  ret
0x298f  ldloc.s  4
0x2991  ret
```
