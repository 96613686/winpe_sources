# CFlowControlValidator::ValidatePhase(IExecutionContext *,COperationQueue *,OP_EXECUTION_PHASE,PHASE_EXECUTION_POINT)

- ea: `0x180216f50`
- end: `0x180217ee1`
- name: `?ValidatePhase@CFlowControlValidator@@UEAAJPEAUIExecutionContext@@PEAVCOperationQueue@@W4OP_EXECUTION_PHASE@@W4PHASE_EXECUTION_POINT@@@Z`
- size: `3985`
- prototype: `int __high(struct IExecutionContext *, struct COperationQueue *, enum OP_EXECUTION_PHASE, enum PHASE_EXECUTION_POINT)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180057dec`
- `0x1800ae6b4`
- `0x1802078b4`
- `0x18020f17c`
- `0x180216f50`
- `0x18021b564`
- `0x1802c6158`
- `0x1802d021c`
- `0x1802d0e40`
- `0x1802d147c`
- `0x1802d8bfc`
- `0x1802e0ff0`
- `0x1802e2078`
- `0x18034f794`
- `0x18034f808`
- `0x180362788`
- `0x18040c348`
- `0x180509010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18021714a`
- `ADVAPI32!RegCloseKey` at `0x1802171f6`
- `ADVAPI32!RegCloseKey` at `0x18021714a`
- `ADVAPI32!RegCloseKey` at `0x1802171f6`
- `ADVAPI32!RegSetValueExW` at `0x1802171e9`
- `ADVAPI32!RegSetValueExW` at `0x1802171e9`
- `ADVAPI32!RegCreateKeyExW` at `0x1802171bd`
- `ADVAPI32!RegCreateKeyExW` at `0x1802171bd`
- `ADVAPI32!RegOpenKeyExW` at `0x1802170ef`
- `ADVAPI32!RegOpenKeyExW` at `0x1802170ef`
- `ADVAPI32!RegQueryValueExW` at `0x180217129`
- `ADVAPI32!RegQueryValueExW` at `0x180217129`
- `KERNEL32!GetProcessHeap` at `0x180217bbe`
- `KERNEL32!GetProcessHeap` at `0x180217bbe`
- `KERNEL32!HeapFree` at `0x180217bcc`
- `KERNEL32!HeapFree` at `0x180217bcc`
- `KERNEL32!GetLastError` at `0x18021701b`
- `KERNEL32!GetLastError` at `0x18021720c`
- `KERNEL32!GetLastError` at `0x180217222`
- `KERNEL32!GetLastError` at `0x180217242`
- `KERNEL32!GetLastError` at `0x1802173ad`
- `KERNEL32!GetLastError` at `0x1802174b9`
- `KERNEL32!GetLastError` at `0x180217571`
- `KERNEL32!GetLastError` at `0x1802176b1`
- `KERNEL32!GetLastError` at `0x18021774b`
- `KERNEL32!GetLastError` at `0x1802177ea`
- `KERNEL32!GetLastError` at `0x1802179c0`
- `KERNEL32!GetLastError` at `0x180217a6a`
- `KERNEL32!GetLastError` at `0x180217bd4`
- `KERNEL32!GetLastError` at `0x180217d3d`
- `KERNEL32!GetLastError` at `0x180217dd8`
- `KERNEL32!GetLastError` at `0x18021701b`
- `KERNEL32!GetLastError` at `0x18021720c`
- `KERNEL32!GetLastError` at `0x180217222`
- `KERNEL32!GetLastError` at `0x180217242`
- `KERNEL32!GetLastError` at `0x1802173ad`
- `KERNEL32!GetLastError` at `0x1802174b9`
- `KERNEL32!GetLastError` at `0x180217571`
- `KERNEL32!GetLastError` at `0x1802176b1`
- `KERNEL32!GetLastError` at `0x18021774b`
- `KERNEL32!GetLastError` at `0x1802177ea`
- `KERNEL32!GetLastError` at `0x1802179c0`
- `KERNEL32!GetLastError` at `0x180217a6a`
- `KERNEL32!GetLastError` at `0x180217bd4`
- `KERNEL32!GetLastError` at `0x180217d3d`
- `KERNEL32!GetLastError` at `0x180217dd8`
- `KERNEL32!SetLastError` at `0x180217152`
- `KERNEL32!SetLastError` at `0x180217163`
- `KERNEL32!SetLastError` at `0x1802171fe`
- `KERNEL32!SetLastError` at `0x180217152`
- `KERNEL32!SetLastError` at `0x180217163`
- `KERNEL32!SetLastError` at `0x1802171fe`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180217606`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180217afe`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180217606`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x180217afe`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x180217697`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x180217697`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802174a2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180217545`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180217685`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180217733`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180217d1b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1802174a2`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180217545`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180217685`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180217733`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180217d1b`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217488`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217626`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802176a7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217882`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217902`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217a64`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217b1e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217c72`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217eb3`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217488`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217626`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1802176a7`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217882`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217902`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217a64`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217b1e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217c72`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x180217eb3`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18021746a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802175e9`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180217677`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180217861`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802178e1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180217a45`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180217ae1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180217c56`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180217e92`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18021746a`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802175e9`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180217677`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180217861`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1802178e1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180217a45`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180217ae1`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180217c56`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180217e92`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180217894`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180217e45`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180217894`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180217e45`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180217634`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180217b2c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180217b7e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180217634`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180217b2c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180217b7e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18021763d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180217b35`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180217b87`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18021763d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180217b35`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180217b87`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802177c8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802177d7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180217c81`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802177c8`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1802177d7`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180217c81`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180217617`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180217661`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180217b0f`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180217617`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180217661`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180217b0f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217084`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802172a7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18021740f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18021751e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217713`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802177b0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18021784c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217a22`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217acc`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217c36`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217da2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217e33`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217084`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802172a7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18021740f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18021751e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217713`
- `WDSCORE!WdsSetupLogMessageW` at `0x1802177b0`
- `WDSCORE!WdsSetupLogMessageW` at `0x18021784c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217a22`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217acc`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217c36`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217da2`
- `WDSCORE!WdsSetupLogMessageW` at `0x180217e33`
- `WDSCORE!CurrentIP` at `0x180217023`
- `WDSCORE!CurrentIP` at `0x18021724a`
- `WDSCORE!CurrentIP` at `0x1802173b5`
- `WDSCORE!CurrentIP` at `0x1802174c1`
- `WDSCORE!CurrentIP` at `0x180217579`
- `WDSCORE!CurrentIP` at `0x1802176b9`
- `WDSCORE!CurrentIP` at `0x180217753`
- `WDSCORE!CurrentIP` at `0x1802177f2`
- `WDSCORE!CurrentIP` at `0x1802179c8`
- `WDSCORE!CurrentIP` at `0x180217a72`
- `WDSCORE!CurrentIP` at `0x180217bdc`
- `WDSCORE!CurrentIP` at `0x180217d45`
- `WDSCORE!CurrentIP` at `0x180217de0`
- `WDSCORE!CurrentIP` at `0x180217023`
- `WDSCORE!CurrentIP` at `0x18021724a`
- `WDSCORE!CurrentIP` at `0x1802173b5`
- `WDSCORE!CurrentIP` at `0x1802174c1`
- `WDSCORE!CurrentIP` at `0x180217579`
- `WDSCORE!CurrentIP` at `0x1802176b9`
- `WDSCORE!CurrentIP` at `0x180217753`
- `WDSCORE!CurrentIP` at `0x1802177f2`
- `WDSCORE!CurrentIP` at `0x1802179c8`
- `WDSCORE!CurrentIP` at `0x180217a72`
- `WDSCORE!CurrentIP` at `0x180217bdc`
- `WDSCORE!CurrentIP` at `0x180217d45`
- `WDSCORE!CurrentIP` at `0x180217de0`

## string_xrefs

- `0x180216ff1`: `SP_INSTALL_INFO`
- `0x180217852`: `StartServices`
- `0x180217a36`: `StartServices`
- `0x180217c4a`: `StartServices`
- `0x180217b58`: `Migration.Services.Deferred`
- `0x180217be5`: `No deferred service to enable`
- `0x18021745b`: `OOBEBootApplyComplete`
- `0x180216fea`: `InstallFlowType`
- `0x180217256`: `Failed to increment boot removal attempts. Error = 0x%08X`
- `0x1802174cd`: `Failed to set setup completion status. Error = 0x%08X`
- `0x180217a7b`: `FLOWTRACK: All migration completed, restoring all services disabled by upgrade`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CFlowControlValidator::ValidatePhase(
        CFlowControlValidator *a1,
        struct IExecutionContext *a2,
        struct COperationQueue *a3,
        int a4,
        int a5)
{
  int v8; // r14d
  __int64 v9; // rax
  __int64 v10; // rdi
  void (__fastcall *v11)(__int64, const wchar_t *, const wchar_t *, _QWORD); // rbx
  unsigned int v12; // eax
  __int64 v13; // rcx
  DWORD LastError; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  LSTATUS v17; // eax
  LSTATUS v18; // ebx
  int v19; // eax
  LSTATUS Key; // ebx
  signed int v21; // eax
  bool v22; // sf
  signed int v23; // eax
  unsigned int v24; // r14d
  DWORD v25; // edi
  __int64 v26; // rbx
  struct tagLOG_PARTIAL_MSG *v27; // rax
  __int64 v28; // rcx
  __int64 i; // rbx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  DWORD v40; // edi
  __int64 v41; // rbx
  struct tagLOG_PARTIAL_MSG *v42; // rax
  BOOL v43; // ebx
  struct UnBCL::String *v44; // rax
  int v45; // r8d
  struct UnBCL::String *P; // rax
  struct UnBCL::String *v47; // rax
  struct UnBCL::String *v48; // rdx
  DWORD v49; // edi
  __int64 v50; // rbx
  struct tagLOG_PARTIAL_MSG *v51; // rax
  void (__fastcall *v52)(struct IExecutionContext *, __int64, char *); // rdi
  CBool *v53; // rax
  CBool *v54; // rdx
  char *v55; // rbx
  __int64 v56; // rax
  DWORD cbData; // [rsp+60h] [rbp-E8h] BYREF
  DWORD Type; // [rsp+68h] [rbp-E0h] BYREF
  _DWORD *v60; // [rsp+70h] [rbp-D8h]
  HKEY hKey[3]; // [rsp+78h] [rbp-D0h] BYREF
  _BYTE v62[24]; // [rsp+90h] [rbp-B8h] BYREF
  _BYTE v63[72]; // [rsp+A8h] [rbp-A0h] BYREF
  __int64 v64; // [rsp+F0h] [rbp-58h]
  int Data; // [rsp+168h] [rbp+20h] BYREF

  v64 = -2;
  v8 = CFlowControlValidator::ExecuteFlowAssessment(a1, a2, a3, a4 == 3);
  if ( v8 < 0 || a4 != 3 || a5 != 2 )
    return (unsigned int)v8;
  v9 = (*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 64LL))(a2);
  v10 = v9;
  v60 = (_DWORD *)v9;
  if ( v9 )
  {
    v11 = *(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v9 + 24LL);
    v12 = (*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 40LL))(a2);
    v11(v10, L"SP_INSTALL_INFO", L"InstallFlowType", v12);
  }
  if ( (*(int (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 40LL))(a2) >= 4 )
  {
    LastError = GetLastError();
    v15 = CurrentIP();
    v16 = ConstructPartialMsgW(0x4000000u, "FLOWTRACK: Will proceed with SafeOS boot removal.");
    WdsSetupLogMessageW(
      v16,
      819200,
      L"D",
      0,
      4434,
      L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
      L"CFlowControlValidator::ValidatePhase",
      v15,
      LastError,
      0,
      0);
    if ( v60 )
      (*(void (__fastcall **)(_DWORD *, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v60 + 16LL))(
        v60,
        L"SP_WINRE_INFO",
        L"WinREPhaseSkip",
        L"Proceed");
    hKey[0] = 0;
    Data = 0;
    cbData = 4;
    Type = 0;
    v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x20019u, hKey);
    if ( v17 || !hKey[0] )
    {
      SetLastError(v17);
      v19 = 0;
      goto LABEL_17;
    }
    v18 = RegQueryValueExW(hKey[0], L"UPGSafeOSBootRemovalCount", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v18 )
    {
      if ( cbData == 4 )
      {
LABEL_15:
        RegCloseKey(hKey[0]);
        SetLastError(v18);
        v19 = Data;
LABEL_17:
        Type = v19 + 1;
        hKey[0] = 0;
        Data = 0;
        Key = RegCreateKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SYSTEM\\Setup",
                0,
                (LPWSTR)&Class,
                0,
                0x20006u,
                0,
                hKey,
                (LPDWORD)&Data);
        if ( !Key )
        {
          Key = RegSetValueExW(hKey[0], L"UPGSafeOSBootRemovalCount", 0, 4u, (const BYTE *)&Type, 4u);
          RegCloseKey(hKey[0]);
        }
        SetLastError(Key);
        if ( Key )
        {
          v21 = GetLastError();
          v22 = v21 < 0;
          if ( v21 > 0 )
            v22 = 1;
          if ( v22 )
          {
            v23 = GetLastError();
            v24 = v23;
            if ( v23 > 0 )
              v24 = (unsigned __int16)v23 | 0x80070000;
          }
          else
          {
            v24 = -2147467259;
          }
          v25 = GetLastError();
          v26 = CurrentIP();
          v27 = ConstructPartialMsgW(0x2000000u, "Failed to increment boot removal attempts. Error = 0x%08X", v24);
          WdsSetupLogMessageW(
            v27,
            819200,
            L"D",
            0,
            4447,
            L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
            L"CFlowControlValidator::ValidatePhase",
            v26,
            v25,
            0,
            0);
          v8 = 0;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow>::GetImpl'::`2'::impl) )
        {
          for ( i = 0; i != 11; ++i )
            CFlowControlValidator::RemoveOperation(v28, a3, (unsigned int)dword_1805C44C0[i]);
        }
        else
        {
          CFlowControlValidator::RemoveOperation(v28, a3, 75);
          CFlowControlValidator::RemoveOperation(v30, a3, 76);
          CFlowControlValidator::RemoveOperation(v31, a3, 77);
          CFlowControlValidator::RemoveOperation(v32, a3, 78);
          CFlowControlValidator::RemoveOperation(v33, a3, 83);
          CFlowControlValidator::RemoveOperation(v34, a3, 56);
          CFlowControlValidator::RemoveOperation(v35, a3, 95);
          CFlowControlValidator::RemoveOperation(v36, a3, 96);
          CFlowControlValidator::RemoveOperation(v37, a3, 138);
          CFlowControlValidator::RemoveOperation(v38, a3, 115);
          CFlowControlValidator::RemoveOperation(v39, a3, 114);
        }
        (*(void (__fastcall **)(struct COperationQueue *, __int64))(*(_QWORD *)a3 + 8LL))(a3, 4);
        if ( (*(int (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 40LL))(a2) >= 5 )
        {
          v40 = GetLastError();
          v41 = CurrentIP();
          v42 = ConstructPartialMsgW(0x4000000u, "FLOWTRACK: Will proceed with First boot removal.");
          WdsSetupLogMessageW(
            v42,
            819200,
            L"D",
            0,
            4482,
            L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
            L"CFlowControlValidator::ValidatePhase",
            v41,
            v40,
            0,
            0);
          if ( v60 )
            (*(void (__fastcall **)(_DWORD *, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v60 + 16LL))(
              v60,
              L"SP_FIRSTBOOT_INFO",
              L"FirstBootSkip",
              L"Proceed");
          Type = (*(__int64 (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 40LL))(a2);
          v43 = (int)Type >= 6;
          v44 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v63, L"OOBEBootApplyComplete");
          cbData = SPGetStoredBOOL(a2, v44, v45);
          UnBCL::String::~String((UnBCL::String *)v63);
          v60 = (_DWORD *)((char *)a1 + 72);
          P = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)a1 + 72);
          SPExecuteFirstBootCompletion(P, v43);
        }
        Type = v8 >= 0;
        goto LABEL_38;
      }
      v18 = 13;
    }
    Data = 0;
    goto LABEL_15;
  }
  Type = 0;
  CFlowControlValidator::RemoveOperation(v13, a3, 112);
