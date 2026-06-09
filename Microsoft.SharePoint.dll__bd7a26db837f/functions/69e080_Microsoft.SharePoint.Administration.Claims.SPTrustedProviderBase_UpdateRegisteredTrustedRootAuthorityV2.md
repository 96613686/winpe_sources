# Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::UpdateRegisteredTrustedRootAuthorityV2

- ea: `0x69e080`
- end: `0x69e614`
- name: `Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::UpdateRegisteredTrustedRootAuthorityV2`
- size: `1428`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x69d930`

## callees

- `0x69d4c0`
- `0x69df60`
- `0x69e080`
- `0x69e620`
- `0x69e840`
- `0x7881c0`
- `0x8ecdb0`
- `0x93dab0`
- `0x93dae0`
- `0x9577b0`
- `0xbd6640`

## string_xrefs

- `0x69e0f7`: `SPTrustedAccessProvider: Certificate from Metadata is Null or Empty.`
- `0x69e144`: `SPTrustedAccessProvider: Found '{0}' Certificates from Metadata.`
- `0x69e185`: `SPTrustedAccessProvider: Found '{0}' Certificates from AutomaticallyRegisteredTrustedRootAuthorities.`
- `0x69e206`: `SPTrustedAccessProvider: Found '{0}' common Certificates between Metadata and AutomaticallyRegisteredTrustedRootAuthorities.`
- `0x69e268`: `SPTrustedAccessProvider: Didn't find '{0}' in Registered Certificates, clearing m_SigningCertificate.`
- `0x69e2c3`: `SPTrustedAccessProvider: m_SigningCertificate is not valid. ErrorMessage: '{0}'.`
- `0x69e373`: `SPTrustedAccessProvider: Removing Primary Certificate to ConfigDB. Thumbprint: '{0}'.`
- `0x69e428`: `SPTrustedAccessProvider: Removing registered Trusted Root Authorities by certificate. Thumbprint: '{0}'.`
- `0x69e46f`: `SPTrustedAccessProvider: Removing registered Trusted Root Authorities by certificate. Thumbprint: '{0}'.`
- `0x69e509`: `SPTrustedAccessProvider: Adding primary certificate to ConfigDB. Thumbprint: '{0}'.`
- `0x69e574`: `SPTrustedAccessProvider: AdditionalSigningCertificates is null.`
- `0x69e595`: `SPTrustedAccessProvider: Adding additional certificate to ConfigDB. Thumbprint: '{0}'.`
- `0x69e5cf`: `SPTrustedAccessProvider: Adding registered Trusted Root Authorities by certificate. Thumbprint: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x69e080  newobj   instance void <>c__DisplayClass9::.ctor()
0x69e085  stloc.s  8
0x69e087  ldc.i4   0x140520A
0x69e08c  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x69e091  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x69e096  ldstr    aCertificatelis// "certificateListFromMetadata"
0x69e09b  ldarg.1
0x69e09c  call     void Microsoft.SharePoint.Utilities.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x69e0a1  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_InvariantCultureIgnoreCase()
0x69e0a6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x69e0ab  stloc.0
0x69e0ac  ldarg.1
0x69e0ad  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::GetEnumerator()
0x69e0b2  stloc.s  9
0x69e0b4  br.s     loc_69E11F
0x69e0b6  ldloca.s 9
0x69e0b8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Current()
0x69e0bd  stloc.1
0x69e0be  ldloc.1
0x69e0bf  brfalse.s loc_69E0EB
0x69e0c1  ldloc.1
0x69e0c2  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x69e0c7  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x69e0cc  brtrue.s loc_69E0EB
0x69e0ce  ldloc.0
0x69e0cf  ldloc.1
0x69e0d0  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x69e0d5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::ContainsKey(var<u1>)
0x69e0da  brtrue.s loc_69E11F
0x69e0dc  ldloc.0
0x69e0dd  ldloc.1
0x69e0de  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x69e0e3  ldloc.1
0x69e0e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::Add(var<u1>, !!T0)
0x69e0e9  br.s     loc_69E11F
0x69e0eb  ldc.i4   0x140520B
0x69e0f0  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x69e0f5  ldc.i4.s 0x32
0x69e0f7  ldstr    aSptrustedacces_16// "SPTrustedAccessProvider: Certificate fr"...
0x69e0fc  ldc.i4.1
0x69e0fd  newarr   [mscorlib]System.Object
0x69e102  stloc.s  0xA
0x69e104  ldloc.s  0xA
0x69e106  ldc.i4.0
0x69e107  ldloc.0
0x69e108  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Keys()
0x69e10d  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Count()
0x69e112  box      [mscorlib]System.Int32
0x69e117  stelem.ref
0x69e118  ldloc.s  0xA
0x69e11a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x69e11f  ldloca.s 9
0x69e121  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::MoveNext()
0x69e126  brtrue.s loc_69E0B6
0x69e128  leave.s  loc_69E138
0x69e12a  ldloca.s 9
0x69e12c  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>
0x69e132  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69e137  endfinally
0x69e138  ldc.i4   0x140520C
0x69e13d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x69e142  ldc.i4.s 0x32
0x69e144  ldstr    aSptrustedacces_17// "SPTrustedAccessProvider: Found '{0}' Ce"...
0x69e149  ldc.i4.1
0x69e14a  newarr   [mscorlib]System.Object
0x69e14f  stloc.s  0xB
0x69e151  ldloc.s  0xB
0x69e153  ldc.i4.0
0x69e154  ldloc.0
0x69e155  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Keys()
0x69e15a  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Count()
0x69e15f  box      [mscorlib]System.Int32
0x69e164  stelem.ref
0x69e165  ldloc.s  0xB
0x69e167  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x69e16c  ldloc.s  8
0x69e16e  ldarg.0
0x69e16f  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2> Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::GetCertificatesFromAutomaticallyRegisteredTrustedRootAuthorities()
0x69e174  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2> <>c__DisplayClass9::certificatesRegistered
0x69e179  ldc.i4   0x140520D
0x69e17e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x69e183  ldc.i4.s 0x32
0x69e185  ldstr    aSptrustedacces_18// "SPTrustedAccessProvider: Found '{0}' Ce"...
0x69e18a  ldc.i4.1
0x69e18b  newarr   [mscorlib]System.Object
0x69e190  stloc.s  0xC
0x69e192  ldloc.s  0xC
0x69e194  ldc.i4.0
0x69e195  ldloc.s  8
0x69e197  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2> <>c__DisplayClass9::certificatesRegistered
0x69e19c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Keys()
0x69e1a1  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Count()
0x69e1a6  box      [mscorlib]System.Int32
0x69e1ab  stelem.ref
0x69e1ac  ldloc.s  0xC
0x69e1ae  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x69e1b3  ldloc.0
0x69e1b4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Keys()
0x69e1b9  ldloc.s  8
0x69e1bb  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2> <>c__DisplayClass9::certificatesRegistered
0x69e1c0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Keys()
0x69e1c5  call     T0x2B0005D7
0x69e1ca  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::CS$<>9__CachedAnonymousMethodDelegate8
0x69e1cf  brtrue.s loc_69E1E2
0x69e1d1  ldnull
0x69e1d2  ldftn    string Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::<UpdateRegisteredTrustedRootAuthorityV2>b__6(string x)
0x69e1d8  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x69e1dd  stsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::CS$<>9__CachedAnonymousMethodDelegate8
0x69e1e2  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::CS$<>9__CachedAnonymousMethodDelegate8
0x69e1e7  ldloc.s  8
0x69e1e9  ldftn    instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 <>c__DisplayClass9::<UpdateRegisteredTrustedRootAuthorityV2>b__7(string x)
0x69e1ef  newobj   instance void class [mscorlib]System.Func`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::.ctor(object, native int)
0x69e1f4  call     T0x2B0005D8
0x69e1f9  stloc.2
0x69e1fa  ldc.i4   0x140520E
0x69e1ff  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x69e204  ldc.i4.s 0x32
0x69e206  ldstr    aSptrustedacces_19// "SPTrustedAccessProvider: Found '{0}' co"...
0x69e20b  ldc.i4.1
0x69e20c  newarr   [mscorlib]System.Object
0x69e211  stloc.s  0xD
0x69e213  ldloc.s  0xD
0x69e215  ldc.i4.0
0x69e216  ldloc.2
0x69e217  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Keys()
0x69e21c  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Count()
0x69e221  box      [mscorlib]System.Int32
0x69e226  stelem.ref
0x69e227  ldloc.s  0xD
0x69e229  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x69e22e  ldarg.0
0x69e22f  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_SigningCertificate
0x69e234  brfalse.s loc_69E2B4
0x69e236  ldarg.0
0x69e237  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_SigningCertificate
0x69e23c  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x69e241  brfalse.s loc_69E2B4
0x69e243  ldloc.s  8
0x69e245  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2> <>c__DisplayClass9::certificatesRegistered
0x69e24a  ldarg.0
0x69e24b  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_SigningCertificate
0x69e250  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x69e255  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::ContainsKey(var<u1>)
0x69e25a  brtrue.s loc_69E2B4
0x69e25c  ldc.i4   0x140520F
0x69e261  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x69e266  ldc.i4.s 0x32
0x69e268  ldstr    aSptrustedacces_20// "SPTrustedAccessProvider: Didn't find '{"...
0x69e26d  ldc.i4.1
0x69e26e  newarr   [mscorlib]System.Object
0x69e273  stloc.s  0xE
0x69e275  ldloc.s  0xE
0x69e277  ldc.i4.0
0x69e278  ldarg.0
0x69e279  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_SigningCertificate
0x69e27e  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x69e283  stelem.ref
0x69e284  ldloc.s  0xE
0x69e286  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x69e28b  ldarg.0
0x69e28c  ldnull
0x69e28d  stfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_SigningCertificate
0x69e292  ldarg.0
0x69e293  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_Details()
0x69e298  ldstr    aIssuer// "Issuer"
0x69e29d  ldnull
0x69e29e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x69e2a3  ldarg.0
0x69e2a4  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_Details()
0x69e2a9  ldstr    aThumbprint// "Thumbprint"
0x69e2ae  ldnull
0x69e2af  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x69e2b4  leave.s  loc_69E30C
0x69e2b6  stloc.3
0x69e2b7  ldc.i4   0x1405210
0x69e2bc  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x69e2c1  ldc.i4.s 0xA
0x69e2c3  ldstr    aSptrustedacces_21// "SPTrustedAccessProvider: m_SigningCerti"...
0x69e2c8  ldc.i4.1
0x69e2c9  newarr   [mscorlib]System.Object
0x69e2ce  stloc.s  0xF
0x69e2d0  ldloc.s  0xF
0x69e2d2  ldc.i4.0
0x69e2d3  ldloc.3
0x69e2d4  callvirt instance string [mscorlib]System.Object::ToString()
0x69e2d9  stelem.ref
0x69e2da  ldloc.s  0xF
0x69e2dc  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x69e2e1  ldarg.0
0x69e2e2  ldnull
0x69e2e3  stfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_SigningCertificate
0x69e2e8  ldarg.0
0x69e2e9  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_Details()
0x69e2ee  ldstr    aIssuer// "Issuer"
0x69e2f3  ldnull
0x69e2f4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x69e2f9  ldarg.0
0x69e2fa  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_Details()
0x69e2ff  ldstr    aThumbprint// "Thumbprint"
0x69e304  ldnull
0x69e305  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x69e30a  leave.s  loc_69E30C
0x69e30c  ldloc.s  8
0x69e30e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2> <>c__DisplayClass9::certificatesRegistered
0x69e313  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Keys()
0x69e318  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::GetEnumerator()
0x69e31d  stloc.s  0x10
0x69e31f  br       loc_69E49D
0x69e324  ldloca.s 0x10
0x69e326  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Current()
0x69e32b  stloc.s  4
0x69e32d  ldloc.2
0x69e32e  ldloc.s  4
0x69e330  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::ContainsKey(var<u1>)
0x69e335  brtrue   loc_69E49D
0x69e33a  ldarg.0
0x69e33b  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_SigningCertificate
0x69e340  brfalse  loc_69E3CF
0x69e345  ldarg.0
0x69e346  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_SigningCertificate
0x69e34b  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x69e350  brfalse.s loc_69E3CF
0x69e352  ldloc.s  4
0x69e354  ldarg.0
0x69e355  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_SigningCertificate
0x69e35a  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x69e35f  ldc.i4.3
0x69e360  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x69e365  brfalse.s loc_69E3CF
0x69e367  ldc.i4   0x1405211
0x69e36c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x69e371  ldc.i4.s 0x32
0x69e373  ldstr    aSptrustedacces_22// "SPTrustedAccessProvider: Removing Prima"...
0x69e378  ldc.i4.1
0x69e379  newarr   [mscorlib]System.Object
0x69e37e  stloc.s  0x11
0x69e380  ldloc.s  0x11
0x69e382  ldc.i4.0
0x69e383  ldloc.s  4
0x69e385  stelem.ref
0x69e386  ldloc.s  0x11
0x69e388  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x69e38d  ldarg.0
0x69e38e  ldnull
0x69e38f  stfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_SigningCertificate
0x69e394  ldarg.0
0x69e395  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_Details()
0x69e39a  ldstr    aIssuer// "Issuer"
0x69e39f  ldnull
0x69e3a0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x69e3a5  ldarg.0
0x69e3a6  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::get_Details()
0x69e3ab  ldstr    aThumbprint// "Thumbprint"
0x69e3b0  ldnull
0x69e3b1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x69e3b6  ldarg.0
0x69e3b7  ldloc.s  8
0x69e3b9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2> <>c__DisplayClass9::certificatesRegistered
0x69e3be  ldloc.s  4
0x69e3c0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Item(void)
0x69e3c5  call     instance void Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::RemoveAutomaticallyRegisteredTrustedRootAuthority(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 certificate)
0x69e3ca  br       loc_69E49D
0x69e3cf  ldarg.0
0x69e3d0  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_AdditionalSigningCertificates
0x69e3d5  brfalse  loc_69E463
0x69e3da  ldarg.0
0x69e3db  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_AdditionalSigningCertificates
0x69e3e0  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x69e3e5  ldc.i4.1
0x69e3e6  sub
0x69e3e7  stloc.s  5
0x69e3e9  br.s     loc_69E45C
0x69e3eb  ldarg.0
0x69e3ec  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_AdditionalSigningCertificates
0x69e3f1  ldloc.s  5
0x69e3f3  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection::get_Item(int32)
0x69e3f8  stloc.s  6
0x69e3fa  ldloc.s  6
0x69e3fc  brfalse.s loc_69E456
0x69e3fe  ldloc.s  4
0x69e400  ldloc.s  6
0x69e402  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x69e407  ldc.i4.3
0x69e408  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x69e40d  brfalse.s loc_69E456
0x69e40f  ldarg.0
0x69e410  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection Microsoft.SharePoint.Administration.Claims.SPTrustedProviderBase::m_AdditionalSigningCertificates
0x69e415  ldloc.s  5
0x69e417  callvirt instance void [mscorlib]System.Collections.CollectionBase::RemoveAt(int32)
0x69e41c  ldc.i4   0x1405212
0x69e421  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x69e426  ldc.i4.s 0x32
0x69e428  ldstr    aSptrustedacces_23// "SPTrustedAccessProvider: Removing regis"...
0x69e42d  ldc.i4.1
0x69e42e  newarr   [mscorlib]System.Object
0x69e433  stloc.s  0x12
0x69e435  ldloc.s  0x12
0x69e437  ldc.i4.0
0x69e438  ldloc.s  4
0x69e43a  stelem.ref
  ... truncated ...
```
