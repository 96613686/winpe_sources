# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180055f04`
- end: `0x180055fff`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `251`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180057a50`

## callees

- `0x180049d00`
- `0x18005277c`
- `0x180052984`
- `0x180052df8`
- `0x180053728`
- `0x180055eb0`
- `0x180055f04`
- `0x180058168`
- `0x180058274`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180055fa9`
- `KERNEL32!CreateThreadpoolTimer` at `0x180055fa9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180055f47`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180055f47`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER *ThreadpoolTimer; // rax
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
                            (PTP_TIMER_CALLBACK)_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)pv + 7,
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
0x180055f04  push    rbx
0x180055f06  push    rbp
0x180055f07  push    rsi
0x180055f08  push    rdi
0x180055f09  push    r14
0x180055f0b  sub     rsp, 50h
0x180055f0f  mov     rax, cs:__security_cookie
0x180055f16  xor     rax, rsp
0x180055f19  mov     [rsp+78h+var_38], rax
0x180055f1e  cmp     byte ptr [rcx], 0
0x180055f21  mov     r14d, r9d
0x180055f24  movzx   ebp, r8w
0x180055f28  mov     esi, edx
0x180055f2a  mov     rdi, rcx
0x180055f2d  jz      loc_180055FE6
0x180055f33  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180055f38  test    al, al
0x180055f3a  jnz     loc_180055FE6
0x180055f40  lea     rbx, [rdi+28h]
0x180055f44  mov     rcx, rbx; SRWLock
0x180055f47  call    cs:__imp_AcquireSRWLockExclusive
0x180055f4e  nop     dword ptr [rax+rax+00h]
0x180055f53  xor     eax, eax
0x180055f55  mov     [rsp+78h+var_50], rbx
0x180055f5a  lea     rcx, [rdi+0E8h]; this
0x180055f61  mov     [rsp+78h+var_42], ax
0x180055f66  lea     rdx, [rsp+78h+var_48]; void *
0x180055f6b  mov     [rsp+78h+var_48], esi
0x180055f6f  mov     [rsp+78h+var_44], bp
0x180055f74  lea     r8d, [rax+0Ch]; unsigned __int64
0x180055f78  mov     [rsp+78h+var_40], r14d
0x180055f7d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180055f82  cmp     byte ptr [rdi+40h], 0
0x180055f86  jnz     short loc_180055FDC
0x180055f88  lea     rbx, [rdi+38h]
0x180055f8c  cmp     qword ptr [rbx], 0
0x180055f90  jnz     short loc_180055FCA
0x180055f92  lea     rcx, [rsp+78h+var_58]; this
0x180055f97  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180055f9c  xor     r8d, r8d; pcbe
0x180055f9f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180055fa6  mov     rdx, rdi; pv
0x180055fa9  call    cs:__imp_CreateThreadpoolTimer
0x180055fb0  nop     dword ptr [rax+rax+00h]
0x180055fb5  mov     rdx, rax
0x180055fb8  mov     rcx, rbx
0x180055fbb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180055fc0  lea     rcx, [rsp+78h+var_58]; this
0x180055fc5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180055fca  mov     r8d, 1388h
0x180055fd0  lea     rdx, [rdi+40h]
0x180055fd4  mov     rcx, rbx
0x180055fd7  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180055fdc  lea     rcx, [rsp+78h+var_50]
0x180055fe1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180055fe6  mov     rcx, [rsp+78h+var_38]
0x180055feb  xor     rcx, rsp; StackCookie
0x180055fee  call    __security_check_cookie
0x180055ff3  add     rsp, 50h
0x180055ff7  pop     r14
0x180055ff9  pop     rdi
0x180055ffa  pop     rsi
0x180055ffb  pop     rbp
0x180055ffc  pop     rbx
0x180055ffd  retn
```
