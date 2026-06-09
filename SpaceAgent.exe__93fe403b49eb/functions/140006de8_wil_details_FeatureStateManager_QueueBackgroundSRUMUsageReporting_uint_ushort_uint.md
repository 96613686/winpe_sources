# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140006de8`
- end: `0x140006ed6`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140008ec0`

## callees

- `0x140004238`
- `0x140004604`
- `0x14000494c`
- `0x140005164`
- `0x140006db4`
- `0x140006de8`
- `0x14000949c`
- `0x1400095a8`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x140006e87`
- `KERNEL32!CreateThreadpoolTimer` at `0x140006e87`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140006e2b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140006e2b`

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
  RTL_SRWLOCK *v10; // [rsp+28h] [rbp-50h] BYREF
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]
  int v14; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v10 = (RTL_SRWLOCK *)(pv + 40);
    v13 = 0;
    v11 = a2;
    v12 = a3;
    v14 = a4;
    wil::details_abi::heap_buffer::push_back((void **)pv + 29, &v11, 0xCu);
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
0x140006de8  push    rbx
0x140006dea  push    rbp
0x140006deb  push    rsi
0x140006dec  push    rdi
0x140006ded  push    r14
0x140006def  sub     rsp, 50h
0x140006df3  mov     rax, cs:__security_cookie
0x140006dfa  xor     rax, rsp
0x140006dfd  mov     [rsp+78h+var_38], rax
0x140006e02  cmp     byte ptr [rcx], 0
0x140006e05  mov     r14d, r9d
0x140006e08  movzx   ebp, r8w
0x140006e0c  mov     esi, edx
0x140006e0e  mov     rdi, rcx
0x140006e11  jz      loc_140006EBE
0x140006e17  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x140006e1c  test    al, al
0x140006e1e  jnz     loc_140006EBE
0x140006e24  lea     rbx, [rdi+28h]
0x140006e28  mov     rcx, rbx; SRWLock
0x140006e2b  call    cs:__imp_AcquireSRWLockExclusive
0x140006e31  xor     eax, eax
0x140006e33  mov     [rsp+78h+var_50], rbx
0x140006e38  lea     rcx, [rdi+0E8h]; this
0x140006e3f  mov     [rsp+78h+var_42], ax
0x140006e44  lea     rdx, [rsp+78h+var_48]; void *
0x140006e49  mov     [rsp+78h+var_48], esi
0x140006e4d  mov     [rsp+78h+var_44], bp
0x140006e52  lea     r8d, [rax+0Ch]; unsigned __int64
0x140006e56  mov     [rsp+78h+var_40], r14d
0x140006e5b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140006e60  cmp     byte ptr [rdi+40h], 0
0x140006e64  jnz     short loc_140006EB4
0x140006e66  lea     rbx, [rdi+38h]
0x140006e6a  cmp     qword ptr [rbx], 0
0x140006e6e  jnz     short loc_140006EA2
0x140006e70  lea     rcx, [rsp+78h+var_58]; this
0x140006e75  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140006e7a  xor     r8d, r8d; pcbe
0x140006e7d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140006e84  mov     rdx, rdi; pv
0x140006e87  call    cs:__imp_CreateThreadpoolTimer
0x140006e8d  mov     rdx, rax
0x140006e90  mov     rcx, rbx
0x140006e93  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x140006e98  lea     rcx, [rsp+78h+var_58]; this
0x140006e9d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140006ea2  mov     r8d, 1388h
0x140006ea8  lea     rdx, [rdi+40h]
0x140006eac  mov     rcx, rbx
0x140006eaf  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x140006eb4  lea     rcx, [rsp+78h+var_50]
0x140006eb9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140006ebe  mov     rcx, [rsp+78h+var_38]
0x140006ec3  xor     rcx, rsp; StackCookie
0x140006ec6  call    __security_check_cookie
0x140006ecb  add     rsp, 50h
0x140006ecf  pop     r14
0x140006ed1  pop     rdi
0x140006ed2  pop     rsi
0x140006ed3  pop     rbp
0x140006ed4  pop     rbx
0x140006ed5  retn
```
