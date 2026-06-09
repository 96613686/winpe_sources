# StateRepository::AutoCoSid::FromSidOrCaller(void *)

- ea: `0x18008b8b4`
- end: `0x18008b952`
- name: `?FromSidOrCaller@AutoCoSid@StateRepository@@QEAAJPEAX@Z`
- size: `158`
- prototype: `__int64 __fastcall(StateRepository::AutoCoSid *this, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18008b620`
- `0x180146f40`

## callees

- `0x18000e694`
- `0x18001a9e0`
- `0x1800430a8`
- `0x18008b8b4`
- `0x18019914d`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18008b8e6`
- `ntdll!RtlLengthSid` at `0x18008b8e6`
- `ntdll!RtlValidSid` at `0x18008b8d9`
- `ntdll!RtlValidSid` at `0x18008b8d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b91e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b93e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b91e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008b93e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008b8f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008b8f2`

## string_xrefs

- `0x18008b905`: `onecore\base\appmodel\staterepository\winrt\client\lib\AutoCoSid.hpp`

## pseudocode

```c

```
