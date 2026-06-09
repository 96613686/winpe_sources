# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180008344`
- end: `0x180008448`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `23`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005b54`
- `0x18000a6a0`
- `0x180012e80`
- `0x180012f60`
- `0x180013040`
- `0x180013120`
- `0x180013200`
- `0x180013380`
- `0x1800134f4`
- `0x180013668`
- `0x1800137dc`
- `0x180013950`
- `0x180013ac4`
- `0x180013c38`
- `0x180013d18`
- `0x180013df8`
- `0x180013ed8`
- `0x180013fb8`
- `0x180014098`
- `0x180014218`
- `0x1800142f8`
- `0x180018adc`
- `0x180023fdc`

## callees

- `0x180002766`
- `0x1800027c8`
- `0x180008344`
- `0x18000911c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800083d5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800083ff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800083d5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800083ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008432`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008432`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008370`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008370`

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
      || a3 != dword_180033334
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180033358, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180033368 - (_QWORD)qword_180033360) & -(__int64)((unsigned __int64)qword_180033360 < qword_180033368);
    if ( qword_180033360 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180033360 = v12;
LABEL_11:
        qword_180033360 = (char *)qword_180033360 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180033360, 0, v8);
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
0x180008344  mov     [rsp+arg_0], rbx
0x180008349  mov     [rsp+arg_8], rsi
0x18000834e  push    rdi
0x18000834f  sub     rsp, 30h
0x180008353  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008359  mov     esi, r8d
0x18000835c  mov     ebx, edx
0x18000835e  mov     rdi, rcx
0x180008361  test    eax, eax
0x180008363  jz      loc_180008438
0x180008369  lea     rcx, SRWLock; SRWLock
0x180008370  call    cs:__imp_AcquireSRWLockExclusive
0x180008376  mov     eax, cs:dword_180033334
0x18000837c  test    esi, esi
0x18000837e  jz      loc_18000841A
0x180008384  cmp     esi, eax
0x180008386  jnz     loc_18000841A
0x18000838c  mov     edx, 10h; unsigned __int64
0x180008391  mov     dword ptr [rsp+38h+var_18+4], 0
0x180008399  lea     rcx, qword_180033358; this
0x1800083a0  mov     dword ptr [rsp+38h+var_18], ebx
0x1800083a4  mov     qword ptr [rsp+38h+var_18+8], rdi
0x1800083a9  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800083ae  test    al, al
0x1800083b0  jz      short loc_18000841A
0x1800083b2  mov     r9, cs:qword_180033360
0x1800083b9  mov     rax, cs:qword_180033368
0x1800083c0  sub     rax, r9
0x1800083c3  cmp     r9, cs:qword_180033368
0x1800083ca  sbb     r8, r8
0x1800083cd  and     r8, rax; Size
0x1800083d0  test    r9, r9
0x1800083d3  jnz     short loc_1800083E3
0x1800083d5  call    cs:__imp__o__errno
0x1800083db  mov     dword ptr [rax], 16h
0x1800083e1  jmp     short loc_18000840B
0x1800083e3  cmp     r8, 10h
0x1800083e7  jb      short loc_1800083F5
0x1800083e9  movups  xmm0, [rsp+38h+var_18]
0x1800083ee  movdqu  xmmword ptr [r9], xmm0
0x1800083f3  jmp     short loc_180008410
0x1800083f5  xor     edx, edx; Val
0x1800083f7  mov     rcx, r9; void *
0x1800083fa  call    memset_0
0x1800083ff  call    cs:__imp__o__errno
0x180008405  mov     dword ptr [rax], 22h ; '"'
0x18000840b  call    _invalid_parameter_noinfo
0x180008410  add     cs:qword_180033360, 10h
0x180008418  jmp     short loc_18000842B
0x18000841a  neg     ebx
0x18000841c  sbb     eax, eax
0x18000841e  and     eax, 83Ah
0x180008423  add     eax, 0FFFFF7C1h
0x180008428  lock and [rdi], eax
0x18000842b  lea     rcx, SRWLock; SRWLock
0x180008432  call    cs:__imp_ReleaseSRWLockExclusive
0x180008438  mov     rbx, [rsp+38h+arg_0]
0x18000843d  mov     rsi, [rsp+38h+arg_8]
0x180008442  add     rsp, 30h
0x180008446  pop     rdi
0x180008447  retn
```
