# CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)

- ea: `0x180224000`
- end: `0x1802255ed`
- name: `?DoExecute@CExecuteUnattend@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z`
- size: `5613`
- prototype: `void __fastcall __noreturn(CExecuteUnattend *__hidden this, struct IExecutionContext *, void *, struct IInternalOperationsProgress *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001413d`
- `0x180057dec`
- `0x180224000`
- `0x1802261ec`
- `0x1802db0f8`
- `0x180403e1c`
- `0x18040c590`
- `0x180423828`
- `0x18042393c`
- `0x180423bec`
- `0x1804241ac`
- `0x1804243b0`
- `0x1804247b0`
- `0x180424e74`
- `0x180426b94`
- `0x180426f08`
- `0x1804bbf62`
- `0x1804bbf6e`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180224267`
- `ADVAPI32!RegCloseKey` at `0x180224308`
- `ADVAPI32!RegCloseKey` at `0x18022457d`
- `ADVAPI32!RegCloseKey` at `0x18022462c`
- `ADVAPI32!RegCloseKey` at `0x180224b63`
- `ADVAPI32!RegCloseKey` at `0x180224c0c`
- `ADVAPI32!RegCloseKey` at `0x180224267`
- `ADVAPI32!RegCloseKey` at `0x180224308`
- `ADVAPI32!RegCloseKey` at `0x18022457d`
- `ADVAPI32!RegCloseKey` at `0x18022462c`
- `ADVAPI32!RegCloseKey` at `0x180224b63`
- `ADVAPI32!RegCloseKey` at `0x180224c0c`
- `ADVAPI32!RegOpenKeyExW` at `0x18022421b`
- `ADVAPI32!RegOpenKeyExW` at `0x1802242b5`
- `ADVAPI32!RegOpenKeyExW` at `0x18022452b`
- `ADVAPI32!RegOpenKeyExW` at `0x1802245d0`
- `ADVAPI32!RegOpenKeyExW` at `0x180224b12`
- `ADVAPI32!RegOpenKeyExW` at `0x180224bb1`
- `ADVAPI32!RegOpenKeyExW` at `0x18022421b`
- `ADVAPI32!RegOpenKeyExW` at `0x1802242b5`
- `ADVAPI32!RegOpenKeyExW` at `0x18022452b`
- `ADVAPI32!RegOpenKeyExW` at `0x1802245d0`
- `ADVAPI32!RegOpenKeyExW` at `0x180224b12`
- `ADVAPI32!RegOpenKeyExW` at `0x180224bb1`
- `ADVAPI32!RegFlushKey` at `0x1802249b7`
- `ADVAPI32!RegFlushKey` at `0x1802249c4`
- `ADVAPI32!RegFlushKey` at `0x1802249d1`
- `ADVAPI32!RegFlushKey` at `0x1802249de`
- `ADVAPI32!RegFlushKey` at `0x1802249b7`
- `ADVAPI32!RegFlushKey` at `0x1802249c4`
- `ADVAPI32!RegFlushKey` at `0x1802249d1`
- `ADVAPI32!RegFlushKey` at `0x1802249de`
- `ADVAPI32!RegQueryValueExW` at `0x18022424f`
- `ADVAPI32!RegQueryValueExW` at `0x1802242e8`
- `ADVAPI32!RegQueryValueExW` at `0x180224562`
- `ADVAPI32!RegQueryValueExW` at `0x180224609`
- `ADVAPI32!RegQueryValueExW` at `0x180224b49`
- `ADVAPI32!RegQueryValueExW` at `0x180224bea`
- `ADVAPI32!RegQueryValueExW` at `0x18022424f`
- `ADVAPI32!RegQueryValueExW` at `0x1802242e8`
- `ADVAPI32!RegQueryValueExW` at `0x180224562`
- `ADVAPI32!RegQueryValueExW` at `0x180224609`
- `ADVAPI32!RegQueryValueExW` at `0x180224b49`
- `ADVAPI32!RegQueryValueExW` at `0x180224bea`
- `KERNEL32!GetProcessHeap` at `0x18022448d`
- `KERNEL32!GetProcessHeap` at `0x18022448d`
- `KERNEL32!HeapFree` at `0x18022449b`
- `KERNEL32!HeapFree` at `0x18022449b`
- `KERNEL32!GetLastError` at `0x180224348`
- `KERNEL32!GetLastError` at `0x1802243d1`
- `KERNEL32!GetLastError` at `0x180224a4c`
- `KERNEL32!GetLastError` at `0x180224c50`
- `KERNEL32!GetLastError` at `0x180224cd5`
- `KERNEL32!GetLastError` at `0x180224df9`
- `KERNEL32!GetLastError` at `0x180224e97`
- `KERNEL32!GetLastError` at `0x180224f45`
- `KERNEL32!GetLastError` at `0x180224fee`
- `KERNEL32!GetLastError` at `0x18022508d`
- `KERNEL32!GetLastError` at `0x180225130`
- `KERNEL32!GetLastError` at `0x1802251dd`
- `KERNEL32!GetLastError` at `0x180225280`
- `KERNEL32!GetLastError` at `0x180225337`
- `KERNEL32!GetLastError` at `0x1802253f0`
- `KERNEL32!GetLastError` at `0x180225488`
- `KERNEL32!GetLastError` at `0x18022551d`
- `KERNEL32!GetLastError` at `0x180224348`
- `KERNEL32!GetLastError` at `0x1802243d1`
- `KERNEL32!GetLastError` at `0x180224a4c`
- `KERNEL32!GetLastError` at `0x180224c50`
- `KERNEL32!GetLastError` at `0x180224cd5`
- `KERNEL32!GetLastError` at `0x180224df9`
- `KERNEL32!GetLastError` at `0x180224e97`
- `KERNEL32!GetLastError` at `0x180224f45`
- `KERNEL32!GetLastError` at `0x180224fee`
- `KERNEL32!GetLastError` at `0x18022508d`
- `KERNEL32!GetLastError` at `0x180225130`
- `KERNEL32!GetLastError` at `0x1802251dd`
- `KERNEL32!GetLastError` at `0x180225280`
- `KERNEL32!GetLastError` at `0x180225337`
- `KERNEL32!GetLastError` at `0x1802253f0`
- `KERNEL32!GetLastError` at `0x180225488`
- `KERNEL32!GetLastError` at `0x18022551d`
- `KERNEL32!SetLastError` at `0x18022426f`
- `KERNEL32!SetLastError` at `0x180224310`
- `KERNEL32!SetLastError` at `0x18022431f`
- `KERNEL32!SetLastError` at `0x180224334`
- `KERNEL32!SetLastError` at `0x180224585`
- `KERNEL32!SetLastError` at `0x180224634`
- `KERNEL32!SetLastError` at `0x180224642`
- `KERNEL32!SetLastError` at `0x180224659`
- `KERNEL32!SetLastError` at `0x180224b6b`
- `KERNEL32!SetLastError` at `0x180224c14`
- `KERNEL32!SetLastError` at `0x180224c23`
- `KERNEL32!SetLastError` at `0x180224c3b`
- `KERNEL32!SetLastError` at `0x18022426f`
- `KERNEL32!SetLastError` at `0x180224310`
- `KERNEL32!SetLastError` at `0x18022431f`
- `KERNEL32!SetLastError` at `0x180224334`
- `KERNEL32!SetLastError` at `0x180224585`
- `KERNEL32!SetLastError` at `0x180224634`
- `KERNEL32!SetLastError` at `0x180224642`
- `KERNEL32!SetLastError` at `0x180224659`
- `KERNEL32!SetLastError` at `0x180224b6b`
- `KERNEL32!SetLastError` at `0x180224c14`
- `KERNEL32!SetLastError` at `0x180224c23`
- `KERNEL32!SetLastError` at `0x180224c3b`
- `KERNEL32!GetTickCount` at `0x1802249a8`
- `KERNEL32!GetTickCount` at `0x1802249e4`
- `KERNEL32!GetTickCount` at `0x1802249a8`
- `KERNEL32!GetTickCount` at `0x1802249e4`
- `KERNEL32!DeleteFileW` at `0x180224d9a`
- `KERNEL32!DeleteFileW` at `0x180224d9a`
- `ole32!CoTaskMemFree` at `0x180224975`
- `ole32!CoTaskMemFree` at `0x180224988`
- `ole32!CoTaskMemFree` at `0x180224975`
- `ole32!CoTaskMemFree` at `0x180224988`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180224098`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180224098`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18022404f`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x18022404f`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802240ea`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1802240ea`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180224dd9`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x180224dd9`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802240de`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802240de`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802240b8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180224130`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802240b8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180224130`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18022408e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802240cd`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18022408e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802240cd`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180224112`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180224112`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18022413e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180224d88`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18022413e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180224d88`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180224147`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180224d91`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180224147`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180224d91`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180224121`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802255bb`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180224121`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802255bb`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802240a9`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802240fb`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802240a9`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1802240fb`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802243ba`
- `WDSCORE!WdsSetupLogMessageW` at `0x18022443b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180224aca`
- `WDSCORE!WdsSetupLogMessageW` at `0x180224cc6`
- `WDSCORE!WdsSetupLogMessageW` at `0x180224d46`
- `WDSCORE!WdsSetupLogMessageW` at `0x180224e64`
- `WDSCORE!WdsSetupLogMessageW` at `0x180224f01`
- `WDSCORE!WdsSetupLogMessageW` at `0x180224faf`
- `WDSCORE!WdsSetupLogMessageW` at `0x18022505e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802250fd`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802251a1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180225246`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802252f4`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802253a4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180225459`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802254ee`
- `WDSCORE!WdsSetupLogMessageW` at `0x180225583`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802243ba`
- `WDSCORE!WdsSetupLogMessageW` at `0x18022443b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180224aca`
- `WDSCORE!WdsSetupLogMessageW` at `0x180224cc6`
- `WDSCORE!WdsSetupLogMessageW` at `0x180224d46`
- `WDSCORE!WdsSetupLogMessageW` at `0x180224e64`
- `WDSCORE!WdsSetupLogMessageW` at `0x180224f01`
- `WDSCORE!WdsSetupLogMessageW` at `0x180224faf`
- `WDSCORE!WdsSetupLogMessageW` at `0x18022505e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802250fd`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802251a1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180225246`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802252f4`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802253a4`
- `WDSCORE!WdsSetupLogMessageW` at `0x180225459`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802254ee`
- `WDSCORE!WdsSetupLogMessageW` at `0x180225583`
- `WDSCORE!CurrentIP` at `0x180224350`
- `WDSCORE!CurrentIP` at `0x1802243d9`
- `WDSCORE!CurrentIP` at `0x180224a54`
- `WDSCORE!CurrentIP` at `0x180224c58`
- `WDSCORE!CurrentIP` at `0x180224cdd`
- `WDSCORE!CurrentIP` at `0x180224e02`
- `WDSCORE!CurrentIP` at `0x180224e9f`
- `WDSCORE!CurrentIP` at `0x180224f4d`
- `WDSCORE!CurrentIP` at `0x180224ff6`
- `WDSCORE!CurrentIP` at `0x180225095`
- `WDSCORE!CurrentIP` at `0x180225138`
- `WDSCORE!CurrentIP` at `0x1802251e5`
- `WDSCORE!CurrentIP` at `0x180225288`
- `WDSCORE!CurrentIP` at `0x18022533f`

## string_xrefs

- `0x1802240be`: `unattend-original.xml`
- `0x180224f59`: `CExecuteUnattend::DoExecute: Unattend result indicates deserialize failure: 0x%08x`
- `0x180224eab`: `CExecuteUnattend::DoExecute: Couldn't deserialize unattend context: 0x%08x`
- `0x18022534b`: `CExecuteUnattend::DoExecute: Couldn't deserialize unattend context: 0x%08x`
- `0x180224e0e`: `CExecuteUnattend::DoExecute: Failed to initialize COM. hr = 0x%x`
- `0x18022549c`: `CExecuteUnattend::DoExecute: Failed to delete original answer file: 0x%08x`
- `0x18022498e`: `Flushing registry to disk...`
- `0x18022486f`: `One or more unattend GCs requested a delayed reboot; we will reboot the computer`
- `0x1802248c8`: `Successfully completed execution of GC queue`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=2
void __fastcall __noreturn CExecuteUnattend::DoExecute(
        CExecuteUnattend *this,
        struct IExecutionContext *a2,
        void *a3,
        struct IInternalOperationsProgress *a4)
{
  unsigned int v4; // r12d
  int v5; // esi
  const struct UnBCL::String *v6; // rcx
  struct UnBCL::String *v7; // rax
  const struct UnBCL::String *v8; // rbx
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v10; // rax
  UnBCL::String *v11; // rax
  const unsigned __int16 *CString; // rax
  int v13; // esi
  int v14; // r14d
  int i; // eax
  const char *v16; // r15
  HKEY v17; // rcx
  BOOL v18; // ebx
  LSTATUS v19; // eax
  LSTATUS v20; // ebx
  int v21; // esi
  DWORD v22; // edi
  __int64 v23; // rbx
  struct tagLOG_PARTIAL_MSG *v24; // rax
  int v25; // eax
  DWORD v26; // edi
  __int64 v27; // rbx
  struct tagLOG_PARTIAL_MSG *v28; // rax
  int v29; // edi
  int v30; // esi
  HKEY v31; // rbx
  HANDLE ProcessHeap; // rax
  int v33; // esi
  __int64 v34; // rcx
  int v35; // r13d
  HKEY v36; // rcx
  BOOL v37; // ebx
  LSTATUS v38; // eax
  LSTATUS v39; // ebx
  unsigned int v40; // ebx
  int TempUnattendRegistrySpace; // esi
  int v42; // eax
  int v43; // ecx
  int v44; // eax
  const unsigned __int16 *v45; // r8
  int v46; // edi
  int v47; // eax
  int v48; // eax
  int v49; // eax
  LPVOID *v50; // rdi
  unsigned __int64 v51; // rbx
  DWORD TickCount; // ebx
  DWORD v53; // eax
  int v54; // esi
  int v55; // esi
  DWORD v56; // edi
  __int64 v57; // rbx
  const wchar_t *v58; // r8
  struct tagLOG_PARTIAL_MSG *v59; // rax
  HKEY v60; // rcx
  BOOL v61; // ebx
  LSTATUS v62; // eax
  LSTATUS v63; // ebx
  DWORD v64; // r13d
  DWORD v65; // edi
  __int64 v66; // rbx
  struct tagLOG_PARTIAL_MSG *v67; // rax
  DWORD v68; // edi
  __int64 v69; // rbx
  struct tagLOG_PARTIAL_MSG *v70; // rax
  UnBCL::String *v71; // rax
  const WCHAR *v72; // rax
  int v73; // esi
  DWORD LastError; // edi
  __int64 v75; // rbx
  struct tagLOG_PARTIAL_MSG *v76; // rax
  DWORD v77; // edi
  __int64 v78; // rbx
  struct tagLOG_PARTIAL_MSG *v79; // rax
  __int64 v80; // rcx
  DWORD v81; // edi
  __int64 v82; // rbx
  struct tagLOG_PARTIAL_MSG *v83; // rax
  __int64 v84; // rcx
  DWORD v85; // edi
  __int64 v86; // rbx
  struct tagLOG_PARTIAL_MSG *v87; // rax
  DWORD v88; // edi
  __int64 v89; // rbx
  struct tagLOG_PARTIAL_MSG *v90; // rax
  DWORD v91; // edi
  __int64 v92; // rbx
  struct tagLOG_PARTIAL_MSG *v93; // rax
  __int64 v94; // rcx
  DWORD v95; // edi
  __int64 v96; // rbx
  struct tagLOG_PARTIAL_MSG *v97; // rax
  DWORD v98; // edi
  __int64 v99; // rbx
  struct tagLOG_PARTIAL_MSG *v100; // rax
  DWORD v101; // edi
  __int64 v102; // rbx
  struct tagLOG_PARTIAL_MSG *v103; // rax
  __int64 v104; // rcx
  DWORD v105; // edi
  __int64 v106; // rbx
  struct tagLOG_PARTIAL_MSG *v107; // rax
  DWORD v108; // edi
  __int64 v109; // rbx
  struct tagLOG_PARTIAL_MSG *v110; // rax
  DWORD v111; // edi
  __int64 v112; // rbx
  struct tagLOG_PARTIAL_MSG *v113; // rax
  DWORD cbData; // [rsp+68h] [rbp-1B0h] BYREF
  BYTE Data[4]; // [rsp+6Ch] [rbp-1ACh] BYREF
  HKEY hKey; // [rsp+70h] [rbp-1A8h] BYREF
  DWORD Type; // [rsp+78h] [rbp-1A0h] BYREF
  BYTE v118[4]; // [rsp+7Ch] [rbp-19Ch] BYREF
  int v119; // [rsp+80h] [rbp-198h]
  HKEY phkResult; // [rsp+88h] [rbp-190h] BYREF
  __int64 v121; // [rsp+90h] [rbp-188h] BYREF
  LPVOID pv[2]; // [rsp+98h] [rbp-180h] BYREF
  int v123; // [rsp+A8h] [rbp-170h]
  int v124; // [rsp+ACh] [rbp-16Ch] BYREF
  HKEY v125; // [rsp+B0h] [rbp-168h] BYREF
  _BYTE v126[16]; // [rsp+B8h] [rbp-160h] BYREF
  _QWORD v127[7]; // [rsp+C8h] [rbp-150h] BYREF
  _DWORD v128[16]; // [rsp+100h] [rbp-118h] BYREF
  _QWORD *v129; // [rsp+140h] [rbp-D8h] BYREF
  _QWORD *v130; // [rsp+148h] [rbp-D0h] BYREF
  _QWORD *v131; // [rsp+150h] [rbp-C8h] BYREF
  _QWORD *v132; // [rsp+158h] [rbp-C0h] BYREF
  _QWORD *v133; // [rsp+160h] [rbp-B8h] BYREF
  _QWORD *v134; // [rsp+168h] [rbp-B0h] BYREF
  _QWORD *v135; // [rsp+170h] [rbp-A8h] BYREF
  _QWORD *v136; // [rsp+178h] [rbp-A0h] BYREF
  _QWORD *v137; // [rsp+180h] [rbp-98h] BYREF
  _QWORD *v138; // [rsp+188h] [rbp-90h] BYREF
  _QWORD *v139; // [rsp+190h] [rbp-88h] BYREF
  _QWORD *pExceptionObject; // [rsp+198h] [rbp-80h] BYREF
  _QWORD *v141; // [rsp+1A0h] [rbp-78h] BYREF
  LPCWSTR lpValueName[4]; // [rsp+1A8h] [rbp-70h] BYREF
  _BYTE v143[80]; // [rsp+1C8h] [rbp-50h] BYREF

