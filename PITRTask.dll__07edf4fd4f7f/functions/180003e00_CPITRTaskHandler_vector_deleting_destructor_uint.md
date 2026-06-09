# CPITRTaskHandler::`vector deleting destructor'(uint)

- ea: `0x180003e00`
- end: `0x180003e30`
- name: `??_ECPITRTaskHandler@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CPITRTaskHandler *__fastcall(CPITRTaskHandler *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task`

## callees

- `0x1800036d0`
- `0x180003e00`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003e1c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003e1c`

## pseudocode

```c
CPITRTaskHandler *__fastcall CPITRTaskHandler::`vector deleting destructor'(CPITRTaskHandler *this, char a2)
{
  CWinTaskHandler::~CWinTaskHandler(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003e00  mov     [rsp+arg_0], rbx
0x180003e05  push    rdi
0x180003e06  sub     rsp, 20h
0x180003e0a  mov     ebx, edx
0x180003e0c  mov     rdi, rcx
0x180003e0f  call    ??1CWinTaskHandler@@MEAA@XZ; CWinTaskHandler::~CWinTaskHandler(void)
0x180003e14  test    bl, 1
0x180003e17  jz      short loc_180003E22
0x180003e19  mov     rcx, rdi
0x180003e1c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003e22  mov     rbx, [rsp+28h+arg_0]
0x180003e27  mov     rax, rdi
0x180003e2a  add     rsp, 20h
0x180003e2e  pop     rdi
0x180003e2f  retn
```
