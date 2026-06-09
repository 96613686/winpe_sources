# PCLmWriter::ByteStreamFlateEncoder::~ByteStreamFlateEncoder(void)

- ea: `0x180011990`
- end: `0x1800119b4`
- name: `??1ByteStreamFlateEncoder@PCLmWriter@@UEAA@XZ`
- size: `36`
- prototype: `void __fastcall(PCLmWriter::ByteStreamFlateEncoder *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012080`

## callees

- `0x1800101cc`
- `0x180011990`
- `0x1800119bc`

## pseudocode

```c
void __fastcall PCLmWriter::ByteStreamFlateEncoder::~ByteStreamFlateEncoder(PCLmWriter::ByteStreamFlateEncoder *this)
{
  std::_Ref_count_base *v2; // rcx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 11);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  PCLmWriter::CByteStream::~CByteStream(this);
}

```

## disassembly

```asm
0x180011990  push    rbx
0x180011992  sub     rsp, 20h
0x180011996  mov     rbx, rcx
0x180011999  mov     rcx, [rcx+58h]; this
0x18001199d  test    rcx, rcx
0x1800119a0  jz      short loc_1800119A7
0x1800119a2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800119a7  mov     rcx, rbx; this
0x1800119aa  add     rsp, 20h
0x1800119ae  pop     rbx
0x1800119af  jmp     ??1CByteStream@PCLmWriter@@UEAA@XZ; PCLmWriter::CByteStream::~CByteStream(void)
```
