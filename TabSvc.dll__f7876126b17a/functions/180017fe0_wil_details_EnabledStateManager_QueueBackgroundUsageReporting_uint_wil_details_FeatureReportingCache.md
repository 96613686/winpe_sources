# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180017fe0`
- end: `0x1800180b9`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800110e0`
- `0x180011570`
- `0x180011c30`

## callees

- `0x1800138cc`
- `0x180013d6c`
- `0x180014070`
- `0x180017fe0`
- `0x180018434`
- `0x1800186a0`
- `0x1800186c0`
- `0x1800186e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018012`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018012`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018074`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018074`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  wil *v6; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v9; // [rsp+28h] [rbp-20h]
  char v10; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v11 = (RTL_SRWLOCK *)(pv + 8);
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        Source[0] = a2;
        Source[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 32), Source, 0x10u);
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
0x180017fe0  mov     [rsp+arg_8], rbx
0x180017fe5  push    rbp
0x180017fe6  push    rsi
0x180017fe7  push    rdi
0x180017fe8  sub     rsp, 30h
0x180017fec  mov     rsi, r8
0x180017fef  mov     ebp, edx
0x180017ff1  mov     rdi, rcx
0x180017ff4  mov     eax, [rcx]
0x180017ff6  test    eax, eax
0x180017ff8  jz      loc_1800180AC
0x180017ffe  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180018003  test    al, al
0x180018005  jnz     loc_1800180AC
0x18001800b  lea     rbx, [rdi+8]
0x18001800f  mov     rcx, rbx; SRWLock
0x180018012  call    cs:__imp_AcquireSRWLockExclusive
0x180018018  mov     [rsp+48h+arg_18], rbx
0x18001801d  mov     eax, [rdi]
0x18001801f  test    eax, eax
0x180018021  jz      short loc_1800180A1
0x180018023  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180018028  test    al, al
0x18001802a  jnz     short loc_1800180A1
0x18001802c  mov     [rsp+48h+Source], ebp
0x180018030  xor     eax, eax
0x180018032  mov     [rsp+48h+var_24], eax
0x180018036  mov     [rsp+48h+var_20], rsi
0x18001803b  lea     rcx, [rdi+20h]; this
0x18001803f  lea     r8d, [rax+10h]; SourceSize
0x180018043  lea     rdx, [rsp+48h+Source]; Source
0x180018048  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001804d  cmp     byte ptr [rdi+18h], 0
0x180018051  jnz     short loc_1800180A1
0x180018053  lea     rbx, [rdi+10h]
0x180018057  cmp     qword ptr [rbx], 0
0x18001805b  jnz     short loc_18001808F
0x18001805d  lea     rcx, [rsp+48h+arg_0]; this
0x180018062  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018067  xor     r8d, r8d; pcbe
0x18001806a  mov     rdx, rdi; pv
0x18001806d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180018074  call    cs:__imp_CreateThreadpoolTimer
0x18001807a  mov     rdx, rax
0x18001807d  mov     rcx, rbx
0x180018080  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180018085  lea     rcx, [rsp+48h+arg_0]; this
0x18001808a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001808f  mov     r8d, 493E0h
0x180018095  lea     rdx, [rdi+18h]
0x180018099  mov     rcx, rbx
0x18001809c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800180a1  lea     rcx, [rsp+48h+arg_18]
0x1800180a6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800180ab  nop
0x1800180ac  mov     rbx, [rsp+48h+arg_8]
0x1800180b1  add     rsp, 30h
0x1800180b5  pop     rdi
0x1800180b6  pop     rsi
0x1800180b7  pop     rbp
0x1800180b8  retn
```
