# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180009198`
- end: `0x180009333`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000bc70`

## callees

- `0x180003f02`
- `0x180003fb8`
- `0x180009198`
- `0x18000c38c`
- `0x180108010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000922f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009259`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000922f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009259`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800091e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800091e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000931f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000931f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800092da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800092e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800092da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800092e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800092d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800092d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800092bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000930d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800092bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000930d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009296`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180009296`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800092c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800092c9`

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
      ThreadpoolTimer = CreateThreadpoolTimer(
                          `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
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
0x180009198  push    rbx
0x18000919a  push    rbp
0x18000919b  push    rsi
0x18000919c  push    rdi
0x18000919d  push    r14
0x18000919f  push    r15
0x1800091a1  sub     rsp, 38h
0x1800091a5  mov     ebp, r9d
0x1800091a8  movzx   ebx, r8w
0x1800091ac  mov     r14d, edx
0x1800091af  mov     rdi, rcx
0x1800091b2  cmp     byte ptr [rcx], 0
0x1800091b5  jz      loc_180009326
0x1800091bb  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800091c2  jnz     loc_180009326
0x1800091c8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800091cf  test    rax, rax
0x1800091d2  jz      short loc_1800091E1
0x1800091d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091d9  test    al, al
0x1800091db  jnz     loc_180009326
0x1800091e1  lea     rsi, [rdi+28h]
0x1800091e5  mov     rcx, rsi; SRWLock
0x1800091e8  call    cs:__imp_AcquireSRWLockExclusive
0x1800091ee  xor     eax, eax
0x1800091f0  mov     word ptr [rsp+68h+var_48+6], ax
0x1800091f5  mov     dword ptr [rsp+68h+var_48], r14d
0x1800091fa  mov     word ptr [rsp+68h+var_48+4], bx
0x1800091ff  lea     rbx, [rdi+0E8h]
0x180009206  lea     edx, [rax+0Ch]; unsigned __int64
0x180009209  mov     rcx, rbx; this
0x18000920c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009211  test    al, al
0x180009213  jz      short loc_18000926F
0x180009215  mov     rcx, [rbx+8]; void *
0x180009219  mov     rax, [rbx+10h]
0x18000921d  sub     rax, rcx
0x180009220  cmp     rcx, [rbx+10h]
0x180009224  sbb     r8, r8
0x180009227  and     r8, rax; Size
0x18000922a  test    rcx, rcx
0x18000922d  jnz     short loc_18000923D
0x18000922f  call    cs:__imp__o__errno
0x180009235  mov     dword ptr [rax], 16h
0x18000923b  jmp     short loc_180009265
0x18000923d  cmp     r8, 0Ch
0x180009241  jb      short loc_180009252
0x180009243  movsd   xmm0, [rsp+68h+var_48]
0x180009249  movsd   qword ptr [rcx], xmm0
0x18000924d  mov     [rcx+8], ebp
0x180009250  jmp     short loc_18000926A
0x180009252  xor     edx, edx; Val
0x180009254  call    memset_0
0x180009259  call    cs:__imp__o__errno
0x18000925f  mov     dword ptr [rax], 22h ; '"'
0x180009265  call    _invalid_parameter_noinfo
0x18000926a  add     qword ptr [rbx+8], 0Ch
0x18000926f  cmp     byte ptr [rdi+40h], 0
0x180009273  jnz     loc_180009317
0x180009279  cmp     qword ptr [rdi+38h], 0
0x18000927e  jnz     short loc_1800092ED
0x180009280  call    cs:__imp_GetLastError
0x180009286  mov     r14d, eax
0x180009289  xor     r8d, r8d; pcbe
0x18000928c  mov     rdx, rdi; pv
0x18000928f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180009296  call    cs:__imp_CreateThreadpoolTimer
0x18000929c  mov     r15, rax
0x18000929f  mov     rbp, [rdi+38h]
0x1800092a3  test    rbp, rbp
0x1800092a6  jz      short loc_1800092E0
0x1800092a8  call    cs:__imp_GetLastError
0x1800092ae  mov     ebx, eax
0x1800092b0  xor     r9d, r9d; msWindowLength
0x1800092b3  xor     r8d, r8d; msPeriod
0x1800092b6  xor     edx, edx; pftDueTime
0x1800092b8  mov     rcx, rbp; pti
0x1800092bb  call    cs:__imp_SetThreadpoolTimer
0x1800092c1  mov     edx, 1; fCancelPendingCallbacks
0x1800092c6  mov     rcx, rbp; pti
0x1800092c9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800092cf  mov     rcx, rbp; pti
0x1800092d2  call    cs:__imp_CloseThreadpoolTimer
0x1800092d8  mov     ecx, ebx; dwErrCode
0x1800092da  call    cs:__imp_SetLastError
0x1800092e0  mov     [rdi+38h], r15
0x1800092e4  mov     ecx, r14d; dwErrCode
0x1800092e7  call    cs:__imp_SetLastError
0x1800092ed  mov     rcx, [rdi+38h]; pti
0x1800092f1  test    rcx, rcx
0x1800092f4  jz      short loc_180009317
0x1800092f6  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800092ff  mov     r9d, 4E2h; msWindowLength
0x180009305  xor     r8d, r8d; msPeriod
0x180009308  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000930d  call    cs:__imp_SetThreadpoolTimer
0x180009313  mov     byte ptr [rdi+40h], 1
0x180009317  test    rsi, rsi
0x18000931a  jz      short loc_180009326
0x18000931c  mov     rcx, rsi; SRWLock
0x18000931f  call    cs:__imp_ReleaseSRWLockExclusive
0x180009325  nop
0x180009326  add     rsp, 38h
0x18000932a  pop     r15
0x18000932c  pop     r14
0x18000932e  pop     rdi
0x18000932f  pop     rsi
0x180009330  pop     rbp
0x180009331  pop     rbx
0x180009332  retn
```
