# Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)

- ea: `0x18001d40c`
- end: `0x18001d458`
- name: `??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z`
- size: `76`
- prototype: `__int64 __fastcall(Gdiplus::SolidBrush *__hidden this, const struct Gdiplus::Color *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001e4a8`

## import_xrefs

- `gdiplus!GdipCreateSolidFill` at `0x18001d436`
- `gdiplus!GdipCreateSolidFill` at `0x18001d436`

## pseudocode

```c
Gdiplus::SolidBrush *__fastcall Gdiplus::SolidBrush::SolidBrush(
        Gdiplus::SolidBrush *this,
        const struct Gdiplus::Color *a2)
{
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  *((_DWORD *)this + 4) = 6;
  *(_QWORD *)this = &Gdiplus::SolidBrush::`vftable';
  *((_DWORD *)this + 4) = GdipCreateSolidFill(*(unsigned int *)a2, &v4);
  *((_QWORD *)this + 1) = v4;
  return this;
}

```

## disassembly

```asm
0x18001d40c  push    rbx
0x18001d40e  sub     rsp, 20h
0x18001d412  and     [rsp+28h+arg_0], 0
0x18001d418  mov     rbx, rcx
0x18001d41b  mov     rax, rdx
0x18001d41e  mov     dword ptr [rcx+10h], 6
0x18001d425  lea     rcx, ??_7SolidBrush@Gdiplus@@6B@; const Gdiplus::SolidBrush::`vftable'
0x18001d42c  lea     rdx, [rsp+28h+arg_0]
0x18001d431  mov     [rbx], rcx
0x18001d434  mov     ecx, [rax]
0x18001d436  call    cs:__imp_GdipCreateSolidFill
0x18001d43d  nop     dword ptr [rax+rax+00h]
0x18001d442  mov     [rbx+10h], eax
0x18001d445  mov     rax, [rsp+28h+arg_0]
0x18001d44a  mov     [rbx+8], rax
0x18001d44e  mov     rax, rbx
0x18001d451  add     rsp, 20h
0x18001d455  pop     rbx
0x18001d456  retn
```
