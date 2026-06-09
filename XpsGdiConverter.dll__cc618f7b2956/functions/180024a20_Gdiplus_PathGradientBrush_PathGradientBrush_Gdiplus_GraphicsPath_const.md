# Gdiplus::PathGradientBrush::PathGradientBrush(Gdiplus::GraphicsPath const *)

- ea: `0x180024a20`
- end: `0x180024a69`
- name: `??0PathGradientBrush@Gdiplus@@QEAA@PEBVGraphicsPath@1@@Z`
- size: `73`
- prototype: `__int64 __fastcall(Gdiplus::PathGradientBrush *__hidden this, const struct Gdiplus::GraphicsPath *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180026438`

## import_xrefs

- `gdiplus!GdipCreatePathGradientFromPath` at `0x180024a4e`
- `gdiplus!GdipCreatePathGradientFromPath` at `0x180024a4e`

## pseudocode

```c
Gdiplus::PathGradientBrush *__fastcall Gdiplus::PathGradientBrush::PathGradientBrush(
        Gdiplus::PathGradientBrush *this,
        const struct Gdiplus::GraphicsPath *a2)
{
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  *((_DWORD *)this + 4) = 6;
  v4 = 0;
  *(_QWORD *)this = &Gdiplus::LinearGradientBrush::`vftable';
  *((_DWORD *)this + 4) = GdipCreatePathGradientFromPath(*(_QWORD *)a2, &v4);
  *((_QWORD *)this + 1) = v4;
  return this;
}

```

## disassembly

```asm
0x180024a20  push    rbx
0x180024a22  sub     rsp, 20h
0x180024a26  mov     rbx, rcx
0x180024a29  mov     dword ptr [rcx+10h], 6
0x180024a30  mov     rax, rdx
0x180024a33  mov     [rsp+28h+arg_0], 0
0x180024a3c  lea     rcx, ??_7LinearGradientBrush@Gdiplus@@6B@; const Gdiplus::LinearGradientBrush::`vftable'
0x180024a43  lea     rdx, [rsp+28h+arg_0]
0x180024a48  mov     [rbx], rcx
0x180024a4b  mov     rcx, [rax]
0x180024a4e  call    cs:__imp_GdipCreatePathGradientFromPath
0x180024a54  mov     [rbx+10h], eax
0x180024a57  mov     rax, [rsp+28h+arg_0]
0x180024a5c  mov     [rbx+8], rax
0x180024a60  mov     rax, rbx
0x180024a63  add     rsp, 20h
0x180024a67  pop     rbx
0x180024a68  retn
```
