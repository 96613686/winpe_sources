# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1400615fc`
- end: `0x140061798`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `412`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140062f00`

## callees

- `0x1400050e0`
- `0x1400615fc`
- `0x1400632e4`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1400616fb`
- `KERNEL32!CreateThreadpoolTimer` at `0x1400616fb`
- `KERNEL32!SetThreadpoolTimer` at `0x140061720`
- `KERNEL32!SetThreadpoolTimer` at `0x140061772`
- `KERNEL32!SetThreadpoolTimer` at `0x140061720`
- `KERNEL32!SetThreadpoolTimer` at `0x140061772`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14006164c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14006164c`
- `KERNEL32!CloseThreadpoolTimer` at `0x140061737`
- `KERNEL32!CloseThreadpoolTimer` at `0x140061737`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140061784`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140061784`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14006172e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14006172e`
- `KERNEL32!GetLastError` at `0x1400616e5`
- `KERNEL32!GetLastError` at `0x14006170d`
- `KERNEL32!GetLastError` at `0x1400616e5`
- `KERNEL32!GetLastError` at `0x14006170d`
- `KERNEL32!SetLastError` at `0x14006173f`
- `KERNEL32!SetLastError` at `0x14006174c`
- `KERNEL32!SetLastError` at `0x14006173f`
- `KERNEL32!SetLastError` at `0x14006174c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140061693`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400616bd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140061693`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400616bd`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1400616c9`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo` at `0x1400616c9`

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
    _invalid_parameter_noinfo();
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
0x1400615fc  push    rbx
0x1400615fe  push    rbp
0x1400615ff  push    rsi
0x140061600  push    rdi
0x140061601  push    r14
0x140061603  push    r15
0x140061605  sub     rsp, 38h
0x140061609  mov     ebp, r9d
0x14006160c  movzx   ebx, r8w
0x140061610  mov     r14d, edx
0x140061613  mov     rdi, rcx
0x140061616  cmp     byte ptr [rcx], 0
0x140061619  jz      loc_14006178B
0x14006161f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140061626  jnz     loc_14006178B
0x14006162c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140061633  test    rax, rax
0x140061636  jz      short loc_140061645
0x140061638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006163d  test    al, al
0x14006163f  jnz     loc_14006178B
0x140061645  lea     rsi, [rdi+28h]
0x140061649  mov     rcx, rsi; SRWLock
0x14006164c  call    cs:__imp_AcquireSRWLockExclusive
0x140061652  xor     eax, eax
0x140061654  mov     word ptr [rsp+68h+var_48+6], ax
0x140061659  mov     dword ptr [rsp+68h+var_48], r14d
0x14006165e  mov     word ptr [rsp+68h+var_48+4], bx
0x140061663  lea     rbx, [rdi+0E8h]
0x14006166a  lea     edx, [rax+0Ch]; unsigned __int64
0x14006166d  mov     rcx, rbx; this
0x140061670  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140061675  test    al, al
0x140061677  jz      short loc_1400616D4
0x140061679  mov     rcx, [rbx+8]; void *
0x14006167d  mov     rax, [rbx+10h]
0x140061681  sub     rax, rcx
0x140061684  cmp     rcx, [rbx+10h]
0x140061688  sbb     r8, r8
0x14006168b  and     r8, rax; Size
0x14006168e  test    rcx, rcx
0x140061691  jnz     short loc_1400616A1
0x140061693  call    cs:__imp__o__errno
0x140061699  mov     dword ptr [rax], 16h
0x14006169f  jmp     short loc_1400616C9
0x1400616a1  cmp     r8, 0Ch
0x1400616a5  jb      short loc_1400616B6
0x1400616a7  movsd   xmm0, [rsp+68h+var_48]
0x1400616ad  movsd   qword ptr [rcx], xmm0
0x1400616b1  mov     [rcx+8], ebp
0x1400616b4  jmp     short loc_1400616CF
0x1400616b6  xor     edx, edx; Val
0x1400616b8  call    memset_0
0x1400616bd  call    cs:__imp__o__errno
0x1400616c3  mov     dword ptr [rax], 22h ; '"'
0x1400616c9  call    cs:__imp__invalid_parameter_noinfo
0x1400616cf  add     qword ptr [rbx+8], 0Ch
0x1400616d4  cmp     byte ptr [rdi+40h], 0
0x1400616d8  jnz     loc_14006177C
0x1400616de  cmp     qword ptr [rdi+38h], 0
0x1400616e3  jnz     short loc_140061752
0x1400616e5  call    cs:__imp_GetLastError
0x1400616eb  mov     r14d, eax
0x1400616ee  xor     r8d, r8d; pcbe
0x1400616f1  mov     rdx, rdi; pv
0x1400616f4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400616fb  call    cs:__imp_CreateThreadpoolTimer
0x140061701  mov     r15, rax
0x140061704  mov     rbp, [rdi+38h]
0x140061708  test    rbp, rbp
0x14006170b  jz      short loc_140061745
0x14006170d  call    cs:__imp_GetLastError
0x140061713  mov     ebx, eax
0x140061715  xor     r9d, r9d; msWindowLength
0x140061718  xor     r8d, r8d; msPeriod
0x14006171b  xor     edx, edx; pftDueTime
0x14006171d  mov     rcx, rbp; pti
0x140061720  call    cs:__imp_SetThreadpoolTimer
0x140061726  mov     edx, 1; fCancelPendingCallbacks
0x14006172b  mov     rcx, rbp; pti
0x14006172e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140061734  mov     rcx, rbp; pti
0x140061737  call    cs:__imp_CloseThreadpoolTimer
0x14006173d  mov     ecx, ebx; dwErrCode
0x14006173f  call    cs:__imp_SetLastError
0x140061745  mov     [rdi+38h], r15
0x140061749  mov     ecx, r14d; dwErrCode
0x14006174c  call    cs:__imp_SetLastError
0x140061752  mov     rcx, [rdi+38h]; pti
0x140061756  test    rcx, rcx
0x140061759  jz      short loc_14006177C
0x14006175b  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140061764  mov     r9d, 4E2h; msWindowLength
0x14006176a  xor     r8d, r8d; msPeriod
0x14006176d  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140061772  call    cs:__imp_SetThreadpoolTimer
0x140061778  mov     byte ptr [rdi+40h], 1
0x14006177c  test    rsi, rsi
0x14006177f  jz      short loc_14006178B
0x140061781  mov     rcx, rsi; SRWLock
0x140061784  call    cs:__imp_ReleaseSRWLockExclusive
0x14006178a  nop
0x14006178b  add     rsp, 38h
0x14006178f  pop     r15
0x140061791  pop     r14
0x140061793  pop     rdi
0x140061794  pop     rsi
0x140061795  pop     rbp
0x140061796  pop     rbx
0x140061797  retn
```
