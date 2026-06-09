# CRecoveryAdminHelper::GetPointInTimeRestoreMaxDiskUsage(int *,int *,ulong *)

- ea: `0x18000e7e0`
- end: `0x18000e88f`
- name: `?GetPointInTimeRestoreMaxDiskUsage@CRecoveryAdminHelper@@UEAAJPEAH0PEAK@Z`
- size: `175`
- prototype: `__int64 __fastcall(CRecoveryAdminHelper *__hidden this, int *, int *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000bef4`
- `0x18000c550`
- `0x18000e110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7f9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e864`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000e864`
- `WDSCORE!CurrentIP` at `0x18000e801`
- `WDSCORE!CurrentIP` at `0x18000e801`

## string_xrefs

- `0x18000e84d`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`

## pseudocode

```c
__int64 __fastcall CRecoveryAdminHelper::GetPointInTimeRestoreMaxDiskUsage(
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
          "CRecoveryAdminHelper::GetPointInTimeRestoreMaxDiskUsage: getting PITR max disk usage");
  WdsSetupLogMessageW(
    v10,
    0,
    L"D",
    0,
    109,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
    L"CRecoveryAdminHelper::GetPointInTimeRestoreMaxDiskUsage",
    v9,
    LastError,
    0,
    0);
  CurrentPointInTimeRestoreHelper = CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(this);
  return CPointInTimeRestoreHelper::GetPointInTimeRestoreMaxDiskUsage(CurrentPointInTimeRestoreHelper, a2, a3, a4);
}

```

## disassembly

```asm
0x18000e7e0  push    rbx
0x18000e7e2  push    rbp
0x18000e7e3  push    rsi
0x18000e7e4  push    rdi
0x18000e7e5  push    r14
0x18000e7e7  push    r15
0x18000e7e9  sub     rsp, 68h
0x18000e7ed  mov     rbp, r9
0x18000e7f0  mov     r14, r8
0x18000e7f3  mov     r15, rdx
0x18000e7f6  mov     rsi, rcx
0x18000e7f9  call    cs:__imp_GetLastError
0x18000e7ff  mov     edi, eax
0x18000e801  call    cs:__imp_CurrentIP
0x18000e807  lea     rdx, aCrecoveryadmin_23; "CRecoveryAdminHelper::GetPointInTimeRes"...
0x18000e80e  mov     ecx, 4000000h; unsigned int
0x18000e813  mov     rbx, rax
0x18000e816  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000e81b  mov     [rsp+98h+var_48], 0
0x18000e823  lea     rcx, aCrecoveryadmin_16; "CRecoveryAdminHelper::GetPointInTimeRes"...
0x18000e82a  mov     [rsp+98h+var_50], 0
0x18000e833  lea     r8, aD; "D"
0x18000e83a  mov     [rsp+98h+var_58], edi
0x18000e83e  xor     r9d, r9d
0x18000e841  mov     [rsp+98h+var_60], rbx
0x18000e846  xor     edx, edx
0x18000e848  mov     [rsp+98h+var_68], rcx
0x18000e84d  lea     rcx, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\recover"...
0x18000e854  mov     [rsp+98h+var_70], rcx
0x18000e859  mov     rcx, rax
0x18000e85c  mov     [rsp+98h+var_78], 6Dh ; 'm'
0x18000e864  call    cs:__imp_WdsSetupLogMessageW
0x18000e86a  mov     rcx, rsi; this
0x18000e86d  call    ?GetCurrentPointInTimeRestoreHelper@CRecoveryAdminHelper@@AEAAPEAVCPointInTimeRestoreHelper@@XZ; CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(void)
0x18000e872  mov     r9, rbp; unsigned int *
0x18000e875  mov     r8, r14; int *
0x18000e878  mov     rdx, r15; int *
0x18000e87b  mov     rcx, rax; this
0x18000e87e  add     rsp, 68h
0x18000e882  pop     r15
0x18000e884  pop     r14
0x18000e886  pop     rdi
0x18000e887  pop     rsi
0x18000e888  pop     rbp
0x18000e889  pop     rbx
0x18000e88a  jmp     ?GetPointInTimeRestoreMaxDiskUsage@CPointInTimeRestoreHelper@@QEAAJPEAH0PEAK@Z; CPointInTimeRestoreHelper::GetPointInTimeRestoreMaxDiskUsage(int *,int *,ulong *)
```
