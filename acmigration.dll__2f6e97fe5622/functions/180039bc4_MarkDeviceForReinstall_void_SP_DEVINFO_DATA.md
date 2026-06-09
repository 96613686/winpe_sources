# MarkDeviceForReinstall(void *,_SP_DEVINFO_DATA *)

- ea: `0x180039bc4`
- end: `0x180039c70`
- name: `?MarkDeviceForReinstall@@YAKPEAXPEAU_SP_DEVINFO_DATA@@@Z`
- size: `172`
- prototype: `unsigned int __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180039c78`

## callees

- `0x180039bc4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180039c56`
- `KERNEL32!GetLastError` at `0x180039c56`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180039c05`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180039c05`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x180039c4c`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x180039c4c`

## pseudocode

```c

```
