# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18003a9f4`
- end: `0x18003ab90`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `412`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18003c4d0`

## callees

- `0x1800031d0`
- `0x180003b2a`
- `0x180003b66`
- `0x180003c64`
- `0x18003a9f4`
- `0x18003c854`
- `0x18003c954`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aaf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aaf4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ab28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ab28`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003aa59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003aa59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ab6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003ab6b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003ab53`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003ab53`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003ab0f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003ab0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        DWORD a2,
        unsigned __int16 a3,
        DWORD a4)
{
  struct _FILETIME *v8; // rcx
  size_t v9; // r8
  __int64 v10; // rcx
  struct _TP_TIMER **v11; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v14; // rcx
  struct _FILETIME pftDueTime; // [rsp+28h] [rbp-40h] BYREF

  if ( !*pv
    || wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv) )
  {
    return;
  }
  AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
  pftDueTime.dwLowDateTime = a2;
  pftDueTime.dwHighDateTime = a3;
  if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 232), 0xCu) )
  {
    v8 = (struct _FILETIME *)*((_QWORD *)pv + 30);
    v9 = (*((_QWORD *)pv + 31) - (_QWORD)v8) & -(__int64)((unsigned __int64)v8 < *((_QWORD *)pv + 31));
    if ( v8 )
    {
      if ( v9 >= 0xC )
      {
        *v8 = pftDueTime;
        v8[1].dwLowDateTime = a4;
LABEL_12:
        *((_QWORD *)pv + 30) += 12LL;
        goto LABEL_13;
      }
      memset_0(v8, 0, v9);
      *(_DWORD *)o__errno_0(v10) = 34;
    }
    else
    {
      *(_DWORD *)o__errno_0(0) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_12;
  }
LABEL_13:
  if ( !pv[64] )
  {
    v11 = (struct _TP_TIMER **)(pv + 56);
    if ( !*((_QWORD *)pv + 7) )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(
                          `wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        (struct _TP_TIMER **)pv + 7,
        ThreadpoolTimer);
      SetLastError(LastError);
    }
    v14 = *v11;
    if ( *v11 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v14, &pftDueTime, 0, 0x4E2u);
      pv[64] = 1;
    }
  }
  if ( pv != (char *)-40LL )
    ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
}

```

## disassembly

```asm
0x18003a9f4  push    rbx
0x18003a9f6  push    rbp
0x18003a9f7  push    rsi
0x18003a9f8  push    rdi
0x18003a9f9  push    r14
0x18003a9fb  sub     rsp, 40h
0x18003a9ff  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x18003aa08  mov     rax, cs:__security_cookie
0x18003aa0f  xor     rax, rsp
0x18003aa12  mov     [rsp+68h+var_30], rax
0x18003aa17  mov     esi, r9d
0x18003aa1a  movzx   r14d, r8w
0x18003aa1e  mov     ebx, edx
0x18003aa20  mov     rdi, rcx
0x18003aa23  cmp     byte ptr [rcx], 0
0x18003aa26  jz      loc_18003AB77
0x18003aa2c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18003aa33  jnz     loc_18003AB77
0x18003aa39  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18003aa40  test    rax, rax
0x18003aa43  jz      short loc_18003AA52
0x18003aa45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa4a  test    al, al
0x18003aa4c  jnz     loc_18003AB77
0x18003aa52  lea     rbp, [rdi+28h]
0x18003aa56  mov     rcx, rbp; SRWLock
0x18003aa59  call    cs:__imp_AcquireSRWLockExclusive
0x18003aa60  nop     dword ptr [rax+rax+00h]
0x18003aa65  xor     eax, eax
0x18003aa67  mov     word ptr [rsp+68h+pftDueTime.dwHighDateTime+2], ax
0x18003aa6c  mov     [rsp+68h+pftDueTime.dwLowDateTime], ebx
0x18003aa70  mov     word ptr [rsp+68h+pftDueTime.dwHighDateTime], r14w
0x18003aa76  lea     rbx, [rdi+0E8h]
0x18003aa7d  lea     edx, [rax+0Ch]; unsigned __int64
0x18003aa80  mov     rcx, rbx; this
0x18003aa83  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18003aa88  test    al, al
0x18003aa8a  jz      short loc_18003AAE4
0x18003aa8c  mov     rcx, [rbx+8]; void *
0x18003aa90  mov     rax, [rbx+10h]
0x18003aa94  sub     rax, rcx
0x18003aa97  cmp     rcx, [rbx+10h]
0x18003aa9b  sbb     r8, r8
0x18003aa9e  and     r8, rax; Size
0x18003aaa1  test    rcx, rcx
0x18003aaa4  jnz     short loc_18003AAB3
0x18003aaa6  call    _o__errno_0
0x18003aaab  mov     dword ptr [rax], 16h
0x18003aab1  jmp     short loc_18003AADA
0x18003aab3  cmp     r8, 0Ch
0x18003aab7  jb      short loc_18003AAC8
0x18003aab9  movsd   xmm0, qword ptr [rsp+68h+pftDueTime.dwLowDateTime]
0x18003aabf  movsd   qword ptr [rcx], xmm0
0x18003aac3  mov     [rcx+8], esi
0x18003aac6  jmp     short loc_18003AADF
0x18003aac8  xor     edx, edx; Val
0x18003aaca  call    memset_0
0x18003aacf  call    _o__errno_0
0x18003aad4  mov     dword ptr [rax], 22h ; '"'
0x18003aada  call    _invalid_parameter_noinfo
0x18003aadf  add     qword ptr [rbx+8], 0Ch
0x18003aae4  cmp     byte ptr [rdi+40h], 0
0x18003aae8  jnz     short loc_18003AB63
0x18003aaea  lea     rsi, [rdi+38h]
0x18003aaee  cmp     qword ptr [rsi], 0
0x18003aaf2  jnz     short loc_18003AB34
0x18003aaf4  call    cs:__imp_GetLastError
0x18003aafb  nop     dword ptr [rax+rax+00h]
0x18003ab00  mov     ebx, eax
0x18003ab02  xor     r8d, r8d; pcbe
0x18003ab05  mov     rdx, rdi; pv
0x18003ab08  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003ab0f  call    cs:__imp_CreateThreadpoolTimer
0x18003ab16  nop     dword ptr [rax+rax+00h]
0x18003ab1b  mov     rdx, rax
0x18003ab1e  mov     rcx, rsi
0x18003ab21  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18003ab26  mov     ecx, ebx; dwErrCode
0x18003ab28  call    cs:__imp_SetLastError
0x18003ab2f  nop     dword ptr [rax+rax+00h]
0x18003ab34  mov     rcx, [rsi]; pti
0x18003ab37  test    rcx, rcx
0x18003ab3a  jz      short loc_18003AB63
0x18003ab3c  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18003ab45  mov     r9d, 4E2h; msWindowLength
0x18003ab4b  xor     r8d, r8d; msPeriod
0x18003ab4e  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18003ab53  call    cs:__imp_SetThreadpoolTimer
0x18003ab5a  nop     dword ptr [rax+rax+00h]
0x18003ab5f  mov     byte ptr [rdi+40h], 1
0x18003ab63  test    rbp, rbp
0x18003ab66  jz      short loc_18003AB77
0x18003ab68  mov     rcx, rbp; SRWLock
0x18003ab6b  call    cs:__imp_ReleaseSRWLockExclusive
0x18003ab72  nop     dword ptr [rax+rax+00h]
0x18003ab77  mov     rcx, [rsp+68h+var_30]
0x18003ab7c  xor     rcx, rsp; StackCookie
0x18003ab7f  call    __security_check_cookie
0x18003ab84  add     rsp, 40h
0x18003ab88  pop     r14
0x18003ab8a  pop     rdi
0x18003ab8b  pop     rsi
0x18003ab8c  pop     rbp
0x18003ab8d  pop     rbx
0x18003ab8e  retn
```
