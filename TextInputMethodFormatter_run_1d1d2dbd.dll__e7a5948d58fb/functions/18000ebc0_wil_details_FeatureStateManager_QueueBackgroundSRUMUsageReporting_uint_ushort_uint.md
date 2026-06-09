# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000ebc0`
- end: `0x18000ed5c`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `412`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180011bc0`

## callees

- `0x180002db8`
- `0x18000ebc0`
- `0x18001268c`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000ec8d`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x18000ec8d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ec57`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ec81`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ec57`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ec81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ed48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ed48`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ec10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ec10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed10`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ecbf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ecbf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ece4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ed36`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ece4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ed36`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ecfb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ecfb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ecf2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ecf2`

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
    _invalid_parameter_noinfo();
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
0x18000ebc0  push    rbx
0x18000ebc2  push    rbp
0x18000ebc3  push    rsi
0x18000ebc4  push    rdi
0x18000ebc5  push    r14
0x18000ebc7  push    r15
0x18000ebc9  sub     rsp, 38h
0x18000ebcd  mov     ebp, r9d
0x18000ebd0  movzx   ebx, r8w
0x18000ebd4  mov     r14d, edx
0x18000ebd7  mov     rdi, rcx
0x18000ebda  cmp     byte ptr [rcx], 0
0x18000ebdd  jz      loc_18000ED4F
0x18000ebe3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000ebea  jnz     loc_18000ED4F
0x18000ebf0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ebf7  test    rax, rax
0x18000ebfa  jz      short loc_18000EC09
0x18000ebfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec01  test    al, al
0x18000ec03  jnz     loc_18000ED4F
0x18000ec09  lea     rsi, [rdi+28h]
0x18000ec0d  mov     rcx, rsi; SRWLock
0x18000ec10  call    cs:__imp_AcquireSRWLockExclusive
0x18000ec16  xor     eax, eax
0x18000ec18  mov     word ptr [rsp+68h+var_48+6], ax
0x18000ec1d  mov     dword ptr [rsp+68h+var_48], r14d
0x18000ec22  mov     word ptr [rsp+68h+var_48+4], bx
0x18000ec27  lea     rbx, [rdi+0E8h]
0x18000ec2e  lea     edx, [rax+0Ch]; unsigned __int64
0x18000ec31  mov     rcx, rbx; this
0x18000ec34  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ec39  test    al, al
0x18000ec3b  jz      short loc_18000EC98
0x18000ec3d  mov     rcx, [rbx+8]; void *
0x18000ec41  mov     rax, [rbx+10h]
0x18000ec45  sub     rax, rcx
0x18000ec48  cmp     rcx, [rbx+10h]
0x18000ec4c  sbb     r8, r8
0x18000ec4f  and     r8, rax; Size
0x18000ec52  test    rcx, rcx
0x18000ec55  jnz     short loc_18000EC65
0x18000ec57  call    cs:__imp__o__errno
0x18000ec5d  mov     dword ptr [rax], 16h
0x18000ec63  jmp     short loc_18000EC8D
0x18000ec65  cmp     r8, 0Ch
0x18000ec69  jb      short loc_18000EC7A
0x18000ec6b  movsd   xmm0, [rsp+68h+var_48]
0x18000ec71  movsd   qword ptr [rcx], xmm0
0x18000ec75  mov     [rcx+8], ebp
0x18000ec78  jmp     short loc_18000EC93
0x18000ec7a  xor     edx, edx; Val
0x18000ec7c  call    memset_0
0x18000ec81  call    cs:__imp__o__errno
0x18000ec87  mov     dword ptr [rax], 22h ; '"'
0x18000ec8d  call    cs:__imp__invalid_parameter_noinfo
0x18000ec93  add     qword ptr [rbx+8], 0Ch
0x18000ec98  cmp     byte ptr [rdi+40h], 0
0x18000ec9c  jnz     loc_18000ED40
0x18000eca2  cmp     qword ptr [rdi+38h], 0
0x18000eca7  jnz     short loc_18000ED16
0x18000eca9  call    cs:__imp_GetLastError
0x18000ecaf  mov     r14d, eax
0x18000ecb2  xor     r8d, r8d; pcbe
0x18000ecb5  mov     rdx, rdi; pv
0x18000ecb8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ecbf  call    cs:__imp_CreateThreadpoolTimer
0x18000ecc5  mov     r15, rax
0x18000ecc8  mov     rbp, [rdi+38h]
0x18000eccc  test    rbp, rbp
0x18000eccf  jz      short loc_18000ED09
0x18000ecd1  call    cs:__imp_GetLastError
0x18000ecd7  mov     ebx, eax
0x18000ecd9  xor     r9d, r9d; msWindowLength
0x18000ecdc  xor     r8d, r8d; msPeriod
0x18000ecdf  xor     edx, edx; pftDueTime
0x18000ece1  mov     rcx, rbp; pti
0x18000ece4  call    cs:__imp_SetThreadpoolTimer
0x18000ecea  mov     edx, 1; fCancelPendingCallbacks
0x18000ecef  mov     rcx, rbp; pti
0x18000ecf2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ecf8  mov     rcx, rbp; pti
0x18000ecfb  call    cs:__imp_CloseThreadpoolTimer
0x18000ed01  mov     ecx, ebx; dwErrCode
0x18000ed03  call    cs:__imp_SetLastError
0x18000ed09  mov     [rdi+38h], r15
0x18000ed0d  mov     ecx, r14d; dwErrCode
0x18000ed10  call    cs:__imp_SetLastError
0x18000ed16  mov     rcx, [rdi+38h]; pti
0x18000ed1a  test    rcx, rcx
0x18000ed1d  jz      short loc_18000ED40
0x18000ed1f  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000ed28  mov     r9d, 4E2h; msWindowLength
0x18000ed2e  xor     r8d, r8d; msPeriod
0x18000ed31  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000ed36  call    cs:__imp_SetThreadpoolTimer
0x18000ed3c  mov     byte ptr [rdi+40h], 1
0x18000ed40  test    rsi, rsi
0x18000ed43  jz      short loc_18000ED4F
0x18000ed45  mov     rcx, rsi; SRWLock
0x18000ed48  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ed4e  nop
0x18000ed4f  add     rsp, 38h
0x18000ed53  pop     r15
0x18000ed55  pop     r14
0x18000ed57  pop     rdi
0x18000ed58  pop     rsi
0x18000ed59  pop     rbp
0x18000ed5a  pop     rbx
0x18000ed5b  retn
```