  lpValueName[3] = (LPCWSTR)-2LL;
  v4 = 0;
  v124 = 0;
  memset_0(v128, 0, sizeof(v128));
  v121 = 0;
  UnBCL::Exception::Exception((UnBCL::Exception *)v127);
  v127[0] = &`CExecuteUnattend::DoExecute'::`3'::CXXXXXHandledException::`vftable';
  v5 = SPInitializeCOM(&v124);
  if ( v5 < 0 )
  {
    LastError = GetLastError();
    v75 = CurrentIP();
    v76 = ConstructPartialMsgW(0x2000000u, "CExecuteUnattend::DoExecute: Failed to initialize COM. hr = 0x%x", v5);
    WdsSetupLogMessageW(
      v76,
      819200,
      L"D",
      0,
      246,
      L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
      L"CExecuteUnattend::DoExecute",
      v75,
      LastError,
      0,
      0);
    pExceptionObject = v127;
    throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&pExceptionObject;
  }
  v6 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v143, L"%windir%\\panther");
  v7 = UnBCL::Environment::ExpandEnvironmentVariables(v6);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v126, v7);
  UnBCL::String::~String((UnBCL::String *)v143);
  v8 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)lpValueName, L"unattend-original.xml");
  P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v126);
  v10 = UnBCL::Path::Combine(P, v8);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(pv, v10);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v126, pv);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(pv);
  UnBCL::String::~String((UnBCL::String *)lpValueName);
  v11 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v126);
  CString = UnBCL::String::get_CString(v11);
  v13 = UnattendCtxDeserializeFile(&v121, CString, v128);
  if ( v13 < 0 )
  {
    v77 = GetLastError();
    v78 = CurrentIP();
    v79 = ConstructPartialMsgW(
            0x2000000u,
            "CExecuteUnattend::DoExecute: Couldn't deserialize unattend context: 0x%08x",
            v13);
    WdsSetupLogMessageW(
      v79,
      819200,
      L"D",
      0,
      258,
      L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
      L"CExecuteUnattend::DoExecute",
      v78,
      v77,
      0,
      0);
    pLogUnattendResults(v80, v128);
    v139 = v127;
    throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v139;
  }
  v14 = v128[0];
  if ( v128[0] < 0 )
  {
    v81 = GetLastError();
    v82 = CurrentIP();
    v83 = ConstructPartialMsgW(
            0x2000000u,
            "CExecuteUnattend::DoExecute: Unattend result indicates deserialize failure: 0x%08x",
            v14);
    WdsSetupLogMessageW(
      v83,
      819200,
      L"D",
      0,
      265,
      L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
      L"CExecuteUnattend::DoExecute",
      v82,
      v81,
      0,
      0);
    pLogUnattendResults(v84, v128);
    v141 = v127;
    throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v141;
  }
  UnattendFreeResults(v128);
  lpValueName[0] = L"specialize";
  lpValueName[1] = L"oobeSystem";
  v119 = 0;
  for ( i = 0; ; i = v123 + 1 )
  {
    v123 = i;
    if ( (unsigned __int64)i >= 2 )
    {
      v71 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v126);
      v72 = UnBCL::String::get_CString(v71);
      if ( DeleteFileW(v72) )
      {
        if ( v119 )
        {
          v73 = OrchestrateShutdownBeforeLogon(1);
          if ( v73 < 0 )
          {
            v111 = GetLastError();
            v112 = CurrentIP();
            v113 = ConstructPartialMsgW(0x2000000u, "CExecuteUnattend::DoExecute: Couldn't request reboot: 0x%08x", v73);
            WdsSetupLogMessageW(
              v113,
              819200,
              L"D",
              0,
              396,
              L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
              L"CExecuteUnattend::DoExecute",
              v112,
              v111,
              0,
              0);
            v137 = v127;
            throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v137;
          }
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v126);
        v138 = v127;
        throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v138;
      }
      v108 = GetLastError();
      v109 = CurrentIP();
      v110 = ConstructPartialMsgW(
               0x2000000u,
               "CExecuteUnattend::DoExecute: Failed to delete original answer file: 0x%08x",
               v13);
      WdsSetupLogMessageW(
        v110,
        819200,
        L"D",
        0,
        386,
        L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
        L"CExecuteUnattend::DoExecute",
        v109,
        v108,
        0,
        0);
      v136 = v127;
      throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v136;
    }
    v16 = (const char *)lpValueName[i];
    if ( !(unsigned int)OrchestrateIsValidPass(v16) )
    {
      v21 = -2147024809;
LABEL_164:
      v105 = GetLastError();
      v106 = CurrentIP();
      v107 = ConstructPartialMsgW(
               0x2000000u,
               "CExecuteUnattend::DoExecute: Couldn't get pass status for %s: 0x%08x",
               v16,
               v21);
      WdsSetupLogMessageW(
        v107,
        819200,
        L"D",
        0,
        289,
        L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
        L"CExecuteUnattend::DoExecute",
        v106,
        v105,
        0,
        0);
      v135 = v127;
      throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v135;
    }
    hKey = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\Status\\UnattendPasses", 0, 0x20019u, &hKey)
      || (v17 = hKey) == 0 )
    {
      SetLastError(0);
      goto LABEL_24;
    }
    if ( v16 )
    {
      v18 = RegQueryValueExW(hKey, (LPCWSTR)v16, 0, 0, 0, 0) == 0;
      v17 = hKey;
    }
    else
    {
      v18 = 1;
    }
    RegCloseKey(v17);
    SetLastError(0);
    if ( !v18 )
      goto LABEL_24;
    hKey = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    Type = 0;
    v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\Status\\UnattendPasses", 0, 0x20019u, &hKey);
    if ( !v19 )
    {
      if ( hKey )
        break;
    }
    SetLastError(v19);
