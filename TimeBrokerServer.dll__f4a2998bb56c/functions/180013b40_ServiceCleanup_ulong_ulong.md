# ServiceCleanup(ulong,ulong)

- ea: `0x180013b40`
- end: `0x180013c28`
- name: `?ServiceCleanup@@YAXKK@Z`
- size: `232`
- prototype: `void __fastcall(__int64, DWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180013c30`
- `0x180013ca0`

## callees

- `0x180005b30`
- `0x18000bba0`
- `0x18000bd30`
- `0x180011bb8`
- `0x180013b40`
- `0x180013c40`
- `0x180015530`
- `0x18001c010`

## import_xrefs

- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180013b9c`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180013b9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013bae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013bae`

## pseudocode

```c
void __fastcall ServiceCleanup(__int64 a1, DWORD a2)
{
  DWORD v3; // edi
  __int64 *Instance; // rax
  std::_Ref_count_base *v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v8; // [rsp+28h] [rbp-10h]

  v3 = a1;
  if ( (unsigned int)dword_180026058 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      a1,
      (__int64)byte_1800204D1);
  g_ServiceStatus.dwWin32ExitCode = a2;
  g_ServiceStatus.dwServiceSpecificExitCode = v3;
  if ( g_hWaitHandle )
    (*((void (**)(void))g_pSvchostGlobals + 27))();
  if ( g_hPowerHandle )
    PowerSettingUnregisterNotification(g_hPowerHandle);
  if ( g_hStopEvent )
    CloseHandle(g_hStopEvent);
  Instance = Broker::TimeBroker::GetInstance(&v7);
  v5 = v8;
  v6 = *Instance;
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  if ( v6 )
  {
    std::shared_ptr<Broker::SystemTimer>::reset(&RpcServer);
    std::shared_ptr<Broker::SystemTimer>::reset(&RpcServerTestHook);
    Broker::TimeBroker::DestroyInstance();
  }
  if ( g_ServiceHandle )
    UpdateState(1u);
  if ( (unsigned int)dword_180026058 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v5,
      (__int64)byte_1800204B3);
}

```

## disassembly

```asm
0x180013b40  mov     [rsp+arg_0], rbx
0x180013b45  push    rdi
0x180013b46  sub     rsp, 30h
0x180013b4a  mov     eax, cs:dword_180026058
0x180013b50  mov     ebx, edx
0x180013b52  mov     edi, ecx
0x180013b54  cmp     eax, 5
0x180013b57  jbe     short loc_180013B65
0x180013b59  lea     rdx, byte_1800204D1
0x180013b60  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180013b65  mov     rcx, cs:?g_hWaitHandle@@3PEAXEA; void * g_hWaitHandle
0x180013b6c  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, ebx; _SERVICE_STATUS g_ServiceStatus ...
0x180013b72  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, edi; _SERVICE_STATUS g_ServiceStatus ...
0x180013b78  test    rcx, rcx
0x180013b7b  jz      short loc_180013B90
0x180013b7d  mov     rax, cs:?g_pSvchostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA_EX_V1@@EA; _SVCHOST_GLOBAL_DATA_EX_V1 * g_pSvchostGlobals
0x180013b84  mov     rax, [rax+0D8h]
0x180013b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b90  mov     rcx, cs:?g_hPowerHandle@@3PEAXEA; RegistrationHandle
0x180013b97  test    rcx, rcx
0x180013b9a  jz      short loc_180013BA2
0x180013b9c  call    cs:__imp_PowerSettingUnregisterNotification
0x180013ba2  mov     rcx, cs:?g_hStopEvent@@3PEAXEA; hObject
0x180013ba9  test    rcx, rcx
0x180013bac  jz      short loc_180013BB4
0x180013bae  call    cs:__imp_CloseHandle
0x180013bb4  lea     rcx, [rsp+38h+var_18]
0x180013bb9  call    ?GetInstance@TimeBroker@Broker@@SA?AV?$shared_ptr@VTimeBroker@Broker@@@std@@XZ; Broker::TimeBroker::GetInstance(void)
0x180013bbe  mov     rcx, [rsp+38h+var_10]; this
0x180013bc3  mov     rbx, [rax]
0x180013bc6  test    rcx, rcx
0x180013bc9  jz      short loc_180013BD0
0x180013bcb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180013bd0  test    rbx, rbx
0x180013bd3  jz      short loc_180013BF2
0x180013bd5  lea     rcx, ?RpcServer@@3V?$shared_ptr@VRpcServerRegistration@Broker@@@std@@A; std::shared_ptr<Broker::RpcServerRegistration> RpcServer
0x180013bdc  call    ?reset@?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAXXZ; std::shared_ptr<Broker::SystemTimer>::reset(void)
0x180013be1  lea     rcx, ?RpcServerTestHook@@3V?$shared_ptr@VRpcServerRegistration@Broker@@@std@@A; std::shared_ptr<Broker::RpcServerRegistration> RpcServerTestHook
0x180013be8  call    ?reset@?$shared_ptr@VSystemTimer@Broker@@@std@@QEAAXXZ; std::shared_ptr<Broker::SystemTimer>::reset(void)
0x180013bed  call    ?DestroyInstance@TimeBroker@Broker@@SAXXZ; Broker::TimeBroker::DestroyInstance(void)
0x180013bf2  cmp     cs:?g_ServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, 0; SERVICE_STATUS_HANDLE__ * g_ServiceHandle
0x180013bfa  jz      short loc_180013C06
0x180013bfc  mov     ecx, 1; unsigned int
0x180013c01  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x180013c06  mov     eax, cs:dword_180026058
0x180013c0c  cmp     eax, 5
0x180013c0f  jbe     short loc_180013C1D
0x180013c11  lea     rdx, byte_1800204B3
0x180013c18  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180013c1d  mov     rbx, [rsp+38h+arg_0]
0x180013c22  add     rsp, 30h
0x180013c26  pop     rdi
0x180013c27  retn
```
