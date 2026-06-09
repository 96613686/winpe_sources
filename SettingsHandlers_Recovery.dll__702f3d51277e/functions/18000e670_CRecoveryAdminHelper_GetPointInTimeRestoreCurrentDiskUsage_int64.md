# CRecoveryAdminHelper::GetPointInTimeRestoreCurrentDiskUsage(__int64 *)

- ea: `0x18000e670`
- end: `0x18000e70b`
- name: `?GetPointInTimeRestoreCurrentDiskUsage@CRecoveryAdminHelper@@UEAAJPEA_J@Z`
- size: `155`
- prototype: `__int64 __fastcall(CRecoveryAdminHelper *__hidden this, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000bef4`
- `0x18000c0a4`
- `0x18000e110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e67f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e67f`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e6ea`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e6ea`
- `WDSCORE!CurrentIP` at `0x18000e687`
- `WDSCORE!CurrentIP` at `0x18000e687`

## string_xrefs

- `0x18000e6d3`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`

## pseudocode

```c
__int64 __fastcall CRecoveryAdminHelper::GetPointInTimeRestoreCurrentDiskUsage(CRecoveryAdminHelper *this, __int64 *a2)
{
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  CPointInTimeRestoreHelper *CurrentPointInTimeRestoreHelper; // rax

  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = ConstructPartialMsgW(
         0x4000000u,
         "CRecoveryAdminHelper::GetPointInTimeRestoreCurrentDiskUsage: getting current disk usage");
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    130,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
    L"CRecoveryAdminHelper::GetPointInTimeRestoreCurrentDiskUsage",
    v5,
    LastError,
    0,
    0);
  CurrentPointInTimeRestoreHelper = CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(this);
  return CPointInTimeRestoreHelper::GetPointInTimeRestoreCurrentDiskUsage(CurrentPointInTimeRestoreHelper, a2);
}

```

## disassembly

```asm
0x18000e670  push    rbx
0x18000e672  push    rbp
0x18000e673  push    rsi
0x18000e674  push    rdi
0x18000e675  sub     rsp, 68h
0x18000e679  mov     rbp, rdx
0x18000e67c  mov     rsi, rcx
0x18000e67f  call    cs:__imp_GetLastError
0x18000e685  mov     edi, eax
0x18000e687  call    cs:__imp_CurrentIP
0x18000e68d  lea     rdx, aCrecoveryadmin_29; "CRecoveryAdminHelper::GetPointInTimeRes"...
0x18000e694  mov     ecx, 4000000h; unsigned int
0x18000e699  mov     rbx, rax
0x18000e69c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000e6a1  mov     [rsp+88h+var_38], 0
0x18000e6a9  lea     rcx, aCrecoveryadmin_2; "CRecoveryAdminHelper::GetPointInTimeRes"...
0x18000e6b0  mov     [rsp+88h+var_40], 0
0x18000e6b9  lea     r8, aD; "D"
0x18000e6c0  mov     [rsp+88h+var_48], edi
0x18000e6c4  xor     r9d, r9d
0x18000e6c7  mov     [rsp+88h+var_50], rbx
0x18000e6cc  xor     edx, edx
0x18000e6ce  mov     [rsp+88h+var_58], rcx
0x18000e6d3  lea     rcx, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\recover"...
0x18000e6da  mov     [rsp+88h+var_60], rcx
0x18000e6df  mov     rcx, rax
0x18000e6e2  mov     [rsp+88h+var_68], 82h
0x18000e6ea  call    cs:__imp_WdsSetupLogMessageW
0x18000e6f0  mov     rcx, rsi; this
0x18000e6f3  call    ?GetCurrentPointInTimeRestoreHelper@CRecoveryAdminHelper@@AEAAPEAVCPointInTimeRestoreHelper@@XZ; CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(void)
0x18000e6f8  mov     rdx, rbp; __int64 *
0x18000e6fb  mov     rcx, rax; this
0x18000e6fe  add     rsp, 68h
0x18000e702  pop     rdi
0x18000e703  pop     rsi
0x18000e704  pop     rbp
0x18000e705  pop     rbx
0x18000e706  jmp     ?GetPointInTimeRestoreCurrentDiskUsage@CPointInTimeRestoreHelper@@QEAAJPEA_J@Z; CPointInTimeRestoreHelper::GetPointInTimeRestoreCurrentDiskUsage(__int64 *)
```