LABEL_21:
    if ( v4 > 9 )
    {
      v21 = -2144337908;
      goto LABEL_25;
    }
LABEL_24:
    v21 = 0;
LABEL_25:
    if ( v21 < 0 )
      goto LABEL_164;
    v22 = GetLastError();
    v23 = CurrentIP();
    v24 = ConstructPartialMsgW(0x4000000u, "Pass status for %s before running: %d", v16, v4);
    WdsSetupLogMessageW(
      v24,
      819200,
      L"D",
      0,
      293,
      L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
      L"CExecuteUnattend::DoExecute",
      v23,
      v22,
      0,
      0);
    if ( v4 <= 8 )
    {
      v25 = 362;
      if ( _bittest(&v25, v4) )
      {
        v26 = GetLastError();
        v27 = CurrentIP();
        v28 = ConstructPartialMsgW(
                0x3000000u,
                "Pass status for %s before running indicates a bad state; will still try to proceed",
                v16);
        WdsSetupLogMessageW(
          v28,
          819200,
          L"D",
          0,
          302,
          L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
          L"CExecuteUnattend::DoExecute",
          v27,
          v26,
          0,
          0);
      }
    }
    v29 = 0;
    hKey = 0;
    v30 = StrAllocatingPrintf(&hKey, L"unattend\\settings[pass=%s]", v16);
    v31 = hKey;
    if ( v30 >= 0 )
      v30 = UnattendCtxSetString(&v121, hKey, L"wasPassProcessed", L"false");
    if ( v31 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v31);
    }
    if ( v30 < 0 )
    {
      v85 = GetLastError();
      v86 = CurrentIP();
      v87 = ConstructPartialMsgW(
              0x2000000u,
              "CExecuteUnattend::DoExecute: Couldn't mark pass %s as unused in unattend context: 0x%08x",
              v16,
              v30);
      WdsSetupLogMessageW(
        v87,
        819200,
        L"D",
        0,
        309,
        L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
        L"CExecuteUnattend::DoExecute",
        v86,
        v85,
        0,
        0);
      v129 = v127;
      throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v129;
    }
    v33 = OrchestrateSetPassStatus((LPCWSTR)v16);
    if ( v33 < 0 )
    {
      v88 = GetLastError();
      v89 = CurrentIP();
      v90 = ConstructPartialMsgW(
              0x2000000u,
              "CExecuteUnattend::DoExecute: Couldn't mark pass %s as not started: 0x%08x",
              v16,
              v33);
      WdsSetupLogMessageW(
        v90,
        819200,
        L"D",
        0,
        317,
        L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
        L"CExecuteUnattend::DoExecute",
        v89,
        v88,
        0,
        0);
      v130 = v127;
      throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v130;
    }
    pv[0] = 0;
    hKey = 0;
    if ( !(unsigned int)OrchestrateIsValidPass(v16) )
    {
      TempUnattendRegistrySpace = -2147024809;
LABEL_162:
      v101 = GetLastError();
      v102 = CurrentIP();
      v103 = ConstructPartialMsgW(
               0x2000000u,
               "CExecuteUnattend::DoExecute: Couldn't deserialize unattend context: 0x%08x",
               TempUnattendRegistrySpace);
      WdsSetupLogMessageW(
        v103,
        819200,
        L"D",
        0,
        325,
        L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
        L"CExecuteUnattend::DoExecute",
        v102,
        v101,
        0,
        0);
      pLogUnattendResults(v104, v128);
      v134 = v127;
      throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v134;
    }
    v35 = 0;
    cbData = 0;
    *(_DWORD *)Data = 0;
    if ( !(unsigned int)OrchestrateIsValidPass(v34) )
    {
      TempUnattendRegistrySpace = -2147024809;
      goto LABEL_69;
    }
    phkResult = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\Status\\UnattendPasses", 0, 0x20019u, &phkResult)
      || (v36 = phkResult) == 0 )
    {
      SetLastError(0);
LABEL_54:
      v40 = 0;
      goto LABEL_55;
    }
    if ( v16 )
    {
      v37 = RegQueryValueExW(phkResult, (LPCWSTR)v16, 0, 0, 0, 0) == 0;
      v36 = phkResult;
    }
    else
    {
      v37 = 1;
    }
    RegCloseKey(v36);
    SetLastError(0);
    if ( !v37 )
      goto LABEL_54;
    v125 = 0;
    *(_DWORD *)v118 = 0;
    Type = 4;
    LODWORD(phkResult) = 0;
    v38 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\Status\\UnattendPasses", 0, 0x20019u, &v125);
    if ( !v38 && v125 )
    {
      v39 = RegQueryValueExW(v125, (LPCWSTR)v16, 0, (LPDWORD)&phkResult, v118, &Type);
      if ( v39 )
        goto LABEL_48;
      if ( Type != 4 )
      {
        v39 = 13;
LABEL_48:
        *(_DWORD *)v118 = 0;
      }
      RegCloseKey(v125);
      SetLastError(v39);
      v40 = *(_DWORD *)v118;
      goto LABEL_51;
    }
    SetLastError(v38);
    v40 = 0;
