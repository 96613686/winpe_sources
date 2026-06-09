# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x14006eaf0`
- end: `0x14006ec5f`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `367`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140071080`

## callees

- `0x14006eaf0`
- `0x1400716b8`
- `0x1400717b8`
- `0x140086ec0`
- `0x14008b010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x14006ebdd`
- `KERNEL32!CreateThreadpoolTimer` at `0x14006ebdd`
- `KERNEL32!SetThreadpoolTimer` at `0x14006ec21`
- `KERNEL32!SetThreadpoolTimer` at `0x14006ec21`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14006eb4c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14006eb4c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14006ec39`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14006ec39`
- `KERNEL32!GetLastError` at `0x14006ebc2`
- `KERNEL32!GetLastError` at `0x14006ebc2`
- `KERNEL32!SetLastError` at `0x14006ebf6`
- `KERNEL32!SetLastError` at `0x14006ebf6`
- `msvcrt!memcpy_s` at `0x14006eba2`
- `msvcrt!memcpy_s` at `0x14006eba2`

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
0x14006eaf0  push    rbx
0x14006eaf2  push    rbp
0x14006eaf3  push    rsi
0x14006eaf4  push    rdi
0x14006eaf5  push    r14
0x14006eaf7  sub     rsp, 40h
0x14006eafb  mov     rax, cs:__security_cookie
0x14006eb02  xor     rax, rsp
0x14006eb05  mov     [rsp+68h+var_30], rax
0x14006eb0a  mov     r14d, r9d
0x14006eb0d  movzx   esi, r8w
0x14006eb11  mov     ebx, edx
0x14006eb13  mov     rdi, rcx
0x14006eb16  cmp     byte ptr [rcx], 0
0x14006eb19  jz      loc_14006EC46
0x14006eb1f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14006eb26  jnz     loc_14006EC46
0x14006eb2c  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14006eb33  test    rax, rax
0x14006eb36  jz      short loc_14006EB45
0x14006eb38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006eb3d  test    al, al
0x14006eb3f  jnz     loc_14006EC46
0x14006eb45  lea     rbp, [rdi+28h]
0x14006eb49  mov     rcx, rbp; SRWLock
0x14006eb4c  call    cs:__imp_AcquireSRWLockExclusive
0x14006eb53  nop     dword ptr [rax+rax+00h]
0x14006eb58  xor     eax, eax
0x14006eb5a  mov     [rsp+68h+var_3A], ax
0x14006eb5f  mov     [rsp+68h+Source], ebx
0x14006eb63  mov     [rsp+68h+var_3C], si
0x14006eb68  mov     [rsp+68h+var_38], r14d
0x14006eb6d  lea     rbx, [rdi+0E8h]
0x14006eb74  lea     esi, [rax+0Ch]
0x14006eb77  mov     edx, esi; unsigned __int64
0x14006eb79  mov     rcx, rbx; this
0x14006eb7c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14006eb81  test    al, al
0x14006eb83  jz      short loc_14006EBB2
0x14006eb85  mov     rcx, [rbx+8]; Destination
0x14006eb89  mov     rax, [rbx+10h]
0x14006eb8d  sub     rax, rcx
0x14006eb90  cmp     rcx, [rbx+10h]
0x14006eb94  sbb     rdx, rdx
0x14006eb97  and     rdx, rax; DestinationSize
0x14006eb9a  mov     r9d, esi; SourceSize
0x14006eb9d  lea     r8, [rsp+68h+Source]; Source
0x14006eba2  call    cs:__imp_memcpy_s
0x14006eba9  nop     dword ptr [rax+rax+00h]
0x14006ebae  add     [rbx+8], rsi
0x14006ebb2  cmp     byte ptr [rdi+40h], 0
0x14006ebb6  jnz     short loc_14006EC31
0x14006ebb8  lea     rsi, [rdi+38h]
0x14006ebbc  cmp     qword ptr [rsi], 0
0x14006ebc0  jnz     short loc_14006EC02
0x14006ebc2  call    cs:__imp_GetLastError
0x14006ebc9  nop     dword ptr [rax+rax+00h]
0x14006ebce  mov     ebx, eax
0x14006ebd0  xor     r8d, r8d; pcbe
0x14006ebd3  mov     rdx, rdi; pv
0x14006ebd6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14006ebdd  call    cs:__imp_CreateThreadpoolTimer
0x14006ebe4  nop     dword ptr [rax+rax+00h]
0x14006ebe9  mov     rdx, rax
0x14006ebec  mov     rcx, rsi
0x14006ebef  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14006ebf4  mov     ecx, ebx; dwErrCode
0x14006ebf6  call    cs:__imp_SetLastError
0x14006ebfd  nop     dword ptr [rax+rax+00h]
0x14006ec02  mov     rcx, [rsi]; pti
0x14006ec05  test    rcx, rcx
0x14006ec08  jz      short loc_14006EC31
0x14006ec0a  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x14006ec13  mov     r9d, 4E2h; msWindowLength
0x14006ec19  xor     r8d, r8d; msPeriod
0x14006ec1c  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x14006ec21  call    cs:__imp_SetThreadpoolTimer
0x14006ec28  nop     dword ptr [rax+rax+00h]
0x14006ec2d  mov     byte ptr [rdi+40h], 1
0x14006ec31  test    rbp, rbp
0x14006ec34  jz      short loc_14006EC46
0x14006ec36  mov     rcx, rbp; SRWLock
0x14006ec39  call    cs:__imp_ReleaseSRWLockExclusive
0x14006ec40  nop     dword ptr [rax+rax+00h]
0x14006ec45  nop
0x14006ec46  mov     rcx, [rsp+68h+var_30]
0x14006ec4b  xor     rcx, rsp; StackCookie
0x14006ec4e  call    __security_check_cookie
0x14006ec53  add     rsp, 40h
0x14006ec57  pop     r14
0x14006ec59  pop     rdi
0x14006ec5a  pop     rsi
0x14006ec5b  pop     rbp
0x14006ec5c  pop     rbx
0x14006ec5d  retn
```
