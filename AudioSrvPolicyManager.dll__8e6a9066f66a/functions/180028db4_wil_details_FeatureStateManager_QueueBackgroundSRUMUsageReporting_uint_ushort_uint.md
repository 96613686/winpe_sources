# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180028db4`
- end: `0x180028e97`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180036590`

## callees

- `0x180025db0`
- `0x1800272f8`
- `0x180028db4`
- `0x180029088`
- `0x1800290cc`
- `0x180029314`
- `0x180029458`
- `0x180036b0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028df0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028df0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180028e4c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180028e4c`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  char *v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = pv + 40;
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
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
}

```

## disassembly

```asm
0x180028db4  mov     [rsp+arg_8], rbx
0x180028db9  mov     [rsp+arg_10], rbp
0x180028dbe  push    rsi
0x180028dbf  push    rdi
0x180028dc0  push    r14
0x180028dc2  sub     rsp, 40h
0x180028dc6  mov     esi, r9d
0x180028dc9  movzx   ebp, r8w
0x180028dcd  mov     r14d, edx
0x180028dd0  mov     rdi, rcx
0x180028dd3  cmp     byte ptr [rcx], 0
0x180028dd6  jz      loc_180028E84
0x180028ddc  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180028de1  test    al, al
0x180028de3  jnz     loc_180028E84
0x180028de9  lea     rbx, [rdi+28h]
0x180028ded  mov     rcx, rbx; SRWLock
0x180028df0  call    cs:__imp_AcquireSRWLockExclusive
0x180028df6  mov     [rsp+58h+var_38], rbx
0x180028dfb  xor     eax, eax
0x180028dfd  mov     [rsp+58h+var_2A], ax
0x180028e02  mov     [rsp+58h+var_30], r14d
0x180028e07  mov     [rsp+58h+var_2C], bp
0x180028e0c  mov     [rsp+58h+var_28], esi
0x180028e10  lea     rcx, [rdi+0E8h]; this
0x180028e17  lea     r8d, [rax+0Ch]; unsigned __int64
0x180028e1b  lea     rdx, [rsp+58h+var_30]; void *
0x180028e20  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180028e25  cmp     byte ptr [rdi+40h], 0
0x180028e29  jnz     short loc_180028E79
0x180028e2b  lea     rbx, [rdi+38h]
0x180028e2f  cmp     qword ptr [rbx], 0
0x180028e33  jnz     short loc_180028E67
0x180028e35  lea     rcx, [rsp+58h+arg_0]; this
0x180028e3a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180028e3f  xor     r8d, r8d; pcbe
0x180028e42  mov     rdx, rdi; pv
0x180028e45  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180028e4c  call    cs:__imp_CreateThreadpoolTimer
0x180028e52  mov     rdx, rax
0x180028e55  mov     rcx, rbx
0x180028e58  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180028e5d  lea     rcx, [rsp+58h+arg_0]; this
0x180028e62  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180028e67  mov     r8d, 1388h
0x180028e6d  lea     rdx, [rdi+40h]
0x180028e71  mov     rcx, rbx
0x180028e74  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180028e79  lea     rcx, [rsp+58h+var_38]
0x180028e7e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180028e83  nop
0x180028e84  mov     rbx, [rsp+58h+arg_8]
0x180028e89  mov     rbp, [rsp+58h+arg_10]
0x180028e8e  add     rsp, 40h
0x180028e92  pop     r14
0x180028e94  pop     rdi
0x180028e95  pop     rsi
0x180028e96  retn
```
