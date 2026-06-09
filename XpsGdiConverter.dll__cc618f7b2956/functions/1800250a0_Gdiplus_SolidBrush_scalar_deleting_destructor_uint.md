# Gdiplus::SolidBrush::`scalar deleting destructor'(uint)

- ea: `0x1800250a0`
- end: `0x1800250f2`
- name: `??_GSolidBrush@Gdiplus@@UEAAPEAXI@Z`
- size: `82`
- prototype: `void *__fastcall(Gdiplus::SolidBrush *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cd90`
- `0x1800250a0`

## import_xrefs

- `gdiplus!GdipFree` at `0x1800250d2`
- `gdiplus!GdipFree` at `0x1800250d2`
- `gdiplus!GdipDeleteBrush` at `0x1800250bd`
- `gdiplus!GdipDeleteBrush` at `0x1800250bd`

## pseudocode

```c
Gdiplus::SolidBrush *__fastcall Gdiplus::SolidBrush::`scalar deleting destructor'(Gdiplus::SolidBrush *this, char a2)
{
  *(_QWORD *)this = &Gdiplus::LinearGradientBrush::`vftable';
  GdipDeleteBrush(*((_QWORD *)this + 1));
  if ( (a2 & 1) != 0 )
  {
    if ( (a2 & 4) != 0 )
      xpsrdr::RectGeometrySink::SetFillMode(this, (enum D2D1_FILL_MODE)24);
    else
      GdipFree(this);
  }
  return this;
}

```

## disassembly

```asm
0x1800250a0  mov     [rsp+arg_0], rbx
0x1800250a5  push    rdi
0x1800250a6  sub     rsp, 20h
0x1800250aa  lea     rax, ??_7LinearGradientBrush@Gdiplus@@6B@; const Gdiplus::LinearGradientBrush::`vftable'
0x1800250b1  mov     rbx, rcx
0x1800250b4  mov     [rcx], rax
0x1800250b7  mov     edi, edx
0x1800250b9  mov     rcx, [rcx+8]
0x1800250bd  call    cs:__imp_GdipDeleteBrush
0x1800250c3  test    dil, 1
0x1800250c7  jz      short loc_1800250E4
0x1800250c9  mov     rcx, rbx; this
0x1800250cc  test    dil, 4
0x1800250d0  jnz     short loc_1800250DA
0x1800250d2  call    cs:__imp_GdipFree
0x1800250d8  jmp     short loc_1800250E4
0x1800250da  mov     edx, 18h; enum D2D1_FILL_MODE
0x1800250df  call    ?SetFillMode@RectGeometrySink@xpsrdr@@UEAAXW4D2D1_FILL_MODE@@@Z; xpsrdr::RectGeometrySink::SetFillMode(D2D1_FILL_MODE)
0x1800250e4  mov     rax, rbx
0x1800250e7  mov     rbx, [rsp+28h+arg_0]
0x1800250ec  add     rsp, 20h
0x1800250f0  pop     rdi
0x1800250f1  retn
```
