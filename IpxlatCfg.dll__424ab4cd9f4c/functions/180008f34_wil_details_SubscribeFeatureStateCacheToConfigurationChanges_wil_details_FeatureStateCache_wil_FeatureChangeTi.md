# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180008f34`
- end: `0x180009038`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `17`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006594`
- `0x18000a550`
- `0x18000a714`
- `0x18000a8e8`
- `0x18000b648`
- `0x18000d10c`
- `0x18000ff68`
- `0x18001013c`
- `0x180010310`
- `0x1800104e4`
- `0x1800106b8`
- `0x180013830`
- `0x180013a04`
- `0x180013bd8`
- `0x180013cb8`
- `0x180013e8c`
- `0x180014060`

## callees

- `0x1800029ca`
- `0x180002a28`
- `0x180008f34`
- `0x180009d1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008fc5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008fef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008fc5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008fef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008f60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008f60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009022`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009022`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        unsigned int a2,
        int a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  size_t v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int128 v12; // [rsp+20h] [rbp-18h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_180023434
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180023458, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180023468 - (_QWORD)qword_180023460) & -(__int64)((unsigned __int64)qword_180023460 < qword_180023468);
    if ( qword_180023460 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180023460 = v12;
LABEL_11:
        qword_180023460 = (char *)qword_180023460 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180023460, 0, v8);
      *(_DWORD *)_o__errno(v10, v9, v11) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v7, v6, v8) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x180008f34  mov     [rsp+arg_0], rbx
0x180008f39  mov     [rsp+arg_8], rsi
0x180008f3e  push    rdi
0x180008f3f  sub     rsp, 30h
0x180008f43  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008f49  mov     esi, r8d
0x180008f4c  mov     ebx, edx
0x180008f4e  mov     rdi, rcx
0x180008f51  test    eax, eax
0x180008f53  jz      loc_180009028
0x180008f59  lea     rcx, SRWLock; SRWLock
0x180008f60  call    cs:__imp_AcquireSRWLockExclusive
0x180008f66  mov     eax, cs:dword_180023434
0x180008f6c  test    esi, esi
0x180008f6e  jz      loc_18000900A
0x180008f74  cmp     esi, eax
0x180008f76  jnz     loc_18000900A
0x180008f7c  mov     edx, 10h; unsigned __int64
0x180008f81  mov     dword ptr [rsp+38h+var_18+4], 0
0x180008f89  lea     rcx, qword_180023458; this
0x180008f90  mov     dword ptr [rsp+38h+var_18], ebx
0x180008f94  mov     qword ptr [rsp+38h+var_18+8], rdi
0x180008f99  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008f9e  test    al, al
0x180008fa0  jz      short loc_18000900A
0x180008fa2  mov     r9, cs:qword_180023460
0x180008fa9  mov     rax, cs:qword_180023468
0x180008fb0  sub     rax, r9
0x180008fb3  cmp     r9, cs:qword_180023468
0x180008fba  sbb     r8, r8
0x180008fbd  and     r8, rax; Size
0x180008fc0  test    r9, r9
0x180008fc3  jnz     short loc_180008FD3
0x180008fc5  call    cs:__imp__o__errno
0x180008fcb  mov     dword ptr [rax], 16h
0x180008fd1  jmp     short loc_180008FFB
0x180008fd3  cmp     r8, 10h
0x180008fd7  jb      short loc_180008FE5
0x180008fd9  movups  xmm0, [rsp+38h+var_18]
0x180008fde  movdqu  xmmword ptr [r9], xmm0
0x180008fe3  jmp     short loc_180009000
0x180008fe5  xor     edx, edx; Val
0x180008fe7  mov     rcx, r9; void *
0x180008fea  call    memset_0
0x180008fef  call    cs:__imp__o__errno
0x180008ff5  mov     dword ptr [rax], 22h ; '"'
0x180008ffb  call    _invalid_parameter_noinfo
0x180009000  add     cs:qword_180023460, 10h
0x180009008  jmp     short loc_18000901B
0x18000900a  neg     ebx
0x18000900c  sbb     eax, eax
0x18000900e  and     eax, 83Ah
0x180009013  add     eax, 0FFFFF7C1h
0x180009018  lock and [rdi], eax
0x18000901b  lea     rcx, SRWLock; SRWLock
0x180009022  call    cs:__imp_ReleaseSRWLockExclusive
0x180009028  mov     rbx, [rsp+38h+arg_0]
0x18000902d  mov     rsi, [rsp+38h+arg_8]
0x180009032  add     rsp, 30h
0x180009036  pop     rdi
0x180009037  retn
```
