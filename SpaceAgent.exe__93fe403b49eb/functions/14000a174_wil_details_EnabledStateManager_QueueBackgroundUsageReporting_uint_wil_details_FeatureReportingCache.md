# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14000a174`
- end: `0x14000a251`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `221`
- prototype: `void __fastcall(char *pv, __int64, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000a330`

## callees

- `0x140004238`
- `0x140004604`
- `0x14000494c`
- `0x140005164`
- `0x140006db4`
- `0x14000949c`
- `0x1400095a8`
- `0x14000a174`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x14000a20a`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000a20a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a1a7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a1a7`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        __int64 a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v5; // rcx
  int v6; // eax
  PTP_TIMER ThreadpoolTimer; // rax
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
        v8[0] = 59117474;
        v8[1] = a3;
        wil::details_abi::heap_buffer::push_back((void **)pv + 4, v8, 0x10u);
        if ( !pv[24] )
        {
          if ( !*((_QWORD *)pv + 2) )
          {
            wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
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
0x14000a174  mov     [rsp+arg_8], rbx
0x14000a179  mov     [rsp+arg_10], rsi
0x14000a17e  push    rdi
0x14000a17f  sub     rsp, 30h
0x14000a183  mov     eax, [rcx]
0x14000a185  mov     rsi, r8
0x14000a188  mov     rdi, rcx
0x14000a18b  test    eax, eax
0x14000a18d  jz      loc_14000A241
0x14000a193  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000a198  test    al, al
0x14000a19a  jnz     loc_14000A241
0x14000a1a0  lea     rbx, [rdi+8]
0x14000a1a4  mov     rcx, rbx; SRWLock
0x14000a1a7  call    cs:__imp_AcquireSRWLockExclusive
0x14000a1ad  mov     eax, [rdi]
0x14000a1af  mov     [rsp+38h+arg_18], rbx
0x14000a1b4  test    eax, eax
0x14000a1b6  jz      short loc_14000A237
0x14000a1b8  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000a1bd  test    al, al
0x14000a1bf  jnz     short loc_14000A237
0x14000a1c1  lea     rcx, [rdi+20h]; this
0x14000a1c5  mov     [rsp+38h+var_18], 3860FA2h
0x14000a1ce  mov     r8d, 10h; unsigned __int64
0x14000a1d4  mov     [rsp+38h+var_10], rsi
0x14000a1d9  lea     rdx, [rsp+38h+var_18]; void *
0x14000a1de  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000a1e3  cmp     byte ptr [rdi+18h], 0
0x14000a1e7  jnz     short loc_14000A237
0x14000a1e9  lea     rbx, [rdi+10h]
0x14000a1ed  cmp     qword ptr [rbx], 0
0x14000a1f1  jnz     short loc_14000A225
0x14000a1f3  lea     rcx, [rsp+38h+arg_0]; this
0x14000a1f8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000a1fd  xor     r8d, r8d; pcbe
0x14000a200  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000a207  mov     rdx, rdi; pv
0x14000a20a  call    cs:__imp_CreateThreadpoolTimer
0x14000a210  mov     rdx, rax
0x14000a213  mov     rcx, rbx
0x14000a216  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000a21b  lea     rcx, [rsp+38h+arg_0]; this
0x14000a220  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000a225  mov     r8d, 493E0h
0x14000a22b  lea     rdx, [rdi+18h]
0x14000a22f  mov     rcx, rbx
0x14000a232  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14000a237  lea     rcx, [rsp+38h+arg_18]
0x14000a23c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000a241  mov     rbx, [rsp+38h+arg_8]
0x14000a246  mov     rsi, [rsp+38h+arg_10]
0x14000a24b  add     rsp, 30h
0x14000a24f  pop     rdi
0x14000a250  retn
```
