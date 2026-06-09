# CRecoveryAdminHelper::GetPointInTimeRestoreSnapshotCadence(int *,int *,ulong *)

- ea: `0x18000e8a0`
- end: `0x18000e94f`
- name: `?GetPointInTimeRestoreSnapshotCadence@CRecoveryAdminHelper@@UEAAJPEAH0PEAK@Z`
- size: `175`
- prototype: `__int64 __fastcall(CRecoveryAdminHelper *__hidden this, int *, int *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000bef4`
- `0x18000c7b8`
- `0x18000e110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e8b9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e924`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e924`
- `WDSCORE!CurrentIP` at `0x18000e8c1`
- `WDSCORE!CurrentIP` at `0x18000e8c1`

## string_xrefs

- `0x18000e90d`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`

## pseudocode

```c
__int64 __fastcall CRecoveryAdminHelper::GetPointInTimeRestoreSnapshotCadence(
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
          "CRecoveryAdminHelper::GetPointInTimeRestoreSnapshotCadence: getting PITR snapshot cadence");
  WdsSetupLogMessageW(
    v10,
    0,
    L"D",
    0,
    63,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
    L"CRecoveryAdminHelper::GetPointInTimeRestoreSnapshotCadence",
    v9,
    LastError,
    0,
    0);
  CurrentPointInTimeRestoreHelper = CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(this);
  return CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotCadence(CurrentPointInTimeRestoreHelper, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e8a0  push    rbx
0x18000e8a2  push    rbp
0x18000e8a3  push    rsi
0x18000e8a4  push    rdi
0x18000e8a5  push    r14
0x18000e8a7  push    r15
0x18000e8a9  sub     rsp, 68h
0x18000e8ad  mov     rbp, r9
0x18000e8b0  mov     r14, r8
0x18000e8b3  mov     r15, rdx
0x18000e8b6  mov     rsi, rcx
0x18000e8b9  call    cs:__imp_GetLastError
0x18000e8bf  mov     edi, eax
0x18000e8c1  call    cs:__imp_CurrentIP
0x18000e8c7  lea     rdx, aCrecoveryadmin_12; "CRecoveryAdminHelper::GetPointInTimeRes"...
0x18000e8ce  mov     ecx, 4000000h; unsigned int
0x18000e8d3  mov     rbx, rax
0x18000e8d6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000e8db  mov     [rsp+98h+var_48], 0
0x18000e8e3  lea     rcx, aCrecoveryadmin_3; "CRecoveryAdminHelper::GetPointInTimeRes"...
0x18000e8ea  mov     [rsp+98h+var_50], 0
0x18000e8f3  lea     r8, aD; "D"
0x18000e8fa  mov     [rsp+98h+var_58], edi
0x18000e8fe  xor     r9d, r9d
0x18000e901  mov     [rsp+98h+var_60], rbx
0x18000e906  xor     edx, edx
0x18000e908  mov     [rsp+98h+var_68], rcx
0x18000e90d  lea     rcx, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\recover"...
0x18000e914  mov     [rsp+98h+var_70], rcx
0x18000e919  mov     rcx, rax
0x18000e91c  mov     [rsp+98h+var_78], 3Fh ; '?'
0x18000e924  call    cs:__imp_WdsSetupLogMessageW
0x18000e92a  mov     rcx, rsi; this
0x18000e92d  call    ?GetCurrentPointInTimeRestoreHelper@CRecoveryAdminHelper@@AEAAPEAVCPointInTimeRestoreHelper@@XZ; CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(void)
0x18000e932  mov     r9, rbp; unsigned int *
0x18000e935  mov     r8, r14; int *
0x18000e938  mov     rdx, r15; int *
0x18000e93b  mov     rcx, rax; this
0x18000e93e  add     rsp, 68h
0x18000e942  pop     r15
0x18000e944  pop     r14
0x18000e946  pop     rdi
0x18000e947  pop     rsi
0x18000e948  pop     rbp
0x18000e949  pop     rbx
0x18000e94a  jmp     ?GetPointInTimeRestoreSnapshotCadence@CPointInTimeRestoreHelper@@QEAAJPEAH0PEAK@Z; CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshotCadence(int *,int *,ulong *)
```
