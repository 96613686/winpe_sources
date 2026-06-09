# CWindowsOldJob::ProcessWindowsOldDir(UnBCL::String *,IStopCallback *,int *,int *,int *)

- ea: `0x180011214`
- end: `0x180011b4f`
- name: `?ProcessWindowsOldDir@CWindowsOldJob@@AEAAXPEAVString@UnBCL@@PEAVIStopCallback@@PEAH22@Z`
- size: `2363`
- prototype: `void __fastcall(CWindowsOldJob *this, struct UnBCL::String *, struct IStopCallback *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180012b50`

## callees

- `0x18000464c`
- `0x18000638c`
- `0x1800066dc`
- `0x18000ffc8`
- `0x180010d7c`
- `0x180011214`
- `0x180013f78`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001123c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001145b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001152e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001123c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001145b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001152e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ac4`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x180011421`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x18001191b`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x180011421`
- `unbcl!?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z` at `0x18001191b`
- `unbcl!?GetDirectories@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x180011682`
- `unbcl!?GetDirectories@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x180011682`
- `unbcl!?ToLower@String@UnBCL@@QEBAPEAV12@XZ` at `0x180011708`
- `unbcl!?ToLower@String@UnBCL@@QEBAPEAV12@XZ` at `0x180011708`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800113f9`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800118ed`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800113f9`
- `unbcl!?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x1800118ed`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180011593`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180011727`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180011593`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180011727`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180011446`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180011943`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180011446`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180011943`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18001176d`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x18001176d`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1800116a2`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1800116a2`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011a7f`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011a7f`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x180011693`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x180011693`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180011413`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180011473`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800114ea`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180011748`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800117ac`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18001182a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18001185f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800118e4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18001190d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180011973`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800119f0`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180011413`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180011473`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800114ea`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180011748`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800117ac`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18001182a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18001185f`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800118e4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x18001190d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180011973`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1800119f0`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180011488`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800117c1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180011874`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18001198b`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180011488`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800117c1`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180011874`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18001198b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180011263`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001130f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001139b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180011491`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001161d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800117ca`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001187d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180011994`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180011ae2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180011263`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001130f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001139b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180011491`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001161d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800117ca`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18001187d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180011994`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180011ae2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011455`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011523`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011952`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011a2c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011a38`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011a4f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011455`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011523`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011952`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011a2c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011a38`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180011a4f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180011407`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180011432`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180011719`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18001177b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800118fe`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18001192c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180011407`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180011432`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180011719`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18001177b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800118fe`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18001192c`
- `WDSCORE!CurrentIP` at `0x180011244`
- `WDSCORE!CurrentIP` at `0x1800112f7`
- `WDSCORE!CurrentIP` at `0x180011383`
- `WDSCORE!CurrentIP` at `0x180011463`
- `WDSCORE!CurrentIP` at `0x180011536`
- `WDSCORE!CurrentIP` at `0x180011600`
- `WDSCORE!CurrentIP` at `0x18001179c`
- `WDSCORE!CurrentIP` at `0x18001184f`
- `WDSCORE!CurrentIP` at `0x180011960`
- `WDSCORE!CurrentIP` at `0x180011acc`
- `WDSCORE!CurrentIP` at `0x180011244`
- `WDSCORE!CurrentIP` at `0x1800112f7`
- `WDSCORE!CurrentIP` at `0x180011383`
- `WDSCORE!CurrentIP` at `0x180011463`
- `WDSCORE!CurrentIP` at `0x180011536`
- `WDSCORE!CurrentIP` at `0x180011600`
- `WDSCORE!CurrentIP` at `0x18001179c`
- `WDSCORE!CurrentIP` at `0x18001184f`
- `WDSCORE!CurrentIP` at `0x180011960`
- `WDSCORE!CurrentIP` at `0x180011acc`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800112c8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001135d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800113f0`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800114df`
- `WDSCORE!WdsSetupLogMessageW` at `0x180011586`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001166f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001181f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800118d0`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800119e2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180011b36`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800112c8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001135d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800113f0`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800114df`
- `WDSCORE!WdsSetupLogMessageW` at `0x180011586`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001166f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001181f`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800118d0`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800119e2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180011b36`

## string_xrefs

