# CRecoveryAdminHelper::SetPointInTimeRestoreSnapshotCadence(ulong)

- ea: `0x18000ed90`
- end: `0x18000ee2c`
- name: `?SetPointInTimeRestoreSnapshotCadence@CRecoveryAdminHelper@@UEAAJK@Z`
- size: `156`
- prototype: `__int64 __fastcall(CRecoveryAdminHelper *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000bef4`
- `0x18000d82c`
- `0x18000e110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed9e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ee0c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ee0c`
- `WDSCORE!CurrentIP` at `0x18000eda6`
- `WDSCORE!CurrentIP` at `0x18000eda6`

## string_xrefs

- `0x18000edf5`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecoveryAdminHelper::SetPointInTimeRestoreSnapshotCadence(
        CRecoveryAdminHelper *this,
        unsigned int a2)
{
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  CPointInTimeRestoreHelper *CurrentPointInTimeRestoreHelper; // rax

  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = ConstructPartialMsgW(
         0x4000000u,
         "CRecoveryAdminHelper::SetPointInTimeRestoreSnapshotCadence: setting PITR snapshot cadence to %u minutes",
         a2);
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    75,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
    L"CRecoveryAdminHelper::SetPointInTimeRestoreSnapshotCadence",
    v5,
    LastError,
    0,
    0);
  CurrentPointInTimeRestoreHelper = CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(this);
  return CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence(CurrentPointInTimeRestoreHelper, a2);
}

```

## disassembly

```asm
0x18000ed90  push    rbx
0x18000ed92  push    rbp
0x18000ed93  push    rsi
0x18000ed94  push    rdi
0x18000ed95  sub     rsp, 68h
0x18000ed99  mov     ebp, edx
0x18000ed9b  mov     rsi, rcx
0x18000ed9e  call    cs:__imp_GetLastError
0x18000eda4  mov     edi, eax
0x18000eda6  call    cs:__imp_CurrentIP
0x18000edac  mov     r8d, ebp
0x18000edaf  lea     rdx, aCrecoveryadmin_9; "CRecoveryAdminHelper::SetPointInTimeRes"...
0x18000edb6  mov     ecx, 4000000h; unsigned int
0x18000edbb  mov     rbx, rax
0x18000edbe  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000edc3  mov     [rsp+88h+var_38], 0
0x18000edcb  lea     rcx, aCrecoveryadmin_15; "CRecoveryAdminHelper::SetPointInTimeRes"...
0x18000edd2  mov     [rsp+88h+var_40], 0
0x18000eddb  lea     r8, aD; "D"
0x18000ede2  mov     [rsp+88h+var_48], edi
0x18000ede6  xor     r9d, r9d
0x18000ede9  mov     [rsp+88h+var_50], rbx
0x18000edee  xor     edx, edx
0x18000edf0  mov     [rsp+88h+var_58], rcx
0x18000edf5  lea     rcx, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\recover"...
0x18000edfc  mov     [rsp+88h+var_60], rcx
0x18000ee01  mov     rcx, rax
0x18000ee04  mov     [rsp+88h+var_68], 4Bh ; 'K'
0x18000ee0c  call    cs:__imp_WdsSetupLogMessageW
0x18000ee12  mov     rcx, rsi; this
0x18000ee15  call    ?GetCurrentPointInTimeRestoreHelper@CRecoveryAdminHelper@@AEAAPEAVCPointInTimeRestoreHelper@@XZ; CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(void)
0x18000ee1a  mov     edx, ebp; unsigned int
0x18000ee1c  mov     rcx, rax; this
0x18000ee1f  add     rsp, 68h
0x18000ee23  pop     rdi
0x18000ee24  pop     rsi
0x18000ee25  pop     rbp
0x18000ee26  pop     rbx
0x18000ee27  jmp     ?SetPointInTimeRestoreSnapshotCadence@CPointInTimeRestoreHelper@@QEAAJK@Z; CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotCadence(ulong)
```
