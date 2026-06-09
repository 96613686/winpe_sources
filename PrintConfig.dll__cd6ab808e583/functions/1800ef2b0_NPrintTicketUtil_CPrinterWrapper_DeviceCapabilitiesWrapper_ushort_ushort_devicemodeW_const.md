# NPrintTicketUtil::CPrinterWrapper::DeviceCapabilitiesWrapper(ushort,ushort *,_devicemodeW const *)

- ea: `0x1800ef2b0`
- end: `0x1800ef3fa`
- name: `?DeviceCapabilitiesWrapper@CPrinterWrapper@NPrintTicketUtil@@AEAAHGPEAGPEBU_devicemodeW@@@Z`
- size: `330`
- prototype: `int(NPrintTicketUtil::CPrinterWrapper *__hidden this, unsigned __int16, unsigned __int16 *, const struct _devicemodeW *)`
- caller_count: `16`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e7fcc`
- `0x1800eb5d0`
- `0x1800eb600`
- `0x1800eb630`
- `0x1800eb660`
- `0x1800eb690`
- `0x1800ecb10`
- `0x1800f2b90`
- `0x1800f2ce0`
- `0x1800f2e90`
- `0x1800f34e0`
- `0x1800f3700`
- `0x1800f5e00`
- `0x180100b00`
- `0x180100b40`
- `0x180101980`

## callees

- `0x1800ef2b0`
- `0x1801adb4c`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800ef308`
- `KERNEL32!GetProcAddress` at `0x1800ef308`
- `KERNEL32!FreeLibrary` at `0x1800ef323`
- `KERNEL32!FreeLibrary` at `0x1800ef323`
- `KERNEL32!GetLastError` at `0x1800ef317`
- `KERNEL32!GetLastError` at `0x1800ef333`
- `KERNEL32!GetLastError` at `0x1800ef317`
- `KERNEL32!GetLastError` at `0x1800ef333`
- `KERNEL32!LoadLibraryExW` at `0x1800ef2ef`
- `KERNEL32!LoadLibraryExW` at `0x1800ef2ef`
- `WINSPOOL!DeviceCapabilitiesW` at `0x1800ef3df`
- `WINSPOOL!DeviceCapabilitiesW` at `0x1800ef3df`
- `prntvpt!__imp_PTReleaseMemory` at `0x1800ef3bc`
- `prntvpt!__imp_PTReleaseMemory` at `0x1800ef3bc`

## string_xrefs

- `0x1800ef2e2`: `PrintCoreConfig.dll`

## pseudocode

```c

```
