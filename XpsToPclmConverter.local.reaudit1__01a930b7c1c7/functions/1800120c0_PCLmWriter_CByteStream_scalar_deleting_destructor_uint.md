# PCLmWriter::CByteStream::`scalar deleting destructor'(uint)

- ea: `0x1800120c0`
- end: `0x1800120f4`
- name: `??_GCByteStream@PCLmWriter@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(PCLmWriter::CByteStream *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180011cb0`

## callees

- `0x180001a90`
- `0x1800119bc`
- `0x1800120c0`

## pseudocode

```c
PCLmWriter::CByteStream *__fastcall PCLmWriter::CByteStream::`scalar deleting destructor'(
        PCLmWriter::CByteStream *this,
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
0x1800120c0  mov     [rsp+arg_0], rbx
0x1800120c5  push    rdi
0x1800120c6  sub     rsp, 20h
0x1800120ca  mov     ebx, edx
0x1800120cc  mov     rdi, rcx
0x1800120cf  call    ??1CByteStream@PCLmWriter@@UEAA@XZ; PCLmWriter::CByteStream::~CByteStream(void)
0x1800120d4  test    bl, 1
0x1800120d7  jz      short loc_1800120E6
0x1800120d9  mov     edx, 48h ; 'H'; unsigned __int64
0x1800120de  mov     rcx, rdi; void *
0x1800120e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800120e6  mov     rbx, [rsp+28h+arg_0]
0x1800120eb  mov     rax, rdi
0x1800120ee  add     rsp, 20h
0x1800120f2  pop     rdi
0x1800120f3  retn
```
