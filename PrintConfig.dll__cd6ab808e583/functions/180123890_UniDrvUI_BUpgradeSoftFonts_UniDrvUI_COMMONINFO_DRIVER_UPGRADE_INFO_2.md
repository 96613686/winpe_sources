# UniDrvUI::BUpgradeSoftFonts(UniDrvUI::_COMMONINFO *,_DRIVER_UPGRADE_INFO_2 *)

- ea: `0x180123890`
- end: `0x180123ab2`
- name: `?BUpgradeSoftFonts@UniDrvUI@@YAHPEAU_COMMONINFO@1@PEAU_DRIVER_UPGRADE_INFO_2@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(UniDrvUI *__hidden this, struct UniDrvUI::_COMMONINFO *, struct _DRIVER_UPGRADE_INFO_2 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180111520`

## callees

- `0x180102674`
- `0x18010427c`
- `0x18010e54c`
- `0x180120f44`
- `0x180123890`
- `0x1801256f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801238fe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801238fe`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801238ed`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801238ed`
- `KERNEL32!UnmapViewOfFile` at `0x180123a54`
- `KERNEL32!UnmapViewOfFile` at `0x180123a54`
- `KERNEL32!CloseHandle` at `0x180123a7b`
- `KERNEL32!CloseHandle` at `0x180123a7b`
- `WINSPOOL!GetPrinterDataW` at `0x180123931`
- `WINSPOOL!GetPrinterDataW` at `0x180123931`

## string_xrefs

- `0x180123a1f`: `Unidrvui!BUpgradeSoftFonts:BInstallSoftFont Failed.\n`
- `0x1801238f3`: `unidrv.dll`
- `0x180123a5e`: `\nUniFont!iXtraFonts: bFICloseRead() fails\n`
- `0x180123a14`: `UnidrvUI!bFINextRead: Invalid FF_REC_HEADER ID\n`
- `0x180123a34`: `UnidrvUI!bFINextRead: FF_HEADER has invalid ID\n`
- `0x180123a3b`: `BFINextRead`

## pseudocode

```c

```
