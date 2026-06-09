# Gdiplus::Bitmap::Bitmap(HINSTANCE__ *,ushort const *)

- ea: `0x18001d304`
- end: `0x18001d352`
- name: `??0Bitmap@Gdiplus@@QEAA@PEAUHINSTANCE__@@PEBG@Z`
- size: `78`
- prototype: `__int64 __fastcall(Gdiplus::Bitmap *__hidden this, HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18001e4a8`

## import_xrefs

- `gdiplus!GdipCreateBitmapFromResource` at `0x18001d330`
- `gdiplus!GdipCreateBitmapFromResource` at `0x18001d330`

## pseudocode

```c
Gdiplus::Bitmap *__fastcall Gdiplus::Bitmap::Bitmap(Gdiplus::Bitmap *this, HINSTANCE a2, const unsigned __int16 *a3)
{
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  *(_QWORD *)this = &Gdiplus::Image::`vftable';
  *((_DWORD *)this + 4) = GdipCreateBitmapFromResource(g_DLLModuleHandle, a3, &v5);
  *((_QWORD *)this + 1) = v5;
  return this;
}

```

## disassembly

```asm
0x18001d304  mov     [rsp+arg_8], rdx
0x18001d309  push    rbx
0x18001d30a  sub     rsp, 20h
0x18001d30e  and     [rsp+28h+arg_8], 0
0x18001d314  mov     rbx, rcx
0x18001d317  lea     rcx, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x18001d31e  mov     rdx, r8
0x18001d321  lea     r8, [rsp+28h+arg_8]
0x18001d326  mov     [rbx], rcx
0x18001d329  mov     rcx, cs:?g_DLLModuleHandle@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_DLLModuleHandle
0x18001d330  call    cs:__imp_GdipCreateBitmapFromResource
0x18001d337  nop     dword ptr [rax+rax+00h]
0x18001d33c  mov     [rbx+10h], eax
0x18001d33f  mov     rax, [rsp+28h+arg_8]
0x18001d344  mov     [rbx+8], rax
0x18001d348  mov     rax, rbx
0x18001d34b  add     rsp, 20h
0x18001d34f  pop     rbx
0x18001d350  retn
```
