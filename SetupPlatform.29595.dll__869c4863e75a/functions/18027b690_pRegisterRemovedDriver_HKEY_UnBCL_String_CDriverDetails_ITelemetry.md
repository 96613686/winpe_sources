# pRegisterRemovedDriver(HKEY__ *,UnBCL::String *,CDriverDetails *,ITelemetry *)

- ea: `0x18027b690`
- end: `0x18027bfef`
- name: `?pRegisterRemovedDriver@@YAHPEAUHKEY__@@PEAVString@UnBCL@@PEAVCDriverDetails@@PEAUITelemetry@@@Z`
- size: `2399`
- prototype: `__int64 __fastcall(HKEY hKey, struct UnBCL::String *, struct CDriverDetails *, struct ITelemetry *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1802724e8`

## callees

- `0x180057dec`
- `0x18027b690`
- `0x180509010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18027be40`
- `ADVAPI32!RegCloseKey` at `0x18027bedd`
- `ADVAPI32!RegCloseKey` at `0x18027be40`
- `ADVAPI32!RegCloseKey` at `0x18027bedd`
- `ADVAPI32!RegSetValueExW` at `0x18027b7f8`
- `ADVAPI32!RegSetValueExW` at `0x18027b906`
- `ADVAPI32!RegSetValueExW` at `0x18027b9fc`
- `ADVAPI32!RegSetValueExW` at `0x18027baf0`
- `ADVAPI32!RegSetValueExW` at `0x18027bbe4`
- `ADVAPI32!RegSetValueExW` at `0x18027b7f8`
- `ADVAPI32!RegSetValueExW` at `0x18027b906`
- `ADVAPI32!RegSetValueExW` at `0x18027b9fc`
- `ADVAPI32!RegSetValueExW` at `0x18027baf0`
- `ADVAPI32!RegSetValueExW` at `0x18027bbe4`
- `ADVAPI32!RegCreateKeyExW` at `0x18027b726`
- `ADVAPI32!RegCreateKeyExW` at `0x18027b7a4`
- `ADVAPI32!RegCreateKeyExW` at `0x18027b726`
- `ADVAPI32!RegCreateKeyExW` at `0x18027b7a4`
- `KERNEL32!GetLastError` at `0x18027b824`
- `KERNEL32!GetLastError` at `0x18027b91a`
- `KERNEL32!GetLastError` at `0x18027ba10`
- `KERNEL32!GetLastError` at `0x18027bb08`
- `KERNEL32!GetLastError` at `0x18027bbfc`
- `KERNEL32!GetLastError` at `0x18027bdb6`
- `KERNEL32!GetLastError` at `0x18027be53`
- `KERNEL32!GetLastError` at `0x18027bef7`
- `KERNEL32!GetLastError` at `0x18027bf6c`
- `KERNEL32!GetLastError` at `0x18027b824`
- `KERNEL32!GetLastError` at `0x18027b91a`
- `KERNEL32!GetLastError` at `0x18027ba10`
- `KERNEL32!GetLastError` at `0x18027bb08`
- `KERNEL32!GetLastError` at `0x18027bbfc`
- `KERNEL32!GetLastError` at `0x18027bdb6`
- `KERNEL32!GetLastError` at `0x18027be53`
- `KERNEL32!GetLastError` at `0x18027bef7`
- `KERNEL32!GetLastError` at `0x18027bf6c`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18027b7c6`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18027b8c8`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18027b9be`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18027bab4`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18027bba8`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18027b7c6`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18027b8c8`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18027b9be`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18027bab4`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18027bba8`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18027b744`
- `unbcl!?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x18027b744`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027b6df`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027b73b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027b8ad`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027b9a3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027ba99`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027bb8d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027bc89`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027bce0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027bd29`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027bd6e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027b6df`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027b73b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027b8ad`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027b9a3`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027ba99`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027bb8d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027bc89`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027bce0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027bd29`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18027bd6e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b764`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b839`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b8bf`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b8d8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b92f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b9b5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b9ce`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027ba25`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027baab`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bac4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bb1d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bb9f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bbb8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bc11`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bc9e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bcee`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bd37`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bd7c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bdcb`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027be68`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b764`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b839`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b8bf`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b8d8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b92f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b9b5`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027b9ce`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027ba25`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027baab`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bac4`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bb1d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bb9f`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bbb8`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bc11`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bc9e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bcee`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bd37`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bd7c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027bdcb`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18027be68`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027b76d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027b7d6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027b842`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027b8e1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027b938`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027b9d7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027ba2e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bacd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bb26`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bbc1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bc1a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bca7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bcf7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bd40`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bd85`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bdd4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027be71`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027b76d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027b7d6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027b842`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027b8e1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027b938`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027b9d7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027ba2e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bacd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bb26`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bbc1`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bc1a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bca7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bcf7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bd40`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bd85`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027bdd4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18027be71`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027beef`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18027beef`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18027b751`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18027b751`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027b89c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027b992`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027ba88`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027bb80`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027bc74`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027be36`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027bed3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027bf61`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027bfd3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027b89c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027b992`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027ba88`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027bb80`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027bc74`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027be36`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027bed3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027bf61`
- `WDSCORE!WdsSetupLogMessageW` at `0x18027bfd3`
- `WDSCORE!CurrentIP` at `0x18027b82c`
- `WDSCORE!CurrentIP` at `0x18027b922`
- `WDSCORE!CurrentIP` at `0x18027ba18`
- `WDSCORE!CurrentIP` at `0x18027bb10`
- `WDSCORE!CurrentIP` at `0x18027bc04`
- `WDSCORE!CurrentIP` at `0x18027bdbe`
- `WDSCORE!CurrentIP` at `0x18027be5b`
- `WDSCORE!CurrentIP` at `0x18027beff`
- `WDSCORE!CurrentIP` at `0x18027bf74`
- `WDSCORE!CurrentIP` at `0x18027b82c`
- `WDSCORE!CurrentIP` at `0x18027b922`
- `WDSCORE!CurrentIP` at `0x18027ba18`
- `WDSCORE!CurrentIP` at `0x18027bb10`
- `WDSCORE!CurrentIP` at `0x18027bc04`
- `WDSCORE!CurrentIP` at `0x18027bdbe`
- `WDSCORE!CurrentIP` at `0x18027be5b`
- `WDSCORE!CurrentIP` at `0x18027beff`
- `WDSCORE!CurrentIP` at `0x18027bf74`

## string_xrefs

- `0x18027b801`: `pRegisterRemovedDriver`
- `0x18027be04`: `pRegisterRemovedDriver`
- `0x18027bea1`: `pRegisterRemovedDriver`
- `0x18027bf2f`: `pRegisterRemovedDriver`
- `0x18027bfa1`: `pRegisterRemovedDriver`
- `0x18027b71c`: `Setup\RemovedDrivers`
- `0x18027bf7d`: `RegisterRemovedDriver: Invalid arguments`
- `0x18027bd05`: `RemovedDriverClassName`
- `0x18027bcb5`: `RemovedDriverProviderName`
- `0x18027bd91`: `RemovedDriverVersion`
- `0x18027bd4e`: `RemovedDriverClassGUID`
- `0x18027bde0`: `Driver entry key %s already exists.`
- `0x18027bf0b`: `Error while creating/opening the RemovedDrivers key. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall pRegisterRemovedDriver(
        HKEY hKey,
        struct UnBCL::String *a2,
        struct CDriverDetails *a3,
        struct ITelemetry *a4)
{
  LSTATUS v8; // r15d
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *FileName; // rax
  UnBCL::String *v11; // rax
  const WCHAR *CString; // rax
  LSTATUS v13; // r14d
  DWORD v14; // ebx
  const BYTE *v15; // rax
  DWORD v16; // edi
  __int64 v17; // rbx
  UnBCL::String *v18; // rax
  const char *v19; // rax
  struct tagLOG_PARTIAL_MSG *v20; // rax
  UnBCL::String *v21; // rax
  DWORD v22; // ebx
  UnBCL::String *v23; // rax
  const BYTE *v24; // rax
  DWORD v25; // edi
  __int64 v26; // rbx
  UnBCL::String *v27; // rax
  const char *v28; // rax
  struct tagLOG_PARTIAL_MSG *v29; // rax
  UnBCL::String *v30; // rax
  DWORD v31; // ebx
  UnBCL::String *v32; // rax
  const BYTE *v33; // rax
  DWORD v34; // edi
  __int64 v35; // rbx
  UnBCL::String *v36; // rax
  const char *v37; // rax
  struct tagLOG_PARTIAL_MSG *v38; // rax
  UnBCL::String *v39; // rax
  DWORD v40; // ebx
  UnBCL::String *v41; // rax
  const BYTE *v42; // rax
  DWORD v43; // edi
  __int64 v44; // rbx
  UnBCL::String *v45; // rax
  const char *v46; // rax
  struct tagLOG_PARTIAL_MSG *v47; // rax
  char *v48; // rsi
  UnBCL::String *v49; // rax
  DWORD v50; // ebx
  UnBCL::String *v51; // rax
  const BYTE *v52; // rax
  DWORD v53; // edi
  __int64 v54; // rbx
  UnBCL::String *v55; // rax
  const char *v56; // rax
  struct tagLOG_PARTIAL_MSG *v57; // rax
  void (__fastcall *v58)(struct ITelemetry *, const wchar_t *, const wchar_t *, const wchar_t *); // r14
  char *v59; // rdi
  const wchar_t *v60; // rbx
  UnBCL::String *v61; // rax
  const wchar_t *v62; // rax
  void (__fastcall *v63)(struct ITelemetry *, const wchar_t *, const wchar_t *, const wchar_t *); // r14
  char *v64; // rdi
  UnBCL::String *v65; // rax
  const wchar_t *v66; // rax
  void (__fastcall *v67)(struct ITelemetry *, const wchar_t *, const wchar_t *, const wchar_t *); // r14
  char *v68; // rdi
  UnBCL::String *v69; // rax
  const wchar_t *v70; // rax
  void (__fastcall *v71)(struct ITelemetry *, const wchar_t *, const wchar_t *, const wchar_t *); // rdi
  UnBCL::String *v72; // rax
  DWORD v73; // edi
  __int64 v74; // rbx
  UnBCL::String *v75; // rax
  const char *v76; // rax
  struct tagLOG_PARTIAL_MSG *v77; // rax
  DWORD v78; // edi
  __int64 v79; // rbx
  UnBCL::String *v80; // rax
  const char *v81; // rax
  struct tagLOG_PARTIAL_MSG *v82; // rax
  DWORD LastError; // edi
  __int64 v84; // rbx
  struct tagLOG_PARTIAL_MSG *v85; // rax
  DWORD v87; // edi
  __int64 v88; // rbx
  struct tagLOG_PARTIAL_MSG *v89; // rax
  LSTATUS v90; // [rsp+60h] [rbp-39h]
  LSTATUS v91; // [rsp+60h] [rbp-39h]
  LSTATUS v92; // [rsp+60h] [rbp-39h]
  LSTATUS v93; // [rsp+60h] [rbp-39h]
  LSTATUS v94; // [rsp+60h] [rbp-39h]
  HKEY phkResult; // [rsp+68h] [rbp-31h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-29h] BYREF
  HKEY hKeya; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v98[16]; // [rsp+80h] [rbp-19h] BYREF
  char *v99; // [rsp+90h] [rbp-9h]
  char *v100; // [rsp+98h] [rbp-1h]
  char *v101; // [rsp+A0h] [rbp+7h]
  __int64 v102; // [rsp+A8h] [rbp+Fh]
  BOOL v103; // [rsp+100h] [rbp+67h]
  int v104; // [rsp+100h] [rbp+67h]

