# CEcoScoreTaskHandler::`scalar deleting destructor'(uint)

- ea: `0x1800035b0`
- end: `0x1800035e9`
- name: `??_GCEcoScoreTaskHandler@@UEAAPEAXI@Z`
- size: `57`
- prototype: `CEcoScoreTaskHandler *__fastcall(CEcoScoreTaskHandler *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x180001aa4`
- `0x180003194`
- `0x1800035b0`

## pseudocode

```c
CEcoScoreTaskHandler *__fastcall CEcoScoreTaskHandler::`scalar deleting destructor'(
        CEcoScoreTaskHandler *this,
        char a2)
{
  *(_QWORD *)this = &CEcoScoreTaskHandler::`vftable';
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800035b0  mov     [rsp+arg_0], rbx
0x1800035b5  push    rdi
0x1800035b6  sub     rsp, 20h
0x1800035ba  lea     rax, ??_7CEcoScoreTaskHandler@@6B@; const CEcoScoreTaskHandler::`vftable'
0x1800035c1  mov     ebx, edx
0x1800035c3  mov     [rcx], rax
0x1800035c6  mov     rdi, rcx
0x1800035c9  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x1800035ce  test    bl, 1
0x1800035d1  jz      short loc_1800035DB
0x1800035d3  mov     rcx, rdi; Block
0x1800035d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800035db  mov     rbx, [rsp+28h+arg_0]
0x1800035e0  mov     rax, rdi
0x1800035e3  add     rsp, 20h
0x1800035e7  pop     rdi
0x1800035e8  retn
```
