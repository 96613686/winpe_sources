# MoUpdateUxManager::SetAndModifyShutdownFlags(ulong,ulong *)

- ea: `0x14017af00`
- end: `0x14017bbbc`
- name: `?SetAndModifyShutdownFlags@MoUpdateUxManager@@UEAAJKPEAK@Z`
- size: `3260`
- prototype: `__int64 __fastcall(MoUpdateUxManager *__hidden this, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400354c0`

## callees

- `0x140040184`
- `0x1400413a8`
- `0x140043284`
- `0x140045404`
- `0x140057a20`
- `0x1400771e8`
- `0x14012d864`
- `0x14017af00`
- `0x14017d9b8`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14017b1bf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14017b23a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14017b1bf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14017b23a`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14017b2ac`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14017b785`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14017b2ac`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x14017b785`

## string_xrefs

- `0x14017bb41`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14017bb5b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14017bb75`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14017bb8f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14017bba9`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14017b09f`: `RestartOrShutdownNoCommit`
- `0x14017b0b4`: `RestartOrShutdownNoCommit`
- `0x14017b1aa`: `UpdateAndShutdown`
- `0x14017b1b1`: `SOFTWARE\Microsoft\WindowsUpdate\CommitStatus`
- `0x14017b22c`: `SOFTWARE\Microsoft\WindowsUpdate\CommitStatus`
- `0x14017b225`: `NoCommit`
- `0x14017b1d4`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x14017b24f`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x14017bb27`: `C:\__w\1\s\src\orchestrator\system\windows\taggedupdatemanager\MoUpdateUxManager.cpp`
- `0x14017af8f`: `EnhancedUpdateAndShutdown`
- `0x14017b466`: `FirstLogonAfterUpdateFlag`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
int __fastcall MoUpdateUxManager::SetAndModifyShutdownFlags(MoUpdateUxManager *this, unsigned int a2, unsigned int *a3)
{
  int result; // eax
  _QWORD *System; // rax
  __int64 (__fastcall *v7)(__int64, __int128 *, __int64); // rbx
  int *traits_2_unsigned_short; // rax
  __int64 v9; // r8
  const char *v10; // r9
  __int64 v11; // r11
  __int64 v12; // rax
  char v13; // r14
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rbx
  _QWORD *v16; // rax
  __int64 (__fastcall *v17)(__int64, __int128 *, __int64); // rbx
  int *v18; // rax
  __int64 v19; // r8
  const char *v20; // r9
  __int64 v21; // r11
  __int64 v22; // rax
  char v23; // si
  const char *v24; // r9
  volatile signed __int32 *v25; // rbx
  volatile signed __int32 *v26; // rbx
  unsigned int v27; // eax
  unsigned int v28; // eax
  _QWORD *v29; // rax
  __int64 v30; // rbx
  __int64 v31; // rax
  const char *v32; // r9
  __int64 v33; // r11
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  volatile signed __int32 *v37; // rbx
  volatile signed __int32 *v38; // rbx
  _QWORD *v39; // rax
  void (__fastcall *v40)(__int64, __int128 *, __int128 *, __int128 *, _OWORD *); // rbx
  int *v41; // rax
  const char *v42; // r9
  __int64 v43; // r11
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  volatile signed __int32 *v47; // rbx
  volatile signed __int32 *v48; // rbx
  _QWORD *v49; // rax
  void (__fastcall *v50)(__int64, __int128 *, __int128 *, __int128 *); // rbx
  GUID *v51; // rax
  const char *v52; // r9
  __int64 v53; // r11
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rdx
  volatile signed __int32 *v57; // rbx
  volatile signed __int32 *v58; // rbx
  _QWORD *v59; // rax
  __int64 v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  volatile signed __int32 *v64; // rbx
  volatile signed __int32 *v65; // rbx
  _QWORD *v66; // rax
  __int64 v67; // rax
  __int64 v68; // rbx
  void (__fastcall *v69)(__int64, __int128 *, __int128 *, __int128 *, _OWORD *); // rsi
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  volatile signed __int32 *v73; // rbx
  volatile signed __int32 *v74; // rbx
  int lpData; // [rsp+20h] [rbp-118h]
  unsigned int lpDataa; // [rsp+20h] [rbp-118h]
  unsigned int lpDatab; // [rsp+20h] [rbp-118h]
  __int128 v78; // [rsp+30h] [rbp-108h] BYREF
  __int128 v79; // [rsp+40h] [rbp-F8h] BYREF
  __int128 v80; // [rsp+50h] [rbp-E8h] BYREF
  __int128 v81; // [rsp+60h] [rbp-D8h] BYREF
  __int128 v82; // [rsp+70h] [rbp-C8h]
  __int128 v83; // [rsp+80h] [rbp-B8h] BYREF
  __int128 v84; // [rsp+90h] [rbp-A8h] BYREF
  __int128 v85; // [rsp+A0h] [rbp-98h] BYREF
  __int128 v86; // [rsp+B0h] [rbp-88h] BYREF
  _OWORD v87[2]; // [rsp+C0h] [rbp-78h] BYREF
  char v88; // [rsp+E0h] [rbp-58h]
  __int128 v89; // [rsp+F0h] [rbp-48h] BYREF
  int Data; // [rsp+100h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  if ( g_coreWorkerShuttingDown )
    return -2145083107;
  try
  {
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x45E,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
        (const char *)0x80004003LL,
        lpData);
    System = (_QWORD *)SystemInterface::Service::GetSystem(&v79);
    v7 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*System + 40LL))(
                                                                                 *System,
                                                                                 &v80)
                                                                + 64LL);
    traits_2_unsigned_short = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                       L"EnhancedUpdateAndShutdown",
                                       &dword_140419B94,
                                       0);
    if ( traits_2_unsigned_short == &dword_140419B94
      || (v12 = ((char *)traits_2_unsigned_short - (char *)L"EnhancedUpdateAndShutdown") >> 1, v12 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v10);
    }
    *(_QWORD *)&v81 = L"EnhancedUpdateAndShutdown";
    *((_QWORD *)&v81 + 1) = v12;
    v78 = v81;
    LOBYTE(v9) = 1;
    v13 = v7(v11, &v78, v9);
    v14 = (volatile signed __int32 *)*((_QWORD *)&v80 + 1);
    if ( *((_QWORD *)&v80 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v80 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    v15 = (volatile signed __int32 *)*((_QWORD *)&v79 + 1);
    if ( *((_QWORD *)&v79 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v79 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    v16 = (_QWORD *)SystemInterface::Service::GetSystem(&v79);
    v17 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v16 + 40LL))(
                                                                                  *v16,
                                                                                  &v80)
                                                                 + 64LL);
    v18 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                   L"RestartOrShutdownNoCommit",
                   &dword_1404199F4,
                   0);
    if ( v18 == &dword_1404199F4 || (v22 = ((char *)v18 - (char *)L"RestartOrShutdownNoCommit") >> 1, v22 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v20);
    *(_QWORD *)&v81 = L"RestartOrShutdownNoCommit";
    *((_QWORD *)&v81 + 1) = v22;
    v78 = v81;
    LOBYTE(v19) = 1;
    v23 = v17(v21, &v78, v19);
    v25 = (volatile signed __int32 *)*((_QWORD *)&v80 + 1);
    if ( *((_QWORD *)&v80 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v80 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
        if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
      }
    }
    v26 = (volatile signed __int32 *)*((_QWORD *)&v79 + 1);
    if ( *((_QWORD *)&v79 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v79 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    Data = 1;
    if ( v13 && (a2 & 0x48) == 0x48 )
    {
      v27 = RegSetKeyValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\WindowsUpdate\\CommitStatus",
              L"UpdateAndShutdown",
              4u,
              &Data,
              4u);
      if ( v27 )
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x46A,
                 (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
                 (const char *)v27,
                 lpDataa);
      a2 = a2 & 0xFFFFFFF3 | 4;
      *a3 = a2;
    }
    if ( v23 )
    {
      if ( (a2 & 0xC) != 0 )
      {
        if ( (a2 & 0x40) == 0 )
        {
          v28 = RegSetKeyValueW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\WindowsUpdate\\CommitStatus",
                  L"NoCommit",
                  4u,
                  &Data,
                  4u);
          if ( v28 )
            return wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)0x473,
                     (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
                     (const char *)v28,
                     lpDatab);
        }
        goto LABEL_35;
      }
    }
    else if ( (a2 & 0xC) != 0 )
    {
LABEL_35:
      if ( (a2 & 0x40) != 0 )
      {
        v29 = (_QWORD *)SystemInterface::Service::GetSystem(&v84);
        v30 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v29 + 32LL))(*v29, &v83);
        *(_QWORD *)&v81 = 0;
        GetSystemTimePreciseAsFileTime(&v81);
        *(_QWORD *)&v81 = ((unsigned __int64)DWORD1(v81) << 32) - 116444736000000000LL + (unsigned int)v81;
        v31 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                L"StartTime",
                &dword_140419BAC,
                0);
        if ( v31 == v33 || (v34 = (v31 - (__int64)L"StartTime") >> 1, v34 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v32);
        *(_QWORD *)&v79 = L"StartTime";
        *((_QWORD *)&v79 + 1) = v34;
        v35 = -1;
        do
          ++v35;
        while ( SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT[v35] );
        *(_QWORD *)&v80 = SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT;
        *((_QWORD *)&v80 + 1) = v35;
        *(_QWORD *)&v78 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
        v36 = -1;
        do
          ++v36;
        while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v36] );
        *((_QWORD *)&v78 + 1) = v36;
        SystemInterface::Registry::SetSystemTime(
          v30,
          (unsigned int)&v78,
          (unsigned int)&v80,
          (unsigned int)&v79,
          (__int64)&v81);
        v37 = (volatile signed __int32 *)*((_QWORD *)&v83 + 1);
        if ( *((_QWORD *)&v83 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v83 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
            if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
          }
        }
        v38 = (volatile signed __int32 *)*((_QWORD *)&v84 + 1);
        if ( *((_QWORD *)&v84 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v84 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
            if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
          }
        }
        v39 = (_QWORD *)SystemInterface::Service::GetSystem(&v85);
        v40 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, _OWORD *))(**(_QWORD **)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v39 + 32LL))(*v39, &v81)
                                                                                           + 64LL);
        LODWORD(v87[0]) = 1;
        v88 = 0;
        v41 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"FirstLogonAfterUpdateFlag",
                       &dword_140419BE4,
                       0);
        if ( v41 == &dword_140419BE4 || (v44 = ((char *)v41 - (char *)L"FirstLogonAfterUpdateFlag") >> 1, v44 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v42);
        *(_QWORD *)&v78 = L"FirstLogonAfterUpdateFlag";
        *((_QWORD *)&v78 + 1) = v44;
        v45 = -1;
        do
          ++v45;
        while ( SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT[v45] );
        *(_QWORD *)&v80 = SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT;
        *((_QWORD *)&v80 + 1) = v45;
        *(_QWORD *)&v79 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
        v46 = -1;
        do
          ++v46;
        while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v46] );
        *((_QWORD *)&v79 + 1) = v46;
        v84 = v78;
        v83 = v80;
        v78 = v79;
        v40(v43, &v78, &v83, &v84, v87);
        if ( v88 != -1 && v88 && v88 != 1 )
          std::wstring::~wstring(v87);
        v47 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
        if ( *((_QWORD *)&v81 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
            if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
          }
        }
        v48 = (volatile signed __int32 *)*((_QWORD *)&v85 + 1);
        if ( *((_QWORD *)&v85 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v85 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
            if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
          }
        }
        v49 = (_QWORD *)SystemInterface::Service::GetSystem(&v86);
        v50 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v49 + 32LL))(
                                                                                                  *v49,
                                                                                                  &v81)
                                                                                 + 80LL);
        v51 = (GUID *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                        L"EndTime",
                        &USO_SERVICE_MU,
                        0);
        if ( v51 == &USO_SERVICE_MU || (v54 = ((char *)v51 - (char *)L"EndTime") >> 1, v54 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v52);
        *(_QWORD *)&v78 = L"EndTime";
        *((_QWORD *)&v78 + 1) = v54;
        v55 = -1;
        do
          ++v55;
        while ( SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT[v55] );
        *(_QWORD *)&v80 = SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT;
        *((_QWORD *)&v80 + 1) = v55;
        *(_QWORD *)&v79 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
        v56 = -1;
        do
          ++v56;
        while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v56] );
        *((_QWORD *)&v79 + 1) = v56;
        v85 = v78;
        v84 = v80;
        v83 = v79;
        v50(v53, &v83, &v84, &v85);
        v57 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
        if ( *((_QWORD *)&v81 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
            if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
          }
        }
        v58 = (volatile signed __int32 *)*((_QWORD *)&v86 + 1);
        if ( *((_QWORD *)&v86 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
            if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
          }
        }
        v59 = (_QWORD *)SystemInterface::Service::GetSystem(&v89);
        v60 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v59 + 32LL))(*v59, &v83);
        *(_QWORD *)&v81 = 0;
        GetSystemTimePreciseAsFileTime(&v81);
        *(_QWORD *)&v81 = ((unsigned __int64)DWORD1(v81) << 32) - 116444736000000000LL + (unsigned int)v81;
        v61 = -1;
        do
          ++v61;
        while ( SystemInterface::Registry::CURRENTREBOOTSTARTTIME[v61] );
        *(_QWORD *)&v78 = SystemInterface::Registry::CURRENTREBOOTSTARTTIME;
        *((_QWORD *)&v78 + 1) = v61;
        v62 = -1;
        do
          ++v62;
        while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v62] );
        *(_QWORD *)&v80 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
        *((_QWORD *)&v80 + 1) = v62;
        *(_QWORD *)&v79 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
        v63 = -1;
        do
          ++v63;
        while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v63] );
        *((_QWORD *)&v79 + 1) = v63;
        v86 = v78;
        v85 = v80;
        v84 = v79;
        SystemInterface::Registry::SetSystemTime(
          v60,
          (unsigned int)&v84,
          (unsigned int)&v85,
          (unsigned int)&v86,
          (__int64)&v81);
        v64 = (volatile signed __int32 *)*((_QWORD *)&v83 + 1);
        if ( *((_QWORD *)&v83 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v83 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v64)(v64);
            if ( _InterlockedExchangeAdd(v64 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v64 + 8LL))(v64);
          }
        }
        v65 = (volatile signed __int32 *)*((_QWORD *)&v89 + 1);
        if ( *((_QWORD *)&v89 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v89 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
            if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
          }
        }
        v66 = (_QWORD *)SystemInterface::Service::GetSystem(&v83);
        v67 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v66 + 32LL))(*v66, &v84);
        v68 = *(_QWORD *)v67;
        v69 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, _OWORD *))(**(_QWORD **)v67 + 64LL);
        v81 = 0;
        v82 = 0u;
        std::wstring::_Construct<1,wchar_t const *>(&v81, L"PowerMenu");
        v87[0] = v81;
        v87[1] = v82;
        *(_QWORD *)&v82 = 0;
        *((_QWORD *)&v82 + 1) = 7;
        LOWORD(v81) = 0;
        v88 = 2;
        v70 = -1;
        do
          ++v70;
        while ( SystemInterface::Registry::CURRENTREBOOTREASON[v70] );
        *(_QWORD *)&v78 = SystemInterface::Registry::CURRENTREBOOTREASON;
        *((_QWORD *)&v78 + 1) = v70;
        v71 = -1;
        do
          ++v71;
        while ( SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT[v71] );
        *(_QWORD *)&v80 = SystemInterface::Registry::UPDATE_UX_STATEVARIABLES_ROOT;
        *((_QWORD *)&v80 + 1) = v71;
        *(_QWORD *)&v79 = SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID;
        v72 = -1;
        do
          ++v72;
        while ( SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID[v72] );
        *((_QWORD *)&v79 + 1) = v72;
        v89 = v78;
        v86 = v80;
        v85 = v79;
        v69(v68, &v85, &v86, &v89, v87);
        if ( v88 != -1 && v88 && v88 != 1 )
          std::wstring::~wstring(v87);
        std::wstring::~wstring(&v81);
        v73 = (volatile signed __int32 *)*((_QWORD *)&v84 + 1);
        if ( *((_QWORD *)&v84 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v84 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v73)(v73);
            if ( _InterlockedExchangeAdd(v73 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v73 + 8LL))(v73);
          }
        }
        v74 = (volatile signed __int32 *)*((_QWORD *)&v83 + 1);
        if ( *((_QWORD *)&v83 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v83 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
            if ( _InterlockedExchangeAdd(v74 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
          }
        }
      }
    }
    *a3 = a2;
    result = 0;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x49D,
             (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\taggedupdatemanager\\MoUpdateUxManager.cpp",
             v24);
  }
  return result;
}

