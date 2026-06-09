# CPrepareNewOSForFirstBoot::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)

- ea: `0x18013fc30`
- end: `0x180140635`
- name: `?DoExecute@CPrepareNewOSForFirstBoot@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z`
- size: `2565`
- prototype: `int(CPrepareNewOSForFirstBoot *__hidden this, struct IExecutionContext *, void *, struct IInternalOperationsProgress *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180044820`
- `0x180057dec`
- `0x18013fc30`
- `0x1802d8bfc`
- `0x1802db44c`
- `0x1802deb40`
- `0x1802e2078`
- `0x1802e6604`
- `0x180329870`
- `0x18037fd48`
- `0x180406640`
- `0x1804bbf46`
- `0x180509010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18013fcf7`
- `KERNEL32!GetLastError` at `0x18013fd18`
- `KERNEL32!GetLastError` at `0x180140020`
- `KERNEL32!GetLastError` at `0x180140038`
- `KERNEL32!GetLastError` at `0x180140050`
- `KERNEL32!GetLastError` at `0x180140189`
- `KERNEL32!GetLastError` at `0x1801401a7`
- `KERNEL32!GetLastError` at `0x1801402c5`
- `KERNEL32!GetLastError` at `0x1801402dd`
- `KERNEL32!GetLastError` at `0x1801402f5`
- `KERNEL32!GetLastError` at `0x18014056d`
- `KERNEL32!GetLastError` at `0x18013fcf7`
- `KERNEL32!GetLastError` at `0x18013fd18`
- `KERNEL32!GetLastError` at `0x180140020`
- `KERNEL32!GetLastError` at `0x180140038`
- `KERNEL32!GetLastError` at `0x180140050`
- `KERNEL32!GetLastError` at `0x180140189`
- `KERNEL32!GetLastError` at `0x1801401a7`
- `KERNEL32!GetLastError` at `0x1801402c5`
- `KERNEL32!GetLastError` at `0x1801402dd`
- `KERNEL32!GetLastError` at `0x1801402f5`
- `KERNEL32!GetLastError` at `0x18014056d`
- `KERNEL32!CloseHandle` at `0x18014024e`
- `KERNEL32!CloseHandle` at `0x180140273`
- `KERNEL32!CloseHandle` at `0x18014024e`
- `KERNEL32!CloseHandle` at `0x180140273`
- `KERNEL32!CreateFileW` at `0x18014012a`
- `KERNEL32!CreateFileW` at `0x18014012a`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18013fc8e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18013ff9c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18013ffdf`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18013fc8e`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18013ff9c`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18013ffdf`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18013feab`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18013fee5`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18013ff20`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18013feab`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18013fee5`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x18013ff20`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013fce8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013fdb6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013fe6d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013fe9c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013fed5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013ff10`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013ff90`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013ffd3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18014029d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18014049b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801404fd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013fce8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013fdb6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013fe6d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013fe9c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013fed5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013ff10`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013ff90`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18013ffd3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18014029d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18014049b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801404fd`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801403ea`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1801403ea`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013fca7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013fdec`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013fe2c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013ff3e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013ff52`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013ff66`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013ffb5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013fff7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180140398`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180140554`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18014055f`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013fca7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013fdec`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013fe2c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013ff3e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013ff52`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013ff66`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013ffb5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18013fff7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180140398`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180140554`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18014055f`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013fc70`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013fdd2`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013fe12`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013fe87`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013fec0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013fefb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013ff80`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013ffc6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180140379`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180140458`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801404af`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801404e9`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013fc70`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013fdd2`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013fe12`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013fe87`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013fec0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013fefb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013ff80`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18013ffc6`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180140379`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180140458`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801404af`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801404e9`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180140438`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180140438`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180140485`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180140485`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013fcb1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013fd2d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013fe36`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180140001`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180140065`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1801400f6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180140158`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1801401bc`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013fcb1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013fd2d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18013fe36`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180140001`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180140065`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1801400f6`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180140158`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1801401bc`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013fcba`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013fd36`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013fe3f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18014000a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18014006e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801400ff`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180140161`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801401c5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013fcba`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013fd36`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18013fe3f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18014000a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18014006e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801400ff`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180140161`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801401c5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801400e2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180140285`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180140290`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180140491`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801405f1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801405fc`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180140607`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180140612`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801400e2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180140285`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180140290`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180140491`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801405f1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801405fc`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180140607`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180140612`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013fc9b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013fcdd`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013fe62`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013ffa9`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013ffec`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180140475`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013fc9b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013fcdd`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013fe62`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013ffa9`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18013ffec`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180140475`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013fd9f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801400d7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18014022a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18014035f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801405e5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18013fd9f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801400d7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18014022a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18014035f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801405e5`
- `WDSCORE!CurrentIP` at `0x18013fd20`
- `WDSCORE!CurrentIP` at `0x180140058`
- `WDSCORE!CurrentIP` at `0x1801401af`
- `WDSCORE!CurrentIP` at `0x1801402fd`
- `WDSCORE!CurrentIP` at `0x180140575`
- `WDSCORE!CurrentIP` at `0x18013fd20`
- `WDSCORE!CurrentIP` at `0x180140058`
- `WDSCORE!CurrentIP` at `0x1801401af`
- `WDSCORE!CurrentIP` at `0x1801402fd`
- `WDSCORE!CurrentIP` at `0x180140575`