- `0x1800112a2`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180011567`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180011800`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x1800118d8`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180011a40`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180011aae`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x1800113a7`: `Failed to move %s to Scratch Reserves. hr = 0x%08X`
- `0x18001188b`: `Failed to move %s to Scratch Reserves. hr = 0x%08X`
- `0x18001153f`: `Directories in the delete list:`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CWindowsOldJob::ProcessWindowsOldDir(
        CWindowsOldJob *this,
        struct UnBCL::String *a2,
        struct IStopCallback *a3,
        int *a4,
        int *a5,
        int *a6)
{
  UnBCL::String *v6; // r14
  DWORD LastError; // ebx
  __int64 v8; // rdi
  const wchar_t *v9; // r15
  const wchar_t *CString; // rax
  struct tagLOG_PARTIAL_MSG *v11; // rax
  CWindowsOldJob *v12; // rcx
  DWORD v13; // edi
  const char *v14; // rax
  struct tagLOG_PARTIAL_MSG *v15; // rax
  int v16; // edi
  const wchar_t *v17; // rax
  struct tagLOG_PARTIAL_MSG *v18; // rax
  struct UnBCL::String *FullPath; // rax
  const struct UnBCL::String *P; // rax
  struct UnBCL::String *v21; // rax
  DWORD v22; // edi
  const wchar_t *v23; // rax
  UnBCL::String *v24; // rax
  struct tagLOG_PARTIAL_MSG *v25; // rax
  struct UnBCL::String *v26; // rax
  DWORD v27; // edi
  __int64 v28; // rbx
  struct tagLOG_PARTIAL_MSG *v29; // rax
  __int64 v30; // rax
  __int64 (__fastcall ***v31)(_QWORD); // rcx
  __int64 v32; // rax
  __int64 v33; // rdi
  const wchar_t *v34; // rax
  struct tagLOG_PARTIAL_MSG *v35; // rax
  __int64 Directories; // rax
  __int64 v37; // rax
  __int64 (__fastcall ***v38)(_QWORD); // rcx
  __int64 v39; // rax
  __int64 (__fastcall ***v40)(_QWORD); // rdi
  struct UnBCL::String *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdi
  unsigned int (__fastcall *v44)(__int64, __int64); // rbx
  __int64 v45; // rax
  struct UnBCL::String *v46; // rax
  DWORD v47; // ebx
  const wchar_t *v48; // rax
  UnBCL::String *v49; // rax
  struct tagLOG_PARTIAL_MSG *v50; // rax
  struct UnBCL::String *v51; // rax
  DWORD v52; // edi
  const wchar_t *v53; // rax
  UnBCL::String *v54; // rax
  struct tagLOG_PARTIAL_MSG *v55; // rax
  const struct UnBCL::String *v56; // rax
  struct UnBCL::String *v57; // rax
  const struct UnBCL::String *v58; // rax
  struct UnBCL::String *v59; // rax
  DWORD v60; // edi
  const wchar_t *v61; // rax
  UnBCL::String *v62; // rax
  struct tagLOG_PARTIAL_MSG *v63; // rax
  struct UnBCL::String *v64; // rax
  DWORD v65; // edi
  struct tagLOG_PARTIAL_MSG *v66; // rax
  DWORD v67; // edi
  __int64 v68; // rsi
  UnBCL::Win32Exception *v69; // rbx
  unsigned int Win32ErrorCode; // r14d
  const wchar_t *v71; // rax
  struct tagLOG_PARTIAL_MSG *v72; // rax
  UnBCL::String *v73[2]; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v74; // [rsp+70h] [rbp-B8h]
  UnBCL::String *v75[2]; // [rsp+78h] [rbp-B0h] BYREF
  _BYTE v76[16]; // [rsp+88h] [rbp-A0h] BYREF
  void **v77; // [rsp+98h] [rbp-90h] BYREF
  __int64 (__fastcall ***v78)(_QWORD); // [rsp+A0h] [rbp-88h]
  _QWORD v79[2]; // [rsp+A8h] [rbp-80h] BYREF
  _BYTE v80[16]; // [rsp+B8h] [rbp-70h] BYREF
  _BYTE v81[16]; // [rsp+C8h] [rbp-60h] BYREF
  _BYTE v82[16]; // [rsp+D8h] [rbp-50h] BYREF
  UnBCL::Win32Exception *v83; // [rsp+E8h] [rbp-40h] BYREF
  __int64 v86; // [rsp+138h] [rbp+10h]

  v6 = a2;
  LastError = GetLastError();
  v8 = CurrentIP();
  if ( v6 )
  {
    CString = UnBCL::String::get_CString(v6);
    v9 = L"(NULL)";
  }
  else
  {
    v9 = L"(NULL)";
    CString = L"(NULL)";
  }
  v11 = ConstructPartialMsgW(0x4000000u, "Processing %s...", (const char *)CString);
  WdsSetupLogMessageW(
    v11,
    0,
    L"D",
    0,
    922,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
    L"CWindowsOldJob::ProcessWindowsOldDir",
    v8,
    LastError,
    0,
    0);
  try
  {
    if ( CWindowsOldJob::GetMigScopeValue(v12) == 5 )
    {
      if ( *((_QWORD *)this + 2) )
      {
        v13 = GetLastError();
        v74 = CurrentIP();
        v14 = (const char *)(v6 ? UnBCL::String::get_CString(v6) : L"(NULL)");
        v15 = ConstructPartialMsgW(0x4000000u, "Moving %s to Scratch Reserves", v14);
        WdsSetupLogMessageW(
          v15,
          0,
          L"D",
          0,
          932,
          L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
          L"CWindowsOldJob::ProcessWindowsOldDir",
          v74,
          v13,
          0,
          0);
        v16 = CWindowsOldJob::MoveWindowsOldDirToScratch(this, v6);
        if ( v16 < 0 )
        {
          LODWORD(v74) = GetLastError();
          v75[0] = (UnBCL::String *)CurrentIP();
          if ( v6 )
            v17 = UnBCL::String::get_CString(v6);
          else
            v17 = L"(NULL)";
          v18 = ConstructPartialMsgW(
                  0x3000000u,
                  "Failed to move %s to Scratch Reserves. hr = 0x%08X",
                  (const char *)v17,
                  v16);
          WdsSetupLogMessageW(
            v18,
            0,
            L"D",
            0,
            936,
            L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
            L"CWindowsOldJob::ProcessWindowsOldDir",
            v75[0],
            v74,
            0,
            0);
        }
      }
      FullPath = UnBCL::Path::GetFullPath(v6);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v73, FullPath);
      P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v73);
      v21 = UnBCL::Path::WithLongPrefix(P, 1);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v76, v21);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v73, v76);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v76);
      v22 = GetLastError();
      v75[0] = (UnBCL::String *)CurrentIP();
      if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v73) )
      {
        v24 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v73);
        v23 = UnBCL::String::get_CString(v24);
      }
      else
      {
        v23 = L"(NULL)";
      }
      v25 = ConstructPartialMsgW(0x4000000u, "Deleting entire %s", (const char *)v23);
      WdsSetupLogMessageW(
        v25,
        0,
        L"D",
        0,
        941,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
        L"CWindowsOldJob::ProcessWindowsOldDir",
        v75[0],
        v22,
        0,
        0);
      v26 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v73);
      pDeleteDirectoryRecursive(v26, a3, a4, a5, a6);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v73);
    }
    else
    {
      v27 = GetLastError();
      v28 = CurrentIP();
      v29 = ConstructPartialMsgW(0x4000000u, "Directories in the delete list:");
      WdsSetupLogMessageW(
        v29,
        0,
        L"D",
        0,
        949,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
        L"CWindowsOldJob::ProcessWindowsOldDir",
        v28,
        v27,
        0,
        0);
      v30 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(CWindowsOldJob::m_DirectoriesToDelete);
      v31 = (__int64 (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v30 + 8) + 8LL) + v30 + 8);
      v32 = (**v31)(v31);
      UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>(v79, v32);
      v33 = v79[1];
      while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33) )
      {
        v75[0] = (UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v33)(v33);
        LODWORD(v74) = GetLastError();
        v73[0] = (UnBCL::String *)CurrentIP();
        if ( v75[0] )
          v34 = UnBCL::String::get_CString(v75[0]);
        else
          v34 = L"(NULL)";
        v35 = ConstructPartialMsgW(0x4000000u, "  %s", (const char *)v34);
        WdsSetupLogMessageW(
          v35,
          0,
          L"D",
          0,
          954,
          L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
          L"CWindowsOldJob::ProcessWindowsOldDir",
          v73[0],
          v74,
          0,
          0);
      }
      Directories = UnBCL::Directory::GetDirectories(v6, 0, 0);
      UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v82, Directories);
      v37 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v82);
      v38 = (__int64 (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v37 + 8) + 8LL) + v37 + 8);
      v39 = (**v38)(v38);
      UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>(&v77, v39);
      while ( 1 )
      {
        v40 = v78;
        if ( !(unsigned int)(*v78)[1](v78) )
          break;
        v73[0] = (UnBCL::String *)(**v40)(v40);
        v41 = UnBCL::String::ToLower(v73[0]);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v81, v41);
        v42 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(CWindowsOldJob::m_DirectoriesToDelete);
        v43 = v42 + *(int *)(*(_QWORD *)(v42 + 8) + 16LL);
        v44 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)(v43 + 8) + 56LL);
        v45 = UnBCL::SmartPtr<UnBCL::String>::get_P(v81);
        if ( v44(v43 + 8, v45) )
        {
          v46 = UnBCL::Path::Combine(v6, v73[0]);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v75, v46);
          if ( *((_QWORD *)this + 2) )
          {
            v47 = GetLastError();
            v73[0] = (UnBCL::String *)CurrentIP();
            if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v75) )
            {
              v49 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v75);
              v48 = UnBCL::String::get_CString(v49);
            }
            else
            {
              v48 = L"(NULL)";
            }
            v50 = ConstructPartialMsgW(0x4000000u, "Moving %s to Scratch Reserves", (const char *)v48);
            WdsSetupLogMessageW(
              v50,
              0,
              L"D",
              0,
              970,
              L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
              L"CWindowsOldJob::ProcessWindowsOldDir",
              v73[0],
              v47,
              0,
              0);
            v51 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v75);
            LODWORD(v74) = CWindowsOldJob::MoveWindowsOldDirToScratch(this, v51);
            if ( (int)v74 < 0 )
            {
              v52 = GetLastError();
              v73[0] = (UnBCL::String *)CurrentIP();
              if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v75) )
              {
                v54 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v75);
                v53 = UnBCL::String::get_CString(v54);
              }
              else
              {
                v53 = L"(NULL)";
              }
              v55 = ConstructPartialMsgW(
                      0x3000000u,
                      "Failed to move %s to Scratch Reserves. hr = 0x%08X",
                      (const char *)v53,
                      v74);
              WdsSetupLogMessageW(
                v55,
                0,
                L"D",
                0,
                974,
                L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
                L"CWindowsOldJob::ProcessWindowsOldDir",
                v73[0],
                v52,
                0,
                0);
            }
          }
          v56 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v75);
          v57 = UnBCL::Path::GetFullPath(v56);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v76, v57);
          v58 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v76);
          v59 = UnBCL::Path::WithLongPrefix(v58, 1);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v80, v59);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v76, v80);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v80);
          v60 = GetLastError();
          v73[0] = (UnBCL::String *)CurrentIP();
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v76) )
          {
            v62 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v76);
            v61 = UnBCL::String::get_CString(v62);
          }
          else
          {
            v61 = L"(NULL)";
          }
          v63 = ConstructPartialMsgW(0x4000000u, "Deleting %s...", (const char *)v61);
          WdsSetupLogMessageW(
            v63,
            0,
            L"D",
            0,
            979,
            L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
            L"CWindowsOldJob::ProcessWindowsOldDir",
            v73[0],
            v60,
            0,
            0);
          v64 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v76);
          pDeleteDirectoryRecursive(v64, a3, a4, a5, a6);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v76);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v75);
        }
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v81);
      }
      v77 = &UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::`vftable';
      UnBCL::SmartPtr<UnBCL::IEnumerator<ISetupCleanupJob *>>::DeAssign(&v77);
      UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v82);
      v79[0] = &UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::`vftable';
      UnBCL::SmartPtr<UnBCL::IEnumerator<ISetupCleanupJob *>>::DeAssign(v79);
    }
  }
  catch ( UnBCL::Win32Exception *v83 )
  {
    v67 = GetLastError();
    v68 = CurrentIP();
    v69 = v83;
    Win32ErrorCode = UnBCL::Win32Exception::get_Win32ErrorCode(v83);
    if ( a2 )
      v71 = UnBCL::String::get_CString(a2);
    else
      v71 = L"(NULL)";
    v72 = ConstructPartialMsgW(
            0x2000000u,
            "Failed to get directories in %s. GLE = %d",
            (const char *)v71,
            Win32ErrorCode);
    WdsSetupLogMessageW(
      v72,
      0,
      L"D",
      0,
      987,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
      L"CWindowsOldJob::ProcessWindowsOldDir",
      v68,
      v67,
      0,
      0);
    if ( v69 )
      (**(void (__fastcall ***)(UnBCL::Win32Exception *, __int64))v69)(v69, 1);
    *a5 = 1;
    v9 = L"(NULL)";
    v6 = a2;
  }
  if ( CWindowsOldJob::GetMigScopeValue(v12) == 5 )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v13 = GetLastError();
      v74 = CurrentIP();
      v14 = (const char *)(v6 ? UnBCL::String::get_CString(v6) : L"(NULL)");
      v15 = ConstructPartialMsgW(0x4000000u, "Moving %s to Scratch Reserves", v14);
      WdsSetupLogMessageW(
        v15,
        0,
        L"D",
        0,
        932,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
        L"CWindowsOldJob::ProcessWindowsOldDir",
        v74,
        v13,
        0,
        0);
      v16 = CWindowsOldJob::MoveWindowsOldDirToScratch(this, v6);
      if ( v16 < 0 )
      {
        LODWORD(v74) = GetLastError();
        v75[0] = (UnBCL::String *)CurrentIP();
        if ( v6 )
          v17 = UnBCL::String::get_CString(v6);
        else
          v17 = L"(NULL)";
        v18 = ConstructPartialMsgW(
                0x3000000u,
                "Failed to move %s to Scratch Reserves. hr = 0x%08X",
                (const char *)v17,
                v16);
        WdsSetupLogMessageW(
          v18,
          0,
          L"D",
          0,
          936,
          L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
          L"CWindowsOldJob::ProcessWindowsOldDir",
          v75[0],
          v74,
          0,
          0);
      }
    }
    FullPath = UnBCL::Path::GetFullPath(v6);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v73, FullPath);
    P = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v73);
    v21 = UnBCL::Path::WithLongPrefix(P, 1);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v76, v21);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v73, v76);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v76);
    v22 = GetLastError();
    v75[0] = (UnBCL::String *)CurrentIP();
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v73) )
    {
      v24 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v73);
      v23 = UnBCL::String::get_CString(v24);
    }
    else
    {
      v23 = L"(NULL)";
    }
    v25 = ConstructPartialMsgW(0x4000000u, "Deleting entire %s", (const char *)v23);
    WdsSetupLogMessageW(
      v25,
      0,
      L"D",
      0,
      941,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
      L"CWindowsOldJob::ProcessWindowsOldDir",
      v75[0],
      v22,
      0,
      0);
    v26 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v73);
    pDeleteDirectoryRecursive(v26, a3, a4, a5, a6);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v73);
  }
  else
  {
    v27 = GetLastError();
    v28 = CurrentIP();
    v29 = ConstructPartialMsgW(0x4000000u, "Directories in the delete list:");
    WdsSetupLogMessageW(
      v29,
      0,
      L"D",
      0,
      949,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
      L"CWindowsOldJob::ProcessWindowsOldDir",
      v28,
      v27,
      0,
      0);
    v30 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(CWindowsOldJob::m_DirectoriesToDelete);
    v31 = (__int64 (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v30 + 8) + 8LL) + v30 + 8);
    v32 = (**v31)(v31);
    UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>(v79, v32);
    v33 = v79[1];
    while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33) )
    {
      v75[0] = (UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v33)(v33);
      LODWORD(v74) = GetLastError();
      v73[0] = (UnBCL::String *)CurrentIP();
      if ( v75[0] )
        v34 = UnBCL::String::get_CString(v75[0]);
      else
        v34 = L"(NULL)";
      v35 = ConstructPartialMsgW(0x4000000u, "  %s", (const char *)v34);
      WdsSetupLogMessageW(
        v35,
        0,
        L"D",
        0,
        954,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
        L"CWindowsOldJob::ProcessWindowsOldDir",
        v73[0],
        v74,
        0,
        0);
    }
    Directories = UnBCL::Directory::GetDirectories(v6, 0, 0);
    UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v82, Directories);
    v37 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v82);
    v38 = (__int64 (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v37 + 8) + 8LL) + v37 + 8);
    v39 = (**v38)(v38);
    UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>(&v77, v39);
    while ( 1 )
    {
      v40 = v78;
      if ( !(unsigned int)(*v78)[1](v78) )
        break;
      v73[0] = (UnBCL::String *)(**v40)(v40);
      v41 = UnBCL::String::ToLower(v73[0]);
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v81, v41);
      v42 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(CWindowsOldJob::m_DirectoriesToDelete);
      v43 = v42 + *(int *)(*(_QWORD *)(v42 + 8) + 16LL);
      v44 = *(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)(v43 + 8) + 56LL);
      v45 = UnBCL::SmartPtr<UnBCL::String>::get_P(v81);
      if ( v44(v43 + 8, v45) )
      {
        v46 = UnBCL::Path::Combine(v6, v73[0]);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v75, v46);
        if ( *((_QWORD *)this + 2) )
        {
          v47 = GetLastError();
          v73[0] = (UnBCL::String *)CurrentIP();
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v75) )
          {
            v49 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v75);
            v48 = UnBCL::String::get_CString(v49);
          }
          else
          {
            v48 = L"(NULL)";
          }
          v50 = ConstructPartialMsgW(0x4000000u, "Moving %s to Scratch Reserves", (const char *)v48);
          WdsSetupLogMessageW(
            v50,
            0,
            L"D",
            0,
            970,
            L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
            L"CWindowsOldJob::ProcessWindowsOldDir",
            v73[0],
            v47,
            0,
            0);
          v51 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v75);
          LODWORD(v74) = CWindowsOldJob::MoveWindowsOldDirToScratch(this, v51);
          if ( (int)v74 < 0 )
          {
            v52 = GetLastError();
            v73[0] = (UnBCL::String *)CurrentIP();
            if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v75) )
            {
              v54 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v75);
              v53 = UnBCL::String::get_CString(v54);
            }
            else
            {
              v53 = L"(NULL)";
            }
            v55 = ConstructPartialMsgW(
                    0x3000000u,
                    "Failed to move %s to Scratch Reserves. hr = 0x%08X",
                    (const char *)v53,
                    v74);
            WdsSetupLogMessageW(
              v55,
              0,
              L"D",
              0,
              974,
              L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
              L"CWindowsOldJob::ProcessWindowsOldDir",
              v73[0],
              v52,
              0,
              0);
          }
        }
        v56 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v75);
        v57 = UnBCL::Path::GetFullPath(v56);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v76, v57);
        v58 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v76);
        v59 = UnBCL::Path::WithLongPrefix(v58, 1);
        UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v80, v59);
        UnBCL::SmartPtr<UnBCL::String>::operator=(v76, v80);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v80);
        v60 = GetLastError();
        v73[0] = (UnBCL::String *)CurrentIP();
        if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v76) )
        {
          v62 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v76);
          v61 = UnBCL::String::get_CString(v62);
        }
        else
        {
          v61 = L"(NULL)";
        }
        v63 = ConstructPartialMsgW(0x4000000u, "Deleting %s...", (const char *)v61);
        WdsSetupLogMessageW(
          v63,
          0,
          L"D",
          0,
          979,
          L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
          L"CWindowsOldJob::ProcessWindowsOldDir",
          v73[0],
          v60,
          0,
          0);
        v64 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v76);
        pDeleteDirectoryRecursive(v64, a3, a4, a5, a6);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v76);
        UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v75);
      }
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v81);
    }
    v77 = &UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::IEnumerator<ISetupCleanupJob *>>::DeAssign(&v77);
    UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v82);
    v79[0] = &UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::IEnumerator<ISetupCleanupJob *>>::DeAssign(v79);
  }
  v67 = GetLastError();
  v68 = CurrentIP();
  v69 = v83;
  Win32ErrorCode = UnBCL::Win32Exception::get_Win32ErrorCode(v83);
}

