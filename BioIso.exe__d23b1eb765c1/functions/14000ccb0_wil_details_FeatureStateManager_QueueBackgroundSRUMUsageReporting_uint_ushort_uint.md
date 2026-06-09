# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14000ccb0`
- end: `0x14000cda0`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `240`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400292b0`

## callees

- `0x14000bd48`
- `0x14000c604`
- `0x14000c628`
- `0x14000c670`
- `0x14000c69c`
- `0x14000ccb0`
- `0x140013958`
- `0x140029808`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ccec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ccec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000cd4e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000cd4e`

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
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v9);
  }
}

```

## disassembly

```asm
0x14000ccb0  mov     [rsp+arg_8], rbx
0x14000ccb5  mov     [rsp+arg_10], rbp
0x14000ccba  push    rsi
0x14000ccbb  push    rdi
0x14000ccbc  push    r14
0x14000ccbe  sub     rsp, 40h
0x14000ccc2  mov     esi, r9d
0x14000ccc5  movzx   ebp, r8w
0x14000ccc9  mov     r14d, edx
0x14000cccc  mov     rdi, rcx
0x14000cccf  cmp     byte ptr [rcx], 0
0x14000ccd2  jz      loc_14000CD8C
0x14000ccd8  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x14000ccdd  test    al, al
0x14000ccdf  jnz     loc_14000CD8C
0x14000cce5  lea     rbx, [rdi+28h]
0x14000cce9  mov     rcx, rbx; SRWLock
0x14000ccec  call    cs:__imp_AcquireSRWLockExclusive
0x14000ccf3  nop     dword ptr [rax+rax+00h]
0x14000ccf8  mov     [rsp+58h+var_38], rbx
0x14000ccfd  xor     eax, eax
0x14000ccff  mov     [rsp+58h+var_2A], ax
0x14000cd04  mov     [rsp+58h+var_30], r14d
0x14000cd09  mov     [rsp+58h+var_2C], bp
0x14000cd0e  mov     [rsp+58h+var_28], esi
0x14000cd12  lea     rcx, [rdi+0E8h]; this
0x14000cd19  lea     r8d, [rax+0Ch]; unsigned __int64
0x14000cd1d  lea     rdx, [rsp+58h+var_30]; void *
0x14000cd22  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000cd27  cmp     byte ptr [rdi+40h], 0
0x14000cd2b  jnz     short loc_14000CD81
0x14000cd2d  lea     rbx, [rdi+38h]
0x14000cd31  cmp     qword ptr [rbx], 0
0x14000cd35  jnz     short loc_14000CD6F
0x14000cd37  lea     rcx, [rsp+58h+arg_0]; this
0x14000cd3c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000cd41  xor     r8d, r8d; pcbe
0x14000cd44  mov     rdx, rdi; pv
0x14000cd47  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000cd4e  call    cs:__imp_CreateThreadpoolTimer
0x14000cd55  nop     dword ptr [rax+rax+00h]
0x14000cd5a  mov     rdx, rax
0x14000cd5d  mov     rcx, rbx
0x14000cd60  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14000cd65  lea     rcx, [rsp+58h+arg_0]; this
0x14000cd6a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000cd6f  mov     r8d, 1388h
0x14000cd75  lea     rdx, [rdi+40h]
0x14000cd79  mov     rcx, rbx
0x14000cd7c  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x14000cd81  lea     rcx, [rsp+58h+var_38]
0x14000cd86  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14000cd8b  nop
0x14000cd8c  mov     rbx, [rsp+58h+arg_8]
0x14000cd91  mov     rbp, [rsp+58h+arg_10]
0x14000cd96  add     rsp, 40h
0x14000cd9a  pop     r14
0x14000cd9c  pop     rdi
0x14000cd9d  pop     rsi
0x14000cd9e  retn
```
