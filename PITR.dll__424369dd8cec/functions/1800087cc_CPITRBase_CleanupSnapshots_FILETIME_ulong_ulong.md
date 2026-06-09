# CPITRBase::CleanupSnapshots(_FILETIME,ulong,ulong)

- ea: `0x1800087cc`
- end: `0x1800097a2`
- name: `?CleanupSnapshots@CPITRBase@@IEAAJU_FILETIME@@KK@Z`
- size: `4054`
- prototype: `__int64 __fastcall(CPITRBase *__hidden this, struct _FILETIME, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180012130`

## callees

- `0x180003e9c`
- `0x1800087cc`
- `0x180009e04`
- `0x18000b070`
- `0x18001def0`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180009312`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18000961d`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x180009312`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18000961d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000933e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000953e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000967e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009039`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000933e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000953e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000967e`
- `WDSCORE!CurrentIP` at `0x1800088f4`
- `WDSCORE!CurrentIP` at `0x1800089c5`
- `WDSCORE!CurrentIP` at `0x180008a83`
- `WDSCORE!CurrentIP` at `0x180008b5e`
- `WDSCORE!CurrentIP` at `0x180008d66`
- `WDSCORE!CurrentIP` at `0x180008ec1`
- `WDSCORE!CurrentIP` at `0x180009041`
- `WDSCORE!CurrentIP` at `0x180009160`
- `WDSCORE!CurrentIP` at `0x18000935f`
- `WDSCORE!CurrentIP` at `0x180009429`
- `WDSCORE!CurrentIP` at `0x180009546`
- `WDSCORE!CurrentIP` at `0x180009686`
- `WDSCORE!CurrentIP` at `0x1800088f4`
- `WDSCORE!CurrentIP` at `0x1800089c5`
- `WDSCORE!CurrentIP` at `0x180008a83`
- `WDSCORE!CurrentIP` at `0x180008b5e`
- `WDSCORE!CurrentIP` at `0x180008d66`
- `WDSCORE!CurrentIP` at `0x180008ec1`
- `WDSCORE!CurrentIP` at `0x180009041`
- `WDSCORE!CurrentIP` at `0x180009160`
- `WDSCORE!CurrentIP` at `0x18000935f`
- `WDSCORE!CurrentIP` at `0x180009429`
- `WDSCORE!CurrentIP` at `0x180009546`
- `WDSCORE!CurrentIP` at `0x180009686`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000895a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180008a22`
- `WDSCORE!WdsSetupLogMessageW` at `0x180008aed`
- `WDSCORE!WdsSetupLogMessageW` at `0x180008bcd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180008e2c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180008f63`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800090e6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800091e4`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800094cc`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800095cb`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800096fb`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000895a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180008a22`
- `WDSCORE!WdsSetupLogMessageW` at `0x180008aed`
- `WDSCORE!WdsSetupLogMessageW` at `0x180008bcd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180008e2c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180008f63`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800090e6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800091e4`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800094cc`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800095cb`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800096fb`
- `unbcl!??0Object@UnBCL@@QEAA@XZ` at `0x180008ca6`
- `unbcl!??0Object@UnBCL@@QEAA@XZ` at `0x180008ca6`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180008842`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180008c31`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180008c4c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000925e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180008842`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180008c31`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180008c4c`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000925e`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180008886`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x1800088ad`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x180008886`
- `unbcl!?AddRef@Object@UnBCL@@QEAAXXZ` at `0x1800088ad`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180008c77`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800092a1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180008c77`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800092a1`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180009280`
- `unbcl!??0String@UnBCL@@QEAA@PEBV01@@Z` at `0x180009280`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800092ed`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800092ed`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180008da2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180008e90`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180008efd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009078`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009131`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18000917e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009300`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009375`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009460`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009517`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009565`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18000960b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18000969c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180008da2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180008e90`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180008efd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009078`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009131`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18000917e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009300`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009375`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009460`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009517`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009565`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18000960b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18000969c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800092c0`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800092c0`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180008832`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180008832`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800092da`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180009742`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180009760`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800092da`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180009742`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180009760`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800092cf`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x1800092cf`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800092f7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18000936c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180009602`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180009693`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800092f7`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18000936c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180009602`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180009693`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180009274`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180009274`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x18000924e`
- `unbcl!??B?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVNullTest@01@XZ` at `0x18000924e`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800092b0`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800092b0`

## string_xrefs

