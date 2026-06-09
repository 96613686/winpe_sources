# CWindowsOldJob::Run(IStopCallback *)

- ea: `0x180012b50`
- end: `0x1800131bd`
- name: `?Run@CWindowsOldJob@@UEAA?AW4SETUP_CLEANUP_JOB_RESULT@@PEAVIStopCallback@@@Z`
- size: `1645`
- prototype: `__int64 __fastcall(CWindowsOldJob *, struct IStopCallback *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180003cb0`
- `0x180003d5c`
- `0x18000464c`
- `0x18000638c`
- `0x1800066dc`
- `0x180011214`
- `0x180012b50`
- `0x18002d640`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013106`
- `unbcl!?GetDirectories@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x180012dd7`
- `unbcl!?GetDirectories@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z` at `0x180012dd7`
- `unbcl!?IsDirectoryEmpty@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180012f5a`
- `unbcl!?IsDirectoryEmpty@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180012f5a`
- `unbcl!?DeleteNE@Directory@UnBCL@@SAHPEBVString@2@H@Z` at `0x180012f78`
- `unbcl!?DeleteNE@Directory@UnBCL@@SAHPEBVString@2@H@Z` at `0x180012f78`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180012ee9`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180012ee9`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x180012e0b`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x180012e80`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x180012e0b`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x180012e80`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180013182`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180013182`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x180012de4`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x180012de4`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012d29`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012d41`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012dc8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012edd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012f03`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012f35`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012f51`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012f6d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012fa5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012fbe`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012d29`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012d41`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012dc8`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012edd`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012f03`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012f35`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012f51`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012f6d`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012fa5`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180012fbe`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180012f3e`
- `unbcl!?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z` at `0x180012f3e`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180012cf5`
- `unbcl!?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z` at `0x180012cf5`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180012d4a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180012fc7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180012d4a`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180012fc7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180013035`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18001318d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180013035`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18001318d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180012d02`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180012ef7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180012d02`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180012ef7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180012d0e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180012df0`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180012d0e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180012df0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180012ceb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180012dbb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180012ceb`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180012dbb`
- `WDSCORE!CurrentIP` at `0x180012ba6`
- `WDSCORE!CurrentIP` at `0x180012c53`
- `WDSCORE!CurrentIP` at `0x180012d1c`
- `WDSCORE!CurrentIP` at `0x180012dfe`
- `WDSCORE!CurrentIP` at `0x180012f8e`
- `WDSCORE!CurrentIP` at `0x18001307a`
- `WDSCORE!CurrentIP` at `0x18001310e`
- `WDSCORE!CurrentIP` at `0x180012ba6`
- `WDSCORE!CurrentIP` at `0x180012c53`
- `WDSCORE!CurrentIP` at `0x180012d1c`
- `WDSCORE!CurrentIP` at `0x180012dfe`
- `WDSCORE!CurrentIP` at `0x180012f8e`
- `WDSCORE!CurrentIP` at `0x18001307a`
- `WDSCORE!CurrentIP` at `0x18001310e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180012c0b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180012cb8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180012da9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180012e76`
- `WDSCORE!WdsSetupLogMessageW` at `0x180013029`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800130d2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180013162`
- `WDSCORE!WdsSetupLogMessageW` at `0x180012c0b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180012cb8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180012da9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180012e76`
- `WDSCORE!WdsSetupLogMessageW` at `0x180013029`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800130d2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180013162`

## string_xrefs

- `0x180012b90`: `SeBackupPrivilege`
- `0x180012c21`: `SeBackupPrivilege`
- `0x180012bb8`: `Enable BACKUP privilege. GLE = %d`
- `0x180012c3d`: `SeRestorePrivilege`
- `0x180012cce`: `SeRestorePrivilege`
- `0x180012c65`: `Enable RESTORE privilege. GLE = %d`
- `0x180012be8`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180012c95`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180012d83`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180012e57`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180013003`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x1800130b3`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180013143`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x180012d53`: `Looking for Windows.old directories in %s...`
- `0x180012daf`: `Windows.old*`
- `0x180012e2e`: `%d Windows.old directories were found`
- `0x180012fd3`: `Failed to delete the %s directory. GLE = %d`

## pseudocode

