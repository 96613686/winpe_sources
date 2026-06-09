# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x140008fc4`
- end: `0x140009146`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `386`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14000a618`

## callees

- `0x140008fc4`
- `0x14000cc9c`
- `0x14000cec8`
- `0x14000d6b8`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009015`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009015`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009125`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400090a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400090a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400090dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400090dc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400090c3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400090c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000910d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000910d`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  struct _TP_TIMER **v6; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v9; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  struct wil_details_FeatureReportingCache *v11; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    if ( *(_DWORD *)pv
      && !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      Source[0] = a2;
      Source[1] = 0;
      v11 = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 48), 0x10u) )
      {
        memcpy_s(
          *((void *const *)pv + 7),
          (*((_QWORD *)pv + 8) - *((_QWORD *)pv + 7)) & -(__int64)(*((_QWORD *)pv + 7) < *((_QWORD *)pv + 8)),
          Source,
          0x10u);
        *((_QWORD *)pv + 7) += 16LL;
      }
      if ( !pv[24] )
      {
        v6 = (struct _TP_TIMER **)(pv + 16);
        if ( !*((_QWORD *)pv + 2) )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            (struct _TP_TIMER **)pv + 2,
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        v9 = *v6;
        if ( *v6 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v9, &pftDueTime, 0, 0x124F8u);
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
0x140008fc4  mov     [rsp+arg_8], rbx
0x140008fc9  mov     [rsp+arg_10], rbp
0x140008fce  push    rsi
0x140008fcf  push    rdi
0x140008fd0  push    r14
0x140008fd2  sub     rsp, 30h
0x140008fd6  mov     rbx, r8
0x140008fd9  mov     ebp, edx
0x140008fdb  mov     rdi, rcx
0x140008fde  mov     eax, [rcx]
0x140008fe0  test    eax, eax
0x140008fe2  jz      loc_140009132
0x140008fe8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140008fef  jnz     loc_140009132
0x140008ff5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140008ffc  test    rax, rax
0x140008fff  jz      short loc_14000900E
0x140009001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009006  test    al, al
0x140009008  jnz     loc_140009132
0x14000900e  lea     rsi, [rdi+8]
0x140009012  mov     rcx, rsi; SRWLock
0x140009015  call    cs:__imp_AcquireSRWLockExclusive
0x14000901c  nop     dword ptr [rax+rax+00h]
0x140009021  mov     eax, [rdi]
0x140009023  test    eax, eax
0x140009025  jz      loc_14000911D
0x14000902b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140009032  jnz     loc_14000911D
0x140009038  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000903f  test    rax, rax
0x140009042  jz      short loc_140009051
0x140009044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009049  test    al, al
0x14000904b  jnz     loc_14000911D
0x140009051  mov     [rsp+48h+Source], ebp
0x140009055  xor     eax, eax
0x140009057  mov     [rsp+48h+var_24], eax
0x14000905b  mov     [rsp+48h+var_20], rbx
0x140009060  lea     ebp, [rax+10h]
0x140009063  mov     edx, ebp; unsigned __int64
0x140009065  lea     rcx, [rdi+30h]; this
0x140009069  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000906e  test    al, al
0x140009070  jz      short loc_140009098
0x140009072  mov     rcx, [rdi+38h]; Destination
0x140009076  mov     rax, [rdi+40h]
0x14000907a  sub     rax, rcx
0x14000907d  cmp     rcx, [rdi+40h]
0x140009081  sbb     rdx, rdx
0x140009084  and     rdx, rax; DestinationSize
0x140009087  mov     r9d, ebp; SourceSize
0x14000908a  lea     r8, [rsp+48h+Source]; Source
0x14000908f  call    memcpy_s
0x140009094  add     [rdi+38h], rbp
0x140009098  cmp     byte ptr [rdi+18h], 0
0x14000909c  jnz     short loc_14000911D
0x14000909e  lea     r14, [rdi+10h]
0x1400090a2  cmp     qword ptr [r14], 0
0x1400090a6  jnz     short loc_1400090E8
0x1400090a8  call    cs:__imp_GetLastError
0x1400090af  nop     dword ptr [rax+rax+00h]
0x1400090b4  mov     ebx, eax
0x1400090b6  xor     r8d, r8d; pcbe
0x1400090b9  mov     rdx, rdi; pv
0x1400090bc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400090c3  call    cs:__imp_CreateThreadpoolTimer
0x1400090ca  nop     dword ptr [rax+rax+00h]
0x1400090cf  mov     rdx, rax
0x1400090d2  mov     rcx, r14
0x1400090d5  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1400090da  mov     ecx, ebx; dwErrCode
0x1400090dc  call    cs:__imp_SetLastError
0x1400090e3  nop     dword ptr [rax+rax+00h]
0x1400090e8  mov     rcx, [r14]; pti
0x1400090eb  test    rcx, rcx
0x1400090ee  jz      short loc_14000911D
0x1400090f0  mov     rax, 0FFFFFFFF4D2FA200h
0x1400090fa  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1400090ff  mov     r9d, 124F8h; msWindowLength
0x140009105  xor     r8d, r8d; msPeriod
0x140009108  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x14000910d  call    cs:__imp_SetThreadpoolTimer
0x140009114  nop     dword ptr [rax+rax+00h]
0x140009119  mov     byte ptr [rdi+18h], 1
0x14000911d  test    rsi, rsi
0x140009120  jz      short loc_140009132
0x140009122  mov     rcx, rsi; SRWLock
0x140009125  call    cs:__imp_ReleaseSRWLockExclusive
0x14000912c  nop     dword ptr [rax+rax+00h]
0x140009131  nop
0x140009132  mov     rbx, [rsp+48h+arg_8]
0x140009137  mov     rbp, [rsp+48h+arg_10]
0x14000913c  add     rsp, 30h
0x140009140  pop     r14
0x140009142  pop     rdi
0x140009143  pop     rsi
0x140009144  retn
```
