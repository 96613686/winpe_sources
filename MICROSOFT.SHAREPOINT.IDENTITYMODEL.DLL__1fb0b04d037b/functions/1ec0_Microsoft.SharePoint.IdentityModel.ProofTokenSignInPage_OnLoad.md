# Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::OnLoad

- ea: `0x1ec0`
- end: `0x20fd`
- name: `Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::OnLoad`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1bd0`
- `0x1e70`
- `0x1ec0`
- `0x2110`
- `0x2250`
- `0x2300`
- `0x2780`
- `0x27a0`
- `0x7790`
- `0x77d0`

## string_xrefs

- `0x1f1e`: `ProofTokenSignIn: Request has proof and identity tokens, will try to authenticate. Diagnostic: '{0}'.`
- `0x1f4b`: `ProofTokenSignIn: Authentication finished successfully for user:{0} and actor:{1}`
- `0x1f8a`: `ProofTokenSignIn: Request has correct information to start the authentication flow. Diagnostic: '{0}'.`
- `0x1fbf`: `ProofTokenSignIn: Request doesn't have correct sufficient information to start an authentication flow. Diagnostic: '{0}'.`
- `0x1ff8`: `ProofTokenSignIn: disable filter silent redirect: '{0}'.`
- `0x202a`: `ProofTokenSignIn: Feature is not enabled, passing through. Diagnostic: '{0}'.`
- `0x207a`: `ProofTokenSignIn: Something went wrong, will try to return a 302 to redirect uri. Diagnostic: '{0}', Exception: '{1}'.`
- `0x20ce`: `ProofTokenSignIn: Something went wrong, failing. Diagnostic: '{0}', Exception: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1ec0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x1ec5  ldnull
0x1ec6  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x1ecb  brfalse.s loc_1EE3
0x1ecd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x1ed2  callvirt instance class [System]System.Collections.Generic.ISet`1<int32> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_ServerDebugFlags()
0x1ed7  ldc.i4   0xD0FE
0x1edc  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<int32>::Contains(var<u1>)
0x1ee1  br.s     loc_1EE4
0x1ee3  ldc.i4.0
0x1ee4  stloc.0
0x1ee5  ldarg.0
0x1ee6  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0x1eeb  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x1ef0  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::AllowFramingFlag
0x1ef5  ldstr    a1// "1"
0x1efa  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x1eff  ldarg.0
0x1f00  call     instance bool Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_IsFeatureEnabled()
0x1f05  brfalse  loc_201E
0x1f0a  ldarg.0
0x1f0b  call     instance bool Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::HasToken()
0x1f10  brfalse.s loc_1F76
0x1f12  ldc.i4   0x35F78B
0x1f17  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1f1c  ldc.i4.s 0x32
0x1f1e  ldstr    aProoftokensign_5// "ProofTokenSignIn: Request has proof and"...
0x1f23  ldc.i4.1
0x1f24  newarr   [mscorlib]System.Object
0x1f29  stloc.3
0x1f2a  ldloc.3
0x1f2b  ldc.i4.0
0x1f2c  ldarg.0
0x1f2d  call     instance string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_DiagnosticString()
0x1f32  stelem.ref
0x1f33  ldloc.3
0x1f34  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f39  ldarg.0
0x1f3a  call     instance void Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::SignInAppWeb()
0x1f3f  ldc.i4   0x35F78C
0x1f44  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1f49  ldc.i4.s 0x32
0x1f4b  ldstr    aProoftokensign_6// "ProofTokenSignIn: Authentication finish"...
0x1f50  ldc.i4.2
0x1f51  newarr   [mscorlib]System.Object
0x1f56  stloc.s  4
0x1f58  ldloc.s  4
0x1f5a  ldc.i4.0
0x1f5b  call     string SPApplicationAuthenticationHelper::GetLoggedInUserNameOrDefault()
0x1f60  stelem.ref
0x1f61  ldloc.s  4
0x1f63  ldc.i4.1
0x1f64  call     string SPApplicationAuthenticationHelper::GetLoggedInActorNameOrDefault()
0x1f69  stelem.ref
0x1f6a  ldloc.s  4
0x1f6c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f71  br       loc_205D
0x1f76  ldarg.0
0x1f77  call     instance bool Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::ShouldRedirectWithProofToken()
0x1f7c  brfalse.s loc_1FB3
0x1f7e  ldc.i4   0x35F78D
0x1f83  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1f88  ldc.i4.s 0x32
0x1f8a  ldstr    aProoftokensign_7// "ProofTokenSignIn: Request has correct i"...
0x1f8f  ldc.i4.1
0x1f90  newarr   [mscorlib]System.Object
0x1f95  stloc.s  5
0x1f97  ldloc.s  5
0x1f99  ldc.i4.0
0x1f9a  ldarg.0
0x1f9b  call     instance string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_DiagnosticString()
0x1fa0  stelem.ref
0x1fa1  ldloc.s  5
0x1fa3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1fa8  ldarg.0
0x1fa9  callvirt instance void Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::OnLogOnRequestToAppWeb()
0x1fae  br       loc_205D
0x1fb3  ldc.i4   0x35F78E
0x1fb8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1fbd  ldc.i4.s 0xA
0x1fbf  ldstr    aProoftokensign_8// "ProofTokenSignIn: Request doesn't have "...
0x1fc4  ldc.i4.1
0x1fc5  newarr   [mscorlib]System.Object
0x1fca  stloc.s  6
0x1fcc  ldloc.s  6
0x1fce  ldc.i4.0
0x1fcf  ldarg.0
0x1fd0  call     instance string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_DiagnosticString()
0x1fd5  stelem.ref
0x1fd6  ldloc.s  6
0x1fd8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1fdd  ldloc.0
0x1fde  brfalse.s loc_205D
0x1fe0  ldc.i4   0x2B2E
0x1fe5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x1fea  brtrue.s loc_205D
0x1fec  ldc.i4   0x1E495857
0x1ff1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x1ff6  ldc.i4.s 0x14
0x1ff8  ldstr    aProoftokensign_9// "ProofTokenSignIn: disable filter silent"...
0x1ffd  ldc.i4.1
0x1ffe  newarr   [mscorlib]System.Object
0x2003  stloc.s  7
0x2005  ldloc.s  7
0x2007  ldc.i4.0
0x2008  ldarg.0
0x2009  call     instance string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_DiagnosticString()
0x200e  stelem.ref
0x200f  ldloc.s  7
0x2011  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2016  ldarg.0
0x2017  call     instance void Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::PassThrough()
0x201c  br.s     loc_205D
0x201e  ldc.i4   0x35F78F
0x2023  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2028  ldc.i4.s 0x32
0x202a  ldstr    aProoftokensign_10// "ProofTokenSignIn: Feature is not enable"...
0x202f  ldc.i4.1
0x2030  newarr   [mscorlib]System.Object
0x2035  stloc.s  8
0x2037  ldloc.s  8
0x2039  ldc.i4.0
0x203a  ldarg.0
0x203b  call     instance string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_DiagnosticString()
0x2040  stelem.ref
0x2041  ldloc.s  8
0x2043  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2048  ldloc.0
0x2049  brfalse.s loc_205D
0x204b  ldc.i4   0x2B2E
0x2050  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x2055  brtrue.s loc_205D
0x2057  ldarg.0
0x2058  call     instance void Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::PassThrough()
0x205d  leave    loc_20FC
0x2062  stloc.1
0x2063  ldloc.1
0x2064  isinst   [mscorlib]System.Threading.ThreadAbortException
0x2069  brtrue   loc_20FA
0x206e  ldc.i4   0x35F790
0x2073  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2078  ldc.i4.s 0xA
0x207a  ldstr    aProoftokensign_11// "ProofTokenSignIn: Something went wrong,"...
0x207f  ldc.i4.2
0x2080  newarr   [mscorlib]System.Object
0x2085  stloc.s  9
0x2087  ldloc.s  9
0x2089  ldc.i4.0
0x208a  ldarg.0
0x208b  call     instance string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_DiagnosticString()
0x2090  stelem.ref
0x2091  ldloc.s  9
0x2093  ldc.i4.1
0x2094  ldloc.1
0x2095  callvirt instance string [mscorlib]System.Object::ToString()
0x209a  stelem.ref
0x209b  ldloc.s  9
0x209d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x20a2  ldloc.0
0x20a3  brfalse.s loc_20FA
0x20a5  ldc.i4   0x2B2E
0x20aa  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x20af  brtrue.s loc_20FA
0x20b1  ldarg.0
0x20b2  call     instance void Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::PassThrough()
0x20b7  leave.s  loc_20FA
0x20b9  stloc.2
0x20ba  ldloc.2
0x20bb  isinst   [mscorlib]System.Threading.ThreadAbortException
0x20c0  brtrue.s loc_20F8
0x20c2  ldc.i4   0x35F791
0x20c7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x20cc  ldc.i4.s 0xA
0x20ce  ldstr    aProoftokensign_12// "ProofTokenSignIn: Something went wrong,"...
0x20d3  ldc.i4.2
0x20d4  newarr   [mscorlib]System.Object
0x20d9  stloc.s  0xA
0x20db  ldloc.s  0xA
0x20dd  ldc.i4.0
0x20de  ldarg.0
0x20df  call     instance string Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::get_DiagnosticString()
0x20e4  stelem.ref
0x20e5  ldloc.s  0xA
0x20e7  ldc.i4.1
0x20e8  ldloc.2
0x20e9  callvirt instance string [mscorlib]System.Object::ToString()
0x20ee  stelem.ref
0x20ef  ldloc.s  0xA
0x20f1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x20f6  rethrow
0x20f8  leave.s  loc_20FA
0x20fa  leave.s  loc_20FC
0x20fc  ret
```
