# CMediaSampleCopyBuffer::`vector deleting destructor'(uint)

- ea: `0x18002b470`
- end: `0x18002b4a4`
- name: `??_ECMediaSampleCopyBuffer@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CMediaSampleCopyBuffer *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x18002b26c`
- `0x18002b470`

## pseudocode

```c
CMediaSampleCopyBuffer *__fastcall CMediaSampleCopyBuffer::`vector deleting destructor'(
        CMediaSampleCopyBuffer *this,
        char a2)
{
  CMediaSampleCopyBuffer::~CMediaSampleCopyBuffer(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18002b470  mov     [rsp+arg_0], rbx
0x18002b475  push    rdi
0x18002b476  sub     rsp, 20h
0x18002b47a  mov     ebx, edx
0x18002b47c  mov     rdi, rcx
0x18002b47f  call    ??1CMediaSampleCopyBuffer@@UEAA@XZ; CMediaSampleCopyBuffer::~CMediaSampleCopyBuffer(void)
0x18002b484  test    bl, 1
0x18002b487  jz      short loc_18002B496
0x18002b489  mov     edx, 58h ; 'X'; unsigned __int64
0x18002b48e  mov     rcx, rdi; void *
0x18002b491  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b496  mov     rbx, [rsp+28h+arg_0]
0x18002b49b  mov     rax, rdi
0x18002b49e  add     rsp, 20h
0x18002b4a2  pop     rdi
0x18002b4a3  retn
```
