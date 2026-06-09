# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180025c0c`
- end: `0x180025cfc`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `240`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001bfb0`

## callees

- `0x180012e40`
- `0x18001ad2c`
- `0x18001b940`
- `0x180025c0c`
- `0x180025d04`
- `0x180025d28`
- `0x180025d70`
- `0x180025d9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025c48`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025c48`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180025caa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180025caa`

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
  int Source; // [rsp+28h] [rbp-30h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-2Ch]
  __int16 v12; // [rsp+2Eh] [rbp-2Ah]
  int v13; // [rsp+30h] [rbp-28h]
  char v14; // [rsp+60h] [rbp+8h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v9 = pv + 40;
    v12 = 0;
    Source = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &Source, 0xCu);
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
0x180025c0c  mov     [rsp+arg_8], rbx
0x180025c11  mov     [rsp+arg_10], rbp
0x180025c16  push    rsi
0x180025c17  push    rdi
0x180025c18  push    r14
0x180025c1a  sub     rsp, 40h
0x180025c1e  mov     esi, r9d
0x180025c21  movzx   ebp, r8w
0x180025c25  mov     r14d, edx
0x180025c28  mov     rdi, rcx
0x180025c2b  cmp     byte ptr [rcx], 0
0x180025c2e  jz      loc_180025CE8
0x180025c34  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180025c39  test    al, al
0x180025c3b  jnz     loc_180025CE8
0x180025c41  lea     rbx, [rdi+28h]
0x180025c45  mov     rcx, rbx; SRWLock
0x180025c48  call    cs:__imp_AcquireSRWLockExclusive
0x180025c4f  nop     dword ptr [rax+rax+00h]
0x180025c54  mov     [rsp+58h+var_38], rbx
0x180025c59  xor     eax, eax
0x180025c5b  mov     [rsp+58h+var_2A], ax
0x180025c60  mov     [rsp+58h+Source], r14d
0x180025c65  mov     [rsp+58h+var_2C], bp
0x180025c6a  mov     [rsp+58h+var_28], esi
0x180025c6e  lea     rcx, [rdi+0E8h]; this
0x180025c75  lea     r8d, [rax+0Ch]; SourceSize
0x180025c79  lea     rdx, [rsp+58h+Source]; Source
0x180025c7e  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180025c83  cmp     byte ptr [rdi+40h], 0
0x180025c87  jnz     short loc_180025CDD
0x180025c89  lea     rbx, [rdi+38h]
0x180025c8d  cmp     qword ptr [rbx], 0
0x180025c91  jnz     short loc_180025CCB
0x180025c93  lea     rcx, [rsp+58h+arg_0]; this
0x180025c98  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180025c9d  xor     r8d, r8d; pcbe
0x180025ca0  mov     rdx, rdi; pv
0x180025ca3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180025caa  call    cs:__imp_CreateThreadpoolTimer
0x180025cb1  nop     dword ptr [rax+rax+00h]
0x180025cb6  mov     rdx, rax
0x180025cb9  mov     rcx, rbx
0x180025cbc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180025cc1  lea     rcx, [rsp+58h+arg_0]; this
0x180025cc6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180025ccb  mov     r8d, 1388h
0x180025cd1  lea     rdx, [rdi+40h]
0x180025cd5  mov     rcx, rbx
0x180025cd8  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180025cdd  lea     rcx, [rsp+58h+var_38]
0x180025ce2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180025ce7  nop
0x180025ce8  mov     rbx, [rsp+58h+arg_8]
0x180025ced  mov     rbp, [rsp+58h+arg_10]
0x180025cf2  add     rsp, 40h
0x180025cf6  pop     r14
0x180025cf8  pop     rdi
0x180025cf9  pop     rsi
0x180025cfa  retn
```
