# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180011c98`
- end: `0x180011e33`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180013500`

## callees

- `0x180006e3e`
- `0x180006ed4`
- `0x180011c98`
- `0x180013a84`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011d2f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011d59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011d2f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011d59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011dda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011de7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011dda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011da8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011da8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011ce8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011ce8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011e1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011e1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011dd2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011dd2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011dc9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011dc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011dbb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011e0d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011dbb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011e0d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011d96`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011d96`

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
0x180011c98  push    rbx
0x180011c9a  push    rbp
0x180011c9b  push    rsi
0x180011c9c  push    rdi
0x180011c9d  push    r14
0x180011c9f  push    r15
0x180011ca1  sub     rsp, 38h
0x180011ca5  mov     ebp, r9d
0x180011ca8  movzx   ebx, r8w
0x180011cac  mov     r14d, edx
0x180011caf  mov     rdi, rcx
0x180011cb2  cmp     byte ptr [rcx], 0
0x180011cb5  jz      loc_180011E26
0x180011cbb  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180011cc2  jnz     loc_180011E26
0x180011cc8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180011ccf  test    rax, rax
0x180011cd2  jz      short loc_180011CE1
0x180011cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cd9  test    al, al
0x180011cdb  jnz     loc_180011E26
0x180011ce1  lea     rsi, [rdi+28h]
0x180011ce5  mov     rcx, rsi; SRWLock
0x180011ce8  call    cs:__imp_AcquireSRWLockExclusive
0x180011cee  xor     eax, eax
0x180011cf0  mov     word ptr [rsp+68h+var_48+6], ax
0x180011cf5  mov     dword ptr [rsp+68h+var_48], r14d
0x180011cfa  mov     word ptr [rsp+68h+var_48+4], bx
0x180011cff  lea     rbx, [rdi+0E8h]
0x180011d06  lea     edx, [rax+0Ch]; unsigned __int64
0x180011d09  mov     rcx, rbx; this
0x180011d0c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180011d11  test    al, al
0x180011d13  jz      short loc_180011D6F
0x180011d15  mov     rcx, [rbx+8]; void *
0x180011d19  mov     rax, [rbx+10h]
0x180011d1d  sub     rax, rcx
0x180011d20  cmp     rcx, [rbx+10h]
0x180011d24  sbb     r8, r8
0x180011d27  and     r8, rax; Size
0x180011d2a  test    rcx, rcx
0x180011d2d  jnz     short loc_180011D3D
0x180011d2f  call    cs:__imp__o__errno
0x180011d35  mov     dword ptr [rax], 16h
0x180011d3b  jmp     short loc_180011D65
0x180011d3d  cmp     r8, 0Ch
0x180011d41  jb      short loc_180011D52
0x180011d43  movsd   xmm0, [rsp+68h+var_48]
0x180011d49  movsd   qword ptr [rcx], xmm0
0x180011d4d  mov     [rcx+8], ebp
0x180011d50  jmp     short loc_180011D6A
0x180011d52  xor     edx, edx; Val
0x180011d54  call    memset_0
0x180011d59  call    cs:__imp__o__errno
0x180011d5f  mov     dword ptr [rax], 22h ; '"'
0x180011d65  call    _invalid_parameter_noinfo
0x180011d6a  add     qword ptr [rbx+8], 0Ch
0x180011d6f  cmp     byte ptr [rdi+40h], 0
0x180011d73  jnz     loc_180011E17
0x180011d79  cmp     qword ptr [rdi+38h], 0
0x180011d7e  jnz     short loc_180011DED
0x180011d80  call    cs:__imp_GetLastError
0x180011d86  mov     r14d, eax
0x180011d89  xor     r8d, r8d; pcbe
0x180011d8c  mov     rdx, rdi; pv
0x180011d8f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180011d96  call    cs:__imp_CreateThreadpoolTimer
0x180011d9c  mov     r15, rax
0x180011d9f  mov     rbp, [rdi+38h]
0x180011da3  test    rbp, rbp
0x180011da6  jz      short loc_180011DE0
0x180011da8  call    cs:__imp_GetLastError
0x180011dae  mov     ebx, eax
0x180011db0  xor     r9d, r9d; msWindowLength
0x180011db3  xor     r8d, r8d; msPeriod
0x180011db6  xor     edx, edx; pftDueTime
0x180011db8  mov     rcx, rbp; pti
0x180011dbb  call    cs:__imp_SetThreadpoolTimer
0x180011dc1  mov     edx, 1; fCancelPendingCallbacks
0x180011dc6  mov     rcx, rbp; pti
0x180011dc9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011dcf  mov     rcx, rbp; pti
0x180011dd2  call    cs:__imp_CloseThreadpoolTimer
0x180011dd8  mov     ecx, ebx; dwErrCode
0x180011dda  call    cs:__imp_SetLastError
0x180011de0  mov     [rdi+38h], r15
0x180011de4  mov     ecx, r14d; dwErrCode
0x180011de7  call    cs:__imp_SetLastError
0x180011ded  mov     rcx, [rdi+38h]; pti
0x180011df1  test    rcx, rcx
0x180011df4  jz      short loc_180011E17
0x180011df6  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180011dff  mov     r9d, 4E2h; msWindowLength
0x180011e05  xor     r8d, r8d; msPeriod
0x180011e08  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180011e0d  call    cs:__imp_SetThreadpoolTimer
0x180011e13  mov     byte ptr [rdi+40h], 1
0x180011e17  test    rsi, rsi
0x180011e1a  jz      short loc_180011E26
0x180011e1c  mov     rcx, rsi; SRWLock
0x180011e1f  call    cs:__imp_ReleaseSRWLockExclusive
0x180011e25  nop
0x180011e26  add     rsp, 38h
0x180011e2a  pop     r15
0x180011e2c  pop     r14
0x180011e2e  pop     rdi
0x180011e2f  pop     rsi
0x180011e30  pop     rbp
0x180011e31  pop     rbx
0x180011e32  retn
```
