# CCanvas::SetBrush(ulong,uchar,bool)

- ea: `0x180023dec`
- end: `0x180023fca`
- name: `?SetBrush@CCanvas@@QEAAJKE_N@Z`
- size: `478`
- prototype: `__int64 __fastcall(CCanvas *__hidden this, COLORREF color, unsigned __int8, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003b548`

## callees

- `0x180010918`
- `0x180023dec`
- `0x1800240dc`
- `0x180098b18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e95`
- `GDI32!CreateSolidBrush` at `0x180023e83`
- `GDI32!CreateSolidBrush` at `0x180023e83`
- `GDI32!SetPolyFillMode` at `0x180023e6f`
- `GDI32!SetPolyFillMode` at `0x180023e6f`
- `GDI32!CreatePen` at `0x180023ece`
- `GDI32!CreatePen` at `0x180023ece`
- `GDI32!SelectObject` at `0x180023eba`
- `GDI32!SelectObject` at `0x180023ef4`
- `GDI32!SelectObject` at `0x180023eba`
- `GDI32!SelectObject` at `0x180023ef4`
- `GDI32!DeleteObject` at `0x180023e16`
- `GDI32!DeleteObject` at `0x180023e16`
- `gdiplus!GdipGetSmoothingMode` at `0x180023f83`
- `gdiplus!GdipGetSmoothingMode` at `0x180023f83`
- `gdiplus!GdipSetSmoothingMode` at `0x180023fab`
- `gdiplus!GdipSetSmoothingMode` at `0x180023fab`
- `gdiplus!GdipAlloc` at `0x180023f47`
- `gdiplus!GdipAlloc` at `0x180023f47`

## pseudocode

