# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180014d60`
- end: `0x180014e4f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `239`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180017880`

## callees

- `0x18000b810`
- `0x18000bc80`
- `0x18000c020`
- `0x18000d6d0`
- `0x180014d2c`
- `0x180014d60`
- `0x180018d34`
- `0x180018f10`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014da3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014da3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014dff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014dff`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-58h] BYREF
  char *v10; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = pv + 40;
    v13 = 0;
    v11 = a2;
    v12 = a3;
    v14 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v11, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x180014d60  push    rbx
0x180014d62  push    rbp
0x180014d63  push    rsi
0x180014d64  push    rdi
0x180014d65  push    r14
0x180014d67  sub     rsp, 50h
0x180014d6b  mov     rax, cs:__security_cookie
0x180014d72  xor     rax, rsp
0x180014d75  mov     [rsp+78h+var_38], rax
0x180014d7a  mov     r14d, r9d
0x180014d7d  movzx   ebp, r8w
0x180014d81  mov     esi, edx
0x180014d83  mov     rdi, rcx
0x180014d86  cmp     byte ptr [rcx], 0
0x180014d89  jz      loc_180014E37
0x180014d8f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180014d94  test    al, al
0x180014d96  jnz     loc_180014E37
0x180014d9c  lea     rbx, [rdi+28h]
0x180014da0  mov     rcx, rbx; SRWLock
0x180014da3  call    cs:__imp_AcquireSRWLockExclusive
0x180014da9  mov     [rsp+78h+var_50], rbx
0x180014dae  xor     eax, eax
0x180014db0  mov     [rsp+78h+var_42], ax
0x180014db5  mov     [rsp+78h+var_48], esi
0x180014db9  mov     [rsp+78h+var_44], bp
0x180014dbe  mov     [rsp+78h+var_40], r14d
0x180014dc3  lea     rcx, [rdi+0E8h]; this
0x180014dca  lea     r8d, [rax+0Ch]; unsigned __int64
0x180014dce  lea     rdx, [rsp+78h+var_48]; void *
0x180014dd3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014dd8  cmp     byte ptr [rdi+40h], 0
0x180014ddc  jnz     short loc_180014E2C
0x180014dde  lea     rbx, [rdi+38h]
0x180014de2  cmp     qword ptr [rbx], 0
0x180014de6  jnz     short loc_180014E1A
0x180014de8  lea     rcx, [rsp+78h+var_58]; this
0x180014ded  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180014df2  xor     r8d, r8d; pcbe
0x180014df5  mov     rdx, rdi; pv
0x180014df8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180014dff  call    cs:__imp_CreateThreadpoolTimer
0x180014e05  mov     rdx, rax
0x180014e08  mov     rcx, rbx
0x180014e0b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180014e10  lea     rcx, [rsp+78h+var_58]; this
0x180014e15  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180014e1a  mov     r8d, 1388h
0x180014e20  lea     rdx, [rdi+40h]
0x180014e24  mov     rcx, rbx
0x180014e27  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180014e2c  lea     rcx, [rsp+78h+var_50]
0x180014e31  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014e36  nop
0x180014e37  mov     rcx, [rsp+78h+var_38]
0x180014e3c  xor     rcx, rsp; StackCookie
0x180014e3f  call    __security_check_cookie
0x180014e44  add     rsp, 50h
0x180014e48  pop     r14
0x180014e4a  pop     rdi
0x180014e4b  pop     rsi
0x180014e4c  pop     rbp
0x180014e4d  pop     rbx
0x180014e4e  retn
```
