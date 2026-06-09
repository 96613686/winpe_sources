# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1400146e0`
- end: `0x14001487b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140015eb0`

## callees

- `0x14000903a`
- `0x1400090ec`
- `0x1400146e0`
- `0x1400162b4`
- `0x140018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014777`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400147a1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014777`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400147a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014730`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014730`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014867`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014867`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014822`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001482f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014822`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001482f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147f0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140014811`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140014811`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400147de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400147de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014803`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014855`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014803`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140014855`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001481a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001481a`

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
0x1400146e0  push    rbx
0x1400146e2  push    rbp
0x1400146e3  push    rsi
0x1400146e4  push    rdi
0x1400146e5  push    r14
0x1400146e7  push    r15
0x1400146e9  sub     rsp, 38h
0x1400146ed  mov     ebp, r9d
0x1400146f0  movzx   ebx, r8w
0x1400146f4  mov     r14d, edx
0x1400146f7  mov     rdi, rcx
0x1400146fa  cmp     byte ptr [rcx], 0
0x1400146fd  jz      loc_14001486E
0x140014703  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14001470a  jnz     loc_14001486E
0x140014710  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140014717  test    rax, rax
0x14001471a  jz      short loc_140014729
0x14001471c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014721  test    al, al
0x140014723  jnz     loc_14001486E
0x140014729  lea     rsi, [rdi+28h]
0x14001472d  mov     rcx, rsi; SRWLock
0x140014730  call    cs:__imp_AcquireSRWLockExclusive
0x140014736  xor     eax, eax
0x140014738  mov     word ptr [rsp+68h+var_48+6], ax
0x14001473d  mov     dword ptr [rsp+68h+var_48], r14d
0x140014742  mov     word ptr [rsp+68h+var_48+4], bx
0x140014747  lea     rbx, [rdi+0E8h]
0x14001474e  lea     edx, [rax+0Ch]; unsigned __int64
0x140014751  mov     rcx, rbx; this
0x140014754  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140014759  test    al, al
0x14001475b  jz      short loc_1400147B7
0x14001475d  mov     rcx, [rbx+8]; void *
0x140014761  mov     rax, [rbx+10h]
0x140014765  sub     rax, rcx
0x140014768  cmp     rcx, [rbx+10h]
0x14001476c  sbb     r8, r8
0x14001476f  and     r8, rax; Size
0x140014772  test    rcx, rcx
0x140014775  jnz     short loc_140014785
0x140014777  call    cs:__imp__o__errno
0x14001477d  mov     dword ptr [rax], 16h
0x140014783  jmp     short loc_1400147AD
0x140014785  cmp     r8, 0Ch
0x140014789  jb      short loc_14001479A
0x14001478b  movsd   xmm0, [rsp+68h+var_48]
0x140014791  movsd   qword ptr [rcx], xmm0
0x140014795  mov     [rcx+8], ebp
0x140014798  jmp     short loc_1400147B2
0x14001479a  xor     edx, edx; Val
0x14001479c  call    memset_0
0x1400147a1  call    cs:__imp__o__errno
0x1400147a7  mov     dword ptr [rax], 22h ; '"'
0x1400147ad  call    _invalid_parameter_noinfo
0x1400147b2  add     qword ptr [rbx+8], 0Ch
0x1400147b7  cmp     byte ptr [rdi+40h], 0
0x1400147bb  jnz     loc_14001485F
0x1400147c1  cmp     qword ptr [rdi+38h], 0
0x1400147c6  jnz     short loc_140014835
0x1400147c8  call    cs:__imp_GetLastError
0x1400147ce  mov     r14d, eax
0x1400147d1  xor     r8d, r8d; pcbe
0x1400147d4  mov     rdx, rdi; pv
0x1400147d7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400147de  call    cs:__imp_CreateThreadpoolTimer
0x1400147e4  mov     r15, rax
0x1400147e7  mov     rbp, [rdi+38h]
0x1400147eb  test    rbp, rbp
0x1400147ee  jz      short loc_140014828
0x1400147f0  call    cs:__imp_GetLastError
0x1400147f6  mov     ebx, eax
0x1400147f8  xor     r9d, r9d; msWindowLength
0x1400147fb  xor     r8d, r8d; msPeriod
0x1400147fe  xor     edx, edx; pftDueTime
0x140014800  mov     rcx, rbp; pti
0x140014803  call    cs:__imp_SetThreadpoolTimer
0x140014809  mov     edx, 1; fCancelPendingCallbacks
0x14001480e  mov     rcx, rbp; pti
0x140014811  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140014817  mov     rcx, rbp; pti
0x14001481a  call    cs:__imp_CloseThreadpoolTimer
0x140014820  mov     ecx, ebx; dwErrCode
0x140014822  call    cs:__imp_SetLastError
0x140014828  mov     [rdi+38h], r15
0x14001482c  mov     ecx, r14d; dwErrCode
0x14001482f  call    cs:__imp_SetLastError
0x140014835  mov     rcx, [rdi+38h]; pti
0x140014839  test    rcx, rcx
0x14001483c  jz      short loc_14001485F
0x14001483e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140014847  mov     r9d, 4E2h; msWindowLength
0x14001484d  xor     r8d, r8d; msPeriod
0x140014850  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140014855  call    cs:__imp_SetThreadpoolTimer
0x14001485b  mov     byte ptr [rdi+40h], 1
0x14001485f  test    rsi, rsi
0x140014862  jz      short loc_14001486E
0x140014864  mov     rcx, rsi; SRWLock
0x140014867  call    cs:__imp_ReleaseSRWLockExclusive
0x14001486d  nop
0x14001486e  add     rsp, 38h
0x140014872  pop     r15
0x140014874  pop     r14
0x140014876  pop     rdi
0x140014877  pop     rsi
0x140014878  pop     rbp
0x140014879  pop     rbx
0x14001487a  retn
```
