# Art::E2oGalleryUser::Draw(Ofc::TReferringPtr<Art::IE2o> const &,Ofc::TSharedPtr<Art::View> const &,GEL::Color const &,Ofc::CSize const &,Ofc::CSize const &,Art::Rect64 const &,Ofc::CSize const &)

- ea: `0x1803731ec`
- end: `0x180373a36`
- name: `?Draw@E2oGalleryUser@Art@@AEAA?AVFlexValueSP@FlexUI@@AEBV?$TReferringPtr@VIE2o@Art@@@Ofc@@AEBV?$TSharedPtr@VView@Art@@@6@AEBUColor@GEL@@AEBVCSize@6@3AEBVRect64@2@3@Z`
- size: `2122`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: ``

## callers

- `0x1803728d4`

## callees

- `0x180012630`
- `0x180026740`
- `0x18002a750`
- `0x1800d1790`
- `0x18010de00`
- `0x1801285f0`
- `0x1801ac61c`
- `0x1801ac720`
- `0x1801b6718`
- `0x1801b908c`
- `0x180217378`
- `0x180233850`
- `0x180278c20`
- `0x180278e70`
- `0x180279050`
- `0x18029aac0`
- `0x18029ada4`
- `0x1803731ec`
- `0x1804deba0`
- `0x180524eb4`
- `0x180554acc`
- `0x180554e20`
- `0x180641954`
- `0x1806bc4f0`

## import_xrefs

