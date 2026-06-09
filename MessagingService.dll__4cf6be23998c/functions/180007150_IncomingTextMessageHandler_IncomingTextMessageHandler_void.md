# IncomingTextMessageHandler::~IncomingTextMessageHandler(void)

- ea: `0x180007150`
- end: `0x1800071a1`
- name: `??1IncomingTextMessageHandler@@MEAA@XZ`
- size: `81`
- prototype: `void __fastcall(IncomingTextMessageHandler *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800071b0`
- `0x180007210`

## callees

- `0x180007128`
- `0x180007150`
- `0x18000c010`

## pseudocode

```c
void __fastcall IncomingTextMessageHandler::~IncomingTextMessageHandler(IncomingTextMessageHandler *this)
{
  IncomingMessageRegistrationEvent *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &IncomingTextMessageHandler::`vftable';
  v2 = (IncomingMessageRegistrationEvent *)*((_QWORD *)this + 5);
  if ( v2 )
    tlx::_delete<IncomingMessageRegistrationEvent>(v2);
  v3 = *((_QWORD *)this + 4);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 3);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
}

```

## disassembly

```asm
0x180007150  push    rbx
0x180007152  sub     rsp, 20h
0x180007156  lea     rax, ??_7IncomingTextMessageHandler@@6B@; const IncomingTextMessageHandler::`vftable'
0x18000715d  mov     rbx, rcx
0x180007160  mov     [rcx], rax
0x180007163  mov     rcx, [rcx+28h]
0x180007167  test    rcx, rcx
0x18000716a  jz      short loc_180007171
0x18000716c  call    ??$_delete@VIncomingMessageRegistrationEvent@@@tlx@@YAXPEAVIncomingMessageRegistrationEvent@@@Z; tlx::_delete<IncomingMessageRegistrationEvent>(IncomingMessageRegistrationEvent *)
0x180007171  mov     rcx, [rbx+20h]
0x180007175  test    rcx, rcx
0x180007178  jz      short loc_180007186
0x18000717a  mov     rax, [rcx]
0x18000717d  mov     rax, [rax+10h]
0x180007181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007186  mov     rcx, [rbx+18h]
0x18000718a  test    rcx, rcx
0x18000718d  jz      short loc_18000719B
0x18000718f  mov     rax, [rcx]
0x180007192  mov     rax, [rax+10h]
0x180007196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000719b  add     rsp, 20h
0x18000719f  pop     rbx
0x1800071a0  retn
```
