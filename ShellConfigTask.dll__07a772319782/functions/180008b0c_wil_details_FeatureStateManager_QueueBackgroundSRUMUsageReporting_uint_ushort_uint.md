# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180008b0c`
- end: `0x180008ca7`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c010`

## callees

- `0x180002f3a`
- `0x180002f98`
- `0x180008b0c`
- `0x18000c6e0`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008ba3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008bcd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008ba3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008bcd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c1c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b5c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008b5c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c93`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008c93`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008c3d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008c3d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008c46`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008c46`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008c0a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008c0a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008c2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008c81`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008c2f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008c81`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        unsigned __int16 a3,
        int a4)
{
  _DWORD *Ptr; // rcx
  size_t v9; // r8
  __int64 v10; // rcx
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v13; // rbp
  DWORD v14; // ebx
  struct _TP_TIMER *v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v16) = a2;
  HIDWORD(v16) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v9 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v9 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v9);
      *(_DWORD *)_o__errno(v10) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0) = 22;
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
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        v14 = GetLastError();
        SetThreadpoolTimer(v13, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v13, 1);
        CloseThreadpoolTimer(v13);
        SetLastError(v14);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v15 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v15 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v15, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x180008b0c  push    rbx
0x180008b0e  push    rbp
0x180008b0f  push    rsi
0x180008b10  push    rdi
0x180008b11  push    r14
0x180008b13  push    r15
0x180008b15  sub     rsp, 38h
0x180008b19  mov     ebp, r9d
0x180008b1c  movzx   ebx, r8w
0x180008b20  mov     r14d, edx
0x180008b23  mov     rdi, rcx
0x180008b26  cmp     byte ptr [rcx], 0
0x180008b29  jz      loc_180008C9A
0x180008b2f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008b36  jnz     loc_180008C9A
0x180008b3c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008b43  test    rax, rax
0x180008b46  jz      short loc_180008B55
0x180008b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b4d  test    al, al
0x180008b4f  jnz     loc_180008C9A
0x180008b55  lea     rsi, [rdi+28h]
0x180008b59  mov     rcx, rsi; SRWLock
0x180008b5c  call    cs:__imp_AcquireSRWLockExclusive
0x180008b62  xor     eax, eax
0x180008b64  mov     word ptr [rsp+68h+var_48+6], ax
0x180008b69  mov     dword ptr [rsp+68h+var_48], r14d
0x180008b6e  mov     word ptr [rsp+68h+var_48+4], bx
0x180008b73  lea     rbx, [rdi+0E8h]
0x180008b7a  lea     edx, [rax+0Ch]; unsigned __int64
0x180008b7d  mov     rcx, rbx; this
0x180008b80  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008b85  test    al, al
0x180008b87  jz      short loc_180008BE3
0x180008b89  mov     rcx, [rbx+8]; void *
0x180008b8d  mov     rax, [rbx+10h]
0x180008b91  sub     rax, rcx
0x180008b94  cmp     rcx, [rbx+10h]
0x180008b98  sbb     r8, r8
0x180008b9b  and     r8, rax; Size
0x180008b9e  test    rcx, rcx
0x180008ba1  jnz     short loc_180008BB1
0x180008ba3  call    cs:__imp__o__errno
0x180008ba9  mov     dword ptr [rax], 16h
0x180008baf  jmp     short loc_180008BD9
0x180008bb1  cmp     r8, 0Ch
0x180008bb5  jb      short loc_180008BC6
0x180008bb7  movsd   xmm0, [rsp+68h+var_48]
0x180008bbd  movsd   qword ptr [rcx], xmm0
0x180008bc1  mov     [rcx+8], ebp
0x180008bc4  jmp     short loc_180008BDE
0x180008bc6  xor     edx, edx; Val
0x180008bc8  call    memset_0
0x180008bcd  call    cs:__imp__o__errno
0x180008bd3  mov     dword ptr [rax], 22h ; '"'
0x180008bd9  call    _invalid_parameter_noinfo
0x180008bde  add     qword ptr [rbx+8], 0Ch
0x180008be3  cmp     byte ptr [rdi+40h], 0
0x180008be7  jnz     loc_180008C8B
0x180008bed  cmp     qword ptr [rdi+38h], 0
0x180008bf2  jnz     short loc_180008C61
0x180008bf4  call    cs:__imp_GetLastError
0x180008bfa  mov     r14d, eax
0x180008bfd  xor     r8d, r8d; pcbe
0x180008c00  mov     rdx, rdi; pv
0x180008c03  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008c0a  call    cs:__imp_CreateThreadpoolTimer
0x180008c10  mov     r15, rax
0x180008c13  mov     rbp, [rdi+38h]
0x180008c17  test    rbp, rbp
0x180008c1a  jz      short loc_180008C54
0x180008c1c  call    cs:__imp_GetLastError
0x180008c22  mov     ebx, eax
0x180008c24  xor     r9d, r9d; msWindowLength
0x180008c27  xor     r8d, r8d; msPeriod
0x180008c2a  xor     edx, edx; pftDueTime
0x180008c2c  mov     rcx, rbp; pti
0x180008c2f  call    cs:__imp_SetThreadpoolTimer
0x180008c35  mov     edx, 1; fCancelPendingCallbacks
0x180008c3a  mov     rcx, rbp; pti
0x180008c3d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008c43  mov     rcx, rbp; pti
0x180008c46  call    cs:__imp_CloseThreadpoolTimer
0x180008c4c  mov     ecx, ebx; dwErrCode
0x180008c4e  call    cs:__imp_SetLastError
0x180008c54  mov     [rdi+38h], r15
0x180008c58  mov     ecx, r14d; dwErrCode
0x180008c5b  call    cs:__imp_SetLastError
0x180008c61  mov     rcx, [rdi+38h]; pti
0x180008c65  test    rcx, rcx
0x180008c68  jz      short loc_180008C8B
0x180008c6a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180008c73  mov     r9d, 4E2h; msWindowLength
0x180008c79  xor     r8d, r8d; msPeriod
0x180008c7c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180008c81  call    cs:__imp_SetThreadpoolTimer
0x180008c87  mov     byte ptr [rdi+40h], 1
0x180008c8b  test    rsi, rsi
0x180008c8e  jz      short loc_180008C9A
0x180008c90  mov     rcx, rsi; SRWLock
0x180008c93  call    cs:__imp_ReleaseSRWLockExclusive
0x180008c99  nop
0x180008c9a  add     rsp, 38h
0x180008c9e  pop     r15
0x180008ca0  pop     r14
0x180008ca2  pop     rdi
0x180008ca3  pop     rsi
0x180008ca4  pop     rbp
0x180008ca5  pop     rbx
0x180008ca6  retn
```
