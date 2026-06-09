# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18001aac0`
- end: `0x18001abb5`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `245`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180011f50`

## callees

- `0x18000debc`
- `0x180010240`
- `0x180010490`
- `0x180011e58`
- `0x18001aac0`
- `0x18001ac90`
- `0x18001adc8`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ab03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ab03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ab7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ab7b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ab5f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ab5f`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[4]; // [rsp+20h] [rbp-58h] BYREF
  DWORD dwErrCode; // [rsp+24h] [rbp-54h]
  RTL_SRWLOCK *v11; // [rsp+28h] [rbp-50h] BYREF
  int v12; // [rsp+30h] [rbp-48h] BYREF
  __int16 v13; // [rsp+34h] [rbp-44h]
  __int16 v14; // [rsp+36h] [rbp-42h]
  int v15; // [rsp+38h] [rbp-40h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v11 = (RTL_SRWLOCK *)(pv + 40);
    v14 = 0;
    v12 = a2;
    v13 = a3;
    v15 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v12, 0xCu);
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
        if ( !v9[0] )
          SetLastError(dwErrCode);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
}

```

## disassembly

```asm
0x18001aac0  push    rbx
0x18001aac2  push    rbp
0x18001aac3  push    rsi
0x18001aac4  push    rdi
0x18001aac5  push    r14
0x18001aac7  sub     rsp, 50h
0x18001aacb  mov     rax, cs:__security_cookie
0x18001aad2  xor     rax, rsp
0x18001aad5  mov     [rsp+78h+var_38], rax
0x18001aada  cmp     byte ptr [rcx], 0
0x18001aadd  mov     r14d, r9d
0x18001aae0  movzx   ebp, r8w
0x18001aae4  mov     esi, edx
0x18001aae6  mov     rdi, rcx
0x18001aae9  jz      loc_18001AB9D
0x18001aaef  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18001aaf4  test    al, al
0x18001aaf6  jnz     loc_18001AB9D
0x18001aafc  lea     rbx, [rdi+28h]
0x18001ab00  mov     rcx, rbx; SRWLock
0x18001ab03  call    cs:__imp_AcquireSRWLockExclusive
0x18001ab09  xor     eax, eax
0x18001ab0b  mov     [rsp+78h+var_50], rbx
0x18001ab10  lea     rcx, [rdi+0E8h]; this
0x18001ab17  mov     [rsp+78h+var_42], ax
0x18001ab1c  lea     rdx, [rsp+78h+var_48]; void *
0x18001ab21  mov     [rsp+78h+var_48], esi
0x18001ab25  mov     [rsp+78h+var_44], bp
0x18001ab2a  lea     r8d, [rax+0Ch]; unsigned __int64
0x18001ab2e  mov     [rsp+78h+var_40], r14d
0x18001ab33  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001ab38  cmp     byte ptr [rdi+40h], 0
0x18001ab3c  jnz     short loc_18001AB93
0x18001ab3e  lea     rbx, [rdi+38h]
0x18001ab42  cmp     qword ptr [rbx], 0
0x18001ab46  jnz     short loc_18001AB81
0x18001ab48  lea     rcx, [rsp+78h+var_58]; this
0x18001ab4d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001ab52  xor     r8d, r8d; pcbe
0x18001ab55  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001ab5c  mov     rdx, rdi; pv
0x18001ab5f  call    cs:__imp_CreateThreadpoolTimer
0x18001ab65  mov     rdx, rax
0x18001ab68  mov     rcx, rbx
0x18001ab6b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001ab70  cmp     [rsp+78h+var_58], 0
0x18001ab75  jnz     short loc_18001AB81
0x18001ab77  mov     ecx, [rsp+78h+dwErrCode]; dwErrCode
0x18001ab7b  call    cs:__imp_SetLastError
0x18001ab81  mov     r8d, 1388h
0x18001ab87  lea     rdx, [rdi+40h]
0x18001ab8b  mov     rcx, rbx
0x18001ab8e  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18001ab93  lea     rcx, [rsp+78h+var_50]
0x18001ab98  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001ab9d  mov     rcx, [rsp+78h+var_38]
0x18001aba2  xor     rcx, rsp; StackCookie
0x18001aba5  call    __security_check_cookie
0x18001abaa  add     rsp, 50h
0x18001abae  pop     r14
0x18001abb0  pop     rdi
0x18001abb1  pop     rsi
0x18001abb2  pop     rbp
0x18001abb3  pop     rbx
0x18001abb4  retn
```
