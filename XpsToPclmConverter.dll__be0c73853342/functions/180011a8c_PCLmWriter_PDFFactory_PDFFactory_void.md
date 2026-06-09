# PCLmWriter::PDFFactory::~PDFFactory(void)

- ea: `0x180011a8c`
- end: `0x180011ab3`
- name: `??1PDFFactory@PCLmWriter@@UEAA@XZ`
- size: `39`
- prototype: `void __fastcall(PCLmWriter::PDFFactory *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012300`

## callees

- `0x180010204`
- `0x180011a8c`

## pseudocode

```c
void __fastcall PCLmWriter::PDFFactory::~PDFFactory(PCLmWriter::PDFFactory *this)
{
  std::_Ref_count_base *v2; // rcx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 2);
  if ( v2 )
    std::_Ref_count_base::_Decwref(v2);
  *(_QWORD *)this = &PCLmWriter::IPDFFactory::`vftable';
}

```

## disassembly

```asm
0x180011a8c  push    rbx
0x180011a8e  sub     rsp, 20h
0x180011a92  mov     rbx, rcx
0x180011a95  mov     rcx, [rcx+10h]; this
0x180011a99  test    rcx, rcx
0x180011a9c  jz      short loc_180011AA3
0x180011a9e  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180011aa3  lea     rax, ??_7IPDFFactory@PCLmWriter@@6B@; const PCLmWriter::IPDFFactory::`vftable'
0x180011aaa  mov     [rbx], rax
0x180011aad  add     rsp, 20h
0x180011ab1  pop     rbx
0x180011ab2  retn
```
