# NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)

- ea: `0x1800f3c40`
- end: `0x1800f3db9`
- name: `?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z`
- size: `377`
- prototype: `int __fastcall(NPrintTicketUtil::CPrinterWrapper *this, WORD, unsigned __int16 *, const struct _devicemodeW *pDevMode)`
- caller_count: `16`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800ec834`
- `0x1800efea0`
- `0x1800efed0`
- `0x1800eff00`
- `0x1800eff30`
- `0x1800eff60`
- `0x1800f1430`
- `0x1800f7600`
- `0x1800f7760`
- `0x1800f7920`
- `0x1800f7fb0`
- `0x1800f81e0`
- `0x1800fa9e0`
- `0x180105670`
- `0x1801056b0`
- `0x1801064f0`

## callees

- `0x1800f3c40`
- `0x1801b56bc`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800f3ca2`
- `KERNEL32!GetProcAddress` at `0x1800f3ca2`
- `KERNEL32!FreeLibrary` at `0x1800f3cc9`
- `KERNEL32!FreeLibrary` at `0x1800f3cc9`
- `KERNEL32!GetLastError` at `0x1800f3cb7`
- `KERNEL32!GetLastError` at `0x1800f3cdf`
- `KERNEL32!GetLastError` at `0x1800f3cb7`
- `KERNEL32!GetLastError` at `0x1800f3cdf`
- `KERNEL32!LoadLibraryExW` at `0x1800f3c83`
- `KERNEL32!LoadLibraryExW` at `0x1800f3c83`
- `WINSPOOL!DeviceCapabilitiesW` at `0x1800f3d97`
- `WINSPOOL!DeviceCapabilitiesW` at `0x1800f3d97`
- `prntvpt!__imp_PTReleaseMemory` at `0x1800f3d6e`
- `prntvpt!__imp_PTReleaseMemory` at `0x1800f3d6e`

## string_xrefs

- `0x1800f3c76`: `PrintCoreConfig.dll`

## pseudocode

```c

```
