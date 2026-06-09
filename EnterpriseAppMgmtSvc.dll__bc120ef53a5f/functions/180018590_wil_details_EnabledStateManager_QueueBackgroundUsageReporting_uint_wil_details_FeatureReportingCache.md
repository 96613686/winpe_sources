# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180018590`
- end: `0x180018719`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `393`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180018db0`

## callees

- `0x18000e8ec`
- `0x18000e9ec`
- `0x180018590`
- `0x180070010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001865b`
- `msvcrt!memcpy_s` at `0x18001865b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001867b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001867b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800186af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800186af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800186f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800186f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800185e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800185e1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018696`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180018696`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800186e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800186e0`

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
0x180018590  mov     [rsp+arg_8], rbx
0x180018595  mov     [rsp+arg_10], rbp
0x18001859a  push    rsi
0x18001859b  push    rdi
0x18001859c  push    r14
0x18001859e  sub     rsp, 30h
0x1800185a2  mov     rbx, r8
0x1800185a5  mov     ebp, edx
0x1800185a7  mov     rdi, rcx
0x1800185aa  mov     eax, [rcx]
0x1800185ac  test    eax, eax
0x1800185ae  jz      loc_180018705
0x1800185b4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800185bb  jnz     loc_180018705
0x1800185c1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800185c8  test    rax, rax
0x1800185cb  jz      short loc_1800185DA
0x1800185cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185d2  test    al, al
0x1800185d4  jnz     loc_180018705
0x1800185da  lea     rsi, [rdi+8]
0x1800185de  mov     rcx, rsi; SRWLock
0x1800185e1  call    cs:__imp_AcquireSRWLockExclusive
0x1800185e8  nop     dword ptr [rax+rax+00h]
0x1800185ed  mov     eax, [rdi]
0x1800185ef  test    eax, eax
0x1800185f1  jz      loc_1800186F0
0x1800185f7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800185fe  jnz     loc_1800186F0
0x180018604  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001860b  test    rax, rax
0x18001860e  jz      short loc_18001861D
0x180018610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018615  test    al, al
0x180018617  jnz     loc_1800186F0
0x18001861d  mov     [rsp+48h+Source], ebp
0x180018621  xor     eax, eax
0x180018623  mov     [rsp+48h+var_24], eax
0x180018627  mov     [rsp+48h+var_20], rbx
0x18001862c  lea     ebp, [rax+10h]
0x18001862f  mov     edx, ebp; unsigned __int64
0x180018631  lea     rcx, [rdi+30h]; this
0x180018635  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001863a  test    al, al
0x18001863c  jz      short loc_18001866B
0x18001863e  mov     rcx, [rdi+38h]; Destination
0x180018642  mov     rax, [rdi+40h]
0x180018646  sub     rax, rcx
0x180018649  cmp     rcx, [rdi+40h]
0x18001864d  sbb     rdx, rdx
0x180018650  and     rdx, rax; DestinationSize
0x180018653  mov     r9d, ebp; SourceSize
0x180018656  lea     r8, [rsp+48h+Source]; Source
0x18001865b  call    cs:__imp_memcpy_s
0x180018662  nop     dword ptr [rax+rax+00h]
0x180018667  add     [rdi+38h], rbp
0x18001866b  cmp     byte ptr [rdi+18h], 0
0x18001866f  jnz     short loc_1800186F0
0x180018671  lea     r14, [rdi+10h]
0x180018675  cmp     qword ptr [r14], 0
0x180018679  jnz     short loc_1800186BB
0x18001867b  call    cs:__imp_GetLastError
0x180018682  nop     dword ptr [rax+rax+00h]
0x180018687  mov     ebx, eax
0x180018689  xor     r8d, r8d; pcbe
0x18001868c  mov     rdx, rdi; pv
0x18001868f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180018696  call    cs:__imp_CreateThreadpoolTimer
0x18001869d  nop     dword ptr [rax+rax+00h]
0x1800186a2  mov     rdx, rax
0x1800186a5  mov     rcx, r14
0x1800186a8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800186ad  mov     ecx, ebx; dwErrCode
0x1800186af  call    cs:__imp_SetLastError
0x1800186b6  nop     dword ptr [rax+rax+00h]
0x1800186bb  mov     rcx, [r14]; pti
0x1800186be  test    rcx, rcx
0x1800186c1  jz      short loc_1800186F0
0x1800186c3  mov     rax, 0FFFFFFFF4D2FA200h
0x1800186cd  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800186d2  mov     r9d, 124F8h; msWindowLength
0x1800186d8  xor     r8d, r8d; msPeriod
0x1800186db  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800186e0  call    cs:__imp_SetThreadpoolTimer
0x1800186e7  nop     dword ptr [rax+rax+00h]
0x1800186ec  mov     byte ptr [rdi+18h], 1
0x1800186f0  test    rsi, rsi
0x1800186f3  jz      short loc_180018705
0x1800186f5  mov     rcx, rsi; SRWLock
0x1800186f8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800186ff  nop     dword ptr [rax+rax+00h]
0x180018704  nop
0x180018705  mov     rbx, [rsp+48h+arg_8]
0x18001870a  mov     rbp, [rsp+48h+arg_10]
0x18001870f  add     rsp, 30h
0x180018713  pop     r14
0x180018715  pop     rdi
0x180018716  pop     rsi
0x180018717  retn
```
