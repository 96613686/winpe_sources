# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001c7d0`
- end: `0x18001c952`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `386`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ce40`

## callees

- `0x1800124c0`
- `0x1800125b8`
- `0x180013758`
- `0x18001c7d0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c931`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c931`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c821`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001c821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c8e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c8e8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c8cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001c8cf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c919`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c919`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  struct _TP_TIMER **v6; // r14
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v9; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v11; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( LODWORD(pv->Ptr)
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = a2;
      Source[1] = 0;
      v11 = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[6], 0x10u) )
      {
        memcpy_s(pv[7].Ptr, ((char *)pv[8].Ptr - (char *)pv[7].Ptr) & -(__int64)(pv[7].Ptr < pv[8].Ptr), Source, 0x10u);
        pv[7].Ptr = (char *)pv[7].Ptr + 16;
      }
      if ( !LOBYTE(pv[3].Ptr) )
      {
        v6 = (struct _TP_TIMER **)&pv[2];
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            &pv[2],
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        v9 = *v6;
        if ( *v6 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v9, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
    }
    if ( pv != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(pv + 1);
  }
}

```

## disassembly

```asm
0x18001c7d0  mov     [rsp+arg_8], rbx
0x18001c7d5  mov     [rsp+arg_10], rbp
0x18001c7da  push    rsi
0x18001c7db  push    rdi
0x18001c7dc  push    r14
0x18001c7de  sub     rsp, 30h
0x18001c7e2  mov     rbx, r8
0x18001c7e5  mov     ebp, edx
0x18001c7e7  mov     rdi, rcx
0x18001c7ea  mov     eax, [rcx]
0x18001c7ec  test    eax, eax
0x18001c7ee  jz      loc_18001C93E
0x18001c7f4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001c7fb  jnz     loc_18001C93E
0x18001c801  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c808  test    rax, rax
0x18001c80b  jz      short loc_18001C81A
0x18001c80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c812  test    al, al
0x18001c814  jnz     loc_18001C93E
0x18001c81a  lea     rsi, [rdi+8]
0x18001c81e  mov     rcx, rsi; SRWLock
0x18001c821  call    cs:__imp_AcquireSRWLockExclusive
0x18001c828  nop     dword ptr [rax+rax+00h]
0x18001c82d  mov     eax, [rdi]
0x18001c82f  test    eax, eax
0x18001c831  jz      loc_18001C929
0x18001c837  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001c83e  jnz     loc_18001C929
0x18001c844  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001c84b  test    rax, rax
0x18001c84e  jz      short loc_18001C85D
0x18001c850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c855  test    al, al
0x18001c857  jnz     loc_18001C929
0x18001c85d  mov     [rsp+48h+Source], ebp
0x18001c861  xor     eax, eax
0x18001c863  mov     [rsp+48h+var_24], eax
0x18001c867  mov     [rsp+48h+var_20], rbx
0x18001c86c  lea     ebp, [rax+10h]
0x18001c86f  mov     edx, ebp; unsigned __int64
0x18001c871  lea     rcx, [rdi+30h]; this
0x18001c875  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001c87a  test    al, al
0x18001c87c  jz      short loc_18001C8A4
0x18001c87e  mov     rcx, [rdi+38h]; Destination
0x18001c882  mov     rax, [rdi+40h]
0x18001c886  sub     rax, rcx
0x18001c889  cmp     rcx, [rdi+40h]
0x18001c88d  sbb     rdx, rdx
0x18001c890  and     rdx, rax; DestinationSize
0x18001c893  mov     r9d, ebp; SourceSize
0x18001c896  lea     r8, [rsp+48h+Source]; Source
0x18001c89b  call    memcpy_s
0x18001c8a0  add     [rdi+38h], rbp
0x18001c8a4  cmp     byte ptr [rdi+18h], 0
0x18001c8a8  jnz     short loc_18001C929
0x18001c8aa  lea     r14, [rdi+10h]
0x18001c8ae  cmp     qword ptr [r14], 0
0x18001c8b2  jnz     short loc_18001C8F4
0x18001c8b4  call    cs:__imp_GetLastError
0x18001c8bb  nop     dword ptr [rax+rax+00h]
0x18001c8c0  mov     ebx, eax
0x18001c8c2  xor     r8d, r8d; pcbe
0x18001c8c5  mov     rdx, rdi; pv
0x18001c8c8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001c8cf  call    cs:__imp_CreateThreadpoolTimer
0x18001c8d6  nop     dword ptr [rax+rax+00h]
0x18001c8db  mov     rdx, rax
0x18001c8de  mov     rcx, r14
0x18001c8e1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001c8e6  mov     ecx, ebx; dwErrCode
0x18001c8e8  call    cs:__imp_SetLastError
0x18001c8ef  nop     dword ptr [rax+rax+00h]
0x18001c8f4  mov     rcx, [r14]; pti
0x18001c8f7  test    rcx, rcx
0x18001c8fa  jz      short loc_18001C929
0x18001c8fc  mov     rax, 0FFFFFFFF4D2FA200h
0x18001c906  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18001c90b  mov     r9d, 124F8h; msWindowLength
0x18001c911  xor     r8d, r8d; msPeriod
0x18001c914  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18001c919  call    cs:__imp_SetThreadpoolTimer
0x18001c920  nop     dword ptr [rax+rax+00h]
0x18001c925  mov     byte ptr [rdi+18h], 1
0x18001c929  test    rsi, rsi
0x18001c92c  jz      short loc_18001C93E
0x18001c92e  mov     rcx, rsi; SRWLock
0x18001c931  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c938  nop     dword ptr [rax+rax+00h]
0x18001c93d  nop
0x18001c93e  mov     rbx, [rsp+48h+arg_8]
0x18001c943  mov     rbp, [rsp+48h+arg_10]
0x18001c948  add     rsp, 30h
0x18001c94c  pop     r14
0x18001c94e  pop     rdi
0x18001c94f  pop     rsi
0x18001c950  retn
```
