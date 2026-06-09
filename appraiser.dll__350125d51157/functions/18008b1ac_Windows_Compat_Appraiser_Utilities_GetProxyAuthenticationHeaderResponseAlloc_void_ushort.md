# Windows::Compat::Appraiser::Utilities::GetProxyAuthenticationHeaderResponseAlloc(void *,ushort * *)

- ea: `0x18008b1ac`
- end: `0x18008b302`
- name: `?GetProxyAuthenticationHeaderResponseAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAXPEAPEAG@Z`
- size: `342`
- prototype: `__int64 __fastcall(HINTERNET hRequest, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800911bc`

## callees

- `0x18001a2f4`
- `0x18008b1ac`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18008b248`
- `KERNEL32!GetProcessHeap` at `0x18008b2dc`
- `KERNEL32!GetProcessHeap` at `0x18008b248`
- `KERNEL32!GetProcessHeap` at `0x18008b2dc`
- `KERNEL32!HeapAlloc` at `0x18008b259`
- `KERNEL32!HeapAlloc` at `0x18008b259`
- `KERNEL32!GetLastError` at `0x18008b1ef`
- `KERNEL32!GetLastError` at `0x18008b1fe`
- `KERNEL32!GetLastError` at `0x18008b29b`
- `KERNEL32!GetLastError` at `0x18008b1ef`
- `KERNEL32!GetLastError` at `0x18008b1fe`
- `KERNEL32!GetLastError` at `0x18008b29b`
- `KERNEL32!HeapFree` at `0x18008b2ea`
- `KERNEL32!HeapFree` at `0x18008b2ea`
- `WINHTTP!WinHttpQueryHeaders` at `0x18008b1e7`
- `WINHTTP!WinHttpQueryHeaders` at `0x18008b291`
- `WINHTTP!WinHttpQueryHeaders` at `0x18008b1e7`
- `WINHTTP!WinHttpQueryHeaders` at `0x18008b291`

## string_xrefs

- `0x18008b221`: `Windows::Compat::Appraiser::Utilities::GetProxyAuthenticationHeaderResponseAlloc`
- `0x18008b2be`: `Windows::Compat::Appraiser::Utilities::GetProxyAuthenticationHeaderResponseAlloc`

## pseudocode

```c

```
