# Gdiplus::LinearGradientBrush::LinearGradientBrush(Gdiplus::PointF const &,Gdiplus::PointF const &,Gdiplus::Color const &,Gdiplus::Color const &)

- ea: `0x180024928`
- end: `0x180024992`
- name: `??0LinearGradientBrush@Gdiplus@@QEAA@AEBVPointF@1@0AEBVColor@1@1@Z`
- size: `106`
- prototype: `__int64 __fastcall(Gdiplus::LinearGradientBrush *__hidden this, const struct Gdiplus::PointF *, const struct Gdiplus::PointF *, const struct Gdiplus::Color *, const struct Gdiplus::Color *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180026100`

## import_xrefs

- `gdiplus!GdipCreateLineBrush` at `0x180024977`
- `gdiplus!GdipCreateLineBrush` at `0x180024977`

## pseudocode

```c
Gdiplus::LinearGradientBrush *__fastcall Gdiplus::LinearGradientBrush::LinearGradientBrush(
        Gdiplus::LinearGradientBrush *this,
        const struct Gdiplus::PointF *a2,
        const struct Gdiplus::PointF *a3,
        const struct Gdiplus::Color *a4,
        const struct Gdiplus::Color *a5)
{
  const struct Gdiplus::Color *v7; // r9
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF

  *((_DWORD *)this + 4) = 6;
  v9 = 0;
  v7 = a5;
  *(_QWORD *)this = &Gdiplus::LinearGradientBrush::`vftable';
  *((_DWORD *)this + 4) = GdipCreateLineBrush(a2, a3, *(unsigned int *)a4, *(unsigned int *)v7, 0, &v9);
  *((_QWORD *)this + 1) = v9;
  return this;
}

```

## disassembly

```asm
0x180024928  push    rbx
0x18002492a  sub     rsp, 30h
0x18002492e  mov     dword ptr [rcx+10h], 6
0x180024935  mov     rbx, rcx
0x180024938  mov     rax, r9
0x18002493b  mov     [rsp+38h+arg_0], 0
0x180024944  mov     r9, [rsp+38h+arg_20]
0x180024949  lea     rcx, ??_7LinearGradientBrush@Gdiplus@@6B@; const Gdiplus::LinearGradientBrush::`vftable'
0x180024950  mov     r10, r8
0x180024953  mov     r11, rdx
0x180024956  mov     [rbx], rcx
0x180024959  mov     rdx, r10
0x18002495c  mov     r8d, [rax]
0x18002495f  lea     rcx, [rsp+38h+arg_0]
0x180024964  mov     r9d, [r9]
0x180024967  mov     [rsp+38h+var_10], rcx
0x18002496c  mov     rcx, r11
0x18002496f  mov     [rsp+38h+var_18], 0
0x180024977  call    cs:__imp_GdipCreateLineBrush
0x18002497d  mov     [rbx+10h], eax
0x180024980  mov     rax, [rsp+38h+arg_0]
0x180024985  mov     [rbx+8], rax
0x180024989  mov     rax, rbx
0x18002498c  add     rsp, 30h
0x180024990  pop     rbx
0x180024991  retn
```
