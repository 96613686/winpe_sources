# WcmCommon::ThreadPoolWorkQueue::WorkCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18000c950`
- end: `0x18000cb07`
- name: `?WorkCallback@ThreadPoolWorkQueue@WcmCommon@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `439`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006df8`
- `0x180009380`
- `0x18000c2a4`
- `0x18000c950`
- `0x18000cb10`
- `0x18000cb40`
- `0x18000cb68`
- `0x18000cbac`
- `0x18000cbf0`
- `0x18000cc14`
- `0x18000cc30`
- `0x18000d2a0`
- `0x18000df88`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18000ca6b`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18000ca6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ca62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ca62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c98e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c98e`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::WorkCallback(
        struct _TP_CALLBACK_INSTANCE *a1,
        char *a2,
        struct _TP_WORK *a3)
{
  char *v4; // rbx
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // rbx
  HANDLE CurrentThread; // rax
  char *v9; // [rsp+20h] [rbp-39h] BYREF
  void **pExceptionObject; // [rsp+28h] [rbp-31h] BYREF
  __int128 v11; // [rsp+30h] [rbp-29h]
  _QWORD v12[8]; // [rsp+40h] [rbp-19h] BYREF
  char v13; // [rsp+80h] [rbp+27h]

  v12[7] = 0;
  v13 = 0;
  v4 = a2 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  v9 = v4;
  if ( *(_DWORD *)a2 != 1 )
  {
    if ( *((_QWORD *)a2 + 33) )
    {
      pExceptionObject = (void **)v12;
      *(_QWORD *)&v11 = std::deque<std::function<void (void)>>::front(a2 + 232);
      ____Visit_V_lambda_1___2__swap___variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__QEAAXAEAV34__Z_AEAV___Variant_storage___0A_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__4_____Variant_raw_visit1__00_std__SAX_K__QEAV_lambda_1___2__swap___variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1_QEAAXAEAV41__Z_AEAV___Variant_storage___0A_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1__Z(
        v13 + 1LL,
        &pExceptionObject,
        v12);
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::pop_front(a2 + 232);
      goto LABEL_9;
    }
    goto LABEL_7;
  }
  if ( !*((_QWORD *)a2 + 28) )
  {
    if ( *((_QWORD *)a2 + 23) )
    {
      v7 = std::deque<std::function<void (void)>>::front(a2 + 152);
      std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(v12);
      v13 = -1;
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Emplace_valueless<0,std::function<void (void)>>(
        v12,
        v7);
      std::deque<std::function<void (void)>>::pop_front(a2 + 152);
      goto LABEL_9;
    }
LABEL_7:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
    goto LABEL_15;
  }
  v5 = std::deque<std::function<void (void)>>::front(a2 + 192);
  std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(v12);
  v13 = -1;
  std::_Construct_in_place<std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>,std::integral_constant<unsigned __int64,1>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(
    v12,
    v6,
    v5);
  v13 = 1;
  std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::pop_front(a2 + 192);
LABEL_9:
  CurrentThread = GetCurrentThread();
  _InterlockedExchange((volatile __int32 *)a2 + 36, GetThreadId(CurrentThread));
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
  if ( v13 == 1 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12[0] + 8LL))(v12[0]);
  }
  else
  {
    if ( v13 )
    {
      v11 = 0;
      pExceptionObject = &std::bad_variant_access::`vftable';
      throw (std::bad_variant_access *)&pExceptionObject;
    }
    std::_Func_class<void,>::operator()(v12);
  }
  _InterlockedDecrement64((volatile signed __int64 *)a2 + 17);
  _InterlockedExchange((volatile __int32 *)a2 + 36, 0);
LABEL_15:
  std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(v12);
}

```

## disassembly

```asm
0x18000c950  mov     [rsp-8+arg_0], rbx
0x18000c955  mov     [rsp-8+arg_10], rsi
0x18000c95a  push    rbp
0x18000c95b  push    rdi
0x18000c95c  push    r14
0x18000c95e  lea     rbp, [rsp-47h]
0x18000c963  sub     rsp, 0A0h
0x18000c96a  mov     rax, cs:__security_cookie
0x18000c971  xor     rax, rsp
0x18000c974  mov     [rbp+57h+var_20], rax
0x18000c978  mov     rdi, rdx
0x18000c97b  mov     [rbp+57h+var_38], 0
0x18000c983  mov     [rbp+57h+var_30], 0
0x18000c987  lea     rbx, [rdx+8]
0x18000c98b  mov     rcx, rbx; lpCriticalSection
0x18000c98e  call    cs:__imp_EnterCriticalSection
0x18000c994  mov     [rbp+57h+var_90], rbx
0x18000c998  lea     rsi, [rdi+98h]
0x18000c99f  cmp     dword ptr [rdi], 1
0x18000c9a2  jnz     short loc_18000CA1A
0x18000c9a4  cmp     qword ptr [rsi+48h], 0
0x18000c9a9  jz      short loc_18000C9E2
0x18000c9ab  lea     rcx, [rsi+28h]
0x18000c9af  call    ?front@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@2@XZ; std::deque<std::function<void (void)>>::front(void)
0x18000c9b4  mov     rbx, rax
0x18000c9b7  lea     rcx, [rbp+57h+var_70]
0x18000c9bb  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x18000c9c0  mov     [rbp+57h+var_30], 0FFh
0x18000c9c4  mov     r8, rbx
0x18000c9c7  lea     rcx, [rbp+57h+var_70]
0x18000c9cb  call    ??$_Construct_in_place@V?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@U?$integral_constant@_K$00@2@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@YAXAEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@0@$$QEAU?$integral_constant@_K$00@0@$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@0@@Z; std::_Construct_in_place<std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>,std::integral_constant<unsigned __int64,1>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &,std::integral_constant<unsigned __int64,1> &&,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x18000c9d0  mov     [rbp+57h+var_30], 1
0x18000c9d4  lea     rcx, [rsi+28h]
0x18000c9d8  call    ?pop_front@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAXXZ; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::pop_front(void)
0x18000c9dd  jmp     loc_18000CA62
0x18000c9e2  cmp     qword ptr [rdi+0B8h], 0
0x18000c9ea  jz      short loc_18000CA21
0x18000c9ec  mov     rcx, rsi
0x18000c9ef  call    ?front@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@2@XZ; std::deque<std::function<void (void)>>::front(void)
0x18000c9f4  mov     rbx, rax
0x18000c9f7  lea     rcx, [rbp+57h+var_70]
0x18000c9fb  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x18000ca00  mov     [rbp+57h+var_30], 0FFh
0x18000ca04  mov     rdx, rbx
0x18000ca07  lea     rcx, [rbp+57h+var_70]
0x18000ca0b  call    ??$_Emplace_valueless@$0A@V?$function@$$A6AXXZ@std@@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@AEAAAEAV?$function@$$A6AXXZ@1@$$QEAV21@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Emplace_valueless<0,std::function<void (void)>>(std::function<void (void)> &&)
0x18000ca10  mov     rcx, rsi
0x18000ca13  call    ?pop_front@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAXXZ; std::deque<std::function<void (void)>>::pop_front(void)
0x18000ca18  jmp     short loc_18000CA62
0x18000ca1a  cmp     qword ptr [rsi+70h], 0
0x18000ca1f  jnz     short loc_18000CA2F
0x18000ca21  lea     rcx, [rbp+57h+var_90]
0x18000ca25  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000ca2a  jmp     loc_18000CAD9
0x18000ca2f  lea     rax, [rbp+57h+var_70]
0x18000ca33  mov     [rbp+57h+pExceptionObject], rax
0x18000ca37  lea     rcx, [rsi+50h]
0x18000ca3b  call    ?front@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAAAEAV?$function@$$A6AXXZ@2@XZ; std::deque<std::function<void (void)>>::front(void)
0x18000ca40  mov     qword ptr [rbp+57h+var_80], rax
0x18000ca44  movsx   rcx, [rbp+57h+var_30]
0x18000ca49  inc     rcx
0x18000ca4c  lea     r8, [rbp+57h+var_70]
0x18000ca50  lea     rdx, [rbp+57h+pExceptionObject]
0x18000ca54  call    ??$_Visit@V_lambda_1_@?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXAEAV34@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@4@@?$_Variant_raw_visit1@$00@std@@SAX_K$$QEAV_lambda_1_@?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@QEAAXAEAV41@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::_Variant_raw_visit1<1>::_Visit<`std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::swap(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &)'::`3'::_lambda_1_,std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &>(unsigned __int64,`std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::swap(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &)'::`3'::_lambda_1_ &&,std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &)
0x18000ca59  lea     rcx, [rsi+50h]
0x18000ca5d  call    ?pop_front@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@QEAAXXZ; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::pop_front(void)
0x18000ca62  call    cs:__imp_GetCurrentThread
0x18000ca68  mov     rcx, rax; Thread
0x18000ca6b  call    cs:__imp_GetThreadId
0x18000ca71  xchg    eax, [rdi+90h]
0x18000ca77  lea     rcx, [rbp+57h+var_90]
0x18000ca7b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000ca80  mov     al, [rbp+57h+var_30]
0x18000ca83  cmp     al, 1
0x18000ca85  jnz     short loc_18000CA99
0x18000ca87  mov     rcx, [rbp+57h+var_70]
0x18000ca8b  mov     rax, [rcx]
0x18000ca8e  mov     rax, [rax+8]
0x18000ca92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca97  jmp     short loc_18000CAC9
0x18000ca99  test    al, al
0x18000ca9b  jz      short loc_18000CAC0
0x18000ca9d  xorps   xmm0, xmm0
0x18000caa0  movups  [rbp+57h+var_80], xmm0
0x18000caa4  lea     rax, ??_7bad_variant_access@std@@6B@; const std::bad_variant_access::`vftable'
0x18000caab  mov     [rbp+57h+pExceptionObject], rax
0x18000caaf  lea     rdx, _TI2?AVbad_variant_access@std@@; pThrowInfo
0x18000cab6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000caba  call    _CxxThrowException_0
0x18000cac0  lea     rcx, [rbp+57h+var_70]
0x18000cac4  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18000cac9  lock dec qword ptr [rdi+88h]
0x18000cad1  xor     eax, eax
0x18000cad3  xchg    eax, [rdi+90h]
0x18000cad9  lea     rcx, [rbp+57h+var_70]
0x18000cadd  call    ?_Destroy@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Destroy(void)
0x18000cae2  nop
0x18000cae3  mov     rcx, [rbp+57h+var_20]
0x18000cae7  xor     rcx, rsp; StackCookie
0x18000caea  call    __security_check_cookie
0x18000caef  lea     r11, [rsp+0B0h+var_10]
0x18000caf7  mov     rbx, [r11+20h]
0x18000cafb  mov     rsi, [r11+30h]
0x18000caff  mov     rsp, r11
0x18000cb02  pop     r14
0x18000cb04  pop     rdi
0x18000cb05  pop     rbp
0x18000cb06  retn
```
