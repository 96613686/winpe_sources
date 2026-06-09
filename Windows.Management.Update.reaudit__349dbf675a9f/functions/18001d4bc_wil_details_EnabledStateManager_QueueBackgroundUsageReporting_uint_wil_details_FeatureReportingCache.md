# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001d4bc`
- end: `0x18001d618`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `348`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001d7cc`

## callees

- `0x1800105e0`
- `0x180010774`
- `0x18001d4bc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d5f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d5f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d50d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d50d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d57a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d57a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d5ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d5ae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d5df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d5df`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d595`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d595`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
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
      wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[4], Source, 0x10u);
      v6 = (struct _TP_TIMER **)&pv[2];
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !*v6 )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            (struct _TP_TIMER **)&pv[2],
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
0x18001d4bc  mov     [rsp+arg_8], rbx
0x18001d4c1  mov     [rsp+arg_10], rbp
0x18001d4c6  push    rsi
0x18001d4c7  push    rdi
0x18001d4c8  push    r14
0x18001d4ca  sub     rsp, 30h
0x18001d4ce  mov     rbx, r8
0x18001d4d1  mov     ebp, edx
0x18001d4d3  mov     rdi, rcx
0x18001d4d6  mov     eax, [rcx]
0x18001d4d8  test    eax, eax
0x18001d4da  jz      loc_18001D604
0x18001d4e0  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001d4e7  jnz     loc_18001D604
0x18001d4ed  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d4f4  test    rax, rax
0x18001d4f7  jz      short loc_18001D506
0x18001d4f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4fe  test    al, al
0x18001d500  jnz     loc_18001D604
0x18001d506  lea     rsi, [rdi+8]
0x18001d50a  mov     rcx, rsi; SRWLock
0x18001d50d  call    cs:__imp_AcquireSRWLockExclusive
0x18001d514  nop     dword ptr [rax+rax+00h]
0x18001d519  mov     eax, [rdi]
0x18001d51b  test    eax, eax
0x18001d51d  jz      loc_18001D5EF
0x18001d523  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001d52a  jnz     loc_18001D5EF
0x18001d530  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d537  test    rax, rax
0x18001d53a  jz      short loc_18001D549
0x18001d53c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d541  test    al, al
0x18001d543  jnz     loc_18001D5EF
0x18001d549  mov     [rsp+48h+Source], ebp
0x18001d54d  xor     eax, eax
0x18001d54f  mov     [rsp+48h+var_24], eax
0x18001d553  mov     [rsp+48h+var_20], rbx
0x18001d558  lea     rcx, [rdi+20h]; this
0x18001d55c  lea     r8d, [rax+10h]; SourceSize
0x18001d560  lea     rdx, [rsp+48h+Source]; Source
0x18001d565  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001d56a  lea     r14, [rdi+10h]
0x18001d56e  cmp     byte ptr [rdi+18h], 0
0x18001d572  jnz     short loc_18001D5EF
0x18001d574  cmp     qword ptr [r14], 0
0x18001d578  jnz     short loc_18001D5BA
0x18001d57a  call    cs:__imp_GetLastError
0x18001d581  nop     dword ptr [rax+rax+00h]
0x18001d586  mov     ebx, eax
0x18001d588  xor     r8d, r8d; pcbe
0x18001d58b  mov     rdx, rdi; pv
0x18001d58e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001d595  call    cs:__imp_CreateThreadpoolTimer
0x18001d59c  nop     dword ptr [rax+rax+00h]
0x18001d5a1  mov     rdx, rax
0x18001d5a4  mov     rcx, r14
0x18001d5a7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001d5ac  mov     ecx, ebx; dwErrCode
0x18001d5ae  call    cs:__imp_SetLastError
0x18001d5b5  nop     dword ptr [rax+rax+00h]
0x18001d5ba  mov     rcx, [r14]; pti
0x18001d5bd  test    rcx, rcx
0x18001d5c0  jz      short loc_18001D5EF
0x18001d5c2  mov     rax, 0FFFFFFFF4D2FA200h
0x18001d5cc  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18001d5d1  mov     r9d, 124F8h; msWindowLength
0x18001d5d7  xor     r8d, r8d; msPeriod
0x18001d5da  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18001d5df  call    cs:__imp_SetThreadpoolTimer
0x18001d5e6  nop     dword ptr [rax+rax+00h]
0x18001d5eb  mov     byte ptr [rdi+18h], 1
0x18001d5ef  test    rsi, rsi
0x18001d5f2  jz      short loc_18001D604
0x18001d5f4  mov     rcx, rsi; SRWLock
0x18001d5f7  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d5fe  nop     dword ptr [rax+rax+00h]
0x18001d603  nop
0x18001d604  mov     rbx, [rsp+48h+arg_8]
0x18001d609  mov     rbp, [rsp+48h+arg_10]
0x18001d60e  add     rsp, 30h
0x18001d612  pop     r14
0x18001d614  pop     rdi
0x18001d615  pop     rsi
0x18001d616  retn
```
