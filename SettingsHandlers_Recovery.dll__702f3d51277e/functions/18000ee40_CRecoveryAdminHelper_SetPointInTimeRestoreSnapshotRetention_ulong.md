# CRecoveryAdminHelper::SetPointInTimeRestoreSnapshotRetention(ulong)

- ea: `0x18000ee40`
- end: `0x18000eedc`
- name: `?SetPointInTimeRestoreSnapshotRetention@CRecoveryAdminHelper@@UEAAJK@Z`
- size: `156`
- prototype: `__int64 __fastcall(CRecoveryAdminHelper *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000bef4`
- `0x18000da8c`
- `0x18000e110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee4e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000eebc`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000eebc`
- `WDSCORE!CurrentIP` at `0x18000ee56`
- `WDSCORE!CurrentIP` at `0x18000ee56`

## string_xrefs

- `0x18000eea5`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecoveryAdminHelper::SetPointInTimeRestoreSnapshotRetention(
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
         "CRecoveryAdminHelper::SetPointInTimeRestoreSnapshotRetention: setting PITR snapshot retention to %u minutes",
         a2);
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    98,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
    L"CRecoveryAdminHelper::SetPointInTimeRestoreSnapshotRetention",
    v5,
    LastError,
    0,
    0);
  CurrentPointInTimeRestoreHelper = CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(this);
  return CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention(CurrentPointInTimeRestoreHelper, a2);
}

```

## disassembly

```asm
0x18000ee40  push    rbx
0x18000ee42  push    rbp
0x18000ee43  push    rsi
0x18000ee44  push    rdi
0x18000ee45  sub     rsp, 68h
0x18000ee49  mov     ebp, edx
0x18000ee4b  mov     rsi, rcx
0x18000ee4e  call    cs:__imp_GetLastError
0x18000ee54  mov     edi, eax
0x18000ee56  call    cs:__imp_CurrentIP
0x18000ee5c  mov     r8d, ebp
0x18000ee5f  lea     rdx, aCrecoveryadmin_22; "CRecoveryAdminHelper::SetPointInTimeRes"...
0x18000ee66  mov     ecx, 4000000h; unsigned int
0x18000ee6b  mov     rbx, rax
0x18000ee6e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ee73  mov     [rsp+88h+var_38], 0
0x18000ee7b  lea     rcx, aCrecoveryadmin_21; "CRecoveryAdminHelper::SetPointInTimeRes"...
0x18000ee82  mov     [rsp+88h+var_40], 0
0x18000ee8b  lea     r8, aD; "D"
0x18000ee92  mov     [rsp+88h+var_48], edi
0x18000ee96  xor     r9d, r9d
0x18000ee99  mov     [rsp+88h+var_50], rbx
0x18000ee9e  xor     edx, edx
0x18000eea0  mov     [rsp+88h+var_58], rcx
0x18000eea5  lea     rcx, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\recover"...
0x18000eeac  mov     [rsp+88h+var_60], rcx
0x18000eeb1  mov     rcx, rax
0x18000eeb4  mov     [rsp+88h+var_68], 62h ; 'b'
0x18000eebc  call    cs:__imp_WdsSetupLogMessageW
0x18000eec2  mov     rcx, rsi; this
0x18000eec5  call    ?GetCurrentPointInTimeRestoreHelper@CRecoveryAdminHelper@@AEAAPEAVCPointInTimeRestoreHelper@@XZ; CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(void)
0x18000eeca  mov     edx, ebp; unsigned int
0x18000eecc  mov     rcx, rax; this
0x18000eecf  add     rsp, 68h
0x18000eed3  pop     rdi
0x18000eed4  pop     rsi
0x18000eed5  pop     rbp
0x18000eed6  pop     rbx
0x18000eed7  jmp     ?SetPointInTimeRestoreSnapshotRetention@CPointInTimeRestoreHelper@@QEAAJK@Z; CPointInTimeRestoreHelper::SetPointInTimeRestoreSnapshotRetention(ulong)
```
