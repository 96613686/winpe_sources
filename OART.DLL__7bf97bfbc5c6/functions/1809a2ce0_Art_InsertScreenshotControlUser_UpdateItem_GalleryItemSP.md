# Art::InsertScreenshotControlUser::UpdateItem(GalleryItemSP &)

- ea: `0x1809a2ce0`
- end: `0x1809a3264`
- name: `?UpdateItem@InsertScreenshotControlUser@Art@@UEAAXAEAVGalleryItemSP@@@Z`
- size: `1412`
- prototype: `void __fastcall(Art::InsertScreenshotControlUser *__hidden this, struct GalleryItemSP *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000da00`
- `0x180030d88`
- `0x180070fe0`
- `0x180071720`
- `0x1800f4b68`
- `0x1802cec40`
- `0x1802fa070`
- `0x180337554`
- `0x1803375ac`
- `0x180598df8`
- `0x1805bb09c`
- `0x18061c90c`
- `0x18064025c`
- `0x1806454d0`
- `0x18066cc60`
- `0x180678a38`
- `0x1809a2ce0`

## import_xrefs

- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x1809a31a0`
- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x1809a31a0`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a2d5c`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a3204`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a322e`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a2d5c`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a3204`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809a322e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a2d22`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a31c3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a2d22`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809a31c3`
- `GDI32!StretchBlt` at `0x1809a3067`
- `GDI32!StretchBlt` at `0x1809a3067`
- `GDI32!SetBrushOrgEx` at `0x1809a300e`
- `GDI32!SetBrushOrgEx` at `0x1809a300e`
- `GDI32!SetStretchBltMode` at `0x1809a2ffd`
- `GDI32!SetStretchBltMode` at `0x1809a2ffd`
- `GDI32!GetPixel` at `0x1809a30a0`
- `GDI32!GetPixel` at `0x1809a30a0`
- `GDI32!SelectObject` at `0x1809a2e18`
- `GDI32!SelectObject` at `0x1809a30fd`
- `GDI32!SelectObject` at `0x1809a3147`
- `GDI32!SelectObject` at `0x1809a2e18`
- `GDI32!SelectObject` at `0x1809a30fd`
- `GDI32!SelectObject` at `0x1809a3147`
- `GDI32!DeleteDC` at `0x1809a3106`
- `GDI32!DeleteDC` at `0x1809a3150`
- `GDI32!DeleteDC` at `0x1809a3106`
- `GDI32!DeleteDC` at `0x1809a3150`
- `USER32!PrintWindow` at `0x1809a2e51`
- `USER32!PrintWindow` at `0x1809a2e51`
- `USER32!FillRect` at `0x1809a2ff0`
- `USER32!FillRect` at `0x1809a2ff0`
- `USER32!GetWindowDC` at `0x1809a2d72`
- `USER32!GetWindowDC` at `0x1809a2d72`
- `USER32!GetWindowRect` at `0x1809a2d9a`
- `USER32!GetWindowRect` at `0x1809a2d9a`
- `USER32!GetDesktopWindow` at `0x1809a2f40`
- `USER32!GetDesktopWindow` at `0x1809a2f40`

## pseudocode

