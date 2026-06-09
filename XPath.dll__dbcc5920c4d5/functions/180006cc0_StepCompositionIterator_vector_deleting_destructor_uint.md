# StepCompositionIterator::`vector deleting destructor'(uint)

- ea: `0x180006cc0`
- end: `0x180006cef`
- name: `??_EStepCompositionIterator@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(StepCompositionIterator *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800069e0`

## callees

- `0x1800010b8`
- `0x1800067f8`
- `0x180006cc0`

## pseudocode

```c
StepCompositionIterator *__fastcall StepCompositionIterator::`vector deleting destructor'(
        StepCompositionIterator *this,
        char a2)
{
  StepCompositionIterator::~StepCompositionIterator(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180006cc0  mov     [rsp+arg_0], rbx
0x180006cc5  push    rdi
0x180006cc6  sub     rsp, 20h
0x180006cca  mov     ebx, edx
0x180006ccc  mov     rdi, rcx
0x180006ccf  call    ??1StepCompositionIterator@@UEAA@XZ; StepCompositionIterator::~StepCompositionIterator(void)
0x180006cd4  test    bl, 1
0x180006cd7  jz      short loc_180006CE1
0x180006cd9  mov     rcx, rdi; Block
0x180006cdc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006ce1  mov     rbx, [rsp+28h+arg_0]
0x180006ce6  mov     rax, rdi
0x180006ce9  add     rsp, 20h
0x180006ced  pop     rdi
0x180006cee  retn
```
