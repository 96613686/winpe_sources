# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180006f34`
- end: `0x180007023`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `239`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000690c`

## callees

- `0x180006f34`
- `0x18005cb34`
- `0x18005d6b4`
- `0x18005dafc`
- `0x18005db40`
- `0x180071784`
- `0x180075e08`
- `0x180075ec8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006f66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006f66`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006fd0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006fd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD Src[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF
  char v11; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v10 = pv + 1;
    if ( !LODWORD(pv->Ptr) || wil::ProcessShutdownInProgress(v6) )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
    }
    else
    {
      Src[0] = a2;
      Src[1] = 0;
      v9 = a3;
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], Src, 0x10u);
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            &pv[2],
            ThreadpoolTimer);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
        }
        wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
    }
  }
}

```

## disassembly

```asm
0x180006f34  mov     [rsp+arg_8], rbx
0x180006f39  push    rbp
0x180006f3a  push    rsi
0x180006f3b  push    rdi
0x180006f3c  sub     rsp, 30h
0x180006f40  mov     rsi, r8
0x180006f43  mov     ebp, edx
0x180006f45  mov     rdi, rcx
0x180006f48  mov     eax, [rcx]
0x180006f4a  test    eax, eax
0x180006f4c  jz      loc_180007016
0x180006f52  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180006f57  test    al, al
0x180006f59  jnz     loc_180007016
0x180006f5f  lea     rbx, [rdi+8]
0x180006f63  mov     rcx, rbx; SRWLock
0x180006f66  call    cs:__imp_AcquireSRWLockExclusive
0x180006f6c  mov     [rsp+48h+arg_0], rbx
0x180006f71  mov     eax, [rdi]
0x180006f73  test    eax, eax
0x180006f75  jz      loc_18000700B
0x180006f7b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180006f80  test    al, al
0x180006f82  jnz     loc_18000700B
0x180006f88  mov     [rsp+48h+Src], ebp
0x180006f8c  xor     eax, eax
0x180006f8e  mov     [rsp+48h+var_24], eax
0x180006f92  mov     [rsp+48h+var_20], rsi
0x180006f97  lea     rcx, [rdi+20h]; this
0x180006f9b  lea     r8d, [rax+10h]; Size
0x180006f9f  lea     rdx, [rsp+48h+Src]; Src
0x180006fa4  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180006fa9  cmp     byte ptr [rdi+18h], 0
0x180006fad  jnz     short loc_180006FFE
0x180006faf  lea     rbx, [rdi+10h]
0x180006fb3  cmp     qword ptr [rbx], 0
0x180006fb7  jnz     short loc_180006FEB
0x180006fb9  lea     rcx, [rsp+48h+arg_18]; this
0x180006fbe  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180006fc3  xor     r8d, r8d; pcbe
0x180006fc6  mov     rdx, rdi; pv
0x180006fc9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006fd0  call    cs:__imp_CreateThreadpoolTimer
0x180006fd6  mov     rdx, rax
0x180006fd9  mov     rcx, rbx
0x180006fdc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180006fe1  lea     rcx, [rsp+48h+arg_18]; this
0x180006fe6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180006feb  mov     r8d, 493E0h
0x180006ff1  lea     rdx, [rdi+18h]
0x180006ff5  mov     rcx, rbx
0x180006ff8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180006ffd  nop
0x180006ffe  lea     rcx, [rsp+48h+arg_0]
0x180007003  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007008  nop
0x180007009  jmp     short loc_180007016
0x18000700b  lea     rcx, [rsp+48h+arg_0]
0x180007010  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180007015  nop
0x180007016  mov     rbx, [rsp+48h+arg_8]
0x18000701b  add     rsp, 30h
0x18000701f  pop     rdi
0x180007020  pop     rsi
0x180007021  pop     rbp
0x180007022  retn
```
