# BufferWriter::CBufferWriter::`scalar deleting destructor'(uint)

- ea: `0x180013500`
- end: `0x180013534`
- name: `??_GCBufferWriter@BufferWriter@@MEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(BufferWriter::CBufferWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180013124`
- `0x180013500`

## pseudocode

```c
BufferWriter::CBufferWriter *__fastcall BufferWriter::CBufferWriter::`scalar deleting destructor'(
        BufferWriter::CBufferWriter *this,
        char a2)
{
  BufferWriter::CBufferWriter::~CBufferWriter(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180013500  mov     [rsp+arg_0], rbx
0x180013505  push    rdi
0x180013506  sub     rsp, 20h
0x18001350a  mov     ebx, edx
0x18001350c  mov     rdi, rcx
0x18001350f  call    ??1CBufferWriter@BufferWriter@@MEAA@XZ; BufferWriter::CBufferWriter::~CBufferWriter(void)
0x180013514  test    bl, 1
0x180013517  jz      short loc_180013526
0x180013519  mov     edx, 98h; unsigned __int64
0x18001351e  mov     rcx, rdi; void *
0x180013521  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013526  mov     rbx, [rsp+28h+arg_0]
0x18001352b  mov     rax, rdi
0x18001352e  add     rsp, 20h
0x180013532  pop     rdi
0x180013533  retn
```
