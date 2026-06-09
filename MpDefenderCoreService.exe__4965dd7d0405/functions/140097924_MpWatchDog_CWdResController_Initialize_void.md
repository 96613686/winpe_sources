# MpWatchDog::CWdResController::Initialize(void)

- ea: `0x140097924`
- end: `0x14009826d`
- name: `?Initialize@CWdResController@MpWatchDog@@QEAAJXZ`
- size: `2377`
- prototype: `__int64 __fastcall(MpWatchDog::CWdResController *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400991d0`

## callees

- `0x14000d658`
- `0x140012088`
- `0x14001263c`
- `0x1400131e4`
- `0x140013274`
- `0x140015624`
- `0x14001cd4c`
- `0x14001f0c0`
- `0x14003a0f4`
- `0x14003a130`
- `0x14003a5c0`
- `0x140059e84`
- `0x140059fe0`
- `0x14007d1e0`
- `0x14007d210`
- `0x1400833d4`
- `0x140097924`
- `0x140166990`

## import_xrefs

- `KERNEL32!AssignProcessToJobObject` at `0x140098007`
- `KERNEL32!AssignProcessToJobObject` at `0x140098007`
- `KERNEL32!QueryInformationJobObject` at `0x140097d33`
- `KERNEL32!QueryInformationJobObject` at `0x140097d33`
- `KERNEL32!SetInformationJobObject` at `0x140097c2b`
- `KERNEL32!SetInformationJobObject` at `0x140097dfc`
- `KERNEL32!SetInformationJobObject` at `0x140097ecd`
- `KERNEL32!SetInformationJobObject` at `0x140097fac`
- `KERNEL32!SetInformationJobObject` at `0x140097c2b`
- `KERNEL32!SetInformationJobObject` at `0x140097dfc`
- `KERNEL32!SetInformationJobObject` at `0x140097ecd`
- `KERNEL32!SetInformationJobObject` at `0x140097fac`
- `KERNEL32!CreateIoCompletionPort` at `0x140097bfb`
- `KERNEL32!CreateIoCompletionPort` at `0x140097bfb`
- `KERNEL32!GetCurrentProcess` at `0x140097ff9`
- `KERNEL32!GetCurrentProcess` at `0x140097ff9`
- `KERNEL32!CloseHandle` at `0x140097b93`
- `KERNEL32!CloseHandle` at `0x140097bcb`
- `KERNEL32!CloseHandle` at `0x140097c86`
- `KERNEL32!CloseHandle` at `0x140097c99`
- `KERNEL32!CloseHandle` at `0x140097cf1`
- `KERNEL32!CloseHandle` at `0x140098060`
- `KERNEL32!CloseHandle` at `0x1400980cd`
- `KERNEL32!CloseHandle` at `0x1400980e9`
- `KERNEL32!CloseHandle` at `0x14009820c`
- `KERNEL32!CloseHandle` at `0x140097b93`
- `KERNEL32!CloseHandle` at `0x140097bcb`
- `KERNEL32!CloseHandle` at `0x140097c86`
- `KERNEL32!CloseHandle` at `0x140097c99`
- `KERNEL32!CloseHandle` at `0x140097cf1`
- `KERNEL32!CloseHandle` at `0x140098060`
- `KERNEL32!CloseHandle` at `0x1400980cd`
- `KERNEL32!CloseHandle` at `0x1400980e9`
- `KERNEL32!CloseHandle` at `0x14009820c`
- `KERNEL32!GetLastError` at `0x140097c39`
- `KERNEL32!GetLastError` at `0x140097ca4`
- `KERNEL32!GetLastError` at `0x140097d3d`
- `KERNEL32!GetLastError` at `0x140097e06`
- `KERNEL32!GetLastError` at `0x140097ed7`
- `KERNEL32!GetLastError` at `0x140097fb6`
- `KERNEL32!GetLastError` at `0x140098011`
- `KERNEL32!GetLastError` at `0x140097c39`
- `KERNEL32!GetLastError` at `0x140097ca4`
- `KERNEL32!GetLastError` at `0x140097d3d`
- `KERNEL32!GetLastError` at `0x140097e06`
- `KERNEL32!GetLastError` at `0x140097ed7`
- `KERNEL32!GetLastError` at `0x140097fb6`
- `KERNEL32!GetLastError` at `0x140098011`
- `KERNEL32!AcquireSRWLockShared` at `0x140097af7`
- `KERNEL32!AcquireSRWLockShared` at `0x140097b33`
- `KERNEL32!AcquireSRWLockShared` at `0x140097d9b`
- `KERNEL32!AcquireSRWLockShared` at `0x140097e64`
- `KERNEL32!AcquireSRWLockShared` at `0x140097af7`
- `KERNEL32!AcquireSRWLockShared` at `0x140097b33`
- `KERNEL32!AcquireSRWLockShared` at `0x140097d9b`
- `KERNEL32!AcquireSRWLockShared` at `0x140097e64`
- `KERNEL32!ReleaseSRWLockShared` at `0x140097b0b`
- `KERNEL32!ReleaseSRWLockShared` at `0x140097b42`
- `KERNEL32!ReleaseSRWLockShared` at `0x140097db3`
- `KERNEL32!ReleaseSRWLockShared` at `0x140097e7c`
- `KERNEL32!ReleaseSRWLockShared` at `0x140097b0b`
- `KERNEL32!ReleaseSRWLockShared` at `0x140097b42`
- `KERNEL32!ReleaseSRWLockShared` at `0x140097db3`
- `KERNEL32!ReleaseSRWLockShared` at `0x140097e7c`
- `ADVAPI32!RegCloseKey` at `0x140097ac3`
- `ADVAPI32!RegCloseKey` at `0x140097ad6`
- `ADVAPI32!RegCloseKey` at `0x140097ac3`
- `ADVAPI32!RegCloseKey` at `0x140097ad6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall MpWatchDog::CWdResController::Initialize(MpWatchDog::CWdResController *this)
{
  MpWatchDog::CWdResController *v1; // r14
  void *v2; // r15
  MpWatchDog *v3; // rcx
  unsigned int v4; // r12d
  struct _SECURITY_ATTRIBUTES *v5; // r9
  unsigned int *v6; // r9
  RTL_SRWLOCK *v7; // rbx
  unsigned int v8; // edi
  unsigned int v9; // eax
  MpWatchDog::WdConfigManager *v10; // rdi
  RTL_SRWLOCK *v11; // rbx
  unsigned int v12; // edi
  unsigned int v13; // eax
  signed int JobObject; // ebx
  HANDLE IoCompletionPort; // rax
  signed int v16; // eax
  signed int v17; // ebx
  signed int LastError; // eax
  signed int v20; // eax
  RTL_SRWLOCK *v21; // rbx
  int v22; // eax
  signed int v23; // eax
  RTL_SRWLOCK *v24; // rbx
  int v25; // eax
  signed int v26; // eax
  int v27; // ecx
  int v28; // ecx
  int v29; // eax
  int v30; // edx
  signed int v31; // eax
  HANDLE CurrentProcess; // rax
  signed int v33; // eax
  HANDLE *v34; // rbx
  int Thread; // eax
  void *v36; // rcx
  HANDLE v37; // rax
  HKEY v38; // rdi
  HKEY v39; // rax
  uintptr_t v40; // rax
  _DWORD *v41; // rcx
  __int64 v42; // rdi
  unsigned int *ThrdAddr; // [rsp+28h] [rbp-150h]
  unsigned int *v44; // [rsp+38h] [rbp-140h]
  MpWatchDog::WdConfigManager *v45; // [rsp+40h] [rbp-138h]
  MpWatchDog::WdConfigManager *v46; // [rsp+40h] [rbp-138h]
  MpWatchDog::WdConfigManager *v47; // [rsp+40h] [rbp-138h]
  _QWORD JobObjectInformation[2]; // [rsp+50h] [rbp-128h] BYREF
  wchar_t v49[4]; // [rsp+60h] [rbp-118h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-110h] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-108h] BYREF
  HKEY v52[2]; // [rsp+80h] [rbp-F8h] BYREF
  __int64 v53; // [rsp+90h] [rbp-E8h] BYREF
  __int128 v54; // [rsp+98h] [rbp-E0h]
  unsigned __int64 v55; // [rsp+A8h] [rbp-D0h]
  int v56; // [rsp+B0h] [rbp-C8h]
  int v57; // [rsp+B4h] [rbp-C4h]
  __int64 v58; // [rsp+B8h] [rbp-C0h]
  _QWORD v59[18]; // [rsp+C0h] [rbp-B8h] BYREF

  v1 = qword_1401E7358;
  v2 = 0;
  hObject = 0;
  v3 = (MpWatchDog *)WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids);
  *((_BYTE *)v1 + 64) = 0;
  *((_DWORD *)v1 + 17) = 0;
  *((_QWORD *)v1 + 2) = 0;
  LOBYTE(v3) = *((_BYTE *)MpWatchDog::gMpWdConfigManager + 12);
  *((_BYTE *)v1 + 24) = (_BYTE)v3;
  if ( (_BYTE)v3 || !(unsigned int)MpIsAppVerifierMode() )
  {
    v4 = 1;
  }
  else
  {
    v4 = 1;
    *((_BYTE *)v1 + 24) = 1;
    v3 = (MpWatchDog *)WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids);
  }
  if ( MpWatchDog::MpIsCoreSvcInDevMode(v3) )
  {
    v52[0] = 0;
    if ( (int)CommonUtil::UtilRegOpenKey(
                (CommonUtil *)v52,
                (HKEY *)0xFFFFFFFF80000002LL,
                (const WCHAR *)&stru_140194720,
                (const wchar_t *)1) >= 0 )
    {
      hKey[0] = 0;
      if ( (int)CommonUtil::UtilRegOpenKey(
                  (CommonUtil *)hKey,
                  (HKEY *)v52[0],
                  (const WCHAR *)&stru_140196060,
                  (const wchar_t *)1) >= 0 )
      {
        *(_DWORD *)v49 = 0;
        if ( (int)CommonUtil::UtilRegGetValueDword((CommonUtil *)hKey[0], (HKEY)&stru_140196F28, v49, &v5->nLength) >= 0 )
          *((_BYTE *)v1 + 36) = *(_DWORD *)v49 == 1;
        if ( (int)CommonUtil::UtilRegGetValueDword((CommonUtil *)hKey[0], (HKEY)&stru_140196F68, v49, v6) >= 0 )
          *((_BYTE *)v1 + 37) = *(_DWORD *)v49 == 1;
        if ( *((_BYTE *)v1 + 36) || *((_BYTE *)v1 + 37) )
          *((_BYTE *)v1 + 24) = 0;
      }
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
    }
    if ( v52[0] )
      RegCloseKey(v52[0]);
  }
  v45 = MpWatchDog::gMpWdConfigManager;
  if ( MpWatchDog::gMpWdConfigManager )
  {
    v7 = (RTL_SRWLOCK *)((char *)MpWatchDog::gMpWdConfigManager + 848);
    AcquireSRWLockShared((PSRWLOCK)MpWatchDog::gMpWdConfigManager + 106);
    v8 = *((_DWORD *)v45 + 166);
    ReleaseSRWLockShared(v7);
    v9 = 0;
    if ( v8 <= 2 )
      v9 = v8;
    *((_DWORD *)v1 + 4) = v9;
    v10 = MpWatchDog::gMpWdConfigManager;
    if ( MpWatchDog::gMpWdConfigManager )
    {
      v11 = (RTL_SRWLOCK *)((char *)MpWatchDog::gMpWdConfigManager + 848);
      AcquireSRWLockShared((PSRWLOCK)MpWatchDog::gMpWdConfigManager + 106);
      v12 = *((_DWORD *)v10 + 167);
      ReleaseSRWLockShared(v11);
      v13 = 0;
      if ( v12 <= 2 )
        v13 = v12;
      *((_DWORD *)v1 + 5) = v13;
    }
  }
  if ( *((_BYTE *)v1 + 24) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids);
    if ( hObject )
      CloseHandle(hObject);
    return v4;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  JobObject = CommonUtil::UtilCreateJobObject((CommonUtil *)&hObject, 0, 0, v5);
  if ( JobObject < 0 )
    goto LABEL_62;
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  if ( IoCompletionPort )
  {
    v2 = IoCompletionPort;
    goto LABEL_45;
  }
  LastError = GetLastError();
  JobObject = LastError;
  if ( LastError > 0 )
    JobObject = (unsigned __int16)LastError | 0x80070000;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      17,
      &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
      (unsigned int)JobObject);
  if ( JobObject < 0 )
  {
LABEL_62:
    if ( hObject )
      CloseHandle(hObject);
    return (unsigned int)JobObject;
  }
LABEL_45:
  JobObjectInformation[0] = 0;
  JobObjectInformation[1] = v2;
  if ( !SetInformationJobObject(hObject, JobObjectAssociateCompletionPortInformation, JobObjectInformation, 0x10u) )
  {
    v16 = GetLastError();
    v17 = v16;
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        18,
        &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
        (unsigned int)v17);
    if ( v17 < 0 )
      goto LABEL_52;
  }
  memset(v59, 0, sizeof(v59));
  if ( !QueryInformationJobObject(hObject, JobObjectExtendedLimitInformation, v59, 0x90u, 0) )
  {
    v20 = GetLastError();
    v17 = v20;
    if ( v20 > 0 )
      v17 = (unsigned __int16)v20 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        19,
        &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
        (unsigned int)v17);
    if ( v17 < 0 )
      goto LABEL_52;
  }
  v46 = MpWatchDog::gMpWdConfigManager;
  if ( MpWatchDog::gMpWdConfigManager )
  {
    v21 = (RTL_SRWLOCK *)((char *)MpWatchDog::gMpWdConfigManager + 848);
    AcquireSRWLockShared((PSRWLOCK)MpWatchDog::gMpWdConfigManager + 106);
    *(_DWORD *)v49 = *((_DWORD *)v46 + 165);
    ReleaseSRWLockShared(v21);
    v22 = *(_DWORD *)v49;
    if ( !*(_DWORD *)v49 )
      v22 = *((_DWORD *)v1 + 7);
    *((_DWORD *)v1 + 7) = v22;
  }
  LODWORD(v59[2]) = 2304;
  v59[14] = (unsigned __int64)*((unsigned int *)v1 + 7) << 20;
  if ( !SetInformationJobObject(hObject, JobObjectExtendedLimitInformation, v59, 0x90u) )
  {
    v23 = GetLastError();
    v17 = v23;
    if ( v23 > 0 )
      v17 = (unsigned __int16)v23 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        20,
        &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
        (unsigned int)v17);
    if ( v17 < 0 )
      goto LABEL_52;
  }
  v47 = MpWatchDog::gMpWdConfigManager;
  if ( MpWatchDog::gMpWdConfigManager )
  {
    v24 = (RTL_SRWLOCK *)((char *)MpWatchDog::gMpWdConfigManager + 848);
    AcquireSRWLockShared((PSRWLOCK)MpWatchDog::gMpWdConfigManager + 106);
    *(_DWORD *)v49 = *((_DWORD *)v47 + 164);
    ReleaseSRWLockShared(v24);
    v25 = *(_DWORD *)v49;
    if ( !*(_DWORD *)v49 )
      v25 = *((_DWORD *)v1 + 8);
    *((_DWORD *)v1 + 8) = v25;
  }
  if ( (unsigned int)MpIsWindows8OrGreater() )
  {
    LODWORD(v52[0]) = 5;
    HIDWORD(v52[0]) = 100 * *((_DWORD *)v1 + 8);
    if ( !SetInformationJobObject(hObject, MaxJobObjectInfoClass|JobObjectBasicProcessIdList, v52, 8u) )
    {
      v26 = GetLastError();
      v17 = v26;
      if ( v26 > 0 )
        v17 = (unsigned __int16)v26 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          21,
          &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
          (unsigned int)v17);
      if ( v17 < 0 )
        goto LABEL_52;
    }
    v53 = 0;
    v54 = 0;
    v58 = 0x40000;
    v55 = (unsigned __int64)*((unsigned int *)v1 + 7) << 20;
    v27 = *((_DWORD *)v1 + 4);
    if ( v27 )
    {
      if ( v27 != 1 )
      {
        v28 = 3;
        v29 = 3;
        goto LABEL_102;
      }
      v29 = 2;
    }
    else
    {
      v29 = 1;
    }
    v28 = 3;
LABEL_102:
    v56 = v29;
    v30 = *((_DWORD *)v1 + 5);
    if ( v30 )
    {
      if ( v30 == 1 )
        v28 = 2;
    }
    else
    {
      v28 = 1;
    }
    v57 = v28;
    if ( !SetInformationJobObject(hObject, MaxJobObjectInfoClass, &v53, 0x30u) )
    {
      v31 = GetLastError();
      v17 = v31;
      if ( v31 > 0 )
        v17 = (unsigned __int16)v31 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          22,
          &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
          (unsigned int)v17);
      if ( v17 < 0 )
        goto LABEL_52;
    }
  }
  CurrentProcess = GetCurrentProcess();
  if ( AssignProcessToJobObject(hObject, CurrentProcess) )
    goto LABEL_120;
  v33 = GetLastError();
  v17 = v33;
  if ( v33 > 0 )
    v17 = (unsigned __int16)v33 | 0x80070000;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      23,
      &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
      (unsigned int)v17);
  if ( v17 >= 0 )
  {
LABEL_120:
    v34 = (HANDLE *)((char *)v1 + 56);
    if ( *((_QWORD *)v1 + 7) )
    {
      CloseHandle(*v34);
      *v34 = 0;
    }
    LODWORD(ThrdAddr) = 0;
    Thread = CommonUtil::UtilCreateThread(
               (MpWatchDog::CWdResController *)((char *)v1 + 56),
               0,
               0,
               (unsigned int)MpWatchDog::CWdResController::MonitorJobThreadFn,
               (unsigned int (*)(void *))v1,
               ThrdAddr,
               0,
               v44);
    v17 = Thread;
    if ( Thread >= 0 )
    {
      v36 = (void *)*((_QWORD *)v1 + 1);
      if ( v36 )
        CloseHandle(v36);
      v37 = hObject;
      hObject = 0;
      *((_QWORD *)v1 + 1) = v37;
      if ( *(_QWORD *)v1 )
        CloseHandle(*(HANDLE *)v1);
      *(_QWORD *)v1 = v2;
      if ( *((_BYTE *)v1 + 36) || *((_BYTE *)v1 + 37) )
      {
        v38 = (HKEY)operator new(0x10u);
        v52[0] = v38;
        v39 = (HKEY)operator new(8u);
        *(_QWORD *)v39 = v1;
        hKey[0] = v39;
        v40 = beginthreadex(
                0,
                0,
                std::thread::_Invoke_std::tuple__lambda_fb0e8531def43d7b6ea8fc2a51219e36____0_,
                v39,
                0,
                (unsigned int *)v38 + 2);
        *(_QWORD *)v38 = v40;
        if ( !v40 )
        {
          *((_DWORD *)v38 + 2) = 0;
          std::_Throw_Cpp_error(6);
        }
        v41 = (_DWORD *)*((_QWORD *)v1 + 6);
        *((_QWORD *)v1 + 6) = v38;
        if ( v41 )
        {
          if ( v41[2] )
            terminate();
          operator delete(v41, (const struct std::nothrow_t *)0x10);
        }
        v42 = *((_QWORD *)v1 + 6);
        if ( v42 )
        {
          if ( !*(_DWORD *)(v42 + 8) )
            std::_Throw_Cpp_error(1);
          *(_OWORD *)v52 = *(_OWORD *)v42;
          if ( Thrd_detach((_Thrd_t *)v52) )
            std::_Throw_Cpp_error(1);
          *(_OWORD *)v42 = 0;
        }
      }
      if ( hObject )
        CloseHandle(hObject);
      return (unsigned int)v17;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        24,
        &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
        (unsigned int)Thread);
  }
LABEL_52:
  if ( hObject )
    CloseHandle(hObject);
  if ( v2 )
    CloseHandle(v2);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140097924  mov     rax, rsp
0x140097927  mov     [rax+8], rbx
0x14009792b  mov     [rax+10h], rsi
0x14009792f  mov     [rax+18h], rdi
0x140097933  mov     [rax+20h], r12
0x140097937  push    r13
0x140097939  push    r14
0x14009793b  push    r15
0x14009793d  sub     rsp, 160h
0x140097944  mov     rax, cs:__security_cookie
0x14009794b  xor     rax, rsp
0x14009794e  mov     [rsp+178h+var_28], rax
0x140097956  xor     esi, esi
0x140097958  mov     r14, cs:qword_1401E7358
0x14009795f  mov     r15d, esi
0x140097962  mov     [rsp+178h+hObject], rsi
0x140097967  lea     rdi, WPP_GLOBAL_Control
0x14009796e  mov     rcx, cs:WPP_GLOBAL_Control
0x140097975  lea     r13, WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids
0x14009797c  cmp     rcx, rdi
0x14009797f  jz      short loc_140097996
0x140097981  test    byte ptr [rcx+1Ch], 10h
0x140097985  jz      short loc_140097996
0x140097987  lea     edx, [rsi+0Dh]
0x14009798a  mov     r8, r13
0x14009798d  mov     rcx, [rcx+10h]
0x140097991  call    WPP_SF_
0x140097996  mov     [r14+40h], sil
0x14009799a  mov     [r14+44h], esi
0x14009799e  mov     [r14+10h], rsi
0x1400979a2  mov     rax, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x1400979a9  mov     cl, [rax+0Ch]; this
0x1400979ac  nop
0x1400979ad  mov     [r14+18h], cl
0x1400979b1  test    cl, cl
0x1400979b3  jnz     short loc_1400979ED
0x1400979b5  call    MpIsAppVerifierMode
0x1400979ba  test    eax, eax
0x1400979bc  jz      short loc_1400979ED
0x1400979be  mov     r12d, 1
0x1400979c4  mov     [r14+18h], r12b
0x1400979c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400979cf  cmp     rcx, rdi
0x1400979d2  jz      short loc_1400979F3
0x1400979d4  test    byte ptr [rcx+1Ch], 2
0x1400979d8  jz      short loc_1400979F3
0x1400979da  lea     edx, [r12+0Dh]
0x1400979df  mov     r8, r13
0x1400979e2  mov     rcx, [rcx+10h]
0x1400979e6  call    WPP_SF_
0x1400979eb  jmp     short loc_1400979F3
0x1400979ed  mov     r12d, 1
0x1400979f3  call    ?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ; MpWatchDog::MpIsCoreSvcInDevMode(void)
0x1400979f8  test    al, al
0x1400979fa  jz      loc_140097ADC
0x140097a00  mov     [rsp+178h+var_F8], rsi
0x140097a08  mov     r9d, r12d; wchar_t *
0x140097a0b  lea     r8, stru_140194720; HKEY
0x140097a12  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x140097a19  lea     rcx, [rsp+178h+var_F8]; this
0x140097a21  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x140097a26  test    eax, eax
0x140097a28  js      loc_140097AC9
0x140097a2e  mov     [rsp+178h+hKey], rsi
0x140097a33  mov     r9d, r12d; wchar_t *
0x140097a36  lea     r8, stru_140196060; HKEY
0x140097a3d  mov     rdx, [rsp+178h+var_F8]; HKEY *
0x140097a45  lea     rcx, [rsp+178h+hKey]; this
0x140097a4a  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x140097a4f  test    eax, eax
0x140097a51  js      short loc_140097AB9
0x140097a53  mov     dword ptr [rsp+178h+var_118], esi
0x140097a57  lea     r8, [rsp+178h+var_118]; wchar_t *
0x140097a5c  lea     rdx, stru_140196F28; HKEY
0x140097a63  mov     rcx, [rsp+178h+hKey]; this
0x140097a68  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,wchar_t const *,ulong *)
0x140097a6d  test    eax, eax
0x140097a6f  js      short loc_140097A7D
0x140097a71  cmp     dword ptr [rsp+178h+var_118], r12d
0x140097a76  setz    al
0x140097a79  xchg    al, [r14+24h]
0x140097a7d  lea     r8, [rsp+178h+var_118]; wchar_t *
0x140097a82  lea     rdx, stru_140196F68; HKEY
0x140097a89  mov     rcx, [rsp+178h+hKey]; this
0x140097a8e  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,wchar_t const *,ulong *)
0x140097a93  test    eax, eax
0x140097a95  js      short loc_140097AA3
0x140097a97  cmp     dword ptr [rsp+178h+var_118], r12d
0x140097a9c  setz    al
0x140097a9f  xchg    al, [r14+25h]
0x140097aa3  mov     al, [r14+24h]
0x140097aa7  nop
0x140097aa8  test    al, al
0x140097aaa  jnz     short loc_140097AB5
0x140097aac  mov     al, [r14+25h]
0x140097ab0  nop
0x140097ab1  test    al, al
0x140097ab3  jz      short loc_140097AB9
0x140097ab5  mov     [r14+18h], sil
0x140097ab9  mov     rcx, [rsp+178h+hKey]; hKey
0x140097abe  test    rcx, rcx
0x140097ac1  jz      short loc_140097AC9
0x140097ac3  call    cs:__imp_RegCloseKey
0x140097ac9  mov     rcx, [rsp+178h+var_F8]; hKey
0x140097ad1  test    rcx, rcx
0x140097ad4  jz      short loc_140097ADC
0x140097ad6  call    cs:__imp_RegCloseKey
0x140097adc  mov     rax, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x140097ae3  mov     [rsp+178h+var_138], rax
0x140097ae8  test    rax, rax
0x140097aeb  jz      short loc_140097B5B
0x140097aed  lea     rbx, [rax+350h]
0x140097af4  mov     rcx, rbx; SRWLock
0x140097af7  call    cs:__imp_AcquireSRWLockShared
0x140097afd  mov     rdi, [rsp+178h+var_138]
0x140097b02  mov     edi, [rdi+298h]
0x140097b08  mov     rcx, rbx; SRWLock
0x140097b0b  call    cs:__imp_ReleaseSRWLockShared
0x140097b11  mov     eax, esi
0x140097b13  cmp     edi, 2
0x140097b16  cmovbe  eax, edi
0x140097b19  mov     [r14+10h], eax
0x140097b1d  mov     rdi, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x140097b24  test    rdi, rdi
0x140097b27  jz      short loc_140097B54
0x140097b29  lea     rbx, [rdi+350h]
0x140097b30  mov     rcx, rbx; SRWLock
0x140097b33  call    cs:__imp_AcquireSRWLockShared
0x140097b39  mov     edi, [rdi+29Ch]
0x140097b3f  mov     rcx, rbx; SRWLock
0x140097b42  call    cs:__imp_ReleaseSRWLockShared
0x140097b48  mov     eax, esi
0x140097b4a  cmp     edi, 2
0x140097b4d  cmovbe  eax, edi
0x140097b50  mov     [r14+14h], eax
0x140097b54  lea     rdi, WPP_GLOBAL_Control
0x140097b5b  cmp     [r14+18h], sil
0x140097b5f  jz      short loc_140097B9E
0x140097b61  mov     rcx, cs:WPP_GLOBAL_Control
0x140097b68  cmp     rcx, rdi
0x140097b6b  jz      short loc_140097B85
0x140097b6d  test    byte ptr [rcx+1Ch], 2
0x140097b71  jz      short loc_140097B85
0x140097b73  mov     edx, 0Fh
0x140097b78  mov     r8, r13
0x140097b7b  mov     rcx, [rcx+10h]
0x140097b7f  call    WPP_SF_
0x140097b84  nop
0x140097b85  mov     rcx, [rsp+178h+hObject]; hObject
0x140097b8a  test    rcx, rcx
0x140097b8d  jz      loc_140097CFA
0x140097b93  call    cs:__imp_CloseHandle
0x140097b99  jmp     loc_140097CFA
0x140097b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140097ba5  cmp     rcx, rdi
0x140097ba8  jz      short loc_140097BC1
0x140097baa  test    byte ptr [rcx+1Ch], 4
0x140097bae  jz      short loc_140097BC1
0x140097bb0  mov     edx, 10h
0x140097bb5  mov     r8, r13
0x140097bb8  mov     rcx, [rcx+10h]
0x140097bbc  call    WPP_SF_
0x140097bc1  mov     rcx, [rsp+178h+hObject]; hObject
0x140097bc6  test    rcx, rcx
0x140097bc9  jz      short loc_140097BD6
0x140097bcb  call    cs:__imp_CloseHandle
0x140097bd1  mov     [rsp+178h+hObject], rsi
0x140097bd6  xor     r8d, r8d; wchar_t *
0x140097bd9  xor     edx, edx; void **
0x140097bdb  lea     rcx, [rsp+178h+hObject]; this
0x140097be0  call    ?UtilCreateJobObject@CommonUtil@@YAJPEAPEAXPEB_WPEBU_SECURITY_ATTRIBUTES@@@Z; CommonUtil::UtilCreateJobObject(void * *,wchar_t const *,_SECURITY_ATTRIBUTES const *)
0x140097be5  mov     ebx, eax
0x140097be7  test    eax, eax
0x140097be9  js      loc_140097CE7
0x140097bef  xor     r9d, r9d; NumberOfConcurrentThreads
0x140097bf2  xor     r8d, r8d; CompletionKey
0x140097bf5  xor     edx, edx; ExistingCompletionPort
0x140097bf7  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x140097bfb  call    cs:__imp_CreateIoCompletionPort
0x140097c01  test    rax, rax
0x140097c04  jz      loc_140097CA4
0x140097c0a  mov     r15, rax
0x140097c0d  mov     [rsp+178h+JobObjectInformation], rsi
0x140097c12  mov     [rsp+178h+var_120], r15
0x140097c17  mov     r9d, 10h; cbJobObjectInformationLength
0x140097c1d  lea     r8, [rsp+178h+JobObjectInformation]; lpJobObjectInformation
0x140097c22  lea     edx, [r9-9]; JobObjectInformationClass
0x140097c26  mov     rcx, [rsp+178h+hObject]; hJob
0x140097c2b  call    cs:__imp_SetInformationJobObject
0x140097c31  test    eax, eax
0x140097c33  jnz     loc_140097D02
0x140097c39  call    cs:__imp_GetLastError
0x140097c3f  mov     ebx, eax
0x140097c41  test    eax, eax
0x140097c43  jle     short loc_140097C4E
0x140097c45  movzx   ebx, ax
0x140097c48  or      ebx, 80070000h
0x140097c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140097c55  cmp     rcx, rdi
0x140097c58  jz      short loc_140097C74
0x140097c5a  test    [rcx+1Ch], r12b
0x140097c5e  jz      short loc_140097C74
0x140097c60  mov     edx, 12h
0x140097c65  mov     r9d, ebx
0x140097c68  mov     r8, r13
0x140097c6b  mov     rcx, [rcx+10h]
0x140097c6f  call    WPP_SF_d
0x140097c74  test    ebx, ebx
0x140097c76  jns     loc_140097D02
0x140097c7c  mov     rcx, [rsp+178h+hObject]; hObject
0x140097c81  test    rcx, rcx
0x140097c84  jz      short loc_140097C8D
0x140097c86  call    cs:__imp_CloseHandle
0x140097c8c  nop
0x140097c8d  test    r15, r15
0x140097c90  jz      loc_140098213
0x140097c96  mov     rcx, r15; hObject
0x140097c99  call    cs:__imp_CloseHandle
0x140097c9f  jmp     loc_140098213
0x140097ca4  call    cs:__imp_GetLastError
0x140097caa  mov     ebx, eax
0x140097cac  test    eax, eax
0x140097cae  jle     short loc_140097CB9
0x140097cb0  movzx   ebx, ax
0x140097cb3  or      ebx, 80070000h
0x140097cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140097cc0  cmp     rcx, rdi
0x140097cc3  jz      short loc_140097CDF
0x140097cc5  test    [rcx+1Ch], r12b
0x140097cc9  jz      short loc_140097CDF
0x140097ccb  mov     edx, 11h
0x140097cd0  mov     r9d, ebx
0x140097cd3  mov     r8, r13
0x140097cd6  mov     rcx, [rcx+10h]
0x140097cda  call    WPP_SF_d
0x140097cdf  test    ebx, ebx
0x140097ce1  jns     loc_140097C0D
0x140097ce7  mov     rcx, [rsp+178h+hObject]; hObject
0x140097cec  test    rcx, rcx
0x140097cef  jz      short loc_140097CF7
0x140097cf1  call    cs:__imp_CloseHandle
0x140097cf7  mov     r12d, ebx
0x140097cfa  mov     eax, r12d
0x140097cfd  jmp     loc_140098215
0x140097d02  mov     ebx, 90h
0x140097d07  mov     r8d, ebx; Size
0x140097d0a  xor     edx, edx; Val
0x140097d0c  lea     rcx, [rsp+178h+var_B8]; void *
0x140097d14  call    memset
0x140097d19  mov     [rsp+178h+lpReturnLength], rsi; lpReturnLength
0x140097d1e  mov     r9d, ebx; cbJobObjectInformationLength
0x140097d21  lea     r8, [rsp+178h+var_B8]; lpJobObjectInformation
0x140097d29  mov     edx, 9; JobObjectInformationClass
0x140097d2e  mov     rcx, [rsp+178h+hObject]; hJob
0x140097d33  call    cs:__imp_QueryInformationJobObject
0x140097d39  test    eax, eax
0x140097d3b  jnz     short loc_140097D80
0x140097d3d  call    cs:__imp_GetLastError
0x140097d43  mov     ebx, eax
0x140097d45  test    eax, eax
0x140097d47  jle     short loc_140097D52
0x140097d49  movzx   ebx, ax
0x140097d4c  or      ebx, 80070000h
0x140097d52  mov     rcx, cs:WPP_GLOBAL_Control
0x140097d59  cmp     rcx, rdi
0x140097d5c  jz      short loc_140097D78
0x140097d5e  test    [rcx+1Ch], r12b
0x140097d62  jz      short loc_140097D78
0x140097d64  mov     edx, 13h
0x140097d69  mov     r9d, ebx
0x140097d6c  mov     r8, r13
0x140097d6f  mov     rcx, [rcx+10h]
0x140097d73  call    WPP_SF_d
0x140097d78  test    ebx, ebx
0x140097d7a  js      loc_140097C7C
0x140097d80  mov     rax, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x140097d87  mov     [rsp+178h+var_138], rax
0x140097d8c  test    rax, rax
0x140097d8f  jz      short loc_140097DC9
0x140097d91  lea     rbx, [rax+350h]
0x140097d98  mov     rcx, rbx; SRWLock
0x140097d9b  call    cs:__imp_AcquireSRWLockShared
0x140097da1  mov     rax, [rsp+178h+var_138]
0x140097da6  mov     eax, [rax+294h]
0x140097dac  mov     dword ptr [rsp+178h+var_118], eax
0x140097db0  mov     rcx, rbx; SRWLock
0x140097db3  call    cs:__imp_ReleaseSRWLockShared
0x140097db9  mov     eax, dword ptr [rsp+178h+var_118]
0x140097dbd  test    eax, eax
0x140097dbf  jnz     short loc_140097DC5
0x140097dc1  mov     eax, [r14+1Ch]
0x140097dc5  mov     [r14+1Ch], eax
0x140097dc9  mov     [rsp+178h+var_A8], 900h
0x140097dd4  mov     eax, [r14+1Ch]
0x140097dd8  shl     rax, 14h
0x140097ddc  mov     [rsp+178h+var_48], rax
0x140097de4  mov     r9d, 90h; cbJobObjectInformationLength
0x140097dea  lea     r8, [rsp+178h+var_B8]; lpJobObjectInformation
0x140097df2  mov     edx, 9; JobObjectInformationClass
0x140097df7  mov     rcx, [rsp+178h+hObject]; hJob
  ... truncated ...
```
