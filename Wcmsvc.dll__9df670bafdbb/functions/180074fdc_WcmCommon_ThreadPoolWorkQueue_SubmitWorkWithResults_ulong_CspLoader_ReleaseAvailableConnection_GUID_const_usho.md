# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults<ulong,`CspLoader::ReleaseAvailableConnection(_GUID const *,ushort const *,ulong)'::`6'::_lambda_1_>(`CspLoader::ReleaseAvailableConnection(_GUID const *,ushort const *,ulong)'::`6'::_lambda_1_ &&)

- ea: `0x180074fdc`
- end: `0x180075159`
- name: `??$SubmitWorkWithResults@KV_lambda_1_@?5??ReleaseAvailableConnection@CspLoader@@QEAAKPEBU_GUID@@PEBGK@Z@@ThreadPoolWorkQueue@WcmCommon@@QEAA?AV?$shared_ptr@V?$ThreadPoolWaitableResult@K@WcmCommon@@@std@@$$QEAV_lambda_1_@?5??ReleaseAvailableConnection@CspLoader@@QEAAKPEBU_GUID@@PEBGK@Z@@Z`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180082118`

## callees

- `0x180007ff8`
- `0x180008394`
- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x180027630`
- `0x18006de30`
- `0x180074fdc`
- `0x180075160`
- `0x18008534c`
- `0x180098260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075045`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075115`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075045`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075115`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007512a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007512a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Z::SubmitWorkWithResults<unsigned long,`CspLoader::ReleaseAvailableConnection'::`6'::_lambda_1_,AKPEBU_GUID * const,unsigned short const *,unsigned long>(
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
    ____0V_lambda_1___5__ReleaseAvailableConnection_CspLoader__QEAAKPEBU_GUID__PEBGK_Z____ThreadPoolWaitableResult_K_WcmCommon__QEAA___QEAV_lambda_1___5__ReleaseAvailableConnection_CspLoader__QEAAKPEBU_GUID__PEBGK_Z__Z(
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
0x180074fdc  mov     [rsp-8+arg_18], rbx
0x180074fe1  push    rbp
0x180074fe2  push    rsi
0x180074fe3  push    rdi
0x180074fe4  push    r14
0x180074fe6  push    r15
0x180074fe8  lea     rbp, [rsp-37h]
0x180074fed  sub     rsp, 0A0h
0x180074ff4  mov     r15, r8
0x180074ff7  mov     rsi, rdx
0x180074ffa  mov     r14, rcx
0x180074ffd  mov     [rbp+57h+lpCriticalSection], rdx
0x180075001  xorps   xmm1, xmm1
0x180075004  movdqu  [rbp+57h+var_88], xmm1
0x180075009  mov     [rbp+57h+lpCriticalSection], 0
0x180075011  lea     rdx, [rcx+8]
0x180075015  lea     rcx, [rbp+57h+lpCriticalSection]
0x180075019  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18007501e  nop
0x18007501f  cmp     byte ptr [r14+110h], 0
0x180075027  jz      short loc_180075050
0x180075029  mov     qword ptr [rsi], 0
0x180075030  mov     qword ptr [rsi+8], 0
0x180075038  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18007503c  test    rcx, rcx
0x18007503f  jz      loc_18007513F
0x180075045  call    cs:__imp_LeaveCriticalSection
0x18007504b  jmp     loc_18007513F
0x180075050  mov     ecx, 78h ; 'x'; Size
0x180075055  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007505a  mov     rdi, rax
0x18007505d  mov     [rbp+57h+var_98], rax
0x180075061  xorps   xmm0, xmm0
0x180075064  movups  xmmword ptr [rax], xmm0
0x180075067  mov     dword ptr [rax+8], 1
0x18007506e  mov     dword ptr [rax+0Ch], 1
0x180075075  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable'
0x18007507c  mov     [rdi], rax
0x18007507f  lea     rbx, [rdi+10h]
0x180075083  mov     rdx, r15
0x180075086  mov     rcx, rbx
0x180075089  call    ??$?0V_lambda_1_@?5??ReleaseAvailableConnection@CspLoader@@QEAAKPEBU_GUID@@PEBGK@Z@@?$ThreadPoolWaitableResult@K@WcmCommon@@QEAA@$$QEAV_lambda_1_@?5??ReleaseAvailableConnection@CspLoader@@QEAAKPEBU_GUID@@PEBGK@Z@@Z; WcmCommon::ThreadPoolWaitableResult<ulong>::ThreadPoolWaitableResult<ulong>(`CspLoader::ReleaseAvailableConnection(_GUID const *,ushort const *,ulong)'::`6'::_lambda_1_ &&)
0x18007508e  nop
0x18007508f  mov     [rbp+57h+var_98], rbx
0x180075093  mov     [rbp+57h+var_90], rdi
0x180075097  lea     rdx, [rbp+57h+var_98]
0x18007509b  lea     rcx, [rbp+57h+var_88]
0x18007509f  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x1800750a4  mov     rcx, [rbp+57h+var_90]; this
0x1800750a8  test    rcx, rcx
0x1800750ab  jz      short loc_1800750B2
0x1800750ad  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800750b2  lea     rdx, [rbp+57h+var_88]
0x1800750b6  cmp     dword ptr [r14], 1
0x1800750ba  jnz     short loc_1800750E7
0x1800750bc  lea     rcx, [rbp+57h+var_98]
0x1800750c0  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x1800750c5  nop
0x1800750c6  lea     rdx, [rbp+57h+var_98]
0x1800750ca  lea     rcx, [r14+0C0h]
0x1800750d1  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x1800750d6  nop
0x1800750d7  mov     rcx, [rbp+57h+var_90]; this
0x1800750db  test    rcx, rcx
0x1800750de  jz      short loc_18007510C
0x1800750e0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800750e5  jmp     short loc_18007510C
0x1800750e7  lea     rcx, [rbp+57h+var_70]
0x1800750eb  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x1800750f0  nop
0x1800750f1  lea     rdx, [rbp+57h+var_70]
0x1800750f5  lea     rcx, [r14+0E8h]
0x1800750fc  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x180075101  nop
0x180075102  lea     rcx, [rbp+57h+var_70]
0x180075106  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x18007510b  nop
0x18007510c  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180075110  test    rcx, rcx
0x180075113  jz      short loc_18007511B
0x180075115  call    cs:__imp_LeaveCriticalSection
0x18007511b  lock inc qword ptr [r14+88h]
0x180075123  mov     rcx, [r14+80h]; pwk
0x18007512a  call    cs:__imp_SubmitThreadpoolWork
0x180075130  mov     rax, qword ptr [rbp+57h+var_88]
0x180075134  mov     [rsi], rax
0x180075137  mov     rax, qword ptr [rbp+57h+var_88+8]
0x18007513b  mov     [rsi+8], rax
0x18007513f  mov     rax, rsi
0x180075142  mov     rbx, [rsp+0C0h+arg_18]
0x18007514a  add     rsp, 0A0h
0x180075151  pop     r15
0x180075153  pop     r14
0x180075155  pop     rdi
0x180075156  pop     rsi
0x180075157  pop     rbp
0x180075158  retn
```