```c
__int64 __fastcall CWindowsOldJob::Run(CWindowsOldJob *a1, struct IStopCallback *a2)
{
  int v4; // esi
  DWORD LastError; // edi
  __int64 v6; // rbx
  DWORD v7; // eax
  struct tagLOG_PARTIAL_MSG *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // esi
  DWORD v12; // edi
  __int64 v13; // rbx
  DWORD v14; // eax
  struct tagLOG_PARTIAL_MSG *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  const struct UnBCL::String *v18; // rax
  struct UnBCL::String *v19; // rax
  DWORD v20; // ebx
  __int64 v21; // rdi
  const wchar_t *CString; // rax
  UnBCL::String *P; // rax
  struct tagLOG_PARTIAL_MSG *v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 Directories; // rax
  DWORD v28; // edi
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 (__fastcall ***v31)(_QWORD); // rcx
  int v32; // eax
  struct tagLOG_PARTIAL_MSG *v33; // rax
  __int64 v34; // rax
  __int64 (__fastcall ***v35)(_QWORD); // rcx
  __int64 v36; // rax
  __int64 v37; // rdi
  const struct UnBCL::String *v38; // rbx
  const struct UnBCL::String *v39; // rax
  struct UnBCL::String *v40; // rax
  struct UnBCL::String *v41; // rax
  const struct UnBCL::String *v42; // rax
  const struct UnBCL::String *v43; // rax
  const struct UnBCL::String *v44; // rax
  DWORD v45; // ebx
  __int64 v46; // rsi
  DWORD v47; // r15d
  const wchar_t *v48; // rax
  UnBCL::String *v49; // rax
  struct tagLOG_PARTIAL_MSG *v50; // rax
  unsigned int v51; // esi
  DWORD v52; // edi
  __int64 v53; // rbx
  struct tagLOG_PARTIAL_MSG *v54; // rax
  __int64 v55; // rax
  int v56; // r14d
  DWORD v57; // edi
  __int64 v58; // rbx
  struct tagLOG_PARTIAL_MSG *v59; // rax
  int v61; // [rsp+60h] [rbp-A0h] BYREF
  int v62; // [rsp+64h] [rbp-9Ch] BYREF
  int v63; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v64[24]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v65[24]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v66[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v67[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v68[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v69[96]; // [rsp+E0h] [rbp-20h] BYREF

  v61 = 0;
  v63 = 0;
  v62 = 0;
  v4 = EnablePrivilegeEx(L"SeBackupPrivilege");
  LastError = GetLastError();
  v6 = CurrentIP();
  v7 = GetLastError();
  v8 = ConstructPartialMsgW(0x4000000u, "Enable BACKUP privilege. GLE = %d", v7);
  WdsSetupLogMessageW(
    v8,
    0,
    L"D",
    0,
    825,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
    L"CWindowsOldJob::Run",
    v6,
    LastError,
    0,
    0);
  LOBYTE(v9) = v4 != 0;
  MakeGuardIF<int (*)(unsigned short const *,int),unsigned short const *,int>(v69, v9, v10, L"SeBackupPrivilege");
  v11 = EnablePrivilegeEx(L"SeRestorePrivilege");
  v12 = GetLastError();
  v13 = CurrentIP();
  v14 = GetLastError();
  v15 = ConstructPartialMsgW(0x4000000u, "Enable RESTORE privilege. GLE = %d", v14);
  WdsSetupLogMessageW(
    v15,
    0,
    L"D",
    0,
    830,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
    L"CWindowsOldJob::Run",
    v13,
    v12,
    0,
    0);
  LOBYTE(v16) = v11 != 0;
  MakeGuardIF<int (*)(unsigned short const *,int),unsigned short const *,int>(v68, v16, v17, L"SeRestorePrivilege");
  v18 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v64, L"%SystemDrive%\\");
  v19 = UnBCL::Environment::ExpandEnvironmentVariables(v18);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v65, v19);
  UnBCL::String::~String((UnBCL::String *)v64);
  v20 = GetLastError();
  v21 = CurrentIP();
  if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v65) )
  {
    P = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v65);
    CString = UnBCL::String::get_CString(P);
  }
  else
  {
    CString = L"(NULL)";
  }
  v24 = ConstructPartialMsgW(0x4000000u, "Looking for Windows.old directories in %s...", (const char *)CString);
  WdsSetupLogMessageW(
    v24,
    0,
    L"D",
    0,
    837,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
    L"CWindowsOldJob::Run",
    v21,
    v20,
    0,
    0);
  v25 = UnBCL::String::String((UnBCL::String *)v64, L"Windows.old*");
  v26 = UnBCL::SmartPtr<UnBCL::String>::get_P(v65);
  Directories = UnBCL::Directory::GetDirectories(v26, v25, 0);
  UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v67, Directories);
  UnBCL::String::~String((UnBCL::String *)v64);
  v28 = GetLastError();
  v29 = CurrentIP();
  v30 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v67);
  v31 = (__int64 (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v30 + 8) + 12LL) + v30 + 8);
  v32 = (**v31)(v31);
  v33 = ConstructPartialMsgW(0x4000000u, "%d Windows.old directories were found", v32);
  WdsSetupLogMessageW(
    v33,
    0,
    L"D",
    0,
    839,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
    L"CWindowsOldJob::Run",
    v29,
    v28,
    0,
    0);
  v34 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v67);
  v35 = (__int64 (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v34 + 8) + 8LL) + v34 + 8);
  v36 = (**v35)(v35);
  UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>(v66, v36);
  v37 = v66[1];
  while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37) )
  {
    v38 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v37)(v37);
    v39 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v65);
    v40 = UnBCL::Path::Combine(v39, v38);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v64, v40);
    v41 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v64);
    CWindowsOldJob::ProcessWindowsOldDir(a1, v41, a2, &v61, &v63, &v62);
    v42 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v64);
    if ( UnBCL::Directory::Exists(v42) )
    {
      v43 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v64);
      if ( UnBCL::Directory::IsDirectoryEmpty(v43) )
      {
        v44 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v64);
        if ( !UnBCL::Directory::DeleteNE(v44, 0) )
        {
          v45 = GetLastError();
          v46 = CurrentIP();
          v47 = GetLastError();
          if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v64) )
          {
            v49 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v64);
            v48 = UnBCL::String::get_CString(v49);
          }
          else
          {
            v48 = L"(NULL)";
          }
          v50 = ConstructPartialMsgW(0x3000000u, "Failed to delete the %s directory. GLE = %d", (const char *)v48, v47);
          WdsSetupLogMessageW(
            v50,
            0,
            L"D",
            0,
            858,
            L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
            L"CWindowsOldJob::Run",
            v46,
            v45,
            0,
            0);
        }
      }
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v64);
  }
  if ( v61 )
  {
    v51 = 3;
  }
  else if ( v62 )
  {
    v51 = 4;
  }
  else
  {
    v51 = (v63 != 0) + 1;
  }
  if ( *((_QWORD *)a1 + 2) )
  {
    v52 = GetLastError();
    v53 = CurrentIP();
    v54 = ConstructPartialMsgW(0x4000000u, "Re-initialize Reserves.");
    WdsSetupLogMessageW(
      v54,
      0,
      L"D",
      0,
      889,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
      L"CWindowsOldJob::Run",
      v53,
      v52,
      0,
      0);
    v55 = (*(__int64 (__fastcall **)(_QWORD *))(**((_QWORD **)a1 + 2) + 8LL))(*((_QWORD **)a1 + 2));
    v56 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2);
    if ( v56 < 0 )
    {
      v57 = GetLastError();
      v58 = CurrentIP();
      v59 = ConstructPartialMsgW(0x3000000u, "CWindowsOldJob::Run: Failed to Initialize Reserves. hr = %x", v56);
      WdsSetupLogMessageW(
        v59,
        0,
        L"D",
        0,
        894,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
        L"CWindowsOldJob::Run",
        v58,
        v57,
        0,
        0);
    }
  }
  v66[0] = &UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<ISetupCleanupJob *>>::DeAssign(v66);
  UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v67);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v65);
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl2<int (*)(unsigned short const *,int),unsigned short const *,int>>(v68);
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl2<int (*)(unsigned short const *,int),unsigned short const *,int>>(v69);
  return v51;
}

```

