# Gdiplus::TextureBrush::TextureBrush(Gdiplus::Image *,Gdiplus::WrapMode,int,int,int,int)

- ea: `0x180024ad4`
- end: `0x180024b42`
- name: `??0TextureBrush@Gdiplus@@QEAA@PEAVImage@1@W4WrapMode@1@HHHH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180025f30`

## import_xrefs

- `gdiplus!GdipCreateTexture2I` at `0x180024b27`
- `gdiplus!GdipCreateTexture2I` at `0x180024b27`

## pseudocode

```c
__int64 __fastcall Gdiplus::TextureBrush::TextureBrush(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7)
{
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  *(_DWORD *)(a1 + 16) = 6;
  v9 = 0;
  *(_QWORD *)a1 = &Gdiplus::LinearGradientBrush::`vftable';
  *(_DWORD *)(a1 + 16) = GdipCreateTexture2I(*(_QWORD *)(a2 + 8), a3, 0, 0, a6, a7, &v9);
  *(_QWORD *)(a1 + 8) = v9;
  return a1;
}

```

## disassembly

```asm
0x180024ad4  push    rbx
0x180024ad6  sub     rsp, 40h
0x180024ada  mov     r11, rdx
0x180024add  mov     dword ptr [rcx+10h], 6
0x180024ae4  mov     r10d, r8d
0x180024ae7  mov     [rsp+48h+arg_0], 0
0x180024af0  lea     rax, ??_7LinearGradientBrush@Gdiplus@@6B@; const Gdiplus::LinearGradientBrush::`vftable'
0x180024af7  mov     rbx, rcx
0x180024afa  mov     [rcx], rax
0x180024afd  xor     r9d, r9d
0x180024b00  mov     rcx, [r11+8]
0x180024b04  lea     rax, [rsp+48h+arg_0]
0x180024b09  mov     [rsp+48h+var_18], rax
0x180024b0e  xor     r8d, r8d
0x180024b11  mov     eax, [rsp+48h+arg_30]
0x180024b18  mov     edx, r10d
0x180024b1b  mov     [rsp+48h+var_20], eax
0x180024b1f  mov     eax, [rsp+48h+arg_28]
0x180024b23  mov     [rsp+48h+var_28], eax
0x180024b27  call    cs:__imp_GdipCreateTexture2I
0x180024b2d  mov     [rbx+10h], eax
0x180024b30  mov     rax, [rsp+48h+arg_0]
0x180024b35  mov     [rbx+8], rax
0x180024b39  mov     rax, rbx
0x180024b3c  add     rsp, 40h
0x180024b40  pop     rbx
0x180024b41  retn
```
