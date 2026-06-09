# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x1800ab984`
- end: `0x1800aba5d`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(char *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800ac554`

## callees

- `0x180069608`
- `0x180069628`
- `0x18006966c`
- `0x18006968c`
- `0x1800696b0`
- `0x1800697e0`
- `0x1800ab984`
- `0x1800addec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ab9b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ab9b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800aba18`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800aba18`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD v8[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  char *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v11 = pv + 8;
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), v8, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v10);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v10);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x1800ab984  mov     [rsp+arg_8], rbx
0x1800ab989  push    rbp
0x1800ab98a  push    rsi
0x1800ab98b  push    rdi
0x1800ab98c  sub     rsp, 30h
0x1800ab990  mov     rsi, r8
0x1800ab993  mov     ebp, edx
0x1800ab995  mov     rdi, rcx
0x1800ab998  mov     eax, [rcx]
0x1800ab99a  test    eax, eax
0x1800ab99c  jz      loc_1800ABA50
0x1800ab9a2  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800ab9a7  test    al, al
0x1800ab9a9  jnz     loc_1800ABA50
0x1800ab9af  lea     rbx, [rdi+8]
0x1800ab9b3  mov     rcx, rbx; SRWLock
0x1800ab9b6  call    cs:__imp_AcquireSRWLockExclusive
0x1800ab9bc  mov     [rsp+48h+arg_18], rbx
0x1800ab9c1  mov     eax, [rdi]
0x1800ab9c3  test    eax, eax
0x1800ab9c5  jz      short loc_1800ABA45
0x1800ab9c7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800ab9cc  test    al, al
0x1800ab9ce  jnz     short loc_1800ABA45
0x1800ab9d0  mov     [rsp+48h+var_28], ebp
0x1800ab9d4  xor     eax, eax
0x1800ab9d6  mov     [rsp+48h+var_24], eax
0x1800ab9da  mov     [rsp+48h+var_20], rsi
0x1800ab9df  lea     rcx, [rdi+20h]; this
0x1800ab9e3  lea     r8d, [rax+10h]; unsigned __int64
0x1800ab9e7  lea     rdx, [rsp+48h+var_28]; void *
0x1800ab9ec  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800ab9f1  cmp     byte ptr [rdi+18h], 0
0x1800ab9f5  jnz     short loc_1800ABA45
0x1800ab9f7  lea     rbx, [rdi+10h]
0x1800ab9fb  cmp     qword ptr [rbx], 0
0x1800ab9ff  jnz     short loc_1800ABA33
0x1800aba01  lea     rcx, [rsp+48h+arg_0]; this
0x1800aba06  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800aba0b  xor     r8d, r8d; pcbe
0x1800aba0e  mov     rdx, rdi; pv
0x1800aba11  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800aba18  call    cs:__imp_CreateThreadpoolTimer
0x1800aba1e  mov     rdx, rax
0x1800aba21  mov     rcx, rbx
0x1800aba24  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800aba29  lea     rcx, [rsp+48h+arg_0]; this
0x1800aba2e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800aba33  mov     r8d, 493E0h
0x1800aba39  lea     rdx, [rdi+18h]
0x1800aba3d  mov     rcx, rbx
0x1800aba40  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800aba45  lea     rcx, [rsp+48h+arg_18]
0x1800aba4a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800aba4f  nop
0x1800aba50  mov     rbx, [rsp+48h+arg_8]
0x1800aba55  add     rsp, 30h
0x1800aba59  pop     rdi
0x1800aba5a  pop     rsi
0x1800aba5b  pop     rbp
0x1800aba5c  retn
```
