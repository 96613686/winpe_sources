# Jot::CFloatieWnd::InvalidateRender(void)

- ea: `0x1400650a0`
- end: `0x1400652f4`
- name: `?InvalidateRender@CFloatieWnd@Jot@@AEAAXXZ`
- size: `596`
- prototype: `void __fastcall(Jot::CFloatieWnd *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140068e90`
- `0x140098310`
- `0x1400984c0`

## callees

- `0x14003b6e8`
- `0x140064af8`
- `0x1400650a0`
- `0x1400652f4`
- `0x140065328`
- `0x14006535c`
- `0x1400653c8`
- `0x140065408`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1400650c0`
- `GDI32!CreateCompatibleDC` at `0x1400650c0`
- `GDI32!SelectObject` at `0x1400650e8`
- `GDI32!SelectObject` at `0x14006523c`
- `GDI32!SelectObject` at `0x1400650e8`
- `GDI32!SelectObject` at `0x14006523c`
- `GDI32!DeleteDC` at `0x14006524b`
- `GDI32!DeleteDC` at `0x14006524b`
- `GDI32!GdiFlush` at `0x14006527f`
- `GDI32!GdiFlush` at `0x14006527f`
- `GDI32!GetDeviceCaps` at `0x14006510c`
- `GDI32!GetDeviceCaps` at `0x14006510c`
- `GDI32!DeleteObject` at `0x1400652bf`
- `GDI32!DeleteObject` at `0x1400652bf`
- `gdiplus!GdipGraphicsClear` at `0x140065124`
- `gdiplus!GdipGraphicsClear` at `0x140065124`
- `gdiplus!GdipDeleteGraphics` at `0x14006521c`
- `gdiplus!GdipDeleteGraphics` at `0x14006521c`
- `gdiplus!GdipFree` at `0x140065225`
- `gdiplus!GdipFree` at `0x140065225`
- `USER32!UpdateLayeredWindow` at `0x14006520d`
- `USER32!UpdateLayeredWindow` at `0x14006520d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Jot::CFloatieWnd::InvalidateRender(Jot::CFloatieWnd *this)
{
  HDC CompatibleDC; // rax
  int v3; // r8d
  HDC hdcSrc; // rdi
  HGDIOBJ v5; // r15
  struct Gdiplus::Graphics *v6; // r14
  int DeviceCaps; // eax
  __int64 v8; // rdx
  int v9; // eax
  Jot::CJotApp *v10; // rbx
  unsigned int BitmapID; // eax
  bool v12; // r8
  Gdiplus::Image *GdiPlusBitmap; // rbx
  unsigned int Height; // r13d
  unsigned int v15; // r12d
  unsigned int Width; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  int v19; // r9d
  void *v20; // rcx
  __int64 v21; // rdx
  unsigned int pptSrc; // [rsp+28h] [rbp-50h]
  HPALETTE crKey; // [rsp+30h] [rbp-48h]
  __int128 v24; // [rsp+50h] [rbp-28h] BYREF
  HDC v25; // [rsp+60h] [rbp-18h]
  __int64 v26; // [rsp+68h] [rbp-10h]
  BLENDFUNCTION pblend; // [rsp+C0h] [rbp+48h] BYREF
  POINT v28; // [rsp+C8h] [rbp+50h] BYREF
  SIZE psize; // [rsp+D0h] [rbp+58h] BYREF
  struct Gdiplus::Graphics *v30; // [rsp+D8h] [rbp+60h]

  v26 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  hdcSrc = CompatibleDC;
  v25 = CompatibleDC;
  if ( !*((_QWORD *)this + 18) )
  {
    v19 = *((_DWORD *)this + 28);
    v24 = 0;
    Ofc::CDIBSection::Create((Ofc::CDIBSection *)&v24, CompatibleDC, v3, v19, v19, pptSrc, crKey);
    GdiFlush();
    if ( !(_QWORD)v24 )
      goto LABEL_15;
    v20 = (void *)*((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = v24;
    *(_QWORD *)&v24 = v20;
    v21 = *((_QWORD *)this + 19);
    *((_QWORD *)this + 19) = *((_QWORD *)&v24 + 1);
    *((_QWORD *)&v24 + 1) = v21;
    if ( v20 )
      DeleteObject(v20);
  }
  *(_QWORD *)&v24 = hdcSrc;
  v5 = SelectObject(hdcSrc, *((HGDIOBJ *)this + 18));
  *((_QWORD *)&v24 + 1) = v5;
  v6 = Gdiplus::Graphics::FromHDC(hdcSrc);
  v30 = v6;
  DeviceCaps = GetDeviceCaps(hdcSrc, 12);
  v8 = 0x1000000;
  if ( DeviceCaps < 24 )
    v8 = 0x4000000;
  v9 = GdipGraphicsClear(*(_QWORD *)v6, v8);
  if ( v9 )
    *((_DWORD *)v6 + 2) = v9;
  v10 = Jot::CJotApp::s_pSingletonJotApp;
  BitmapID = Jot::CFloatieWnd::GetBitmapID(this, *((_BYTE *)this + 128));
  GdiPlusBitmap = Jot::CJotApp::GetGdiPlusBitmap(v10, BitmapID, v12, 0);
  if ( *((_BYTE *)this + 129) )
  {
    Height = Gdiplus::Image::GetHeight(GdiPlusBitmap);
    v15 = -Gdiplus::Image::GetWidth(GdiPlusBitmap);
    Width = Gdiplus::Image::GetWidth(GdiPlusBitmap);
  }
  else
  {
    Height = Gdiplus::Image::GetHeight(GdiPlusBitmap);
    v15 = Gdiplus::Image::GetWidth(GdiPlusBitmap);
    Width = 0;
  }
  Gdiplus::Graphics::DrawImage(v6, GdiPlusBitmap, Width, 0, v15, Height);
  pblend = (BLENDFUNCTION)33488896;
  v28 = 0;
  v17 = Gdiplus::Image::GetWidth(GdiPlusBitmap);
  if ( v17 > 0x7FFFFFFF || (psize.cx = v17, v18 = Gdiplus::Image::GetHeight(GdiPlusBitmap), v18 > 0x7FFFFFFF) )
    __fastfail(5u);
  psize.cy = v18;
  UpdateLayeredWindow(*((HWND *)this + 1), 0, 0, &psize, hdcSrc, &v28, 0, &pblend, 2u);
  if ( v6 )
  {
    GdipDeleteGraphics(*(_QWORD *)v6);
    GdipFree(v6);
  }
  if ( v5 && hdcSrc )
    SelectObject(hdcSrc, v5);
LABEL_15:
  if ( hdcSrc )
    DeleteDC(hdcSrc);
}

```

## disassembly

```asm
0x1400650a0  push    rbp
0x1400650a2  push    rbx
0x1400650a3  push    rsi
0x1400650a4  push    rdi
0x1400650a5  push    r12
0x1400650a7  push    r13
0x1400650a9  push    r14
0x1400650ab  push    r15
0x1400650ad  mov     rbp, rsp
0x1400650b0  sub     rsp, 78h
0x1400650b4  mov     rsi, rcx
0x1400650b7  xor     r12d, r12d
0x1400650ba  mov     [rbp+var_10], r12
0x1400650be  xor     ecx, ecx; hdc
0x1400650c0  call    cs:__imp_CreateCompatibleDC
0x1400650c6  mov     rdi, rax
0x1400650c9  mov     [rbp+var_18], rax
0x1400650cd  cmp     [rsi+90h], r12
0x1400650d4  jz      loc_140065262
0x1400650da  mov     qword ptr [rbp+var_28], rdi
0x1400650de  mov     rdx, [rsi+90h]; h
0x1400650e5  mov     rcx, rdi; hdc
0x1400650e8  call    cs:__imp_SelectObject
0x1400650ee  mov     r15, rax
0x1400650f1  mov     qword ptr [rbp+var_28+8], rax
0x1400650f5  mov     rcx, rdi; HDC
0x1400650f8  call    ?FromHDC@Graphics@Gdiplus@@SAPEAV12@PEAUHDC__@@@Z; Gdiplus::Graphics::FromHDC(HDC__ *)
0x1400650fd  mov     r14, rax
0x140065100  mov     [rbp+arg_18], rax
0x140065104  mov     edx, 0Ch; index
0x140065109  mov     rcx, rdi; hdc
0x14006510c  call    cs:__imp_GetDeviceCaps
0x140065112  mov     rcx, [r14]
0x140065115  cmp     eax, 18h
0x140065118  mov     edx, 1000000h
0x14006511d  jge     short loc_140065124
0x14006511f  mov     edx, 4000000h
0x140065124  call    cs:__imp_GdipGraphicsClear
0x14006512a  test    eax, eax
0x14006512c  jnz     loc_1400652E4
0x140065132  mov     rbx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x140065139  mov     dl, [rsi+80h]; bool
0x14006513f  mov     rcx, rsi; this
0x140065142  call    ?GetBitmapID@CFloatieWnd@Jot@@AEAAH_N@Z; Jot::CFloatieWnd::GetBitmapID(bool)
0x140065147  xor     r9d, r9d; bool
0x14006514a  mov     edx, eax; unsigned int
0x14006514c  mov     rcx, rbx; this
0x14006514f  call    ?GetGdiPlusBitmap@CJotApp@Jot@@QEAAPEAVBitmap@Gdiplus@@I_N0@Z; Jot::CJotApp::GetGdiPlusBitmap(uint,bool,bool)
0x140065154  mov     rbx, rax
0x140065157  mov     rcx, rax; this
0x14006515a  cmp     [rsi+81h], r12b
0x140065161  jz      loc_1400652CA
0x140065167  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x14006516c  mov     r13d, eax
0x14006516f  mov     rcx, rbx; this
0x140065172  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x140065177  mov     r12d, eax
0x14006517a  neg     r12d
0x14006517d  mov     rcx, rbx; this
0x140065180  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x140065185  mov     dword ptr [rsp+78h+pptSrc], r13d
0x14006518a  mov     dword ptr [rsp+78h+hdcSrc], r12d
0x14006518f  xor     r9d, r9d
0x140065192  mov     r8d, eax
0x140065195  mov     rdx, rbx
0x140065198  mov     rcx, r14
0x14006519b  call    ?DrawImage@Graphics@Gdiplus@@QEAA?AW4Status@2@PEAVImage@2@HHHH@Z; Gdiplus::Graphics::DrawImage(Gdiplus::Image *,int,int,int,int)
0x1400651a0  xor     r12d, r12d
0x1400651a3  mov     dword ptr [rbp+arg_0.BlendOp], 1FF0000h
0x1400651aa  mov     qword ptr [rbp+arg_8.x], r12
0x1400651ae  mov     rcx, rbx; this
0x1400651b1  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x1400651b6  mov     r13d, 7FFFFFFFh
0x1400651bc  cmp     eax, r13d
0x1400651bf  ja      loc_1400652ED
0x1400651c5  mov     [rbp+psize.cx], eax
0x1400651c8  mov     rcx, rbx; this
0x1400651cb  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x1400651d0  cmp     eax, r13d
0x1400651d3  ja      loc_1400652ED
0x1400651d9  mov     [rbp+psize.cy], eax
0x1400651dc  mov     [rsp+78h+dwFlags], 2; dwFlags
0x1400651e4  lea     rax, [rbp+arg_0]
0x1400651e8  mov     [rsp+78h+pblend], rax; pblend
0x1400651ed  mov     dword ptr [rsp+78h+crKey], r12d; crKey
0x1400651f2  lea     rax, [rbp+arg_8]
0x1400651f6  mov     [rsp+78h+pptSrc], rax; pptSrc
0x1400651fb  mov     [rsp+78h+hdcSrc], rdi; hdcSrc
0x140065200  lea     r9, [rbp+psize]; psize
0x140065204  xor     r8d, r8d; pptDst
0x140065207  xor     edx, edx; hdcDst
0x140065209  mov     rcx, [rsi+8]; hWnd
0x14006520d  call    cs:__imp_UpdateLayeredWindow
0x140065213  nop
0x140065214  test    r14, r14
0x140065217  jz      short loc_14006522C
0x140065219  mov     rcx, [r14]
0x14006521c  call    cs:__imp_GdipDeleteGraphics
0x140065222  mov     rcx, r14
0x140065225  call    cs:__imp_GdipFree
0x14006522b  nop
0x14006522c  test    r15, r15
0x14006522f  jz      short loc_140065243
0x140065231  test    rdi, rdi
0x140065234  jz      short loc_140065243
0x140065236  mov     rdx, r15; h
0x140065239  mov     rcx, rdi; hdc
0x14006523c  call    cs:__imp_SelectObject
0x140065242  nop
0x140065243  test    rdi, rdi
0x140065246  jz      short loc_140065251
0x140065248  mov     rcx, rdi; hdc
0x14006524b  call    cs:__imp_DeleteDC
0x140065251  add     rsp, 78h
0x140065255  pop     r15
0x140065257  pop     r14
0x140065259  pop     r13
0x14006525b  pop     r12
0x14006525d  pop     rdi
0x14006525e  pop     rsi
0x14006525f  pop     rbx
0x140065260  pop     rbp
0x140065261  retn
0x140065262  mov     r9d, [rsi+70h]; int
0x140065266  xorps   xmm0, xmm0
0x140065269  movdqu  [rbp+var_28], xmm0
0x14006526e  mov     dword ptr [rsp+78h+hdcSrc], r9d; int
0x140065273  mov     rdx, rdi; HDC
0x140065276  lea     rcx, [rbp+var_28]; this
0x14006527a  call    ?Create@CDIBSection@Ofc@@QEAAXPEAUHDC__@@HHHIPEAUHPALETTE__@@@Z; Ofc::CDIBSection::Create(HDC__ *,int,int,int,uint,HPALETTE__ *)
0x14006527f  call    cs:__imp_GdiFlush
0x140065285  mov     rax, qword ptr [rbp+var_28]
0x140065289  test    rax, rax
0x14006528c  jz      short loc_140065243
0x14006528e  mov     rcx, [rsi+90h]; ho
0x140065295  mov     [rsi+90h], rax
0x14006529c  mov     qword ptr [rbp+var_28], rcx
0x1400652a0  mov     rdx, [rsi+98h]
0x1400652a7  mov     rax, qword ptr [rbp+var_28+8]
0x1400652ab  mov     [rsi+98h], rax
0x1400652b2  mov     qword ptr [rbp+var_28+8], rdx
0x1400652b6  test    rcx, rcx
0x1400652b9  jz      loc_1400650DA
0x1400652bf  call    cs:__imp_DeleteObject
0x1400652c5  jmp     loc_1400650DA
0x1400652ca  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x1400652cf  mov     r13d, eax
0x1400652d2  mov     rcx, rbx; this
0x1400652d5  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x1400652da  mov     r12d, eax
0x1400652dd  xor     eax, eax
0x1400652df  jmp     loc_140065185
0x1400652e4  mov     [r14+8], eax
0x1400652e8  jmp     loc_140065132
0x1400652ed  mov     ecx, 5
0x1400652f2  int     29h; Win8: RtlFailFast(ecx)
```