- `gfx!?ColorToPixel32@Gfx@@YA?AUPixel32@ARC@@AEBUColor@GEL@@_N@Z` at `0x18037346c`
- `gfx!?ColorToPixel32@Gfx@@YA?AUPixel32@ARC@@AEBUColor@GEL@@_N@Z` at `0x18037346c`
- `gfx!?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z` at `0x180373327`
- `gfx!?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z` at `0x180373327`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z` at `0x18037390a`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z` at `0x18037390a`
- `Mso98Win32Client!__imp_?GetImageScaleFactor@CMsoGalleryUserDefault@@QEBAHXZ` at `0x180373839`
- `Mso98Win32Client!__imp_?GetImageScaleFactor@CMsoGalleryUserDefault@@QEBAHXZ` at `0x1803738bd`
- `Mso98Win32Client!__imp_?GetImageScaleFactor@CMsoGalleryUserDefault@@QEBAHXZ` at `0x180373839`
- `Mso98Win32Client!__imp_?GetImageScaleFactor@CMsoGalleryUserDefault@@QEBAHXZ` at `0x1803738bd`
- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x180373395`
- `mso40uiWin32Client!__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z` at `0x180373395`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x1803736d1`
- `mso40uiWin32Client!__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ` at `0x1803736d1`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x180373648`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x1803736df`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x180373648`
- `mso40uiWin32Client!__imp_??1ExceptionScope@ARC@@QEAA@XZ` at `0x1803736df`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x1803739ba`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x1803739ba`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18037361c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18037361c`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18037335f`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18037335f`

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
  bool v30; // cl
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
  if ( byte_180E1CA78 < 0 )
  {
    v15 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180E1CA78);
    v14 = v47;
  }
  else
  {
    v15 = byte_180E1CA78 != 0;
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
    sub_180554ACC(v47, v34, v67);
    if ( v46 )
    {
      *(_QWORD *)a2 = 0;
      if ( v47 )
        (*(void (__fastcall **)(struct Gfx::ITarget *))(*(_QWORD *)v47 + 8LL))(v47);
      goto LABEL_30;
    }
LABEL_16:
    if ( (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&qword_180E1CA88) )
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
0x1803731ec  mov     rax, rsp
0x1803731ef  push    rbx
0x1803731f0  push    rsi
0x1803731f1  push    rdi
0x1803731f2  push    r12
0x1803731f4  push    r13
0x1803731f6  push    r14
0x1803731f8  push    r15
0x1803731fa  sub     rsp, 3D0h
0x180373201  movaps  xmmword ptr [rax-48h], xmm6
0x180373205  mov     rax, cs:__security_cookie
0x18037320c  xor     rax, rsp
0x18037320f  mov     [rsp+408h+var_58], rax
0x180373217  mov     rdi, r9
0x18037321a  mov     [rsp+408h+var_370], r9
0x180373222  mov     [rsp+408h+var_390], r8
0x180373227  mov     r14, rdx
0x18037322a  mov     rsi, rcx
0x18037322d  mov     rax, [rsp+408h+arg_38]
0x180373235  mov     [rsp+408h+var_330], rax
0x18037323d  mov     [rsp+408h+var_2F8], r9
0x180373245  mov     [rsp+408h+var_358], rcx
0x18037324d  mov     [rsp+408h+var_300], rcx
0x180373255  mov     [rsp+408h+var_378], rdx
0x18037325d  mov     [rsp+408h+var_360], r8
0x180373265  mov     rcx, [rsp+408h+arg_20]; this
0x18037326d  mov     r12, [rsp+408h+arg_30]
0x180373275  mov     [rsp+408h+var_2F0], r12
0x18037327d  mov     r13, rax
0x180373280  mov     [rsp+408h+var_350], rax
0x180373288  xor     ebx, ebx
0x18037328a  mov     [rsp+408h+var_398], ebx
0x18037328e  call    ?ToPixel32@Color@GEL@@QEBAKXZ; GEL::Color::ToPixel32(void)
0x180373293  mov     [rsp+408h+var_388], eax
0x18037329a  lea     rcx, [rsp+408h+var_118]; this
0x1803732a2  call    ??0Info@View@Art@@QEAA@XZ; Art::View::Info::Info(void)
0x1803732a7  mov     rcx, [rdi]; this
0x1803732aa  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803732af  lea     rdx, [rax+28h]
0x1803732b3  lea     rcx, [rsp+408h+var_118]
0x1803732bb  call    ??4Info@View@Art@@QEAAAEAU012@AEBU012@@Z; Art::View::Info::operator=(Art::View::Info const &)
0x1803732c0  movsd   xmm0, [rsp+408h+var_A0]
0x1803732c9  movsd   [rsp+408h+var_368], xmm0
0x1803732d2  lea     rax, [r12+4]
0x1803732d7  mov     [rsp+408h+var_308], rax
0x1803732df  mov     ecx, [rax]
0x1803732e1  mov     eax, [r12]
0x1803732e5  mov     [rsp+408h+var_384], eax
0x1803732ec  mov     [rsp+408h+var_384+4], ecx
0x1803732f3  mov     rax, qword ptr [rsp+408h+var_384]
0x1803732fb  mov     qword ptr [rsp+408h+var_384], rax
0x180373303  mov     dword ptr [rsp+408h+var_3E8], 2
0x18037330b  lea     r9d, [rbx+1]
0x18037330f  lea     r8, [rsp+408h+var_368]
0x180373317  lea     rdx, [rsp+408h+var_384]
0x18037331f  lea     rcx, [rsp+408h+var_338]
0x180373327  call    cs:__imp_?Create@IBitmapTarget@Gfx@@SA?AV?$TCntPtr@UIBitmapTarget@Gfx@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBV?$TConvertibleDPI2@M@2@W4AlphaMode@ARC@@I@Z; Gfx::IBitmapTarget::Create(Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,Gfx::TConvertibleDPI2<float> const &,ARC::AlphaMode,uint)
0x18037332d  lea     edi, [rbx+10h]
0x180373330  mov     [rsp+408h+var_398], edi
0x180373334  mov     r15, [rsp+408h+var_338]
0x18037333c  mov     [rsp+408h+var_338], rbx
0x180373344  mov     [rsp+408h+var_3A0], r15
0x180373349  mov     al, cs:byte_180E1CA78
0x18037334f  test    al, al
0x180373351  js      short loc_180373358
0x180373353  setnz   al
0x180373356  jmp     short loc_18037336A
0x180373358  lea     rcx, byte_180E1CA78
0x18037335f  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x180373365  mov     r15, [rsp+408h+var_3A0]
0x18037336a  test    al, al
0x18037336c  jnz     loc_18037373A
0x180373372  mov     [rsp+408h+var_368], r15
0x18037337a  mov     rax, [r15]
0x18037337d  mov     rcx, r15
0x180373380  mov     rax, [rax+60h]
0x180373384  call    cs:__guard_dispatch_icall_fptr
0x18037338a  mov     rdx, rax
0x18037338d  lea     rcx, [rsp+408h+var_2E8]
0x180373395  call    cs:__imp_??0ExceptionScope@ARC@@QEAA@PEBUIFactory@1@@Z; ARC::ExceptionScope::ExceptionScope(ARC::IFactory const *)
0x18037339b  nop
0x18037339c  mov     rax, [rsi]
0x18037339f  mov     rcx, rsi
0x1803733a2  mov     rax, [rax+198h]
0x1803733a9  call    cs:__guard_dispatch_icall_fptr
0x1803733af  lea     r9, [rax+48h]; struct Gfx::IAbortSignal *
0x1803733b3  xor     r8d, r8d; struct Gfx::IRegionAccumulator *
0x1803733b6  mov     rdx, r15; struct Gfx::ITarget *
0x1803733b9  lea     rcx, [rsp+408h+var_268]; this
0x1803733c1  call    ??0Frame@ITarget@Gfx@@QEAA@AEAU12@PEAUIRegionAccumulator@2@PEBUIAbortSignal@2@@Z; Gfx::ITarget::Frame::Frame(Gfx::ITarget &,Gfx::IRegionAccumulator *,Gfx::IAbortSignal const *)
0x1803733c6  lea     rdx, [rsp+408h+var_268]; struct Frame *
0x1803733ce  lea     rcx, [rsp+408h+var_1B8]; this
0x1803733d6  call    ??0Clip@ITarget@Gfx@@QEAA@AEAVFrame@12@@Z; Gfx::ITarget::Clip::Clip(Gfx::ITarget::Frame &)
0x1803733db  mov     edx, 5
0x1803733e0  lea     rcx, [rsp+408h+var_280]
0x1803733e8  call    ??0Color@Art@@QEAA@W4SystemColorVal@1@@Z; Art::Color::Color(Art::SystemColorVal)
0x1803733ed  mov     rcx, rax; this
0x1803733f0  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x1803733f5  mov     ecx, eax
0x1803733f7  shr     eax, 10h
0x1803733fa  movzx   eax, al
0x1803733fd  movd    xmm3, eax
0x180373401  cvtdq2ps xmm3, xmm3
0x180373404  movss   xmm2, cs:__real@437f0000
0x18037340c  divss   xmm3, xmm2
0x180373410  movzx   eax, cx
0x180373413  shr     ax, 8
0x180373417  movzx   eax, ax
0x18037341a  movd    xmm1, eax
0x18037341e  cvtdq2ps xmm1, xmm1
0x180373421  divss   xmm1, xmm2
0x180373425  movzx   eax, cl
0x180373428  movd    xmm0, eax
0x18037342c  cvtdq2ps xmm0, xmm0
0x18037342f  divss   xmm0, xmm2
0x180373433  movss   [rsp+408h+var_328], xmm0
0x18037343c  movss   [rsp+408h+var_324], xmm1
0x180373445  movss   [rsp+408h+var_320], xmm3
0x18037344e  mov     [rsp+408h+var_31C], 3F800000h
0x180373459  xor     r8d, r8d
0x18037345c  lea     rdx, [rsp+408h+var_328]
0x180373464  lea     rcx, [rsp+408h+var_384]
0x18037346c  call    cs:__imp_?ColorToPixel32@Gfx@@YA?AUPixel32@ARC@@AEBUColor@GEL@@_N@Z; Gfx::ColorToPixel32(GEL::Color const &,bool)
0x180373472  mov     edx, [rax]
0x180373474  lea     rcx, [rsp+408h+var_268]
0x18037347c  call    ??$Fill@UPixel32@ARC@@@Frame@ITarget@Gfx@@QEAAXUPixel32@ARC@@@Z; Gfx::ITarget::Frame::Fill<ARC::Pixel32>(ARC::Pixel32)
0x180373481  nop
0x180373482  lea     rcx, [rsp+408h+var_280]; this
0x18037348a  call    ??1Color@Art@@QEAA@XZ; Art::Color::~Color(void)
0x18037348f  mov     r8d, [r13+18h]
0x180373493  mov     edx, [r13+10h]
0x180373497  mov     ecx, [r13+8]
0x18037349b  mov     rax, [rsp+408h+var_330]
0x1803734a3  mov     eax, [rax]
0x1803734a5  mov     [rsp+408h+var_318], eax
0x1803734ac  mov     [rsp+408h+var_314], ecx
0x1803734b3  mov     [rsp+408h+var_310], edx
0x1803734ba  mov     [rsp+408h+var_30C], r8d
0x1803734c2  lea     r8, [rsp+408h+var_318]
0x1803734ca  mov     edx, [rsp+408h+var_388]
0x1803734d1  lea     rcx, [rsp+408h+var_268]
0x1803734d9  call    ??$Fill@UPixel32@ARC@@VCRect@Ofc@@@Frame@ITarget@Gfx@@QEAAXUPixel32@ARC@@AEBVCRect@Ofc@@@Z; Gfx::ITarget::Frame::Fill<ARC::Pixel32,Ofc::CRect>(ARC::Pixel32,Ofc::CRect const &)
0x1803734de  mov     rax, [rsi]
0x1803734e1  mov     rcx, rsi
0x1803734e4  mov     rax, [rax+198h]
0x1803734eb  call    cs:__guard_dispatch_icall_fptr
0x1803734f1  mov     rax, [rsp+408h+arg_28]
0x1803734f9  mov     r8d, [rax]
0x1803734fc  mov     ecx, [rax+4]
0x1803734ff  movd    xmm2, ecx
0x180373503  cvtdq2pd xmm2, xmm2
0x180373507  mov     rax, [rsp+408h+arg_40]
0x18037350f  movd    xmm0, dword ptr [rax+4]
0x180373514  cvtdq2pd xmm0, xmm0
0x180373518  divsd   xmm2, xmm0
0x18037351c  movd    xmm1, r8d
0x180373521  cvtdq2pd xmm1, xmm1
0x180373525  movd    xmm0, dword ptr [rax]
0x180373529  cvtdq2pd xmm0, xmm0
0x18037352d  divsd   xmm1, xmm0
0x180373531  minsd   xmm2, xmm1
0x180373535  unpcklpd xmm2, xmm2
0x180373539  movups  [rsp+408h+var_298], xmm2
0x180373541  mov     rax, [rsp+408h+var_308]
0x180373549  mov     eax, [rax]
0x18037354b  sub     eax, ecx
0x18037354d  cdq
0x18037354e  mov     r15d, 2
0x180373554  idiv    r15d
0x180373557  movd    xmm1, eax
0x18037355b  mov     eax, [r12]
0x18037355f  sub     eax, r8d
0x180373562  cdq
0x180373563  idiv    r15d
0x180373566  movd    xmm0, eax
0x18037356a  cvtdq2pd xmm0, xmm0
0x18037356e  movsd   qword ptr [rsp+408h+var_348], xmm0
0x180373577  cvtdq2pd xmm1, xmm1
0x18037357b  movsd   qword ptr [rsp+408h+var_348+8], xmm1
0x180373584  mov     rax, [rsp+408h+var_370]
0x18037358c  mov     rcx, [rax]; this
0x18037358f  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180373594  mov     r13, rax
0x180373597  mov     rax, [rsi]
0x18037359a  mov     rcx, rsi
0x18037359d  mov     rax, [rax+198h]
0x1803735a4  call    cs:__guard_dispatch_icall_fptr
0x1803735aa  add     rax, 48h ; 'H'
0x1803735ae  mov     [rsp+408h+var_3D0], rbx; struct Gfx::IShape *
0x1803735b3  mov     [rsp+408h+var_3D8], rbx; struct Gfx::IShapeFilter *
0x1803735b8  mov     [rsp+408h+var_3E0], bl; bool
0x1803735bc  mov     [rsp+408h+var_3E8], rax; struct Gfx::IAbortSignal *
0x1803735c1  lea     r9, [rsp+408h+var_298]; struct GEL::Vector *
0x1803735c9  lea     r8, [rsp+408h+var_348]; struct GEL::Vector *
0x1803735d1  mov     rdx, [rsp+408h+var_3A0]; struct Gfx::ITarget *
0x1803735d6  mov     rcx, r13; this
0x1803735d9  call    ?FDrawToTarget@View@Art@@QEAA_NAEAUITarget@Gfx@@AEBUVector@GEL@@1PEBUIAbortSignal@4@_NPEBUIShapeFilter@4@PEBUIShape@4@@Z; Art::View::FDrawToTarget(Gfx::ITarget &,GEL::Vector const &,GEL::Vector const &,Gfx::IAbortSignal const *,bool,Gfx::IShapeFilter const *,Gfx::IShape const *)
0x1803735de  mov     cl, al
0x1803735e0  mov     rax, [rsp+408h+var_300]
0x1803735e8  mov     rax, [rax]
0x1803735eb  test    cl, cl
0x1803735ed  mov     rcx, rsi
0x1803735f0  jnz     loc_18037367B
0x1803735f6  mov     rax, [rax+198h]
0x1803735fd  call    cs:__guard_dispatch_icall_fptr
0x180373603  lea     rcx, [rax+48h]
0x180373607  mov     rax, [rcx]
0x18037360a  mov     rax, [rax]
0x18037360d  call    cs:__guard_dispatch_icall_fptr
0x180373613  test    al, al
0x180373615  jnz     short loc_180373622
0x180373617  mov     ecx, 234848D4h
0x18037361c  call    cs:__imp_MsoShipAssertTagProc
0x180373622  mov     [r14], rbx
0x180373625  lea     rcx, [rsp+408h+var_1B8]; this
0x18037362d  call    ??1Clip@ITarget@Gfx@@QEAA@XZ; Gfx::ITarget::Clip::~Clip(void)
0x180373632  lea     rcx, [rsp+408h+var_268]; this
0x18037363a  call    ??1Frame@ITarget@Gfx@@QEAA@XZ; Gfx::ITarget::Frame::~Frame(void)
0x18037363f  nop
0x180373640  lea     rcx, [rsp+408h+var_2E8]
0x180373648  call    cs:__imp_??1ExceptionScope@ARC@@QEAA@XZ; ARC::ExceptionScope::~ExceptionScope(void)
0x18037364e  mov     rcx, [rsp+408h+var_3A0]
0x180373653  test    rcx, rcx
0x180373656  jz      short loc_180373666
0x180373658  mov     rdx, [rcx]
0x18037365b  mov     rax, [rdx+8]
0x18037365f  call    cs:__guard_dispatch_icall_fptr
0x180373665  nop
0x180373666  lea     rcx, [rsp+408h+var_118]; this
0x18037366e  call    ??1Info@View@Art@@QEAA@XZ; Art::View::Info::~Info(void)
0x180373673  mov     rax, r14
0x180373676  jmp     loc_180373A0B
0x18037367b  mov     r9, [rsp+408h+var_3A0]
0x180373680  mov     r8, r12
0x180373683  mov     rdx, [rsp+408h+var_390]
0x180373688  mov     rax, [rax+1B8h]
0x18037368f  call    cs:__guard_dispatch_icall_fptr
0x180373695  mov     rcx, [rsp+408h+var_268.lpVtbl]
0x18037369d  mov     rax, [rcx]
0x1803736a0  xor     edx, edx
0x1803736a2  mov     rax, [rax+138h]
0x1803736a9  call    cs:__guard_dispatch_icall_fptr
0x1803736af  lea     rcx, [rsp+408h+var_1B8]; this
0x1803736b7  call    ??1Clip@ITarget@Gfx@@QEAA@XZ; Gfx::ITarget::Clip::~Clip(void)
0x1803736bc  lea     rcx, [rsp+408h+var_268]; this
0x1803736c4  call    ??1Frame@ITarget@Gfx@@QEAA@XZ; Gfx::ITarget::Frame::~Frame(void)
0x1803736c9  lea     rcx, [rsp+408h+var_2E8]
0x1803736d1  call    cs:__imp_?RethrowCachedException@ExceptionScope@ARC@@QEAAXXZ; ARC::ExceptionScope::RethrowCachedException(void)
0x1803736d7  lea     rcx, [rsp+408h+var_2E8]
0x1803736df  call    cs:__imp_??1ExceptionScope@ARC@@QEAA@XZ; ARC::ExceptionScope::~ExceptionScope(void)
0x1803736e5  jmp     loc_180373822
0x1803736ea  xor     ebx, ebx
0x1803736ec  mov     r15, [rsp+408h+var_368]
0x1803736f4  mov     edi, [rsp+408h+var_398]
0x1803736f8  mov     rax, [rsp+408h+var_2F8]
0x180373700  mov     [rsp+408h+var_370], rax
0x180373708  mov     r12, [rsp+408h+var_2F0]
0x180373710  mov     rax, [rsp+408h+var_360]
0x180373718  mov     [rsp+408h+var_390], rax
0x18037371d  mov     rsi, [rsp+408h+var_358]
0x180373725  mov     r14, [rsp+408h+var_378]
0x18037372d  mov     r13, [rsp+408h+var_350]
0x180373735  jmp     loc_18037339C
0x18037373a  mov     [rsp+408h+var_3A8], bl
0x18037373e  lea     rax, [rsp+408h+var_388]
0x180373746  mov     [rsp+408h+var_2E8], rax
0x18037374e  mov     [rsp+408h+var_2E0], r13
0x180373756  mov     [rsp+408h+var_2D8], rsi
0x18037375e  mov     rax, [rsp+408h+arg_28]
0x180373766  mov     [rsp+408h+var_2D0], rax
0x18037376e  mov     rax, [rsp+408h+arg_40]
0x180373776  mov     [rsp+408h+var_2C8], rax
0x18037377e  mov     [rsp+408h+var_2C0], r12
0x180373786  mov     rax, [rsp+408h+var_370]
0x18037378e  mov     [rsp+408h+var_2B8], rax
0x180373796  lea     rax, [rsp+408h+var_3A0]
0x18037379b  mov     [rsp+408h+var_2B0], rax
0x1803737a3  lea     rax, [rsp+408h+var_3A8]
0x1803737a8  mov     [rsp+408h+var_2A8], rax
0x1803737b0  mov     rcx, [rsp+408h+var_390]
0x1803737b5  mov     [rsp+408h+var_2A0], rcx
0x1803737bd  mov     rax, [rsi]
0x1803737c0  mov     rcx, rsi
0x1803737c3  mov     rax, [rax+198h]
0x1803737ca  call    cs:__guard_dispatch_icall_fptr
0x1803737d0  lea     rdx, [rax+48h]
0x1803737d4  lea     r8, [rsp+408h+var_2E8]
0x1803737dc  mov     rcx, [rsp+408h+var_3A0]
0x1803737e1  call    sub_180554ACC
0x1803737e6  cmp     [rsp+408h+var_3A8], bl
0x1803737ea  jz      short loc_18037381C
0x1803737ec  mov     [r14], rbx
0x1803737ef  mov     rcx, [rsp+408h+var_3A0]
0x1803737f4  test    rcx, rcx
0x1803737f7  jz      short loc_180373807
0x1803737f9  mov     rax, [rcx]
0x1803737fc  mov     rax, [rax+8]
0x180373800  call    cs:__guard_dispatch_icall_fptr
0x180373806  nop
0x180373807  lea     rcx, [rsp+408h+var_118]; this
  ... truncated ...
```
