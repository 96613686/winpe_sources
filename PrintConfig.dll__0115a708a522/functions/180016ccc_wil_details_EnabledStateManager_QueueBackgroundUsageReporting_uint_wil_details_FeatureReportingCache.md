# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180016ccc`
- end: `0x180016e58`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `396`
- prototype: `void __fastcall(char *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001823c`

## callees

- `0x18000d09c`
- `0x18000d194`
- `0x18000d538`
- `0x180016ccc`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180016dd5`
- `KERNEL32!CreateThreadpoolTimer` at `0x180016dd5`
- `KERNEL32!SetThreadpoolTimer` at `0x180016e1f`
- `KERNEL32!SetThreadpoolTimer` at `0x180016e1f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016d27`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180016d27`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180016e37`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180016e37`
- `KERNEL32!SetLastError` at `0x180016dee`
- `KERNEL32!SetLastError` at `0x180016dee`
- `KERNEL32!GetLastError` at `0x180016dba`
- `KERNEL32!GetLastError` at `0x180016dba`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rcx
  struct _TP_TIMER **v7; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v10; // rcx
  _DWORD Source[2]; // [rsp+28h] [rbp-30h] BYREF
  struct wil_details_FeatureReportingCache *v12; // [rsp+30h] [rbp-28h]
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv)) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    if ( *(_DWORD *)pv
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v6)) )
    {
      Source[0] = a2;
      Source[1] = 0;
      v12 = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 48), 0x10u) )
      {
        memcpy_s_0(
          *((void *const *)pv + 7),
          (*((_QWORD *)pv + 8) - *((_QWORD *)pv + 7)) & -(__int64)(*((_QWORD *)pv + 7) < *((_QWORD *)pv + 8)),
          Source,
          0x10u);
        *((_QWORD *)pv + 7) += 16LL;
      }
      if ( !pv[24] )
      {
        v7 = (struct _TP_TIMER **)(pv + 16);
        if ( !*((_QWORD *)pv + 2) )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              (PTP_TIMER_CALLBACK)_lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            (struct _TP_TIMER **)pv + 2,
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        v10 = *v7;
        if ( *v7 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v10, &pftDueTime, 0, 0x124F8u);
          pv[24] = 1;
        }
      }
    }
    if ( pv != (char *)-8LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 1);
  }
}

```

## disassembly

```asm
0x180016ccc  push    rsi
0x180016cce  push    rdi
0x180016ccf  push    r14
0x180016cd1  sub     rsp, 40h
0x180016cd5  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180016cde  mov     [rsp+58h+arg_8], rbx
0x180016ce3  mov     [rsp+58h+arg_10], rbp
0x180016ce8  mov     rbx, r8
0x180016ceb  mov     ebp, edx
0x180016ced  mov     rdi, rcx
0x180016cf0  mov     eax, [rcx]
0x180016cf2  test    eax, eax
0x180016cf4  jz      loc_180016E44
0x180016cfa  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180016d01  jnz     loc_180016E44
0x180016d07  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180016d0e  test    rax, rax
0x180016d11  jz      short loc_180016D20
0x180016d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d18  test    al, al
0x180016d1a  jnz     loc_180016E44
0x180016d20  lea     rsi, [rdi+8]
0x180016d24  mov     rcx, rsi; SRWLock
0x180016d27  call    cs:__imp_AcquireSRWLockExclusive
0x180016d2e  nop     dword ptr [rax+rax+00h]
0x180016d33  mov     eax, [rdi]
0x180016d35  test    eax, eax
0x180016d37  jz      loc_180016E2F
0x180016d3d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180016d44  jnz     loc_180016E2F
0x180016d4a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180016d51  test    rax, rax
0x180016d54  jz      short loc_180016D63
0x180016d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d5b  test    al, al
0x180016d5d  jnz     loc_180016E2F
0x180016d63  mov     [rsp+58h+Source], ebp
0x180016d67  xor     eax, eax
0x180016d69  mov     [rsp+58h+var_2C], eax
0x180016d6d  mov     [rsp+58h+var_28], rbx
0x180016d72  lea     ebp, [rax+10h]
0x180016d75  mov     edx, ebp; unsigned __int64
0x180016d77  lea     rcx, [rdi+30h]; this
0x180016d7b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180016d80  test    al, al
0x180016d82  jz      short loc_180016DAA
0x180016d84  mov     rcx, [rdi+38h]; Destination
0x180016d88  mov     rax, [rdi+40h]
0x180016d8c  sub     rax, rcx
0x180016d8f  cmp     rcx, [rdi+40h]
0x180016d93  sbb     rdx, rdx
0x180016d96  and     rdx, rax; DestinationSize
0x180016d99  mov     r9d, ebp; SourceSize
0x180016d9c  lea     r8, [rsp+58h+Source]; Source
0x180016da1  call    memcpy_s_0
0x180016da6  add     [rdi+38h], rbp
0x180016daa  cmp     byte ptr [rdi+18h], 0
0x180016dae  jnz     short loc_180016E2F
0x180016db0  lea     r14, [rdi+10h]
0x180016db4  cmp     qword ptr [r14], 0
0x180016db8  jnz     short loc_180016DFA
0x180016dba  call    cs:__imp_GetLastError
0x180016dc1  nop     dword ptr [rax+rax+00h]
0x180016dc6  mov     ebx, eax
0x180016dc8  xor     r8d, r8d; pcbe
0x180016dcb  mov     rdx, rdi; pv
0x180016dce  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180016dd5  call    cs:__imp_CreateThreadpoolTimer
0x180016ddc  nop     dword ptr [rax+rax+00h]
0x180016de1  mov     rdx, rax
0x180016de4  mov     rcx, r14
0x180016de7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180016dec  mov     ecx, ebx; dwErrCode
0x180016dee  call    cs:__imp_SetLastError
0x180016df5  nop     dword ptr [rax+rax+00h]
0x180016dfa  mov     rcx, [r14]; pti
0x180016dfd  test    rcx, rcx
0x180016e00  jz      short loc_180016E2F
0x180016e02  mov     rax, 0FFFFFFFF4D2FA200h
0x180016e0c  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x180016e11  mov     r9d, 124F8h; msWindowLength
0x180016e17  xor     r8d, r8d; msPeriod
0x180016e1a  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180016e1f  call    cs:__imp_SetThreadpoolTimer
0x180016e26  nop     dword ptr [rax+rax+00h]
0x180016e2b  mov     byte ptr [rdi+18h], 1
0x180016e2f  test    rsi, rsi
0x180016e32  jz      short loc_180016E44
0x180016e34  mov     rcx, rsi; SRWLock
0x180016e37  call    cs:__imp_ReleaseSRWLockExclusive
0x180016e3e  nop     dword ptr [rax+rax+00h]
0x180016e43  nop
0x180016e44  mov     rbx, [rsp+58h+arg_8]
0x180016e49  mov     rbp, [rsp+58h+arg_10]
0x180016e4e  add     rsp, 40h
0x180016e52  pop     r14
0x180016e54  pop     rdi
0x180016e55  pop     rsi
0x180016e56  retn
```
