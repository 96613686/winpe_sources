# DevModeLruCache<_devicemodeW>::Find(ushort const *,void * const,_devicemodeW const *,_devicemodeW * *)

- ea: `0x1800339b4`
- end: `0x180033d1d`
- name: `?Find@?$DevModeLruCache@U_devicemodeW@@@@QEAAJPEBGQEAXPEBU_devicemodeW@@PEAPEAU2@@Z`
- size: `873`
- prototype: `__int64 __fastcall(__int64, wchar_t *, void *, unsigned __int16 *, _QWORD *pData)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180033d24`
- `0x180034084`

## callees

- `0x180003430`
- `0x180003bec`
- `0x180004564`
- `0x18000f830`
- `0x18000fa4c`
- `0x1800339b4`
- `0x18003421c`
- `0x1801502f4`
- `0x18015a10c`
- `0x18015a3ec`
- `0x1801b56b0`
- `0x1801b56bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180033afe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180033afe`
- `KERNEL32!LeaveCriticalSection` at `0x180033a1b`
- `KERNEL32!LeaveCriticalSection` at `0x180033a6c`
- `KERNEL32!LeaveCriticalSection` at `0x180033c73`
- `KERNEL32!LeaveCriticalSection` at `0x180033cbd`
- `KERNEL32!LeaveCriticalSection` at `0x180033a1b`
- `KERNEL32!LeaveCriticalSection` at `0x180033a6c`
- `KERNEL32!LeaveCriticalSection` at `0x180033c73`
- `KERNEL32!LeaveCriticalSection` at `0x180033cbd`
- `KERNEL32!EnterCriticalSection` at `0x1800339f3`
- `KERNEL32!EnterCriticalSection` at `0x1800339f3`
- `KERNEL32!GetTickCount64` at `0x180033c1c`
- `KERNEL32!GetTickCount64` at `0x180033c1c`
- `WINSPOOL!GetPrinterDataW` at `0x180033bac`
- `WINSPOOL!GetPrinterDataW` at `0x180033bac`
- `WINSPOOL!ClosePrinter` at `0x180033bd1`
- `WINSPOOL!ClosePrinter` at `0x180033bd1`

## string_xrefs

- `0x180033b77`: `V4_Config_Cache_ChangeID_Connection`
- `0x180033b70`: `V4_Config_Cache_ChangeID_Local`

## pseudocode

```c

```
