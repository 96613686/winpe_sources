# CapabilityAccessFactory::CreateWithProcessId(HSTRING__ *,HSTRING__ *,uint,uint,Windows::Internal::CapabilityAccess::ICapabilityAccess * *)

- ea: `0x18008a280`
- end: `0x18008a424`
- name: `?CreateWithProcessId@CapabilityAccessFactory@@UEAAJPEAUHSTRING__@@0IIPEAPEAUICapabilityAccess@CapabilityAccess@Internal@Windows@@@Z`
- size: `420`
- prototype: `int(CapabilityAccessFactory *__hidden this, HSTRING, HSTRING, unsigned int, unsigned int, struct Windows::Internal::CapabilityAccess::ICapabilityAccess **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x180017bc4`
- `0x18001ab9c`
- `0x18001d00c`
- `0x180089c24`
- `0x18008a280`
- `0x18008a640`
- `0x18008a680`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a33b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a349`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a33b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008a349`

## string_xrefs

- `0x18008a2f9`: `onecore\base\devices\cam\winrt\lib\capabilityaccessfactory.cpp`
- `0x18008a356`: `onecore\base\devices\cam\winrt\lib\capabilityaccessfactory.cpp`
- `0x18008a412`: `onecore\base\devices\cam\winrt\lib\capabilityaccessfactory.cpp`
- `0x18008a37f`: `Attempt to call CreateWithProcessId cross-container denied: user(%ws), cap(%ws), pid(%u), tid(%u)`

## pseudocode

```c

```
