# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14002391c`
- end: `0x140023a09`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `237`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140032660`

## callees

- `0x14000e2b4`
- `0x14000f30c`
- `0x1400101e4`
- `0x1400155e8`
- `0x140021ddc`
- `0x14002391c`
- `0x1400375c4`
- `0x140037d88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140023962`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140023962`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400239be`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400239be`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _QWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+30h] [rbp-28h] BYREF
  __int16 v11; // [rsp+34h] [rbp-24h]
  __int16 v12; // [rsp+36h] [rbp-22h]
  int v13; // [rsp+38h] [rbp-20h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  v9[1] = -2;
  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9[0] = pv + 40;
    v12 = 0;
    v10 = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v10, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v9);
  }
}

```

## disassembly

```asm
0x14002391c  push    rsi
0x14002391e  push    rdi
0x14002391f  push    r14
0x140023921  sub     rsp, 40h
0x140023925  mov     [rsp+58h+var_30], 0FFFFFFFFFFFFFFFEh
0x14002392e  mov     [rsp+58h+arg_8], rbx
0x140023933  mov     [rsp+58h+arg_10], rbp
0x140023938  mov     esi, r9d
0x14002393b  movzx   ebp, r8w
0x14002393f  mov     r14d, edx
0x140023942  mov     rdi, rcx
0x140023945  cmp     byte ptr [rcx], 0
0x140023948  jz      loc_1400239F6
0x14002394e  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140023953  test    al, al
0x140023955  jnz     loc_1400239F6
0x14002395b  lea     rbx, [rdi+28h]
0x14002395f  mov     rcx, rbx; SRWLock
0x140023962  call    cs:__imp_AcquireSRWLockExclusive
0x140023968  mov     [rsp+58h+var_38], rbx
0x14002396d  xor     eax, eax
0x14002396f  mov     [rsp+58h+var_22], ax
0x140023974  mov     [rsp+58h+var_28], r14d
0x140023979  mov     [rsp+58h+var_24], bp
0x14002397e  mov     [rsp+58h+var_20], esi
0x140023982  lea     rcx, [rdi+0E8h]; this
0x140023989  lea     r8d, [rax+0Ch]; unsigned __int64
0x14002398d  lea     rdx, [rsp+58h+var_28]; void *
0x140023992  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140023997  cmp     byte ptr [rdi+40h], 0
0x14002399b  jnz     short loc_1400239EB
0x14002399d  lea     rbx, [rdi+38h]
0x1400239a1  cmp     qword ptr [rbx], 0
0x1400239a5  jnz     short loc_1400239D9
0x1400239a7  lea     rcx, [rsp+58h+arg_0]; this
0x1400239ac  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400239b1  xor     r8d, r8d; pcbe
0x1400239b4  mov     rdx, rdi; pv
0x1400239b7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400239be  call    cs:__imp_CreateThreadpoolTimer
0x1400239c4  mov     rdx, rax
0x1400239c7  mov     rcx, rbx
0x1400239ca  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400239cf  lea     rcx, [rsp+58h+arg_0]; this
0x1400239d4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400239d9  mov     r8d, 1388h
0x1400239df  lea     rdx, [rdi+40h]
0x1400239e3  mov     rcx, rbx
0x1400239e6  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1400239eb  lea     rcx, [rsp+58h+var_38]
0x1400239f0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400239f5  nop
0x1400239f6  mov     rbx, [rsp+58h+arg_8]
0x1400239fb  mov     rbp, [rsp+58h+arg_10]
0x140023a00  add     rsp, 40h
0x140023a04  pop     r14
0x140023a06  pop     rdi
0x140023a07  pop     rsi
0x140023a08  retn
```
