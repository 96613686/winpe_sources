# Art::E2oGalleryUser::Draw(Ofc::TReferringPtr<Art::IE2o> const &,Ofc::TSharedPtr<Art::View> const &,GEL::Color const &,Ofc::CSize const &,Ofc::CSize const &,Art::Rect64 const &,Ofc::CSize const &)

- ea: `0x1802df93c`
- end: `0x1802e0186`
- name: `?Draw@E2oGalleryUser@Art@@AEAA?AVFlexValueSP@FlexUI@@AEBV?$TReferringPtr@VIE2o@Art@@@Ofc@@AEBV?$TSharedPtr@VView@Art@@@6@AEBUColor@GEL@@AEBVCSize@6@3AEBVRect64@2@3@Z`
- size: `2122`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: ``

## callers

- `0x1802df020`

## callees

- `0x180003c40`
- `0x18001df00`
- `0x180024f50`
- `0x180037370`
- `0x180037d30`
- `0x18003ff50`
- `0x180070fe0`
- `0x1800713c0`
- `0x180071720`
- `0x1800f47dc`
- `0x1800f4a90`
- `0x1801fb844`
- `0x1802a0590`
- `0x1802d3b84`
- `0x1802d4260`
- `0x1802d4308`
- `0x1802d4360`
- `0x1802df93c`
- `0x18042e738`
- `0x1804a9cf4`
- `0x1805310c4`
- `0x18053141c`
- `0x18061fd2c`
- `0x1806a5084`

## import_xrefs

- `gfx!?ColorToPixel32@Gfx@@YA?AUPixel32@ARC@@AEBUColor@GEL@@_N@Z` at `0x1802dfbbc`
- `gfx!?ColorToPixel32@Gfx@@YA?AUPixel32@ARC@@AEBUColor@GEL@@_N@Z` at `0x1802dfbbc`
- `gfx!?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z` at `0x1802dfa77`
- `gfx!?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z` at `0x1802dfa77`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z` at `0x1802e005a`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z` at `0x1802e005a`
- `Mso98Win32Client!__imp_?GetImageScaleFactor@CMsoGalleryUserDefault@@QEBAHXZ` at `0x1802dff89`
- `Mso98Win32Client!__imp_?GetImageScaleFactor@CMsoGalleryUserDefault@@QEBAHXZ` at `0x1802e000d`
- `Mso98Win32Client!__imp_?GetImageScaleFactor@CMsoGalleryUserDefault@@QEBAHXZ` at `0x1802dff89`
- `Mso98Win32Client!__imp_?GetImageScaleFactor@CMsoGalleryUserDefault@@QEBAHXZ` at `0x1802e000d`
- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x1802dfae5`
- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x1802dfae5`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x1802dfe21`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x1802dfe21`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x1802dfd98`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x1802dfe2f`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x1802dfd98`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x1802dfe2f`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x1802e010a`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x1802e010a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802dfd6c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802dfd6c`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1802dfaaf`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1802dfaaf`

## pseudocode

