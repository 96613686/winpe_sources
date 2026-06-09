# Gdiplus::Bitmap::Bitmap(int,int,int,int,uchar *)

- ea: `0x180024440`
- end: `0x1800244aa`
- name: `??0Bitmap@Gdiplus@@QEAA@HHHHPEAE@Z`
- size: `106`
- prototype: `__int64 __fastcall(Gdiplus::Bitmap *__hidden this, int, int, int, int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180025f30`

## import_xrefs

- `gdiplus!GdipCreateBitmapFromScan0` at `0x18002448a`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18002448a`

## pseudocode

```c
Gdiplus::Bitmap *__fastcall Gdiplus::Bitmap::Bitmap(
        Gdiplus::Bitmap *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        unsigned __int8 *a6)
{
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF

  v8 = 0;
  *(_QWORD *)this = &Gdiplus::Image::`vftable';
  *((_DWORD *)this + 4) = GdipCreateBitmapFromScan0(a2, a3, a4, 2498570, a6, &v8);
  *((_QWORD *)this + 1) = v8;
  return this;
}

```

## disassembly

```asm
0x180024440  mov     [rsp+arg_8], rbx
0x180024445  push    rdi
0x180024446  sub     rsp, 30h
0x18002444a  mov     r10d, r9d
0x18002444d  mov     [rsp+38h+arg_0], 0
0x180024456  mov     r11d, r8d
0x180024459  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x180024460  mov     [rcx], rax
0x180024463  mov     ebx, edx
0x180024465  lea     rax, [rsp+38h+arg_0]
0x18002446a  mov     rdi, rcx
0x18002446d  mov     [rsp+38h+var_10], rax
0x180024472  mov     r9d, 26200Ah
0x180024478  mov     rax, [rsp+38h+arg_28]
0x18002447d  mov     r8d, r10d
0x180024480  mov     edx, r11d
0x180024483  mov     [rsp+38h+var_18], rax
0x180024488  mov     ecx, ebx
0x18002448a  call    cs:__imp_GdipCreateBitmapFromScan0
0x180024490  mov     rbx, [rsp+38h+arg_8]
0x180024495  mov     [rdi+10h], eax
0x180024498  mov     rax, [rsp+38h+arg_0]
0x18002449d  mov     [rdi+8], rax
0x1800244a1  mov     rax, rdi
0x1800244a4  add     rsp, 30h
0x1800244a8  pop     rdi
0x1800244a9  retn
```
