# CancellationTokenProvider::CancellationTokenProvider(std::vector<wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>>> const &)

- ea: `0x1400588b0`
- end: `0x140058a3c`
- name: `??0CancellationTokenProvider@@QEAA@AEBV?$vector@V?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@Z`
- size: `396`
- prototype: `CancellationTokenProvider *__fastcall(CancellationTokenProvider *this, __int64 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401bc4d0`

## callees

- `0x14002871c`
- `0x1400587d8`
- `0x1400588b0`
- `0x140058a44`
- `0x140058a98`
- `0x140058aec`
- `0x140059880`
- `0x140059948`
- `0x14005b628`
- `0x14006af38`
- `0x140132940`
- `0x1402c2010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1400589c9`
- `msvcp_win!_Mtx_unlock` at `0x1400589c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140058996`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140058996`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140058965`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140058965`

## string_xrefs

- `0x1400589fa`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`
- `0x140058a12`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`
- `0x140058a2a`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CancellationTokenProvider *__fastcall CancellationTokenProvider::CancellationTokenProvider(
        CancellationTokenProvider *this,
        __int64 **a2)
{
  __int64 *v4; // rsi
  __int64 *v5; // r15
  __int64 v6; // r14
  __int64 (__fastcall *v7)(__int64, HANDLE *); // rbx
  int v8; // eax
  PTP_WAIT ThreadpoolWait; // rax
  int v11; // [rsp+20h] [rbp-40h]
  HANDLE h[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v13; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v11 = (int)this;
  CancellationTokenProvider::CancellationTokenProvider(this);
  std::_Mutex_base::lock(this);
  v4 = *a2;
  v5 = a2[1];
  while ( v4 != v5 )
  {
    v6 = *v4;
    if ( !*v4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecore\\vm\\common\\cancellation\\cancellationtokenprovider.cpp",
        (const char *)0x80004003LL,
        v11);
    *(_OWORD *)h = 0;
    v13 = 0;
    v7 = *(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v6 + 24LL);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &h[1],
      0);
    v8 = v7(v6, &h[1]);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"onecore\\vm\\common\\cancellation\\cancellationtokenprovider.cpp",
        (const char *)(unsigned int)v8,
        v11);
    wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>::operator=(&v13, v4);
    ThreadpoolWait = CreateThreadpoolWait(lambda_e4ffa3337851658bfdbd92f22338e347_::_lambda_invoker_cdecl_, this, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
      h,
      ThreadpoolWait);
    if ( !h[0] )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecore\\vm\\common\\cancellation\\cancellationtokenprovider.cpp",
        (const char *)retaddr);
    SetThreadpoolWait((PTP_WAIT)h[0], h[1], 0);
    std::vector<CancellationTokenProvider::TrackedDetails>::push_back((char *)this + 96, h);
    CancellationTokenProvider::TrackedDetails::~TrackedDetails((CancellationTokenProvider::TrackedDetails *)h);
    ++v4;
  }
  _Mtx_unlock(this);
  return this;
}

```

## disassembly

