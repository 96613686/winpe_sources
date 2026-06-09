# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180017240`
- end: `0x180017344`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013c8c`
- `0x180013e5c`
- `0x180014828`

## callees

- `0x1800028c8`
- `0x180002928`
- `0x180017240`
- `0x180018294`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800172d1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800172fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800172d1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800172fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001726c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001726c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001732e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001732e`

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
      || a3 != dword_1800297EC
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180029810, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180029820 - (_QWORD)qword_180029818) & -(__int64)((unsigned __int64)qword_180029818 < qword_180029820);
    if ( qword_180029818 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180029818 = v12;
LABEL_11:
        qword_180029818 = (char *)qword_180029818 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180029818, 0, v8);
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
0x180017240  mov     [rsp+arg_0], rbx
0x180017245  mov     [rsp+arg_8], rsi
0x18001724a  push    rdi
0x18001724b  sub     rsp, 30h
0x18001724f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180017255  mov     esi, r8d
0x180017258  mov     ebx, edx
0x18001725a  mov     rdi, rcx
0x18001725d  test    eax, eax
0x18001725f  jz      loc_180017334
0x180017265  lea     rcx, SRWLock; SRWLock
0x18001726c  call    cs:__imp_AcquireSRWLockExclusive
0x180017272  mov     eax, cs:dword_1800297EC
0x180017278  test    esi, esi
0x18001727a  jz      loc_180017316
0x180017280  cmp     esi, eax
0x180017282  jnz     loc_180017316
0x180017288  mov     edx, 10h; unsigned __int64
0x18001728d  mov     dword ptr [rsp+38h+var_18+4], 0
0x180017295  lea     rcx, qword_180029810; this
0x18001729c  mov     dword ptr [rsp+38h+var_18], ebx
0x1800172a0  mov     qword ptr [rsp+38h+var_18+8], rdi
0x1800172a5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800172aa  test    al, al
0x1800172ac  jz      short loc_180017316
0x1800172ae  mov     r9, cs:qword_180029818
0x1800172b5  mov     rax, cs:qword_180029820
0x1800172bc  sub     rax, r9
0x1800172bf  cmp     r9, cs:qword_180029820
0x1800172c6  sbb     r8, r8
0x1800172c9  and     r8, rax; Size
0x1800172cc  test    r9, r9
0x1800172cf  jnz     short loc_1800172DF
0x1800172d1  call    cs:__imp__o__errno
0x1800172d7  mov     dword ptr [rax], 16h
0x1800172dd  jmp     short loc_180017307
0x1800172df  cmp     r8, 10h
0x1800172e3  jb      short loc_1800172F1
0x1800172e5  movups  xmm0, [rsp+38h+var_18]
0x1800172ea  movdqu  xmmword ptr [r9], xmm0
0x1800172ef  jmp     short loc_18001730C
0x1800172f1  xor     edx, edx; Val
0x1800172f3  mov     rcx, r9; void *
0x1800172f6  call    memset_0
0x1800172fb  call    cs:__imp__o__errno
0x180017301  mov     dword ptr [rax], 22h ; '"'
0x180017307  call    _invalid_parameter_noinfo
0x18001730c  add     cs:qword_180029818, 10h
0x180017314  jmp     short loc_180017327
0x180017316  neg     ebx
0x180017318  sbb     eax, eax
0x18001731a  and     eax, 83Ah
0x18001731f  add     eax, 0FFFFF7C1h
0x180017324  lock and [rdi], eax
0x180017327  lea     rcx, SRWLock; SRWLock
0x18001732e  call    cs:__imp_ReleaseSRWLockExclusive
0x180017334  mov     rbx, [rsp+38h+arg_0]
0x180017339  mov     rsi, [rsp+38h+arg_8]
0x18001733e  add     rsp, 30h
0x180017342  pop     rdi
0x180017343  retn
```
