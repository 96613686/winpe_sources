# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180004b2c`
- end: `0x180004c0f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `227`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000f8c0`

## callees

- `0x180004b2c`
- `0x180004ce0`
- `0x180004d00`
- `0x180004d44`
- `0x180004d64`
- `0x180004d90`
- `0x180005250`
- `0x18001012c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004b68`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004b68`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004bc4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004bc4`

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
0x180004b2c  mov     [rsp+arg_8], rbx
0x180004b31  mov     [rsp+arg_10], rbp
0x180004b36  push    rsi
0x180004b37  push    rdi
0x180004b38  push    r14
0x180004b3a  sub     rsp, 40h
0x180004b3e  mov     esi, r9d
0x180004b41  movzx   ebp, r8w
0x180004b45  mov     r14d, edx
0x180004b48  mov     rdi, rcx
0x180004b4b  cmp     byte ptr [rcx], 0
0x180004b4e  jz      loc_180004BFC
0x180004b54  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180004b59  test    al, al
0x180004b5b  jnz     loc_180004BFC
0x180004b61  lea     rbx, [rdi+28h]
0x180004b65  mov     rcx, rbx; SRWLock
0x180004b68  call    cs:__imp_AcquireSRWLockExclusive
0x180004b6e  mov     [rsp+58h+var_38], rbx
0x180004b73  xor     eax, eax
0x180004b75  mov     [rsp+58h+var_2A], ax
0x180004b7a  mov     [rsp+58h+var_30], r14d
0x180004b7f  mov     [rsp+58h+var_2C], bp
0x180004b84  mov     [rsp+58h+var_28], esi
0x180004b88  lea     rcx, [rdi+0E8h]; this
0x180004b8f  lea     r8d, [rax+0Ch]; unsigned __int64
0x180004b93  lea     rdx, [rsp+58h+var_30]; void *
0x180004b98  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180004b9d  cmp     byte ptr [rdi+40h], 0
0x180004ba1  jnz     short loc_180004BF1
0x180004ba3  lea     rbx, [rdi+38h]
0x180004ba7  cmp     qword ptr [rbx], 0
0x180004bab  jnz     short loc_180004BDF
0x180004bad  lea     rcx, [rsp+58h+arg_0]; this
0x180004bb2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180004bb7  xor     r8d, r8d; pcbe
0x180004bba  mov     rdx, rdi; pv
0x180004bbd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004bc4  call    cs:__imp_CreateThreadpoolTimer
0x180004bca  mov     rdx, rax
0x180004bcd  mov     rcx, rbx
0x180004bd0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180004bd5  lea     rcx, [rsp+58h+arg_0]; this
0x180004bda  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180004bdf  mov     r8d, 1388h
0x180004be5  lea     rdx, [rdi+40h]
0x180004be9  mov     rcx, rbx
0x180004bec  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180004bf1  lea     rcx, [rsp+58h+var_38]
0x180004bf6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180004bfb  nop
0x180004bfc  mov     rbx, [rsp+58h+arg_8]
0x180004c01  mov     rbp, [rsp+58h+arg_10]
0x180004c06  add     rsp, 40h
0x180004c0a  pop     r14
0x180004c0c  pop     rdi
0x180004c0d  pop     rsi
0x180004c0e  retn
```
