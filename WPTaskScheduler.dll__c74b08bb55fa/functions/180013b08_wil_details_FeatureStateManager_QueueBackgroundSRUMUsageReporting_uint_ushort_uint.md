# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180013b08`
- end: `0x180013bf7`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `239`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180015ec0`

## callees

- `0x180011598`
- `0x1800117f4`
- `0x180011ac0`
- `0x1800120f4`
- `0x180013ad4`
- `0x180013b08`
- `0x180016bb0`
- `0x180016cbc`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013ba7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013ba7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013b4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013b4b`

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
0x180013b08  push    rbx
0x180013b0a  push    rbp
0x180013b0b  push    rsi
0x180013b0c  push    rdi
0x180013b0d  push    r14
0x180013b0f  sub     rsp, 50h
0x180013b13  mov     rax, cs:__security_cookie
0x180013b1a  xor     rax, rsp
0x180013b1d  mov     [rsp+78h+var_38], rax
0x180013b22  mov     r14d, r9d
0x180013b25  movzx   ebp, r8w
0x180013b29  mov     esi, edx
0x180013b2b  mov     rdi, rcx
0x180013b2e  cmp     byte ptr [rcx], 0
0x180013b31  jz      loc_180013BDF
0x180013b37  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180013b3c  test    al, al
0x180013b3e  jnz     loc_180013BDF
0x180013b44  lea     rbx, [rdi+28h]
0x180013b48  mov     rcx, rbx; SRWLock
0x180013b4b  call    cs:__imp_AcquireSRWLockExclusive
0x180013b51  mov     [rsp+78h+var_50], rbx
0x180013b56  xor     eax, eax
0x180013b58  mov     [rsp+78h+var_42], ax
0x180013b5d  mov     [rsp+78h+var_48], esi
0x180013b61  mov     [rsp+78h+var_44], bp
0x180013b66  mov     [rsp+78h+var_40], r14d
0x180013b6b  lea     rcx, [rdi+0E8h]; this
0x180013b72  lea     r8d, [rax+0Ch]; unsigned __int64
0x180013b76  lea     rdx, [rsp+78h+var_48]; void *
0x180013b7b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013b80  cmp     byte ptr [rdi+40h], 0
0x180013b84  jnz     short loc_180013BD4
0x180013b86  lea     rbx, [rdi+38h]
0x180013b8a  cmp     qword ptr [rbx], 0
0x180013b8e  jnz     short loc_180013BC2
0x180013b90  lea     rcx, [rsp+78h+var_58]; this
0x180013b95  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180013b9a  xor     r8d, r8d; pcbe
0x180013b9d  mov     rdx, rdi; pv
0x180013ba0  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180013ba7  call    cs:__imp_CreateThreadpoolTimer
0x180013bad  mov     rdx, rax
0x180013bb0  mov     rcx, rbx
0x180013bb3  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180013bb8  lea     rcx, [rsp+78h+var_58]; this
0x180013bbd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180013bc2  mov     r8d, 1388h
0x180013bc8  lea     rdx, [rdi+40h]
0x180013bcc  mov     rcx, rbx
0x180013bcf  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180013bd4  lea     rcx, [rsp+78h+var_50]
0x180013bd9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013bde  nop
0x180013bdf  mov     rcx, [rsp+78h+var_38]
0x180013be4  xor     rcx, rsp; StackCookie
0x180013be7  call    __security_check_cookie
0x180013bec  add     rsp, 50h
0x180013bf0  pop     r14
0x180013bf2  pop     rdi
0x180013bf3  pop     rsi
0x180013bf4  pop     rbp
0x180013bf5  pop     rbx
0x180013bf6  retn
```
