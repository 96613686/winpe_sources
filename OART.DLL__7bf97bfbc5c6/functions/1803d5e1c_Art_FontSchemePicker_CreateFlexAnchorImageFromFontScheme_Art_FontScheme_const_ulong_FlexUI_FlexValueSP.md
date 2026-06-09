# Art::FontSchemePicker::CreateFlexAnchorImageFromFontScheme(Art::FontScheme const &,ulong,FlexUI::FlexValueSP &)

- ea: `0x1803d5e1c`
- end: `0x1803d6120`
- name: `?CreateFlexAnchorImageFromFontScheme@FontSchemePicker@Art@@IEAAXAEBVFontScheme@2@KAEAVFlexValueSP@FlexUI@@@Z`
- size: `772`
- prototype: `void(Art::FontSchemePicker *__hidden this, const struct Art::FontScheme *, unsigned int, struct FlexUI::FlexValueSP *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18053a620`

## callees

- `0x18000da00`
- `0x18000dbc0`
- `0x180070fe0`
- `0x180071720`
- `0x180152ee0`
- `0x1802f67e8`
- `0x1803374f0`
- `0x180337554`
- `0x1803375ac`
- `0x1803d5e1c`
- `0x1803d6120`
- `0x1803d6204`
- `0x1803d68f0`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x180a1b6bc`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!round` at `0x1803d5f15`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1803d5f76`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1803d5f15`
- `api-ms-win-crt-math-l1-1-0!round` at `0x1803d5f76`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x1803d5ea5`
- `Mso98Win32Client!__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ` at `0x1803d5ea5`
- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x1803d6083`
- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x1803d6083`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x1803d5f1f`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x1803d5f80`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x1803d5f1f`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x1803d5f80`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x1803d5fc0`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x1803d5fc0`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x1803d6094`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x1803d6094`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x1803d5ef4`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x1803d5f55`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x1803d5ef4`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x1803d5f55`
- `GDI32!SelectObject` at `0x1803d60a8`
- `GDI32!SelectObject` at `0x1803d60d0`
- `GDI32!SelectObject` at `0x1803d60a8`
- `GDI32!SelectObject` at `0x1803d60d0`
- `GDI32!DeleteObject` at `0x1803d60b8`
- `GDI32!DeleteObject` at `0x1803d60b8`
- `GDI32!DeleteDC` at `0x1803d60d9`
- `GDI32!DeleteDC` at `0x1803d60d9`
- `USER32!FillRect` at `0x1803d6016`
- `USER32!FillRect` at `0x1803d6016`
- `USER32!GetDC` at `0x1803d5fa0`
- `USER32!GetDC` at `0x1803d5fa0`
- `USER32!ReleaseDC` at `0x1803d60ea`
- `USER32!ReleaseDC` at `0x1803d60ea`

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
0x1803d5e1c  mov     rax, rsp
0x1803d5e1f  push    rbp
0x1803d5e20  push    rbx
0x1803d5e21  push    rsi
0x1803d5e22  push    rdi
0x1803d5e23  push    r12
0x1803d5e25  push    r13
0x1803d5e27  push    r15
0x1803d5e29  lea     rbp, [rax-5Fh]
0x1803d5e2d  sub     rsp, 0E0h
0x1803d5e34  movaps  xmmword ptr [rax-48h], xmm7
0x1803d5e38  mov     rax, cs:__security_cookie
0x1803d5e3f  xor     rax, rsp
0x1803d5e42  mov     [rbp+57h+var_50], rax
0x1803d5e46  mov     r12, r9
0x1803d5e49  mov     [rbp+57h+var_C0], r8d
0x1803d5e4d  mov     r13, rdx
0x1803d5e50  mov     rbx, rcx
0x1803d5e53  mov     rcx, [rcx+0F0h]
0x1803d5e5a  cmp     qword ptr [rcx+10h], 0
0x1803d5e5f  jnz     short loc_1803D5E68
0x1803d5e61  mov     rcx, [rbx+0F8h]; struct Ofc::CProxyPtrImpl *
0x1803d5e68  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1803d5e6d  mov     [rbp+57h+var_B8], rax
0x1803d5e71  mov     rcx, rax; this
0x1803d5e74  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803d5e79  mov     rcx, rax
0x1803d5e7c  mov     rdx, [rax]
0x1803d5e7f  mov     rax, [rdx+60h]
0x1803d5e83  lea     rdx, [rbp+57h+var_60]
0x1803d5e87  call    cs:__guard_dispatch_icall_fptr
0x1803d5e8d  mov     rdx, rax
0x1803d5e90  lea     rcx, [rbp+57h+hDC]
0x1803d5e94  call    ?GetDPIFromUserInterface@Art@@YA?AV?$TConvertibleDPI2@M@Gfx@@AEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::GetDPIFromUserInterface(Ofc::TWeakPtr<Art::UserInterface> const &)
0x1803d5e99  lea     rcx, [rbp+57h+var_60]; struct Ofc::CProxyPtrImpl **
0x1803d5e9d  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1803d5ea2  mov     rcx, rbx
0x1803d5ea5  call    cs:__imp_?GetGalleryDataSource@CMsoGalleryUserDefault@@UEAAAEAVGalleryDSSP@@XZ; CMsoGalleryUserDefault::GetGalleryDataSource(void)
0x1803d5eab  mov     r8d, 42C0003Dh
0x1803d5eb1  mov     rcx, [rax]
0x1803d5eb4  call    ??$DataSourceGetImpl@V?$TypeTraits@_N@FlexUI@@@FlexUI@@YA_NPEAUIDataSource@0@IH@Z; FlexUI::DataSourceGetImpl<FlexUI::TypeTraits<bool>>(FlexUI::IDataSource *,uint,int)
0x1803d5eb9  movzx   edi, al
0x1803d5ebc  inc     edi
0x1803d5ebe  mov     rcx, [rbp+57h+var_B8]; this
0x1803d5ec2  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803d5ec7  mov     rdx, rax
0x1803d5eca  mov     rcx, [rax]
0x1803d5ecd  mov     rax, [rcx+70h]
0x1803d5ed1  mov     rcx, rdx
0x1803d5ed4  call    cs:__guard_dispatch_icall_fptr
0x1803d5eda  mov     ebx, eax
0x1803d5edc  imul    ebx, edi
0x1803d5edf  call    ?FDynamicDpiEnabled@Art@@YA_NXZ; Art::FDynamicDpiEnabled(void)
0x1803d5ee4  movsd   xmm7, cs:__real@c1e0000000000000
0x1803d5eec  test    al, al
0x1803d5eee  jnz     short loc_1803D5EFC
0x1803d5ef0  mov     dl, 1
0x1803d5ef2  mov     ecx, ebx
0x1803d5ef4  call    cs:__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z; NetUI::ScalePixelsForSystemSettings(int,bool)
0x1803d5efa  jmp     short loc_1803D5F25
0x1803d5efc  xor     edx, edx
0x1803d5efe  lea     rcx, [rbp+57h+hDC]
0x1803d5f02  call    ?GetScaleFactor@Art@@YAMAEBV?$TConvertibleDPI2@M@Gfx@@_N@Z; Art::GetScaleFactor(Gfx::TConvertibleDPI2<float> const &,bool)
0x1803d5f07  movd    xmm1, ebx
0x1803d5f0b  cvtdq2ps xmm1, xmm1
0x1803d5f0e  mulss   xmm1, xmm0
0x1803d5f12  cvtps2pd xmm0, xmm1; X
0x1803d5f15  call    cs:__imp_round
0x1803d5f1b  cvttsd2si ecx, xmm0
0x1803d5f1f  call    cs:__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z; NetUI::ScaleProportionalToSystemFontPx(int)
0x1803d5f25  mov     esi, eax
0x1803d5f27  mov     rcx, [rbp+57h+var_B8]; this
0x1803d5f2b  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803d5f30  mov     rdx, rax
0x1803d5f33  mov     rcx, [rax]
0x1803d5f36  mov     rax, [rcx+70h]
0x1803d5f3a  mov     rcx, rdx
0x1803d5f3d  call    cs:__guard_dispatch_icall_fptr
0x1803d5f43  mov     ebx, eax
0x1803d5f45  imul    ebx, edi
0x1803d5f48  call    ?FDynamicDpiEnabled@Art@@YA_NXZ; Art::FDynamicDpiEnabled(void)
0x1803d5f4d  test    al, al
0x1803d5f4f  jnz     short loc_1803D5F5D
0x1803d5f51  mov     dl, 1
0x1803d5f53  mov     ecx, ebx
0x1803d5f55  call    cs:__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z; NetUI::ScalePixelsForSystemSettings(int,bool)
0x1803d5f5b  jmp     short loc_1803D5F86
0x1803d5f5d  xor     edx, edx
0x1803d5f5f  lea     rcx, [rbp+57h+hDC]
0x1803d5f63  call    ?GetScaleFactor@Art@@YAMAEBV?$TConvertibleDPI2@M@Gfx@@_N@Z; Art::GetScaleFactor(Gfx::TConvertibleDPI2<float> const &,bool)
0x1803d5f68  movd    xmm1, ebx
0x1803d5f6c  cvtdq2ps xmm1, xmm1
0x1803d5f6f  mulss   xmm1, xmm0
0x1803d5f73  cvtps2pd xmm0, xmm1; X
0x1803d5f76  call    cs:__imp_round
0x1803d5f7c  cvttsd2si ecx, xmm0
0x1803d5f80  call    cs:__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z; NetUI::ScaleProportionalToSystemFontPx(int)
0x1803d5f86  mov     ebx, eax
0x1803d5f88  mov     qword ptr [rbp+57h+rc.left], 0
0x1803d5f90  mov     [rbp+57h+rc.right], esi
0x1803d5f93  mov     [rbp+57h+rc.bottom], eax
0x1803d5f96  call    ?GetTransparentColor@Art@@YAKXZ; Art::GetTransparentColor(void)
0x1803d5f9b  mov     r15d, eax
0x1803d5f9e  xor     ecx, ecx; hWnd
0x1803d5fa0  call    cs:__imp_GetDC
0x1803d5fa6  mov     rdi, rax
0x1803d5fa9  mov     [rbp+57h+var_88], rax
0x1803d5fad  xorps   xmm0, xmm0
0x1803d5fb0  movdqu  [rbp+57h+var_80], xmm0
0x1803d5fb5  xor     r9d, r9d
0x1803d5fb8  mov     r8d, ebx
0x1803d5fbb  mov     edx, esi
0x1803d5fbd  mov     rcx, rax
0x1803d5fc0  call    cs:__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z; MsoHbmpCreateCompatibleBitmap(HDC__ *,int,int,void *)
0x1803d5fc6  mov     rsi, rax
0x1803d5fc9  mov     [rbp+57h+var_60], rax
0x1803d5fcd  test    rax, rax
0x1803d5fd0  jnz     short loc_1803D5FE1
0x1803d5fd2  mov     ecx, 13906CCh; unsigned int
0x1803d5fd7  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x1803d5fdc  nop
0x1803d5fdd  jmp     short loc_1803D5FE0
0x1803d5fe0  nop
0x1803d5fe1  xorps   xmm0, xmm0
0x1803d5fe4  movdqu  xmmword ptr [rbp+57h+hDC], xmm0
0x1803d5fe9  mov     r8, rsi; HBITMAP
0x1803d5fec  mov     rdx, rdi; HDC
0x1803d5fef  lea     rcx, [rbp+57h+hDC]; this
0x1803d5ff3  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x1803d5ff8  mov     r8d, r15d; unsigned int
0x1803d5ffb  mov     rbx, [rbp+57h+hDC]
0x1803d5fff  mov     rdx, rbx; HDC
0x1803d6002  lea     rcx, [rbp+57h+hbr]; this
0x1803d6006  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x1803d600b  mov     r8, [rbp+57h+hbr]; hbr
0x1803d600f  lea     rdx, [rbp+57h+rc]; lprc
0x1803d6013  mov     rcx, rbx; hDC
0x1803d6016  call    cs:__imp_FillRect
0x1803d601c  lea     rdx, [rbp+57h+rc]; struct tagRECT *
0x1803d6020  mov     rcx, rbx; HDC
0x1803d6023  call    ?DrawFontSchemeIconBackground@FontSchemePicker@Art@@KAXPEAUHDC__@@AEBUtagRECT@@_N@Z; Art::FontSchemePicker::DrawFontSchemeIconBackground(HDC__ *,tagRECT const &,bool)
0x1803d6028  mov     r9d, [rbp+57h+var_C0]; unsigned int
0x1803d602c  mov     r8, r13; struct Art::FontScheme *
0x1803d602f  lea     rdx, [rbp+57h+rc]; struct tagRECT *
0x1803d6033  mov     rcx, rbx; HDC
0x1803d6036  call    ?DrawFontSchemeAnchorIcon@FontSchemePicker@Art@@KAXPEAUHDC__@@AEBUtagRECT@@AEBVFontScheme@2@K@Z; Art::FontSchemePicker::DrawFontSchemeAnchorIcon(HDC__ *,tagRECT const &,Art::FontScheme const &,ulong)
0x1803d603b  movaps  xmm0, xmmword ptr [rbp+57h+rc.left]
0x1803d603f  movdqa  xmmword ptr [rbp+57h+var_60], xmm0
0x1803d6044  lea     rax, [rbp+57h+var_60]
0x1803d6048  mov     qword ptr [rsp+110h+var_F0], rax; unsigned int
0x1803d604d  mov     r9d, 816C61h; int
0x1803d6053  mov     rcx, rbx; this
0x1803d6056  call    ?FrameRect@Ofc@@YAXPEAUHDC__@@HHKAEBUtagRECT@@@Z; Ofc::FrameRect(HDC__ *,int,int,ulong,tagRECT const &)
0x1803d605b  xor     r13d, r13d
0x1803d605e  mov     [rsp+40h], r13b
0x1803d6063  mov     [rsp+110h+var_D8], 1
0x1803d6068  mov     [rsp+110h+var_E0], r13b
0x1803d606d  mov     byte ptr [rsp+110h+var_E8], r13b
0x1803d6072  mov     byte ptr [rsp+110h+var_F0], r13b
0x1803d6077  mov     r9d, r15d
0x1803d607a  mov     r8b, 3
0x1803d607d  mov     rdx, r12
0x1803d6080  mov     rcx, rsi
0x1803d6083  call    cs:__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z; FlexUI::FlexValue::CreateImage(HBITMAP__ *,FlexUI::FlexValueSP &,uchar,uint,bool,bool,bool,bool,bool)
0x1803d6089  mov     rcx, [r12]
0x1803d608d  test    rcx, rcx
0x1803d6090  jz      short loc_1803D609B
0x1803d6092  xor     edx, edx
0x1803d6094  call    cs:__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z; FlexUI::FlexValue::SetGraphicScaleForDPI(bool)
0x1803d609a  nop
0x1803d609b  mov     rdx, [rbp+57h+h]; h
0x1803d609f  test    rdx, rdx
0x1803d60a2  jz      short loc_1803D60AE
0x1803d60a4  mov     rcx, [rbp+57h+hdc]; hdc
0x1803d60a8  call    cs:__imp_SelectObject
0x1803d60ae  cmp     [rbp+57h+hbr], r13
0x1803d60b2  jz      short loc_1803D60BF
0x1803d60b4  mov     rcx, [rbp+57h+hbr]; ho
0x1803d60b8  call    cs:__imp_DeleteObject
0x1803d60be  nop
0x1803d60bf  test    rbx, rbx
0x1803d60c2  jz      short loc_1803D60E0
0x1803d60c4  mov     rdx, [rbp+57h+hDC+8]; h
0x1803d60c8  test    rdx, rdx
0x1803d60cb  jz      short loc_1803D60D6
0x1803d60cd  mov     rcx, rbx; hdc
0x1803d60d0  call    cs:__imp_SelectObject
0x1803d60d6  mov     rcx, rbx; hdc
0x1803d60d9  call    cs:__imp_DeleteDC
0x1803d60df  nop
0x1803d60e0  test    rdi, rdi
0x1803d60e3  jz      short loc_1803D60F1
0x1803d60e5  mov     rdx, rdi; hDC
0x1803d60e8  xor     ecx, ecx; hWnd
0x1803d60ea  call    cs:__imp_ReleaseDC
0x1803d60f0  nop
0x1803d60f1  lea     rcx, [rbp+57h+var_B8]; struct Ofc::CProxyPtrImpl **
0x1803d60f5  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1803d60fa  mov     rcx, [rbp+57h+var_50]
0x1803d60fe  xor     rcx, rsp; StackCookie
0x1803d6101  call    __security_check_cookie
0x1803d6106  movaps  xmm7, [rsp+110h+var_48+8]
0x1803d610e  add     rsp, 0E0h
0x1803d6115  pop     r15
0x1803d6117  pop     r13
0x1803d6119  pop     r12
0x1803d611b  pop     rdi
0x1803d611c  pop     rsi
0x1803d611d  pop     rbx
0x1803d611e  pop     rbp
0x1803d611f  retn
```
