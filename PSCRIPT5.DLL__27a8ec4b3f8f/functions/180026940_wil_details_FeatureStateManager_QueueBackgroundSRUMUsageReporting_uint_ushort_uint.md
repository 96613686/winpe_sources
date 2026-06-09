# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180026940`
- end: `0x180026a9b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `347`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800288c0`

## callees

- `0x180026940`
- `0x180028e2c`
- `0x180028f24`
- `0x1800297d0`
- `0x18005f010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x180026a1f`
- `KERNEL32!CreateThreadpoolTimer` at `0x180026a1f`
- `KERNEL32!SetThreadpoolTimer` at `0x180026a63`
- `KERNEL32!SetThreadpoolTimer` at `0x180026a63`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026995`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026995`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026a7b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026a7b`
- `KERNEL32!SetLastError` at `0x180026a38`
- `KERNEL32!SetLastError` at `0x180026a38`
- `KERNEL32!GetLastError` at `0x180026a04`
- `KERNEL32!GetLastError` at `0x180026a04`

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
  struct _TP_TIMER *ThreadpoolTimer; // rax
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
    v13 = a3;
    v15 = a4;
    v14 = 0;
    Source = a2;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s_0(
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
                            (PTP_TIMER_CALLBACK)_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
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
0x180026940  mov     [rsp+arg_8], rbx
0x180026945  mov     [rsp+arg_10], rbp
0x18002694a  push    rsi
0x18002694b  push    rdi
0x18002694c  push    r14
0x18002694e  sub     rsp, 30h
0x180026952  cmp     byte ptr [rcx], 0
0x180026955  mov     ebx, r9d
0x180026958  movzx   esi, r8w
0x18002695c  mov     r14d, edx
0x18002695f  mov     rdi, rcx
0x180026962  jz      loc_180026A87
0x180026968  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18002696f  jnz     loc_180026A87
0x180026975  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18002697c  test    rax, rax
0x18002697f  jz      short loc_18002698E
0x180026981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026986  test    al, al
0x180026988  jnz     loc_180026A87
0x18002698e  lea     rbp, [rdi+28h]
0x180026992  mov     rcx, rbp; SRWLock
0x180026995  call    cs:__imp_AcquireSRWLockExclusive
0x18002699c  nop     dword ptr [rax+rax+00h]
0x1800269a1  xor     eax, eax
0x1800269a3  mov     [rsp+48h+var_24], si
0x1800269a8  mov     [rsp+48h+var_20], ebx
0x1800269ac  lea     rbx, [rdi+0E8h]
0x1800269b3  mov     rcx, rbx; this
0x1800269b6  mov     [rsp+48h+var_22], ax
0x1800269bb  mov     [rsp+48h+Source], r14d
0x1800269c0  lea     esi, [rax+0Ch]
0x1800269c3  mov     edx, esi; unsigned __int64
0x1800269c5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800269ca  test    al, al
0x1800269cc  jz      short loc_1800269F4
0x1800269ce  mov     rcx, [rbx+8]; Destination
0x1800269d2  lea     r8, [rsp+48h+Source]; Source
0x1800269d7  mov     rax, [rbx+10h]
0x1800269db  mov     r9d, esi; SourceSize
0x1800269de  sub     rax, rcx
0x1800269e1  cmp     rcx, [rbx+10h]
0x1800269e5  sbb     rdx, rdx
0x1800269e8  and     rdx, rax; DestinationSize
0x1800269eb  call    memcpy_s_0
0x1800269f0  add     [rbx+8], rsi
0x1800269f4  cmp     byte ptr [rdi+40h], 0
0x1800269f8  jnz     short loc_180026A73
0x1800269fa  lea     rsi, [rdi+38h]
0x1800269fe  cmp     qword ptr [rsi], 0
0x180026a02  jnz     short loc_180026A44
0x180026a04  call    cs:__imp_GetLastError
0x180026a0b  nop     dword ptr [rax+rax+00h]
0x180026a10  xor     r8d, r8d; pcbe
0x180026a13  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180026a1a  mov     rdx, rdi; pv
0x180026a1d  mov     ebx, eax
0x180026a1f  call    cs:__imp_CreateThreadpoolTimer
0x180026a26  nop     dword ptr [rax+rax+00h]
0x180026a2b  mov     rdx, rax
0x180026a2e  mov     rcx, rsi
0x180026a31  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180026a36  mov     ecx, ebx; dwErrCode
0x180026a38  call    cs:__imp_SetLastError
0x180026a3f  nop     dword ptr [rax+rax+00h]
0x180026a44  mov     rcx, [rsi]; pti
0x180026a47  test    rcx, rcx
0x180026a4a  jz      short loc_180026A73
0x180026a4c  mov     r9d, 4E2h; msWindowLength
0x180026a52  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180026a5b  xor     r8d, r8d; msPeriod
0x180026a5e  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180026a63  call    cs:__imp_SetThreadpoolTimer
0x180026a6a  nop     dword ptr [rax+rax+00h]
0x180026a6f  mov     byte ptr [rdi+40h], 1
0x180026a73  test    rbp, rbp
0x180026a76  jz      short loc_180026A87
0x180026a78  mov     rcx, rbp; SRWLock
0x180026a7b  call    cs:__imp_ReleaseSRWLockExclusive
0x180026a82  nop     dword ptr [rax+rax+00h]
0x180026a87  mov     rbx, [rsp+48h+arg_8]
0x180026a8c  mov     rbp, [rsp+48h+arg_10]
0x180026a91  add     rsp, 30h
0x180026a95  pop     r14
0x180026a97  pop     rdi
0x180026a98  pop     rsi
0x180026a99  retn
```