```

## disassembly

```asm
0x14017af00  mov     [rsp+arg_0], rbx
0x14017af05  mov     [rsp+arg_8], rsi
0x14017af0a  push    rdi
0x14017af0b  push    r12
0x14017af0d  push    r13
0x14017af0f  push    r14
0x14017af11  push    r15
0x14017af13  sub     rsp, 110h
0x14017af1a  mov     rax, cs:__security_cookie
0x14017af21  xor     rax, rsp
0x14017af24  mov     [rsp+138h+var_30], rax
0x14017af2c  mov     r15, r8
0x14017af2f  mov     edi, edx
0x14017af31  xor     r13d, r13d
0x14017af34  cmp     cs:?g_coreWorkerShuttingDown@@3_NA, r13b; bool g_coreWorkerShuttingDown
0x14017af3b  jz      short loc_14017AF47
0x14017af3d  mov     eax, 8024A11Dh
0x14017af42  jmp     loc_14017BAF4
0x14017af47  mov     rcx, [rsp+138h]; this
0x14017af4f  test    r15, r15
0x14017af52  jz      loc_14017BB21
0x14017af58  lea     rcx, [rsp+138h+var_F8]
0x14017af5d  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x14017af62  nop
0x14017af63  mov     rcx, [rax]
0x14017af66  mov     rax, [rcx]
0x14017af69  lea     rdx, [rsp+138h+var_E8]
0x14017af6e  mov     rax, [rax+28h]
0x14017af72  call    _guard_dispatch_icall
0x14017af77  nop
0x14017af78  mov     r11, [rax]
0x14017af7b  mov     rax, [r11]
0x14017af7e  mov     rbx, [rax+40h]
0x14017af82  xor     r8d, r8d
0x14017af85  lea     rsi, dword_140419B94
0x14017af8c  mov     rdx, rsi
0x14017af8f  lea     r14, aEnhancedupdate; "EnhancedUpdateAndShutdown"
0x14017af96  mov     rcx, r14
0x14017af99  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14017af9e  cmp     rax, rsi
0x14017afa1  jz      loc_14017BBA1
0x14017afa7  sub     rax, r14
0x14017afaa  sar     rax, 1
0x14017afad  or      r12, 0FFFFFFFFFFFFFFFFh
0x14017afb1  cmp     rax, r12
0x14017afb4  jz      loc_14017BBA1
0x14017afba  mov     qword ptr [rsp+138h+var_D8], r14
0x14017afbf  mov     qword ptr [rsp+138h+var_D8+8], rax
0x14017afc4  movaps  xmm0, [rsp+138h+var_D8]
0x14017afc9  movdqa  [rsp+138h+var_108], xmm0
0x14017afcf  mov     r8b, 1
0x14017afd2  lea     rdx, [rsp+138h+var_108]
0x14017afd7  mov     rcx, r11
0x14017afda  mov     rax, rbx
0x14017afdd  call    _guard_dispatch_icall
0x14017afe2  mov     r14b, al
0x14017afe5  mov     rbx, qword ptr [rsp+138h+var_E8+8]
0x14017afea  test    rbx, rbx
0x14017afed  jz      short loc_14017B027
0x14017afef  mov     ecx, r12d
0x14017aff2  lock xadd [rbx+8], ecx
0x14017aff7  add     ecx, r12d
0x14017affa  jnz     short loc_14017B027
0x14017affc  mov     rax, [rbx]
0x14017afff  mov     rcx, rbx
0x14017b002  mov     rax, [rax]
0x14017b005  call    _guard_dispatch_icall
0x14017b00a  mov     eax, r12d
0x14017b00d  lock xadd [rbx+0Ch], eax
0x14017b012  add     eax, r12d
0x14017b015  jnz     short loc_14017B027
0x14017b017  mov     rax, [rbx]
0x14017b01a  mov     rcx, rbx
0x14017b01d  mov     rax, [rax+8]
0x14017b021  call    _guard_dispatch_icall
0x14017b026  nop
0x14017b027  mov     rbx, qword ptr [rsp+138h+var_F8+8]
0x14017b02c  test    rbx, rbx
0x14017b02f  jz      short loc_14017B068
0x14017b031  mov     eax, r12d
0x14017b034  lock xadd [rbx+8], eax
0x14017b039  add     eax, r12d
0x14017b03c  jnz     short loc_14017B068
0x14017b03e  mov     rax, [rbx]
0x14017b041  mov     rcx, rbx
0x14017b044  mov     rax, [rax]
0x14017b047  call    _guard_dispatch_icall
0x14017b04c  mov     eax, r12d
0x14017b04f  lock xadd [rbx+0Ch], eax
0x14017b054  add     eax, r12d
0x14017b057  jnz     short loc_14017B068
0x14017b059  mov     rax, [rbx]
0x14017b05c  mov     rcx, rbx
0x14017b05f  mov     rax, [rax+8]
0x14017b063  call    _guard_dispatch_icall
0x14017b068  lea     rcx, [rsp+138h+var_F8]
0x14017b06d  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x14017b072  nop
0x14017b073  mov     rcx, [rax]
0x14017b076  mov     rax, [rcx]
0x14017b079  lea     rdx, [rsp+138h+var_E8]
0x14017b07e  mov     rax, [rax+28h]
0x14017b082  call    _guard_dispatch_icall
0x14017b087  nop
0x14017b088  mov     r11, [rax]
0x14017b08b  mov     rax, [r11]
0x14017b08e  mov     rbx, [rax+40h]
0x14017b092  xor     r8d, r8d
0x14017b095  lea     rsi, dword_1404199F4
0x14017b09c  mov     rdx, rsi
0x14017b09f  lea     rcx, aRestartorshutd; "RestartOrShutdownNoCommit"
0x14017b0a6  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14017b0ab  cmp     rax, rsi
0x14017b0ae  jz      loc_14017BB39
0x14017b0b4  lea     rcx, aRestartorshutd; "RestartOrShutdownNoCommit"
0x14017b0bb  sub     rax, rcx
0x14017b0be  sar     rax, 1
0x14017b0c1  cmp     rax, r12
0x14017b0c4  jz      loc_14017BB39
0x14017b0ca  mov     qword ptr [rsp+138h+var_D8], rcx
0x14017b0cf  mov     qword ptr [rsp+138h+var_D8+8], rax
0x14017b0d4  movaps  xmm0, [rsp+138h+var_D8]
0x14017b0d9  movdqa  [rsp+138h+var_108], xmm0
0x14017b0df  mov     r8b, 1
0x14017b0e2  lea     rdx, [rsp+138h+var_108]
0x14017b0e7  mov     rcx, r11
0x14017b0ea  mov     rax, rbx
0x14017b0ed  call    _guard_dispatch_icall
0x14017b0f2  mov     sil, al
0x14017b0f5  mov     rbx, qword ptr [rsp+138h+var_E8+8]
0x14017b0fa  test    rbx, rbx
0x14017b0fd  jz      short loc_14017B137
0x14017b0ff  mov     ecx, r12d
0x14017b102  lock xadd [rbx+8], ecx
0x14017b107  add     ecx, r12d
0x14017b10a  jnz     short loc_14017B137
0x14017b10c  mov     rax, [rbx]
0x14017b10f  mov     rcx, rbx
0x14017b112  mov     rax, [rax]
0x14017b115  call    _guard_dispatch_icall
0x14017b11a  mov     eax, r12d
0x14017b11d  lock xadd [rbx+0Ch], eax
0x14017b122  add     eax, r12d
0x14017b125  jnz     short loc_14017B137
0x14017b127  mov     rax, [rbx]
0x14017b12a  mov     rcx, rbx
0x14017b12d  mov     rax, [rax+8]
0x14017b131  call    _guard_dispatch_icall
0x14017b136  nop
0x14017b137  mov     rbx, qword ptr [rsp+138h+var_F8+8]
0x14017b13c  test    rbx, rbx
0x14017b13f  jz      short loc_14017B178
0x14017b141  mov     eax, r12d
0x14017b144  lock xadd [rbx+8], eax
0x14017b149  add     eax, r12d
0x14017b14c  jnz     short loc_14017B178
0x14017b14e  mov     rax, [rbx]
0x14017b151  mov     rcx, rbx
0x14017b154  mov     rax, [rax]
0x14017b157  call    _guard_dispatch_icall
0x14017b15c  mov     eax, r12d
0x14017b15f  lock xadd [rbx+0Ch], eax
0x14017b164  add     eax, r12d
0x14017b167  jnz     short loc_14017B178
0x14017b169  mov     rax, [rbx]
0x14017b16c  mov     rcx, rbx
0x14017b16f  mov     rax, [rax+8]
0x14017b173  call    _guard_dispatch_icall
0x14017b178  mov     [rsp+138h+Data], 1
0x14017b183  test    r14b, r14b
0x14017b186  jz      short loc_14017B1F4
0x14017b188  mov     eax, edi
0x14017b18a  and     eax, 48h
0x14017b18d  cmp     al, 48h ; 'H'
0x14017b18f  jnz     short loc_14017B1F4
0x14017b191  mov     ebx, 4
0x14017b196  mov     [rsp+138h+cbData], ebx; cbData
0x14017b19a  lea     rax, [rsp+138h+Data]
0x14017b1a2  mov     [rsp+138h+lpData], rax; unsigned int
0x14017b1a7  mov     r9d, ebx; dwType
0x14017b1aa  lea     r8, ValueName; "UpdateAndShutdown"
0x14017b1b1  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\WindowsUpdate\\Com"...
0x14017b1b8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14017b1bf  call    cs:__imp_RegSetKeyValueW
0x14017b1c5  test    eax, eax
0x14017b1c7  jz      short loc_14017B1EA
0x14017b1c9  mov     rcx, [rsp+138h]; this
0x14017b1d1  mov     r9d, eax; char *
0x14017b1d4  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14017b1db  mov     edx, 46Ah; void *
0x14017b1e0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14017b1e5  jmp     loc_14017BAF4
0x14017b1ea  and     edi, 0FFFFFFF7h
0x14017b1ed  or      edi, ebx
0x14017b1ef  mov     [r15], edi
0x14017b1f2  jmp     short loc_14017B1F9
0x14017b1f4  mov     ebx, 4
0x14017b1f9  test    sil, sil
0x14017b1fc  jz      short loc_14017B265
0x14017b1fe  test    dil, 0Ch
0x14017b202  jz      loc_14017BAE6
0x14017b208  mov     eax, edi
0x14017b20a  shr     eax, 6
0x14017b20d  test    al, 1
0x14017b20f  jnz     short loc_14017B26F
0x14017b211  mov     [rsp+138h+cbData], ebx; cbData
0x14017b215  lea     rax, [rsp+138h+Data]
0x14017b21d  mov     [rsp+138h+lpData], rax; unsigned int
0x14017b222  mov     r9d, ebx; dwType
0x14017b225  lea     r8, aNocommit; "NoCommit"
0x14017b22c  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\WindowsUpdate\\Com"...
0x14017b233  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14017b23a  call    cs:__imp_RegSetKeyValueW
0x14017b240  test    eax, eax
0x14017b242  jz      short loc_14017B26F
0x14017b244  mov     rcx, [rsp+138h]; this
0x14017b24c  mov     r9d, eax; char *
0x14017b24f  lea     r8, aCW1SSrcOrchest_24; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14017b256  mov     edx, 473h; void *
0x14017b25b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14017b260  jmp     loc_14017BAF4
0x14017b265  test    dil, 0Ch
0x14017b269  jz      loc_14017BAE6
0x14017b26f  test    dil, 40h
0x14017b273  jz      loc_14017BAE6
0x14017b279  lea     rcx, [rsp+138h+var_A8]
0x14017b281  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x14017b286  nop
0x14017b287  mov     rcx, [rax]
0x14017b28a  mov     rax, [rcx]
0x14017b28d  lea     rdx, [rsp+138h+var_B8]
0x14017b295  mov     rax, [rax+20h]
0x14017b299  call    _guard_dispatch_icall
0x14017b29e  nop
0x14017b29f  mov     rbx, [rax]
0x14017b2a2  mov     qword ptr [rsp+138h+var_D8], r13
0x14017b2a7  lea     rcx, [rsp+138h+var_D8]
0x14017b2ac  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x14017b2b2  mov     eax, dword ptr [rsp+138h+var_D8+4]
0x14017b2b6  shl     rax, 20h
0x14017b2ba  mov     ecx, dword ptr [rsp+138h+var_D8]
0x14017b2be  mov     rdx, 0FE624E212AC18000h
0x14017b2c8  add     rax, rdx
0x14017b2cb  add     rcx, rax
0x14017b2ce  mov     qword ptr [rsp+138h+var_D8], rcx
0x14017b2d3  xor     r8d, r8d
0x14017b2d6  lea     r11, dword_140419BAC
0x14017b2dd  mov     rdx, r11
0x14017b2e0  lea     rsi, aStarttime; "StartTime"
0x14017b2e7  mov     rcx, rsi
0x14017b2ea  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14017b2ef  cmp     rax, r11
0x14017b2f2  jz      loc_14017BB87
0x14017b2f8  sub     rax, rsi
0x14017b2fb  sar     rax, 1
0x14017b2fe  cmp     rax, r12
0x14017b301  jz      loc_14017BB87
0x14017b307  mov     qword ptr [rsp+138h+var_F8], rsi
0x14017b30c  mov     qword ptr [rsp+138h+var_F8+8], rax
0x14017b311  mov     rcx, cs:?UPDATE_UX_REBOOTDOWNTIME_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UPDATE_UX_REBOOTDOWNTIME_ROOT
0x14017b318  mov     rax, r12
0x14017b31b  inc     rax
0x14017b31e  cmp     [rcx+rax*2], r13w
0x14017b323  jnz     short loc_14017B31B
0x14017b325  mov     qword ptr [rsp+138h+var_E8], rcx
0x14017b32a  mov     qword ptr [rsp+138h+var_E8+8], rax
0x14017b32f  mov     rcx, cs:?UPDATEUXROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::UPDATEUXROOT_REDIRECTION_ID
0x14017b336  mov     qword ptr [rsp+138h+var_108], rcx
0x14017b33b  mov     rax, r12
0x14017b33e  inc     rax
0x14017b341  cmp     [rcx+rax*2], r13w
0x14017b346  jnz     short loc_14017B33E
0x14017b348  mov     qword ptr [rsp+138h+var_108+8], rax
0x14017b34d  movups  xmm0, [rsp+138h+var_F8]
0x14017b352  movdqu  [rsp+138h+var_F8], xmm0
0x14017b358  movups  xmm1, [rsp+138h+var_E8]
0x14017b35d  movdqu  [rsp+138h+var_E8], xmm1
0x14017b363  movaps  xmm0, [rsp+138h+var_108]
0x14017b368  movdqa  [rsp+138h+var_108], xmm0
0x14017b36e  lea     rax, [rsp+138h+var_D8]
0x14017b373  mov     [rsp+138h+lpData], rax
0x14017b378  lea     r9, [rsp+138h+var_F8]
0x14017b37d  lea     r8, [rsp+138h+var_E8]
0x14017b382  lea     rdx, [rsp+138h+var_108]
0x14017b387  mov     rcx, rbx
0x14017b38a  call    ?SetSystemTime@Registry@SystemInterface@@QEAAXV?$basic_zstring_view@_W@wil@@00AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; SystemInterface::Registry::SetSystemTime(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x14017b38f  nop
0x14017b390  mov     rbx, qword ptr [rsp+138h+var_B8+8]
0x14017b398  test    rbx, rbx
0x14017b39b  jz      short loc_14017B3D5
0x14017b39d  mov     eax, r12d
0x14017b3a0  lock xadd [rbx+8], eax
0x14017b3a5  add     eax, r12d
0x14017b3a8  jnz     short loc_14017B3D5
0x14017b3aa  mov     rax, [rbx]
0x14017b3ad  mov     rcx, rbx
0x14017b3b0  mov     rax, [rax]
0x14017b3b3  call    _guard_dispatch_icall
0x14017b3b8  mov     eax, r12d
0x14017b3bb  lock xadd [rbx+0Ch], eax
  ... truncated ...
```
