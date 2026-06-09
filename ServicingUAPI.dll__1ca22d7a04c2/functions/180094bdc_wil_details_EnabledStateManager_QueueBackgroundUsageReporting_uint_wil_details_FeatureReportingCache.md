# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180094bdc`
- end: `0x180094da8`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `460`
- prototype: `void __fastcall(PVOID pv, unsigned int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180094f80`

## callees

- `0x1800031d0`
- `0x180003b2a`
- `0x180003b66`
- `0x180003c64`
- `0x18003c854`
- `0x18003c954`
- `0x180094bdc`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094cfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094cfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094d30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180094d30`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180094c45`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180094c45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180094d79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180094d79`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180094d61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180094d61`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180094d17`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180094d17`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        char *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rcx
  _DWORD *v7; // rcx
  size_t v8; // r8
  __int64 v9; // rcx
  struct _TP_TIMER **v10; // r14
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v13; // rcx
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-40h] BYREF

  if ( *(_DWORD *)pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv)) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 1);
    if ( !*(_DWORD *)pv
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v6) )
    {
LABEL_22:
      if ( pv != (char *)-8LL )
        ReleaseSRWLockExclusive((PSRWLOCK)pv + 1);
      return;
    }
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 32), 0x10u) )
    {
LABEL_17:
      if ( !pv[24] )
      {
        v10 = (struct _TP_TIMER **)(pv + 16);
        if ( !*((_QWORD *)pv + 2) )
        {
          LastError = GetLastError();
          ThreadpoolTimer = CreateThreadpoolTimer(
                              `wil::details::EnsureCoalescedTimer<wil::details::EnabledStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                              pv,
                              0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            (struct _TP_TIMER **)pv + 2,
            ThreadpoolTimer);
          SetLastError(LastError);
        }
        v13 = *v10;
        if ( *v10 )
        {
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v13, &pftDueTime, 0, 0x124F8u);
          pv[24] = 1;
        }
      }
      goto LABEL_22;
    }
    v7 = (_DWORD *)*((_QWORD *)pv + 5);
    v8 = (*((_QWORD *)pv + 6) - (_QWORD)v7) & -(__int64)((unsigned __int64)v7 < *((_QWORD *)pv + 6));
    if ( v7 )
    {
      if ( v8 >= 0x10 )
      {
        *v7 = a2;
        v7[1] = 0;
        *((_QWORD *)v7 + 1) = a3;
LABEL_16:
        *((_QWORD *)pv + 5) += 16LL;
        goto LABEL_17;
      }
      memset_0(v7, 0, v8);
      *(_DWORD *)o__errno_0(v9) = 34;
    }
    else
    {
      *(_DWORD *)o__errno_0(0) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x180094bdc  mov     rax, rsp
0x180094bdf  push    rbp
0x180094be0  push    rsi
0x180094be1  push    rdi
0x180094be2  push    r12
0x180094be4  push    r14
0x180094be6  sub     rsp, 40h
0x180094bea  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180094bf2  mov     [rax+20h], rbx
0x180094bf6  mov     rax, cs:__security_cookie
0x180094bfd  xor     rax, rsp
0x180094c00  mov     [rsp+68h+var_38], rax
0x180094c05  mov     rbp, r8
0x180094c08  mov     r14d, edx
0x180094c0b  mov     rdi, rcx
0x180094c0e  mov     eax, [rcx]
0x180094c10  test    eax, eax
0x180094c12  jz      loc_180094D86
0x180094c18  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180094c1f  jnz     loc_180094D86
0x180094c25  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180094c2c  test    rax, rax
0x180094c2f  jz      short loc_180094C3E
0x180094c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094c36  test    al, al
0x180094c38  jnz     loc_180094D86
0x180094c3e  lea     rsi, [rdi+8]
0x180094c42  mov     rcx, rsi; SRWLock
0x180094c45  call    cs:__imp_AcquireSRWLockExclusive
0x180094c4c  nop     dword ptr [rax+rax+00h]
0x180094c51  mov     eax, [rdi]
0x180094c53  test    eax, eax
0x180094c55  jz      loc_180094D71
0x180094c5b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180094c62  jnz     loc_180094D71
0x180094c68  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180094c6f  test    rax, rax
0x180094c72  jz      short loc_180094C81
0x180094c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094c79  test    al, al
0x180094c7b  jnz     loc_180094D71
0x180094c81  xor     r12d, r12d
0x180094c84  lea     edx, [r12+10h]; unsigned __int64
0x180094c89  lea     rcx, [rdi+20h]; this
0x180094c8d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180094c92  test    al, al
0x180094c94  jz      short loc_180094CEC
0x180094c96  mov     rcx, [rdi+28h]; void *
0x180094c9a  mov     rax, [rdi+30h]
0x180094c9e  sub     rax, rcx
0x180094ca1  cmp     rcx, [rdi+30h]
0x180094ca5  sbb     r8, r8
0x180094ca8  and     r8, rax; Size
0x180094cab  test    rcx, rcx
0x180094cae  jnz     short loc_180094CBD
0x180094cb0  call    _o__errno_0
0x180094cb5  mov     dword ptr [rax], 16h
0x180094cbb  jmp     short loc_180094CE2
0x180094cbd  cmp     r8, 10h
0x180094cc1  jb      short loc_180094CD0
0x180094cc3  mov     [rcx], r14d
0x180094cc6  mov     [rcx+4], r12d
0x180094cca  mov     [rcx+8], rbp
0x180094cce  jmp     short loc_180094CE7
0x180094cd0  xor     edx, edx; Val
0x180094cd2  call    memset_0
0x180094cd7  call    _o__errno_0
0x180094cdc  mov     dword ptr [rax], 22h ; '"'
0x180094ce2  call    _invalid_parameter_noinfo
0x180094ce7  add     qword ptr [rdi+28h], 10h
0x180094cec  cmp     byte ptr [rdi+18h], 0
0x180094cf0  jnz     short loc_180094D71
0x180094cf2  lea     r14, [rdi+10h]
0x180094cf6  cmp     qword ptr [r14], 0
0x180094cfa  jnz     short loc_180094D3C
0x180094cfc  call    cs:__imp_GetLastError
0x180094d03  nop     dword ptr [rax+rax+00h]
0x180094d08  mov     ebx, eax
0x180094d0a  xor     r8d, r8d; pcbe
0x180094d0d  mov     rdx, rdi; pv
0x180094d10  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VEnabledStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVEnabledStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180094d17  call    cs:__imp_CreateThreadpoolTimer
0x180094d1e  nop     dword ptr [rax+rax+00h]
0x180094d23  mov     rdx, rax
0x180094d26  mov     rcx, r14
0x180094d29  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180094d2e  mov     ecx, ebx; dwErrCode
0x180094d30  call    cs:__imp_SetLastError
0x180094d37  nop     dword ptr [rax+rax+00h]
0x180094d3c  mov     rcx, [r14]; pti
0x180094d3f  test    rcx, rcx
0x180094d42  jz      short loc_180094D71
0x180094d44  mov     rax, 0FFFFFFFF4D2FA200h
0x180094d4e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], rax
0x180094d53  mov     r9d, 124F8h; msWindowLength
0x180094d59  xor     r8d, r8d; msPeriod
0x180094d5c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180094d61  call    cs:__imp_SetThreadpoolTimer
0x180094d68  nop     dword ptr [rax+rax+00h]
0x180094d6d  mov     byte ptr [rdi+18h], 1
0x180094d71  test    rsi, rsi
0x180094d74  jz      short loc_180094D86
0x180094d76  mov     rcx, rsi; SRWLock
0x180094d79  call    cs:__imp_ReleaseSRWLockExclusive
0x180094d80  nop     dword ptr [rax+rax+00h]
0x180094d85  nop
0x180094d86  mov     rcx, [rsp+68h+var_38]
0x180094d8b  xor     rcx, rsp; StackCookie
0x180094d8e  call    __security_check_cookie
0x180094d93  mov     rbx, [rsp+68h+arg_18]
0x180094d9b  add     rsp, 40h
0x180094d9f  pop     r14
0x180094da1  pop     r12
0x180094da3  pop     rdi
0x180094da4  pop     rsi
0x180094da5  pop     rbp
0x180094da6  retn
```
