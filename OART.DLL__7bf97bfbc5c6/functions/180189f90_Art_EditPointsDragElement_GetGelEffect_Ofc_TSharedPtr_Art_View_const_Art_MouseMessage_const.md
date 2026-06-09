# Art::EditPointsDragElement::GetGelEffect(Ofc::TSharedPtr<Art::View> const &,Art::MouseMessage const &)

- ea: `0x180189f90`
- end: `0x18018a669`
- name: `?GetGelEffect@EditPointsDragElement@Art@@UEBA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBV?$TSharedPtr@VView@Art@@@4@AEBVMouseMessage@2@@Z`
- size: `1753`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18002e9cc`
- `0x1800428c8`
- `0x180071720`
- `0x1800b78a0`
- `0x1800d707c`
- `0x18010c0a4`
- `0x180132908`
- `0x180189eac`
- `0x180189f90`
- `0x18018a670`
- `0x18018a6c0`
- `0x18018ad30`
- `0x18018b778`
- `0x1801eba58`
- `0x1801f0b48`
- `0x1801f156c`
- `0x1801f1d88`
- `0x1801f1f20`
- `0x1801fa040`
- `0x1801fd780`
- `0x1805dcf30`
- `0x1806082d4`
- `0x1806a5084`

## import_xrefs

- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x18018a244`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x18018a244`
- `gfx!?EndFigure@PathBuilder@GEL@@QEAAAEAV12@W4FigureEnd@Path@Graphics@Mso@@@Z` at `0x18018a232`
- `gfx!?EndFigure@PathBuilder@GEL@@QEAAAEAV12@W4FigureEnd@Path@Graphics@Mso@@@Z` at `0x18018a232`
- `gfx!?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x18018a1ed`
- `gfx!?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x18018a209`
- `gfx!?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x18018a1ed`
- `gfx!?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x18018a209`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x18018a620`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x18018a620`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x18018a1ba`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x18018a1ba`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x18018a30c`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x18018a420`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x18018a30c`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x18018a420`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x18018a2e8`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x18018a364`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x18018a2e8`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x18018a364`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x18018a2a9`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x18018a2a9`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x180189fe4`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x180189fe4`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018a5b7`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18018a5b7`

## pseudocode

```c
_QWORD *__fastcall Art::EditPointsDragElement::GetGelEffect(
        Art::EditPointsDragElement *this,
        _QWORD *a2,
        Ofc::CProxyPtrImpl **a3,
        const struct Art::MouseMessage *a4)
{
  unsigned int *Checked; // rax
  const struct Art::Path2DTable *Paths; // rax
  Art *v9; // rbx
  __int64 v10; // rax
  _OWORD *v11; // rdx
  __m128d v12; // xmm7
  __m128d v13; // xmm6
  __m128d v14; // xmm6
  __int64 GelTransform; // rax
  __int128 v16; // xmm3
  __m128d v17; // xmm2
  _QWORD *v18; // r15
  __int64 v19; // rax
  int v20; // r8d
  unsigned int PrevSegmentIndex; // edi
  unsigned int NextSegmentIndex; // r13d
  int v23; // r8d
  unsigned int v24; // r14d
  __int64 v25; // rax
  __int64 v26; // rbx
  __int64 SegmentEndPoint; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  _QWORD *v32; // rax
  __int64 *v33; // rax
  __int64 v34; // r14
  Ofc::CProxyPtrImpl **v35; // r13
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rbx
  void (__fastcall *v39)(__int64, _QWORD); // rdi
  _QWORD *v40; // rax
  Ofc::CProxyPtrImpl **v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rbx
  void (__fastcall *v44)(__int64, _QWORD); // rdi
  _QWORD *v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rdi
  void (__fastcall *v51)(__int64, _QWORD, _OWORD *); // rbx
  _QWORD *TangentGelEffect; // rax
  void *v53; // rdx
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rdi
  void (__fastcall *v58)(__int64, _QWORD, _OWORD *); // rbx
  _QWORD *v59; // rax
  Mso::Memory *v61[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v62; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v63[3]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v64; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v65; // [rsp+70h] [rbp-98h]
  _QWORD v66[3]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v67[16]; // [rsp+90h] [rbp-78h] BYREF
  _OWORD v68[3]; // [rsp+A0h] [rbp-68h] BYREF
  _OWORD v69[2]; // [rsp+D0h] [rbp-38h] BYREF
  int v70; // [rsp+F0h] [rbp-18h]
  __int16 v71; // [rsp+F4h] [rbp-14h]
  __int64 v72; // [rsp+F8h] [rbp-10h]
  __int64 v73; // [rsp+100h] [rbp-8h]
  __int64 v74; // [rsp+108h] [rbp+0h] BYREF
  _OWORD v75[3]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v76[64]; // [rsp+148h] [rbp+40h] BYREF
  char v77[80]; // [rsp+188h] [rbp+80h] BYREF
  Ofc::CProxyPtrImpl **v78; // [rsp+228h] [rbp+120h] BYREF

  v78 = a3;
  Checked = (unsigned int *)Ofc::CProxyPtrImpl::GetChecked(*a3);
  GEL::ITopLevelEffect::Create(a2, Checked[96]);
  if ( (unsigned __int8)Ofc::TPropertySet<Art::ShapePropsIDs>::IsValid<Art::SpPr::Geometry>((char *)this + 168) )
  {
    v64 = 0;
    v65 = 0;
    Art::EditPointsDragElement::GetNewPathGeometry(this, (struct Art::Geometry2D *)&v64, a4);
    Paths = Art::Geometry2D::GetPaths((Art::Geometry2D *)&v64);
    v9 = (Art *)Ofc::TArray<Art::Path2D>::operator[]((char *)Paths + 8, *((unsigned int *)this + 55));
    memset(v69, 0, sizeof(v69));
    v70 = 0;
    v71 = 0;
    v72 = 0;
    v73 = 0;
    v10 = Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::GetPtrIfValid<Art::Text::Line>((char *)this + 168);
    v11 = v69;
    if ( v10 )
      v11 = (_OWORD *)v10;
    v12 = (__m128d)*(unsigned __int64 *)&DOUBLE_1_0;
    if ( *((_QWORD *)v9 + 3) )
    {
      v13 = 0;
      v13.m128d_f64[0] = (double)(int)*((_QWORD *)v11 + 2) / (double)(int)*((_QWORD *)v9 + 3);
    }
    else
    {
      v13 = (__m128d)*(unsigned __int64 *)&DOUBLE_1_0;
    }
    v14 = _mm_unpacklo_pd(v13, v13);
    if ( *((_QWORD *)v9 + 4) )
    {
      v12 = 0;
      v12.m128d_f64[0] = (double)(int)*((_QWORD *)v11 + 3) / (double)(int)*((_QWORD *)v9 + 4);
    }
    GelTransform = Art::GetGelTransform(v77, v11);
    v16 = *(_OWORD *)(GelTransform + 32);
    v17 = *(__m128d *)(GelTransform + 16);
    v68[0] = _mm_mul_pd(*(__m128d *)GelTransform, v14);
    v68[1] = _mm_mul_pd(_mm_unpacklo_pd(v12, v12), v17);
    v68[2] = v16;
    if ( *((_DWORD *)this + 54) == -1 )
    {
      Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::~TChoice<Art::LineStyleDataChoiceIDsImpl>(&v64);
    }
    else
    {
      v18 = (_QWORD *)((char *)v9 + 8);
      v19 = Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](
              (char *)v9 + 8,
              *((unsigned int *)this + 68));
      if ( (unsigned __int8)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::MoveTo>(v19)
        && Art::Path2D::FIsFigureClosed(v9, *((_DWORD *)this + 68)) )
      {
        PrevSegmentIndex = Art::FindPrevSegmentIndex(v9, (const struct Art::Path2D *)*((unsigned int *)this + 68), v20);
      }
      else
      {
        PrevSegmentIndex = *((_DWORD *)this + 68);
      }
      NextSegmentIndex = Art::FindNextSegmentIndex(v9, (const struct Art::Path2D *)PrevSegmentIndex, v20);
      v24 = Art::FindPrevSegmentIndex(v9, (const struct Art::Path2D *)PrevSegmentIndex, v23);
      if ( v24 == -1 && (int)PrevSegmentIndex > 0 )
      {
        v25 = Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](v18, PrevSegmentIndex - 1);
        if ( (unsigned __int8)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::MoveTo>(v25) )
          v24 = PrevSegmentIndex - 1;
      }
      v26 = Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](v18, PrevSegmentIndex);
      SegmentEndPoint = Art::GetSegmentEndPoint(v26);
      Art::AdjToGelPt(v67, SegmentEndPoint);
      GEL::PathBuilder::PathBuilder((GEL::PathBuilder *)v76);
      if ( v24 == -1 )
      {
        GEL::PathBuilder::BeginFigure(v76, v67);
      }
      else
      {
        v28 = Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](v18, v24);
        v29 = Art::GetSegmentEndPoint(v28);
        v30 = Art::AdjToGelPt(&v74, v29);
        GEL::PathBuilder::BeginFigure(v76, v30);
        Art::DrawSegment(v76, v26);
      }
      if ( NextSegmentIndex != -1 )
      {
        v31 = Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](v18, NextSegmentIndex);
        Art::DrawSegment(v76, v31);
      }
      GEL::PathBuilder::EndFigure(v76, 0);
      v32 = (_QWORD *)GEL::PathBuilder::Finish(v76, &v63[1], 0);
      v33 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *, _OWORD *))(*(_QWORD *)*v32 + 128LL))(
                         *v32,
                         &v66[1],
                         v68);
      v34 = *v33;
      *v33 = 0;
      v74 = v34;
      if ( v66[1] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v66[1] + 8LL))(v66[1]);
      if ( v63[1] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v63[1] + 8LL))(v63[1]);
      GEL::IEffectContainer::Create(v63);
      *(__m128i *)&v63[1] = _mm_load_si128((const __m128i *)&_xmm);
      v35 = v78;
      Art::ViewToHostX(v36, v78);
      GEL::IPen::Create(v66, v37, &v63[1]);
      v38 = v63[0];
      v39 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v63[0] + 144LL);
      v40 = (_QWORD *)GEL::IEffectPennedPath::Create(&v78, v34, v66[0]);
      v39(v38, *v40);
      v41 = v78;
      if ( v78 )
        (*((void (__fastcall **)(Ofc::CProxyPtrImpl **))*v78 + 1))(v78);
      *(__m128i *)&v66[1] = _mm_load_si128((const __m128i *)&_xmm);
      Art::ViewToHostX(v41, v35);
      GEL::IPen::Create(&v62, v42, &v66[1]);
      v61[0] = 0;
      v61[1] = (Mso::Memory *)0x8000000000000000LL;
      *(_QWORD *)Ofc::CArrayImpl::NewTop<double>(v61) = 0x400C000000000000LL;
      *(_QWORD *)Ofc::CArrayImpl::NewTop<double>(v61) = 0x400C000000000000LL;
      (*(void (__fastcall **)(__int64, Mso::Memory **))(*(_QWORD *)v62 + 96LL))(v62, v61);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v62 + 112LL))(v62, 0);
      v43 = v63[0];
      v44 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v63[0] + 144LL);
      v45 = (_QWORD *)GEL::IEffectPennedPath::Create(&v78, v34, v62);
      v44(v43, *v45);
      if ( v78 )
        (*((void (__fastcall **)(Ofc::CProxyPtrImpl **))*v78 + 1))(v78);
      v75[0] = _mm_load_si128((const __m128i *)&_xmm);
      v75[1] = _mm_load_si128((const __m128i *)&_xmm);
      v75[2] = 0;
      (*(void (__fastcall **)(_QWORD, _QWORD, _OWORD *))(*(_QWORD *)*a2 + 120LL))(*a2, v63[0], v75);
      v46 = *((unsigned int *)this + 69);
      if ( (int)v46 >= 0 )
      {
        v47 = Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](v18, v46);
        v48 = Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::CubicBezierTo>(v47);
        v49 = Ofc::TArray<Art::AdjPoint2D>::operator[](v48 + 8, 1);
        Art::AdjToGelPt(&v63[1], v49);
        v50 = *a2;
        v51 = *(void (__fastcall **)(__int64, _QWORD, _OWORD *))(*(_QWORD *)*a2 + 120LL);
        TangentGelEffect = (_QWORD *)Art::EditPointsDragElement::GetTangentGelEffect(
                                       (unsigned int)&v78,
                                       (_DWORD)v35,
                                       (unsigned int)v67,
                                       (unsigned int)&v63[1],
                                       (__int64)v68);
        v51(v50, *TangentGelEffect, v75);
        if ( v78 )
          (*((void (__fastcall **)(Ofc::CProxyPtrImpl **))*v78 + 1))(v78);
      }
      v53 = (void *)*((unsigned int *)this + 70);
      if ( (int)v53 >= 0 )
      {
        v54 = Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](v18, v53);
        v55 = Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::CubicBezierTo>(v54);
        v56 = Ofc::TArray<Art::AdjPoint2D>::operator[](v55 + 8, 0);
        Art::AdjToGelPt(&v63[1], v56);
        v57 = *a2;
        v58 = *(void (__fastcall **)(__int64, _QWORD, _OWORD *))(*(_QWORD *)*a2 + 120LL);
        v59 = (_QWORD *)Art::EditPointsDragElement::GetTangentGelEffect(
                          (unsigned int)&v78,
                          (_DWORD)v35,
                          (unsigned int)v67,
                          (unsigned int)&v63[1],
                          (__int64)v68);
        v58(v57, *v59, v75);
        if ( v78 )
          (*((void (__fastcall **)(Ofc::CProxyPtrImpl **))*v78 + 1))(v78);
      }
      if ( v61[0] )
        Mso::Memory::Free(v61[0], v53);
      if ( v62 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 8LL))(v62);
      if ( v66[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v66[0] + 8LL))(v66[0]);
      if ( v63[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v63[0] + 8LL))(v63[0]);
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 8LL))(v34);
      GEL::PathBuilder::~PathBuilder((GEL::PathBuilder *)v76);
      if ( v65 > 1 )
        (*(void (__fastcall **)(__int64 *))(v65 + 16))(&v64);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180189f90  mov     rax, rsp
