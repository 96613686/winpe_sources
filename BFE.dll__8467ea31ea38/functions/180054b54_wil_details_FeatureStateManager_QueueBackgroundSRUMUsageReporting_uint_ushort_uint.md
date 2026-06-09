# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180054b54`
- end: `0x180054c27`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `211`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18005e340`

## callees

- `0x1800439cc`
- `0x180054b54`
- `0x180054d00`
- `0x180054d20`
- `0x180054d80`
- `0x180054da4`
- `0x180054ecc`
- `0x18005e9f4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180054be4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180054be4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054b88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180054b88`

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
0x180054b54  push    rbx
0x180054b56  push    rbp
0x180054b57  push    rsi
0x180054b58  push    rdi
0x180054b59  push    r14
0x180054b5b  sub     rsp, 40h
0x180054b5f  mov     r14d, r9d
0x180054b62  movzx   ebp, r8w
0x180054b66  mov     esi, edx
0x180054b68  mov     rdi, rcx
0x180054b6b  cmp     byte ptr [rcx], 0
0x180054b6e  jz      loc_180054C1C
0x180054b74  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180054b79  test    al, al
0x180054b7b  jnz     loc_180054C1C
0x180054b81  lea     rbx, [rdi+28h]
0x180054b85  mov     rcx, rbx; SRWLock
0x180054b88  call    cs:__imp_AcquireSRWLockExclusive
0x180054b8e  mov     [rsp+68h+var_38], rbx
0x180054b93  xor     eax, eax
0x180054b95  mov     [rsp+68h+var_42], ax
0x180054b9a  mov     [rsp+68h+var_48], esi
0x180054b9e  mov     [rsp+68h+var_44], bp
0x180054ba3  mov     [rsp+68h+var_40], r14d
0x180054ba8  lea     rcx, [rdi+0E8h]; this
0x180054baf  lea     r8d, [rax+0Ch]; unsigned __int64
0x180054bb3  lea     rdx, [rsp+68h+var_48]; void *
0x180054bb8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180054bbd  cmp     byte ptr [rdi+40h], 0
0x180054bc1  jnz     short loc_180054C11
0x180054bc3  lea     rbx, [rdi+38h]
0x180054bc7  cmp     qword ptr [rbx], 0
0x180054bcb  jnz     short loc_180054BFF
0x180054bcd  lea     rcx, [rsp+68h+var_48]; this
0x180054bd2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180054bd7  xor     r8d, r8d; pcbe
0x180054bda  mov     rdx, rdi; pv
0x180054bdd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180054be4  call    cs:__imp_CreateThreadpoolTimer
0x180054bea  mov     rdx, rax
0x180054bed  mov     rcx, rbx
0x180054bf0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180054bf5  lea     rcx, [rsp+68h+var_48]; this
0x180054bfa  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180054bff  mov     r8d, 1388h
0x180054c05  lea     rdx, [rdi+40h]
0x180054c09  mov     rcx, rbx
0x180054c0c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180054c11  lea     rcx, [rsp+68h+var_38]
0x180054c16  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180054c1b  nop
0x180054c1c  add     rsp, 40h
0x180054c20  pop     r14
0x180054c22  pop     rdi
0x180054c23  pop     rsi
0x180054c24  pop     rbp
0x180054c25  pop     rbx
0x180054c26  retn
```
