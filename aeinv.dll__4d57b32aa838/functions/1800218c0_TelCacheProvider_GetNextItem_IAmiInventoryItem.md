# TelCacheProvider::GetNextItem(IAmiInventoryItem *)

- ea: `0x1800218c0`
- end: `0x180021b4d`
- name: `?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, struct IAmiInventoryItem *)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180012ba0`
- `0x1800217f8`
- `0x18002da48`
- `0x180031a40`
- `0x18005d200`
- `0x180060460`
- `0x1800f9c18`
- `0x1800fc078`

## callees

- `0x1800197d4`
- `0x1800218c0`
- `0x180059920`
- `0x180130010`

## import_xrefs

- `KERNEL32!SignalObjectAndWait` at `0x180021a8b`
- `KERNEL32!SignalObjectAndWait` at `0x180021a8b`
- `KERNEL32!WaitForSingleObject` at `0x180021938`
- `KERNEL32!WaitForSingleObject` at `0x180021a04`
- `KERNEL32!WaitForSingleObject` at `0x180021ad9`
- `KERNEL32!WaitForSingleObject` at `0x180021938`
- `KERNEL32!WaitForSingleObject` at `0x180021a04`
- `KERNEL32!WaitForSingleObject` at `0x180021ad9`
- `KERNEL32!SetEvent` at `0x180021a27`
- `KERNEL32!SetEvent` at `0x180021a27`
- `KERNEL32!ReleaseMutex` at `0x18002195b`
- `KERNEL32!ReleaseMutex` at `0x180021a1d`
- `KERNEL32!ReleaseMutex` at `0x18002195b`
- `KERNEL32!ReleaseMutex` at `0x180021a1d`

## string_xrefs

- `0x180021b37`: `TelCacheProvider::GetNextItem`
- `0x180021b08`: `InvCacheEnumerateItems failed. [%#x]`

## pseudocode

```c

```
