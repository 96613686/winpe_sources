# CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence(ulong)

- ea: `0x18000d82c`
- end: `0x18000da83`
- name: `?SetPointInTimeRestoreSnapshotCadence@CPointInTimeRestoreHelper@@QEAAJK@Z`
- size: `599`
- prototype: `__int64 __fastcall(CPointInTimeRestoreHelper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000ed90`

## callees

- `0x18000bef4`
- `0x18000bfe0`
- `0x18000d82c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000da10`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d8b1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d924`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000da0a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000da6c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d8b1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000d924`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000da0a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000da6c`
- `WDSCORE!CurrentIP` at `0x18000d848`
- `WDSCORE!CurrentIP` at `0x18000d8d0`
- `WDSCORE!CurrentIP` at `0x18000d95e`
- `WDSCORE!CurrentIP` at `0x18000d9b6`
- `WDSCORE!CurrentIP` at `0x18000da18`
- `WDSCORE!CurrentIP` at `0x18000d848`
- `WDSCORE!CurrentIP` at `0x18000d8d0`
- `WDSCORE!CurrentIP` at `0x18000d95e`
- `WDSCORE!CurrentIP` at `0x18000d9b6`
- `WDSCORE!CurrentIP` at `0x18000da18`

## string_xrefs

- `0x18000d87d`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`

## pseudocode

