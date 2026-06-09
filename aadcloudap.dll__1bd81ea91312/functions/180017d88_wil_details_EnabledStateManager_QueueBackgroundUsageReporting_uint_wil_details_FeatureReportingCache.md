# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180017d88`
- end: `0x180017e61`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180018e14`

## callees

- `0x180009980`
- `0x18000a188`
- `0x18000a7e8`
- `0x180014c14`
- `0x180017cb4`
- `0x180017d88`
- `0x18001b72c`
- `0x18001bad4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017dba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017dba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017e1c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017e1c`

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
0x180017d88  mov     [rsp+arg_8], rbx
0x180017d8d  push    rbp
0x180017d8e  push    rsi
0x180017d8f  push    rdi
0x180017d90  sub     rsp, 30h
0x180017d94  mov     rsi, r8
0x180017d97  mov     ebp, edx
0x180017d99  mov     rdi, rcx
0x180017d9c  mov     eax, [rcx]
0x180017d9e  test    eax, eax
0x180017da0  jz      loc_180017E54
0x180017da6  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180017dab  test    al, al
0x180017dad  jnz     loc_180017E54
0x180017db3  lea     rbx, [rdi+8]
0x180017db7  mov     rcx, rbx; SRWLock
0x180017dba  call    cs:__imp_AcquireSRWLockExclusive
0x180017dc0  mov     [rsp+48h+arg_18], rbx
0x180017dc5  mov     eax, [rdi]
0x180017dc7  test    eax, eax
0x180017dc9  jz      short loc_180017E49
0x180017dcb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180017dd0  test    al, al
0x180017dd2  jnz     short loc_180017E49
0x180017dd4  mov     [rsp+48h+var_28], ebp
0x180017dd8  xor     eax, eax
0x180017dda  mov     [rsp+48h+var_24], eax
0x180017dde  mov     [rsp+48h+var_20], rsi
0x180017de3  lea     rcx, [rdi+20h]; this
0x180017de7  lea     r8d, [rax+10h]; unsigned __int64
0x180017deb  lea     rdx, [rsp+48h+var_28]; void *
0x180017df0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180017df5  cmp     byte ptr [rdi+18h], 0
0x180017df9  jnz     short loc_180017E49
0x180017dfb  lea     rbx, [rdi+10h]
0x180017dff  cmp     qword ptr [rbx], 0
0x180017e03  jnz     short loc_180017E37
0x180017e05  lea     rcx, [rsp+48h+arg_0]; this
0x180017e0a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180017e0f  xor     r8d, r8d; pcbe
0x180017e12  mov     rdx, rdi; pv
0x180017e15  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180017e1c  call    cs:__imp_CreateThreadpoolTimer
0x180017e22  mov     rdx, rax
0x180017e25  mov     rcx, rbx
0x180017e28  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180017e2d  lea     rcx, [rsp+48h+arg_0]; this
0x180017e32  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180017e37  mov     r8d, 493E0h
0x180017e3d  lea     rdx, [rdi+18h]
0x180017e41  mov     rcx, rbx
0x180017e44  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180017e49  lea     rcx, [rsp+48h+arg_18]
0x180017e4e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017e53  nop
0x180017e54  mov     rbx, [rsp+48h+arg_8]
0x180017e59  add     rsp, 30h
0x180017e5d  pop     rdi
0x180017e5e  pop     rsi
0x180017e5f  pop     rbp
0x180017e60  retn
```
