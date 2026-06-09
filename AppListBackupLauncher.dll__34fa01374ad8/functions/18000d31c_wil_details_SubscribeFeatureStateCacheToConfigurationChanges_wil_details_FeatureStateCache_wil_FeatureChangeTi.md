# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000d31c`
- end: `0x18000d420`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007d94`
- `0x180007e74`
- `0x180007fe8`
- `0x180009108`

## callees

- `0x180002d6a`
- `0x180002de0`
- `0x18000d31c`
- `0x18000eb4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d3ad`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d3d7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d3ad`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d3d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d40a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d40a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d348`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d348`

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
      || a3 != dword_1800196D4
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800196F8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180019708 - (_QWORD)qword_180019700) & -(__int64)((unsigned __int64)qword_180019700 < qword_180019708);
    if ( qword_180019700 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180019700 = v12;
LABEL_11:
        qword_180019700 = (char *)qword_180019700 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180019700, 0, v8);
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
0x18000d31c  mov     [rsp+arg_0], rbx
0x18000d321  mov     [rsp+arg_8], rsi
0x18000d326  push    rdi
0x18000d327  sub     rsp, 30h
0x18000d32b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000d331  mov     esi, r8d
0x18000d334  mov     ebx, edx
0x18000d336  mov     rdi, rcx
0x18000d339  test    eax, eax
0x18000d33b  jz      loc_18000D410
0x18000d341  lea     rcx, SRWLock; SRWLock
0x18000d348  call    cs:__imp_AcquireSRWLockExclusive
0x18000d34e  mov     eax, cs:dword_1800196D4
0x18000d354  test    esi, esi
0x18000d356  jz      loc_18000D3F2
0x18000d35c  cmp     esi, eax
0x18000d35e  jnz     loc_18000D3F2
0x18000d364  mov     edx, 10h; unsigned __int64
0x18000d369  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000d371  lea     rcx, qword_1800196F8; this
0x18000d378  mov     dword ptr [rsp+38h+var_18], ebx
0x18000d37c  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000d381  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000d386  test    al, al
0x18000d388  jz      short loc_18000D3F2
0x18000d38a  mov     r9, cs:qword_180019700
0x18000d391  mov     rax, cs:qword_180019708
0x18000d398  sub     rax, r9
0x18000d39b  cmp     r9, cs:qword_180019708
0x18000d3a2  sbb     r8, r8
0x18000d3a5  and     r8, rax; Size
0x18000d3a8  test    r9, r9
0x18000d3ab  jnz     short loc_18000D3BB
0x18000d3ad  call    cs:__imp__o__errno
0x18000d3b3  mov     dword ptr [rax], 16h
0x18000d3b9  jmp     short loc_18000D3E3
0x18000d3bb  cmp     r8, 10h
0x18000d3bf  jb      short loc_18000D3CD
0x18000d3c1  movups  xmm0, [rsp+38h+var_18]
0x18000d3c6  movdqu  xmmword ptr [r9], xmm0
0x18000d3cb  jmp     short loc_18000D3E8
0x18000d3cd  xor     edx, edx; Val
0x18000d3cf  mov     rcx, r9; void *
0x18000d3d2  call    memset_0
0x18000d3d7  call    cs:__imp__o__errno
0x18000d3dd  mov     dword ptr [rax], 22h ; '"'
0x18000d3e3  call    _invalid_parameter_noinfo
0x18000d3e8  add     cs:qword_180019700, 10h
0x18000d3f0  jmp     short loc_18000D403
0x18000d3f2  neg     ebx
0x18000d3f4  sbb     eax, eax
0x18000d3f6  and     eax, 83Ah
0x18000d3fb  add     eax, 0FFFFF7C1h
0x18000d400  lock and [rdi], eax
0x18000d403  lea     rcx, SRWLock; SRWLock
0x18000d40a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d410  mov     rbx, [rsp+38h+arg_0]
0x18000d415  mov     rsi, [rsp+38h+arg_8]
0x18000d41a  add     rsp, 30h
0x18000d41e  pop     rdi
0x18000d41f  retn
```