0x180189f93  mov     [rax+20h], rbx
0x180189f97  mov     [rax+18h], r8
0x180189f9b  mov     [rax+10h], rdx
0x180189f9f  push    rbp
0x180189fa0  push    rsi
0x180189fa1  push    rdi
0x180189fa2  push    r12
0x180189fa4  push    r13
0x180189fa6  push    r14
0x180189fa8  push    r15
0x180189faa  lea     rbp, [rax-108h]
0x180189fb1  sub     rsp, 1D0h
0x180189fb8  movaps  xmmword ptr [rax-48h], xmm6
0x180189fbc  movaps  xmmword ptr [rax-58h], xmm7
0x180189fc0  mov     rbx, r9
0x180189fc3  mov     r12, rdx
0x180189fc6  mov     rsi, rcx
0x180189fc9  mov     [rbp+100h+arg_0], 1
0x180189fd3  mov     rcx, [r8]; this
0x180189fd6  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180189fdb  mov     edx, [rax+180h]
0x180189fe1  mov     rcx, r12
0x180189fe4  call    cs:__imp_?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z; GEL::ITopLevelEffect::Create(Gfx::RenderingPolicy)
0x180189fea  mov     [rbp+100h+arg_0], 1
0x180189ff4  lea     rdi, [rsi+0A8h]
0x180189ffb  mov     rcx, rdi
0x180189ffe  call    ??$IsValid@UGeometry@SpPr@Art@@@?$TPropertySet@VShapePropsIDs@Art@@@Ofc@@QEBA_NXZ; Ofc::TPropertySet<Art::ShapePropsIDs>::IsValid<Art::SpPr::Geometry>(void)
0x18018a003  xor     r14d, r14d
0x18018a006  test    al, al
0x18018a008  jz      loc_18018A641
0x18018a00e  xor     eax, eax
0x18018a010  mov     [rsp+200h+var_1A0], rax
0x18018a015  mov     [rsp+200h+var_198], r14
0x18018a01a  mov     r8, rbx; struct Art::MouseMessage *
0x18018a01d  lea     rdx, [rsp+200h+var_1A0]; struct Art::Geometry2D *
0x18018a022  mov     rcx, rsi; this
0x18018a025  call    ?GetNewPathGeometry@EditPointsDragElement@Art@@QEBAXAEAVGeometry2D@2@AEBVMouseMessage@2@@Z; Art::EditPointsDragElement::GetNewPathGeometry(Art::Geometry2D &,Art::MouseMessage const &)
0x18018a02a  lea     rcx, [rsp+200h+var_1A0]; this
0x18018a02f  call    ?GetPaths@Geometry2D@Art@@QEBAAEBVPath2DTable@2@XZ; Art::Geometry2D::GetPaths(void)
0x18018a034  lea     rcx, [rax+8]
0x18018a038  mov     edx, [rsi+0DCh]
0x18018a03e  call    ??A?$TArray@VPath2D@Art@@@Ofc@@QEBAAEBVPath2D@Art@@K@Z; Ofc::TArray<Art::Path2D>::operator[](ulong)
0x18018a043  mov     rbx, rax
0x18018a046  xorps   xmm0, xmm0
0x18018a049  movdqu  [rbp+100h+var_138], xmm0
0x18018a04e  xorps   xmm1, xmm1
0x18018a051  movdqu  [rbp+100h+var_128], xmm1
0x18018a056  mov     [rbp+100h+var_118], r14d
0x18018a05a  mov     [rbp+100h+var_114], r14w
0x18018a05f  xor     eax, eax
0x18018a061  mov     [rbp+100h+var_110], rax
0x18018a065  mov     [rbp+100h+var_108], rax
0x18018a069  mov     rcx, rdi
0x18018a06c  call    ??$GetPtrIfValid@ULine@Text@Art@@@?$TPropertySet@VTextCharPropertyBagIDs@Art@@@Ofc@@QEBAPEBVLineProps@Art@@XZ; Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::GetPtrIfValid<Art::Text::Line>(void)
0x18018a071  lea     rdx, [rbp+100h+var_138]
0x18018a075  test    rax, rax
0x18018a078  cmovnz  rdx, rax
0x18018a07c  movsd   xmm7, cs:__real@3ff0000000000000
0x18018a084  cmp     [rbx+18h], r14
0x18018a088  jnz     short loc_18018A08F
0x18018a08a  movaps  xmm6, xmm7
0x18018a08d  jmp     short loc_18018A0A5
0x18018a08f  xorps   xmm6, xmm6
0x18018a092  cvtsi2sd xmm6, qword ptr [rdx+10h]
0x18018a098  xorps   xmm0, xmm0
0x18018a09b  cvtsi2sd xmm0, qword ptr [rbx+18h]
0x18018a0a1  divsd   xmm6, xmm0
0x18018a0a5  unpcklpd xmm6, xmm6
0x18018a0a9  cmp     [rbx+20h], r14
0x18018a0ad  jz      short loc_18018A0C5
0x18018a0af  xorps   xmm7, xmm7
0x18018a0b2  cvtsi2sd xmm7, qword ptr [rdx+18h]
0x18018a0b8  xorps   xmm0, xmm0
0x18018a0bb  cvtsi2sd xmm0, qword ptr [rbx+20h]
0x18018a0c1  divsd   xmm7, xmm0
0x18018a0c5  lea     rcx, [rbp+100h+var_80]
0x18018a0cc  call    ?GetGelTransform@Art@@YA?AU?$TAffine3x3@N@Math@@AEBVTransform2D@1@@Z; Art::GetGelTransform(Art::Transform2D const &)
0x18018a0d1  movups  xmm3, xmmword ptr [rax+20h]
0x18018a0d5  movups  xmm2, xmmword ptr [rax+10h]
0x18018a0d9  movups  xmm0, xmmword ptr [rax]
0x18018a0dc  mulpd   xmm0, xmm6
0x18018a0e0  movups  [rbp+100h+var_168], xmm0
0x18018a0e4  movaps  xmm1, xmm7
0x18018a0e7  unpcklpd xmm1, xmm1
0x18018a0eb  mulpd   xmm1, xmm2
0x18018a0ef  movups  [rbp+100h+var_158], xmm1
0x18018a0f3  movups  [rbp+100h+var_148], xmm3
0x18018a0f7  cmp     dword ptr [rsi+0D8h], 0FFFFFFFFh
0x18018a0fe  jnz     short loc_18018A10F
0x18018a100  lea     rcx, [rsp+200h+var_1A0]
0x18018a105  call    ??1?$TChoice@VLineStyleDataChoiceIDsImpl@Art@@@Ofc@@QEAA@XZ; Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::~TChoice<Art::LineStyleDataChoiceIDsImpl>(void)
0x18018a10a  jmp     loc_18018A641
0x18018a10f  lea     r15, [rbx+8]
0x18018a113  mov     edx, [rsi+110h]
0x18018a119  mov     rcx, r15
0x18018a11c  call    ??A?$TArray@V?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@@Ofc@@QEBAAEBV?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@K@Z; Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](ulong)
0x18018a121  mov     rcx, rax
0x18018a124  call    ??$Is@UMoveTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::MoveTo>(void)
0x18018a129  test    al, al
0x18018a12b  jz      short loc_18018A151
0x18018a12d  mov     edx, [rsi+110h]; int
0x18018a133  mov     rcx, rbx; this
0x18018a136  call    ?FIsFigureClosed@Path2D@Art@@QEBA_NH@Z; Art::Path2D::FIsFigureClosed(int)
0x18018a13b  test    al, al
0x18018a13d  jz      short loc_18018A151
0x18018a13f  mov     edx, [rsi+110h]; struct Art::Path2D *
0x18018a145  mov     rcx, rbx; this
0x18018a148  call    ?FindPrevSegmentIndex@Art@@YAHAEBVPath2D@1@H@Z; Art::FindPrevSegmentIndex(Art::Path2D const &,int)
0x18018a14d  mov     edi, eax
0x18018a14f  jmp     short loc_18018A157
0x18018a151  mov     edi, [rsi+110h]
0x18018a157  mov     edx, edi; struct Art::Path2D *
0x18018a159  mov     rcx, rbx; this
0x18018a15c  call    ?FindNextSegmentIndex@Art@@YAHAEBVPath2D@1@H@Z; Art::FindNextSegmentIndex(Art::Path2D const &,int)
0x18018a161  mov     r13d, eax
0x18018a164  mov     edx, edi; struct Art::Path2D *
0x18018a166  mov     rcx, rbx; this
0x18018a169  call    ?FindPrevSegmentIndex@Art@@YAHAEBVPath2D@1@H@Z; Art::FindPrevSegmentIndex(Art::Path2D const &,int)
0x18018a16e  mov     r14d, eax
0x18018a171  cmp     eax, 0FFFFFFFFh
0x18018a174  jnz     short loc_18018A195
0x18018a176  test    edi, edi
0x18018a178  jle     short loc_18018A195
0x18018a17a  lea     ebx, [rdi-1]
0x18018a17d  mov     edx, ebx
0x18018a17f  mov     rcx, r15
0x18018a182  call    ??A?$TArray@V?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@@Ofc@@QEBAAEBV?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@K@Z; Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](ulong)
0x18018a187  mov     rcx, rax
0x18018a18a  call    ??$Is@UMoveTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::MoveTo>(void)
0x18018a18f  test    al, al
0x18018a191  cmovnz  r14d, ebx
0x18018a195  mov     edx, edi
0x18018a197  mov     rcx, r15
0x18018a19a  call    ??A?$TArray@V?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@@Ofc@@QEBAAEBV?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@K@Z; Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](ulong)
0x18018a19f  mov     rbx, rax
0x18018a1a2  mov     rcx, rax
0x18018a1a5  call    ?GetSegmentEndPoint@Art@@YAAEBVAdjPoint2D@1@PEBV?$Segment_@$0A@@Path2DData@1@@Z; Art::GetSegmentEndPoint(Art::Path2DData::Segment_<0> const *)
0x18018a1aa  mov     rdx, rax
0x18018a1ad  lea     rcx, [rbp+100h+var_178]
0x18018a1b1  call    ?AdjToGelPt@Art@@YA?AUPoint@GEL@@AEBVAdjPoint2D@1@@Z; Art::AdjToGelPt(Art::AdjPoint2D const &)
0x18018a1b6  lea     rcx, [rbp+100h+var_C0]
0x18018a1ba  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x18018a1c0  nop
0x18018a1c1  cmp     r14d, 0FFFFFFFFh
0x18018a1c5  jz      short loc_18018A201
0x18018a1c7  mov     edx, r14d
0x18018a1ca  mov     rcx, r15
0x18018a1cd  call    ??A?$TArray@V?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@@Ofc@@QEBAAEBV?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@K@Z; Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](ulong)
0x18018a1d2  mov     rcx, rax
0x18018a1d5  call    ?GetSegmentEndPoint@Art@@YAAEBVAdjPoint2D@1@PEBV?$Segment_@$0A@@Path2DData@1@@Z; Art::GetSegmentEndPoint(Art::Path2DData::Segment_<0> const *)
0x18018a1da  mov     rdx, rax
0x18018a1dd  lea     rcx, [rbp+100h+var_100]
0x18018a1e1  call    ?AdjToGelPt@Art@@YA?AUPoint@GEL@@AEBVAdjPoint2D@1@@Z; Art::AdjToGelPt(Art::AdjPoint2D const &)
0x18018a1e6  mov     rdx, rax
0x18018a1e9  lea     rcx, [rbp+100h+var_C0]
0x18018a1ed  call    cs:__imp_?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z; GEL::PathBuilder::BeginFigure(Math::TPoint2<double> const &)
0x18018a1f3  mov     rdx, rbx
0x18018a1f6  lea     rcx, [rbp+100h+var_C0]
0x18018a1fa  call    ?DrawSegment@Art@@YAXAEAVPathBuilder@GEL@@AEBV?$Segment_@$0A@@Path2DData@1@@Z; Art::DrawSegment(GEL::PathBuilder &,Art::Path2DData::Segment_<0> const &)
0x18018a1ff  jmp     short loc_18018A20F
0x18018a201  lea     rdx, [rbp+100h+var_178]
0x18018a205  lea     rcx, [rbp+100h+var_C0]
0x18018a209  call    cs:__imp_?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z; GEL::PathBuilder::BeginFigure(Math::TPoint2<double> const &)
0x18018a20f  cmp     r13d, 0FFFFFFFFh
0x18018a213  jz      short loc_18018A22C
0x18018a215  mov     edx, r13d
0x18018a218  mov     rcx, r15
0x18018a21b  call    ??A?$TArray@V?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@@Ofc@@QEBAAEBV?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@K@Z; Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](ulong)
0x18018a220  mov     rdx, rax
0x18018a223  lea     rcx, [rbp+100h+var_C0]
0x18018a227  call    ?DrawSegment@Art@@YAXAEAVPathBuilder@GEL@@AEBV?$Segment_@$0A@@Path2DData@1@@Z; Art::DrawSegment(GEL::PathBuilder &,Art::Path2DData::Segment_<0> const &)
0x18018a22c  xor     edx, edx
0x18018a22e  lea     rcx, [rbp+100h+var_C0]
0x18018a232  call    cs:__imp_?EndFigure@PathBuilder@GEL@@QEAAAEAV12@W4FigureEnd@Path@Graphics@Mso@@@Z; GEL::PathBuilder::EndFigure(Mso::Graphics::Path::FigureEnd)
0x18018a238  xor     r8d, r8d
0x18018a23b  lea     rdx, [rsp+200h+var_1B8+8]
0x18018a240  lea     rcx, [rbp+100h+var_C0]
0x18018a244  call    cs:__imp_?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x18018a24a  nop
0x18018a24b  mov     rcx, [rax]
0x18018a24e  mov     rax, [rcx]
0x18018a251  lea     r8, [rbp+100h+var_168]
0x18018a255  lea     rdx, [rsp+200h+var_190+8]
0x18018a25a  mov     rax, [rax+80h]
0x18018a261  call    cs:__guard_dispatch_icall_fptr
0x18018a267  mov     r14, [rax]
0x18018a26a  mov     qword ptr [rax], 0
0x18018a271  mov     [rbp+100h+var_100], r14
0x18018a275  mov     rcx, qword ptr [rsp+200h+var_190+8]
0x18018a27a  test    rcx, rcx
0x18018a27d  jz      short loc_18018A28D
0x18018a27f  mov     rax, [rcx]
0x18018a282  mov     rax, [rax+8]
0x18018a286  call    cs:__guard_dispatch_icall_fptr
0x18018a28c  nop
0x18018a28d  mov     rcx, qword ptr [rsp+200h+var_1B8+8]
0x18018a292  test    rcx, rcx
0x18018a295  jz      short loc_18018A2A4
0x18018a297  mov     rax, [rcx]
0x18018a29a  mov     rax, [rax+8]
0x18018a29e  call    cs:__guard_dispatch_icall_fptr
0x18018a2a4  lea     rcx, [rsp+200h+var_1B8]
0x18018a2a9  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x18018a2af  movdqa  xmm0, cs:__xmm@3f8000003f8000003f8000003f800000
0x18018a2b7  movups  xmmword ptr [rsp+200h+var_1B8+8], xmm0
0x18018a2bc  mov     r13, [rbp+100h+arg_10]
0x18018a2c3  mov     rdx, r13
0x18018a2c6  movss   xmm6, cs:__real@3f800000
0x18018a2ce  movaps  xmm0, xmm6
0x18018a2d1  call    ?ViewToHostX@Art@@YA_JMAEBV?$TSharedPtr@$$CBVView@Art@@@Ofc@@@Z; Art::ViewToHostX(float,Ofc::TSharedPtr<Art::View const> const &)
0x18018a2d6  xorps   xmm1, xmm1
0x18018a2d9  cvtsi2sd xmm1, rax
0x18018a2de  lea     r8, [rsp+200h+var_1B8+8]
0x18018a2e3  lea     rcx, [rsp+200h+var_190]
0x18018a2e8  call    cs:__imp_?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z; GEL::IPen::Create(double,GEL::Color const &)
0x18018a2ee  mov     rbx, qword ptr [rsp+200h+var_1B8]
0x18018a2f3  mov     rax, [rbx]
0x18018a2f6  mov     rdi, [rax+90h]
0x18018a2fd  mov     r8, qword ptr [rsp+200h+var_190]
0x18018a302  mov     rdx, r14
0x18018a305  lea     rcx, [rbp+100h+arg_10]
0x18018a30c  call    cs:__imp_?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z; GEL::IEffectPennedPath::Create(GEL::IPath const &,GEL::IPen const &)
0x18018a312  mov     rdx, [rax]
0x18018a315  mov     rcx, rbx
0x18018a318  mov     rax, rdi
0x18018a31b  call    cs:__guard_dispatch_icall_fptr
0x18018a321  mov     rcx, [rbp+100h+arg_10]
0x18018a328  test    rcx, rcx
0x18018a32b  jz      short loc_18018A33A
0x18018a32d  mov     rax, [rcx]
0x18018a330  mov     rax, [rax+8]
0x18018a334  call    cs:__guard_dispatch_icall_fptr
0x18018a33a  movdqa  xmm1, cs:__xmm@3f800000000000000000000000000000
0x18018a342  movups  xmmword ptr [rsp+200h+var_190+8], xmm1
0x18018a347  mov     rdx, r13
0x18018a34a  movaps  xmm0, xmm6
0x18018a34d  call    ?ViewToHostX@Art@@YA_JMAEBV?$TSharedPtr@$$CBVView@Art@@@Ofc@@@Z; Art::ViewToHostX(float,Ofc::TSharedPtr<Art::View const> const &)
0x18018a352  xorps   xmm1, xmm1
0x18018a355  cvtsi2sd xmm1, rax
0x18018a35a  lea     r8, [rsp+200h+var_190+8]
0x18018a35f  lea     rcx, [rsp+200h+var_1C0]
0x18018a364  call    cs:__imp_?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z; GEL::IPen::Create(double,GEL::Color const &)
0x18018a36a  mov     qword ptr [rsp+200h+var_1D0], 0
0x18018a373  mov     dword ptr [rsp+200h+var_1C8], 0
0x18018a37b  mov     dword ptr [rsp+200h+var_1C8+4], 80000000h
0x18018a383  lea     rcx, [rsp+200h+var_1D0]
0x18018a388  call    ??$NewTop@N@CArrayImpl@Ofc@@IEAAAEANXZ; Ofc::CArrayImpl::NewTop<double>(void)
0x18018a38d  mov     rbx, 400C000000000000h
0x18018a397  mov     [rax], rbx
0x18018a39a  mov     eax, dword ptr [rsp+200h+var_1C8+4]
0x18018a39e  btr     eax, 1Fh
0x18018a3a2  mov     ecx, dword ptr [rsp+200h+var_1C8]
0x18018a3a6  cmp     ecx, eax
0x18018a3a8  jb      short loc_18018A3CA
0x18018a3aa  mov     rdx, qword ptr [rsp+200h+var_1D0]
0x18018a3af  test    rdx, rdx
0x18018a3b2  jz      short loc_18018A3CA
0x18018a3b4  lea     r8, qword_180C3BE58
0x18018a3bb  cmp     rdx, r8
0x18018a3be  ja      short loc_18018A3CA
0x18018a3c0  lea     ecx, ds:0[rcx*8]
0x18018a3c7  add     rcx, rdx
0x18018a3ca  lea     rcx, [rsp+200h+var_1D0]
0x18018a3cf  call    ??$NewTop@N@CArrayImpl@Ofc@@IEAAAEANXZ; Ofc::CArrayImpl::NewTop<double>(void)
0x18018a3d4  mov     [rax], rbx
0x18018a3d7  mov     rcx, [rsp+200h+var_1C0]
0x18018a3dc  mov     rax, [rcx]
0x18018a3df  lea     rdx, [rsp+200h+var_1D0]
0x18018a3e4  mov     rax, [rax+60h]
0x18018a3e8  call    cs:__guard_dispatch_icall_fptr
0x18018a3ee  mov     rcx, [rsp+200h+var_1C0]
0x18018a3f3  mov     rax, [rcx]
0x18018a3f6  xor     edx, edx
0x18018a3f8  mov     rax, [rax+70h]
0x18018a3fc  call    cs:__guard_dispatch_icall_fptr
0x18018a402  mov     rbx, qword ptr [rsp+200h+var_1B8]
0x18018a407  mov     rax, [rbx]
0x18018a40a  mov     rdi, [rax+90h]
0x18018a411  mov     r8, [rsp+200h+var_1C0]
0x18018a416  mov     rdx, r14
0x18018a419  lea     rcx, [rbp+100h+arg_10]
0x18018a420  call    cs:__imp_?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z; GEL::IEffectPennedPath::Create(GEL::IPath const &,GEL::IPen const &)
0x18018a426  nop
0x18018a427  mov     rdx, [rax]
0x18018a42a  mov     rcx, rbx
0x18018a42d  mov     rax, rdi
0x18018a430  call    cs:__guard_dispatch_icall_fptr
0x18018a436  nop
0x18018a437  mov     rcx, [rbp+100h+arg_10]
0x18018a43e  test    rcx, rcx
0x18018a441  jz      short loc_18018A450
0x18018a443  mov     rax, [rcx]
0x18018a446  mov     rax, [rax+8]
0x18018a44a  call    cs:__guard_dispatch_icall_fptr
0x18018a450  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x18018a458  movups  [rbp+100h+var_F0], xmm0
0x18018a45c  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x18018a464  movups  [rbp+100h+var_E0], xmm1
0x18018a468  xorps   xmm0, xmm0
  ... truncated ...
```
