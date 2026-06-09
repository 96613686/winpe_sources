# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800197cc`
- end: `0x180019928`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `348`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180020590`

## callees

- `0x180009b20`
- `0x1800197cc`
- `0x180021904`
- `0x180021b48`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019907`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019907`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019821`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019890`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198c4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800198ab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800198ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800198ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800198ef`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // rsi
  DWORD LastError; // ebx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  int Source; // [rsp+20h] [rbp-28h] BYREF
  __int16 v13; // [rsp+24h] [rbp-24h]
  __int16 v14; // [rsp+26h] [rbp-22h]
  int v15; // [rsp+28h] [rbp-20h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v14 = 0;
    Source = a2;
    v13 = a3;
    v15 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s(
        pv[30].Ptr,
        ((char *)pv[31].Ptr - (char *)pv[30].Ptr) & -(__int64)(pv[30].Ptr < pv[31].Ptr),
        &Source,
        0xCu);
      pv[30].Ptr = (char *)pv[30].Ptr + 12;
    }
    if ( !LOBYTE(pv[8].Ptr) )
    {
      v8 = (struct _TP_TIMER **)&pv[7];
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          &pv[7],
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
0x1800197cc  mov     [rsp+arg_8], rbx
0x1800197d1  mov     [rsp+arg_10], rbp
0x1800197d6  push    rsi
0x1800197d7  push    rdi
0x1800197d8  push    r14
0x1800197da  sub     rsp, 30h
0x1800197de  mov     ebx, r9d
0x1800197e1  movzx   esi, r8w
0x1800197e5  mov     r14d, edx
0x1800197e8  mov     rdi, rcx
0x1800197eb  cmp     byte ptr [rcx], 0
0x1800197ee  jz      loc_180019914
0x1800197f4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800197fb  jnz     loc_180019914
0x180019801  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180019808  test    rax, rax
0x18001980b  jz      short loc_18001981A
0x18001980d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019812  test    al, al
0x180019814  jnz     loc_180019914
0x18001981a  lea     rbp, [rdi+28h]
0x18001981e  mov     rcx, rbp; SRWLock
0x180019821  call    cs:__imp_AcquireSRWLockExclusive
0x180019828  nop     dword ptr [rax+rax+00h]
0x18001982d  xor     eax, eax
0x18001982f  mov     [rsp+48h+var_22], ax
0x180019834  mov     [rsp+48h+Source], r14d
0x180019839  mov     [rsp+48h+var_24], si
0x18001983e  mov     [rsp+48h+var_20], ebx
0x180019842  lea     rbx, [rdi+0E8h]
0x180019849  lea     esi, [rax+0Ch]
0x18001984c  mov     edx, esi; unsigned __int64
0x18001984e  mov     rcx, rbx; this
0x180019851  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180019856  test    al, al
0x180019858  jz      short loc_180019880
0x18001985a  mov     rcx, [rbx+8]; Destination
0x18001985e  mov     rax, [rbx+10h]
0x180019862  sub     rax, rcx
0x180019865  cmp     rcx, [rbx+10h]
0x180019869  sbb     rdx, rdx
0x18001986c  and     rdx, rax; DestinationSize
0x18001986f  mov     r9d, esi; SourceSize
0x180019872  lea     r8, [rsp+48h+Source]; Source
0x180019877  call    memcpy_s
0x18001987c  add     [rbx+8], rsi
0x180019880  cmp     byte ptr [rdi+40h], 0
0x180019884  jnz     short loc_1800198FF
0x180019886  lea     rsi, [rdi+38h]
0x18001988a  cmp     qword ptr [rsi], 0
0x18001988e  jnz     short loc_1800198D0
0x180019890  call    cs:__imp_GetLastError
0x180019897  nop     dword ptr [rax+rax+00h]
0x18001989c  mov     ebx, eax
0x18001989e  xor     r8d, r8d; pcbe
0x1800198a1  mov     rdx, rdi; pv
0x1800198a4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800198ab  call    cs:__imp_CreateThreadpoolTimer
0x1800198b2  nop     dword ptr [rax+rax+00h]
0x1800198b7  mov     rdx, rax
0x1800198ba  mov     rcx, rsi
0x1800198bd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800198c2  mov     ecx, ebx; dwErrCode
0x1800198c4  call    cs:__imp_SetLastError
0x1800198cb  nop     dword ptr [rax+rax+00h]
0x1800198d0  mov     rcx, [rsi]; pti
0x1800198d3  test    rcx, rcx
0x1800198d6  jz      short loc_1800198FF
0x1800198d8  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800198e1  mov     r9d, 4E2h; msWindowLength
0x1800198e7  xor     r8d, r8d; msPeriod
0x1800198ea  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800198ef  call    cs:__imp_SetThreadpoolTimer
0x1800198f6  nop     dword ptr [rax+rax+00h]
0x1800198fb  mov     byte ptr [rdi+40h], 1
0x1800198ff  test    rbp, rbp
0x180019902  jz      short loc_180019914
0x180019904  mov     rcx, rbp; SRWLock
0x180019907  call    cs:__imp_ReleaseSRWLockExclusive
0x18001990e  nop     dword ptr [rax+rax+00h]
0x180019913  nop
0x180019914  mov     rbx, [rsp+48h+arg_8]
0x180019919  mov     rbp, [rsp+48h+arg_10]
0x18001991e  add     rsp, 30h
0x180019922  pop     r14
0x180019924  pop     rdi
0x180019925  pop     rsi
0x180019926  retn
```
