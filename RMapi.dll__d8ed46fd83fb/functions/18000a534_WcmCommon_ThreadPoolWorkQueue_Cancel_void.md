# WcmCommon::ThreadPoolWorkQueue::Cancel(void)

- ea: `0x18000a534`
- end: `0x18000a69a`
- name: `?Cancel@ThreadPoolWorkQueue@WcmCommon@@QEAAXXZ`
- size: `358`
- prototype: `void __fastcall(WcmCommon::ThreadPoolWorkQueue *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004a20`
- `0x18000a470`
- `0x18002056c`

## callees

- `0x180005530`
- `0x18000a534`
- `0x18000a6fc`
- `0x18000a75c`
- `0x18000b8fc`
- `0x18000d2a0`
- `0x18001958c`
- `0x18001966c`
- `0x1800196c0`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a66f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a66f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a565`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a565`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::Cancel(WcmCommon::ThreadPoolWorkQueue *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  bool v3; // zf
  __int64 v4; // rbx
  __int64 v5; // r15
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // r14
  _BYTE *v9; // rax
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+20h] [rbp-20h] BYREF
  char *v11; // [rsp+28h] [rbp-18h] BYREF
  __int64 v12; // [rsp+30h] [rbp-10h]

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v10 = v1;
  v3 = *((_QWORD *)this + 16) == 0;
  *((_BYTE *)this + 272) = 1;
  if ( !v3 )
  {
    v3 = *(_DWORD *)this == 1;
    v12 = 0;
    if ( v3 )
    {
      v4 = *((_QWORD *)this + 27);
      v5 = v4 + *((_QWORD *)this + 28);
      v11 = (char *)this + 192;
      while ( 1 )
      {
        v12 = v4;
        if ( v4 == v5 )
          break;
        v6 = *(_QWORD *)std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>>::operator*(&v11);
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        ++v4;
      }
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Tidy((char *)this + 192);
      std::deque<std::function<void (void)>>::_Tidy((char *)this + 152);
    }
    else
    {
      v7 = *((_QWORD *)this + 32);
      v8 = v7 + *((_QWORD *)this + 33);
      v11 = (char *)this + 232;
      while ( 1 )
      {
        v12 = v7;
        if ( v7 == v8 )
          break;
        v9 = (_BYTE *)std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>>::operator*(&v11);
        if ( v9 && v9[64] == 1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 16LL))(*(_QWORD *)v9);
        ++v7;
      }
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Tidy((char *)this + 232);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
      &v10,
      0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      (struct _TP_WORK **)this + 16,
      0);
    WcmCommon::details::TPEnvironment::reset((WcmCommon::ThreadPoolWorkQueue *)((char *)this + 48));
    v1 = v10;
    _InterlockedExchange64((volatile __int64 *)this + 17, 0);
  }
  if ( v1 )
    LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18000a534  mov     [rsp-28h+arg_8], rbx
