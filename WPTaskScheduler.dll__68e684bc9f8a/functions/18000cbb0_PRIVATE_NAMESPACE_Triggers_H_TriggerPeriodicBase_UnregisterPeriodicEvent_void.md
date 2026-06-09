# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::UnregisterPeriodicEvent(void)

- ea: `0x18000cbb0`
- end: `0x18000cc49`
- name: `?UnregisterPeriodicEvent@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@AEAAJXZ`
- size: `153`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bea0`
- `0x18000ee18`

## callees

- `0x18000cbb0`
- `0x180022010`

## import_xrefs

- `EventAggregation!EADeleteAggregateEvent` at `0x18000cc0e`
- `EventAggregation!EADeleteAggregateEvent` at `0x18000cc0e`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18000cc24`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18000cc24`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::UnregisterPeriodicEvent(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rcx
  unsigned int v5; // edi
  void (__fastcall ***v6)(_QWORD, __int64); // rcx

  v4 = *((_QWORD *)this + 54);
  v5 = 0;
  if ( v4 )
  {
    EADeleteAggregateEvent(v4, a2, a3);
    *((_QWORD *)this + 54) = 0;
  }
  if ( *((_QWORD *)this + 52) )
  {
    v5 = TbDeleteCEvent(*((_QWORD *)this + 52), a2, a3);
    *((_QWORD *)this + 52) = 0;
  }
  v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 51);
  if ( v6 )
    (**v6)(v6, 1);
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 53) = 0;
  return v5;
}

```

## disassembly

```asm
0x18000cbb0  mov     [rsp+arg_0], rbx
0x18000cbb5  mov     [rsp+arg_8], rsi
0x18000cbba  push    rdi
0x18000cbbb  sub     rsp, 20h
0x18000cbbf  xor     esi, esi
0x18000cbc1  mov     rbx, rcx
0x18000cbc4  mov     rcx, [rcx+1B0h]
0x18000cbcb  mov     edi, esi
0x18000cbcd  test    rcx, rcx
0x18000cbd0  jnz     short loc_18000CC0E
0x18000cbd2  mov     eax, [rbx+1A4h]
0x18000cbd8  or      eax, [rbx+1A0h]
0x18000cbde  jnz     short loc_18000CC1D
0x18000cbe0  mov     rcx, [rbx+198h]
0x18000cbe7  test    rcx, rcx
0x18000cbea  jnz     short loc_18000CC37
0x18000cbec  mov     [rbx+198h], rsi
0x18000cbf3  xor     eax, eax
0x18000cbf5  mov     rsi, [rsp+28h+arg_8]
0x18000cbfa  mov     [rbx+1A8h], rax
0x18000cc01  mov     eax, edi
0x18000cc03  mov     rbx, [rsp+28h+arg_0]
0x18000cc08  add     rsp, 20h
0x18000cc0c  pop     rdi
0x18000cc0d  retn
0x18000cc0e  call    cs:__imp_EADeleteAggregateEvent
0x18000cc14  mov     [rbx+1B0h], rsi
0x18000cc1b  jmp     short loc_18000CBD2
0x18000cc1d  mov     rcx, [rbx+1A0h]
0x18000cc24  call    cs:__imp_TbDeleteCEvent
0x18000cc2a  mov     edi, eax
0x18000cc2c  xor     eax, eax
0x18000cc2e  mov     [rbx+1A0h], rax
0x18000cc35  jmp     short loc_18000CBE0
0x18000cc37  mov     rdx, [rcx]
0x18000cc3a  mov     rax, [rdx]
0x18000cc3d  mov     edx, 1
0x18000cc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc47  jmp     short loc_18000CBEC
```