```c
signed int __fastcall CCanvas::SetBrush(CCanvas *this, COLORREF color, char a3, unsigned __int8 a4)
{
  int v5; // ebp
  void *v8; // rcx
  Gdiplus::Region *v9; // rcx
  HDC v10; // rcx
  int v11; // eax
  HBRUSH SolidBrush; // rax
  signed int result; // eax
  HPEN Pen; // rax
  HDC v15; // rcx
  Gdiplus::SolidBrush *v16; // rax
  __int64 v17; // rdi
  int SmoothingMode; // eax
  __int64 v19; // rdi
  __int64 v20; // rdx
  int v21; // eax
  COLORREF v22; // [rsp+50h] [rbp+8h] BYREF

  v5 = a4;
  if ( *((_DWORD *)this + 61) )
  {
    v8 = (void *)*((_QWORD *)this + 41);
    if ( v8 )
      DeleteObject(v8);
    *((_QWORD *)this + 41) = 0;
  }
  else
  {
    v9 = (Gdiplus::Region *)*((_QWORD *)this + 29);
    if ( v9 )
      Gdiplus::Region::`scalar deleting destructor'(v9, color);
    *((_QWORD *)this + 29) = 0;
  }
  CCanvas::ResetPen(this);
  if ( !*((_DWORD *)this + 61) )
  {
    if ( *((_QWORD *)this + 1) )
    {
      v22 = BYTE2(color) | color & 0xFF00 | (((unsigned __int8)color | ((unsigned __int8)~a3 << 8)) << 16);
      v16 = (Gdiplus::SolidBrush *)GdipAlloc(24);
      if ( v16 )
        v16 = (Gdiplus::SolidBrush *)Gdiplus::SolidBrush::SolidBrush(v16, (const struct Gdiplus::Color *)&v22);
      *((_QWORD *)this + 3) = v16;
      if ( !v16 )
        return -2147024882;
      v17 = *((_QWORD *)this + 1);
      v22 = -1;
      SmoothingMode = GdipGetSmoothingMode(*(_QWORD *)v17, &v22);
      if ( SmoothingMode )
        *(_DWORD *)(v17 + 8) = SmoothingMode;
      v19 = *((_QWORD *)this + 1);
      v20 = (unsigned int)(4 * v5);
      *((_DWORD *)this + 8) = v22;
      *((_DWORD *)this + 9) = v20;
      if ( v19 )
      {
        v21 = GdipSetSmoothingMode(*(_QWORD *)v19, v20);
        if ( v21 )
          *(_DWORD *)(v19 + 8) = v21;
      }
      *((_BYTE *)this + 200) = a3;
      return 0;
    }
    return -2147467261;
  }
  v10 = (HDC)*((_QWORD *)this + 31);
  if ( !v10 )
    return -2147467261;
  v11 = SetPolyFillMode(v10, 2);
  *((_DWORD *)this + 80) = color;
  *((_DWORD *)this + 74) = v11;
  SolidBrush = CreateSolidBrush(color);
  *((_QWORD *)this + 36) = SolidBrush;
  if ( SolidBrush )
  {
    *((_QWORD *)this + 35) = SelectObject(*((HDC *)this + 31), SolidBrush);
    Pen = CreatePen(0, 0, color);
    *((_QWORD *)this + 34) = Pen;
    if ( Pen )
    {
      v15 = (HDC)*((_QWORD *)this + 31);
      *((_DWORD *)this + 77) = 0;
      *((_QWORD *)this + 33) = SelectObject(v15, Pen);
      return 0;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180023dec  push    rbx
0x180023dee  push    rbp
0x180023def  push    rsi
0x180023df0  push    rdi
0x180023df1  sub     rsp, 28h
0x180023df5  cmp     dword ptr [rcx+0F4h], 0
0x180023dfc  mov     sil, r8b
0x180023dff  movzx   ebp, r9b
0x180023e03  mov     edi, edx
0x180023e05  mov     rbx, rcx
0x180023e08  jz      short loc_180023E29
0x180023e0a  mov     rcx, [rcx+148h]; ho
0x180023e11  test    rcx, rcx
0x180023e14  jz      short loc_180023E1C
0x180023e16  call    cs:__imp_DeleteObject
0x180023e1c  mov     qword ptr [rbx+148h], 0
0x180023e27  jmp     short loc_180023E45
0x180023e29  mov     rcx, [rcx+0E8h]; this
0x180023e30  test    rcx, rcx
0x180023e33  jz      short loc_180023E3A
0x180023e35  call    ??_GRegion@Gdiplus@@QEAAPEAXI@Z; Gdiplus::Region::`scalar deleting destructor'(uint)
0x180023e3a  mov     qword ptr [rbx+0E8h], 0
0x180023e45  mov     rcx, rbx; this
0x180023e48  call    ?ResetPen@CCanvas@@QEAAXXZ; CCanvas::ResetPen(void)
0x180023e4d  cmp     dword ptr [rbx+0F4h], 0
0x180023e54  jz      loc_180023F06
0x180023e5a  mov     rcx, [rbx+0F8h]; hdc
0x180023e61  test    rcx, rcx
0x180023e64  jz      loc_180023F0D
0x180023e6a  mov     edx, 2; mode
0x180023e6f  call    cs:__imp_SetPolyFillMode
0x180023e75  mov     ecx, edi; color
0x180023e77  mov     [rbx+140h], edi
0x180023e7d  mov     [rbx+128h], eax
0x180023e83  call    cs:__imp_CreateSolidBrush
0x180023e89  mov     [rbx+120h], rax
0x180023e90  test    rax, rax
0x180023e93  jnz     short loc_180023EB0
0x180023e95  call    cs:__imp_GetLastError
0x180023e9b  test    eax, eax
0x180023e9d  jle     loc_180023FC1
0x180023ea3  movzx   eax, ax
0x180023ea6  or      eax, 80070000h
0x180023eab  jmp     loc_180023FC1
0x180023eb0  mov     rcx, [rbx+0F8h]; hdc
0x180023eb7  mov     rdx, rax; h
0x180023eba  call    cs:__imp_SelectObject
0x180023ec0  mov     r8d, edi; color
0x180023ec3  xor     edx, edx; cWidth
0x180023ec5  xor     ecx, ecx; iStyle
0x180023ec7  mov     [rbx+118h], rax
0x180023ece  call    cs:__imp_CreatePen
0x180023ed4  mov     [rbx+110h], rax
0x180023edb  test    rax, rax
0x180023ede  jz      short loc_180023E95
0x180023ee0  mov     rcx, [rbx+0F8h]; hdc
0x180023ee7  mov     rdx, rax; h
0x180023eea  mov     dword ptr [rbx+134h], 0
0x180023ef4  call    cs:__imp_SelectObject
0x180023efa  mov     [rbx+108h], rax
0x180023f01  jmp     loc_180023FBF
0x180023f06  cmp     qword ptr [rbx+8], 0
0x180023f0b  jnz     short loc_180023F17
0x180023f0d  mov     eax, 80004003h
0x180023f12  jmp     loc_180023FC1
0x180023f17  mov     al, sil
0x180023f1a  not     al
0x180023f1c  movzx   ecx, al
0x180023f1f  shl     ecx, 8
0x180023f22  movzx   eax, dil
0x180023f26  or      ecx, eax
0x180023f28  movzx   eax, di
0x180023f2b  shl     ecx, 10h
0x180023f2e  and     eax, 0FFFFFF00h
0x180023f33  or      ecx, eax
0x180023f35  shr     edi, 10h
0x180023f38  movzx   eax, dil
0x180023f3c  or      ecx, eax
0x180023f3e  mov     [rsp+48h+arg_0], ecx
0x180023f42  mov     ecx, 18h
0x180023f47  call    cs:__imp_GdipAlloc
0x180023f4d  test    rax, rax
0x180023f50  jz      short loc_180023F5F
0x180023f52  lea     rdx, [rsp+48h+arg_0]; struct Gdiplus::Color *
0x180023f57  mov     rcx, rax; this
0x180023f5a  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x180023f5f  mov     [rbx+18h], rax
0x180023f63  test    rax, rax
0x180023f66  jnz     short loc_180023F6F
0x180023f68  mov     eax, 8007000Eh
0x180023f6d  jmp     short loc_180023FC1
0x180023f6f  mov     rdi, [rbx+8]
0x180023f73  lea     rdx, [rsp+48h+arg_0]
0x180023f78  mov     [rsp+48h+arg_0], 0FFFFFFFFh
0x180023f80  mov     rcx, [rdi]
0x180023f83  call    cs:__imp_GdipGetSmoothingMode
0x180023f89  test    eax, eax
0x180023f8b  jz      short loc_180023F90
0x180023f8d  mov     [rdi+8], eax
0x180023f90  mov     rdi, [rbx+8]
0x180023f94  mov     edx, ebp
0x180023f96  mov     eax, [rsp+48h+arg_0]
0x180023f9a  shl     edx, 2
0x180023f9d  mov     [rbx+20h], eax
0x180023fa0  mov     [rbx+24h], edx
0x180023fa3  test    rdi, rdi
0x180023fa6  jz      short loc_180023FB8
0x180023fa8  mov     rcx, [rdi]
0x180023fab  call    cs:__imp_GdipSetSmoothingMode
0x180023fb1  test    eax, eax
0x180023fb3  jz      short loc_180023FB8
0x180023fb5  mov     [rdi+8], eax
0x180023fb8  mov     [rbx+0C8h], sil
0x180023fbf  xor     eax, eax
0x180023fc1  add     rsp, 28h
0x180023fc5  pop     rdi
0x180023fc6  pop     rsi
0x180023fc7  pop     rbp
0x180023fc8  pop     rbx
0x180023fc9  retn
```
