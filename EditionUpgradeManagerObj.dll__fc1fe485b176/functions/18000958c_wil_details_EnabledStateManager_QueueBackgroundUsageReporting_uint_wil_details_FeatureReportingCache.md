# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18000958c`
- end: `0x180009743`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `439`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009884`

## callees

- `0x180002652`
- `0x1800026b4`
- `0x18000877c`
- `0x18000958c`
- `0x180023010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000963d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009665`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000963d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009665`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009730`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009730`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800095d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800095d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000968b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000968b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800096d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800096d4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800096dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800096dd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800096a1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800096a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800096c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000971e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800096c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000971e`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rdx
  _DWORD *v7; // rcx
  size_t v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v15; // r15
  DWORD v16; // ebx
  struct _TP_TIMER *v17; // rcx
  struct _FILETIME pftDueTime; // [rsp+60h] [rbp+8h] BYREF

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
LABEL_24:
      if ( pv != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(pv + 1);
      return;
    }
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
    {
LABEL_17:
      if ( !LOBYTE(pv[3].Ptr) )
      {
        if ( !pv[2].Ptr )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          v15 = ThreadpoolTimer;
          if ( Ptr )
          {
            v16 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v16);
          }
          pv[2].Ptr = v15;
          SetLastError(LastError);
        }
        v17 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v17 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v17, &pftDueTime, 0, 0x124F8u);
          LOBYTE(pv[3].Ptr) = 1;
        }
      }
      goto LABEL_24;
    }
    v7 = pv[5].Ptr;
    v8 = ((char *)pv[6].Ptr - (char *)v7) & -(__int64)(v7 < pv[6].Ptr);
    if ( v7 )
    {
      if ( v8 >= 0x10 )
      {
        *v7 = a2;
        v7[1] = 0;
        *((_QWORD *)v7 + 1) = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(v7, 0, v8);
      *(_DWORD *)_o__errno(v10, v9, v11) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0, v6, v8) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x18000958c  push    rbx
0x18000958e  push    rbp
0x18000958f  push    rsi
0x180009590  push    rdi
0x180009591  push    r14
0x180009593  push    r15
0x180009595  sub     rsp, 28h
0x180009599  mov     eax, [rcx]
0x18000959b  mov     rbp, r8
0x18000959e  mov     r14d, edx
0x1800095a1  mov     rdi, rcx
0x1800095a4  test    eax, eax
0x1800095a6  jz      loc_180009736
0x1800095ac  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800095b3  jnz     loc_180009736
0x1800095b9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800095c0  test    rax, rax
0x1800095c3  jz      short loc_1800095D2
0x1800095c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ca  test    al, al
0x1800095cc  jnz     loc_180009736
0x1800095d2  lea     rsi, [rdi+8]
0x1800095d6  mov     rcx, rsi; SRWLock
0x1800095d9  call    cs:__imp_AcquireSRWLockExclusive
0x1800095df  mov     eax, [rdi]
0x1800095e1  test    eax, eax
0x1800095e3  jz      loc_180009728
0x1800095e9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800095f0  jnz     loc_180009728
0x1800095f6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800095fd  test    rax, rax
0x180009600  jz      short loc_18000960F
0x180009602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009607  test    al, al
0x180009609  jnz     loc_180009728
0x18000960f  xor     r15d, r15d
0x180009612  lea     rcx, [rdi+20h]; this
0x180009616  lea     edx, [r15+10h]; unsigned __int64
0x18000961a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000961f  test    al, al
0x180009621  jz      short loc_18000967B
0x180009623  mov     rcx, [rdi+28h]; void *
0x180009627  mov     rax, [rdi+30h]
0x18000962b  sub     rax, rcx
0x18000962e  cmp     rcx, [rdi+30h]
0x180009632  sbb     r8, r8
0x180009635  and     r8, rax; Size
0x180009638  test    rcx, rcx
0x18000963b  jnz     short loc_18000964B
0x18000963d  call    cs:__imp__o__errno
0x180009643  mov     dword ptr [rax], 16h
0x180009649  jmp     short loc_180009671
0x18000964b  cmp     r8, 10h
0x18000964f  jb      short loc_18000965E
0x180009651  mov     [rcx], r14d
0x180009654  mov     [rcx+4], r15d
0x180009658  mov     [rcx+8], rbp
0x18000965c  jmp     short loc_180009676
0x18000965e  xor     edx, edx; Val
0x180009660  call    memset_0
0x180009665  call    cs:__imp__o__errno
0x18000966b  mov     dword ptr [rax], 22h ; '"'
0x180009671  call    _invalid_parameter_noinfo
0x180009676  add     qword ptr [rdi+28h], 10h
0x18000967b  cmp     [rdi+18h], r15b
0x18000967f  jnz     loc_180009728
0x180009685  cmp     [rdi+10h], r15
0x180009689  jnz     short loc_1800096F8
0x18000968b  call    cs:__imp_GetLastError
0x180009691  xor     r8d, r8d; pcbe
0x180009694  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000969b  mov     rdx, rdi; pv
0x18000969e  mov     r14d, eax
0x1800096a1  call    cs:__imp_CreateThreadpoolTimer
0x1800096a7  mov     rbp, [rdi+10h]
0x1800096ab  mov     r15, rax
0x1800096ae  test    rbp, rbp
0x1800096b1  jz      short loc_1800096EB
0x1800096b3  call    cs:__imp_GetLastError
0x1800096b9  xor     r9d, r9d; msWindowLength
0x1800096bc  xor     r8d, r8d; msPeriod
0x1800096bf  xor     edx, edx; pftDueTime
0x1800096c1  mov     rcx, rbp; pti
0x1800096c4  mov     ebx, eax
0x1800096c6  call    cs:__imp_SetThreadpoolTimer
0x1800096cc  mov     edx, 1; fCancelPendingCallbacks
0x1800096d1  mov     rcx, rbp; pti
0x1800096d4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800096da  mov     rcx, rbp; pti
0x1800096dd  call    cs:__imp_CloseThreadpoolTimer
0x1800096e3  mov     ecx, ebx; dwErrCode
0x1800096e5  call    cs:__imp_SetLastError
0x1800096eb  mov     ecx, r14d; dwErrCode
0x1800096ee  mov     [rdi+10h], r15
0x1800096f2  call    cs:__imp_SetLastError
0x1800096f8  mov     rcx, [rdi+10h]; pti
0x1800096fc  test    rcx, rcx
0x1800096ff  jz      short loc_180009728
0x180009701  mov     rax, 0FFFFFFFF4D2FA200h
0x18000970b  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180009710  mov     r9d, 124F8h; msWindowLength
0x180009716  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x18000971b  xor     r8d, r8d; msPeriod
0x18000971e  call    cs:__imp_SetThreadpoolTimer
0x180009724  mov     byte ptr [rdi+18h], 1
0x180009728  test    rsi, rsi
0x18000972b  jz      short loc_180009736
0x18000972d  mov     rcx, rsi; SRWLock
0x180009730  call    cs:__imp_ReleaseSRWLockExclusive
0x180009736  add     rsp, 28h
0x18000973a  pop     r15
0x18000973c  pop     r14
0x18000973e  pop     rdi
0x18000973f  pop     rsi
0x180009740  pop     rbp
0x180009741  pop     rbx
0x180009742  retn
```
