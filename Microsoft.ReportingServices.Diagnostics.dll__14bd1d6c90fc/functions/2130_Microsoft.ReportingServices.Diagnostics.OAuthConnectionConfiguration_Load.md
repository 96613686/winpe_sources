# Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::Load

- ea: `0x2130`
- end: `0x229e`
- name: `Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::Load`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4170`

## callees

- `0x17c0`
- `0x1820`
- `0x1f50`
- `0x1f70`
- `0x1f90`
- `0x1fb0`
- `0x1fd0`
- `0x1ff0`
- `0x2010`
- `0x2030`
- `0x2050`
- `0x2070`
- `0x2090`
- `0x2130`

## string_xrefs

- `0x219e`: `OAuthTokenUrl`

## pseudocode

```c

```

## disassembly

```asm
0x2130  ldarg.0
0x2131  ldarg.1
0x2132  stfld    class Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::m_properties
0x2137  newobj   instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::.ctor()
0x213c  stloc.0
0x213d  ldarg.1
0x213e  ldstr    aOauthclientid// "OAuthClientId"
0x2143  ldloca.s 0
0x2145  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::TryGetValue(var<u1>, !!T0)
0x214a  brfalse.s loc_215D
0x214c  ldarg.0
0x214d  ldloc.0
0x214e  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2153  castclass [mscorlib]System.String
0x2158  call     instance void Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::set_ClientId(string value)
0x215d  ldarg.1
0x215e  ldstr    aOauthclientsec// "OAuthClientSecret"
0x2163  ldloca.s 0
0x2165  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::TryGetValue(var<u1>, !!T0)
0x216a  brfalse.s loc_217D
0x216c  ldarg.0
0x216d  ldloc.0
0x216e  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2173  castclass [mscorlib]System.String
0x2178  call     instance void Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::set_ClientSecret(string value)
0x217d  ldarg.1
0x217e  ldstr    aOauthtenant// "OAuthTenant"
0x2183  ldloca.s 0
0x2185  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::TryGetValue(var<u1>, !!T0)
0x218a  brfalse.s loc_219D
0x218c  ldarg.0
0x218d  ldloc.0
0x218e  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2193  castclass [mscorlib]System.String
0x2198  call     instance void Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::set_TenantId(string value)
0x219d  ldarg.1
0x219e  ldstr    aOauthtokenurl// "OAuthTokenUrl"
0x21a3  ldloca.s 0
0x21a5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::TryGetValue(var<u1>, !!T0)
0x21aa  brfalse.s loc_21BD
0x21ac  ldarg.0
0x21ad  ldloc.0
0x21ae  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x21b3  castclass [mscorlib]System.String
0x21b8  call     instance void Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::set_TokenUrl(string value)
0x21bd  ldarg.1
0x21be  ldstr    aOauthauthoriza// "OAuthAuthorizationUrl"
0x21c3  ldloca.s 0
0x21c5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::TryGetValue(var<u1>, !!T0)
0x21ca  brfalse.s loc_21DD
0x21cc  ldarg.0
0x21cd  ldloc.0
0x21ce  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x21d3  castclass [mscorlib]System.String
0x21d8  call     instance void Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::set_AuthorizationUrl(string value)
0x21dd  ldarg.1
0x21de  ldstr    aOauthfederatio// "OAuthFederationMetadataUrl"
0x21e3  ldloca.s 0
0x21e5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::TryGetValue(var<u1>, !!T0)
0x21ea  brfalse.s loc_21FD
0x21ec  ldarg.0
0x21ed  ldloc.0
0x21ee  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x21f3  castclass [mscorlib]System.String
0x21f8  call     instance void Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::set_FederationMetadataUrl(string value)
0x21fd  ldarg.1
0x21fe  ldstr    aOauthresourceu// "OAuthResourceUrl"
0x2203  ldloca.s 0
0x2205  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::TryGetValue(var<u1>, !!T0)
0x220a  brfalse.s loc_221D
0x220c  ldarg.0
0x220d  ldloc.0
0x220e  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2213  castclass [mscorlib]System.String
0x2218  call     instance void Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::set_ResourceUrl(string value)
0x221d  ldarg.1
0x221e  ldstr    aOauthnativecli// "OAuthNativeClientId"
0x2223  ldloca.s 0
0x2225  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::TryGetValue(var<u1>, !!T0)
0x222a  brfalse.s loc_223D
0x222c  ldarg.0
0x222d  ldloc.0
0x222e  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2233  castclass [mscorlib]System.String
0x2238  call     instance void Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::set_NativeClientId(string value)
0x223d  ldarg.1
0x223e  ldstr    aOauthgraphurl// "OAuthGraphUrl"
0x2243  ldloca.s 0
0x2245  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::TryGetValue(var<u1>, !!T0)
0x224a  brfalse.s loc_225D
0x224c  ldarg.0
0x224d  ldloc.0
0x224e  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2253  castclass [mscorlib]System.String
0x2258  call     instance void Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::set_GraphUrl(string value)
0x225d  ldarg.1
0x225e  ldstr    aOauthsessionco// "OAuthSessionCookieName"
0x2263  ldloca.s 0
0x2265  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::TryGetValue(var<u1>, !!T0)
0x226a  brfalse.s loc_227D
0x226c  ldarg.0
0x226d  ldloc.0
0x226e  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2273  castclass [mscorlib]System.String
0x2278  call     instance void Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::set_SessionCookieName(string value)
0x227d  ldarg.1
0x227e  ldstr    aOauthlogouturl// "OAuthLogoutUrl"
0x2283  ldloca.s 0
0x2285  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo>::TryGetValue(var<u1>, !!T0)
0x228a  brfalse.s loc_229D
0x228c  ldarg.0
0x228d  ldloc.0
0x228e  callvirt instance object Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyInfo::get_Value()
0x2293  castclass [mscorlib]System.String
0x2298  call     instance void Microsoft.ReportingServices.Diagnostics.OAuthConnectionConfiguration::set_LogoutUrl(string value)
0x229d  ret
```
