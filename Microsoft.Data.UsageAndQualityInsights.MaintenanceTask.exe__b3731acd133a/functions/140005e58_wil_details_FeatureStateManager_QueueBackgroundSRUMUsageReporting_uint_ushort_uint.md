# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140005e58`
- end: `0x140005ff3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400085b0`

## callees

- `0x14000216a`
- `0x14000221c`
- `0x140005e58`
- `0x140008c3c`
- `0x14000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005eef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005f19`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005eef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005f19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005ea8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005ea8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005fdf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005f68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005f9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005fa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005f9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005fa7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140005f56`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140005f56`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005f92`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005f92`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005f7b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005fcd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005f7b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005fcd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005f89`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005f89`

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
      ThreadpoolTimer = CreateThreadpoolTimer(
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
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
0x140005e58  push    rbx
0x140005e5a  push    rbp
0x140005e5b  push    rsi
0x140005e5c  push    rdi
0x140005e5d  push    r14
0x140005e5f  push    r15
0x140005e61  sub     rsp, 38h
0x140005e65  mov     ebp, r9d
0x140005e68  movzx   ebx, r8w
0x140005e6c  mov     r14d, edx
0x140005e6f  mov     rdi, rcx
0x140005e72  cmp     byte ptr [rcx], 0
0x140005e75  jz      loc_140005FE6
0x140005e7b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140005e82  jnz     loc_140005FE6
0x140005e88  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140005e8f  test    rax, rax
0x140005e92  jz      short loc_140005EA1
0x140005e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e99  test    al, al
0x140005e9b  jnz     loc_140005FE6
0x140005ea1  lea     rsi, [rdi+28h]
0x140005ea5  mov     rcx, rsi; SRWLock
0x140005ea8  call    cs:__imp_AcquireSRWLockExclusive
0x140005eae  xor     eax, eax
0x140005eb0  mov     word ptr [rsp+68h+var_48+6], ax
0x140005eb5  mov     dword ptr [rsp+68h+var_48], r14d
0x140005eba  mov     word ptr [rsp+68h+var_48+4], bx
0x140005ebf  lea     rbx, [rdi+0E8h]
0x140005ec6  lea     edx, [rax+0Ch]; unsigned __int64
0x140005ec9  mov     rcx, rbx; this
0x140005ecc  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140005ed1  test    al, al
0x140005ed3  jz      short loc_140005F2F
0x140005ed5  mov     rcx, [rbx+8]; void *
0x140005ed9  mov     rax, [rbx+10h]
0x140005edd  sub     rax, rcx
0x140005ee0  cmp     rcx, [rbx+10h]
0x140005ee4  sbb     r8, r8
0x140005ee7  and     r8, rax; Size
0x140005eea  test    rcx, rcx
0x140005eed  jnz     short loc_140005EFD
0x140005eef  call    cs:__imp__o__errno
0x140005ef5  mov     dword ptr [rax], 16h
0x140005efb  jmp     short loc_140005F25
0x140005efd  cmp     r8, 0Ch
0x140005f01  jb      short loc_140005F12
0x140005f03  movsd   xmm0, [rsp+68h+var_48]
0x140005f09  movsd   qword ptr [rcx], xmm0
0x140005f0d  mov     [rcx+8], ebp
0x140005f10  jmp     short loc_140005F2A
0x140005f12  xor     edx, edx; Val
0x140005f14  call    memset_0
0x140005f19  call    cs:__imp__o__errno
0x140005f1f  mov     dword ptr [rax], 22h ; '"'
0x140005f25  call    _invalid_parameter_noinfo
0x140005f2a  add     qword ptr [rbx+8], 0Ch
0x140005f2f  cmp     byte ptr [rdi+40h], 0
0x140005f33  jnz     loc_140005FD7
0x140005f39  cmp     qword ptr [rdi+38h], 0
0x140005f3e  jnz     short loc_140005FAD
0x140005f40  call    cs:__imp_GetLastError
0x140005f46  mov     r14d, eax
0x140005f49  xor     r8d, r8d; pcbe
0x140005f4c  mov     rdx, rdi; pv
0x140005f4f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140005f56  call    cs:__imp_CreateThreadpoolTimer
0x140005f5c  mov     r15, rax
0x140005f5f  mov     rbp, [rdi+38h]
0x140005f63  test    rbp, rbp
0x140005f66  jz      short loc_140005FA0
0x140005f68  call    cs:__imp_GetLastError
0x140005f6e  mov     ebx, eax
0x140005f70  xor     r9d, r9d; msWindowLength
0x140005f73  xor     r8d, r8d; msPeriod
0x140005f76  xor     edx, edx; pftDueTime
0x140005f78  mov     rcx, rbp; pti
0x140005f7b  call    cs:__imp_SetThreadpoolTimer
0x140005f81  mov     edx, 1; fCancelPendingCallbacks
0x140005f86  mov     rcx, rbp; pti
0x140005f89  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005f8f  mov     rcx, rbp; pti
0x140005f92  call    cs:__imp_CloseThreadpoolTimer
0x140005f98  mov     ecx, ebx; dwErrCode
0x140005f9a  call    cs:__imp_SetLastError
0x140005fa0  mov     [rdi+38h], r15
0x140005fa4  mov     ecx, r14d; dwErrCode
0x140005fa7  call    cs:__imp_SetLastError
0x140005fad  mov     rcx, [rdi+38h]; pti
0x140005fb1  test    rcx, rcx
0x140005fb4  jz      short loc_140005FD7
0x140005fb6  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140005fbf  mov     r9d, 4E2h; msWindowLength
0x140005fc5  xor     r8d, r8d; msPeriod
0x140005fc8  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140005fcd  call    cs:__imp_SetThreadpoolTimer
0x140005fd3  mov     byte ptr [rdi+40h], 1
0x140005fd7  test    rsi, rsi
0x140005fda  jz      short loc_140005FE6
0x140005fdc  mov     rcx, rsi; SRWLock
0x140005fdf  call    cs:__imp_ReleaseSRWLockExclusive
0x140005fe5  nop
0x140005fe6  add     rsp, 38h
0x140005fea  pop     r15
0x140005fec  pop     r14
0x140005fee  pop     rdi
0x140005fef  pop     rsi
0x140005ff0  pop     rbp
0x140005ff1  pop     rbx
0x140005ff2  retn
```
