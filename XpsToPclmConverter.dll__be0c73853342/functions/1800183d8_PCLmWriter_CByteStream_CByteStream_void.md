# PCLmWriter::CByteStream::CByteStream(void)

- ea: `0x1800183d8`
- end: `0x180018418`
- name: `??0CByteStream@PCLmWriter@@QEAA@XZ`
- size: `64`
- prototype: `__int64 __fastcall(PCLmWriter::CByteStream *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011678`
- `0x18001a17c`

## callees

- `0x18000f448`

## pseudocode

```c
__int64 __fastcall PCLmWriter::CByteStream::CByteStream(PCLmWriter::CByteStream *this)
{
  __int64 v1; // rdx
  __int64 result; // rax
  int v3; // r8d

  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *(_QWORD *)this = &PCLmWriter::CByteStream::`vftable'{for `PCLmWriter::IByteStream'};
  *((_QWORD *)this + 1) = &PCLmWriter::CByteStream::`vftable'{for `PCLmWriter::IStreamBufferProvider'};
  *((_BYTE *)this + 32) = 0;
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>((_QWORD *)this + 5);
  result = v1;
  *(_DWORD *)(v1 + 64) = v3;
  return result;
}

```

## disassembly

```asm
0x1800183d8  sub     rsp, 28h
0x1800183dc  xor     r8d, r8d
0x1800183df  lea     rax, ??_7CByteStream@PCLmWriter@@6BIByteStream@1@@; const PCLmWriter::CByteStream::`vftable'{for `PCLmWriter::IByteStream'}
0x1800183e6  mov     [rcx+10h], r8
0x1800183ea  mov     rdx, rcx
0x1800183ed  mov     [rcx+18h], r8
0x1800183f1  mov     [rcx], rax
0x1800183f4  lea     rax, ??_7CByteStream@PCLmWriter@@6BIStreamBufferProvider@1@@; const PCLmWriter::CByteStream::`vftable'{for `PCLmWriter::IStreamBufferProvider'}
0x1800183fb  mov     [rcx+8], rax
0x1800183ff  mov     [rcx+20h], r8b
0x180018403  add     rcx, 28h ; '('
0x180018407  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x18001840c  mov     rax, rdx
0x18001840f  mov     [rdx+40h], r8d
0x180018413  add     rsp, 28h
0x180018417  retn
```
