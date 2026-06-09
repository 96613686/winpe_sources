# CRecoveryAdminHelper::SetPointInTimeRestoreMaxDiskUsage(ulong)

- ea: `0x18000ece0`
- end: `0x18000ed7c`
- name: `?SetPointInTimeRestoreMaxDiskUsage@CRecoveryAdminHelper@@UEAAJK@Z`
- size: `156`
- prototype: `__int64 __fastcall(CRecoveryAdminHelper *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000bef4`
- `0x18000d5cc`
- `0x18000e110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecee`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ed5c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ed5c`
- `WDSCORE!CurrentIP` at `0x18000ecf6`
- `WDSCORE!CurrentIP` at `0x18000ecf6`

## string_xrefs

- `0x18000ed45`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecoveryAdminHelper::SetPointInTimeRestoreMaxDiskUsage(CRecoveryAdminHelper *this, unsigned int a2)
{
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  CPointInTimeRestoreHelper *CurrentPointInTimeRestoreHelper; // rax

  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = ConstructPartialMsgW(
         0x4000000u,
         "CRecoveryAdminHelper::SetPointInTimeRestoreMaxDiskUsage: setting PITR max disk usage to %u MB",
         a2);
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    121,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
    L"CRecoveryAdminHelper::SetPointInTimeRestoreMaxDiskUsage",
    v5,
    LastError,
    0,
    0);
  CurrentPointInTimeRestoreHelper = CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(this);
  return CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage(CurrentPointInTimeRestoreHelper, a2);
}

```

## disassembly

```asm
0x18000ece0  push    rbx
0x18000ece2  push    rbp
0x18000ece3  push    rsi
0x18000ece4  push    rdi
0x18000ece5  sub     rsp, 68h
0x18000ece9  mov     ebp, edx
0x18000eceb  mov     rsi, rcx
0x18000ecee  call    cs:__imp_GetLastError
0x18000ecf4  mov     edi, eax
0x18000ecf6  call    cs:__imp_CurrentIP
0x18000ecfc  mov     r8d, ebp
0x18000ecff  lea     rdx, aCrecoveryadmin_18; "CRecoveryAdminHelper::SetPointInTimeRes"...
0x18000ed06  mov     ecx, 4000000h; unsigned int
0x18000ed0b  mov     rbx, rax
0x18000ed0e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ed13  mov     [rsp+88h+var_38], 0
0x18000ed1b  lea     rcx, aCrecoveryadmin_5; "CRecoveryAdminHelper::SetPointInTimeRes"...
0x18000ed22  mov     [rsp+88h+var_40], 0
0x18000ed2b  lea     r8, aD; "D"
0x18000ed32  mov     [rsp+88h+var_48], edi
0x18000ed36  xor     r9d, r9d
0x18000ed39  mov     [rsp+88h+var_50], rbx
0x18000ed3e  xor     edx, edx
0x18000ed40  mov     [rsp+88h+var_58], rcx
0x18000ed45  lea     rcx, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\recover"...
0x18000ed4c  mov     [rsp+88h+var_60], rcx
0x18000ed51  mov     rcx, rax
0x18000ed54  mov     [rsp+88h+var_68], 79h ; 'y'
0x18000ed5c  call    cs:__imp_WdsSetupLogMessageW
0x18000ed62  mov     rcx, rsi; this
0x18000ed65  call    ?GetCurrentPointInTimeRestoreHelper@CRecoveryAdminHelper@@AEAAPEAVCPointInTimeRestoreHelper@@XZ; CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(void)
0x18000ed6a  mov     edx, ebp; unsigned int
0x18000ed6c  mov     rcx, rax; this
0x18000ed6f  add     rsp, 68h
0x18000ed73  pop     rdi
0x18000ed74  pop     rsi
0x18000ed75  pop     rbp
0x18000ed76  pop     rbx
0x18000ed77  jmp     ?SetPointInTimeRestoreMaxDiskUsage@CPointInTimeRestoreHelper@@QEAAJK@Z; CPointInTimeRestoreHelper::SetPointInTimeRestoreMaxDiskUsage(ulong)
```
