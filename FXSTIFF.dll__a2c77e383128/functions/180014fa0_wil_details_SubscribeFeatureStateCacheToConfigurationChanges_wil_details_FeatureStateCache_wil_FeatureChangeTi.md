# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180014fa0`
- end: `0x18001506b`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180014fa0`
- `0x180015cac`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001502e`
- `msvcrt!memcpy_s` at `0x18001502e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015055`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180015055`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014fcc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180014fcc`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD Source[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( a3
      && a3 == dword_1800702AC
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800702D0, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_1800702E0 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_1800702E0),
        Source,
        0x10u);
      Destination = (char *)Destination + 16;
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
0x180014fa0  mov     [rsp+arg_0], rbx
0x180014fa5  mov     [rsp+arg_8], rsi
0x180014faa  push    rdi
0x180014fab  sub     rsp, 30h
0x180014faf  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014fb5  mov     esi, r8d
0x180014fb8  mov     ebx, edx
0x180014fba  mov     rdi, rcx
0x180014fbd  test    eax, eax
0x180014fbf  jz      loc_18001505B
0x180014fc5  lea     rcx, SRWLock; SRWLock
0x180014fcc  call    cs:__imp_AcquireSRWLockExclusive
0x180014fd2  mov     eax, cs:dword_1800702AC
0x180014fd8  test    esi, esi
0x180014fda  jz      short loc_18001503D
0x180014fdc  cmp     esi, eax
0x180014fde  jnz     short loc_18001503D
0x180014fe0  mov     esi, 10h
0x180014fe5  mov     [rsp+38h+var_14], 0
0x180014fed  mov     edx, esi; unsigned __int64
0x180014fef  mov     [rsp+38h+Source], ebx
0x180014ff3  lea     rcx, qword_1800702D0; this
0x180014ffa  mov     [rsp+38h+var_10], rdi
0x180014fff  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180015004  test    al, al
0x180015006  jz      short loc_18001503D
0x180015008  mov     rcx, cs:Destination; Destination
0x18001500f  lea     r8, [rsp+38h+Source]; Source
0x180015014  mov     rax, cs:qword_1800702E0
0x18001501b  mov     r9d, esi; SourceSize
0x18001501e  sub     rax, rcx
0x180015021  cmp     rcx, cs:qword_1800702E0
0x180015028  sbb     rdx, rdx
0x18001502b  and     rdx, rax; DestinationSize
0x18001502e  call    cs:__imp_memcpy_s
0x180015034  add     cs:Destination, rsi
0x18001503b  jmp     short loc_18001504E
0x18001503d  neg     ebx
0x18001503f  sbb     eax, eax
0x180015041  and     eax, 83Ah
0x180015046  add     eax, 0FFFFF7C1h
0x18001504b  lock and [rdi], eax
0x18001504e  lea     rcx, SRWLock; SRWLock
0x180015055  call    cs:__imp_ReleaseSRWLockExclusive
0x18001505b  mov     rbx, [rsp+38h+arg_0]
0x180015060  mov     rsi, [rsp+38h+arg_8]
0x180015065  add     rsp, 30h
0x180015069  pop     rdi
0x18001506a  retn
```
