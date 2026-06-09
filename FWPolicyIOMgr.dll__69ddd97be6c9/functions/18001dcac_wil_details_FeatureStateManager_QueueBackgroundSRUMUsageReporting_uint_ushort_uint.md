# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001dcac`
- end: `0x18001dd7f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `211`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001ae50`

## callees

- `0x1800133f8`
- `0x1800135d4`
- `0x1800135f4`
- `0x180013654`
- `0x180013678`
- `0x180013738`
- `0x18001dcac`
- `0x18001dd88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001dce0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001dce0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001dd3c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001dd3c`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  int v9; // [rsp+20h] [rbp-48h] BYREF
  __int16 v10; // [rsp+24h] [rbp-44h]
  __int16 v11; // [rsp+26h] [rbp-42h]
  int v12; // [rsp+28h] [rbp-40h]
  RTL_SRWLOCK *v13; // [rsp+30h] [rbp-38h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v13 = (RTL_SRWLOCK *)(pv + 40);
    v11 = 0;
    v9 = a2;
    v10 = a3;
    v12 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v9, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  }
}

```

## disassembly

```asm
0x18001dcac  push    rbx
0x18001dcae  push    rbp
0x18001dcaf  push    rsi
0x18001dcb0  push    rdi
0x18001dcb1  push    r14
0x18001dcb3  sub     rsp, 40h
0x18001dcb7  mov     r14d, r9d
0x18001dcba  movzx   ebp, r8w
0x18001dcbe  mov     esi, edx
0x18001dcc0  mov     rdi, rcx
0x18001dcc3  cmp     byte ptr [rcx], 0
0x18001dcc6  jz      loc_18001DD74
0x18001dccc  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001dcd1  test    al, al
0x18001dcd3  jnz     loc_18001DD74
0x18001dcd9  lea     rbx, [rdi+28h]
0x18001dcdd  mov     rcx, rbx; SRWLock
0x18001dce0  call    cs:__imp_AcquireSRWLockExclusive
0x18001dce6  mov     [rsp+68h+var_38], rbx
0x18001dceb  xor     eax, eax
0x18001dced  mov     [rsp+68h+var_42], ax
0x18001dcf2  mov     [rsp+68h+var_48], esi
0x18001dcf6  mov     [rsp+68h+var_44], bp
0x18001dcfb  mov     [rsp+68h+var_40], r14d
0x18001dd00  lea     rcx, [rdi+0E8h]; this
0x18001dd07  lea     r8d, [rax+0Ch]; unsigned __int64
0x18001dd0b  lea     rdx, [rsp+68h+var_48]; void *
0x18001dd10  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001dd15  cmp     byte ptr [rdi+40h], 0
0x18001dd19  jnz     short loc_18001DD69
0x18001dd1b  lea     rbx, [rdi+38h]
0x18001dd1f  cmp     qword ptr [rbx], 0
0x18001dd23  jnz     short loc_18001DD57
0x18001dd25  lea     rcx, [rsp+68h+var_48]; this
0x18001dd2a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001dd2f  xor     r8d, r8d; pcbe
0x18001dd32  mov     rdx, rdi; pv
0x18001dd35  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001dd3c  call    cs:__imp_CreateThreadpoolTimer
0x18001dd42  mov     rdx, rax
0x18001dd45  mov     rcx, rbx
0x18001dd48  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001dd4d  lea     rcx, [rsp+68h+var_48]; this
0x18001dd52  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001dd57  mov     r8d, 1388h
0x18001dd5d  lea     rdx, [rdi+40h]
0x18001dd61  mov     rcx, rbx
0x18001dd64  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001dd69  lea     rcx, [rsp+68h+var_38]
0x18001dd6e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001dd73  nop
0x18001dd74  add     rsp, 40h
0x18001dd78  pop     r14
0x18001dd7a  pop     rdi
0x18001dd7b  pop     rsi
0x18001dd7c  pop     rbp
0x18001dd7d  pop     rbx
0x18001dd7e  retn
```