```c
void __fastcall Art::InsertScreenshotControlUser::UpdateItem(
        Art::InsertScreenshotControlUser *this,
        struct GalleryItemSP *a2)
{
  __int64 v4; // rcx
  int v5; // r13d
  HWND v6; // rbx
  __int64 v7; // rdx
  HDC WindowDC; // rdi
  HDC hdcSrc; // rdi
  BOOL v10; // eax
  __int64 v11; // rdx
  char *v12; // rbx
  __int64 DPIFromUserInterface; // rax
  int v14; // r15d
  __int64 v15; // rax
  int v16; // eax
  int v17; // r12d
  int v18; // ebx
  double v19; // xmm1_8
  HWND DesktopWindow; // rax
  HPALETTE v21; // r8
  HDC v22; // r15
  __int64 v23; // rdx
  char v24; // r12
  int v25; // r14d
  int i; // eax
  NetUI::BaseValue *v27; // rbx
  __int64 v28; // rsi
  int wDest; // [rsp+60h] [rbp-E8h]
  int hDest; // [rsp+64h] [rbp-E4h]
  NetUI::BaseValue *v31; // [rsp+68h] [rbp-E0h] BYREF
  HBITMAP v32; // [rsp+70h] [rbp-D8h] BYREF
  HGDIOBJ h; // [rsp+78h] [rbp-D0h] BYREF
  NetUI::BaseValue *v34; // [rsp+80h] [rbp-C8h] BYREF
  HBITMAP v35; // [rsp+88h] [rbp-C0h] BYREF
  HDC hDC[2]; // [rsp+90h] [rbp-B8h] BYREF
  HDC hdc[2]; // [rsp+A0h] [rbp-A8h] BYREF
  _QWORD v38[2]; // [rsp+B0h] [rbp-98h] BYREF
  HDC v39[3]; // [rsp+C0h] [rbp-88h] BYREF
  HBRUSH hbr[3]; // [rsp+D8h] [rbp-70h] BYREF
  struct tagRECT Rect; // [rsp+F0h] [rbp-58h] BYREF
  RECT rc; // [rsp+100h] [rbp-48h] BYREF

  v4 = *(_QWORD *)a2;
  v5 = 0;
  if ( *(_QWORD *)a2 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64, __int64, NetUI::BaseValue **))(*(_QWORD *)v4 + 40LL))(v4, 126, &v31);
    if ( v31 )
    {
      v6 = (HWND)*((_QWORD *)v31 + 1);
      NetUI::BaseValue::Release(v31);
    }
    else
    {
      v6 = 0;
    }
    v31 = 0;
  }
  else
  {
    MsoShipAssertTagProc(7997216);
    v6 = 0;
  }
  v34 = 0;
  WindowDC = GetWindowDC(v6);
  if ( WindowDC )
  {
    Rect = 0;
    GetWindowRect(v6, &Rect);
    if ( Rect.right != Rect.left && Rect.bottom != Rect.top )
    {
      h = 0;
      Ofc::CHBitmap::Create((Ofc::CHBitmap *)&h, WindowDC, Rect.right - Rect.left, Rect.bottom - Rect.top);
      *(_OWORD *)hdc = 0;
      Ofc::CCompatibleHDC::Create((Ofc::CCompatibleHDC *)hdc, WindowDC, (HBITMAP)h);
      hdcSrc = hdc[0];
      v38[0] = hdc[0];
      v38[1] = SelectObject(hdc[0], h);
      if ( Art::InsertScreenshotControlUser::FIsCurrentProcess(v6) )
        v10 = PrintWindow(v6, hdcSrc, 2u);
      else
        v10 = Art::InsertScreenshotControlUser::CaptureWindow(v6, hdcSrc);
      if ( v10 )
      {
        v12 = (char *)this + 240;
        DPIFromUserInterface = Art::GetDPIFromUserInterface(&v35, (char *)this + 240);
        v14 = Art::ScaleForDPI(DPIFromUserInterface, 96);
        v15 = Art::GetDPIFromUserInterface(&v35, v12);
        v16 = Art::ScaleForDPI(v15, 96);
        v17 = v16;
        wDest = v14;
        hDest = v16;
        v18 = 0;
        v19 = (double)(Rect.right - Rect.left) / (double)(Rect.bottom - Rect.top);
        if ( v19 < 1.0 )
        {
          wDest = (int)((double)v16 * v19);
          v18 = (v14 - wDest) / 2;
        }
        else
        {
          hDest = (int)((double)v14 / v19);
          v5 = (v16 - hDest) / 2;
        }
        DesktopWindow = GetDesktopWindow();
        Ofc::CHDC::CHDC((Ofc::CHDC *)v39, DesktopWindow, v21);
        v32 = 0;
        Ofc::CHBitmap::Create((Ofc::CHBitmap *)&v32, v39[0], v14, v17);
        *(_OWORD *)hDC = 0;
        v35 = v32;
        Ofc::CCompatibleHDC::Create((Ofc::CCompatibleHDC *)hDC, v39[0], v32);
        *(_QWORD *)&rc.left = 0;
        rc.right = v14;
        rc.bottom = v17;
        v22 = hDC[0];
        Ofc::CHBrush::CHBrush((Ofc::CHBrush *)hbr, hDC[0], 0xFF00FFu);
        FillRect(v22, &rc, hbr[0]);
        SetStretchBltMode(v22, 4);
        SetBrushOrgEx(v22, 0, 0, 0);
        StretchBlt(v22, v18, v5, wDest, hDest, hdcSrc, 0, 0, Rect.right - Rect.left, Rect.bottom - Rect.top, 0xCC0020u);
        v24 = 0;
        LODWORD(v31) = wDest + v18;
        if ( v18 >= wDest + v18 )
          goto LABEL_27;
        while ( !v24 )
        {
          v25 = v5;
          for ( i = v5 + hDest; v25 < i; i = v5 + hDest )
          {
            if ( GetPixel(v22, v18, v25) )
            {
              v24 = 1;
              break;
            }
            ++v25;
          }
          if ( ++v18 >= (int)v31 )
          {
            if ( !v24 )
              goto LABEL_27;
            break;
          }
        }
        v32 = 0;
        if ( FlexUI::FlexValue::CreateImage(v35, (struct FlexUI::FlexValueSP *)&v34, 3u, 0xFF00FFu, 0, 0, 0, 1, 0) )
        {
          v27 = v34;
          v28 = *(_QWORD *)a2;
          if ( v28 )
          {
            if ( v34 )
            {
              NetUI::BaseValue::AddRef(v34);
              (*(void (__fastcall **)(__int64, _QWORD, __int64, NetUI::BaseValue *))(*(_QWORD *)v28 + 48LL))(
                v28,
                0,
                3,
                v27);
              NetUI::BaseValue::Release(v27);
            }
          }
          else
          {
            MsoShipAssertTagProc(7997248);
          }
        }
        else
        {
LABEL_27:
          FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<bool>,bool>(*(_QWORD *)a2, v23, 1082130440);
        }
        Ofc::CHBrush::Delete((Ofc::CHBrush *)hbr);
        if ( v22 )
        {
          if ( hDC[1] )
            SelectObject(v22, hDC[1]);
          DeleteDC(v22);
        }
        Ofc::CHBitmap::Reset((Ofc::CHBitmap *)&v32);
        Ofc::CHDC::~CHDC((Ofc::CHDC *)v39);
      }
      else
      {
        FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<bool>,bool>(*(_QWORD *)a2, v11, 1077936135);
      }
      Ofc::CGDIObjSelector::~CGDIObjSelector((Ofc::CGDIObjSelector *)v38);
      if ( hdcSrc )
      {
        if ( hdc[1] )
          SelectObject(hdcSrc, hdc[1]);
        DeleteDC(hdcSrc);
      }
      Ofc::CHBitmap::Reset((Ofc::CHBitmap *)&h);
    }
  }
  else
  {
    FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<bool>,bool>(*(_QWORD *)a2, v7, 1077936135);
  }
  if ( v34 )
    NetUI::BaseValue::Release(v34);
}

```

