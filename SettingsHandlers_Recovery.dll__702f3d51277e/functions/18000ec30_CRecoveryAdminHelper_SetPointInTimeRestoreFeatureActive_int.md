# CRecoveryAdminHelper::SetPointInTimeRestoreFeatureActive(int)

- ea: `0x18000ec30`
- end: `0x18000eccc`
- name: `?SetPointInTimeRestoreFeatureActive@CRecoveryAdminHelper@@UEAAJH@Z`
- size: `156`
- prototype: `__int64 __fastcall(CRecoveryAdminHelper *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000bef4`
- `0x18000d36c`
- `0x18000e110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec3e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ecac`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ecac`
- `WDSCORE!CurrentIP` at `0x18000ec46`
- `WDSCORE!CurrentIP` at `0x18000ec46`

## string_xrefs

- `0x18000ec95`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecoveryAdminHelper::SetPointInTimeRestoreFeatureActive(CRecoveryAdminHelper *this, int a2)
{
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  CPointInTimeRestoreHelper *CurrentPointInTimeRestoreHelper; // rax

  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = ConstructPartialMsgW(
         0x4000000u,
         "CRecoveryAdminHelper::SetPointInTimeRestoreFeatureActive: setting PITR feature active to %d",
         a2);
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    52,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
    L"CRecoveryAdminHelper::SetPointInTimeRestoreFeatureActive",
    v5,
    LastError,
    0,
    0);
  CurrentPointInTimeRestoreHelper = CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(this);
  return CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive(CurrentPointInTimeRestoreHelper, a2);
}

```

## disassembly

```asm
0x18000ec30  push    rbx
0x18000ec32  push    rbp
0x18000ec33  push    rsi
0x18000ec34  push    rdi
0x18000ec35  sub     rsp, 68h
0x18000ec39  mov     ebp, edx
0x18000ec3b  mov     rsi, rcx
0x18000ec3e  call    cs:__imp_GetLastError
0x18000ec44  mov     edi, eax
0x18000ec46  call    cs:__imp_CurrentIP
0x18000ec4c  mov     r8d, ebp
0x18000ec4f  lea     rdx, aCrecoveryadmin_25; "CRecoveryAdminHelper::SetPointInTimeRes"...
0x18000ec56  mov     ecx, 4000000h; unsigned int
0x18000ec5b  mov     rbx, rax
0x18000ec5e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ec63  mov     [rsp+88h+var_38], 0
0x18000ec6b  lea     rcx, aCrecoveryadmin_7; "CRecoveryAdminHelper::SetPointInTimeRes"...
0x18000ec72  mov     [rsp+88h+var_40], 0
0x18000ec7b  lea     r8, aD; "D"
0x18000ec82  mov     [rsp+88h+var_48], edi
0x18000ec86  xor     r9d, r9d
0x18000ec89  mov     [rsp+88h+var_50], rbx
0x18000ec8e  xor     edx, edx
0x18000ec90  mov     [rsp+88h+var_58], rcx
0x18000ec95  lea     rcx, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\recover"...
0x18000ec9c  mov     [rsp+88h+var_60], rcx
0x18000eca1  mov     rcx, rax
0x18000eca4  mov     [rsp+88h+var_68], 34h ; '4'
0x18000ecac  call    cs:__imp_WdsSetupLogMessageW
0x18000ecb2  mov     rcx, rsi; this
0x18000ecb5  call    ?GetCurrentPointInTimeRestoreHelper@CRecoveryAdminHelper@@AEAAPEAVCPointInTimeRestoreHelper@@XZ; CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(void)
0x18000ecba  mov     edx, ebp; int
0x18000ecbc  mov     rcx, rax; this
0x18000ecbf  add     rsp, 68h
0x18000ecc3  pop     rdi
0x18000ecc4  pop     rsi
0x18000ecc5  pop     rbp
0x18000ecc6  pop     rbx
0x18000ecc7  jmp     ?SetPointInTimeRestoreFeatureActive@CPointInTimeRestoreHelper@@QEAAJH@Z; CPointInTimeRestoreHelper::SetPointInTimeRestoreFeatureActive(int)
```
