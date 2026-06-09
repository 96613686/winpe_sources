# _SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork_::_1_::catch$7

- ea: `0x180029a29`
- end: `0x180029adb`
- name: `_SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork_::_1_::catch$7`
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

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a46`
- `WDSCORE!WdsSetupLogMessageW` at `0x180029ab1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180029ab1`
- `WDSCORE!CurrentIP` at `0x180029a4e`
- `WDSCORE!CurrentIP` at `0x180029a4e`

## string_xrefs

- `0x180029a57`: `SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork: Failed to create snapshot setting item`

## pseudocode

```c
__int64 __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::DoGetValueAsyncWork_::_1_::catch_7(
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
    1583,
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
0x180029a29  mov     [rsp+arg_8], rdx
0x180029a2e  push    rbx
0x180029a2f  push    rbp
0x180029a30  push    rsi
0x180029a31  push    rdi
0x180029a32  sub     rsp, 68h
0x180029a36  mov     rbp, rdx
0x180029a39  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180029a3e  mov     esi, eax
0x180029a40  mov     [rbp+0E0h], eax
0x180029a46  call    cs:__imp_GetLastError
0x180029a4c  mov     edi, eax
0x180029a4e  call    cs:__imp_CurrentIP
0x180029a54  mov     rbx, rax
0x180029a57  lea     rdx, aSystemsettings_43; "SystemSettings::PointInTimeRestore::CPo"...
0x180029a5e  mov     ecx, 2000000h; unsigned int
0x180029a63  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180029a68  mov     [rsp+88h+var_38], 0
0x180029a70  mov     [rsp+88h+var_40], 0
0x180029a79  mov     [rsp+88h+var_48], edi
0x180029a7d  mov     [rsp+88h+var_50], rbx
0x180029a82  lea     rcx, aSystemsettings_46; "SystemSettings::PointInTimeRestore::CPo"...
0x180029a89  mov     [rsp+88h+var_58], rcx
0x180029a8e  lea     rcx, aPcshellShellSy_1; "pcshell\\shell\\systemsettings\\recover"...
0x180029a95  mov     [rsp+88h+var_60], rcx
0x180029a9a  mov     [rsp+88h+var_68], 62Fh
0x180029aa2  xor     r9d, r9d
0x180029aa5  lea     r8, aD; "D"
0x180029aac  xor     edx, edx
0x180029aae  mov     rcx, rax
0x180029ab1  call    cs:__imp_WdsSetupLogMessageW
0x180029ab7  call    ?GetCurrent@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@SAPEAV123@XZ; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::GetCurrent(void)
0x180029abc  mov     edx, esi; int
0x180029abe  mov     rcx, rax; this
0x180029ac1  call    ?SetLastPITRError@CPointInTimeRestoreStateSingleton@PointInTimeRestore@SystemSettings@@QEAAXJ@Z; SystemSettings::PointInTimeRestore::CPointInTimeRestoreStateSingleton::SetLastPITRError(long)
0x180029ac6  nop
0x180029ac7  mov     rax, 0
0x180029ad1  add     rsp, 68h
0x180029ad5  pop     rdi
0x180029ad6  pop     rsi
0x180029ad7  pop     rbp
0x180029ad8  pop     rbx
0x180029ad9  retn
```
