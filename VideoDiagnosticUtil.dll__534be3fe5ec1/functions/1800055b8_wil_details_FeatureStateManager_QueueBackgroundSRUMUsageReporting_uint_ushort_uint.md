# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x1800055b8`
- end: `0x180005726`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `366`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800074b0`

## callees

- `0x1800055b8`
- `0x180008360`
- `0x18000897c`
- `0x1800096b0`
- `0x18000a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000566a`
- `msvcrt!memcpy_s` at `0x18000566a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005614`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180005614`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005701`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180005701`
- `KERNEL32!GetLastError` at `0x18000568a`
- `KERNEL32!GetLastError` at `0x18000568a`
- `KERNEL32!SetLastError` at `0x1800056be`
- `KERNEL32!SetLastError` at `0x1800056be`
- `KERNEL32!SetThreadpoolTimer` at `0x1800056e9`
- `KERNEL32!SetThreadpoolTimer` at `0x1800056e9`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800056a5`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800056a5`

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
    Source = a2;
    v14 = a3;
    v15 = 0;
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
0x1800055b8  push    rbx
0x1800055ba  push    rbp
0x1800055bb  push    rsi
0x1800055bc  push    rdi
0x1800055bd  push    r14
0x1800055bf  sub     rsp, 40h
0x1800055c3  mov     rax, cs:__security_cookie
0x1800055ca  xor     rax, rsp
0x1800055cd  mov     [rsp+68h+var_30], rax
0x1800055d2  cmp     byte ptr [rcx], 0
0x1800055d5  mov     r14d, r9d
0x1800055d8  movzx   esi, r8w
0x1800055dc  mov     ebx, edx
0x1800055de  mov     rdi, rcx
0x1800055e1  jz      loc_18000570D
0x1800055e7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800055ee  jnz     loc_18000570D
0x1800055f4  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800055fb  test    rax, rax
0x1800055fe  jz      short loc_18000560D
0x180005600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005605  test    al, al
0x180005607  jnz     loc_18000570D
0x18000560d  lea     rbp, [rdi+28h]
0x180005611  mov     rcx, rbp; SRWLock
0x180005614  call    cs:__imp_AcquireSRWLockExclusive
0x18000561b  nop     dword ptr [rax+rax+00h]
0x180005620  xor     eax, eax
0x180005622  mov     [rsp+68h+Source], ebx
0x180005626  mov     [rsp+68h+var_3C], si
0x18000562b  lea     rbx, [rdi+0E8h]
0x180005632  mov     rcx, rbx; this
0x180005635  mov     [rsp+68h+var_3A], ax
0x18000563a  mov     [rsp+68h+var_38], r14d
0x18000563f  lea     esi, [rax+0Ch]
0x180005642  mov     edx, esi; unsigned __int64
0x180005644  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005649  test    al, al
0x18000564b  jz      short loc_18000567A
0x18000564d  mov     rcx, [rbx+8]; Destination
0x180005651  lea     r8, [rsp+68h+Source]; Source
0x180005656  mov     rax, [rbx+10h]
0x18000565a  mov     r9d, esi; SourceSize
0x18000565d  sub     rax, rcx
0x180005660  cmp     rcx, [rbx+10h]
0x180005664  sbb     rdx, rdx
0x180005667  and     rdx, rax; DestinationSize
0x18000566a  call    cs:__imp_memcpy_s
0x180005671  nop     dword ptr [rax+rax+00h]
0x180005676  add     [rbx+8], rsi
0x18000567a  cmp     byte ptr [rdi+40h], 0
0x18000567e  jnz     short loc_1800056F9
0x180005680  lea     rsi, [rdi+38h]
0x180005684  cmp     qword ptr [rsi], 0
0x180005688  jnz     short loc_1800056CA
0x18000568a  call    cs:__imp_GetLastError
0x180005691  nop     dword ptr [rax+rax+00h]
0x180005696  xor     r8d, r8d; pcbe
0x180005699  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800056a0  mov     rdx, rdi; pv
0x1800056a3  mov     ebx, eax
0x1800056a5  call    cs:__imp_CreateThreadpoolTimer
0x1800056ac  nop     dword ptr [rax+rax+00h]
0x1800056b1  mov     rdx, rax
0x1800056b4  mov     rcx, rsi
0x1800056b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800056bc  mov     ecx, ebx; dwErrCode
0x1800056be  call    cs:__imp_SetLastError
0x1800056c5  nop     dword ptr [rax+rax+00h]
0x1800056ca  mov     rcx, [rsi]; pti
0x1800056cd  test    rcx, rcx
0x1800056d0  jz      short loc_1800056F9
0x1800056d2  mov     r9d, 4E2h; msWindowLength
0x1800056d8  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800056e1  xor     r8d, r8d; msPeriod
0x1800056e4  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800056e9  call    cs:__imp_SetThreadpoolTimer
0x1800056f0  nop     dword ptr [rax+rax+00h]
0x1800056f5  mov     byte ptr [rdi+40h], 1
0x1800056f9  test    rbp, rbp
0x1800056fc  jz      short loc_18000570D
0x1800056fe  mov     rcx, rbp; SRWLock
0x180005701  call    cs:__imp_ReleaseSRWLockExclusive
0x180005708  nop     dword ptr [rax+rax+00h]
0x18000570d  mov     rcx, [rsp+68h+var_30]
0x180005712  xor     rcx, rsp; StackCookie
0x180005715  call    __security_check_cookie
0x18000571a  add     rsp, 40h
0x18000571e  pop     r14
0x180005720  pop     rdi
0x180005721  pop     rsi
0x180005722  pop     rbp
0x180005723  pop     rbx
0x180005724  retn
```
