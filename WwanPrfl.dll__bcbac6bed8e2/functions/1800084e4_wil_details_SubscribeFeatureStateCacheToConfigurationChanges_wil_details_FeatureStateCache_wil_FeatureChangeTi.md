# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800084e4`
- end: `0x1800085e8`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004b44`
- `0x1800058c4`

## callees

- `0x180001fca`
- `0x180002034`
- `0x1800084e4`
- `0x18000d5fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008575`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000859f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008575`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000859f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800085d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800085d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008510`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008510`

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
      || a3 != dword_18001F41C
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18001F440, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_18001F450 - (_QWORD)qword_18001F448) & -(__int64)((unsigned __int64)qword_18001F448 < qword_18001F450);
    if ( qword_18001F448 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_18001F448 = v12;
LABEL_11:
        qword_18001F448 = (char *)qword_18001F448 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_18001F448, 0, v8);
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
0x1800084e4  mov     [rsp+arg_0], rbx
0x1800084e9  mov     [rsp+arg_8], rsi
0x1800084ee  push    rdi
0x1800084ef  sub     rsp, 30h
0x1800084f3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800084f9  mov     esi, r8d
0x1800084fc  mov     ebx, edx
0x1800084fe  mov     rdi, rcx
0x180008501  test    eax, eax
0x180008503  jz      loc_1800085D8
0x180008509  lea     rcx, SRWLock; SRWLock
0x180008510  call    cs:__imp_AcquireSRWLockExclusive
0x180008516  mov     eax, cs:dword_18001F41C
0x18000851c  test    esi, esi
0x18000851e  jz      loc_1800085BA
0x180008524  cmp     esi, eax
0x180008526  jnz     loc_1800085BA
0x18000852c  mov     edx, 10h; unsigned __int64
0x180008531  mov     dword ptr [rsp+38h+var_18+4], 0
0x180008539  lea     rcx, qword_18001F440; this
0x180008540  mov     dword ptr [rsp+38h+var_18], ebx
0x180008544  mov     qword ptr [rsp+38h+var_18+8], rdi
0x180008549  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000854e  test    al, al
0x180008550  jz      short loc_1800085BA
0x180008552  mov     r9, cs:qword_18001F448
0x180008559  mov     rax, cs:qword_18001F450
0x180008560  sub     rax, r9
0x180008563  cmp     r9, cs:qword_18001F450
0x18000856a  sbb     r8, r8
0x18000856d  and     r8, rax; Size
0x180008570  test    r9, r9
0x180008573  jnz     short loc_180008583
0x180008575  call    cs:__imp__o__errno
0x18000857b  mov     dword ptr [rax], 16h
0x180008581  jmp     short loc_1800085AB
0x180008583  cmp     r8, 10h
0x180008587  jb      short loc_180008595
0x180008589  movups  xmm0, [rsp+38h+var_18]
0x18000858e  movdqu  xmmword ptr [r9], xmm0
0x180008593  jmp     short loc_1800085B0
0x180008595  xor     edx, edx; Val
0x180008597  mov     rcx, r9; void *
0x18000859a  call    memset_0
0x18000859f  call    cs:__imp__o__errno
0x1800085a5  mov     dword ptr [rax], 22h ; '"'
0x1800085ab  call    _invalid_parameter_noinfo
0x1800085b0  add     cs:qword_18001F448, 10h
0x1800085b8  jmp     short loc_1800085CB
0x1800085ba  neg     ebx
0x1800085bc  sbb     eax, eax
0x1800085be  and     eax, 83Ah
0x1800085c3  add     eax, 0FFFFF7C1h
0x1800085c8  lock and [rdi], eax
0x1800085cb  lea     rcx, SRWLock; SRWLock
0x1800085d2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800085d8  mov     rbx, [rsp+38h+arg_0]
0x1800085dd  mov     rsi, [rsp+38h+arg_8]
0x1800085e2  add     rsp, 30h
0x1800085e6  pop     rdi
0x1800085e7  retn
```
