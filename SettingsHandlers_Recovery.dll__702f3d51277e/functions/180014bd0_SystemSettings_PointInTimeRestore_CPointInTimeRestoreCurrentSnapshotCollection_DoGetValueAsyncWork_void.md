# SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork(void)

- ea: `0x180014bd0`
- end: `0x180015167`
- name: `?DoGetValueAsyncWork@CPointInTimeRestoreCurrentSnapshotCollection@PointInTimeRestore@SystemSettings@@UEAAXXZ`
- size: `1431`
- prototype: `void __fastcall(SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180002380`
- `0x18000bef4`
- `0x1800102cc`
- `0x18001147c`
- `0x180014bd0`
- `0x18001ba18`
- `0x180025920`
- `0x180025c88`
- `0x1800261f0`
- `0x18002b010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180014ecf`
- `ole32!CoTaskMemFree` at `0x180014ecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001507d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001507d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014c51`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014cee`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014d88`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014e7e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014f2f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014fde`
- `WDSCORE!WdsSetupLogMessageW` at `0x180015058`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800150cf`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014c51`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014cee`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014d88`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014e7e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014f2f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014fde`
- `WDSCORE!WdsSetupLogMessageW` at `0x180015058`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800150cf`
- `WDSCORE!CurrentIP` at `0x180014bef`
- `WDSCORE!CurrentIP` at `0x180014c96`
- `WDSCORE!CurrentIP` at `0x180014d36`
- `WDSCORE!CurrentIP` at `0x180014e26`
- `WDSCORE!CurrentIP` at `0x180014ee5`
- `WDSCORE!CurrentIP` at `0x180014f8d`
- `WDSCORE!CurrentIP` at `0x18001500e`
- `WDSCORE!CurrentIP` at `0x180015085`
- `WDSCORE!CurrentIP` at `0x180014bef`
- `WDSCORE!CurrentIP` at `0x180014c96`
- `WDSCORE!CurrentIP` at `0x180014d36`
- `WDSCORE!CurrentIP` at `0x180014e26`
- `WDSCORE!CurrentIP` at `0x180014ee5`
- `WDSCORE!CurrentIP` at `0x180014f8d`
- `WDSCORE!CurrentIP` at `0x18001500e`
- `WDSCORE!CurrentIP` at `0x180015085`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection *this)
{
  DWORD LastError; // edi
  __int64 v2; // rbx
  struct tagLOG_PARTIAL_MSG *v3; // rax
  const wchar_t *v4; // rsi
  volatile signed __int32 **Current; // rax
  __int64 v6; // r12
  DWORD v7; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  int v10; // r12d
  DWORD v11; // edi
  __int64 v12; // rbx
  struct tagLOG_PARTIAL_MSG *v13; // rax
  struct _PitrSnapshotData *i; // r15
  struct _PitrSnapshotData *v15; // rdi
  __int64 v16; // rbx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem *v17; // rax
  __int64 v18; // r9
  wil *v19; // rcx
  __int64 v20; // rdi
  struct tagLOG_PARTIAL_MSG *v21; // rax
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *v22; // rax
  DWORD v23; // edi
  __int64 v24; // rbx
  struct tagLOG_PARTIAL_MSG *v25; // rax
  __int64 v26; // rbx
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem *v27; // rax
  __int64 v28; // rax
  __int64 v29; // r9
  wil *v30; // rcx
  DWORD v31; // esi
  __int64 v32; // rdi
  struct tagLOG_PARTIAL_MSG *v33; // rax
  DWORD v34; // edi
  __int64 v35; // rbx
  struct tagLOG_PARTIAL_MSG *v36; // rax
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *v37; // rax
  DWORD v38; // edi
  __int64 v39; // rbx
  struct tagLOG_PARTIAL_MSG *v40; // rax
  struct _RTL_CRITICAL_SECTION *v41; // rax
  __int64 v42; // r8
  volatile signed __int32 *v43; // rbx
  const wchar_t *v44; // kr10_8
  int v45; // esi
  DWORD v46; // edi
  __int64 v47; // rbx
  struct tagLOG_PARTIAL_MSG *v48; // rax
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *v49; // rax
  int v50; // esi
  DWORD v51; // edi
  __int64 v52; // rbx
  struct tagLOG_PARTIAL_MSG *v53; // rax
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *v54; // rax
  struct _PitrSnapshotData *v55; // [rsp+68h] [rbp-60h]
  _QWORD v56[2]; // [rsp+70h] [rbp-58h] BYREF
  __int64 v57; // [rsp+80h] [rbp-48h] BYREF
  volatile signed __int32 *v58; // [rsp+88h] [rbp-40h]
  int v60; // [rsp+D8h] [rbp+10h] BYREF
  __int64 v61; // [rsp+E0h] [rbp+18h]
  LPVOID pv; // [rsp+E8h] [rbp+20h] BYREF

  LastError = GetLastError();
  v2 = CurrentIP();
  v3 = ConstructPartialMsgW(
         0x4000000u,
         "SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork: Getting "
         "all current PITR snapshots");
  v4 = L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork";
  WdsSetupLogMessageW(
    v3,
    0,
    L"D",
    0,
    1539,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
    L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork",
    v2,
    LastError,
    0,
    0);
  Current = (volatile signed __int32 **)SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetPITRManager(Current, &v57);
  v6 = v57;
  if ( v57 )
  {
    v60 = 0;
    pv = 0;
    v7 = GetLastError();
    v8 = CurrentIP();
    v9 = ConstructPartialMsgW(
           0x4000000u,
           "SystemSettings::PointInTimeRestore::PointInTimeRestoreManager::GetPointInTimeRestoreCurrentSnapshots: Getting"
           " PITR current snapshots");
    WdsSetupLogMessageW(
      v9,
      0,
      L"D",
      0,
      162,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\pointintimerestoremanager.cpp",
      L"SystemSettings::PointInTimeRestore::PointInTimeRestoreManager::GetPointInTimeRestoreCurrentSnapshots",
      v8,
      v7,
      0,
      0);
    v10 = (*(__int64 (__fastcall **)(_QWORD, int *, LPVOID *))(**(_QWORD **)(v6 + 8) + 96LL))(
            *(_QWORD *)(v6 + 8),
            &v60,
            &pv);
    if ( v10 < 0 )
    {
      v34 = GetLastError();
      v35 = CurrentIP();
      v36 = ConstructPartialMsgW(
              0x2000000u,
              "SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork: Fai"
              "led to get current snapshots");
      WdsSetupLogMessageW(
        v36,
        0,
        L"D",
        0,
        1620,
        L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
        L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork",
        v35,
        v34,
        0,
        0);
      v37 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
      SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::SetLastPITRError(v37, v10);
    }
    else if ( v60 )
    {
      v11 = GetLastError();
      v12 = CurrentIP();
      v13 = ConstructPartialMsgW(
              0x4000000u,
              "SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork: Suc"
              "cessfully retrieved %d current PITR snapshots",
              v60);
      WdsSetupLogMessageW(
        v13,
        0,
        L"D",
        0,
        1553,
        L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
        L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork",
        v12,
        v11,
        0,
        0);
      for ( i = (struct _PitrSnapshotData *)pv; i; i = v15 )
      {
        v15 = (struct _PitrSnapshotData *)*((_QWORD *)i + 3);
        v55 = v15;
        v56[0] = v15;
        if ( v10 >= 0 )
        {
          try
          {
            v16 = 0;
            v61 = 0;
            v17 = (SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem *)operator new(
                                                                                           0xF0u,
                                                                                           (const struct std::nothrow_t *)&std::nothrow);
            if ( v17 )
            {
              v16 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem::CPointInTimeRestoreSnapshotItem(
                      v17,
                      i);
              v61 = v16;
            }
            if ( v16 )
            {
              LOBYTE(v18) = 1;
              Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
                *((_QWORD *)this + 26),
                0,
                v16,
                v18);
            }
            else
            {
              v10 = -2147024882;
              v4 = (const wchar_t *)GetLastError();
              v20 = CurrentIP();
              v21 = ConstructPartialMsgW(
                      0x2000000u,
                      "SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncW"
                      "ork : CPointInTimeRestoreSnapshotItem unexpectedly null");
              WdsSetupLogMessageW(
                v21,
                0,
                L"D",
                0,
                1576,
                L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
                L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork",
                v20,
                (_DWORD)v4,
                0,
                0);
              v22 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
              SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::SetLastPITRError(v22, -2147024882);
              v15 = v55;
            }
            if ( v16 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          catch ( ... )
          {
            v44 = v4;
            v45 = wil::ResultFromCaughtException(v19);
            LODWORD(v61) = v45;
            v46 = GetLastError();
            v47 = CurrentIP();
            v48 = ConstructPartialMsgW(
                    0x2000000u,
                    "SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWor"
                    "k: Failed to create snapshot setting item");
            WdsSetupLogMessageW(
              v48,
              0,
              L"D",
              0,
              1583,
              L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
              L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork",
              v47,
              v46,
              0,
              0);
            v49 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
            SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::SetLastPITRError(v49, v45);
            v4 = v44;
            v10 = v61;
            v15 = (struct _PitrSnapshotData *)v56[0];
          }
        }
        CoTaskMemFree(i);
      }
    }
    else
    {
      try
      {
        v23 = GetLastError();
        v24 = CurrentIP();
        v25 = ConstructPartialMsgW(
                0x4000000u,
                "SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork: N"
                "o current PITR snapshots found");
        WdsSetupLogMessageW(
          v25,
          0,
          L"D",
          0,
          1596,
          L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork",
          v24,
          v23,
          0,
          0);
        v26 = 0;
        v27 = (SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem *)operator new(
                                                                                       0xF0u,
                                                                                       (const struct std::nothrow_t *)&std::nothrow);
        if ( v27
          && (v28 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem::CPointInTimeRestoreSnapshotItem(
                      v27,
                      0),
              (v26 = v28) != 0) )
        {
          LOBYTE(v29) = 1;
          Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
            *((_QWORD *)this + 26),
            0,
            v28,
            v29);
        }
        else
        {
          v10 = -2147024882;
          v31 = GetLastError();
          v32 = CurrentIP();
          v33 = ConstructPartialMsgW(
                  0x2000000u,
                  "SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork "
                  ": CPointInTimeRestoreSnapshotItem unexpectedly null");
          WdsSetupLogMessageW(
            v33,
            0,
            L"D",
            0,
            1607,
            L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
            L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork",
            v32,
            v31,
            0,
            0);
        }
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      catch ( ... )
      {
        v50 = wil::ResultFromCaughtException(v30);
        LODWORD(v61) = v50;
        v51 = GetLastError();
        v52 = CurrentIP();
        v53 = ConstructPartialMsgW(
                0x2000000u,
                "SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork: F"
                "ailed to create snapshot setting item");
        WdsSetupLogMessageW(
          v53,
          0,
          L"D",
          0,
          1613,
          L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
          L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork",
          v52,
          v51,
          0,
          0);
        v54 = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::SetLastPITRError(v54, v50);
        v10 = v61;
      }
    }
    if ( v10 < 0 )
      goto LABEL_29;
    v6 = v57;
  }
  else
  {
    v38 = GetLastError();
    v39 = CurrentIP();
    v40 = ConstructPartialMsgW(
            0x2000000u,
            "SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork: PITR manager is null");
    WdsSetupLogMessageW(
      v40,
      0,
      L"D",
      0,
      1626,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
      L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork",
      v39,
      v38,
      0,
      0);
  }
  if ( !v6 )
  {
LABEL_29:
    v41 = (struct _RTL_CRITICAL_SECTION *)SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
    v60 = 6;
    v56[0] = L"CPointInTimeRestoreDialog";
    v56[1] = &v60;
    SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PointInTimeRestore::PITREvent>::_Notify<_lambda_ba361b346e648473d0e0f5ec774d7d2a_>(
      v41,
      (__int64)v56,
      v42);
  }
  v43 = v58;
  if ( v58 )
  {
    if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
      if ( !_InterlockedDecrement(v43 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
    }
  }
}

```