LABEL_51:
    if ( v40 > 9 )
    {
      TempUnattendRegistrySpace = -2144337908;
      goto LABEL_56;
    }
LABEL_55:
    TempUnattendRegistrySpace = 0;
LABEL_56:
    if ( TempUnattendRegistrySpace >= 0 )
    {
      UnattendLogW(0, L"Current pass status for [%s] is [0x%x]", v16, v40);
      if ( v40 > 8 || (v42 = 362, !_bittest(&v42, v40)) )
      {
        if ( (int)v40 < 4 )
        {
          cbData = 0;
        }
        else
        {
          v29 = 1;
          if ( v40 == 7 )
          {
            cbData = 1;
            goto LABEL_66;
          }
          cbData = 0;
          if ( v40 == 9 )
          {
            *(_DWORD *)Data = 1;
LABEL_67:
            v43 = 1;
            goto LABEL_70;
          }
        }
LABEL_66:
        *(_DWORD *)Data = 0;
        goto LABEL_67;
      }
      UnattendLogW(1, L"Pass has failed status; system is in an invalid state.");
      TempUnattendRegistrySpace = -2144337908;
    }
LABEL_69:
    v43 = 0;
LABEL_70:
    v44 = 0;
    if ( !v29 )
      v44 = v43;
    if ( v44 )
    {
      UnattendLogW(0, L"Applying data-only settings overrides using SMI...");
      TempUnattendRegistrySpace = OrchestrateSetPassStatus((LPCWSTR)v16);
      if ( TempUnattendRegistrySpace < 0
        || (TempUnattendRegistrySpace = CleanTempUnattendRegistrySpace(), TempUnattendRegistrySpace < 0)
        || (TempUnattendRegistrySpace = CreateTempUnattendRegistrySpace(), TempUnattendRegistrySpace < 0)
        || (TempUnattendRegistrySpace = RunSMIDataPass(
                                          (const struct _UNATTEND_CONTEXT *)&v121,
                                          (const unsigned __int16 *)v16,
                                          v45,
                                          (const unsigned __int16 ***)pv,
                                          (unsigned __int64 *)&hKey,
                                          (struct _UNATTEND_PROCESSING_RESULTS *)v128),
            TempUnattendRegistrySpace < 0) )
      {
        UnattendLogW(
          1,
          L"Failed to apply data-only settings overrides; hr = 0x%x",
          (unsigned int)TempUnattendRegistrySpace);
      }
      else
      {
        UnattendLogW(0, L"Successfully applied data-only settings overrides.");
        TempUnattendRegistrySpace = OrchestrateSetPassStatus((LPCWSTR)v16);
      }
    }
    if ( TempUnattendRegistrySpace < 0 )
    {
LABEL_109:
      if ( TempUnattendRegistrySpace == -2144337908 )
        goto LABEL_113;
      goto LABEL_110;
    }
    v46 = v128[0];
    if ( v128[0] >= 0
      && v16
      && (!wcscmp_0(L"windowsPE", (const wchar_t *)v16) || !wcscmp_0(L"offlineServicing", (const wchar_t *)v16)) )
    {
      v47 = 1;
    }
    else
    {
      v47 = *(_DWORD *)Data;
    }
    if ( v46 >= 0 )
    {
      if ( !v47 )
      {
        TempUnattendRegistrySpace = OrchestrateSetPassStatus((LPCWSTR)v16);
        if ( TempUnattendRegistrySpace < 0 )
          goto LABEL_109;
        UnattendLogW(0, L"Calling into RunSMIActionPass to execute unattend GCs for pass [%s]", v16);
        v48 = RunSMIActionPass(
                (const struct _UNATTEND_CONTEXT *)&v121,
                (const unsigned __int16 *)v16,
                cbData,
                (const unsigned __int16 **)pv[0],
                (unsigned __int64)hKey,
                (struct _UNATTEND_PROCESSING_RESULTS *)v128);
        TempUnattendRegistrySpace = v48;
        if ( v48 == 2887681 )
        {
          UnattendLogW(
            0,
            L"An unattend GC requested that immediately reboot; we will resume queue execution after rebooting");
          v35 = 1;
        }
        else
        {
          if ( v48 == 2887680 )
          {
            UnattendLogW(0, L"One or more unattend GCs requested a delayed reboot; we will reboot the computer");
            if ( (unsigned int)OrchestrateIsValidPass(v16) )
            {
              TempUnattendRegistrySpace = CleanTempUnattendRegistrySpace();
              if ( TempUnattendRegistrySpace >= 0 )
                TempUnattendRegistrySpace = OrchestratePostProcessSettingsInCtx(
                                              (const struct _UNATTEND_CONTEXT *)&v121,
                                              (const unsigned __int16 *)v16);
            }
            else
            {
              TempUnattendRegistrySpace = -2147024809;
            }
            v35 = 1;
          }
          else if ( v48 < 0 || v128[0] < 0 )
          {
            UnattendLogW(
              1,
              L"Execution of unattend GCs failed; hr = 0x%x; pResults->hrResult = 0x%x",
              (unsigned int)v48,
              v128[0]);
          }
          else
          {
            UnattendLogW(0, L"Successfully completed execution of GC queue");
            if ( (unsigned int)OrchestrateIsValidPass(v16) )
            {
              TempUnattendRegistrySpace = CleanTempUnattendRegistrySpace();
              if ( TempUnattendRegistrySpace >= 0 )
                TempUnattendRegistrySpace = OrchestratePostProcessSettingsInCtx(
                                              (const struct _UNATTEND_CONTEXT *)&v121,
                                              (const unsigned __int16 *)v16);
            }
            else
            {
              TempUnattendRegistrySpace = -2147024809;
            }
          }
          if ( TempUnattendRegistrySpace < 0 )
            goto LABEL_109;
        }
        v46 = v128[0];
      }
      if ( v46 >= 0 )
      {
        TempUnattendRegistrySpace = OrchestrateSetPassStatus((LPCWSTR)v16);
        goto LABEL_113;
      }
    }
