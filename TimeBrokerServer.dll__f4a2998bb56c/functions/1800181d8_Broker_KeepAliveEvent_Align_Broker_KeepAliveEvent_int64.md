# Broker::KeepAliveEvent::Align(Broker::KeepAliveEvent *,__int64)

- ea: `0x1800181d8`
- end: `0x18001825c`
- name: `?Align@KeepAliveEvent@Broker@@QEAAXPEAV12@_J@Z`
- size: `132`
- prototype: `void __fastcall(Broker::KeepAliveEvent *__hidden this, struct Broker::KeepAliveEvent *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800050d0`

## callees

- `0x180009cf0`
- `0x1800181d8`

## pseudocode

```c
void __fastcall Broker::KeepAliveEvent::Align(
        Broker::KeepAliveEvent *this,
        struct Broker::KeepAliveEvent *a2,
        __int64 a3)
{
  __int64 v4; // r9
  __int64 v5; // rdx

  if ( !*((_BYTE *)this + 284) && *((_DWORD *)this + 22) == 1 )
  {
    v4 = *((_QWORD *)this + 3) / 2LL + *((_QWORD *)this + 4) / 2LL;
    v5 = *((_QWORD *)a2 + 4) / 2LL + *((_QWORD *)a2 + 3) / 2LL;
    if ( v4 < v5 )
      v5 = v4 + (v5 - v4) % *((_QWORD *)this + 8) - *((_QWORD *)this + 8);
    if ( v5 >= a3 )
    {
      Broker::TimeEvent::ArmTimeEvent(this);
      *((_BYTE *)this + 284) = 1;
    }
  }
}

```

## disassembly

```asm
0x1800181d8  push    rbx
0x1800181da  sub     rsp, 20h
0x1800181de  cmp     byte ptr [rcx+11Ch], 0
0x1800181e5  mov     r10, rdx
0x1800181e8  mov     rbx, rcx
0x1800181eb  jnz     short loc_180018256
0x1800181ed  cmp     dword ptr [rcx+58h], 1
0x1800181f1  jnz     short loc_180018256
0x1800181f3  mov     rax, [rcx+20h]
0x1800181f7  mov     r11d, 2
0x1800181fd  cqo
0x1800181ff  idiv    r11
0x180018202  mov     r9, rax
0x180018205  mov     rax, [rcx+18h]
0x180018209  cqo
0x18001820b  idiv    r11
0x18001820e  add     r9, rax
0x180018211  mov     rax, [r10+20h]
0x180018215  cqo
0x180018217  idiv    r11
0x18001821a  mov     rcx, rax
0x18001821d  mov     rax, [r10+18h]
0x180018221  cqo
0x180018223  idiv    r11
0x180018226  lea     rdx, [rcx+rax]
0x18001822a  cmp     r9, rdx
0x18001822d  jge     short loc_180018242
0x18001822f  sub     rdx, r9
0x180018232  mov     rax, rdx
0x180018235  cqo
0x180018237  idiv    qword ptr [rbx+40h]
0x18001823b  sub     rdx, [rbx+40h]
0x18001823f  add     rdx, r9
0x180018242  cmp     rdx, r8
0x180018245  jl      short loc_180018256
0x180018247  mov     rcx, rbx
0x18001824a  call    ?ArmTimeEvent@TimeEvent@Broker@@IEAAX_JW4States@12@@Z; Broker::TimeEvent::ArmTimeEvent(__int64,Broker::TimeEvent::States)
0x18001824f  mov     byte ptr [rbx+11Ch], 1
0x180018256  add     rsp, 20h
0x18001825a  pop     rbx
0x18001825b  retn
```
