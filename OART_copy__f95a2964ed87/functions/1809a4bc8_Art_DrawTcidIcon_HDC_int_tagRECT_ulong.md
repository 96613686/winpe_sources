# Art::DrawTcidIcon(HDC__ *,int,tagRECT &,ulong)

- ea: `0x1809a4bc8`
- end: `0x1809a4df4`
- name: `?DrawTcidIcon@Art@@YAXPEAUHDC__@@HAEAUtagRECT@@K@Z`
- size: `556`
- prototype: `void __fastcall(HDC hdc, HDC, int, struct tagRECT *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1809a4490`

## callees

- `0x180278e70`
- `0x180279050`
- `0x1809a4bc8`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetAPI@CommandBarVisuals@ToolBar@Mso@@YAAEAUIMsoToolBarCommandBarVisualsApi@123@XZ` at `0x1809a4ce1`
- `mso40uiWin32Client!__imp_?GetAPI@CommandBarVisuals@ToolBar@Mso@@YAAEAUIMsoToolBarCommandBarVisualsApi@123@XZ` at `0x1809a4ce1`
- `mso40uiWin32Client!__imp_??0PaintContext@@QEAA@PEAUHDC__@@PEAUtagRGBQUAD@@HH@Z` at `0x1809a4d18`
- `mso40uiWin32Client!__imp_??0PaintContext@@QEAA@PEAUHDC__@@PEAUtagRGBQUAD@@HH@Z` at `0x1809a4d18`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1809a4c02`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1809a4c02`
- `mso40uiWin32Client!__imp_?GetITheming@Theming@@YAAEAUITheming@1@XZ` at `0x1809a4c13`
- `mso40uiWin32Client!__imp_?GetITheming@Theming@@YAAEAUITheming@1@XZ` at `0x1809a4c13`
- `mso40uiWin32Client!__imp_?MsoAlphaBlend@@YAHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@Z` at `0x1809a4d9e`
- `mso40uiWin32Client!__imp_?MsoAlphaBlend@@YAHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@Z` at `0x1809a4d9e`
- `Mso20Win32Client!__imp_?MsoGetSystemScaleFactor@Mso@@YA?AV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@Math@@XZ` at `0x1809a4cfa`
- `Mso20Win32Client!__imp_?MsoGetSystemScaleFactor@Mso@@YA?AV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@Math@@XZ` at `0x1809a4cfa`
- `GDI32!SetTextColor` at `0x1809a4c75`
- `GDI32!SetTextColor` at `0x1809a4c75`
- `GDI32!CreateDIBSection` at `0x1809a4cbf`
- `GDI32!CreateDIBSection` at `0x1809a4cbf`
- `GDI32!SelectObject` at `0x1809a4cd8`
- `GDI32!SelectObject` at `0x1809a4daa`
- `GDI32!SelectObject` at `0x1809a4cd8`
- `GDI32!SelectObject` at `0x1809a4daa`
- `GDI32!DeleteObject` at `0x1809a4db4`
- `GDI32!DeleteObject` at `0x1809a4db4`
- `GDI32!CreateCompatibleDC` at `0x1809a4c65`
- `GDI32!CreateCompatibleDC` at `0x1809a4c65`
- `GDI32!DeleteDC` at `0x1809a4dc2`
- `GDI32!DeleteDC` at `0x1809a4dc2`
- `USER32!InflateRect` at `0x1809a4c48`
- `USER32!InflateRect` at `0x1809a4c48`

## pseudocode

```c
void __fastcall Art::DrawTcidIcon(HDC hdc, HDC a2, struct tagRECT *a3, struct tagRECT *a4)
{
  Theming *v6; // rcx
  struct Theming::ITheming *ITheming; // rax
  LONG v8; // r14d
  HDC CompatibleDC; // r15
  HBITMAP v10; // rax
  HGDIOBJ v11; // rsi
  Mso::ToolBar::CommandBarVisuals *v12; // rcx
  struct Mso::ToolBar::CommandBarVisuals::IMsoToolBarCommandBarVisualsApi *API; // rdi
  void (__fastcall **v14)(struct Mso::ToolBar::CommandBarVisuals::IMsoToolBarCommandBarVisualsApi *, PaintContext *, __int64, struct tagRECT *, int, int, COLORREF *, int, _DWORD, _BYTE *); // rcx
  void (__fastcall *v15)(struct Mso::ToolBar::CommandBarVisuals::IMsoToolBarCommandBarVisualsApi *, PaintContext *, __int64, struct tagRECT *, int, int, COLORREF *, int, _DWORD, _BYTE *); // rbx
  int v16; // xmm6_4
  PaintContext *v17; // rax
  LONG top; // r8d
  int v19; // edx
  int hSection; // [rsp+28h] [rbp-E0h]
  int offset; // [rsp+30h] [rbp-D8h]
  int v22; // [rsp+68h] [rbp-A0h] BYREF
  COLORREF color[2]; // [rsp+70h] [rbp-98h] BYREF
  void *ppvBits; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v25[8]; // [rsp+80h] [rbp-88h] BYREF
  HGDIOBJ ho; // [rsp+88h] [rbp-80h]
  struct tagRECT rc; // [rsp+90h] [rbp-78h] BYREF
  BITMAPINFO pbmi; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v29[56]; // [rsp+D0h] [rbp-38h] BYREF

  color[0] = (unsigned int)a4;
  if ( !MsoFCbvHighContrast() )
  {
    ITheming = Theming::GetITheming(v6);
    if ( (*(unsigned int (__fastcall **)(struct Theming::ITheming *))(*(_QWORD *)ITheming + 56LL))(ITheming) == 1 )
      color[0] = 0;
  }
  rc = *a3;
  InflateRect(&rc, -1, -1);
  v8 = a3->bottom - a3->top;
  rc.right = v8;
  rc.bottom = v8;
  *(_QWORD *)&rc.left = 0;
  CompatibleDC = CreateCompatibleDC(hdc);
  SetTextColor(CompatibleDC, color[0]);
  ppvBits = 0;
  pbmi.bmiHeader.biHeight = -v8;
  pbmi.bmiHeader.biSize = 40;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  pbmi.bmiHeader.biWidth = v8;
  memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
  v10 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
  ho = v10;
  if ( v10 )
  {
    v11 = SelectObject(CompatibleDC, v10);
    API = Mso::ToolBar::CommandBarVisuals::GetAPI(v12);
    v14 = *(void (__fastcall ***)(struct Mso::ToolBar::CommandBarVisuals::IMsoToolBarCommandBarVisualsApi *, PaintContext *, __int64, struct tagRECT *, int, int, COLORREF *, int, _DWORD, _BYTE *))API;
    v25[4] = 0;
    v15 = *v14;
    v16 = *(_DWORD *)Mso::MsoGetSystemScaleFactor(&v22);
    v17 = PaintContext::PaintContext((PaintContext *)v29, CompatibleDC, (struct tagRGBQUAD *)ppvBits, v8, v8);
    LOBYTE(offset) = 0;
    LOBYTE(hSection) = 0;
    v15(API, v17, 32619, &rc, hSection, offset, color, v16, 0, v25);
    top = a3->top;
    v19 = a3->right - v8;
    v22 = 33488896;
    MsoAlphaBlend(hdc, v19, top, v8, v8, CompatibleDC, 0, 0, v8, v8, (struct _BLENDFUNCTION)33488896);
    SelectObject(CompatibleDC, v11);
    DeleteObject(ho);
    if ( CompatibleDC )
      DeleteDC(CompatibleDC);
  }
}