## disassembly

```asm
0x180014bd0  mov     [rsp+arg_0], rcx
0x180014bd5  push    rbx
0x180014bd6  push    rsi
0x180014bd7  push    rdi
0x180014bd8  push    r12
0x180014bda  push    r13
0x180014bdc  push    r14
0x180014bde  push    r15
0x180014be0  sub     rsp, 90h
0x180014be7  call    cs:__imp_GetLastError
0x180014bed  mov     edi, eax
0x180014bef  call    cs:__imp_CurrentIP
0x180014bf5  mov     rbx, rax
0x180014bf8  lea     rdx, aSystemsettings; "SystemSettings::PointInTimeRestore::CPo"...
0x180014bff  mov     ecx, 4000000h; unsigned int
0x180014c04  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180014c09  xor     r14d, r14d
0x180014c0c  mov     [rsp+0C8h+var_78], r14d
0x180014c11  mov     [rsp+0C8h+var_80], r14
0x180014c16  mov     [rsp+0C8h+var_88], edi
0x180014c1a  mov     [rsp+0C8h+var_90], rbx
0x180014c1f  lea     rsi, aSystemsettings_46; "SystemSettings::PointInTimeRestore::CPo"...
0x180014c26  mov     [rsp+0C8h+var_98], rsi
0x180014c2b  lea     r15, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x180014c32  mov     [rsp+0C8h+var_A0], r15
0x180014c37  mov     [rsp+0C8h+var_A8], 603h
0x180014c3f  xor     r9d, r9d
0x180014c42  lea     r13, aD; "D"
0x180014c49  mov     r8, r13
0x180014c4c  xor     edx, edx
0x180014c4e  mov     rcx, rax
0x180014c51  call    cs:__imp_WdsSetupLogMessageW
0x180014c57  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x180014c5c  lea     rdx, [rsp+0C8h+var_48]
0x180014c64  mov     rcx, rax; this
0x180014c67  call    ?GetPITRManager@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEAA?AV?$shared_ptr@VPointInTimeRestoreManager@PointInTimeRestore@SystemSettings@@@std@@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetPITRManager(void)
0x180014c6c  nop
0x180014c6d  mov     r12, [rsp+0C8h+var_48]
0x180014c75  test    r12, r12
0x180014c78  jz      loc_18001507D
0x180014c7e  mov     [rsp+0C8h+arg_8], r14d
0x180014c86  mov     [rsp+0C8h+pv], r14
0x180014c8e  call    cs:__imp_GetLastError
0x180014c94  mov     edi, eax
0x180014c96  call    cs:__imp_CurrentIP
0x180014c9c  mov     rbx, rax
0x180014c9f  lea     rdx, aSystemsettings_5; "SystemSettings::PointInTimeRestore::Poi"...
0x180014ca6  mov     ecx, 4000000h; unsigned int
0x180014cab  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180014cb0  mov     [rsp+0C8h+var_78], r14d
0x180014cb5  mov     [rsp+0C8h+var_80], r14
0x180014cba  mov     [rsp+0C8h+var_88], edi
0x180014cbe  mov     [rsp+0C8h+var_90], rbx
0x180014cc3  lea     rcx, aSystemsettings_83; "SystemSettings::PointInTimeRestore::Poi"...
0x180014cca  mov     [rsp+0C8h+var_98], rcx
0x180014ccf  lea     rcx, aPcshellShellSy_2; "pcshell\\shell\\systemsettings\\recover"...
0x180014cd6  mov     [rsp+0C8h+var_A0], rcx
0x180014cdb  mov     [rsp+0C8h+var_A8], 0A2h
0x180014ce3  xor     r9d, r9d
0x180014ce6  mov     r8, r13
0x180014ce9  xor     edx, edx
0x180014ceb  mov     rcx, rax
0x180014cee  call    cs:__imp_WdsSetupLogMessageW
0x180014cf4  mov     rcx, [r12+8]
0x180014cf9  mov     rax, [rcx]
0x180014cfc  lea     r8, [rsp+0C8h+pv]
0x180014d04  lea     rdx, [rsp+0C8h+arg_8]
0x180014d0c  mov     rax, [rax+60h]
0x180014d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d15  mov     r12d, eax
0x180014d18  test    eax, eax
0x180014d1a  js      loc_180015006
0x180014d20  cmp     [rsp+0C8h+arg_8], r14d
0x180014d28  jbe     loc_180014EDD
0x180014d2e  call    cs:__imp_GetLastError
0x180014d34  mov     edi, eax
0x180014d36  call    cs:__imp_CurrentIP
0x180014d3c  mov     rbx, rax
0x180014d3f  mov     r8d, [rsp+0C8h+arg_8]
0x180014d47  lea     rdx, aSystemsettings_128; "SystemSettings::PointInTimeRestore::CPo"...
0x180014d4e  mov     ecx, 4000000h; unsigned int
0x180014d53  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180014d58  mov     [rsp+0C8h+var_78], r14d
0x180014d5d  mov     [rsp+0C8h+var_80], r14
0x180014d62  mov     [rsp+0C8h+var_88], edi
0x180014d66  mov     [rsp+0C8h+var_90], rbx
0x180014d6b  mov     [rsp+0C8h+var_98], rsi
0x180014d70  mov     [rsp+0C8h+var_A0], r15
0x180014d75  mov     [rsp+0C8h+var_A8], 611h
0x180014d7d  xor     r9d, r9d
0x180014d80  mov     r8, r13
0x180014d83  xor     edx, edx
0x180014d85  mov     rcx, rax
0x180014d88  call    cs:__imp_WdsSetupLogMessageW
0x180014d8e  mov     r15, [rsp+0C8h+pv]
0x180014d96  mov     [rsp+0C8h+var_68], r15
0x180014d9b  test    r15, r15
0x180014d9e  jz      loc_18001506E
0x180014da4  mov     rdi, [r15+18h]
0x180014da8  mov     [rsp+0C8h+var_60], rdi
0x180014dad  mov     [rsp+0C8h+var_58], rdi
0x180014db2  test    r12d, r12d
0x180014db5  js      loc_180014ECC
0x180014dbb  mov     rbx, r14
0x180014dbe  mov     [rsp+0C8h+arg_10], rbx
0x180014dc6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014dcd  mov     ecx, 0F0h; unsigned __int64
0x180014dd2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014dd7  test    rax, rax
0x180014dda  jz      short loc_180014DF2
0x180014ddc  mov     rdx, r15; struct _PitrSnapshotData *
0x180014ddf  mov     rcx, rax; this
0x180014de2  call    ??0CPointInTimeRestoreSnapshotItem@PointInTimeRestore@SystemSettings@@QEAA@PEAU_PitrSnapshotData@@@Z; SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem::CPointInTimeRestoreSnapshotItem(_PitrSnapshotData *)
0x180014de7  mov     rbx, rax
0x180014dea  mov     [rsp+0C8h+arg_10], rax
0x180014df2  test    rbx, rbx
0x180014df5  jz      short loc_180014E18
0x180014df7  mov     r9b, 1
0x180014dfa  mov     r8, rbx
0x180014dfd  xor     edx, edx
0x180014dff  mov     rax, [rsp+0C8h+arg_0]
0x180014e07  mov     rcx, [rax+0D0h]
0x180014e0e  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x180014e13  jmp     loc_180014E99
0x180014e18  mov     r12d, 8007000Eh
0x180014e1e  call    cs:__imp_GetLastError
0x180014e24  mov     esi, eax
0x180014e26  call    cs:__imp_CurrentIP
0x180014e2c  mov     rdi, rax
0x180014e2f  lea     rdx, aSystemsettings_107; "SystemSettings::PointInTimeRestore::CPo"...
0x180014e36  mov     ecx, 2000000h; unsigned int
0x180014e3b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180014e40  mov     [rsp+0C8h+var_78], r14d
0x180014e45  mov     [rsp+0C8h+var_80], r14
0x180014e4a  mov     [rsp+0C8h+var_88], esi
0x180014e4e  mov     [rsp+0C8h+var_90], rdi
0x180014e53  lea     rcx, aSystemsettings_46; "SystemSettings::PointInTimeRestore::CPo"...
0x180014e5a  mov     [rsp+0C8h+var_98], rcx
0x180014e5f  lea     rcx, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x180014e66  mov     [rsp+0C8h+var_A0], rcx
0x180014e6b  mov     [rsp+0C8h+var_A8], 628h
0x180014e73  xor     r9d, r9d
0x180014e76  mov     r8, r13
0x180014e79  xor     edx, edx
0x180014e7b  mov     rcx, rax
0x180014e7e  call    cs:__imp_WdsSetupLogMessageW
0x180014e84  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x180014e89  mov     edx, r12d; int
0x180014e8c  mov     rcx, rax; this
0x180014e8f  call    ?SetLastPITRError@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEAAXJ@Z; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::SetLastPITRError(long)
0x180014e94  mov     rdi, [rsp+0C8h+var_60]
0x180014e99  test    rbx, rbx
0x180014e9c  jz      short loc_180014EAE
0x180014e9e  mov     rax, [rbx]
0x180014ea1  mov     rcx, rbx
0x180014ea4  mov     rax, [rax+10h]
0x180014ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ead  nop
0x180014eae  jmp     short loc_180014ECC
0x180014eb0  xor     r14d, r14d
0x180014eb3  lea     r13, aD; "D"
0x180014eba  mov     r12d, dword ptr [rsp+0C8h+arg_10]
0x180014ec2  mov     r15, [rsp+0C8h+var_68]
0x180014ec7  mov     rdi, [rsp+0C8h+var_58]
0x180014ecc  mov     rcx, r15; pv
0x180014ecf  call    cs:__imp_CoTaskMemFree
0x180014ed5  mov     r15, rdi
0x180014ed8  jmp     loc_180014D96
0x180014edd  call    cs:__imp_GetLastError
0x180014ee3  mov     edi, eax
0x180014ee5  call    cs:__imp_CurrentIP
0x180014eeb  mov     rbx, rax
0x180014eee  lea     rdx, aSystemsettings_45; "SystemSettings::PointInTimeRestore::CPo"...
0x180014ef5  mov     ecx, 4000000h; unsigned int
0x180014efa  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180014eff  mov     [rsp+0C8h+var_78], r14d
0x180014f04  mov     [rsp+0C8h+var_80], r14
0x180014f09  mov     [rsp+0C8h+var_88], edi
0x180014f0d  mov     [rsp+0C8h+var_90], rbx
0x180014f12  mov     [rsp+0C8h+var_98], rsi
0x180014f17  mov     [rsp+0C8h+var_A0], r15
0x180014f1c  mov     [rsp+0C8h+var_A8], 63Ch
0x180014f24  xor     r9d, r9d
0x180014f27  mov     r8, r13
0x180014f2a  xor     edx, edx
0x180014f2c  mov     rcx, rax
0x180014f2f  call    cs:__imp_WdsSetupLogMessageW
0x180014f35  nop
0x180014f36  mov     rbx, r14
0x180014f39  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014f40  mov     ecx, 0F0h; unsigned __int64
0x180014f45  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014f4a  test    rax, rax
0x180014f4d  jz      short loc_180014F7F
0x180014f4f  xor     edx, edx; struct _PitrSnapshotData *
0x180014f51  mov     rcx, rax; this
0x180014f54  call    ??0CPointInTimeRestoreSnapshotItem@PointInTimeRestore@SystemSettings@@QEAA@PEAU_PitrSnapshotData@@@Z; SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem::CPointInTimeRestoreSnapshotItem(_PitrSnapshotData *)
0x180014f59  mov     rbx, rax
0x180014f5c  test    rax, rax
0x180014f5f  jz      short loc_180014F7F
0x180014f61  mov     r9b, 1
0x180014f64  mov     r8, rax
0x180014f67  xor     edx, edx
0x180014f69  mov     rax, [rsp+0C8h+arg_0]
0x180014f71  mov     rcx, [rax+0D0h]
0x180014f78  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x180014f7d  jmp     short loc_180014FE5
0x180014f7f  mov     r12d, 8007000Eh
0x180014f85  call    cs:__imp_GetLastError
0x180014f8b  mov     esi, eax
0x180014f8d  call    cs:__imp_CurrentIP
0x180014f93  mov     rdi, rax
0x180014f96  lea     rdx, aSystemsettings_107; "SystemSettings::PointInTimeRestore::CPo"...
0x180014f9d  mov     ecx, 2000000h; unsigned int
0x180014fa2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180014fa7  mov     [rsp+0C8h+var_78], r14d
0x180014fac  mov     [rsp+0C8h+var_80], r14
0x180014fb1  mov     [rsp+0C8h+var_88], esi
0x180014fb5  mov     [rsp+0C8h+var_90], rdi
0x180014fba  lea     rcx, aSystemsettings_46; "SystemSettings::PointInTimeRestore::CPo"...
0x180014fc1  mov     [rsp+0C8h+var_98], rcx
0x180014fc6  mov     [rsp+0C8h+var_A0], r15
0x180014fcb  mov     [rsp+0C8h+var_A8], 647h
0x180014fd3  xor     r9d, r9d
0x180014fd6  mov     r8, r13
0x180014fd9  xor     edx, edx
0x180014fdb  mov     rcx, rax
0x180014fde  call    cs:__imp_WdsSetupLogMessageW
0x180014fe4  nop
0x180014fe5  test    rbx, rbx
0x180014fe8  jz      short loc_180014FFA
0x180014fea  mov     rax, [rbx]
0x180014fed  mov     rcx, rbx
0x180014ff0  mov     rax, [rax+10h]
0x180014ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ff9  nop
0x180014ffa  jmp     short loc_18001506E
0x180014ffc  mov     r12d, dword ptr [rsp+0C8h+arg_10]
0x180015004  jmp     short loc_18001506E
0x180015006  call    cs:__imp_GetLastError
0x18001500c  mov     edi, eax
0x18001500e  call    cs:__imp_CurrentIP
0x180015014  mov     rbx, rax
0x180015017  lea     rdx, aSystemsettings_51; "SystemSettings::PointInTimeRestore::CPo"...
0x18001501e  mov     ecx, 2000000h; unsigned int
0x180015023  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180015028  mov     [rsp+0C8h+var_78], r14d
0x18001502d  mov     [rsp+0C8h+var_80], r14
0x180015032  mov     [rsp+0C8h+var_88], edi
0x180015036  mov     [rsp+0C8h+var_90], rbx
0x18001503b  mov     [rsp+0C8h+var_98], rsi
0x180015040  mov     [rsp+0C8h+var_A0], r15
0x180015045  mov     [rsp+0C8h+var_A8], 654h
0x18001504d  xor     r9d, r9d
0x180015050  mov     r8, r13
0x180015053  xor     edx, edx
0x180015055  mov     rcx, rax
0x180015058  call    cs:__imp_WdsSetupLogMessageW
0x18001505e  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x180015063  mov     edx, r12d; int
0x180015066  mov     rcx, rax; this
0x180015069  call    ?SetLastPITRError@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEAAXJ@Z; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::SetLastPITRError(long)
0x18001506e  test    r12d, r12d
0x180015071  js      short loc_1800150DA
0x180015073  mov     r12, [rsp+0C8h+var_48]
0x18001507b  jmp     short loc_1800150D5
0x18001507d  call    cs:__imp_GetLastError
0x180015083  mov     edi, eax
0x180015085  call    cs:__imp_CurrentIP
0x18001508b  mov     rbx, rax
0x18001508e  lea     rdx, aSystemsettings_44; "SystemSettings::PointInTimeRestore::CPo"...
0x180015095  mov     ecx, 2000000h; unsigned int
0x18001509a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001509f  mov     [rsp+0C8h+var_78], r14d
0x1800150a4  mov     [rsp+0C8h+var_80], r14
0x1800150a9  mov     [rsp+0C8h+var_88], edi
0x1800150ad  mov     [rsp+0C8h+var_90], rbx
0x1800150b2  mov     [rsp+0C8h+var_98], rsi
0x1800150b7  mov     [rsp+0C8h+var_A0], r15
0x1800150bc  mov     [rsp+0C8h+var_A8], 65Ah
0x1800150c4  xor     r9d, r9d
0x1800150c7  mov     r8, r13
0x1800150ca  xor     edx, edx
0x1800150cc  mov     rcx, rax
0x1800150cf  call    cs:__imp_WdsSetupLogMessageW
0x1800150d5  test    r12, r12
0x1800150d8  jnz     short loc_180015111
0x1800150da  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x1800150df  mov     [rsp+0C8h+arg_8], 6
0x1800150ea  lea     rcx, aCpointintimere_71; "CPointInTimeRestoreDialog"
0x1800150f1  mov     [rsp+0C8h+var_58], rcx
0x1800150f6  lea     rcx, [rsp+0C8h+arg_8]
0x1800150fe  mov     [rsp+0C8h+var_50], rcx
0x180015103  lea     rdx, [rsp+0C8h+var_58]
0x180015108  mov     rcx, rax
0x18001510b  call    ??$_Notify@V_lambda_ba361b346e648473d0e0f5ec774d7d2a_@@@?$CSingletonHelper@W4PITREvent@PointInTimeRestore@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_ba361b346e648473d0e0f5ec774d7d2a_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PointInTimeRestore::PITREvent>::_Notify<_lambda_ba361b346e648473d0e0f5ec774d7d2a_>(_lambda_ba361b346e648473d0e0f5ec774d7d2a_ const &)
0x180015110  nop
0x180015111  mov     rbx, [rsp+0C8h+var_40]
0x180015119  test    rbx, rbx
0x18001511c  jz      short loc_180015154
  ... truncated ...
```
