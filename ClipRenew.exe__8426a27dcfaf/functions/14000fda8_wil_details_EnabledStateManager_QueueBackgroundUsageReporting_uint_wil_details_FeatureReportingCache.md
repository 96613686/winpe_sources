# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14000fda8`
- end: `0x14000ff3b`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `403`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400110ac`

## callees

- `0x14000fda8`
- `0x140011fcc`
- `0x140014010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000fe68`
- `msvcrt!memcpy_s` at `0x14000fe68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ff28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ff28`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000fdf4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000fdf4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fedd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000feea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000fedd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000feea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fe83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000feab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fe83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000feab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000fecc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000fecc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fed5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000fed5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000febe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ff16`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000febe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ff16`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000fe99`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000fe99`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v9; // r15
  DWORD v10; // ebx
  struct _TP_TIMER *v11; // rcx
  _DWORD Source[2]; // [rsp+20h] [rbp-48h] BYREF
  struct wil_details_FeatureReportingCache *v13; // [rsp+28h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

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
      v13 = a3;
      if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
      {
        memcpy_s(pv[5].Ptr, ((char *)pv[6].Ptr - (char *)pv[5].Ptr) & -(__int64)(pv[5].Ptr < pv[6].Ptr), Source, 0x10u);
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
      }
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          v9 = ThreadpoolTimer;
          if ( Ptr )
          {
            v10 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v10);
          }
          pv[2].Ptr = v9;
          SetLastError(LastError);
        }
        v11 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v11 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v11, &pftDueTime, 0, 0x124F8u);
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
0x14000fda8  push    rbx
0x14000fdaa  push    rbp
0x14000fdab  push    rsi
0x14000fdac  push    rdi
0x14000fdad  push    r14
0x14000fdaf  push    r15
0x14000fdb1  sub     rsp, 38h
0x14000fdb5  mov     eax, [rcx]
0x14000fdb7  mov     rbx, r8
0x14000fdba  mov     ebp, edx
0x14000fdbc  mov     rdi, rcx
0x14000fdbf  test    eax, eax
0x14000fdc1  jz      loc_14000FF2E
0x14000fdc7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000fdce  jnz     loc_14000FF2E
0x14000fdd4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000fddb  test    rax, rax
0x14000fdde  jz      short loc_14000FDED
0x14000fde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fde5  test    al, al
0x14000fde7  jnz     loc_14000FF2E
0x14000fded  lea     rsi, [rdi+8]
0x14000fdf1  mov     rcx, rsi; SRWLock
0x14000fdf4  call    cs:__imp_AcquireSRWLockExclusive
0x14000fdfa  mov     eax, [rdi]
0x14000fdfc  test    eax, eax
0x14000fdfe  jz      loc_14000FF20
0x14000fe04  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000fe0b  jnz     loc_14000FF20
0x14000fe11  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000fe18  test    rax, rax
0x14000fe1b  jz      short loc_14000FE2A
0x14000fe1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe22  test    al, al
0x14000fe24  jnz     loc_14000FF20
0x14000fe2a  xor     eax, eax
0x14000fe2c  mov     [rsp+68h+Source], ebp
0x14000fe30  lea     rcx, [rdi+20h]; this
0x14000fe34  mov     [rsp+68h+var_44], eax
0x14000fe38  mov     [rsp+68h+var_40], rbx
0x14000fe3d  lea     ebp, [rax+10h]
0x14000fe40  mov     edx, ebp; unsigned __int64
0x14000fe42  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000fe47  test    al, al
0x14000fe49  jz      short loc_14000FE72
0x14000fe4b  mov     rcx, [rdi+28h]; Destination
0x14000fe4f  lea     r8, [rsp+68h+Source]; Source
0x14000fe54  mov     rax, [rdi+30h]
0x14000fe58  mov     r9d, ebp; SourceSize
0x14000fe5b  sub     rax, rcx
0x14000fe5e  cmp     rcx, [rdi+30h]
0x14000fe62  sbb     rdx, rdx
0x14000fe65  and     rdx, rax; DestinationSize
0x14000fe68  call    cs:__imp_memcpy_s
0x14000fe6e  add     [rdi+28h], rbp
0x14000fe72  cmp     byte ptr [rdi+18h], 0
0x14000fe76  jnz     loc_14000FF20
0x14000fe7c  cmp     qword ptr [rdi+10h], 0
0x14000fe81  jnz     short loc_14000FEF0
0x14000fe83  call    cs:__imp_GetLastError
0x14000fe89  xor     r8d, r8d; pcbe
0x14000fe8c  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000fe93  mov     rdx, rdi; pv
0x14000fe96  mov     r14d, eax
0x14000fe99  call    cs:__imp_CreateThreadpoolTimer
0x14000fe9f  mov     rbp, [rdi+10h]
0x14000fea3  mov     r15, rax
0x14000fea6  test    rbp, rbp
0x14000fea9  jz      short loc_14000FEE3
0x14000feab  call    cs:__imp_GetLastError
0x14000feb1  xor     r9d, r9d; msWindowLength
0x14000feb4  xor     r8d, r8d; msPeriod
0x14000feb7  xor     edx, edx; pftDueTime
0x14000feb9  mov     rcx, rbp; pti
0x14000febc  mov     ebx, eax
0x14000febe  call    cs:__imp_SetThreadpoolTimer
0x14000fec4  mov     edx, 1; fCancelPendingCallbacks
0x14000fec9  mov     rcx, rbp; pti
0x14000fecc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000fed2  mov     rcx, rbp; pti
0x14000fed5  call    cs:__imp_CloseThreadpoolTimer
0x14000fedb  mov     ecx, ebx; dwErrCode
0x14000fedd  call    cs:__imp_SetLastError
0x14000fee3  mov     ecx, r14d; dwErrCode
0x14000fee6  mov     [rdi+10h], r15
0x14000feea  call    cs:__imp_SetLastError
0x14000fef0  mov     rcx, [rdi+10h]; pti
0x14000fef4  test    rcx, rcx
0x14000fef7  jz      short loc_14000FF20
0x14000fef9  mov     rax, 0FFFFFFFF4D2FA200h
0x14000ff03  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x14000ff08  mov     r9d, 124F8h; msWindowLength
0x14000ff0e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x14000ff13  xor     r8d, r8d; msPeriod
0x14000ff16  call    cs:__imp_SetThreadpoolTimer
0x14000ff1c  mov     byte ptr [rdi+18h], 1
0x14000ff20  test    rsi, rsi
0x14000ff23  jz      short loc_14000FF2E
0x14000ff25  mov     rcx, rsi; SRWLock
0x14000ff28  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ff2e  add     rsp, 38h
0x14000ff32  pop     r15
0x14000ff34  pop     r14
0x14000ff36  pop     rdi
0x14000ff37  pop     rsi
0x14000ff38  pop     rbp
0x14000ff39  pop     rbx
0x14000ff3a  retn
```
