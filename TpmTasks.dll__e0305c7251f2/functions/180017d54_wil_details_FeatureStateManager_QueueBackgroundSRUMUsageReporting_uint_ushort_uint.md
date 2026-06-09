# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180017d54`
- end: `0x180017e37`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001e250`

## callees

- `0x18000dd54`
- `0x18000e4cc`
- `0x18000ea88`
- `0x180010a4c`
- `0x180017b38`
- `0x180017d54`
- `0x180024720`
- `0x18002495c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017d90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017d90`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017dec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180017dec`

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
0x180017d54  mov     [rsp+arg_8], rbx
0x180017d59  mov     [rsp+arg_10], rbp
0x180017d5e  push    rsi
0x180017d5f  push    rdi
0x180017d60  push    r14
0x180017d62  sub     rsp, 40h
0x180017d66  mov     esi, r9d
0x180017d69  movzx   ebp, r8w
0x180017d6d  mov     r14d, edx
0x180017d70  mov     rdi, rcx
0x180017d73  cmp     byte ptr [rcx], 0
0x180017d76  jz      loc_180017E24
0x180017d7c  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180017d81  test    al, al
0x180017d83  jnz     loc_180017E24
0x180017d89  lea     rbx, [rdi+28h]
0x180017d8d  mov     rcx, rbx; SRWLock
0x180017d90  call    cs:__imp_AcquireSRWLockExclusive
0x180017d96  mov     [rsp+58h+var_38], rbx
0x180017d9b  xor     eax, eax
0x180017d9d  mov     [rsp+58h+var_2A], ax
0x180017da2  mov     [rsp+58h+var_30], r14d
0x180017da7  mov     [rsp+58h+var_2C], bp
0x180017dac  mov     [rsp+58h+var_28], esi
0x180017db0  lea     rcx, [rdi+0E8h]; this
0x180017db7  lea     r8d, [rax+0Ch]; unsigned __int64
0x180017dbb  lea     rdx, [rsp+58h+var_30]; void *
0x180017dc0  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180017dc5  cmp     byte ptr [rdi+40h], 0
0x180017dc9  jnz     short loc_180017E19
0x180017dcb  lea     rbx, [rdi+38h]
0x180017dcf  cmp     qword ptr [rbx], 0
0x180017dd3  jnz     short loc_180017E07
0x180017dd5  lea     rcx, [rsp+58h+arg_0]; this
0x180017dda  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180017ddf  xor     r8d, r8d; pcbe
0x180017de2  mov     rdx, rdi; pv
0x180017de5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180017dec  call    cs:__imp_CreateThreadpoolTimer
0x180017df2  mov     rdx, rax
0x180017df5  mov     rcx, rbx
0x180017df8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180017dfd  lea     rcx, [rsp+58h+arg_0]; this
0x180017e02  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180017e07  mov     r8d, 1388h
0x180017e0d  lea     rdx, [rdi+40h]
0x180017e11  mov     rcx, rbx
0x180017e14  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180017e19  lea     rcx, [rsp+58h+var_38]
0x180017e1e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017e23  nop
0x180017e24  mov     rbx, [rsp+58h+arg_8]
0x180017e29  mov     rbp, [rsp+58h+arg_10]
0x180017e2e  add     rsp, 40h
0x180017e32  pop     r14
0x180017e34  pop     rdi
0x180017e35  pop     rsi
0x180017e36  retn
```
