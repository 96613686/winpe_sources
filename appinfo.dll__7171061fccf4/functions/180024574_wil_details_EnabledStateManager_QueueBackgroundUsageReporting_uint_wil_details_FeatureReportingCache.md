# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180024574`
- end: `0x180024657`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001dac4`

## callees

- `0x18000debc`
- `0x180010240`
- `0x180010490`
- `0x180011e58`
- `0x18001ac90`
- `0x18001adc8`
- `0x180024574`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800245a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800245a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024628`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024628`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002460c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002460c`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  int v7; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-20h]
  char v11; // [rsp+50h] [rbp+8h] BYREF
  DWORD dwErrCode; // [rsp+54h] [rbp+Ch]
  RTL_SRWLOCK *v13; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v7 = *(_DWORD *)pv;
    v13 = (RTL_SRWLOCK *)(pv + 8);
    if ( v7 )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v9[0] = a2;
        v9[1] = 0;
        v10 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), v9, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            if ( !v11 )
              SetLastError(dwErrCode);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  }
}

```

## disassembly

```asm
0x180024574  mov     [rsp+arg_8], rbx
0x180024579  push    rbp
0x18002457a  push    rsi
0x18002457b  push    rdi
0x18002457c  sub     rsp, 30h
0x180024580  mov     eax, [rcx]
0x180024582  mov     rsi, r8
0x180024585  mov     ebp, edx
0x180024587  mov     rdi, rcx
0x18002458a  test    eax, eax
0x18002458c  jz      loc_18002464A
0x180024592  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180024597  test    al, al
0x180024599  jnz     loc_18002464A
0x18002459f  lea     rbx, [rdi+8]
0x1800245a3  mov     rcx, rbx; SRWLock
0x1800245a6  call    cs:__imp_AcquireSRWLockExclusive
0x1800245ac  mov     eax, [rdi]
0x1800245ae  mov     [rsp+48h+arg_18], rbx
0x1800245b3  test    eax, eax
0x1800245b5  jz      loc_180024640
0x1800245bb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800245c0  test    al, al
0x1800245c2  jnz     short loc_180024640
0x1800245c4  xor     eax, eax
0x1800245c6  mov     [rsp+48h+var_28], ebp
0x1800245ca  lea     rcx, [rdi+20h]; this
0x1800245ce  mov     [rsp+48h+var_24], eax
0x1800245d2  lea     rdx, [rsp+48h+var_28]; void *
0x1800245d7  mov     [rsp+48h+var_20], rsi
0x1800245dc  lea     r8d, [rax+10h]; unsigned __int64
0x1800245e0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800245e5  cmp     byte ptr [rdi+18h], 0
0x1800245e9  jnz     short loc_180024640
0x1800245eb  lea     rbx, [rdi+10h]
0x1800245ef  cmp     qword ptr [rbx], 0
0x1800245f3  jnz     short loc_18002462E
0x1800245f5  lea     rcx, [rsp+48h+arg_0]; this
0x1800245fa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800245ff  xor     r8d, r8d; pcbe
0x180024602  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180024609  mov     rdx, rdi; pv
0x18002460c  call    cs:__imp_CreateThreadpoolTimer
0x180024612  mov     rdx, rax
0x180024615  mov     rcx, rbx
0x180024618  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002461d  cmp     [rsp+48h+arg_0], 0
0x180024622  jnz     short loc_18002462E
0x180024624  mov     ecx, [rsp+48h+dwErrCode]; dwErrCode
0x180024628  call    cs:__imp_SetLastError
0x18002462e  mov     r8d, 493E0h
0x180024634  lea     rdx, [rdi+18h]
0x180024638  mov     rcx, rbx
0x18002463b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180024640  lea     rcx, [rsp+48h+arg_18]
0x180024645  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002464a  mov     rbx, [rsp+48h+arg_8]
0x18002464f  add     rsp, 30h
0x180024653  pop     rdi
0x180024654  pop     rsi
0x180024655  pop     rbp
0x180024656  retn
```