LABEL_38:
  Data = 0;
  if ( (unsigned int)COperationQueue::IsOperationPresent(a3, 64)
    && (unsigned int)COperationQueue::IsOperationExecuted(a3, 64) )
  {
    if ( !*((_DWORD *)a1 + 25) )
    {
      cbData = 0;
      (*(void (__fastcall **)(struct IExecutionContext *))(*(_QWORD *)a2 + 24LL))(a2);
      v47 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)a1 + 72);
      SPEvaluateRespecializeCompletionStatus(v47, v48, (int *)&cbData, &Data);
    }
    if ( *((_DWORD *)a1 + 27) )
    {
      v49 = GetLastError();
      v50 = CurrentIP();
      v51 = ConstructPartialMsgW(0x4000000u, "FLOWTRACK: Respecialize required to run online");
      WdsSetupLogMessageW(
        v51,
        819200,
        L"D",
        0,
        4697,
        L"base\\ntsetup\\setupplatform\\lib\\src\\datamigration.cpp",
        L"CFlowControlValidator::ValidatePhase",
        v50,
        v49,
        0,
        0);
      v52 = *(void (__fastcall **)(struct IExecutionContext *, __int64, char *))(*(_QWORD *)a2 + 96LL);
      v53 = (CBool *)UnBCL::Object::operator new(0x40u);
      v60 = v53;
      if ( v53 )
        v54 = CBool::CBool(v53, 1);
      else
        v54 = 0;
      if ( v54 )
        v55 = (char *)v54 + *(int *)(*((_QWORD *)v54 + 1) + 8LL) + 8;
      else
        v55 = 0;
      v56 = UnBCL::String::String((UnBCL::String *)v62, L"CallRespecializeOnline");
      v52(a2, v56, v55);
      UnBCL::String::~String((UnBCL::String *)v62);
    }
  }
  if ( Type )
    return (unsigned int)-2147023659;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180216f50  mov     rax, rsp
