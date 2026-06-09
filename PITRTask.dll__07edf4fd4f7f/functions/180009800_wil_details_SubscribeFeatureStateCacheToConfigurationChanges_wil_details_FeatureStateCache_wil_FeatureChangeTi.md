# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180009800`
- end: `0x1800098e7`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `231`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800055d4`
- `0x1800056c8`
- `0x1800057bc`
- `0x1800058b0`
- `0x1800069d0`

## callees

- `0x180009800`
- `0x18000bf6c`
- `0x1800107c0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000989d`
- `msvcrt!memcpy_s` at `0x18000989d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800098c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800098c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000983b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000983b`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-20h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( a3
      && a3 == dword_18001B714
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18001B738, 0x10u)) )
    {
      memcpy_s(
        qword_18001B740,
        (qword_18001B748 - (_QWORD)qword_18001B740) & -(__int64)((unsigned __int64)qword_18001B740 < qword_18001B748),
        Source,
        0x10u);
      qword_18001B740 = (char *)qword_18001B740 + 16;
    }
    else
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180009800  mov     [rsp+arg_10], rbx
0x180009805  mov     [rsp+arg_18], rsi
0x18000980a  push    rdi
0x18000980b  sub     rsp, 40h
0x18000980f  mov     rax, cs:__security_cookie
0x180009816  xor     rax, rsp
0x180009819  mov     [rsp+48h+var_18], rax
0x18000981e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009824  mov     esi, r8d
0x180009827  mov     edi, edx
0x180009829  mov     rbx, rcx
0x18000982c  test    eax, eax
0x18000982e  jz      loc_1800098CA
0x180009834  lea     rcx, SRWLock; SRWLock
0x18000983b  call    cs:__imp_AcquireSRWLockExclusive
0x180009841  mov     eax, cs:dword_18001B714
0x180009847  test    esi, esi
0x180009849  jz      short loc_1800098AC
0x18000984b  cmp     esi, eax
0x18000984d  jnz     short loc_1800098AC
0x18000984f  mov     esi, 10h
0x180009854  mov     [rsp+48h+var_24], 0
0x18000985c  mov     edx, esi; unsigned __int64
0x18000985e  mov     [rsp+48h+Source], edi
0x180009862  lea     rcx, qword_18001B738; this
0x180009869  mov     [rsp+48h+var_20], rbx
0x18000986e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009873  test    al, al
0x180009875  jz      short loc_1800098AC
0x180009877  mov     rcx, cs:qword_18001B740; Destination
0x18000987e  lea     r8, [rsp+48h+Source]; Source
0x180009883  mov     rax, cs:qword_18001B748
0x18000988a  mov     r9d, esi; SourceSize
0x18000988d  sub     rax, rcx
0x180009890  cmp     rcx, cs:qword_18001B748
0x180009897  sbb     rdx, rdx
0x18000989a  and     rdx, rax; DestinationSize
0x18000989d  call    cs:__imp_memcpy_s
0x1800098a3  add     cs:qword_18001B740, rsi
0x1800098aa  jmp     short loc_1800098BD
0x1800098ac  neg     edi
0x1800098ae  sbb     eax, eax
0x1800098b0  and     eax, 83Ah
0x1800098b5  add     eax, 0FFFFF7C1h
0x1800098ba  lock and [rbx], eax
0x1800098bd  lea     rcx, SRWLock; SRWLock
0x1800098c4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800098ca  mov     rcx, [rsp+48h+var_18]
0x1800098cf  xor     rcx, rsp; StackCookie
0x1800098d2  call    __security_check_cookie
0x1800098d7  mov     rbx, [rsp+48h+arg_10]
0x1800098dc  mov     rsi, [rsp+48h+arg_18]
0x1800098e1  add     rsp, 40h
0x1800098e5  pop     rdi
0x1800098e6  retn
```
