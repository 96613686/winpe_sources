# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180008770`
- end: `0x180008874`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `21`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005dd0`
- `0x18000ed5c`
- `0x18000ee3c`
- `0x18000efbc`
- `0x1800263f0`
- `0x1800264d0`
- `0x1800265b0`
- `0x180026690`
- `0x180026804`
- `0x180026978`
- `0x180026aec`
- `0x180026c60`
- `0x180026dd4`
- `0x180026f48`
- `0x180027028`
- `0x180027108`
- `0x1800271e8`
- `0x1800272c8`
- `0x1800273a8`
- `0x180027528`
- `0x180027608`

## callees

- `0x180002432`
- `0x1800024ac`
- `0x180008770`
- `0x18000959c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008801`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000882b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008801`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000882b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000885e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000885e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000879c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000879c`

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
      || a3 != dword_1800444DC
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180044500, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180044510 - (_QWORD)qword_180044508) & -(__int64)((unsigned __int64)qword_180044508 < qword_180044510);
    if ( qword_180044508 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180044508 = v12;
LABEL_11:
        qword_180044508 = (char *)qword_180044508 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180044508, 0, v8);
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
0x180008770  mov     [rsp+arg_0], rbx
0x180008775  mov     [rsp+arg_8], rsi
0x18000877a  push    rdi
0x18000877b  sub     rsp, 30h
0x18000877f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008785  mov     esi, r8d
0x180008788  mov     ebx, edx
0x18000878a  mov     rdi, rcx
0x18000878d  test    eax, eax
0x18000878f  jz      loc_180008864
0x180008795  lea     rcx, SRWLock; SRWLock
0x18000879c  call    cs:__imp_AcquireSRWLockExclusive
0x1800087a2  mov     eax, cs:dword_1800444DC
0x1800087a8  test    esi, esi
0x1800087aa  jz      loc_180008846
0x1800087b0  cmp     esi, eax
0x1800087b2  jnz     loc_180008846
0x1800087b8  mov     edx, 10h; unsigned __int64
0x1800087bd  mov     dword ptr [rsp+38h+var_18+4], 0
0x1800087c5  lea     rcx, qword_180044500; this
0x1800087cc  mov     dword ptr [rsp+38h+var_18], ebx
0x1800087d0  mov     qword ptr [rsp+38h+var_18+8], rdi
0x1800087d5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800087da  test    al, al
0x1800087dc  jz      short loc_180008846
0x1800087de  mov     r9, cs:qword_180044508
0x1800087e5  mov     rax, cs:qword_180044510
0x1800087ec  sub     rax, r9
0x1800087ef  cmp     r9, cs:qword_180044510
0x1800087f6  sbb     r8, r8
0x1800087f9  and     r8, rax; Size
0x1800087fc  test    r9, r9
0x1800087ff  jnz     short loc_18000880F
0x180008801  call    cs:__imp__o__errno
0x180008807  mov     dword ptr [rax], 16h
0x18000880d  jmp     short loc_180008837
0x18000880f  cmp     r8, 10h
0x180008813  jb      short loc_180008821
0x180008815  movups  xmm0, [rsp+38h+var_18]
0x18000881a  movdqu  xmmword ptr [r9], xmm0
0x18000881f  jmp     short loc_18000883C
0x180008821  xor     edx, edx; Val
0x180008823  mov     rcx, r9; void *
0x180008826  call    memset_0
0x18000882b  call    cs:__imp__o__errno
0x180008831  mov     dword ptr [rax], 22h ; '"'
0x180008837  call    _invalid_parameter_noinfo
0x18000883c  add     cs:qword_180044508, 10h
0x180008844  jmp     short loc_180008857
0x180008846  neg     ebx
0x180008848  sbb     eax, eax
0x18000884a  and     eax, 83Ah
0x18000884f  add     eax, 0FFFFF7C1h
0x180008854  lock and [rdi], eax
0x180008857  lea     rcx, SRWLock; SRWLock
0x18000885e  call    cs:__imp_ReleaseSRWLockExclusive
0x180008864  mov     rbx, [rsp+38h+arg_0]
0x180008869  mov     rsi, [rsp+38h+arg_8]
0x18000886e  add     rsp, 30h
0x180008872  pop     rdi
0x180008873  retn
```