```asm
0x1400588b0  mov     [rsp-28h+arg_10], rbx
0x1400588b5  push    rbp
0x1400588b6  push    rsi
0x1400588b7  push    rdi
0x1400588b8  push    r14
0x1400588ba  push    r15
0x1400588bc  mov     rbp, rsp
0x1400588bf  sub     rsp, 60h
0x1400588c3  mov     rax, cs:__security_cookie
0x1400588ca  xor     rax, rsp
0x1400588cd  mov     [rbp+var_10], rax
0x1400588d1  mov     rbx, rdx
0x1400588d4  mov     rdi, rcx
0x1400588d7  mov     qword ptr [rbp+var_40], rcx
0x1400588db  call    ??0CancellationTokenProvider@@QEAA@XZ; CancellationTokenProvider::CancellationTokenProvider(void)
0x1400588e0  nop
0x1400588e1  mov     [rbp+var_30], rdi
0x1400588e5  mov     rcx, rdi; this
0x1400588e8  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1400588ed  nop
0x1400588ee  mov     rsi, [rbx]
0x1400588f1  mov     r15, [rbx+8]
0x1400588f5  jmp     loc_1400589BD
0x1400588fa  mov     r14, [rsi]
0x1400588fd  test    r14, r14
0x140058900  setz    al
0x140058903  mov     rcx, [rbp+28h]; this
0x140058907  test    al, al
0x140058909  jnz     loc_140058A24
0x14005890f  xorps   xmm0, xmm0
0x140058912  movdqu  xmmword ptr [rbp+h], xmm0
0x140058917  mov     [rbp+var_18], 0
0x14005891f  mov     rax, [r14]
0x140058922  mov     rbx, [rax+18h]
0x140058926  xor     edx, edx
0x140058928  lea     rcx, [rbp+h+8]
0x14005892c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140058931  lea     rdx, [rbp+h+8]
0x140058935  mov     rcx, r14
0x140058938  mov     rax, rbx
0x14005893b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058940  mov     rcx, [rbp+28h]; this
0x140058944  test    eax, eax
0x140058946  js      loc_140058A0F
0x14005894c  mov     rdx, rsi
0x14005894f  lea     rcx, [rbp+var_18]
0x140058953  call    ??4?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>::operator=(wil::com_ptr_t<ICancellationToken,wil::err_exception_policy> const &)
0x140058958  xor     r8d, r8d; pcbe
0x14005895b  mov     rdx, rdi; pv
0x14005895e  lea     rcx, _lambda_e4ffa3337851658bfdbd92f22338e347____lambda_invoker_cdecl_; pfnwa
0x140058965  call    cs:__imp_CreateThreadpoolWait
0x14005896c  nop     dword ptr [rax+rax+00h]
0x140058971  mov     rdx, rax
0x140058974  lea     rcx, [rbp+h]
0x140058978  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x14005897d  mov     rcx, [rbp+h]; pwa
0x140058981  test    rcx, rcx
0x140058984  setz    al
0x140058987  mov     r9, [rbp+28h]; char *
0x14005898b  test    al, al
0x14005898d  jnz     short loc_1400589FA
0x14005898f  xor     r8d, r8d; pftTimeout
0x140058992  mov     rdx, [rbp+h+8]; h
0x140058996  call    cs:__imp_SetThreadpoolWait
0x14005899d  nop     dword ptr [rax+rax+00h]
0x1400589a2  lea     rcx, [rdi+60h]
0x1400589a6  lea     rdx, [rbp+h]
0x1400589aa  call    ?push_back@?$vector@UTrackedDetails@CancellationTokenProvider@@V?$allocator@UTrackedDetails@CancellationTokenProvider@@@std@@@std@@QEAAX$$QEAUTrackedDetails@CancellationTokenProvider@@@Z; std::vector<CancellationTokenProvider::TrackedDetails>::push_back(CancellationTokenProvider::TrackedDetails &&)
0x1400589af  nop
0x1400589b0  lea     rcx, [rbp+h]; this
0x1400589b4  call    ??1TrackedDetails@CancellationTokenProvider@@QEAA@XZ; CancellationTokenProvider::TrackedDetails::~TrackedDetails(void)
0x1400589b9  add     rsi, 8
0x1400589bd  cmp     rsi, r15
0x1400589c0  jnz     loc_1400588FA
0x1400589c6  mov     rcx, rdi; _Mtx_t
0x1400589c9  call    cs:__imp__Mtx_unlock
0x1400589d0  nop     dword ptr [rax+rax+00h]
0x1400589d5  nop
0x1400589d6  mov     rax, rdi
0x1400589d9  mov     rcx, [rbp+var_10]
0x1400589dd  xor     rcx, rsp; StackCookie
0x1400589e0  call    __security_check_cookie
0x1400589e5  mov     rbx, [rsp+60h+arg_10]
0x1400589ed  add     rsp, 60h
0x1400589f1  pop     r15
0x1400589f3  pop     r14
0x1400589f5  pop     rdi
0x1400589f6  pop     rsi
0x1400589f7  pop     rbp
0x1400589f8  retn
0x1400589fa  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x140058a01  mov     edx, 9Ch; void *
0x140058a06  mov     rcx, r9; this
0x140058a09  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140058a0f  mov     r9d, eax; char *
0x140058a12  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x140058a19  mov     edx, 94h; void *
0x140058a1e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140058a24  mov     r9d, 80004003h; char *
0x140058a2a  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x140058a31  mov     edx, 91h; void *
0x140058a36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
