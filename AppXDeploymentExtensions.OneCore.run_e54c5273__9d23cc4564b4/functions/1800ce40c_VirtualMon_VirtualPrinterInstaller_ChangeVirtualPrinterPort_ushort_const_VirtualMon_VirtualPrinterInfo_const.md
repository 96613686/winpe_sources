# VirtualMon::VirtualPrinterInstaller::ChangeVirtualPrinterPort(ushort const *,VirtualMon::VirtualPrinterInfo const &)

- ea: `0x1800ce40c`
- end: `0x1800ce728`
- name: `?ChangeVirtualPrinterPort@VirtualPrinterInstaller@VirtualMon@@AEAAXPEBGAEBUVirtualPrinterInfo@2@@Z`
- size: `796`
- prototype: `void __fastcall(VirtualMon::VirtualPrinterInstaller *__hidden this, const unsigned __int16 *, const struct VirtualMon::VirtualPrinterInfo *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x1800af438`

## callees

- `0x180012964`
- `0x18007689c`
- `0x180076900`
- `0x1800b127c`
- `0x1800b141c`
- `0x1800b3320`
- `0x1800ca1ac`
- `0x1800ce40c`
- `0x1800ce730`
- `0x1800ce890`
- `0x1800ec2f8`
- `0x1800f0260`
- `0x1800f0a7c`
- `0x18014de84`
- `0x18018f760`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce6c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce6c0`
- `WINSPOOL!OpenPrinterW` at `0x1800ce553`
- `WINSPOOL!OpenPrinterW` at `0x1800ce553`
- `WINSPOOL!ClosePrinter` at `0x1800ce52b`
- `WINSPOOL!ClosePrinter` at `0x1800ce52b`
- `WINSPOOL!GetPrinterW` at `0x1800ce589`
- `WINSPOOL!GetPrinterW` at `0x1800ce623`
- `WINSPOOL!GetPrinterW` at `0x1800ce589`
- `WINSPOOL!GetPrinterW` at `0x1800ce623`
- `WINSPOOL!SetPrinterW` at `0x1800ce6a1`
- `WINSPOOL!SetPrinterW` at `0x1800ce6a1`

## string_xrefs

- `0x1800ce45a`: `VirtualMon::VirtualPrinterInstaller::ChangeVirtualPrinterPort`
- `0x1800ce49f`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x1800ce502`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x1800ce599`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x1800ce5da`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x1800ce66d`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`

## pseudocode

```c

```
