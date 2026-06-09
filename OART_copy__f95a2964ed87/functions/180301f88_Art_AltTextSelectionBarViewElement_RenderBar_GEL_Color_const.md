# Art::AltTextSelectionBarViewElement::RenderBar(GEL::Color const &)

- ea: `0x180301f88`
- end: `0x1803025f1`
- name: `?RenderBar@AltTextSelectionBarViewElement@Art@@AEAAXAEBUColor@GEL@@@Z`
- size: `1641`
- prototype: `void __fastcall(Art::AltTextSelectionBarViewElement *__hidden this, const struct GEL::Color *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180303600`

## callees

- `0x180019e80`
- `0x1800d1790`
- `0x1801061d0`
- `0x18010ccd0`
- `0x18010de00`
- `0x18014fd70`
- `0x1801518a0`
- `0x180159960`
- `0x1801b8328`
- `0x180221d98`
- `0x180276c60`
- `0x180278c20`
- `0x180278e70`
- `0x180279050`
- `0x1802ffc40`
- `0x180301368`
- `0x1803014a0`
- `0x180301f88`
- `0x180302a84`
- `0x18035e66c`
- `0x18035eef0`
- `0x18066ea48`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`

## import_xrefs

- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x180302399`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x180302399`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x18030236a`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x18030236a`
- `gfx!?Create@IEffectTransform@GEL@@SA?AV?$TCntPtr@UIEffectTransform@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x18030244c`
- `gfx!?Create@IEffectTransform@GEL@@SA?AV?$TCntPtr@UIEffectTransform@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x18030244c`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@W4RenderingPolicy@Gfx@@@Z` at `0x1803024ab`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@W4RenderingPolicy@Gfx@@@Z` at `0x1803024ab`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1803022a0`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1803023c9`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1803022a0`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1803023c9`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x18030233e`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x18030233e`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180302092`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180302136`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180302159`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18030219d`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180302092`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180302136`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x180302159`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x18030219d`

## pseudocode

```c
void __fastcall Art::AltTextSelectionBarViewElement::RenderBar(
        Art::AltTextSelectionBarViewElement *this,
        const struct GEL::Color *a2)
{
  double v3; // xmm1_8
  struct Ofc::CProxyPtrImpl **View; // rax
  struct Ofc::CProxyPtrImpl *v5; // rcx
  int v6; // eax
  char v7; // r12
  void *Checked; // rax
  __int16 v9; // bx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  void *v13; // rax
  const wchar_t **v14; // rax
  struct Ofc::CVarStr *v15; // rdx
  int v16; // r8d
  __int64 HinstIntl; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  char *v22; // rax
  Art *v23; // rcx
  int v24; // edx
  bool v25; // r13
  wchar_t *v26; // rdi
  char *v27; // rax
  wchar_t **v28; // rax
  __int64 v29; // rax
  __int64 v30; // rbx
  void (__fastcall *v31)(__int64, _QWORD); // r14
  Art::TextBuilder *v32; // rsi
  _QWORD *TextBuilderEffects; // rax
  unsigned int v34; // edx
  const struct Art::TextViewLine *TextViewLine; // rcx
  __int64 *v36; // rax
  __int64 v37; // r12
  __int128 v38; // xmm2
  __int64 v39; // rbx
  void (__fastcall *v40)(__int64, _QWORD); // r14
  _QWORD *v41; // rax
  unsigned int v42; // eax
  struct GEL::ITopLevelEffect **v43; // rax
  wchar_t *v44; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD *v45; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+58h] [rbp-B0h] BYREF
  Ofc::CProxyPtrImpl *v47; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v49; // [rsp+70h] [rbp-98h] BYREF
  __int64 v50; // [rsp+78h] [rbp-90h] BYREF
  __int64 v51; // [rsp+80h] [rbp-88h] BYREF
  Ofc::CProxyPtrImpl *v52; // [rsp+88h] [rbp-80h] BYREF
  Art::TextBuilder *v53; // [rsp+90h] [rbp-78h] BYREF
  struct Ofc::CProxyPtrImpl *v54; // [rsp+98h] [rbp-70h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-68h] BYREF
  _OWORD v56[3]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v57[56]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v58[192]; // [rsp+118h] [rbp+10h] BYREF

  v3 = *((double *)this + 40) - *((double *)this + 38);
  if ( v3 + v3 <= *((double *)this + 42) && v3 * *((double *)this + 57) <= *((double *)this + 41) )
  {
    View = (struct Ofc::CProxyPtrImpl **)Art::ViewElement::GetView(this);
    v47 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*View);
    v54 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*((struct Ofc::CProxyPtrImpl **)this + 47));
    v5 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*((struct Ofc::CProxyPtrImpl **)this + 48));
    v52 = v5;
    if ( *((_QWORD *)v5 + 2) )
    {
      v6 = *((_DWORD *)this + 98);
      v7 = 1;
      if ( v6 )
      {
        if ( v6 == 1 )
        {
          HinstIntl = MsoGetHinstIntl(v5, 2);
          sub_1801518A0((char *)this + 400, HinstIntl, 4093707006LL);
          v44 = (wchar_t *)&word_180A9C374;
          v20 = MsoGetHinstIntl(v19, v18);
          sub_1801518A0(&v44, v20, 4093706996LL);
          Ofc::CStr::Replace((wchar_t **)this + 50, L"^0", v44, 0);
          Ofc::XString::Release((Ofc::XString *)(v44 - 6));
        }
        else if ( v6 == 2 )
        {
          v21 = MsoGetHinstIntl(v5, 2);
          sub_1801518A0((char *)this + 400, v21, 4093706997LL);
        }
      }
      else
      {
        Checked = Ofc::CProxyPtrImpl::GetChecked(v5);
        v9 = **(_WORD **)(*(__int64 (__fastcall **)(void *, wchar_t **))(*(_QWORD *)Checked + 80LL))(Checked, &v44);
        Ofc::XString::Release((Ofc::XString *)(v44 - 6));
        v12 = MsoGetHinstIntl(v11, v10);
        sub_1801518A0((char *)this + 400, v12, 4093707006LL);
        if ( v9 )
        {
          v13 = Ofc::CProxyPtrImpl::GetChecked(v52);
          v14 = (const wchar_t **)(*(__int64 (__fastcall **)(void *, wchar_t **))(*(_QWORD *)v13 + 80LL))(v13, &v44);
          Ofc::CStr::Replace((wchar_t **)this + 50, L"^0", *v14, 0);
          Ofc::XString::Release((Ofc::XString *)(v44 - 6));
          Art::FRemoveAppendedAutoCaptionDisclaimer((wchar_t **)this + 50, v15);
          Art::FRemoveSubString((wchar_t **)this + 50, (struct Ofc::CVarStr *)0xF40102FDLL, v16);
        }
        else
        {
          Ofc::CStr::Replace((wchar_t **)this + 50, L"^0", &word_180B454F0, 0);
        }
      }
      Art::View::Info::Info((Art::View::Info *)v58);
      v22 = (char *)Ofc::CProxyPtrImpl::GetChecked(v47);
      Art::View::Info::operator=(v58, v22 + 40);
      Art::GetViewPixelToHostEMUScale(&v47);
      v25 = Art::FAltTextBarFeedbackUIEnabled(v23);
      v26 = 0;
      v44 = 0;
      if ( v25 )
      {
        v27 = (char *)Ofc::CProxyPtrImpl::GetChecked(v47);
        v28 = (wchar_t **)Art::AltTextBarFeedbackUIContainer::CreateUIEffects((char *)this + 464, &v53, v27 + 160);
        v26 = *v28;
        *v28 = 0;
        v44 = v26;
        if ( v53 )
          (*(void (__fastcall **)(Art::TextBuilder *))(*(_QWORD *)v53 + 8LL))(v53);
        *((double *)this + 53) = *((double *)this + 62) - *((double *)this + 55);
      }
      v29 = *((_QWORD *)this + 50);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      Art::AltTextSelectionBarViewElement::CreateAltTextBuilder(
        (unsigned int)&v53,
        v24,
        (unsigned int)v58,
        (_DWORD)this + 408,
        (__int64)&si128,
        v29,
        0);
      GEL::IEffectContainer::Create(&v50);
      v30 = v50;
      v31 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v50 + 144LL);
      v32 = v53;
      TextBuilderEffects = (_QWORD *)Art::GetTextBuilderEffects(&v45, v53);
      v31(v30, *TextBuilderEffects);
      if ( v45 )
        (*(void (__fastcall **)(_QWORD *))(*v45 + 8LL))(v45);
      if ( v25 )
      {
        TextViewLine = Art::TextBuilder::GetTextViewLine(v32, v34);
        if ( !TextViewLine || *((_DWORD *)TextViewLine + 13) > *(_DWORD *)(*((_QWORD *)this + 50) - 4LL) / 2 )
          v7 = 0;
        *((_BYTE *)this + 448) = v7;
      }
      v49 = 0;
      v36 = (__int64 *)GEL::IRectanglePath::Create(&v45, (char *)this + 296);
      v37 = *v36;
      *v36 = 0;
      si128.m128i_i64[0] = v37;
      if ( v45 )
        (*(void (__fastcall **)(_QWORD *))(*v45 + 8LL))(v45);
      Gfx::IFigureStyle::Create(&v48);
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v48 + 24LL))(
        v48,
        &Art::AltTextSelectionBarViewElement::c_defaultColor);
      Gfx::IFigureShapeBuilder::Create(&v51, v37, v48, 0);
      if ( !(*(unsigned int (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v51 + 424LL))(v51, &v49, 0) )
      {
        GEL::IEffectContainer::Create(&v46);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 144LL))(v46, v49);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v46 + 144LL))(v46, v50);
        if ( v25 )
        {
          if ( v26 )
          {
            v38 = *((_OWORD *)this + 31);
            v56[0] = _mm_load_si128((const __m128i *)&_xmm);
            v56[1] = _mm_load_si128((const __m128i *)&_xmm);
            v56[2] = v38;
            v39 = v46;
            v40 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v46 + 144LL);
            v41 = (_QWORD *)GEL::IEffectTransform::Create(&v45, v26, v56);
            v40(v39, *v41);
            if ( v45 )
              (*(void (__fastcall **)(_QWORD *))(*v45 + 8LL))(v45);
          }
        }
        Art::GetGelTransform(v57, (char *)this + 72);
        v42 = (*(__int64 (__fastcall **)(Art::AltTextSelectionBarViewElement *))(*(_QWORD *)this + 160LL))(this);
        v43 = (struct GEL::ITopLevelEffect **)GEL::ITopLevelEffect::Create(&v45, v46, v57, v42);
        Art::ViewElement::SetEffect(this, *v43);
        if ( v45 )
          (*(void (__fastcall **)(_QWORD *))(v45[1] + 8LL))(v45 + 1);
        if ( v46 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 8LL))(v46);
      }
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
      if ( v37 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
      if ( v49 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
      if ( v50 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
      if ( v32 )
      {
        Art::TextBuilder::~TextBuilder(v32);
        operator delete(v32);
      }
      if ( v26 )
        (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v26 + 8LL))(v26);
      Art::View::Info::~Info((Art::View::Info *)v58);
    }
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v52);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v54);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v47);
  }
}

