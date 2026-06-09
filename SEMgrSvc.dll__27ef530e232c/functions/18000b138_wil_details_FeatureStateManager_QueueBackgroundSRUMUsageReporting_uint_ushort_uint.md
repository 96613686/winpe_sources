# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000b138`
- end: `0x18000b2d3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ded0`

## callees

- `0x1800057c6`
- `0x180005858`
- `0x18000b138`
- `0x18000e60c`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b1cf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b1f9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b1cf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b1f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b188`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b188`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b2bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b2bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b248`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b248`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b27a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b287`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b27a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b287`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b269`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b269`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b236`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000b236`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b25b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b2ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b25b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b2ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b272`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b272`

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
      ThreadpoolTimer = CreateThreadpoolTimer(
                          `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
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
0x18000b138  push    rbx
0x18000b13a  push    rbp
0x18000b13b  push    rsi
0x18000b13c  push    rdi
0x18000b13d  push    r14
0x18000b13f  push    r15
0x18000b141  sub     rsp, 38h
0x18000b145  mov     ebp, r9d
0x18000b148  movzx   ebx, r8w
0x18000b14c  mov     r14d, edx
0x18000b14f  mov     rdi, rcx
0x18000b152  cmp     byte ptr [rcx], 0
0x18000b155  jz      loc_18000B2C6
0x18000b15b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b162  jnz     loc_18000B2C6
0x18000b168  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b16f  test    rax, rax
0x18000b172  jz      short loc_18000B181
0x18000b174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b179  test    al, al
0x18000b17b  jnz     loc_18000B2C6
0x18000b181  lea     rsi, [rdi+28h]
0x18000b185  mov     rcx, rsi; SRWLock
0x18000b188  call    cs:__imp_AcquireSRWLockExclusive
0x18000b18e  xor     eax, eax
0x18000b190  mov     word ptr [rsp+68h+var_48+6], ax
0x18000b195  mov     dword ptr [rsp+68h+var_48], r14d
0x18000b19a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000b19f  lea     rbx, [rdi+0E8h]
0x18000b1a6  lea     edx, [rax+0Ch]; unsigned __int64
0x18000b1a9  mov     rcx, rbx; this
0x18000b1ac  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000b1b1  test    al, al
0x18000b1b3  jz      short loc_18000B20F
0x18000b1b5  mov     rcx, [rbx+8]; void *
0x18000b1b9  mov     rax, [rbx+10h]
0x18000b1bd  sub     rax, rcx
0x18000b1c0  cmp     rcx, [rbx+10h]
0x18000b1c4  sbb     r8, r8
0x18000b1c7  and     r8, rax; Size
0x18000b1ca  test    rcx, rcx
0x18000b1cd  jnz     short loc_18000B1DD
0x18000b1cf  call    cs:__imp__o__errno
0x18000b1d5  mov     dword ptr [rax], 16h
0x18000b1db  jmp     short loc_18000B205
0x18000b1dd  cmp     r8, 0Ch
0x18000b1e1  jb      short loc_18000B1F2
0x18000b1e3  movsd   xmm0, [rsp+68h+var_48]
0x18000b1e9  movsd   qword ptr [rcx], xmm0
0x18000b1ed  mov     [rcx+8], ebp
0x18000b1f0  jmp     short loc_18000B20A
0x18000b1f2  xor     edx, edx; Val
0x18000b1f4  call    memset_0
0x18000b1f9  call    cs:__imp__o__errno
0x18000b1ff  mov     dword ptr [rax], 22h ; '"'
0x18000b205  call    _invalid_parameter_noinfo
0x18000b20a  add     qword ptr [rbx+8], 0Ch
0x18000b20f  cmp     byte ptr [rdi+40h], 0
0x18000b213  jnz     loc_18000B2B7
0x18000b219  cmp     qword ptr [rdi+38h], 0
0x18000b21e  jnz     short loc_18000B28D
0x18000b220  call    cs:__imp_GetLastError
0x18000b226  mov     r14d, eax
0x18000b229  xor     r8d, r8d; pcbe
0x18000b22c  mov     rdx, rdi; pv
0x18000b22f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000b236  call    cs:__imp_CreateThreadpoolTimer
0x18000b23c  mov     r15, rax
0x18000b23f  mov     rbp, [rdi+38h]
0x18000b243  test    rbp, rbp
0x18000b246  jz      short loc_18000B280
0x18000b248  call    cs:__imp_GetLastError
0x18000b24e  mov     ebx, eax
0x18000b250  xor     r9d, r9d; msWindowLength
0x18000b253  xor     r8d, r8d; msPeriod
0x18000b256  xor     edx, edx; pftDueTime
0x18000b258  mov     rcx, rbp; pti
0x18000b25b  call    cs:__imp_SetThreadpoolTimer
0x18000b261  mov     edx, 1; fCancelPendingCallbacks
0x18000b266  mov     rcx, rbp; pti
0x18000b269  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b26f  mov     rcx, rbp; pti
0x18000b272  call    cs:__imp_CloseThreadpoolTimer
0x18000b278  mov     ecx, ebx; dwErrCode
0x18000b27a  call    cs:__imp_SetLastError
0x18000b280  mov     [rdi+38h], r15
0x18000b284  mov     ecx, r14d; dwErrCode
0x18000b287  call    cs:__imp_SetLastError
0x18000b28d  mov     rcx, [rdi+38h]; pti
0x18000b291  test    rcx, rcx
0x18000b294  jz      short loc_18000B2B7
0x18000b296  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000b29f  mov     r9d, 4E2h; msWindowLength
0x18000b2a5  xor     r8d, r8d; msPeriod
0x18000b2a8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000b2ad  call    cs:__imp_SetThreadpoolTimer
0x18000b2b3  mov     byte ptr [rdi+40h], 1
0x18000b2b7  test    rsi, rsi
0x18000b2ba  jz      short loc_18000B2C6
0x18000b2bc  mov     rcx, rsi; SRWLock
0x18000b2bf  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b2c5  nop
0x18000b2c6  add     rsp, 38h
0x18000b2ca  pop     r15
0x18000b2cc  pop     r14
0x18000b2ce  pop     rdi
0x18000b2cf  pop     rsi
0x18000b2d0  pop     rbp
0x18000b2d1  pop     rbx
0x18000b2d2  retn
```
