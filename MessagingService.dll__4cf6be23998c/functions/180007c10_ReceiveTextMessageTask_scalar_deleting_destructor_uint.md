# ReceiveTextMessageTask::`scalar deleting destructor'(uint)

- ea: `0x180007c10`
- end: `0x180007c40`
- name: `??_GReceiveTextMessageTask@@MEAAPEAXI@Z`
- size: `48`
- prototype: `ReceiveTextMessageTask *__fastcall(ReceiveTextMessageTask *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task`

## callees

- `0x180007ae4`
- `0x180007c10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007c2c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007c2c`

## pseudocode

```c
ReceiveTextMessageTask *__fastcall ReceiveTextMessageTask::`scalar deleting destructor'(
        ReceiveTextMessageTask *this,
        char a2)
{
  ReceiveTextMessageTask::~ReceiveTextMessageTask(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180007c10  mov     [rsp+arg_0], rbx
0x180007c15  push    rdi
0x180007c16  sub     rsp, 20h
0x180007c1a  mov     ebx, edx
0x180007c1c  mov     rdi, rcx
0x180007c1f  call    ??1ReceiveTextMessageTask@@MEAA@XZ; ReceiveTextMessageTask::~ReceiveTextMessageTask(void)
0x180007c24  test    bl, 1
0x180007c27  jz      short loc_180007C32
0x180007c29  mov     rcx, rdi
0x180007c2c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007c32  mov     rbx, [rsp+28h+arg_0]
0x180007c37  mov     rax, rdi
0x180007c3a  add     rsp, 20h
0x180007c3e  pop     rdi
0x180007c3f  retn
```
