# tlx::_delete<IncomingMessageRegistrationEvent>(IncomingMessageRegistrationEvent *)

- ea: `0x180007128`
- end: `0x180007149`
- name: `??$_delete@VIncomingMessageRegistrationEvent@@@tlx@@YAXPEAVIncomingMessageRegistrationEvent@@@Z`
- size: `33`
- prototype: `void __fastcall(IncomingMessageRegistrationEvent *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007150`
- `0x180007318`
- `0x180007930`

## callees

- `0x180007128`
- `0x180009aec`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000713d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000713d`

## pseudocode

```c
void __fastcall tlx::_delete<IncomingMessageRegistrationEvent>(IncomingMessageRegistrationEvent *a1)
{
  if ( a1 )
  {
    IncomingMessageRegistrationEvent::~IncomingMessageRegistrationEvent(a1);
    operator delete(a1);
  }
}

```

## disassembly

```asm
0x180007128  test    rcx, rcx
0x18000712b  jz      short locret_180007148
0x18000712d  push    rbx
0x18000712e  sub     rsp, 20h
0x180007132  mov     rbx, rcx
0x180007135  call    ??1IncomingMessageRegistrationEvent@@QEAA@XZ; IncomingMessageRegistrationEvent::~IncomingMessageRegistrationEvent(void)
0x18000713a  mov     rcx, rbx
0x18000713d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007143  add     rsp, 20h
0x180007147  pop     rbx
0x180007148  retn
```
