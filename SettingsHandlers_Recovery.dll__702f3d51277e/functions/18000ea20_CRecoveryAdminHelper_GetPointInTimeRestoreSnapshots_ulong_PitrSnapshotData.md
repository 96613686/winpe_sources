# CRecoveryAdminHelper::GetPointInTimeRestoreSnapshots(ulong *,_PitrSnapshotData * *)

- ea: `0x18000ea20`
- end: `0x18000eb3a`
- name: `?GetPointInTimeRestoreSnapshots@CRecoveryAdminHelper@@UEAAJPEAKPEAPEAU_PitrSnapshotData@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(CRecoveryAdminHelper *__hidden this, unsigned int *, struct _PitrSnapshotData **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000b784`
- `0x18000bef4`
- `0x18000cc80`
- `0x18000e110`
- `0x18000ea20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea3c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000eaa7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000eaa7`
- `WDSCORE!CurrentIP` at `0x18000ea44`
- `WDSCORE!CurrentIP` at `0x18000ea44`

## string_xrefs

- `0x18000ea90`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`
- `0x18000eafb`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`

## pseudocode

```c
__int64 __fastcall CRecoveryAdminHelper::GetPointInTimeRestoreSnapshots(
        CRecoveryAdminHelper *this,
        unsigned int *a2,
        struct _PitrSnapshotData **a3)
{
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  CPointInTimeRestoreHelper *CurrentPointInTimeRestoreHelper; // rax
  int PointInTimeRestoreSnapshots; // ebx
  char *v12; // [rsp+28h] [rbp-60h]
  struct _PitrSnapshotData *v13; // [rsp+60h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int v15; // [rsp+A8h] [rbp+20h] BYREF

  LastError = GetLastError();
  v7 = CurrentIP();
  v8 = ConstructPartialMsgW(
         0x4000000u,
         "CRecoveryAdminHelper::GetPointInTimeRestoreSnapshots: getting all current snapshots");
  WdsSetupLogMessageW(
    v8,
    0,
    L"D",
    0,
    140,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
    L"CRecoveryAdminHelper::GetPointInTimeRestoreSnapshots",
    v7,
    LastError,
    0,
    0);
  v15 = 0;
  v13 = 0;
  CurrentPointInTimeRestoreHelper = CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(this);
  PointInTimeRestoreSnapshots = CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots(
                                  CurrentPointInTimeRestoreHelper,
                                  &v15,
                                  &v13);
  if ( PointInTimeRestoreSnapshots >= 0 )
  {
    *a2 = v15;
    *a3 = v13;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x90,
      (unsigned int)"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
      (const char *)(unsigned int)PointInTimeRestoreSnapshots,
      (int)"Failed to get PITR snapshots",
      v12);
    return (unsigned int)PointInTimeRestoreSnapshots;
  }
}

```

## disassembly

```asm
0x18000ea20  mov     [rsp+arg_0], rbx
0x18000ea25  mov     [rsp+arg_8], rsi
0x18000ea2a  push    rdi
0x18000ea2b  push    r14
0x18000ea2d  push    r15
0x18000ea2f  sub     rsp, 70h
0x18000ea33  mov     r14, r8
0x18000ea36  mov     r15, rdx
0x18000ea39  mov     rsi, rcx
0x18000ea3c  call    cs:__imp_GetLastError
0x18000ea42  mov     edi, eax
0x18000ea44  call    cs:__imp_CurrentIP
0x18000ea4a  lea     rdx, aCrecoveryadmin_28; "CRecoveryAdminHelper::GetPointInTimeRes"...
0x18000ea51  mov     ecx, 4000000h; unsigned int
0x18000ea56  mov     rbx, rax
0x18000ea59  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ea5e  mov     [rsp+88h+var_38], 0
0x18000ea66  lea     rcx, aCrecoveryadmin_20; "CRecoveryAdminHelper::GetPointInTimeRes"...
0x18000ea6d  mov     [rsp+88h+var_40], 0
0x18000ea76  lea     r8, aD; "D"
0x18000ea7d  mov     [rsp+88h+var_48], edi
0x18000ea81  xor     r9d, r9d
0x18000ea84  mov     [rsp+88h+var_50], rbx
0x18000ea89  xor     edx, edx
0x18000ea8b  mov     [rsp+88h+var_58], rcx
0x18000ea90  lea     rcx, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\recover"...
0x18000ea97  mov     [rsp+88h+var_60], rcx; char *
0x18000ea9c  mov     rcx, rax
0x18000ea9f  mov     [rsp+88h+var_68], 8Ch
0x18000eaa7  call    cs:__imp_WdsSetupLogMessageW
0x18000eaad  mov     rcx, rsi; this
0x18000eab0  mov     [rsp+88h+arg_18], 0
0x18000eabb  mov     [rsp+88h+var_28], 0
0x18000eac4  call    ?GetCurrentPointInTimeRestoreHelper@CRecoveryAdminHelper@@AEAAPEAVCPointInTimeRestoreHelper@@XZ; CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(void)
0x18000eac9  lea     r8, [rsp+88h+var_28]; struct _PitrSnapshotData **
0x18000eace  mov     rcx, rax; this
0x18000ead1  lea     rdx, [rsp+88h+arg_18]; unsigned int *
0x18000ead9  call    ?GetPointInTimeRestoreSnapshots@CPointInTimeRestoreHelper@@QEAAJPEAKPEAPEAU_PitrSnapshotData@@@Z; CPointInTimeRestoreHelper::GetPointInTimeRestoreSnapshots(ulong *,_PitrSnapshotData * *)
0x18000eade  mov     ebx, eax
0x18000eae0  test    eax, eax
0x18000eae2  jns     short loc_18000EB10
0x18000eae4  mov     rcx, [rsp+88h]; this
0x18000eaec  lea     rax, aFailedToGetPit; "Failed to get PITR snapshots"
0x18000eaf3  mov     r9d, ebx; char *
0x18000eaf6  mov     qword ptr [rsp+88h+var_68], rax; int
0x18000eafb  lea     r8, aPcshellShellSy_5; "pcshell\\shell\\systemsettings\\recover"...
0x18000eb02  mov     edx, 90h; void *
0x18000eb07  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000eb0c  mov     eax, ebx
0x18000eb0e  jmp     short loc_18000EB24
0x18000eb10  mov     eax, [rsp+88h+arg_18]
0x18000eb17  mov     [r15], eax
0x18000eb1a  mov     rax, [rsp+88h+var_28]
0x18000eb1f  mov     [r14], rax
0x18000eb22  xor     eax, eax
0x18000eb24  lea     r11, [rsp+88h+var_18]
0x18000eb29  mov     rbx, [r11+20h]
0x18000eb2d  mov     rsi, [r11+28h]
0x18000eb31  mov     rsp, r11
0x18000eb34  pop     r15
0x18000eb36  pop     r14
0x18000eb38  pop     rdi
0x18000eb39  retn
```
