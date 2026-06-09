# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RoutePolicyOnDemand::IsKnownInterfaceInternal_::_3_::_lambda_1___

- ea: `0x180008214`
- end: `0x18000833e`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RoutePolicyOnDemand::IsKnownInterfaceInternal_::_3_::_lambda_1___`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000811c`

## callees

- `0x180007ff8`
- `0x180008214`
- `0x180008394`
- `0x180008ed8`
- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x18006de30`
- `0x180098260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008243`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008243`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008271`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008303`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008271`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008303`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180008318`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180008318`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_bool__RoutePolicyOnDemand::IsKnownInterfaceInternal_::_3_::_lambda_1___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  __int64 v7; // rax
  __int128 v9; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v10[8]; // [rsp+30h] [rbp-39h] BYREF
  std::_Ref_count_base *v11; // [rsp+38h] [rbp-31h]
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+48h] [rbp-21h]
  _BYTE v13[112]; // [rsp+50h] [rbp-19h] BYREF

  v9 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v12 = v6;
  if ( *(_BYTE *)(a1 + 272) )
  {
    *a2 = 0;
    a2[1] = 0;
    if ( v6 )
      LeaveCriticalSection(v6);
  }
  else
  {
    v7 = std::make_shared_WcmCommon::ThreadPoolWaitableResult_bool___RoutePolicyOnDemand::IsKnownInterfaceInternal_::_3_::_lambda_1___(
           v10,
           a3);
    std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(
      &v9,
      v7);
    if ( v11 )
      std::_Ref_count_base::_Decref(v11);
    if ( *(_DWORD *)a1 == 1 )
    {
      std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(v10);
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(a1 + 192, v10);
      if ( v11 )
        std::_Ref_count_base::_Decref(v11);
    }
    else
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(
        v13,
        &v9);
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(
        a1 + 232,
        v13);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v13);
    }
    if ( v6 )
      LeaveCriticalSection(v6);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *(_OWORD *)a2 = v9;
  }
  return a2;
}

```

## disassembly

```asm
0x180008214  push    rbp
0x180008216  push    rbx
0x180008217  push    rsi
0x180008218  push    rdi
0x180008219  push    r14
0x18000821b  lea     rbp, [rsp-37h]
0x180008220  sub     rsp, 0A0h
0x180008227  mov     r14, r8
0x18000822a  mov     rbx, rdx
0x18000822d  mov     rdi, rcx
0x180008230  mov     [rbp+57h+var_78], rdx
0x180008234  xorps   xmm1, xmm1
0x180008237  movdqu  [rbp+57h+var_A0], xmm1
0x18000823c  lea     rsi, [rcx+8]
0x180008240  mov     rcx, rsi; lpCriticalSection
0x180008243  call    cs:__imp_EnterCriticalSection
0x180008249  mov     [rbp+57h+var_78], rsi
0x18000824d  cmp     byte ptr [rdi+110h], 0
0x180008254  jz      short loc_18000827C
0x180008256  mov     qword ptr [rbx], 0
0x18000825d  mov     qword ptr [rbx+8], 0
0x180008265  test    rsi, rsi
0x180008268  jz      loc_18000832D
0x18000826e  mov     rcx, rsi; lpCriticalSection
0x180008271  call    cs:__imp_LeaveCriticalSection
0x180008277  jmp     loc_18000832D
0x18000827c  mov     rdx, r14
0x18000827f  lea     rcx, [rbp+57h+var_90]
0x180008283  call    std__make_shared_WcmCommon__ThreadPoolWaitableResult_bool___RoutePolicyOnDemand__IsKnownInterfaceInternal____3____lambda_1___
0x180008288  mov     rdx, rax
0x18000828b  lea     rcx, [rbp+57h+var_A0]
0x18000828f  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x180008294  mov     rcx, [rbp+57h+var_88]; this
0x180008298  test    rcx, rcx
0x18000829b  jz      short loc_1800082A2
0x18000829d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800082a2  lea     rdx, [rbp+57h+var_A0]
0x1800082a6  cmp     dword ptr [rdi], 1
0x1800082a9  jnz     short loc_1800082D6
0x1800082ab  lea     rcx, [rbp+57h+var_90]
0x1800082af  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x1800082b4  nop
0x1800082b5  lea     rdx, [rbp+57h+var_90]
0x1800082b9  lea     rcx, [rdi+0C0h]
0x1800082c0  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x1800082c5  nop
0x1800082c6  mov     rcx, [rbp+57h+var_88]; this
0x1800082ca  test    rcx, rcx
0x1800082cd  jz      short loc_1800082FB
0x1800082cf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800082d4  jmp     short loc_1800082FB
0x1800082d6  lea     rcx, [rbp+57h+var_70]
0x1800082da  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x1800082df  nop
0x1800082e0  lea     rdx, [rbp+57h+var_70]
0x1800082e4  lea     rcx, [rdi+0E8h]
0x1800082eb  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x1800082f0  nop
0x1800082f1  lea     rcx, [rbp+57h+var_70]
0x1800082f5  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x1800082fa  nop
0x1800082fb  test    rsi, rsi
0x1800082fe  jz      short loc_180008309
0x180008300  mov     rcx, rsi; lpCriticalSection
0x180008303  call    cs:__imp_LeaveCriticalSection
0x180008309  lock inc qword ptr [rdi+88h]
0x180008311  mov     rcx, [rdi+80h]; pwk
0x180008318  call    cs:__imp_SubmitThreadpoolWork
0x18000831e  mov     rax, qword ptr [rbp+57h+var_A0]
0x180008322  mov     [rbx], rax
0x180008325  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x180008329  mov     [rbx+8], rax
0x18000832d  mov     rax, rbx
0x180008330  add     rsp, 0A0h
0x180008337  pop     r14
0x180008339  pop     rdi
0x18000833a  pop     rsi
0x18000833b  pop     rbx
0x18000833c  pop     rbp
0x18000833d  retn
```
