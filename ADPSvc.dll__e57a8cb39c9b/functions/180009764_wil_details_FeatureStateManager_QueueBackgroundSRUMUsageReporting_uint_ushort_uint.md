# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180009764`
- end: `0x1800098ff`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000b170`

## callees

- `0x180002c6a`
- `0x180002cf8`
- `0x180009764`
- `0x18000b5ac`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800097fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009825`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800097fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009825`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800098eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800098eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800097b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800097b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800098a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800098b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800098a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800098b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000984c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000984c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009874`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009887`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800098d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009887`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800098d9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009862`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009862`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009895`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009895`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000989e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000989e`

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
0x180009764  push    rbx
0x180009766  push    rbp
0x180009767  push    rsi
0x180009768  push    rdi
0x180009769  push    r14
0x18000976b  push    r15
0x18000976d  sub     rsp, 38h
0x180009771  mov     ebp, r9d
0x180009774  movzx   ebx, r8w
0x180009778  mov     r14d, edx
0x18000977b  mov     rdi, rcx
0x18000977e  cmp     byte ptr [rcx], 0
0x180009781  jz      loc_1800098F2
0x180009787  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000978e  jnz     loc_1800098F2
0x180009794  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000979b  test    rax, rax
0x18000979e  jz      short loc_1800097AD
0x1800097a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097a5  test    al, al
0x1800097a7  jnz     loc_1800098F2
0x1800097ad  lea     rsi, [rdi+28h]
0x1800097b1  mov     rcx, rsi; SRWLock
0x1800097b4  call    cs:__imp_AcquireSRWLockExclusive
0x1800097ba  xor     eax, eax
0x1800097bc  mov     word ptr [rsp+68h+var_48+6], ax
0x1800097c1  mov     dword ptr [rsp+68h+var_48], r14d
0x1800097c6  mov     word ptr [rsp+68h+var_48+4], bx
0x1800097cb  lea     rbx, [rdi+0E8h]
0x1800097d2  lea     edx, [rax+0Ch]; unsigned __int64
0x1800097d5  mov     rcx, rbx; this
0x1800097d8  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800097dd  test    al, al
0x1800097df  jz      short loc_18000983B
0x1800097e1  mov     rcx, [rbx+8]; void *
0x1800097e5  mov     rax, [rbx+10h]
0x1800097e9  sub     rax, rcx
0x1800097ec  cmp     rcx, [rbx+10h]
0x1800097f0  sbb     r8, r8
0x1800097f3  and     r8, rax; Size
0x1800097f6  test    rcx, rcx
0x1800097f9  jnz     short loc_180009809
0x1800097fb  call    cs:__imp__o__errno
0x180009801  mov     dword ptr [rax], 16h
0x180009807  jmp     short loc_180009831
0x180009809  cmp     r8, 0Ch
0x18000980d  jb      short loc_18000981E
0x18000980f  movsd   xmm0, [rsp+68h+var_48]
0x180009815  movsd   qword ptr [rcx], xmm0
0x180009819  mov     [rcx+8], ebp
0x18000981c  jmp     short loc_180009836
0x18000981e  xor     edx, edx; Val
0x180009820  call    memset_0
0x180009825  call    cs:__imp__o__errno
0x18000982b  mov     dword ptr [rax], 22h ; '"'
0x180009831  call    _invalid_parameter_noinfo
0x180009836  add     qword ptr [rbx+8], 0Ch
0x18000983b  cmp     byte ptr [rdi+40h], 0
0x18000983f  jnz     loc_1800098E3
0x180009845  cmp     qword ptr [rdi+38h], 0
0x18000984a  jnz     short loc_1800098B9
0x18000984c  call    cs:__imp_GetLastError
0x180009852  mov     r14d, eax
0x180009855  xor     r8d, r8d; pcbe
0x180009858  mov     rdx, rdi; pv
0x18000985b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009862  call    cs:__imp_CreateThreadpoolTimer
0x180009868  mov     r15, rax
0x18000986b  mov     rbp, [rdi+38h]
0x18000986f  test    rbp, rbp
0x180009872  jz      short loc_1800098AC
0x180009874  call    cs:__imp_GetLastError
0x18000987a  mov     ebx, eax
0x18000987c  xor     r9d, r9d; msWindowLength
0x18000987f  xor     r8d, r8d; msPeriod
0x180009882  xor     edx, edx; pftDueTime
0x180009884  mov     rcx, rbp; pti
0x180009887  call    cs:__imp_SetThreadpoolTimer
0x18000988d  mov     edx, 1; fCancelPendingCallbacks
0x180009892  mov     rcx, rbp; pti
0x180009895  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000989b  mov     rcx, rbp; pti
0x18000989e  call    cs:__imp_CloseThreadpoolTimer
0x1800098a4  mov     ecx, ebx; dwErrCode
0x1800098a6  call    cs:__imp_SetLastError
0x1800098ac  mov     [rdi+38h], r15
0x1800098b0  mov     ecx, r14d; dwErrCode
0x1800098b3  call    cs:__imp_SetLastError
0x1800098b9  mov     rcx, [rdi+38h]; pti
0x1800098bd  test    rcx, rcx
0x1800098c0  jz      short loc_1800098E3
0x1800098c2  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800098cb  mov     r9d, 4E2h; msWindowLength
0x1800098d1  xor     r8d, r8d; msPeriod
0x1800098d4  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800098d9  call    cs:__imp_SetThreadpoolTimer
0x1800098df  mov     byte ptr [rdi+40h], 1
0x1800098e3  test    rsi, rsi
0x1800098e6  jz      short loc_1800098F2
0x1800098e8  mov     rcx, rsi; SRWLock
0x1800098eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800098f1  nop
0x1800098f2  add     rsp, 38h
0x1800098f6  pop     r15
0x1800098f8  pop     r14
0x1800098fa  pop     rdi
0x1800098fb  pop     rsi
0x1800098fc  pop     rbp
0x1800098fd  pop     rbx
0x1800098fe  retn
```
