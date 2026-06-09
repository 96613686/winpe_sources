# <>c__DisplayClass1::<get_AuthInfo>b__0

- ea: `0x378b0`
- end: `0x37b09`
- name: `<>c__DisplayClass1::<get_AuthInfo>b__0`
- size: `601`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6e70`
- `0xe010`
- `0x378b0`

## string_xrefs

- `0x378de`: `Error when trying to get Authentication from web.config: {0}`
- `0x3793b`: `system.webServer/security/authentication/windowsAuthentication`
- `0x3794d`: `system.webServer/security/authentication/windowsAuthentication`
- `0x37a0a`: `system.webServer/security/authentication/anonymousAuthentication`
- `0x37a1c`: `system.webServer/security/authentication/anonymousAuthentication`
- `0x37a4c`: `system.webServer/security/authentication/basicAuthentication`
- `0x37a5e`: `system.webServer/security/authentication/basicAuthentication`
- `0x37a8e`: `system.webServer/security/authentication/digestAuthentication`
- `0x37aa0`: `system.webServer/security/authentication/digestAuthentication`

## pseudocode

```c

```

## disassembly

```asm
0x378b0  ldc.i4.1
0x378b1  stloc.0
0x378b2  ldstr    aSystemWebAuthe// "system.web/authentication"
0x378b7  ldarg.0
0x378b8  ldfld    string <>c__DisplayClass1::virtualPath
0x378bd  call     object [System.Web]System.Web.Configuration.WebConfigurationManager::GetSection(string, string)
0x378c2  castclass [System.Web]System.Web.Configuration.AuthenticationSection
0x378c7  stloc.1
0x378c8  ldloc.1
0x378c9  callvirt instance valuetype [System.Web]System.Web.Configuration.AuthenticationMode [System.Web]System.Web.Configuration.AuthenticationSection::get_Mode()
0x378ce  stloc.0
0x378cf  leave.s  loc_378F9
0x378d1  stloc.2
0x378d2  ldarg.0
0x378d3  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost <>c__DisplayClass1::clientServiceHost
0x378d8  ldc.i4   0x387613
0x378dd  ldc.i4.1
0x378de  ldstr    aErrorWhenTryin// "Error when trying to get Authentication"...
0x378e3  ldc.i4.1
0x378e4  newarr   [mscorlib]System.Object
0x378e9  stloc.s  7
0x378eb  ldloc.s  7
0x378ed  ldc.i4.0
0x378ee  ldloc.2
0x378ef  stelem.ref
0x378f0  ldloc.s  7
0x378f2  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x378f7  leave.s  loc_378F9
0x378f9  ldarg.0
0x378fa  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost <>c__DisplayClass1::clientServiceHost
0x378ff  ldc.i4   0x387614
0x37904  ldc.i4.2
0x37905  ldstr    aAuthentication// "AuthenticationMode={0}"
0x3790a  ldc.i4.1
0x3790b  newarr   [mscorlib]System.Object
0x37910  stloc.s  8
0x37912  ldloc.s  8
0x37914  ldc.i4.0
0x37915  ldloc.0
0x37916  box      [System.Web]System.Web.Configuration.AuthenticationMode
0x3791b  stelem.ref
0x3791c  ldloc.s  8
0x3791e  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x37923  ldarg.0
0x37924  ldfld    class AuthenticationInfo <>c__DisplayClass1::authInfo
0x37929  ldloc.0
0x3792a  stfld    valuetype [System.Web]System.Web.Configuration.AuthenticationMode AuthenticationInfo::AuthMode
0x3792f  ldarg.0
0x37930  ldfld    string <>c__DisplayClass1::siteName
0x37935  ldarg.0
0x37936  ldfld    string <>c__DisplayClass1::virtualPath
0x3793b  ldstr    aSystemWebserve// "system.webServer/security/authenticatio"...
0x37940  call     class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationSection [Microsoft.Web.Administration]Microsoft.Web.Administration.WebConfigurationManager::GetSection(string, string, string)
0x37945  stloc.3
0x37946  ldarg.0
0x37947  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost <>c__DisplayClass1::clientServiceHost
0x3794c  ldloc.3
0x3794d  ldstr    aSystemWebserve// "system.webServer/security/authenticatio"...
0x37952  ldstr    aEnabled// "enabled"
0x37957  call     bool Microsoft.SharePoint.Client.ClientRequestServiceBehaviorAttribute::CheckConfigurationSectionBoolAttribute(class Microsoft.SharePoint.Client.ClientServiceHost clientServiceHost, class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationSection section, string sectionName, string attrName)
0x3795c  brfalse  loc_379FE
0x37961  ldarg.0
0x37962  ldfld    class AuthenticationInfo <>c__DisplayClass1::authInfo
0x37967  dup
0x37968  ldfld    valuetype AuthFlags AuthenticationInfo::AuthFlags
0x3796d  ldc.i4.4
0x3796e  or
0x3796f  stfld    valuetype AuthFlags AuthenticationInfo::AuthFlags
0x37974  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x37979  stloc.s  4
0x3797b  ldloc.3
0x3797c  ldstr    aProviders// "providers"
0x37981  callvirt instance class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElementCollection [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElement::GetCollection(string)
0x37986  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElementCollectionBase`1<class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElement>::GetEnumerator()
0x3798b  stloc.s  9
0x3798d  br.s     loc_379D5
0x3798f  ldloc.s  9
0x37991  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElement>::get_Current()
0x37996  stloc.s  5
0x37998  ldloc.s  4
0x3799a  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x3799f  ldc.i4.0
0x379a0  ble.s    loc_379AF
0x379a2  ldloc.s  4
0x379a4  ldstr    asc_3F8FA// ","
0x379a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x379ae  pop
0x379af  ldloc.s  5
0x379b1  ldstr    aValue// "value"
0x379b6  callvirt instance object [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationElement::get_Item(string)
0x379bb  isinst   [mscorlib]System.String
0x379c0  stloc.s  6
0x379c2  ldloc.s  6
0x379c4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x379c9  brtrue.s loc_379D5
0x379cb  ldloc.s  4
0x379cd  ldloc.s  6
0x379cf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x379d4  pop
0x379d5  ldloc.s  9
0x379d7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x379dc  brtrue.s loc_3798F
0x379de  leave.s  loc_379EC
0x379e0  ldloc.s  9
0x379e2  brfalse.s loc_379EB
0x379e4  ldloc.s  9
0x379e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x379eb  endfinally
0x379ec  ldarg.0
0x379ed  ldfld    class AuthenticationInfo <>c__DisplayClass1::authInfo
0x379f2  ldloc.s  4
0x379f4  callvirt instance string [mscorlib]System.Object::ToString()
0x379f9  stfld    string AuthenticationInfo::NTAuthenticationProviders
0x379fe  ldarg.0
0x379ff  ldfld    string <>c__DisplayClass1::siteName
0x37a04  ldarg.0
0x37a05  ldfld    string <>c__DisplayClass1::virtualPath
0x37a0a  ldstr    aSystemWebserve_0// "system.webServer/security/authenticatio"...
0x37a0f  call     class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationSection [Microsoft.Web.Administration]Microsoft.Web.Administration.WebConfigurationManager::GetSection(string, string, string)
0x37a14  stloc.3
0x37a15  ldarg.0
0x37a16  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost <>c__DisplayClass1::clientServiceHost
0x37a1b  ldloc.3
0x37a1c  ldstr    aSystemWebserve_0// "system.webServer/security/authenticatio"...
0x37a21  ldstr    aEnabled// "enabled"
0x37a26  call     bool Microsoft.SharePoint.Client.ClientRequestServiceBehaviorAttribute::CheckConfigurationSectionBoolAttribute(class Microsoft.SharePoint.Client.ClientServiceHost clientServiceHost, class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationSection section, string sectionName, string attrName)
0x37a2b  brfalse.s loc_37A40
0x37a2d  ldarg.0
0x37a2e  ldfld    class AuthenticationInfo <>c__DisplayClass1::authInfo
0x37a33  dup
0x37a34  ldfld    valuetype AuthFlags AuthenticationInfo::AuthFlags
0x37a39  ldc.i4.1
0x37a3a  or
0x37a3b  stfld    valuetype AuthFlags AuthenticationInfo::AuthFlags
0x37a40  ldarg.0
0x37a41  ldfld    string <>c__DisplayClass1::siteName
0x37a46  ldarg.0
0x37a47  ldfld    string <>c__DisplayClass1::virtualPath
0x37a4c  ldstr    aSystemWebserve_1// "system.webServer/security/authenticatio"...
0x37a51  call     class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationSection [Microsoft.Web.Administration]Microsoft.Web.Administration.WebConfigurationManager::GetSection(string, string, string)
0x37a56  stloc.3
0x37a57  ldarg.0
0x37a58  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost <>c__DisplayClass1::clientServiceHost
0x37a5d  ldloc.3
0x37a5e  ldstr    aSystemWebserve_1// "system.webServer/security/authenticatio"...
0x37a63  ldstr    aEnabled// "enabled"
0x37a68  call     bool Microsoft.SharePoint.Client.ClientRequestServiceBehaviorAttribute::CheckConfigurationSectionBoolAttribute(class Microsoft.SharePoint.Client.ClientServiceHost clientServiceHost, class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationSection section, string sectionName, string attrName)
0x37a6d  brfalse.s loc_37A82
0x37a6f  ldarg.0
0x37a70  ldfld    class AuthenticationInfo <>c__DisplayClass1::authInfo
0x37a75  dup
0x37a76  ldfld    valuetype AuthFlags AuthenticationInfo::AuthFlags
0x37a7b  ldc.i4.2
0x37a7c  or
0x37a7d  stfld    valuetype AuthFlags AuthenticationInfo::AuthFlags
0x37a82  ldarg.0
0x37a83  ldfld    string <>c__DisplayClass1::siteName
0x37a88  ldarg.0
0x37a89  ldfld    string <>c__DisplayClass1::virtualPath
0x37a8e  ldstr    aSystemWebserve_2// "system.webServer/security/authenticatio"...
0x37a93  call     class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationSection [Microsoft.Web.Administration]Microsoft.Web.Administration.WebConfigurationManager::GetSection(string, string, string)
0x37a98  stloc.3
0x37a99  ldarg.0
0x37a9a  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost <>c__DisplayClass1::clientServiceHost
0x37a9f  ldloc.3
0x37aa0  ldstr    aSystemWebserve_2// "system.webServer/security/authenticatio"...
0x37aa5  ldstr    aEnabled// "enabled"
0x37aaa  call     bool Microsoft.SharePoint.Client.ClientRequestServiceBehaviorAttribute::CheckConfigurationSectionBoolAttribute(class Microsoft.SharePoint.Client.ClientServiceHost clientServiceHost, class [Microsoft.Web.Administration]Microsoft.Web.Administration.ConfigurationSection section, string sectionName, string attrName)
0x37aaf  brfalse.s loc_37AC5
0x37ab1  ldarg.0
0x37ab2  ldfld    class AuthenticationInfo <>c__DisplayClass1::authInfo
0x37ab7  dup
0x37ab8  ldfld    valuetype AuthFlags AuthenticationInfo::AuthFlags
0x37abd  ldc.i4.s 0x10
0x37abf  or
0x37ac0  stfld    valuetype AuthFlags AuthenticationInfo::AuthFlags
0x37ac5  ldarg.0
0x37ac6  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost <>c__DisplayClass1::clientServiceHost
0x37acb  ldc.i4   0x387615
0x37ad0  ldc.i4.2
0x37ad1  ldstr    aAuthflags0Ntau// "AuthFlags={0}, NTAuthenticationProvider"...
0x37ad6  ldc.i4.2
0x37ad7  newarr   [mscorlib]System.Object
0x37adc  stloc.s  0xA
0x37ade  ldloc.s  0xA
0x37ae0  ldc.i4.0
0x37ae1  ldarg.0
0x37ae2  ldfld    class AuthenticationInfo <>c__DisplayClass1::authInfo
0x37ae7  ldfld    valuetype AuthFlags AuthenticationInfo::AuthFlags
0x37aec  box      AuthFlags
0x37af1  stelem.ref
0x37af2  ldloc.s  0xA
0x37af4  ldc.i4.1
0x37af5  ldarg.0
0x37af6  ldfld    class AuthenticationInfo <>c__DisplayClass1::authInfo
0x37afb  ldfld    string AuthenticationInfo::NTAuthenticationProviders
0x37b00  stelem.ref
0x37b01  ldloc.s  0xA
0x37b03  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x37b08  ret
```
