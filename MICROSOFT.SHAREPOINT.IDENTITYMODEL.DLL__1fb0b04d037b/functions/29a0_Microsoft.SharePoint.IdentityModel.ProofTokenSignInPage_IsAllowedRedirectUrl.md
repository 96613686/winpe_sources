# Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::IsAllowedRedirectUrl

- ea: `0x29a0`
- end: `0x2a66`
- name: `Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::IsAllowedRedirectUrl`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x2300`

## callees

- `0x29a0`
- `0x2a70`
- `0x2b00`
- `0x2bb0`
- `0x2c630`

## string_xrefs

- `0x29af`: `redirectUri`
- `0x2a05`: `ProofTokenSignIn: no FilterSilentRedirect IsAllowedRedirectUrl: `
- `0x2a4e`: `ProofTokenSignIn: with FilterSilentRedirect IsAllowedRedirectUrl: `

## pseudocode

```c

```

## disassembly

```asm
0x29a0  ldc.i4   0x175A1C6
0x29a5  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x29aa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x29af  ldstr    aRedirecturi_0// "redirectUri"
0x29b4  ldarg.0
0x29b5  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnRelative(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, class [System]System.Uri value)
0x29ba  ldc.i4.0
0x29bb  stloc.0
0x29bc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x29c1  ldnull
0x29c2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x29c7  brfalse.s loc_29DF
0x29c9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x29ce  callvirt instance class [System]System.Collections.Generic.ISet`1<int32> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_ServerDebugFlags()
0x29d3  ldc.i4   0xD0FE
0x29d8  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<int32>::Contains(var<u1>)
0x29dd  br.s     loc_29E0
0x29df  ldc.i4.0
0x29e0  stloc.1
0x29e1  ldloc.1
0x29e2  brfalse.s loc_2A1D
0x29e4  ldarg.0
0x29e5  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::LookupSiteSubscriptionId(class [System]System.Uri redirectUri)
0x29ea  stloc.2
0x29eb  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::GetCurrentSiteSubscriptionId()
0x29f0  stloc.3
0x29f1  ldloc.2
0x29f2  ldloc.3
0x29f3  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x29f8  stloc.0
0x29f9  ldc.i4   0x1E495856
0x29fe  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2a03  ldc.i4.s 0x32
0x2a05  ldstr    aProoftokensign_36// "ProofTokenSignIn: no FilterSilentRedire"...
0x2a0a  ldloca.s 0
0x2a0c  call     instance string [mscorlib]System.Boolean::ToString()
0x2a11  call     string [mscorlib]System.String::Concat(string, string)
0x2a16  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2a1b  br.s     loc_2A64
0x2a1d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a22  stloc.s  4
0x2a24  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::GetCurrentSiteSubscriptionId()
0x2a29  stloc.s  5
0x2a2b  ldarg.0
0x2a2c  ldloca.s 4
0x2a2e  call     bool Microsoft.SharePoint.IdentityModel.ProofTokenSignInPage::TryLookupSiteSubscriptionId(class [System]System.Uri redirectUri, [out] valuetype [mscorlib]System.Guid& retSiteSubscriptionId)
0x2a33  brfalse.s loc_2A40
0x2a35  ldloc.s  4
0x2a37  ldloc.s  5
0x2a39  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2a3e  br.s     loc_2A41
0x2a40  ldc.i4.0
0x2a41  stloc.0
0x2a42  ldc.i4   0x1E495855
0x2a47  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2a4c  ldc.i4.s 0x32
0x2a4e  ldstr    aProoftokensign_37// "ProofTokenSignIn: with FilterSilentRedi"...
0x2a53  ldloca.s 0
0x2a55  call     instance string [mscorlib]System.Boolean::ToString()
0x2a5a  call     string [mscorlib]System.String::Concat(string, string)
0x2a5f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2a64  ldloc.0
0x2a65  ret
```
