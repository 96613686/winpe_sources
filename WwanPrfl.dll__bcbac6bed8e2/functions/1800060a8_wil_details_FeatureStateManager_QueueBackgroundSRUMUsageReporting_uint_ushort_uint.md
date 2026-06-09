# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800060a8`
- end: `0x180006243`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008c30`

## callees

- `0x180001fca`
- `0x180002034`
- `0x1800060a8`
- `0x18000d5fc`
- `0x180014010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000613f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006169`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000613f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006190`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800061ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800061f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800061ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800061f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000622f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000622f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800060f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800060f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800061e2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800061e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800061d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800061d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800061cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000621d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800061cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000621d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800061a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800061a6`

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
0x1800060a8  push    rbx
0x1800060aa  push    rbp
0x1800060ab  push    rsi
0x1800060ac  push    rdi
0x1800060ad  push    r14
0x1800060af  push    r15
0x1800060b1  sub     rsp, 38h
0x1800060b5  mov     ebp, r9d
0x1800060b8  movzx   ebx, r8w
0x1800060bc  mov     r14d, edx
0x1800060bf  mov     rdi, rcx
0x1800060c2  cmp     byte ptr [rcx], 0
0x1800060c5  jz      loc_180006236
0x1800060cb  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800060d2  jnz     loc_180006236
0x1800060d8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800060df  test    rax, rax
0x1800060e2  jz      short loc_1800060F1
0x1800060e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060e9  test    al, al
0x1800060eb  jnz     loc_180006236
0x1800060f1  lea     rsi, [rdi+28h]
0x1800060f5  mov     rcx, rsi; SRWLock
0x1800060f8  call    cs:__imp_AcquireSRWLockExclusive
0x1800060fe  xor     eax, eax
0x180006100  mov     word ptr [rsp+68h+var_48+6], ax
0x180006105  mov     dword ptr [rsp+68h+var_48], r14d
0x18000610a  mov     word ptr [rsp+68h+var_48+4], bx
0x18000610f  lea     rbx, [rdi+0E8h]
0x180006116  lea     edx, [rax+0Ch]; unsigned __int64
0x180006119  mov     rcx, rbx; this
0x18000611c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006121  test    al, al
0x180006123  jz      short loc_18000617F
0x180006125  mov     rcx, [rbx+8]; void *
0x180006129  mov     rax, [rbx+10h]
0x18000612d  sub     rax, rcx
0x180006130  cmp     rcx, [rbx+10h]
0x180006134  sbb     r8, r8
0x180006137  and     r8, rax; Size
0x18000613a  test    rcx, rcx
0x18000613d  jnz     short loc_18000614D
0x18000613f  call    cs:__imp__o__errno
0x180006145  mov     dword ptr [rax], 16h
0x18000614b  jmp     short loc_180006175
0x18000614d  cmp     r8, 0Ch
0x180006151  jb      short loc_180006162
0x180006153  movsd   xmm0, [rsp+68h+var_48]
0x180006159  movsd   qword ptr [rcx], xmm0
0x18000615d  mov     [rcx+8], ebp
0x180006160  jmp     short loc_18000617A
0x180006162  xor     edx, edx; Val
0x180006164  call    memset_0
0x180006169  call    cs:__imp__o__errno
0x18000616f  mov     dword ptr [rax], 22h ; '"'
0x180006175  call    _invalid_parameter_noinfo
0x18000617a  add     qword ptr [rbx+8], 0Ch
0x18000617f  cmp     byte ptr [rdi+40h], 0
0x180006183  jnz     loc_180006227
0x180006189  cmp     qword ptr [rdi+38h], 0
0x18000618e  jnz     short loc_1800061FD
0x180006190  call    cs:__imp_GetLastError
0x180006196  mov     r14d, eax
0x180006199  xor     r8d, r8d; pcbe
0x18000619c  mov     rdx, rdi; pv
0x18000619f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800061a6  call    cs:__imp_CreateThreadpoolTimer
0x1800061ac  mov     r15, rax
0x1800061af  mov     rbp, [rdi+38h]
0x1800061b3  test    rbp, rbp
0x1800061b6  jz      short loc_1800061F0
0x1800061b8  call    cs:__imp_GetLastError
0x1800061be  mov     ebx, eax
0x1800061c0  xor     r9d, r9d; msWindowLength
0x1800061c3  xor     r8d, r8d; msPeriod
0x1800061c6  xor     edx, edx; pftDueTime
0x1800061c8  mov     rcx, rbp; pti
0x1800061cb  call    cs:__imp_SetThreadpoolTimer
0x1800061d1  mov     edx, 1; fCancelPendingCallbacks
0x1800061d6  mov     rcx, rbp; pti
0x1800061d9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800061df  mov     rcx, rbp; pti
0x1800061e2  call    cs:__imp_CloseThreadpoolTimer
0x1800061e8  mov     ecx, ebx; dwErrCode
0x1800061ea  call    cs:__imp_SetLastError
0x1800061f0  mov     [rdi+38h], r15
0x1800061f4  mov     ecx, r14d; dwErrCode
0x1800061f7  call    cs:__imp_SetLastError
0x1800061fd  mov     rcx, [rdi+38h]; pti
0x180006201  test    rcx, rcx
0x180006204  jz      short loc_180006227
0x180006206  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000620f  mov     r9d, 4E2h; msWindowLength
0x180006215  xor     r8d, r8d; msPeriod
0x180006218  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000621d  call    cs:__imp_SetThreadpoolTimer
0x180006223  mov     byte ptr [rdi+40h], 1
0x180006227  test    rsi, rsi
0x18000622a  jz      short loc_180006236
0x18000622c  mov     rcx, rsi; SRWLock
0x18000622f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006235  nop
0x180006236  add     rsp, 38h
0x18000623a  pop     r15
0x18000623c  pop     r14
0x18000623e  pop     rdi
0x18000623f  pop     rsi
0x180006240  pop     rbp
0x180006241  pop     rbx
0x180006242  retn
```
