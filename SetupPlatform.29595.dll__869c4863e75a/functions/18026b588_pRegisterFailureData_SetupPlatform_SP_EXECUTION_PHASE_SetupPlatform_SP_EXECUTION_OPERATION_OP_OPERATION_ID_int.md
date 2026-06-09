# pRegisterFailureData(SetupPlatform::SP_EXECUTION_PHASE,SetupPlatform::SP_EXECUTION_OPERATION,OP_OPERATION_ID,int,long,UnBCL::String *,UnBCL::String *,UnBCL::String *)

- ea: `0x18026b588`
- end: `0x18026cc08`
- name: `?pRegisterFailureData@@YAHW4SP_EXECUTION_PHASE@SetupPlatform@@W4SP_EXECUTION_OPERATION@2@W4OP_OPERATION_ID@@HJPEAVString@UnBCL@@33@Z`
- size: `5760`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180267008`

## callees

- `0x180013804`
- `0x180057dec`
- `0x18026b588`
- `0x1802dad70`
- `0x1802e2078`

## import_xrefs

- `msvcrt!_wcstoui64` at `0x18026beae`
- `msvcrt!_wcstoui64` at `0x18026bfd6`
- `msvcrt!_wcstoui64` at `0x18026c0fe`
- `msvcrt!_wcstoui64` at `0x18026c226`
- `msvcrt!_wcstoui64` at `0x18026beae`
- `msvcrt!_wcstoui64` at `0x18026bfd6`
- `msvcrt!_wcstoui64` at `0x18026c0fe`
- `msvcrt!_wcstoui64` at `0x18026c226`
- `msvcrt!_wtoi` at `0x18026b9ec`
- `msvcrt!_wtoi` at `0x18026bbde`
- `msvcrt!_wtoi` at `0x18026b9ec`
- `msvcrt!_wtoi` at `0x18026bbde`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18026be33`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18026be33`
- `ADVAPI32!RegCloseKey` at `0x18026cb67`
- `ADVAPI32!RegCloseKey` at `0x18026cb67`
- `ADVAPI32!RegSetValueExW` at `0x18026b691`
- `ADVAPI32!RegSetValueExW` at `0x18026b759`
- `ADVAPI32!RegSetValueExW` at `0x18026b7fb`
- `ADVAPI32!RegSetValueExW` at `0x18026b8a1`
- `ADVAPI32!RegSetValueExW` at `0x18026b951`
- `ADVAPI32!RegSetValueExW` at `0x18026ba17`
- `ADVAPI32!RegSetValueExW` at `0x18026bad7`
- `ADVAPI32!RegSetValueExW` at `0x18026bc0a`
- `ADVAPI32!RegSetValueExW` at `0x18026bda8`
- `ADVAPI32!RegSetValueExW` at `0x18026bedd`
- `ADVAPI32!RegSetValueExW` at `0x18026c005`
- `ADVAPI32!RegSetValueExW` at `0x18026c12d`
- `ADVAPI32!RegSetValueExW` at `0x18026c255`
- `ADVAPI32!RegSetValueExW` at `0x18026c37c`
- `ADVAPI32!RegSetValueExW` at `0x18026c4f8`
- `ADVAPI32!RegSetValueExW` at `0x18026c61f`
- `ADVAPI32!RegSetValueExW` at `0x18026c746`
- `ADVAPI32!RegSetValueExW` at `0x18026c86f`
- `ADVAPI32!RegSetValueExW` at `0x18026c992`
- `ADVAPI32!RegSetValueExW` at `0x18026cacd`
- `ADVAPI32!RegSetValueExW` at `0x18026b691`
- `ADVAPI32!RegSetValueExW` at `0x18026b759`
- `ADVAPI32!RegSetValueExW` at `0x18026b7fb`
- `ADVAPI32!RegSetValueExW` at `0x18026b8a1`
- `ADVAPI32!RegSetValueExW` at `0x18026b951`
- `ADVAPI32!RegSetValueExW` at `0x18026ba17`
- `ADVAPI32!RegSetValueExW` at `0x18026bad7`
- `ADVAPI32!RegSetValueExW` at `0x18026bc0a`
- `ADVAPI32!RegSetValueExW` at `0x18026bda8`
- `ADVAPI32!RegSetValueExW` at `0x18026bedd`
- `ADVAPI32!RegSetValueExW` at `0x18026c005`
- `ADVAPI32!RegSetValueExW` at `0x18026c12d`
- `ADVAPI32!RegSetValueExW` at `0x18026c255`
- `ADVAPI32!RegSetValueExW` at `0x18026c37c`
- `ADVAPI32!RegSetValueExW` at `0x18026c4f8`
- `ADVAPI32!RegSetValueExW` at `0x18026c61f`
- `ADVAPI32!RegSetValueExW` at `0x18026c746`
- `ADVAPI32!RegSetValueExW` at `0x18026c86f`
- `ADVAPI32!RegSetValueExW` at `0x18026c992`
- `ADVAPI32!RegSetValueExW` at `0x18026cacd`
- `ADVAPI32!RegDeleteKeyW` at `0x18026b5d1`
- `ADVAPI32!RegDeleteKeyW` at `0x18026b5d1`
- `ADVAPI32!RegCreateKeyExW` at `0x18026b612`
- `ADVAPI32!RegCreateKeyExW` at `0x18026b612`
- `ADVAPI32!RegDeleteValueW` at `0x18026b9d0`
- `ADVAPI32!RegDeleteValueW` at `0x18026b9d0`
- `KERNEL32!GetLastError` at `0x18026b6c2`
- `KERNEL32!GetLastError` at `0x18026b769`
- `KERNEL32!GetLastError` at `0x18026b80f`
- `KERNEL32!GetLastError` at `0x18026b8b5`
- `KERNEL32!GetLastError` at `0x18026b965`
- `KERNEL32!GetLastError` at `0x18026ba2b`
- `KERNEL32!GetLastError` at `0x18026baeb`
- `KERNEL32!GetLastError` at `0x18026bc1e`
- `KERNEL32!GetLastError` at `0x18026bd2f`
- `KERNEL32!GetLastError` at `0x18026bdbc`
- `KERNEL32!GetLastError` at `0x18026bef1`
- `KERNEL32!GetLastError` at `0x18026c019`
- `KERNEL32!GetLastError` at `0x18026c141`
- `KERNEL32!GetLastError` at `0x18026c269`
- `KERNEL32!GetLastError` at `0x18026c390`
- `KERNEL32!GetLastError` at `0x18026c50c`
- `KERNEL32!GetLastError` at `0x18026c633`
- `KERNEL32!GetLastError` at `0x18026c75a`
- `KERNEL32!GetLastError` at `0x18026c87f`
- `KERNEL32!GetLastError` at `0x18026c9a6`
- `KERNEL32!GetLastError` at `0x18026cae0`
- `KERNEL32!GetLastError` at `0x18026cb83`
- `KERNEL32!GetLastError` at `0x18026b6c2`
- `KERNEL32!GetLastError` at `0x18026b769`
- `KERNEL32!GetLastError` at `0x18026b80f`
- `KERNEL32!GetLastError` at `0x18026b8b5`
- `KERNEL32!GetLastError` at `0x18026b965`
- `KERNEL32!GetLastError` at `0x18026ba2b`
- `KERNEL32!GetLastError` at `0x18026baeb`
- `KERNEL32!GetLastError` at `0x18026bc1e`
- `KERNEL32!GetLastError` at `0x18026bd2f`
- `KERNEL32!GetLastError` at `0x18026bdbc`
- `KERNEL32!GetLastError` at `0x18026bef1`
- `KERNEL32!GetLastError` at `0x18026c019`
- `KERNEL32!GetLastError` at `0x18026c141`
- `KERNEL32!GetLastError` at `0x18026c269`
- `KERNEL32!GetLastError` at `0x18026c390`
- `KERNEL32!GetLastError` at `0x18026c50c`
- `KERNEL32!GetLastError` at `0x18026c633`
- `KERNEL32!GetLastError` at `0x18026c75a`
- `KERNEL32!GetLastError` at `0x18026c87f`
- `KERNEL32!GetLastError` at `0x18026c9a6`
- `KERNEL32!GetLastError` at `0x18026cae0`
- `KERNEL32!GetLastError` at `0x18026cb83`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026b657`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026baa4`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026bcf4`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026c33f`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026c4bb`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026c5e2`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026c709`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026c830`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026c955`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026b657`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026baa4`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026bcf4`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026c33f`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026c4bb`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026c5e2`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026c709`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026c830`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18026c955`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18026ca99`
- `unbcl!?Compare@String@UnBCL@@SAHPEBG0H@Z` at `0x18026ca99`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18026b636`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18026b636`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026bbb9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026bcd8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026bd14`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026be83`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026bfab`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c0d3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c1fb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c323`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c44a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c49f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c5c6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c6ed`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c814`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c939`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026ca60`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026bbb9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026bcd8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026bd14`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026be83`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026bfab`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c0d3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c1fb`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c323`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c44a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c49f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c5c6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c6ed`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c814`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026c939`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18026ca60`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18026bb68`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18026bb68`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026bba4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026bcc3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026be6e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026bf96`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c0be`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c1e6`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c30e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c435`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c48a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c5b1`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c6d8`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c7ff`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c924`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026ca4b`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026bba4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026bcc3`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026be6e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026bf96`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c0be`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c1e6`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c30e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c435`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c48a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c5b1`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c6d8`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c7ff`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026c924`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18026ca4b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026b64e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026b668`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026bbcc`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026bceb`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026be96`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026bfbe`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026c0e6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026c20e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026c336`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026c350`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026c4b2`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18026c4cc`

