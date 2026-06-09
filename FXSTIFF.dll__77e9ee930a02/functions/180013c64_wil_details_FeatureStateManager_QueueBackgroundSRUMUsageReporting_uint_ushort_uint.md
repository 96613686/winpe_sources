# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180013c64`
- end: `0x180013dd5`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `369`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800161a0`

## callees

- `0x180013c64`
- `0x18001685c`
- `0x18001695c`
- `0x1800189d0`
- `0x180019010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180013d16`
- `msvcrt!memcpy_s` at `0x180013d16`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180013daf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180013daf`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013cc0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180013cc0`
- `KERNEL32!SetThreadpoolTimer` at `0x180013d97`
- `KERNEL32!SetThreadpoolTimer` at `0x180013d97`
- `KERNEL32!CreateThreadpoolTimer` at `0x180013d51`
- `KERNEL32!CreateThreadpoolTimer` at `0x180013d51`
- `KERNEL32!GetLastError` at `0x180013d36`
- `KERNEL32!GetLastError` at `0x180013d36`
- `KERNEL32!SetLastError` at `0x180013d6b`
- `KERNEL32!SetLastError` at `0x180013d6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180013c64  push    rbx
0x180013c66  push    rbp
0x180013c67  push    rsi
0x180013c68  push    rdi
0x180013c69  push    r14
0x180013c6b  sub     rsp, 40h
0x180013c6f  mov     rax, cs:__security_cookie
0x180013c76  xor     rax, rsp
0x180013c79  mov     [rsp+68h+var_30], rax
0x180013c7e  mov     r14d, r9d
0x180013c81  movzx   esi, r8w
0x180013c85  mov     ebx, edx
0x180013c87  mov     rdi, rcx
0x180013c8a  cmp     byte ptr [rcx], 0
0x180013c8d  jz      loc_180013DBC
0x180013c93  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180013c9a  jnz     loc_180013DBC
0x180013ca0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180013ca7  test    rax, rax
0x180013caa  jz      short loc_180013CB9
0x180013cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cb1  test    al, al
0x180013cb3  jnz     loc_180013DBC
0x180013cb9  lea     rbp, [rdi+28h]
0x180013cbd  mov     rcx, rbp; SRWLock
0x180013cc0  call    cs:__imp_AcquireSRWLockExclusive
0x180013cc7  nop     dword ptr [rax+rax+00h]
0x180013ccc  xor     eax, eax
0x180013cce  mov     [rsp+68h+var_3A], ax
0x180013cd3  mov     [rsp+68h+Source], ebx
0x180013cd7  mov     [rsp+68h+var_3C], si
0x180013cdc  mov     [rsp+68h+var_38], r14d
0x180013ce1  lea     rbx, [rdi+0E8h]
0x180013ce8  lea     esi, [rax+0Ch]
0x180013ceb  mov     edx, esi; unsigned __int64
0x180013ced  mov     rcx, rbx; this
0x180013cf0  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180013cf5  test    al, al
0x180013cf7  jz      short loc_180013D26
0x180013cf9  mov     rcx, [rbx+8]; Destination
0x180013cfd  mov     rax, [rbx+10h]
0x180013d01  sub     rax, rcx
0x180013d04  cmp     rcx, [rbx+10h]
0x180013d08  sbb     rdx, rdx
0x180013d0b  and     rdx, rax; DestinationSize
0x180013d0e  mov     r9d, esi; SourceSize
0x180013d11  lea     r8, [rsp+68h+Source]; Source
0x180013d16  call    cs:__imp_memcpy_s
0x180013d1d  nop     dword ptr [rax+rax+00h]
0x180013d22  add     [rbx+8], rsi
0x180013d26  cmp     byte ptr [rdi+40h], 0
0x180013d2a  jnz     short loc_180013DA7
0x180013d2c  lea     rsi, [rdi+38h]
0x180013d30  cmp     qword ptr [rsi], 0
0x180013d34  jnz     short loc_180013D78
0x180013d36  call    cs:__imp_GetLastError
0x180013d3d  nop     dword ptr [rax+rax+00h]
0x180013d42  mov     ebx, eax
0x180013d44  xor     r8d, r8d; pcbe
0x180013d47  mov     rdx, rdi; pv
0x180013d4a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180013d51  call    cs:__imp_CreateThreadpoolTimer
0x180013d58  nop     dword ptr [rax+rax+00h]
0x180013d5d  mov     rdx, rax
0x180013d60  mov     rcx, rsi
0x180013d63  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180013d68  nop
0x180013d69  mov     ecx, ebx; dwErrCode
0x180013d6b  call    cs:__imp_SetLastError
0x180013d72  nop     dword ptr [rax+rax+00h]
0x180013d77  nop
0x180013d78  mov     rcx, [rsi]; pti
0x180013d7b  test    rcx, rcx
0x180013d7e  jz      short loc_180013DA7
0x180013d80  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180013d89  mov     r9d, 4E2h; msWindowLength
0x180013d8f  xor     r8d, r8d; msPeriod
0x180013d92  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180013d97  call    cs:__imp_SetThreadpoolTimer
0x180013d9e  nop     dword ptr [rax+rax+00h]
0x180013da3  mov     byte ptr [rdi+40h], 1
0x180013da7  test    rbp, rbp
0x180013daa  jz      short loc_180013DBC
0x180013dac  mov     rcx, rbp; SRWLock
0x180013daf  call    cs:__imp_ReleaseSRWLockExclusive
0x180013db6  nop     dword ptr [rax+rax+00h]
0x180013dbb  nop
0x180013dbc  mov     rcx, [rsp+68h+var_30]
0x180013dc1  xor     rcx, rsp; StackCookie
0x180013dc4  call    __security_check_cookie
0x180013dc9  add     rsp, 40h
0x180013dcd  pop     r14
0x180013dcf  pop     rdi
0x180013dd0  pop     rsi
0x180013dd1  pop     rbp
0x180013dd2  pop     rbx
0x180013dd3  retn
```
