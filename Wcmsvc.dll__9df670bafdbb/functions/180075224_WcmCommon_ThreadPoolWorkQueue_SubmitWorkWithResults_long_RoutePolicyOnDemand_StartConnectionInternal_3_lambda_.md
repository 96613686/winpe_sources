# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__RoutePolicyOnDemand::StartConnectionInternal_::_3_::_lambda_1___

- ea: `0x180075224`
- end: `0x1800753a1`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__RoutePolicyOnDemand::StartConnectionInternal_::_3_::_lambda_1___`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180063e84`

## callees

- `0x180007ff8`
- `0x180008394`
- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x180027630`
- `0x18006de30`
- `0x180075224`
- `0x1800753a8`
- `0x18008534c`
- `0x180098260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007528d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007535d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007528d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007535d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180075372`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180075372`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_long__RoutePolicyOnDemand::StartConnectionInternal_::_3_::_lambda_1___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  std::_Ref_count_base *v6; // rdi
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-49h] BYREF
  std::_Ref_count_base *v9; // [rsp+28h] [rbp-41h] BYREF
  std::_Ref_count_base *v10; // [rsp+30h] [rbp-39h]
  __int128 v11; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v12[112]; // [rsp+50h] [rbp-19h] BYREF

  v11 = 0;
  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, a1 + 8);
  if ( *(_BYTE *)(a1 + 272) )
  {
    *a2 = 0;
    a2[1] = 0;
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
  else
  {
    v6 = (std::_Ref_count_base *)operator new(0x78u);
    v9 = v6;
    *(_OWORD *)v6 = 0;
    *((_DWORD *)v6 + 2) = 1;
    *((_DWORD *)v6 + 3) = 1;
    *(_QWORD *)v6 = &std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable';
    WcmCommon::ThreadPoolWaitableResult_long_::ThreadPoolWaitableResult_long___RoutePolicyOnDemand::StartConnectionInternal_::_3_::_lambda_1___(
      (char *)v6 + 16,
      a3);
    v9 = (std::_Ref_count_base *)((char *)v6 + 16);
    v10 = v6;
    std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(
      &v11,
      &v9);
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
    if ( *(_DWORD *)a1 == 1 )
    {
      std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(&v9);
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(a1 + 192, &v9);
      if ( v10 )
        std::_Ref_count_base::_Decref(v10);
    }
    else
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(
        v12,
        &v11);
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(
        a1 + 232,
        v12);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v12);
    }
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *(_OWORD *)a2 = v11;
  }
  return a2;
}

```

## disassembly

```asm
0x180075224  mov     [rsp-8+arg_10], rbx
0x180075229  push    rbp
0x18007522a  push    rsi
0x18007522b  push    rdi
0x18007522c  push    r14
0x18007522e  push    r15
0x180075230  lea     rbp, [rsp-37h]
0x180075235  sub     rsp, 0A0h
0x18007523c  mov     r15, r8
0x18007523f  mov     rsi, rdx
0x180075242  mov     r14, rcx
0x180075245  mov     [rbp+57h+lpCriticalSection], rdx
0x180075249  xorps   xmm1, xmm1
0x18007524c  movdqu  [rbp+57h+var_88], xmm1
0x180075251  mov     [rbp+57h+lpCriticalSection], 0
0x180075259  lea     rdx, [rcx+8]
0x18007525d  lea     rcx, [rbp+57h+lpCriticalSection]
0x180075261  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180075266  nop
0x180075267  cmp     byte ptr [r14+110h], 0
0x18007526f  jz      short loc_180075298
0x180075271  mov     qword ptr [rsi], 0
0x180075278  mov     qword ptr [rsi+8], 0
0x180075280  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180075284  test    rcx, rcx
0x180075287  jz      loc_180075387
0x18007528d  call    cs:__imp_LeaveCriticalSection
0x180075293  jmp     loc_180075387
0x180075298  mov     ecx, 78h ; 'x'; Size
0x18007529d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800752a2  mov     rdi, rax
0x1800752a5  mov     [rbp+57h+var_98], rax
0x1800752a9  xorps   xmm0, xmm0
0x1800752ac  movups  xmmword ptr [rax], xmm0
0x1800752af  mov     dword ptr [rax+8], 1
0x1800752b6  mov     dword ptr [rax+0Ch], 1
0x1800752bd  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable'
0x1800752c4  mov     [rdi], rax
0x1800752c7  lea     rbx, [rdi+10h]
0x1800752cb  mov     rdx, r15
0x1800752ce  mov     rcx, rbx
0x1800752d1  call    WcmCommon__ThreadPoolWaitableResult_long___ThreadPoolWaitableResult_long___RoutePolicyOnDemand__StartConnectionInternal____3____lambda_1___
0x1800752d6  nop
0x1800752d7  mov     [rbp+57h+var_98], rbx
0x1800752db  mov     [rbp+57h+var_90], rdi
0x1800752df  lea     rdx, [rbp+57h+var_98]
0x1800752e3  lea     rcx, [rbp+57h+var_88]
0x1800752e7  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x1800752ec  mov     rcx, [rbp+57h+var_90]; this
0x1800752f0  test    rcx, rcx
0x1800752f3  jz      short loc_1800752FA
0x1800752f5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800752fa  lea     rdx, [rbp+57h+var_88]
0x1800752fe  cmp     dword ptr [r14], 1
0x180075302  jnz     short loc_18007532F
0x180075304  lea     rcx, [rbp+57h+var_98]
0x180075308  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x18007530d  nop
0x18007530e  lea     rdx, [rbp+57h+var_98]
0x180075312  lea     rcx, [r14+0C0h]
0x180075319  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x18007531e  nop
0x18007531f  mov     rcx, [rbp+57h+var_90]; this
0x180075323  test    rcx, rcx
0x180075326  jz      short loc_180075354
0x180075328  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007532d  jmp     short loc_180075354
0x18007532f  lea     rcx, [rbp+57h+var_70]
0x180075333  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x180075338  nop
0x180075339  lea     rdx, [rbp+57h+var_70]
0x18007533d  lea     rcx, [r14+0E8h]
0x180075344  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x180075349  nop
0x18007534a  lea     rcx, [rbp+57h+var_70]
0x18007534e  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x180075353  nop
0x180075354  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180075358  test    rcx, rcx
0x18007535b  jz      short loc_180075363
0x18007535d  call    cs:__imp_LeaveCriticalSection
0x180075363  lock inc qword ptr [r14+88h]
0x18007536b  mov     rcx, [r14+80h]; pwk
0x180075372  call    cs:__imp_SubmitThreadpoolWork
0x180075378  mov     rax, qword ptr [rbp+57h+var_88]
0x18007537c  mov     [rsi], rax
0x18007537f  mov     rax, qword ptr [rbp+57h+var_88+8]
0x180075383  mov     [rsi+8], rax
0x180075387  mov     rax, rsi
0x18007538a  mov     rbx, [rsp+0C0h+arg_10]
0x180075392  add     rsp, 0A0h
0x180075399  pop     r15
0x18007539b  pop     r14
0x18007539d  pop     rdi
0x18007539e  pop     rsi
0x18007539f  pop     rbp
0x1800753a0  retn
```
