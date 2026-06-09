# CRecoveryAdminHelper::GetPointInTimeRestoreSnapshotRetention(int *,int *,ulong *)

- ea: `0x18000e960`
- end: `0x18000ea0f`
- name: `?GetPointInTimeRestoreSnapshotRetention@CRecoveryAdminHelper@@UEAAJPEAH0PEAK@Z`
- size: `175`
- prototype: `__int64 __fastcall(CRecoveryAdminHelper *__hidden this, int *, int *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000bef4`
- `0x18000ca18`
- `0x18000e110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e979`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e979`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e9e4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e9e4`
- `WDSCORE!CurrentIP` at `0x18000e981`
- `WDSCORE!CurrentIP` at `0x18000e981`

## string_xrefs

- `0x18000e9cd`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`

## pseudocode

```c
__int64 __fastcall CRecoveryAdminHelper::GetPointInTimeRestoreSnapshotRetention(
        CRecoveryAdminHelper *this,
        int *a2,
        int *a3,
        unsigned int *a4)
{
  DWORD LastError; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  CPointInTimeRestoreHelper *CurrentPointInTimeRestoreHelper; // rax

  LastError = GetLastError();
  v9 = CurrentIP();
  v10 = ConstructPartialMsgW(
          0x4000000u,
          "CRecoveryAdminHelper::GetPointInTimeRestoreSnapshotRetention: getting PITR snapshot retention");
  WdsSetupLogMessageW(
    v10,
    0,
    L"D",
    0,
    86,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
    L"CRecoveryAdminHelper::GetPointInTimeRestoreSnapshotRetention",
    v9,
    LastError,
    0,
    0);
  CurrentPointInTimeRestoreHelper = CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(this);
  return CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotRetention(CurrentPointInTimeRestoreHelper, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e960  push    rbx
0x18000e962  push    rbp
0x18000e963  push    rsi
0x18000e964  push    rdi
0x18000e965  push    r14
0x18000e967  push    r15
0x18000e969  sub     rsp, 68h
0x18000e96d  mov     rbp, r9
0x18000e970  mov     r14, r8
0x18000e973  mov     r15, rdx
0x18000e976  mov     rsi, rcx
0x18000e979  call    cs:__imp_GetLastError
0x18000e97f  mov     edi, eax
0x18000e981  call    cs:__imp_CurrentIP
0x18000e987  lea     rdx, aCrecoveryadmin_14; "CRecoveryAdminHelper::GetPointInTimeRes"...
0x18000e98e  mov     ecx, 4000000h; unsigned int
0x18000e993  mov     rbx, rax
0x18000e996  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000e99b  mov     [rsp+98h+var_48], 0
0x18000e9a3  lea     rcx, aCrecoveryadmin_4; "CRecoveryAdminHelper::GetPointInTimeRes"...
0x18000e9aa  mov     [rsp+98h+var_50], 0
0x18000e9b3  lea     r8, aD; "D"
0x18000e9ba  mov     [rsp+98h+var_58], edi
0x18000e9be  xor     r9d, r9d
0x18000e9c1  mov     [rsp+98h+var_60], rbx
0x18000e9c6  xor     edx, edx
0x18000e9c8  mov     [rsp+98h+var_68], rcx
0x18000e9cd  lea     rcx, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\recover"...
0x18000e9d4  mov     [rsp+98h+var_70], rcx
0x18000e9d9  mov     rcx, rax
0x18000e9dc  mov     [rsp+98h+var_78], 56h ; 'V'
0x18000e9e4  call    cs:__imp_WdsSetupLogMessageW
0x18000e9ea  mov     rcx, rsi; this
0x18000e9ed  call    ?GetCurrentPointInTimeRestoreHelper@CRecoveryAdminHelper@@AEAAPEAVCPointInTimeRestoreHelper@@XZ; CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(void)
0x18000e9f2  mov     r9, rbp; unsigned int *
0x18000e9f5  mov     r8, r14; int *
0x18000e9f8  mov     rdx, r15; int *
0x18000e9fb  mov     rcx, rax; this
0x18000e9fe  add     rsp, 68h
0x18000ea02  pop     r15
0x18000ea04  pop     r14
0x18000ea06  pop     rdi
0x18000ea07  pop     rsi
0x18000ea08  pop     rbp
0x18000ea09  pop     rbx
0x18000ea0a  jmp     ?GetPointInTimeRestoreSnapshotRetention@CPointInTimeRestoreHelper@@QEAAJPEAH0PEAK@Z; CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotRetention(int *,int *,ulong *)
```
