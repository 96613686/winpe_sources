# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14000acb4`
- end: `0x14000ae4f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000d7a0`

## callees

- `0x140002f1a`
- `0x140002fcc`
- `0x14000acb4`
- `0x14000dd18`
- `0x140012010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ad4b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ad75`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ad4b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ad75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ad9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000adc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ad9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000adc4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000adf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ae03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000adf6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ae03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ad04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ad04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ae3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ae3b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000ade5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000ade5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000adb2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000adb2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000adee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000adee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000add7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ae29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000add7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ae29`

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
0x14000acb4  push    rbx
0x14000acb6  push    rbp
0x14000acb7  push    rsi
0x14000acb8  push    rdi
0x14000acb9  push    r14
0x14000acbb  push    r15
0x14000acbd  sub     rsp, 38h
0x14000acc1  mov     ebp, r9d
0x14000acc4  movzx   ebx, r8w
0x14000acc8  mov     r14d, edx
0x14000accb  mov     rdi, rcx
0x14000acce  cmp     byte ptr [rcx], 0
0x14000acd1  jz      loc_14000AE42
0x14000acd7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000acde  jnz     loc_14000AE42
0x14000ace4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000aceb  test    rax, rax
0x14000acee  jz      short loc_14000ACFD
0x14000acf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acf5  test    al, al
0x14000acf7  jnz     loc_14000AE42
0x14000acfd  lea     rsi, [rdi+28h]
0x14000ad01  mov     rcx, rsi; SRWLock
0x14000ad04  call    cs:__imp_AcquireSRWLockExclusive
0x14000ad0a  xor     eax, eax
0x14000ad0c  mov     word ptr [rsp+68h+var_48+6], ax
0x14000ad11  mov     dword ptr [rsp+68h+var_48], r14d
0x14000ad16  mov     word ptr [rsp+68h+var_48+4], bx
0x14000ad1b  lea     rbx, [rdi+0E8h]
0x14000ad22  lea     edx, [rax+0Ch]; unsigned __int64
0x14000ad25  mov     rcx, rbx; this
0x14000ad28  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000ad2d  test    al, al
0x14000ad2f  jz      short loc_14000AD8B
0x14000ad31  mov     rcx, [rbx+8]; void *
0x14000ad35  mov     rax, [rbx+10h]
0x14000ad39  sub     rax, rcx
0x14000ad3c  cmp     rcx, [rbx+10h]
0x14000ad40  sbb     r8, r8
0x14000ad43  and     r8, rax; Size
0x14000ad46  test    rcx, rcx
0x14000ad49  jnz     short loc_14000AD59
0x14000ad4b  call    cs:__imp__o__errno
0x14000ad51  mov     dword ptr [rax], 16h
0x14000ad57  jmp     short loc_14000AD81
0x14000ad59  cmp     r8, 0Ch
0x14000ad5d  jb      short loc_14000AD6E
0x14000ad5f  movsd   xmm0, [rsp+68h+var_48]
0x14000ad65  movsd   qword ptr [rcx], xmm0
0x14000ad69  mov     [rcx+8], ebp
0x14000ad6c  jmp     short loc_14000AD86
0x14000ad6e  xor     edx, edx; Val
0x14000ad70  call    memset_0
0x14000ad75  call    cs:__imp__o__errno
0x14000ad7b  mov     dword ptr [rax], 22h ; '"'
0x14000ad81  call    _invalid_parameter_noinfo
0x14000ad86  add     qword ptr [rbx+8], 0Ch
0x14000ad8b  cmp     byte ptr [rdi+40h], 0
0x14000ad8f  jnz     loc_14000AE33
0x14000ad95  cmp     qword ptr [rdi+38h], 0
0x14000ad9a  jnz     short loc_14000AE09
0x14000ad9c  call    cs:__imp_GetLastError
0x14000ada2  mov     r14d, eax
0x14000ada5  xor     r8d, r8d; pcbe
0x14000ada8  mov     rdx, rdi; pv
0x14000adab  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000adb2  call    cs:__imp_CreateThreadpoolTimer
0x14000adb8  mov     r15, rax
0x14000adbb  mov     rbp, [rdi+38h]
0x14000adbf  test    rbp, rbp
0x14000adc2  jz      short loc_14000ADFC
0x14000adc4  call    cs:__imp_GetLastError
0x14000adca  mov     ebx, eax
0x14000adcc  xor     r9d, r9d; msWindowLength
0x14000adcf  xor     r8d, r8d; msPeriod
0x14000add2  xor     edx, edx; pftDueTime
0x14000add4  mov     rcx, rbp; pti
0x14000add7  call    cs:__imp_SetThreadpoolTimer
0x14000addd  mov     edx, 1; fCancelPendingCallbacks
0x14000ade2  mov     rcx, rbp; pti
0x14000ade5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000adeb  mov     rcx, rbp; pti
0x14000adee  call    cs:__imp_CloseThreadpoolTimer
0x14000adf4  mov     ecx, ebx; dwErrCode
0x14000adf6  call    cs:__imp_SetLastError
0x14000adfc  mov     [rdi+38h], r15
0x14000ae00  mov     ecx, r14d; dwErrCode
0x14000ae03  call    cs:__imp_SetLastError
0x14000ae09  mov     rcx, [rdi+38h]; pti
0x14000ae0d  test    rcx, rcx
0x14000ae10  jz      short loc_14000AE33
0x14000ae12  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14000ae1b  mov     r9d, 4E2h; msWindowLength
0x14000ae21  xor     r8d, r8d; msPeriod
0x14000ae24  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x14000ae29  call    cs:__imp_SetThreadpoolTimer
0x14000ae2f  mov     byte ptr [rdi+40h], 1
0x14000ae33  test    rsi, rsi
0x14000ae36  jz      short loc_14000AE42
0x14000ae38  mov     rcx, rsi; SRWLock
0x14000ae3b  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ae41  nop
0x14000ae42  add     rsp, 38h
0x14000ae46  pop     r15
0x14000ae48  pop     r14
0x14000ae4a  pop     rdi
0x14000ae4b  pop     rsi
0x14000ae4c  pop     rbp
0x14000ae4d  pop     rbx
0x14000ae4e  retn
```
