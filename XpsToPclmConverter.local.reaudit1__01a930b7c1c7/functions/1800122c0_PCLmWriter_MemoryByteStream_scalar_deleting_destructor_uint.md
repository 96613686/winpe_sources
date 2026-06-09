# PCLmWriter::MemoryByteStream::`scalar deleting destructor'(uint)

- ea: `0x1800122c0`
- end: `0x1800122f4`
- name: `??_GMemoryByteStream@PCLmWriter@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(PCLmWriter::MemoryByteStream *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180011cc0`

## callees

- `0x180001a90`
- `0x1800119bc`
- `0x1800122c0`

## pseudocode

```c
PCLmWriter::MemoryByteStream *__fastcall PCLmWriter::MemoryByteStream::`scalar deleting destructor'(
        PCLmWriter::MemoryByteStream *this,
        char a2)
{
  PCLmWriter::CByteStream::~CByteStream(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800122c0  mov     [rsp+arg_0], rbx
0x1800122c5  push    rdi
0x1800122c6  sub     rsp, 20h
0x1800122ca  mov     ebx, edx
0x1800122cc  mov     rdi, rcx
0x1800122cf  call    ??1CByteStream@PCLmWriter@@UEAA@XZ; PCLmWriter::CByteStream::~CByteStream(void)
0x1800122d4  test    bl, 1
0x1800122d7  jz      short loc_1800122E6
0x1800122d9  mov     edx, 50h ; 'P'; unsigned __int64
0x1800122de  mov     rcx, rdi; void *
0x1800122e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800122e6  mov     rbx, [rsp+28h+arg_0]
0x1800122eb  mov     rax, rdi
0x1800122ee  add     rsp, 20h
0x1800122f2  pop     rdi
0x1800122f3  retn
```
