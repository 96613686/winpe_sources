# UniDrvUI::BUpgradeSoftFonts(UniDrvUI::_COMMONINFO *,_DRIVER_UPGRADE_INFO_2 *)

- ea: `0x18012942c`
- end: `0x18012966d`
- name: `?BUpgradeSoftFonts@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_DRIVER_UPGRADE_INFO_2@@@Z`
- size: `577`
- prototype: `__int64 __fastcall(HANDLE *this, struct UniDrvUI::_COMMONINFO *, struct _DRIVER_UPGRADE_INFO_2 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180116494`

## callees

- `0x180107214`
- `0x180108e2c`
- `0x1801131f4`
- `0x1801267b4`
- `0x18012942c`
- `0x18012b354`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801294a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801294a0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180129489`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180129489`
- `KERNEL32!UnmapViewOfFile` at `0x180129602`
- `KERNEL32!UnmapViewOfFile` at `0x180129602`
- `KERNEL32!CloseHandle` at `0x18012962f`
- `KERNEL32!CloseHandle` at `0x18012962f`
- `WINSPOOL!GetPrinterDataW` at `0x1801294d9`
- `WINSPOOL!GetPrinterDataW` at `0x1801294d9`

## string_xrefs

- `0x1801295cd`: `Unidrvui!BUpgradeSoftFonts:BInstallSoftFont Failed.\n`
- `0x180129612`: `\nUniFont!iXtraFonts: bFICloseRead() fails\n`
- `0x180129495`: `unidrv.dll`
- `0x1801295c2`: `UnidrvUI!bFINextRead: Invalid FF_REC_HEADER ID\n`
- `0x1801295e2`: `UnidrvUI!bFINextRead: FF_HEADER has invalid ID\n`
- `0x1801295e9`: `BFINextRead`

## pseudocode

```c

```
