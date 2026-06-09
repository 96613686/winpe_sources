# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800569bc`
- end: `0x180056a9c`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `224`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180060550`

## callees

- `0x180045864`
- `0x1800569bc`
- `0x180056b84`
- `0x180056ba8`
- `0x180056c0c`
- `0x180056c38`
- `0x180056d6c`
- `0x180060c28`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180056a52`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180056a52`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800569f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800569f0`

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
  char *v13; // [rsp+30h] [rbp-38h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v13 = pv + 40;
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
0x1800569bc  push    rbx
0x1800569be  push    rbp
0x1800569bf  push    rsi
0x1800569c0  push    rdi
0x1800569c1  push    r14
0x1800569c3  sub     rsp, 40h
0x1800569c7  mov     r14d, r9d
0x1800569ca  movzx   ebp, r8w
0x1800569ce  mov     esi, edx
0x1800569d0  mov     rdi, rcx
0x1800569d3  cmp     byte ptr [rcx], 0
0x1800569d6  jz      loc_180056A90
0x1800569dc  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800569e1  test    al, al
0x1800569e3  jnz     loc_180056A90
0x1800569e9  lea     rbx, [rdi+28h]
0x1800569ed  mov     rcx, rbx; SRWLock
0x1800569f0  call    cs:__imp_AcquireSRWLockExclusive
0x1800569f7  nop     dword ptr [rax+rax+00h]
0x1800569fc  mov     [rsp+68h+var_38], rbx
0x180056a01  xor     eax, eax
0x180056a03  mov     [rsp+68h+var_42], ax
0x180056a08  mov     [rsp+68h+var_48], esi
0x180056a0c  mov     [rsp+68h+var_44], bp
0x180056a11  mov     [rsp+68h+var_40], r14d
0x180056a16  lea     rcx, [rdi+0E8h]; this
0x180056a1d  lea     r8d, [rax+0Ch]; unsigned __int64
0x180056a21  lea     rdx, [rsp+68h+var_48]; void *
0x180056a26  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180056a2b  cmp     byte ptr [rdi+40h], 0
0x180056a2f  jnz     short loc_180056A85
0x180056a31  lea     rbx, [rdi+38h]
0x180056a35  cmp     qword ptr [rbx], 0
0x180056a39  jnz     short loc_180056A73
0x180056a3b  lea     rcx, [rsp+68h+var_48]; this
0x180056a40  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180056a45  xor     r8d, r8d; pcbe
0x180056a48  mov     rdx, rdi; pv
0x180056a4b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180056a52  call    cs:__imp_CreateThreadpoolTimer
0x180056a59  nop     dword ptr [rax+rax+00h]
0x180056a5e  mov     rdx, rax
0x180056a61  mov     rcx, rbx
0x180056a64  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180056a69  lea     rcx, [rsp+68h+var_48]; this
0x180056a6e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180056a73  mov     r8d, 1388h
0x180056a79  lea     rdx, [rdi+40h]
0x180056a7d  mov     rcx, rbx
0x180056a80  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180056a85  lea     rcx, [rsp+68h+var_38]
0x180056a8a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180056a8f  nop
0x180056a90  add     rsp, 40h
0x180056a94  pop     r14
0x180056a96  pop     rdi
0x180056a97  pop     rsi
0x180056a98  pop     rbp
0x180056a99  pop     rbx
0x180056a9a  retn
```
