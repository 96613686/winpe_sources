# CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention(ulong)

- ea: `0x18000da8c`
- end: `0x18000dce6`
- name: `?SetPointInTimeRestoreSnapshotRetention@CPointInTimeRestoreHelper@@QEAAJK@Z`
- size: `602`
- prototype: `__int64 __fastcall(CPointInTimeRestoreHelper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000ee40`

## callees

- `0x18000bef4`
- `0x18000bfe0`
- `0x18000da8c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000daa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000daa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc73`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000db11`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000db84`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000dc6d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000dccf`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000db11`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000db84`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000dc6d`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000dccf`
- `WDSCORE!CurrentIP` at `0x18000daa8`
- `WDSCORE!CurrentIP` at `0x18000db30`
- `WDSCORE!CurrentIP` at `0x18000dbc1`
- `WDSCORE!CurrentIP` at `0x18000dc19`
- `WDSCORE!CurrentIP` at `0x18000dc7b`
- `WDSCORE!CurrentIP` at `0x18000daa8`
- `WDSCORE!CurrentIP` at `0x18000db30`
- `WDSCORE!CurrentIP` at `0x18000dbc1`
- `WDSCORE!CurrentIP` at `0x18000dc19`
- `WDSCORE!CurrentIP` at `0x18000dc7b`

## string_xrefs

- `0x18000dadd`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`

## pseudocode

