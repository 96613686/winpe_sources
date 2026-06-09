# PCLmWriter::CByteStream::~CByteStream(void)

- ea: `0x1800119bc`
- end: `0x1800119f7`
- name: `??1CByteStream@PCLmWriter@@UEAA@XZ`
- size: `59`
- prototype: `void __fastcall(PCLmWriter::CByteStream *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180011990`
- `0x1800120c0`
- `0x1800122c0`
- `0x18001a21c`

## callees

- `0x180010204`
- `0x1800119bc`
- `0x180013028`

## pseudocode

```c
void __fastcall PCLmWriter::CByteStream::~CByteStream(PCLmWriter::CByteStream *this)
{
  std::_Ref_count_base *v2; // rcx

  std::vector<unsigned char>::_Tidy((char *)this + 40);
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 3);
  if ( v2 )
    std::_Ref_count_base::_Decwref(v2);
  *((_QWORD *)this + 1) = &PCLmWriter::IStreamBufferProvider::`vftable';
  *(_QWORD *)this = &PCLmWriter::IByteStream::`vftable';
}

```

## disassembly

```asm
0x1800119bc  push    rbx
0x1800119be  sub     rsp, 20h
0x1800119c2  mov     rbx, rcx
0x1800119c5  add     rcx, 28h ; '('
0x1800119c9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800119ce  mov     rcx, [rbx+18h]; this
0x1800119d2  test    rcx, rcx
0x1800119d5  jz      short loc_1800119DC
0x1800119d7  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800119dc  lea     rax, ??_7IStreamBufferProvider@PCLmWriter@@6B@; const PCLmWriter::IStreamBufferProvider::`vftable'
0x1800119e3  mov     [rbx+8], rax
0x1800119e7  lea     rax, ??_7IByteStream@PCLmWriter@@6B@; const PCLmWriter::IByteStream::`vftable'
0x1800119ee  mov     [rbx], rax
0x1800119f1  add     rsp, 20h
0x1800119f5  pop     rbx
0x1800119f6  retn
```