## string_xrefs

- `0x18026b5c0`: `SYSTEM\Setup\Rollback`
- `0x18026b608`: `SYSTEM\Setup\Rollback`
- `0x18026bacc`: `UninstallComment`
- `0x18026bb00`: `UninstallComment`
- `0x18026ba0c`: `UninstallReason`
- `0x18026ba40`: `UninstallReason`
- `0x18026b6de`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026b785`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026b82b`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026b8d1`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026b981`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026ba47`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026bb07`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026bc3a`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026bdd8`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026bf0d`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026c035`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026c15d`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026c285`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026c3ac`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026c528`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026c64f`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026c776`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026c89b`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026c9c2`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026cafb`: `Error creating Rollback entry %s. Error: 0x%08X`
- `0x18026b6a7`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026bc68`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026bd72`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026be06`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026bf3b`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026c063`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026c18b`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026c2b3`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026c3da`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026c556`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026c67d`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026c7a4`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026c8c9`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026c9f0`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026cb29`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026cbc6`: `base\ntsetup\setupplatform\lib\private\rollback.cpp`
- `0x18026cb97`: `Error while creating/opening the Rollback key. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
_BOOL8 __fastcall pRegisterFailureData(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        UnBCL::String *a6,
        UnBCL::String *a7,
        UnBCL::String *a8)
{
  LSTATUS v8; // r14d
  struct UnBCL::String *v9; // rax
  UnBCL::String *v10; // rax
  DWORD v11; // ebx
  UnBCL::String *v12; // rax
  const BYTE *CString; // rax
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  DWORD v17; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  DWORD v23; // edi
  __int64 v24; // rbx
  struct tagLOG_PARTIAL_MSG *v25; // rax
  DWORD v26; // edi
  __int64 v27; // rbx
  struct tagLOG_PARTIAL_MSG *v28; // rax
  const wchar_t *v29; // rax
  DWORD v30; // edi
  __int64 v31; // rbx
  struct tagLOG_PARTIAL_MSG *v32; // rax
  DWORD v33; // ebx
  const BYTE *v34; // rax
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  const WCHAR *v38; // rax
  struct UnBCL::String *v39; // rax
  UnBCL::String *v40; // rax
  const wchar_t *v41; // rax
  DWORD v42; // edi
  __int64 v43; // rbx
  struct tagLOG_PARTIAL_MSG *v44; // rax
  const WCHAR *v45; // rax
  struct UnBCL::String *v46; // rax
  UnBCL::String *v47; // rax
  unsigned int v48; // ebx
  unsigned __int8 *v49; // rdi
  unsigned int v50; // ebx
  struct UnBCL::String *P; // rax
  DWORD v52; // edi
  __int64 v53; // rbx
  struct tagLOG_PARTIAL_MSG *v54; // rax
  DWORD v55; // edi
  __int64 v56; // rbx
  struct tagLOG_PARTIAL_MSG *v57; // rax
  const WCHAR *v58; // rax
  struct UnBCL::String *v59; // rax
  UnBCL::String *v60; // rax
  const wchar_t *v61; // rax
  DWORD v62; // edi
  __int64 v63; // rbx
  struct tagLOG_PARTIAL_MSG *v64; // rax
  const WCHAR *v65; // rax
  struct UnBCL::String *v66; // rax
  UnBCL::String *v67; // rax
  const wchar_t *v68; // rax
  DWORD v69; // edi
  __int64 v70; // rbx
  struct tagLOG_PARTIAL_MSG *v71; // rax
  const WCHAR *v72; // rax
  struct UnBCL::String *v73; // rax
  UnBCL::String *v74; // rax
  const wchar_t *v75; // rax
  DWORD v76; // edi
  __int64 v77; // rbx
  struct tagLOG_PARTIAL_MSG *v78; // rax
  const WCHAR *v79; // rax
  struct UnBCL::String *v80; // rax
  UnBCL::String *v81; // rax
  const wchar_t *v82; // rax
  DWORD v83; // edi
  __int64 v84; // rbx
  struct tagLOG_PARTIAL_MSG *v85; // rax
  const WCHAR *v86; // rax
  struct UnBCL::String *v87; // rax
  UnBCL::String *v88; // rax
  DWORD v89; // ebx
  UnBCL::String *v90; // rax
  const BYTE *v91; // rax
  DWORD v92; // edi
  __int64 v93; // rbx
  struct tagLOG_PARTIAL_MSG *v94; // rax
  const WCHAR *v95; // rax
  struct UnBCL::String *v96; // rax
  const WCHAR *v97; // rax
  struct UnBCL::String *v98; // rax
  UnBCL::String *v99; // rax
  DWORD v100; // ebx
  UnBCL::String *v101; // rax
  const BYTE *v102; // rax
  DWORD v103; // edi
  __int64 v104; // rbx
  struct tagLOG_PARTIAL_MSG *v105; // rax
  const WCHAR *v106; // rax
  struct UnBCL::String *v107; // rax
  UnBCL::String *v108; // rax
  DWORD v109; // ebx
  UnBCL::String *v110; // rax
  const BYTE *v111; // rax
  DWORD v112; // edi
  __int64 v113; // rbx
  struct tagLOG_PARTIAL_MSG *v114; // rax
  const WCHAR *v115; // rax
  struct UnBCL::String *v116; // rax
  UnBCL::String *v117; // rax
  DWORD v118; // ebx
  UnBCL::String *v119; // rax
  const BYTE *v120; // rax
  DWORD v121; // edi
  __int64 v122; // rbx
  struct tagLOG_PARTIAL_MSG *v123; // rax
  const WCHAR *v124; // rax
  struct UnBCL::String *v125; // rax
  UnBCL::String *v126; // rax
  DWORD v127; // ebx
  UnBCL::String *v128; // rax
  const BYTE *v129; // rax
  DWORD v130; // edi
  __int64 v131; // rbx
  struct tagLOG_PARTIAL_MSG *v132; // rax
  const WCHAR *v133; // rax
  struct UnBCL::String *v134; // rax
  UnBCL::String *v135; // rax
  DWORD v136; // ebx
  UnBCL::String *v137; // rax
  const BYTE *v138; // rax
  DWORD v139; // edi
  __int64 v140; // rbx
  struct tagLOG_PARTIAL_MSG *v141; // rax
  const WCHAR *v142; // rax
  struct UnBCL::String *v143; // rax
  UnBCL::String *v144; // rax
  const unsigned __int16 *v145; // rax
  LSTATUS v146; // esi
  DWORD v147; // edi
  __int64 v148; // rbx
  struct tagLOG_PARTIAL_MSG *v149; // rax
  BOOL v150; // esi
  DWORD LastError; // edi
  __int64 v152; // rbx
  struct tagLOG_PARTIAL_MSG *v153; // rax
  LSTATUS v155; // [rsp+68h] [rbp-51h]
  LSTATUS v156; // [rsp+68h] [rbp-51h]
  LSTATUS v157; // [rsp+68h] [rbp-51h]
  LSTATUS v158; // [rsp+68h] [rbp-51h]
  LSTATUS v159; // [rsp+68h] [rbp-51h]
  LSTATUS v160; // [rsp+68h] [rbp-51h]
  LSTATUS v161; // [rsp+68h] [rbp-51h]
  LSTATUS v162; // [rsp+68h] [rbp-51h]
  int v163; // [rsp+68h] [rbp-51h]
  LSTATUS v164; // [rsp+68h] [rbp-51h]
  LSTATUS v165; // [rsp+68h] [rbp-51h]
  LSTATUS v166; // [rsp+68h] [rbp-51h]
  LSTATUS v167; // [rsp+68h] [rbp-51h]
  LSTATUS v168; // [rsp+68h] [rbp-51h]
  LSTATUS v169; // [rsp+68h] [rbp-51h]
  LSTATUS v170; // [rsp+68h] [rbp-51h]
  LSTATUS v171; // [rsp+68h] [rbp-51h]
  LSTATUS v172; // [rsp+68h] [rbp-51h]
  LSTATUS v173; // [rsp+68h] [rbp-51h]
  LSTATUS v174; // [rsp+68h] [rbp-51h]
  int v175; // [rsp+6Ch] [rbp-4Dh]
  BYTE Data[8]; // [rsp+70h] [rbp-49h] BYREF
  BYTE v177[16]; // [rsp+78h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-31h] BYREF
  _BYTE v179[16]; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v180[16]; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v181; // [rsp+B0h] [rbp-9h]

  v181 = -2;
  hKey = 0;
  RegDeleteKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup\\Rollback");
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup\\Rollback", 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v8 )
  {
    v150 = 0;
    LastError = GetLastError();
    v152 = CurrentIP();
    v153 = ConstructPartialMsgW(0x2000000u, "Error while creating/opening the Rollback key. Error: 0x%08X", v8);
    WdsSetupLogMessageW(
      v153,
      819200,
      L"D",
      0,
      480,
      L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
      L"pRegisterFailureData",
      v152,
      LastError,
      0,
      0);
    return v150;
  }
  v175 = 0;
  v9 = UnBCL::String::Format(L"%u.%u", 1, 103);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v180, v9);
  v10 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v180);
  v11 = 2 * UnBCL::String::get_Length(v10) + 2;
  v12 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v180);
  CString = (const BYTE *)UnBCL::String::get_CString(v12);
  v155 = RegSetValueExW(hKey, L"Setup platform version", 0, 1u, CString, v11);
  if ( v155 )
  {
    v175 = 1;
    v14 = GetLastError();
    v15 = CurrentIP();
    v16 = ConstructPartialMsgW(
            0x2000000u,
            "Error creating Rollback entry %s. Error: 0x%08X",
            (const char *)L"Setup platform version",
            v155);
    WdsSetupLogMessageW(
      v16,
      819200,
      L"D",
      0,
      84,
      L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
      L"pRegisterFailureData",
      v15,
      v14,
      0,
      0);
  }
  *(_DWORD *)Data = a1;
  v156 = RegSetValueExW(hKey, L"Phase", 0, 4u, Data, 4u);
  if ( v156 )
  {
    v175 = 1;
    v17 = GetLastError();
    v18 = CurrentIP();
    v19 = ConstructPartialMsgW(
            0x2000000u,
            "Error creating Rollback entry %s. Error: 0x%08X",
            (const char *)L"Phase",
            v156);
    WdsSetupLogMessageW(
      v19,
      819200,
      L"D",
      0,
      100,
      L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
      L"pRegisterFailureData",
      v18,
      v17,
      0,
      0);
  }
  *(_DWORD *)Data = a2;
  v157 = RegSetValueExW(hKey, L"Operation", 0, 4u, Data, 4u);
  if ( v157 )
  {
    v175 = 1;
    v20 = GetLastError();
    v21 = CurrentIP();
    v22 = ConstructPartialMsgW(
            0x2000000u,
            "Error creating Rollback entry %s. Error: 0x%08X",
            (const char *)L"Operation",
            v157);
    WdsSetupLogMessageW(
      v22,
      819200,
      L"D",
      0,
      116,
      L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
      L"pRegisterFailureData",
      v21,
      v20,
      0,
      0);
  }
  *(_DWORD *)Data = a3;
  v158 = RegSetValueExW(hKey, L"Internal operation", 0, 4u, Data, 4u);
  if ( v158 )
  {
    v175 = 1;
    v23 = GetLastError();
    v24 = CurrentIP();
    v25 = ConstructPartialMsgW(
            0x2000000u,
            "Error creating Rollback entry %s. Error: 0x%08X",
            (const char *)L"Internal operation",
            v158);
    WdsSetupLogMessageW(
      v25,
      819200,
      L"D",
      0,
      132,
      L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
      L"pRegisterFailureData",
      v24,
      v23,
      0,
      0);
  }
  if ( a4 )
  {
    *(_DWORD *)Data = a5;
    v159 = RegSetValueExW(hKey, L"Result", 0, 4u, Data, 4u);
    if ( v159 )
    {
      v175 = 1;
      v26 = GetLastError();
      v27 = CurrentIP();
      v28 = ConstructPartialMsgW(
              0x2000000u,
              "Error creating Rollback entry %s. Error: 0x%08X",
              (const char *)L"Result",
              v159);
      WdsSetupLogMessageW(
        v28,
        819200,
        L"D",
        0,
        150,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"pRegisterFailureData",
        v27,
        v26,
        0,
        0);
    }
  }
  else
  {
    RegDeleteValueW(hKey, L"Result");
  }
  if ( a6 )
  {
    v29 = UnBCL::String::get_CString(a6);
    *(_DWORD *)Data = _wtoi(v29);
    v160 = RegSetValueExW(hKey, L"UninstallReason", 0, 4u, Data, 4u);
    if ( v160 )
    {
      v175 = 1;
      v30 = GetLastError();
      v31 = CurrentIP();
      v32 = ConstructPartialMsgW(
              0x2000000u,
              "Error creating Rollback entry %s. Error: 0x%08X",
              (const char *)L"UninstallReason",
              v160);
      WdsSetupLogMessageW(
        v32,
        819200,
        L"D",
        0,
        172,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"pRegisterFailureData",
        v31,
        v30,
        0,
        0);
    }
  }
  if ( a7 )
  {
    v33 = 2 * UnBCL::String::get_Length(a7) + 2;
    v34 = (const BYTE *)UnBCL::String::get_CString(a7);
    v161 = RegSetValueExW(hKey, L"UninstallComment", 0, 1u, v34, v33);
    if ( v161 )
    {
      v175 = 1;
      v35 = GetLastError();
      v36 = CurrentIP();
      v37 = ConstructPartialMsgW(
              0x2000000u,
              "Error creating Rollback entry %s. Error: 0x%08X",
              (const char *)L"UninstallComment",
              v161);
      WdsSetupLogMessageW(
        v37,
        819200,
        L"D",
        0,
        189,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"pRegisterFailureData",
        v36,
        v35,
        0,
        0);
    }
  }
  if ( a8 )
  {
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v179);
    v38 = UnBCL::String::get_CString(a8);
    v39 = SPReadConfigValue(L"Bugcheck", L"Code", v38);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v39);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
    {
      v40 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
      v41 = UnBCL::String::get_CString(v40);
      *(_DWORD *)Data = _wtoi(v41);
      v162 = RegSetValueExW(hKey, L"Bugcheck code", 0, 4u, Data, 4u);
      if ( v162 )
      {
        v175 = 1;
        v42 = GetLastError();
        v43 = CurrentIP();
        v44 = ConstructPartialMsgW(
                0x2000000u,
                "Error creating Rollback entry %s. Error: 0x%08X",
                (const char *)L"Bugcheck code",
                v162);
        WdsSetupLogMessageW(
          v44,
          819200,
          L"D",
          0,
          214,
          L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
          L"pRegisterFailureData",
          v43,
          v42,
          0,
          0);
      }
    }
    v45 = UnBCL::String::get_CString(a8);
    v46 = SPReadConfigValue(L"Bugcheck", L"BinaryInfo", v45);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v46);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
    if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
      goto LABEL_31;
    v47 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
    v48 = UnBCL::String::get_Length(v47) + 1;
    v49 = (unsigned __int8 *)operator new[]((unsigned __int64)v48 >> 1);
    *(_QWORD *)v177 = v49;
    v50 = v48 >> 1;
    P = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v179);
    v163 = SPHexDecode(P, v49, v50);
    if ( v163 )
    {
      v52 = GetLastError();
      v53 = CurrentIP();
      v54 = ConstructPartialMsgW(0x2000000u, "Failed to Decode Hex Binary Info. Error: 0x%08X", v163);
      WdsSetupLogMessageW(
        v54,
        819200,
        L"D",
        0,
        227,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"pRegisterFailureData",
        v53,
        v52,
        0,
        0);
    }
    else
    {
      v164 = RegSetValueExW(hKey, L"Bugcheck binary info", 0, 3u, v49, v50);
      if ( !v164 )
      {
LABEL_30:
        operator delete[](v49);
LABEL_31:
        v58 = UnBCL::String::get_CString(a8);
        v59 = SPReadConfigValue(L"Bugcheck", L"Param1", v58);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v59);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
        {
          v60 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v61 = UnBCL::String::get_CString(v60);
          *(_QWORD *)v177 = _wcstoui64(v61, 0, 10);
          v165 = RegSetValueExW(hKey, L"Bugcheck param 1", 0, 0xBu, v177, 8u);
          if ( v165 )
          {
            v175 = 1;
            v62 = GetLastError();
            v63 = CurrentIP();
            v64 = ConstructPartialMsgW(
                    0x2000000u,
                    "Error creating Rollback entry %s. Error: 0x%08X",
                    (const char *)L"Bugcheck param 1",
                    v165);
            WdsSetupLogMessageW(
              v64,
              819200,
              L"D",
              0,
              266,
              L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
              L"pRegisterFailureData",
              v63,
              v62,
              0,
              0);
          }
        }
        v65 = UnBCL::String::get_CString(a8);
        v66 = SPReadConfigValue(L"Bugcheck", L"Param2", v65);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v66);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
        {
          v67 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v68 = UnBCL::String::get_CString(v67);
          *(_QWORD *)v177 = _wcstoui64(v68, 0, 10);
          v166 = RegSetValueExW(hKey, L"Bugcheck param 2", 0, 0xBu, v177, 8u);
          if ( v166 )
          {
            v175 = 1;
            v69 = GetLastError();
            v70 = CurrentIP();
            v71 = ConstructPartialMsgW(
                    0x2000000u,
                    "Error creating Rollback entry %s. Error: 0x%08X",
                    (const char *)L"Bugcheck param 2",
                    v166);
            WdsSetupLogMessageW(
              v71,
              819200,
              L"D",
              0,
              286,
              L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
              L"pRegisterFailureData",
              v70,
              v69,
              0,
              0);
          }
        }
        v72 = UnBCL::String::get_CString(a8);
        v73 = SPReadConfigValue(L"Bugcheck", L"Param3", v72);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v73);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
        {
          v74 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v75 = UnBCL::String::get_CString(v74);
          *(_QWORD *)v177 = _wcstoui64(v75, 0, 10);
          v167 = RegSetValueExW(hKey, L"Bugcheck param 3", 0, 0xBu, v177, 8u);
          if ( v167 )
          {
            v175 = 1;
            v76 = GetLastError();
            v77 = CurrentIP();
            v78 = ConstructPartialMsgW(
                    0x2000000u,
                    "Error creating Rollback entry %s. Error: 0x%08X",
                    (const char *)L"Bugcheck param 3",
                    v167);
            WdsSetupLogMessageW(
              v78,
              819200,
              L"D",
              0,
              306,
              L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
              L"pRegisterFailureData",
              v77,
              v76,
              0,
              0);
          }
        }
        v79 = UnBCL::String::get_CString(a8);
        v80 = SPReadConfigValue(L"Bugcheck", L"Param4", v79);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v80);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
        {
          v81 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v82 = UnBCL::String::get_CString(v81);
          *(_QWORD *)v177 = _wcstoui64(v82, 0, 10);
          v168 = RegSetValueExW(hKey, L"Bugcheck param 4", 0, 0xBu, v177, 8u);
          if ( v168 )
          {
            v175 = 1;
            v83 = GetLastError();
            v84 = CurrentIP();
            v85 = ConstructPartialMsgW(
                    0x2000000u,
                    "Error creating Rollback entry %s. Error: 0x%08X",
                    (const char *)L"Bugcheck param 4",
                    v168);
            WdsSetupLogMessageW(
              v85,
              819200,
              L"D",
              0,
              326,
              L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
              L"pRegisterFailureData",
              v84,
              v83,
              0,
              0);
          }
        }
        v86 = UnBCL::String::get_CString(a8);
        v87 = SPReadConfigValue(L"Bugcheck", L"StackInfo", v86);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v87);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
        {
          v88 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v89 = 2 * UnBCL::String::get_Length(v88) + 2;
          v90 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v91 = (const BYTE *)UnBCL::String::get_CString(v90);
          v169 = RegSetValueExW(hKey, L"Bugcheck stack", 0, 1u, v91, v89);
          if ( v169 )
          {
            v175 = 1;
            v92 = GetLastError();
            v93 = CurrentIP();
            v94 = ConstructPartialMsgW(
                    0x2000000u,
                    "Error creating Rollback entry %s. Error: 0x%08X",
                    (const char *)L"Bugcheck stack",
                    v169);
            WdsSetupLogMessageW(
              v94,
              819200,
              L"D",
              0,
              345,
              L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
              L"pRegisterFailureData",
              v93,
              v92,
              0,
              0);
          }
        }
        v95 = UnBCL::String::get_CString(a8);
        v96 = SPReadConfigValue(L"Bugcheck", L"Module", v95);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v96);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
        if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
        {
          v97 = UnBCL::String::get_CString(a8);
          v98 = SPReadConfigValue(L"Bugcheck", L"ParamModule", v97);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v98);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
        }
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
        {
          v99 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v100 = 2 * UnBCL::String::get_Length(v99) + 2;
          v101 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v102 = (const BYTE *)UnBCL::String::get_CString(v101);
          v170 = RegSetValueExW(hKey, L"Bugcheck module", 0, 1u, v102, v100);
          if ( v170 )
          {
            v175 = 1;
            v103 = GetLastError();
            v104 = CurrentIP();
            v105 = ConstructPartialMsgW(
                     0x2000000u,
                     "Error creating Rollback entry %s. Error: 0x%08X",
                     (const char *)L"Bugcheck module",
                     v170);
            WdsSetupLogMessageW(
              v105,
              819200,
              L"D",
              0,
              368,
              L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
              L"pRegisterFailureData",
              v104,
              v103,
              0,
              0);
          }
        }
        v106 = UnBCL::String::get_CString(a8);
        v107 = SPReadConfigValue(L"Bugcheck", L"DriverInf", v106);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v107);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
        {
          v108 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v109 = 2 * UnBCL::String::get_Length(v108) + 2;
          v110 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v111 = (const BYTE *)UnBCL::String::get_CString(v110);
          v171 = RegSetValueExW(hKey, L"Bugcheck driver INF name", 0, 1u, v111, v109);
          if ( v171 )
          {
            v175 = 1;
            v112 = GetLastError();
            v113 = CurrentIP();
            v114 = ConstructPartialMsgW(
                     0x2000000u,
                     "Error creating Rollback entry %s. Error: 0x%08X",
                     (const char *)L"Bugcheck driver INF name",
                     v171);
            WdsSetupLogMessageW(
              v114,
              819200,
              L"D",
              0,
              387,
              L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
              L"pRegisterFailureData",
              v113,
              v112,
              0,
              0);
          }
        }
        v115 = UnBCL::String::get_CString(a8);
        v116 = SPReadConfigValue(L"Bugcheck", L"DriverProvider", v115);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v116);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
        {
          v117 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v118 = 2 * UnBCL::String::get_Length(v117) + 2;
          v119 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v120 = (const BYTE *)UnBCL::String::get_CString(v119);
          v172 = RegSetValueExW(hKey, L"Bugcheck driver provider", 0, 1u, v120, v118);
          if ( v172 )
          {
            v175 = 1;
            v121 = GetLastError();
            v122 = CurrentIP();
            v123 = ConstructPartialMsgW(
                     0x2000000u,
                     "Error creating Rollback entry %s. Error: 0x%08X",
                     (const char *)L"Bugcheck driver provider",
                     v172);
            WdsSetupLogMessageW(
              v123,
              819200,
              L"D",
              0,
              406,
              L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
              L"pRegisterFailureData",
              v122,
              v121,
              0,
              0);
          }
        }
        v124 = UnBCL::String::get_CString(a8);
        v125 = SPReadConfigValue(L"Bugcheck", L"DriverClassGUID", v124);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v125);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
        {
          v126 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v127 = 2 * UnBCL::String::get_Length(v126) + 2;
          v128 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v129 = (const BYTE *)UnBCL::String::get_CString(v128);
          v173 = RegSetValueExW(hKey, L"Bugcheck driver class", 0, 1u, v129, v127);
          if ( v173 )
          {
            v175 = 1;
            v130 = GetLastError();
            v131 = CurrentIP();
            v132 = ConstructPartialMsgW(
                     0x2000000u,
                     "Error creating Rollback entry %s. Error: 0x%08X",
                     (const char *)L"Bugcheck driver class",
                     v173);
            WdsSetupLogMessageW(
              v132,
              819200,
              L"D",
              0,
              425,
              L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
              L"pRegisterFailureData",
              v131,
              v130,
              0,
              0);
          }
        }
        v133 = UnBCL::String::get_CString(a8);
        v134 = SPReadConfigValue(L"Bugcheck", L"DriverVersion", v133);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v134);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
        {
          v135 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v136 = 2 * UnBCL::String::get_Length(v135) + 2;
          v137 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v138 = (const BYTE *)UnBCL::String::get_CString(v137);
          v174 = RegSetValueExW(hKey, L"Bugcheck driver version", 0, 1u, v138, v136);
          if ( v174 )
          {
            v175 = 1;
            v139 = GetLastError();
            v140 = CurrentIP();
            v141 = ConstructPartialMsgW(
                     0x2000000u,
                     "Error creating Rollback entry %s. Error: 0x%08X",
                     (const char *)L"Bugcheck driver version",
                     v174);
            WdsSetupLogMessageW(
              v141,
              819200,
              L"D",
              0,
              444,
              L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
              L"pRegisterFailureData",
              v140,
              v139,
              0,
              0);
          }
        }
        v142 = UnBCL::String::get_CString(a8);
        v143 = SPReadConfigValue(L"Bugcheck", L"DriverDownloaded", v142);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v177, v143);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v179, v177);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v177);
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v179) )
        {
          *(_DWORD *)Data = 0;
          v144 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v179);
          v145 = UnBCL::String::get_CString(v144);
          if ( !UnBCL::String::Compare(v145, L"Yes", 1) )
            *(_DWORD *)Data = 1;
          v146 = RegSetValueExW(hKey, L"Bugcheck driver downloaded", 0, 4u, Data, 4u);
          if ( v146 )
          {
            v175 = 1;
            v147 = GetLastError();
            v148 = CurrentIP();
            v149 = ConstructPartialMsgW(
                     0x2000000u,
                     "Error creating Rollback entry %s. Error: 0x%08X",
                     (const char *)L"Bugcheck driver downloaded",
                     v146);
            WdsSetupLogMessageW(
              v149,
              819200,
              L"D",
              0,
              468,
              L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
              L"pRegisterFailureData",
              v148,
              v147,
              0,
              0);
          }
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v179);
        goto LABEL_69;
      }
      v175 = 1;
      v55 = GetLastError();
      v56 = CurrentIP();
      v57 = ConstructPartialMsgW(
              0x2000000u,
              "Error creating Rollback entry %s. Error: 0x%08X",
              (const char *)L"Bugcheck binary info",
              v164);
      WdsSetupLogMessageW(
        v57,
        819200,
        L"D",
        0,
        243,
        L"base\\ntsetup\\setupplatform\\lib\\private\\rollback.cpp",
        L"pRegisterFailureData",
        v56,
        v55,
        0,
        0);
    }
    v49 = *(unsigned __int8 **)v177;
    goto LABEL_30;
  }
LABEL_69:
  v150 = v175 == 0;
  RegCloseKey(hKey);
  hKey = 0;
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v180);
  return v150;
}

```

