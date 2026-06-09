# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18006e0dc`
- end: `0x18006e1ca`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `238`
- prototype: `void __fastcall(char *pv, __int64, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18006e2ac`

## callees

- `0x18005277c`
- `0x180052984`
- `0x180052df8`
- `0x180053728`
- `0x180055eb0`
- `0x180058168`
- `0x180058274`
- `0x18006e0dc`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x18006e17c`
- `KERNEL32!CreateThreadpoolTimer` at `0x18006e17c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18006e10f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18006e10f`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  int v6; // eax
  struct _TP_TIMER *ThreadpoolTimer; // rax
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF
  char v9; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v10; // [rsp+58h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v6 = *(_DWORD *)pv;
    v10 = (RTL_SRWLOCK *)(pv + 8);
    if ( v6 )
    {
      if ( !wil::ProcessShutdownInProgress(v5) )
      {
        v8[0] = 59692005;
        v8[1] = a3;
        wil::details_abi::heap_buffer::push_back((void **)pv + 6, v8, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                (PTP_TIMER_CALLBACK)_lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              (struct _TP_TIMER **)pv + 2,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 2, pv + 24, 300000);
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x18006e0dc  mov     [rsp+arg_8], rbx
0x18006e0e1  mov     [rsp+arg_10], rsi
0x18006e0e6  push    rdi
0x18006e0e7  sub     rsp, 30h
0x18006e0eb  mov     eax, [rcx]
0x18006e0ed  mov     rsi, r8
0x18006e0f0  mov     rdi, rcx
0x18006e0f3  test    eax, eax
0x18006e0f5  jz      loc_18006E1B9
0x18006e0fb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18006e100  test    al, al
0x18006e102  jnz     loc_18006E1B9
0x18006e108  lea     rbx, [rdi+8]
0x18006e10c  mov     rcx, rbx; SRWLock
0x18006e10f  call    cs:__imp_AcquireSRWLockExclusive
0x18006e116  nop     dword ptr [rax+rax+00h]
0x18006e11b  mov     eax, [rdi]
0x18006e11d  mov     [rsp+38h+arg_18], rbx
0x18006e122  test    eax, eax
0x18006e124  jz      loc_18006E1AF
0x18006e12a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18006e12f  test    al, al
0x18006e131  jnz     short loc_18006E1AF
0x18006e133  lea     rcx, [rdi+30h]; this
0x18006e137  mov     [rsp+38h+var_18], 38ED3E5h
0x18006e140  mov     r8d, 10h; unsigned __int64
0x18006e146  mov     [rsp+38h+var_10], rsi
0x18006e14b  lea     rdx, [rsp+38h+var_18]; void *
0x18006e150  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18006e155  cmp     byte ptr [rdi+18h], 0
0x18006e159  jnz     short loc_18006E1AF
0x18006e15b  lea     rbx, [rdi+10h]
0x18006e15f  cmp     qword ptr [rbx], 0
0x18006e163  jnz     short loc_18006E19D
0x18006e165  lea     rcx, [rsp+38h+arg_0]; this
0x18006e16a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006e16f  xor     r8d, r8d; pcbe
0x18006e172  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18006e179  mov     rdx, rdi; pv
0x18006e17c  call    cs:__imp_CreateThreadpoolTimer
0x18006e183  nop     dword ptr [rax+rax+00h]
0x18006e188  mov     rdx, rax
0x18006e18b  mov     rcx, rbx
0x18006e18e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18006e193  lea     rcx, [rsp+38h+arg_0]; this
0x18006e198  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006e19d  mov     r8d, 493E0h
0x18006e1a3  lea     rdx, [rdi+18h]
0x18006e1a7  mov     rcx, rbx
0x18006e1aa  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18006e1af  lea     rcx, [rsp+38h+arg_18]
0x18006e1b4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006e1b9  mov     rbx, [rsp+38h+arg_8]
0x18006e1be  mov     rsi, [rsp+38h+arg_10]
0x18006e1c3  add     rsp, 30h
0x18006e1c7  pop     rdi
0x18006e1c8  retn
```