0x18000a539  mov     [rsp-28h+arg_10], rsi
0x18000a53e  push    rbp
0x18000a53f  push    rdi
0x18000a540  push    r12
0x18000a542  push    r14
0x18000a544  push    r15
0x18000a546  mov     rbp, rsp
0x18000a549  sub     rsp, 40h
0x18000a54d  mov     rax, cs:__security_cookie
0x18000a554  xor     rax, rsp
0x18000a557  mov     [rbp+var_8], rax
0x18000a55b  lea     rbx, [rcx+8]
0x18000a55f  mov     rdi, rcx
0x18000a562  mov     rcx, rbx; lpCriticalSection
0x18000a565  call    cs:__imp_EnterCriticalSection
0x18000a56b  lea     r12, [rdi+80h]
0x18000a572  mov     [rbp+var_20], rbx
0x18000a576  cmp     qword ptr [r12], 0
0x18000a57b  lea     r14, [rdi+98h]
0x18000a582  mov     byte ptr [r14+78h], 1
0x18000a587  jz      loc_18000A667
0x18000a58d  cmp     dword ptr [rdi], 1
0x18000a590  mov     [rbp+var_10], 0
0x18000a598  jnz     short loc_18000A5ED
0x18000a59a  lea     rsi, [rdi+0C0h]
0x18000a5a1  mov     rbx, [rsi+18h]
0x18000a5a5  mov     r15, [rsi+20h]
0x18000a5a9  add     r15, rbx
0x18000a5ac  mov     [rbp+var_18], rsi
0x18000a5b0  mov     [rbp+var_10], rbx
0x18000a5b4  cmp     rbx, r15
0x18000a5b7  jz      short loc_18000A5DB
0x18000a5b9  lea     rcx, [rbp+var_18]
0x18000a5bd  call    ??D?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@std@@@std@@@std@@QEBAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@XZ; std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>>::operator*(void)
0x18000a5c2  mov     rcx, [rax]
0x18000a5c5  test    rcx, rcx
0x18000a5c8  jz      short loc_18000A5D6
0x18000a5ca  mov     rax, [rcx]
0x18000a5cd  mov     rax, [rax+10h]
0x18000a5d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5d6  inc     rbx
0x18000a5d9  jmp     short loc_18000A5B0
0x18000a5db  mov     rcx, rsi
0x18000a5de  call    ?_Tidy@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@AEAAXXZ; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Tidy(void)
0x18000a5e3  mov     rcx, r14
0x18000a5e6  call    ?_Tidy@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAXXZ; std::deque<std::function<void (void)>>::_Tidy(void)
0x18000a5eb  jmp     short loc_18000A63C
0x18000a5ed  lea     rsi, [rdi+0E8h]
0x18000a5f4  mov     rbx, [rsi+18h]
0x18000a5f8  mov     r14, [rsi+20h]
0x18000a5fc  add     r14, rbx
0x18000a5ff  mov     [rbp+var_18], rsi
0x18000a603  mov     [rbp+var_10], rbx
0x18000a607  cmp     rbx, r14
0x18000a60a  jz      short loc_18000A634
0x18000a60c  lea     rcx, [rbp+var_18]
0x18000a610  call    ??D?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@std@@@std@@@std@@QEBAAEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@XZ; std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>>::operator*(void)
0x18000a615  test    rax, rax
0x18000a618  jz      short loc_18000A62F
0x18000a61a  cmp     byte ptr [rax+40h], 1
0x18000a61e  jnz     short loc_18000A62F
0x18000a620  mov     rcx, [rax]
0x18000a623  mov     rax, [rcx]
0x18000a626  mov     rax, [rax+10h]
0x18000a62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a62f  inc     rbx
0x18000a632  jmp     short loc_18000A603
0x18000a634  mov     rcx, rsi
0x18000a637  call    ?_Tidy@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAXXZ; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Tidy(void)
0x18000a63c  xor     edx, edx
0x18000a63e  lea     rcx, [rbp+var_20]
0x18000a642  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x18000a647  xor     edx, edx
0x18000a649  mov     rcx, r12
0x18000a64c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18000a651  lea     rcx, [rdi+30h]; this
0x18000a655  call    ?reset@TPEnvironment@details@WcmCommon@@QEAAXXZ; WcmCommon::details::TPEnvironment::reset(void)
0x18000a65a  mov     rbx, [rbp+var_20]
0x18000a65e  xor     eax, eax
0x18000a660  xchg    rax, [rdi+88h]
0x18000a667  test    rbx, rbx
0x18000a66a  jz      short loc_18000A675
0x18000a66c  mov     rcx, rbx; lpCriticalSection
0x18000a66f  call    cs:__imp_LeaveCriticalSection
0x18000a675  mov     rcx, [rbp+var_8]
0x18000a679  xor     rcx, rsp; StackCookie
0x18000a67c  call    __security_check_cookie
0x18000a681  lea     r11, [rsp+40h+var_s0]
0x18000a686  mov     rbx, [r11+38h]
0x18000a68a  mov     rsi, [r11+40h]
0x18000a68e  mov     rsp, r11
0x18000a691  pop     r15
0x18000a693  pop     r14
0x18000a695  pop     r12
0x18000a697  pop     rdi
0x18000a698  pop     rbp
0x18000a699  retn
```
