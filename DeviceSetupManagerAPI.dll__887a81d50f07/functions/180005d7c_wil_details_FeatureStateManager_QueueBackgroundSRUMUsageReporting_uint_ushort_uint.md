# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180005d7c`
- end: `0x180005f17`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008150`

## callees

- `0x1800024f6`
- `0x180002570`
- `0x180005d7c`
- `0x18000877c`
- `0x18000f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e13`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e3d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e13`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005dcc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005dcc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005f03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ebe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ecb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ebe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ecb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005eb6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005eb6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005ead`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005ead`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005e9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005ef1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005e9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005ef1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005e7a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005e7a`

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
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v16;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
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
0x180005d7c  push    rbx
0x180005d7e  push    rbp
0x180005d7f  push    rsi
0x180005d80  push    rdi
0x180005d81  push    r14
0x180005d83  push    r15
0x180005d85  sub     rsp, 38h
0x180005d89  mov     ebp, r9d
0x180005d8c  movzx   ebx, r8w
0x180005d90  mov     r14d, edx
0x180005d93  mov     rdi, rcx
0x180005d96  cmp     byte ptr [rcx], 0
0x180005d99  jz      loc_180005F0A
0x180005d9f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180005da6  jnz     loc_180005F0A
0x180005dac  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180005db3  test    rax, rax
0x180005db6  jz      short loc_180005DC5
0x180005db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dbd  test    al, al
0x180005dbf  jnz     loc_180005F0A
0x180005dc5  lea     rsi, [rdi+28h]
0x180005dc9  mov     rcx, rsi; SRWLock
0x180005dcc  call    cs:__imp_AcquireSRWLockExclusive
0x180005dd2  xor     eax, eax
0x180005dd4  mov     word ptr [rsp+68h+var_48+6], ax
0x180005dd9  mov     dword ptr [rsp+68h+var_48], r14d
0x180005dde  mov     word ptr [rsp+68h+var_48+4], bx
0x180005de3  lea     rbx, [rdi+0E8h]
0x180005dea  lea     edx, [rax+0Ch]; unsigned __int64
0x180005ded  mov     rcx, rbx; this
0x180005df0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005df5  test    al, al
0x180005df7  jz      short loc_180005E53
0x180005df9  mov     rcx, [rbx+8]; void *
0x180005dfd  mov     rax, [rbx+10h]
0x180005e01  sub     rax, rcx
0x180005e04  cmp     rcx, [rbx+10h]
0x180005e08  sbb     r8, r8
0x180005e0b  and     r8, rax; Size
0x180005e0e  test    rcx, rcx
0x180005e11  jnz     short loc_180005E21
0x180005e13  call    cs:__imp__o__errno
0x180005e19  mov     dword ptr [rax], 16h
0x180005e1f  jmp     short loc_180005E49
0x180005e21  cmp     r8, 0Ch
0x180005e25  jb      short loc_180005E36
0x180005e27  movsd   xmm0, [rsp+68h+var_48]
0x180005e2d  movsd   qword ptr [rcx], xmm0
0x180005e31  mov     [rcx+8], ebp
0x180005e34  jmp     short loc_180005E4E
0x180005e36  xor     edx, edx; Val
0x180005e38  call    memset_0
0x180005e3d  call    cs:__imp__o__errno
0x180005e43  mov     dword ptr [rax], 22h ; '"'
0x180005e49  call    _invalid_parameter_noinfo
0x180005e4e  add     qword ptr [rbx+8], 0Ch
0x180005e53  cmp     byte ptr [rdi+40h], 0
0x180005e57  jnz     loc_180005EFB
0x180005e5d  cmp     qword ptr [rdi+38h], 0
0x180005e62  jnz     short loc_180005ED1
0x180005e64  call    cs:__imp_GetLastError
0x180005e6a  mov     r14d, eax
0x180005e6d  xor     r8d, r8d; pcbe
0x180005e70  mov     rdx, rdi; pv
0x180005e73  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005e7a  call    cs:__imp_CreateThreadpoolTimer
0x180005e80  mov     r15, rax
0x180005e83  mov     rbp, [rdi+38h]
0x180005e87  test    rbp, rbp
0x180005e8a  jz      short loc_180005EC4
0x180005e8c  call    cs:__imp_GetLastError
0x180005e92  mov     ebx, eax
0x180005e94  xor     r9d, r9d; msWindowLength
0x180005e97  xor     r8d, r8d; msPeriod
0x180005e9a  xor     edx, edx; pftDueTime
0x180005e9c  mov     rcx, rbp; pti
0x180005e9f  call    cs:__imp_SetThreadpoolTimer
0x180005ea5  mov     edx, 1; fCancelPendingCallbacks
0x180005eaa  mov     rcx, rbp; pti
0x180005ead  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005eb3  mov     rcx, rbp; pti
0x180005eb6  call    cs:__imp_CloseThreadpoolTimer
0x180005ebc  mov     ecx, ebx; dwErrCode
0x180005ebe  call    cs:__imp_SetLastError
0x180005ec4  mov     [rdi+38h], r15
0x180005ec8  mov     ecx, r14d; dwErrCode
0x180005ecb  call    cs:__imp_SetLastError
0x180005ed1  mov     rcx, [rdi+38h]; pti
0x180005ed5  test    rcx, rcx
0x180005ed8  jz      short loc_180005EFB
0x180005eda  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180005ee3  mov     r9d, 4E2h; msWindowLength
0x180005ee9  xor     r8d, r8d; msPeriod
0x180005eec  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180005ef1  call    cs:__imp_SetThreadpoolTimer
0x180005ef7  mov     byte ptr [rdi+40h], 1
0x180005efb  test    rsi, rsi
0x180005efe  jz      short loc_180005F0A
0x180005f00  mov     rcx, rsi; SRWLock
0x180005f03  call    cs:__imp_ReleaseSRWLockExclusive
0x180005f09  nop
0x180005f0a  add     rsp, 38h
0x180005f0e  pop     r15
0x180005f10  pop     r14
0x180005f12  pop     rdi
0x180005f13  pop     rsi
0x180005f14  pop     rbp
0x180005f15  pop     rbx
0x180005f16  retn
```
