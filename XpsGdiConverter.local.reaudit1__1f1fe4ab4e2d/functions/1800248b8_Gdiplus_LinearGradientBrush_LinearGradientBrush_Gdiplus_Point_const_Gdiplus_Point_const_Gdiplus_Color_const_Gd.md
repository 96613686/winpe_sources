# Gdiplus::LinearGradientBrush::LinearGradientBrush(Gdiplus::Point const &,Gdiplus::Point const &,Gdiplus::Color const &,Gdiplus::Color const &)

- ea: `0x1800248b8`
- end: `0x180024922`
- name: `??0LinearGradientBrush@Gdiplus@@QEAA@AEBVPoint@1@0AEBVColor@1@1@Z`
- size: `106`
- prototype: `__int64 __fastcall(Gdiplus::LinearGradientBrush *__hidden this, const struct Gdiplus::Point *, const struct Gdiplus::Point *, const struct Gdiplus::Color *, const struct Gdiplus::Color *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180026100`

## import_xrefs

- `gdiplus!GdipCreateLineBrushI` at `0x180024907`
- `gdiplus!GdipCreateLineBrushI` at `0x180024907`

## pseudocode

```c
Gdiplus::LinearGradientBrush *__fastcall Gdiplus::LinearGradientBrush::LinearGradientBrush(
        Gdiplus::LinearGradientBrush *this,
        const struct Gdiplus::Point *a2,
        const struct Gdiplus::Point *a3,
        const struct Gdiplus::Color *a4,
        const struct Gdiplus::Color *a5)
{
  const struct Gdiplus::Color *v7; // r9
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF

  *((_DWORD *)this + 4) = 6;
  v9 = 0;
  v7 = a5;
  *(_QWORD *)this = &Gdiplus::LinearGradientBrush::`vftable';
  *((_DWORD *)this + 4) = GdipCreateLineBrushI(a2, a3, *(unsigned int *)a4, *(unsigned int *)v7, 0, &v9);
  *((_QWORD *)this + 1) = v9;
  return this;
}

```

## disassembly

```asm
0x1800248b8  push    rbx
0x1800248ba  sub     rsp, 30h
0x1800248be  mov     dword ptr [rcx+10h], 6
0x1800248c5  mov     rbx, rcx
0x1800248c8  mov     rax, r9
0x1800248cb  mov     [rsp+38h+arg_0], 0
0x1800248d4  mov     r9, [rsp+38h+arg_20]
0x1800248d9  lea     rcx, ??_7LinearGradientBrush@Gdiplus@@6B@; const Gdiplus::LinearGradientBrush::`vftable'
0x1800248e0  mov     r10, r8
0x1800248e3  mov     r11, rdx
0x1800248e6  mov     [rbx], rcx
0x1800248e9  mov     rdx, r10
0x1800248ec  mov     r8d, [rax]
0x1800248ef  lea     rcx, [rsp+38h+arg_0]
0x1800248f4  mov     r9d, [r9]
0x1800248f7  mov     [rsp+38h+var_10], rcx
0x1800248fc  mov     rcx, r11
0x1800248ff  mov     [rsp+38h+var_18], 0
0x180024907  call    cs:__imp_GdipCreateLineBrushI
0x18002490d  mov     [rbx+10h], eax
0x180024910  mov     rax, [rsp+38h+arg_0]
0x180024915  mov     [rbx+8], rax
0x180024919  mov     rax, rbx
0x18002491c  add     rsp, 30h
0x180024920  pop     rbx
0x180024921  retn
```
