# Microsoft.ReportingServices.Hybrid.OAuth.CatalogAadSessionCache::GetServiceTokenFromCache

- ea: `0x36470`
- end: `0x364be`
- name: `Microsoft.ReportingServices.Hybrid.OAuth.CatalogAadSessionCache::GetServiceTokenFromCache`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x36470`
- `0x369c0`
- `0x37070`

## string_xrefs

- `0x36476`: `AADAuthToken`
- `0x364a3`: `Exception when trying to get ServiceToken from cache: `

## pseudocode

```c

```

## disassembly

```asm
0x36470  ldarg.0
0x36471  ldfld    class Microsoft.ReportingServices.Rendering.Hybrid.IUserSettingsAccessor Microsoft.ReportingServices.Hybrid.OAuth.CatalogAadSessionCache::m_settingsAccessor
0x36476  ldstr    aAadauthtoken// "AADAuthToken"
0x3647b  callvirt instance string Microsoft.ReportingServices.Rendering.Hybrid.IUserSettingsAccessor::GetUserSettings(string property)
0x36480  stloc.0
0x36481  ldloc.0
0x36482  brtrue.s loc_36488
0x36484  ldnull
0x36485  stloc.1
0x36486  leave.s  loc_364BC
0x36488  ldloc.0
0x36489  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3648e  brtrue.s loc_36499
0x36490  ldloc.0
0x36491  call     class Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken Microsoft.ReportingServices.Hybrid.OAuth.ServiceToken::FromJson(string json)
0x36496  stloc.1
0x36497  leave.s  loc_364BC
0x36499  ldnull
0x3649a  stloc.1
0x3649b  leave.s  loc_364BC
0x3649d  stloc.2
0x3649e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x364a3  ldstr    aExceptionWhenT// "Exception when trying to get ServiceTok"...
0x364a8  ldloc.2
0x364a9  callvirt instance string [mscorlib]System.Object::ToString()
0x364ae  call     string [mscorlib]System.String::Concat(string, string)
0x364b3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string)
0x364b8  ldnull
0x364b9  stloc.1
0x364ba  leave.s  loc_364BC
0x364bc  ldloc.1
0x364bd  ret
```
