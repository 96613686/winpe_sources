# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800e91f0`
- end: `0x1800e938b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800ec020`

## callees

- `0x1800039c6`
- `0x180003a40`
- `0x1800e91f0`
- `0x1800ec730`
- `0x18010d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e9287`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e92b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e9287`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e92b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e9240`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e9240`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e9377`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e9377`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e9332`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e933f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e9332`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800e933f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e92d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e92d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9300`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e92ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800e92ee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e9321`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800e9321`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e932a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800e932a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e9313`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e9365`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e9313`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800e9365`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  __int64 v8; // rdx
  _DWORD *Ptr; // rcx
  size_t v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v16; // rbp
  DWORD v17; // ebx
  struct _TP_TIMER *v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v19) = a2;
  HIDWORD(v19) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v19;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)_o__errno(v12, v11, v13) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v8, v10) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
LABEL_13:
  if ( !LOBYTE(pv[8].Ptr) )
  {
    if ( !pv[7].Ptr )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_, pv, 0);
      v16 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v16 )
      {
        v17 = GetLastError();
        SetThreadpoolTimer(v16, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v16, 1);
        CloseThreadpoolTimer(v16);
        SetLastError(v17);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v18 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v18 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v18, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x1800e91f0  push    rbx
0x1800e91f2  push    rbp
0x1800e91f3  push    rsi
0x1800e91f4  push    rdi
0x1800e91f5  push    r14
0x1800e91f7  push    r15
0x1800e91f9  sub     rsp, 38h
0x1800e91fd  mov     ebp, r9d
0x1800e9200  movzx   ebx, r8w
0x1800e9204  mov     r14d, edx
0x1800e9207  mov     rdi, rcx
0x1800e920a  cmp     byte ptr [rcx], 0
0x1800e920d  jz      loc_1800E937E
0x1800e9213  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800e921a  jnz     loc_1800E937E
0x1800e9220  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800e9227  test    rax, rax
0x1800e922a  jz      short loc_1800E9239
0x1800e922c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9231  test    al, al
0x1800e9233  jnz     loc_1800E937E
0x1800e9239  lea     rsi, [rdi+28h]
0x1800e923d  mov     rcx, rsi; SRWLock
0x1800e9240  call    cs:__imp_AcquireSRWLockExclusive
0x1800e9246  xor     eax, eax
0x1800e9248  mov     word ptr [rsp+68h+var_48+6], ax
0x1800e924d  mov     dword ptr [rsp+68h+var_48], r14d
0x1800e9252  mov     word ptr [rsp+68h+var_48+4], bx
0x1800e9257  lea     rbx, [rdi+0E8h]
0x1800e925e  lea     edx, [rax+0Ch]; unsigned __int64
0x1800e9261  mov     rcx, rbx; this
0x1800e9264  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800e9269  test    al, al
0x1800e926b  jz      short loc_1800E92C7
0x1800e926d  mov     rcx, [rbx+8]; void *
0x1800e9271  mov     rax, [rbx+10h]
0x1800e9275  sub     rax, rcx
0x1800e9278  cmp     rcx, [rbx+10h]
0x1800e927c  sbb     r8, r8
0x1800e927f  and     r8, rax; Size
0x1800e9282  test    rcx, rcx
0x1800e9285  jnz     short loc_1800E9295
0x1800e9287  call    cs:__imp__o__errno
0x1800e928d  mov     dword ptr [rax], 16h
0x1800e9293  jmp     short loc_1800E92BD
0x1800e9295  cmp     r8, 0Ch
0x1800e9299  jb      short loc_1800E92AA
0x1800e929b  movsd   xmm0, [rsp+68h+var_48]
0x1800e92a1  movsd   qword ptr [rcx], xmm0
0x1800e92a5  mov     [rcx+8], ebp
0x1800e92a8  jmp     short loc_1800E92C2
0x1800e92aa  xor     edx, edx; Val
0x1800e92ac  call    memset_0
0x1800e92b1  call    cs:__imp__o__errno
0x1800e92b7  mov     dword ptr [rax], 22h ; '"'
0x1800e92bd  call    _invalid_parameter_noinfo
0x1800e92c2  add     qword ptr [rbx+8], 0Ch
0x1800e92c7  cmp     byte ptr [rdi+40h], 0
0x1800e92cb  jnz     loc_1800E936F
0x1800e92d1  cmp     qword ptr [rdi+38h], 0
0x1800e92d6  jnz     short loc_1800E9345
0x1800e92d8  call    cs:__imp_GetLastError
0x1800e92de  mov     r14d, eax
0x1800e92e1  xor     r8d, r8d; pcbe
0x1800e92e4  mov     rdx, rdi; pv
0x1800e92e7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800e92ee  call    cs:__imp_CreateThreadpoolTimer
0x1800e92f4  mov     r15, rax
0x1800e92f7  mov     rbp, [rdi+38h]
0x1800e92fb  test    rbp, rbp
0x1800e92fe  jz      short loc_1800E9338
0x1800e9300  call    cs:__imp_GetLastError
0x1800e9306  mov     ebx, eax
0x1800e9308  xor     r9d, r9d; msWindowLength
0x1800e930b  xor     r8d, r8d; msPeriod
0x1800e930e  xor     edx, edx; pftDueTime
0x1800e9310  mov     rcx, rbp; pti
0x1800e9313  call    cs:__imp_SetThreadpoolTimer
0x1800e9319  mov     edx, 1; fCancelPendingCallbacks
0x1800e931e  mov     rcx, rbp; pti
0x1800e9321  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800e9327  mov     rcx, rbp; pti
0x1800e932a  call    cs:__imp_CloseThreadpoolTimer
0x1800e9330  mov     ecx, ebx; dwErrCode
0x1800e9332  call    cs:__imp_SetLastError
0x1800e9338  mov     [rdi+38h], r15
0x1800e933c  mov     ecx, r14d; dwErrCode
0x1800e933f  call    cs:__imp_SetLastError
0x1800e9345  mov     rcx, [rdi+38h]; pti
0x1800e9349  test    rcx, rcx
0x1800e934c  jz      short loc_1800E936F
0x1800e934e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800e9357  mov     r9d, 4E2h; msWindowLength
0x1800e935d  xor     r8d, r8d; msPeriod
0x1800e9360  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800e9365  call    cs:__imp_SetThreadpoolTimer
0x1800e936b  mov     byte ptr [rdi+40h], 1
0x1800e936f  test    rsi, rsi
0x1800e9372  jz      short loc_1800E937E
0x1800e9374  mov     rcx, rsi; SRWLock
0x1800e9377  call    cs:__imp_ReleaseSRWLockExclusive
0x1800e937d  nop
0x1800e937e  add     rsp, 38h
0x1800e9382  pop     r15
0x1800e9384  pop     r14
0x1800e9386  pop     rdi
0x1800e9387  pop     rsi
0x1800e9388  pop     rbp
0x1800e9389  pop     rbx
0x1800e938a  retn
```
