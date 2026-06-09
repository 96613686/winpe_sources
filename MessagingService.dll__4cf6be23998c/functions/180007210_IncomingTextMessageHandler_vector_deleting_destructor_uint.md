# IncomingTextMessageHandler::`vector deleting destructor'(uint)

- ea: `0x180007210`
- end: `0x180007240`
- name: `??_EIncomingTextMessageHandler@@MEAAPEAXI@Z`
- size: `48`
- prototype: `IncomingTextMessageHandler *__fastcall(IncomingTextMessageHandler *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180007150`
- `0x180007210`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000722c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000722c`

## pseudocode

```c
IncomingTextMessageHandler *__fastcall IncomingTextMessageHandler::`vector deleting destructor'(
        IncomingTextMessageHandler *this,
        char a2)
{
  IncomingTextMessageHandler::~IncomingTextMessageHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007210  mov     [rsp+arg_0], rbx
0x180007215  push    rdi
0x180007216  sub     rsp, 20h
0x18000721a  mov     ebx, edx
0x18000721c  mov     rdi, rcx
0x18000721f  call    ??1IncomingTextMessageHandler@@MEAA@XZ; IncomingTextMessageHandler::~IncomingTextMessageHandler(void)
0x180007224  test    bl, 1
0x180007227  jz      short loc_180007232
0x180007229  mov     rcx, rdi
0x18000722c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007232  mov     rbx, [rsp+28h+arg_0]
0x180007237  mov     rax, rdi
0x18000723a  add     rsp, 20h
0x18000723e  pop     rdi
0x18000723f  retn
```
