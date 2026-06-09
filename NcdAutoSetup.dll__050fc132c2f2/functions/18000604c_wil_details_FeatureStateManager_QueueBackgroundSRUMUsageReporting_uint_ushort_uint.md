# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000604c`
- end: `0x1800061d4`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `392`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, __int16, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180008780`

## callees

- `0x18000604c`
- `0x18000a0e4`
- `0x180013840`
- `0x180014010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800060fa`
- `msvcrt!memcpy_s` at `0x1800060fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000613d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000613d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000616f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000617c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000616f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000617c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800061b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800061b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800060aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800060aa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006167`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006167`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006150`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800061a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006150`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800061a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000612b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000612b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000615e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000615e`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        __int16 a3,
        int a4)
{
  DWORD LastError; // r14d
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *Ptr; // rbp
  PTP_TIMER v11; // r15
  DWORD v12; // ebx
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-58h] BYREF
  int Source; // [rsp+28h] [rbp-50h] BYREF
  __int16 v16; // [rsp+2Ch] [rbp-4Ch]
  __int16 v17; // [rsp+2Eh] [rbp-4Ah]
  int v18; // [rsp+30h] [rbp-48h]

  if ( LOBYTE(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 5);
    Source = a2;
    v16 = a3;
    v17 = 0;
    v18 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[29], 0xCu) )
    {
      memcpy_s(
        pv[30].Ptr,
        ((char *)pv[31].Ptr - (char *)pv[30].Ptr) & -(__int64)(pv[30].Ptr < pv[31].Ptr),
        &Source,
        0xCu);
      pv[30].Ptr = (char *)pv[30].Ptr + 12;
    }
    if ( !LOBYTE(pv[8].Ptr) )
    {
      if ( !pv[7].Ptr )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        Ptr = (struct _TP_TIMER *)pv[7].Ptr;
        v11 = ThreadpoolTimer;
        if ( Ptr )
        {
          v12 = GetLastError();
          SetThreadpoolTimer(Ptr, 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(Ptr, 1);
          CloseThreadpoolTimer(Ptr);
          SetLastError(v12);
        }
        pv[7].Ptr = v11;
        SetLastError(LastError);
      }
      v13 = (struct _TP_TIMER *)pv[7].Ptr;
      if ( v13 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v13, &pftDueTime, 0, 0x4E2u);
        LOBYTE(pv[8].Ptr) = 1;
      }
    }
    if ( pv != (RTL_SRWLOCK *)-40LL )
      ReleaseSRWLockExclusive(pv + 5);
  }
}

```

## disassembly

```asm
0x18000604c  push    rbx
0x18000604e  push    rbp
0x18000604f  push    rsi
0x180006050  push    rdi
0x180006051  push    r14
0x180006053  push    r15
0x180006055  sub     rsp, 48h
0x180006059  mov     rax, cs:__security_cookie
0x180006060  xor     rax, rsp
0x180006063  mov     [rsp+78h+var_40], rax
0x180006068  cmp     byte ptr [rcx], 0
0x18000606b  mov     r14d, r9d
0x18000606e  movzx   ebp, r8w
0x180006072  mov     ebx, edx
0x180006074  mov     rdi, rcx
0x180006077  jz      loc_1800061BA
0x18000607d  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006084  jnz     loc_1800061BA
0x18000608a  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006091  test    rax, rax
0x180006094  jz      short loc_1800060A3
0x180006096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000609b  test    al, al
0x18000609d  jnz     loc_1800061BA
0x1800060a3  lea     rsi, [rdi+28h]
0x1800060a7  mov     rcx, rsi; SRWLock
0x1800060aa  call    cs:__imp_AcquireSRWLockExclusive
0x1800060b0  xor     eax, eax
0x1800060b2  mov     [rsp+78h+Source], ebx
0x1800060b6  mov     [rsp+78h+var_4C], bp
0x1800060bb  lea     rbx, [rdi+0E8h]
0x1800060c2  mov     rcx, rbx; this
0x1800060c5  mov     [rsp+78h+var_4A], ax
0x1800060ca  mov     [rsp+78h+var_48], r14d
0x1800060cf  lea     ebp, [rax+0Ch]
0x1800060d2  mov     edx, ebp; unsigned __int64
0x1800060d4  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800060d9  test    al, al
0x1800060db  jz      short loc_180006104
0x1800060dd  mov     rcx, [rbx+8]; Destination
0x1800060e1  lea     r8, [rsp+78h+Source]; Source
0x1800060e6  mov     rax, [rbx+10h]
0x1800060ea  mov     r9d, ebp; SourceSize
0x1800060ed  sub     rax, rcx
0x1800060f0  cmp     rcx, [rbx+10h]
0x1800060f4  sbb     rdx, rdx
0x1800060f7  and     rdx, rax; DestinationSize
0x1800060fa  call    cs:__imp_memcpy_s
0x180006100  add     [rbx+8], rbp
0x180006104  cmp     byte ptr [rdi+40h], 0
0x180006108  jnz     loc_1800061AC
0x18000610e  cmp     qword ptr [rdi+38h], 0
0x180006113  jnz     short loc_180006182
0x180006115  call    cs:__imp_GetLastError
0x18000611b  xor     r8d, r8d; pcbe
0x18000611e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006125  mov     rdx, rdi; pv
0x180006128  mov     r14d, eax
0x18000612b  call    cs:__imp_CreateThreadpoolTimer
0x180006131  mov     rbp, [rdi+38h]
0x180006135  mov     r15, rax
0x180006138  test    rbp, rbp
0x18000613b  jz      short loc_180006175
0x18000613d  call    cs:__imp_GetLastError
0x180006143  xor     r9d, r9d; msWindowLength
0x180006146  xor     r8d, r8d; msPeriod
0x180006149  xor     edx, edx; pftDueTime
0x18000614b  mov     rcx, rbp; pti
0x18000614e  mov     ebx, eax
0x180006150  call    cs:__imp_SetThreadpoolTimer
0x180006156  mov     edx, 1; fCancelPendingCallbacks
0x18000615b  mov     rcx, rbp; pti
0x18000615e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006164  mov     rcx, rbp; pti
0x180006167  call    cs:__imp_CloseThreadpoolTimer
0x18000616d  mov     ecx, ebx; dwErrCode
0x18000616f  call    cs:__imp_SetLastError
0x180006175  mov     ecx, r14d; dwErrCode
0x180006178  mov     [rdi+38h], r15
0x18000617c  call    cs:__imp_SetLastError
0x180006182  mov     rcx, [rdi+38h]; pti
0x180006186  test    rcx, rcx
0x180006189  jz      short loc_1800061AC
0x18000618b  mov     r9d, 4E2h; msWindowLength
0x180006191  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000619a  xor     r8d, r8d; msPeriod
0x18000619d  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x1800061a2  call    cs:__imp_SetThreadpoolTimer
0x1800061a8  mov     byte ptr [rdi+40h], 1
0x1800061ac  test    rsi, rsi
0x1800061af  jz      short loc_1800061BA
0x1800061b1  mov     rcx, rsi; SRWLock
0x1800061b4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800061ba  mov     rcx, [rsp+78h+var_40]
0x1800061bf  xor     rcx, rsp; StackCookie
0x1800061c2  call    __security_check_cookie
0x1800061c7  add     rsp, 48h
0x1800061cb  pop     r15
0x1800061cd  pop     r14
0x1800061cf  pop     rdi
0x1800061d0  pop     rsi
0x1800061d1  pop     rbp
0x1800061d2  pop     rbx
0x1800061d3  retn
```
