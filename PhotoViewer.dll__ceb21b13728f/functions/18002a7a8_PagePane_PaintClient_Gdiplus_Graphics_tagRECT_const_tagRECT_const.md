# PagePane::PaintClient(Gdiplus::Graphics *,tagRECT const &,tagRECT const &)

- ea: `0x18002a7a8`
- end: `0x18002a94c`
- name: `?PaintClient@PagePane@@QEAAXPEAVGraphics@Gdiplus@@AEBUtagRECT@@1@Z`
- size: `420`
- prototype: `void __fastcall(PagePane *__hidden this, struct Gdiplus::Graphics *, const struct tagRECT *, const struct tagRECT *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18002a66c`
- `0x180036c6c`
- `0x180037254`

## callees

- `0x1800046b8`
- `0x18002479c`
- `0x1800259e4`
- `0x18002a7a8`
- `0x18002aa80`

## import_xrefs

- `USER32!GetSysColor` at `0x18002a864`
- `USER32!GetSysColor` at `0x18002a864`
- `gdiplus!GdipSetSolidFillColor` at `0x18002a88c`
- `gdiplus!GdipSetSolidFillColor` at `0x18002a88c`
- `gdiplus!GdipFillRectangleI` at `0x18002a84a`
- `gdiplus!GdipFillRectangleI` at `0x18002a8ba`
- `gdiplus!GdipFillRectangleI` at `0x18002a84a`
- `gdiplus!GdipFillRectangleI` at `0x18002a8ba`
- `gdiplus!GdipDeleteBrush` at `0x18002a945`
- `gdiplus!GdipCreateSolidFill` at `0x18002a811`
- `gdiplus!GdipCreateSolidFill` at `0x18002a811`

## pseudocode

```c
void __fastcall PagePane::PaintClient(
        HWND *this,
        struct Gdiplus::Graphics *a2,
        const struct tagRECT *a3,
        const struct tagRECT *a4)
{
  int v7; // edx
  bool IsHighContrastOn; // bp
  unsigned __int8 v9; // r8
  unsigned int SysGdiplusColor; // eax
  int v11; // r12d
  int v12; // esi
  const struct tagRECT *v13; // r14
  int v14; // r15d
  __int64 v15; // rcx
  int v16; // eax
  DWORD SysColor; // eax
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  _QWORD v21[2]; // [rsp+30h] [rbp-48h] BYREF
  int v22; // [rsp+40h] [rbp-38h]
  const struct tagRECT *v23; // [rsp+98h] [rbp+20h] BYREF

  v23 = a4;
  IsHighContrastOn = UIBase::IsHighContrastOn((UIBase *)this);
  if ( IsHighContrastOn )
  {
    LOBYTE(v7) = -1;
    SysGdiplusColor = GdipUtil::GetSysGdiplusColor((GdipUtil *)5, v7, v9);
  }
  else
  {
    SysGdiplusColor = GetBackgroundColor(this[1]);
  }
  v23 = 0;
  v21[0] = &Gdiplus::LinearGradientBrush::`vftable';
  v11 = GdipCreateSolidFill(SysGdiplusColor, &v23);
  v12 = a3->bottom - a3->top;
  v13 = v23;
  v14 = a3->right - a3->left;
  v15 = *(_QWORD *)a2;
  v21[1] = v23;
  v16 = GdipFillRectangleI(v15, v23);
  if ( v16 )
    *((_DWORD *)a2 + 2) = v16;
  SysColor = GetSysColor(IsHighContrastOn ? 6 : 3);
  v18 = GdipSetSolidFillColor(v13, BYTE2(SysColor) | SysColor & 0xFF00 | ((SysColor | 0xFFFFFF00) << 16));
  v19 = *(_QWORD *)a2;
  if ( v18 )
    v11 = v18;
  v22 = v11;
  v20 = GdipFillRectangleI(v19, v13);
  if ( v20 )
    *((_DWORD *)a2 + 2) = v20;
  if ( !IsHighContrastOn )
  {
    Gdiplus::Graphics::FillRectangle(a2, v21, (unsigned int)a3->left, (unsigned int)(a3->bottom - 1), v14, 1);
    Gdiplus::Graphics::FillRectangle(a2, v21, (unsigned int)a3->left, (unsigned int)a3->top, 1, v12);
    Gdiplus::Graphics::FillRectangle(a2, v21, (unsigned int)a3->left, (unsigned int)(a3->right - 1), 1, v12);
  }
  GdipDeleteBrush(v13);
}

