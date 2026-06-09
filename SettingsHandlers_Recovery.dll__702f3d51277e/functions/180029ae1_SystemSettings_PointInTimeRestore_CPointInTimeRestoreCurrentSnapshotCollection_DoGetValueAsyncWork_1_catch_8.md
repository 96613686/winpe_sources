# _SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork_::_1_::catch$8

- ea: `0x180029ae1`
- end: `0x180029b93`
- name: `_SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork_::_1_::catch$8`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000bef4`
- `0x18001ee08`
- `0x180025920`
- `0x1800261f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029afe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029afe`
- `WDSCORE!WdsSetupLogMessageW` at `0x180029b69`
- `WDSCORE!WdsSetupLogMessageW` at `0x180029b69`
- `WDSCORE!CurrentIP` at `0x180029b06`
- `WDSCORE!CurrentIP` at `0x180029b06`

## string_xrefs

- `0x180029b0f`: `SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork: Failed to create snapshot setting item`

## pseudocode

```c
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork_::_1_::catch_8(
        wil *a1,
        __int64 a2)
{
  int v3; // esi
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton *Current; // rax

  v3 = wil::ResultFromCaughtException(a1);
  *(_DWORD *)(a2 + 224) = v3;
  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = ConstructPartialMsgW(
         0x2000000u,
         "SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork: Failed t"
         "o create snapshot setting item");
  WdsSetupLogMessageW(
    v6,
    0,
    L"D",
    0,
    1613,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\cpointintimerestoresetting.cpp",
    L"SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork",
    v5,
    LastError,
    0,
    0);
  Current = SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent();
  SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::SetLastPITRError(Current, v3);
  return 0;
}

```

## disassembly

```asm
0x180029ae1  mov     [rsp+arg_8], rdx
0x180029ae6  push    rbx
0x180029ae7  push    rbp
0x180029ae8  push    rsi
0x180029ae9  push    rdi
0x180029aea  sub     rsp, 68h
0x180029aee  mov     rbp, rdx
0x180029af1  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180029af6  mov     esi, eax
0x180029af8  mov     [rbp+0E0h], eax
0x180029afe  call    cs:__imp_GetLastError
0x180029b04  mov     edi, eax
0x180029b06  call    cs:__imp_CurrentIP
0x180029b0c  mov     rbx, rax
0x180029b0f  lea     rdx, aSystemsettings_43; "SystemSettings::PointInTimeRestore::CPo"...
0x180029b16  mov     ecx, 2000000h; unsigned int
0x180029b1b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180029b20  mov     [rsp+88h+var_38], 0
0x180029b28  mov     [rsp+88h+var_40], 0
0x180029b31  mov     [rsp+88h+var_48], edi
0x180029b35  mov     [rsp+88h+var_50], rbx
0x180029b3a  lea     rcx, aSystemsettings_46; "SystemSettings::PointInTimeRestore::CPo"...
0x180029b41  mov     [rsp+88h+var_58], rcx
0x180029b46  lea     rcx, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x180029b4d  mov     [rsp+88h+var_60], rcx
0x180029b52  mov     [rsp+88h+var_68], 64Dh
0x180029b5a  xor     r9d, r9d
0x180029b5d  lea     r8, aD; "D"
0x180029b64  xor     edx, edx
0x180029b66  mov     rcx, rax
0x180029b69  call    cs:__imp_WdsSetupLogMessageW
0x180029b6f  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x180029b74  mov     edx, esi; int
0x180029b76  mov     rcx, rax; this
0x180029b79  call    ?SetLastPITRError@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEAAXJ@Z; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::SetLastPITRError(long)
0x180029b7e  nop
0x180029b7f  mov     rax, 0
0x180029b89  add     rsp, 68h
0x180029b8d  pop     rdi
0x180029b8e  pop     rsi
0x180029b8f  pop     rbp
0x180029b90  pop     rbx
0x180029b91  retn
```
