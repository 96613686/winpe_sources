# Microsoft.ReportingServices.Hybrid.OAuth.CatalogAadSessionCache::RemoveServiceTokenFromCache

- ea: `0x364c0`
- end: `0x364d2`
- name: `Microsoft.ReportingServices.Hybrid.OAuth.CatalogAadSessionCache::RemoveServiceTokenFromCache`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x37080`

## string_xrefs

- `0x364c6`: `AADAuthToken`

## pseudocode

```c

```

## disassembly

```asm
0x364c0  ldarg.0
0x364c1  ldfld    class Microsoft.ReportingServices.Rendering.Hybrid.IUserSettingsAccessor Microsoft.ReportingServices.Hybrid.OAuth.CatalogAadSessionCache::m_settingsAccessor
0x364c6  ldstr    aAadauthtoken// "AADAuthToken"
0x364cb  ldnull
0x364cc  callvirt instance void Microsoft.ReportingServices.Rendering.Hybrid.IUserSettingsAccessor::SetUserSetting(string name, string value)
0x364d1  ret
```
