# CRecoveryAdminHelper::GetPointInTimeRestoreFeatureActive(int *,int *,int *)

- ea: `0x18000e720`
- end: `0x18000e7cf`
- name: `?GetPointInTimeRestoreFeatureActive@CRecoveryAdminHelper@@UEAAJPEAH00@Z`
- size: `175`
- prototype: `__int64 __fastcall(CRecoveryAdminHelper *__hidden this, int *, int *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000bef4`
- `0x18000c2f0`
- `0x18000e110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e739`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e7a4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e7a4`
- `WDSCORE!CurrentIP` at `0x18000e741`
- `WDSCORE!CurrentIP` at `0x18000e741`

## string_xrefs

- `0x18000e78d`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`

## pseudocode

```c
__int64 __fastcall CRecoveryAdminHelper::GetPointInTimeRestoreFeatureActive(
        CRecoveryAdminHelper *this,
        int *a2,
        int *a3,
        int *a4)
{
  DWORD LastError; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  CPointInTimeRestoreHelper *CurrentPointInTimeRestoreHelper; // rax

  LastError = GetLastError();
  v9 = CurrentIP();
  v10 = ConstructPartialMsgW(
          0x4000000u,
          "CRecoveryAdminHelper::GetPointInTimeRestoreFeatureActive: getting PITR feature active");
  WdsSetupLogMessageW(
    v10,
    0,
    L"D",
    0,
    40,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
    L"CRecoveryAdminHelper::GetPointInTimeRestoreFeatureActive",
    v9,
    LastError,
    0,
    0);
  CurrentPointInTimeRestoreHelper = CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(this);
  return CPointInTimeRestoreHelper::GetPointInTimeRestoreFeatureActive(CurrentPointInTimeRestoreHelper, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e720  push    rbx
0x18000e722  push    rbp
0x18000e723  push    rsi
0x18000e724  push    rdi
0x18000e725  push    r14
0x18000e727  push    r15
0x18000e729  sub     rsp, 68h
0x18000e72d  mov     rbp, r9
0x18000e730  mov     r14, r8
0x18000e733  mov     r15, rdx
0x18000e736  mov     rsi, rcx
0x18000e739  call    cs:__imp_GetLastError
0x18000e73f  mov     edi, eax
0x18000e741  call    cs:__imp_CurrentIP
0x18000e747  lea     rdx, aCrecoveryadmin_6; "CRecoveryAdminHelper::GetPointInTimeRes"...
0x18000e74e  mov     ecx, 4000000h; unsigned int
0x18000e753  mov     rbx, rax
0x18000e756  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000e75b  mov     [rsp+98h+var_48], 0
0x18000e763  lea     rcx, aCrecoveryadmin_19; "CRecoveryAdminHelper::GetPointInTimeRes"...
0x18000e76a  mov     [rsp+98h+var_50], 0
0x18000e773  lea     r8, aD; "D"
0x18000e77a  mov     [rsp+98h+var_58], edi
0x18000e77e  xor     r9d, r9d
0x18000e781  mov     [rsp+98h+var_60], rbx
0x18000e786  xor     edx, edx
0x18000e788  mov     [rsp+98h+var_68], rcx
0x18000e78d  lea     rcx, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\recover"...
0x18000e794  mov     [rsp+98h+var_70], rcx
0x18000e799  mov     rcx, rax
0x18000e79c  mov     [rsp+98h+var_78], 28h ; '('
0x18000e7a4  call    cs:__imp_WdsSetupLogMessageW
0x18000e7aa  mov     rcx, rsi; this
0x18000e7ad  call    ?GetCurrentPointInTimeRestoreHelper@CRecoveryAdminHelper@@AEAAPEAVCPointInTimeRestoreHelper@@XZ; CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(void)
0x18000e7b2  mov     r9, rbp; int *
0x18000e7b5  mov     r8, r14; int *
0x18000e7b8  mov     rdx, r15; int *
0x18000e7bb  mov     rcx, rax; this
0x18000e7be  add     rsp, 68h
0x18000e7c2  pop     r15
0x18000e7c4  pop     r14
0x18000e7c6  pop     rdi
0x18000e7c7  pop     rsi
0x18000e7c8  pop     rbp
0x18000e7c9  pop     rbx
0x18000e7ca  jmp     ?GetPointInTimeRestoreFeatureActive@CPointInTimeRestoreHelper@@QEAAJPEAH00@Z; CPointInTimeRestoreHelper::GetPointInTimeRestoreFeatureActive(int *,int *,int *)
```
