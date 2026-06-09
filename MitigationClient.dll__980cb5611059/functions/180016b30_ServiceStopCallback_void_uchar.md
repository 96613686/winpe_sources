# ServiceStopCallback(void *,uchar)

- ea: `0x180016b30`
- end: `0x180016be4`
- name: `?ServiceStopCallback@@YAXPEAXE@Z`
- size: `180`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180014030`
- `0x18001609c`
- `0x180016210`
- `0x180016b30`
- `0x180016c60`
- `0x180016e88`

## import_xrefs

- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180016b4d`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180016b4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016bb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180016bb0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016bd8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016bd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bba`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180016b95`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180016b95`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ServiceStopCallback(void *a1)
{
  ServiceComContextRegistrar *v1; // rcx
  ServiceComContextRegistrar *v2; // rcx
  __int64 v3; // rcx
  int LastError; // eax
  int v5; // [rsp+20h] [rbp-18h] BYREF
  HANDLE hMutex; // [rsp+28h] [rbp-10h]

  Microsoft::WRL::Wrappers::Mutex::Lock(a1, &v5);
  ServiceComContextRegistrar::Unregister(v1);
  ServiceComContextRegistrar::Disconnect(v2);
  CoRegisterServerShutdownDelay(0, 0);
  dword_180080AB8 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void UnregisterWaitNoCheck(void *)>>::reset(
    v3,
    0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &qword_180080BD8,
    0);
  g_serviceStatus.dwCurrentState = 1;
  *(_QWORD *)&g_serviceStatus.dwCheckPoint = 0;
  SetServiceStatus(g_serviceStatusHandle, &g_serviceStatus);
  if ( hMutex && (v5 & 0xFFFFFF7F) == 0 && !ReleaseMutex(hMutex) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180016b30  sub     rsp, 38h
0x180016b34  lea     rdx, [rsp+38h+var_18]
0x180016b39  call    ?Lock@Mutex@Wrappers@WRL@Microsoft@@QEAA?AV?$SyncLockWithStatusT@UMutexTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Details@234@K@Z; Microsoft::WRL::Wrappers::Mutex::Lock(ulong)
0x180016b3e  nop
0x180016b3f  call    ?Unregister@ServiceComContextRegistrar@@QEAAJXZ; ServiceComContextRegistrar::Unregister(void)
0x180016b44  call    ?Disconnect@ServiceComContextRegistrar@@QEAAJXZ; ServiceComContextRegistrar::Disconnect(void)
0x180016b49  xor     edx, edx
0x180016b4b  xor     ecx, ecx
0x180016b4d  call    cs:__imp_CoRegisterServerShutdownDelay
0x180016b53  mov     cs:dword_180080AB8, 0
0x180016b5d  xor     edx, edx
0x180016b5f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AXPEAX@Z$1?UnregisterWaitNoCheck@@YAX0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&UnregisterWaitNoCheck(void *)>>::reset(void *)
0x180016b64  xor     edx, edx
0x180016b66  lea     rcx, qword_180080BD8
0x180016b6d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180016b72  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_serviceStatus ...
0x180016b7c  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_serviceStatus ...
0x180016b87  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180016b8e  mov     rcx, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180016b95  call    cs:__imp_SetServiceStatus
0x180016b9b  nop
0x180016b9c  mov     rcx, [rsp+38h+hMutex]; hMutex
0x180016ba1  test    rcx, rcx
0x180016ba4  jz      short loc_180016BDF
0x180016ba6  test    [rsp+38h+var_18], 0FFFFFF7Fh
0x180016bae  jnz     short loc_180016BDF
0x180016bb0  call    cs:__imp_ReleaseMutex
0x180016bb6  test    eax, eax
0x180016bb8  jnz     short loc_180016BDF
0x180016bba  call    cs:__imp_GetLastError
0x180016bc0  test    eax, eax
0x180016bc2  jle     short loc_180016BCC
0x180016bc4  movzx   eax, ax
0x180016bc7  or      eax, 80070000h
0x180016bcc  xor     r9d, r9d; lpArguments
0x180016bcf  xor     r8d, r8d; nNumberOfArguments
0x180016bd2  lea     edx, [r9+1]; dwExceptionFlags
0x180016bd6  mov     ecx, eax; dwExceptionCode
0x180016bd8  call    cs:__imp_RaiseException
0x180016bde  int     3; Trap to Debugger
0x180016bdf  add     rsp, 38h
0x180016be3  retn
```