```c
__int64 __fastcall CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence(
        CPointInTimeRestoreHelper *this,
        unsigned int a2)
{
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  DWORD v7; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  struct PITR::IPITRSettings *PITRSettingsInterface; // rax
  int v11; // esi
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax

  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = ConstructPartialMsgW(
         0x4000000u,
         "Enter CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence: setting PITR snapshot cadence to %d",
         a2);
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    445,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence",
    v5,
    LastError,
    0,
    0);
  if ( CPointInTimeRestoreHelper::GetPITRSettingsInterface(this) )
  {
    v7 = GetLastError();
    v8 = CurrentIP();
    v9 = ConstructPartialMsgW(
           0x4000000u,
           "CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence: Setting snapshot interval to %d",
           a2);
    WdsSetupLogMessageW(
      v9,
      0,
      L"D",
      0,
      451,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence",
      v8,
      v7,
      0,
      0);
    PITRSettingsInterface = CPointInTimeRestoreHelper::GetPITRSettingsInterface(this);
    v11 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64, _QWORD))(*(_QWORD *)PITRSettingsInterface
                                                                                   + 72LL))(
            PITRSettingsInterface,
            2,
            a2);
    if ( v11 < 0 )
    {
      v12 = GetLastError();
      v13 = CurrentIP();
      v14 = ConstructPartialMsgW(
              0x2000000u,
              "CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence: Failed to set PITR snapshot interval. hr=0x%08X",
              v11);
      WdsSetupLogMessageW(
        v14,
        0,
        L"D",
        0,
        455,
        L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
        L"CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence",
        v13,
        v12,
        0,
        0);
    }
  }
  else
  {
    v11 = -2147418113;
    v15 = GetLastError();
    v16 = CurrentIP();
    v17 = ConstructPartialMsgW(
            0x2000000u,
            "CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence: PITR setting interface is unexpectedly null. hr=0x%08X",
            -2147418113);
    WdsSetupLogMessageW(
      v17,
      0,
      L"D",
      0,
      462,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence",
      v16,
      v15,
      0,
      0);
  }
  v18 = GetLastError();
  v19 = CurrentIP();
  v20 = ConstructPartialMsgW(
          0x4000000u,
          "CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence: Exiting with hr=0x%08X",
          v11);
  WdsSetupLogMessageW(
    v20,
    0,
    L"D",
    0,
    468,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence",
    v19,
    v18,
    0,
    0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000d82c  push    rbx
0x18000d82e  push    rbp
0x18000d82f  push    rsi
0x18000d830  push    rdi
0x18000d831  push    r12
0x18000d833  push    r13
0x18000d835  push    r15
0x18000d837  sub     rsp, 60h
0x18000d83b  mov     esi, edx
0x18000d83d  mov     rbp, rcx
0x18000d840  call    cs:__imp_GetLastError
0x18000d846  mov     edi, eax
0x18000d848  call    cs:__imp_CurrentIP
0x18000d84e  mov     r8d, esi
0x18000d851  lea     rdx, aEnterCpointint_1; "Enter CPointInTimeRestoreHelper::SetPoi"...
0x18000d858  mov     ecx, 4000000h; unsigned int
0x18000d85d  mov     rbx, rax
0x18000d860  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d865  mov     [rsp+98h+var_48], 0
0x18000d86d  lea     r12, aCpointintimere_72; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d874  mov     [rsp+98h+var_50], 0
0x18000d87d  lea     r13, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000d884  mov     [rsp+98h+var_58], edi
0x18000d888  lea     r15, aD; "D"
0x18000d88f  mov     [rsp+98h+var_60], rbx
0x18000d894  xor     r9d, r9d
0x18000d897  mov     [rsp+98h+var_68], r12
0x18000d89c  mov     r8, r15
0x18000d89f  mov     [rsp+98h+var_70], r13
0x18000d8a4  xor     edx, edx
0x18000d8a6  mov     rcx, rax
0x18000d8a9  mov     [rsp+98h+var_78], 1BDh
0x18000d8b1  call    cs:__imp_WdsSetupLogMessageW
0x18000d8b7  mov     rcx, rbp; this
0x18000d8ba  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000d8bf  test    rax, rax
0x18000d8c2  jz      loc_18000D9A9
0x18000d8c8  call    cs:__imp_GetLastError
0x18000d8ce  mov     edi, eax
0x18000d8d0  call    cs:__imp_CurrentIP
0x18000d8d6  mov     r8d, esi
0x18000d8d9  lea     rdx, aCpointintimere_49; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d8e0  mov     ecx, 4000000h; unsigned int
0x18000d8e5  mov     rbx, rax
0x18000d8e8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d8ed  mov     [rsp+98h+var_48], 0
0x18000d8f5  xor     r9d, r9d
0x18000d8f8  mov     [rsp+98h+var_50], 0
0x18000d901  mov     r8, r15
0x18000d904  mov     [rsp+98h+var_58], edi
0x18000d908  xor     edx, edx
0x18000d90a  mov     [rsp+98h+var_60], rbx
0x18000d90f  mov     rcx, rax
0x18000d912  mov     [rsp+98h+var_68], r12
0x18000d917  mov     [rsp+98h+var_70], r13
0x18000d91c  mov     [rsp+98h+var_78], 1C3h
0x18000d924  call    cs:__imp_WdsSetupLogMessageW
0x18000d92a  mov     rcx, rbp; this
0x18000d92d  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000d932  mov     r9, rax
0x18000d935  mov     r8d, esi
0x18000d938  mov     edx, 2
0x18000d93d  mov     rcx, [rax]
0x18000d940  mov     rax, [rcx+48h]
0x18000d944  mov     rcx, r9
0x18000d947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d94c  mov     esi, eax
0x18000d94e  test    eax, eax
0x18000d950  jns     loc_18000DA10
0x18000d956  call    cs:__imp_GetLastError
0x18000d95c  mov     edi, eax
0x18000d95e  call    cs:__imp_CurrentIP
0x18000d964  mov     r8d, esi
0x18000d967  lea     rdx, aCpointintimere_66; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d96e  mov     ecx, 2000000h; unsigned int
0x18000d973  mov     rbx, rax
0x18000d976  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d97b  mov     [rsp+98h+var_48], 0
0x18000d983  mov     [rsp+98h+var_50], 0
0x18000d98c  mov     [rsp+98h+var_58], edi
0x18000d990  mov     [rsp+98h+var_60], rbx
0x18000d995  mov     [rsp+98h+var_68], r12
0x18000d99a  mov     [rsp+98h+var_70], r13
0x18000d99f  mov     [rsp+98h+var_78], 1C7h
0x18000d9a7  jmp     short loc_18000D9FF
0x18000d9a9  mov     esi, 8000FFFFh
0x18000d9ae  call    cs:__imp_GetLastError
0x18000d9b4  mov     edi, eax
0x18000d9b6  call    cs:__imp_CurrentIP
0x18000d9bc  mov     r8d, esi
0x18000d9bf  lea     rdx, aCpointintimere_73; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000d9c6  mov     ecx, 2000000h; unsigned int
0x18000d9cb  mov     rbx, rax
0x18000d9ce  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000d9d3  mov     [rsp+98h+var_48], 0
0x18000d9db  mov     [rsp+98h+var_50], 0
0x18000d9e4  mov     [rsp+98h+var_58], edi
0x18000d9e8  mov     [rsp+98h+var_60], rbx
0x18000d9ed  mov     [rsp+98h+var_68], r12
0x18000d9f2  mov     [rsp+98h+var_70], r13
0x18000d9f7  mov     [rsp+98h+var_78], 1CEh
0x18000d9ff  xor     r9d, r9d
0x18000da02  mov     r8, r15
0x18000da05  xor     edx, edx
0x18000da07  mov     rcx, rax
0x18000da0a  call    cs:__imp_WdsSetupLogMessageW
0x18000da10  call    cs:__imp_GetLastError
0x18000da16  mov     edi, eax
0x18000da18  call    cs:__imp_CurrentIP
0x18000da1e  mov     r8d, esi
0x18000da21  lea     rdx, aCpointintimere_10; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000da28  mov     ecx, 4000000h; unsigned int
0x18000da2d  mov     rbx, rax
0x18000da30  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000da35  mov     [rsp+98h+var_48], 0
0x18000da3d  xor     r9d, r9d
0x18000da40  mov     [rsp+98h+var_50], 0
0x18000da49  mov     r8, r15
0x18000da4c  mov     [rsp+98h+var_58], edi
0x18000da50  xor     edx, edx
0x18000da52  mov     [rsp+98h+var_60], rbx
0x18000da57  mov     rcx, rax
0x18000da5a  mov     [rsp+98h+var_68], r12
0x18000da5f  mov     [rsp+98h+var_70], r13
0x18000da64  mov     [rsp+98h+var_78], 1D4h
0x18000da6c  call    cs:__imp_WdsSetupLogMessageW
0x18000da72  mov     eax, esi
0x18000da74  add     rsp, 60h
0x18000da78  pop     r15
0x18000da7a  pop     r13
0x18000da7c  pop     r12
0x18000da7e  pop     rdi
0x18000da7f  pop     rsi
0x18000da80  pop     rbp
0x18000da81  pop     rbx
0x18000da82  retn
```
