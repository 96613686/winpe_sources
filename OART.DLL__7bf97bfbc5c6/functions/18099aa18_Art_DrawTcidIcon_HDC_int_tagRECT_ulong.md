# Art::DrawTcidIcon(HDC__ *,int,tagRECT &,ulong)

- ea: `0x18099aa18`
- end: `0x18099ac44`
- name: `?DrawTcidIcon@Art@@YAXPEAUHDC__@@HAEAUtagRECT@@K@Z`
- size: `556`
- prototype: `void __fastcall(HDC hdc, HDC, int, struct tagRECT *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18099a2e0`

## callees

- `0x180070fe0`
- `0x180071720`
- `0x18099aa18`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetAPI@CommandBarVisuals@ToolBar@Mso@@YAAEAUIMsoToolBarCommandBarVisualsApi@123@XZ` at `0x18099ab31`
- `mso40uiWin32Client!__imp_?GetAPI@CommandBarVisuals@ToolBar@Mso@@YAAEAUIMsoToolBarCommandBarVisualsApi@123@XZ` at `0x18099ab31`
- `mso40uiWin32Client!__imp_??0PaintContext@@QEAA@PEAUHDC__@@PEAUtagRGBQUAD@@HH@Z` at `0x18099ab68`
- `mso40uiWin32Client!__imp_??0PaintContext@@QEAA@PEAUHDC__@@PEAUtagRGBQUAD@@HH@Z` at `0x18099ab68`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x18099aa52`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x18099aa52`
- `mso40uiWin32Client!__imp_?GetITheming@Theming@@YAAEAUITheming@1@XZ` at `0x18099aa63`
- `mso40uiWin32Client!__imp_?GetITheming@Theming@@YAAEAUITheming@1@XZ` at `0x18099aa63`
- `mso40uiWin32Client!__imp_?MsoAlphaBlend@@YAHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@Z` at `0x18099abee`
- `mso40uiWin32Client!__imp_?MsoAlphaBlend@@YAHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@Z` at `0x18099abee`
- `Mso20Win32Client!__imp_?MsoGetSystemScaleFactor@Mso@@YA?AV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@Math@@XZ` at `0x18099ab4a`
- `Mso20Win32Client!__imp_?MsoGetSystemScaleFactor@Mso@@YA?AV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@Math@@XZ` at `0x18099ab4a`
- `GDI32!SetTextColor` at `0x18099aac5`
- `GDI32!SetTextColor` at `0x18099aac5`
- `GDI32!CreateDIBSection` at `0x18099ab0f`
- `GDI32!CreateDIBSection` at `0x18099ab0f`
- `GDI32!SelectObject` at `0x18099ab28`
- `GDI32!SelectObject` at `0x18099abfa`
- `GDI32!SelectObject` at `0x18099ab28`
- `GDI32!SelectObject` at `0x18099abfa`
- `GDI32!DeleteObject` at `0x18099ac04`
- `GDI32!DeleteObject` at `0x18099ac04`
- `GDI32!CreateCompatibleDC` at `0x18099aab5`
- `GDI32!CreateCompatibleDC` at `0x18099aab5`
- `GDI32!DeleteDC` at `0x18099ac12`
- `GDI32!DeleteDC` at `0x18099ac12`
- `USER32!InflateRect` at `0x18099aa98`
- `USER32!InflateRect` at `0x18099aa98`

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
0x18099aa18  mov     rax, rsp
0x18099aa1b  mov     [rax+10h], rbx
0x18099aa1f  push    rbp
0x18099aa20  push    rsi
0x18099aa21  push    rdi
0x18099aa22  push    r12
0x18099aa24  push    r13
0x18099aa26  push    r14
0x18099aa28  push    r15
0x18099aa2a  lea     rbp, [rax-58h]
0x18099aa2e  sub     rsp, 120h
0x18099aa35  movaps  xmmword ptr [rax-48h], xmm6
0x18099aa39  mov     rax, cs:__security_cookie
0x18099aa40  xor     rax, rsp
0x18099aa43  mov     [rbp+50h+var_50], rax
0x18099aa47  mov     r13, r8
0x18099aa4a  mov     [rsp+150h+color], r9d
0x18099aa4f  mov     r12, rcx
0x18099aa52  call    cs:__imp_?MsoFCbvHighContrast@@YAHXZ; MsoFCbvHighContrast(void)
0x18099aa58  xor     ebx, ebx
0x18099aa5a  mov     edi, 1
0x18099aa5f  test    eax, eax
0x18099aa61  jnz     short loc_18099AA84
0x18099aa63  call    cs:__imp_?GetITheming@Theming@@YAAEAUITheming@1@XZ; Theming::GetITheming(void)
0x18099aa69  mov     rdx, rax
0x18099aa6c  mov     rcx, [rax]
0x18099aa6f  mov     rax, [rcx+38h]
0x18099aa73  mov     rcx, rdx
0x18099aa76  call    cs:__guard_dispatch_icall_fptr
0x18099aa7c  cmp     eax, edi
0x18099aa7e  jnz     short loc_18099AA84
0x18099aa80  mov     [rsp+150h+color], ebx
0x18099aa84  movups  xmm0, xmmword ptr [r13+0]
0x18099aa89  or      edx, 0FFFFFFFFh; dx
0x18099aa8c  lea     rcx, [rbp+50h+rc]; lprc
0x18099aa90  mov     r8d, edx; dy
0x18099aa93  movdqu  xmmword ptr [rbp+50h+rc.left], xmm0
0x18099aa98  call    cs:__imp_InflateRect
0x18099aa9e  mov     r14d, [r13+0Ch]
0x18099aaa2  mov     rcx, r12; hdc
0x18099aaa5  sub     r14d, [r13+4]
0x18099aaa9  mov     [rbp+50h+rc.right], r14d
0x18099aaad  mov     [rbp+50h+rc.bottom], r14d
0x18099aab1  mov     qword ptr [rbp+50h+rc.left], rbx
0x18099aab5  call    cs:__imp_CreateCompatibleDC
0x18099aabb  mov     edx, [rsp+150h+color]; color
0x18099aabf  mov     rcx, rax; hdc
0x18099aac2  mov     r15, rax
0x18099aac5  call    cs:__imp_SetTextColor
0x18099aacb  mov     ecx, r14d
0x18099aace  mov     [rsp+150h+offset], ebx; offset
0x18099aad2  neg     ecx
0x18099aad4  mov     [rsp+150h+ppvBits], rbx
0x18099aad9  mov     [rbp+50h+pbmi.bmiHeader.biHeight], ecx
0x18099aadc  lea     r9, [rsp+150h+ppvBits]; ppvBits
0x18099aae1  xorps   xmm0, xmm0
0x18099aae4  mov     qword ptr [rbp+50h+pbmi.bmiHeader.biClrImportant], rbx
0x18099aae8  mov     rcx, r15; hdc
0x18099aaeb  mov     [rbp+50h+pbmi.bmiHeader.biSize], 28h ; '('
0x18099aaf2  xor     r8d, r8d; usage
0x18099aaf5  mov     qword ptr [rbp+50h+pbmi.bmiHeader.biPlanes], 200001h
0x18099aafd  lea     rdx, [rbp+50h+pbmi]; pbmi
0x18099ab01  mov     [rbp+50h+pbmi.bmiHeader.biWidth], r14d
0x18099ab05  movdqu  xmmword ptr [rbp+50h+pbmi.bmiHeader.biSizeImage], xmm0
0x18099ab0a  mov     [rsp+150h+hSection], rbx; hSection
0x18099ab0f  call    cs:__imp_CreateDIBSection
0x18099ab15  mov     [rbp+50h+ho], rax
0x18099ab19  test    rax, rax
0x18099ab1c  jz      loc_18099AC18
0x18099ab22  mov     rdx, rax; h
0x18099ab25  mov     rcx, r15; hdc
0x18099ab28  call    cs:__imp_SelectObject
0x18099ab2e  mov     rsi, rax
0x18099ab31  call    cs:__imp_?GetAPI@CommandBarVisuals@ToolBar@Mso@@YAAEAUIMsoToolBarCommandBarVisualsApi@123@XZ; Mso::ToolBar::CommandBarVisuals::GetAPI(void)
0x18099ab37  mov     rdi, rax
0x18099ab3a  mov     rcx, [rax]
0x18099ab3d  mov     [rsp+150h+var_D4], 0
0x18099ab42  mov     rbx, [rcx]
0x18099ab45  lea     rcx, [rsp+150h+var_F0]
0x18099ab4a  call    cs:__imp_?MsoGetSystemScaleFactor@Mso@@YA?AV?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UDeviceIndependentPixels@2@@Math@@@Math@@XZ; Mso::MsoGetSystemScaleFactor(void)
0x18099ab50  mov     r8, [rsp+150h+ppvBits]
0x18099ab55  lea     rcx, [rbp+50h+var_88]
0x18099ab59  mov     r9d, r14d
0x18099ab5c  mov     dword ptr [rsp+150h+hSection], r14d
0x18099ab61  mov     rdx, r15
0x18099ab64  movss   xmm6, dword ptr [rax]
0x18099ab68  call    cs:__imp_??0PaintContext@@QEAA@PEAUHDC__@@PEAUtagRGBQUAD@@HH@Z; PaintContext::PaintContext(HDC__ *,tagRGBQUAD *,int,int)
0x18099ab6e  xor     edx, edx
0x18099ab70  lea     rcx, [rsp+150h+var_D8]
0x18099ab75  mov     qword ptr [rsp+150h+var_108], rcx
0x18099ab7a  lea     r9, [rbp+50h+rc]
0x18099ab7e  mov     dword ptr [rsp+150h+var_110], edx
0x18099ab82  lea     rcx, [rsp+150h+color]
0x18099ab87  movss   [rsp+150h+var_118], xmm6
0x18099ab8d  mov     r8d, 7F6Bh
0x18099ab93  mov     qword ptr [rsp+150h+var_120], rcx
0x18099ab98  mov     rcx, rdi
0x18099ab9b  mov     byte ptr [rsp+150h+offset], dl
0x18099ab9f  mov     byte ptr [rsp+150h+hSection], dl
0x18099aba3  mov     rdx, rax
0x18099aba6  mov     rax, rbx
0x18099aba9  call    cs:__guard_dispatch_icall_fptr
0x18099abaf  mov     edx, [r13+8]
0x18099abb3  xor     ebx, ebx
0x18099abb5  mov     r8d, [r13+4]
0x18099abb9  sub     edx, r14d
0x18099abbc  mov     [rsp+150h+var_F0], 1FF0000h
0x18099abc4  mov     r9d, r14d
0x18099abc7  mov     eax, [rsp+150h+var_F0]
0x18099abcb  mov     rcx, r12
0x18099abce  mov     [rsp+150h+var_100], eax
0x18099abd2  mov     [rsp+150h+var_108], r14d
0x18099abd7  mov     dword ptr [rsp+150h+var_110], r14d
0x18099abdc  mov     [rsp+150h+var_118], ebx
0x18099abe0  mov     [rsp+150h+var_120], ebx
0x18099abe4  mov     qword ptr [rsp+150h+offset], r15
0x18099abe9  mov     dword ptr [rsp+150h+hSection], r14d
0x18099abee  call    cs:__imp_?MsoAlphaBlend@@YAHPEAUHDC__@@HHHH0HHHHU_BLENDFUNCTION@@@Z; MsoAlphaBlend(HDC__ *,int,int,int,int,HDC__ *,int,int,int,int,_BLENDFUNCTION)
0x18099abf4  mov     rdx, rsi; h
0x18099abf7  mov     rcx, r15; hdc
0x18099abfa  call    cs:__imp_SelectObject
0x18099ac00  mov     rcx, [rbp+50h+ho]; ho
0x18099ac04  call    cs:__imp_DeleteObject
0x18099ac0a  test    r15, r15
0x18099ac0d  jz      short loc_18099AC18
0x18099ac0f  mov     rcx, r15; hdc
0x18099ac12  call    cs:__imp_DeleteDC
0x18099ac18  mov     rcx, [rbp+50h+var_50]
0x18099ac1c  xor     rcx, rsp; StackCookie
0x18099ac1f  call    __security_check_cookie
0x18099ac24  lea     r11, [rsp+150h+var_30]
0x18099ac2c  mov     rbx, [r11+48h]
0x18099ac30  movaps  xmm6, xmmword ptr [r11-10h]
0x18099ac35  mov     rsp, r11
0x18099ac38  pop     r15
0x18099ac3a  pop     r14
0x18099ac3c  pop     r13
0x18099ac3e  pop     r12
0x18099ac40  pop     rdi
0x18099ac41  pop     rsi
0x18099ac42  pop     rbp
0x18099ac43  retn
```
