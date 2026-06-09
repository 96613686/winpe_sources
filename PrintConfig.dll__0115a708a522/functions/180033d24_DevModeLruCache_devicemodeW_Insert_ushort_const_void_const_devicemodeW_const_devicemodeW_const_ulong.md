# DevModeLruCache<_devicemodeW>::Insert(ushort const *,void * const,_devicemodeW const *,_devicemodeW const *,ulong)

- ea: `0x180033d24`
- end: `0x18003407d`
- name: `?Insert@?$DevModeLruCache@U_devicemodeW@@@@QEAAJPEBGQEAXPEBU_devicemodeW@@2K@Z`
- size: `857`
- prototype: `__int64 __fastcall(unsigned int *, WCHAR *, void *, unsigned __int16 *, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18003411c`

## callees

- `0x180003430`
- `0x180003bec`
- `0x180003c20`
- `0x180004564`
- `0x18000f830`
- `0x18000fa4c`
- `0x180019618`
- `0x1800339b4`
- `0x180033d24`
- `0x18003421c`
- `0x1801502f4`
- `0x18015a10c`
- `0x18015a3ec`
- `0x1801b56bc`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180033dc5`
- `KERNEL32!LeaveCriticalSection` at `0x180034016`
- `KERNEL32!LeaveCriticalSection` at `0x180034034`
- `KERNEL32!LeaveCriticalSection` at `0x180033dc5`
- `KERNEL32!LeaveCriticalSection` at `0x180034016`
- `KERNEL32!LeaveCriticalSection` at `0x180034034`
- `KERNEL32!EnterCriticalSection` at `0x180033d5d`
- `KERNEL32!EnterCriticalSection` at `0x180033d5d`
- `KERNEL32!GetTickCount64` at `0x180033f50`
- `KERNEL32!GetTickCount64` at `0x180033f50`
- `WINSPOOL!GetPrinterDataW` at `0x180033e67`
- `WINSPOOL!GetPrinterDataW` at `0x180033e67`
- `WINSPOOL!ClosePrinter` at `0x180033e8c`
- `WINSPOOL!ClosePrinter` at `0x180033e8c`

## string_xrefs

- `0x180033e35`: `V4_Config_Cache_ChangeID_Connection`
- `0x180033e2e`: `V4_Config_Cache_ChangeID_Local`

## pseudocode

```c

```
