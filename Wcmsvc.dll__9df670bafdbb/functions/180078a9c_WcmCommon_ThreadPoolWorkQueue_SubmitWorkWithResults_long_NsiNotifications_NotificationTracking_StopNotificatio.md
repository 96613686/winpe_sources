# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults<long,`NsiNotifications::NotificationTracking::StopNotifications(void)'::`2'::_lambda_1_>(`NsiNotifications::NotificationTracking::StopNotifications(void)'::`2'::_lambda_1_ &&)

- ea: `0x180078a9c`
- end: `0x180078c19`
- name: `??$SubmitWorkWithResults@JV_lambda_1_@?1??StopNotifications@NotificationTracking@NsiNotifications@@QEAAXXZ@@ThreadPoolWorkQueue@WcmCommon@@QEAA?AV?$shared_ptr@V?$ThreadPoolWaitableResult@J@WcmCommon@@@std@@$$QEAV_lambda_1_@?1??StopNotifications@NotificationTracking@NsiNotifications@@QEAAXXZ@@Z`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009864c`

## callees

- `0x180007ff8`
- `0x180008394`
- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x180027630`
- `0x18006de30`
- `0x180078a9c`
- `0x180078c20`
- `0x18008534c`
- `0x180098260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078b05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078bd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078b05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078bd5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180078bea`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180078bea`

## pseudocode

```c
_QWORD *__fastcall ___SubmitWorkWithResults_JV_lambda_1___1__StopNotifications_NotificationTracking_NsiNotifications__QEAAXXZ__ThreadPoolWorkQueue_WcmCommon__QEAA_AV__shared_ptr_V__ThreadPoolWaitableResult_J_WcmCommon___std____QEAV_lambda_1___1__StopNotifications_NotificationTracking_NsiNotifications__QEAAXXZ__Z(
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
    ____0V_lambda_1___1__StopNotifications_NotificationTracking_NsiNotifications__QEAAXXZ____ThreadPoolWaitableResult_J_WcmCommon__QEAA___QEAV_lambda_1___1__StopNotifications_NotificationTracking_NsiNotifications__QEAAXXZ__Z(
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
0x180078a9c  mov     [rsp-8+arg_10], rbx
0x180078aa1  push    rbp
0x180078aa2  push    rsi
0x180078aa3  push    rdi
0x180078aa4  push    r14
0x180078aa6  push    r15
0x180078aa8  lea     rbp, [rsp-37h]
0x180078aad  sub     rsp, 0A0h
0x180078ab4  mov     r15, r8
0x180078ab7  mov     rsi, rdx
0x180078aba  mov     r14, rcx
0x180078abd  mov     [rbp+57h+lpCriticalSection], rdx
0x180078ac1  xorps   xmm1, xmm1
0x180078ac4  movdqu  [rbp+57h+var_88], xmm1
0x180078ac9  mov     [rbp+57h+lpCriticalSection], 0
0x180078ad1  lea     rdx, [rcx+8]
0x180078ad5  lea     rcx, [rbp+57h+lpCriticalSection]
0x180078ad9  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180078ade  nop
0x180078adf  cmp     byte ptr [r14+110h], 0
0x180078ae7  jz      short loc_180078B10
0x180078ae9  mov     qword ptr [rsi], 0
0x180078af0  mov     qword ptr [rsi+8], 0
0x180078af8  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180078afc  test    rcx, rcx
0x180078aff  jz      loc_180078BFF
0x180078b05  call    cs:__imp_LeaveCriticalSection
0x180078b0b  jmp     loc_180078BFF
0x180078b10  mov     ecx, 78h ; 'x'; Size
0x180078b15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180078b1a  mov     rdi, rax
0x180078b1d  mov     [rbp+57h+var_98], rax
0x180078b21  xorps   xmm0, xmm0
0x180078b24  movups  xmmword ptr [rax], xmm0
0x180078b27  mov     dword ptr [rax+8], 1
0x180078b2e  mov     dword ptr [rax+0Ch], 1
0x180078b35  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<bool>>::`vftable'
0x180078b3c  mov     [rdi], rax
0x180078b3f  lea     rbx, [rdi+10h]
0x180078b43  mov     rdx, r15
0x180078b46  mov     rcx, rbx
0x180078b49  call    ??$?0V_lambda_1_@?1??StopNotifications@NotificationTracking@NsiNotifications@@QEAAXXZ@@?$ThreadPoolWaitableResult@J@WcmCommon@@QEAA@$$QEAV_lambda_1_@?1??StopNotifications@NotificationTracking@NsiNotifications@@QEAAXXZ@@Z; WcmCommon::ThreadPoolWaitableResult<long>::ThreadPoolWaitableResult<long>(`NsiNotifications::NotificationTracking::StopNotifications(void)'::`2'::_lambda_1_ &&)
0x180078b4e  nop
0x180078b4f  mov     [rbp+57h+var_98], rbx
0x180078b53  mov     [rbp+57h+var_90], rdi
0x180078b57  lea     rdx, [rbp+57h+var_98]
0x180078b5b  lea     rcx, [rbp+57h+var_88]
0x180078b5f  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>> &&)
0x180078b64  mov     rcx, [rbp+57h+var_90]; this
0x180078b68  test    rcx, rcx
0x180078b6b  jz      short loc_180078B72
0x180078b6d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180078b72  lea     rdx, [rbp+57h+var_88]
0x180078b76  cmp     dword ptr [r14], 1
0x180078b7a  jnz     short loc_180078BA7
0x180078b7c  lea     rcx, [rbp+57h+var_98]
0x180078b80  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x180078b85  nop
0x180078b86  lea     rdx, [rbp+57h+var_98]
0x180078b8a  lea     rcx, [r14+0C0h]
0x180078b91  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x180078b96  nop
0x180078b97  mov     rcx, [rbp+57h+var_90]; this
0x180078b9b  test    rcx, rcx
0x180078b9e  jz      short loc_180078BCC
0x180078ba0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180078ba5  jmp     short loc_180078BCC
0x180078ba7  lea     rcx, [rbp+57h+var_70]
0x180078bab  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x180078bb0  nop
0x180078bb1  lea     rdx, [rbp+57h+var_70]
0x180078bb5  lea     rcx, [r14+0E8h]
0x180078bbc  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x180078bc1  nop
0x180078bc2  lea     rcx, [rbp+57h+var_70]
0x180078bc6  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x180078bcb  nop
0x180078bcc  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180078bd0  test    rcx, rcx
0x180078bd3  jz      short loc_180078BDB
0x180078bd5  call    cs:__imp_LeaveCriticalSection
0x180078bdb  lock inc qword ptr [r14+88h]
0x180078be3  mov     rcx, [r14+80h]; pwk
0x180078bea  call    cs:__imp_SubmitThreadpoolWork
0x180078bf0  mov     rax, qword ptr [rbp+57h+var_88]
0x180078bf4  mov     [rsi], rax
0x180078bf7  mov     rax, qword ptr [rbp+57h+var_88+8]
0x180078bfb  mov     [rsi+8], rax
0x180078bff  mov     rax, rsi
0x180078c02  mov     rbx, [rsp+0C0h+arg_10]
0x180078c0a  add     rsp, 0A0h
0x180078c11  pop     r15
0x180078c13  pop     r14
0x180078c15  pop     rdi
0x180078c16  pop     rsi
0x180078c17  pop     rbp
0x180078c18  retn
```
