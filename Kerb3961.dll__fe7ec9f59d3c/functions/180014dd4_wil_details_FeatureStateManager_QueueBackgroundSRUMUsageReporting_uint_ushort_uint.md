# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180014dd4`
- end: `0x180014f6e`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `410`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180017a90`

## callees

- `0x1800028c8`
- `0x180002928`
- `0x180014dd4`
- `0x180018294`
- `0x18001e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014e6b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014e95`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014e6b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014e95`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014e24`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014e24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014f5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014f5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014f16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014f23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014f16`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014f23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ee4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ee4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014f0e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014f0e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014f05`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014f05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014ef7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014f49`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014ef7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014f49`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014ed2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180014ed2`

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
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v16; // rbp
  PTP_TIMER v17; // r15
  DWORD v18; // ebx
  struct _TP_TIMER *v19; // rcx
  __int64 v20; // [rsp+20h] [rbp-48h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  if ( !LOBYTE(pv->Ptr)
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    return;
  }
  AcquireSRWLockExclusive(pv + 5);
  HIDWORD(v20) = a3;
  LODWORD(v20) = a2;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
  {
    Ptr = pv[30].Ptr;
    v10 = ((char *)pv[31].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[31].Ptr);
    if ( Ptr )
    {
      if ( v10 >= 0xC )
      {
        *(_QWORD *)Ptr = v20;
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
      v17 = ThreadpoolTimer;
      if ( v16 )
      {
        v18 = GetLastError();
        SetThreadpoolTimer(v16, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v16, 1);
        CloseThreadpoolTimer(v16);
        SetLastError(v18);
      }
      pv[7].Ptr = v17;
      SetLastError(LastError);
    }
    v19 = (struct _TP_TIMER *)pv[7].Ptr;
    if ( v19 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v19, &pftDueTime, 0, 0x4E2u);
      LOBYTE(pv[8].Ptr) = 1;
    }
  }
  if ( pv != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(pv + 5);
}

```

## disassembly

```asm
0x180014dd4  push    rbx
0x180014dd6  push    rbp
0x180014dd7  push    rsi
0x180014dd8  push    rdi
0x180014dd9  push    r14
0x180014ddb  push    r15
0x180014ddd  sub     rsp, 38h
0x180014de1  cmp     byte ptr [rcx], 0
0x180014de4  mov     ebp, r9d
0x180014de7  movzx   ebx, r8w
0x180014deb  mov     r14d, edx
0x180014dee  mov     rdi, rcx
0x180014df1  jz      loc_180014F61
0x180014df7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180014dfe  jnz     loc_180014F61
0x180014e04  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180014e0b  test    rax, rax
0x180014e0e  jz      short loc_180014E1D
0x180014e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e15  test    al, al
0x180014e17  jnz     loc_180014F61
0x180014e1d  lea     rsi, [rdi+28h]
0x180014e21  mov     rcx, rsi; SRWLock
0x180014e24  call    cs:__imp_AcquireSRWLockExclusive
0x180014e2a  xor     eax, eax
0x180014e2c  mov     word ptr [rsp+68h+var_48+4], bx
0x180014e31  lea     rbx, [rdi+0E8h]
0x180014e38  mov     word ptr [rsp+68h+var_48+6], ax
0x180014e3d  mov     rcx, rbx; this
0x180014e40  mov     dword ptr [rsp+68h+var_48], r14d
0x180014e45  lea     edx, [rax+0Ch]; unsigned __int64
0x180014e48  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180014e4d  test    al, al
0x180014e4f  jz      short loc_180014EAB
0x180014e51  mov     rcx, [rbx+8]; void *
0x180014e55  mov     rax, [rbx+10h]
0x180014e59  sub     rax, rcx
0x180014e5c  cmp     rcx, [rbx+10h]
0x180014e60  sbb     r8, r8
0x180014e63  and     r8, rax; Size
0x180014e66  test    rcx, rcx
0x180014e69  jnz     short loc_180014E79
0x180014e6b  call    cs:__imp__o__errno
0x180014e71  mov     dword ptr [rax], 16h
0x180014e77  jmp     short loc_180014EA1
0x180014e79  cmp     r8, 0Ch
0x180014e7d  jb      short loc_180014E8E
0x180014e7f  movsd   xmm0, [rsp+68h+var_48]
0x180014e85  movsd   qword ptr [rcx], xmm0
0x180014e89  mov     [rcx+8], ebp
0x180014e8c  jmp     short loc_180014EA6
0x180014e8e  xor     edx, edx; Val
0x180014e90  call    memset_0
0x180014e95  call    cs:__imp__o__errno
0x180014e9b  mov     dword ptr [rax], 22h ; '"'
0x180014ea1  call    _invalid_parameter_noinfo
0x180014ea6  add     qword ptr [rbx+8], 0Ch
0x180014eab  cmp     byte ptr [rdi+40h], 0
0x180014eaf  jnz     loc_180014F53
0x180014eb5  cmp     qword ptr [rdi+38h], 0
0x180014eba  jnz     short loc_180014F29
0x180014ebc  call    cs:__imp_GetLastError
0x180014ec2  xor     r8d, r8d; pcbe
0x180014ec5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180014ecc  mov     rdx, rdi; pv
0x180014ecf  mov     r14d, eax
0x180014ed2  call    cs:__imp_CreateThreadpoolTimer
0x180014ed8  mov     rbp, [rdi+38h]
0x180014edc  mov     r15, rax
0x180014edf  test    rbp, rbp
0x180014ee2  jz      short loc_180014F1C
0x180014ee4  call    cs:__imp_GetLastError
0x180014eea  xor     r9d, r9d; msWindowLength
0x180014eed  xor     r8d, r8d; msPeriod
0x180014ef0  xor     edx, edx; pftDueTime
0x180014ef2  mov     rcx, rbp; pti
0x180014ef5  mov     ebx, eax
0x180014ef7  call    cs:__imp_SetThreadpoolTimer
0x180014efd  mov     edx, 1; fCancelPendingCallbacks
0x180014f02  mov     rcx, rbp; pti
0x180014f05  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014f0b  mov     rcx, rbp; pti
0x180014f0e  call    cs:__imp_CloseThreadpoolTimer
0x180014f14  mov     ecx, ebx; dwErrCode
0x180014f16  call    cs:__imp_SetLastError
0x180014f1c  mov     ecx, r14d; dwErrCode
0x180014f1f  mov     [rdi+38h], r15
0x180014f23  call    cs:__imp_SetLastError
0x180014f29  mov     rcx, [rdi+38h]; pti
0x180014f2d  test    rcx, rcx
0x180014f30  jz      short loc_180014F53
0x180014f32  mov     r9d, 4E2h; msWindowLength
0x180014f38  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180014f41  xor     r8d, r8d; msPeriod
0x180014f44  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180014f49  call    cs:__imp_SetThreadpoolTimer
0x180014f4f  mov     byte ptr [rdi+40h], 1
0x180014f53  test    rsi, rsi
0x180014f56  jz      short loc_180014F61
0x180014f58  mov     rcx, rsi; SRWLock
0x180014f5b  call    cs:__imp_ReleaseSRWLockExclusive
0x180014f61  add     rsp, 38h
0x180014f65  pop     r15
0x180014f67  pop     r14
0x180014f69  pop     rdi
0x180014f6a  pop     rsi
0x180014f6b  pop     rbp
0x180014f6c  pop     rbx
0x180014f6d  retn
```
