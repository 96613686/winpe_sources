# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000cd04`
- end: `0x18000cdce`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b594`
- `0x180013d70`

## callees

- `0x180001f4c`
- `0x18000cd04`
- `0x18000d284`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cd30`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cd30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdb8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdb8`

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
    AcquireSRWLockExclusive(&stru_180023208);
    if ( a3
      && a3 == dword_18002321C
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180023240, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_180023250 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_180023250),
        Source,
        0x10u);
      Destination = (char *)Destination + 16;
    }
    else
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&stru_180023208);
  }
}

```

## disassembly

```asm
0x18000cd04  mov     [rsp+arg_0], rbx
0x18000cd09  mov     [rsp+arg_8], rsi
0x18000cd0e  push    rdi
0x18000cd0f  sub     rsp, 30h
0x18000cd13  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000cd19  mov     esi, r8d
0x18000cd1c  mov     ebx, edx
0x18000cd1e  mov     rdi, rcx
0x18000cd21  test    eax, eax
0x18000cd23  jz      loc_18000CDBE
0x18000cd29  lea     rcx, stru_180023208; SRWLock
0x18000cd30  call    cs:__imp_AcquireSRWLockExclusive
0x18000cd36  mov     eax, cs:dword_18002321C
0x18000cd3c  test    esi, esi
0x18000cd3e  jz      short loc_18000CDA0
0x18000cd40  cmp     esi, eax
0x18000cd42  jnz     short loc_18000CDA0
0x18000cd44  mov     esi, 10h
0x18000cd49  mov     [rsp+38h+var_14], 0
0x18000cd51  mov     edx, esi; unsigned __int64
0x18000cd53  mov     [rsp+38h+Source], ebx
0x18000cd57  lea     rcx, qword_180023240; this
0x18000cd5e  mov     [rsp+38h+var_10], rdi
0x18000cd63  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000cd68  test    al, al
0x18000cd6a  jz      short loc_18000CDA0
0x18000cd6c  mov     rcx, cs:Destination; Destination
0x18000cd73  lea     r8, [rsp+38h+Source]; Source
0x18000cd78  mov     rax, cs:qword_180023250
0x18000cd7f  mov     r9d, esi; SourceSize
0x18000cd82  sub     rax, rcx
0x18000cd85  cmp     rcx, cs:qword_180023250
0x18000cd8c  sbb     rdx, rdx
0x18000cd8f  and     rdx, rax; DestinationSize
0x18000cd92  call    memcpy_s
0x18000cd97  add     cs:Destination, rsi
0x18000cd9e  jmp     short loc_18000CDB1
0x18000cda0  neg     ebx
0x18000cda2  sbb     eax, eax
0x18000cda4  and     eax, 83Ah
0x18000cda9  add     eax, 0FFFFF7C1h
0x18000cdae  lock and [rdi], eax
0x18000cdb1  lea     rcx, stru_180023208; SRWLock
0x18000cdb8  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cdbe  mov     rbx, [rsp+38h+arg_0]
0x18000cdc3  mov     rsi, [rsp+38h+arg_8]
0x18000cdc8  add     rsp, 30h
0x18000cdcc  pop     rdi
0x18000cdcd  retn
```