```

## disassembly

```asm
0x18002a7a8  mov     [rsp+arg_0], rbx
0x18002a7ad  mov     [rsp+arg_8], rbp
0x18002a7b2  mov     [rsp+arg_18], r9
0x18002a7b7  push    rsi
0x18002a7b8  push    rdi
0x18002a7b9  push    r12
0x18002a7bb  push    r14
0x18002a7bd  push    r15
0x18002a7bf  sub     rsp, 50h
0x18002a7c3  mov     rbx, r8
0x18002a7c6  mov     rdi, rdx
0x18002a7c9  mov     rsi, rcx
0x18002a7cc  call    ?IsHighContrastOn@UIBase@@YA_NXZ; UIBase::IsHighContrastOn(void)
0x18002a7d1  mov     bpl, al
0x18002a7d4  test    al, al
0x18002a7d6  jz      short loc_18002A7E6
0x18002a7d8  mov     dl, 0FFh; int
0x18002a7da  mov     ecx, 5; this
0x18002a7df  call    ?GetSysGdiplusColor@GdipUtil@@YAKHE@Z; GdipUtil::GetSysGdiplusColor(int,uchar)
0x18002a7e4  jmp     short loc_18002A7EF
0x18002a7e6  mov     rcx, [rsi+8]; HWND
0x18002a7ea  call    ?GetBackgroundColor@@YAKPEAUHWND__@@@Z; GetBackgroundColor(HWND__ *)
0x18002a7ef  lea     rcx, ??_7LinearGradientBrush@Gdiplus@@6B@; const Gdiplus::LinearGradientBrush::`vftable'
0x18002a7f6  mov     [rsp+78h+arg_18], 0
0x18002a802  mov     [rsp+78h+var_48], rcx
0x18002a807  lea     rdx, [rsp+78h+arg_18]
0x18002a80f  mov     ecx, eax
0x18002a811  call    cs:__imp_GdipCreateSolidFill
0x18002a817  mov     esi, [rbx+0Ch]
0x18002a81a  mov     r12d, eax
0x18002a81d  mov     r9d, [rbx+4]
0x18002a821  sub     esi, r9d
0x18002a824  mov     r15d, [rbx+8]
0x18002a828  mov     r14, [rsp+78h+arg_18]
0x18002a830  sub     r15d, [rbx]
0x18002a833  mov     rdx, r14
0x18002a836  mov     r8d, [rbx]
0x18002a839  mov     rcx, [rdi]
0x18002a83c  mov     [rsp+78h+var_50], esi
0x18002a840  mov     [rsp+78h+var_58], r15d
0x18002a845  mov     [rsp+78h+var_40], r14
0x18002a84a  call    cs:__imp_GdipFillRectangleI
0x18002a850  test    eax, eax
0x18002a852  jz      short loc_18002A857
0x18002a854  mov     [rdi+8], eax
0x18002a857  mov     al, bpl
0x18002a85a  neg     al
0x18002a85c  sbb     ecx, ecx
0x18002a85e  and     ecx, 3
0x18002a861  add     ecx, 3; nIndex
0x18002a864  call    cs:__imp_GetSysColor
0x18002a86a  movzx   ecx, ax
0x18002a86d  mov     r8d, 0FFFFFF00h
0x18002a873  movzx   edx, al
0x18002a876  and     ecx, r8d
0x18002a879  or      edx, r8d
0x18002a87c  shr     eax, 10h
0x18002a87f  shl     edx, 10h
0x18002a882  or      edx, ecx
0x18002a884  movzx   eax, al
0x18002a887  or      edx, eax
0x18002a889  mov     rcx, r14
0x18002a88c  call    cs:__imp_GdipSetSolidFillColor
0x18002a892  mov     r9d, [rbx+4]
0x18002a896  mov     rdx, r14
0x18002a899  mov     r8d, [rbx]
0x18002a89c  test    eax, eax
0x18002a89e  mov     rcx, [rdi]
0x18002a8a1  cmovnz  r12d, eax
0x18002a8a5  mov     [rsp+78h+var_38], r12d
0x18002a8aa  mov     r12d, 1
0x18002a8b0  mov     [rsp+78h+var_50], r12d
0x18002a8b5  mov     [rsp+78h+var_58], r15d
0x18002a8ba  call    cs:__imp_GdipFillRectangleI
0x18002a8c0  test    eax, eax
0x18002a8c2  jz      short loc_18002A8C7
0x18002a8c4  mov     [rdi+8], eax
0x18002a8c7  test    bpl, bpl
0x18002a8ca  jnz     short loc_18002A92A
0x18002a8cc  mov     r9d, [rbx+0Ch]
0x18002a8d0  lea     rdx, [rsp+78h+var_48]
0x18002a8d5  mov     r8d, [rbx]
0x18002a8d8  sub     r9d, r12d
0x18002a8db  mov     [rsp+78h+var_50], r12d
0x18002a8e0  mov     rcx, rdi
0x18002a8e3  mov     [rsp+78h+var_58], r15d
0x18002a8e8  call    ?FillRectangle@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@HHHH@Z; Gdiplus::Graphics::FillRectangle(Gdiplus::Brush const *,int,int,int,int)
0x18002a8ed  mov     r9d, [rbx+4]
0x18002a8f1  lea     rdx, [rsp+78h+var_48]
0x18002a8f6  mov     r8d, [rbx]
0x18002a8f9  mov     rcx, rdi
0x18002a8fc  mov     [rsp+78h+var_50], esi
0x18002a900  mov     [rsp+78h+var_58], r12d
0x18002a905  call    ?FillRectangle@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@HHHH@Z; Gdiplus::Graphics::FillRectangle(Gdiplus::Brush const *,int,int,int,int)
0x18002a90a  mov     r9d, [rbx+8]
0x18002a90e  lea     rdx, [rsp+78h+var_48]
0x18002a913  mov     r8d, [rbx]
0x18002a916  sub     r9d, r12d
0x18002a919  mov     [rsp+78h+var_50], esi
0x18002a91d  mov     rcx, rdi
0x18002a920  mov     [rsp+78h+var_58], r12d
0x18002a925  call    ?FillRectangle@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@HHHH@Z; Gdiplus::Graphics::FillRectangle(Gdiplus::Brush const *,int,int,int,int)
0x18002a92a  mov     rcx, r14
0x18002a92d  lea     r11, [rsp+78h+var_28]
0x18002a932  mov     rbx, [r11+30h]
0x18002a936  mov     rbp, [r11+38h]
0x18002a93a  mov     rsp, r11
0x18002a93d  pop     r15
0x18002a93f  pop     r14
0x18002a941  pop     r12
0x18002a943  pop     rdi
0x18002a944  pop     rsi
0x18002a945  jmp     cs:__imp_GdipDeleteBrush
```
