# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180013780`
- end: `0x18001391b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800154e0`

## callees

- `0x1800030ee`
- `0x18000316c`
- `0x180013780`
- `0x1800159cc`
- `0x18004f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013817`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013841`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013817`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180013841`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013907`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013907`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800137d0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800137d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013890`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800138c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800138cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800138c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800138cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800138ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800138ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800138b1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800138b1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001387e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001387e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800138a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800138f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800138a3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800138f5`

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
0x180013780  push    rbx
0x180013782  push    rbp
0x180013783  push    rsi
0x180013784  push    rdi
0x180013785  push    r14
0x180013787  push    r15
0x180013789  sub     rsp, 38h
0x18001378d  mov     ebp, r9d
0x180013790  movzx   ebx, r8w
0x180013794  mov     r14d, edx
0x180013797  mov     rdi, rcx
0x18001379a  cmp     byte ptr [rcx], 0
0x18001379d  jz      loc_18001390E
0x1800137a3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800137aa  jnz     loc_18001390E
0x1800137b0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800137b7  test    rax, rax
0x1800137ba  jz      short loc_1800137C9
0x1800137bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137c1  test    al, al
0x1800137c3  jnz     loc_18001390E
0x1800137c9  lea     rsi, [rdi+28h]
0x1800137cd  mov     rcx, rsi; SRWLock
0x1800137d0  call    cs:__imp_AcquireSRWLockExclusive
0x1800137d6  xor     eax, eax
0x1800137d8  mov     word ptr [rsp+68h+var_48+6], ax
0x1800137dd  mov     dword ptr [rsp+68h+var_48], r14d
0x1800137e2  mov     word ptr [rsp+68h+var_48+4], bx
0x1800137e7  lea     rbx, [rdi+0E8h]
0x1800137ee  lea     edx, [rax+0Ch]; unsigned __int64
0x1800137f1  mov     rcx, rbx; this
0x1800137f4  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800137f9  test    al, al
0x1800137fb  jz      short loc_180013857
0x1800137fd  mov     rcx, [rbx+8]; void *
0x180013801  mov     rax, [rbx+10h]
0x180013805  sub     rax, rcx
0x180013808  cmp     rcx, [rbx+10h]
0x18001380c  sbb     r8, r8
0x18001380f  and     r8, rax; Size
0x180013812  test    rcx, rcx
0x180013815  jnz     short loc_180013825
0x180013817  call    cs:__imp__o__errno
0x18001381d  mov     dword ptr [rax], 16h
0x180013823  jmp     short loc_18001384D
0x180013825  cmp     r8, 0Ch
0x180013829  jb      short loc_18001383A
0x18001382b  movsd   xmm0, [rsp+68h+var_48]
0x180013831  movsd   qword ptr [rcx], xmm0
0x180013835  mov     [rcx+8], ebp
0x180013838  jmp     short loc_180013852
0x18001383a  xor     edx, edx; Val
0x18001383c  call    memset_0
0x180013841  call    cs:__imp__o__errno
0x180013847  mov     dword ptr [rax], 22h ; '"'
0x18001384d  call    _invalid_parameter_noinfo
0x180013852  add     qword ptr [rbx+8], 0Ch
0x180013857  cmp     byte ptr [rdi+40h], 0
0x18001385b  jnz     loc_1800138FF
0x180013861  cmp     qword ptr [rdi+38h], 0
0x180013866  jnz     short loc_1800138D5
0x180013868  call    cs:__imp_GetLastError
0x18001386e  mov     r14d, eax
0x180013871  xor     r8d, r8d; pcbe
0x180013874  mov     rdx, rdi; pv
0x180013877  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001387e  call    cs:__imp_CreateThreadpoolTimer
0x180013884  mov     r15, rax
0x180013887  mov     rbp, [rdi+38h]
0x18001388b  test    rbp, rbp
0x18001388e  jz      short loc_1800138C8
0x180013890  call    cs:__imp_GetLastError
0x180013896  mov     ebx, eax
0x180013898  xor     r9d, r9d; msWindowLength
0x18001389b  xor     r8d, r8d; msPeriod
0x18001389e  xor     edx, edx; pftDueTime
0x1800138a0  mov     rcx, rbp; pti
0x1800138a3  call    cs:__imp_SetThreadpoolTimer
0x1800138a9  mov     edx, 1; fCancelPendingCallbacks
0x1800138ae  mov     rcx, rbp; pti
0x1800138b1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800138b7  mov     rcx, rbp; pti
0x1800138ba  call    cs:__imp_CloseThreadpoolTimer
0x1800138c0  mov     ecx, ebx; dwErrCode
0x1800138c2  call    cs:__imp_SetLastError
0x1800138c8  mov     [rdi+38h], r15
0x1800138cc  mov     ecx, r14d; dwErrCode
0x1800138cf  call    cs:__imp_SetLastError
0x1800138d5  mov     rcx, [rdi+38h]; pti
0x1800138d9  test    rcx, rcx
0x1800138dc  jz      short loc_1800138FF
0x1800138de  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800138e7  mov     r9d, 4E2h; msWindowLength
0x1800138ed  xor     r8d, r8d; msPeriod
0x1800138f0  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800138f5  call    cs:__imp_SetThreadpoolTimer
0x1800138fb  mov     byte ptr [rdi+40h], 1
0x1800138ff  test    rsi, rsi
0x180013902  jz      short loc_18001390E
0x180013904  mov     rcx, rsi; SRWLock
0x180013907  call    cs:__imp_ReleaseSRWLockExclusive
0x18001390d  nop
0x18001390e  add     rsp, 38h
0x180013912  pop     r15
0x180013914  pop     r14
0x180013916  pop     rdi
0x180013917  pop     rsi
0x180013918  pop     rbp
0x180013919  pop     rbx
0x18001391a  retn
```
