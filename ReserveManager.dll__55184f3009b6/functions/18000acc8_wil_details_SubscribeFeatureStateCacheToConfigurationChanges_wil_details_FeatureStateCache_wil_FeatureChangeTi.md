# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000acc8`
- end: `0x18000adcc`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008154`
- `0x180016040`
- `0x180016134`
- `0x180016228`
- `0x180027c6c`
- `0x180027e58`

## callees

- `0x18000422a`
- `0x1800042f4`
- `0x18000acc8`
- `0x18000c0cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ad59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ad83`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ad59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ad83`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000acf4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000acf4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000adb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000adb6`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        unsigned int a2,
        int a3)
{
  __int64 v6; // rcx
  size_t v7; // r8
  __int64 v8; // rcx
  __int128 v9; // [rsp+20h] [rbp-18h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_18004C4B4
      || (*(_QWORD *)&v9 = a2,
          *((_QWORD *)&v9 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18004C4D8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v7 = (qword_18004C4E8 - (_QWORD)qword_18004C4E0) & -(__int64)((unsigned __int64)qword_18004C4E0 < qword_18004C4E8);
    if ( qword_18004C4E0 )
    {
      if ( v7 >= 0x10 )
      {
        *(_OWORD *)qword_18004C4E0 = v9;
LABEL_11:
        qword_18004C4E0 = (char *)qword_18004C4E0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_18004C4E0, 0, v7);
      *(_DWORD *)_o__errno(v8) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v6) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x18000acc8  mov     [rsp+arg_10], rbx
0x18000accd  mov     [rsp+arg_18], rsi
0x18000acd2  push    rdi
0x18000acd3  sub     rsp, 30h
0x18000acd7  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000acdd  mov     esi, r8d
0x18000ace0  mov     edi, edx
0x18000ace2  mov     rbx, rcx
0x18000ace5  test    eax, eax
0x18000ace7  jz      loc_18000ADBC
0x18000aced  lea     rcx, SRWLock; SRWLock
0x18000acf4  call    cs:__imp_AcquireSRWLockExclusive
0x18000acfa  mov     eax, cs:dword_18004C4B4
0x18000ad00  test    esi, esi
0x18000ad02  jz      loc_18000AD9E
0x18000ad08  cmp     esi, eax
0x18000ad0a  jnz     loc_18000AD9E
0x18000ad10  mov     edx, 10h; unsigned __int64
0x18000ad15  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000ad1d  lea     rcx, qword_18004C4D8; this
0x18000ad24  mov     dword ptr [rsp+38h+var_18], edi
0x18000ad28  mov     qword ptr [rsp+38h+var_18+8], rbx
0x18000ad2d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ad32  test    al, al
0x18000ad34  jz      short loc_18000AD9E
0x18000ad36  mov     r9, cs:qword_18004C4E0
0x18000ad3d  mov     rax, cs:qword_18004C4E8
0x18000ad44  sub     rax, r9
0x18000ad47  cmp     r9, cs:qword_18004C4E8
0x18000ad4e  sbb     r8, r8
0x18000ad51  and     r8, rax; Size
0x18000ad54  test    r9, r9
0x18000ad57  jnz     short loc_18000AD67
0x18000ad59  call    cs:__imp__o__errno
0x18000ad5f  mov     dword ptr [rax], 16h
0x18000ad65  jmp     short loc_18000AD8F
0x18000ad67  cmp     r8, 10h
0x18000ad6b  jb      short loc_18000AD79
0x18000ad6d  movups  xmm0, [rsp+38h+var_18]
0x18000ad72  movdqu  xmmword ptr [r9], xmm0
0x18000ad77  jmp     short loc_18000AD94
0x18000ad79  xor     edx, edx; Val
0x18000ad7b  mov     rcx, r9; void *
0x18000ad7e  call    memset_0
0x18000ad83  call    cs:__imp__o__errno
0x18000ad89  mov     dword ptr [rax], 22h ; '"'
0x18000ad8f  call    _invalid_parameter_noinfo
0x18000ad94  add     cs:qword_18004C4E0, 10h
0x18000ad9c  jmp     short loc_18000ADAF
0x18000ad9e  neg     edi
0x18000ada0  sbb     eax, eax
0x18000ada2  and     eax, 83Ah
0x18000ada7  add     eax, 0FFFFF7C1h
0x18000adac  lock and [rbx], eax
0x18000adaf  lea     rcx, SRWLock; SRWLock
0x18000adb6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000adbc  mov     rbx, [rsp+38h+arg_10]
0x18000adc1  mov     rsi, [rsp+38h+arg_18]
0x18000adc6  add     rsp, 30h
0x18000adca  pop     rdi
0x18000adcb  retn
```
