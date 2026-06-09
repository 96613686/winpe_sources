# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18002bd60`
- end: `0x18002be40`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `224`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180038020`

## callees

- `0x18001d670`
- `0x1800276f8`
- `0x18002791c`
- `0x18002bd60`
- `0x18002be48`
- `0x18002be6c`
- `0x18002bed0`
- `0x18002bffc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bd94`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002bd94`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002bdf6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002bdf6`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  int Source; // [rsp+20h] [rbp-48h] BYREF
  __int16 v10; // [rsp+24h] [rbp-44h]
  __int16 v11; // [rsp+26h] [rbp-42h]
  int v12; // [rsp+28h] [rbp-40h]
  RTL_SRWLOCK *v13; // [rsp+30h] [rbp-38h] BYREF

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v13 = (RTL_SRWLOCK *)(pv + 40);
    v11 = 0;
    Source = a2;
    v10 = a3;
    v12 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &Source, 0xCu);
    if ( !pv[64] )
    {
      if ( !*((_QWORD *)pv + 7) )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&Source);
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          pv + 56,
          ThreadpoolTimer);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&Source);
      }
      wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)pv + 7, pv + 64, 5000);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  }
}

```

## disassembly

```asm
0x18002bd60  push    rbx
0x18002bd62  push    rbp
0x18002bd63  push    rsi
0x18002bd64  push    rdi
0x18002bd65  push    r14
0x18002bd67  sub     rsp, 40h
0x18002bd6b  mov     r14d, r9d
0x18002bd6e  movzx   ebp, r8w
0x18002bd72  mov     esi, edx
0x18002bd74  mov     rdi, rcx
0x18002bd77  cmp     byte ptr [rcx], 0
0x18002bd7a  jz      loc_18002BE34
0x18002bd80  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002bd85  test    al, al
0x18002bd87  jnz     loc_18002BE34
0x18002bd8d  lea     rbx, [rdi+28h]
0x18002bd91  mov     rcx, rbx; SRWLock
0x18002bd94  call    cs:__imp_AcquireSRWLockExclusive
0x18002bd9b  nop     dword ptr [rax+rax+00h]
0x18002bda0  mov     [rsp+68h+var_38], rbx
0x18002bda5  xor     eax, eax
0x18002bda7  mov     [rsp+68h+var_42], ax
0x18002bdac  mov     [rsp+68h+Source], esi
0x18002bdb0  mov     [rsp+68h+var_44], bp
0x18002bdb5  mov     [rsp+68h+var_40], r14d
0x18002bdba  lea     rcx, [rdi+0E8h]; this
0x18002bdc1  lea     r8d, [rax+0Ch]; SourceSize
0x18002bdc5  lea     rdx, [rsp+68h+Source]; Source
0x18002bdca  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002bdcf  cmp     byte ptr [rdi+40h], 0
0x18002bdd3  jnz     short loc_18002BE29
0x18002bdd5  lea     rbx, [rdi+38h]
0x18002bdd9  cmp     qword ptr [rbx], 0
0x18002bddd  jnz     short loc_18002BE17
0x18002bddf  lea     rcx, [rsp+68h+Source]; this
0x18002bde4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002bde9  xor     r8d, r8d; pcbe
0x18002bdec  mov     rdx, rdi; pv
0x18002bdef  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002bdf6  call    cs:__imp_CreateThreadpoolTimer
0x18002bdfd  nop     dword ptr [rax+rax+00h]
0x18002be02  mov     rdx, rax
0x18002be05  mov     rcx, rbx
0x18002be08  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002be0d  lea     rcx, [rsp+68h+Source]; this
0x18002be12  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002be17  mov     r8d, 1388h
0x18002be1d  lea     rdx, [rdi+40h]
0x18002be21  mov     rcx, rbx
0x18002be24  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18002be29  lea     rcx, [rsp+68h+var_38]
0x18002be2e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002be33  nop
0x18002be34  add     rsp, 40h
0x18002be38  pop     r14
0x18002be3a  pop     rdi
0x18002be3b  pop     rsi
0x18002be3c  pop     rbp
0x18002be3d  pop     rbx
0x18002be3e  retn
```