```

## disassembly

```asm
0x1809a4bc8  mov     rax, rsp
0x1809a4bcb  mov     [rax+10h], rbx
0x1809a4bcf  push    rbp
0x1809a4bd0  push    rsi
0x1809a4bd1  push    rdi
0x1809a4bd2  push    r12
0x1809a4bd4  push    r13
0x1809a4bd6  push    r14
0x1809a4bd8  push    r15
0x1809a4bda  lea     rbp, [rax-58h]
0x1809a4bde  sub     rsp, 120h
0x1809a4be5  movaps  xmmword ptr [rax-48h], xmm6
0x1809a4be9  mov     rax, cs:__security_cookie
0x1809a4bf0  xor     rax, rsp
0x1809a4bf3  mov     [rbp+50h+var_50], rax
0x1809a4bf7  mov     r13, r8
0x1809a4bfa  mov     [rsp+150h+color], r9d
0x1809a4bff  mov     r12, rcx
0x1809a4c02  call    cs:__imp_?MsoFCbvHighContrast@@YAHXZ; MsoFCbvHighContrast(void)
0x1809a4c08  xor     ebx, ebx
0x1809a4c0a  mov     edi, 1
0x1809a4c0f  test    eax, eax
0x1809a4c11  jnz     short loc_1809A4C34
0x1809a4c13  call    cs:__imp_?GetITheming@Theming@@YAAEAUITheming@1@XZ; Theming::GetITheming(void)
0x1809a4c19  mov     rdx, rax
0x1809a4c1c  mov     rcx, [rax]
0x1809a4c1f  mov     rax, [rcx+38h]
0x1809a4c23  mov     rcx, rdx
0x1809a4c26  call    cs:__guard_dispatch_icall_fptr
0x1809a4c2c  cmp     eax, edi
0x1809a4c2e  jnz     short loc_1809A4C34
0x1809a4c30  mov     [rsp+150h+color], ebx
0x1809a4c34  movups  xmm0, xmmword ptr [r13+0]
0x1809a4c39  or      edx, 0FFFFFFFFh; dx
0x1809a4c3c  lea     rcx, [rbp+50h+rc]; lprc
0x1809a4c40  mov     r8d, edx; dy
0x1809a4c43  movdqu  xmmword ptr [rbp+50h+rc.left], xmm0
0x1809a4c48  call    cs:__imp_InflateRect
0x1809a4c4e  mov     r14d, [r13+0Ch]
0x1809a4c52  mov     rcx, r12; hdc
0x1809a4c55  sub     r14d, [r13+4]
0x1809a4c59  mov     [rbp+50h+rc.right], r14d
0x1809a4c5d  mov     [rbp+50h+rc.bottom], r14d
0x1809a4c61  mov     qword ptr [rbp+50h+rc.left], rbx
0x1809a4c65  call    cs:__imp_CreateCompatibleDC
0x1809a4c6b  mov     edx, [rsp+150h+color]; color
0x1809a4c6f  mov     rcx, rax; hdc
0x1809a4c72  mov     r15, rax
0x1809a4c75  call    cs:__imp_SetTextColor
0x1809a4c7b  mov     ecx, r14d
0x1809a4c7e  mov     [rsp+150h+offset], ebx; offset
0x1809a4c82  neg     ecx
0x1809a4c84  mov     [rsp+150h+ppvBits], rbx
0x1809a4c89  mov     [rbp+50h+pbmi.bmiHeader.biHeight], ecx
0x1809a4c8c  lea     r9, [rsp+150h+ppvBits]; ppvBits
0x1809a4c91  xorps   xmm0, xmm0
0x1809a4c94  mov     qword ptr [rbp+50h+pbmi.bmiHeader.biClrImportant], rbx
0x1809a4c98  mov     rcx, r15; hdc
0x1809a4c9b  mov     [rbp+50h+pbmi.bmiHeader.biSize], 28h ; '('
0x1809a4ca2  xor     r8d, r8d; usage
0x1809a4ca5  mov     qword ptr [rbp+50h+pbmi.bmiHeader.biPlanes], 200001h
0x1809a4cad  lea     rdx, [rbp+50h+pbmi]; pbmi
0x1809a4cb1  mov     [rbp+50h+pbmi.bmiHeader.biWidth], r14d
0x1809a4cb5  movdqu  xmmword ptr [rbp+50h+pbmi.bmiHeader.biSizeImage], xmm0
0x1809a4cba  mov     [rsp+150h+hSection], rbx; hSection
0x1809a4cbf  call    cs:__imp_CreateDIBSection
0x1809a4cc5  mov     [rbp+50h+ho], rax
0x1809a4cc9  test    rax, rax
0x1809a4ccc  jz      loc_1809A4DC8
0x1809a4cd2  mov     rdx, rax; h
0x1809a4cd5  mov     rcx, r15; hdc
0x1809a4cd8  call    cs:__imp_SelectObject
0x1809a4cde  mov     rsi, rax
0x1809a4ce1  call    cs:__imp_?GetAPI@CommandBarVisuals@ToolBar@Mso@@YAAEAUIMsoToolBarCommandBarVisualsApi@123@XZ; Mso::ToolBar::CommandBarVisuals::GetAPI(void)
0x1809a4ce7  mov     rdi, rax
0x1809a4cea  mov     rcx, [rax]
0x1809a4ced  mov     [rsp+150h+var_D4], 0
0x1809a4cf2  mov     rbx, [rcx]
0x1809a4cf5  lea     rcx, [rsp+150h+var_F0]
0x1809a4cfa  call    cs:__imp_?MsoGetSystemScaleFactor@Mso@@YA?AV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@Math@@XZ; Mso::MsoGetSystemScaleFactor(void)
0x1809a4d00  mov     r8, [rsp+150h+ppvBits]
0x1809a4d05  lea     rcx, [rbp+50h+var_88]
0x1809a4d09  mov     r9d, r14d
0x1809a4d0c  mov     dword ptr [rsp+150h+hSection], r14d
0x1809a4d11  mov     rdx, r15
0x1809a4d14  movss   xmm6, dword ptr [rax]
0x1809a4d18  call    cs:__imp_??0PaintContext@@QEAA@PEAUHDC__@@PEAUtagRGBQUAD@@HH@Z; PaintContext::PaintContext(HDC__ *,tagRGBQUAD *,int,int)
0x1809a4d1e  xor     edx, edx
0x1809a4d20  lea     rcx, [rsp+150h+var_D8]
0x1809a4d25  mov     qword ptr [rsp+150h+var_108], rcx
0x1809a4d2a  lea     r9, [rbp+50h+rc]
0x1809a4d2e  mov     dword ptr [rsp+150h+var_110], edx
0x1809a4d32  lea     rcx, [rsp+150h+color]
0x1809a4d37  movss   [rsp+150h+var_118], xmm6
0x1809a4d3d  mov     r8d, 7F6Bh
0x1809a4d43  mov     qword ptr [rsp+150h+var_120], rcx
0x1809a4d48  mov     rcx, rdi
0x1809a4d4b  mov     byte ptr [rsp+150h+offset], dl
0x1809a4d4f  mov     byte ptr [rsp+150h+hSection], dl
0x1809a4d53  mov     rdx, rax
0x1809a4d56  mov     rax, rbx
0x1809a4d59  call    cs:__guard_dispatch_icall_fptr
0x1809a4d5f  mov     edx, [r13+8]
0x1809a4d63  xor     ebx, ebx
0x1809a4d65  mov     r8d, [r13+4]
0x1809a4d69  sub     edx, r14d
0x1809a4d6c  mov     [rsp+150h+var_F0], 1FF0000h
0x1809a4d74  mov     r9d, r14d
0x1809a4d77  mov     eax, [rsp+150h+var_F0]
0x1809a4d7b  mov     rcx, r12
0x1809a4d7e  mov     [rsp+150h+var_100], eax
0x1809a4d82  mov     [rsp+150h+var_108], r14d
0x1809a4d87  mov     dword ptr [rsp+150h+var_110], r14d
0x1809a4d8c  mov     [rsp+150h+var_118], ebx
0x1809a4d90  mov     [rsp+150h+var_120], ebx
0x1809a4d94  mov     qword ptr [rsp+150h+offset], r15
0x1809a4d99  mov     dword ptr [rsp+150h+hSection], r14d
0x1809a4d9e  call    cs:__imp_?MsoAlphaBlend@@YAHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@Z; MsoAlphaBlend(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int,_BLENDFUNCTION)
0x1809a4da4  mov     rdx, rsi; h
0x1809a4da7  mov     rcx, r15; hdc
0x1809a4daa  call    cs:__imp_SelectObject
0x1809a4db0  mov     rcx, [rbp+50h+ho]; ho
0x1809a4db4  call    cs:__imp_DeleteObject
0x1809a4dba  test    r15, r15
0x1809a4dbd  jz      short loc_1809A4DC8
0x1809a4dbf  mov     rcx, r15; hdc
0x1809a4dc2  call    cs:__imp_DeleteDC
0x1809a4dc8  mov     rcx, [rbp+50h+var_50]
0x1809a4dcc  xor     rcx, rsp; StackCookie
0x1809a4dcf  call    __security_check_cookie
0x1809a4dd4  lea     r11, [rsp+150h+var_30]
0x1809a4ddc  mov     rbx, [r11+48h]
0x1809a4de0  movaps  xmm6, xmmword ptr [r11-10h]
0x1809a4de5  mov     rsp, r11
0x1809a4de8  pop     r15
0x1809a4dea  pop     r14
0x1809a4dec  pop     r13
0x1809a4dee  pop     r12
0x1809a4df0  pop     rdi
0x1809a4df1  pop     rsi
0x1809a4df2  pop     rbp
0x1809a4df3  retn
```