```c
FlexUI::FlexValueSP *__fastcall Art::E2oGalleryUser::Draw(
        CMsoGalleryUserDefault *a1,
        FlexUI::FlexValueSP *a2,
        FlexUI::FlexValue *a3,
        Ofc::CProxyPtrImpl **a4,
        GEL::Color *a5,
        int *a6,
        _DWORD *a7,
        _DWORD *a8,
        int *a9)
{
  char *Checked; // rax
  int v13; // ecx
  struct Gfx::ITarget *v14; // r15
  bool v15; // al
  const struct ARC::IFactory *v16; // rax
  const struct Gfx::IAbortSignal *v17; // r9
  Art::Color *v18; // rcx
  unsigned int COLORREF; // eax
  unsigned int *v20; // rax
  int v21; // r8d
  int v22; // edx
  int v23; // ecx
  int v24; // r8d
  int v25; // ecx
  __m128d v26; // xmm2
  __m128i v27; // xmm1
  Art::View *v28; // r13
  __int64 v29; // rax
  char v30; // cl
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v34; // rdx
  double v35; // xmm6_8
  unsigned int v36; // esi
  __int64 v37; // rax
  const struct FlexUI::FlexValueSP *v38; // rax
  char v39; // di
  double ImageScaleFactor; // xmm6_8
  unsigned int v41; // esi
  __int64 v42; // rax
  _QWORD *v43; // rax
  int v44; // [rsp+30h] [rbp-3D8h]
  int v45; // [rsp+38h] [rbp-3D0h]
  char v46; // [rsp+60h] [rbp-3A8h] BYREF
  struct Gfx::ITarget *v47; // [rsp+68h] [rbp-3A0h] BYREF
  int v48; // [rsp+70h] [rbp-398h]
  FlexUI::FlexValue *v49; // [rsp+78h] [rbp-390h] BYREF
  unsigned int v50; // [rsp+80h] [rbp-388h] BYREF
  _DWORD v51[3]; // [rsp+84h] [rbp-384h] BYREF
  FlexUI::FlexValueSP *v52; // [rsp+90h] [rbp-378h]
  Ofc::CProxyPtrImpl **v53; // [rsp+98h] [rbp-370h]
  struct Gfx::ITarget *v54; // [rsp+A0h] [rbp-368h] BYREF
  FlexUI::FlexValue *v55; // [rsp+A8h] [rbp-360h] BYREF
  CMsoGalleryUserDefault *v56; // [rsp+B0h] [rbp-358h] BYREF
  _DWORD *v57; // [rsp+B8h] [rbp-350h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-348h] BYREF
  struct Gfx::ITarget *v59; // [rsp+D0h] [rbp-338h] BYREF
  _DWORD *v60; // [rsp+D8h] [rbp-330h]
  float v61[4]; // [rsp+E0h] [rbp-328h] BYREF
  _DWORD v62[4]; // [rsp+F0h] [rbp-318h] BYREF
  _DWORD *v63; // [rsp+100h] [rbp-308h]
  CMsoGalleryUserDefault *v64; // [rsp+108h] [rbp-300h]
  Ofc::CProxyPtrImpl **v65; // [rsp+110h] [rbp-2F8h]
  _DWORD *v66; // [rsp+118h] [rbp-2F0h]
  _QWORD v67[10]; // [rsp+120h] [rbp-2E8h] BYREF
  __m128d v68; // [rsp+170h] [rbp-298h] BYREF
  _BYTE v69[24]; // [rsp+188h] [rbp-280h] BYREF
  struct Frame v70; // [rsp+1A0h] [rbp-268h] BYREF
  _BYTE v71[160]; // [rsp+250h] [rbp-1B8h] BYREF
  _BYTE v72[120]; // [rsp+2F0h] [rbp-118h] BYREF
  struct Gfx::ITarget *v73; // [rsp+368h] [rbp-A0h]

  v53 = a4;
  v49 = a3;
  v60 = a8;
  v65 = a4;
  v56 = a1;
  v64 = a1;
  v52 = a2;
  v55 = a3;
  v66 = a7;
  v57 = a8;
  v48 = 0;
  v50 = GEL::Color::ToPixel32(a5);
  Art::View::Info::Info((Art::View::Info *)v72);
  Checked = (char *)Ofc::CProxyPtrImpl::GetChecked(*a4);
  Art::View::Info::operator=(v72, Checked + 40);
  v54 = v73;
  v63 = a7 + 1;
  v13 = a7[1];
  v51[0] = *a7;
  v51[1] = v13;
  Gfx::IBitmapTarget::Create(&v59, v51, &v54, 1, 2);
  v48 = 16;
  v14 = v59;
  v59 = 0;
  v47 = v14;
  if ( byte_180E1CDE8 < 0 )
  {
    v15 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180E1CDE8);
    v14 = v47;
  }
  else
  {
    v15 = byte_180E1CDE8 != 0;
  }
  if ( v15 )
  {
    v46 = 0;
    v67[0] = &v50;
    v67[1] = a8;
    v67[2] = a1;
    v67[3] = a6;
    v67[4] = a9;
    v67[5] = a7;
    v67[6] = v53;
    v67[7] = &v47;
    v67[8] = &v46;
    v67[9] = v49;
    v34 = (*(__int64 (__fastcall **)(CMsoGalleryUserDefault *))(*(_QWORD *)a1 + 408LL))(a1) + 72;
    sub_1805310C4(v47, v34, v67);
    if ( v46 )
    {
      *(_QWORD *)a2 = 0;
      if ( v47 )
        (*(void (__fastcall **)(struct Gfx::ITarget *))(*(_QWORD *)v47 + 8LL))(v47);
      goto LABEL_30;
    }
LABEL_16:
    if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&qword_180E1CDF8) )
    {
      ImageScaleFactor = (double)(int)CMsoGalleryUserDefault::GetImageScaleFactor(a1);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v41 = GEL::Color::ToCOLORREF((GEL::Color *)&si128);
      v42 = (*(__int64 (__fastcall **)(struct Gfx::ITarget *, _QWORD))(*(_QWORD *)v47 + 464LL))(v47, *(_QWORD *)v47);
      v43 = (_QWORD *)GEL::IImage::Create(&v56, v42);
      v48 = 20;
      LOBYTE(v45) = 0;
      LOBYTE(v44) = 0;
      v38 = (const struct FlexUI::FlexValueSP *)Art::CreateFlexValueFromImage(
                                                  &v57,
                                                  *v43,
                                                  0,
                                                  v41,
                                                  *(_QWORD *)&ImageScaleFactor,
                                                  -1,
                                                  v44,
                                                  v45,
                                                  0,
                                                  1,
                                                  0);
      v39 = 28;
    }
    else
    {
      v35 = (double)(int)CMsoGalleryUserDefault::GetImageScaleFactor(a1);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v36 = GEL::Color::ToCOLORREF((GEL::Color *)&si128);
      v37 = (*(__int64 (__fastcall **)(struct Gfx::ITarget *))(*(_QWORD *)v47 + 472LL))(v47);
      LOBYTE(v45) = 0;
      LOBYTE(v44) = 0;
      v38 = (const struct FlexUI::FlexValueSP *)Art::CreateFlexValueFromImage(
                                                  &v55,
                                                  v37,
                                                  0,
                                                  v36,
                                                  *(_QWORD *)&v35,
                                                  -1,
                                                  v44,
                                                  v45,
                                                  0,
                                                  1,
                                                  0);
      v39 = 18;
    }
    FlexUI::FlexValueSP::FlexValueSP((FlexUI::FlexValueSP *)&v49, v38);
    if ( (v39 & 8) != 0 )
    {
      v39 &= ~8u;
      FlexUI::FlexValueSP::~FlexValueSP((FlexUI::FlexValueSP *)&v57);
    }
    if ( (v39 & 4) != 0 )
    {
      v39 &= ~4u;
      if ( v56 )
        (*(void (__fastcall **)(CMsoGalleryUserDefault *))(*(_QWORD *)v56 + 8LL))(v56);
    }
    if ( (v39 & 2) != 0 )
      FlexUI::FlexValueSP::~FlexValueSP((FlexUI::FlexValueSP *)&v55);
    if ( v49 )
      FlexUI::FlexValue::SetGraphicScaleForDPI(v49, 0);
    FlexUI::FlexValueSP::FlexValueSP(a2, (const struct FlexUI::FlexValueSP *)&v49);
    FlexUI::FlexValueSP::~FlexValueSP((FlexUI::FlexValueSP *)&v49);
    if ( v47 )
      (*(void (__fastcall **)(struct Gfx::ITarget *))(*(_QWORD *)v47 + 8LL))(v47);
LABEL_30:
    Art::View::Info::~Info((Art::View::Info *)v72);
    return a2;
  }
  v54 = v14;
  v16 = (const struct ARC::IFactory *)(*(__int64 (__fastcall **)(struct Gfx::ITarget *))(*(_QWORD *)v14 + 96LL))(v14);
  ARC::ExceptionScope::ExceptionScope((ARC::ExceptionScope *)v67, v16);
  v17 = (const struct Gfx::IAbortSignal *)((*(__int64 (__fastcall **)(CMsoGalleryUserDefault *))(*(_QWORD *)a1 + 408LL))(a1)
                                         + 72);
  Gfx::ITarget::Frame::Frame((Gfx::ITarget::Frame *)&v70, v14, 0, v17);
  Gfx::ITarget::Clip::Clip((Gfx::ITarget::Clip *)v71, &v70);
  v18 = (Art::Color *)Art::Color::Color(v69, 5);
  COLORREF = Art::Color::GetCOLORREF(v18);
  v61[0] = (float)(unsigned __int8)COLORREF / 255.0;
  v61[1] = (float)BYTE1(COLORREF) / 255.0;
  v61[2] = (float)BYTE2(COLORREF) / 255.0;
  v61[3] = 1.0;
  v20 = (unsigned int *)Gfx::ColorToPixel32(v51, v61, 0);
  Gfx::ITarget::Frame::Fill<ARC::Pixel32>(&v70, *v20);
  Art::Color::~Color((Art::Color *)v69);
  v21 = a8[6];
  v22 = a8[4];
  v23 = a8[2];
  v62[0] = *v60;
  v62[1] = v23;
  v62[2] = v22;
  v62[3] = v21;
  Gfx::ITarget::Frame::Fill<ARC::Pixel32,Ofc::CRect>(&v70, v50, v62);
  (*(void (__fastcall **)(CMsoGalleryUserDefault *))(*(_QWORD *)a1 + 408LL))(a1);
  v24 = *a6;
  v25 = a6[1];
  v26 = (__m128d)COERCE_UNSIGNED_INT64((double)v25);
  v26.m128d_f64[0] = fmin(v26.m128d_f64[0] / (double)a9[1], (double)*a6 / (double)*a9);
  v68 = _mm_unpacklo_pd(v26, v26);
  v27 = _mm_cvtsi32_si128((*v63 - v25) / 2);
  *(double *)si128.m128i_i64 = (double)((*a7 - v24) / 2);
  si128.m128i_i64[1] = *(_OWORD *)&_mm_cvtepi32_pd(v27);
  v28 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(*v53);
  v29 = (*(__int64 (__fastcall **)(CMsoGalleryUserDefault *))(*(_QWORD *)a1 + 408LL))(a1);
  v30 = Art::View::FDrawToTarget(
          v28,
          v47,
          (const struct GEL::Vector *)&si128,
          (const struct GEL::Vector *)&v68,
          (const struct Gfx::IAbortSignal *)(v29 + 72),
          0,
          0,
          0);
  v31 = *(_QWORD *)v64;
  if ( v30 )
  {
    (*(void (__fastcall **)(CMsoGalleryUserDefault *, FlexUI::FlexValue *, _DWORD *, struct Gfx::ITarget *))(v31 + 440))(
      a1,
      v49,
      a7,
      v47);
    (*((void (__fastcall **)(struct FrameVtbl *, _QWORD))v70.lpVtbl->QueryInterface + 39))(v70.lpVtbl, 0);
    Gfx::ITarget::Clip::~Clip((Gfx::ITarget::Clip *)v71);
    Gfx::ITarget::Frame::~Frame((Gfx::ITarget::Frame *)&v70);
    ARC::ExceptionScope::RethrowCachedException((ARC::ExceptionScope *)v67);
    ARC::ExceptionScope::~ExceptionScope((ARC::ExceptionScope *)v67);
    goto LABEL_16;
  }
  v32 = (*(__int64 (__fastcall **)(CMsoGalleryUserDefault *))(v31 + 408))(a1);
  if ( !(**(unsigned __int8 (__fastcall ***)(__int64))(v32 + 72))(v32 + 72) )
    MsoShipAssertTagProc(591939796);
  *(_QWORD *)a2 = 0;
  Gfx::ITarget::Clip::~Clip((Gfx::ITarget::Clip *)v71);
  Gfx::ITarget::Frame::~Frame((Gfx::ITarget::Frame *)&v70);
  ARC::ExceptionScope::~ExceptionScope((ARC::ExceptionScope *)v67);
  if ( v47 )
    (*(void (__fastcall **)(struct Gfx::ITarget *))(*(_QWORD *)v47 + 8LL))(v47);
  Art::View::Info::~Info((Art::View::Info *)v72);
  return a2;
}

```

