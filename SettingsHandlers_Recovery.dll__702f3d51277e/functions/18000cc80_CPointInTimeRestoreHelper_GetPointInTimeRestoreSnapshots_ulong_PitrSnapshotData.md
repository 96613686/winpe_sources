# CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots(ulong *,_PitrSnapshotData * *)

- ea: `0x18000cc80`
- end: `0x18000d366`
- name: `?GetPointInTimeRestoreSnapshots@CPointInTimeRestoreHelper@@QEAAJPEAKPEAPEAU_PitrSnapshotData@@@Z`
- size: `1766`
- prototype: `__int64 __fastcall(CPointInTimeRestoreHelper *__hidden this, unsigned int *, struct _PitrSnapshotData **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18000ea20`

## callees

- `0x18000bef4`
- `0x18000bf24`
- `0x18000cc80`
- `0x18002b010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000cea5`
- `ole32!CoTaskMemAlloc` at `0x18000cea5`
- `ole32!CoTaskMemFree` at `0x18000cfa3`
- `ole32!CoTaskMemFree` at `0x18000cfa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d145`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d20e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cdc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ce4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cfb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d145`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d1c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d20e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2ee`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000cd23`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000cd9f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ce1b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ce9c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000cf9a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d00c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d0d5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d12a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d1a5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d275`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d2d8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d343`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000cd23`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000cd9f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ce1b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ce9c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000cf9a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d00c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d0d5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d12a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d1a5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d275`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d2d8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d343`
- `WDSCORE!CurrentIP` at `0x18000ccc4`
- `WDSCORE!CurrentIP` at `0x18000cd55`
- `WDSCORE!CurrentIP` at `0x18000cdca`
- `WDSCORE!CurrentIP` at `0x18000ce53`
- `WDSCORE!CurrentIP` at `0x18000cf49`
- `WDSCORE!CurrentIP` at `0x18000cfbb`
- `WDSCORE!CurrentIP` at `0x18000d029`
- `WDSCORE!CurrentIP` at `0x18000d07c`
- `WDSCORE!CurrentIP` at `0x18000d14d`
- `WDSCORE!CurrentIP` at `0x18000d1cd`
- `WDSCORE!CurrentIP` at `0x18000d216`
- `WDSCORE!CurrentIP` at `0x18000d28e`
- `WDSCORE!CurrentIP` at `0x18000d2f6`
- `WDSCORE!CurrentIP` at `0x18000ccc4`
- `WDSCORE!CurrentIP` at `0x18000cd55`
- `WDSCORE!CurrentIP` at `0x18000cdca`
- `WDSCORE!CurrentIP` at `0x18000ce53`
- `WDSCORE!CurrentIP` at `0x18000cf49`
- `WDSCORE!CurrentIP` at `0x18000cfbb`
- `WDSCORE!CurrentIP` at `0x18000d029`
- `WDSCORE!CurrentIP` at `0x18000d07c`
- `WDSCORE!CurrentIP` at `0x18000d14d`
- `WDSCORE!CurrentIP` at `0x18000d1cd`
- `WDSCORE!CurrentIP` at `0x18000d216`
- `WDSCORE!CurrentIP` at `0x18000d28e`
- `WDSCORE!CurrentIP` at `0x18000d2f6`

## string_xrefs

- `0x18000ccef`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000d241`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000cfc1`: `CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: Failed to create snapshot info struct`

## pseudocode

