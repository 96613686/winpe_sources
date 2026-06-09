# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14000f0b8`
- end: `0x14000f191`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `217`
- prototype: `void __fastcall(char *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140010260`

## callees

- `0x1400039f0`
- `0x140003dd0`
- `0x14000552c`
- `0x1400092f0`
- `0x14000b29c`
- `0x14000f0b8`
- `0x140012af8`
- `0x140012c04`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x14000f14c`
- `KERNEL32!CreateThreadpoolTimer` at `0x14000f14c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000f0ea`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000f0ea`

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
  RTL_SRWLOCK *v11; // [rsp+68h] [rbp+20h] BYREF

  if ( *(_DWORD *)pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    v11 = (RTL_SRWLOCK *)(pv + 8);
    if ( *(_DWORD *)pv )
    {
      if ( !wil::ProcessShutdownInProgress(v6) )
      {
        v8[0] = a2;
        v8[1] = 0;
        v9 = a3;
        wil::details_abi::heap_buffer::push_back((void **)pv + 4, v8, 0x10u);
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
0x14000f0b8  mov     [rsp+arg_8], rbx
0x14000f0bd  push    rbp
0x14000f0be  push    rsi
0x14000f0bf  push    rdi
0x14000f0c0  sub     rsp, 30h
0x14000f0c4  mov     rsi, r8
0x14000f0c7  mov     ebp, edx
0x14000f0c9  mov     rdi, rcx
0x14000f0cc  mov     eax, [rcx]
0x14000f0ce  test    eax, eax
0x14000f0d0  jz      loc_14000F184
0x14000f0d6  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000f0db  test    al, al
0x14000f0dd  jnz     loc_14000F184
0x14000f0e3  lea     rbx, [rdi+8]
0x14000f0e7  mov     rcx, rbx; SRWLock
0x14000f0ea  call    cs:__imp_AcquireSRWLockExclusive
0x14000f0f0  mov     [rsp+48h+arg_18], rbx
0x14000f0f5  mov     eax, [rdi]
0x14000f0f7  test    eax, eax
0x14000f0f9  jz      short loc_14000F179
0x14000f0fb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000f100  test    al, al
0x14000f102  jnz     short loc_14000F179
0x14000f104  mov     [rsp+48h+var_28], ebp
0x14000f108  xor     eax, eax
0x14000f10a  mov     [rsp+48h+var_24], eax
0x14000f10e  mov     [rsp+48h+var_20], rsi
0x14000f113  lea     rcx, [rdi+20h]; this
0x14000f117  lea     r8d, [rax+10h]; unsigned __int64
0x14000f11b  lea     rdx, [rsp+48h+var_28]; void *
0x14000f120  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000f125  cmp     byte ptr [rdi+18h], 0
0x14000f129  jnz     short loc_14000F179
0x14000f12b  lea     rbx, [rdi+10h]
0x14000f12f  cmp     qword ptr [rbx], 0
0x14000f133  jnz     short loc_14000F167
0x14000f135  lea     rcx, [rsp+48h+arg_0]; this
0x14000f13a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000f13f  xor     r8d, r8d; pcbe
0x14000f142  mov     rdx, rdi; pv
0x14000f145  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000f14c  call    cs:__imp_CreateThreadpoolTimer
0x14000f152  mov     rdx, rax
0x14000f155  mov     rcx, rbx
0x14000f158  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000f15d  lea     rcx, [rsp+48h+arg_0]; this
0x14000f162  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000f167  mov     r8d, 493E0h
0x14000f16d  lea     rdx, [rdi+18h]
0x14000f171  mov     rcx, rbx
0x14000f174  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14000f179  lea     rcx, [rsp+48h+arg_18]
0x14000f17e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000f183  nop
0x14000f184  mov     rbx, [rsp+48h+arg_8]
0x14000f189  add     rsp, 30h
0x14000f18d  pop     rdi
0x14000f18e  pop     rsi
0x14000f18f  pop     rbp
0x14000f190  retn
```