0x180216f53  mov     [rax+18h], r8
0x180216f57  mov     [rax+10h], rdx
0x180216f5b  mov     [rax+8], rcx
0x180216f5f  push    rbx
0x180216f60  push    rsi
0x180216f61  push    rdi
0x180216f62  push    r12
0x180216f64  push    r13
0x180216f66  push    r14
0x180216f68  push    r15
0x180216f6a  sub     rsp, 110h
0x180216f71  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x180216f79  mov     ebx, r9d
0x180216f7c  mov     r12, r8
0x180216f7f  mov     r15, rdx
0x180216f82  xor     esi, esi
0x180216f84  mov     r9d, esi
0x180216f87  cmp     ebx, 3
0x180216f8a  setz    r9b; int
0x180216f8e  call    ?ExecuteFlowAssessment@CFlowControlValidator@@IEAAJPEAUIExecutionContext@@PEAVCOperationQueue@@H@Z; CFlowControlValidator::ExecuteFlowAssessment(IExecutionContext *,COperationQueue *,int)
0x180216f93  mov     r14d, eax
0x180216f96  test    eax, eax
0x180216f98  js      loc_180217ECB
0x180216f9e  cmp     ebx, 3
0x180216fa1  jnz     loc_180217ECB
0x180216fa7  cmp     [rsp+148h+arg_20], 2
0x180216faf  jnz     loc_180217ECB
0x180216fb5  mov     rcx, [r15]
0x180216fb8  mov     rax, [rcx+40h]
0x180216fbc  mov     rcx, r15
0x180216fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216fc4  mov     rdi, rax
0x180216fc7  mov     [rsp+148h+var_D8], rax
0x180216fcc  test    rax, rax
0x180216fcf  jz      short loc_180217003
0x180216fd1  mov     rcx, [rax]
0x180216fd4  mov     rbx, [rcx+18h]
0x180216fd8  mov     rcx, [r15]
0x180216fdb  mov     rax, [rcx+28h]
0x180216fdf  mov     rcx, r15
0x180216fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180216fe7  mov     r9d, eax
0x180216fea  lea     r8, aInstallflowtyp; "InstallFlowType"
0x180216ff1  lea     rdx, aSpInstallInfo; "SP_INSTALL_INFO"
0x180216ff8  mov     rcx, rdi
0x180216ffb  mov     rax, rbx
0x180216ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217003  mov     rax, [r15]
0x180217006  mov     rcx, r15
0x180217009  mov     rax, [rax+28h]
0x18021700d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217012  cmp     eax, 4
0x180217015  jl      loc_180217CA5
0x18021701b  call    cs:__imp_GetLastError
0x180217021  mov     edi, eax
0x180217023  call    cs:__imp_CurrentIP
0x180217029  mov     rbx, rax
0x18021702c  lea     rdx, aFlowtrackWillP_0; "FLOWTRACK: Will proceed with SafeOS boo"...
0x180217033  mov     ecx, 4000000h; unsigned int
0x180217038  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18021703d  mov     [rsp+148h+var_F8], esi
0x180217041  mov     [rsp+148h+var_100], rsi
0x180217046  mov     dword ptr [rsp+148h+lpdwDisposition], edi
0x18021704a  mov     [rsp+148h+var_110], rbx
0x18021704f  lea     rcx, aCflowcontrolva; "CFlowControlValidator::ValidatePhase"
0x180217056  mov     [rsp+148h+lpSecurityAttributes], rcx
0x18021705b  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x180217062  mov     [rsp+148h+lpcbData], rcx
0x180217067  mov     dword ptr [rsp+148h+phkResult], 1152h
0x18021706f  xor     r9d, r9d
0x180217072  lea     r13, aD_0; "D"
0x180217079  mov     r8, r13
0x18021707c  mov     edx, 0C8000h
0x180217081  mov     rcx, rax
0x180217084  call    cs:__imp_WdsSetupLogMessageW
0x18021708a  mov     rcx, [rsp+148h+var_D8]
0x18021708f  test    rcx, rcx
0x180217092  jz      short loc_1802170B5
0x180217094  mov     rax, [rcx]
0x180217097  lea     r9, aProceed; "Proceed"
0x18021709e  lea     r8, aWinrephaseskip; "WinREPhaseSkip"
0x1802170a5  lea     rdx, aSpWinreInfo; "SP_WINRE_INFO"
0x1802170ac  mov     rax, [rax+10h]
0x1802170b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802170b5  mov     [rsp+148h+hKey], rsi
0x1802170ba  mov     [rsp+148h+Data], esi
0x1802170c1  mov     edi, 4
0x1802170c6  mov     [rsp+148h+cbData], edi
0x1802170ca  mov     [rsp+148h+Type], esi
0x1802170ce  lea     rax, [rsp+148h+hKey]
0x1802170d3  mov     [rsp+148h+phkResult], rax; phkResult
0x1802170d8  mov     r9d, 20019h; samDesired
0x1802170de  xor     r8d, r8d; ulOptions
0x1802170e1  lea     rdx, aSystemSetup_0; "SYSTEM\\Setup"
0x1802170e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802170ef  call    cs:__imp_RegOpenKeyExW
0x1802170f5  test    eax, eax
0x1802170f7  jnz     short loc_180217161
0x1802170f9  mov     rcx, [rsp+148h+hKey]; hKey
0x1802170fe  test    rcx, rcx
0x180217101  jz      short loc_180217161
0x180217103  lea     rax, [rsp+148h+cbData]
0x180217108  mov     [rsp+148h+lpcbData], rax; lpcbData
0x18021710d  lea     rax, [rsp+148h+Data]
0x180217115  mov     [rsp+148h+phkResult], rax; lpData
0x18021711a  lea     r9, [rsp+148h+Type]; lpType
0x18021711f  xor     r8d, r8d; lpReserved
0x180217122  lea     rdx, aUpgsafeosbootr; "UPGSafeOSBootRemovalCount"
0x180217129  call    cs:__imp_RegQueryValueExW
0x18021712f  mov     ebx, eax
0x180217131  test    eax, eax
0x180217133  jnz     short loc_18021713E
0x180217135  cmp     [rsp+148h+cbData], edi
0x180217139  jz      short loc_180217145
0x18021713b  lea     ebx, [rdi+9]
0x18021713e  mov     [rsp+148h+Data], esi
0x180217145  mov     rcx, [rsp+148h+hKey]; hKey
0x18021714a  call    cs:__imp_RegCloseKey
0x180217150  mov     ecx, ebx; dwErrCode
0x180217152  call    cs:__imp_SetLastError
0x180217158  mov     eax, [rsp+148h+Data]
0x18021715f  jmp     short loc_18021716B
0x180217161  mov     ecx, eax; dwErrCode
0x180217163  call    cs:__imp_SetLastError
0x180217169  mov     eax, esi
0x18021716b  inc     eax
0x18021716d  mov     [rsp+148h+Type], eax
0x180217171  mov     [rsp+148h+hKey], rsi
0x180217176  mov     [rsp+148h+Data], esi
0x18021717d  lea     rax, [rsp+148h+Data]
0x180217185  mov     [rsp+148h+lpdwDisposition], rax; lpdwDisposition
0x18021718a  lea     rax, [rsp+148h+hKey]
0x18021718f  mov     [rsp+148h+var_110], rax; phkResult
0x180217194  mov     [rsp+148h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180217199  mov     dword ptr [rsp+148h+lpcbData], 20006h; samDesired
0x1802171a1  mov     dword ptr [rsp+148h+phkResult], esi; dwOptions
0x1802171a5  lea     r9, Class; lpClass
0x1802171ac  xor     r8d, r8d; Reserved
0x1802171af  lea     rdx, aSystemSetup_0; "SYSTEM\\Setup"
0x1802171b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802171bd  call    cs:__imp_RegCreateKeyExW
0x1802171c3  mov     ebx, eax
0x1802171c5  test    eax, eax
0x1802171c7  jnz     short loc_1802171FC
0x1802171c9  mov     dword ptr [rsp+148h+lpcbData], edi; cbData
0x1802171cd  lea     rax, [rsp+148h+Type]
0x1802171d2  mov     [rsp+148h+phkResult], rax; lpData
0x1802171d7  mov     r9d, edi; dwType
0x1802171da  xor     r8d, r8d; Reserved
0x1802171dd  lea     rdx, aUpgsafeosbootr; "UPGSafeOSBootRemovalCount"
0x1802171e4  mov     rcx, [rsp+148h+hKey]; hKey
0x1802171e9  call    cs:__imp_RegSetValueExW
0x1802171ef  mov     ebx, eax
0x1802171f1  mov     rcx, [rsp+148h+hKey]; hKey
0x1802171f6  call    cs:__imp_RegCloseKey
0x1802171fc  mov     ecx, ebx; dwErrCode
0x1802171fe  call    cs:__imp_SetLastError
0x180217204  test    ebx, ebx
0x180217206  jz      loc_1802172B5
0x18021720c  call    cs:__imp_GetLastError
0x180217212  test    eax, eax
0x180217214  jle     short loc_180217220
0x180217216  movzx   eax, ax
0x180217219  or      eax, 80070000h
0x18021721e  test    eax, eax
0x180217220  jns     short loc_18021723C
0x180217222  call    cs:__imp_GetLastError
0x180217228  mov     r14d, eax
0x18021722b  test    eax, eax
0x18021722d  jle     short loc_180217242
0x18021722f  movzx   r14d, ax
0x180217233  or      r14d, 80070000h
0x18021723a  jmp     short loc_180217242
0x18021723c  mov     r14d, 80004005h
0x180217242  call    cs:__imp_GetLastError
0x180217248  mov     edi, eax
0x18021724a  call    cs:__imp_CurrentIP
0x180217250  mov     rbx, rax
0x180217253  mov     r8d, r14d
0x180217256  lea     rdx, aFailedToIncrem; "Failed to increment boot removal attemp"...
0x18021725d  mov     ecx, 2000000h; unsigned int
0x180217262  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180217267  mov     [rsp+148h+var_F8], esi
0x18021726b  mov     [rsp+148h+var_100], rsi
0x180217270  mov     dword ptr [rsp+148h+lpdwDisposition], edi
0x180217274  mov     [rsp+148h+var_110], rbx
0x180217279  lea     rcx, aCflowcontrolva; "CFlowControlValidator::ValidatePhase"
0x180217280  mov     [rsp+148h+lpSecurityAttributes], rcx
0x180217285  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x18021728c  mov     [rsp+148h+lpcbData], rcx
0x180217291  mov     dword ptr [rsp+148h+phkResult], 115Fh
0x180217299  xor     r9d, r9d
0x18021729c  mov     r8, r13
0x18021729f  mov     edx, 0C8000h
0x1802172a4  mov     rcx, rax
0x1802172a7  call    cs:__imp_WdsSetupLogMessageW
0x1802172ad  mov     r14d, esi
0x1802172b0  mov     edi, 4
0x1802172b5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow>::GetImpl(void)'::`2'::impl
0x1802172bc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupPlatform_NeoFlow>::__private_IsEnabled(void)
0x1802172c1  test    al, al
0x1802172c3  jz      short loc_1802172E9
0x1802172c5  mov     rbx, rsi
0x1802172c8  lea     r8, dword_1805C44C0
0x1802172cf  mov     r8d, [r8+rbx*4]
0x1802172d3  mov     rdx, r12
0x1802172d6  call    ?RemoveOperation@CFlowControlValidator@@IEAAXPEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::RemoveOperation(COperationQueue *,OP_OPERATION_ID)
0x1802172db  inc     rbx
0x1802172de  cmp     rbx, 0Bh
0x1802172e2  jnz     short loc_1802172C8
0x1802172e4  jmp     loc_180217383
0x1802172e9  mov     r8d, 4Bh ; 'K'
0x1802172ef  mov     rdx, r12
0x1802172f2  call    ?RemoveOperation@CFlowControlValidator@@IEAAXPEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::RemoveOperation(COperationQueue *,OP_OPERATION_ID)
0x1802172f7  mov     r8d, 4Ch ; 'L'
0x1802172fd  mov     rdx, r12
0x180217300  call    ?RemoveOperation@CFlowControlValidator@@IEAAXPEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::RemoveOperation(COperationQueue *,OP_OPERATION_ID)
0x180217305  mov     r8d, 4Dh ; 'M'
0x18021730b  mov     rdx, r12
0x18021730e  call    ?RemoveOperation@CFlowControlValidator@@IEAAXPEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::RemoveOperation(COperationQueue *,OP_OPERATION_ID)
0x180217313  mov     r8d, 4Eh ; 'N'
0x180217319  mov     rdx, r12
0x18021731c  call    ?RemoveOperation@CFlowControlValidator@@IEAAXPEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::RemoveOperation(COperationQueue *,OP_OPERATION_ID)
0x180217321  mov     r8d, 53h ; 'S'
0x180217327  mov     rdx, r12
0x18021732a  call    ?RemoveOperation@CFlowControlValidator@@IEAAXPEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::RemoveOperation(COperationQueue *,OP_OPERATION_ID)
0x18021732f  mov     r8d, 38h ; '8'
0x180217335  mov     rdx, r12
0x180217338  call    ?RemoveOperation@CFlowControlValidator@@IEAAXPEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::RemoveOperation(COperationQueue *,OP_OPERATION_ID)
0x18021733d  mov     r8d, 5Fh ; '_'
0x180217343  mov     rdx, r12
0x180217346  call    ?RemoveOperation@CFlowControlValidator@@IEAAXPEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::RemoveOperation(COperationQueue *,OP_OPERATION_ID)
0x18021734b  mov     r8d, 60h ; '`'
0x180217351  mov     rdx, r12
0x180217354  call    ?RemoveOperation@CFlowControlValidator@@IEAAXPEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::RemoveOperation(COperationQueue *,OP_OPERATION_ID)
0x180217359  mov     r8d, 8Ah
0x18021735f  mov     rdx, r12
0x180217362  call    ?RemoveOperation@CFlowControlValidator@@IEAAXPEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::RemoveOperation(COperationQueue *,OP_OPERATION_ID)
0x180217367  mov     r8d, 73h ; 's'
0x18021736d  mov     rdx, r12
0x180217370  call    ?RemoveOperation@CFlowControlValidator@@IEAAXPEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::RemoveOperation(COperationQueue *,OP_OPERATION_ID)
0x180217375  mov     r8d, 72h ; 'r'
0x18021737b  mov     rdx, r12
0x18021737e  call    ?RemoveOperation@CFlowControlValidator@@IEAAXPEAVCOperationQueue@@W4OP_OPERATION_ID@@@Z; CFlowControlValidator::RemoveOperation(COperationQueue *,OP_OPERATION_ID)
0x180217383  mov     rax, [r12]
0x180217387  mov     edx, edi
0x180217389  mov     rcx, r12
0x18021738c  mov     rax, [rax+8]
0x180217390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217395  mov     rax, [r15]
0x180217398  mov     rcx, r15
0x18021739b  mov     rax, [rax+28h]
0x18021739f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802173a4  cmp     eax, 5
0x1802173a7  jl      loc_180217C87
0x1802173ad  call    cs:__imp_GetLastError
0x1802173b3  mov     edi, eax
0x1802173b5  call    cs:__imp_CurrentIP
0x1802173bb  mov     rbx, rax
0x1802173be  lea     rdx, aFlowtrackWillP; "FLOWTRACK: Will proceed with First boot"...
0x1802173c5  mov     ecx, 4000000h; unsigned int
0x1802173ca  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1802173cf  mov     [rsp+148h+var_F8], esi
0x1802173d3  mov     [rsp+148h+var_100], rsi
0x1802173d8  mov     dword ptr [rsp+148h+lpdwDisposition], edi
0x1802173dc  mov     [rsp+148h+var_110], rbx
0x1802173e1  lea     rcx, aCflowcontrolva; "CFlowControlValidator::ValidatePhase"
0x1802173e8  mov     [rsp+148h+lpSecurityAttributes], rcx
0x1802173ed  lea     rcx, aBaseNtsetupSet_21; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1802173f4  mov     [rsp+148h+lpcbData], rcx
0x1802173f9  mov     dword ptr [rsp+148h+phkResult], 1182h
0x180217401  xor     r9d, r9d
0x180217404  mov     r8, r13
0x180217407  mov     edx, 0C8000h
0x18021740c  mov     rcx, rax
0x18021740f  call    cs:__imp_WdsSetupLogMessageW
0x180217415  mov     rcx, [rsp+148h+var_D8]
0x18021741a  test    rcx, rcx
0x18021741d  jz      short loc_180217440
0x18021741f  mov     rax, [rcx]
0x180217422  lea     r9, aProceed; "Proceed"
0x180217429  lea     r8, aFirstbootskip; "FirstBootSkip"
0x180217430  lea     rdx, aSpFirstbootInf; "SP_FIRSTBOOT_INFO"
0x180217437  mov     rax, [rax+10h]
0x18021743b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217440  mov     rax, [r15]
0x180217443  mov     rcx, r15
0x180217446  mov     rax, [rax+28h]
0x18021744a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021744f  mov     [rsp+148h+Type], eax
0x180217453  mov     ebx, esi
0x180217455  cmp     eax, 6
0x180217458  setnl   bl
0x18021745b  lea     rdx, aOobebootapplyc; "OOBEBootApplyComplete"
0x180217462  lea     rcx, [rsp+148h+var_A0]
0x18021746a  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180217470  nop
0x180217471  mov     rdx, rax; struct UnBCL::String *
0x180217474  mov     rcx, r15; struct IExecutionContext *
  ... truncated ...
```