  v102 = -2;
  if ( hKey && a2 && a3 && UnBCL::SmartPtr<UnBCL::String>::get_P((char *)a3 + 16) )
  {
    v103 = 0;
    hKeya = 0;
    v8 = RegCreateKeyExW(hKey, L"Setup\\RemovedDrivers", 0, 0, 0, 0xF003Fu, 0, &hKeya, 0);
    if ( v8 )
    {
      LastError = GetLastError();
      v84 = CurrentIP();
      v85 = ConstructPartialMsgW(0x2000000u, "Error while creating/opening the RemovedDrivers key. Error: 0x%08X", v8);
      WdsSetupLogMessageW(
        v85,
        819200,
        L"D",
        0,
        1432,
        L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
        L"pRegisterRemovedDriver",
        v84,
        LastError,
        0,
        0);
    }
    else
    {
      P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)a3 + 16);
      FileName = UnBCL::Path::GetFileName(P);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v98, FileName);
      phkResult = 0;
      dwDisposition = 0;
      v11 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
      CString = UnBCL::String::get_CString(v11);
      v13 = RegCreateKeyExW(hKeya, CString, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
      if ( v13 )
      {
        v78 = GetLastError();
        v79 = CurrentIP();
        v80 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
        v81 = (const char *)UnBCL::String::get_CString(v80);
        v82 = ConstructPartialMsgW(0x2000000u, "Error while creating the driver entry key %s. Error: 0x%08X", v81, v13);
        WdsSetupLogMessageW(
          v82,
          819200,
          L"D",
          0,
          1420,
          L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
          L"pRegisterRemovedDriver",
          v79,
          v78,
          0,
          0);
      }
      else
      {
        if ( dwDisposition == 1 )
        {
          v104 = 0;
          v14 = 2 * UnBCL::String::get_Length(a2) + 2;
          v15 = (const BYTE *)UnBCL::String::get_CString(a2);
          v90 = RegSetValueExW(phkResult, L"ModuleName", 0, 1u, v15, v14);
          if ( v90 )
          {
            v104 = 1;
            v16 = GetLastError();
            v17 = CurrentIP();
            v18 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
            v19 = (const char *)UnBCL::String::get_CString(v18);
            v20 = ConstructPartialMsgW(0x2000000u, "Error creating ModuleName value for %s. Error: 0x%08X", v19, v90);
            WdsSetupLogMessageW(
              v20,
              819200,
              L"D",
              0,
              1297,
              L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
              L"pRegisterRemovedDriver",
              v17,
              v16,
              0,
              0);
          }
          v99 = (char *)a3 + 80;
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)a3 + 80) )
          {
            v21 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)a3 + 80);
            v22 = 2 * UnBCL::String::get_Length(v21) + 2;
            v23 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)a3 + 80);
            v24 = (const BYTE *)UnBCL::String::get_CString(v23);
            v91 = RegSetValueExW(phkResult, L"Provider", 0, 1u, v24, v22);
            if ( v91 )
            {
              v104 = 1;
              v25 = GetLastError();
              v26 = CurrentIP();
              v27 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
              v28 = (const char *)UnBCL::String::get_CString(v27);
              v29 = ConstructPartialMsgW(0x2000000u, "Error creating Provider value for %s. Error: 0x%08X", v28, v91);
              WdsSetupLogMessageW(
                v29,
                819200,
                L"D",
                0,
                1319,
                L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
                L"pRegisterRemovedDriver",
                v26,
                v25,
                0,
                0);
            }
          }
          v100 = (char *)a3 + 48;
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)a3 + 48) )
          {
            v30 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)a3 + 48);
            v31 = 2 * UnBCL::String::get_Length(v30) + 2;
            v32 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)a3 + 48);
            v33 = (const BYTE *)UnBCL::String::get_CString(v32);
            v92 = RegSetValueExW(phkResult, L"ClassGUID", 0, 1u, v33, v31);
            if ( v92 )
            {
              v104 = 1;
              v34 = GetLastError();
              v35 = CurrentIP();
              v36 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
              v37 = (const char *)UnBCL::String::get_CString(v36);
              v38 = ConstructPartialMsgW(0x2000000u, "Error creating ClassGUID value for %s. Error: 0x%08X", v37, v92);
              WdsSetupLogMessageW(
                v38,
                819200,
                L"D",
                0,
                1342,
                L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
                L"pRegisterRemovedDriver",
                v35,
                v34,
                0,
                0);
            }
          }
          v101 = (char *)a3 + 64;
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P((char *)a3 + 64) )
          {
            v39 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)a3 + 64);
            v40 = 2 * UnBCL::String::get_Length(v39) + 2;
            v41 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->((char *)a3 + 64);
            v42 = (const BYTE *)UnBCL::String::get_CString(v41);
            v93 = RegSetValueExW(phkResult, L"Class", 0, 1u, v42, v40);
            if ( v93 )
            {
              v104 = 1;
              v43 = GetLastError();
              v44 = CurrentIP();
              v45 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
              v46 = (const char *)UnBCL::String::get_CString(v45);
              v47 = ConstructPartialMsgW(0x2000000u, "Error creating Class value for %s. Error: 0x%08X", v46, v93);
              WdsSetupLogMessageW(
                v47,
                819200,
                L"D",
                0,
                1365,
                L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
                L"pRegisterRemovedDriver",
                v44,
                v43,
                0,
                0);
            }
          }
          v48 = (char *)a3 + 96;
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v48) )
          {
            v49 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v48);
            v50 = 2 * UnBCL::String::get_Length(v49) + 2;
            v51 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v48);
            v52 = (const BYTE *)UnBCL::String::get_CString(v51);
            v94 = RegSetValueExW(phkResult, L"DriverVer", 0, 1u, v52, v50);
            if ( v94 )
            {
              v104 = 1;
              v53 = GetLastError();
              v54 = CurrentIP();
              v55 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
              v56 = (const char *)UnBCL::String::get_CString(v55);
              v57 = ConstructPartialMsgW(0x2000000u, "Error creating DriverVer value for %s. Error: 0x%08X", v56, v94);
              WdsSetupLogMessageW(
                v57,
                819200,
                L"D",
                0,
                1388,
                L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
                L"pRegisterRemovedDriver",
                v54,
                v53,
                0,
                0);
            }
          }
          v58 = *(void (__fastcall **)(struct ITelemetry *, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)a4 + 16LL);
          v59 = v99;
          v60 = &cchOriginalDestLength;
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v99) )
          {
            v61 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v59);
            v62 = UnBCL::String::get_CString(v61);
          }
          else
          {
            v62 = &cchOriginalDestLength;
          }
          v58(a4, L"SP_RETRY_INFO", L"RemovedDriverProviderName", v62);
          v63 = *(void (__fastcall **)(struct ITelemetry *, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)a4 + 16LL);
          v64 = v100;
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v100) )
          {
            v65 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v64);
            v66 = UnBCL::String::get_CString(v65);
          }
          else
          {
            v66 = &cchOriginalDestLength;
          }
          v63(a4, L"SP_RETRY_INFO", L"RemovedDriverClassName", v66);
          v67 = *(void (__fastcall **)(struct ITelemetry *, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)a4 + 16LL);
          v68 = v101;
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v101) )
          {
            v69 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v68);
            v70 = UnBCL::String::get_CString(v69);
          }
          else
          {
            v70 = &cchOriginalDestLength;
          }
          v67(a4, L"SP_RETRY_INFO", L"RemovedDriverClassGUID", v70);
          v71 = *(void (__fastcall **)(struct ITelemetry *, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)a4 + 16LL);
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v48) )
          {
            v72 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v48);
            v60 = UnBCL::String::get_CString(v72);
          }
          v71(a4, L"SP_RETRY_INFO", L"RemovedDriverVersion", v60);
          v103 = v104 == 0;
        }
        else
        {
          v73 = GetLastError();
          v74 = CurrentIP();
          v75 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v98);
          v76 = (const char *)UnBCL::String::get_CString(v75);
          v77 = ConstructPartialMsgW(0x2000000u, "Driver entry key %s already exists.", v76);
          WdsSetupLogMessageW(
            v77,
            819200,
            L"D",
            0,
            1407,
            L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
            L"pRegisterRemovedDriver",
            v74,
            v73,
            0,
            0);
        }
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      RegCloseKey(hKeya);
      hKeya = 0;
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v98);
    }
    return v103;
  }
  else
  {
    v87 = GetLastError();
    v88 = CurrentIP();
    v89 = ConstructPartialMsgW(0x4000000u, "RegisterRemovedDriver: Invalid arguments");
    WdsSetupLogMessageW(
      v89,
      819200,
      L"D",
      0,
      1237,
      L"base\\ntsetup\\setupplatform\\lib\\private\\crashrecovery.cpp",
      L"pRegisterRemovedDriver",
      v88,
      v87,
      0,
      0);
    return 0;
  }
}