## disassembly

```asm
0x1809a2ce0  mov     [rsp+arg_10], rbx
0x1809a2ce5  mov     [rsp+arg_18], rsi
0x1809a2cea  push    rdi
0x1809a2ceb  push    r12
0x1809a2ced  push    r13
0x1809a2cef  push    r14
0x1809a2cf1  push    r15
0x1809a2cf3  sub     rsp, 120h
0x1809a2cfa  mov     rax, cs:__security_cookie
0x1809a2d01  xor     rax, rsp
0x1809a2d04  mov     [rsp+148h+var_38], rax
0x1809a2d0c  mov     rsi, rdx
0x1809a2d0f  mov     r15, rcx
0x1809a2d12  mov     rcx, [rdx]
0x1809a2d15  xor     r13d, r13d
0x1809a2d18  test    rcx, rcx
0x1809a2d1b  jnz     short loc_1809A2D2D
0x1809a2d1d  mov     ecx, 7A0720h
0x1809a2d22  call    cs:__imp_MsoShipAssertTagProc
0x1809a2d28  mov     ebx, r13d
0x1809a2d2b  jmp     short loc_1809A2D67
0x1809a2d2d  mov     [rsp+148h+var_E0], r13
0x1809a2d32  mov     rax, [rcx]
0x1809a2d35  lea     r8, [rsp+148h+var_E0]
0x1809a2d3a  mov     edx, 7Eh ; '~'
0x1809a2d3f  mov     rax, [rax+28h]
0x1809a2d43  call    cs:__guard_dispatch_icall_fptr
0x1809a2d49  mov     rcx, [rsp+148h+var_E0]
0x1809a2d4e  test    rcx, rcx
0x1809a2d51  jnz     short loc_1809A2D58
0x1809a2d53  mov     rbx, r13
0x1809a2d56  jmp     short loc_1809A2D62
0x1809a2d58  mov     rbx, [rcx+8]
0x1809a2d5c  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809a2d62  mov     [rsp+148h+var_E0], r13
0x1809a2d67  mov     [rsp+148h+var_C8], r13
0x1809a2d6f  mov     rcx, rbx; hWnd
0x1809a2d72  call    cs:__imp_GetWindowDC
0x1809a2d78  mov     rdi, rax
0x1809a2d7b  test    rax, rax
0x1809a2d7e  jz      loc_1809A320F
0x1809a2d84  xorps   xmm0, xmm0
0x1809a2d87  movups  xmmword ptr [rsp+148h+Rect.left], xmm0
0x1809a2d8f  lea     rdx, [rsp+148h+Rect]; lpRect
0x1809a2d97  mov     rcx, rbx; hWnd
0x1809a2d9a  call    cs:__imp_GetWindowRect
0x1809a2da0  mov     r8d, [rsp+148h+Rect.right]
0x1809a2da8  sub     r8d, [rsp+148h+Rect.left]; int
0x1809a2db0  jz      loc_1809A3221
0x1809a2db6  mov     r9d, [rsp+148h+Rect.bottom]
0x1809a2dbe  sub     r9d, [rsp+148h+Rect.top]; int
0x1809a2dc6  jz      loc_1809A3221
0x1809a2dcc  mov     [rsp+148h+h], r13
0x1809a2dd1  mov     rdx, rdi; HDC
0x1809a2dd4  lea     rcx, [rsp+148h+h]; this
0x1809a2dd9  call    ?Create@CHBitmap@Ofc@@QEAAXPEAUHDC__@@HH@Z; Ofc::CHBitmap::Create(HDC__ *,int,int)
0x1809a2dde  xorps   xmm0, xmm0
0x1809a2de1  movdqu  xmmword ptr [rsp+148h+hdc], xmm0
0x1809a2dea  mov     r8, [rsp+148h+h]; HBITMAP
0x1809a2def  mov     rdx, rdi; HDC
0x1809a2df2  lea     rcx, [rsp+148h+hdc]; this
0x1809a2dfa  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x1809a2dff  nop
0x1809a2e00  mov     rdi, [rsp+148h+hdc]
0x1809a2e08  mov     [rsp+148h+var_98], rdi
0x1809a2e10  mov     rdx, [rsp+148h+h]; h
0x1809a2e15  mov     rcx, rdi; hdc
0x1809a2e18  call    cs:__imp_SelectObject
0x1809a2e1e  mov     [rsp+148h+var_90], rax
0x1809a2e26  mov     rcx, rbx; HWND
0x1809a2e29  call    ?FIsCurrentProcess@InsertScreenshotControlUser@Art@@CA_NPEAUHWND__@@@Z; Art::InsertScreenshotControlUser::FIsCurrentProcess(HWND__ *)
0x1809a2e2e  mov     rdx, rdi; HDC
0x1809a2e31  mov     rcx, rbx; HWND
0x1809a2e34  test    al, al
0x1809a2e36  jnz     short loc_1809A2E48
0x1809a2e38  call    ?CaptureWindow@InsertScreenshotControlUser@Art@@SA_NPEAUHWND__@@PEAUHDC__@@@Z; Art::InsertScreenshotControlUser::CaptureWindow(HWND__ *,HDC__ *)
0x1809a2e3d  movzx   eax, al
0x1809a2e40  mov     r14d, 2
0x1809a2e46  jmp     short loc_1809A2E57
0x1809a2e48  mov     r14d, 2
0x1809a2e4e  mov     r8d, r14d; nFlags
0x1809a2e51  call    cs:__imp_PrintWindow
0x1809a2e57  test    eax, eax
0x1809a2e59  jnz     short loc_1809A2E71
0x1809a2e5b  xor     r9d, r9d
0x1809a2e5e  mov     r8d, 40400007h
0x1809a2e64  mov     rcx, [rsi]
0x1809a2e67  call    ??$DataSourceSetImpl@V?$TypeTraits@_N@FlexUI@@_N@FlexUI@@YA_NPEAUIDataSource@0@IH_NPEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<bool>,bool>(FlexUI::IDataSource *,uint,int,bool,void *)
0x1809a2e6c  jmp     loc_1809A3125
0x1809a2e71  lea     rbx, [r15+0F0h]
0x1809a2e78  mov     rdx, rbx
0x1809a2e7b  lea     rcx, [rsp+148h+var_C0]
0x1809a2e83  call    ?GetDPIFromUserInterface@Art@@YA?AV?$TConvertibleDPI2@M@Gfx@@AEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::GetDPIFromUserInterface(Ofc::TWeakPtr<Art::UserInterface> const &)
0x1809a2e88  mov     rcx, rax
0x1809a2e8b  mov     r12d, 60h ; '`'
0x1809a2e91  mov     edx, r12d
0x1809a2e94  call    ?ScaleForDPI@Art@@YAHAEBV?$TConvertibleDPI2@M@Gfx@@H@Z; Art::ScaleForDPI(Gfx::TConvertibleDPI2<float> const &,int)
0x1809a2e99  mov     r15d, eax
0x1809a2e9c  mov     rdx, rbx
0x1809a2e9f  lea     rcx, [rsp+148h+var_C0]
0x1809a2ea7  call    ?GetDPIFromUserInterface@Art@@YA?AV?$TConvertibleDPI2@M@Gfx@@AEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::GetDPIFromUserInterface(Ofc::TWeakPtr<Art::UserInterface> const &)
0x1809a2eac  mov     rcx, rax
0x1809a2eaf  mov     edx, r12d
0x1809a2eb2  call    ?ScaleForDPI@Art@@YAHAEBV?$TConvertibleDPI2@M@Gfx@@H@Z; Art::ScaleForDPI(Gfx::TConvertibleDPI2<float> const &,int)
0x1809a2eb7  mov     r12d, eax
0x1809a2eba  mov     [rsp+148h+wDest], r15d
0x1809a2ebf  mov     [rsp+148h+var_E4], eax
0x1809a2ec3  mov     ebx, r13d
0x1809a2ec6  mov     ecx, [rsp+148h+Rect.right]
0x1809a2ecd  sub     ecx, [rsp+148h+Rect.left]
0x1809a2ed4  movd    xmm1, ecx
0x1809a2ed8  cvtdq2pd xmm1, xmm1
0x1809a2edc  mov     ecx, [rsp+148h+Rect.bottom]
0x1809a2ee3  sub     ecx, [rsp+148h+Rect.top]
0x1809a2eea  movd    xmm0, ecx
0x1809a2eee  cvtdq2pd xmm0, xmm0
0x1809a2ef2  divsd   xmm1, xmm0
0x1809a2ef6  comisd  xmm1, cs:__real@3ff0000000000000
0x1809a2efe  jb      short loc_1809A2F20
0x1809a2f00  movd    xmm0, r15d
0x1809a2f05  cvtdq2pd xmm0, xmm0
0x1809a2f09  divsd   xmm0, xmm1
0x1809a2f0d  cvttsd2si ecx, xmm0
0x1809a2f11  mov     [rsp+148h+var_E4], ecx
0x1809a2f15  sub     eax, ecx
0x1809a2f17  cdq
0x1809a2f18  idiv    r14d
0x1809a2f1b  mov     r13d, eax
0x1809a2f1e  jmp     short loc_1809A2F40
0x1809a2f20  movd    xmm0, r12d
0x1809a2f25  cvtdq2pd xmm0, xmm0
0x1809a2f29  mulsd   xmm0, xmm1
0x1809a2f2d  cvttsd2si ecx, xmm0
0x1809a2f31  mov     [rsp+148h+wDest], ecx
0x1809a2f35  mov     eax, r15d
0x1809a2f38  sub     eax, ecx
0x1809a2f3a  cdq
0x1809a2f3b  idiv    r14d
0x1809a2f3e  mov     ebx, eax
0x1809a2f40  call    cs:__imp_GetDesktopWindow
0x1809a2f46  mov     rdx, rax; HWND
0x1809a2f49  lea     rcx, [rsp+148h+var_88]; this
0x1809a2f51  call    ??0CHDC@Ofc@@QEAA@PEAUHWND__@@PEAUHPALETTE__@@@Z; Ofc::CHDC::CHDC(HWND__ *,HPALETTE__ *)
0x1809a2f56  xor     r14d, r14d
0x1809a2f59  mov     [rsp+148h+var_D8], r14
0x1809a2f5e  mov     r9d, r12d; int
0x1809a2f61  mov     r8d, r15d; int
0x1809a2f64  mov     rdx, [rsp+148h+var_88]; HDC
0x1809a2f6c  lea     rcx, [rsp+148h+var_D8]; this
0x1809a2f71  call    ?Create@CHBitmap@Ofc@@QEAAXPEAUHDC__@@HH@Z; Ofc::CHBitmap::Create(HDC__ *,int,int)
0x1809a2f76  xorps   xmm0, xmm0
0x1809a2f79  movdqu  xmmword ptr [rsp+148h+hDC], xmm0
0x1809a2f82  mov     rax, [rsp+148h+var_D8]
0x1809a2f87  mov     [rsp+148h+var_C0], rax
0x1809a2f8f  mov     r8, rax; HBITMAP
0x1809a2f92  mov     rdx, [rsp+148h+var_88]; HDC
0x1809a2f9a  lea     rcx, [rsp+148h+hDC]; this
0x1809a2fa2  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x1809a2fa7  mov     qword ptr [rsp+148h+rc.left], r14
0x1809a2faf  mov     [rsp+148h+rc.right], r15d
0x1809a2fb7  mov     [rsp+148h+rc.bottom], r12d
0x1809a2fbf  mov     r8d, 0FF00FFh; unsigned int
0x1809a2fc5  mov     r15, [rsp+148h+hDC]
0x1809a2fcd  mov     rdx, r15; HDC
0x1809a2fd0  lea     rcx, [rsp+148h+hbr]; this
0x1809a2fd8  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x1809a2fdd  mov     r8, [rsp+148h+hbr]; hbr
0x1809a2fe5  lea     rdx, [rsp+148h+rc]; lprc
0x1809a2fed  mov     rcx, r15; hDC
0x1809a2ff0  call    cs:__imp_FillRect
0x1809a2ff6  lea     edx, [r14+4]; mode
0x1809a2ffa  mov     rcx, r15; hdc
0x1809a2ffd  call    cs:__imp_SetStretchBltMode
0x1809a3003  xor     r9d, r9d; lppt
0x1809a3006  xor     r8d, r8d; y
0x1809a3009  xor     edx, edx; x
0x1809a300b  mov     rcx, r15; hdc
0x1809a300e  call    cs:__imp_SetBrushOrgEx
0x1809a3014  mov     ecx, [rsp+148h+Rect.bottom]
0x1809a301b  sub     ecx, [rsp+148h+Rect.top]
0x1809a3022  mov     eax, [rsp+148h+Rect.right]
0x1809a3029  sub     eax, [rsp+148h+Rect.left]
0x1809a3030  mov     [rsp+148h+rop], 0CC0020h; rop
0x1809a3038  mov     [rsp+148h+hSrc], ecx; hSrc
0x1809a303c  mov     [rsp+148h+wSrc], eax; wSrc
0x1809a3040  mov     [rsp+148h+ySrc], r14d; ySrc
0x1809a3045  mov     [rsp+148h+xSrc], r14d; xSrc
0x1809a304a  mov     [rsp+148h+hdcSrc], rdi; hdcSrc
0x1809a304f  mov     eax, [rsp+148h+var_E4]
0x1809a3053  mov     [rsp+148h+hDest], eax; hDest
0x1809a3057  mov     r14d, [rsp+148h+wDest]
0x1809a305c  mov     r9d, r14d; wDest
0x1809a305f  mov     r8d, r13d; yDest
0x1809a3062  mov     edx, ebx; xDest
0x1809a3064  mov     rcx, r15; hdcDest
0x1809a3067  call    cs:__imp_StretchBlt
0x1809a306d  xor     r12b, r12b
0x1809a3070  lea     eax, [r14+rbx]
0x1809a3074  mov     dword ptr [rsp+148h+var_E0], eax
0x1809a3078  cmp     ebx, eax
0x1809a307a  jge     short loc_1809A30CA
0x1809a307c  test    r12b, r12b
0x1809a307f  jnz     loc_1809A3166
0x1809a3085  mov     r14d, r13d
0x1809a3088  mov     eax, [rsp+148h+var_E4]
0x1809a308c  add     eax, r13d
0x1809a308f  mov     [rsp+148h+wDest], eax
0x1809a3093  cmp     r14d, eax
0x1809a3096  jge     short loc_1809A30B6
0x1809a3098  mov     r8d, r14d; y
0x1809a309b  mov     edx, ebx; x
0x1809a309d  mov     rcx, r15; hdc
0x1809a30a0  call    cs:__imp_GetPixel
0x1809a30a6  test    eax, eax
0x1809a30a8  jnz     short loc_1809A30B3
0x1809a30aa  inc     r14d
0x1809a30ad  mov     eax, [rsp+148h+wDest]
0x1809a30b1  jmp     short loc_1809A3093
0x1809a30b3  mov     r12b, 1
0x1809a30b6  inc     ebx
0x1809a30b8  cmp     ebx, dword ptr [rsp+148h+var_E0]
0x1809a30bc  jl      short loc_1809A307C
0x1809a30be  xor     r13d, r13d
0x1809a30c1  test    r12b, r12b
0x1809a30c4  jnz     loc_1809A3169
0x1809a30ca  xor     r9d, r9d
0x1809a30cd  mov     r8d, 40800008h
0x1809a30d3  mov     rcx, [rsi]
0x1809a30d6  call    ??$DataSourceSetImpl@V?$TypeTraits@_N@FlexUI@@_N@FlexUI@@YA_NPEAUIDataSource@0@IH_NPEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<bool>,bool>(FlexUI::IDataSource *,uint,int,bool,void *)
0x1809a30db  lea     rcx, [rsp+148h+hbr]; this
0x1809a30e3  call    ?Delete@CHBrush@Ofc@@QEAAXXZ; Ofc::CHBrush::Delete(void)
0x1809a30e8  test    r15, r15
0x1809a30eb  jz      short loc_1809A310D
0x1809a30ed  mov     rdx, [rsp+148h+hDC+8]; h
0x1809a30f5  test    rdx, rdx
0x1809a30f8  jz      short loc_1809A3103
0x1809a30fa  mov     rcx, r15; hdc
0x1809a30fd  call    cs:__imp_SelectObject
0x1809a3103  mov     rcx, r15; hdc
0x1809a3106  call    cs:__imp_DeleteDC
0x1809a310c  nop
0x1809a310d  lea     rcx, [rsp+148h+var_D8]; this
0x1809a3112  call    ?Reset@CHBitmap@Ofc@@QEAAXXZ; Ofc::CHBitmap::Reset(void)
0x1809a3117  lea     rcx, [rsp+148h+var_88]; this
0x1809a311f  call    ??1CHDC@Ofc@@QEAA@XZ; Ofc::CHDC::~CHDC(void)
0x1809a3124  nop
0x1809a3125  lea     rcx, [rsp+148h+var_98]; this
0x1809a312d  call    ??1CGDIObjSelector@Ofc@@QEAA@XZ; Ofc::CGDIObjSelector::~CGDIObjSelector(void)
0x1809a3132  test    rdi, rdi
0x1809a3135  jz      short loc_1809A3157
0x1809a3137  mov     rdx, [rsp+148h+hdc+8]; h
0x1809a313f  test    rdx, rdx
0x1809a3142  jz      short loc_1809A314D
0x1809a3144  mov     rcx, rdi; hdc
0x1809a3147  call    cs:__imp_SelectObject
0x1809a314d  mov     rcx, rdi; hdc
0x1809a3150  call    cs:__imp_DeleteDC
0x1809a3156  nop
0x1809a3157  lea     rcx, [rsp+148h+h]; this
0x1809a315c  call    ?Reset@CHBitmap@Ofc@@QEAAXXZ; Ofc::CHBitmap::Reset(void)
0x1809a3161  jmp     loc_1809A3221
0x1809a3166  xor     r13d, r13d
0x1809a3169  mov     [rsp+148h+var_D8], r13
0x1809a316e  mov     byte ptr [rsp+148h+wSrc], r13b
0x1809a3173  mov     byte ptr [rsp+148h+ySrc], 1
0x1809a3178  mov     byte ptr [rsp+148h+xSrc], r13b
0x1809a317d  mov     byte ptr [rsp+148h+hdcSrc], r13b
0x1809a3182  mov     byte ptr [rsp+148h+hDest], r13b
0x1809a3187  mov     r9d, 0FF00FFh
0x1809a318d  mov     r8b, 3
0x1809a3190  lea     rdx, [rsp+148h+var_C8]
0x1809a3198  mov     rcx, [rsp+148h+var_C0]
0x1809a31a0  call    cs:__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z; FlexUI::FlexValue::CreateImage(HBITMAP__ *,FlexUI::FlexValueSP &,uchar,uint,bool,bool,bool,bool,bool)
0x1809a31a6  test    al, al
0x1809a31a8  jz      loc_1809A30CA
0x1809a31ae  mov     rbx, [rsp+148h+var_C8]
0x1809a31b6  mov     rsi, [rsi]
0x1809a31b9  test    rsi, rsi
0x1809a31bc  jnz     short loc_1809A31CE
0x1809a31be  mov     ecx, 7A0740h
0x1809a31c3  call    cs:__imp_MsoShipAssertTagProc
0x1809a31c9  jmp     loc_1809A30DB
0x1809a31ce  test    rbx, rbx
0x1809a31d1  jz      loc_1809A30DB
0x1809a31d7  mov     rcx, rbx; this
0x1809a31da  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x1809a31df  test    rbx, rbx
0x1809a31e2  jz      loc_1809A30DB
0x1809a31e8  mov     rax, [rsi]
0x1809a31eb  mov     r9, rbx
0x1809a31ee  xor     edx, edx
0x1809a31f0  lea     r8d, [rdx+3]
0x1809a31f4  mov     rcx, rsi
0x1809a31f7  mov     rax, [rax+30h]
0x1809a31fb  call    cs:__guard_dispatch_icall_fptr
0x1809a3201  mov     rcx, rbx
0x1809a3204  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809a320a  jmp     loc_1809A30DB
0x1809a320f  xor     r9d, r9d
0x1809a3212  mov     r8d, 40400007h
  ... truncated ...
```
