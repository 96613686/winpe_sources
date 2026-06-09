# GdipUtil::PalettizedGraphics::PalettizedGraphics(HDC__ *)

- ea: `0x18002a9d8`
- end: `0x18002aa79`
- name: `??0PalettizedGraphics@GdipUtil@@QEAA@PEAUHDC__@@@Z`
- size: `161`
- prototype: `_QWORD(GdipUtil::PalettizedGraphics *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002a954`

## callees

- `0x18002a9d8`
- `0x18002ac94`
- `0x18005bcb4`
- `0x18007b000`

## import_xrefs

- `gdiplus!GdipCreateFromHDC` at `0x18002aa33`
- `gdiplus!GdipCreateFromHDC` at `0x18002aa33`
- `GDI32!SelectPalette` at `0x18002aa13`
- `GDI32!SelectPalette` at `0x18002aa13`
- `GDI32!RealizePalette` at `0x18002aa1c`
- `GDI32!RealizePalette` at `0x18002aa1c`
- `GDI32!GetDeviceCaps` at `0x18002a9f5`
- `GDI32!GetDeviceCaps` at `0x18002a9f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
GdipUtil::PalettizedGraphics *__fastcall GdipUtil::PalettizedGraphics::PalettizedGraphics(
        GdipUtil::PalettizedGraphics *this,
        HDC a2)
{
  GdipUtilPrivate *v4; // rcx
  HPALETTE CachedGdiplusPalette; // rax
  int v6; // eax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF

  if ( GetDeviceCaps(a2, 12) == 8 )
  {
    CachedGdiplusPalette = (HPALETTE)GdipUtilPrivate::GetCachedGdiplusPalette(v4);
    if ( CachedGdiplusPalette )
    {
      SelectPalette(a2, CachedGdiplusPalette, 0);
      RealizePalette(a2);
    }
  }
  v9 = 0;
  v6 = GdipCreateFromHDC(a2, &v9);
  *((_QWORD *)this + 1) = v9;
  *((_DWORD *)this + 4) = 0;
  if ( v6 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v6);
    throw (Base::GdiException *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18002a9d8  mov     [rsp+arg_8], rbx
0x18002a9dd  mov     [rsp+arg_0], rcx
0x18002a9e2  push    rdi
0x18002a9e3  sub     rsp, 40h
0x18002a9e7  mov     rdi, rdx
0x18002a9ea  mov     rbx, rcx
0x18002a9ed  mov     edx, 0Ch; index
0x18002a9f2  mov     rcx, rdi; hdc
0x18002a9f5  call    cs:__imp_GetDeviceCaps
0x18002a9fb  cmp     eax, 8
0x18002a9fe  jnz     short loc_18002AA22
0x18002aa00  call    ?GetCachedGdiplusPalette@GdipUtilPrivate@@YAPEAUHPALETTE__@@XZ; GdipUtilPrivate::GetCachedGdiplusPalette(void)
0x18002aa05  test    rax, rax
0x18002aa08  jz      short loc_18002AA22
0x18002aa0a  xor     r8d, r8d; bForceBkgd
0x18002aa0d  mov     rdx, rax; hPal
0x18002aa10  mov     rcx, rdi; hdc
0x18002aa13  call    cs:__imp_SelectPalette
0x18002aa19  mov     rcx, rdi; hdc
0x18002aa1c  call    cs:__imp_RealizePalette
0x18002aa22  mov     [rsp+48h+arg_10], 0
0x18002aa2b  lea     rdx, [rsp+48h+arg_10]
0x18002aa30  mov     rcx, rdi
0x18002aa33  call    cs:__imp_GdipCreateFromHDC
0x18002aa39  mov     rcx, [rsp+48h+arg_10]
0x18002aa3e  mov     [rbx+8], rcx
0x18002aa42  mov     dword ptr [rbx+10h], 0
0x18002aa49  test    eax, eax
0x18002aa4b  jz      short loc_18002AA6B
0x18002aa4d  mov     edx, eax; int
0x18002aa4f  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18002aa54  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x18002aa59  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x18002aa60  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18002aa65  call    _CxxThrowException_0
0x18002aa6b  mov     rax, rbx
0x18002aa6e  mov     rbx, [rsp+48h+arg_8]
0x18002aa73  add     rsp, 40h
0x18002aa77  pop     rdi
0x18002aa78  retn
```
