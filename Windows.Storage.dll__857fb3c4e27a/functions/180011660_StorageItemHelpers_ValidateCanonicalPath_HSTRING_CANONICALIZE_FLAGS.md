# StorageItemHelpers::ValidateCanonicalPath(HSTRING__ *,CANONICALIZE_FLAGS)

- ea: `0x180011660`
- end: `0x180011910`
- name: `?ValidateCanonicalPath@StorageItemHelpers@@YAJPEAUHSTRING__@@W4CANONICALIZE_FLAGS@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(HSTRING, char)`
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f7e0`
- `0x1800c6910`
- `0x1801e2240`
- `0x1802c07e4`
- `0x180306258`
- `0x180428a10`

## callees

- `0x18000cbc0`
- `0x18000cf04`
- `0x180010110`
- `0x180010220`
- `0x180011660`
- `0x1800432f0`
- `0x180129da0`
- `0x1803a4cb0`

## import_xrefs

- `ntdll!RtlAreLongPathsEnabled` at `0x1800116fe`
- `ntdll!RtlAreLongPathsEnabled` at `0x1800116fe`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800118ab`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800118ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800118c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800118c2`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180011899`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x180011899`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800118dd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x1800118dd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsValidCharW` at `0x1800117eb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsValidCharW` at `0x1800117eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001181a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001181a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800116d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180011762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800116d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180011762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800116b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800116b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800116c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800116c7`

## string_xrefs

- `0x180011739`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x1800117a7`: `onecoreuap\shell\windows.storage\dataaccess.cpp`
- `0x18001168f`: `ValidateCanonicalPath`

## pseudocode

```c

```
