# wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)

- ea: `0x18001cfe4`
- end: `0x18001d104`
- name: `?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z`
- size: `288`
- prototype: `void __fastcall(RTL_SRWLOCK *pv, int, struct wil_details_FeatureReportingCache *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001ec00`

## callees

- `0x18000422a`
- `0x1800042f4`
- `0x18000c0cc`
- `0x180015c7c`
- `0x18001cfe4`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d09e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d0c6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d09e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d0c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d03e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d03e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d0ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d0ec`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
        RTL_SRWLOCK *pv,
        int a2,
        struct wil_details_FeatureReportingCache *a3)
{
  __int64 v6; // rcx
  _DWORD *Ptr; // rcx
  size_t v8; // r8
  __int64 v9; // rcx

  if ( LODWORD(pv->Ptr)
    && !wil::details::g_processShutdownInProgress
    && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress(pv)) )
  {
    AcquireSRWLockExclusive(pv + 1);
    if ( !LODWORD(pv->Ptr)
      || wil::details::g_processShutdownInProgress
      || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress(v6) )
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
      *(_DWORD *)_o__errno(v9) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(0) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_16;
  }
}

```

## disassembly

```asm
0x18001cfe4  push    rbp
0x18001cfe6  push    rsi
0x18001cfe7  push    rdi
0x18001cfe8  push    r14
0x18001cfea  push    r15
0x18001cfec  sub     rsp, 30h
0x18001cff0  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18001cff9  mov     [rsp+58h+arg_18], rbx
0x18001cffe  mov     rbp, r8
0x18001d001  mov     r14d, edx
0x18001d004  mov     rdi, rcx
0x18001d007  mov     eax, [rcx]
0x18001d009  test    eax, eax
0x18001d00b  jz      loc_18001D0F3
0x18001d011  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001d018  jnz     loc_18001D0F3
0x18001d01e  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d025  test    rax, rax
0x18001d028  jz      short loc_18001D037
0x18001d02a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d02f  test    al, al
0x18001d031  jnz     loc_18001D0F3
0x18001d037  lea     rbx, [rdi+8]
0x18001d03b  mov     rcx, rbx; SRWLock
0x18001d03e  call    cs:__imp_AcquireSRWLockExclusive
0x18001d044  mov     eax, [rdi]
0x18001d046  test    eax, eax
0x18001d048  jz      loc_18001D0E4
0x18001d04e  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001d055  jnz     loc_18001D0E4
0x18001d05b  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001d062  test    rax, rax
0x18001d065  jz      short loc_18001D070
0x18001d067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d06c  test    al, al
0x18001d06e  jnz     short loc_18001D0E4
0x18001d070  xor     r15d, r15d
0x18001d073  lea     edx, [r15+10h]; unsigned __int64
0x18001d077  lea     rcx, [rdi+20h]; this
0x18001d07b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001d080  test    al, al
0x18001d082  jz      short loc_18001D0DC
0x18001d084  mov     rcx, [rdi+28h]; void *
0x18001d088  mov     rax, [rdi+30h]
0x18001d08c  sub     rax, rcx
0x18001d08f  cmp     rcx, [rdi+30h]
0x18001d093  sbb     r8, r8
0x18001d096  and     r8, rax; Size
0x18001d099  test    rcx, rcx
0x18001d09c  jnz     short loc_18001D0AC
0x18001d09e  call    cs:__imp__o__errno
0x18001d0a4  mov     dword ptr [rax], 16h
0x18001d0aa  jmp     short loc_18001D0D2
0x18001d0ac  cmp     r8, 10h
0x18001d0b0  jb      short loc_18001D0BF
0x18001d0b2  mov     [rcx], r14d
0x18001d0b5  mov     [rcx+4], r15d
0x18001d0b9  mov     [rcx+8], rbp
0x18001d0bd  jmp     short loc_18001D0D7
0x18001d0bf  xor     edx, edx; Val
0x18001d0c1  call    memset_0
0x18001d0c6  call    cs:__imp__o__errno
0x18001d0cc  mov     dword ptr [rax], 22h ; '"'
0x18001d0d2  call    _invalid_parameter_noinfo
0x18001d0d7  add     qword ptr [rdi+28h], 10h
0x18001d0dc  mov     rcx, rdi; pv
0x18001d0df  call    ?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z; wil::details::EnabledStateManager::EnsureTimerUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)
0x18001d0e4  test    rbx, rbx
0x18001d0e7  jz      short loc_18001D0F3
0x18001d0e9  mov     rcx, rbx; SRWLock
0x18001d0ec  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d0f2  nop
0x18001d0f3  mov     rbx, [rsp+58h+arg_18]
0x18001d0f8  add     rsp, 30h
0x18001d0fc  pop     r15
0x18001d0fe  pop     r14
0x18001d100  pop     rdi
0x18001d101  pop     rsi
0x18001d102  pop     rbp
0x18001d103  retn
```
