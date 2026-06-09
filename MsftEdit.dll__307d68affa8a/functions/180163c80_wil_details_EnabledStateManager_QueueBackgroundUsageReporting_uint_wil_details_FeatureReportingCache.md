# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180163c80`
- end: `0x180163d58`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180164618`

## callees

- `0x18012ae94`
- `0x1801402f4`
- `0x18014051c`
- `0x180140808`
- `0x180140e24`
- `0x18014491c`
- `0x180144a38`
- `0x180163c80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180163cb2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180163cb2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180163d14`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180163d14`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int Ptr; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-20h]
  char v11; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    Ptr = (int)pv->Ptr;
    v12 = pv + 1;
    if ( Ptr )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v9[0] = a2;
        v9[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v9, 0x10u);
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
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x180163c80  mov     [rsp+arg_8], rbx
0x180163c85  push    rbp
0x180163c86  push    rsi
0x180163c87  push    rdi
0x180163c88  sub     rsp, 30h
0x180163c8c  mov     eax, [rcx]
0x180163c8e  mov     rsi, r8
0x180163c91  mov     ebp, edx
0x180163c93  mov     rdi, rcx
0x180163c96  test    eax, eax
0x180163c98  jz      loc_180163D4B
0x180163c9e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180163ca3  test    al, al
0x180163ca5  jnz     loc_180163D4B
0x180163cab  lea     rbx, [rdi+8]
0x180163caf  mov     rcx, rbx; SRWLock
0x180163cb2  call    cs:__imp_AcquireSRWLockExclusive
0x180163cb8  mov     eax, [rdi]
0x180163cba  mov     [rsp+48h+arg_18], rbx
0x180163cbf  test    eax, eax
0x180163cc1  jz      short loc_180163D41
0x180163cc3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180163cc8  test    al, al
0x180163cca  jnz     short loc_180163D41
0x180163ccc  xor     eax, eax
0x180163cce  mov     [rsp+48h+var_28], ebp
0x180163cd2  lea     rcx, [rdi+20h]; this
0x180163cd6  mov     [rsp+48h+var_24], eax
0x180163cda  lea     rdx, [rsp+48h+var_28]; void *
0x180163cdf  mov     [rsp+48h+var_20], rsi
0x180163ce4  lea     r8d, [rax+10h]; unsigned __int64
0x180163ce8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180163ced  cmp     byte ptr [rdi+18h], 0
0x180163cf1  jnz     short loc_180163D41
0x180163cf3  lea     rbx, [rdi+10h]
0x180163cf7  cmp     qword ptr [rbx], 0
0x180163cfb  jnz     short loc_180163D2F
0x180163cfd  lea     rcx, [rsp+48h+arg_0]; this
0x180163d02  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180163d07  xor     r8d, r8d; pcbe
0x180163d0a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180163d11  mov     rdx, rdi; pv
0x180163d14  call    cs:__imp_CreateThreadpoolTimer
0x180163d1a  mov     rdx, rax
0x180163d1d  mov     rcx, rbx
0x180163d20  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180163d25  lea     rcx, [rsp+48h+arg_0]; this
0x180163d2a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180163d2f  mov     r8d, 493E0h
0x180163d35  lea     rdx, [rdi+18h]
0x180163d39  mov     rcx, rbx
0x180163d3c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180163d41  lea     rcx, [rsp+48h+arg_18]
0x180163d46  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180163d4b  mov     rbx, [rsp+48h+arg_8]
0x180163d50  add     rsp, 30h
0x180163d54  pop     rdi
0x180163d55  pop     rsi
0x180163d56  pop     rbp
0x180163d57  retn
```
