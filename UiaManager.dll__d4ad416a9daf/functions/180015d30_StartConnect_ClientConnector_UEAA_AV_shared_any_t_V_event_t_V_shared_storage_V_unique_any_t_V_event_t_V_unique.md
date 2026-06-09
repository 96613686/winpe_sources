# ?StartConnect@ClientConnector@@UEAA?AV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@XZ

- ea: `0x180015d30`
- end: `0x180015e4d`
- name: `?StartConnect@ClientConnector@@UEAA?AV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@XZ`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x1800054c0`
- `0x180015d30`
- `0x18001607c`
- `0x1800160fc`
- `0x18001645c`
- `0x180016d24`
- `0x18001d9c4`
- `0x18002a514`
- `0x180075a9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180015e2e`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180015e2e`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180015ded`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180015ded`

## string_xrefs

- `0x180015e3d`: `onecore\windows\accessibletech\uiamanager\dll\namedpipechannel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ClientConnector::StartConnect(ClientConnector *this, _QWORD *a2)
{
  _QWORD *v4; // rax
  HANDLE WaitableTimerW; // rax
  _QWORD *v7; // rcx
  const char *v8; // r9
  _QWORD v9[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LARGE_INTEGER DueTime; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v12; // [rsp+68h] [rbp+10h]

  v12 = a2;
  if ( *((_BYTE *)this + 8) )
  {
    *((_BYTE *)this + 8) = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=((char *)this + 16);
  }
  *(_OWORD *)a2 = 0;
  *a2 = 0;
  a2[1] = 0;
  ClientConnector::TryConnect(this);
  if ( (unsigned __int64)(*((_QWORD *)this + 2) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    WaitableTimerW = CreateWaitableTimerW(0, 0, 0);
    _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
      a2,
      WaitableTimerW);
    v7 = (_QWORD *)*a2;
    if ( *a2 )
      v7 = (_QWORD *)*v7;
    DueTime.QuadPart = -10000000;
    if ( !SetWaitableTimer(v7, &DueTime, 0, 0, 0, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\namedpipechannel.cpp",
        v8);
  }
  else
  {
    DueTime.LowPart = 1;
    v4 = ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
           v9,
           (int *)&DueTime);
    if ( a2 != v4 )
      std::shared_ptr<WorkerThread<Unit>>::operator=(a2, v4);
    std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v9);
    _SetEvent___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEBAXXZ(a2);
  }
  *((_BYTE *)this + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x180015d30  mov     rax, rsp
0x180015d33  mov     [rax+18h], rbx
0x180015d37  mov     [rax+20h], rsi
0x180015d3b  mov     [rax+10h], rdx
0x180015d3f  push    rdi
0x180015d40  sub     rsp, 50h
0x180015d44  mov     rbx, rdx
0x180015d47  mov     rsi, rcx
0x180015d4a  mov     dword ptr [rax-28h], 0
0x180015d51  cmp     byte ptr [rcx+8], 0
0x180015d55  jz      short loc_180015D64
0x180015d57  mov     byte ptr [rcx+8], 0
0x180015d5b  add     rcx, 10h
0x180015d5f  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(std::nullptr_t)
0x180015d64  xorps   xmm0, xmm0
0x180015d67  movups  xmmword ptr [rbx], xmm0
0x180015d6a  mov     qword ptr [rbx], 0
0x180015d71  mov     qword ptr [rbx+8], 0
0x180015d79  mov     [rsp+58h+var_28], 1
0x180015d81  mov     rcx, rsi; this
0x180015d84  call    ?TryConnect@ClientConnector@@AEAAXXZ; ClientConnector::TryConnect(void)
0x180015d89  mov     rax, [rsi+10h]
0x180015d8d  dec     rax
0x180015d90  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015d94  ja      short loc_180015DE6
0x180015d96  mov     dword ptr [rsp+58h+DueTime], 1
0x180015d9e  lea     rdx, [rsp+58h+DueTime]
0x180015da3  lea     rcx, [rsp+58h+var_20]
0x180015da8  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180015dad  cmp     rbx, rax
0x180015db0  jz      short loc_180015DBD
0x180015db2  mov     rdx, rax
0x180015db5  mov     rcx, rbx
0x180015db8  call    ??4?$shared_ptr@V?$WorkerThread@UUnit@@@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<WorkerThread<Unit>>::operator=(std::shared_ptr<WorkerThread<Unit>> &&)
0x180015dbd  lea     rcx, [rsp+58h+var_20]
0x180015dc2  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x180015dc7  mov     rcx, rbx
0x180015dca  call    ?SetEvent@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBAXXZ
0x180015dcf  mov     byte ptr [rsi+8], 1
0x180015dd3  mov     rax, rbx
0x180015dd6  mov     rbx, [rsp+58h+arg_10]
0x180015ddb  mov     rsi, [rsp+58h+arg_18]
0x180015de0  add     rsp, 50h
0x180015de4  pop     rdi
0x180015de5  retn
0x180015de6  xor     r8d, r8d; lpTimerName
0x180015de9  xor     edx, edx; bManualReset
0x180015deb  xor     ecx, ecx; lpTimerAttributes
0x180015ded  call    cs:__imp_CreateWaitableTimerW
0x180015df3  mov     rdx, rax
0x180015df6  mov     rcx, rbx
0x180015df9  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x180015dfe  mov     rcx, [rbx]
0x180015e01  test    rcx, rcx
0x180015e04  jz      short loc_180015E09
0x180015e06  mov     rcx, [rcx]; hTimer
0x180015e09  mov     qword ptr [rsp+58h+DueTime], 0FFFFFFFFFF676980h
0x180015e12  mov     [rsp+58h+fResume], 0; fResume
0x180015e1a  mov     [rsp+58h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x180015e23  xor     r9d, r9d; pfnCompletionRoutine
0x180015e26  xor     r8d, r8d; lPeriod
0x180015e29  lea     rdx, [rsp+58h+DueTime]; lpDueTime
0x180015e2e  call    cs:__imp_SetWaitableTimer
0x180015e34  test    eax, eax
0x180015e36  jnz     short loc_180015DCF
0x180015e38  mov     rcx, [rsp+58h]; this
0x180015e3d  lea     r8, aOnecoreWindows_29; "onecore\\windows\\accessibletech\\uiama"...
0x180015e44  lea     edx, [rax+2Ah]; void *
0x180015e47  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
