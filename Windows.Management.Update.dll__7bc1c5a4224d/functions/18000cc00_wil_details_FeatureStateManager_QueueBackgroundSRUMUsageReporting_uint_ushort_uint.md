# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000cc00`
- end: `0x18000cd9b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000f640`

## callees

- `0x180003392`
- `0x1800033e8`
- `0x18000cc00`
- `0x18000fcc0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000cc97`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ccc1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000cc97`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ccc1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cc50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cc50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cd87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cd87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd10`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cd23`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cd75`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cd23`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cd75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cd3a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cd3a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ccfe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ccfe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cd31`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cd31`

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
0x18000cc00  push    rbx
0x18000cc02  push    rbp
0x18000cc03  push    rsi
0x18000cc04  push    rdi
0x18000cc05  push    r14
0x18000cc07  push    r15
0x18000cc09  sub     rsp, 38h
0x18000cc0d  mov     ebp, r9d
0x18000cc10  movzx   ebx, r8w
0x18000cc14  mov     r14d, edx
0x18000cc17  mov     rdi, rcx
0x18000cc1a  cmp     byte ptr [rcx], 0
0x18000cc1d  jz      loc_18000CD8E
0x18000cc23  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000cc2a  jnz     loc_18000CD8E
0x18000cc30  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000cc37  test    rax, rax
0x18000cc3a  jz      short loc_18000CC49
0x18000cc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc41  test    al, al
0x18000cc43  jnz     loc_18000CD8E
0x18000cc49  lea     rsi, [rdi+28h]
0x18000cc4d  mov     rcx, rsi; SRWLock
0x18000cc50  call    cs:__imp_AcquireSRWLockExclusive
0x18000cc56  xor     eax, eax
0x18000cc58  mov     word ptr [rsp+68h+var_48+6], ax
0x18000cc5d  mov     dword ptr [rsp+68h+var_48], r14d
0x18000cc62  mov     word ptr [rsp+68h+var_48+4], bx
0x18000cc67  lea     rbx, [rdi+0E8h]
0x18000cc6e  lea     edx, [rax+0Ch]; unsigned __int64
0x18000cc71  mov     rcx, rbx; this
0x18000cc74  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000cc79  test    al, al
0x18000cc7b  jz      short loc_18000CCD7
0x18000cc7d  mov     rcx, [rbx+8]; void *
0x18000cc81  mov     rax, [rbx+10h]
0x18000cc85  sub     rax, rcx
0x18000cc88  cmp     rcx, [rbx+10h]
0x18000cc8c  sbb     r8, r8
0x18000cc8f  and     r8, rax; Size
0x18000cc92  test    rcx, rcx
0x18000cc95  jnz     short loc_18000CCA5
0x18000cc97  call    cs:__imp__o__errno
0x18000cc9d  mov     dword ptr [rax], 16h
0x18000cca3  jmp     short loc_18000CCCD
0x18000cca5  cmp     r8, 0Ch
0x18000cca9  jb      short loc_18000CCBA
0x18000ccab  movsd   xmm0, [rsp+68h+var_48]
0x18000ccb1  movsd   qword ptr [rcx], xmm0
0x18000ccb5  mov     [rcx+8], ebp
0x18000ccb8  jmp     short loc_18000CCD2
0x18000ccba  xor     edx, edx; Val
0x18000ccbc  call    memset_0
0x18000ccc1  call    cs:__imp__o__errno
0x18000ccc7  mov     dword ptr [rax], 22h ; '"'
0x18000cccd  call    _invalid_parameter_noinfo
0x18000ccd2  add     qword ptr [rbx+8], 0Ch
0x18000ccd7  cmp     byte ptr [rdi+40h], 0
0x18000ccdb  jnz     loc_18000CD7F
0x18000cce1  cmp     qword ptr [rdi+38h], 0
0x18000cce6  jnz     short loc_18000CD55
0x18000cce8  call    cs:__imp_GetLastError
0x18000ccee  mov     r14d, eax
0x18000ccf1  xor     r8d, r8d; pcbe
0x18000ccf4  mov     rdx, rdi; pv
0x18000ccf7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ccfe  call    cs:__imp_CreateThreadpoolTimer
0x18000cd04  mov     r15, rax
0x18000cd07  mov     rbp, [rdi+38h]
0x18000cd0b  test    rbp, rbp
0x18000cd0e  jz      short loc_18000CD48
0x18000cd10  call    cs:__imp_GetLastError
0x18000cd16  mov     ebx, eax
0x18000cd18  xor     r9d, r9d; msWindowLength
0x18000cd1b  xor     r8d, r8d; msPeriod
0x18000cd1e  xor     edx, edx; pftDueTime
0x18000cd20  mov     rcx, rbp; pti
0x18000cd23  call    cs:__imp_SetThreadpoolTimer
0x18000cd29  mov     edx, 1; fCancelPendingCallbacks
0x18000cd2e  mov     rcx, rbp; pti
0x18000cd31  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cd37  mov     rcx, rbp; pti
0x18000cd3a  call    cs:__imp_CloseThreadpoolTimer
0x18000cd40  mov     ecx, ebx; dwErrCode
0x18000cd42  call    cs:__imp_SetLastError
0x18000cd48  mov     [rdi+38h], r15
0x18000cd4c  mov     ecx, r14d; dwErrCode
0x18000cd4f  call    cs:__imp_SetLastError
0x18000cd55  mov     rcx, [rdi+38h]; pti
0x18000cd59  test    rcx, rcx
0x18000cd5c  jz      short loc_18000CD7F
0x18000cd5e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000cd67  mov     r9d, 4E2h; msWindowLength
0x18000cd6d  xor     r8d, r8d; msPeriod
0x18000cd70  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000cd75  call    cs:__imp_SetThreadpoolTimer
0x18000cd7b  mov     byte ptr [rdi+40h], 1
0x18000cd7f  test    rsi, rsi
0x18000cd82  jz      short loc_18000CD8E
0x18000cd84  mov     rcx, rsi; SRWLock
0x18000cd87  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cd8d  nop
0x18000cd8e  add     rsp, 38h
0x18000cd92  pop     r15
0x18000cd94  pop     r14
0x18000cd96  pop     rdi
0x18000cd97  pop     rsi
0x18000cd98  pop     rbp
0x18000cd99  pop     rbx
0x18000cd9a  retn
```
