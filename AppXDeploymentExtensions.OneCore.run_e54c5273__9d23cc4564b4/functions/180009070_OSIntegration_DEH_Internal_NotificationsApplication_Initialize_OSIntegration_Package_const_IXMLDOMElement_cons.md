# OSIntegration::DEH::Internal::NotificationsApplication::Initialize(OSIntegration::Package const *,IXMLDOMElement const *,APPX_CAPABILITIES,bool)

- ea: `0x180009070`
- end: `0x180009479`
- name: `?Initialize@NotificationsApplication@Internal@DEH@OSIntegration@@AEAAJPEBVPackage@4@PEBUIXMLDOMElement@@W4APPX_CAPABILITIES@@_N@Z`
- size: `1033`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::NotificationsApplication *__hidden this, const struct OSIntegration::Package *, const struct IXMLDOMElement *, enum APPX_CAPABILITIES, bool)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008e50`

## callees

- `0x180009070`
- `0x18000afcc`
- `0x18000b3bc`
- `0x18000b7d0`
- `0x18000bd80`
- `0x18000e6e0`
- `0x180012550`
- `0x1800138e0`
- `0x18001b84c`
- `0x18004b888`
- `0x18004b92c`
- `0x18004ba40`
- `0x180098bf4`
- `0x1800a5970`
- `0x1800b8300`
- `0x1800f0700`
- `0x180211010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009350`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000936a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009387`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800093a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800093c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009350`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000936a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009387`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800093a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800093c1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800092e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800092fb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800092e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800092fb`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800091da`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800091da`
- `ntdll!RtlFreeUnicodeString` at `0x18000921b`
- `ntdll!RtlFreeUnicodeString` at `0x18000921b`
- `AppXAllUserStore!DidAppSurviveOSUpgradeForUser` at `0x18000923b`
- `AppXAllUserStore!DidAppSurviveOSUpgradeForUser` at `0x18000923b`

## string_xrefs

- `0x1800091eb`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x180009263`: `*[local-name()='DefaultTile']/*[local-name()='TileUpdate']`

## pseudocode

```c

```
