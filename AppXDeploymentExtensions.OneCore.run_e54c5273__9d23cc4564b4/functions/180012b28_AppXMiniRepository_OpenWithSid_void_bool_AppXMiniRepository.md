# AppXMiniRepository::OpenWithSid(void *,bool,AppXMiniRepository * *)

- ea: `0x180012b28`
- end: `0x18001303b`
- name: `?OpenWithSid@AppXMiniRepository@@SAJPEAX_NPEAPEAV1@@Z`
- size: `1299`
- prototype: `__int64 __fastcall(PSID Sid, bool, struct AppXMiniRepository **)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bc90`

## callees

- `0x18000e6e0`
- `0x180012b28`
- `0x1800138e0`
- `0x180016760`
- `0x18005c97c`
- `0x18005ded4`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800a5970`
- `0x1800b6394`
- `0x1800f0700`
- `0x1800f17bc`
- `0x1800fc0ec`
- `0x1800fc211`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013006`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012e92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013006`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180012b80`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180012b80`
- `ntdll!RtlFreeUnicodeString` at `0x180012ba9`
- `ntdll!RtlFreeUnicodeString` at `0x180012ba9`

## string_xrefs

- `0x18001301b`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012ea4`: `onecore\base\appmodel\common\sidhelper.cpp`
- `0x180012f60`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x180012f05`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180012fc4`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180012fd8`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c

```
