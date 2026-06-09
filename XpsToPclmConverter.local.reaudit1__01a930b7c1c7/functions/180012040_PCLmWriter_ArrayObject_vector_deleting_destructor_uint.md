# PCLmWriter::ArrayObject::`vector deleting destructor'(uint)

- ea: `0x180012040`
- end: `0x180012074`
- name: `??_EArrayObject@PCLmWriter@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(PCLmWriter::ArrayObject *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001a90`
- `0x180011968`
- `0x180012040`

## pseudocode

```c
PCLmWriter::ArrayObject *__fastcall PCLmWriter::ArrayObject::`vector deleting destructor'(
        PCLmWriter::ArrayObject *this,
        char a2)
{
  PCLmWriter::ArrayObject::~ArrayObject(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180012040  mov     [rsp+arg_0], rbx
0x180012045  push    rdi
0x180012046  sub     rsp, 20h
0x18001204a  mov     ebx, edx
0x18001204c  mov     rdi, rcx
0x18001204f  call    ??1ArrayObject@PCLmWriter@@UEAA@XZ; PCLmWriter::ArrayObject::~ArrayObject(void)
0x180012054  test    bl, 1
0x180012057  jz      short loc_180012066
0x180012059  mov     edx, 30h ; '0'; unsigned __int64
0x18001205e  mov     rcx, rdi; void *
0x180012061  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012066  mov     rbx, [rsp+28h+arg_0]
0x18001206b  mov     rax, rdi
0x18001206e  add     rsp, 20h
0x180012072  pop     rdi
0x180012073  retn
```
