# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18002da64`
- end: `0x18002db3d`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002eee8`

## callees

- `0x180029188`
- `0x1800293e4`
- `0x180029738`
- `0x18002a5d4`
- `0x18002d37c`
- `0x18002da64`
- `0x1800307b0`
- `0x1800308cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002da96`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002da96`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002daf8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002daf8`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( LODWORD(pv->Ptr) && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive(pv + 1);
    v11 = pv + 1;
    if ( LODWORD(pv->Ptr) )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], v8, 0x10u);
        if ( !LOBYTE(pv[3].Ptr) )
        {
          if ( !pv[2].Ptr )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              &pv[2],
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer(&pv[2], &pv[3], 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18002da64  mov     [rsp+arg_8], rbx
0x18002da69  push    rbp
0x18002da6a  push    rsi
0x18002da6b  push    rdi
0x18002da6c  sub     rsp, 30h
0x18002da70  mov     rsi, r8
0x18002da73  mov     ebp, edx
0x18002da75  mov     rdi, rcx
0x18002da78  mov     eax, [rcx]
0x18002da7a  test    eax, eax
0x18002da7c  jz      loc_18002DB30
0x18002da82  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002da87  test    al, al
0x18002da89  jnz     loc_18002DB30
0x18002da8f  lea     rbx, [rdi+8]
0x18002da93  mov     rcx, rbx; SRWLock
0x18002da96  call    cs:__imp_AcquireSRWLockExclusive
0x18002da9c  mov     [rsp+48h+arg_18], rbx
0x18002daa1  mov     eax, [rdi]
0x18002daa3  test    eax, eax
0x18002daa5  jz      short loc_18002DB25
0x18002daa7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002daac  test    al, al
0x18002daae  jnz     short loc_18002DB25
0x18002dab0  mov     [rsp+48h+var_28], ebp
0x18002dab4  xor     eax, eax
0x18002dab6  mov     [rsp+48h+var_24], eax
0x18002daba  mov     [rsp+48h+var_20], rsi
0x18002dabf  lea     rcx, [rdi+20h]; this
0x18002dac3  lea     r8d, [rax+10h]; unsigned __int64
0x18002dac7  lea     rdx, [rsp+48h+var_28]; void *
0x18002dacc  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002dad1  cmp     byte ptr [rdi+18h], 0
0x18002dad5  jnz     short loc_18002DB25
0x18002dad7  lea     rbx, [rdi+10h]
0x18002dadb  cmp     qword ptr [rbx], 0
0x18002dadf  jnz     short loc_18002DB13
0x18002dae1  lea     rcx, [rsp+48h+arg_0]; this
0x18002dae6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002daeb  xor     r8d, r8d; pcbe
0x18002daee  mov     rdx, rdi; pv
0x18002daf1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002daf8  call    cs:__imp_CreateThreadpoolTimer
0x18002dafe  mov     rdx, rax
0x18002db01  mov     rcx, rbx
0x18002db04  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002db09  lea     rcx, [rsp+48h+arg_0]; this
0x18002db0e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002db13  mov     r8d, 493E0h
0x18002db19  lea     rdx, [rdi+18h]
0x18002db1d  mov     rcx, rbx
0x18002db20  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002db25  lea     rcx, [rsp+48h+arg_18]
0x18002db2a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002db2f  nop
0x18002db30  mov     rbx, [rsp+48h+arg_8]
0x18002db35  add     rsp, 30h
0x18002db39  pop     rdi
0x18002db3a  pop     rsi
0x18002db3b  pop     rbp
0x18002db3c  retn
```
