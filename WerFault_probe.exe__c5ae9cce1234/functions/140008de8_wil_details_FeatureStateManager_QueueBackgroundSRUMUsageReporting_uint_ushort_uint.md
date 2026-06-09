# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140008de8`
- end: `0x140008f83`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000c060`

## callees

- `0x140002ff2`
- `0x1400030a8`
- `0x140008de8`
- `0x14000ca4c`
- `0x14005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008e7f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008ea9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008e7f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008ea9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008e38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008e38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008f6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140008f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008ed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008ed0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008ef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008f2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008f37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008f2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008f37`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008f22`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008f22`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008f19`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140008f19`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140008ee6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140008ee6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008f0b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008f5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008f0b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008f5d`

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
0x140008de8  push    rbx
0x140008dea  push    rbp
0x140008deb  push    rsi
0x140008dec  push    rdi
0x140008ded  push    r14
0x140008def  push    r15
0x140008df1  sub     rsp, 38h
0x140008df5  mov     ebp, r9d
0x140008df8  movzx   ebx, r8w
0x140008dfc  mov     r14d, edx
0x140008dff  mov     rdi, rcx
0x140008e02  cmp     byte ptr [rcx], 0
0x140008e05  jz      loc_140008F76
0x140008e0b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140008e12  jnz     loc_140008F76
0x140008e18  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140008e1f  test    rax, rax
0x140008e22  jz      short loc_140008E31
0x140008e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e29  test    al, al
0x140008e2b  jnz     loc_140008F76
0x140008e31  lea     rsi, [rdi+28h]
0x140008e35  mov     rcx, rsi; SRWLock
0x140008e38  call    cs:__imp_AcquireSRWLockExclusive
0x140008e3e  xor     eax, eax
0x140008e40  mov     word ptr [rsp+68h+var_48+6], ax
0x140008e45  mov     dword ptr [rsp+68h+var_48], r14d
0x140008e4a  mov     word ptr [rsp+68h+var_48+4], bx
0x140008e4f  lea     rbx, [rdi+0E8h]
0x140008e56  lea     edx, [rax+0Ch]; unsigned __int64
0x140008e59  mov     rcx, rbx; this
0x140008e5c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140008e61  test    al, al
0x140008e63  jz      short loc_140008EBF
0x140008e65  mov     rcx, [rbx+8]; void *
0x140008e69  mov     rax, [rbx+10h]
0x140008e6d  sub     rax, rcx
0x140008e70  cmp     rcx, [rbx+10h]
0x140008e74  sbb     r8, r8
0x140008e77  and     r8, rax; Size
0x140008e7a  test    rcx, rcx
0x140008e7d  jnz     short loc_140008E8D
0x140008e7f  call    cs:__imp__o__errno
0x140008e85  mov     dword ptr [rax], 16h
0x140008e8b  jmp     short loc_140008EB5
0x140008e8d  cmp     r8, 0Ch
0x140008e91  jb      short loc_140008EA2
0x140008e93  movsd   xmm0, [rsp+68h+var_48]
0x140008e99  movsd   qword ptr [rcx], xmm0
0x140008e9d  mov     [rcx+8], ebp
0x140008ea0  jmp     short loc_140008EBA
0x140008ea2  xor     edx, edx; Val
0x140008ea4  call    memset_0
0x140008ea9  call    cs:__imp__o__errno
0x140008eaf  mov     dword ptr [rax], 22h ; '"'
0x140008eb5  call    _invalid_parameter_noinfo
0x140008eba  add     qword ptr [rbx+8], 0Ch
0x140008ebf  cmp     byte ptr [rdi+40h], 0
0x140008ec3  jnz     loc_140008F67
0x140008ec9  cmp     qword ptr [rdi+38h], 0
0x140008ece  jnz     short loc_140008F3D
0x140008ed0  call    cs:__imp_GetLastError
0x140008ed6  mov     r14d, eax
0x140008ed9  xor     r8d, r8d; pcbe
0x140008edc  mov     rdx, rdi; pv
0x140008edf  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140008ee6  call    cs:__imp_CreateThreadpoolTimer
0x140008eec  mov     r15, rax
0x140008eef  mov     rbp, [rdi+38h]
0x140008ef3  test    rbp, rbp
0x140008ef6  jz      short loc_140008F30
0x140008ef8  call    cs:__imp_GetLastError
0x140008efe  mov     ebx, eax
0x140008f00  xor     r9d, r9d; msWindowLength
0x140008f03  xor     r8d, r8d; msPeriod
0x140008f06  xor     edx, edx; pftDueTime
0x140008f08  mov     rcx, rbp; pti
0x140008f0b  call    cs:__imp_SetThreadpoolTimer
0x140008f11  mov     edx, 1; fCancelPendingCallbacks
0x140008f16  mov     rcx, rbp; pti
0x140008f19  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008f1f  mov     rcx, rbp; pti
0x140008f22  call    cs:__imp_CloseThreadpoolTimer
0x140008f28  mov     ecx, ebx; dwErrCode
0x140008f2a  call    cs:__imp_SetLastError
0x140008f30  mov     [rdi+38h], r15
0x140008f34  mov     ecx, r14d; dwErrCode
0x140008f37  call    cs:__imp_SetLastError
0x140008f3d  mov     rcx, [rdi+38h]; pti
0x140008f41  test    rcx, rcx
0x140008f44  jz      short loc_140008F67
0x140008f46  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140008f4f  mov     r9d, 4E2h; msWindowLength
0x140008f55  xor     r8d, r8d; msPeriod
0x140008f58  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140008f5d  call    cs:__imp_SetThreadpoolTimer
0x140008f63  mov     byte ptr [rdi+40h], 1
0x140008f67  test    rsi, rsi
0x140008f6a  jz      short loc_140008F76
0x140008f6c  mov     rcx, rsi; SRWLock
0x140008f6f  call    cs:__imp_ReleaseSRWLockExclusive
0x140008f75  nop
0x140008f76  add     rsp, 38h
0x140008f7a  pop     r15
0x140008f7c  pop     r14
0x140008f7e  pop     rdi
0x140008f7f  pop     rsi
0x140008f80  pop     rbp
0x140008f81  pop     rbx
0x140008f82  retn
```
