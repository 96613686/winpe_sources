# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800097b0`
- end: `0x1800098b4`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006c68`
- `0x180015924`
- `0x1800255e0`
- `0x1800256c0`
- `0x1800257a0`

## callees

- `0x180002e3a`
- `0x180002ed4`
- `0x1800097b0`
- `0x18000a5e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009841`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000986b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009841`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000986b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800097dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800097dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000989e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000989e`

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
      || a3 != dword_180059AC4
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180059AE8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180059AF8 - (_QWORD)qword_180059AF0) & -(__int64)((unsigned __int64)qword_180059AF0 < qword_180059AF8);
    if ( qword_180059AF0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180059AF0 = v12;
LABEL_11:
        qword_180059AF0 = (char *)qword_180059AF0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180059AF0, 0, v8);
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
0x1800097b0  mov     [rsp+arg_0], rbx
0x1800097b5  mov     [rsp+arg_8], rsi
0x1800097ba  push    rdi
0x1800097bb  sub     rsp, 30h
0x1800097bf  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800097c5  mov     esi, r8d
0x1800097c8  mov     ebx, edx
0x1800097ca  mov     rdi, rcx
0x1800097cd  test    eax, eax
0x1800097cf  jz      loc_1800098A4
0x1800097d5  lea     rcx, SRWLock; SRWLock
0x1800097dc  call    cs:__imp_AcquireSRWLockExclusive
0x1800097e2  mov     eax, cs:dword_180059AC4
0x1800097e8  test    esi, esi
0x1800097ea  jz      loc_180009886
0x1800097f0  cmp     esi, eax
0x1800097f2  jnz     loc_180009886
0x1800097f8  mov     edx, 10h; unsigned __int64
0x1800097fd  mov     dword ptr [rsp+38h+var_18+4], 0
0x180009805  lea     rcx, qword_180059AE8; this
0x18000980c  mov     dword ptr [rsp+38h+var_18], ebx
0x180009810  mov     qword ptr [rsp+38h+var_18+8], rdi
0x180009815  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000981a  test    al, al
0x18000981c  jz      short loc_180009886
0x18000981e  mov     r9, cs:qword_180059AF0
0x180009825  mov     rax, cs:qword_180059AF8
0x18000982c  sub     rax, r9
0x18000982f  cmp     r9, cs:qword_180059AF8
0x180009836  sbb     r8, r8
0x180009839  and     r8, rax; Size
0x18000983c  test    r9, r9
0x18000983f  jnz     short loc_18000984F
0x180009841  call    cs:__imp__o__errno
0x180009847  mov     dword ptr [rax], 16h
0x18000984d  jmp     short loc_180009877
0x18000984f  cmp     r8, 10h
0x180009853  jb      short loc_180009861
0x180009855  movups  xmm0, [rsp+38h+var_18]
0x18000985a  movdqu  xmmword ptr [r9], xmm0
0x18000985f  jmp     short loc_18000987C
0x180009861  xor     edx, edx; Val
0x180009863  mov     rcx, r9; void *
0x180009866  call    memset_0
0x18000986b  call    cs:__imp__o__errno
0x180009871  mov     dword ptr [rax], 22h ; '"'
0x180009877  call    _invalid_parameter_noinfo
0x18000987c  add     cs:qword_180059AF0, 10h
0x180009884  jmp     short loc_180009897
0x180009886  neg     ebx
0x180009888  sbb     eax, eax
0x18000988a  and     eax, 83Ah
0x18000988f  add     eax, 0FFFFF7C1h
0x180009894  lock and [rdi], eax
0x180009897  lea     rcx, SRWLock; SRWLock
0x18000989e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800098a4  mov     rbx, [rsp+38h+arg_0]
0x1800098a9  mov     rsi, [rsp+38h+arg_8]
0x1800098ae  add     rsp, 30h
0x1800098b2  pop     rdi
0x1800098b3  retn
```