```

## disassembly

```asm
0x180301f88  mov     rax, rsp
0x180301f8b  mov     [rax+10h], rbx
0x180301f8f  mov     [rax+18h], rsi
0x180301f93  mov     [rax+20h], rdi
0x180301f97  push    rbp
0x180301f98  push    r12
0x180301f9a  push    r13
0x180301f9c  push    r14
0x180301f9e  push    r15
0x180301fa0  lea     rbp, [rax-118h]
0x180301fa7  sub     rsp, 1F0h
0x180301fae  movaps  xmmword ptr [rax-38h], xmm6
0x180301fb2  mov     rax, cs:__security_cookie
0x180301fb9  xor     rax, rsp
0x180301fbc  mov     [rbp+110h+var_40], rax
0x180301fc3  mov     r15, rcx
0x180301fc6  movsd   xmm1, qword ptr [rcx+140h]
0x180301fce  subsd   xmm1, qword ptr [rcx+130h]
0x180301fd6  movaps  xmm0, xmm1
0x180301fd9  addsd   xmm0, xmm1
0x180301fdd  comisd  xmm0, qword ptr [rcx+150h]
0x180301fe5  ja      loc_1803025BC
0x180301feb  mulsd   xmm1, qword ptr [rcx+1C8h]
0x180301ff3  comisd  xmm1, qword ptr [rcx+148h]
0x180301ffb  ja      loc_1803025BC
0x180302001  call    ?GetView@ViewElement@Art@@QEAAAEBV?$TWeakPtr@VView@Art@@@Ofc@@XZ; Art::ViewElement::GetView(void)
0x180302006  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x180302009  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18030200e  mov     [rsp+210h+var_1B8], rax
0x180302013  mov     rcx, [r15+178h]; struct Ofc::CProxyPtrImpl *
0x18030201a  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18030201f  mov     [rbp+110h+var_180], rax
0x180302023  mov     rcx, [r15+180h]; struct Ofc::CProxyPtrImpl *
0x18030202a  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18030202f  mov     rcx, rax; this
0x180302032  mov     [rbp+110h+var_190], rax
0x180302036  xor     r14d, r14d
0x180302039  cmp     [rax+10h], r14
0x18030203d  jz      loc_1803025A0
0x180302043  mov     eax, [r15+188h]
0x18030204a  lea     edx, [r14+2]
0x18030204e  lea     r12d, [r14+1]
0x180302052  test    eax, eax
0x180302054  jnz     loc_18030212A
0x18030205a  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18030205f  mov     r8, rax
0x180302062  mov     rcx, [rax]
0x180302065  mov     rax, [rcx+50h]
0x180302069  lea     rdx, [rsp+210h+var_1D0]
0x18030206e  mov     rcx, r8
0x180302071  call    cs:__guard_dispatch_icall_fptr
0x180302077  mov     rcx, [rax]
0x18030207a  movzx   ebx, word ptr [rcx]
0x18030207d  mov     rcx, [rsp+210h+var_1D0]
0x180302082  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x180302086  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x18030208b  lea     rdi, [r15+190h]
0x180302092  call    cs:__imp_MsoGetHinstIntl
0x180302098  mov     r8d, 0F40102FEh
0x18030209e  mov     rdx, rax
0x1803020a1  mov     rcx, rdi
0x1803020a4  call    sub_1801518A0
0x1803020a9  test    bx, bx
0x1803020ac  jz      short loc_18030210C
0x1803020ae  mov     rcx, [rbp+110h+var_190]; this
0x1803020b2  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803020b7  mov     r8, rax
0x1803020ba  mov     rcx, [rax]
0x1803020bd  mov     rax, [rcx+50h]
0x1803020c1  lea     rdx, [rsp+210h+var_1D0]
0x1803020c6  mov     rcx, r8
0x1803020c9  call    cs:__guard_dispatch_icall_fptr
0x1803020cf  xor     r9d, r9d; bool
0x1803020d2  mov     r8, [rax]; wchar_t *
0x1803020d5  lea     rdx, ?PLACEHOLDER0@Ofc@@3QB_WB; "^0"
0x1803020dc  mov     rcx, rdi; this
0x1803020df  call    ?Replace@CStr@Ofc@@QEAAXPEB_W0_N@Z; Ofc::CStr::Replace(wchar_t const *,wchar_t const *,bool)
0x1803020e4  mov     rcx, [rsp+210h+var_1D0]
0x1803020e9  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x1803020ed  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1803020f2  mov     rcx, rdi; this
0x1803020f5  call    ?FRemoveAppendedAutoCaptionDisclaimer@Art@@YA_NAEAVCVarStr@Ofc@@@Z; Art::FRemoveAppendedAutoCaptionDisclaimer(Ofc::CVarStr &)
0x1803020fa  mov     edx, 0F40102FDh; struct Ofc::CVarStr *
0x1803020ff  mov     rcx, rdi; this
0x180302102  call    ?FRemoveSubString@Art@@YA_NAEAVCVarStr@Ofc@@H@Z; Art::FRemoveSubString(Ofc::CVarStr &,int)
0x180302107  jmp     loc_1803021B8
0x18030210c  xor     r9d, r9d; bool
0x18030210f  lea     r8, word_180B454F0; wchar_t *
0x180302116  lea     rdx, ?PLACEHOLDER0@Ofc@@3QB_WB; "^0"
0x18030211d  mov     rcx, rdi; this
0x180302120  call    ?Replace@CStr@Ofc@@QEAAXPEB_W0_N@Z; Ofc::CStr::Replace(wchar_t const *,wchar_t const *,bool)
0x180302125  jmp     loc_1803021B8
0x18030212a  cmp     eax, r12d
0x18030212d  jnz     short loc_180302199
0x18030212f  lea     rbx, [r15+190h]
0x180302136  call    cs:__imp_MsoGetHinstIntl
0x18030213c  mov     r8d, 0F40102FEh
0x180302142  mov     rdx, rax
0x180302145  mov     rcx, rbx
0x180302148  call    sub_1801518A0
0x18030214d  lea     rax, word_180A9C374
0x180302154  mov     [rsp+210h+var_1D0], rax
0x180302159  call    cs:__imp_MsoGetHinstIntl
0x18030215f  mov     r8d, 0F40102F4h
0x180302165  mov     rdx, rax
0x180302168  lea     rcx, [rsp+210h+var_1D0]
0x18030216d  call    sub_1801518A0
0x180302172  xor     r9d, r9d; bool
0x180302175  mov     r8, [rsp+210h+var_1D0]; wchar_t *
0x18030217a  lea     rdx, ?PLACEHOLDER0@Ofc@@3QB_WB; "^0"
0x180302181  mov     rcx, rbx; this
0x180302184  call    ?Replace@CStr@Ofc@@QEAAXPEB_W0_N@Z; Ofc::CStr::Replace(wchar_t const *,wchar_t const *,bool)
0x180302189  mov     rcx, [rsp+210h+var_1D0]
0x18030218e  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x180302192  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x180302197  jmp     short loc_1803021B8
0x180302199  cmp     eax, edx
0x18030219b  jnz     short loc_1803021B8
0x18030219d  call    cs:__imp_MsoGetHinstIntl
0x1803021a3  lea     rcx, [r15+190h]
0x1803021aa  mov     r8d, 0F40102F5h
0x1803021b0  mov     rdx, rax
0x1803021b3  call    sub_1801518A0
0x1803021b8  lea     rcx, [rbp+110h+var_100]; this
0x1803021bc  call    ??0Info@View@Art@@QEAA@XZ; Art::View::Info::Info(void)
0x1803021c1  nop
0x1803021c2  mov     rcx, [rsp+210h+var_1B8]; this
0x1803021c7  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803021cc  lea     rdx, [rax+28h]
0x1803021d0  lea     rcx, [rbp+110h+var_100]
0x1803021d4  call    ??4Info@View@Art@@QEAAAEAU012@AEBU012@@Z; Art::View::Info::operator=(Art::View::Info const &)
0x1803021d9  lea     rcx, [rsp+210h+var_1B8]
0x1803021de  call    ?GetViewPixelToHostEMUScale@Art@@YANAEBV?$TSharedPtr@$$CBVView@Art@@@Ofc@@@Z; Art::GetViewPixelToHostEMUScale(Ofc::TSharedPtr<Art::View const> const &)
0x1803021e3  movaps  xmm6, xmm0
0x1803021e6  call    ?FAltTextBarFeedbackUIEnabled@Art@@YA_NXZ; Art::FAltTextBarFeedbackUIEnabled(void)
0x1803021eb  mov     r13b, al
0x1803021ee  mov     rdi, r14
0x1803021f1  mov     [rsp+210h+var_1D0], r14
0x1803021f6  test    al, al
0x1803021f8  jz      short loc_18030225A
0x1803021fa  mov     rcx, [rsp+210h+var_1B8]; this
0x1803021ff  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180302204  lea     r8, [rax+0A0h]
0x18030220b  lea     rcx, [r15+1D0h]
0x180302212  movaps  xmm3, xmm6
0x180302215  lea     rdx, [rbp+110h+var_188]
0x180302219  call    ?CreateUIEffects@AltTextBarFeedbackUIContainer@Art@@QEAA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@AEBV?$TConvertibleDPI2@M@Gfx@@N@Z; Art::AltTextBarFeedbackUIContainer::CreateUIEffects(Gfx::TConvertibleDPI2<float> const &,double)
0x18030221e  mov     rdi, [rax]
0x180302221  mov     [rax], r14
0x180302224  mov     [rsp+210h+var_1D0], rdi
0x180302229  mov     rcx, [rbp+110h+var_188]
0x18030222d  test    rcx, rcx
0x180302230  jz      short loc_18030223F
0x180302232  mov     rax, [rcx]
0x180302235  mov     rax, [rax+8]
0x180302239  call    cs:__guard_dispatch_icall_fptr
0x18030223f  movsd   xmm0, qword ptr [r15+1F0h]
0x180302248  subsd   xmm0, qword ptr [r15+1B8h]
0x180302251  movsd   qword ptr [r15+1A8h], xmm0
0x18030225a  mov     rax, [r15+190h]
0x180302261  movdqa  xmm0, cs:__xmm@3f8000003f8000003f8000003f800000
0x180302269  movups  [rbp+110h+var_178], xmm0
0x18030226d  lea     rsi, [r15+198h]
0x180302274  mov     [rsp+210h+var_1E0], r14b
0x180302279  mov     qword ptr [rsp+210h+var_1E8], rax
0x18030227e  lea     rax, [rbp+110h+var_178]
0x180302282  mov     [rsp+210h+var_1F0], rax
0x180302287  mov     r9, rsi
0x18030228a  lea     r8, [rbp+110h+var_100]
0x18030228e  movaps  xmm1, xmm6
0x180302291  lea     rcx, [rbp+110h+var_188]
0x180302295  call    ?CreateAltTextBuilder@AltTextSelectionBarViewElement@Art@@CA?AV?$TOwnerPtr@VTextBuilder@Art@@@Ofc@@NAEBUInfo@View@2@AEBURect@GEL@@AEBUColor@8@PEB_W_N@Z; Art::AltTextSelectionBarViewElement::CreateAltTextBuilder(double,Art::View::Info const &,GEL::Rect const &,GEL::Color const &,wchar_t const *,bool)
0x18030229a  nop
0x18030229b  lea     rcx, [rsp+210h+var_1A0]
0x1803022a0  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x1803022a6  nop
0x1803022a7  mov     rbx, [rsp+210h+var_1A0]
0x1803022ac  mov     rax, [rbx]
0x1803022af  mov     r14, [rax+90h]
0x1803022b6  movsd   xmm2, qword ptr [rsi]
0x1803022ba  mov     rsi, [rbp+110h+var_188]
0x1803022be  mov     rdx, rsi
0x1803022c1  lea     rcx, [rsp+210h+var_1C8]
0x1803022c6  call    ?GetTextBuilderEffects@Art@@YA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@AEBVTextBuilder@1@N@Z; Art::GetTextBuilderEffects(Art::TextBuilder const &,double)
0x1803022cb  nop
0x1803022cc  mov     rdx, [rax]
0x1803022cf  mov     rcx, rbx
0x1803022d2  mov     rax, r14
0x1803022d5  call    cs:__guard_dispatch_icall_fptr
0x1803022db  nop
0x1803022dc  mov     rcx, [rsp+210h+var_1C8]
0x1803022e1  xor     ebx, ebx
0x1803022e3  test    rcx, rcx
0x1803022e6  jz      short loc_1803022F5
0x1803022e8  mov     rax, [rcx]
0x1803022eb  mov     rax, [rax+8]
0x1803022ef  call    cs:__guard_dispatch_icall_fptr
0x1803022f5  test    r13b, r13b
0x1803022f8  jz      short loc_18030232D
0x1803022fa  mov     rcx, rsi; this
0x1803022fd  call    ?GetTextViewLine@TextBuilder@Art@@QEBAPEBUTextViewLine@2@K@Z; Art::TextBuilder::GetTextViewLine(ulong)
0x180302302  mov     rcx, rax
0x180302305  test    rax, rax
0x180302308  jz      short loc_180302323
0x18030230a  mov     rax, [r15+190h]
0x180302311  mov     eax, [rax-4]
0x180302314  cdq
0x180302315  mov     r8d, 2
0x18030231b  idiv    r8d
0x18030231e  cmp     [rcx+34h], eax
0x180302321  jle     short loc_180302326
0x180302323  mov     r12b, bl
0x180302326  mov     [r15+1C0h], r12b
0x18030232d  mov     [rsp+210h+var_1A8], rbx
0x180302332  lea     rdx, [r15+128h]
0x180302339  lea     rcx, [rsp+210h+var_1C8]
0x18030233e  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x180302344  mov     r12, [rax]
0x180302347  mov     [rax], rbx
0x18030234a  mov     qword ptr [rbp+110h+var_178], r12
0x18030234e  mov     rcx, [rsp+210h+var_1C8]
0x180302353  test    rcx, rcx
0x180302356  jz      short loc_180302365
0x180302358  mov     rax, [rcx]
0x18030235b  mov     rax, [rax+8]
0x18030235f  call    cs:__guard_dispatch_icall_fptr
0x180302365  lea     rcx, [rsp+210h+var_1B0]
0x18030236a  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ; Gfx::IFigureStyle::Create(void)
0x180302370  mov     rcx, [rsp+210h+var_1B0]
0x180302375  mov     rax, [rcx]
0x180302378  lea     rdx, ?c_defaultColor@AltTextSelectionBarViewElement@Art@@0UColor@GEL@@B; GEL::Color const Art::AltTextSelectionBarViewElement::c_defaultColor
0x18030237f  mov     rax, [rax+18h]
0x180302383  call    cs:__guard_dispatch_icall_fptr
0x180302389  xor     r9d, r9d
0x18030238c  mov     r8, [rsp+210h+var_1B0]
0x180302391  mov     rdx, r12
0x180302394  lea     rcx, [rsp+210h+var_198]
0x180302399  call    cs:__imp_?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z; Gfx::IFigureShapeBuilder::Create(GEL::IPath const &,Gfx::IFigureStyle *,Gfx::IEffectParams const *)
0x18030239f  mov     rcx, [rsp+210h+var_198]
0x1803023a4  mov     rax, [rcx]
0x1803023a7  xor     r8d, r8d
0x1803023aa  lea     rdx, [rsp+210h+var_1A8]
0x1803023af  mov     rax, [rax+1A8h]
0x1803023b6  call    cs:__guard_dispatch_icall_fptr
0x1803023bc  test    eax, eax
0x1803023be  jnz     loc_1803024F0
0x1803023c4  lea     rcx, [rsp+210h+var_1C0]
0x1803023c9  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x1803023cf  mov     rcx, [rsp+210h+var_1C0]
0x1803023d4  mov     rax, [rcx]
0x1803023d7  mov     rdx, [rsp+210h+var_1A8]
0x1803023dc  mov     rax, [rax+90h]
0x1803023e3  call    cs:__guard_dispatch_icall_fptr
0x1803023e9  mov     rcx, [rsp+210h+var_1C0]
0x1803023ee  mov     rax, [rcx]
0x1803023f1  mov     rdx, [rsp+210h+var_1A0]
0x1803023f6  mov     rax, [rax+90h]
0x1803023fd  call    cs:__guard_dispatch_icall_fptr
0x180302403  test    r13b, r13b
0x180302406  jz      short loc_18030247A
0x180302408  test    rdi, rdi
0x18030240b  jz      short loc_18030247A
0x18030240d  movups  xmm2, xmmword ptr [r15+1F0h]
0x180302415  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x18030241d  movups  [rbp+110h+var_168], xmm0
0x180302421  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x180302429  movups  [rbp+110h+var_158], xmm1
0x18030242d  movups  [rbp+110h+var_148], xmm2
0x180302431  mov     rbx, [rsp+210h+var_1C0]
0x180302436  mov     rax, [rbx]
0x180302439  mov     r14, [rax+90h]
0x180302440  lea     r8, [rbp+110h+var_168]
0x180302444  mov     rdx, rdi
0x180302447  lea     rcx, [rsp+210h+var_1C8]
0x18030244c  call    cs:__imp_?Create@IEffectTransform@GEL@@SA?AV?$TCntPtr@UIEffectTransform@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@@Z; GEL::IEffectTransform::Create(GEL::IEffect const &,Math::TAffine3x3<double> const &)
0x180302452  nop
0x180302453  mov     rdx, [rax]
0x180302456  mov     rcx, rbx
0x180302459  mov     rax, r14
0x18030245c  call    cs:__guard_dispatch_icall_fptr
0x180302462  nop
0x180302463  mov     rcx, [rsp+210h+var_1C8]
0x180302468  test    rcx, rcx
0x18030246b  jz      short loc_18030247A
0x18030246d  mov     rax, [rcx]
0x180302470  mov     rax, [rax+8]
0x180302474  call    cs:__guard_dispatch_icall_fptr
0x18030247a  lea     rdx, [r15+48h]
0x18030247e  lea     rcx, [rbp+110h+var_138]
0x180302482  call    ?GetGelTransform@Art@@YA?AU?$TAffine3x3@N@Math@@AEBVTransform2D@1@@Z; Art::GetGelTransform(Art::Transform2D const &)
0x180302487  mov     rax, [r15]
0x18030248a  mov     rcx, r15
0x18030248d  mov     rax, [rax+0A0h]
0x180302494  call    cs:__guard_dispatch_icall_fptr
0x18030249a  mov     r9d, eax
0x18030249d  lea     r8, [rbp+110h+var_138]
0x1803024a1  mov     rdx, [rsp+210h+var_1C0]
0x1803024a6  lea     rcx, [rsp+210h+var_1C8]
0x1803024ab  call    cs:__imp_?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@W4RenderingPolicy@Gfx@@@Z; GEL::ITopLevelEffect::Create(GEL::IEffect const &,Math::TAffine3x3<double> const &,Gfx::RenderingPolicy)
0x1803024b1  mov     rdx, [rax]; struct GEL::ITopLevelEffect *
  ... truncated ...
```
