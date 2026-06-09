# Art::InsertScreenshotControlUser::UpdateItem(GalleryItemSP &)

- ea: `0x1809acf50`
- end: `0x1809ad4d4`
- name: `?UpdateItem@InsertScreenshotControlUser@Art@@UEAAXAEAVGalleryItemSP@@@Z`
- size: `1412`
- prototype: `void __fastcall(Art::InsertScreenshotControlUser *__hidden this, struct GalleryItemSP *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18003a234`
- `0x180121260`
- `0x1801d8b80`
- `0x1802534b0`
- `0x180279030`
- `0x180279050`
- `0x18029ab98`
- `0x18029bcec`
- `0x180434fb8`
- `0x180435010`
- `0x1805b8f20`
- `0x1805e7a54`
- `0x18065c0ac`
- `0x180667e80`
- `0x180690680`
- `0x180693978`
- `0x1809acf50`

## import_xrefs

- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x1809ad410`
- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x1809ad410`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809acfcc`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809ad474`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809ad49e`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809acfcc`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809ad474`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x1809ad49e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809acf92`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809ad433`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809acf92`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1809ad433`
- `GDI32!StretchBlt` at `0x1809ad2d7`
- `GDI32!StretchBlt` at `0x1809ad2d7`
- `GDI32!SetBrushOrgEx` at `0x1809ad27e`
- `GDI32!SetBrushOrgEx` at `0x1809ad27e`
- `GDI32!SetStretchBltMode` at `0x1809ad26d`
- `GDI32!SetStretchBltMode` at `0x1809ad26d`
- `GDI32!GetPixel` at `0x1809ad310`
- `GDI32!GetPixel` at `0x1809ad310`
- `GDI32!SelectObject` at `0x1809ad088`
- `GDI32!SelectObject` at `0x1809ad36d`
- `GDI32!SelectObject` at `0x1809ad3b7`
- `GDI32!SelectObject` at `0x1809ad088`
- `GDI32!SelectObject` at `0x1809ad36d`
- `GDI32!SelectObject` at `0x1809ad3b7`
- `GDI32!DeleteDC` at `0x1809ad376`
- `GDI32!DeleteDC` at `0x1809ad3c0`
- `GDI32!DeleteDC` at `0x1809ad376`
- `GDI32!DeleteDC` at `0x1809ad3c0`
- `USER32!PrintWindow` at `0x1809ad0c1`
- `USER32!PrintWindow` at `0x1809ad0c1`
- `USER32!FillRect` at `0x1809ad260`
- `USER32!FillRect` at `0x1809ad260`
- `USER32!GetWindowDC` at `0x1809acfe2`
- `USER32!GetWindowDC` at `0x1809acfe2`
- `USER32!GetWindowRect` at `0x1809ad00a`
- `USER32!GetWindowRect` at `0x1809ad00a`
- `USER32!GetDesktopWindow` at `0x1809ad1b0`
- `USER32!GetDesktopWindow` at `0x1809ad1b0`

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
        LODWORD(v31) = v18 + wDest;
        if ( v18 >= v18 + wDest )
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
        Ofc::CHBitmap::~CHBitmap((Ofc::CHBitmap *)&v32);
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
      Ofc::CHBitmap::~CHBitmap((Ofc::CHBitmap *)&h);
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
0x1809acf50  mov     [rsp+arg_10], rbx
0x1809acf55  mov     [rsp+arg_18], rsi
0x1809acf5a  push    rdi
0x1809acf5b  push    r12
0x1809acf5d  push    r13
0x1809acf5f  push    r14
0x1809acf61  push    r15
0x1809acf63  sub     rsp, 120h
0x1809acf6a  mov     rax, cs:__security_cookie
0x1809acf71  xor     rax, rsp
0x1809acf74  mov     [rsp+148h+var_38], rax
0x1809acf7c  mov     rsi, rdx
0x1809acf7f  mov     r15, rcx
0x1809acf82  mov     rcx, [rdx]
0x1809acf85  xor     r13d, r13d
0x1809acf88  test    rcx, rcx
0x1809acf8b  jnz     short loc_1809ACF9D
0x1809acf8d  mov     ecx, 7A0720h
0x1809acf92  call    cs:__imp_MsoShipAssertTagProc
0x1809acf98  mov     ebx, r13d
0x1809acf9b  jmp     short loc_1809ACFD7
0x1809acf9d  mov     [rsp+148h+var_E0], r13
0x1809acfa2  mov     rax, [rcx]
0x1809acfa5  lea     r8, [rsp+148h+var_E0]
0x1809acfaa  mov     edx, 7Eh ; '~'
0x1809acfaf  mov     rax, [rax+28h]
0x1809acfb3  call    cs:__guard_dispatch_icall_fptr
0x1809acfb9  mov     rcx, [rsp+148h+var_E0]
0x1809acfbe  test    rcx, rcx
0x1809acfc1  jnz     short loc_1809ACFC8
0x1809acfc3  mov     rbx, r13
0x1809acfc6  jmp     short loc_1809ACFD2
0x1809acfc8  mov     rbx, [rcx+8]
0x1809acfcc  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809acfd2  mov     [rsp+148h+var_E0], r13
0x1809acfd7  mov     [rsp+148h+var_C8], r13
0x1809acfdf  mov     rcx, rbx; hWnd
0x1809acfe2  call    cs:__imp_GetWindowDC
0x1809acfe8  mov     rdi, rax
0x1809acfeb  test    rax, rax
0x1809acfee  jz      loc_1809AD47F
0x1809acff4  xorps   xmm0, xmm0
0x1809acff7  movups  xmmword ptr [rsp+148h+Rect.left], xmm0
0x1809acfff  lea     rdx, [rsp+148h+Rect]; lpRect
0x1809ad007  mov     rcx, rbx; hWnd
0x1809ad00a  call    cs:__imp_GetWindowRect
0x1809ad010  mov     r8d, [rsp+148h+Rect.right]
0x1809ad018  sub     r8d, [rsp+148h+Rect.left]; int
0x1809ad020  jz      loc_1809AD491
0x1809ad026  mov     r9d, [rsp+148h+Rect.bottom]
0x1809ad02e  sub     r9d, [rsp+148h+Rect.top]; int
0x1809ad036  jz      loc_1809AD491
0x1809ad03c  mov     [rsp+148h+h], r13
0x1809ad041  mov     rdx, rdi; HDC
0x1809ad044  lea     rcx, [rsp+148h+h]; this
0x1809ad049  call    ?Create@CHBitmap@Ofc@@QEAAXPEAUHDC__@@HH@Z; Ofc::CHBitmap::Create(HDC__ *,int,int)
0x1809ad04e  xorps   xmm0, xmm0
0x1809ad051  movdqu  xmmword ptr [rsp+148h+hdc], xmm0
0x1809ad05a  mov     r8, [rsp+148h+h]; HBITMAP
0x1809ad05f  mov     rdx, rdi; HDC
0x1809ad062  lea     rcx, [rsp+148h+hdc]; this
0x1809ad06a  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x1809ad06f  nop
0x1809ad070  mov     rdi, [rsp+148h+hdc]
0x1809ad078  mov     [rsp+148h+var_98], rdi
0x1809ad080  mov     rdx, [rsp+148h+h]; h
0x1809ad085  mov     rcx, rdi; hdc
0x1809ad088  call    cs:__imp_SelectObject
0x1809ad08e  mov     [rsp+148h+var_90], rax
0x1809ad096  mov     rcx, rbx; HWND
0x1809ad099  call    ?FIsCurrentProcess@InsertScreenshotControlUser@Art@@CA_NPEAUHWND__@@@Z; Art::InsertScreenshotControlUser::FIsCurrentProcess(HWND__ *)
0x1809ad09e  mov     rdx, rdi; HDC
0x1809ad0a1  mov     rcx, rbx; HWND
0x1809ad0a4  test    al, al
0x1809ad0a6  jnz     short loc_1809AD0B8
0x1809ad0a8  call    ?CaptureWindow@InsertScreenshotControlUser@Art@@SA_NPEAUHWND__@@PEAUHDC__@@@Z; Art::InsertScreenshotControlUser::CaptureWindow(HWND__ *,HDC__ *)
0x1809ad0ad  movzx   eax, al
0x1809ad0b0  mov     r14d, 2
0x1809ad0b6  jmp     short loc_1809AD0C7
0x1809ad0b8  mov     r14d, 2
0x1809ad0be  mov     r8d, r14d; nFlags
0x1809ad0c1  call    cs:__imp_PrintWindow
0x1809ad0c7  test    eax, eax
0x1809ad0c9  jnz     short loc_1809AD0E1
0x1809ad0cb  xor     r9d, r9d
0x1809ad0ce  mov     r8d, 40400007h
0x1809ad0d4  mov     rcx, [rsi]
0x1809ad0d7  call    ??$DataSourceSetImpl@V?$TypeTraits@_N@FlexUI@@_N@FlexUI@@YA_NPEAUIDataSource@0@IH_NPEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<bool>,bool>(FlexUI::IDataSource *,uint,int,bool,void *)
0x1809ad0dc  jmp     loc_1809AD395
0x1809ad0e1  lea     rbx, [r15+0F0h]
0x1809ad0e8  mov     rdx, rbx
0x1809ad0eb  lea     rcx, [rsp+148h+var_C0]
0x1809ad0f3  call    ?GetDPIFromUserInterface@Art@@YA?AV?$TConvertibleDPI2@M@Gfx@@AEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::GetDPIFromUserInterface(Ofc::TWeakPtr<Art::UserInterface> const &)
0x1809ad0f8  mov     rcx, rax
0x1809ad0fb  mov     r12d, 60h ; '`'
0x1809ad101  mov     edx, r12d
0x1809ad104  call    ?ScaleForDPI@Art@@YAHAEBV?$TConvertibleDPI2@M@Gfx@@H@Z; Art::ScaleForDPI(Gfx::TConvertibleDPI2<float> const &,int)
0x1809ad109  mov     r15d, eax
0x1809ad10c  mov     rdx, rbx
0x1809ad10f  lea     rcx, [rsp+148h+var_C0]
0x1809ad117  call    ?GetDPIFromUserInterface@Art@@YA?AV?$TConvertibleDPI2@M@Gfx@@AEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::GetDPIFromUserInterface(Ofc::TWeakPtr<Art::UserInterface> const &)
0x1809ad11c  mov     rcx, rax
0x1809ad11f  mov     edx, r12d
0x1809ad122  call    ?ScaleForDPI@Art@@YAHAEBV?$TConvertibleDPI2@M@Gfx@@H@Z; Art::ScaleForDPI(Gfx::TConvertibleDPI2<float> const &,int)
0x1809ad127  mov     r12d, eax
0x1809ad12a  mov     [rsp+148h+wDest], r15d
0x1809ad12f  mov     [rsp+148h+var_E4], eax
0x1809ad133  mov     ebx, r13d
0x1809ad136  mov     ecx, [rsp+148h+Rect.right]
0x1809ad13d  sub     ecx, [rsp+148h+Rect.left]
0x1809ad144  movd    xmm1, ecx
0x1809ad148  cvtdq2pd xmm1, xmm1
0x1809ad14c  mov     ecx, [rsp+148h+Rect.bottom]
0x1809ad153  sub     ecx, [rsp+148h+Rect.top]
0x1809ad15a  movd    xmm0, ecx
0x1809ad15e  cvtdq2pd xmm0, xmm0
0x1809ad162  divsd   xmm1, xmm0
0x1809ad166  comisd  xmm1, cs:__real@3ff0000000000000
0x1809ad16e  jb      short loc_1809AD190
0x1809ad170  movd    xmm0, r15d
0x1809ad175  cvtdq2pd xmm0, xmm0
0x1809ad179  divsd   xmm0, xmm1
0x1809ad17d  cvttsd2si ecx, xmm0
0x1809ad181  mov     [rsp+148h+var_E4], ecx
0x1809ad185  sub     eax, ecx
0x1809ad187  cdq
0x1809ad188  idiv    r14d
0x1809ad18b  mov     r13d, eax
0x1809ad18e  jmp     short loc_1809AD1B0
0x1809ad190  movd    xmm0, r12d
0x1809ad195  cvtdq2pd xmm0, xmm0
0x1809ad199  mulsd   xmm0, xmm1
0x1809ad19d  cvttsd2si ecx, xmm0
0x1809ad1a1  mov     [rsp+148h+wDest], ecx
0x1809ad1a5  mov     eax, r15d
0x1809ad1a8  sub     eax, ecx
0x1809ad1aa  cdq
0x1809ad1ab  idiv    r14d
0x1809ad1ae  mov     ebx, eax
0x1809ad1b0  call    cs:__imp_GetDesktopWindow
0x1809ad1b6  mov     rdx, rax; HWND
0x1809ad1b9  lea     rcx, [rsp+148h+var_88]; this
0x1809ad1c1  call    ??0CHDC@Ofc@@QEAA@PEAUHWND__@@PEAUHPALETTE__@@@Z; Ofc::CHDC::CHDC(HWND__ *,HPALETTE__ *)
0x1809ad1c6  xor     r14d, r14d
0x1809ad1c9  mov     [rsp+148h+var_D8], r14
0x1809ad1ce  mov     r9d, r12d; int
0x1809ad1d1  mov     r8d, r15d; int
0x1809ad1d4  mov     rdx, [rsp+148h+var_88]; HDC
0x1809ad1dc  lea     rcx, [rsp+148h+var_D8]; this
0x1809ad1e1  call    ?Create@CHBitmap@Ofc@@QEAAXPEAUHDC__@@HH@Z; Ofc::CHBitmap::Create(HDC__ *,int,int)
0x1809ad1e6  xorps   xmm0, xmm0
0x1809ad1e9  movdqu  xmmword ptr [rsp+148h+hDC], xmm0
0x1809ad1f2  mov     rax, [rsp+148h+var_D8]
0x1809ad1f7  mov     [rsp+148h+var_C0], rax
0x1809ad1ff  mov     r8, rax; HBITMAP
0x1809ad202  mov     rdx, [rsp+148h+var_88]; HDC
0x1809ad20a  lea     rcx, [rsp+148h+hDC]; this
0x1809ad212  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x1809ad217  mov     qword ptr [rsp+148h+rc.left], r14
0x1809ad21f  mov     [rsp+148h+rc.right], r15d
0x1809ad227  mov     [rsp+148h+rc.bottom], r12d
0x1809ad22f  mov     r8d, 0FF00FFh; unsigned int
0x1809ad235  mov     r15, [rsp+148h+hDC]
0x1809ad23d  mov     rdx, r15; HDC
0x1809ad240  lea     rcx, [rsp+148h+hbr]; this
0x1809ad248  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x1809ad24d  mov     r8, [rsp+148h+hbr]; hbr
0x1809ad255  lea     rdx, [rsp+148h+rc]; lprc
0x1809ad25d  mov     rcx, r15; hDC
0x1809ad260  call    cs:__imp_FillRect
0x1809ad266  lea     edx, [r14+4]; mode
0x1809ad26a  mov     rcx, r15; hdc
0x1809ad26d  call    cs:__imp_SetStretchBltMode
0x1809ad273  xor     r9d, r9d; lppt
0x1809ad276  xor     r8d, r8d; y
0x1809ad279  xor     edx, edx; x
0x1809ad27b  mov     rcx, r15; hdc
0x1809ad27e  call    cs:__imp_SetBrushOrgEx
0x1809ad284  mov     ecx, [rsp+148h+Rect.bottom]
0x1809ad28b  sub     ecx, [rsp+148h+Rect.top]
0x1809ad292  mov     eax, [rsp+148h+Rect.right]
0x1809ad299  sub     eax, [rsp+148h+Rect.left]
0x1809ad2a0  mov     [rsp+148h+rop], 0CC0020h; rop
0x1809ad2a8  mov     [rsp+148h+hSrc], ecx; hSrc
0x1809ad2ac  mov     [rsp+148h+wSrc], eax; wSrc
0x1809ad2b0  mov     [rsp+148h+ySrc], r14d; ySrc
0x1809ad2b5  mov     [rsp+148h+xSrc], r14d; xSrc
0x1809ad2ba  mov     [rsp+148h+hdcSrc], rdi; hdcSrc
0x1809ad2bf  mov     eax, [rsp+148h+var_E4]
0x1809ad2c3  mov     [rsp+148h+hDest], eax; hDest
0x1809ad2c7  mov     r14d, [rsp+148h+wDest]
0x1809ad2cc  mov     r9d, r14d; wDest
0x1809ad2cf  mov     r8d, r13d; yDest
0x1809ad2d2  mov     edx, ebx; xDest
0x1809ad2d4  mov     rcx, r15; hdcDest
0x1809ad2d7  call    cs:__imp_StretchBlt
0x1809ad2dd  xor     r12b, r12b
0x1809ad2e0  lea     eax, [rbx+r14]
0x1809ad2e4  mov     dword ptr [rsp+148h+var_E0], eax
0x1809ad2e8  cmp     ebx, eax
0x1809ad2ea  jge     short loc_1809AD33A
0x1809ad2ec  test    r12b, r12b
0x1809ad2ef  jnz     loc_1809AD3D6
0x1809ad2f5  mov     r14d, r13d
0x1809ad2f8  mov     eax, [rsp+148h+var_E4]
0x1809ad2fc  add     eax, r13d
0x1809ad2ff  mov     [rsp+148h+wDest], eax
0x1809ad303  cmp     r14d, eax
0x1809ad306  jge     short loc_1809AD326
0x1809ad308  mov     r8d, r14d; y
0x1809ad30b  mov     edx, ebx; x
0x1809ad30d  mov     rcx, r15; hdc
0x1809ad310  call    cs:__imp_GetPixel
0x1809ad316  test    eax, eax
0x1809ad318  jnz     short loc_1809AD323
0x1809ad31a  inc     r14d
0x1809ad31d  mov     eax, [rsp+148h+wDest]
0x1809ad321  jmp     short loc_1809AD303
0x1809ad323  mov     r12b, 1
0x1809ad326  inc     ebx
0x1809ad328  cmp     ebx, dword ptr [rsp+148h+var_E0]
0x1809ad32c  jl      short loc_1809AD2EC
0x1809ad32e  xor     r13d, r13d
0x1809ad331  test    r12b, r12b
0x1809ad334  jnz     loc_1809AD3D9
0x1809ad33a  xor     r9d, r9d
0x1809ad33d  mov     r8d, 40800008h
0x1809ad343  mov     rcx, [rsi]
0x1809ad346  call    ??$DataSourceSetImpl@V?$TypeTraits@_N@FlexUI@@_N@FlexUI@@YA_NPEAUIDataSource@0@IH_NPEAX@Z; FlexUI::DataSourceSetImpl<FlexUI::TypeTraits<bool>,bool>(FlexUI::IDataSource *,uint,int,bool,void *)
0x1809ad34b  lea     rcx, [rsp+148h+hbr]; this
0x1809ad353  call    ?Delete@CHBrush@Ofc@@QEAAXXZ; Ofc::CHBrush::Delete(void)
0x1809ad358  test    r15, r15
0x1809ad35b  jz      short loc_1809AD37D
0x1809ad35d  mov     rdx, [rsp+148h+hDC+8]; h
0x1809ad365  test    rdx, rdx
0x1809ad368  jz      short loc_1809AD373
0x1809ad36a  mov     rcx, r15; hdc
0x1809ad36d  call    cs:__imp_SelectObject
0x1809ad373  mov     rcx, r15; hdc
0x1809ad376  call    cs:__imp_DeleteDC
0x1809ad37c  nop
0x1809ad37d  lea     rcx, [rsp+148h+var_D8]; this
0x1809ad382  call    ??1CHBitmap@Ofc@@QEAA@XZ; Ofc::CHBitmap::~CHBitmap(void)
0x1809ad387  lea     rcx, [rsp+148h+var_88]; this
0x1809ad38f  call    ??1CHDC@Ofc@@QEAA@XZ; Ofc::CHDC::~CHDC(void)
0x1809ad394  nop
0x1809ad395  lea     rcx, [rsp+148h+var_98]; this
0x1809ad39d  call    ??1CGDIObjSelector@Ofc@@QEAA@XZ; Ofc::CGDIObjSelector::~CGDIObjSelector(void)
0x1809ad3a2  test    rdi, rdi
0x1809ad3a5  jz      short loc_1809AD3C7
0x1809ad3a7  mov     rdx, [rsp+148h+hdc+8]; h
0x1809ad3af  test    rdx, rdx
0x1809ad3b2  jz      short loc_1809AD3BD
0x1809ad3b4  mov     rcx, rdi; hdc
0x1809ad3b7  call    cs:__imp_SelectObject
0x1809ad3bd  mov     rcx, rdi; hdc
0x1809ad3c0  call    cs:__imp_DeleteDC
0x1809ad3c6  nop
0x1809ad3c7  lea     rcx, [rsp+148h+h]; this
0x1809ad3cc  call    ??1CHBitmap@Ofc@@QEAA@XZ; Ofc::CHBitmap::~CHBitmap(void)
0x1809ad3d1  jmp     loc_1809AD491
0x1809ad3d6  xor     r13d, r13d
0x1809ad3d9  mov     [rsp+148h+var_D8], r13
0x1809ad3de  mov     byte ptr [rsp+148h+wSrc], r13b
0x1809ad3e3  mov     byte ptr [rsp+148h+ySrc], 1
0x1809ad3e8  mov     byte ptr [rsp+148h+xSrc], r13b
0x1809ad3ed  mov     byte ptr [rsp+148h+hdcSrc], r13b
0x1809ad3f2  mov     byte ptr [rsp+148h+hDest], r13b
0x1809ad3f7  mov     r9d, 0FF00FFh
0x1809ad3fd  mov     r8b, 3
0x1809ad400  lea     rdx, [rsp+148h+var_C8]
0x1809ad408  mov     rcx, [rsp+148h+var_C0]
0x1809ad410  call    cs:__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z; FlexUI::FlexValue::CreateImage(HBITMAP__ *,FlexUI::FlexValueSP &,uchar,uint,bool,bool,bool,bool,bool)
0x1809ad416  test    al, al
0x1809ad418  jz      loc_1809AD33A
0x1809ad41e  mov     rbx, [rsp+148h+var_C8]
0x1809ad426  mov     rsi, [rsi]
0x1809ad429  test    rsi, rsi
0x1809ad42c  jnz     short loc_1809AD43E
0x1809ad42e  mov     ecx, 7A0740h
0x1809ad433  call    cs:__imp_MsoShipAssertTagProc
0x1809ad439  jmp     loc_1809AD34B
0x1809ad43e  test    rbx, rbx
0x1809ad441  jz      loc_1809AD34B
0x1809ad447  mov     rcx, rbx; this
0x1809ad44a  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x1809ad44f  test    rbx, rbx
0x1809ad452  jz      loc_1809AD34B
0x1809ad458  mov     rax, [rsi]
0x1809ad45b  mov     r9, rbx
0x1809ad45e  xor     edx, edx
0x1809ad460  lea     r8d, [rdx+3]
0x1809ad464  mov     rcx, rsi
0x1809ad467  mov     rax, [rax+30h]
0x1809ad46b  call    cs:__guard_dispatch_icall_fptr
0x1809ad471  mov     rcx, rbx
0x1809ad474  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x1809ad47a  jmp     loc_1809AD34B
0x1809ad47f  xor     r9d, r9d
0x1809ad482  mov     r8d, 40400007h
  ... truncated ...
```
