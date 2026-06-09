# Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)

- ea: `0x180024a84`
- end: `0x180024acc`
- name: `??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z`
- size: `72`
- prototype: `__int64 __fastcall(Gdiplus::SolidBrush *__hidden this, const struct Gdiplus::Color *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180026438`

## import_xrefs

- `gdiplus!GdipCreateSolidFill` at `0x180024ab1`
- `gdiplus!GdipCreateSolidFill` at `0x180024ab1`

## pseudocode

```c
Gdiplus::SolidBrush *__fastcall Gdiplus::SolidBrush::SolidBrush(
        Gdiplus::SolidBrush *this,
        const struct Gdiplus::Color *a2)
{
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  *((_DWORD *)this + 4) = 6;
  v4 = 0;
  *(_QWORD *)this = &Gdiplus::LinearGradientBrush::`vftable';
  *((_DWORD *)this + 4) = GdipCreateSolidFill(*(unsigned int *)a2, &v4);
  *((_QWORD *)this + 1) = v4;
  return this;
}

```

## disassembly

```asm
0x180024a84  push    rbx
0x180024a86  sub     rsp, 20h
0x180024a8a  mov     rbx, rcx
0x180024a8d  mov     dword ptr [rcx+10h], 6
0x180024a94  mov     rax, rdx
0x180024a97  mov     [rsp+28h+arg_0], 0
0x180024aa0  lea     rcx, ??_7LinearGradientBrush@Gdiplus@@6B@; const Gdiplus::LinearGradientBrush::`vftable'
0x180024aa7  lea     rdx, [rsp+28h+arg_0]
0x180024aac  mov     [rbx], rcx
0x180024aaf  mov     ecx, [rax]
0x180024ab1  call    cs:__imp_GdipCreateSolidFill
0x180024ab7  mov     [rbx+10h], eax
0x180024aba  mov     rax, [rsp+28h+arg_0]
0x180024abf  mov     [rbx+8], rax
0x180024ac3  mov     rax, rbx
0x180024ac6  add     rsp, 20h
0x180024aca  pop     rbx
0x180024acb  retn
```