## string_xrefs

- `0x1801404dd`: `MonitoringPaths`
- `0x18013fdc6`: `InstallICB`
- `0x18013fd42`: `Failed to read the migration scope from %s. hr = 0x%08X`
- `0x180140171`: `DeleteDisableCmdFile`
- `0x18014007a`: `Failed to create path %s. hr = 0x%08X`
- `0x1801401d1`: `Failed to create file %s. hr = 0x%08X`
- `0x180140588`: `%hs: Failed to install/start monitoring driver. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall CPrepareNewOSForFirstBoot::DoExecute(
        CPrepareNewOSForFirstBoot *this,
        struct IExecutionContext *a2,
        void *a3,
        struct IInternalOperationsProgress *a4)
{
  CPrepareNewOSForFirstBoot *v5; // rsi
  const struct UnBCL::String *v6; // rbx
  const struct UnBCL::String *v7; // rax
  struct UnBCL::String *v8; // rax
  UnBCL::String *v9; // rax
  const WCHAR *CString; // rax
  struct UnBCL::String *v11; // rax
  signed int LastError; // eax
  unsigned int v13; // esi
  DWORD v14; // edi
  __int64 v15; // rbx
  UnBCL::String *v16; // rax
  const char *v17; // rax
  struct tagLOG_PARTIAL_MSG *v18; // rax
  int v19; // ebx
  __int64 P; // rax
  struct UnBCL::String *v21; // rax
  int v22; // r8d
  int v23; // r13d
  BOOL v24; // r14d
  BOOL v25; // r15d
  struct UnBCL::String *v26; // rax
  int v27; // r8d
  UnBCL::String *v28; // rax
  const WCHAR *v29; // rax
  struct UnBCL::String *v30; // rax
  const struct UnBCL::String *v31; // rbx
  char v32; // di
  const struct UnBCL::String *v33; // rax
  const struct UnBCL::String *v34; // rbx
  const struct UnBCL::String *v35; // rax
  const struct UnBCL::String *v36; // rbx
  const struct UnBCL::String *v37; // rax
  bool v38; // bl
  const struct UnBCL::String *v39; // rbx
  const struct UnBCL::String *v40; // rax
  struct UnBCL::String *v41; // rax
  const struct UnBCL::String *v42; // rbx
  const struct UnBCL::String *v43; // rax
  struct UnBCL::String *v44; // rax
  UnBCL::String *v45; // rax
  const unsigned __int16 *v46; // rax
  signed int v47; // eax
  bool v48; // sf
  signed int v49; // eax
  DWORD v50; // edi
  __int64 v51; // rbx
  UnBCL::String *v52; // rax
  const char *v53; // rax
  struct tagLOG_PARTIAL_MSG *v54; // rax
  UnBCL::String *v55; // rax
  const WCHAR *v56; // rax
  HANDLE FileW; // rax
  UnBCL::String *v58; // rax
  const unsigned __int16 *v59; // rax
  signed int v60; // eax
  DWORD v61; // edi
  __int64 v62; // rbx
  UnBCL::String *v63; // rax
  const char *v64; // rax
  struct tagLOG_PARTIAL_MSG *v65; // rax
  struct UnBCL::String *v66; // rax
  _BYTE v68[24]; // [rsp+78h] [rbp-90h] BYREF
  void **v69; // [rsp+90h] [rbp-78h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp-70h]
  _BYTE v71[16]; // [rsp+A0h] [rbp-68h] BYREF
  int v72; // [rsp+B0h] [rbp-58h]
  _BYTE v73[16]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v74[16]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v75[24]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v76[24]; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v77[16]; // [rsp+108h] [rbp+0h] BYREF
  __int64 v78; // [rsp+118h] [rbp+10h]

  v78 = -2;
  v5 = this;
  v6 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v68, L"SetupPlatform.ini", a3, a4);
  v7 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))a2)(a2);
  v8 = UnBCL::Path::Combine(v7, v6);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v74, v8);
  UnBCL::String::~String((UnBCL::String *)v68);
  v9 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v74);
  CString = UnBCL::String::get_CString(v9);
  v11 = SPReadConfigValue(L"Parameters", L"MigrationScope", CString);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v77, v11);
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v77) )
  {
    P = UnBCL::SmartPtr<UnBCL::String>::get_P(v77);
    v19 = SPGetMigScopeFromString(P);
    goto LABEL_8;
  }
  LastError = GetLastError();
  v13 = LastError;
  if ( (unsigned int)(LastError - 2) <= 1 )
  {
    v19 = 0;
    v5 = this;
LABEL_8:
    v21 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v68, L"InstallICB");
    v23 = SPGetStoredBOOL(a2, v21, v22);
    UnBCL::String::~String((UnBCL::String *)v68);
    v24 = v19 >= 2;
    v25 = v19 == 5;
    v26 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v68, L"FreezeProfilesFolder");
    v72 = SPGetStoredBOOL(a2, v26, v27);
    UnBCL::String::~String((UnBCL::String *)v68);
    v28 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v74);
    v29 = UnBCL::String::get_CString(v28);
    v30 = SPReadConfigValue(L"Parameters", L"DisableShiftF10", v29);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v71, v30);
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v71) )
    {
      v31 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v75, L"TRUE");
      v32 = 1;
      v33 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v71);
      v38 = 1;
      if ( UnBCL::String::Compare(v33, v31, 1) )
      {
        v34 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v76, L"Yes");
        v32 = 3;
        v35 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v71);
        if ( UnBCL::String::Compare(v35, v34, 1) )
        {
          v36 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v68, L"1");
          v32 = 7;
          v37 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v71);
          if ( UnBCL::String::Compare(v37, v36, 1) )
            v38 = 0;
        }
      }
      if ( (v32 & 4) != 0 )
      {
        v32 &= ~4u;
        UnBCL::String::~String((UnBCL::String *)v68);
      }
      if ( (v32 & 2) != 0 )
      {
        v32 &= ~2u;
        UnBCL::String::~String((UnBCL::String *)v76);
      }
      if ( (v32 & 1) != 0 )
        UnBCL::String::~String((UnBCL::String *)v75);
      if ( v38 )
      {
        v39 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v68, L"Setup\\Scripts");
        v40 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v5 + 224);
        v41 = UnBCL::Path::Combine(v40, v39);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v73, v41);
        UnBCL::String::~String((UnBCL::String *)v68);
        v42 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v76, L"disablecmdrequest.tag");
        v43 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v73);
        v44 = UnBCL::Path::Combine(v43, v42);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v75, v44);
        UnBCL::String::~String((UnBCL::String *)v76);
        v45 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v73);
        v46 = UnBCL::String::get_CString(v45);
        if ( !(unsigned int)CreatePath(v46) )
        {
          v47 = GetLastError();
          v48 = v47 < 0;
          if ( v47 > 0 )
            v48 = 1;
          if ( v48 )
          {
            v49 = GetLastError();
            v13 = v49;
            if ( v49 > 0 )
              v13 = (unsigned __int16)v49 | 0x80070000;
          }
          else
          {
            v13 = -2147467259;
          }
          v50 = GetLastError();
          v51 = CurrentIP();
          v52 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v73);
          v53 = (const char *)UnBCL::String::get_CString(v52);
          v54 = ConstructPartialMsgW(0x2000000u, "Failed to create path %s. hr = 0x%08X", v53, v13);
          WdsSetupLogMessageW(
            v54,
            819200,
            L"D",
            0,
            3717,
            L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
            L"CPrepareNewOSForFirstBoot::DoExecute",
            v51,
            v50,
            0,
            0);
LABEL_29:
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v75);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v73);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v71);
          goto LABEL_42;
        }
        v55 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v75);
        v56 = UnBCL::String::get_CString(v55);
        FileW = CreateFileW(v56, 0, 3u, 0, 1u, 0x80u, 0);
        v69 = &RAII::CAutoCleanup<void *>::`vftable';
        hObject = FileW;
        if ( (unsigned __int64)(*(_QWORD *)RAII::CAutoCleanupBase<VdsVolumePathEnumerator *>::operator&(&v69) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
        {
          v60 = GetLastError();
          v13 = v60;
          if ( v60 != 80 )
          {
            if ( v60 > 0 )
              v13 = (unsigned __int16)v60 | 0x80070000;
            v61 = GetLastError();
            v62 = CurrentIP();
            v63 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v75);
            v64 = (const char *)UnBCL::String::get_CString(v63);
            v65 = ConstructPartialMsgW(0x2000000u, "Failed to create file %s. hr = 0x%08X", v64, v13);
            WdsSetupLogMessageW(
              v65,
              819200,
              L"D",
              0,
              3741,
              L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
              L"CPrepareNewOSForFirstBoot::DoExecute",
              v62,
              v61,
              0,
              0);
            v69 = &RAII::CAutoCleanup<void *>::`vftable';
            if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            {
              CloseHandle(hObject);
              hObject = 0;
            }
            goto LABEL_29;
          }
          v5 = this;
        }
        else
        {
          v58 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v74);
          v59 = UnBCL::String::get_CString(v58);
          SPWriteConfigValue(L"Parameters", L"DeleteDisableCmdFile", L"Yes", v59);
        }
        v69 = &RAII::CAutoCleanup<void *>::`vftable';
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          CloseHandle(hObject);
          hObject = 0;
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v75);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v73);
      }
    }
    v66 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)v5 + 224);
    SPModifyOfflineHives(v23, v24, v25, v72, v66);
  }
  if ( LastError > 0 )
    v13 = (unsigned __int16)LastError | 0x80070000;
  v14 = GetLastError();
  v15 = CurrentIP();
  v16 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v74);
  v17 = (const char *)UnBCL::String::get_CString(v16);
  v18 = ConstructPartialMsgW(0x2000000u, "Failed to read the migration scope from %s. hr = 0x%08X", v17, v13);
  WdsSetupLogMessageW(
    v18,
    819200,
    L"D",
    0,
    3686,
    L"base\\ntsetup\\setupplatform\\lib\\src\\boothandling.cpp",
    L"CPrepareNewOSForFirstBoot::DoExecute",
    v15,
    v14,
    0,
    0);