- `0x180008937`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180008a03`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180008ace`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180008bae`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180008d37`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180008e09`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180008f40`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180008f87`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800090c3`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800091c1`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180009203`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800095a8`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000963b`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800096d8`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180008a9e`: `CPITRBase::CleanupSnapshots: Snapshot %s is no longer present, will remove the metadata`
- `0x180008b7e`: `CPITRBase::CleanupSnapshots: Failed to delete snapshot %s. Error: 0x%08X`
- `0x180008f09`: `CPITRBase::CleanupSnapshots: Failed to delete snapshot %s. Error: 0x%08X`
- `0x18000918a`: `CPITRBase::CleanupSnapshots: Failed to delete snapshot %s. Error: 0x%08X`
- `0x180009571`: `CPITRBase::CleanupSnapshots: Failed to delete snapshot %s. Error: 0x%08X`
- `0x180009479`: `CPITRBase::CleanupSnapshots: Free disk space is below treshold (%I64u vs %I64u), snapshot %s will be removed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CPITRBase::CleanupSnapshots(CPITRBase *this, struct _FILETIME a2, unsigned int a3, unsigned int a4)
{
  int v5; // r12d
  void (__fastcall *v6)(__int64, _QWORD *); // rax
  __int64 v7; // r14
  __int64 v8; // r13
  signed int v9; // r15d
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  int v13; // eax
  DWORD v14; // esi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  DWORD LastError; // esi
  __int64 v18; // rbx
  const char *v19; // rax
  struct tagLOG_PARTIAL_MSG *v20; // rax
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(CPITRBase *, __int64); // rbx
  __int64 v23; // rax
  DWORD v24; // esi
  __int64 v25; // rbx
  const char *v26; // rax
  struct tagLOG_PARTIAL_MSG *v27; // rax
  __int64 v28; // rbx
  _QWORD *v29; // rsi
  const unsigned __int16 *v30; // rax
  __int64 v31; // rcx
  DWORD v32; // edi
  unsigned int (__fastcall ***v33)(_QWORD); // rcx
  DWORD v34; // r14d
  __int64 v35; // rsi
  __int64 v36; // rcx
  _QWORD *v37; // rax
  UnBCL::String *v38; // rax
  const char *CString; // rbx
  __int64 (__fastcall ***v40)(_QWORD); // rcx
  int v41; // eax
  struct tagLOG_PARTIAL_MSG *v42; // rax
  __int64 v43; // rsi
  __int64 (__fastcall *v44)(CPITRBase *, const unsigned __int16 *); // rbx
  __int64 v45; // rcx
  _QWORD *v46; // rax
  UnBCL::String *v47; // rax
  const unsigned __int16 *v48; // rax
  DWORD v49; // esi
  __int64 v50; // rbx
  __int64 v51; // rcx
  _QWORD *v52; // rax
  UnBCL::String *v53; // rax
  const char *v54; // rax
  struct tagLOG_PARTIAL_MSG *v55; // rax
  __int64 v56; // rcx
  unsigned int (__fastcall ***v57)(_QWORD); // rcx
  __int64 v58; // rcx
  __int64 v59; // rax
  unsigned __int64 v60; // rcx
  DWORD v61; // esi
  __int64 v62; // rbx
  __int64 v63; // rcx
  _QWORD *v64; // rax
  UnBCL::String *v65; // rax
  const char *v66; // rax
  struct tagLOG_PARTIAL_MSG *v67; // rax
  __int64 v68; // rsi
  __int64 (__fastcall *v69)(CPITRBase *, const unsigned __int16 *); // rbx
  UnBCL::String *v70; // rax
  const unsigned __int16 *v71; // rax
  DWORD v72; // esi
  __int64 v73; // rbx
  UnBCL::String *v74; // rax
  const char *v75; // rax
  struct tagLOG_PARTIAL_MSG *v76; // rax
  __int64 v77; // rcx
  UnBCL::String *v78; // rbx
  const struct UnBCL::String *P; // rax
  const struct UnBCL::String *v80; // rax
  UnBCL::String *v81; // rax
  const WCHAR *v82; // rax
  signed int v83; // eax
  signed int v84; // eax
  DWORD v85; // edi
  __int64 v86; // rbx
  UnBCL::String *v87; // rax
  const char *v88; // rax
  struct tagLOG_PARTIAL_MSG *v89; // rax
  unsigned int (__fastcall ***v90)(_QWORD); // rcx
  __int64 v91; // rcx
  DWORD v92; // edi
  __int64 v93; // rbx
  __int64 v94; // rcx
  _QWORD *v95; // rax
  UnBCL::String *v96; // rax
  const char *v97; // rax
  struct tagLOG_PARTIAL_MSG *v98; // rax
  __int64 v99; // rdi
  __int64 (__fastcall *v100)(CPITRBase *, const unsigned __int16 *); // rbx
  UnBCL::String *v101; // rax
  const unsigned __int16 *v102; // rax
  DWORD v103; // edi
  __int64 v104; // rbx
  UnBCL::String *v105; // rax
  const char *v106; // rax
  struct tagLOG_PARTIAL_MSG *v107; // rax
  __int64 v108; // rcx
  UnBCL::String *v109; // rax
  const WCHAR *v110; // rax
  signed int v111; // eax
  signed int v112; // eax
  DWORD v113; // edi
  __int64 v114; // rbx
  UnBCL::String *v115; // rax
  const char *v116; // rax
  struct tagLOG_PARTIAL_MSG *v117; // rax
  char v119; // [rsp+60h] [rbp-A0h]
  int v120; // [rsp+68h] [rbp-98h]
  int v121; // [rsp+68h] [rbp-98h]
  UnBCL::String *v122; // [rsp+68h] [rbp-98h]
  __int64 v123; // [rsp+70h] [rbp-90h]
  __int64 (__fastcall ***v124)(_QWORD); // [rsp+70h] [rbp-90h]
  __int64 v127; // [rsp+80h] [rbp-80h]
  DWORD dwLowDateTime; // [rsp+90h] [rbp-70h]
  unsigned __int64 v130; // [rsp+90h] [rbp-70h]
  void **v131; // [rsp+98h] [rbp-68h] BYREF
  __int64 v132; // [rsp+A0h] [rbp-60h]
  void **v133; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v134; // [rsp+B0h] [rbp-50h]
  void (__fastcall *v135)(__int64, _QWORD *); // [rsp+B8h] [rbp-48h]
  __int64 v136; // [rsp+C0h] [rbp-40h]
  __int64 dwHighDateTime; // [rsp+C8h] [rbp-38h]
  _QWORD v138[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v139[24]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v140; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v141; // [rsp+100h] [rbp+0h] BYREF
  _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v143[16]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v144; // [rsp+120h] [rbp+20h] BYREF

  dwLowDateTime = a2.dwLowDateTime;
  dwHighDateTime = a2.dwHighDateTime;
  v119 = 0;
  v5 = 0;
  v133 = &UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>>::`vftable';
  v134 = 0;
  v141 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v143);
  TotalNumberOfFreeBytes.QuadPart = 0;
  v6 = (void (__fastcall *)(__int64, _QWORD *))UnBCL::Object::operator new(0x80u);
  v135 = v6;
  if ( v6 )
    v7 = UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>(v6);
  else
    v7 = 0;
  v123 = v7;
  v131 = &UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>>::`vftable';
  v132 = 0;
  v8 = v7 + 8;
  if ( v7 )
    UnBCL::Object::AddRef((UnBCL::Object *)(v7 + *(int *)(*(_QWORD *)v8 + 4LL) + 8LL));
  UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign(&v131);
  v132 = v7;
  if ( v7 )
    UnBCL::Object::AddRef((UnBCL::Object *)(v7 + *(int *)(*(_QWORD *)v8 + 4LL) + 8LL));
  UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign(&v133);
  v134 = v7;
  v131 = &UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign(&v131);
  v9 = (*(__int64 (__fastcall **)(CPITRBase *, __int64 *))(*(_QWORD *)this + 32LL))(this, &v141);
  if ( v9 >= 0 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v140 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v141 + 8LL))(v141, &v140);
        v120 = v13;
        if ( v13 < 0 )
          break;
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
          || (*(unsigned int (__fastcall **)(unsigned __int64))(*(_QWORD *)v140 + 8LL))(v140) )
        {
          (*(void (__fastcall **)(unsigned __int64, __int64 *))(*(_QWORD *)v140 + 16LL))(v140, &v144);
          v28 = v144;
          v136 = v7 + *(int *)(*(_QWORD *)v8 + 16LL) + 8LL;
          v135 = *(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v136 + 40LL);
          v29 = UnBCL::Object::operator new(0x40u);
          v138[0] = v29;
          if ( v29 )
          {
            v122 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
            v131 = (void **)v122;
            if ( v122 )
            {
              v30 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(unsigned __int64))v140)(v140);
              UnBCL::String::String(v122, v30);
              *(_QWORD *)v122 = &UnBCL::String::`local vftable';
            }
            else
            {
              v122 = 0;
            }
            v29[1] = &UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64>::`vbtable';
            UnBCL::Object::Object((UnBCL::Object *)(v29 + 6));
            v119 |= 2u;
            *v29 = &UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64>::`vftable'{for `UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64>'};
            *(_QWORD *)((char *)v29 + *(int *)(v29[1] + 4LL) + 8) = &UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64>::`vftable'{for `UnBCL::Object'};
            v31 = *(int *)(v29[1] + 4LL);
            *(_DWORD *)((char *)v29 + v31 + 4) = v31 - 40;
            v29[2] = v122;
            v29[3] = v28;
            v29[4] = 1;
          }
          else
          {
            v29 = 0;
          }
          v135(v136, v29);
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v140 + 64LL))(v140);
        }
        else
        {
          LastError = GetLastError();
          v18 = CurrentIP();
          v19 = (const char *)(**(__int64 (__fastcall ***)(unsigned __int64))v140)(v140);
          v20 = ConstructPartialMsgW(
                  0x4000000u,
                  "CPITRBase::CleanupSnapshots: Snapshot %s is no longer present, will remove the metadata",
                  v19);
          WdsSetupLogMessageW(
            v20,
            0,
            L"D",
            0,
            3088,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"CPITRBase::CleanupSnapshots",
            v18,
            LastError,
            0,
            0);
          v21 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
          *(_QWORD *)(v21 + 8) = L"MissingSnapshot";
          v22 = *(__int64 (__fastcall **)(CPITRBase *, __int64))(*(_QWORD *)this + 24LL);
          v23 = (**(__int64 (__fastcall ***)(unsigned __int64))v140)(v140);
          v121 = v22(this, v23);
          *(_QWORD *)(v21 + 8) = 0;
          if ( v121 < 0 )
          {
            v24 = GetLastError();
            v25 = CurrentIP();
            v26 = (const char *)(**(__int64 (__fastcall ***)(unsigned __int64))v140)(v140);
            v27 = ConstructPartialMsgW(
                    0x2000000u,
                    "CPITRBase::CleanupSnapshots: Failed to delete snapshot %s. Error: 0x%08X",
                    v26,
                    v121);
            WdsSetupLogMessageW(
              v27,
              0,
              L"D",
              0,
              3094,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"CPITRBase::CleanupSnapshots",
              v25,
              v24,
              0,
              0);
            if ( v5 >= 0 )
              v5 = v121;
          }
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v140 + 64LL))(v140);
          v7 = v123;
        }
      }
      if ( v13 == -2147024637 )
        break;
      v14 = GetLastError();
      v15 = CurrentIP();
      v16 = ConstructPartialMsgW(0x3000000u, "Failed to get the next snapshot. Error: 0x%08X", v120);
      WdsSetupLogMessageW(
        v16,
        0,
        L"D",
        0,
        3077,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::CleanupSnapshots",
        v15,
        v14,
        0,
        0);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
        && v5 >= 0 )
      {
        v5 = v120;
      }
    }
    v9 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
    v141 = 0;
    v32 = dwLowDateTime;
    while ( 1 )
    {
      v33 = (unsigned int (__fastcall ***)(_QWORD))(v8 + *(int *)(*(_QWORD *)v8 + 12LL));
      if ( (**v33)(v33) <= a3 )
        break;
      v34 = GetLastError();
      v35 = CurrentIP();
      v36 = *(int *)(*(_QWORD *)v8 + 16LL) + v123 + 8;
      v37 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v36 + 24LL))(v36, 0);
      v38 = (UnBCL::String *)(**(__int64 (__fastcall ***)(_QWORD))*v37)(*v37);
      CString = (const char *)UnBCL::String::get_CString(v38);
      v40 = (__int64 (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)v8 + 12LL) + v123 + 8);
      v41 = (**v40)(v40);
      v42 = ConstructPartialMsgW(
              0x4000000u,
              "CPITRBase::CleanupSnapshots: Too many snapshots (%d vs %d). Removing snapshot %s",
              v41,
              a3,
              CString);
      WdsSetupLogMessageW(
        v42,
        0,
        L"D",
        0,
        3114,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::CleanupSnapshots",
        v35,
        v34,
        0,
        0);
      v43 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
      *(_QWORD *)(v43 + 8) = L"MaxCountExceeded";
      v44 = *(__int64 (__fastcall **)(CPITRBase *, const unsigned __int16 *))(*(_QWORD *)this + 24LL);
      v45 = v123 + *(int *)(*(_QWORD *)v8 + 16LL) + 8LL;
      v46 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v45 + 24LL))(v45, 0);
      v47 = (UnBCL::String *)(**(__int64 (__fastcall ***)(_QWORD))*v46)(*v46);
      v48 = UnBCL::String::get_CString(v47);
      v9 = v44(this, v48);
      *(_QWORD *)(v43 + 8) = 0;
      if ( v9 >= 0 )
      {
        v7 = v123;
      }
      else
      {
        v49 = GetLastError();
        v50 = CurrentIP();
        v7 = v123;
        v51 = *(int *)(*(_QWORD *)v8 + 16LL) + v123 + 8;
        v52 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v51 + 24LL))(v51, 0);
        v53 = (UnBCL::String *)(**(__int64 (__fastcall ***)(_QWORD))*v52)(*v52);
        v54 = (const char *)UnBCL::String::get_CString(v53);
        v55 = ConstructPartialMsgW(
                0x2000000u,
                "CPITRBase::CleanupSnapshots: Failed to delete snapshot %s. Error: 0x%08X",
                v54,
                v9);
        WdsSetupLogMessageW(
          v55,
          0,
          L"D",
          0,
          3120,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::CleanupSnapshots",
          v50,
          v49,
          0,
          0);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
          && v5 >= 0 )
        {
          v5 = v9;
        }
      }
      v56 = v7 + *(int *)(*(_QWORD *)v8 + 16LL) + 8LL;
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v56 + 88LL))(v56, 0);
    }
    while ( 1 )
    {
      v57 = (unsigned int (__fastcall ***)(_QWORD))(v8 + *(int *)(*(_QWORD *)v8 + 12LL));
      if ( !(**v57)(v57) )
        break;
      v58 = v7 + *(int *)(*(_QWORD *)v8 + 16LL) + 8LL;
      v127 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v58 + 24LL))(v58, 0);
      v140 = __PAIR64__(dwHighDateTime, v32);
      v59 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
      v60 = v140 - v59;
      if ( (__int64)(v140 - v59) < 0 )
        break;
      v130 = v60 / 0x23C34600;
      if ( (__int64)(v60 / 0x23C34600) <= a4 )
        break;
      v61 = GetLastError();
      v62 = CurrentIP();
      v63 = v7 + *(int *)(*(_QWORD *)v8 + 16LL) + 8LL;
      v64 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v63 + 24LL))(v63, 0);
      v65 = (UnBCL::String *)(**(__int64 (__fastcall ***)(_QWORD))*v64)(*v64);
      v66 = (const char *)UnBCL::String::get_CString(v65);
      v67 = ConstructPartialMsgW(
              0x4000000u,
              "CPITRBase::CleanupSnapshots: Snapshot %s is too old (%I64d minutes vs %d max minutes). Removing snapshot.",
              v66,
              v130,
              a4);
      WdsSetupLogMessageW(
        v67,
        0,
        L"D",
        0,
        3159,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::CleanupSnapshots",
        v62,
        v61,
        0,
        0);
      v68 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
      *(_QWORD *)(v68 + 8) = L"MaxTimespanExceeded";
      v69 = *(__int64 (__fastcall **)(CPITRBase *, const unsigned __int16 *))(*(_QWORD *)this + 24LL);
      v70 = (UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v127)(v127);
      v71 = UnBCL::String::get_CString(v70);
      v9 = v69(this, v71);
      *(_QWORD *)(v68 + 8) = 0;
      if ( v9 < 0 )
      {
        v72 = GetLastError();
        v73 = CurrentIP();
        v74 = (UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v127)(v127);
        v75 = (const char *)UnBCL::String::get_CString(v74);
        v76 = ConstructPartialMsgW(
                0x2000000u,
                "CPITRBase::CleanupSnapshots: Failed to delete snapshot %s. Error: 0x%08X",
                v75,
                v9);
        WdsSetupLogMessageW(
          v76,
          0,
          L"D",
          0,
          3165,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::CleanupSnapshots",
          v73,
          v72,
          0,
          0);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
        {
          if ( v5 >= 0 )
            v5 = v9;
        }
      }
      v7 = v123;
      v77 = v123 + *(int *)(*(_QWORD *)v8 + 16LL) + 8LL;
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v77 + 88LL))(v77, 0);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
    {
      if ( UnBCL::SmartPtr<UnBCL::String>::operator UnBCL::SmartPtr<UnBCL::String>::NullTest *((char *)this + 24) )
      {
        v78 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
        v131 = (void **)v78;
        if ( v78 )
        {
          P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 24);
          UnBCL::String::String(v78, P);
          *(_QWORD *)v78 = &UnBCL::String::`local vftable';
        }
        else
        {
          v78 = 0;
        }
      }
      else
      {
        v80 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v139, L"%windir%");
        v119 |= 1u;
        v78 = UnBCL::Environment::ExpandEnvironmentVariables(v80);
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v138, v78);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v143, v138);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v138);
      if ( (v119 & 1) != 0 )
        UnBCL::String::~String((UnBCL::String *)v139);
      v81 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v143);
      v82 = UnBCL::String::get_CString(v81);
      if ( GetDiskFreeSpaceExW(v82, 0, 0, &TotalNumberOfFreeBytes) )
      {
        while ( TotalNumberOfFreeBytes.QuadPart < 0x4A817C800LL )
        {
          v90 = (unsigned int (__fastcall ***)(_QWORD))(v8 + *(int *)(*(_QWORD *)v8 + 12LL));
          if ( !(**v90)(v90) )
            break;
          v91 = v7 + *(int *)(*(_QWORD *)v8 + 16LL) + 8LL;
          v124 = *(__int64 (__fastcall ****)(_QWORD))(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v91 + 24LL))(
                                                       v91,
                                                       0);
          v92 = GetLastError();
          v93 = CurrentIP();
          v94 = v7 + *(int *)(*(_QWORD *)v8 + 16LL) + 8LL;
          v95 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v94 + 24LL))(v94, 0);
          v96 = (UnBCL::String *)(**(__int64 (__fastcall ***)(_QWORD))*v95)(*v95);
          v97 = (const char *)UnBCL::String::get_CString(v96);
          v98 = ConstructPartialMsgW(
                  0x4000000u,
                  "CPITRBase::CleanupSnapshots: Free disk space is below treshold (%I64u vs %I64u), snapshot %s will be removed.",
                  TotalNumberOfFreeBytes.QuadPart,
                  20000000000LL,
                  v97);
          WdsSetupLogMessageW(
            v98,
            0,
            L"D",
            0,
            3208,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"CPITRBase::CleanupSnapshots",
            v93,
            v92,
            0,
            0);
          v99 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
          *(_QWORD *)(v99 + 8) = L"LowFreeDiskSpace";
          v100 = *(__int64 (__fastcall **)(CPITRBase *, const unsigned __int16 *))(*(_QWORD *)this + 24LL);
          v101 = (UnBCL::String *)(**v124)(v124);
          v102 = UnBCL::String::get_CString(v101);
          v9 = v100(this, v102);
          *(_QWORD *)(v99 + 8) = 0;
          if ( v9 < 0 )
          {
            v103 = GetLastError();
            v104 = CurrentIP();
            v105 = (UnBCL::String *)(**v124)(v124);
            v106 = (const char *)UnBCL::String::get_CString(v105);
            v107 = ConstructPartialMsgW(
                     0x2000000u,
                     "CPITRBase::CleanupSnapshots: Failed to delete snapshot %s. Error: 0x%08X",
                     v106,
                     v9);
            WdsSetupLogMessageW(
              v107,
              0,
              L"D",
              0,
              3214,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"CPITRBase::CleanupSnapshots",
              v104,
              v103,
              0,
              0);
            if ( v5 >= 0 )
              v5 = v9;
          }
          v108 = v7 + *(int *)(*(_QWORD *)v8 + 16LL) + 8LL;
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v108 + 88LL))(v108, 0);
          v109 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v143);
          v110 = UnBCL::String::get_CString(v109);
          if ( !GetDiskFreeSpaceExW(v110, 0, 0, &TotalNumberOfFreeBytes) )
          {
            v111 = GetLastError();
            if ( v111 > 0 )
              v111 = (unsigned __int16)v111 | 0x80070000;
            if ( v111 >= 0 )
            {
              v9 = -2147467259;
            }
            else
            {
              v112 = GetLastError();
              v9 = v112;
              if ( v112 > 0 )
                v9 = (unsigned __int16)v112 | 0x80070000;
            }
            v113 = GetLastError();
            v114 = CurrentIP();
            v115 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v143);
            v116 = (const char *)UnBCL::String::get_CString(v115);
            v117 = ConstructPartialMsgW(
                     0x3000000u,
                     "CPITRBase::CleanupSnapshots: Failed to get disk space info for %s, will not trim snapshots based on"
                     " free disk space. Error: 0x%08X",
                     v116,
                     v9);
            WdsSetupLogMessageW(
              v117,
              0,
              L"D",
              0,
              3222,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"CPITRBase::CleanupSnapshots",
              v114,
              v113,
              0,
              0);
            goto LABEL_77;
          }
        }
      }
      else
      {
        v83 = GetLastError();
        if ( v83 > 0 )
          v83 = (unsigned __int16)v83 | 0x80070000;
        if ( v83 >= 0 )
        {
          v9 = -2147467259;
        }
        else
        {
          v84 = GetLastError();
          v9 = v84;
          if ( v84 > 0 )
            v9 = (unsigned __int16)v84 | 0x80070000;
        }
        v85 = GetLastError();
        v86 = CurrentIP();
        v87 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v143);
        v88 = (const char *)UnBCL::String::get_CString(v87);
        v89 = ConstructPartialMsgW(
                0x3000000u,
                "CPITRBase::CleanupSnapshots: Failed to get disk space info for %s, will not trim snapshots based on free"
                " disk space. Error: 0x%08X",
                v88,
                v9);
        WdsSetupLogMessageW(
          v89,
          0,
          L"D",
          0,
          3189,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::CleanupSnapshots",
          v86,
          v85,
          0,
          0);
LABEL_77:
        if ( v5 >= 0 )
        {
          v5 = v9;
          if ( v9 >= 0 )
            v5 = -2147467259;
        }
      }
    }
  }
  else
  {
    v10 = GetLastError();
    v11 = CurrentIP();
    v12 = ConstructPartialMsgW(
            0x2000000u,
            "CPITRBase::CleanupSnapshots: Failed to get snapshot enumerator. Error: 0x%08X",
            v9);
    WdsSetupLogMessageW(
      v12,
      0,
      L"D",
      0,
      3054,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRBase::CleanupSnapshots",
      v11,
      v10,
      0,
      0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
      v5 = v9;
  }
  if ( v141 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
    v141 = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
  {
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v143);
    v133 = &UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign(&v133);
  }
  else
  {
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v143);
    v133 = &UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::IEnumerator<unsigned long>>::DeAssign(&v133);
    return (unsigned int)v9;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800087cc  push    rbp
0x1800087ce  push    rbx
0x1800087cf  push    rsi
0x1800087d0  push    rdi
0x1800087d1  push    r12
0x1800087d3  push    r13
0x1800087d5  push    r14
0x1800087d7  push    r15
0x1800087d9  lea     rbp, [rsp-38h]
0x1800087de  sub     rsp, 138h
0x1800087e5  mov     rax, cs:__security_cookie
0x1800087ec  xor     rax, rsp
0x1800087ef  mov     [rbp+70h+var_48], rax
0x1800087f3  mov     [rbp+70h+var_E8], r9d
0x1800087f7  mov     dword ptr [rbp+70h+var_F0], r8d
0x1800087fb  mov     [rbp+70h+var_E0], rdx
0x1800087ff  mov     rbx, rcx
0x180008802  mov     [rsp+170h+var_F8], rcx
0x180008807  mov     rax, rdx
0x18000880a  shr     rax, 20h
0x18000880e  mov     [rbp+70h+var_A8], rax
0x180008812  xor     esi, esi
0x180008814  mov     dword ptr [rsp+170h+var_110], esi
0x180008818  mov     r12d, esi
0x18000881b  lea     r15, ??_7?$SmartPtr@V?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>>::`vftable'
0x180008822  mov     [rbp+70h+var_C8], r15
0x180008826  mov     [rbp+70h+var_C0], rsi
0x18000882a  mov     [rbp+70h+var_70], rsi
0x18000882e  lea     rcx, [rbp+70h+var_60]
0x180008832  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180008838  nop
0x180008839  mov     qword ptr [rbp+70h+TotalNumberOfFreeBytes], rsi
0x18000883d  mov     ecx, 80h
0x180008842  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180008848  mov     [rbp+70h+var_B8], rax
0x18000884c  test    rax, rax
0x18000884f  jz      short loc_18000885E
0x180008851  mov     rcx, rax
0x180008854  call    ??0?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>(void)
0x180008859  mov     r14, rax
0x18000885c  jmp     short loc_180008861
0x18000885e  mov     r14, rsi
0x180008861  mov     [rsp+170h+var_100], r14
0x180008866  mov     [rbp+70h+var_D8], r15
0x18000886a  mov     [rbp+70h+var_D0], rsi
0x18000886e  lea     r13, [r14+8]
0x180008872  test    r14, r14
0x180008875  jz      short loc_18000888C
0x180008877  mov     rax, [r13+0]
0x18000887b  movsxd  rcx, dword ptr [rax+4]
0x18000887f  add     rcx, 8
0x180008883  add     rcx, r14
0x180008886  call    cs:__imp_?AddRef@Object@UnBCL@@QEAAXXZ; UnBCL::Object::AddRef(void)
0x18000888c  lea     rcx, [rbp+70h+var_D8]
0x180008890  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x180008895  mov     [rbp+70h+var_D0], r14
0x180008899  test    r14, r14
0x18000889c  jz      short loc_1800088B3
0x18000889e  mov     rax, [r13+0]
0x1800088a2  movsxd  rcx, dword ptr [rax+4]
0x1800088a6  add     rcx, 8
0x1800088aa  add     rcx, r14
0x1800088ad  call    cs:__imp_?AddRef@Object@UnBCL@@QEAAXXZ; UnBCL::Object::AddRef(void)
0x1800088b3  lea     rcx, [rbp+70h+var_C8]
0x1800088b7  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x1800088bc  mov     [rbp+70h+var_C0], r14
0x1800088c0  mov     [rbp+70h+var_D8], r15
0x1800088c4  lea     rcx, [rbp+70h+var_D8]
0x1800088c8  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@K@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ulong>>::DeAssign(void)
0x1800088cd  nop
0x1800088ce  mov     rax, [rbx]
0x1800088d1  lea     rdx, [rbp+70h+var_70]
0x1800088d5  mov     rcx, rbx
0x1800088d8  mov     rax, [rax+20h]
0x1800088dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088e1  mov     r15d, eax
0x1800088e4  test    eax, eax
0x1800088e6  jns     loc_18000897C
0x1800088ec  call    cs:__imp_GetLastError
0x1800088f2  mov     edi, eax
0x1800088f4  call    cs:__imp_CurrentIP
0x1800088fa  mov     rbx, rax
0x1800088fd  mov     r8d, r15d
0x180008900  lea     rdx, aCpitrbaseClean_2; "CPITRBase::CleanupSnapshots: Failed to "...
0x180008907  mov     ecx, 2000000h; unsigned int
0x18000890c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180008911  mov     [rsp+170h+var_120], 0
0x180008919  mov     [rsp+170h+var_128], 0
0x180008922  mov     [rsp+170h+var_130], edi
0x180008926  mov     [rsp+170h+var_138], rbx
0x18000892b  lea     rcx, aCpitrbaseClean_1; "CPITRBase::CleanupSnapshots"
0x180008932  mov     [rsp+170h+var_140], rcx
0x180008937  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000893e  mov     [rsp+170h+var_148], rcx
0x180008943  mov     dword ptr [rsp+170h+var_150], 0BEEh
0x18000894b  xor     r9d, r9d
0x18000894e  lea     r8, aD; "D"
0x180008955  xor     edx, edx
0x180008957  mov     rcx, rax
0x18000895a  call    cs:__imp_WdsSetupLogMessageW
0x180008960  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180008967  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18000896c  test    al, al
0x18000896e  jz      loc_180009710
0x180008974  mov     r12d, r15d
0x180008977  jmp     loc_180009710
0x18000897c  lea     rdi, aCpitrbaseClean_1; "CPITRBase::CleanupSnapshots"
0x180008983  lea     r15, aD; "D"
0x18000898a  mov     [rbp+70h+var_78], 0
0x180008992  mov     rcx, [rbp+70h+var_70]
0x180008996  mov     rax, [rcx]
0x180008999  lea     rdx, [rbp+70h+var_78]
0x18000899d  mov     rax, [rax+8]
0x1800089a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089a6  mov     dword ptr [rsp+170h+var_108], eax
0x1800089aa  test    eax, eax
0x1800089ac  jns     loc_180008A4F
0x1800089b2  cmp     eax, 80070103h
0x1800089b7  jz      loc_180008D1C
0x1800089bd  call    cs:__imp_GetLastError
0x1800089c3  mov     esi, eax
0x1800089c5  call    cs:__imp_CurrentIP
0x1800089cb  mov     rbx, rax
0x1800089ce  mov     r8d, dword ptr [rsp+170h+var_108]
0x1800089d3  lea     rdx, aFailedToGetThe_1; "Failed to get the next snapshot. Error:"...
0x1800089da  mov     ecx, 3000000h; unsigned int
0x1800089df  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800089e4  mov     [rsp+170h+var_120], 0
0x1800089ec  mov     [rsp+170h+var_128], 0
0x1800089f5  mov     [rsp+170h+var_130], esi
0x1800089f9  mov     [rsp+170h+var_138], rbx
0x1800089fe  mov     [rsp+170h+var_140], rdi
0x180008a03  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180008a0a  mov     [rsp+170h+var_148], rcx
0x180008a0f  mov     dword ptr [rsp+170h+var_150], 0C05h
0x180008a17  xor     r9d, r9d
0x180008a1a  mov     r8, r15
0x180008a1d  xor     edx, edx
0x180008a1f  mov     rcx, rax
0x180008a22  call    cs:__imp_WdsSetupLogMessageW
0x180008a28  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180008a2f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180008a34  test    al, al
0x180008a36  jz      loc_18000898A
0x180008a3c  test    r12d, r12d
0x180008a3f  js      loc_18000898A
0x180008a45  mov     r12d, dword ptr [rsp+170h+var_108]
0x180008a4a  jmp     loc_18000898A
0x180008a4f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180008a56  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180008a5b  test    al, al
0x180008a5d  jz      loc_180008BF6
0x180008a63  mov     rcx, [rbp+70h+var_78]
0x180008a67  mov     rax, [rcx]
0x180008a6a  mov     rax, [rax+8]
0x180008a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a73  test    eax, eax
0x180008a75  jnz     loc_180008BF6
0x180008a7b  call    cs:__imp_GetLastError
0x180008a81  mov     esi, eax
0x180008a83  call    cs:__imp_CurrentIP
0x180008a89  mov     rbx, rax
0x180008a8c  mov     rcx, [rbp+70h+var_78]
0x180008a90  mov     rdx, [rcx]
0x180008a93  mov     rax, [rdx]
0x180008a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a9b  mov     r8, rax
0x180008a9e  lea     rdx, aCpitrbaseClean_3; "CPITRBase::CleanupSnapshots: Snapshot %"...
0x180008aa5  mov     ecx, 4000000h; unsigned int
0x180008aaa  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180008aaf  mov     [rsp+170h+var_120], 0
0x180008ab7  mov     [rsp+170h+var_128], 0
0x180008ac0  mov     [rsp+170h+var_130], esi
0x180008ac4  mov     [rsp+170h+var_138], rbx
0x180008ac9  mov     [rsp+170h+var_140], rdi
0x180008ace  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180008ad5  mov     [rsp+170h+var_148], rcx
0x180008ada  mov     dword ptr [rsp+170h+var_150], 0C10h
0x180008ae2  xor     r9d, r9d
0x180008ae5  mov     r8, r15
0x180008ae8  xor     edx, edx
0x180008aea  mov     rcx, rax
0x180008aed  call    cs:__imp_WdsSetupLogMessageW
0x180008af3  mov     r14d, 8
0x180008af9  mov     eax, cs:_tls_index
0x180008aff  mov     rcx, gs:58h
0x180008b08  mov     rsi, [rcx+rax*8]
0x180008b0c  lea     rax, aMissingsnapsho; "MissingSnapshot"
0x180008b13  mov     [r14+rsi], rax
0x180008b17  mov     rax, [rsp+170h+var_F8]
0x180008b1c  mov     rax, [rax]
0x180008b1f  mov     rbx, [rax+18h]
0x180008b23  mov     rcx, [rbp+70h+var_78]
0x180008b27  mov     rdx, [rcx]
0x180008b2a  mov     rax, [rdx]
0x180008b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b32  mov     rdx, rax
0x180008b35  mov     rcx, [rsp+170h+var_F8]
0x180008b3a  mov     rax, rbx
0x180008b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b42  mov     dword ptr [rsp+170h+var_108], eax
0x180008b46  mov     qword ptr [r14+rsi], 0
0x180008b4e  test    eax, eax
0x180008b50  jns     loc_180008BDC
0x180008b56  call    cs:__imp_GetLastError
0x180008b5c  mov     esi, eax
0x180008b5e  call    cs:__imp_CurrentIP
0x180008b64  mov     rbx, rax
0x180008b67  mov     rcx, [rbp+70h+var_78]
0x180008b6b  mov     rdx, [rcx]
0x180008b6e  mov     rax, [rdx]
0x180008b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b76  mov     r8, rax
0x180008b79  mov     r9d, dword ptr [rsp+170h+var_108]
0x180008b7e  lea     rdx, aCpitrbaseClean_6; "CPITRBase::CleanupSnapshots: Failed to "...
0x180008b85  mov     ecx, 2000000h; unsigned int
0x180008b8a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180008b8f  mov     [rsp+170h+var_120], 0
0x180008b97  mov     [rsp+170h+var_128], 0
0x180008ba0  mov     [rsp+170h+var_130], esi
0x180008ba4  mov     [rsp+170h+var_138], rbx
0x180008ba9  mov     [rsp+170h+var_140], rdi
0x180008bae  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180008bb5  mov     [rsp+170h+var_148], rcx
0x180008bba  mov     dword ptr [rsp+170h+var_150], 0C16h
0x180008bc2  xor     r9d, r9d
0x180008bc5  mov     r8, r15
0x180008bc8  xor     edx, edx
0x180008bca  mov     rcx, rax
0x180008bcd  call    cs:__imp_WdsSetupLogMessageW
0x180008bd3  test    r12d, r12d
0x180008bd6  cmovns  r12d, dword ptr [rsp+170h+var_108]
0x180008bdc  mov     rcx, [rbp+70h+var_78]
0x180008be0  mov     rax, [rcx]
0x180008be3  mov     rax, [rax+40h]
0x180008be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bec  mov     r14, [rsp+170h+var_100]
0x180008bf1  jmp     loc_18000898A
0x180008bf6  mov     rcx, [rbp+70h+var_78]
0x180008bfa  mov     rax, [rcx]
0x180008bfd  lea     rdx, [rbp+70h+var_50]
0x180008c01  mov     rax, [rax+10h]
0x180008c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c0a  mov     rbx, [rbp+70h+var_50]
0x180008c0e  mov     rax, [r13+0]
0x180008c12  movsxd  rax, dword ptr [rax+10h]
0x180008c16  add     rax, 8
0x180008c1a  add     rax, r14
0x180008c1d  mov     [rbp+70h+var_B0], rax
0x180008c21  mov     rax, [rax]
0x180008c24  mov     rax, [rax+28h]
0x180008c28  mov     [rbp+70h+var_B8], rax
0x180008c2c  mov     ecx, 40h ; '@'
0x180008c31  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180008c37  mov     rsi, rax
0x180008c3a  mov     [rbp+70h+var_A0], rax
0x180008c3e  test    rax, rax
0x180008c41  jz      loc_180008CF5
0x180008c47  mov     ecx, 18h
0x180008c4c  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180008c52  mov     [rsp+170h+var_108], rax
0x180008c57  mov     [rbp+70h+var_D8], rax
0x180008c5b  test    rax, rax
0x180008c5e  jz      short loc_180008C8E
0x180008c60  mov     rcx, [rbp+70h+var_78]
0x180008c64  mov     rdx, [rcx]
0x180008c67  mov     rax, [rdx]
0x180008c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c6f  mov     rdx, rax
0x180008c72  mov     rcx, [rsp+170h+var_108]
0x180008c77  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180008c7d  mov     rax, [rsp+170h+var_108]
0x180008c82  lea     rcx, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180008c89  mov     [rax], rcx
0x180008c8c  jmp     short loc_180008C97
0x180008c8e  mov     [rsp+170h+var_108], 0
0x180008c97  lea     rax, ??_8?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@7B@; const UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64>::`vbtable'
0x180008c9e  mov     [rsi+8], rax
0x180008ca2  lea     rcx, [rsi+30h]
0x180008ca6  call    cs:__imp_??0Object@UnBCL@@QEAA@XZ; UnBCL::Object::Object(void)
0x180008cac  or      dword ptr [rsp+170h+var_110], 2
0x180008cb1  lea     rax, ??_7?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@6B01@@; const UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64>::`vftable'{for `UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64>'}
0x180008cb8  mov     [rsi], rax
0x180008cbb  mov     rax, [rsi+8]
0x180008cbf  movsxd  rcx, dword ptr [rax+4]
0x180008cc3  lea     rax, ??_7?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@6BObject@1@@; const UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64>::`vftable'{for `UnBCL::Object'}
0x180008cca  mov     [rcx+rsi+8], rax
0x180008ccf  mov     rax, [rsi+8]
0x180008cd3  movsxd  rcx, dword ptr [rax+4]
0x180008cd7  lea     edx, [rcx-28h]
0x180008cda  mov     [rcx+rsi+4], edx
0x180008cde  mov     rax, [rsp+170h+var_108]
0x180008ce3  mov     [rsi+10h], rax
0x180008ce7  mov     [rsi+18h], rbx
0x180008ceb  mov     qword ptr [rsi+20h], 1
0x180008cf3  jmp     short loc_180008CF7
0x180008cf5  xor     esi, esi
0x180008cf7  mov     rdx, rsi
0x180008cfa  mov     rcx, [rbp+70h+var_B0]
0x180008cfe  mov     rax, [rbp+70h+var_B8]
  ... truncated ...
```
