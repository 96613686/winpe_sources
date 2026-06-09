# Art::AltTextSelectionBarViewElement::RenderBar(GEL::Color const &)

- ea: `0x1802ce130`
- end: `0x1802ce7a2`
- name: `?RenderBar@AltTextSelectionBarViewElement@Art@@AEAAXAEBUColor@GEL@@@Z`
- size: `1650`
- prototype: `void __fastcall(Art::AltTextSelectionBarViewElement *__hidden this, const struct GEL::Color *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config`

## callers

- `0x1802cd39c`

## callees

- `0x180024f50`
- `0x180037370`
- `0x180038180`
- `0x180065990`
- `0x180070fe0`
- `0x1800713c0`
- `0x180071720`
- `0x1800b2360`
- `0x180185e40`
- `0x1801afa90`
- `0x1801bd760`
- `0x1801c0940`
- `0x1801fa040`
- `0x1801fb5f0`
- `0x18027a298`
- `0x1802cdbb8`
- `0x1802ce130`
- `0x18030a588`
- `0x18030b2f0`
- `0x1803d1a78`
- `0x1803d3280`
- `0x180653700`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`

## import_xrefs

- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x1802ce54d`
- `gfx!?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z` at `0x1802ce54d`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x1802ce51e`
- `gfx!?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ` at `0x1802ce51e`
- `gfx!?Create@IEffectTransform@GEL@@SA?AV?$TCntPtr@UIEffectTransform@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x1802ce600`
- `gfx!?Create@IEffectTransform@GEL@@SA?AV?$TCntPtr@UIEffectTransform@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@@Z` at `0x1802ce600`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@W4RenderingPolicy@Gfx@@@Z` at `0x1802ce65f`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@W4RenderingPolicy@Gfx@@@Z` at `0x1802ce65f`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1802ce448`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1802ce57d`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1802ce448`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1802ce57d`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x1802ce4f2`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x1802ce4f2`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802ce23a`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802ce2de`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802ce301`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802ce345`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802ce23a`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802ce2de`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802ce301`
- `Mso30Win32Client!__imp_MsoGetHinstIntl` at `0x1802ce345`

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
          sub_1801AFA90((char *)this + 400, HinstIntl, 4093707005LL);
          v44 = (wchar_t *)&word_180A77374;
          v20 = MsoGetHinstIntl(v19, v18);
          sub_1801AFA90(&v44, v20, 4093706995LL);
          Ofc::CStr::Replace((wchar_t **)this + 50, L"^0", v44, 0);
          Ofc::XString::Release((Ofc::XString *)(v44 - 6));
        }
        else if ( v6 == 2 )
        {
          v21 = MsoGetHinstIntl(v5, 2);
          sub_1801AFA90((char *)this + 400, v21, 4093706996LL);
        }
      }
      else
      {
        Checked = Ofc::CProxyPtrImpl::GetChecked(v5);
        v9 = **(_WORD **)(*(__int64 (__fastcall **)(void *, wchar_t **))(*(_QWORD *)Checked + 80LL))(Checked, &v44);
        Ofc::XString::Release((Ofc::XString *)(v44 - 6));
        v12 = MsoGetHinstIntl(v11, v10);
        sub_1801AFA90((char *)this + 400, v12, 4093707005LL);
        if ( v9 )
        {
          v13 = Ofc::CProxyPtrImpl::GetChecked(v52);
          v14 = (const wchar_t **)(*(__int64 (__fastcall **)(void *, wchar_t **))(*(_QWORD *)v13 + 80LL))(v13, &v44);
          Ofc::CStr::Replace((wchar_t **)this + 50, L"^0", *v14, 0);
          Ofc::XString::Release((Ofc::XString *)(v44 - 6));
          Art::FRemoveAppendedAutoCaptionDisclaimer((wchar_t **)this + 50, v15);
          Art::FRemoveSubString((wchar_t **)this + 50, (struct Ofc::CVarStr *)0xF40102FCLL, v16);
        }
        else
        {
          Ofc::CStr::Replace((wchar_t **)this + 50, L"^0", &word_180B89A10, 0);
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
        v42 = (*(__int64 (__fastcall **)(Art::AltTextSelectionBarViewElement *))(*(_QWORD *)this + 168LL))(this);
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
0x1802ce130  mov     rax, rsp
0x1802ce133  mov     [rax+10h], rbx
0x1802ce137  mov     [rax+18h], rsi
0x1802ce13b  mov     [rax+20h], rdi
0x1802ce13f  push    rbp
0x1802ce140  push    r12
0x1802ce142  push    r13
0x1802ce144  push    r14
0x1802ce146  push    r15
0x1802ce148  lea     rbp, [rax-118h]
0x1802ce14f  sub     rsp, 1F0h
0x1802ce156  movaps  xmmword ptr [rax-38h], xmm6
0x1802ce15a  mov     rax, cs:__security_cookie
0x1802ce161  xor     rax, rsp
0x1802ce164  mov     [rbp+110h+var_40], rax
0x1802ce16b  mov     r15, rcx
0x1802ce16e  movsd   xmm1, qword ptr [rcx+140h]
0x1802ce176  subsd   xmm1, qword ptr [rcx+130h]
0x1802ce17e  movaps  xmm0, xmm1
0x1802ce181  addsd   xmm0, xmm1
0x1802ce185  comisd  xmm0, qword ptr [rcx+150h]
0x1802ce18d  ja      loc_1802CE76D
0x1802ce193  mulsd   xmm1, qword ptr [rcx+1C8h]
0x1802ce19b  comisd  xmm1, qword ptr [rcx+148h]
0x1802ce1a3  ja      loc_1802CE76D
0x1802ce1a9  call    ?GetView@ViewElement@Art@@QEAAAEBV?$TWeakPtr@VView@Art@@@Ofc@@XZ; Art::ViewElement::GetView(void)
0x1802ce1ae  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x1802ce1b1  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1802ce1b6  mov     [rsp+210h+var_1B8], rax
0x1802ce1bb  mov     rcx, [r15+178h]; struct Ofc::CProxyPtrImpl *
0x1802ce1c2  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1802ce1c7  mov     [rbp+110h+var_180], rax
0x1802ce1cb  mov     rcx, [r15+180h]; struct Ofc::CProxyPtrImpl *
0x1802ce1d2  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1802ce1d7  mov     rcx, rax; this
0x1802ce1da  mov     [rbp+110h+var_190], rax
0x1802ce1de  xor     r14d, r14d
0x1802ce1e1  cmp     [rax+10h], r14
0x1802ce1e5  jz      loc_1802CE751
0x1802ce1eb  mov     eax, [r15+188h]
0x1802ce1f2  lea     edx, [r14+2]
0x1802ce1f6  lea     r12d, [r14+1]
0x1802ce1fa  test    eax, eax
0x1802ce1fc  jnz     loc_1802CE2D2
0x1802ce202  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1802ce207  mov     r8, rax
0x1802ce20a  mov     rcx, [rax]
0x1802ce20d  mov     rax, [rcx+50h]
0x1802ce211  lea     rdx, [rsp+210h+var_1D0]
0x1802ce216  mov     rcx, r8
0x1802ce219  call    cs:__guard_dispatch_icall_fptr
0x1802ce21f  mov     rcx, [rax]
0x1802ce222  movzx   ebx, word ptr [rcx]
0x1802ce225  mov     rcx, [rsp+210h+var_1D0]
0x1802ce22a  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x1802ce22e  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1802ce233  lea     rdi, [r15+190h]
0x1802ce23a  call    cs:__imp_MsoGetHinstIntl
0x1802ce240  mov     r8d, 0F40102FDh
0x1802ce246  mov     rdx, rax
0x1802ce249  mov     rcx, rdi
0x1802ce24c  call    sub_1801AFA90
0x1802ce251  test    bx, bx
0x1802ce254  jz      short loc_1802CE2B4
0x1802ce256  mov     rcx, [rbp+110h+var_190]; this
0x1802ce25a  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1802ce25f  mov     r8, rax
0x1802ce262  mov     rcx, [rax]
0x1802ce265  mov     rax, [rcx+50h]
0x1802ce269  lea     rdx, [rsp+210h+var_1D0]
0x1802ce26e  mov     rcx, r8
0x1802ce271  call    cs:__guard_dispatch_icall_fptr
0x1802ce277  xor     r9d, r9d; bool
0x1802ce27a  mov     r8, [rax]; wchar_t *
0x1802ce27d  lea     rdx, ?PLACEHOLDER0@Ofc@@3QB_WB; "^0"
0x1802ce284  mov     rcx, rdi; this
0x1802ce287  call    ?Replace@CStr@Ofc@@QEAAXPEB_W0_N@Z; Ofc::CStr::Replace(wchar_t const *,wchar_t const *,bool)
0x1802ce28c  mov     rcx, [rsp+210h+var_1D0]
0x1802ce291  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x1802ce295  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1802ce29a  mov     rcx, rdi; this
0x1802ce29d  call    ?FRemoveAppendedAutoCaptionDisclaimer@Art@@YA_NAEAVCVarStr@Ofc@@@Z; Art::FRemoveAppendedAutoCaptionDisclaimer(Ofc::CVarStr &)
0x1802ce2a2  mov     edx, 0F40102FCh; struct Ofc::CVarStr *
0x1802ce2a7  mov     rcx, rdi; this
0x1802ce2aa  call    ?FRemoveSubString@Art@@YA_NAEAVCVarStr@Ofc@@H@Z; Art::FRemoveSubString(Ofc::CVarStr &,int)
0x1802ce2af  jmp     loc_1802CE360
0x1802ce2b4  xor     r9d, r9d; bool
0x1802ce2b7  lea     r8, word_180B89A10; wchar_t *
0x1802ce2be  lea     rdx, ?PLACEHOLDER0@Ofc@@3QB_WB; "^0"
0x1802ce2c5  mov     rcx, rdi; this
0x1802ce2c8  call    ?Replace@CStr@Ofc@@QEAAXPEB_W0_N@Z; Ofc::CStr::Replace(wchar_t const *,wchar_t const *,bool)
0x1802ce2cd  jmp     loc_1802CE360
0x1802ce2d2  cmp     eax, r12d
0x1802ce2d5  jnz     short loc_1802CE341
0x1802ce2d7  lea     rbx, [r15+190h]
0x1802ce2de  call    cs:__imp_MsoGetHinstIntl
0x1802ce2e4  mov     r8d, 0F40102FDh
0x1802ce2ea  mov     rdx, rax
0x1802ce2ed  mov     rcx, rbx
0x1802ce2f0  call    sub_1801AFA90
0x1802ce2f5  lea     rax, word_180A77374
0x1802ce2fc  mov     [rsp+210h+var_1D0], rax
0x1802ce301  call    cs:__imp_MsoGetHinstIntl
0x1802ce307  mov     r8d, 0F40102F3h
0x1802ce30d  mov     rdx, rax
0x1802ce310  lea     rcx, [rsp+210h+var_1D0]
0x1802ce315  call    sub_1801AFA90
0x1802ce31a  xor     r9d, r9d; bool
0x1802ce31d  mov     r8, [rsp+210h+var_1D0]; wchar_t *
0x1802ce322  lea     rdx, ?PLACEHOLDER0@Ofc@@3QB_WB; "^0"
0x1802ce329  mov     rcx, rbx; this
0x1802ce32c  call    ?Replace@CStr@Ofc@@QEAAXPEB_W0_N@Z; Ofc::CStr::Replace(wchar_t const *,wchar_t const *,bool)
0x1802ce331  mov     rcx, [rsp+210h+var_1D0]
0x1802ce336  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x1802ce33a  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1802ce33f  jmp     short loc_1802CE360
0x1802ce341  cmp     eax, edx
0x1802ce343  jnz     short loc_1802CE360
0x1802ce345  call    cs:__imp_MsoGetHinstIntl
0x1802ce34b  lea     rcx, [r15+190h]
0x1802ce352  mov     r8d, 0F40102F4h
0x1802ce358  mov     rdx, rax
0x1802ce35b  call    sub_1801AFA90
0x1802ce360  lea     rcx, [rbp+110h+var_100]; this
0x1802ce364  call    ??0Info@View@Art@@QEAA@XZ; Art::View::Info::Info(void)
0x1802ce369  nop
0x1802ce36a  mov     rcx, [rsp+210h+var_1B8]; this
0x1802ce36f  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1802ce374  lea     rdx, [rax+28h]
0x1802ce378  lea     rcx, [rbp+110h+var_100]
0x1802ce37c  call    ??4Info@View@Art@@QEAAAEAU012@AEBU012@@Z; Art::View::Info::operator=(Art::View::Info const &)
0x1802ce381  lea     rcx, [rsp+210h+var_1B8]
0x1802ce386  call    ?GetViewPixelToHostEMUScale@Art@@YANAEBV?$TSharedPtr@$$CBVView@Art@@@Ofc@@@Z; Art::GetViewPixelToHostEMUScale(Ofc::TSharedPtr<Art::View const> const &)
0x1802ce38b  movaps  xmm6, xmm0
0x1802ce38e  call    ?FAltTextBarFeedbackUIEnabled@Art@@YA_NXZ; Art::FAltTextBarFeedbackUIEnabled(void)
0x1802ce393  mov     r13b, al
0x1802ce396  mov     rdi, r14
0x1802ce399  mov     [rsp+210h+var_1D0], r14
0x1802ce39e  test    al, al
0x1802ce3a0  jz      short loc_1802CE402
0x1802ce3a2  mov     rcx, [rsp+210h+var_1B8]; this
0x1802ce3a7  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1802ce3ac  lea     r8, [rax+0A0h]
0x1802ce3b3  lea     rcx, [r15+1D0h]
0x1802ce3ba  movaps  xmm3, xmm6
0x1802ce3bd  lea     rdx, [rbp+110h+var_188]
0x1802ce3c1  call    ?CreateUIEffects@AltTextBarFeedbackUIContainer@Art@@QEAA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@AEBV?$TConvertibleDPI2@M@Gfx@@N@Z; Art::AltTextBarFeedbackUIContainer::CreateUIEffects(Gfx::TConvertibleDPI2<float> const &,double)
0x1802ce3c6  mov     rdi, [rax]
0x1802ce3c9  mov     [rax], r14
0x1802ce3cc  mov     [rsp+210h+var_1D0], rdi
0x1802ce3d1  mov     rcx, [rbp+110h+var_188]
0x1802ce3d5  test    rcx, rcx
0x1802ce3d8  jz      short loc_1802CE3E7
0x1802ce3da  mov     rax, [rcx]
0x1802ce3dd  mov     rax, [rax+8]
0x1802ce3e1  call    cs:__guard_dispatch_icall_fptr
0x1802ce3e7  movsd   xmm0, qword ptr [r15+1F0h]
0x1802ce3f0  subsd   xmm0, qword ptr [r15+1B8h]
0x1802ce3f9  movsd   qword ptr [r15+1A8h], xmm0
0x1802ce402  mov     rax, [r15+190h]
0x1802ce409  movdqa  xmm0, cs:__xmm@3f8000003f8000003f8000003f800000
0x1802ce411  movups  [rbp+110h+var_178], xmm0
0x1802ce415  lea     rsi, [r15+198h]
0x1802ce41c  mov     [rsp+210h+var_1E0], r14b
0x1802ce421  mov     qword ptr [rsp+210h+var_1E8], rax
0x1802ce426  lea     rax, [rbp+110h+var_178]
0x1802ce42a  mov     [rsp+210h+var_1F0], rax
0x1802ce42f  mov     r9, rsi
0x1802ce432  lea     r8, [rbp+110h+var_100]
0x1802ce436  movaps  xmm1, xmm6
0x1802ce439  lea     rcx, [rbp+110h+var_188]
0x1802ce43d  call    ?CreateAltTextBuilder@AltTextSelectionBarViewElement@Art@@CA?AV?$TOwnerPtr@VTextBuilder@Art@@@Ofc@@NAEBUInfo@View@2@AEBURect@GEL@@AEBUColor@8@PEB_W_N@Z; Art::AltTextSelectionBarViewElement::CreateAltTextBuilder(double,Art::View::Info const &,GEL::Rect const &,GEL::Color const &,wchar_t const *,bool)
0x1802ce442  nop
0x1802ce443  lea     rcx, [rsp+210h+var_1A0]
0x1802ce448  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x1802ce44e  nop
0x1802ce44f  mov     rbx, [rsp+210h+var_1A0]
0x1802ce454  mov     rax, [rbx]
0x1802ce457  mov     r14, [rax+90h]
0x1802ce45e  movsd   xmm2, qword ptr [rsi]
0x1802ce462  mov     rsi, [rbp+110h+var_188]
0x1802ce466  mov     rdx, rsi
0x1802ce469  lea     rcx, [rsp+210h+var_1C8]
0x1802ce46e  call    ?GetTextBuilderEffects@Art@@YA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@AEBVTextBuilder@1@N@Z; Art::GetTextBuilderEffects(Art::TextBuilder const &,double)
0x1802ce473  nop
0x1802ce474  nop     dword ptr [rax+00h]
0x1802ce478  nop     dword ptr [rax+rax+00000000h]
0x1802ce480  mov     rdx, [rax]
0x1802ce483  mov     rcx, rbx
0x1802ce486  mov     rax, r14
0x1802ce489  call    cs:__guard_dispatch_icall_fptr
0x1802ce48f  nop
0x1802ce490  mov     rcx, [rsp+210h+var_1C8]
0x1802ce495  xor     ebx, ebx
0x1802ce497  test    rcx, rcx
0x1802ce49a  jz      short loc_1802CE4A9
0x1802ce49c  mov     rax, [rcx]
0x1802ce49f  mov     rax, [rax+8]
0x1802ce4a3  call    cs:__guard_dispatch_icall_fptr
0x1802ce4a9  test    r13b, r13b
0x1802ce4ac  jz      short loc_1802CE4E1
0x1802ce4ae  mov     rcx, rsi; this
0x1802ce4b1  call    ?GetTextViewLine@TextBuilder@Art@@QEBAPEBUTextViewLine@2@K@Z; Art::TextBuilder::GetTextViewLine(ulong)
0x1802ce4b6  mov     rcx, rax
0x1802ce4b9  test    rax, rax
0x1802ce4bc  jz      short loc_1802CE4D7
0x1802ce4be  mov     rax, [r15+190h]
0x1802ce4c5  mov     eax, [rax-4]
0x1802ce4c8  cdq
0x1802ce4c9  mov     r8d, 2
0x1802ce4cf  idiv    r8d
0x1802ce4d2  cmp     [rcx+34h], eax
0x1802ce4d5  jle     short loc_1802CE4DA
0x1802ce4d7  mov     r12b, bl
0x1802ce4da  mov     [r15+1C0h], r12b
0x1802ce4e1  mov     [rsp+210h+var_1A8], rbx
0x1802ce4e6  lea     rdx, [r15+128h]
0x1802ce4ed  lea     rcx, [rsp+210h+var_1C8]
0x1802ce4f2  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x1802ce4f8  mov     r12, [rax]
0x1802ce4fb  mov     [rax], rbx
0x1802ce4fe  mov     qword ptr [rbp+110h+var_178], r12
0x1802ce502  mov     rcx, [rsp+210h+var_1C8]
0x1802ce507  test    rcx, rcx
0x1802ce50a  jz      short loc_1802CE519
0x1802ce50c  mov     rax, [rcx]
0x1802ce50f  mov     rax, [rax+8]
0x1802ce513  call    cs:__guard_dispatch_icall_fptr
0x1802ce519  lea     rcx, [rsp+210h+var_1B0]
0x1802ce51e  call    cs:__imp_?Create@IFigureStyle@Gfx@@SA?AV?$TCntPtr@UIFigureStyle@Gfx@@@Ofc@@XZ; Gfx::IFigureStyle::Create(void)
0x1802ce524  mov     rcx, [rsp+210h+var_1B0]
0x1802ce529  mov     rax, [rcx]
0x1802ce52c  lea     rdx, ?c_defaultColor@AltTextSelectionBarViewElement@Art@@0UColor@GEL@@B; GEL::Color const Art::AltTextSelectionBarViewElement::c_defaultColor
0x1802ce533  mov     rax, [rax+18h]
0x1802ce537  call    cs:__guard_dispatch_icall_fptr
0x1802ce53d  xor     r9d, r9d
0x1802ce540  mov     r8, [rsp+210h+var_1B0]
0x1802ce545  mov     rdx, r12
0x1802ce548  lea     rcx, [rsp+210h+var_198]
0x1802ce54d  call    cs:__imp_?Create@IFigureShapeBuilder@Gfx@@SA?AV?$TCntPtr@UIFigureShapeBuilder@Gfx@@@Ofc@@AEBUIPath@GEL@@PEAUIFigureStyle@2@PEBUIEffectParams@2@@Z; Gfx::IFigureShapeBuilder::Create(GEL::IPath const &,Gfx::IFigureStyle *,Gfx::IEffectParams const *)
0x1802ce553  mov     rcx, [rsp+210h+var_198]
0x1802ce558  mov     rax, [rcx]
0x1802ce55b  xor     r8d, r8d
0x1802ce55e  lea     rdx, [rsp+210h+var_1A8]
0x1802ce563  mov     rax, [rax+1A8h]
0x1802ce56a  call    cs:__guard_dispatch_icall_fptr
0x1802ce570  test    eax, eax
0x1802ce572  jnz     loc_1802CE6A4
0x1802ce578  lea     rcx, [rsp+210h+var_1C0]
0x1802ce57d  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x1802ce583  mov     rcx, [rsp+210h+var_1C0]
0x1802ce588  mov     rax, [rcx]
0x1802ce58b  mov     rdx, [rsp+210h+var_1A8]
0x1802ce590  mov     rax, [rax+90h]
0x1802ce597  call    cs:__guard_dispatch_icall_fptr
0x1802ce59d  mov     rcx, [rsp+210h+var_1C0]
0x1802ce5a2  mov     rax, [rcx]
0x1802ce5a5  mov     rdx, [rsp+210h+var_1A0]
0x1802ce5aa  mov     rax, [rax+90h]
0x1802ce5b1  call    cs:__guard_dispatch_icall_fptr
0x1802ce5b7  test    r13b, r13b
0x1802ce5ba  jz      short loc_1802CE62E
0x1802ce5bc  test    rdi, rdi
0x1802ce5bf  jz      short loc_1802CE62E
0x1802ce5c1  movups  xmm2, xmmword ptr [r15+1F0h]
0x1802ce5c9  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1802ce5d1  movups  [rbp+110h+var_168], xmm0
0x1802ce5d5  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1802ce5dd  movups  [rbp+110h+var_158], xmm1
0x1802ce5e1  movups  [rbp+110h+var_148], xmm2
0x1802ce5e5  mov     rbx, [rsp+210h+var_1C0]
0x1802ce5ea  mov     rax, [rbx]
0x1802ce5ed  mov     r14, [rax+90h]
0x1802ce5f4  lea     r8, [rbp+110h+var_168]
0x1802ce5f8  mov     rdx, rdi
0x1802ce5fb  lea     rcx, [rsp+210h+var_1C8]
0x1802ce600  call    cs:__imp_?Create@IEffectTransform@GEL@@SA?AV?$TCntPtr@UIEffectTransform@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@@Z; GEL::IEffectTransform::Create(GEL::IEffect const &,Math::TAffine3x3<double> const &)
0x1802ce606  nop
0x1802ce607  mov     rdx, [rax]
0x1802ce60a  mov     rcx, rbx
0x1802ce60d  mov     rax, r14
0x1802ce610  call    cs:__guard_dispatch_icall_fptr
0x1802ce616  nop
0x1802ce617  mov     rcx, [rsp+210h+var_1C8]
0x1802ce61c  test    rcx, rcx
0x1802ce61f  jz      short loc_1802CE62E
0x1802ce621  mov     rax, [rcx]
0x1802ce624  mov     rax, [rax+8]
0x1802ce628  call    cs:__guard_dispatch_icall_fptr
0x1802ce62e  lea     rdx, [r15+48h]
0x1802ce632  lea     rcx, [rbp+110h+var_138]
0x1802ce636  call    ?GetGelTransform@Art@@YA?AU?$TAffine3x3@N@Math@@AEBVTransform2D@1@@Z; Art::GetGelTransform(Art::Transform2D const &)
0x1802ce63b  mov     rax, [r15]
0x1802ce63e  mov     rcx, r15
0x1802ce641  mov     rax, [rax+0A8h]
0x1802ce648  call    cs:__guard_dispatch_icall_fptr
0x1802ce64e  mov     r9d, eax
0x1802ce651  lea     r8, [rbp+110h+var_138]
0x1802ce655  mov     rdx, [rsp+210h+var_1C0]
0x1802ce65a  lea     rcx, [rsp+210h+var_1C8]
  ... truncated ...
```
