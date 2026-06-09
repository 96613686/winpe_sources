# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000ebe0`
- end: `0x18000ed3c`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `348`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180011c40`

## callees

- `0x18000ebe0`
- `0x1800124c0`
- `0x1800125b8`
- `0x180013758`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ed1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ed1b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ec35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ec35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eca4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eca4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ecd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ecd8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ecbf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ecbf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ed03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ed03`

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
0x18000ebe0  mov     [rsp+arg_8], rbx
0x18000ebe5  mov     [rsp+arg_10], rbp
0x18000ebea  push    rsi
0x18000ebeb  push    rdi
0x18000ebec  push    r14
0x18000ebee  sub     rsp, 30h
0x18000ebf2  mov     ebx, r9d
0x18000ebf5  movzx   esi, r8w
0x18000ebf9  mov     r14d, edx
0x18000ebfc  mov     rdi, rcx
0x18000ebff  cmp     byte ptr [rcx], 0
0x18000ec02  jz      loc_18000ED28
0x18000ec08  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ec0f  jnz     loc_18000ED28
0x18000ec15  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ec1c  test    rax, rax
0x18000ec1f  jz      short loc_18000EC2E
0x18000ec21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec26  test    al, al
0x18000ec28  jnz     loc_18000ED28
0x18000ec2e  lea     rbp, [rdi+28h]
0x18000ec32  mov     rcx, rbp; SRWLock
0x18000ec35  call    cs:__imp_AcquireSRWLockExclusive
0x18000ec3c  nop     dword ptr [rax+rax+00h]
0x18000ec41  xor     eax, eax
0x18000ec43  mov     [rsp+48h+var_22], ax
0x18000ec48  mov     [rsp+48h+Source], r14d
0x18000ec4d  mov     [rsp+48h+var_24], si
0x18000ec52  mov     [rsp+48h+var_20], ebx
0x18000ec56  lea     rbx, [rdi+0E8h]
0x18000ec5d  lea     esi, [rax+0Ch]
0x18000ec60  mov     edx, esi; unsigned __int64
0x18000ec62  mov     rcx, rbx; this
0x18000ec65  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ec6a  test    al, al
0x18000ec6c  jz      short loc_18000EC94
0x18000ec6e  mov     rcx, [rbx+8]; Destination
0x18000ec72  mov     rax, [rbx+10h]
0x18000ec76  sub     rax, rcx
0x18000ec79  cmp     rcx, [rbx+10h]
0x18000ec7d  sbb     rdx, rdx
0x18000ec80  and     rdx, rax; DestinationSize
0x18000ec83  mov     r9d, esi; SourceSize
0x18000ec86  lea     r8, [rsp+48h+Source]; Source
0x18000ec8b  call    memcpy_s
0x18000ec90  add     [rbx+8], rsi
0x18000ec94  cmp     byte ptr [rdi+40h], 0
0x18000ec98  jnz     short loc_18000ED13
0x18000ec9a  lea     rsi, [rdi+38h]
0x18000ec9e  cmp     qword ptr [rsi], 0
0x18000eca2  jnz     short loc_18000ECE4
0x18000eca4  call    cs:__imp_GetLastError
0x18000ecab  nop     dword ptr [rax+rax+00h]
0x18000ecb0  mov     ebx, eax
0x18000ecb2  xor     r8d, r8d; pcbe
0x18000ecb5  mov     rdx, rdi; pv
0x18000ecb8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ecbf  call    cs:__imp_CreateThreadpoolTimer
0x18000ecc6  nop     dword ptr [rax+rax+00h]
0x18000eccb  mov     rdx, rax
0x18000ecce  mov     rcx, rsi
0x18000ecd1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000ecd6  mov     ecx, ebx; dwErrCode
0x18000ecd8  call    cs:__imp_SetLastError
0x18000ecdf  nop     dword ptr [rax+rax+00h]
0x18000ece4  mov     rcx, [rsi]; pti
0x18000ece7  test    rcx, rcx
0x18000ecea  jz      short loc_18000ED13
0x18000ecec  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000ecf5  mov     r9d, 4E2h; msWindowLength
0x18000ecfb  xor     r8d, r8d; msPeriod
0x18000ecfe  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000ed03  call    cs:__imp_SetThreadpoolTimer
0x18000ed0a  nop     dword ptr [rax+rax+00h]
0x18000ed0f  mov     byte ptr [rdi+40h], 1
0x18000ed13  test    rbp, rbp
0x18000ed16  jz      short loc_18000ED28
0x18000ed18  mov     rcx, rbp; SRWLock
0x18000ed1b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ed22  nop     dword ptr [rax+rax+00h]
0x18000ed27  nop
0x18000ed28  mov     rbx, [rsp+48h+arg_8]
0x18000ed2d  mov     rbp, [rsp+48h+arg_10]
0x18000ed32  add     rsp, 30h
0x18000ed36  pop     r14
0x18000ed38  pop     rdi
0x18000ed39  pop     rsi
0x18000ed3a  retn
```
