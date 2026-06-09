# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140009fd8`
- end: `0x14000a11c`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `324`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000c220`

## callees

- `0x140006e4c`
- `0x140009fd8`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000a069`
- `KERNEL32!GetLastError` at `0x14000a091`
- `KERNEL32!GetLastError` at `0x14000a069`
- `KERNEL32!GetLastError` at `0x14000a091`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a028`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a028`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a108`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a108`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a0c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a0d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a0c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a0d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000a07f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000a07f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000a0b2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000a0b2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000a0a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000a0f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000a0a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000a0f6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000a0bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000a0bb`

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
  int Src; // [rsp+20h] [rbp-48h] BYREF
  __int16 v14; // [rsp+24h] [rbp-44h]
  __int16 v15; // [rsp+26h] [rbp-42h]
  int v16; // [rsp+28h] [rbp-40h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    v15 = 0;
    Src = a2;
    v14 = a3;
    v16 = a4;
    wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&pv[29], &Src, 0xCu);
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
0x140009fd8  push    rbx
0x140009fda  push    rbp
0x140009fdb  push    rsi
0x140009fdc  push    rdi
0x140009fdd  push    r14
0x140009fdf  push    r15
0x140009fe1  sub     rsp, 38h
0x140009fe5  mov     ebx, r9d
0x140009fe8  movzx   ebp, r8w
0x140009fec  mov     r14d, edx
0x140009fef  mov     rdi, rcx
0x140009ff2  cmp     byte ptr [rcx], 0
0x140009ff5  jz      loc_14000A10F
0x140009ffb  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000a002  jnz     loc_14000A10F
0x14000a008  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000a00f  test    rax, rax
0x14000a012  jz      short loc_14000A021
0x14000a014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a019  test    al, al
0x14000a01b  jnz     loc_14000A10F
0x14000a021  lea     rsi, [rdi+28h]
0x14000a025  mov     rcx, rsi; SRWLock
0x14000a028  call    cs:__imp_AcquireSRWLockExclusive
0x14000a02e  xor     eax, eax
0x14000a030  mov     [rsp+68h+var_42], ax
0x14000a035  mov     [rsp+68h+Src], r14d
0x14000a03a  mov     [rsp+68h+var_44], bp
0x14000a03f  mov     [rsp+68h+var_40], ebx
0x14000a043  lea     rcx, [rdi+0E8h]; this
0x14000a04a  lea     r8d, [rax+0Ch]; Size
0x14000a04e  lea     rdx, [rsp+68h+Src]; Src
0x14000a053  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000a058  cmp     byte ptr [rdi+40h], 0
0x14000a05c  jnz     loc_14000A100
0x14000a062  cmp     qword ptr [rdi+38h], 0
0x14000a067  jnz     short loc_14000A0D6
0x14000a069  call    cs:__imp_GetLastError
0x14000a06f  mov     r14d, eax
0x14000a072  xor     r8d, r8d; pcbe
0x14000a075  mov     rdx, rdi; pv
0x14000a078  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000a07f  call    cs:__imp_CreateThreadpoolTimer
0x14000a085  mov     r15, rax
0x14000a088  mov     rbp, [rdi+38h]
0x14000a08c  test    rbp, rbp
0x14000a08f  jz      short loc_14000A0C9
0x14000a091  call    cs:__imp_GetLastError
0x14000a097  mov     ebx, eax
0x14000a099  xor     r9d, r9d; msWindowLength
0x14000a09c  xor     r8d, r8d; msPeriod
0x14000a09f  xor     edx, edx; pftDueTime
0x14000a0a1  mov     rcx, rbp; pti
0x14000a0a4  call    cs:__imp_SetThreadpoolTimer
0x14000a0aa  mov     edx, 1; fCancelPendingCallbacks
0x14000a0af  mov     rcx, rbp; pti
0x14000a0b2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000a0b8  mov     rcx, rbp; pti
0x14000a0bb  call    cs:__imp_CloseThreadpoolTimer
0x14000a0c1  mov     ecx, ebx; dwErrCode
0x14000a0c3  call    cs:__imp_SetLastError
0x14000a0c9  mov     [rdi+38h], r15
0x14000a0cd  mov     ecx, r14d; dwErrCode
0x14000a0d0  call    cs:__imp_SetLastError
0x14000a0d6  mov     rcx, [rdi+38h]; pti
0x14000a0da  test    rcx, rcx
0x14000a0dd  jz      short loc_14000A100
0x14000a0df  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14000a0e8  mov     r9d, 4E2h; msWindowLength
0x14000a0ee  xor     r8d, r8d; msPeriod
0x14000a0f1  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x14000a0f6  call    cs:__imp_SetThreadpoolTimer
0x14000a0fc  mov     byte ptr [rdi+40h], 1
0x14000a100  test    rsi, rsi
0x14000a103  jz      short loc_14000A10F
0x14000a105  mov     rcx, rsi; SRWLock
0x14000a108  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a10e  nop
0x14000a10f  add     rsp, 38h
0x14000a113  pop     r15
0x14000a115  pop     r14
0x14000a117  pop     rdi
0x14000a118  pop     rsi
0x14000a119  pop     rbp
0x14000a11a  pop     rbx
0x14000a11b  retn
```
