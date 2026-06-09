# GetComponentPathEx(ushort const *,ushort const *,ushort const *,tagMSIINSTALLCONTEXT,ushort *,ulong *)

- ea: `0x18006431c`
- end: `0x18006490e`
- name: `?GetComponentPathEx@@YA?AW4tagINSTALLSTATE@@PEBG00W4tagMSIINSTALLCONTEXT@@PEAGPEAK@Z`
- size: `1522`
- prototype: `enum tagINSTALLSTATE __usercall@<eax>(LPCWSTR lpString@<rcx>, LPCWSTR@<rdx>, wchar_t *String1@<r8>, enum tagMSIINSTALLCONTEXT@<r9d>, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180065330`
- `0x18019ddd0`

## callees

- `0x180017a84`
- `0x180025560`
- `0x18006431c`
- `0x180064914`
- `0x18006499c`
- `0x180064a10`
- `0x180064a78`
- `0x180064fd8`
- `0x180065070`
- `0x180065230`
- `0x1800652bc`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x1800648c6`
- `KERNEL32!GlobalAlloc` at `0x1800648c6`
- `KERNEL32!lstrlenW` at `0x18006438c`
- `KERNEL32!lstrlenW` at `0x180064461`
- `KERNEL32!lstrlenW` at `0x18006438c`
- `KERNEL32!lstrlenW` at `0x180064461`
- `KERNEL32!GlobalFree` at `0x180064666`
- `KERNEL32!GlobalFree` at `0x180064672`
- `KERNEL32!GlobalFree` at `0x1800648e4`
- `KERNEL32!GlobalFree` at `0x180064666`
- `KERNEL32!GlobalFree` at `0x180064672`
- `KERNEL32!GlobalFree` at `0x1800648e4`

## string_xrefs

- `0x18006441e`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`
- `0x1800644cd`: `Software\Microsoft\Windows\CurrentVersion\Installer\UserData`

## pseudocode

```c

```
