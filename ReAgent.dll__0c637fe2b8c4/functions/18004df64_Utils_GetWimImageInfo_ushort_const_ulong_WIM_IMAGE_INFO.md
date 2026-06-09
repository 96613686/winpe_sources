# Utils::GetWimImageInfo(ushort const *,ulong,_WIM_IMAGE_INFO *)

- ea: `0x18004df64`
- end: `0x18004e0bf`
- name: `?GetWimImageInfo@Utils@@SAKPEBGKPEAU_WIM_IMAGE_INFO@@@Z`
- size: `347`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct _WIM_IMAGE_INFO *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180020478`
- `0x18002dd30`
- `0x18002fc20`

## callees

- `0x18004df64`
- `0x18004e5c8`
- `0x18004f8d0`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004dfcf`
- `KERNEL32!GetLastError` at `0x18004e02c`
- `KERNEL32!GetLastError` at `0x18004dfcf`
- `KERNEL32!GetLastError` at `0x18004e02c`
- `WIMGAPI!WIMCloseHandle` at `0x18004e0a2`
- `WIMGAPI!WIMCloseHandle` at `0x18004e0a2`
- `WIMGAPI!WIMCreateFile` at `0x18004dfc1`
- `WIMGAPI!WIMCreateFile` at `0x18004dfc1`
- `WIMGAPI!WIMGetImageInformation` at `0x18004e022`
- `WIMGAPI!WIMGetImageInformation` at `0x18004e022`

## pseudocode

```c

```
