# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000b8bc`
- end: `0x18000b9aa`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `238`
- prototype: `void __fastcall(char *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180011de0`

## callees

- `0x18000991c`
- `0x18000b49c`
- `0x18000b8bc`
- `0x18000bb00`
- `0x18000bb20`
- `0x18000bb44`
- `0x180012990`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b8ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b8ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b98b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b98b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b956`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b956`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  PTP_TIMER ThreadpoolTimer; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-48h] BYREF
  int v10; // [rsp+28h] [rbp-40h] BYREF
  __int16 v11; // [rsp+2Ch] [rbp-3Ch]
  __int16 v12; // [rsp+2Eh] [rbp-3Ah]
  int v13; // [rsp+30h] [rbp-38h]

  if ( *pv && !wil::ProcessShutdownInProgress((wil *)pv) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v12 = 0;
    v10 = a2;
    v11 = a3;
    v13 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(pv + 232), &v10, 0xCu);
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
    if ( pv != (char *)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
  }
}

```

## disassembly

```asm
0x18000b8bc  push    rbx
0x18000b8be  push    rbp
0x18000b8bf  push    rsi
0x18000b8c0  push    rdi
0x18000b8c1  push    r14
0x18000b8c3  sub     rsp, 40h
0x18000b8c7  mov     rax, cs:__security_cookie
0x18000b8ce  xor     rax, rsp
0x18000b8d1  mov     [rsp+68h+var_30], rax
0x18000b8d6  mov     r14d, r9d
0x18000b8d9  movzx   ebp, r8w
0x18000b8dd  mov     edi, edx
0x18000b8df  mov     rbx, rcx
0x18000b8e2  cmp     byte ptr [rcx], 0
0x18000b8e5  jz      loc_18000B992
0x18000b8eb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000b8f0  test    al, al
0x18000b8f2  jnz     loc_18000B992
0x18000b8f8  lea     rsi, [rbx+28h]
0x18000b8fc  mov     rcx, rsi; SRWLock
0x18000b8ff  call    cs:__imp_AcquireSRWLockExclusive
0x18000b905  xor     eax, eax
0x18000b907  mov     [rsp+68h+var_3A], ax
0x18000b90c  mov     [rsp+68h+var_40], edi
0x18000b910  mov     [rsp+68h+var_3C], bp
0x18000b915  mov     [rsp+68h+var_38], r14d
0x18000b91a  lea     rcx, [rbx+0E8h]; this
0x18000b921  lea     r8d, [rax+0Ch]; unsigned __int64
0x18000b925  lea     rdx, [rsp+68h+var_40]; void *
0x18000b92a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b92f  cmp     byte ptr [rbx+40h], 0
0x18000b933  jnz     short loc_18000B983
0x18000b935  lea     rdi, [rbx+38h]
0x18000b939  cmp     qword ptr [rdi], 0
0x18000b93d  jnz     short loc_18000B971
0x18000b93f  lea     rcx, [rsp+68h+var_48]; this
0x18000b944  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000b949  xor     r8d, r8d; pcbe
0x18000b94c  mov     rdx, rbx; pv
0x18000b94f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b956  call    cs:__imp_CreateThreadpoolTimer
0x18000b95c  mov     rdx, rax
0x18000b95f  mov     rcx, rdi
0x18000b962  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000b967  lea     rcx, [rsp+68h+var_48]; this
0x18000b96c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000b971  mov     r8d, 1388h
0x18000b977  lea     rdx, [rbx+40h]
0x18000b97b  mov     rcx, rdi
0x18000b97e  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000b983  test    rsi, rsi
0x18000b986  jz      short loc_18000B992
0x18000b988  mov     rcx, rsi; SRWLock
0x18000b98b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b991  nop
0x18000b992  mov     rcx, [rsp+68h+var_30]
0x18000b997  xor     rcx, rsp; StackCookie
0x18000b99a  call    __security_check_cookie
0x18000b99f  add     rsp, 40h
0x18000b9a3  pop     r14
0x18000b9a5  pop     rdi
0x18000b9a6  pop     rsi
0x18000b9a7  pop     rbp
0x18000b9a8  pop     rbx
0x18000b9a9  retn
```
