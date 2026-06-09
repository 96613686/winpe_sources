# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x18000bf84`
- end: `0x18000c0f3`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `367`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e3a0`

## callees

- `0x18000bf84`
- `0x18000e8ec`
- `0x18000e9ec`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c036`
- `msvcrt!memcpy_s` at `0x18000c036`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c056`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c08a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c08a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c0cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c0cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bfe0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bfe0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c071`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c071`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c0b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c0b5`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        char *pv,
        int a2,
        __int16 a3,
        int a4)
{
  struct _TP_TIMER **v8; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _TP_TIMER *v11; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-48h] BYREF
  int Source; // [rsp+28h] [rbp-40h] BYREF
  __int16 v14; // [rsp+2Ch] [rbp-3Ch]
  __int16 v15; // [rsp+2Eh] [rbp-3Ah]
  int v16; // [rsp+30h] [rbp-38h]

  if ( *pv
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)pv + 5);
    v15 = 0;
    Source = a2;
    v14 = a3;
    v16 = a4;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(pv + 232), 0xCu) )
    {
      memcpy_s(
        *((void *const *)pv + 30),
        (*((_QWORD *)pv + 31) - *((_QWORD *)pv + 30)) & -(__int64)(*((_QWORD *)pv + 30) < *((_QWORD *)pv + 31)),
        &Source,
        0xCu);
      *((_QWORD *)pv + 30) += 12LL;
    }
    if ( !pv[64] )
    {
      v8 = (struct _TP_TIMER **)(pv + 56);
      if ( !*((_QWORD *)pv + 7) )
      {
        LastError = GetLastError();
        ThreadpoolTimer = CreateThreadpoolTimer(
                            _lambda_5035b992506f4af81a770c5842624510_::_lambda_invoker_cdecl_,
                            pv,
                            0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (struct _TP_TIMER **)pv + 7,
          ThreadpoolTimer);
        SetLastError(LastError);
      }
      v11 = *v8;
      if ( *v8 )
      {
        pftDueTime = (struct _FILETIME)-50000000LL;
        SetThreadpoolTimer(v11, &pftDueTime, 0, 0x4E2u);
        pv[64] = 1;
      }
    }
    if ( pv != (char *)-40LL )
      ReleaseSRWLockExclusive((PSRWLOCK)pv + 5);
  }
}

```

## disassembly

```asm
0x18000bf84  push    rbx
0x18000bf86  push    rbp
0x18000bf87  push    rsi
0x18000bf88  push    rdi
0x18000bf89  push    r14
0x18000bf8b  sub     rsp, 40h
0x18000bf8f  mov     rax, cs:__security_cookie
0x18000bf96  xor     rax, rsp
0x18000bf99  mov     [rsp+68h+var_30], rax
0x18000bf9e  mov     r14d, r9d
0x18000bfa1  movzx   esi, r8w
0x18000bfa5  mov     ebx, edx
0x18000bfa7  mov     rdi, rcx
0x18000bfaa  cmp     byte ptr [rcx], 0
0x18000bfad  jz      loc_18000C0DA
0x18000bfb3  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000bfba  jnz     loc_18000C0DA
0x18000bfc0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000bfc7  test    rax, rax
0x18000bfca  jz      short loc_18000BFD9
0x18000bfcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfd1  test    al, al
0x18000bfd3  jnz     loc_18000C0DA
0x18000bfd9  lea     rbp, [rdi+28h]
0x18000bfdd  mov     rcx, rbp; SRWLock
0x18000bfe0  call    cs:__imp_AcquireSRWLockExclusive
0x18000bfe7  nop     dword ptr [rax+rax+00h]
0x18000bfec  xor     eax, eax
0x18000bfee  mov     [rsp+68h+var_3A], ax
0x18000bff3  mov     [rsp+68h+Source], ebx
0x18000bff7  mov     [rsp+68h+var_3C], si
0x18000bffc  mov     [rsp+68h+var_38], r14d
0x18000c001  lea     rbx, [rdi+0E8h]
0x18000c008  lea     esi, [rax+0Ch]
0x18000c00b  mov     edx, esi; unsigned __int64
0x18000c00d  mov     rcx, rbx; this
0x18000c010  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000c015  test    al, al
0x18000c017  jz      short loc_18000C046
0x18000c019  mov     rcx, [rbx+8]; Destination
0x18000c01d  mov     rax, [rbx+10h]
0x18000c021  sub     rax, rcx
0x18000c024  cmp     rcx, [rbx+10h]
0x18000c028  sbb     rdx, rdx
0x18000c02b  and     rdx, rax; DestinationSize
0x18000c02e  mov     r9d, esi; SourceSize
0x18000c031  lea     r8, [rsp+68h+Source]; Source
0x18000c036  call    cs:__imp_memcpy_s
0x18000c03d  nop     dword ptr [rax+rax+00h]
0x18000c042  add     [rbx+8], rsi
0x18000c046  cmp     byte ptr [rdi+40h], 0
0x18000c04a  jnz     short loc_18000C0C5
0x18000c04c  lea     rsi, [rdi+38h]
0x18000c050  cmp     qword ptr [rsi], 0
0x18000c054  jnz     short loc_18000C096
0x18000c056  call    cs:__imp_GetLastError
0x18000c05d  nop     dword ptr [rax+rax+00h]
0x18000c062  mov     ebx, eax
0x18000c064  xor     r8d, r8d; pcbe
0x18000c067  mov     rdx, rdi; pv
0x18000c06a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c071  call    cs:__imp_CreateThreadpoolTimer
0x18000c078  nop     dword ptr [rax+rax+00h]
0x18000c07d  mov     rdx, rax
0x18000c080  mov     rcx, rsi
0x18000c083  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000c088  mov     ecx, ebx; dwErrCode
0x18000c08a  call    cs:__imp_SetLastError
0x18000c091  nop     dword ptr [rax+rax+00h]
0x18000c096  mov     rcx, [rsi]; pti
0x18000c099  test    rcx, rcx
0x18000c09c  jz      short loc_18000C0C5
0x18000c09e  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000c0a7  mov     r9d, 4E2h; msWindowLength
0x18000c0ad  xor     r8d, r8d; msPeriod
0x18000c0b0  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x18000c0b5  call    cs:__imp_SetThreadpoolTimer
0x18000c0bc  nop     dword ptr [rax+rax+00h]
0x18000c0c1  mov     byte ptr [rdi+40h], 1
0x18000c0c5  test    rbp, rbp
0x18000c0c8  jz      short loc_18000C0DA
0x18000c0ca  mov     rcx, rbp; SRWLock
0x18000c0cd  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c0d4  nop     dword ptr [rax+rax+00h]
0x18000c0d9  nop
0x18000c0da  mov     rcx, [rsp+68h+var_30]
0x18000c0df  xor     rcx, rsp; StackCookie
0x18000c0e2  call    __security_check_cookie
0x18000c0e7  add     rsp, 40h
0x18000c0eb  pop     r14
0x18000c0ed  pop     rdi
0x18000c0ee  pop     rsi
0x18000c0ef  pop     rbp
0x18000c0f0  pop     rbx
0x18000c0f1  retn
```