## disassembly

```asm
0x180012b50  push    rbp
0x180012b52  push    rbx
0x180012b53  push    rsi
0x180012b54  push    rdi
0x180012b55  push    r12
0x180012b57  push    r13
0x180012b59  push    r14
0x180012b5b  push    r15
0x180012b5d  lea     rbp, [rsp-8]
0x180012b62  sub     rsp, 108h
0x180012b69  mov     r12, rdx
0x180012b6c  mov     r14, rcx
0x180012b6f  xor     r13d, r13d
0x180012b72  mov     [rsp+140h+var_E0], r13d
0x180012b77  mov     [rsp+140h+var_D8], r13d
0x180012b7c  mov     [rsp+140h+var_DC], r13d
0x180012b81  mov     [rbp+40h+arg_0], r13d
0x180012b85  lea     r8, [rbp+40h+arg_0]
0x180012b89  lea     r15d, [r13+1]
0x180012b8d  mov     edx, r15d
0x180012b90  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x180012b97  call    EnablePrivilegeEx
0x180012b9c  mov     esi, eax
0x180012b9e  call    cs:__imp_GetLastError
0x180012ba4  mov     edi, eax
0x180012ba6  call    cs:__imp_CurrentIP
0x180012bac  mov     rbx, rax
0x180012baf  call    cs:__imp_GetLastError
0x180012bb5  mov     r8d, eax
0x180012bb8  lea     rdx, aEnableBackupPr; "Enable BACKUP privilege. GLE = %d"
0x180012bbf  mov     ecx, 4000000h; unsigned int
0x180012bc4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180012bc9  mov     [rsp+140h+var_F0], r13d
0x180012bce  mov     [rsp+140h+var_F8], r13
0x180012bd3  mov     [rsp+140h+var_100], edi
0x180012bd7  mov     [rsp+140h+var_108], rbx
0x180012bdc  lea     rcx, aCwindowsoldjob_5; "CWindowsOldJob::Run"
0x180012be3  mov     [rsp+140h+var_110], rcx
0x180012be8  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180012bef  mov     [rsp+140h+var_118], rcx
0x180012bf4  mov     dword ptr [rsp+140h+var_120], 339h
0x180012bfc  xor     r9d, r9d
0x180012bff  lea     r8, aD_0; "D"
0x180012c06  xor     edx, edx
0x180012c08  mov     rcx, rax
0x180012c0b  call    cs:__imp_WdsSetupLogMessageW
0x180012c11  test    esi, esi
0x180012c13  jz      short loc_180012C1E
0x180012c15  cmp     [rbp+40h+arg_0], r13d
0x180012c19  mov     dl, r15b
0x180012c1c  jz      short loc_180012C21
0x180012c1e  mov     dl, r13b
0x180012c21  lea     r9, aSebackupprivil; "SeBackupPrivilege"
0x180012c28  lea     rcx, [rbp+40h+var_60]
0x180012c2c  call    ??$MakeGuardIF@P6AHPEBGH@ZPEBGH@@YA?AV?$ScopeGuardImpl2@P6AHPEBGH@ZPEBGH@@_NP6AHPEBGH@Z1H@Z; MakeGuardIF<int (*)(ushort const *,int),ushort const *,int>(bool,int (*)(ushort const *,int),ushort const *,int)
0x180012c31  nop
0x180012c32  mov     [rbp+40h+arg_0], r13d
0x180012c36  lea     r8, [rbp+40h+arg_0]
0x180012c3a  mov     edx, r15d
0x180012c3d  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180012c44  call    EnablePrivilegeEx
0x180012c49  mov     esi, eax
0x180012c4b  call    cs:__imp_GetLastError
0x180012c51  mov     edi, eax
0x180012c53  call    cs:__imp_CurrentIP
0x180012c59  mov     rbx, rax
0x180012c5c  call    cs:__imp_GetLastError
0x180012c62  mov     r8d, eax
0x180012c65  lea     rdx, aEnableRestoreP; "Enable RESTORE privilege. GLE = %d"
0x180012c6c  mov     ecx, 4000000h; unsigned int
0x180012c71  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180012c76  mov     [rsp+140h+var_F0], r13d
0x180012c7b  mov     [rsp+140h+var_F8], r13
0x180012c80  mov     [rsp+140h+var_100], edi
0x180012c84  mov     [rsp+140h+var_108], rbx
0x180012c89  lea     rcx, aCwindowsoldjob_5; "CWindowsOldJob::Run"
0x180012c90  mov     [rsp+140h+var_110], rcx
0x180012c95  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180012c9c  mov     [rsp+140h+var_118], rcx
0x180012ca1  mov     dword ptr [rsp+140h+var_120], 33Eh
0x180012ca9  xor     r9d, r9d
0x180012cac  lea     r8, aD_0; "D"
0x180012cb3  xor     edx, edx
0x180012cb5  mov     rcx, rax
0x180012cb8  call    cs:__imp_WdsSetupLogMessageW
0x180012cbe  test    esi, esi
0x180012cc0  jz      short loc_180012CCB
0x180012cc2  cmp     [rbp+40h+arg_0], r13d
0x180012cc6  mov     dl, r15b
0x180012cc9  jz      short loc_180012CCE
0x180012ccb  mov     dl, r13b
0x180012cce  lea     r9, aSerestoreprivi; "SeRestorePrivilege"
0x180012cd5  lea     rcx, [rbp+40h+var_80]
0x180012cd9  call    ??$MakeGuardIF@P6AHPEBGH@ZPEBGH@@YA?AV?$ScopeGuardImpl2@P6AHPEBGH@ZPEBGH@@_NP6AHPEBGH@Z1H@Z; MakeGuardIF<int (*)(ushort const *,int),ushort const *,int>(bool,int (*)(ushort const *,int),ushort const *,int)
0x180012cde  nop
0x180012cdf  lea     rdx, aSystemdrive_1; "%SystemDrive%\\"
0x180012ce6  lea     rcx, [rsp+140h+var_D0]
0x180012ceb  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180012cf1  nop
0x180012cf2  mov     rcx, rax
0x180012cf5  call    cs:__imp_?ExpandEnvironmentVariables@Environment@UnBCL@@SAPEAVString@2@PEBV32@@Z; UnBCL::Environment::ExpandEnvironmentVariables(UnBCL::String const *)
0x180012cfb  mov     rdx, rax
0x180012cfe  lea     rcx, [rbp+40h+var_B8]
0x180012d02  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180012d08  nop
0x180012d09  lea     rcx, [rsp+140h+var_D0]
0x180012d0e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180012d14  call    cs:__imp_GetLastError
0x180012d1a  mov     ebx, eax
0x180012d1c  call    cs:__imp_CurrentIP
0x180012d22  mov     rdi, rax
0x180012d25  lea     rcx, [rbp+40h+var_B8]
0x180012d29  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180012d2f  test    rax, rax
0x180012d32  jnz     short loc_180012D3D
0x180012d34  lea     rax, aNull; "(NULL)"
0x180012d3b  jmp     short loc_180012D50
0x180012d3d  lea     rcx, [rbp+40h+var_B8]
0x180012d41  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180012d47  mov     rcx, rax
0x180012d4a  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180012d50  mov     r8, rax
0x180012d53  lea     rdx, aLookingForWind; "Looking for Windows.old directories in "...
0x180012d5a  mov     ecx, 4000000h; unsigned int
0x180012d5f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180012d64  mov     [rsp+140h+var_F0], r13d
0x180012d69  mov     [rsp+140h+var_F8], r13
0x180012d6e  mov     [rsp+140h+var_100], ebx
0x180012d72  mov     [rsp+140h+var_108], rdi
0x180012d77  lea     rsi, aCwindowsoldjob_5; "CWindowsOldJob::Run"
0x180012d7e  mov     [rsp+140h+var_110], rsi
0x180012d83  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180012d8a  mov     [rsp+140h+var_118], rcx
0x180012d8f  mov     dword ptr [rsp+140h+var_120], 345h
0x180012d97  xor     r9d, r9d
0x180012d9a  lea     r15, aD_0; "D"
0x180012da1  mov     r8, r15
0x180012da4  xor     edx, edx
0x180012da6  mov     rcx, rax
0x180012da9  call    cs:__imp_WdsSetupLogMessageW
0x180012daf  lea     rdx, aWindowsOld; "Windows.old*"
0x180012db6  lea     rcx, [rsp+140h+var_D0]
0x180012dbb  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180012dc1  mov     rbx, rax
0x180012dc4  lea     rcx, [rbp+40h+var_B8]
0x180012dc8  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180012dce  xor     r8d, r8d
0x180012dd1  mov     rdx, rbx
0x180012dd4  mov     rcx, rax
0x180012dd7  call    cs:__imp_?GetDirectories@Directory@UnBCL@@SAPEAV?$Array@PEAVString@UnBCL@@@2@PEBVString@2@0H@Z; UnBCL::Directory::GetDirectories(UnBCL::String const *,UnBCL::String const *,int)
0x180012ddd  mov     rdx, rax
0x180012de0  lea     rcx, [rbp+40h+var_90]
0x180012de4  call    cs:__imp_??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(UnBCL::Array<UnBCL::String *> *)
0x180012dea  nop
0x180012deb  lea     rcx, [rsp+140h+var_D0]
0x180012df0  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180012df6  call    cs:__imp_GetLastError
0x180012dfc  mov     edi, eax
0x180012dfe  call    cs:__imp_CurrentIP
0x180012e04  mov     rbx, rax
0x180012e07  lea     rcx, [rbp+40h+var_90]
0x180012e0b  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x180012e11  mov     rcx, [rax+8]
0x180012e15  movsxd  rdx, dword ptr [rcx+0Ch]
0x180012e19  lea     rcx, [rax+8]
0x180012e1d  add     rcx, rdx
0x180012e20  mov     rdx, [rcx]
0x180012e23  mov     rax, [rdx]
0x180012e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e2b  mov     r8d, eax
0x180012e2e  lea     rdx, aDWindowsOldDir; "%d Windows.old directories were found"
0x180012e35  mov     ecx, 4000000h; unsigned int
0x180012e3a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180012e3f  mov     [rsp+140h+var_F0], r13d
0x180012e44  mov     [rsp+140h+var_F8], r13
0x180012e49  mov     [rsp+140h+var_100], edi
0x180012e4d  mov     [rsp+140h+var_108], rbx
0x180012e52  mov     [rsp+140h+var_110], rsi
0x180012e57  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180012e5e  mov     [rsp+140h+var_118], rcx
0x180012e63  mov     dword ptr [rsp+140h+var_120], 347h
0x180012e6b  xor     r9d, r9d
0x180012e6e  mov     r8, r15
0x180012e71  xor     edx, edx
0x180012e73  mov     rcx, rax
0x180012e76  call    cs:__imp_WdsSetupLogMessageW
0x180012e7c  lea     rcx, [rbp+40h+var_90]
0x180012e80  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x180012e86  mov     rcx, [rax+8]
0x180012e8a  movsxd  rdx, dword ptr [rcx+8]
0x180012e8e  lea     rcx, [rax+8]
0x180012e92  add     rcx, rdx
0x180012e95  mov     rax, [rcx]
0x180012e98  mov     rax, [rax]
0x180012e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ea0  mov     rdx, rax
0x180012ea3  lea     rcx, [rbp+40h+var_A0]
0x180012ea7  call    ??0?$SmartPtr@U?$IEnumerator@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAU?$IEnumerator@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>(UnBCL::IEnumerator<UnBCL::String *> *)
0x180012eac  nop
0x180012ead  mov     rdi, [rbp+40h+var_98]
0x180012eb1  mov     rax, [rdi]
0x180012eb4  mov     rcx, rdi
0x180012eb7  mov     rax, [rax+8]
0x180012ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ec0  test    eax, eax
0x180012ec2  jz      loc_180013040
0x180012ec8  mov     rax, [rdi]
0x180012ecb  mov     rcx, rdi
0x180012ece  mov     rax, [rax]
0x180012ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ed6  mov     rbx, rax
0x180012ed9  lea     rcx, [rbp+40h+var_B8]
0x180012edd  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180012ee3  mov     rcx, rax
0x180012ee6  mov     rdx, rbx
0x180012ee9  call    cs:__imp_?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z; UnBCL::Path::Combine(UnBCL::String const *,UnBCL::String const *)
0x180012eef  mov     rdx, rax
0x180012ef2  lea     rcx, [rsp+140h+var_D0]
0x180012ef7  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180012efd  nop
0x180012efe  lea     rcx, [rsp+140h+var_D0]
0x180012f03  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180012f09  mov     rdx, rax; struct UnBCL::String *
0x180012f0c  lea     rax, [rsp+140h+var_DC]
0x180012f11  mov     [rsp+140h+var_118], rax; int *
0x180012f16  lea     rax, [rsp+140h+var_D8]
0x180012f1b  mov     [rsp+140h+var_120], rax; int *
0x180012f20  lea     r9, [rsp+140h+var_E0]; int *
0x180012f25  mov     r8, r12; struct IStopCallback *
0x180012f28  mov     rcx, r14; this
0x180012f2b  call    ?ProcessWindowsOldDir@CWindowsOldJob@@AEAAXPEAVString@UnBCL@@PEAVIStopCallback@@PEAH22@Z; CWindowsOldJob::ProcessWindowsOldDir(UnBCL::String *,IStopCallback *,int *,int *,int *)
0x180012f30  lea     rcx, [rsp+140h+var_D0]
0x180012f35  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180012f3b  mov     rcx, rax
0x180012f3e  call    cs:__imp_?Exists@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::Exists(UnBCL::String const *)
0x180012f44  test    eax, eax
0x180012f46  jz      loc_180013030
0x180012f4c  lea     rcx, [rsp+140h+var_D0]
0x180012f51  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180012f57  mov     rcx, rax
0x180012f5a  call    cs:__imp_?IsDirectoryEmpty@Directory@UnBCL@@SAHPEBVString@2@@Z; UnBCL::Directory::IsDirectoryEmpty(UnBCL::String const *)
0x180012f60  test    eax, eax
0x180012f62  jz      loc_180013030
0x180012f68  lea     rcx, [rsp+140h+var_D0]
0x180012f6d  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180012f73  mov     rcx, rax
0x180012f76  xor     edx, edx
0x180012f78  call    cs:__imp_?DeleteNE@Directory@UnBCL@@SAHPEBVString@2@H@Z; UnBCL::Directory::DeleteNE(UnBCL::String const *,int)
0x180012f7e  test    eax, eax
0x180012f80  jnz     loc_180013030
0x180012f86  call    cs:__imp_GetLastError
0x180012f8c  mov     ebx, eax
0x180012f8e  call    cs:__imp_CurrentIP
0x180012f94  mov     rsi, rax
0x180012f97  call    cs:__imp_GetLastError
0x180012f9d  mov     r15d, eax
0x180012fa0  lea     rcx, [rsp+140h+var_D0]
0x180012fa5  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180012fab  test    rax, rax
0x180012fae  jnz     short loc_180012FB9
0x180012fb0  lea     rax, aNull; "(NULL)"
0x180012fb7  jmp     short loc_180012FCD
0x180012fb9  lea     rcx, [rsp+140h+var_D0]
0x180012fbe  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180012fc4  mov     rcx, rax
0x180012fc7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180012fcd  mov     r9d, r15d
0x180012fd0  mov     r8, rax
0x180012fd3  lea     rdx, aFailedToDelete_6; "Failed to delete the %s directory. GLE "...
0x180012fda  mov     ecx, 3000000h; unsigned int
0x180012fdf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180012fe4  mov     [rsp+140h+var_F0], r13d
0x180012fe9  mov     [rsp+140h+var_F8], r13
0x180012fee  mov     [rsp+140h+var_100], ebx
0x180012ff2  mov     [rsp+140h+var_108], rsi
0x180012ff7  lea     rcx, aCwindowsoldjob_5; "CWindowsOldJob::Run"
0x180012ffe  mov     [rsp+140h+var_110], rcx
0x180013003  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x18001300a  mov     [rsp+140h+var_118], rcx
0x18001300f  mov     dword ptr [rsp+140h+var_120], 35Ah
0x180013017  xor     r9d, r9d
0x18001301a  lea     r15, aD_0; "D"
0x180013021  mov     r8, r15
0x180013024  xor     edx, edx
0x180013026  mov     rcx, rax
0x180013029  call    cs:__imp_WdsSetupLogMessageW
0x18001302f  nop
0x180013030  lea     rcx, [rsp+140h+var_D0]
0x180013035  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18001303b  jmp     loc_180012EB1
0x180013040  cmp     [rsp+140h+var_E0], r13d
0x180013045  jz      short loc_18001304E
0x180013047  mov     esi, 3
0x18001304c  jmp     short loc_180013068
0x18001304e  cmp     [rsp+140h+var_DC], r13d
0x180013053  jz      short loc_18001305C
0x180013055  mov     esi, 4
0x18001305a  jmp     short loc_180013068
0x18001305c  mov     eax, [rsp+140h+var_D8]
0x180013060  neg     eax
  ... truncated ...
```
