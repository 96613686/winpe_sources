# Art::FontSchemePicker::CreateFlexAnchorImageFromFontScheme(Art::FontScheme const &,ulong,FlexUI::FlexValueSP &)

- ea: `0x18042c178`
- end: `0x18042c47c`
- name: `?CreateFlexAnchorImageFromFontScheme@FontSchemePicker@Art@@IEAAXAEBVFontScheme@2@KAEAVFlexValueSP@FlexUI@@@Z`
- size: `772`
- prototype: `void(Art::FontSchemePicker *__hidden this, const struct Art::FontScheme *, unsigned int, struct FlexUI::FlexValueSP *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1805af0e0`

## callees

- `0x180121260`
- `0x180128840`
- `0x180141230`
- `0x180278e70`
- `0x180279050`
- `0x1802a7444`
- `0x18042c178`
- `0x18042c47c`
- `0x18042c560`
- `0x18042cc4c`
- `0x180434ae8`
- `0x180434fb8`
- `0x180435010`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`
- `0x180a2473c`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!round` at `0x18042c271`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18042c2d2`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18042c271`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18042c2d2`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x18042c201`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x18042c201`
- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x18042c3df`
- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x18042c3df`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x18042c27b`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x18042c2dc`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x18042c27b`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x18042c2dc`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x18042c31c`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x18042c31c`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x18042c3f0`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x18042c3f0`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x18042c250`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x18042c2b1`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x18042c250`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x18042c2b1`
- `GDI32!SelectObject` at `0x18042c404`
- `GDI32!SelectObject` at `0x18042c42c`
- `GDI32!SelectObject` at `0x18042c404`
- `GDI32!SelectObject` at `0x18042c42c`
- `GDI32!DeleteObject` at `0x18042c414`
- `GDI32!DeleteObject` at `0x18042c414`
- `GDI32!DeleteDC` at `0x18042c435`
- `GDI32!DeleteDC` at `0x18042c435`
- `USER32!FillRect` at `0x18042c372`
- `USER32!FillRect` at `0x18042c372`
- `USER32!GetDC` at `0x18042c2fc`
- `USER32!GetDC` at `0x18042c2fc`
- `USER32!ReleaseDC` at `0x18042c446`
- `USER32!ReleaseDC` at `0x18042c446`

## pseudocode

```c
void __fastcall Art::FontSchemePicker::CreateFlexAnchorImageFromFontScheme(
        Art::FontSchemePicker *this,
        const struct Art::FontScheme *a2,
        unsigned int a3,
        struct FlexUI::FlexValueSP *a4)
{
  double v4; // xmm0_8
  struct Ofc::CProxyPtrImpl *v8; // rcx
  void *Checked; // rax
  __int64 v10; // rax
  struct GalleryDSSP *GalleryDataSource; // rax
  __int64 v12; // rdx
  int v13; // edi
  void *v14; // rax
  int v15; // ebx
  Art *v16; // rcx
  int v17; // edx
  bool v18; // r8
  LONG v19; // eax
  int v20; // edx
  LONG v21; // esi
  void *v22; // rax
  int v23; // ebx
  Art *v24; // rcx
  int v25; // edx
  bool v26; // r8
  LONG v27; // eax
  Art *v28; // rcx
  double v29; // xmm0_8
  int v30; // edx
  LONG v31; // ebx
  unsigned int TransparentColor; // r15d
  HDC DC; // rdi
  HBITMAP CompatibleBitmap; // rsi
  HDC v35; // rbx
  bool v36; // r8
  HDC v37; // rdx
  int v38; // r8d
  const struct tagRECT *v39; // [rsp+30h] [rbp-91h]
  Ofc::CProxyPtrImpl *v41; // [rsp+60h] [rbp-61h] BYREF
  HDC hDC[2]; // [rsp+68h] [rbp-59h] BYREF
  HBRUSH hbr[2]; // [rsp+78h] [rbp-49h] BYREF
  HGDIOBJ h; // [rsp+88h] [rbp-39h]
  HDC v45; // [rsp+90h] [rbp-31h]
  __int128 v46; // [rsp+98h] [rbp-29h]
  RECT rc; // [rsp+A8h] [rbp-19h] BYREF
  struct Ofc::CProxyPtrImpl *v48[2]; // [rsp+B8h] [rbp-9h] BYREF

