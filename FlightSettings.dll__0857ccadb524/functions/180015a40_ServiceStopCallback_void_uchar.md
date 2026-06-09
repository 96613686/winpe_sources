# ServiceStopCallback(void *,uchar)

- ea: `0x180015a40`
- end: `0x180015b23`
- name: `?ServiceStopCallback@@YAXPEAXE@Z`
- size: `227`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000e528`
- `0x1800114b4`
- `0x180013d20`
- `0x180013da0`
- `0x180013f3c`
- `0x180015a40`
- `0x180016384`
- `0x18001691c`
- `0x1800177bc`
- `0x1800178a8`
- `0x18008f55c`

## import_xrefs

- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180015ac4`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180015ac4`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180015a6f`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180015a6f`
- `ntdll!RtlNtStatusToDosError` at `0x180015a77`
- `ntdll!RtlNtStatusToDosError` at `0x180015a77`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180015b0c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180015b0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ServiceStopCallback(void *a1)
{
  ServiceComContextRegistrar *v1; // rcx
  NTSTATUS v2; // eax
  signed int v3; // eax
  unsigned __int64 v4; // rdx
  unsigned __int8 v5; // cl
  unsigned int v6; // ebx
  FlightSettingsAPITelemetryClass *v7; // rax
  ServiceComContextRegistrar *v8; // rcx
  __int64 v9; // rcx
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF

  Microsoft::WRL::Wrappers::Mutex::Lock(&g_serviceLock, v10, 0xFFFFFFFFLL);
  SvcAllowAsyncActions(0);
  v1 = g_WNFSubscription;
  if ( g_WNFSubscription )
  {
    v2 = RtlUnsubscribeWnfNotificationWaitForCompletion();
    v3 = RtlNtStatusToDosError(v2);
    v6 = v3;
    if ( v3 > 0 )
      v6 = (unsigned __int16)v3 | 0x80070000;
    if ( FlightSettingsAPITelemetryClass::IsEnabled(v5, v4) )
    {
      v7 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                v1,
                                                _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
      FlightSettingsAPITelemetryClass::ServiceWNSUnregister_(v7, v6);
    }
    g_WNFSubscription = 0;
  }
  ServiceComContextRegistrar::Unregister(v1);
  ServiceComContextRegistrar::Disconnect(v8);
  CoRegisterServerShutdownDelay(0, 0);
  dword_18011D65C = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void UnregisterWaitNoCheck(void *)>>::reset(
    v9,
    0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &qword_18011D728,
    0);
  g_serviceStatus.dwCurrentState = 1;
  *(_QWORD *)&g_serviceStatus.dwCheckPoint = 0;
  SetServiceStatus(g_serviceStatusHandle, &g_serviceStatus);
  Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT<Microsoft::WRL::Wrappers::HandleTraits::MutexTraits>::InternalUnlock(v10);
}

```

## disassembly

```asm
0x180015a40  push    rbx
0x180015a42  sub     rsp, 30h
0x180015a46  or      r8d, 0FFFFFFFFh
0x180015a4a  lea     rdx, [rsp+38h+var_18]
0x180015a4f  lea     rcx, ?g_serviceLock@@3VMutex@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::Mutex g_serviceLock
0x180015a56  call    ?Lock@Mutex@Wrappers@WRL@Microsoft@@QEAA?AV?$SyncLockWithStatusT@UMutexTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Details@234@K@Z; Microsoft::WRL::Wrappers::Mutex::Lock(ulong)
0x180015a5b  nop
0x180015a5c  xor     ecx, ecx
0x180015a5e  call    SvcAllowAsyncActions
0x180015a63  mov     rcx, cs:?g_WNFSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * g_WNFSubscription
0x180015a6a  test    rcx, rcx
0x180015a6d  jz      short loc_180015AB6
0x180015a6f  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180015a75  mov     ecx, eax; Status
0x180015a77  call    cs:__imp_RtlNtStatusToDosError
0x180015a7d  mov     ebx, eax
0x180015a7f  test    eax, eax
0x180015a81  jle     short loc_180015A8C
0x180015a83  movzx   ebx, ax
0x180015a86  or      ebx, 80070000h
0x180015a8c  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x180015a91  test    al, al
0x180015a93  jz      short loc_180015AAB
0x180015a95  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x180015a9c  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x180015aa1  mov     edx, ebx; int
0x180015aa3  mov     rcx, rax; this
0x180015aa6  call    ?ServiceWNSUnregister_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::ServiceWNSUnregister_(long)
0x180015aab  mov     cs:?g_WNFSubscription@@3PEAU_WNF_USER_SUBSCRIPTION@@EA, 0; _WNF_USER_SUBSCRIPTION * g_WNFSubscription
0x180015ab6  call    ?Unregister@ServiceComContextRegistrar@@QEAAJXZ; ServiceComContextRegistrar::Unregister(void)
0x180015abb  call    ?Disconnect@ServiceComContextRegistrar@@QEAAJXZ; ServiceComContextRegistrar::Disconnect(void)
0x180015ac0  xor     edx, edx
0x180015ac2  xor     ecx, ecx
0x180015ac4  call    cs:__imp_CoRegisterServerShutdownDelay
0x180015aca  mov     cs:dword_18011D65C, 0
0x180015ad4  xor     edx, edx
0x180015ad6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AXPEAX@Z$1?UnregisterWaitNoCheck@@YAX0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&UnregisterWaitNoCheck(void *)>>::reset(void *)
0x180015adb  xor     edx, edx
0x180015add  lea     rcx, qword_18011D728
0x180015ae4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180015ae9  mov     cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_serviceStatus ...
0x180015af3  mov     qword ptr cs:?g_serviceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_serviceStatus ...
0x180015afe  lea     rdx, ?g_serviceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180015b05  mov     rcx, cs:?g_serviceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180015b0c  call    cs:__imp_SetServiceStatus
0x180015b12  nop
0x180015b13  lea     rcx, [rsp+38h+var_18]
0x180015b18  call    ?InternalUnlock@?$SyncLockWithStatusT@UMutexTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT<Microsoft::WRL::Wrappers::HandleTraits::MutexTraits>::InternalUnlock(void)
0x180015b1d  add     rsp, 30h
0x180015b21  pop     rbx
0x180015b22  retn
```
