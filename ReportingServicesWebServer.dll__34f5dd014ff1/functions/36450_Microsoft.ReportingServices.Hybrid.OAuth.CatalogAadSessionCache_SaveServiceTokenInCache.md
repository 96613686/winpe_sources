# Microsoft.ReportingServices.Hybrid.OAuth.CatalogAadSessionCache::SaveServiceTokenInCache

- ea: `0x36450`
- end: `0x3646b`
- name: `Microsoft.ReportingServices.Hybrid.OAuth.CatalogAadSessionCache::SaveServiceTokenInCache`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x36450`
- `0x36960`
- `0x37080`

## string_xrefs

- `0x3645a`: `AADAuthToken`

## pseudocode

```c

```

## disassembly

```asm
0x36450  ldarg.1
0x36451  brtrue.s loc_36454
0x36453  ret
0x36454  ldarg.0
0x36455  ldfld    class Microsoft.ReportingServices.Rendering.Hybrid.IUserSettingsAccessor Microsoft.ReportingServices.Hybrid.OAuth.CatalogAadSessionCache::m_settingsAccessor
0x3645a  ldstr    aAadauthtoken// "AADAuthToken"
0x3645f  ldarg.1
0x36460  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::ToJson()
0x36465  callvirt instance void Microsoft.ReportingServices.Rendering.Hybrid.IUserSettingsAccessor::SetUserSetting(string name, string value)
0x3646a  ret
```