  v8 = (struct Ofc::CProxyPtrImpl *)*((_QWORD *)this + 30);
  if ( !*((_QWORD *)v8 + 2) )
    v8 = (struct Ofc::CProxyPtrImpl *)*((_QWORD *)this + 31);
  v41 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v8);
  Checked = Ofc::CProxyPtrImpl::GetChecked(v41);
  v10 = (*(__int64 (__fastcall **)(void *, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)Checked + 96LL))(Checked, v48);
  Art::GetDPIFromUserInterface(hDC, v10);
  Ofc::CProxyPtrImpl::DtorWeakRelease(v48);
  GalleryDataSource = CMsoGalleryUserDefault::GetGalleryDataSource(this);
  v13 = (unsigned __int8)FlexUI::DataSourceGetImpl<FlexUI::TypeTraits<bool>>(
                           *(_QWORD *)GalleryDataSource,
                           v12,
                           1119879229)
      + 1;
  v14 = Ofc::CProxyPtrImpl::GetChecked(v41);
  v15 = v13 * (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v14 + 112LL))(v14);
  if ( Art::FDynamicDpiEnabled(v16) )
  {
    Art::GetScaleFactor(hDC, 0);
    v4 = round((float)((float)v15 * *(float *)&v4));
    v19 = NetUI::ScaleProportionalToSystemFontPx((NetUI *)(unsigned int)(int)v4, v20);
  }
  else
  {
    LOBYTE(v17) = 1;
    v19 = NetUI::ScalePixelsForSystemSettings((NetUI *)(unsigned int)v15, v17, v18);
  }
  v21 = v19;
  v22 = Ofc::CProxyPtrImpl::GetChecked(v41);
  v23 = v13 * (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v22 + 112LL))(v22);
  if ( Art::FDynamicDpiEnabled(v24) )
  {
    Art::GetScaleFactor(hDC, 0);
    v29 = round((float)((float)v23 * *(float *)&v4));
    v27 = NetUI::ScaleProportionalToSystemFontPx((NetUI *)(unsigned int)(int)v29, v30);
  }
  else
  {
    LOBYTE(v25) = 1;
    v27 = NetUI::ScalePixelsForSystemSettings((NetUI *)(unsigned int)v23, v25, v26);
  }
  v31 = v27;
  *(_QWORD *)&rc.left = 0;
  rc.right = v21;
  rc.bottom = v27;
  TransparentColor = Art::GetTransparentColor(v28);
  DC = GetDC(0);
  v45 = DC;
  v46 = 0;
  CompatibleBitmap = MsoHbmpCreateCompatibleBitmap(DC, v21, v31, 0);
  v48[0] = (struct Ofc::CProxyPtrImpl *)CompatibleBitmap;
  if ( !CompatibleBitmap )
    Ofc::CLastErrorException::ThrowTag(0x13906CCu);
  *(_OWORD *)hDC = 0;
  Ofc::CCompatibleHDC::Create((Ofc::CCompatibleHDC *)hDC, DC, CompatibleBitmap);
  v35 = hDC[0];
  Ofc::CHBrush::CHBrush((Ofc::CHBrush *)hbr, hDC[0], TransparentColor);
  FillRect(v35, &rc, hbr[0]);
  Art::FontSchemePicker::DrawFontSchemeIconBackground(v35, &rc, v36);
  Art::FontSchemePicker::DrawFontSchemeAnchorIcon(v35, &rc, a2, a3);
  *(RECT *)v48 = rc;
  Ofc::FrameRect(v35, v37, v38, 8481889, (unsigned int)v48, v39);
  FlexUI::FlexValue::CreateImage(CompatibleBitmap, a4, 3u, TransparentColor, 0, 0, 0, 1, 0);
  if ( *(_QWORD *)a4 )
    FlexUI::FlexValue::SetGraphicScaleForDPI(*(FlexUI::FlexValue **)a4, 0);
  if ( h )
    SelectObject((HDC)hbr[1], h);
  if ( hbr[0] )
    DeleteObject(hbr[0]);
  if ( v35 )
  {
    if ( hDC[1] )
      SelectObject(v35, hDC[1]);
    DeleteDC(v35);
  }
  if ( DC )
    ReleaseDC(0, DC);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v41);
}

