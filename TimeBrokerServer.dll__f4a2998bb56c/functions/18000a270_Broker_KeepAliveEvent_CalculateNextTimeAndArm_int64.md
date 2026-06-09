# Broker::KeepAliveEvent::CalculateNextTimeAndArm(__int64)

- ea: `0x18000a270`
- end: `0x18000a2e1`
- name: `?CalculateNextTimeAndArm@KeepAliveEvent@Broker@@MEAAX_J@Z`
- size: `113`
- prototype: `void __fastcall(Broker::KeepAliveEvent *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009cf0`
- `0x180009ea0`
- `0x18000a270`

## pseudocode

```c
void __fastcall Broker::KeepAliveEvent::CalculateNextTimeAndArm(Broker::KeepAliveEvent *this, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx

  if ( *((_BYTE *)this + 92) )
  {
    Broker::TimeEvent::SetState(this, 0);
  }
  else
  {
    v4 = *((_QWORD *)this + 4) / 2LL + *((_QWORD *)this + 3) / 2LL;
    if ( !v4 || *((_DWORD *)this + 22) == 2 )
    {
      v5 = *((_QWORD *)this + 5);
      if ( !v5 )
      {
        *((_QWORD *)this + 5) = a2;
        v5 = a2;
      }
      v6 = *((_QWORD *)this + 8) + v5;
      if ( v6 > a2 )
        a2 = v6;
      v4 = a2 - *((_QWORD *)this + 7) / 2LL;
    }
    Broker::TimeEvent::ArmTimeEvent((__int64)this, v4);
  }
}

```

## disassembly

```asm
0x18000a270  cmp     byte ptr [rcx+5Ch], 0
0x18000a274  mov     r9, rdx
0x18000a277  mov     r8, rcx
0x18000a27a  jnz     short loc_18000A2DA
0x18000a27c  mov     rax, [rcx+20h]
0x18000a280  mov     r10d, 2
0x18000a286  cqo
0x18000a288  idiv    r10
0x18000a28b  mov     rcx, rax
0x18000a28e  mov     rax, [r8+18h]
0x18000a292  cqo
0x18000a294  idiv    r10
0x18000a297  lea     rdx, [rcx+rax]
0x18000a29b  test    rdx, rdx
0x18000a29e  jz      short loc_18000A2AE
0x18000a2a0  cmp     [r8+58h], r10d
0x18000a2a4  jz      short loc_18000A2AE
0x18000a2a6  mov     rcx, r8
0x18000a2a9  jmp     ?ArmTimeEvent@TimeEvent@Broker@@IEAAX_JW4States@12@@Z; Broker::TimeEvent::ArmTimeEvent(__int64,Broker::TimeEvent::States)
0x18000a2ae  mov     rcx, [r8+28h]
0x18000a2b2  test    rcx, rcx
0x18000a2b5  jnz     short loc_18000A2BE
0x18000a2b7  mov     [r8+28h], r9
0x18000a2bb  mov     rcx, r9
0x18000a2be  add     rcx, [r8+40h]
0x18000a2c2  mov     rax, [r8+38h]
0x18000a2c6  cmp     rcx, r9
0x18000a2c9  cqo
0x18000a2cb  cmovg   r9, rcx
0x18000a2cf  idiv    r10
0x18000a2d2  sub     r9, rax
0x18000a2d5  mov     rdx, r9
0x18000a2d8  jmp     short loc_18000A2A6
0x18000a2da  xor     edx, edx
0x18000a2dc  jmp     ?SetState@TimeEvent@Broker@@IEAAXW4States@12@@Z; Broker::TimeEvent::SetState(Broker::TimeEvent::States)
```
