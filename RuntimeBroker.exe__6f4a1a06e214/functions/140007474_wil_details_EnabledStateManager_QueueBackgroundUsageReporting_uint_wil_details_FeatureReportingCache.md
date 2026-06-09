# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140007474`
- end: `0x140007551`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `221`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140005238`

## callees

- `0x140003b84`
- `0x140003e30`
- `0x140007474`
- `0x1400077f4`
- `0x1400082f4`
- `0x1400085c4`
- `0x14000ab14`
- `0x14000ad60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400074a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400074a7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000750a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000750a`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  int Ptr; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  char v9; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v10; // [rsp+58h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v10 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v8[0] = 8482243;
        v8[1] = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x140007474  mov     [rsp+arg_8], rbx
0x140007479  mov     [rsp+arg_10], rsi
0x14000747e  push    rdi
0x14000747f  sub     rsp, 30h
0x140007483  mov     eax, [rcx]
0x140007485  mov     rsi, r8
0x140007488  mov     rdi, rcx
0x14000748b  test    eax, eax
0x14000748d  jz      loc_140007541
0x140007493  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140007498  test    al, al
0x14000749a  jnz     loc_140007541
0x1400074a0  lea     rbx, [rdi+8]
0x1400074a4  mov     rcx, rbx; SRWLock
0x1400074a7  call    cs:__imp_AcquireSRWLockExclusive
0x1400074ad  mov     eax, [rdi]
0x1400074af  mov     [rsp+38h+arg_18], rbx
0x1400074b4  test    eax, eax
0x1400074b6  jz      short loc_140007537
0x1400074b8  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1400074bd  test    al, al
0x1400074bf  jnz     short loc_140007537
0x1400074c1  lea     rcx, [rdi+20h]; this
0x1400074c5  mov     [rsp+38h+var_18], 816DC3h
0x1400074ce  mov     r8d, 10h; unsigned __int64
0x1400074d4  mov     [rsp+38h+var_10], rsi
0x1400074d9  lea     rdx, [rsp+38h+var_18]; void *
0x1400074de  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1400074e3  cmp     byte ptr [rdi+18h], 0
0x1400074e7  jnz     short loc_140007537
0x1400074e9  lea     rbx, [rdi+10h]
0x1400074ed  cmp     qword ptr [rbx], 0
0x1400074f1  jnz     short loc_140007525
0x1400074f3  lea     rcx, [rsp+38h+arg_0]; this
0x1400074f8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400074fd  xor     r8d, r8d; pcbe
0x140007500  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140007507  mov     rdx, rdi; pv
0x14000750a  call    cs:__imp_CreateThreadpoolTimer
0x140007510  mov     rdx, rax
0x140007513  mov     rcx, rbx
0x140007516  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000751b  lea     rcx, [rsp+38h+arg_0]; this
0x140007520  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140007525  mov     r8d, 493E0h
0x14000752b  lea     rdx, [rdi+18h]
0x14000752f  mov     rcx, rbx
0x140007532  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140007537  lea     rcx, [rsp+38h+arg_18]
0x14000753c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140007541  mov     rbx, [rsp+38h+arg_8]
0x140007546  mov     rsi, [rsp+38h+arg_10]
0x14000754b  add     rsp, 30h
0x14000754f  pop     rdi
0x140007550  retn
```
