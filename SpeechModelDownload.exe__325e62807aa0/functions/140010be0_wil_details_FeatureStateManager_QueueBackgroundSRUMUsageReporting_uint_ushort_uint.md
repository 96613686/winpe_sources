# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x140010be0`
- end: `0x140010d7b`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `411`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140012d90`

## callees

- `0x140003026`
- `0x1400030dc`
- `0x140010be0`
- `0x140013290`
- `0x14001d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010c77`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010ca1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010c77`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010ca1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010d67`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010d67`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010c30`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010cc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010cc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010cf0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010d22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010d2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010d22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010d2f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140010cde`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140010cde`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010d03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010d55`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010d03`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010d55`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140010d1a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140010d1a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140010d11`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140010d11`

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
0x140010be0  push    rbx
0x140010be2  push    rbp
0x140010be3  push    rsi
0x140010be4  push    rdi
0x140010be5  push    r14
0x140010be7  push    r15
0x140010be9  sub     rsp, 38h
0x140010bed  mov     ebp, r9d
0x140010bf0  movzx   ebx, r8w
0x140010bf4  mov     r14d, edx
0x140010bf7  mov     rdi, rcx
0x140010bfa  cmp     byte ptr [rcx], 0
0x140010bfd  jz      loc_140010D6E
0x140010c03  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140010c0a  jnz     loc_140010D6E
0x140010c10  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140010c17  test    rax, rax
0x140010c1a  jz      short loc_140010C29
0x140010c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c21  test    al, al
0x140010c23  jnz     loc_140010D6E
0x140010c29  lea     rsi, [rdi+28h]
0x140010c2d  mov     rcx, rsi; SRWLock
0x140010c30  call    cs:__imp_AcquireSRWLockExclusive
0x140010c36  xor     eax, eax
0x140010c38  mov     word ptr [rsp+68h+var_48+6], ax
0x140010c3d  mov     dword ptr [rsp+68h+var_48], r14d
0x140010c42  mov     word ptr [rsp+68h+var_48+4], bx
0x140010c47  lea     rbx, [rdi+0E8h]
0x140010c4e  lea     edx, [rax+0Ch]; unsigned __int64
0x140010c51  mov     rcx, rbx; this
0x140010c54  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140010c59  test    al, al
0x140010c5b  jz      short loc_140010CB7
0x140010c5d  mov     rcx, [rbx+8]; void *
0x140010c61  mov     rax, [rbx+10h]
0x140010c65  sub     rax, rcx
0x140010c68  cmp     rcx, [rbx+10h]
0x140010c6c  sbb     r8, r8
0x140010c6f  and     r8, rax; Size
0x140010c72  test    rcx, rcx
0x140010c75  jnz     short loc_140010C85
0x140010c77  call    cs:__imp__o__errno
0x140010c7d  mov     dword ptr [rax], 16h
0x140010c83  jmp     short loc_140010CAD
0x140010c85  cmp     r8, 0Ch
0x140010c89  jb      short loc_140010C9A
0x140010c8b  movsd   xmm0, [rsp+68h+var_48]
0x140010c91  movsd   qword ptr [rcx], xmm0
0x140010c95  mov     [rcx+8], ebp
0x140010c98  jmp     short loc_140010CB2
0x140010c9a  xor     edx, edx; Val
0x140010c9c  call    memset_0
0x140010ca1  call    cs:__imp__o__errno
0x140010ca7  mov     dword ptr [rax], 22h ; '"'
0x140010cad  call    _invalid_parameter_noinfo
0x140010cb2  add     qword ptr [rbx+8], 0Ch
0x140010cb7  cmp     byte ptr [rdi+40h], 0
0x140010cbb  jnz     loc_140010D5F
0x140010cc1  cmp     qword ptr [rdi+38h], 0
0x140010cc6  jnz     short loc_140010D35
0x140010cc8  call    cs:__imp_GetLastError
0x140010cce  mov     r14d, eax
0x140010cd1  xor     r8d, r8d; pcbe
0x140010cd4  mov     rdx, rdi; pv
0x140010cd7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140010cde  call    cs:__imp_CreateThreadpoolTimer
0x140010ce4  mov     r15, rax
0x140010ce7  mov     rbp, [rdi+38h]
0x140010ceb  test    rbp, rbp
0x140010cee  jz      short loc_140010D28
0x140010cf0  call    cs:__imp_GetLastError
0x140010cf6  mov     ebx, eax
0x140010cf8  xor     r9d, r9d; msWindowLength
0x140010cfb  xor     r8d, r8d; msPeriod
0x140010cfe  xor     edx, edx; pftDueTime
0x140010d00  mov     rcx, rbp; pti
0x140010d03  call    cs:__imp_SetThreadpoolTimer
0x140010d09  mov     edx, 1; fCancelPendingCallbacks
0x140010d0e  mov     rcx, rbp; pti
0x140010d11  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140010d17  mov     rcx, rbp; pti
0x140010d1a  call    cs:__imp_CloseThreadpoolTimer
0x140010d20  mov     ecx, ebx; dwErrCode
0x140010d22  call    cs:__imp_SetLastError
0x140010d28  mov     [rdi+38h], r15
0x140010d2c  mov     ecx, r14d; dwErrCode
0x140010d2f  call    cs:__imp_SetLastError
0x140010d35  mov     rcx, [rdi+38h]; pti
0x140010d39  test    rcx, rcx
0x140010d3c  jz      short loc_140010D5F
0x140010d3e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x140010d47  mov     r9d, 4E2h; msWindowLength
0x140010d4d  xor     r8d, r8d; msPeriod
0x140010d50  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140010d55  call    cs:__imp_SetThreadpoolTimer
0x140010d5b  mov     byte ptr [rdi+40h], 1
0x140010d5f  test    rsi, rsi
0x140010d62  jz      short loc_140010D6E
0x140010d64  mov     rcx, rsi; SRWLock
0x140010d67  call    cs:__imp_ReleaseSRWLockExclusive
0x140010d6d  nop
0x140010d6e  add     rsp, 38h
0x140010d72  pop     r15
0x140010d74  pop     r14
0x140010d76  pop     rdi
0x140010d77  pop     rsi
0x140010d78  pop     rbp
0x140010d79  pop     rbx
0x140010d7a  retn
```
