# Microsoft::Diagnostics::Utils::Registry::RegisterForValueChangeNotifications(void *,HKEY__ *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ulong)

- ea: `0x18010ed98`
- end: `0x18010eef9`
- name: `?RegisterForValueChangeNotifications@Registry@Utils@Diagnostics@Microsoft@@SAJPEAXPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `353`
- prototype: `__int64 __fastcall(HANDLE hEvent, HKEY hKey)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18010ebf4`
- `0x18010ef00`

## callees

- `0x180020db8`
- `0x18002df00`
- `0x18008abf4`
- `0x18010ed98`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18010ee67`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18010ee67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010eebc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010eebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010eea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010eea9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010eeb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010eeb4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18010ee36`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18010ee36`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18010ee56`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18010ee56`

## string_xrefs

- `0x18010eed2`: `onecore\base\telemetry\utc\include\RegistryUtils.h`

## pseudocode

```c

```