```

## disassembly

```asm
0x18027b690  push    rbp
0x18027b692  push    rbx
0x18027b693  push    rsi
0x18027b694  push    rdi
0x18027b695  push    r12
0x18027b697  push    r13
0x18027b699  push    r14
0x18027b69b  push    r15
0x18027b69d  lea     rbp, [rsp-1Fh]
0x18027b6a2  sub     rsp, 0B8h
0x18027b6a9  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFEh
0x18027b6b1  mov     r13, r9
0x18027b6b4  mov     rsi, r8
0x18027b6b7  mov     rdi, rdx
0x18027b6ba  mov     rbx, rcx
0x18027b6bd  xor     r12d, r12d
0x18027b6c0  test    rcx, rcx
0x18027b6c3  jz      loc_18027BF6C
0x18027b6c9  test    rdx, rdx
0x18027b6cc  jz      loc_18027BF6C
0x18027b6d2  test    r8, r8
0x18027b6d5  jz      loc_18027BF6C
0x18027b6db  lea     rcx, [r8+10h]
0x18027b6df  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18027b6e5  test    rax, rax
0x18027b6e8  jz      loc_18027BF6C
0x18027b6ee  mov     [rbp+57h+arg_0], r12d
0x18027b6f2  mov     [rbp+57h+hKey], r12
0x18027b6f6  mov     [rsp+0F0h+lpdwDisposition], r12; lpdwDisposition
0x18027b6fb  lea     rax, [rbp+57h+hKey]
0x18027b6ff  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18027b704  mov     [rsp+0F0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18027b709  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x18027b711  mov     [rsp+0F0h+dwOptions], r12d; dwOptions
0x18027b716  xor     r9d, r9d; lpClass
0x18027b719  xor     r8d, r8d; Reserved
0x18027b71c  lea     rdx, aSetupRemoveddr; "Setup\\RemovedDrivers"
0x18027b723  mov     rcx, rbx; hKey
0x18027b726  call    cs:__imp_RegCreateKeyExW
0x18027b72c  mov     r15d, eax
0x18027b72f  test    eax, eax
0x18027b731  jnz     loc_18027BEF7
0x18027b737  lea     rcx, [rsi+10h]
0x18027b73b  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18027b741  mov     rcx, rax
0x18027b744  call    cs:__imp_?GetFileName@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFileName(UnBCL::String const *)
0x18027b74a  mov     rdx, rax
0x18027b74d  lea     rcx, [rbp+57h+var_70]
0x18027b751  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18027b757  nop
0x18027b758  mov     [rbp+57h+var_88], r12
0x18027b75c  mov     [rbp+57h+dwDisposition], r12d
0x18027b760  lea     rcx, [rbp+57h+var_70]
0x18027b764  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027b76a  mov     rcx, rax
0x18027b76d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18027b773  lea     rcx, [rbp+57h+dwDisposition]
0x18027b777  mov     [rsp+0F0h+lpdwDisposition], rcx; lpdwDisposition
0x18027b77c  lea     rcx, [rbp+57h+var_88]
0x18027b780  mov     [rsp+0F0h+phkResult], rcx; phkResult
0x18027b785  mov     [rsp+0F0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18027b78a  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x18027b792  mov     [rsp+0F0h+dwOptions], r12d; dwOptions
0x18027b797  xor     r9d, r9d; lpClass
0x18027b79a  xor     r8d, r8d; Reserved
0x18027b79d  mov     rdx, rax; lpSubKey
0x18027b7a0  mov     rcx, [rbp+57h+hKey]; hKey
0x18027b7a4  call    cs:__imp_RegCreateKeyExW
0x18027b7aa  mov     r14d, eax
0x18027b7ad  test    eax, eax
0x18027b7af  jnz     loc_18027BE53
0x18027b7b5  cmp     [rbp+57h+dwDisposition], 1
0x18027b7b9  jnz     loc_18027BDB6
0x18027b7bf  mov     [rbp+57h+arg_0], r12d
0x18027b7c3  mov     rcx, rdi
0x18027b7c6  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18027b7cc  lea     ebx, ds:2[rax*2]
0x18027b7d3  mov     rcx, rdi
0x18027b7d6  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18027b7dc  mov     [rsp+0F0h+samDesired], ebx; cbData
0x18027b7e0  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18027b7e5  lea     r9d, [r12+1]; dwType
0x18027b7ea  xor     r8d, r8d; Reserved
0x18027b7ed  lea     rdx, aModulename; "ModuleName"
0x18027b7f4  mov     rcx, [rbp+57h+var_88]; hKey
0x18027b7f8  call    cs:__imp_RegSetValueExW
0x18027b7fe  mov     [rbp+57h+var_90], eax
0x18027b801  lea     r15, aPregisterremov; "pRegisterRemovedDriver"
0x18027b808  lea     r12, aBaseNtsetupSet_57; "base\\ntsetup\\setupplatform\\lib\\priv"...
0x18027b80f  mov     r14d, 0C8000h
0x18027b815  test    eax, eax
0x18027b817  jz      loc_18027B8A2
0x18027b81d  mov     [rbp+57h+arg_0], 1
0x18027b824  call    cs:__imp_GetLastError
0x18027b82a  mov     edi, eax
0x18027b82c  call    cs:__imp_CurrentIP
0x18027b832  mov     rbx, rax
0x18027b835  lea     rcx, [rbp+57h+var_70]
0x18027b839  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027b83f  mov     rcx, rax
0x18027b842  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18027b848  mov     r8, rax
0x18027b84b  mov     r9d, [rbp+57h+var_90]
0x18027b84f  lea     rdx, aErrorCreatingM; "Error creating ModuleName value for %s."...
0x18027b856  mov     ecx, 2000000h; unsigned int
0x18027b85b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18027b860  mov     [rsp+0F0h+var_A0], 0
0x18027b868  mov     [rsp+0F0h+var_A8], 0
0x18027b871  mov     dword ptr [rsp+0F0h+lpdwDisposition], edi
0x18027b875  mov     [rsp+0F0h+phkResult], rbx
0x18027b87a  mov     [rsp+0F0h+lpSecurityAttributes], r15
0x18027b87f  mov     qword ptr [rsp+0F0h+samDesired], r12
0x18027b884  mov     [rsp+0F0h+dwOptions], 511h
0x18027b88c  xor     r9d, r9d
0x18027b88f  lea     r8, aD_0; "D"
0x18027b896  mov     edx, r14d
0x18027b899  mov     rcx, rax
0x18027b89c  call    cs:__imp_WdsSetupLogMessageW
0x18027b8a2  lea     rdi, [rsi+50h]
0x18027b8a6  mov     [rbp+57h+var_60], rdi
0x18027b8aa  mov     rcx, rdi
0x18027b8ad  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18027b8b3  test    rax, rax
0x18027b8b6  jz      loc_18027B998
0x18027b8bc  mov     rcx, rdi
0x18027b8bf  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027b8c5  mov     rcx, rax
0x18027b8c8  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18027b8ce  lea     ebx, ds:2[rax*2]
0x18027b8d5  mov     rcx, rdi
0x18027b8d8  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027b8de  mov     rcx, rax
0x18027b8e1  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18027b8e7  mov     [rsp+0F0h+samDesired], ebx; cbData
0x18027b8eb  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18027b8f0  mov     ebx, 1
0x18027b8f5  mov     r9d, ebx; dwType
0x18027b8f8  xor     r8d, r8d; Reserved
0x18027b8fb  lea     rdx, aProvider_0; "Provider"
0x18027b902  mov     rcx, [rbp+57h+var_88]; hKey
0x18027b906  call    cs:__imp_RegSetValueExW
0x18027b90c  mov     [rbp+57h+var_90], eax
0x18027b90f  test    eax, eax
0x18027b911  jz      loc_18027B998
0x18027b917  mov     [rbp+57h+arg_0], ebx
0x18027b91a  call    cs:__imp_GetLastError
0x18027b920  mov     edi, eax
0x18027b922  call    cs:__imp_CurrentIP
0x18027b928  mov     rbx, rax
0x18027b92b  lea     rcx, [rbp+57h+var_70]
0x18027b92f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027b935  mov     rcx, rax
0x18027b938  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18027b93e  mov     r8, rax
0x18027b941  mov     r9d, [rbp+57h+var_90]
0x18027b945  lea     rdx, aErrorCreatingP; "Error creating Provider value for %s. E"...
0x18027b94c  mov     ecx, 2000000h; unsigned int
0x18027b951  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18027b956  mov     [rsp+0F0h+var_A0], 0
0x18027b95e  mov     [rsp+0F0h+var_A8], 0
0x18027b967  mov     dword ptr [rsp+0F0h+lpdwDisposition], edi
0x18027b96b  mov     [rsp+0F0h+phkResult], rbx
0x18027b970  mov     [rsp+0F0h+lpSecurityAttributes], r15
0x18027b975  mov     qword ptr [rsp+0F0h+samDesired], r12
0x18027b97a  mov     [rsp+0F0h+dwOptions], 527h
0x18027b982  xor     r9d, r9d
0x18027b985  lea     r8, aD_0; "D"
0x18027b98c  mov     edx, r14d
0x18027b98f  mov     rcx, rax
0x18027b992  call    cs:__imp_WdsSetupLogMessageW
0x18027b998  lea     rdi, [rsi+30h]
0x18027b99c  mov     [rbp+57h+var_58], rdi
0x18027b9a0  mov     rcx, rdi
0x18027b9a3  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18027b9a9  test    rax, rax
0x18027b9ac  jz      loc_18027BA8E
0x18027b9b2  mov     rcx, rdi
0x18027b9b5  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027b9bb  mov     rcx, rax
0x18027b9be  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18027b9c4  lea     ebx, ds:2[rax*2]
0x18027b9cb  mov     rcx, rdi
0x18027b9ce  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027b9d4  mov     rcx, rax
0x18027b9d7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18027b9dd  mov     [rsp+0F0h+samDesired], ebx; cbData
0x18027b9e1  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18027b9e6  mov     ebx, 1
0x18027b9eb  mov     r9d, ebx; dwType
0x18027b9ee  xor     r8d, r8d; Reserved
0x18027b9f1  lea     rdx, aClassguid; "ClassGUID"
0x18027b9f8  mov     rcx, [rbp+57h+var_88]; hKey
0x18027b9fc  call    cs:__imp_RegSetValueExW
0x18027ba02  mov     [rbp+57h+var_90], eax
0x18027ba05  test    eax, eax
0x18027ba07  jz      loc_18027BA8E
0x18027ba0d  mov     [rbp+57h+arg_0], ebx
0x18027ba10  call    cs:__imp_GetLastError
0x18027ba16  mov     edi, eax
0x18027ba18  call    cs:__imp_CurrentIP
0x18027ba1e  mov     rbx, rax
0x18027ba21  lea     rcx, [rbp+57h+var_70]
0x18027ba25  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027ba2b  mov     rcx, rax
0x18027ba2e  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18027ba34  mov     r8, rax
0x18027ba37  mov     r9d, [rbp+57h+var_90]
0x18027ba3b  lea     rdx, aErrorCreatingC; "Error creating ClassGUID value for %s. "...
0x18027ba42  mov     ecx, 2000000h; unsigned int
0x18027ba47  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18027ba4c  mov     [rsp+0F0h+var_A0], 0
0x18027ba54  mov     [rsp+0F0h+var_A8], 0
0x18027ba5d  mov     dword ptr [rsp+0F0h+lpdwDisposition], edi
0x18027ba61  mov     [rsp+0F0h+phkResult], rbx
0x18027ba66  mov     [rsp+0F0h+lpSecurityAttributes], r15
0x18027ba6b  mov     qword ptr [rsp+0F0h+samDesired], r12
0x18027ba70  mov     [rsp+0F0h+dwOptions], 53Eh
0x18027ba78  xor     r9d, r9d
0x18027ba7b  lea     r8, aD_0; "D"
0x18027ba82  mov     edx, r14d
0x18027ba85  mov     rcx, rax
0x18027ba88  call    cs:__imp_WdsSetupLogMessageW
0x18027ba8e  lea     rdi, [rsi+40h]
0x18027ba92  mov     [rbp+57h+var_50], rdi
0x18027ba96  mov     rcx, rdi
0x18027ba99  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18027ba9f  test    rax, rax
0x18027baa2  jz      loc_18027BB86
0x18027baa8  mov     rcx, rdi
0x18027baab  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027bab1  mov     rcx, rax
0x18027bab4  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18027baba  lea     ebx, ds:2[rax*2]
0x18027bac1  mov     rcx, rdi
0x18027bac4  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027baca  mov     rcx, rax
0x18027bacd  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18027bad3  mov     [rsp+0F0h+samDesired], ebx; cbData
0x18027bad7  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18027badc  mov     r9d, 1; dwType
0x18027bae2  xor     r8d, r8d; Reserved
0x18027bae5  lea     rdx, aClass_0; "Class"
0x18027baec  mov     rcx, [rbp+57h+var_88]; hKey
0x18027baf0  call    cs:__imp_RegSetValueExW
0x18027baf6  mov     [rbp+57h+var_90], eax
0x18027baf9  test    eax, eax
0x18027bafb  jz      loc_18027BB86
0x18027bb01  mov     [rbp+57h+arg_0], 1
0x18027bb08  call    cs:__imp_GetLastError
0x18027bb0e  mov     edi, eax
0x18027bb10  call    cs:__imp_CurrentIP
0x18027bb16  mov     rbx, rax
0x18027bb19  lea     rcx, [rbp+57h+var_70]
0x18027bb1d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027bb23  mov     rcx, rax
0x18027bb26  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18027bb2c  mov     r8, rax
0x18027bb2f  mov     r9d, [rbp+57h+var_90]
0x18027bb33  lea     rdx, aErrorCreatingC_0; "Error creating Class value for %s. Erro"...
0x18027bb3a  mov     ecx, 2000000h; unsigned int
0x18027bb3f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18027bb44  mov     [rsp+0F0h+var_A0], 0
0x18027bb4c  mov     [rsp+0F0h+var_A8], 0
0x18027bb55  mov     dword ptr [rsp+0F0h+lpdwDisposition], edi
0x18027bb59  mov     [rsp+0F0h+phkResult], rbx
0x18027bb5e  mov     [rsp+0F0h+lpSecurityAttributes], r15
0x18027bb63  mov     qword ptr [rsp+0F0h+samDesired], r12
0x18027bb68  mov     [rsp+0F0h+dwOptions], 555h
0x18027bb70  xor     r9d, r9d
0x18027bb73  lea     r8, aD_0; "D"
0x18027bb7a  mov     edx, r14d
0x18027bb7d  mov     rcx, rax
0x18027bb80  call    cs:__imp_WdsSetupLogMessageW
0x18027bb86  add     rsi, 60h ; '`'
0x18027bb8a  mov     rcx, rsi
0x18027bb8d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x18027bb93  test    rax, rax
0x18027bb96  jz      loc_18027BC7A
0x18027bb9c  mov     rcx, rsi
0x18027bb9f  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027bba5  mov     rcx, rax
0x18027bba8  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18027bbae  lea     ebx, ds:2[rax*2]
0x18027bbb5  mov     rcx, rsi
0x18027bbb8  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18027bbbe  mov     rcx, rax
0x18027bbc1  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18027bbc7  mov     [rsp+0F0h+samDesired], ebx; cbData
0x18027bbcb  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18027bbd0  mov     r9d, 1; dwType
0x18027bbd6  xor     r8d, r8d; Reserved
0x18027bbd9  lea     rdx, aDriverver; "DriverVer"
0x18027bbe0  mov     rcx, [rbp+57h+var_88]; hKey
0x18027bbe4  call    cs:__imp_RegSetValueExW
0x18027bbea  mov     [rbp+57h+var_90], eax
0x18027bbed  test    eax, eax
0x18027bbef  jz      loc_18027BC7A
0x18027bbf5  mov     [rbp+57h+arg_0], 1
0x18027bbfc  call    cs:__imp_GetLastError
0x18027bc02  mov     edi, eax
  ... truncated ...
```
