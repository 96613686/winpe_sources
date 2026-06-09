# Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemovePowerBIRegistration

- ea: `0x4740`
- end: `0x47a4`
- name: `Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemovePowerBIRegistration`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x43a0`

## callees

- `0x4730`

## string_xrefs

- `0x4799`: `TokenUrl`

## pseudocode

```c

```

## disassembly

```asm
0x4740  ldarg.0
0x4741  ldstr    aAppobjectid// "AppObjectId"
0x4746  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string key)
0x474b  ldarg.0
0x474c  ldstr    aAuthorizationu// "AuthorizationUrl"
0x4751  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string key)
0x4756  ldarg.0
0x4757  ldstr    aClientid// "ClientId"
0x475c  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string key)
0x4761  ldarg.0
0x4762  ldstr    aClientsecret// "ClientSecret"
0x4767  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string key)
0x476c  ldarg.0
0x476d  ldstr    aRedirecturls// "RedirectUrls"
0x4772  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string key)
0x4777  ldarg.0
0x4778  ldstr    aResourceurl// "ResourceUrl"
0x477d  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string key)
0x4782  ldarg.0
0x4783  ldstr    aTenantid// "TenantId"
0x4788  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string key)
0x478d  ldarg.0
0x478e  ldstr    aTenantname// "TenantName"
0x4793  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string key)
0x4798  ldarg.0
0x4799  ldstr    aTokenurl// "TokenUrl"
0x479e  call     void Microsoft.BIServer.HostingEnvironment.HostingInfo.CatalogConfigUpgrade::RemoveSetting(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration, string key)
0x47a3  ret
```
