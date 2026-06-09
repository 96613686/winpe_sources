# LicenseProxyService::DoRequestSubscriptions(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,char const *,Microsoft::WRL::ComPtr<ILicenseIdentityInternalSnapshot> const &,web::json::value const &,HttpResponse *,web::json::value *)

- ea: `0x18005e044`
- end: `0x18005e259`
- name: `?DoRequestSubscriptions@LicenseProxyService@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBDAEBV?$ComPtr@UILicenseIdentityInternalSnapshot@@@WRL@Microsoft@@AEBVvalue@json@web@@PEAVHttpResponse@@PEAV789@@Z`
- size: `533`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, HttpResponse *, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005f600`

## callees

- `0x180006b08`
- `0x180006b38`
- `0x180006cec`
- `0x180007704`
- `0x180007c78`
- `0x18000a0e4`
- `0x180013b50`
- `0x180036394`
- `0x180040b08`
- `0x1800593bc`
- `0x18005e044`
- `0x18005e260`
- `0x18005eeb0`
- `0x18005f014`
- `0x180075e60`
- `0x18007b370`
- `0x18009bb4c`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005e0fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005e1b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005e0fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005e1b4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005e17f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005e17f`

## string_xrefs

- `0x18005e0df`: `LicenseProxyService::DoRequestSubscriptions`

## pseudocode

```c

```