```

## disassembly

```asm
0x180011214  mov     rax, rsp
0x180011217  mov     [rax+20h], r9
0x18001121b  mov     [rax+18h], r8
0x18001121f  mov     [rax+10h], rdx
0x180011223  mov     [rax+8], rcx
0x180011227  push    rbx
0x180011228  push    rsi
0x180011229  push    rdi
0x18001122a  push    r12
0x18001122c  push    r13
0x18001122e  push    r14
0x180011230  push    r15
0x180011232  sub     rsp, 0F0h
0x180011239  mov     r14, rdx
0x18001123c  call    cs:__imp_GetLastError
0x180011242  mov     ebx, eax
0x180011244  call    cs:__imp_CurrentIP
0x18001124a  mov     rdi, rax
0x18001124d  xor     esi, esi
0x18001124f  test    r14, r14
0x180011252  jnz     short loc_180011260
0x180011254  lea     r15, aNull; "(NULL)"
0x18001125b  mov     rax, r15
0x18001125e  jmp     short loc_180011270
0x180011260  mov     rcx, r14
0x180011263  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180011269  lea     r15, aNull; "(NULL)"
0x180011270  mov     r8, rax
0x180011273  lea     rdx, aProcessingS; "Processing %s..."
0x18001127a  mov     ecx, 4000000h; unsigned int
0x18001127f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180011284  mov     [rsp+128h+var_D8], esi
0x180011288  mov     [rsp+128h+var_E0], rsi
0x18001128d  mov     [rsp+128h+var_E8], ebx
0x180011291  mov     [rsp+128h+var_F0], rdi
0x180011296  lea     r13, aCwindowsoldjob_0; "CWindowsOldJob::ProcessWindowsOldDir"
0x18001129d  mov     [rsp+128h+var_F8], r13
0x1800112a2  lea     rbx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800112a9  mov     [rsp+128h+var_100], rbx
0x1800112ae  mov     dword ptr [rsp+128h+var_108], 39Ah
0x1800112b6  xor     r9d, r9d
0x1800112b9  lea     r12, aD_0; "D"
0x1800112c0  mov     r8, r12
0x1800112c3  xor     edx, edx
0x1800112c5  mov     rcx, rax
0x1800112c8  call    cs:__imp_WdsSetupLogMessageW
0x1800112ce  nop
0x1800112cf  call    ?GetMigScopeValue@CWindowsOldJob@@AEAAKXZ; CWindowsOldJob::GetMigScopeValue(void)
0x1800112d4  cmp     eax, 5
0x1800112d7  jnz     loc_18001152E
0x1800112dd  mov     rax, [rsp+128h+arg_0]
0x1800112e5  cmp     [rax+10h], rsi
0x1800112e9  jz      loc_1800113F6
0x1800112ef  call    cs:__imp_GetLastError
0x1800112f5  mov     edi, eax
0x1800112f7  call    cs:__imp_CurrentIP
0x1800112fd  mov     [rsp+128h+var_B8], rax
0x180011302  test    r14, r14
0x180011305  jnz     short loc_18001130C
0x180011307  mov     rax, r15
0x18001130a  jmp     short loc_180011315
0x18001130c  mov     rcx, r14
0x18001130f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180011315  mov     r8, rax
0x180011318  lea     rdx, aMovingSToScrat; "Moving %s to Scratch Reserves"
0x18001131f  mov     ecx, 4000000h; unsigned int
0x180011324  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180011329  mov     [rsp+128h+var_D8], esi
0x18001132d  mov     [rsp+128h+var_E0], rsi
0x180011332  mov     [rsp+128h+var_E8], edi
0x180011336  mov     rcx, [rsp+128h+var_B8]
0x18001133b  mov     [rsp+128h+var_F0], rcx
0x180011340  mov     [rsp+128h+var_F8], r13
0x180011345  mov     [rsp+128h+var_100], rbx
0x18001134a  mov     dword ptr [rsp+128h+var_108], 3A4h
0x180011352  xor     r9d, r9d
0x180011355  mov     r8, r12
0x180011358  xor     edx, edx
0x18001135a  mov     rcx, rax
0x18001135d  call    cs:__imp_WdsSetupLogMessageW
0x180011363  mov     rdx, r14; struct UnBCL::String *
0x180011366  mov     rcx, [rsp+128h+arg_0]; this
0x18001136e  call    ?MoveWindowsOldDirToScratch@CWindowsOldJob@@AEAAJPEAVString@UnBCL@@@Z; CWindowsOldJob::MoveWindowsOldDirToScratch(UnBCL::String *)
0x180011373  mov     edi, eax
0x180011375  test    eax, eax
0x180011377  jns     short loc_1800113F6
0x180011379  call    cs:__imp_GetLastError
0x18001137f  mov     dword ptr [rsp+128h+var_B8], eax
0x180011383  call    cs:__imp_CurrentIP
0x180011389  mov     [rsp+128h+var_B0], rax
0x18001138e  test    r14, r14
0x180011391  jnz     short loc_180011398
0x180011393  mov     rax, r15
0x180011396  jmp     short loc_1800113A1
0x180011398  mov     rcx, r14
0x18001139b  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800113a1  mov     r9d, edi
0x1800113a4  mov     r8, rax
0x1800113a7  lea     rdx, aFailedToMoveST; "Failed to move %s to Scratch Reserves. "...
0x1800113ae  mov     ecx, 3000000h; unsigned int
0x1800113b3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800113b8  mov     [rsp+128h+var_D8], esi
0x1800113bc  mov     [rsp+128h+var_E0], rsi
0x1800113c1  mov     ecx, dword ptr [rsp+128h+var_B8]
0x1800113c5  mov     [rsp+128h+var_E8], ecx
0x1800113c9  mov     rcx, [rsp+128h+var_B0]
0x1800113ce  mov     [rsp+128h+var_F0], rcx
0x1800113d3  mov     [rsp+128h+var_F8], r13
0x1800113d8  mov     [rsp+128h+var_100], rbx
0x1800113dd  mov     dword ptr [rsp+128h+var_108], 3A8h
0x1800113e5  xor     r9d, r9d
0x1800113e8  mov     r8, r12
0x1800113eb  xor     edx, edx
0x1800113ed  mov     rcx, rax
0x1800113f0  call    cs:__imp_WdsSetupLogMessageW
0x1800113f6  mov     rcx, r14
0x1800113f9  call    cs:__imp_?GetFullPath@Path@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Path::GetFullPath(UnBCL::String const *)
0x1800113ff  mov     rdx, rax
0x180011402  lea     rcx, [rsp+128h+var_C8]
0x180011407  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18001140d  nop
0x18001140e  lea     rcx, [rsp+128h+var_C8]
0x180011413  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180011419  mov     rcx, rax
0x18001141c  mov     edx, 1
0x180011421  call    cs:__imp_?WithLongPrefix@Path@UnBCL@@SAPEAVString@2@PEBV32@H@Z; UnBCL::Path::WithLongPrefix(UnBCL::String const *,int)
0x180011427  mov     rdx, rax
0x18001142a  lea     rcx, [rsp+128h+var_A0]
0x180011432  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180011438  nop
0x180011439  lea     rdx, [rsp+128h+var_A0]
0x180011441  lea     rcx, [rsp+128h+var_C8]
0x180011446  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18001144c  nop
0x18001144d  lea     rcx, [rsp+128h+var_A0]
0x180011455  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18001145b  call    cs:__imp_GetLastError
0x180011461  mov     edi, eax
0x180011463  call    cs:__imp_CurrentIP
0x180011469  mov     [rsp+128h+var_B0], rax
0x18001146e  lea     rcx, [rsp+128h+var_C8]
0x180011473  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180011479  test    rax, rax
0x18001147c  jnz     short loc_180011483
0x18001147e  mov     rax, r15
0x180011481  jmp     short loc_180011497
0x180011483  lea     rcx, [rsp+128h+var_C8]
0x180011488  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18001148e  mov     rcx, rax
0x180011491  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180011497  mov     r8, rax
0x18001149a  lea     rdx, aDeletingEntire; "Deleting entire %s"
0x1800114a1  mov     ecx, 4000000h; unsigned int
0x1800114a6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800114ab  mov     [rsp+128h+var_D8], esi
0x1800114af  mov     [rsp+128h+var_E0], rsi
0x1800114b4  mov     [rsp+128h+var_E8], edi
0x1800114b8  mov     rcx, [rsp+128h+var_B0]
0x1800114bd  mov     [rsp+128h+var_F0], rcx
0x1800114c2  mov     [rsp+128h+var_F8], r13
0x1800114c7  mov     [rsp+128h+var_100], rbx
0x1800114cc  mov     dword ptr [rsp+128h+var_108], 3ADh
0x1800114d4  xor     r9d, r9d
0x1800114d7  mov     r8, r12
0x1800114da  xor     edx, edx
0x1800114dc  mov     rcx, rax
0x1800114df  call    cs:__imp_WdsSetupLogMessageW
0x1800114e5  lea     rcx, [rsp+128h+var_C8]
0x1800114ea  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1800114f0  mov     rcx, rax; struct UnBCL::String *
0x1800114f3  mov     rax, [rsp+128h+arg_28]
0x1800114fb  mov     [rsp+128h+var_108], rax; int *
0x180011500  mov     r9, [rsp+128h+arg_20]; int *
0x180011508  mov     r8, [rsp+128h+arg_18]; int *
0x180011510  mov     rdx, [rsp+128h+arg_10]; struct IStopCallback *
0x180011518  call    ?pDeleteDirectoryRecursive@@YAXPEAVString@UnBCL@@PEAVIStopCallback@@PEAH22@Z; pDeleteDirectoryRecursive(UnBCL::String *,IStopCallback *,int *,int *,int *)
0x18001151d  nop
0x18001151e  lea     rcx, [rsp+128h+var_C8]
0x180011523  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180011529  jmp     loc_180011A9C
0x18001152e  call    cs:__imp_GetLastError
0x180011534  mov     edi, eax
0x180011536  call    cs:__imp_CurrentIP
0x18001153c  mov     rbx, rax
0x18001153f  lea     rdx, aDirectoriesInT; "Directories in the delete list:"
0x180011546  mov     ecx, 4000000h; unsigned int
0x18001154b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180011550  mov     [rsp+128h+var_D8], esi
0x180011554  mov     [rsp+128h+var_E0], rsi
0x180011559  mov     [rsp+128h+var_E8], edi
0x18001155d  mov     [rsp+128h+var_F0], rbx
0x180011562  mov     [rsp+128h+var_F8], r13
0x180011567  lea     rbx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18001156e  mov     [rsp+128h+var_100], rbx
0x180011573  mov     dword ptr [rsp+128h+var_108], 3B5h
0x18001157b  xor     r9d, r9d
0x18001157e  mov     r8, r12
0x180011581  xor     edx, edx
0x180011583  mov     rcx, rax
0x180011586  call    cs:__imp_WdsSetupLogMessageW
0x18001158c  lea     rcx, ?m_DirectoriesToDelete@CWindowsOldJob@@0V?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@A; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>> CWindowsOldJob::m_DirectoriesToDelete
0x180011593  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x180011599  mov     rcx, [rax+8]
0x18001159d  movsxd  rdx, dword ptr [rcx+8]
0x1800115a1  lea     rcx, [rax+8]
0x1800115a5  add     rcx, rdx
0x1800115a8  mov     rax, [rcx]
0x1800115ab  mov     rax, [rax]
0x1800115ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115b3  mov     rdx, rax
0x1800115b6  lea     rcx, [rsp+128h+var_80]
0x1800115be  call    ??0?$SmartPtr@U?$IEnumerator@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAU?$IEnumerator@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>(UnBCL::IEnumerator<UnBCL::String *> *)
0x1800115c3  nop
0x1800115c4  mov     rdi, [rsp+128h+var_78]
0x1800115cc  mov     rax, [rdi]
0x1800115cf  mov     rcx, rdi
0x1800115d2  mov     rax, [rax+8]
0x1800115d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115db  test    eax, eax
0x1800115dd  jz      loc_18001167A
0x1800115e3  mov     rax, [rdi]
0x1800115e6  mov     rcx, rdi
0x1800115e9  mov     rax, [rax]
0x1800115ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115f1  mov     [rsp+128h+var_B0], rax
0x1800115f6  call    cs:__imp_GetLastError
0x1800115fc  mov     dword ptr [rsp+128h+var_B8], eax
0x180011600  call    cs:__imp_CurrentIP
0x180011606  mov     [rsp+128h+var_C8], rax
0x18001160b  mov     rax, [rsp+128h+var_B0]
0x180011610  test    rax, rax
0x180011613  jnz     short loc_18001161A
0x180011615  mov     rax, r15
0x180011618  jmp     short loc_180011623
0x18001161a  mov     rcx, rax
0x18001161d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180011623  mov     r8, rax
0x180011626  lea     rdx, aS; "  %s"
0x18001162d  mov     ecx, 4000000h; unsigned int
0x180011632  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180011637  mov     [rsp+128h+var_D8], esi
0x18001163b  mov     [rsp+128h+var_E0], rsi
0x180011640  mov     ecx, dword ptr [rsp+128h+var_B8]
0x180011644  mov     [rsp+128h+var_E8], ecx
0x180011648  mov     rcx, [rsp+128h+var_C8]
0x18001164d  mov     [rsp+128h+var_F0], rcx
0x180011652  mov     [rsp+128h+var_F8], r13
0x180011657  mov     [rsp+128h+var_100], rbx
0x18001165c  mov     dword ptr [rsp+128h+var_108], 3BAh
0x180011664  xor     r9d, r9d
0x180011667  mov     r8, r12
0x18001166a  xor     edx, edx
0x18001166c  mov     rcx, rax
0x18001166f  call    cs:__imp_WdsSetupLogMessageW
0x180011675  jmp     loc_1800115CC
0x18001167a  xor     r8d, r8d
0x18001167d  xor     edx, edx
0x18001167f  mov     rcx, r14
0x180011682  call    cs:__imp_?GetDirectories@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z; UnBCL::Directory::GetDirectories(UnBCL::String const *,UnBCL::String const *,int)
0x180011688  mov     rdx, rax
0x18001168b  lea     rcx, [rsp+128h+var_50]
0x180011693  call    cs:__imp_??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(UnBCL::Array<UnBCL::String *> *)
0x180011699  nop
0x18001169a  lea     rcx, [rsp+128h+var_50]
0x1800116a2  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x1800116a8  mov     rcx, [rax+8]
0x1800116ac  movsxd  rdx, dword ptr [rcx+8]
0x1800116b0  lea     rcx, [rax+8]
0x1800116b4  add     rcx, rdx
0x1800116b7  mov     rax, [rcx]
0x1800116ba  mov     rax, [rax]
0x1800116bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116c2  mov     rdx, rax
0x1800116c5  lea     rcx, [rsp+128h+var_90]
0x1800116cd  call    ??0?$SmartPtr@U?$IEnumerator@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAU?$IEnumerator@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>(UnBCL::IEnumerator<UnBCL::String *> *)
0x1800116d2  nop
0x1800116d3  mov     rdi, [rsp+128h+var_88]
0x1800116db  mov     rax, [rdi]
0x1800116de  mov     rcx, rdi
0x1800116e1  mov     rax, [rax+8]
0x1800116e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116ea  test    eax, eax
0x1800116ec  jz      loc_180011A5A
0x1800116f2  mov     rax, [rdi]
0x1800116f5  mov     rcx, rdi
0x1800116f8  mov     rax, [rax]
0x1800116fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011700  mov     [rsp+128h+var_C8], rax
0x180011705  mov     rcx, rax
0x180011708  call    cs:__imp_?ToLower@String@UnBCL@@QEBAPEAV12@XZ; UnBCL::String::ToLower(void)
0x18001170e  mov     rdx, rax
0x180011711  lea     rcx, [rsp+128h+var_60]
0x180011719  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18001171f  nop
0x180011720  lea     rcx, ?m_DirectoriesToDelete@CWindowsOldJob@@0V?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@A; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>> CWindowsOldJob::m_DirectoriesToDelete
0x180011727  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x18001172d  mov     rcx, [rax+8]
0x180011731  movsxd  rdi, dword ptr [rcx+10h]
0x180011735  add     rdi, rax
0x180011738  mov     rdx, [rdi+8]
  ... truncated ...
```
