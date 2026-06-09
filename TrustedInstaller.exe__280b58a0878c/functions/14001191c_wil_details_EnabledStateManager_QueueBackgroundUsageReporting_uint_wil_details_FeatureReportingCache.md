# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14001191c`
- end: `0x1400119f4`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `216`
- prototype: `void __fastcall(char *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140011cc0`

## callees

- `0x140003b94`
- `0x140003e04`
- `0x14000537c`
- `0x1400066cc`
- `0x1400071ac`
- `0x14000aee0`
- `0x14000afe8`
- `0x14001191c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001194e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001194e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400119b0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400119b0`

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
  _DWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  struct wil_details_FeatureReportingCache *v10; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v11; // [rsp+30h] [rbp-28h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v7 = *(_DWORD *)pv;
    v11 = (RTL_SRWLOCK *)(pv + 8);
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
            wil::last_error_context::last_error_context((wil::last_error_context *)v9);
            ThreadpoolTimer = CreateThreadpoolTimer(
                                _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                pv,
                                0);
            wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
              pv + 16,
              ThreadpoolTimer);
            wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
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
0x14001191c  mov     [rsp+arg_18], rbx
0x140011921  push    rbp
0x140011922  push    rsi
0x140011923  push    rdi
0x140011924  sub     rsp, 40h
0x140011928  mov     eax, [rcx]
0x14001192a  mov     rbp, r8
0x14001192d  mov     esi, edx
0x14001192f  mov     rdi, rcx
0x140011932  test    eax, eax
0x140011934  jz      loc_1400119E7
0x14001193a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14001193f  test    al, al
0x140011941  jnz     loc_1400119E7
0x140011947  lea     rbx, [rdi+8]
0x14001194b  mov     rcx, rbx; SRWLock
0x14001194e  call    cs:__imp_AcquireSRWLockExclusive
0x140011954  mov     eax, [rdi]
0x140011956  mov     [rsp+58h+var_28], rbx
0x14001195b  test    eax, eax
0x14001195d  jz      short loc_1400119DD
0x14001195f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140011964  test    al, al
0x140011966  jnz     short loc_1400119DD
0x140011968  xor     eax, eax
0x14001196a  mov     [rsp+58h+var_38], esi
0x14001196e  lea     rcx, [rdi+20h]; this
0x140011972  mov     [rsp+58h+var_34], eax
0x140011976  lea     rdx, [rsp+58h+var_38]; void *
0x14001197b  mov     [rsp+58h+var_30], rbp
0x140011980  lea     r8d, [rax+10h]; unsigned __int64
0x140011984  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140011989  cmp     byte ptr [rdi+18h], 0
0x14001198d  jnz     short loc_1400119DD
0x14001198f  lea     rbx, [rdi+10h]
0x140011993  cmp     qword ptr [rbx], 0
0x140011997  jnz     short loc_1400119CB
0x140011999  lea     rcx, [rsp+58h+var_38]; this
0x14001199e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400119a3  xor     r8d, r8d; pcbe
0x1400119a6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400119ad  mov     rdx, rdi; pv
0x1400119b0  call    cs:__imp_CreateThreadpoolTimer
0x1400119b6  mov     rdx, rax
0x1400119b9  mov     rcx, rbx
0x1400119bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400119c1  lea     rcx, [rsp+58h+var_38]; this
0x1400119c6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400119cb  mov     r8d, 493E0h
0x1400119d1  lea     rdx, [rdi+18h]
0x1400119d5  mov     rcx, rbx
0x1400119d8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1400119dd  lea     rcx, [rsp+58h+var_28]
0x1400119e2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400119e7  mov     rbx, [rsp+58h+arg_18]
0x1400119ec  add     rsp, 40h
0x1400119f0  pop     rdi
0x1400119f1  pop     rsi
0x1400119f2  pop     rbp
0x1400119f3  retn
```
