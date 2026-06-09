# Gdiplus::PathGradientBrush::~PathGradientBrush(void)

- ea: `0x180024ef0`
- end: `0x180024f05`
- name: `??1PathGradientBrush@Gdiplus@@UEAA@XZ`
- size: `21`
- prototype: `void __fastcall(Gdiplus::PathGradientBrush *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18004843b`
- `0x180048495`

## import_xrefs

- `gdiplus!GdipDeleteBrush` at `0x180024efe`

## pseudocode

```c
void __fastcall Gdiplus::PathGradientBrush::~PathGradientBrush(Gdiplus::PathGradientBrush *this)
{
  *(_QWORD *)this = &Gdiplus::LinearGradientBrush::`vftable';
  GdipDeleteBrush(*((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x180024ef0  lea     rax, ??_7LinearGradientBrush@Gdiplus@@6B@; const Gdiplus::LinearGradientBrush::`vftable'
0x180024ef7  mov     [rcx], rax
0x180024efa  mov     rcx, [rcx+8]
0x180024efe  jmp     cs:__imp_GdipDeleteBrush
```
