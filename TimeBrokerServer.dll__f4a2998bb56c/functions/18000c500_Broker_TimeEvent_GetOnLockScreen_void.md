# Broker::TimeEvent::GetOnLockScreen(void)

- ea: `0x18000c500`
- end: `0x18000c572`
- name: `?GetOnLockScreen@TimeEvent@Broker@@QEAA_NXZ`
- size: `114`
- prototype: `__int64 __fastcall(Broker::TimeEvent *this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c4d0`
- `0x18000f6f0`
- `0x18000fa10`
- `0x180010490`
- `0x180017910`
- `0x1800188a0`

## callees

- `0x180003800`
- `0x18000c500`

## import_xrefs

- `BrokerLib!BrGetBrokeredAppState2` at `0x18000c531`
- `BrokerLib!BrGetBrokeredAppState2` at `0x18000c531`

## pseudocode

```c
__int64 __fastcall Broker::TimeEvent::GetOnLockScreen(Broker::TimeEvent *this)
{
  __int64 result; // rax
  unsigned int BrokeredAppState2; // eax
  unsigned __int8 v3; // [rsp+40h] [rbp+8h] BYREF

  result = *((unsigned __int8 *)this + 93);
  v3 = result;
  if ( !(_BYTE)result )
  {
    BrokeredAppState2 = BrGetBrokeredAppState2(*((_QWORD *)this + 30), *((_QWORD *)this + 31), 0, 1, &v3);
    if ( BrokeredAppState2
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids,
        BrokeredAppState2);
    }
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x18000c500  sub     rsp, 38h
0x18000c504  movzx   eax, byte ptr [rcx+5Dh]
0x18000c508  mov     [rsp+38h+arg_0], al
0x18000c50c  test    al, al
0x18000c50e  jnz     short loc_18000C540
0x18000c510  mov     rdx, [rcx+0F8h]
0x18000c517  lea     rax, [rsp+38h+arg_0]
0x18000c51c  mov     rcx, [rcx+0F0h]
0x18000c523  mov     r9d, 1
0x18000c529  xor     r8d, r8d
0x18000c52c  mov     [rsp+38h+var_18], rax
0x18000c531  call    cs:__imp_BrGetBrokeredAppState2
0x18000c537  test    eax, eax
0x18000c539  jnz     short loc_18000C545
0x18000c53b  movzx   eax, [rsp+38h+arg_0]
0x18000c540  add     rsp, 38h
0x18000c544  retn
0x18000c545  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c54c  test    byte ptr [rcx+1Ch], 40h
0x18000c550  jz      short loc_18000C53B
0x18000c552  cmp     byte ptr [rcx+19h], 2
0x18000c556  jb      short loc_18000C53B
0x18000c558  mov     rcx, [rcx+10h]
0x18000c55c  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x18000c563  mov     edx, 0Bh
0x18000c568  mov     r9d, eax
0x18000c56b  call    WPP_SF_d
0x18000c570  jmp     short loc_18000C53B
```
