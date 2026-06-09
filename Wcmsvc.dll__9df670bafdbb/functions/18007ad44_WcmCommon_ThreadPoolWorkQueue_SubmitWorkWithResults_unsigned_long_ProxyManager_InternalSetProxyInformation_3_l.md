# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_unsigned_long__ProxyManager::InternalSetProxyInformation_::_3_::_lambda_1___

- ea: `0x18007ad44`
- end: `0x18007aec1`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_unsigned_long__ProxyManager::InternalSetProxyInformation_::_3_::_lambda_1___`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074aa4`

## callees

- `0x180007ff8`
- `0x180008394`
- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x180027630`
- `0x18006de30`
- `0x18007ad44`
- `0x18007aec8`
- `0x18008534c`
- `0x180098260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007adad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ae7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007adad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ae7d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007ae92`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007ae92`

## pseudocode

```c
_QWORD *__fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults_unsigned_long__ProxyManager::InternalSetProxyInformation_::_3_::_lambda_1___(
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
    WcmCommon::ThreadPoolWaitableResult_unsigned_long_::ThreadPoolWaitableResult_unsigned_long___ProxyManager::InternalSetProxyInformation_::_3_::_lambda_1___(
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
0x18007ad44  mov     [rsp-8+arg_18], rbx
0x18007ad49  push    rbp
0x18007ad4a  push    rsi
0x18007ad4b  push    rdi
0x18007ad4c  push    r14
0x18007ad4e  push    r15
0x18007ad50  lea     rbp, [rsp-37h]
0x18007ad55  sub     rsp, 0A0h
0x18007ad5c  mov     r15, r8
0x18007ad5f  mov     rsi, rdx
0x18007ad62  mov     r14, rcx
0x18007ad65  mov     [rbp+57h+lpCriticalSection], rdx
0x18007ad69  xorps   xmm1, xmm1
0x18007ad6c  movdqu  [rbp+57h+var_88], xmm1
0x18007ad71  mov     [rbp+57h+lpCriticalSection], 0
0x18007ad79  lea     rdx, [rcx+8]
0x18007ad7d  lea     rcx, [rbp+57h+lpCriticalSection]
0x18007ad81  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18007ad86  nop
0x18007ad87  cmp     byte ptr [r14+110h], 0
0x18007ad8f  jz      short loc_18007ADB8
0x18007ad91  mov     qword ptr [rsi], 0
0x18007ad98  mov     qword ptr [rsi+8], 0
0x18007ada0  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18007ada4  test    rcx, rcx
0x18007ada7  jz      loc_18007AEA7
0x18007adad  call    cs:__imp_LeaveCriticalSection
0x18007adb3  jmp     loc_18007AEA7
0x18007adb8  mov     ecx, 78h ; 'x'; Size
0x18007adbd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007adc2  mov     rdi, rax
0x18007adc5  mov     [rbp+57h+var_98], rax
0x18007adc9  xorps   xmm0, xmm0
0x18007adcc  movups  xmmword ptr [rax], xmm0
0x18007adcf  mov     dword ptr [rax+8], 1
0x18007add6  mov     dword ptr [rax+0Ch], 1
0x18007addd  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable'
0x18007ade4  mov     [rdi], rax
0x18007ade7  lea     rbx, [rdi+10h]
0x18007adeb  mov     rdx, r15
0x18007adee  mov     rcx, rbx
0x18007adf1  call    WcmCommon__ThreadPoolWaitableResult_unsigned_long___ThreadPoolWaitableResult_unsigned_long___ProxyManager__InternalSetProxyInformation____3____lambda_1___
0x18007adf6  nop
0x18007adf7  mov     [rbp+57h+var_98], rbx
0x18007adfb  mov     [rbp+57h+var_90], rdi
0x18007adff  lea     rdx, [rbp+57h+var_98]
0x18007ae03  lea     rcx, [rbp+57h+var_88]
0x18007ae07  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x18007ae0c  mov     rcx, [rbp+57h+var_90]; this
0x18007ae10  test    rcx, rcx
0x18007ae13  jz      short loc_18007AE1A
0x18007ae15  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007ae1a  lea     rdx, [rbp+57h+var_88]
0x18007ae1e  cmp     dword ptr [r14], 1
0x18007ae22  jnz     short loc_18007AE4F
0x18007ae24  lea     rcx, [rbp+57h+var_98]
0x18007ae28  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x18007ae2d  nop
0x18007ae2e  lea     rdx, [rbp+57h+var_98]
0x18007ae32  lea     rcx, [r14+0C0h]
0x18007ae39  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x18007ae3e  nop
0x18007ae3f  mov     rcx, [rbp+57h+var_90]; this
0x18007ae43  test    rcx, rcx
0x18007ae46  jz      short loc_18007AE74
0x18007ae48  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007ae4d  jmp     short loc_18007AE74
0x18007ae4f  lea     rcx, [rbp+57h+var_70]
0x18007ae53  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x18007ae58  nop
0x18007ae59  lea     rdx, [rbp+57h+var_70]
0x18007ae5d  lea     rcx, [r14+0E8h]
0x18007ae64  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x18007ae69  nop
0x18007ae6a  lea     rcx, [rbp+57h+var_70]
0x18007ae6e  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x18007ae73  nop
0x18007ae74  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18007ae78  test    rcx, rcx
0x18007ae7b  jz      short loc_18007AE83
0x18007ae7d  call    cs:__imp_LeaveCriticalSection
0x18007ae83  lock inc qword ptr [r14+88h]
0x18007ae8b  mov     rcx, [r14+80h]; pwk
0x18007ae92  call    cs:__imp_SubmitThreadpoolWork
0x18007ae98  mov     rax, qword ptr [rbp+57h+var_88]
0x18007ae9c  mov     [rsi], rax
0x18007ae9f  mov     rax, qword ptr [rbp+57h+var_88+8]
0x18007aea3  mov     [rsi+8], rax
0x18007aea7  mov     rax, rsi
0x18007aeaa  mov     rbx, [rsp+0C0h+arg_18]
0x18007aeb2  add     rsp, 0A0h
0x18007aeb9  pop     r15
0x18007aebb  pop     r14
0x18007aebd  pop     rdi
0x18007aebe  pop     rsi
0x18007aebf  pop     rbp
0x18007aec0  retn
```
