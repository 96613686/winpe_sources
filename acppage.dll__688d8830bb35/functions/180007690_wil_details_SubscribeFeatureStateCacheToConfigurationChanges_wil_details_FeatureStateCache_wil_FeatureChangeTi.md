# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180007690`
- end: `0x18000775b`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005698`
- `0x180009128`

## callees

- `0x180007690`
- `0x18000835c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000771e`
- `msvcrt!memcpy_s` at `0x18000771e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007745`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180007745`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800076bc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800076bc`

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
      && a3 == dword_18002048C
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800204B0, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_1800204C0 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_1800204C0),
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
0x180007690  mov     [rsp+arg_0], rbx
0x180007695  mov     [rsp+arg_8], rsi
0x18000769a  push    rdi
0x18000769b  sub     rsp, 30h
0x18000769f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800076a5  mov     esi, r8d
0x1800076a8  mov     ebx, edx
0x1800076aa  mov     rdi, rcx
0x1800076ad  test    eax, eax
0x1800076af  jz      loc_18000774B
0x1800076b5  lea     rcx, SRWLock; SRWLock
0x1800076bc  call    cs:__imp_AcquireSRWLockExclusive
0x1800076c2  mov     eax, cs:dword_18002048C
0x1800076c8  test    esi, esi
0x1800076ca  jz      short loc_18000772D
0x1800076cc  cmp     esi, eax
0x1800076ce  jnz     short loc_18000772D
0x1800076d0  mov     esi, 10h
0x1800076d5  mov     [rsp+38h+var_14], 0
0x1800076dd  mov     edx, esi; unsigned __int64
0x1800076df  mov     [rsp+38h+Source], ebx
0x1800076e3  lea     rcx, qword_1800204B0; this
0x1800076ea  mov     [rsp+38h+var_10], rdi
0x1800076ef  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800076f4  test    al, al
0x1800076f6  jz      short loc_18000772D
0x1800076f8  mov     rcx, cs:Destination; Destination
0x1800076ff  lea     r8, [rsp+38h+Source]; Source
0x180007704  mov     rax, cs:qword_1800204C0
0x18000770b  mov     r9d, esi; SourceSize
0x18000770e  sub     rax, rcx
0x180007711  cmp     rcx, cs:qword_1800204C0
0x180007718  sbb     rdx, rdx
0x18000771b  and     rdx, rax; DestinationSize
0x18000771e  call    cs:__imp_memcpy_s
0x180007724  add     cs:Destination, rsi
0x18000772b  jmp     short loc_18000773E
0x18000772d  neg     ebx
0x18000772f  sbb     eax, eax
0x180007731  and     eax, 83Ah
0x180007736  add     eax, 0FFFFF7C1h
0x18000773b  lock and [rdi], eax
0x18000773e  lea     rcx, SRWLock; SRWLock
0x180007745  call    cs:__imp_ReleaseSRWLockExclusive
0x18000774b  mov     rbx, [rsp+38h+arg_0]
0x180007750  mov     rsi, [rsp+38h+arg_8]
0x180007755  add     rsp, 30h
0x180007759  pop     rdi
0x18000775a  retn
```
