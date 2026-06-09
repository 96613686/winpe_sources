# BufferWriter::CAsyncIO::`vector deleting destructor'(uint)

- ea: `0x1800134c0`
- end: `0x1800134f4`
- name: `??_ECAsyncIO@BufferWriter@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(BufferWriter::CAsyncIO *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180013068`
- `0x1800134c0`

## pseudocode

```c
BufferWriter::CAsyncIO *__fastcall BufferWriter::CAsyncIO::`vector deleting destructor'(
        BufferWriter::CAsyncIO *this,
        char a2)
{
  BufferWriter::CAsyncIO::~CAsyncIO(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800134c0  mov     [rsp+arg_0], rbx
0x1800134c5  push    rdi
0x1800134c6  sub     rsp, 20h
0x1800134ca  mov     ebx, edx
0x1800134cc  mov     rdi, rcx
0x1800134cf  call    ??1CAsyncIO@BufferWriter@@UEAA@XZ; BufferWriter::CAsyncIO::~CAsyncIO(void)
0x1800134d4  test    bl, 1
0x1800134d7  jz      short loc_1800134E6
0x1800134d9  mov     edx, 80h; unsigned __int64
0x1800134de  mov     rcx, rdi; void *
0x1800134e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800134e6  mov     rbx, [rsp+28h+arg_0]
0x1800134eb  mov     rax, rdi
0x1800134ee  add     rsp, 20h
0x1800134f2  pop     rdi
0x1800134f3  retn
```
