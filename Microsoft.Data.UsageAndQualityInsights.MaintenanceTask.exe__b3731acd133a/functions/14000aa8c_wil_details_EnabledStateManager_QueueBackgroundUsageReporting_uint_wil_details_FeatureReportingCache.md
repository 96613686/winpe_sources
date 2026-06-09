# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x14000aa8c`
- end: `0x14000ac44`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `440`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14000ad84`

## callees

- `0x14000216a`
- `0x14000221c`
- `0x140008c3c`
- `0x14000aa8c`
- `0x14000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ab3d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ab65`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ab3d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ab65`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000aad9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000aad9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ac30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ac30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ab8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000abb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ab8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000abb3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000abe5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000abf2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000abe5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000abf2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000aba1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000aba1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000abdd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000abdd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000abc6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ac1e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000abc6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ac1e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000abd4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000abd4`

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
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // rbp
  DWORD v15; // ebx
  struct _TP_TIMER *v16; // rcx
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
                              (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          Ptr = (struct _TP_TIMER *)pv[2].Ptr;
          if ( Ptr )
          {
            v15 = GetLastError();
            SetThreadpoolTimer(Ptr, 0, 0, 0);
            WaitForThreadpoolTimerCallbacks(Ptr, 1);
            CloseThreadpoolTimer(Ptr);
            SetLastError(v15);
          }
          pv[2].Ptr = ThreadpoolTimer;
          SetLastError(LastError);
        }
        v16 = (struct _TP_TIMER *)pv[2].Ptr;
        if ( v16 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v16, &pftDueTime, 0, 0x124F8u);
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
0x14000aa8c  push    rbx
0x14000aa8e  push    rbp
0x14000aa8f  push    rsi
0x14000aa90  push    rdi
0x14000aa91  push    r14
0x14000aa93  push    r15
0x14000aa95  sub     rsp, 28h
0x14000aa99  mov     rbp, r8
0x14000aa9c  mov     r14d, edx
0x14000aa9f  mov     rdi, rcx
0x14000aaa2  mov     eax, [rcx]
0x14000aaa4  test    eax, eax
0x14000aaa6  jz      loc_14000AC37
0x14000aaac  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000aab3  jnz     loc_14000AC37
0x14000aab9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000aac0  test    rax, rax
0x14000aac3  jz      short loc_14000AAD2
0x14000aac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aaca  test    al, al
0x14000aacc  jnz     loc_14000AC37
0x14000aad2  lea     rsi, [rdi+8]
0x14000aad6  mov     rcx, rsi; SRWLock
0x14000aad9  call    cs:__imp_AcquireSRWLockExclusive
0x14000aadf  mov     eax, [rdi]
0x14000aae1  test    eax, eax
0x14000aae3  jz      loc_14000AC28
0x14000aae9  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000aaf0  jnz     loc_14000AC28
0x14000aaf6  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000aafd  test    rax, rax
0x14000ab00  jz      short loc_14000AB0F
0x14000ab02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab07  test    al, al
0x14000ab09  jnz     loc_14000AC28
0x14000ab0f  xor     r15d, r15d
0x14000ab12  lea     edx, [r15+10h]; unsigned __int64
0x14000ab16  lea     rcx, [rdi+20h]; this
0x14000ab1a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000ab1f  test    al, al
0x14000ab21  jz      short loc_14000AB7B
0x14000ab23  mov     rcx, [rdi+28h]; void *
0x14000ab27  mov     rax, [rdi+30h]
0x14000ab2b  sub     rax, rcx
0x14000ab2e  cmp     rcx, [rdi+30h]
0x14000ab32  sbb     r8, r8
0x14000ab35  and     r8, rax; Size
0x14000ab38  test    rcx, rcx
0x14000ab3b  jnz     short loc_14000AB4B
0x14000ab3d  call    cs:__imp__o__errno
0x14000ab43  mov     dword ptr [rax], 16h
0x14000ab49  jmp     short loc_14000AB71
0x14000ab4b  cmp     r8, 10h
0x14000ab4f  jb      short loc_14000AB5E
0x14000ab51  mov     [rcx], r14d
0x14000ab54  mov     [rcx+4], r15d
0x14000ab58  mov     [rcx+8], rbp
0x14000ab5c  jmp     short loc_14000AB76
0x14000ab5e  xor     edx, edx; Val
0x14000ab60  call    memset_0
0x14000ab65  call    cs:__imp__o__errno
0x14000ab6b  mov     dword ptr [rax], 22h ; '"'
0x14000ab71  call    _invalid_parameter_noinfo
0x14000ab76  add     qword ptr [rdi+28h], 10h
0x14000ab7b  cmp     [rdi+18h], r15b
0x14000ab7f  jnz     loc_14000AC28
0x14000ab85  cmp     [rdi+10h], r15
0x14000ab89  jnz     short loc_14000ABF8
0x14000ab8b  call    cs:__imp_GetLastError
0x14000ab91  mov     r14d, eax
0x14000ab94  xor     r8d, r8d; pcbe
0x14000ab97  mov     rdx, rdi; pv
0x14000ab9a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000aba1  call    cs:__imp_CreateThreadpoolTimer
0x14000aba7  mov     r15, rax
0x14000abaa  mov     rbp, [rdi+10h]
0x14000abae  test    rbp, rbp
0x14000abb1  jz      short loc_14000ABEB
0x14000abb3  call    cs:__imp_GetLastError
0x14000abb9  mov     ebx, eax
0x14000abbb  xor     r9d, r9d; msWindowLength
0x14000abbe  xor     r8d, r8d; msPeriod
0x14000abc1  xor     edx, edx; pftDueTime
0x14000abc3  mov     rcx, rbp; pti
0x14000abc6  call    cs:__imp_SetThreadpoolTimer
0x14000abcc  mov     edx, 1; fCancelPendingCallbacks
0x14000abd1  mov     rcx, rbp; pti
0x14000abd4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000abda  mov     rcx, rbp; pti
0x14000abdd  call    cs:__imp_CloseThreadpoolTimer
0x14000abe3  mov     ecx, ebx; dwErrCode
0x14000abe5  call    cs:__imp_SetLastError
0x14000abeb  mov     [rdi+10h], r15
0x14000abef  mov     ecx, r14d; dwErrCode
0x14000abf2  call    cs:__imp_SetLastError
0x14000abf8  mov     rcx, [rdi+10h]; pti
0x14000abfc  test    rcx, rcx
0x14000abff  jz      short loc_14000AC28
0x14000ac01  mov     rax, 0FFFFFFFF4D2FA200h
0x14000ac0b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], rax
0x14000ac10  mov     r9d, 124F8h; msWindowLength
0x14000ac16  xor     r8d, r8d; msPeriod
0x14000ac19  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x14000ac1e  call    cs:__imp_SetThreadpoolTimer
0x14000ac24  mov     byte ptr [rdi+18h], 1
0x14000ac28  test    rsi, rsi
0x14000ac2b  jz      short loc_14000AC37
0x14000ac2d  mov     rcx, rsi; SRWLock
0x14000ac30  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ac36  nop
0x14000ac37  add     rsp, 28h
0x14000ac3b  pop     r15
0x14000ac3d  pop     r14
0x14000ac3f  pop     rdi
0x14000ac40  pop     rsi
0x14000ac41  pop     rbp
0x14000ac42  pop     rbx
0x14000ac43  retn
```