## disassembly

```asm
0x1802df93c  mov     rax, rsp
0x1802df93f  push    rbx
0x1802df940  push    rsi
0x1802df941  push    rdi
0x1802df942  push    r12
0x1802df944  push    r13
0x1802df946  push    r14
0x1802df948  push    r15
0x1802df94a  sub     rsp, 3D0h
0x1802df951  movaps  xmmword ptr [rax-48h], xmm6
0x1802df955  mov     rax, cs:__security_cookie
0x1802df95c  xor     rax, rsp
0x1802df95f  mov     [rsp+408h+var_58], rax
0x1802df967  mov     rdi, r9
0x1802df96a  mov     [rsp+408h+var_370], r9
0x1802df972  mov     [rsp+408h+var_390], r8
0x1802df977  mov     r14, rdx
0x1802df97a  mov     rsi, rcx
0x1802df97d  mov     rax, [rsp+408h+arg_38]
0x1802df985  mov     [rsp+408h+var_330], rax
0x1802df98d  mov     [rsp+408h+var_2F8], r9
0x1802df995  mov     [rsp+408h+var_358], rcx
0x1802df99d  mov     [rsp+408h+var_300], rcx
0x1802df9a5  mov     [rsp+408h+var_378], rdx
0x1802df9ad  mov     [rsp+408h+var_360], r8
0x1802df9b5  mov     rcx, [rsp+408h+arg_20]; this
0x1802df9bd  mov     r12, [rsp+408h+arg_30]
0x1802df9c5  mov     [rsp+408h+var_2F0], r12
0x1802df9cd  mov     r13, rax
0x1802df9d0  mov     [rsp+408h+var_350], rax
0x1802df9d8  xor     ebx, ebx
0x1802df9da  mov     [rsp+408h+var_398], ebx
0x1802df9de  call    ?ToPixel32@Color@GEL@@QEBAKXZ; GEL::Color::ToPixel32(void)
0x1802df9e3  mov     [rsp+408h+var_388], eax
0x1802df9ea  lea     rcx, [rsp+408h+var_118]; this
0x1802df9f2  call    ??0Info@View@Art@@QEAA@XZ; Art::View::Info::Info(void)
0x1802df9f7  mov     rcx, [rdi]; this
0x1802df9fa  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1802df9ff  lea     rdx, [rax+28h]
0x1802dfa03  lea     rcx, [rsp+408h+var_118]
0x1802dfa0b  call    ??4Info@View@Art@@QEAAAEAU012@AEBU012@@Z; Art::View::Info::operator=(Art::View::Info const &)
0x1802dfa10  movsd   xmm0, [rsp+408h+var_A0]
0x1802dfa19  movsd   [rsp+408h+var_368], xmm0
0x1802dfa22  lea     rax, [r12+4]
0x1802dfa27  mov     [rsp+408h+var_308], rax
0x1802dfa2f  mov     ecx, [rax]
0x1802dfa31  mov     eax, [r12]
0x1802dfa35  mov     [rsp+408h+var_384], eax
0x1802dfa3c  mov     [rsp+408h+var_384+4], ecx
0x1802dfa43  mov     rax, qword ptr [rsp+408h+var_384]
0x1802dfa4b  mov     qword ptr [rsp+408h+var_384], rax
0x1802dfa53  mov     dword ptr [rsp+408h+var_3E8], 2
0x1802dfa5b  lea     r9d, [rbx+1]
0x1802dfa5f  lea     r8, [rsp+408h+var_368]
0x1802dfa67  lea     rdx, [rsp+408h+var_384]
0x1802dfa6f  lea     rcx, [rsp+408h+var_338]
0x1802dfa77  call    cs:__imp_?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z; Gfx::IBitmapTarget::Create(Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,Gfx::TConvertibleDPI2<float> const &,ARC::AlphaMode,uint)
0x1802dfa7d  lea     edi, [rbx+10h]
0x1802dfa80  mov     [rsp+408h+var_398], edi
0x1802dfa84  mov     r15, [rsp+408h+var_338]
0x1802dfa8c  mov     [rsp+408h+var_338], rbx
0x1802dfa94  mov     [rsp+408h+var_3A0], r15
0x1802dfa99  mov     al, cs:byte_180E1CDE8
0x1802dfa9f  test    al, al
0x1802dfaa1  js      short loc_1802DFAA8
0x1802dfaa3  setnz   al
0x1802dfaa6  jmp     short loc_1802DFABA
0x1802dfaa8  lea     rcx, byte_180E1CDE8
0x1802dfaaf  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1802dfab5  mov     r15, [rsp+408h+var_3A0]
0x1802dfaba  test    al, al
0x1802dfabc  jnz     loc_1802DFE8A
0x1802dfac2  mov     [rsp+408h+var_368], r15
0x1802dfaca  mov     rax, [r15]
0x1802dfacd  mov     rcx, r15
0x1802dfad0  mov     rax, [rax+60h]
0x1802dfad4  call    cs:__guard_dispatch_icall_fptr
0x1802dfada  mov     rdx, rax
0x1802dfadd  lea     rcx, [rsp+408h+var_2E8]
0x1802dfae5  call    cs:__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z; ARC::ExceptionScope::ExceptionScope(ARC::IFactory const *)
0x1802dfaeb  nop
0x1802dfaec  mov     rax, [rsi]
0x1802dfaef  mov     rcx, rsi
0x1802dfaf2  mov     rax, [rax+198h]
0x1802dfaf9  call    cs:__guard_dispatch_icall_fptr
0x1802dfaff  lea     r9, [rax+48h]; struct Gfx::IAbortSignal *
0x1802dfb03  xor     r8d, r8d; struct Gfx::IRegionAccumulator *
0x1802dfb06  mov     rdx, r15; struct Gfx::ITarget *
0x1802dfb09  lea     rcx, [rsp+408h+var_268]; this
0x1802dfb11  call    ??0Frame@ITarget@Gfx@@QEAA@AEAU12@PEAUIRegionAccumulator@2@PEBUIAbortSignal@2@@Z; Gfx::ITarget::Frame::Frame(Gfx::ITarget &,Gfx::IRegionAccumulator *,Gfx::IAbortSignal const *)
0x1802dfb16  lea     rdx, [rsp+408h+var_268]; struct Frame *
0x1802dfb1e  lea     rcx, [rsp+408h+var_1B8]; this
0x1802dfb26  call    ??0Clip@ITarget@Gfx@@QEAA@AEAVFrame@12@@Z; Gfx::ITarget::Clip::Clip(Gfx::ITarget::Frame &)
0x1802dfb2b  mov     edx, 5
0x1802dfb30  lea     rcx, [rsp+408h+var_280]
0x1802dfb38  call    ??0Color@Art@@QEAA@W4SystemColorVal@1@@Z; Art::Color::Color(Art::SystemColorVal)
0x1802dfb3d  mov     rcx, rax; this
0x1802dfb40  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x1802dfb45  mov     ecx, eax
0x1802dfb47  shr     eax, 10h
0x1802dfb4a  movzx   eax, al
0x1802dfb4d  movd    xmm3, eax
0x1802dfb51  cvtdq2ps xmm3, xmm3
0x1802dfb54  movss   xmm2, cs:__real@437f0000
0x1802dfb5c  divss   xmm3, xmm2
0x1802dfb60  movzx   eax, cx
0x1802dfb63  shr     ax, 8
0x1802dfb67  movzx   eax, ax
0x1802dfb6a  movd    xmm1, eax
0x1802dfb6e  cvtdq2ps xmm1, xmm1
0x1802dfb71  divss   xmm1, xmm2
0x1802dfb75  movzx   eax, cl
0x1802dfb78  movd    xmm0, eax
0x1802dfb7c  cvtdq2ps xmm0, xmm0
0x1802dfb7f  divss   xmm0, xmm2
0x1802dfb83  movss   [rsp+408h+var_328], xmm0
0x1802dfb8c  movss   [rsp+408h+var_324], xmm1
0x1802dfb95  movss   [rsp+408h+var_320], xmm3
0x1802dfb9e  mov     [rsp+408h+var_31C], 3F800000h
0x1802dfba9  xor     r8d, r8d
0x1802dfbac  lea     rdx, [rsp+408h+var_328]
0x1802dfbb4  lea     rcx, [rsp+408h+var_384]
0x1802dfbbc  call    cs:__imp_?ColorToPixel32@Gfx@@YA?AUPixel32@ARC@@AEBUColor@GEL@@_N@Z; Gfx::ColorToPixel32(GEL::Color const &,bool)
0x1802dfbc2  mov     edx, [rax]
0x1802dfbc4  lea     rcx, [rsp+408h+var_268]
0x1802dfbcc  call    ??$Fill@UPixel32@ARC@@@Frame@ITarget@Gfx@@QEAAXUPixel32@ARC@@@Z; Gfx::ITarget::Frame::Fill<ARC::Pixel32>(ARC::Pixel32)
0x1802dfbd1  nop
0x1802dfbd2  lea     rcx, [rsp+408h+var_280]; this
0x1802dfbda  call    ??1Color@Art@@QEAA@XZ; Art::Color::~Color(void)
0x1802dfbdf  mov     r8d, [r13+18h]
0x1802dfbe3  mov     edx, [r13+10h]
0x1802dfbe7  mov     ecx, [r13+8]
0x1802dfbeb  mov     rax, [rsp+408h+var_330]
0x1802dfbf3  mov     eax, [rax]
0x1802dfbf5  mov     [rsp+408h+var_318], eax
0x1802dfbfc  mov     [rsp+408h+var_314], ecx
0x1802dfc03  mov     [rsp+408h+var_310], edx
0x1802dfc0a  mov     [rsp+408h+var_30C], r8d
0x1802dfc12  lea     r8, [rsp+408h+var_318]
0x1802dfc1a  mov     edx, [rsp+408h+var_388]
0x1802dfc21  lea     rcx, [rsp+408h+var_268]
0x1802dfc29  call    ??$Fill@UPixel32@ARC@@VCRect@Ofc@@@Frame@ITarget@Gfx@@QEAAXUPixel32@ARC@@AEBVCRect@Ofc@@@Z; Gfx::ITarget::Frame::Fill<ARC::Pixel32,Ofc::CRect>(ARC::Pixel32,Ofc::CRect const &)
0x1802dfc2e  mov     rax, [rsi]
0x1802dfc31  mov     rcx, rsi
0x1802dfc34  mov     rax, [rax+198h]
0x1802dfc3b  call    cs:__guard_dispatch_icall_fptr
0x1802dfc41  mov     rax, [rsp+408h+arg_28]
0x1802dfc49  mov     r8d, [rax]
0x1802dfc4c  mov     ecx, [rax+4]
0x1802dfc4f  movd    xmm2, ecx
0x1802dfc53  cvtdq2pd xmm2, xmm2
0x1802dfc57  mov     rax, [rsp+408h+arg_40]
0x1802dfc5f  movd    xmm0, dword ptr [rax+4]
0x1802dfc64  cvtdq2pd xmm0, xmm0
0x1802dfc68  divsd   xmm2, xmm0
0x1802dfc6c  movd    xmm1, r8d
0x1802dfc71  cvtdq2pd xmm1, xmm1
0x1802dfc75  movd    xmm0, dword ptr [rax]
0x1802dfc79  cvtdq2pd xmm0, xmm0
0x1802dfc7d  divsd   xmm1, xmm0
0x1802dfc81  minsd   xmm2, xmm1
0x1802dfc85  unpcklpd xmm2, xmm2
0x1802dfc89  movups  [rsp+408h+var_298], xmm2
0x1802dfc91  mov     rax, [rsp+408h+var_308]
0x1802dfc99  mov     eax, [rax]
0x1802dfc9b  sub     eax, ecx
0x1802dfc9d  cdq
0x1802dfc9e  mov     r15d, 2
0x1802dfca4  idiv    r15d
0x1802dfca7  movd    xmm1, eax
0x1802dfcab  mov     eax, [r12]
0x1802dfcaf  sub     eax, r8d
0x1802dfcb2  cdq
0x1802dfcb3  idiv    r15d
0x1802dfcb6  movd    xmm0, eax
0x1802dfcba  cvtdq2pd xmm0, xmm0
0x1802dfcbe  movsd   qword ptr [rsp+408h+var_348], xmm0
0x1802dfcc7  cvtdq2pd xmm1, xmm1
0x1802dfccb  movsd   qword ptr [rsp+408h+var_348+8], xmm1
0x1802dfcd4  mov     rax, [rsp+408h+var_370]
0x1802dfcdc  mov     rcx, [rax]; this
0x1802dfcdf  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1802dfce4  mov     r13, rax
0x1802dfce7  mov     rax, [rsi]
0x1802dfcea  mov     rcx, rsi
0x1802dfced  mov     rax, [rax+198h]
0x1802dfcf4  call    cs:__guard_dispatch_icall_fptr
0x1802dfcfa  add     rax, 48h ; 'H'
0x1802dfcfe  mov     [rsp+408h+var_3D0], rbx; struct Gfx::IShape *
0x1802dfd03  mov     [rsp+408h+var_3D8], rbx; struct Gfx::IShapeFilter *
0x1802dfd08  mov     [rsp+408h+var_3E0], bl; bool
0x1802dfd0c  mov     [rsp+408h+var_3E8], rax; struct Gfx::IAbortSignal *
0x1802dfd11  lea     r9, [rsp+408h+var_298]; struct GEL::Vector *
0x1802dfd19  lea     r8, [rsp+408h+var_348]; struct GEL::Vector *
0x1802dfd21  mov     rdx, [rsp+408h+var_3A0]; struct Gfx::ITarget *
0x1802dfd26  mov     rcx, r13; this
0x1802dfd29  call    ?FDrawToTarget@View@Art@@QEAA_NAEAUITarget@Gfx@@AEBUVector@GEL@@1PEBUIAbortSignal@4@_NPEBUIShapeFilter@4@PEBUIShape@4@@Z; Art::View::FDrawToTarget(Gfx::ITarget &,GEL::Vector const &,GEL::Vector const &,Gfx::IAbortSignal const *,bool,Gfx::IShapeFilter const *,Gfx::IShape const *)
0x1802dfd2e  mov     cl, al
0x1802dfd30  mov     rax, [rsp+408h+var_300]
0x1802dfd38  mov     rax, [rax]
0x1802dfd3b  test    cl, cl
0x1802dfd3d  mov     rcx, rsi
0x1802dfd40  jnz     loc_1802DFDCB
0x1802dfd46  mov     rax, [rax+198h]
0x1802dfd4d  call    cs:__guard_dispatch_icall_fptr
0x1802dfd53  lea     rcx, [rax+48h]
0x1802dfd57  mov     rax, [rcx]
0x1802dfd5a  mov     rax, [rax]
0x1802dfd5d  call    cs:__guard_dispatch_icall_fptr
0x1802dfd63  test    al, al
0x1802dfd65  jnz     short loc_1802DFD72
0x1802dfd67  mov     ecx, 234848D4h
0x1802dfd6c  call    cs:__imp_MsoShipAssertTagProc
0x1802dfd72  mov     [r14], rbx
0x1802dfd75  lea     rcx, [rsp+408h+var_1B8]; this
0x1802dfd7d  call    ??1Clip@ITarget@Gfx@@QEAA@XZ; Gfx::ITarget::Clip::~Clip(void)
0x1802dfd82  lea     rcx, [rsp+408h+var_268]; this
0x1802dfd8a  call    ??1Frame@ITarget@Gfx@@QEAA@XZ; Gfx::ITarget::Frame::~Frame(void)
0x1802dfd8f  nop
0x1802dfd90  lea     rcx, [rsp+408h+var_2E8]
0x1802dfd98  call    cs:__imp_??1ExceptionScope@ARC@@QEAA@XZ; ARC::ExceptionScope::~ExceptionScope(void)
0x1802dfd9e  mov     rcx, [rsp+408h+var_3A0]
0x1802dfda3  test    rcx, rcx
0x1802dfda6  jz      short loc_1802DFDB6
0x1802dfda8  mov     rdx, [rcx]
0x1802dfdab  mov     rax, [rdx+8]
0x1802dfdaf  call    cs:__guard_dispatch_icall_fptr
0x1802dfdb5  nop
0x1802dfdb6  lea     rcx, [rsp+408h+var_118]; this
0x1802dfdbe  call    ??1Info@View@Art@@QEAA@XZ; Art::View::Info::~Info(void)
0x1802dfdc3  mov     rax, r14
0x1802dfdc6  jmp     loc_1802E015B
0x1802dfdcb  mov     r9, [rsp+408h+var_3A0]
0x1802dfdd0  mov     r8, r12
0x1802dfdd3  mov     rdx, [rsp+408h+var_390]
0x1802dfdd8  mov     rax, [rax+1B8h]
0x1802dfddf  call    cs:__guard_dispatch_icall_fptr
0x1802dfde5  mov     rcx, [rsp+408h+var_268.lpVtbl]
0x1802dfded  mov     rax, [rcx]
0x1802dfdf0  xor     edx, edx
0x1802dfdf2  mov     rax, [rax+138h]
0x1802dfdf9  call    cs:__guard_dispatch_icall_fptr
0x1802dfdff  lea     rcx, [rsp+408h+var_1B8]; this
0x1802dfe07  call    ??1Clip@ITarget@Gfx@@QEAA@XZ; Gfx::ITarget::Clip::~Clip(void)
0x1802dfe0c  lea     rcx, [rsp+408h+var_268]; this
0x1802dfe14  call    ??1Frame@ITarget@Gfx@@QEAA@XZ; Gfx::ITarget::Frame::~Frame(void)
0x1802dfe19  lea     rcx, [rsp+408h+var_2E8]
0x1802dfe21  call    cs:__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ; ARC::ExceptionScope::RethrowCachedException(void)
0x1802dfe27  lea     rcx, [rsp+408h+var_2E8]
0x1802dfe2f  call    cs:__imp_??1ExceptionScope@ARC@@QEAA@XZ; ARC::ExceptionScope::~ExceptionScope(void)
0x1802dfe35  jmp     loc_1802DFF72
0x1802dfe3a  xor     ebx, ebx
0x1802dfe3c  mov     r15, [rsp+408h+var_368]
0x1802dfe44  mov     edi, [rsp+408h+var_398]
0x1802dfe48  mov     rax, [rsp+408h+var_2F8]
0x1802dfe50  mov     [rsp+408h+var_370], rax
0x1802dfe58  mov     r12, [rsp+408h+var_2F0]
0x1802dfe60  mov     rax, [rsp+408h+var_360]
0x1802dfe68  mov     [rsp+408h+var_390], rax
0x1802dfe6d  mov     rsi, [rsp+408h+var_358]
0x1802dfe75  mov     r14, [rsp+408h+var_378]
0x1802dfe7d  mov     r13, [rsp+408h+var_350]
0x1802dfe85  jmp     loc_1802DFAEC
0x1802dfe8a  mov     [rsp+408h+var_3A8], bl
0x1802dfe8e  lea     rax, [rsp+408h+var_388]
0x1802dfe96  mov     [rsp+408h+var_2E8], rax
0x1802dfe9e  mov     [rsp+408h+var_2E0], r13
0x1802dfea6  mov     [rsp+408h+var_2D8], rsi
0x1802dfeae  mov     rax, [rsp+408h+arg_28]
0x1802dfeb6  mov     [rsp+408h+var_2D0], rax
0x1802dfebe  mov     rax, [rsp+408h+arg_40]
0x1802dfec6  mov     [rsp+408h+var_2C8], rax
0x1802dfece  mov     [rsp+408h+var_2C0], r12
0x1802dfed6  mov     rax, [rsp+408h+var_370]
0x1802dfede  mov     [rsp+408h+var_2B8], rax
0x1802dfee6  lea     rax, [rsp+408h+var_3A0]
0x1802dfeeb  mov     [rsp+408h+var_2B0], rax
0x1802dfef3  lea     rax, [rsp+408h+var_3A8]
0x1802dfef8  mov     [rsp+408h+var_2A8], rax
0x1802dff00  mov     rcx, [rsp+408h+var_390]
0x1802dff05  mov     [rsp+408h+var_2A0], rcx
0x1802dff0d  mov     rax, [rsi]
0x1802dff10  mov     rcx, rsi
0x1802dff13  mov     rax, [rax+198h]
0x1802dff1a  call    cs:__guard_dispatch_icall_fptr
0x1802dff20  lea     rdx, [rax+48h]
0x1802dff24  lea     r8, [rsp+408h+var_2E8]
0x1802dff2c  mov     rcx, [rsp+408h+var_3A0]
0x1802dff31  call    sub_1805310C4
0x1802dff36  cmp     [rsp+408h+var_3A8], bl
0x1802dff3a  jz      short loc_1802DFF6C
0x1802dff3c  mov     [r14], rbx
0x1802dff3f  mov     rcx, [rsp+408h+var_3A0]
0x1802dff44  test    rcx, rcx
0x1802dff47  jz      short loc_1802DFF57
0x1802dff49  mov     rax, [rcx]
0x1802dff4c  mov     rax, [rax+8]
0x1802dff50  call    cs:__guard_dispatch_icall_fptr
0x1802dff56  nop
0x1802dff57  lea     rcx, [rsp+408h+var_118]; this
  ... truncated ...
```
