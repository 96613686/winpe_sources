# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180008dd8`
- end: `0x180008f73`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000b7a0`

## callees

- `0x18000302e`
- `0x1800030d0`
- `0x180008dd8`
- `0x18000bebc`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e6f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e99`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e6f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e99`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008f5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008f5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008e28`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ee8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f27`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f27`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008efb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008f4d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008efb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008f4d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008f12`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008f12`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008f09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008f09`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008ed6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008ed6`

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
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *v15; // rbp
  DWORD v16; // ebx
  struct _TP_TIMER *v17; // rcx
  __int64 v18; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  LODWORD(v18) = a2;
  HIDWORD(v18) = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v18;
        Ptr[2] = a4;
LABEL_12:
        pv[30].Ptr = (char *)pv[30].Ptr + 12;
        goto LABEL_13;
      }
      memset_0(Ptr, 0, v10);
      *(_DWORD *)_o__errno(v12, v11) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v8) = 22;
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
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
      v15 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v15 )
      {
        v16 = GetLastError();
        SetThreadpoolTimer(v15, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v15, 1);
        CloseThreadpoolTimer(v15);
        SetLastError(v16);
      }
      pv[7].Ptr = ThreadpoolTimer;
      SetLastError(LastError);
    }
    v17 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v17 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v17, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x180008dd8  push    rbx
0x180008dda  push    rbp
0x180008ddb  push    rsi
0x180008ddc  push    rdi
0x180008ddd  push    r14
0x180008ddf  push    r15
0x180008de1  sub     rsp, 38h
0x180008de5  mov     ebp, r9d
0x180008de8  movzx   ebx, r8w
0x180008dec  mov     r14d, edx
0x180008def  mov     rdi, rcx
0x180008df2  cmp     byte ptr [rcx], 0
0x180008df5  jz      loc_180008F66
0x180008dfb  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008e02  jnz     loc_180008F66
0x180008e08  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008e0f  test    rax, rax
0x180008e12  jz      short loc_180008E21
0x180008e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e19  test    al, al
0x180008e1b  jnz     loc_180008F66
0x180008e21  lea     rsi, [rdi+28h]
0x180008e25  mov     rcx, rsi; SRWLock
0x180008e28  call    cs:__imp_AcquireSRWLockExclusive
0x180008e2e  xor     eax, eax
0x180008e30  mov     word ptr [rsp+68h+var_48+6], ax
0x180008e35  mov     dword ptr [rsp+68h+var_48], r14d
0x180008e3a  mov     word ptr [rsp+68h+var_48+4], bx
0x180008e3f  lea     rbx, [rdi+0E8h]
0x180008e46  lea     edx, [rax+0Ch]; unsigned __int64
0x180008e49  mov     rcx, rbx; this
0x180008e4c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008e51  test    al, al
0x180008e53  jz      short loc_180008EAF
0x180008e55  mov     rcx, [rbx+8]; void *
0x180008e59  mov     rax, [rbx+10h]
0x180008e5d  sub     rax, rcx
0x180008e60  cmp     rcx, [rbx+10h]
0x180008e64  sbb     r8, r8
0x180008e67  and     r8, rax; Size
0x180008e6a  test    rcx, rcx
0x180008e6d  jnz     short loc_180008E7D
0x180008e6f  call    cs:__imp__o__errno
0x180008e75  mov     dword ptr [rax], 16h
0x180008e7b  jmp     short loc_180008EA5
0x180008e7d  cmp     r8, 0Ch
0x180008e81  jb      short loc_180008E92
0x180008e83  movsd   xmm0, [rsp+68h+var_48]
0x180008e89  movsd   qword ptr [rcx], xmm0
0x180008e8d  mov     [rcx+8], ebp
0x180008e90  jmp     short loc_180008EAA
0x180008e92  xor     edx, edx; Val
0x180008e94  call    memset_0
0x180008e99  call    cs:__imp__o__errno
0x180008e9f  mov     dword ptr [rax], 22h ; '"'
0x180008ea5  call    _invalid_parameter_noinfo
0x180008eaa  add     qword ptr [rbx+8], 0Ch
0x180008eaf  cmp     byte ptr [rdi+40h], 0
0x180008eb3  jnz     loc_180008F57
0x180008eb9  cmp     qword ptr [rdi+38h], 0
0x180008ebe  jnz     short loc_180008F2D
0x180008ec0  call    cs:__imp_GetLastError
0x180008ec6  mov     r14d, eax
0x180008ec9  xor     r8d, r8d; pcbe
0x180008ecc  mov     rdx, rdi; pv
0x180008ecf  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008ed6  call    cs:__imp_CreateThreadpoolTimer
0x180008edc  mov     r15, rax
0x180008edf  mov     rbp, [rdi+38h]
0x180008ee3  test    rbp, rbp
0x180008ee6  jz      short loc_180008F20
0x180008ee8  call    cs:__imp_GetLastError
0x180008eee  mov     ebx, eax
0x180008ef0  xor     r9d, r9d; msWindowLength
0x180008ef3  xor     r8d, r8d; msPeriod
0x180008ef6  xor     edx, edx; pftDueTime
0x180008ef8  mov     rcx, rbp; pti
0x180008efb  call    cs:__imp_SetThreadpoolTimer
0x180008f01  mov     edx, 1; fCancelPendingCallbacks
0x180008f06  mov     rcx, rbp; pti
0x180008f09  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008f0f  mov     rcx, rbp; pti
0x180008f12  call    cs:__imp_CloseThreadpoolTimer
0x180008f18  mov     ecx, ebx; dwErrCode
0x180008f1a  call    cs:__imp_SetLastError
0x180008f20  mov     [rdi+38h], r15
0x180008f24  mov     ecx, r14d; dwErrCode
0x180008f27  call    cs:__imp_SetLastError
0x180008f2d  mov     rcx, [rdi+38h]; pti
0x180008f31  test    rcx, rcx
0x180008f34  jz      short loc_180008F57
0x180008f36  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180008f3f  mov     r9d, 4E2h; msWindowLength
0x180008f45  xor     r8d, r8d; msPeriod
0x180008f48  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180008f4d  call    cs:__imp_SetThreadpoolTimer
0x180008f53  mov     byte ptr [rdi+40h], 1
0x180008f57  test    rsi, rsi
0x180008f5a  jz      short loc_180008F66
0x180008f5c  mov     rcx, rsi; SRWLock
0x180008f5f  call    cs:__imp_ReleaseSRWLockExclusive
0x180008f65  nop
0x180008f66  add     rsp, 38h
0x180008f6a  pop     r15
0x180008f6c  pop     r14
0x180008f6e  pop     rdi
0x180008f6f  pop     rsi
0x180008f70  pop     rbp
0x180008f71  pop     rbx
0x180008f72  retn
```
