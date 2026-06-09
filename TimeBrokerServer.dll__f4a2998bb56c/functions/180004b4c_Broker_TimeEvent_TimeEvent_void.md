# Broker::TimeEvent::~TimeEvent(void)

- ea: `0x180004b4c`
- end: `0x180004b62`
- name: `??1TimeEvent@Broker@@UEAA@XZ`
- size: `22`
- prototype: `void __fastcall(Broker::TimeEvent *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001be4d`
- `0x18001be5f`

## callees

- `0x180004b70`

## pseudocode

```c
void __fastcall Broker::TimeEvent::~TimeEvent(Broker::TimeEvent *this)
{
  *(_QWORD *)this = &Broker::TimeEvent::`vftable';
  std::vector<unsigned char>::_Tidy((char *)this + 256);
}

```

## disassembly

```asm
0x180004b4c  lea     rax, ??_7TimeEvent@Broker@@6B@; const Broker::TimeEvent::`vftable'
0x180004b53  mov     [rcx], rax
0x180004b56  add     rcx, 100h
0x180004b5d  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
```
