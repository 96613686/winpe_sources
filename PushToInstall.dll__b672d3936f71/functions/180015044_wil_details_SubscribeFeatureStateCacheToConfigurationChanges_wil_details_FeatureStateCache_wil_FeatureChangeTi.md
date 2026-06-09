# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180015044`
- end: `0x180015148`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `18`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013134`
- `0x180013214`
- `0x1800134dc`
- `0x18002022c`
- `0x1800203ac`
- `0x18002052c`
- `0x1800206ac`
- `0x180020880`
- `0x1800209f4`
- `0x180020b74`
- `0x180020c54`
- `0x180022bd8`
- `0x180022cb8`
- `0x18002e920`
- `0x18002ea00`
- `0x18003fc70`
- `0x18003fd50`
- `0x180047724`

## callees

- `0x1800030ee`
- `0x18000316c`
- `0x180015044`
- `0x1800159cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800150d5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800150ff`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800150d5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800150ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015132`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015132`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015070`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015070`

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
      || a3 != dword_180065F64
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180065F88, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180065F98 - (_QWORD)qword_180065F90) & -(__int64)((unsigned __int64)qword_180065F90 < qword_180065F98);
    if ( qword_180065F90 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180065F90 = v12;
LABEL_11:
        qword_180065F90 = (char *)qword_180065F90 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180065F90, 0, v8);
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
0x180015044  mov     [rsp+arg_0], rbx
0x180015049  mov     [rsp+arg_8], rsi
0x18001504e  push    rdi
0x18001504f  sub     rsp, 30h
0x180015053  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015059  mov     esi, r8d
0x18001505c  mov     ebx, edx
0x18001505e  mov     rdi, rcx
0x180015061  test    eax, eax
0x180015063  jz      loc_180015138
0x180015069  lea     rcx, SRWLock; SRWLock
0x180015070  call    cs:__imp_AcquireSRWLockExclusive
0x180015076  mov     eax, cs:dword_180065F64
0x18001507c  test    esi, esi
0x18001507e  jz      loc_18001511A
0x180015084  cmp     esi, eax
0x180015086  jnz     loc_18001511A
0x18001508c  mov     edx, 10h; unsigned __int64
0x180015091  mov     dword ptr [rsp+38h+var_18+4], 0
0x180015099  lea     rcx, qword_180065F88; this
0x1800150a0  mov     dword ptr [rsp+38h+var_18], ebx
0x1800150a4  mov     qword ptr [rsp+38h+var_18+8], rdi
0x1800150a9  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800150ae  test    al, al
0x1800150b0  jz      short loc_18001511A
0x1800150b2  mov     r9, cs:qword_180065F90
0x1800150b9  mov     rax, cs:qword_180065F98
0x1800150c0  sub     rax, r9
0x1800150c3  cmp     r9, cs:qword_180065F98
0x1800150ca  sbb     r8, r8
0x1800150cd  and     r8, rax; Size
0x1800150d0  test    r9, r9
0x1800150d3  jnz     short loc_1800150E3
0x1800150d5  call    cs:__imp__o__errno
0x1800150db  mov     dword ptr [rax], 16h
0x1800150e1  jmp     short loc_18001510B
0x1800150e3  cmp     r8, 10h
0x1800150e7  jb      short loc_1800150F5
0x1800150e9  movups  xmm0, [rsp+38h+var_18]
0x1800150ee  movdqu  xmmword ptr [r9], xmm0
0x1800150f3  jmp     short loc_180015110
0x1800150f5  xor     edx, edx; Val
0x1800150f7  mov     rcx, r9; void *
0x1800150fa  call    memset_0
0x1800150ff  call    cs:__imp__o__errno
0x180015105  mov     dword ptr [rax], 22h ; '"'
0x18001510b  call    _invalid_parameter_noinfo
0x180015110  add     cs:qword_180065F90, 10h
0x180015118  jmp     short loc_18001512B
0x18001511a  neg     ebx
0x18001511c  sbb     eax, eax
0x18001511e  and     eax, 83Ah
0x180015123  add     eax, 0FFFFF7C1h
0x180015128  lock and [rdi], eax
0x18001512b  lea     rcx, SRWLock; SRWLock
0x180015132  call    cs:__imp_ReleaseSRWLockExclusive
0x180015138  mov     rbx, [rsp+38h+arg_0]
0x18001513d  mov     rsi, [rsp+38h+arg_8]
0x180015142  add     rsp, 30h
0x180015146  pop     rdi
0x180015147  retn
```
