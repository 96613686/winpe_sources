# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000ea7c`
- end: `0x18000eb5f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180012290`

## callees

- `0x180009b34`
- `0x180009edc`
- `0x18000a37c`
- `0x18000b030`
- `0x18000e88c`
- `0x18000ea7c`
- `0x180012b98`
- `0x180012cb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eab8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000eab8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000eb14`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000eb14`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  RTL_SRWLOCK *v9; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = (RTL_SRWLOCK *)(pv + 40);
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
0x18000ea7c  mov     [rsp+arg_8], rbx
0x18000ea81  mov     [rsp+arg_10], rbp
0x18000ea86  push    rsi
0x18000ea87  push    rdi
0x18000ea88  push    r14
0x18000ea8a  sub     rsp, 40h
0x18000ea8e  mov     esi, r9d
0x18000ea91  movzx   ebp, r8w
0x18000ea95  mov     r14d, edx
0x18000ea98  mov     rdi, rcx
0x18000ea9b  cmp     byte ptr [rcx], 0
0x18000ea9e  jz      loc_18000EB4C
0x18000eaa4  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000eaa9  test    al, al
0x18000eaab  jnz     loc_18000EB4C
0x18000eab1  lea     rbx, [rdi+28h]
0x18000eab5  mov     rcx, rbx; SRWLock
0x18000eab8  call    cs:__imp_AcquireSRWLockExclusive
0x18000eabe  mov     [rsp+58h+var_38], rbx
0x18000eac3  xor     eax, eax
0x18000eac5  mov     [rsp+58h+var_2A], ax
0x18000eaca  mov     [rsp+58h+var_30], r14d
0x18000eacf  mov     [rsp+58h+var_2C], bp
0x18000ead4  mov     [rsp+58h+var_28], esi
0x18000ead8  lea     rcx, [rdi+0E8h]; this
0x18000eadf  lea     r8d, [rax+0Ch]; unsigned __int64
0x18000eae3  lea     rdx, [rsp+58h+var_30]; void *
0x18000eae8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000eaed  cmp     byte ptr [rdi+40h], 0
0x18000eaf1  jnz     short loc_18000EB41
0x18000eaf3  lea     rbx, [rdi+38h]
0x18000eaf7  cmp     qword ptr [rbx], 0
0x18000eafb  jnz     short loc_18000EB2F
0x18000eafd  lea     rcx, [rsp+58h+arg_0]; this
0x18000eb02  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000eb07  xor     r8d, r8d; pcbe
0x18000eb0a  mov     rdx, rdi; pv
0x18000eb0d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000eb14  call    cs:__imp_CreateThreadpoolTimer
0x18000eb1a  mov     rdx, rax
0x18000eb1d  mov     rcx, rbx
0x18000eb20  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000eb25  lea     rcx, [rsp+58h+arg_0]; this
0x18000eb2a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000eb2f  mov     r8d, 1388h
0x18000eb35  lea     rdx, [rdi+40h]
0x18000eb39  mov     rcx, rbx
0x18000eb3c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000eb41  lea     rcx, [rsp+58h+var_38]
0x18000eb46  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000eb4b  nop
0x18000eb4c  mov     rbx, [rsp+58h+arg_8]
0x18000eb51  mov     rbp, [rsp+58h+arg_10]
0x18000eb56  add     rsp, 40h
0x18000eb5a  pop     r14
0x18000eb5c  pop     rdi
0x18000eb5d  pop     rsi
0x18000eb5e  retn
```
