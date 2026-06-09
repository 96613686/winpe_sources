# NDFRepairExecutionClosure::`vector deleting destructor'(uint)

- ea: `0x18000c770`
- end: `0x18000c7a0`
- name: `??_ENDFRepairExecutionClosure@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(NDFRepairExecutionClosure *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x18000c3c8`
- `0x18000c770`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c78c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c78c`

## pseudocode

```c
NDFRepairExecutionClosure *__fastcall NDFRepairExecutionClosure::`vector deleting destructor'(
        NDFRepairExecutionClosure *this,
        char a2)
{
  NDFRepairExecutionClosure::~NDFRepairExecutionClosure(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c770  mov     [rsp+arg_0], rbx
0x18000c775  push    rdi
0x18000c776  sub     rsp, 20h
0x18000c77a  mov     ebx, edx
0x18000c77c  mov     rdi, rcx
0x18000c77f  call    ??1NDFRepairExecutionClosure@@UEAA@XZ; NDFRepairExecutionClosure::~NDFRepairExecutionClosure(void)
0x18000c784  test    bl, 1
0x18000c787  jz      short loc_18000C792
0x18000c789  mov     rcx, rdi
0x18000c78c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c792  mov     rbx, [rsp+28h+arg_0]
0x18000c797  mov     rax, rdi
0x18000c79a  add     rsp, 20h
0x18000c79e  pop     rdi
0x18000c79f  retn
```
