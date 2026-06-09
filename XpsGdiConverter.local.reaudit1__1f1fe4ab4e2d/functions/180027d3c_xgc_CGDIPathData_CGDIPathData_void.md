# xgc::CGDIPathData::~CGDIPathData(void)

- ea: `0x180027d3c`
- end: `0x180027d67`
- name: `??1CGDIPathData@xgc@@UEAA@XZ`
- size: `43`
- prototype: `void __fastcall(xgc::CGDIPathData *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180027db0`
- `0x180027dfc`
- `0x180027ed4`
- `0x180028098`
- `0x180028338`
- `0x18002bcf0`
- `0x1800484ef`
- `0x180048501`
- `0x180048513`
- `0x180048781`

## callees

- `0x180011d60`
- `0x1800179a0`

## pseudocode

```c
void __fastcall xgc::CGDIPathData::~CGDIPathData(xgc::CGDIPathData *this)
{
  std::vector<unsigned char>::_Tidy((char *)this + 64);
  std::vector<DWRITE_GLYPH_OFFSET>::_Tidy((char *)this + 40);
  *(_QWORD *)this = &CUnknownBase<ID2D1SimplifiedGeometrySink>::`vftable';
}

```

## disassembly

```asm
0x180027d3c  push    rbx
0x180027d3e  sub     rsp, 20h
0x180027d42  mov     rbx, rcx
0x180027d45  add     rcx, 40h ; '@'
0x180027d49  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180027d4e  lea     rcx, [rbx+28h]
0x180027d52  call    ?_Tidy@?$vector@UDWRITE_GLYPH_OFFSET@@V?$allocator@UDWRITE_GLYPH_OFFSET@@@std@@@std@@AEAAXXZ; std::vector<DWRITE_GLYPH_OFFSET>::_Tidy(void)
0x180027d57  lea     rax, ??_7?$CUnknownBase@UID2D1SimplifiedGeometrySink@@@@6B@; const CUnknownBase<ID2D1SimplifiedGeometrySink>::`vftable'
0x180027d5e  mov     [rbx], rax
0x180027d61  add     rsp, 20h
0x180027d65  pop     rbx
0x180027d66  retn
```