```

## disassembly

```asm
0x18042c178  mov     rax, rsp
0x18042c17b  push    rbp
0x18042c17c  push    rbx
0x18042c17d  push    rsi
0x18042c17e  push    rdi
0x18042c17f  push    r12
0x18042c181  push    r13
0x18042c183  push    r15
0x18042c185  lea     rbp, [rax-5Fh]
0x18042c189  sub     rsp, 0E0h
0x18042c190  movaps  xmmword ptr [rax-48h], xmm7
0x18042c194  mov     rax, cs:__security_cookie
0x18042c19b  xor     rax, rsp
0x18042c19e  mov     [rbp+57h+var_50], rax
0x18042c1a2  mov     r12, r9
0x18042c1a5  mov     [rbp+57h+var_C0], r8d
0x18042c1a9  mov     r13, rdx
0x18042c1ac  mov     rbx, rcx
0x18042c1af  mov     rcx, [rcx+0F0h]
0x18042c1b6  cmp     qword ptr [rcx+10h], 0
0x18042c1bb  jnz     short loc_18042C1C4
0x18042c1bd  mov     rcx, [rbx+0F8h]; struct Ofc::CProxyPtrImpl *
0x18042c1c4  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18042c1c9  mov     [rbp+57h+var_B8], rax
0x18042c1cd  mov     rcx, rax; this
0x18042c1d0  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18042c1d5  mov     rcx, rax
0x18042c1d8  mov     rdx, [rax]
0x18042c1db  mov     rax, [rdx+60h]
0x18042c1df  lea     rdx, [rbp+57h+var_60]
0x18042c1e3  call    cs:__guard_dispatch_icall_fptr
0x18042c1e9  mov     rdx, rax
0x18042c1ec  lea     rcx, [rbp+57h+hDC]
0x18042c1f0  call    ?GetDPIFromUserInterface@Art@@YA?AV?$TConvertibleDPI2@M@Gfx@@AEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::GetDPIFromUserInterface(Ofc::TWeakPtr<Art::UserInterface> const &)
0x18042c1f5  lea     rcx, [rbp+57h+var_60]; struct Ofc::CProxyPtrImpl **
0x18042c1f9  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x18042c1fe  mov     rcx, rbx
0x18042c201  call    cs:__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ; CMsoGalleryUserDefault::GetGalleryDataSource(void)
0x18042c207  mov     r8d, 42C0003Dh
0x18042c20d  mov     rcx, [rax]
0x18042c210  call    ??$DataSourceGetImpl@V?$TypeTraits@_N@FlexUI@@@FlexUI@@YA_NPEAUIDataSource@0@IH@Z; FlexUI::DataSourceGetImpl<FlexUI::TypeTraits<bool>>(FlexUI::IDataSource *,uint,int)
0x18042c215  movzx   edi, al
0x18042c218  inc     edi
0x18042c21a  mov     rcx, [rbp+57h+var_B8]; this
0x18042c21e  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18042c223  mov     rdx, rax
0x18042c226  mov     rcx, [rax]
0x18042c229  mov     rax, [rcx+70h]
0x18042c22d  mov     rcx, rdx
0x18042c230  call    cs:__guard_dispatch_icall_fptr
0x18042c236  mov     ebx, eax
0x18042c238  imul    ebx, edi
0x18042c23b  call    ?FDynamicDpiEnabled@Art@@YA_NXZ; Art::FDynamicDpiEnabled(void)
0x18042c240  movsd   xmm7, cs:__real@c1e0000000000000
0x18042c248  test    al, al
0x18042c24a  jnz     short loc_18042C258
0x18042c24c  mov     dl, 1
0x18042c24e  mov     ecx, ebx
0x18042c250  call    cs:__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z; NetUI::ScalePixelsForSystemSettings(int,bool)
0x18042c256  jmp     short loc_18042C281
0x18042c258  xor     edx, edx
0x18042c25a  lea     rcx, [rbp+57h+hDC]
0x18042c25e  call    ?GetScaleFactor@Art@@YAMAEBV?$TConvertibleDPI2@M@Gfx@@_N@Z; Art::GetScaleFactor(Gfx::TConvertibleDPI2<float> const &,bool)
0x18042c263  movd    xmm1, ebx
0x18042c267  cvtdq2ps xmm1, xmm1
0x18042c26a  mulss   xmm1, xmm0
0x18042c26e  cvtps2pd xmm0, xmm1; X
0x18042c271  call    cs:__imp_round
0x18042c277  cvttsd2si ecx, xmm0
0x18042c27b  call    cs:__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z; NetUI::ScaleProportionalToSystemFontPx(int)
0x18042c281  mov     esi, eax
0x18042c283  mov     rcx, [rbp+57h+var_B8]; this
0x18042c287  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18042c28c  mov     rdx, rax
0x18042c28f  mov     rcx, [rax]
0x18042c292  mov     rax, [rcx+70h]
0x18042c296  mov     rcx, rdx
0x18042c299  call    cs:__guard_dispatch_icall_fptr
0x18042c29f  mov     ebx, eax
0x18042c2a1  imul    ebx, edi
0x18042c2a4  call    ?FDynamicDpiEnabled@Art@@YA_NXZ; Art::FDynamicDpiEnabled(void)
0x18042c2a9  test    al, al
0x18042c2ab  jnz     short loc_18042C2B9
0x18042c2ad  mov     dl, 1
0x18042c2af  mov     ecx, ebx
0x18042c2b1  call    cs:__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z; NetUI::ScalePixelsForSystemSettings(int,bool)
0x18042c2b7  jmp     short loc_18042C2E2
0x18042c2b9  xor     edx, edx
0x18042c2bb  lea     rcx, [rbp+57h+hDC]
0x18042c2bf  call    ?GetScaleFactor@Art@@YAMAEBV?$TConvertibleDPI2@M@Gfx@@_N@Z; Art::GetScaleFactor(Gfx::TConvertibleDPI2<float> const &,bool)
0x18042c2c4  movd    xmm1, ebx
0x18042c2c8  cvtdq2ps xmm1, xmm1
0x18042c2cb  mulss   xmm1, xmm0
0x18042c2cf  cvtps2pd xmm0, xmm1; X
0x18042c2d2  call    cs:__imp_round
0x18042c2d8  cvttsd2si ecx, xmm0
0x18042c2dc  call    cs:__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z; NetUI::ScaleProportionalToSystemFontPx(int)
0x18042c2e2  mov     ebx, eax
0x18042c2e4  mov     qword ptr [rbp+57h+rc.left], 0
0x18042c2ec  mov     [rbp+57h+rc.right], esi
0x18042c2ef  mov     [rbp+57h+rc.bottom], eax
0x18042c2f2  call    ?GetTransparentColor@Art@@YAKXZ; Art::GetTransparentColor(void)
0x18042c2f7  mov     r15d, eax
0x18042c2fa  xor     ecx, ecx; hWnd
0x18042c2fc  call    cs:__imp_GetDC
0x18042c302  mov     rdi, rax
0x18042c305  mov     [rbp+57h+var_88], rax
0x18042c309  xorps   xmm0, xmm0
0x18042c30c  movdqu  [rbp+57h+var_80], xmm0
0x18042c311  xor     r9d, r9d
0x18042c314  mov     r8d, ebx
0x18042c317  mov     edx, esi
0x18042c319  mov     rcx, rax
0x18042c31c  call    cs:__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z; MsoHbmpCreateCompatibleBitmap(HDC__ *,int,int,void *)
0x18042c322  mov     rsi, rax
0x18042c325  mov     [rbp+57h+var_60], rax
0x18042c329  test    rax, rax
0x18042c32c  jnz     short loc_18042C33D
0x18042c32e  mov     ecx, 13906CCh; unsigned int
0x18042c333  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x18042c338  nop
0x18042c339  jmp     short loc_18042C33C
0x18042c33c  nop
0x18042c33d  xorps   xmm0, xmm0
0x18042c340  movdqu  xmmword ptr [rbp+57h+hDC], xmm0
0x18042c345  mov     r8, rsi; HBITMAP
0x18042c348  mov     rdx, rdi; HDC
0x18042c34b  lea     rcx, [rbp+57h+hDC]; this
0x18042c34f  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x18042c354  mov     r8d, r15d; unsigned int
0x18042c357  mov     rbx, [rbp+57h+hDC]
0x18042c35b  mov     rdx, rbx; HDC
0x18042c35e  lea     rcx, [rbp+57h+hbr]; this
0x18042c362  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x18042c367  mov     r8, [rbp+57h+hbr]; hbr
0x18042c36b  lea     rdx, [rbp+57h+rc]; lprc
0x18042c36f  mov     rcx, rbx; hDC
0x18042c372  call    cs:__imp_FillRect
0x18042c378  lea     rdx, [rbp+57h+rc]; struct tagRECT *
0x18042c37c  mov     rcx, rbx; HDC
0x18042c37f  call    ?DrawFontSchemeIconBackground@FontSchemePicker@Art@@KAXPEAUHDC__@@AEBUtagRECT@@_N@Z; Art::FontSchemePicker::DrawFontSchemeIconBackground(HDC__ *,tagRECT const &,bool)
0x18042c384  mov     r9d, [rbp+57h+var_C0]; unsigned int
0x18042c388  mov     r8, r13; struct Art::FontScheme *
0x18042c38b  lea     rdx, [rbp+57h+rc]; struct tagRECT *
0x18042c38f  mov     rcx, rbx; HDC
0x18042c392  call    ?DrawFontSchemeAnchorIcon@FontSchemePicker@Art@@KAXPEAUHDC__@@AEBUtagRECT@@AEBVFontScheme@2@K@Z; Art::FontSchemePicker::DrawFontSchemeAnchorIcon(HDC__ *,tagRECT const &,Art::FontScheme const &,ulong)
0x18042c397  movaps  xmm0, xmmword ptr [rbp+57h+rc.left]
0x18042c39b  movdqa  xmmword ptr [rbp+57h+var_60], xmm0
0x18042c3a0  lea     rax, [rbp+57h+var_60]
0x18042c3a4  mov     qword ptr [rsp+110h+var_F0], rax; unsigned int
0x18042c3a9  mov     r9d, 816C61h; int
0x18042c3af  mov     rcx, rbx; this
0x18042c3b2  call    ?FrameRect@Ofc@@YAXPEAUHDC__@@HHKAEBUtagRECT@@@Z; Ofc::FrameRect(HDC__ *,int,int,ulong,tagRECT const &)
0x18042c3b7  xor     r13d, r13d
0x18042c3ba  mov     [rsp+40h], r13b
0x18042c3bf  mov     [rsp+110h+var_D8], 1
0x18042c3c4  mov     [rsp+110h+var_E0], r13b
0x18042c3c9  mov     byte ptr [rsp+110h+var_E8], r13b
0x18042c3ce  mov     byte ptr [rsp+110h+var_F0], r13b
0x18042c3d3  mov     r9d, r15d
0x18042c3d6  mov     r8b, 3
0x18042c3d9  mov     rdx, r12
0x18042c3dc  mov     rcx, rsi
0x18042c3df  call    cs:__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z; FlexUI::FlexValue::CreateImage(HBITMAP__ *,FlexUI::FlexValueSP &,uchar,uint,bool,bool,bool,bool,bool)
0x18042c3e5  mov     rcx, [r12]
0x18042c3e9  test    rcx, rcx
0x18042c3ec  jz      short loc_18042C3F7
0x18042c3ee  xor     edx, edx
0x18042c3f0  call    cs:__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z; FlexUI::FlexValue::SetGraphicScaleForDPI(bool)
0x18042c3f6  nop
0x18042c3f7  mov     rdx, [rbp+57h+h]; h
0x18042c3fb  test    rdx, rdx
0x18042c3fe  jz      short loc_18042C40A
0x18042c400  mov     rcx, [rbp+57h+hdc]; hdc
0x18042c404  call    cs:__imp_SelectObject
0x18042c40a  cmp     [rbp+57h+hbr], r13
0x18042c40e  jz      short loc_18042C41B
0x18042c410  mov     rcx, [rbp+57h+hbr]; ho
0x18042c414  call    cs:__imp_DeleteObject
0x18042c41a  nop
0x18042c41b  test    rbx, rbx
0x18042c41e  jz      short loc_18042C43C
0x18042c420  mov     rdx, [rbp+57h+hDC+8]; h
0x18042c424  test    rdx, rdx
0x18042c427  jz      short loc_18042C432
0x18042c429  mov     rcx, rbx; hdc
0x18042c42c  call    cs:__imp_SelectObject
0x18042c432  mov     rcx, rbx; hdc
0x18042c435  call    cs:__imp_DeleteDC
0x18042c43b  nop
0x18042c43c  test    rdi, rdi
0x18042c43f  jz      short loc_18042C44D
0x18042c441  mov     rdx, rdi; hDC
0x18042c444  xor     ecx, ecx; hWnd
0x18042c446  call    cs:__imp_ReleaseDC
0x18042c44c  nop
0x18042c44d  lea     rcx, [rbp+57h+var_B8]; struct Ofc::CProxyPtrImpl **
0x18042c451  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18042c456  mov     rcx, [rbp+57h+var_50]
0x18042c45a  xor     rcx, rsp; StackCookie
0x18042c45d  call    __security_check_cookie
0x18042c462  movaps  xmm7, [rsp+110h+var_48+8]
0x18042c46a  add     rsp, 0E0h
0x18042c471  pop     r15
0x18042c473  pop     r13
0x18042c475  pop     r12
0x18042c477  pop     rdi
0x18042c478  pop     rsi
0x18042c479  pop     rbx
0x18042c47a  pop     rbp
0x18042c47b  retn
```
