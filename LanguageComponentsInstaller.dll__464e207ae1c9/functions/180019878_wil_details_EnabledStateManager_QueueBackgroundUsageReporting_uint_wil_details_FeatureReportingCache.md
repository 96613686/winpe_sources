# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x180019878`
- end: `0x18001998e`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `278`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001b218`

## callees

- `0x180004086`
- `0x180004118`
- `0x180016124`
- `0x180019878`
- `0x180021e9c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180019928`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180019950`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180019928`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180019950`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019976`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019976`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800198c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800198c8`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rdx
  _DWORD *Ptr; // rcx
  size_t v8; // r8

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
    {
      goto LABEL_18;
    }
    if ( !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&pv[4], 0x10u) )
    {
LABEL_17:
      wil::details::EnabledStateManager::EnsureTimerUnderLock((struct _TP_TIMER **)pv);
LABEL_18:
      if ( pv != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(pv + 1);
      return;
    }
    Ptr = pv[5].Ptr;
    v8 = ((char *)pv[6].Ptr - (char *)Ptr) & -(__int64)(Ptr < pv[6].Ptr);
    if ( Ptr )
    {
      if ( v8 >= 0x10 )
      {
        *Ptr = a2;
        Ptr[1] = 0;
        *((_QWORD *)Ptr + 1) = a3;
LABEL_16:
        pv[5].Ptr = (char *)pv[5].Ptr + 16;
        goto LABEL_17;
      }
      memset_0(Ptr, 0, v8);
      *(_DWORD *)((__int64 (*)(void))_o__errno)() = 34;
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
0x180019878  mov     [rsp+arg_18], rbx
0x18001987d  push    rbp
0x18001987e  push    rsi
0x18001987f  push    rdi
0x180019880  push    r14
0x180019882  push    r15
0x180019884  sub     rsp, 20h
0x180019888  mov     rbp, r8
0x18001988b  mov     r14d, edx
0x18001988e  mov     rdi, rcx
0x180019891  mov     eax, [rcx]
0x180019893  test    eax, eax
0x180019895  jz      loc_18001997D
0x18001989b  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800198a2  jnz     loc_18001997D
0x1800198a8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800198af  test    rax, rax
0x1800198b2  jz      short loc_1800198C1
0x1800198b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198b9  test    al, al
0x1800198bb  jnz     loc_18001997D
0x1800198c1  lea     rbx, [rdi+8]
0x1800198c5  mov     rcx, rbx; SRWLock
0x1800198c8  call    cs:__imp_AcquireSRWLockExclusive
0x1800198ce  mov     eax, [rdi]
0x1800198d0  test    eax, eax
0x1800198d2  jz      loc_18001996E
0x1800198d8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800198df  jnz     loc_18001996E
0x1800198e5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800198ec  test    rax, rax
0x1800198ef  jz      short loc_1800198FA
0x1800198f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198f6  test    al, al
0x1800198f8  jnz     short loc_18001996E
0x1800198fa  xor     r15d, r15d
0x1800198fd  lea     edx, [r15+10h]; unsigned __int64
0x180019901  lea     rcx, [rdi+20h]; this
0x180019905  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001990a  test    al, al
0x18001990c  jz      short loc_180019966
0x18001990e  mov     rcx, [rdi+28h]; void *
0x180019912  mov     rax, [rdi+30h]
0x180019916  sub     rax, rcx
0x180019919  cmp     rcx, [rdi+30h]
0x18001991d  sbb     r8, r8
0x180019920  and     r8, rax; Size
0x180019923  test    rcx, rcx
0x180019926  jnz     short loc_180019936
0x180019928  call    cs:__imp__o__errno
0x18001992e  mov     dword ptr [rax], 16h
0x180019934  jmp     short loc_18001995C
0x180019936  cmp     r8, 10h
0x18001993a  jb      short loc_180019949
0x18001993c  mov     [rcx], r14d
0x18001993f  mov     [rcx+4], r15d
0x180019943  mov     [rcx+8], rbp
0x180019947  jmp     short loc_180019961
0x180019949  xor     edx, edx; Val
0x18001994b  call    memset_0
0x180019950  call    cs:__imp__o__errno
0x180019956  mov     dword ptr [rax], 22h ; '"'
0x18001995c  call    _invalid_parameter_noinfo
0x180019961  add     qword ptr [rdi+28h], 10h
0x180019966  mov     rcx, rdi; pv
0x180019969  call    ?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::EnsureTimerUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18001996e  test    rbx, rbx
0x180019971  jz      short loc_18001997D
0x180019973  mov     rcx, rbx; SRWLock
0x180019976  call    cs:__imp_ReleaseSRWLockExclusive
0x18001997c  nop
0x18001997d  mov     rbx, [rsp+48h+arg_18]
0x180019982  add     rsp, 20h
0x180019986  pop     r15
0x180019988  pop     r14
0x18001998a  pop     rdi
0x18001998b  pop     rsi
0x18001998c  pop     rbp
0x18001998d  retn
```
