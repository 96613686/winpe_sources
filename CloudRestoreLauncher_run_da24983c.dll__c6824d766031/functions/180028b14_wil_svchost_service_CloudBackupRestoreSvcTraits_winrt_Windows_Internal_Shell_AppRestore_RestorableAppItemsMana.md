# wil::svchost_service<CloudBackupRestoreSvcTraits,winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>::update_status(ulong,ulong)

- ea: `0x180028b14`
- end: `0x180028ba8`
- name: `?update_status@?$svchost_service@UCloudBackupRestoreSvcTraits@@URestorableAppItemsManager@AppRestore@Shell@Internal@Windows@winrt@@URestorableTileItemsManager@34567@UAppRestoreOrchestrator@34567@@wil@@AEAAXKK@Z`
- size: `148`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x1800276c0`
- `0x180028910`
- `0x180028a54`

## callees

- `0x18000c6e0`
- `0x18001dd54`
- `0x180028b14`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x180028b82`
- `ADVAPI32!SetServiceStatus` at `0x180028b82`

## pseudocode

```c
BOOL __fastcall wil::svchost_service<CloudBackupRestoreSvcTraits,winrt::Windows::Internal::Shell::AppRestore::RestorableAppItemsManager,winrt::Windows::Internal::Shell::AppRestore::RestorableTileItemsManager,winrt::Windows::Internal::Shell::AppRestore::AppRestoreOrchestrator>::update_status(
        __int64 a1,
        DWORD a2,
        DWORD a3)
{
  SERVICE_STATUS_HANDLE v3; // rcx
  BOOL result; // eax
  const struct winrt::impl::slim_source_location *v5; // rdx
  int v6; // [rsp+20h] [rbp-40h] BYREF
  __int128 v7; // [rsp+28h] [rbp-38h]
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-28h] BYREF

  ServiceStatus.dwServiceType = 96;
  ServiceStatus.dwCurrentState = a2;
  memset(&ServiceStatus.dwControlsAccepted, 0, 20);
  ServiceStatus.dwWin32ExitCode = a3;
  if ( a2 == 4 || a2 == 1 )
  {
    ServiceStatus.dwControlsAccepted = 1025;
  }
  else
  {
    ServiceStatus.dwWaitHint = 5000;
    ServiceStatus.dwCheckPoint = _InterlockedIncrement((volatile signed __int32 *)(a1 + 40));
  }
  v3 = *(SERVICE_STATUS_HANDLE *)(a1 + 32);
  v6 = 0;
  v7 = 0;
  result = SetServiceStatus(v3, &ServiceStatus);
  if ( !result )
    winrt::throw_last_error((winrt *)&v6, v5);
  return result;
}

```

## disassembly

```asm
0x180028b14  push    rbp
0x180028b16  mov     rbp, rsp
0x180028b19  sub     rsp, 60h
0x180028b1d  mov     rax, cs:__security_cookie
0x180028b24  xor     rax, rsp
0x180028b27  mov     [rbp+var_8], rax
0x180028b2b  xor     eax, eax
0x180028b2d  mov     [rbp+ServiceStatus.dwServiceType], 60h ; '`'
0x180028b34  mov     [rbp+ServiceStatus.dwCurrentState], edx
0x180028b37  xorps   xmm0, xmm0
0x180028b3a  mov     [rbp+ServiceStatus.dwWaitHint], eax
0x180028b3d  movups  xmmword ptr [rbp+ServiceStatus.dwControlsAccepted], xmm0
0x180028b41  mov     [rbp+ServiceStatus.dwWin32ExitCode], r8d
0x180028b45  cmp     edx, 4
0x180028b48  jz      short loc_180028B67
0x180028b4a  cmp     edx, 1
0x180028b4d  jz      short loc_180028B67
0x180028b4f  mov     eax, 1
0x180028b54  lock xadd [rcx+28h], eax
0x180028b59  inc     eax
0x180028b5b  mov     [rbp+ServiceStatus.dwWaitHint], 1388h
0x180028b62  mov     [rbp+ServiceStatus.dwCheckPoint], eax
0x180028b65  jmp     short loc_180028B6E
0x180028b67  mov     [rbp+ServiceStatus.dwControlsAccepted], 401h
0x180028b6e  mov     rcx, [rcx+20h]; hServiceStatus
0x180028b72  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x180028b76  mov     [rbp+var_40], 0
0x180028b7d  movdqu  [rbp+var_38], xmm0
0x180028b82  call    cs:__imp_SetServiceStatus
0x180028b88  test    eax, eax
0x180028b8a  jz      short loc_180028B9E
0x180028b8c  mov     rcx, [rbp+var_8]
0x180028b90  xor     rcx, rsp; StackCookie
0x180028b93  call    __security_check_cookie
0x180028b98  add     rsp, 60h
0x180028b9c  pop     rbp
0x180028b9d  retn
0x180028b9e  lea     rcx, [rbp+var_40]; this
0x180028ba2  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
