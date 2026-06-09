# CWofTasksHandler::`scalar deleting destructor'(uint)

- ea: `0x180002bc0`
- end: `0x180002bf9`
- name: `??_GCWofTasksHandler@@UEAAPEAXI@Z`
- size: `57`
- prototype: `CWofTasksHandler *__fastcall(CWofTasksHandler *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001048`
- `0x180002b14`
- `0x180002bc0`

## pseudocode

```c
CWofTasksHandler *__fastcall CWofTasksHandler::`scalar deleting destructor'(CWofTasksHandler *this, char a2)
{
  *(_QWORD *)this = &CWofTasksHandler::`vftable';
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002bc0  mov     [rsp+arg_0], rbx
0x180002bc5  push    rdi
0x180002bc6  sub     rsp, 20h
0x180002bca  lea     rax, ??_7CWofTasksHandler@@6B@; const CWofTasksHandler::`vftable'
0x180002bd1  mov     ebx, edx
0x180002bd3  mov     [rcx], rax
0x180002bd6  mov     rdi, rcx
0x180002bd9  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x180002bde  test    bl, 1
0x180002be1  jz      short loc_180002BEB
0x180002be3  mov     rcx, rdi; Block
0x180002be6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002beb  mov     rbx, [rsp+28h+arg_0]
0x180002bf0  mov     rax, rdi
0x180002bf3  add     rsp, 20h
0x180002bf7  pop     rdi
0x180002bf8  retn
```
