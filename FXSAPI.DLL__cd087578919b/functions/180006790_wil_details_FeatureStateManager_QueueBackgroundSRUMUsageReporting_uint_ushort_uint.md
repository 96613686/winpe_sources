# wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)

- ea: `0x180006790`
- end: `0x1800068ff`
- name: `?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z`
- size: `367`
- prototype: `void __fastcall(PVOID pv, unsigned int, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180009060`

## callees

- `0x180006790`
- `0x18000971c`
- `0x18000981c`
- `0x18003d510`
- `0x18003e010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006842`
- `msvcrt!memcpy_s` at `0x180006842`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000687d`
- `KERNEL32!CreateThreadpoolTimer` at `0x18000687d`
- `KERNEL32!SetThreadpoolTimer` at `0x1800068c1`
- `KERNEL32!SetThreadpoolTimer` at `0x1800068c1`
- `KERNEL32!SetLastError` at `0x180006896`
- `KERNEL32!SetLastError` at `0x180006896`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800068d9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800068d9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800067ec`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800067ec`
- `KERNEL32!GetLastError` at `0x180006862`
- `KERNEL32!GetLastError` at `0x180006862`

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
0x180006790  push    rbx
0x180006792  push    rbp
0x180006793  push    rsi
0x180006794  push    rdi
0x180006795  push    r14
0x180006797  sub     rsp, 40h
0x18000679b  mov     rax, cs:__security_cookie
0x1800067a2  xor     rax, rsp
0x1800067a5  mov     [rsp+68h+var_30], rax
0x1800067aa  mov     r14d, r9d
0x1800067ad  movzx   esi, r8w
0x1800067b1  mov     ebx, edx
0x1800067b3  mov     rdi, rcx
0x1800067b6  cmp     byte ptr [rcx], 0
0x1800067b9  jz      loc_1800068E6
0x1800067bf  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800067c6  jnz     loc_1800068E6
0x1800067cc  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800067d3  test    rax, rax
0x1800067d6  jz      short loc_1800067E5
0x1800067d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067dd  test    al, al
0x1800067df  jnz     loc_1800068E6
0x1800067e5  lea     rbp, [rdi+28h]
0x1800067e9  mov     rcx, rbp; SRWLock
0x1800067ec  call    cs:__imp_AcquireSRWLockExclusive
0x1800067f3  nop     dword ptr [rax+rax+00h]
0x1800067f8  xor     eax, eax
0x1800067fa  mov     [rsp+68h+var_3A], ax
0x1800067ff  mov     [rsp+68h+Source], ebx
0x180006803  mov     [rsp+68h+var_3C], si
0x180006808  mov     [rsp+68h+var_38], r14d
0x18000680d  lea     rbx, [rdi+0E8h]
0x180006814  lea     esi, [rax+0Ch]
0x180006817  mov     edx, esi; unsigned __int64
0x180006819  mov     rcx, rbx; this
0x18000681c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006821  test    al, al
0x180006823  jz      short loc_180006852
0x180006825  mov     rcx, [rbx+8]; Destination
0x180006829  mov     rax, [rbx+10h]
0x18000682d  sub     rax, rcx
0x180006830  cmp     rcx, [rbx+10h]
0x180006834  sbb     rdx, rdx
0x180006837  and     rdx, rax; DestinationSize
0x18000683a  mov     r9d, esi; SourceSize
0x18000683d  lea     r8, [rsp+68h+Source]; Source
0x180006842  call    cs:__imp_memcpy_s
0x180006849  nop     dword ptr [rax+rax+00h]
0x18000684e  add     [rbx+8], rsi
0x180006852  cmp     byte ptr [rdi+40h], 0
0x180006856  jnz     short loc_1800068D1
0x180006858  lea     rsi, [rdi+38h]
0x18000685c  cmp     qword ptr [rsi], 0
0x180006860  jnz     short loc_1800068A2
0x180006862  call    cs:__imp_GetLastError
0x180006869  nop     dword ptr [rax+rax+00h]
0x18000686e  mov     ebx, eax
0x180006870  xor     r8d, r8d; pcbe
0x180006873  mov     rdx, rdi; pv
0x180006876  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5035b992506f4af81a770c5842624510_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000687d  call    cs:__imp_CreateThreadpoolTimer
0x180006884  nop     dword ptr [rax+rax+00h]
0x180006889  mov     rdx, rax
0x18000688c  mov     rcx, rsi
0x18000688f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180006894  mov     ecx, ebx; dwErrCode
0x180006896  call    cs:__imp_SetLastError
0x18000689d  nop     dword ptr [rax+rax+00h]
0x1800068a2  mov     rcx, [rsi]; pti
0x1800068a5  test    rcx, rcx
0x1800068a8  jz      short loc_1800068D1
0x1800068aa  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x1800068b3  mov     r9d, 4E2h; msWindowLength
0x1800068b9  xor     r8d, r8d; msPeriod
0x1800068bc  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1800068c1  call    cs:__imp_SetThreadpoolTimer
0x1800068c8  nop     dword ptr [rax+rax+00h]
0x1800068cd  mov     byte ptr [rdi+40h], 1
0x1800068d1  test    rbp, rbp
0x1800068d4  jz      short loc_1800068E6
0x1800068d6  mov     rcx, rbp; SRWLock
0x1800068d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800068e0  nop     dword ptr [rax+rax+00h]
0x1800068e5  nop
0x1800068e6  mov     rcx, [rsp+68h+var_30]
0x1800068eb  xor     rcx, rsp; StackCookie
0x1800068ee  call    __security_check_cookie
0x1800068f3  add     rsp, 40h
0x1800068f7  pop     r14
0x1800068f9  pop     rdi
0x1800068fa  pop     rsi
0x1800068fb  pop     rbp
0x1800068fc  pop     rbx
0x1800068fd  retn
```
