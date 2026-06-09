# Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::GetBearerTokenForUserAuthentication

- ea: `0x27740`
- end: `0x278d3`
- name: `Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::GetBearerTokenForUserAuthentication`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x282d0`

## callees

- `0x27740`
- `0x279d0`
- `0x27a40`
- `0x281a0`
- `0x28240`
- `0x282b0`
- `0x283e0`
- `0x28400`
- `0x28430`

## string_xrefs

- `0x27745`: `https://{0}/{1}/oauth2/token`
- `0x27810`: `openid`
- `0x278b7`: `access_token`

## pseudocode

```c

```

## disassembly

```asm
0x27740  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x27745  ldstr    aHttps01Oauth2T// "https://{0}/{1}/oauth2/token"
0x2774a  ldc.i4.2
0x2774b  newarr   [mscorlib]System.Object
0x27750  stloc.s  0xA
0x27752  ldloc.s  0xA
0x27754  ldc.i4.0
0x27755  ldarg.0
0x27756  call     instance string Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::get_AuthEndpoint()
0x2775b  stelem.ref
0x2775c  ldloc.s  0xA
0x2775e  ldc.i4.1
0x2775f  ldarg.0
0x27760  call     instance string Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::get_TenantId()
0x27765  stelem.ref
0x27766  ldloc.s  0xA
0x27768  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2776d  newobj   instance void [System]System.Uri::.ctor(string)
0x27772  stloc.0
0x27773  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x27778  stloc.2
0x27779  ldarg.0
0x2777a  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserCredential Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::userCredential
0x2777f  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserCredential::get_Password()
0x27784  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::SecureStringToBSTR(class [mscorlib]System.Security.SecureString)
0x27789  stloc.2
0x2778a  ldloc.2
0x2778b  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0x27790  stloc.1
0x27791  leave.s  loc_2779A
0x27793  ldloc.2
0x27794  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ZeroFreeBSTR(native int)
0x27799  endfinally
0x2779a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x2779f  stloc.s  9
0x277a1  ldloc.s  9
0x277a3  ldstr    aResource_0// "resource"
0x277a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x277ad  ldstr    aHttps0// "https://{0}"
0x277b2  ldc.i4.1
0x277b3  newarr   [mscorlib]System.Object
0x277b8  stloc.s  0xB
0x277ba  ldloc.s  0xB
0x277bc  ldc.i4.0
0x277bd  ldarg.0
0x277be  call     instance string Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::get_GraphApiEndpoint()
0x277c3  stelem.ref
0x277c4  ldloc.s  0xB
0x277c6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x277cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x277d0  ldloc.s  9
0x277d2  ldstr    aClientId// "client_id"
0x277d7  ldstr    aD3590ed652b341// "d3590ed6-52b3-4102-aeff-aad2292ab01c"
0x277dc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x277e1  ldloc.s  9
0x277e3  ldstr    aGrantType// "grant_type"
0x277e8  ldstr    aPassword// "password"
0x277ed  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x277f2  ldloc.s  9
0x277f4  ldstr    aUsername// "username"
0x277f9  ldarg.0
0x277fa  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserCredential Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::userCredential
0x277ff  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserCredential::get_UserName()
0x27804  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27809  ldloc.s  9
0x2780b  ldstr    aScope_0// "scope"
0x27810  ldstr    aOpenid// "openid"
0x27815  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2781a  ldloc.s  9
0x2781c  ldstr    aPassword// "password"
0x27821  ldloc.1
0x27822  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x27827  ldloc.s  9
0x27829  stloc.3
0x2782a  ldstr    asc_85012// "&"
0x2782f  ldloc.3
0x27830  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::CS$<>9__CachedAnonymousMethodDelegate9
0x27835  brtrue.s loc_27848
0x27837  ldnull
0x27838  ldftn    string Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::<GetBearerTokenForUserAuthentication>b__7(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> keyValuePair)
0x2783e  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0x27843  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::CS$<>9__CachedAnonymousMethodDelegate9
0x27848  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::CS$<>9__CachedAnonymousMethodDelegate9
0x2784d  call     T0x2B00000E
0x27852  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x27857  stloc.s  4
0x27859  ldarg.0
0x2785a  ldloc.0
0x2785b  ldsfld   class [mscorlib]System.Action`1<class [System]System.Net.HttpWebRequest> Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::CS$<>9__CachedAnonymousMethodDelegatea
0x27860  brtrue.s loc_27873
0x27862  ldnull
0x27863  ldftn    void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::<GetBearerTokenForUserAuthentication>b__8(class [System]System.Net.HttpWebRequest request)
0x27869  newobj   instance void class [mscorlib]System.Action`1<class [System]System.Net.HttpWebRequest>::.ctor(object, native int)
0x2786e  stsfld   class [mscorlib]System.Action`1<class [System]System.Net.HttpWebRequest> Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::CS$<>9__CachedAnonymousMethodDelegatea
0x27873  ldsfld   class [mscorlib]System.Action`1<class [System]System.Net.HttpWebRequest> Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::CS$<>9__CachedAnonymousMethodDelegatea
0x27878  ldloc.s  4
0x2787a  call     instance class [System]System.Net.HttpWebResponse Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::Post(class [System]System.Uri uri, class [mscorlib]System.Action`1<class [System]System.Net.HttpWebRequest> requestHandler, string data)
0x2787f  stloc.s  5
0x27881  ldarg.0
0x27882  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserCredential Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::userCredential
0x27887  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserCredential::get_Password()
0x2788c  brfalse.s loc_2789E
0x2788e  ldarg.0
0x2788f  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserCredential Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::userCredential
0x27894  callvirt instance class [mscorlib]System.Security.SecureString Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserCredential::get_Password()
0x27899  callvirt instance void [mscorlib]System.Security.SecureString::Clear()
0x2789e  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x278a3  stloc.s  6
0x278a5  ldloc.s  6
0x278a7  ldloc.s  5
0x278a9  call     string Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::GetTextFromResponse(class [System]System.Net.HttpWebResponse response)
0x278ae  callvirt T0x2B000031
0x278b3  stloc.s  7
0x278b5  ldloc.s  7
0x278b7  ldstr    aAccessToken// "access_token"
0x278bc  ldloca.s 8
0x278be  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x278c3  pop
0x278c4  ldarg.0
0x278c5  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserCredential Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::userCredential
0x278ca  ldc.i4.1
0x278cb  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserCredential::set_Verified(bool value)
0x278d0  ldloc.s  8
0x278d2  ret
```