```c
__int64 __fastcall CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention(
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
         "Enter CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention: setting PITR snapshot retention to %d",
         a2);
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    477,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention",
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
           "CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention: Setting snapshot retention to %d",
           a2);
    WdsSetupLogMessageW(
      v9,
      0,
      L"D",
      0,
      483,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention",
      v8,
      v7,
      0,
      0);
    PITRSettingsInterface = CPointInTimeRestoreHelper::GetPITRSettingsInterface(this);
    v11 = (*(__int64 (__fastcall **)(struct PITR::IPITRSettings *, __int64, _QWORD))(*(_QWORD *)PITRSettingsInterface
                                                                                   + 136LL))(
            PITRSettingsInterface,
            2,
            a2);
    if ( v11 < 0 )
    {
      v12 = GetLastError();
      v13 = CurrentIP();
      v14 = ConstructPartialMsgW(
              0x2000000u,
              "CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention: Failed to set PITR snapshot retention. hr=0x%08X",
              v11);
      WdsSetupLogMessageW(
        v14,
        0,
        L"D",
        0,
        487,
        L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
        L"CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention",
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
            "CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention: PITR setting interface is unexpectedly null. hr=0x%08X",
            -2147418113);
    WdsSetupLogMessageW(
      v17,
      0,
      L"D",
      0,
      494,
      L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
      L"CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention",
      v16,
      v15,
      0,
      0);
  }
  v18 = GetLastError();
  v19 = CurrentIP();
  v20 = ConstructPartialMsgW(
          0x4000000u,
          "CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention: Exiting with hr=0x%08X",
          v11);
  WdsSetupLogMessageW(
    v20,
    0,
    L"D",
    0,
    500,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention",
    v19,
    v18,
    0,
    0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000da8c  push    rbx
0x18000da8e  push    rbp
0x18000da8f  push    rsi
0x18000da90  push    rdi
0x18000da91  push    r12
0x18000da93  push    r13
0x18000da95  push    r15
0x18000da97  sub     rsp, 60h
0x18000da9b  mov     esi, edx
0x18000da9d  mov     rbp, rcx
0x18000daa0  call    cs:__imp_GetLastError
0x18000daa6  mov     edi, eax
0x18000daa8  call    cs:__imp_CurrentIP
0x18000daae  mov     r8d, esi
0x18000dab1  lea     rdx, aEnterCpointint_5; "Enter CPointInTimeRestoreHelper::SetPoi"...
0x18000dab8  mov     ecx, 4000000h; unsigned int
0x18000dabd  mov     rbx, rax
0x18000dac0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000dac5  mov     [rsp+98h+var_48], 0
0x18000dacd  lea     r12, aCpointintimere_45; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000dad4  mov     [rsp+98h+var_50], 0
0x18000dadd  lea     r13, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000dae4  mov     [rsp+98h+var_58], edi
0x18000dae8  lea     r15, aD; "D"
0x18000daef  mov     [rsp+98h+var_60], rbx
0x18000daf4  xor     r9d, r9d
0x18000daf7  mov     [rsp+98h+var_68], r12
0x18000dafc  mov     r8, r15
0x18000daff  mov     [rsp+98h+var_70], r13
0x18000db04  xor     edx, edx
0x18000db06  mov     rcx, rax
0x18000db09  mov     [rsp+98h+var_78], 1DDh
0x18000db11  call    cs:__imp_WdsSetupLogMessageW
0x18000db17  mov     rcx, rbp; this
0x18000db1a  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000db1f  test    rax, rax
0x18000db22  jz      loc_18000DC0C
0x18000db28  call    cs:__imp_GetLastError
0x18000db2e  mov     edi, eax
0x18000db30  call    cs:__imp_CurrentIP
0x18000db36  mov     r8d, esi
0x18000db39  lea     rdx, aCpointintimere_50; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000db40  mov     ecx, 4000000h; unsigned int
0x18000db45  mov     rbx, rax
0x18000db48  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000db4d  mov     [rsp+98h+var_48], 0
0x18000db55  xor     r9d, r9d
0x18000db58  mov     [rsp+98h+var_50], 0
0x18000db61  mov     r8, r15
0x18000db64  mov     [rsp+98h+var_58], edi
0x18000db68  xor     edx, edx
0x18000db6a  mov     [rsp+98h+var_60], rbx
0x18000db6f  mov     rcx, rax
0x18000db72  mov     [rsp+98h+var_68], r12
0x18000db77  mov     [rsp+98h+var_70], r13
0x18000db7c  mov     [rsp+98h+var_78], 1E3h
0x18000db84  call    cs:__imp_WdsSetupLogMessageW
0x18000db8a  mov     rcx, rbp; this
0x18000db8d  call    ?GetPITRSettingsInterface@CPointInTimeRestoreHelper@@AEAAPEAUIPITRSettings@PITR@@XZ; CPointInTimeRestoreHelper::GetPITRSettingsInterface(void)
0x18000db92  mov     r9, rax
0x18000db95  mov     r8d, esi
0x18000db98  mov     edx, 2
0x18000db9d  mov     rcx, [rax]
0x18000dba0  mov     rax, [rcx+88h]
0x18000dba7  mov     rcx, r9
0x18000dbaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbaf  mov     esi, eax
0x18000dbb1  test    eax, eax
0x18000dbb3  jns     loc_18000DC73
0x18000dbb9  call    cs:__imp_GetLastError
0x18000dbbf  mov     edi, eax
0x18000dbc1  call    cs:__imp_CurrentIP
0x18000dbc7  mov     r8d, esi
0x18000dbca  lea     rdx, aCpointintimere_60; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000dbd1  mov     ecx, 2000000h; unsigned int
0x18000dbd6  mov     rbx, rax
0x18000dbd9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000dbde  mov     [rsp+98h+var_48], 0
0x18000dbe6  mov     [rsp+98h+var_50], 0
0x18000dbef  mov     [rsp+98h+var_58], edi
0x18000dbf3  mov     [rsp+98h+var_60], rbx
0x18000dbf8  mov     [rsp+98h+var_68], r12
0x18000dbfd  mov     [rsp+98h+var_70], r13
0x18000dc02  mov     [rsp+98h+var_78], 1E7h
0x18000dc0a  jmp     short loc_18000DC62
0x18000dc0c  mov     esi, 8000FFFFh
0x18000dc11  call    cs:__imp_GetLastError
0x18000dc17  mov     edi, eax
0x18000dc19  call    cs:__imp_CurrentIP
0x18000dc1f  mov     r8d, esi
0x18000dc22  lea     rdx, aCpointintimere_36; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000dc29  mov     ecx, 2000000h; unsigned int
0x18000dc2e  mov     rbx, rax
0x18000dc31  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000dc36  mov     [rsp+98h+var_48], 0
0x18000dc3e  mov     [rsp+98h+var_50], 0
0x18000dc47  mov     [rsp+98h+var_58], edi
0x18000dc4b  mov     [rsp+98h+var_60], rbx
0x18000dc50  mov     [rsp+98h+var_68], r12
0x18000dc55  mov     [rsp+98h+var_70], r13
0x18000dc5a  mov     [rsp+98h+var_78], 1EEh
0x18000dc62  xor     r9d, r9d
0x18000dc65  mov     r8, r15
0x18000dc68  xor     edx, edx
0x18000dc6a  mov     rcx, rax
0x18000dc6d  call    cs:__imp_WdsSetupLogMessageW
0x18000dc73  call    cs:__imp_GetLastError
0x18000dc79  mov     edi, eax
0x18000dc7b  call    cs:__imp_CurrentIP
0x18000dc81  mov     r8d, esi
0x18000dc84  lea     rdx, aCpointintimere_61; "CPointInTimeRestoreHelper::SetPointInTi"...
0x18000dc8b  mov     ecx, 4000000h; unsigned int
0x18000dc90  mov     rbx, rax
0x18000dc93  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000dc98  mov     [rsp+98h+var_48], 0
0x18000dca0  xor     r9d, r9d
0x18000dca3  mov     [rsp+98h+var_50], 0
0x18000dcac  mov     r8, r15
0x18000dcaf  mov     [rsp+98h+var_58], edi
0x18000dcb3  xor     edx, edx
0x18000dcb5  mov     [rsp+98h+var_60], rbx
0x18000dcba  mov     rcx, rax
0x18000dcbd  mov     [rsp+98h+var_68], r12
0x18000dcc2  mov     [rsp+98h+var_70], r13
0x18000dcc7  mov     [rsp+98h+var_78], 1F4h
0x18000dccf  call    cs:__imp_WdsSetupLogMessageW
0x18000dcd5  mov     eax, esi
0x18000dcd7  add     rsp, 60h
0x18000dcdb  pop     r15
0x18000dcdd  pop     r13
0x18000dcdf  pop     r12
0x18000dce1  pop     rdi
0x18000dce2  pop     rsi
0x18000dce3  pop     rbp
0x18000dce4  pop     rbx
0x18000dce5  retn
```