LABEL_110:
    v49 = OrchestrateSetPassStatus((LPCWSTR)v16);
    if ( v49 < 0 && TempUnattendRegistrySpace >= 0 )
      TempUnattendRegistrySpace = v49;
LABEL_113:
    v50 = (LPVOID *)pv[0];
    if ( pv[0] )
    {
      v51 = 0;
      if ( hKey )
      {
        do
          CoTaskMemFree(v50[v51++]);
        while ( v51 < (unsigned __int64)hKey );
      }
      CoTaskMemFree(v50);
    }
    LibLog(&g_WdsLibLog, 0x4000000, L"Flushing registry to disk...");
    TickCount = GetTickCount();
    RegFlushKey(HKEY_CLASSES_ROOT);
    RegFlushKey(HKEY_CURRENT_USER);
    RegFlushKey(HKEY_LOCAL_MACHINE);
    RegFlushKey(HKEY_USERS);
    v53 = GetTickCount();
    LibLog(&g_WdsLibLog, 0x4000000, L"Flush took %u ms.", v53 - TickCount);
    if ( TempUnattendRegistrySpace < 0 )
      goto LABEL_162;
    v54 = v128[0];
    if ( v128[0] < 0 )
    {
      v91 = GetLastError();
      v92 = CurrentIP();
      v93 = ConstructPartialMsgW(
              0x2000000u,
              "CExecuteUnattend::DoExecute: Unattend result indicates SMI pass failure: 0x%08x",
              v54);
      WdsSetupLogMessageW(
        v93,
        819200,
        L"D",
        0,
        332,
        L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
        L"CExecuteUnattend::DoExecute",
        v92,
        v91,
        0,
        0);
      pLogUnattendResults(v94, v128);
      v131 = v127;
      throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v131;
    }
    UnattendFreeResults(v128);
    v55 = 0;
    if ( v119 || (v119 = 0, v35) )
      v119 = 1;
    v56 = GetLastError();
    v57 = CurrentIP();
    v58 = &cchOriginalDestLength;
    if ( !v35 )
      v58 = L" not";
    v59 = ConstructPartialMsgW(0x4000000u, "A reboot was%s requested by pass %s", (const char *)v58, v16);
    WdsSetupLogMessageW(
      v59,
      819200,
      L"D",
      0,
      341,
      L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
      L"CExecuteUnattend::DoExecute",
      v57,
      v56,
      0,
      0);
    if ( !(unsigned int)OrchestrateIsValidPass(v16) )
    {
      v55 = -2147024809;
LABEL_160:
      v98 = GetLastError();
      v99 = CurrentIP();
      v100 = ConstructPartialMsgW(
               0x2000000u,
               "CExecuteUnattend::DoExecute: Couldn't get new pass status for %s: 0x%08x",
               v16,
               v55);
      WdsSetupLogMessageW(
        v100,
        819200,
        L"D",
        0,
        361,
        L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
        L"CExecuteUnattend::DoExecute",
        v99,
        v98,
        0,
        0);
      v133 = v127;
      throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v133;
    }
    pv[0] = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\Status\\UnattendPasses", 0, 0x20019u, (PHKEY)pv)
      || (v60 = (HKEY)pv[0]) == 0 )
    {
      SetLastError(0);
LABEL_142:
      v64 = 0;
      goto LABEL_143;
    }
    if ( v16 )
    {
      v61 = RegQueryValueExW((HKEY)pv[0], (LPCWSTR)v16, 0, 0, 0, 0) == 0;
      v60 = (HKEY)pv[0];
    }
    else
    {
      v61 = 1;
    }
    RegCloseKey(v60);
    SetLastError(0);
    if ( !v61 )
      goto LABEL_142;
    pv[0] = 0;
    cbData = 0;
    Type = 4;
    LODWORD(phkResult) = 0;
    v62 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup\\Status\\UnattendPasses", 0, 0x20019u, (PHKEY)pv);
    if ( !v62 && pv[0] )
    {
      v63 = RegQueryValueExW((HKEY)pv[0], (LPCWSTR)v16, 0, (LPDWORD)&phkResult, (LPBYTE)&cbData, &Type);
      if ( v63 )
        goto LABEL_136;
      if ( Type != 4 )
      {
        v63 = 13;
LABEL_136:
        cbData = 0;
      }
      RegCloseKey((HKEY)pv[0]);
      SetLastError(v63);
      v64 = cbData;
      goto LABEL_139;
    }
    SetLastError(v62);
    v64 = 0;