## disassembly

```asm
0x18026b588  mov     rax, rsp
0x18026b58b  mov     [rax+20h], r9d
0x18026b58f  mov     [rax+18h], r8d
0x18026b593  mov     [rax+10h], edx
0x18026b596  mov     [rax+8], ecx
0x18026b599  push    rbp
0x18026b59a  push    rbx
0x18026b59b  push    rsi
0x18026b59c  push    rdi
0x18026b59d  push    r12
0x18026b59f  push    r13
0x18026b5a1  push    r14
0x18026b5a3  push    r15
0x18026b5a5  lea     rbp, [rax-47h]
0x18026b5a9  sub     rsp, 0B8h
0x18026b5b0  mov     [rbp+3Fh+var_48], 0FFFFFFFFFFFFFFFEh
0x18026b5b8  mov     [rbp+3Fh+hKey], 0
0x18026b5c0  lea     rdx, aSystemSetupRol; "SYSTEM\\Setup\\Rollback"
0x18026b5c7  mov     rbx, 0FFFFFFFF80000002h
0x18026b5ce  mov     rcx, rbx; hKey
0x18026b5d1  call    cs:__imp_RegDeleteKeyW
0x18026b5d7  mov     [rsp+0F0h+lpdwDisposition], 0; lpdwDisposition
0x18026b5e0  lea     rax, [rbp+3Fh+hKey]
0x18026b5e4  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18026b5e9  mov     [rsp+0F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18026b5f2  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x18026b5fa  mov     [rsp+0F0h+dwOptions], 0; dwOptions
0x18026b602  xor     r9d, r9d; lpClass
0x18026b605  xor     r8d, r8d; Reserved
0x18026b608  lea     rdx, aSystemSetupRol; "SYSTEM\\Setup\\Rollback"
0x18026b60f  mov     rcx, rbx; hKey
0x18026b612  call    cs:__imp_RegCreateKeyExW
0x18026b618  mov     r14d, eax
0x18026b61b  test    eax, eax
0x18026b61d  jnz     loc_18026CB81
0x18026b623  mov     [rbp+3Fh+var_8C], eax
0x18026b626  lea     edi, [rax+1]
0x18026b629  lea     r8d, [rax+67h]
0x18026b62d  mov     edx, edi
0x18026b62f  lea     rcx, aUU; "%u.%u"
0x18026b636  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x18026b63c  mov     rdx, rax
0x18026b63f  lea     rcx, [rbp+3Fh+var_58]
0x18026b643  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18026b649  nop
0x18026b64a  lea     rcx, [rbp+3Fh+var_58]
0x18026b64e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18026b654  mov     rcx, rax
0x18026b657  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18026b65d  lea     ebx, ds:2[rax*2]
0x18026b664  lea     rcx, [rbp+3Fh+var_58]
0x18026b668  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18026b66e  mov     rcx, rax
0x18026b671  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18026b677  mov     [rsp+0F0h+samDesired], ebx; cbData
0x18026b67b  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18026b680  mov     r9d, edi; dwType
0x18026b683  xor     r8d, r8d; Reserved
0x18026b686  lea     rdx, aSetupPlatformV_0; "Setup platform version"
0x18026b68d  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18026b691  call    cs:__imp_RegSetValueExW
0x18026b697  mov     [rbp+3Fh+var_90], eax
0x18026b69a  mov     r14d, 2000000h
0x18026b6a0  lea     r13, aPregisterfailu; "pRegisterFailureData"
0x18026b6a7  lea     rsi, aBaseNtsetupSet_35; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x18026b6ae  lea     r15, aD_0; "D"
0x18026b6b5  mov     r12d, 0C8000h
0x18026b6bb  test    eax, eax
0x18026b6bd  jz      short loc_18026B730
0x18026b6bf  mov     [rbp+3Fh+var_8C], edi
0x18026b6c2  call    cs:__imp_GetLastError
0x18026b6c8  mov     edi, eax
0x18026b6ca  call    cs:__imp_CurrentIP
0x18026b6d0  mov     rbx, rax
0x18026b6d3  mov     r9d, [rbp+3Fh+var_90]
0x18026b6d7  lea     r8, aSetupPlatformV_0; "Setup platform version"
0x18026b6de  lea     rdx, aErrorCreatingR; "Error creating Rollback entry %s. Error"...
0x18026b6e5  mov     ecx, r14d; unsigned int
0x18026b6e8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18026b6ed  mov     dword ptr [rsp+50h], 0
0x18026b6f5  mov     qword ptr [rsp+0F0h+var_A8], 0
0x18026b6fe  mov     dword ptr [rsp+0F0h+lpdwDisposition], edi
0x18026b702  mov     [rsp+0F0h+phkResult], rbx
0x18026b707  mov     [rsp+0F0h+lpSecurityAttributes], r13
0x18026b70c  mov     qword ptr [rsp+0F0h+samDesired], rsi
0x18026b711  mov     [rsp+0F0h+dwOptions], 54h ; 'T'
0x18026b719  xor     r9d, r9d
0x18026b71c  mov     r8, r15
0x18026b71f  mov     edx, r12d
0x18026b722  mov     rcx, rax
0x18026b725  call    cs:__imp_WdsSetupLogMessageW
0x18026b72b  mov     edi, 1
0x18026b730  mov     eax, [rbp+3Fh+arg_0]
0x18026b733  mov     dword ptr [rbp+3Fh+Data], eax
0x18026b736  mov     ebx, 4
0x18026b73b  mov     [rsp+0F0h+samDesired], ebx; cbData
0x18026b73f  lea     rax, [rbp+3Fh+Data]
0x18026b743  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18026b748  mov     r9d, ebx; dwType
0x18026b74b  xor     r8d, r8d; Reserved
0x18026b74e  lea     rdx, aPhase; "Phase"
0x18026b755  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18026b759  call    cs:__imp_RegSetValueExW
0x18026b75f  mov     [rbp+3Fh+var_90], eax
0x18026b762  test    eax, eax
0x18026b764  jz      short loc_18026B7D7
0x18026b766  mov     [rbp+3Fh+var_8C], edi
0x18026b769  call    cs:__imp_GetLastError
0x18026b76f  mov     edi, eax
0x18026b771  call    cs:__imp_CurrentIP
0x18026b777  mov     rbx, rax
0x18026b77a  mov     r9d, [rbp+3Fh+var_90]
0x18026b77e  lea     r8, aPhase; "Phase"
0x18026b785  lea     rdx, aErrorCreatingR; "Error creating Rollback entry %s. Error"...
0x18026b78c  mov     ecx, r14d; unsigned int
0x18026b78f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18026b794  mov     dword ptr [rsp+50h], 0
0x18026b79c  mov     qword ptr [rsp+0F0h+var_A8], 0
0x18026b7a5  mov     dword ptr [rsp+0F0h+lpdwDisposition], edi
0x18026b7a9  mov     [rsp+0F0h+phkResult], rbx
0x18026b7ae  mov     [rsp+0F0h+lpSecurityAttributes], r13
0x18026b7b3  mov     qword ptr [rsp+0F0h+samDesired], rsi
0x18026b7b8  mov     [rsp+0F0h+dwOptions], 64h ; 'd'
0x18026b7c0  xor     r9d, r9d
0x18026b7c3  mov     r8, r15
0x18026b7c6  mov     edx, r12d
0x18026b7c9  mov     rcx, rax
0x18026b7cc  call    cs:__imp_WdsSetupLogMessageW
0x18026b7d2  mov     ebx, 4
0x18026b7d7  mov     eax, [rbp+3Fh+arg_8]
0x18026b7da  mov     dword ptr [rbp+3Fh+Data], eax
0x18026b7dd  mov     [rsp+0F0h+samDesired], ebx; cbData
0x18026b7e1  lea     rax, [rbp+3Fh+Data]
0x18026b7e5  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18026b7ea  mov     r9d, ebx; dwType
0x18026b7ed  xor     r8d, r8d; Reserved
0x18026b7f0  lea     rdx, aOperation; "Operation"
0x18026b7f7  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18026b7fb  call    cs:__imp_RegSetValueExW
0x18026b801  mov     [rbp+3Fh+var_90], eax
0x18026b804  test    eax, eax
0x18026b806  jz      short loc_18026B87D
0x18026b808  mov     [rbp+3Fh+var_8C], 1
0x18026b80f  call    cs:__imp_GetLastError
0x18026b815  mov     edi, eax
0x18026b817  call    cs:__imp_CurrentIP
0x18026b81d  mov     rbx, rax
0x18026b820  mov     r9d, [rbp+3Fh+var_90]
0x18026b824  lea     r8, aOperation; "Operation"
0x18026b82b  lea     rdx, aErrorCreatingR; "Error creating Rollback entry %s. Error"...
0x18026b832  mov     ecx, r14d; unsigned int
0x18026b835  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18026b83a  mov     dword ptr [rsp+50h], 0
0x18026b842  mov     qword ptr [rsp+0F0h+var_A8], 0
0x18026b84b  mov     dword ptr [rsp+0F0h+lpdwDisposition], edi
0x18026b84f  mov     [rsp+0F0h+phkResult], rbx
0x18026b854  mov     [rsp+0F0h+lpSecurityAttributes], r13
0x18026b859  mov     qword ptr [rsp+0F0h+samDesired], rsi
0x18026b85e  mov     [rsp+0F0h+dwOptions], 74h ; 't'
0x18026b866  xor     r9d, r9d
0x18026b869  mov     r8, r15
0x18026b86c  mov     edx, r12d
0x18026b86f  mov     rcx, rax
0x18026b872  call    cs:__imp_WdsSetupLogMessageW
0x18026b878  mov     ebx, 4
0x18026b87d  mov     eax, [rbp+3Fh+arg_10]
0x18026b880  mov     dword ptr [rbp+3Fh+Data], eax
0x18026b883  mov     [rsp+0F0h+samDesired], ebx; cbData
0x18026b887  lea     rax, [rbp+3Fh+Data]
0x18026b88b  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18026b890  mov     r9d, ebx; dwType
0x18026b893  xor     r8d, r8d; Reserved
0x18026b896  lea     rdx, aInternalOperat; "Internal operation"
0x18026b89d  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18026b8a1  call    cs:__imp_RegSetValueExW
0x18026b8a7  mov     [rbp+3Fh+var_90], eax
0x18026b8aa  test    eax, eax
0x18026b8ac  jz      short loc_18026B923
0x18026b8ae  mov     [rbp+3Fh+var_8C], 1
0x18026b8b5  call    cs:__imp_GetLastError
0x18026b8bb  mov     edi, eax
0x18026b8bd  call    cs:__imp_CurrentIP
0x18026b8c3  mov     rbx, rax
0x18026b8c6  mov     r9d, [rbp+3Fh+var_90]
0x18026b8ca  lea     r8, aInternalOperat; "Internal operation"
0x18026b8d1  lea     rdx, aErrorCreatingR; "Error creating Rollback entry %s. Error"...
0x18026b8d8  mov     ecx, r14d; unsigned int
0x18026b8db  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18026b8e0  mov     dword ptr [rsp+50h], 0
0x18026b8e8  mov     qword ptr [rsp+0F0h+var_A8], 0
0x18026b8f1  mov     dword ptr [rsp+0F0h+lpdwDisposition], edi
0x18026b8f5  mov     [rsp+0F0h+phkResult], rbx
0x18026b8fa  mov     [rsp+0F0h+lpSecurityAttributes], r13
0x18026b8ff  mov     qword ptr [rsp+0F0h+samDesired], rsi
0x18026b904  mov     [rsp+0F0h+dwOptions], 84h
0x18026b90c  xor     r9d, r9d
0x18026b90f  mov     r8, r15
0x18026b912  mov     edx, r12d
0x18026b915  mov     rcx, rax
0x18026b918  call    cs:__imp_WdsSetupLogMessageW
0x18026b91e  mov     ebx, 4
0x18026b923  lea     rdx, aResult; "Result"
0x18026b92a  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18026b92e  cmp     [rbp+3Fh+arg_18], 0
0x18026b932  jz      loc_18026B9D0
0x18026b938  mov     eax, [rbp+3Fh+arg_20]
0x18026b93b  mov     dword ptr [rbp+3Fh+Data], eax
0x18026b93e  mov     [rsp+0F0h+samDesired], ebx; cbData
0x18026b942  lea     rax, [rbp+3Fh+Data]
0x18026b946  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18026b94b  mov     r9d, ebx; dwType
0x18026b94e  xor     r8d, r8d; Reserved
0x18026b951  call    cs:__imp_RegSetValueExW
0x18026b957  mov     [rbp+3Fh+var_90], eax
0x18026b95a  test    eax, eax
0x18026b95c  jz      short loc_18026B9D6
0x18026b95e  mov     [rbp+3Fh+var_8C], 1
0x18026b965  call    cs:__imp_GetLastError
0x18026b96b  mov     edi, eax
0x18026b96d  call    cs:__imp_CurrentIP
0x18026b973  mov     rbx, rax
0x18026b976  mov     r9d, [rbp+3Fh+var_90]
0x18026b97a  lea     r8, aResult; "Result"
0x18026b981  lea     rdx, aErrorCreatingR; "Error creating Rollback entry %s. Error"...
0x18026b988  mov     ecx, r14d; unsigned int
0x18026b98b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18026b990  mov     dword ptr [rsp+50h], 0
0x18026b998  mov     qword ptr [rsp+0F0h+var_A8], 0
0x18026b9a1  mov     dword ptr [rsp+0F0h+lpdwDisposition], edi
0x18026b9a5  mov     [rsp+0F0h+phkResult], rbx
0x18026b9aa  mov     [rsp+0F0h+lpSecurityAttributes], r13
0x18026b9af  mov     qword ptr [rsp+0F0h+samDesired], rsi
0x18026b9b4  mov     [rsp+0F0h+dwOptions], 96h
0x18026b9bc  xor     r9d, r9d
0x18026b9bf  mov     r8, r15
0x18026b9c2  mov     edx, r12d
0x18026b9c5  mov     rcx, rax
0x18026b9c8  call    cs:__imp_WdsSetupLogMessageW
0x18026b9ce  jmp     short loc_18026B9D6
0x18026b9d0  call    cs:__imp_RegDeleteValueW
0x18026b9d6  mov     rcx, [rbp+3Fh+arg_28]
0x18026b9da  test    rcx, rcx
0x18026b9dd  jz      loc_18026BA94
0x18026b9e3  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18026b9e9  mov     rcx, rax; String
0x18026b9ec  call    cs:__imp__wtoi
0x18026b9f2  mov     dword ptr [rbp+3Fh+Data], eax
0x18026b9f5  mov     r9d, 4; dwType
0x18026b9fb  mov     [rsp+0F0h+samDesired], r9d; cbData
0x18026ba00  lea     rax, [rbp+3Fh+Data]
0x18026ba04  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18026ba09  xor     r8d, r8d; Reserved
0x18026ba0c  lea     rdx, aUninstallreaso; "UninstallReason"
0x18026ba13  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18026ba17  call    cs:__imp_RegSetValueExW
0x18026ba1d  mov     [rbp+3Fh+var_90], eax
0x18026ba20  test    eax, eax
0x18026ba22  jz      short loc_18026BA94
0x18026ba24  mov     [rbp+3Fh+var_8C], 1
0x18026ba2b  call    cs:__imp_GetLastError
0x18026ba31  mov     edi, eax
0x18026ba33  call    cs:__imp_CurrentIP
0x18026ba39  mov     rbx, rax
0x18026ba3c  mov     r9d, [rbp+3Fh+var_90]
0x18026ba40  lea     r8, aUninstallreaso; "UninstallReason"
0x18026ba47  lea     rdx, aErrorCreatingR; "Error creating Rollback entry %s. Error"...
0x18026ba4e  mov     ecx, r14d; unsigned int
0x18026ba51  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18026ba56  mov     dword ptr [rsp+50h], 0
0x18026ba5e  mov     qword ptr [rsp+0F0h+var_A8], 0
0x18026ba67  mov     dword ptr [rsp+0F0h+lpdwDisposition], edi
0x18026ba6b  mov     [rsp+0F0h+phkResult], rbx
0x18026ba70  mov     [rsp+0F0h+lpSecurityAttributes], r13
0x18026ba75  mov     qword ptr [rsp+0F0h+samDesired], rsi
0x18026ba7a  mov     [rsp+0F0h+dwOptions], 0ACh
0x18026ba82  xor     r9d, r9d
0x18026ba85  mov     r8, r15
0x18026ba88  mov     edx, r12d
0x18026ba8b  mov     rcx, rax
0x18026ba8e  call    cs:__imp_WdsSetupLogMessageW
0x18026ba94  mov     rdi, [rbp+3Fh+arg_30]
0x18026ba98  test    rdi, rdi
0x18026ba9b  jz      loc_18026BB54
0x18026baa1  mov     rcx, rdi
0x18026baa4  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18026baaa  lea     ebx, ds:2[rax*2]
0x18026bab1  mov     rcx, rdi
0x18026bab4  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18026baba  mov     [rsp+0F0h+samDesired], ebx; cbData
0x18026babe  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18026bac3  mov     r9d, 1; dwType
0x18026bac9  xor     r8d, r8d; Reserved
0x18026bacc  lea     rdx, aUninstallcomme; "UninstallComment"
0x18026bad3  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18026bad7  call    cs:__imp_RegSetValueExW
0x18026badd  mov     [rbp+3Fh+var_90], eax
0x18026bae0  test    eax, eax
0x18026bae2  jz      short loc_18026BB54
0x18026bae4  mov     [rbp+3Fh+var_8C], 1
0x18026baeb  call    cs:__imp_GetLastError
  ... truncated ...
```