LABEL_42:
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v77);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v74);
  return v13;
}

```

## disassembly

```asm
0x18013fc30  mov     rax, rsp
0x18013fc33  mov     [rax+8], rcx
0x18013fc37  push    rbp
0x18013fc38  push    rsi
0x18013fc39  push    rdi
0x18013fc3a  push    r12
0x18013fc3c  push    r13
0x18013fc3e  push    r14
0x18013fc40  push    r15
0x18013fc42  lea     rbp, [rax-68h]
0x18013fc46  sub     rsp, 130h
0x18013fc4d  mov     [rbp+60h+var_50], 0FFFFFFFFFFFFFFFEh
0x18013fc55  mov     [rax+18h], rbx
0x18013fc59  mov     r12, rdx
0x18013fc5c  mov     rsi, rcx
0x18013fc5f  xor     edi, edi
0x18013fc61  mov     dword ptr [rbp+60h+arg_8], edi
0x18013fc64  lea     rdx, aSetupplatformI; "SetupPlatform.ini"
0x18013fc6b  lea     rcx, [rsp+160h+var_F0]
0x18013fc70  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18013fc76  mov     rbx, rax
0x18013fc79  mov     r8, [r12]
0x18013fc7d  mov     rcx, r12
0x18013fc80  mov     rax, [r8]
0x18013fc83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013fc88  mov     rdx, rbx
0x18013fc8b  mov     rcx, rax
0x18013fc8e  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18013fc94  mov     rdx, rax
0x18013fc97  lea     rcx, [rbp+60h+var_A0]
0x18013fc9b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18013fca1  nop
0x18013fca2  lea     rcx, [rsp+160h+var_F0]
0x18013fca7  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18013fcad  lea     rcx, [rbp+60h+var_A0]
0x18013fcb1  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18013fcb7  mov     rcx, rax
0x18013fcba  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18013fcc0  mov     r8, rax; lpFileName
0x18013fcc3  lea     rdx, aMigrationscope; "MigrationScope"
0x18013fcca  lea     rcx, szSection; "Parameters"
0x18013fcd1  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x18013fcd6  mov     rdx, rax
0x18013fcd9  lea     rcx, [rbp+60h+var_60]
0x18013fcdd  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18013fce3  nop
0x18013fce4  lea     rcx, [rbp+60h+var_60]
0x18013fce8  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18013fcee  test    rax, rax
0x18013fcf1  jnz     loc_18013FDB2
0x18013fcf7  call    cs:__imp_GetLastError
0x18013fcfd  mov     esi, eax
0x18013fcff  lea     ecx, [rax-2]
0x18013fd02  cmp     ecx, 1
0x18013fd05  jbe     loc_18013FDAA
0x18013fd0b  test    eax, eax
0x18013fd0d  jle     short loc_18013FD18
0x18013fd0f  movzx   esi, ax
0x18013fd12  or      esi, 80070000h
0x18013fd18  call    cs:__imp_GetLastError
0x18013fd1e  mov     edi, eax
0x18013fd20  call    cs:__imp_CurrentIP
0x18013fd26  mov     rbx, rax
0x18013fd29  lea     rcx, [rbp+60h+var_A0]
0x18013fd2d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18013fd33  mov     rcx, rax
0x18013fd36  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18013fd3c  mov     r8, rax
0x18013fd3f  mov     r9d, esi
0x18013fd42  lea     rdx, aFailedToReadTh_0; "Failed to read the migration scope from"...
0x18013fd49  mov     ecx, 2000000h; unsigned int
0x18013fd4e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18013fd53  mov     [rsp+160h+var_110], 0
0x18013fd5b  mov     [rsp+160h+var_118], 0
0x18013fd64  mov     dword ptr [rsp+160h+var_120], edi
0x18013fd68  mov     [rsp+160h+var_128], rbx
0x18013fd6d  lea     rcx, aCpreparenewosf_0; "CPrepareNewOSForFirstBoot::DoExecute"
0x18013fd74  mov     [rsp+160h+hTemplateFile], rcx
0x18013fd79  lea     rcx, aBaseNtsetupSet_27; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18013fd80  mov     qword ptr [rsp+160h+dwFlagsAndAttributes], rcx
0x18013fd85  mov     [rsp+160h+dwCreationDisposition], 0E66h
0x18013fd8d  xor     r9d, r9d
0x18013fd90  lea     r8, aD_0; "D"
0x18013fd97  mov     edx, 0C8000h
0x18013fd9c  mov     rcx, rax
0x18013fd9f  call    cs:__imp_WdsSetupLogMessageW
0x18013fda5  jmp     loc_180140603
0x18013fdaa  xor     ebx, ebx
0x18013fdac  mov     rsi, [rbp+60h+arg_0]
0x18013fdb0  jmp     short loc_18013FDC6
0x18013fdb2  lea     rcx, [rbp+60h+var_60]
0x18013fdb6  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18013fdbc  mov     rcx, rax
0x18013fdbf  call    ?SPGetMigScopeFromString@@YA?AW4SP_MIG_SCOPE@SetupPlatform@@PEAVString@UnBCL@@@Z; SPGetMigScopeFromString(UnBCL::String *)
0x18013fdc4  mov     ebx, eax
0x18013fdc6  lea     rdx, aInstallicb; "InstallICB"
0x18013fdcd  lea     rcx, [rsp+160h+var_F0]
0x18013fdd2  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18013fdd8  nop
0x18013fdd9  mov     rdx, rax; struct UnBCL::String *
0x18013fddc  mov     rcx, r12; struct IExecutionContext *
0x18013fddf  call    ?SPGetStoredBOOL@@YAHPEAUIExecutionContext@@PEAVString@UnBCL@@H@Z; SPGetStoredBOOL(IExecutionContext *,UnBCL::String *,int)
0x18013fde4  mov     r13d, eax
0x18013fde7  lea     rcx, [rsp+160h+var_F0]
0x18013fdec  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18013fdf2  xor     r14d, r14d
0x18013fdf5  cmp     ebx, 2
0x18013fdf8  setnl   r14b
0x18013fdfc  xor     r15d, r15d
0x18013fdff  cmp     ebx, 5
0x18013fe02  setz    r15b
0x18013fe06  lea     rdx, aFreezeprofiles; "FreezeProfilesFolder"
0x18013fe0d  lea     rcx, [rsp+160h+var_F0]
0x18013fe12  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18013fe18  nop
0x18013fe19  mov     rdx, rax; struct UnBCL::String *
0x18013fe1c  mov     rcx, r12; struct IExecutionContext *
0x18013fe1f  call    ?SPGetStoredBOOL@@YAHPEAUIExecutionContext@@PEAVString@UnBCL@@H@Z; SPGetStoredBOOL(IExecutionContext *,UnBCL::String *,int)
0x18013fe24  mov     [rbp+60h+var_B8], eax
0x18013fe27  lea     rcx, [rsp+160h+var_F0]
0x18013fe2c  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18013fe32  lea     rcx, [rbp+60h+var_A0]
0x18013fe36  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18013fe3c  mov     rcx, rax
0x18013fe3f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18013fe45  mov     r8, rax; lpFileName
0x18013fe48  lea     rdx, aDisableshiftf1; "DisableShiftF10"
0x18013fe4f  lea     rcx, szSection; "Parameters"
0x18013fe56  call    ?SPReadConfigValue@@YAPEAVString@UnBCL@@PEBG00@Z; SPReadConfigValue(ushort const *,ushort const *,ushort const *)
0x18013fe5b  mov     rdx, rax
0x18013fe5e  lea     rcx, [rbp+60h+var_C8]
0x18013fe62  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18013fe68  nop
0x18013fe69  lea     rcx, [rbp+60h+var_C8]
0x18013fe6d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18013fe73  test    rax, rax
0x18013fe76  jz      loc_180140296
0x18013fe7c  lea     rdx, aTrue_1; "TRUE"
0x18013fe83  lea     rcx, [rbp+60h+var_90]
0x18013fe87  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18013fe8d  mov     rbx, rax
0x18013fe90  mov     edi, 1
0x18013fe95  mov     dword ptr [rbp+60h+arg_8], edi
0x18013fe98  lea     rcx, [rbp+60h+var_C8]
0x18013fe9c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18013fea2  mov     r8d, edi
0x18013fea5  mov     rdx, rbx
0x18013fea8  mov     rcx, rax
0x18013feab  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBV12@0H@Z; UnBCL::String::Compare(UnBCL::String const *,UnBCL::String const *,int)
0x18013feb1  test    eax, eax
0x18013feb3  jz      short loc_18013FF2E
0x18013feb5  lea     rdx, aYes_1; "Yes"
0x18013febc  lea     rcx, [rbp+60h+var_78]
0x18013fec0  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18013fec6  mov     rbx, rax
0x18013fec9  mov     edi, 3
0x18013fece  mov     dword ptr [rbp+60h+arg_8], edi
0x18013fed1  lea     rcx, [rbp+60h+var_C8]
0x18013fed5  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18013fedb  lea     r8d, [rdi-2]
0x18013fedf  mov     rdx, rbx
0x18013fee2  mov     rcx, rax
0x18013fee5  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBV12@0H@Z; UnBCL::String::Compare(UnBCL::String const *,UnBCL::String const *,int)
0x18013feeb  test    eax, eax
0x18013feed  jz      short loc_18013FF2E
0x18013feef  lea     rdx, Value; "1"
0x18013fef6  lea     rcx, [rsp+160h+var_F0]
0x18013fefb  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18013ff01  mov     rbx, rax
0x18013ff04  mov     edi, 7
0x18013ff09  mov     dword ptr [rbp+60h+arg_8], edi
0x18013ff0c  lea     rcx, [rbp+60h+var_C8]
0x18013ff10  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18013ff16  lea     r8d, [rdi-6]
0x18013ff1a  mov     rdx, rbx
0x18013ff1d  mov     rcx, rax
0x18013ff20  call    cs:__imp_?Compare@String@UnBCL@@SAHPEBV12@0H@Z; UnBCL::String::Compare(UnBCL::String const *,UnBCL::String const *,int)
0x18013ff26  test    eax, eax
0x18013ff28  jz      short loc_18013FF2E
0x18013ff2a  xor     bl, bl
0x18013ff2c  jmp     short loc_18013FF30
0x18013ff2e  mov     bl, 1
0x18013ff30  test    dil, 4
0x18013ff34  jz      short loc_18013FF45
0x18013ff36  and     edi, 0FFFFFFFBh
0x18013ff39  lea     rcx, [rsp+160h+var_F0]
0x18013ff3e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18013ff44  nop
0x18013ff45  test    dil, 2
0x18013ff49  jz      short loc_18013FF59
0x18013ff4b  and     edi, 0FFFFFFFDh
0x18013ff4e  lea     rcx, [rbp+60h+var_78]
0x18013ff52  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18013ff58  nop
0x18013ff59  test    dil, 1
0x18013ff5d  jz      short loc_18013FF6C
0x18013ff5f  and     edi, 0FFFFFFFEh
0x18013ff62  lea     rcx, [rbp+60h+var_90]
0x18013ff66  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18013ff6c  test    bl, bl
0x18013ff6e  jz      loc_180140296
0x18013ff74  lea     rdx, aSetupScripts; "Setup\\Scripts"
0x18013ff7b  lea     rcx, [rsp+160h+var_F0]
0x18013ff80  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18013ff86  mov     rbx, rax
0x18013ff89  lea     rcx, [rsi+0E0h]
0x18013ff90  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18013ff96  mov     rdx, rbx
0x18013ff99  mov     rcx, rax
0x18013ff9c  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18013ffa2  mov     rdx, rax
0x18013ffa5  lea     rcx, [rbp+60h+var_B0]
0x18013ffa9  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18013ffaf  nop
0x18013ffb0  lea     rcx, [rsp+160h+var_F0]
0x18013ffb5  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18013ffbb  lea     rdx, aDisablecmdrequ; "disablecmdrequest.tag"
0x18013ffc2  lea     rcx, [rbp+60h+var_78]
0x18013ffc6  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18013ffcc  mov     rbx, rax
0x18013ffcf  lea     rcx, [rbp+60h+var_B0]
0x18013ffd3  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18013ffd9  mov     rdx, rbx
0x18013ffdc  mov     rcx, rax
0x18013ffdf  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x18013ffe5  mov     rdx, rax
0x18013ffe8  lea     rcx, [rbp+60h+var_90]
0x18013ffec  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18013fff2  nop
0x18013fff3  lea     rcx, [rbp+60h+var_78]
0x18013fff7  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x18013fffd  lea     rcx, [rbp+60h+var_B0]
0x180140001  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180140007  mov     rcx, rax
0x18014000a  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180140010  mov     rcx, rax
0x180140013  call    CreatePath
0x180140018  test    eax, eax
0x18014001a  jnz     loc_1801400F2
0x180140020  call    cs:__imp_GetLastError
0x180140026  mov     ebx, 80070000h
0x18014002b  test    eax, eax
0x18014002d  jle     short loc_180140036
0x18014002f  movzx   eax, ax
0x180140032  or      eax, ebx
0x180140034  test    eax, eax
0x180140036  jns     short loc_18014004B
0x180140038  call    cs:__imp_GetLastError
0x18014003e  mov     esi, eax
0x180140040  test    eax, eax
0x180140042  jle     short loc_180140050
0x180140044  movzx   esi, ax
0x180140047  or      esi, ebx
0x180140049  jmp     short loc_180140050
0x18014004b  mov     esi, 80004005h
0x180140050  call    cs:__imp_GetLastError
0x180140056  mov     edi, eax
0x180140058  call    cs:__imp_CurrentIP
0x18014005e  mov     rbx, rax
0x180140061  lea     rcx, [rbp+60h+var_B0]
0x180140065  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18014006b  mov     rcx, rax
0x18014006e  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180140074  mov     r8, rax
0x180140077  mov     r9d, esi
0x18014007a  lea     rdx, aFailedToCreate_30; "Failed to create path %s. hr = 0x%08X"
0x180140081  mov     ecx, 2000000h; unsigned int
0x180140086  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18014008b  mov     [rsp+160h+var_110], 0
0x180140093  mov     [rsp+160h+var_118], 0
0x18014009c  mov     dword ptr [rsp+160h+var_120], edi
0x1801400a0  mov     [rsp+160h+var_128], rbx
0x1801400a5  lea     rcx, aCpreparenewosf_0; "CPrepareNewOSForFirstBoot::DoExecute"
0x1801400ac  mov     [rsp+160h+hTemplateFile], rcx
0x1801400b1  lea     rcx, aBaseNtsetupSet_27; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801400b8  mov     qword ptr [rsp+160h+dwFlagsAndAttributes], rcx
0x1801400bd  mov     [rsp+160h+dwCreationDisposition], 0E85h
0x1801400c5  xor     r9d, r9d
0x1801400c8  lea     r8, aD_0; "D"
0x1801400cf  mov     edx, 0C8000h
0x1801400d4  mov     rcx, rax
0x1801400d7  call    cs:__imp_WdsSetupLogMessageW
0x1801400dd  nop
0x1801400de  lea     rcx, [rbp+60h+var_90]
0x1801400e2  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1801400e8  nop
0x1801400e9  lea     rcx, [rbp+60h+var_B0]
0x1801400ed  jmp     loc_1801405F1
0x1801400f2  lea     rcx, [rbp+60h+var_90]
0x1801400f6  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1801400fc  mov     rcx, rax
0x1801400ff  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180140105  mov     rcx, rax; lpFileName
0x180140108  mov     [rsp+160h+hTemplateFile], 0; hTemplateFile
0x180140111  mov     [rsp+160h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180140119  mov     [rsp+160h+dwCreationDisposition], 1; dwCreationDisposition
0x180140121  xor     r9d, r9d; lpSecurityAttributes
0x180140124  xor     edx, edx; dwDesiredAccess
0x180140126  lea     r8d, [r9+3]; dwShareMode
0x18014012a  call    cs:__imp_CreateFileW
  ... truncated ...
```