LABEL_139:
    if ( v64 > 9 )
      v55 = -2144337908;
LABEL_143:
    if ( v55 < 0 )
      goto LABEL_160;
    v65 = GetLastError();
    v66 = CurrentIP();
    v67 = ConstructPartialMsgW(0x4000000u, "Pass status for %s after running: %d", v16, v64);
    WdsSetupLogMessageW(
      v67,
      819200,
      L"D",
      0,
      365,
      L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
      L"CExecuteUnattend::DoExecute",
      v66,
      v65,
      0,
      0);
    if ( v64 - 6 <= 1 )
    {
      v68 = GetLastError();
      v69 = CurrentIP();
      v70 = ConstructPartialMsgW(
              0x3000000u,
              "Pass status for %s after running indicates more action to be run after reboot; but we can't run them",
              v16);
      WdsSetupLogMessageW(
        v70,
        819200,
        L"D",
        0,
        370,
        L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
        L"CExecuteUnattend::DoExecute",
        v69,
        v68,
        0,
        0);
    }
    v13 = OrchestrateSetPassStatus((LPCWSTR)v16);
    v4 = 0;
    if ( v13 < 0 )
    {
      v95 = GetLastError();
      v96 = CurrentIP();
      v97 = ConstructPartialMsgW(
              0x2000000u,
              "CExecuteUnattend::DoExecute: Couldn't restore the status of pass %s: 0x%08x",
              v16,
              v13);
      WdsSetupLogMessageW(
        v97,
        819200,
        L"D",
        0,
        377,
        L"base\\ntsetup\\setupplatform\\lib\\src\\unattend.cpp",
        L"CExecuteUnattend::DoExecute",
        v96,
        v95,
        0,
        0);
      v132 = v127;
      throw (`CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v132;
    }
  }
  v20 = RegQueryValueExW(hKey, (LPCWSTR)v16, 0, &Type, Data, &cbData);
  if ( !v20 )
  {
    if ( cbData == 4 )
    {
LABEL_19:
      RegCloseKey(hKey);
      SetLastError(v20);
      v4 = *(_DWORD *)Data;
      goto LABEL_21;
    }
    v20 = 13;
  }
  *(_DWORD *)Data = 0;
  goto LABEL_19;
}

```

## disassembly

```asm
0x180224000  mov     rax, rsp
0x180224003  push    rbx
0x180224004  push    rsi
0x180224005  push    rdi
0x180224006  push    r12
0x180224008  push    r13
0x18022400a  push    r14
0x18022400c  push    r15
0x18022400e  sub     rsp, 1E0h
0x180224015  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x18022401d  xor     r12d, r12d
0x180224020  mov     [rax-16Ch], r12d
0x180224027  xor     edx, edx; Val
0x180224029  lea     r8d, [r12+40h]; Size
0x18022402e  lea     rcx, [rax-118h]; void *
0x180224035  call    memset_0
0x18022403a  mov     [rsp+218h+var_188], r12
0x180224042  mov     [rsp+218h+var_1B4], r12d
0x180224047  lea     rcx, [rsp+218h+var_150]
0x18022404f  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x180224055  lea     rax, ??_7CXXXXXHandledException@?2??DoExecute@CExecuteUnattend@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z@6B@; const `CExecuteUnattend::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException::`vftable'
0x18022405c  mov     [rsp+218h+var_150], rax
0x180224064  lea     rcx, [rsp+218h+var_16C]; int *
0x18022406c  call    ?SPInitializeCOM@@YAJAEAH@Z; SPInitializeCOM(int &)
0x180224071  mov     esi, eax
0x180224073  mov     [rsp+218h+var_1B8], eax
0x180224077  test    eax, eax
0x180224079  js      loc_180224DF9
0x18022407f  lea     rdx, aWindirPanther; "%windir%\\panther"
0x180224086  lea     rcx, [rsp+218h+var_50]
0x18022408e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180224094  nop
0x180224095  mov     rcx, rax
0x180224098  call    cs:__imp_?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Environment::ExpandEnvironmentVariables(UnBCL::String const *)
0x18022409e  mov     rdx, rax
0x1802240a1  lea     rcx, [rsp+218h+var_160]
0x1802240a9  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1802240af  nop
0x1802240b0  lea     rcx, [rsp+218h+var_50]
0x1802240b8  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1802240be  lea     rdx, aUnattendOrigin; "unattend-original.xml"
0x1802240c5  lea     rcx, [rsp+218h+lpValueName]
0x1802240cd  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1802240d3  mov     rbx, rax
0x1802240d6  lea     rcx, [rsp+218h+var_160]
0x1802240de  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1802240e4  mov     rdx, rbx
0x1802240e7  mov     rcx, rax
0x1802240ea  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x1802240f0  mov     rdx, rax
0x1802240f3  lea     rcx, [rsp+218h+pv]
0x1802240fb  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180224101  nop
0x180224102  lea     rdx, [rsp+218h+pv]
0x18022410a  lea     rcx, [rsp+218h+var_160]
0x180224112  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180224118  nop
0x180224119  lea     rcx, [rsp+218h+pv]
0x180224121  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180224127  nop
0x180224128  lea     rcx, [rsp+218h+lpValueName]
0x180224130  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180224136  lea     rcx, [rsp+218h+var_160]
0x18022413e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180224144  mov     rcx, rax
0x180224147  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18022414d  lea     r8, [rsp+218h+var_118]
0x180224155  mov     rdx, rax
0x180224158  lea     rcx, [rsp+218h+var_188]
0x180224160  call    cs:__imp_UnattendCtxDeserializeFile
0x180224166  mov     esi, eax
0x180224168  mov     [rsp+218h+var_1B8], eax
0x18022416c  test    eax, eax
0x18022416e  js      loc_180224E97
0x180224174  mov     r14d, [rsp+218h+var_118]
0x18022417c  test    r14d, r14d
0x18022417f  js      loc_180224F40
0x180224185  lea     rcx, [rsp+218h+var_118]
0x18022418d  call    cs:__imp_UnattendFreeResults
0x180224193  lea     rax, aSpecialize; "specialize"
0x18022419a  mov     [rsp+218h+lpValueName], rax
0x1802241a2  lea     rax, aOobesystem; "oobeSystem"
0x1802241a9  mov     [rsp+218h+var_68], rax
0x1802241b1  mov     [rsp+218h+var_198], r12d
0x1802241b9  mov     eax, r12d
0x1802241bc  lea     r13, aD_0; "D"
0x1802241c3  mov     r14d, 1
0x1802241c9  mov     [rsp+218h+var_170], eax
0x1802241d0  movsxd  r15, eax
0x1802241d3  cmp     r15, 2
0x1802241d7  jnb     loc_180224D80
0x1802241dd  mov     r15, [rsp+r15*8+218h+lpValueName]
0x1802241e5  mov     rcx, r15
0x1802241e8  call    OrchestrateIsValidPass
0x1802241ed  test    eax, eax
0x1802241ef  jz      loc_1802253E0
0x1802241f5  mov     [rsp+218h+hKey], r12
0x1802241fa  lea     rax, [rsp+218h+hKey]
0x1802241ff  mov     [rsp+218h+phkResult], rax; phkResult
0x180224204  mov     r9d, 20019h; samDesired
0x18022420a  xor     r8d, r8d; ulOptions
0x18022420d  lea     rdx, aSystemSetupSta_0; "System\\Setup\\Status\\UnattendPasses"
0x180224214  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18022421b  call    cs:__imp_RegOpenKeyExW
0x180224221  test    eax, eax
0x180224223  jnz     loc_180224332
0x180224229  mov     rcx, [rsp+218h+hKey]; hKey
0x18022422e  test    rcx, rcx
0x180224231  jz      loc_180224332
0x180224237  test    r15, r15
0x18022423a  jz      short loc_180224264
0x18022423c  mov     [rsp+218h+lpcbData], r12; lpcbData
0x180224241  mov     [rsp+218h+phkResult], r12; lpData
0x180224246  xor     r9d, r9d; lpType
0x180224249  xor     r8d, r8d; lpReserved
0x18022424c  mov     rdx, r15; lpValueName
0x18022424f  call    cs:__imp_RegQueryValueExW
0x180224255  mov     ebx, r12d
0x180224258  test    eax, eax
0x18022425a  setz    bl
0x18022425d  mov     rcx, [rsp+218h+hKey]
0x180224262  jmp     short loc_180224267
0x180224264  mov     ebx, r14d
0x180224267  call    cs:__imp_RegCloseKey
0x18022426d  xor     ecx, ecx; dwErrCode
0x18022426f  call    cs:__imp_SetLastError
0x180224275  test    ebx, ebx
0x180224277  jz      loc_18022433A
0x18022427d  mov     [rsp+218h+hKey], r12
0x180224282  mov     dword ptr [rsp+218h+Data], r12d
0x180224287  mov     [rsp+218h+cbData], 4
0x18022428f  mov     [rsp+218h+Type], r12d
0x180224294  lea     rax, [rsp+218h+hKey]
0x180224299  mov     [rsp+218h+phkResult], rax; phkResult
0x18022429e  mov     r9d, 20019h; samDesired
0x1802242a4  xor     r8d, r8d; ulOptions
0x1802242a7  lea     rdx, aSystemSetupSta_0; "System\\Setup\\Status\\UnattendPasses"
0x1802242ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802242b5  call    cs:__imp_RegOpenKeyExW
0x1802242bb  test    eax, eax
0x1802242bd  jnz     short loc_18022431D
0x1802242bf  mov     rcx, [rsp+218h+hKey]; hKey
0x1802242c4  test    rcx, rcx
0x1802242c7  jz      short loc_18022431D
0x1802242c9  lea     rax, [rsp+218h+cbData]
0x1802242ce  mov     [rsp+218h+lpcbData], rax; lpcbData
0x1802242d3  lea     rax, [rsp+218h+Data]
0x1802242d8  mov     [rsp+218h+phkResult], rax; lpData
0x1802242dd  lea     r9, [rsp+218h+Type]; lpType
0x1802242e2  xor     r8d, r8d; lpReserved
0x1802242e5  mov     rdx, r15; lpValueName
0x1802242e8  call    cs:__imp_RegQueryValueExW
0x1802242ee  mov     ebx, eax
0x1802242f0  test    eax, eax
0x1802242f2  jnz     short loc_1802242FE
0x1802242f4  cmp     [rsp+218h+cbData], 4
0x1802242f9  jz      short loc_180224303
0x1802242fb  lea     ebx, [rax+0Dh]
0x1802242fe  mov     dword ptr [rsp+218h+Data], r12d
0x180224303  mov     rcx, [rsp+218h+hKey]; hKey
0x180224308  call    cs:__imp_RegCloseKey
0x18022430e  mov     ecx, ebx; dwErrCode
0x180224310  call    cs:__imp_SetLastError
0x180224316  mov     r12d, dword ptr [rsp+218h+Data]
0x18022431b  jmp     short loc_180224325
0x18022431d  mov     ecx, eax; dwErrCode
0x18022431f  call    cs:__imp_SetLastError
0x180224325  cmp     r12d, 9
0x180224329  jbe     short loc_18022433A
0x18022432b  mov     esi, 8030000Ch
0x180224330  jmp     short loc_18022433C
0x180224332  xor     ecx, ecx; dwErrCode
0x180224334  call    cs:__imp_SetLastError
0x18022433a  xor     esi, esi
0x18022433c  mov     [rsp+218h+var_1B8], esi
0x180224340  test    esi, esi
0x180224342  js      loc_1802253ED
0x180224348  call    cs:__imp_GetLastError
0x18022434e  mov     edi, eax
0x180224350  call    cs:__imp_CurrentIP
0x180224356  mov     rbx, rax
0x180224359  mov     r9d, r12d
0x18022435c  mov     r8, r15
0x18022435f  lea     rdx, aPassStatusForS; "Pass status for %s before running: %d"
0x180224366  mov     ecx, 4000000h; unsigned int
0x18022436b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180224370  mov     [rsp+218h+var_1C8], 0
0x180224378  mov     [rsp+218h+var_1D0], 0
0x180224381  mov     [rsp+218h+var_1D8], edi
0x180224385  mov     [rsp+218h+var_1E0], rbx
0x18022438a  lea     rcx, aCexecuteunatte_11; "CExecuteUnattend::DoExecute"
0x180224391  mov     [rsp+218h+var_1E8], rcx
0x180224396  lea     rcx, aBaseNtsetupSet_46; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18022439d  mov     [rsp+218h+lpcbData], rcx
0x1802243a2  mov     dword ptr [rsp+218h+phkResult], 125h
0x1802243aa  xor     r9d, r9d
0x1802243ad  mov     r8, r13
0x1802243b0  mov     esi, 0C8000h
0x1802243b5  mov     edx, esi
0x1802243b7  mov     rcx, rax
0x1802243ba  call    cs:__imp_WdsSetupLogMessageW
0x1802243c0  cmp     r12d, 8
0x1802243c4  ja      short loc_180224441
0x1802243c6  mov     eax, 16Ah
0x1802243cb  bt      eax, r12d
0x1802243cf  jnb     short loc_180224441
0x1802243d1  call    cs:__imp_GetLastError
0x1802243d7  mov     edi, eax
0x1802243d9  call    cs:__imp_CurrentIP
0x1802243df  mov     rbx, rax
0x1802243e2  mov     r8, r15
0x1802243e5  lea     rdx, aPassStatusForS_1; "Pass status for %s before running indic"...
0x1802243ec  mov     ecx, 3000000h; unsigned int
0x1802243f1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802243f6  mov     [rsp+218h+var_1C8], 0
0x1802243fe  mov     [rsp+218h+var_1D0], 0
0x180224407  mov     [rsp+218h+var_1D8], edi
0x18022440b  mov     [rsp+218h+var_1E0], rbx
0x180224410  lea     rcx, aCexecuteunatte_11; "CExecuteUnattend::DoExecute"
0x180224417  mov     [rsp+218h+var_1E8], rcx
0x18022441c  lea     rcx, aBaseNtsetupSet_46; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180224423  mov     [rsp+218h+lpcbData], rcx
0x180224428  mov     dword ptr [rsp+218h+phkResult], 12Eh
0x180224430  xor     r9d, r9d
0x180224433  mov     r8, r13
0x180224436  mov     edx, esi
0x180224438  mov     rcx, rax
0x18022443b  call    cs:__imp_WdsSetupLogMessageW
0x180224441  xor     edi, edi
0x180224443  mov     [rsp+218h+hKey], rdi
0x180224448  mov     r8, r15
0x18022444b  lea     rdx, aUnattendSettin_1; "unattend\\settings[pass=%s]"
0x180224452  lea     rcx, [rsp+218h+hKey]
0x180224457  call    StrAllocatingPrintf
0x18022445c  mov     esi, eax
0x18022445e  mov     rbx, [rsp+218h+hKey]
0x180224463  test    eax, eax
0x180224465  js      short loc_180224488
0x180224467  lea     r9, aFalse; "false"
0x18022446e  lea     r8, aWaspassprocess; "wasPassProcessed"
0x180224475  mov     rdx, rbx
0x180224478  lea     rcx, [rsp+218h+var_188]
0x180224480  call    cs:__imp_UnattendCtxSetString
0x180224486  mov     esi, eax
0x180224488  test    rbx, rbx
0x18022448b  jz      short loc_1802244A1
0x18022448d  call    cs:__imp_GetProcessHeap
0x180224493  mov     r8, rbx; lpMem
0x180224496  xor     edx, edx; dwFlags
0x180224498  mov     rcx, rax; hHeap
0x18022449b  call    cs:__imp_HeapFree
0x1802244a1  mov     [rsp+218h+var_1B8], esi
0x1802244a5  test    esi, esi
0x1802244a7  js      loc_180224FEE
0x1802244ad  xor     edx, edx
0x1802244af  mov     rcx, r15; lpValueName
0x1802244b2  call    OrchestrateSetPassStatus
0x1802244b7  mov     esi, eax
0x1802244b9  mov     [rsp+218h+var_1B8], eax
0x1802244bd  test    eax, eax
0x1802244bf  js      loc_18022508D
0x1802244c5  mov     [rsp+218h+pv], rdi
0x1802244cd  mov     [rsp+218h+hKey], rdi
0x1802244d2  mov     rcx, r15
0x1802244d5  call    OrchestrateIsValidPass
0x1802244da  test    eax, eax
0x1802244dc  jz      loc_180225323
0x1802244e2  xor     r13d, r13d
0x1802244e5  mov     [rsp+218h+cbData], r13d
0x1802244ea  mov     dword ptr [rsp+218h+Data], r13d
0x1802244ef  call    OrchestrateIsValidPass
0x1802244f4  test    eax, eax
0x1802244f6  jz      loc_1802246D6
0x1802244fc  mov     [rsp+218h+var_190], r13
0x180224504  lea     rax, [rsp+218h+var_190]
0x18022450c  mov     [rsp+218h+phkResult], rax; phkResult
0x180224511  mov     r9d, 20019h; samDesired
0x180224517  xor     r8d, r8d; ulOptions
0x18022451a  lea     rdx, aSystemSetupSta_0; "System\\Setup\\Status\\UnattendPasses"
0x180224521  mov     rsi, 0FFFFFFFF80000002h
0x180224528  mov     rcx, rsi; hKey
0x18022452b  call    cs:__imp_RegOpenKeyExW
0x180224531  test    eax, eax
0x180224533  jnz     loc_180224657
0x180224539  mov     rcx, [rsp+218h+var_190]; hKey
0x180224541  test    rcx, rcx
0x180224544  jz      loc_180224657
0x18022454a  test    r15, r15
0x18022454d  jz      short loc_18022457A
0x18022454f  mov     [rsp+218h+lpcbData], r13; lpcbData
0x180224554  mov     [rsp+218h+phkResult], r13; lpData
0x180224559  xor     r9d, r9d; lpType
0x18022455c  xor     r8d, r8d; lpReserved
0x18022455f  mov     rdx, r15; lpValueName
0x180224562  call    cs:__imp_RegQueryValueExW
0x180224568  mov     ebx, r13d
0x18022456b  test    eax, eax
0x18022456d  setz    bl
0x180224570  mov     rcx, [rsp+218h+var_190]
0x180224578  jmp     short loc_18022457D
  ... truncated ...
```
