# PCLmWriter::IStreamByteStream::`vector deleting destructor'(uint)

- ea: `0x18001a270`
- end: `0x18001a2a4`
- name: `??_EIStreamByteStream@PCLmWriter@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(PCLmWriter::IStreamByteStream *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001a260`

## callees

- `0x180001a90`
- `0x18001a21c`
- `0x18001a270`

## pseudocode

```c
PCLmWriter::IStreamByteStream *__fastcall PCLmWriter::IStreamByteStream::`vector deleting destructor'(
        PCLmWriter::IStreamByteStream *this,
        char a2)
{
  PCLmWriter::IStreamByteStream::~IStreamByteStream(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001a270  mov     [rsp+arg_0], rbx
0x18001a275  push    rdi
0x18001a276  sub     rsp, 20h
0x18001a27a  mov     ebx, edx
0x18001a27c  mov     rdi, rcx
0x18001a27f  call    ??1IStreamByteStream@PCLmWriter@@UEAA@XZ; PCLmWriter::IStreamByteStream::~IStreamByteStream(void)
0x18001a284  test    bl, 1
0x18001a287  jz      short loc_18001A296
0x18001a289  mov     edx, 50h ; 'P'; unsigned __int64
0x18001a28e  mov     rcx, rdi; void *
0x18001a291  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a296  mov     rbx, [rsp+28h+arg_0]
0x18001a29b  mov     rax, rdi
0x18001a29e  add     rsp, 20h
0x18001a2a2  pop     rdi
0x18001a2a3  retn
```
