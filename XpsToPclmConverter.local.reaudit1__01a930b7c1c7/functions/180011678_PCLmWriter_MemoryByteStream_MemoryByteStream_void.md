# PCLmWriter::MemoryByteStream::MemoryByteStream(void)

- ea: `0x180011678`
- end: `0x1800116a9`
- name: `??0MemoryByteStream@PCLmWriter@@QEAA@XZ`
- size: `49`
- prototype: `__int64 __fastcall(PCLmWriter::MemoryByteStream *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800109f4`
- `0x180010b28`

## callees

- `0x1800183d8`

## pseudocode

```c
__int64 __fastcall PCLmWriter::MemoryByteStream::MemoryByteStream(PCLmWriter::MemoryByteStream *this)
{
  __int64 v1; // r9
  __int64 result; // rax

  PCLmWriter::CByteStream::CByteStream(this);
  *(_DWORD *)(v1 + 72) = 0;
  *(_QWORD *)(v1 + 8) = &PCLmWriter::MemoryByteStream::`vftable'{for `PCLmWriter::IStreamBufferProvider'};
  result = v1;
  *(_QWORD *)v1 = &PCLmWriter::MemoryByteStream::`vftable'{for `PCLmWriter::IByteStream'};
  return result;
}

```

## disassembly

```asm
0x180011678  sub     rsp, 28h
0x18001167c  mov     r9, rcx
0x18001167f  call    ??0CByteStream@PCLmWriter@@QEAA@XZ; PCLmWriter::CByteStream::CByteStream(void)
0x180011684  lea     rax, ??_7MemoryByteStream@PCLmWriter@@6BIStreamBufferProvider@1@@; const PCLmWriter::MemoryByteStream::`vftable'{for `PCLmWriter::IStreamBufferProvider'}
0x18001168b  mov     dword ptr [r9+48h], 0
0x180011693  lea     r10, ??_7MemoryByteStream@PCLmWriter@@6BIByteStream@1@@; const PCLmWriter::MemoryByteStream::`vftable'{for `PCLmWriter::IByteStream'}
0x18001169a  mov     [r9+8], rax
0x18001169e  mov     rax, r9
0x1800116a1  mov     [r9], r10
0x1800116a4  add     rsp, 28h
0x1800116a8  retn
```