```c
__int64 __fastcall CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots(
        CPointInTimeRestoreHelper *this,
        unsigned int *a2,
        struct _PitrSnapshotData **a3)
{
  _DWORD *v3; // r13
  DWORD v5; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  struct PITR::IPITRBase *PITRBaseInterface; // rax
  int v9; // esi
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  DWORD v13; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  DWORD v16; // edi
  __int64 v17; // rbx
  struct tagLOG_PARTIAL_MSG *v18; // rax
  _OWORD *v19; // rax
  _DWORD *v20; // rsi
  _DWORD *v21; // rax
  DWORD v22; // edi
  __int64 v23; // rbx
  struct tagLOG_PARTIAL_MSG *v24; // rax
  DWORD v25; // edi
  __int64 v26; // rbx
  struct tagLOG_PARTIAL_MSG *v27; // rax
  DWORD v28; // edi
  __int64 v29; // rbx
  struct tagLOG_PARTIAL_MSG *v30; // rax
  DWORD v31; // edi
  __int64 v32; // rbx
  struct tagLOG_PARTIAL_MSG *v33; // rax
  struct tagLOG_PARTIAL_MSG *v34; // rax
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  DWORD v38; // edi
  __int64 v39; // rbx
  struct tagLOG_PARTIAL_MSG *v40; // rax
  DWORD LastError; // edi
  __int64 v42; // rbx
  struct tagLOG_PARTIAL_MSG *v43; // rax
  DWORD v44; // edi
  __int64 v45; // rbx
  struct tagLOG_PARTIAL_MSG *v46; // rax
  DWORD v47; // edi
  __int64 v48; // rbx
  struct tagLOG_PARTIAL_MSG *v49; // rax
  __int64 i; // [rsp+60h] [rbp-20h] BYREF
  __int64 v52; // [rsp+68h] [rbp-18h] BYREF
  struct _PitrSnapshotData *v53; // [rsp+70h] [rbp-10h]
  _BYTE v54[8]; // [rsp+78h] [rbp-8h] BYREF
  unsigned int v57; // [rsp+D8h] [rbp+58h]

  v3 = 0;
  v52 = 0;
  if ( !CPointInTimeRestoreHelper::GetPITRBaseInterface(this) )
  {
    LastError = GetLastError();
    v42 = CurrentIP();
    v43 = ConstructPartialMsgW(
            0x2000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: PITR base interface is unexpectedly null.");
    WdsSetupLogMessageW(
      v43,
      0,
      L"D",
      0,
      361,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
      v42,
      LastError,
      0,
      0);
    goto LABEL_25;
  }
  v5 = GetLastError();
  v6 = CurrentIP();
  v7 = ConstructPartialMsgW(
         0x4000000u,
         "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: getting PITR snapshot enumerator");
  WdsSetupLogMessageW(
    v7,
    0,
    L"D",
    0,
    263,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
    v6,
    v5,
    0,
    0);
  PITRBaseInterface = CPointInTimeRestoreHelper::GetPITRBaseInterface(this);
  v9 = (*(__int64 (__fastcall **)(struct PITR::IPITRBase *, __int64 *))(*(_QWORD *)PITRBaseInterface + 32LL))(
         PITRBaseInterface,
         &v52);
  if ( v9 < 0 )
  {
    v10 = GetLastError();
    v11 = CurrentIP();
    v12 = ConstructPartialMsgW(
            0x2000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: Failed to get PITR snapshot enumerator");
    WdsSetupLogMessageW(
      v12,
      0,
      L"D",
      0,
      267,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
      v11,
      v10,
      0,
      0);
    goto LABEL_26;
  }
  if ( !v52 )
  {
    v38 = GetLastError();
    v39 = CurrentIP();
    v40 = ConstructPartialMsgW(
            0x2000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: PITR snapshot enumerator is unexpectedly null.");
    WdsSetupLogMessageW(
      v40,
      0,
      L"D",
      0,
      354,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
      v39,
      v38,
      0,
      0);
LABEL_25:
    v9 = -2147418113;
    goto LABEL_26;
  }
  v57 = 0;
  v53 = 0;
  for ( i = 0; ; i = 0 )
  {
    v13 = GetLastError();
    v14 = CurrentIP();
    v15 = ConstructPartialMsgW(
            0x4000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: getting next PITR snapshot");
    WdsSetupLogMessageW(
      v15,
      0,
      L"D",
      0,
      276,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
      v14,
      v13,
      0,
      0);
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 8LL))(v52, &i);
    if ( v9 < 0 )
      break;
    if ( !i )
    {
      v9 = -2147418113;
      v28 = GetLastError();
      v29 = CurrentIP();
      v30 = ConstructPartialMsgW(
              0x2000000u,
              "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: PITR snapshot is unexpectedly null.");
      WdsSetupLogMessageW(
        v30,
        0,
        L"D",
        0,
        296,
        L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
        L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
        v29,
        v28,
        0,
        0);
      goto LABEL_20;
    }
    v16 = GetLastError();
    v17 = CurrentIP();
    v18 = ConstructPartialMsgW(
            0x4000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: Populating snapshot information");
    WdsSetupLogMessageW(
      v18,
      0,
      L"D",
      0,
      300,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
      v17,
      v16,
      0,
      0);
    v19 = CoTaskMemAlloc(0x20u);
    v20 = v19;
    if ( !v19 )
    {
      v25 = GetLastError();
      v26 = CurrentIP();
      v27 = ConstructPartialMsgW(
              0x2000000u,
              "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: Failed to create snapshot info struct");
      WdsSetupLogMessageW(
        v27,
        0,
        L"D",
        0,
        304,
        L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
        L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
        v26,
        v25,
        0,
        0);
      v9 = -2147024882;
      goto LABEL_20;
    }
    *v19 = 0;
    v19[1] = 0;
    v21 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)i + 40LL))(i);
    if ( !v21 )
    {
      v22 = GetLastError();
      v23 = CurrentIP();
      v24 = ConstructPartialMsgW(
              0x2000000u,
              "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: Failed to get snapshot OS version");
      WdsSetupLogMessageW(
        v24,
        0,
        L"D",
        0,
        314,
        L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
        L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
        v23,
        v22,
        0,
        0);
      CoTaskMemFree(v20);
      v9 = -2147418113;
      goto LABEL_20;
    }
    *v20 = *v21;
    v20[1] = v21[1];
    v20[2] = v21[2];
    v20[3] = v21[3];
    *((_QWORD *)v20 + 2) = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)i + 16LL))(i, v54);
    *((_QWORD *)v20 + 3) = 0;
    if ( v3 )
      *((_QWORD *)v3 + 3) = v20;
    else
      v53 = (struct _PitrSnapshotData *)v20;
    v3 = v20;
    ++v57;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)i + 64LL))(i);
  }
  v31 = GetLastError();
  v32 = CurrentIP();
  if ( v9 == -2147024637 )
  {
    v33 = ConstructPartialMsgW(
            0x4000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: Found all snapshots!");
    WdsSetupLogMessageW(
      v33,
      0,
      L"D",
      0,
      283,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
      v32,
      v31,
      0,
      0);
    v9 = 0;
  }
  else
  {
    v34 = ConstructPartialMsgW(
            0x2000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: Failed to get the next snapshot. Error: 0x%08X\n",
            v9);
    WdsSetupLogMessageW(
      v34,
      0,
      L"D",
      0,
      288,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
      v32,
      v31,
      0,
      0);
  }
LABEL_20:
  if ( i )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)i + 64LL))(i);
  v35 = GetLastError();
  v36 = CurrentIP();
  v37 = ConstructPartialMsgW(
          0x4000000u,
          "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: Found %d snapshots",
          v57);
  WdsSetupLogMessageW(
    v37,
    0,
    L"D",
    0,
    367,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
    v36,
    v35,
    0,
    0);
  *a3 = v53;
  *a2 = v57;
LABEL_26:
  if ( v52 )
  {
    v44 = GetLastError();
    v45 = CurrentIP();
    v46 = ConstructPartialMsgW(
            0x4000000u,
            "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: Releasing PITR snapshot enumerator");
    WdsSetupLogMessageW(
      v46,
      0,
      L"D",
      0,
      379,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
      v45,
      v44,
      0,
      0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  }
  v47 = GetLastError();
  v48 = CurrentIP();
  v49 = ConstructPartialMsgW(
          0x4000000u,
          "CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots: Exiting with hr=0x%08X",
          v9);
  WdsSetupLogMessageW(
    v49,
    0,
    L"D",
    0,
    390,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots",
    v48,
    v47,
    0,
    0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000cc80  mov     [rsp-38h+arg_0], rbx
0x18000cc85  mov     [rsp-38h+arg_10], r8
0x18000cc8a  mov     [rsp-38h+arg_8], rdx
0x18000cc8f  push    rbp
0x18000cc90  push    rsi
0x18000cc91  push    rdi
0x18000cc92  push    r12
0x18000cc94  push    r13
0x18000cc96  push    r14
0x18000cc98  push    r15
0x18000cc9a  mov     rbp, rsp
0x18000cc9d  sub     rsp, 80h
0x18000cca4  xor     r13d, r13d
0x18000cca7  mov     rsi, rcx
0x18000ccaa  mov     [rbp+var_18], r13
0x18000ccae  call    ?GetPITRBaseInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRBase@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRBaseInterface(void)
0x18000ccb3  test    rax, rax
0x18000ccb6  jz      loc_18000D20E
0x18000ccbc  call    cs:__imp_GetLastError
0x18000ccc2  mov     edi, eax
0x18000ccc4  call    cs:__imp_CurrentIP
0x18000ccca  lea     rdx, aCpointintimere_23; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000ccd1  mov     ecx, 4000000h; unsigned int
0x18000ccd6  mov     rbx, rax
0x18000ccd9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ccde  mov     [rsp+80h+var_30], r13d
0x18000cce3  lea     r15, aCpointintimere_40; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000ccea  mov     [rsp+80h+var_38], r13
0x18000ccef  lea     r12, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000ccf6  mov     [rsp+80h+var_40], edi
0x18000ccfa  lea     r14, aD; "D"
0x18000cd01  mov     [rsp+80h+var_48], rbx
0x18000cd06  xor     r9d, r9d
0x18000cd09  mov     [rsp+80h+var_50], r15
0x18000cd0e  mov     r8, r14
0x18000cd11  mov     [rsp+80h+var_58], r12
0x18000cd16  xor     edx, edx
0x18000cd18  mov     rcx, rax
0x18000cd1b  mov     [rsp+80h+var_60], 107h
0x18000cd23  call    cs:__imp_WdsSetupLogMessageW
0x18000cd29  mov     rcx, rsi; this
0x18000cd2c  call    ?GetPITRBaseInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRBase@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRBaseInterface(void)
0x18000cd31  mov     r8, rax
0x18000cd34  lea     rdx, [rbp+var_18]
0x18000cd38  mov     rcx, [rax]
0x18000cd3b  mov     rax, [rcx+20h]
0x18000cd3f  mov     rcx, r8
0x18000cd42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd47  mov     esi, eax
0x18000cd49  test    eax, eax
0x18000cd4b  jns     short loc_18000CDAA
0x18000cd4d  call    cs:__imp_GetLastError
0x18000cd53  mov     edi, eax
0x18000cd55  call    cs:__imp_CurrentIP
0x18000cd5b  lea     rdx, aCpointintimere_35; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000cd62  mov     ecx, 2000000h; unsigned int
0x18000cd67  mov     rbx, rax
0x18000cd6a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cd6f  mov     [rsp+80h+var_30], r13d
0x18000cd74  xor     r9d, r9d
0x18000cd77  mov     [rsp+80h+var_38], r13
0x18000cd7c  mov     r8, r14
0x18000cd7f  mov     [rsp+80h+var_40], edi
0x18000cd83  xor     edx, edx
0x18000cd85  mov     [rsp+80h+var_48], rbx
0x18000cd8a  mov     rcx, rax
0x18000cd8d  mov     [rsp+80h+var_50], r15
0x18000cd92  mov     [rsp+80h+var_58], r12
0x18000cd97  mov     [rsp+80h+var_60], 10Bh
0x18000cd9f  call    cs:__imp_WdsSetupLogMessageW
0x18000cda5  jmp     loc_18000D280
0x18000cdaa  cmp     [rbp+var_18], r13
0x18000cdae  jz      loc_18000D1C5
0x18000cdb4  xor     eax, eax
0x18000cdb6  mov     [rbp+arg_18], r13d
0x18000cdba  mov     [rbp+var_10], rax
0x18000cdbe  mov     [rbp+var_20], rax
0x18000cdc2  call    cs:__imp_GetLastError
0x18000cdc8  mov     edi, eax
0x18000cdca  call    cs:__imp_CurrentIP
0x18000cdd0  lea     rdx, aCpointintimere_0; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000cdd7  mov     ecx, 4000000h; unsigned int
0x18000cddc  mov     rbx, rax
0x18000cddf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cde4  mov     [rsp+80h+var_30], 0
0x18000cdec  xor     r9d, r9d
0x18000cdef  mov     [rsp+80h+var_38], 0
0x18000cdf8  mov     r8, r14
0x18000cdfb  mov     [rsp+80h+var_40], edi
0x18000cdff  xor     edx, edx
0x18000ce01  mov     [rsp+80h+var_48], rbx
0x18000ce06  mov     rcx, rax
0x18000ce09  mov     [rsp+80h+var_50], r15
0x18000ce0e  mov     [rsp+80h+var_58], r12
0x18000ce13  mov     [rsp+80h+var_60], 114h
0x18000ce1b  call    cs:__imp_WdsSetupLogMessageW
0x18000ce21  mov     rcx, [rbp+var_18]
0x18000ce25  lea     rdx, [rbp+var_20]
0x18000ce29  mov     rax, [rcx]
0x18000ce2c  mov     rax, [rax+8]
0x18000ce30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce35  mov     esi, eax
0x18000ce37  test    eax, eax
0x18000ce39  js      loc_18000D074
0x18000ce3f  xor     esi, esi
0x18000ce41  cmp     [rbp+var_20], rsi
0x18000ce45  jz      loc_18000D01C
0x18000ce4b  call    cs:__imp_GetLastError
0x18000ce51  mov     edi, eax
0x18000ce53  call    cs:__imp_CurrentIP
0x18000ce59  lea     rdx, aCpointintimere_2; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000ce60  mov     ecx, 4000000h; unsigned int
0x18000ce65  mov     rbx, rax
0x18000ce68  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ce6d  mov     [rsp+80h+var_30], esi
0x18000ce71  xor     r9d, r9d
0x18000ce74  mov     [rsp+80h+var_38], rsi
0x18000ce79  mov     r8, r14
0x18000ce7c  mov     [rsp+80h+var_40], edi
0x18000ce80  xor     edx, edx
0x18000ce82  mov     [rsp+80h+var_48], rbx
0x18000ce87  mov     rcx, rax
0x18000ce8a  mov     [rsp+80h+var_50], r15
0x18000ce8f  mov     [rsp+80h+var_58], r12
0x18000ce94  mov     [rsp+80h+var_60], 12Ch
0x18000ce9c  call    cs:__imp_WdsSetupLogMessageW
0x18000cea2  lea     ecx, [rsi+20h]; cb
0x18000cea5  call    cs:__imp_CoTaskMemAlloc
0x18000ceab  mov     rsi, rax
0x18000ceae  test    rax, rax
0x18000ceb1  jz      loc_18000CFB3
0x18000ceb7  xorps   xmm0, xmm0
0x18000ceba  movups  xmmword ptr [rax], xmm0
0x18000cebd  movups  xmmword ptr [rax+10h], xmm0
0x18000cec1  mov     rcx, [rbp+var_20]
0x18000cec5  mov     rdx, [rcx]
0x18000cec8  mov     rax, [rdx+28h]
0x18000cecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ced1  test    rax, rax
0x18000ced4  jz      short loc_18000CF41
0x18000ced6  mov     ecx, [rax]
0x18000ced8  lea     rdx, [rbp+var_8]
0x18000cedc  mov     [rsi], ecx
0x18000cede  mov     ecx, [rax+4]
0x18000cee1  mov     [rsi+4], ecx
0x18000cee4  mov     ecx, [rax+8]
0x18000cee7  mov     [rsi+8], ecx
0x18000ceea  mov     eax, [rax+0Ch]
0x18000ceed  mov     [rsi+0Ch], eax
0x18000cef0  mov     rcx, [rbp+var_20]
0x18000cef4  mov     rax, [rcx]
0x18000cef7  mov     rax, [rax+10h]
0x18000cefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf00  mov     rcx, [rax]
0x18000cf03  mov     [rsi+10h], rcx
0x18000cf07  mov     qword ptr [rsi+18h], 0
0x18000cf0f  test    r13, r13
0x18000cf12  jz      short loc_18000CF1A
0x18000cf14  mov     [r13+18h], rsi
0x18000cf18  jmp     short loc_18000CF1E
0x18000cf1a  mov     [rbp+var_10], rsi
0x18000cf1e  mov     rcx, [rbp+var_20]
0x18000cf22  mov     r13, rsi
0x18000cf25  inc     [rbp+arg_18]
0x18000cf28  mov     rax, [rcx]
0x18000cf2b  mov     rax, [rax+40h]
0x18000cf2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf34  mov     [rbp+var_20], 0
0x18000cf3c  jmp     loc_18000CDC2
0x18000cf41  call    cs:__imp_GetLastError
0x18000cf47  mov     edi, eax
0x18000cf49  call    cs:__imp_CurrentIP
0x18000cf4f  lea     rdx, aCpointintimere_9; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000cf56  mov     ecx, 2000000h; unsigned int
0x18000cf5b  mov     rbx, rax
0x18000cf5e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cf63  mov     [rsp+80h+var_30], 0
0x18000cf6b  xor     r9d, r9d
0x18000cf6e  mov     [rsp+80h+var_38], 0
0x18000cf77  mov     r8, r14
0x18000cf7a  mov     [rsp+80h+var_40], edi
0x18000cf7e  xor     edx, edx
0x18000cf80  mov     [rsp+80h+var_48], rbx
0x18000cf85  mov     rcx, rax
0x18000cf88  mov     [rsp+80h+var_50], r15
0x18000cf8d  mov     [rsp+80h+var_58], r12
0x18000cf92  mov     [rsp+80h+var_60], 13Ah
0x18000cf9a  call    cs:__imp_WdsSetupLogMessageW
0x18000cfa0  mov     rcx, rsi; pv
0x18000cfa3  call    cs:__imp_CoTaskMemFree
0x18000cfa9  mov     esi, 8000FFFFh
0x18000cfae  jmp     loc_18000D130
0x18000cfb3  call    cs:__imp_GetLastError
0x18000cfb9  mov     edi, eax
0x18000cfbb  call    cs:__imp_CurrentIP
0x18000cfc1  lea     rdx, aCpointintimere_46; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000cfc8  mov     ecx, 2000000h; unsigned int
0x18000cfcd  mov     rbx, rax
0x18000cfd0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000cfd5  mov     [rsp+80h+var_30], 0
0x18000cfdd  xor     r9d, r9d
0x18000cfe0  mov     [rsp+80h+var_38], 0
0x18000cfe9  mov     r8, r14
0x18000cfec  mov     [rsp+80h+var_40], edi
0x18000cff0  xor     edx, edx
0x18000cff2  mov     [rsp+80h+var_48], rbx
0x18000cff7  mov     rcx, rax
0x18000cffa  mov     [rsp+80h+var_50], r15
0x18000cfff  mov     [rsp+80h+var_58], r12
0x18000d004  mov     [rsp+80h+var_60], 130h
0x18000d00c  call    cs:__imp_WdsSetupLogMessageW
0x18000d012  mov     esi, 8007000Eh
0x18000d017  jmp     loc_18000D130
0x18000d01c  mov     esi, 8000FFFFh
0x18000d021  call    cs:__imp_GetLastError
0x18000d027  mov     edi, eax
0x18000d029  call    cs:__imp_CurrentIP
0x18000d02f  lea     rdx, aCpointintimere_12; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000d036  mov     ecx, 2000000h; unsigned int
0x18000d03b  mov     rbx, rax
0x18000d03e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d043  mov     [rsp+80h+var_30], 0
0x18000d04b  mov     [rsp+80h+var_38], 0
0x18000d054  mov     [rsp+80h+var_40], edi
0x18000d058  mov     [rsp+80h+var_48], rbx
0x18000d05d  mov     [rsp+80h+var_50], r15
0x18000d062  mov     [rsp+80h+var_58], r12
0x18000d067  mov     [rsp+80h+var_60], 128h
0x18000d06f  jmp     loc_18000D11F
0x18000d074  call    cs:__imp_GetLastError
0x18000d07a  mov     edi, eax
0x18000d07c  call    cs:__imp_CurrentIP
0x18000d082  mov     rbx, rax
0x18000d085  cmp     esi, 80070103h
0x18000d08b  jnz     short loc_18000D0DF
0x18000d08d  lea     rdx, aCpointintimere_70; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000d094  mov     ecx, 4000000h; unsigned int
0x18000d099  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d09e  mov     [rsp+80h+var_30], 0
0x18000d0a6  xor     r9d, r9d
0x18000d0a9  mov     [rsp+80h+var_38], 0
0x18000d0b2  mov     r8, r14
0x18000d0b5  mov     [rsp+80h+var_40], edi
0x18000d0b9  xor     edx, edx
0x18000d0bb  mov     [rsp+80h+var_48], rbx
0x18000d0c0  mov     rcx, rax
0x18000d0c3  mov     [rsp+80h+var_50], r15
0x18000d0c8  mov     [rsp+80h+var_58], r12
0x18000d0cd  mov     [rsp+80h+var_60], 11Bh
0x18000d0d5  call    cs:__imp_WdsSetupLogMessageW
0x18000d0db  xor     esi, esi
0x18000d0dd  jmp     short loc_18000D130
0x18000d0df  mov     r8d, esi
0x18000d0e2  lea     rdx, aCpointintimere_24; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000d0e9  mov     ecx, 2000000h; unsigned int
0x18000d0ee  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d0f3  mov     [rsp+80h+var_30], 0
0x18000d0fb  mov     [rsp+80h+var_38], 0
0x18000d104  mov     [rsp+80h+var_40], edi
0x18000d108  mov     [rsp+80h+var_48], rbx
0x18000d10d  mov     [rsp+80h+var_50], r15
0x18000d112  mov     [rsp+80h+var_58], r12
0x18000d117  mov     [rsp+80h+var_60], 120h
0x18000d11f  xor     r9d, r9d
0x18000d122  mov     r8, r14
0x18000d125  xor     edx, edx
0x18000d127  mov     rcx, rax
0x18000d12a  call    cs:__imp_WdsSetupLogMessageW
0x18000d130  mov     rcx, [rbp+var_20]
0x18000d134  test    rcx, rcx
0x18000d137  jz      short loc_18000D145
0x18000d139  mov     rax, [rcx]
0x18000d13c  mov     rax, [rax+40h]
0x18000d140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d145  call    cs:__imp_GetLastError
0x18000d14b  mov     edi, eax
0x18000d14d  call    cs:__imp_CurrentIP
0x18000d153  mov     r13d, [rbp+arg_18]
0x18000d157  lea     rdx, aCpointintimere_14; "CPointInTimeRestoreHelper::GetPointInTi"...
0x18000d15e  mov     r8d, r13d
0x18000d161  mov     ecx, 4000000h; unsigned int
0x18000d166  mov     rbx, rax
0x18000d169  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d16e  mov     [rsp+80h+var_30], 0
0x18000d176  xor     r9d, r9d
0x18000d179  mov     [rsp+80h+var_38], 0
0x18000d182  mov     r8, r14
0x18000d185  mov     [rsp+80h+var_40], edi
0x18000d189  xor     edx, edx
0x18000d18b  mov     [rsp+80h+var_48], rbx
0x18000d190  mov     rcx, rax
0x18000d193  mov     [rsp+80h+var_50], r15
0x18000d198  mov     [rsp+80h+var_58], r12
0x18000d19d  mov     [rsp+80h+var_60], 16Fh
0x18000d1a5  call    cs:__imp_WdsSetupLogMessageW
0x18000d1ab  mov     rax, [rbp+var_10]
0x18000d1af  mov     rcx, [rbp+arg_10]
0x18000d1b3  mov     [rcx], rax
0x18000d1b6  mov     rax, [rbp+arg_8]
0x18000d1ba  mov     [rax], r13d
  ... truncated ...
```
