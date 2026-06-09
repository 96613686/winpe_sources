# PrintConfig::IppPdcProvider::GetPdcOmForPrinter(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *)

- ea: `0x1800700e0`
- end: `0x1800703e0`
- name: `?GetPdcOmForPrinter@IppPdcProvider@PrintConfig@@SA?AV?$shared_ptr@VPrintDeviceCapabilities@PrintDeviceCapabilitiesOM@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAX@Z`
- size: `768`
- prototype: `_QWORD *__fastcall(_QWORD *, wchar_t *, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020550`
- `0x18015ffc0`

## callees

- `0x180010140`
- `0x180019410`
- `0x180019bf8`
- `0x180020c8c`
- `0x1800412a4`
- `0x18006998c`
- `0x1800700e0`
- `0x1800703e8`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18007025f`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18007025f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007015d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007024d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007015d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007024d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180070213`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800703a2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180070213`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800703a2`
- `IppCommon!IppGetPdcXmlObject` at `0x18007013b`
- `IppCommon!IppGetPdcXmlObject` at `0x18007013b`

## string_xrefs

- `0x1800703ce`: `printscan\print\drivers\usermode\config\printconfig\ipppdcprovider.cpp`

## pseudocode

```c

```
