# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14001b6f4`
- end: `0x14001b843`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `335`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140020a40`

## callees

- `0x14001b6f4`
- `0x14002118c`
- `0x140021310`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x14001b803`
- `KERNEL32!SetThreadpoolTimer` at `0x14001b803`
- `KERNEL32!CreateThreadpoolTimer` at `0x14001b7bf`
- `KERNEL32!CreateThreadpoolTimer` at `0x14001b7bf`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001b75e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14001b75e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001b81b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001b81b`
- `KERNEL32!GetLastError` at `0x14001b7a4`
- `KERNEL32!GetLastError` at `0x14001b7a4`
- `KERNEL32!SetLastError` at `0x14001b7d8`
- `KERNEL32!SetLastError` at `0x14001b7d8`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-68h] BYREF
  __int64 v13; // [rsp+28h] [rbp-60h]
  int Source; // [rsp+30h] [rbp-58h] BYREF
  __int16 v15; // [rsp+34h] [rbp-54h]
  __int16 v16; // [rsp+36h] [rbp-52h]
  int v17; // [rsp+38h] [rbp-50h]

  v13 = -2;
  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v16 = 0;
    Source = a2;
    v15 = a3;
    v17 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[29], &Source, 0xCu);
    v8 = (struct _TP_TIMER **)&pv[7];
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !*v8 )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)&pv[7],
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v11 = *v8;
      if ( *v8 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v11, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x14001b6f4  push    rbx
0x14001b6f6  push    rbp
0x14001b6f7  push    rsi
0x14001b6f8  push    rdi
0x14001b6f9  push    r14
0x14001b6fb  push    r15
0x14001b6fd  sub     rsp, 58h
0x14001b701  mov     [rsp+88h+var_60], 0FFFFFFFFFFFFFFFEh
0x14001b70a  mov     rax, cs:__security_cookie
0x14001b711  xor     rax, rsp
0x14001b714  mov     [rsp+88h+var_48], rax
0x14001b719  mov     r14d, r9d
0x14001b71c  movzx   ebp, r8w
0x14001b720  mov     ebx, edx
0x14001b722  mov     rdi, rcx
0x14001b725  xor     r15d, r15d
0x14001b728  cmp     [rcx], r15b
0x14001b72b  jz      loc_14001B828
0x14001b731  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r15b; bool wil::details::g_processShutdownInProgress
0x14001b738  jnz     loc_14001B828
0x14001b73e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14001b745  test    rax, rax
0x14001b748  jz      short loc_14001B757
0x14001b74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b74f  test    al, al
0x14001b751  jnz     loc_14001B828
0x14001b757  lea     rsi, [rdi+28h]
0x14001b75b  mov     rcx, rsi; SRWLock
0x14001b75e  call    cs:__imp_AcquireSRWLockExclusive
0x14001b765  nop     dword ptr [rax+rax+00h]
0x14001b76a  mov     [rsp+88h+var_52], r15w
0x14001b770  mov     [rsp+88h+Source], ebx
0x14001b774  mov     [rsp+88h+var_54], bp
0x14001b779  mov     [rsp+88h+var_50], r14d
0x14001b77e  lea     rcx, [rdi+0E8h]; this
0x14001b785  mov     r8d, 0Ch; SourceSize
0x14001b78b  lea     rdx, [rsp+88h+Source]; Source
0x14001b790  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14001b795  lea     r14, [rdi+38h]
0x14001b799  cmp     [rdi+40h], r15b
0x14001b79d  jnz     short loc_14001B813
0x14001b79f  cmp     [r14], r15
0x14001b7a2  jnz     short loc_14001B7E4
0x14001b7a4  call    cs:__imp_GetLastError
0x14001b7ab  nop     dword ptr [rax+rax+00h]
0x14001b7b0  mov     ebx, eax
0x14001b7b2  xor     r8d, r8d; pcbe
0x14001b7b5  mov     rdx, rdi; pv
0x14001b7b8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14001b7bf  call    cs:__imp_CreateThreadpoolTimer
0x14001b7c6  nop     dword ptr [rax+rax+00h]
0x14001b7cb  mov     rdx, rax
0x14001b7ce  mov     rcx, r14
0x14001b7d1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14001b7d6  mov     ecx, ebx; dwErrCode
0x14001b7d8  call    cs:__imp_SetLastError
0x14001b7df  nop     dword ptr [rax+rax+00h]
0x14001b7e4  mov     rcx, [r14]; pti
0x14001b7e7  test    rcx, rcx
0x14001b7ea  jz      short loc_14001B813
0x14001b7ec  mov     qword ptr [rsp+88h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14001b7f5  mov     r9d, 4E2h; msWindowLength
0x14001b7fb  xor     r8d, r8d; msPeriod
0x14001b7fe  lea     rdx, [rsp+88h+pftDueTime]; pftDueTime
0x14001b803  call    cs:__imp_SetThreadpoolTimer
0x14001b80a  nop     dword ptr [rax+rax+00h]
0x14001b80f  mov     byte ptr [rdi+40h], 1
0x14001b813  test    rsi, rsi
0x14001b816  jz      short loc_14001B828
0x14001b818  mov     rcx, rsi; SRWLock
0x14001b81b  call    cs:__imp_ReleaseSRWLockExclusive
0x14001b822  nop     dword ptr [rax+rax+00h]
0x14001b827  nop
0x14001b828  mov     rcx, [rsp+88h+var_48]
0x14001b82d  xor     rcx, rsp; StackCookie
0x14001b830  call    __security_check_cookie
0x14001b835  add     rsp, 58h
0x14001b839  pop     r15
0x14001b83b  pop     r14
0x14001b83d  pop     rdi
0x14001b83e  pop     rsi
0x14001b83f  pop     rbp
0x14001b840  pop     rbx
0x14001b841  retn
```
