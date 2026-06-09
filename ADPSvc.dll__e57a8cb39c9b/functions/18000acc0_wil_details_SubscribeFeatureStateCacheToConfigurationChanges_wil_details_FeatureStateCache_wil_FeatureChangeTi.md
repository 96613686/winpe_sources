# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000acc0`
- end: `0x18000adc4`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800094c0`
- `0x18000ca64`
- `0x18000cb44`
- `0x18000cc24`
- `0x18000cd04`
- `0x18000ced8`
- `0x18000cfb8`
- `0x18000d12c`
- `0x18000d2a0`
- `0x18000d380`
- `0x18000d500`
- `0x18000d5e0`
- `0x180024d70`
- `0x180032bd4`

## callees

- `0x180002c6a`
- `0x180002cf8`
- `0x18000acc0`
- `0x18000b5ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ad51`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ad7b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ad51`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ad7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000adae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000adae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000acec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000acec`

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
      || a3 != dword_18010F2D4
      || (*(_QWORD *)&v9 = a2,
          *((_QWORD *)&v9 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18010F2F8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v7 = (qword_18010F308 - (_QWORD)qword_18010F300) & -(__int64)((unsigned __int64)qword_18010F300 < qword_18010F308);
    if ( qword_18010F300 )
    {
      if ( v7 >= 0x10 )
      {
        *(_OWORD *)qword_18010F300 = v9;
LABEL_11:
        qword_18010F300 = (char *)qword_18010F300 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_18010F300, 0, v7);
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
0x18000acc0  mov     [rsp+arg_0], rbx
0x18000acc5  mov     [rsp+arg_8], rsi
0x18000acca  push    rdi
0x18000accb  sub     rsp, 30h
0x18000accf  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000acd5  mov     esi, r8d
0x18000acd8  mov     ebx, edx
0x18000acda  mov     rdi, rcx
0x18000acdd  test    eax, eax
0x18000acdf  jz      loc_18000ADB4
0x18000ace5  lea     rcx, SRWLock; SRWLock
0x18000acec  call    cs:__imp_AcquireSRWLockExclusive
0x18000acf2  mov     eax, cs:dword_18010F2D4
0x18000acf8  test    esi, esi
0x18000acfa  jz      loc_18000AD96
0x18000ad00  cmp     esi, eax
0x18000ad02  jnz     loc_18000AD96
0x18000ad08  mov     edx, 10h; unsigned __int64
0x18000ad0d  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000ad15  lea     rcx, qword_18010F2F8; this
0x18000ad1c  mov     dword ptr [rsp+38h+var_18], ebx
0x18000ad20  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000ad25  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ad2a  test    al, al
0x18000ad2c  jz      short loc_18000AD96
0x18000ad2e  mov     r9, cs:qword_18010F300
0x18000ad35  mov     rax, cs:qword_18010F308
0x18000ad3c  sub     rax, r9
0x18000ad3f  cmp     r9, cs:qword_18010F308
0x18000ad46  sbb     r8, r8
0x18000ad49  and     r8, rax; Size
0x18000ad4c  test    r9, r9
0x18000ad4f  jnz     short loc_18000AD5F
0x18000ad51  call    cs:__imp__o__errno
0x18000ad57  mov     dword ptr [rax], 16h
0x18000ad5d  jmp     short loc_18000AD87
0x18000ad5f  cmp     r8, 10h
0x18000ad63  jb      short loc_18000AD71
0x18000ad65  movups  xmm0, [rsp+38h+var_18]
0x18000ad6a  movdqu  xmmword ptr [r9], xmm0
0x18000ad6f  jmp     short loc_18000AD8C
0x18000ad71  xor     edx, edx; Val
0x18000ad73  mov     rcx, r9; void *
0x18000ad76  call    memset_0
0x18000ad7b  call    cs:__imp__o__errno
0x18000ad81  mov     dword ptr [rax], 22h ; '"'
0x18000ad87  call    _invalid_parameter_noinfo
0x18000ad8c  add     cs:qword_18010F300, 10h
0x18000ad94  jmp     short loc_18000ADA7
0x18000ad96  neg     ebx
0x18000ad98  sbb     eax, eax
0x18000ad9a  and     eax, 83Ah
0x18000ad9f  add     eax, 0FFFFF7C1h
0x18000ada4  lock and [rdi], eax
0x18000ada7  lea     rcx, SRWLock; SRWLock
0x18000adae  call    cs:__imp_ReleaseSRWLockExclusive
0x18000adb4  mov     rbx, [rsp+38h+arg_0]
0x18000adb9  mov     rsi, [rsp+38h+arg_8]
0x18000adbe  add     rsp, 30h
0x18000adc2  pop     rdi
0x18000adc3  retn
```
