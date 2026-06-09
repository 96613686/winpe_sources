# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000a7f0`
- end: `0x18000a979`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `393`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000c080`

## callees

- `0x18000a7f0`
- `0x18000d014`
- `0x180021850`
- `0x180024010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a89e`
- `msvcrt!memcpy_s` at `0x18000a89e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a84e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a84e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a958`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a958`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a913`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a920`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a913`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a920`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a902`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a902`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a8cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a8cf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a8f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a946`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a8f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a946`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a90b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a90b`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v11; // ebx
  struct _TP_TIMER *v12; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v15; // [rsp+2Ch] [rbp-4Ch]
  __int16 v16; // [rsp+2Eh] [rbp-4Ah]
  int v17; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v16 = 0;
    Source = a2;
    v15 = a3;
    v17 = a4;
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
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        Ptr = (struct _TP_TIMER *)pv[7].Ptr;
        if ( Ptr )
        {
          v11 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v11);
        }
        pv[7].Ptr = ThreadpoolTimer;
        SetLastError(LastError);
      }
      v12 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v12 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v12, &pftDueTime, 0, 0x4E2u);
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
0x18000a7f0  push    rbx
0x18000a7f2  push    rbp
0x18000a7f3  push    rsi
0x18000a7f4  push    rdi
0x18000a7f5  push    r14
0x18000a7f7  push    r15
0x18000a7f9  sub     rsp, 48h
0x18000a7fd  mov     rax, cs:__security_cookie
0x18000a804  xor     rax, rsp
0x18000a807  mov     [rsp+78h+var_40], rax
0x18000a80c  mov     r14d, r9d
0x18000a80f  movzx   ebp, r8w
0x18000a813  mov     ebx, edx
0x18000a815  mov     rdi, rcx
0x18000a818  cmp     byte ptr [rcx], 0
0x18000a81b  jz      loc_18000A95F
0x18000a821  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a828  jnz     loc_18000A95F
0x18000a82e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a835  test    rax, rax
0x18000a838  jz      short loc_18000A847
0x18000a83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a83f  test    al, al
0x18000a841  jnz     loc_18000A95F
0x18000a847  lea     rsi, [rdi+28h]
0x18000a84b  mov     rcx, rsi; SRWLock
0x18000a84e  call    cs:__imp_AcquireSRWLockExclusive
0x18000a854  xor     eax, eax
0x18000a856  mov     [rsp+78h+var_4A], ax
0x18000a85b  mov     [rsp+78h+Source], ebx
0x18000a85f  mov     [rsp+78h+var_4C], bp
0x18000a864  mov     [rsp+78h+var_48], r14d
0x18000a869  lea     rbx, [rdi+0E8h]
0x18000a870  lea     ebp, [rax+0Ch]
0x18000a873  mov     edx, ebp; unsigned __int64
0x18000a875  mov     rcx, rbx; this
0x18000a878  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a87d  test    al, al
0x18000a87f  jz      short loc_18000A8A8
0x18000a881  mov     rcx, [rbx+8]; Destination
0x18000a885  mov     rax, [rbx+10h]
0x18000a889  sub     rax, rcx
0x18000a88c  cmp     rcx, [rbx+10h]
0x18000a890  sbb     rdx, rdx
0x18000a893  and     rdx, rax; DestinationSize
0x18000a896  mov     r9d, ebp; SourceSize
0x18000a899  lea     r8, [rsp+78h+Source]; Source
0x18000a89e  call    cs:__imp_memcpy_s
0x18000a8a4  add     [rbx+8], rbp
0x18000a8a8  cmp     byte ptr [rdi+40h], 0
0x18000a8ac  jnz     loc_18000A950
0x18000a8b2  cmp     qword ptr [rdi+38h], 0
0x18000a8b7  jnz     short loc_18000A926
0x18000a8b9  call    cs:__imp_GetLastError
0x18000a8bf  mov     r14d, eax
0x18000a8c2  xor     r8d, r8d; pcbe
0x18000a8c5  mov     rdx, rdi; pv
0x18000a8c8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a8cf  call    cs:__imp_CreateThreadpoolTimer
0x18000a8d5  mov     r15, rax
0x18000a8d8  mov     rbp, [rdi+38h]
0x18000a8dc  test    rbp, rbp
0x18000a8df  jz      short loc_18000A919
0x18000a8e1  call    cs:__imp_GetLastError
0x18000a8e7  mov     ebx, eax
0x18000a8e9  xor     r9d, r9d; msWindowLength
0x18000a8ec  xor     r8d, r8d; msPeriod
0x18000a8ef  xor     edx, edx; pftDueTime
0x18000a8f1  mov     rcx, rbp; pti
0x18000a8f4  call    cs:__imp_SetThreadpoolTimer
0x18000a8fa  mov     edx, 1; fCancelPendingCallbacks
0x18000a8ff  mov     rcx, rbp; pti
0x18000a902  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a908  mov     rcx, rbp; pti
0x18000a90b  call    cs:__imp_CloseThreadpoolTimer
0x18000a911  mov     ecx, ebx; dwErrCode
0x18000a913  call    cs:__imp_SetLastError
0x18000a919  mov     [rdi+38h], r15
0x18000a91d  mov     ecx, r14d; dwErrCode
0x18000a920  call    cs:__imp_SetLastError
0x18000a926  mov     rcx, [rdi+38h]; pti
0x18000a92a  test    rcx, rcx
0x18000a92d  jz      short loc_18000A950
0x18000a92f  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000a938  mov     r9d, 4E2h; msWindowLength
0x18000a93e  xor     r8d, r8d; msPeriod
0x18000a941  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x18000a946  call    cs:__imp_SetThreadpoolTimer
0x18000a94c  mov     byte ptr [rdi+40h], 1
0x18000a950  test    rsi, rsi
0x18000a953  jz      short loc_18000A95F
0x18000a955  mov     rcx, rsi; SRWLock
0x18000a958  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a95e  nop
0x18000a95f  mov     rcx, [rsp+78h+var_40]
0x18000a964  xor     rcx, rsp; StackCookie
0x18000a967  call    __security_check_cookie
0x18000a96c  add     rsp, 48h
0x18000a970  pop     r15
0x18000a972  pop     r14
0x18000a974  pop     rdi
0x18000a975  pop     rsi
0x18000a976  pop     rbp
0x18000a977  pop     rbx
0x18000a978  retn
```
