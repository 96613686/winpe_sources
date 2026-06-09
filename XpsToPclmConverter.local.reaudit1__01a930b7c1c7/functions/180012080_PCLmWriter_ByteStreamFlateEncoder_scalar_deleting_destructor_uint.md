# PCLmWriter::ByteStreamFlateEncoder::`scalar deleting destructor'(uint)

- ea: `0x180012080`
- end: `0x1800120b4`
- name: `??_GByteStreamFlateEncoder@PCLmWriter@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(PCLmWriter::ByteStreamFlateEncoder *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180011ca0`

## callees

- `0x180001a90`
- `0x180011990`
- `0x180012080`

## pseudocode

```c
PCLmWriter::ByteStreamFlateEncoder *__fastcall PCLmWriter::ByteStreamFlateEncoder::`scalar deleting destructor'(
        PCLmWriter::ByteStreamFlateEncoder *this,
        char a2)
{
  PCLmWriter::ByteStreamFlateEncoder::~ByteStreamFlateEncoder(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180012080  mov     [rsp+arg_0], rbx
0x180012085  push    rdi
0x180012086  sub     rsp, 20h
0x18001208a  mov     ebx, edx
0x18001208c  mov     rdi, rcx
0x18001208f  call    ??1ByteStreamFlateEncoder@PCLmWriter@@UEAA@XZ; PCLmWriter::ByteStreamFlateEncoder::~ByteStreamFlateEncoder(void)
0x180012094  test    bl, 1
0x180012097  jz      short loc_1800120A6
0x180012099  mov     edx, 60h ; '`'; unsigned __int64
0x18001209e  mov     rcx, rdi; void *
0x1800120a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800120a6  mov     rbx, [rsp+28h+arg_0]
0x1800120ab  mov     rax, rdi
0x1800120ae  add     rsp, 20h
0x1800120b2  pop     rdi
0x1800120b3  retn
```
