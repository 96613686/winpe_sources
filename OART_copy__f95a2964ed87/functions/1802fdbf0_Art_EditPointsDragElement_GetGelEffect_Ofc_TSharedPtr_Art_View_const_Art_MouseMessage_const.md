# Art::EditPointsDragElement::GetGelEffect(Ofc::TSharedPtr<Art::View> const &,Art::MouseMessage const &)

- ea: `0x1802fdbf0`
- end: `0x1802fe2cf`
- name: `?GetGelEffect@EditPointsDragElement@Art@@UEBA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBV?$TSharedPtr@VView@Art@@@4@AEBVMouseMessage@2@@Z`
- size: `1759`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180052708`
- `0x180079e18`
- `0x1800b9580`
- `0x1800b9620`
- `0x1800ba3a8`
- `0x1801061d0`
- `0x1801538e8`
- `0x1801aa980`
- `0x1801ebbe0`
- `0x180261628`
- `0x180279050`
- `0x18027f410`
- `0x180281054`
- `0x180281074`
- `0x180281eb0`
- `0x1802fdb08`
- `0x1802fdbf0`
- `0x1802fe2d0`
- `0x1802fe3b0`
- `0x1802fe8d8`
- `0x1802ff3c0`
- `0x1805fc500`
- `0x1806bc4f0`

## import_xrefs

- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x1802fdea5`
- `gfx!?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z` at `0x1802fdea5`
- `gfx!?EndFigure@PathBuilder@GEL@@QEAAAEAV12@W4FigureEnd@Path@Graphics@Mso@@@Z` at `0x1802fde93`
- `gfx!?EndFigure@PathBuilder@GEL@@QEAAAEAV12@W4FigureEnd@Path@Graphics@Mso@@@Z` at `0x1802fde93`
- `gfx!?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x1802fde4e`
- `gfx!?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x1802fde6a`
- `gfx!?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x1802fde4e`
- `gfx!?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x1802fde6a`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x1802fe286`
- `gfx!??1PathBuilder@GEL@@QEAA@XZ` at `0x1802fe286`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1802fde1b`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x1802fde1b`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1802fdf6e`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1802fe086`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1802fdf6e`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x1802fe086`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1802fdf49`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1802fdfc8`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1802fdf49`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x1802fdfc8`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1802fdf0a`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1802fdf0a`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x1802fdc44`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x1802fdc44`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802fe21d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1802fe21d`

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
0x1802fdbf0  mov     rax, rsp
0x1802fdbf3  mov     [rax+20h], rbx
0x1802fdbf7  mov     [rax+18h], r8
0x1802fdbfb  mov     [rax+10h], rdx
0x1802fdbff  push    rbp
0x1802fdc00  push    rsi
0x1802fdc01  push    rdi
0x1802fdc02  push    r12
0x1802fdc04  push    r13
0x1802fdc06  push    r14
0x1802fdc08  push    r15
0x1802fdc0a  lea     rbp, [rax-108h]
0x1802fdc11  sub     rsp, 1D0h
0x1802fdc18  movaps  xmmword ptr [rax-48h], xmm6
0x1802fdc1c  movaps  xmmword ptr [rax-58h], xmm7
0x1802fdc20  mov     rbx, r9
0x1802fdc23  mov     r12, rdx
0x1802fdc26  mov     rsi, rcx
0x1802fdc29  mov     [rbp+100h+arg_0], 1
0x1802fdc33  mov     rcx, [r8]; this
0x1802fdc36  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1802fdc3b  mov     edx, [rax+180h]
0x1802fdc41  mov     rcx, r12
0x1802fdc44  call    cs:__imp_?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z; GEL::ITopLevelEffect::Create(Gfx::RenderingPolicy)
0x1802fdc4a  nop
0x1802fdc4b  mov     [rbp+100h+arg_0], 1
0x1802fdc55  lea     rdi, [rsi+0A8h]
0x1802fdc5c  mov     rcx, rdi
0x1802fdc5f  call    ??$IsValid@UGeometry@SpPr@Art@@@?$TPropertySet@VShapePropsIDs@Art@@@Ofc@@QEBA_NXZ; Ofc::TPropertySet<Art::ShapePropsIDs>::IsValid<Art::SpPr::Geometry>(void)
0x1802fdc64  xor     r14d, r14d
0x1802fdc67  test    al, al
0x1802fdc69  jz      loc_1802FE2A7
0x1802fdc6f  xor     eax, eax
0x1802fdc71  mov     [rsp+200h+var_1A0], rax
0x1802fdc76  mov     [rsp+200h+var_198], r14
0x1802fdc7b  mov     r8, rbx; struct Art::MouseMessage *
0x1802fdc7e  lea     rdx, [rsp+200h+var_1A0]; struct Art::Geometry2D *
0x1802fdc83  mov     rcx, rsi; this
0x1802fdc86  call    ?GetNewPathGeometry@EditPointsDragElement@Art@@QEBAXAEAVGeometry2D@2@AEBVMouseMessage@2@@Z; Art::EditPointsDragElement::GetNewPathGeometry(Art::Geometry2D &,Art::MouseMessage const &)
0x1802fdc8b  lea     rcx, [rsp+200h+var_1A0]; this
0x1802fdc90  call    ?GetPaths@Geometry2D@Art@@QEBAAEBVPath2DTable@2@XZ; Art::Geometry2D::GetPaths(void)
0x1802fdc95  lea     rcx, [rax+8]
0x1802fdc99  mov     edx, [rsi+0DCh]
0x1802fdc9f  call    ??A?$TArray@VPath2D@Art@@@Ofc@@QEBAAEBVPath2D@Art@@K@Z; Ofc::TArray<Art::Path2D>::operator[](ulong)
0x1802fdca4  mov     rbx, rax
0x1802fdca7  xorps   xmm0, xmm0
0x1802fdcaa  movdqu  [rbp+100h+var_138], xmm0
0x1802fdcaf  xorps   xmm1, xmm1
0x1802fdcb2  movdqu  [rbp+100h+var_128], xmm1
0x1802fdcb7  mov     [rbp+100h+var_118], r14d
0x1802fdcbb  mov     [rbp+100h+var_114], r14w
0x1802fdcc0  xor     eax, eax
0x1802fdcc2  mov     [rbp+100h+var_110], rax
0x1802fdcc6  mov     [rbp+100h+var_108], rax
0x1802fdcca  mov     rcx, rdi
0x1802fdccd  call    ??$GetPtrIfValid@ULine@Text@Art@@@?$TPropertySet@VTextCharPropertyBagIDs@Art@@@Ofc@@QEBAPEBVLineProps@Art@@XZ; Ofc::TPropertySet<Art::TextCharPropertyBagIDs>::GetPtrIfValid<Art::Text::Line>(void)
0x1802fdcd2  lea     rdx, [rbp+100h+var_138]
0x1802fdcd6  test    rax, rax
0x1802fdcd9  cmovnz  rdx, rax
0x1802fdcdd  movsd   xmm7, cs:__real@3ff0000000000000
0x1802fdce5  cmp     [rbx+18h], r14
0x1802fdce9  jnz     short loc_1802FDCF0
0x1802fdceb  movaps  xmm6, xmm7
0x1802fdcee  jmp     short loc_1802FDD06
0x1802fdcf0  xorps   xmm6, xmm6
0x1802fdcf3  cvtsi2sd xmm6, qword ptr [rdx+10h]
0x1802fdcf9  xorps   xmm0, xmm0
0x1802fdcfc  cvtsi2sd xmm0, qword ptr [rbx+18h]
0x1802fdd02  divsd   xmm6, xmm0
0x1802fdd06  unpcklpd xmm6, xmm6
0x1802fdd0a  cmp     [rbx+20h], r14
0x1802fdd0e  jz      short loc_1802FDD26
0x1802fdd10  xorps   xmm7, xmm7
0x1802fdd13  cvtsi2sd xmm7, qword ptr [rdx+18h]
0x1802fdd19  xorps   xmm0, xmm0
0x1802fdd1c  cvtsi2sd xmm0, qword ptr [rbx+20h]
0x1802fdd22  divsd   xmm7, xmm0
0x1802fdd26  lea     rcx, [rbp+100h+var_80]
0x1802fdd2d  call    ?GetGelTransform@Art@@YA?AU?$TAffine3x3@N@Math@@AEBVTransform2D@1@@Z; Art::GetGelTransform(Art::Transform2D const &)
0x1802fdd32  movups  xmm3, xmmword ptr [rax+20h]
0x1802fdd36  movups  xmm2, xmmword ptr [rax+10h]
0x1802fdd3a  movups  xmm0, xmmword ptr [rax]
0x1802fdd3d  mulpd   xmm0, xmm6
0x1802fdd41  movups  [rbp+100h+var_168], xmm0
0x1802fdd45  movaps  xmm1, xmm7
0x1802fdd48  unpcklpd xmm1, xmm1
0x1802fdd4c  mulpd   xmm1, xmm2
0x1802fdd50  movups  [rbp+100h+var_158], xmm1
0x1802fdd54  movups  [rbp+100h+var_148], xmm3
0x1802fdd58  cmp     dword ptr [rsi+0D8h], 0FFFFFFFFh
0x1802fdd5f  jnz     short loc_1802FDD70
0x1802fdd61  lea     rcx, [rsp+200h+var_1A0]
0x1802fdd66  call    ??1?$TChoice@VLineStyleDataChoiceIDsImpl@Art@@@Ofc@@QEAA@XZ; Ofc::TChoice<Art::LineStyleDataChoiceIDsImpl>::~TChoice<Art::LineStyleDataChoiceIDsImpl>(void)
0x1802fdd6b  jmp     loc_1802FE2A7
0x1802fdd70  lea     r15, [rbx+8]
0x1802fdd74  mov     edx, [rsi+110h]
0x1802fdd7a  mov     rcx, r15
0x1802fdd7d  call    ??A?$TArray@V?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@@Ofc@@QEBAAEBV?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@K@Z; Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](ulong)
0x1802fdd82  mov     rcx, rax
0x1802fdd85  call    ??$Is@UMoveTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::MoveTo>(void)
0x1802fdd8a  test    al, al
0x1802fdd8c  jz      short loc_1802FDDB2
0x1802fdd8e  mov     edx, [rsi+110h]; int
0x1802fdd94  mov     rcx, rbx; this
0x1802fdd97  call    ?FIsFigureClosed@Path2D@Art@@QEBA_NH@Z; Art::Path2D::FIsFigureClosed(int)
0x1802fdd9c  test    al, al
0x1802fdd9e  jz      short loc_1802FDDB2
0x1802fdda0  mov     edx, [rsi+110h]; struct Art::Path2D *
0x1802fdda6  mov     rcx, rbx; this
0x1802fdda9  call    ?FindPrevSegmentIndex@Art@@YAHAEBVPath2D@1@H@Z; Art::FindPrevSegmentIndex(Art::Path2D const &,int)
0x1802fddae  mov     edi, eax
0x1802fddb0  jmp     short loc_1802FDDB8
0x1802fddb2  mov     edi, [rsi+110h]
0x1802fddb8  mov     edx, edi; struct Art::Path2D *
0x1802fddba  mov     rcx, rbx; this
0x1802fddbd  call    ?FindNextSegmentIndex@Art@@YAHAEBVPath2D@1@H@Z; Art::FindNextSegmentIndex(Art::Path2D const &,int)
0x1802fddc2  mov     r13d, eax
0x1802fddc5  mov     edx, edi; struct Art::Path2D *
0x1802fddc7  mov     rcx, rbx; this
0x1802fddca  call    ?FindPrevSegmentIndex@Art@@YAHAEBVPath2D@1@H@Z; Art::FindPrevSegmentIndex(Art::Path2D const &,int)
0x1802fddcf  mov     r14d, eax
0x1802fddd2  cmp     eax, 0FFFFFFFFh
0x1802fddd5  jnz     short loc_1802FDDF6
0x1802fddd7  test    edi, edi
0x1802fddd9  jle     short loc_1802FDDF6
0x1802fdddb  lea     ebx, [rdi-1]
0x1802fddde  mov     edx, ebx
0x1802fdde0  mov     rcx, r15
0x1802fdde3  call    ??A?$TArray@V?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@@Ofc@@QEBAAEBV?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@K@Z; Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](ulong)
0x1802fdde8  mov     rcx, rax
0x1802fddeb  call    ??$Is@UMoveTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Is<Art::Path2DData::MoveTo>(void)
0x1802fddf0  test    al, al
0x1802fddf2  cmovnz  r14d, ebx
0x1802fddf6  mov     edx, edi
0x1802fddf8  mov     rcx, r15
0x1802fddfb  call    ??A?$TArray@V?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@@Ofc@@QEBAAEBV?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@K@Z; Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](ulong)
0x1802fde00  mov     rbx, rax
0x1802fde03  mov     rcx, rax
0x1802fde06  call    ?GetSegmentEndPoint@Art@@YAAEBVAdjPoint2D@1@PEBV?$Segment_@$0A@@Path2DData@1@@Z; Art::GetSegmentEndPoint(Art::Path2DData::Segment_<0> const *)
0x1802fde0b  mov     rdx, rax
0x1802fde0e  lea     rcx, [rbp+100h+var_178]
0x1802fde12  call    ?AdjToGelPt@Art@@YA?AUPoint@GEL@@AEBVAdjPoint2D@1@@Z; Art::AdjToGelPt(Art::AdjPoint2D const &)
0x1802fde17  lea     rcx, [rbp+100h+var_C0]
0x1802fde1b  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x1802fde21  nop
0x1802fde22  cmp     r14d, 0FFFFFFFFh
0x1802fde26  jz      short loc_1802FDE62
0x1802fde28  mov     edx, r14d
0x1802fde2b  mov     rcx, r15
0x1802fde2e  call    ??A?$TArray@V?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@@Ofc@@QEBAAEBV?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@K@Z; Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](ulong)
0x1802fde33  mov     rcx, rax
0x1802fde36  call    ?GetSegmentEndPoint@Art@@YAAEBVAdjPoint2D@1@PEBV?$Segment_@$0A@@Path2DData@1@@Z; Art::GetSegmentEndPoint(Art::Path2DData::Segment_<0> const *)
0x1802fde3b  mov     rdx, rax
0x1802fde3e  lea     rcx, [rbp+100h+var_100]
0x1802fde42  call    ?AdjToGelPt@Art@@YA?AUPoint@GEL@@AEBVAdjPoint2D@1@@Z; Art::AdjToGelPt(Art::AdjPoint2D const &)
0x1802fde47  mov     rdx, rax
0x1802fde4a  lea     rcx, [rbp+100h+var_C0]
0x1802fde4e  call    cs:__imp_?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z; GEL::PathBuilder::BeginFigure(Math::TPoint2<double> const &)
0x1802fde54  mov     rdx, rbx
0x1802fde57  lea     rcx, [rbp+100h+var_C0]
0x1802fde5b  call    ?DrawSegment@Art@@YAXAEAVPathBuilder@GEL@@AEBV?$Segment_@$0A@@Path2DData@1@@Z; Art::DrawSegment(GEL::PathBuilder &,Art::Path2DData::Segment_<0> const &)
0x1802fde60  jmp     short loc_1802FDE70
0x1802fde62  lea     rdx, [rbp+100h+var_178]
0x1802fde66  lea     rcx, [rbp+100h+var_C0]
0x1802fde6a  call    cs:__imp_?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z; GEL::PathBuilder::BeginFigure(Math::TPoint2<double> const &)
0x1802fde70  cmp     r13d, 0FFFFFFFFh
0x1802fde74  jz      short loc_1802FDE8D
0x1802fde76  mov     edx, r13d
0x1802fde79  mov     rcx, r15
0x1802fde7c  call    ??A?$TArray@V?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@@Ofc@@QEBAAEBV?$traceViewChoice_@$0A@@InkTraceViewData@InkML@@K@Z; Ofc::TArray<InkML::InkTraceViewData::traceViewChoice_<0>>::operator[](ulong)
0x1802fde81  mov     rdx, rax
0x1802fde84  lea     rcx, [rbp+100h+var_C0]
0x1802fde88  call    ?DrawSegment@Art@@YAXAEAVPathBuilder@GEL@@AEBV?$Segment_@$0A@@Path2DData@1@@Z; Art::DrawSegment(GEL::PathBuilder &,Art::Path2DData::Segment_<0> const &)
0x1802fde8d  xor     edx, edx
0x1802fde8f  lea     rcx, [rbp+100h+var_C0]
0x1802fde93  call    cs:__imp_?EndFigure@PathBuilder@GEL@@QEAAAEAV12@W4FigureEnd@Path@Graphics@Mso@@@Z; GEL::PathBuilder::EndFigure(Mso::Graphics::Path::FigureEnd)
0x1802fde99  xor     r8d, r8d
0x1802fde9c  lea     rdx, [rsp+200h+var_1B8+8]
0x1802fdea1  lea     rcx, [rbp+100h+var_C0]
0x1802fdea5  call    cs:__imp_?Finish@PathBuilder@GEL@@QEAA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@W4FillMode@Path@Graphics@Mso@@@Z; GEL::PathBuilder::Finish(Mso::Graphics::Path::FillMode)
0x1802fdeab  nop
0x1802fdeac  mov     rcx, [rax]
0x1802fdeaf  mov     rax, [rcx]
0x1802fdeb2  lea     r8, [rbp+100h+var_168]
0x1802fdeb6  lea     rdx, [rsp+200h+var_190+8]
0x1802fdebb  mov     rax, [rax+80h]
0x1802fdec2  call    cs:__guard_dispatch_icall_fptr
0x1802fdec8  mov     r14, [rax]
0x1802fdecb  mov     qword ptr [rax], 0
0x1802fded2  mov     [rbp+100h+var_100], r14
0x1802fded6  mov     rcx, qword ptr [rsp+200h+var_190+8]
0x1802fdedb  test    rcx, rcx
0x1802fdede  jz      short loc_1802FDEEE
0x1802fdee0  mov     rax, [rcx]
0x1802fdee3  mov     rax, [rax+8]
0x1802fdee7  call    cs:__guard_dispatch_icall_fptr
0x1802fdeed  nop
0x1802fdeee  mov     rcx, qword ptr [rsp+200h+var_1B8+8]
0x1802fdef3  test    rcx, rcx
0x1802fdef6  jz      short loc_1802FDF05
0x1802fdef8  mov     rax, [rcx]
0x1802fdefb  mov     rax, [rax+8]
0x1802fdeff  call    cs:__guard_dispatch_icall_fptr
0x1802fdf05  lea     rcx, [rsp+200h+var_1B8]
0x1802fdf0a  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x1802fdf10  movdqa  xmm0, cs:__xmm@3f8000003f8000003f8000003f800000
0x1802fdf18  movups  xmmword ptr [rsp+200h+var_1B8+8], xmm0
0x1802fdf1d  mov     r13, [rbp+100h+arg_10]
0x1802fdf24  mov     rdx, r13
0x1802fdf27  movss   xmm6, cs:__real@3f800000
0x1802fdf2f  movaps  xmm0, xmm6
0x1802fdf32  call    ?ViewToHostX@Art@@YA_JMAEBV?$TSharedPtr@$$CBVView@Art@@@Ofc@@@Z; Art::ViewToHostX(float,Ofc::TSharedPtr<Art::View const> const &)
0x1802fdf37  xorps   xmm1, xmm1
0x1802fdf3a  cvtsi2sd xmm1, rax
0x1802fdf3f  lea     r8, [rsp+200h+var_1B8+8]
0x1802fdf44  lea     rcx, [rsp+200h+var_190]
0x1802fdf49  call    cs:__imp_?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z; GEL::IPen::Create(double,GEL::Color const &)
0x1802fdf4f  nop
0x1802fdf50  mov     rbx, qword ptr [rsp+200h+var_1B8]
0x1802fdf55  mov     rax, [rbx]
0x1802fdf58  mov     rdi, [rax+90h]
0x1802fdf5f  mov     r8, qword ptr [rsp+200h+var_190]
0x1802fdf64  mov     rdx, r14
0x1802fdf67  lea     rcx, [rbp+100h+arg_10]
0x1802fdf6e  call    cs:__imp_?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z; GEL::IEffectPennedPath::Create(GEL::IPath const &,GEL::IPen const &)
0x1802fdf74  nop
0x1802fdf75  mov     rdx, [rax]
0x1802fdf78  mov     rcx, rbx
0x1802fdf7b  mov     rax, rdi
0x1802fdf7e  call    cs:__guard_dispatch_icall_fptr
0x1802fdf84  nop
0x1802fdf85  mov     rcx, [rbp+100h+arg_10]
0x1802fdf8c  test    rcx, rcx
0x1802fdf8f  jz      short loc_1802FDF9E
0x1802fdf91  mov     rax, [rcx]
0x1802fdf94  mov     rax, [rax+8]
0x1802fdf98  call    cs:__guard_dispatch_icall_fptr
0x1802fdf9e  movdqa  xmm1, cs:__xmm@3f800000000000000000000000000000
0x1802fdfa6  movups  xmmword ptr [rsp+200h+var_190+8], xmm1
0x1802fdfab  mov     rdx, r13
0x1802fdfae  movaps  xmm0, xmm6
0x1802fdfb1  call    ?ViewToHostX@Art@@YA_JMAEBV?$TSharedPtr@$$CBVView@Art@@@Ofc@@@Z; Art::ViewToHostX(float,Ofc::TSharedPtr<Art::View const> const &)
0x1802fdfb6  xorps   xmm1, xmm1
0x1802fdfb9  cvtsi2sd xmm1, rax
0x1802fdfbe  lea     r8, [rsp+200h+var_190+8]
0x1802fdfc3  lea     rcx, [rsp+200h+var_1C0]
0x1802fdfc8  call    cs:__imp_?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z; GEL::IPen::Create(double,GEL::Color const &)
0x1802fdfce  nop
0x1802fdfcf  nop
0x1802fdfd0  mov     qword ptr [rsp+200h+var_1D0], 0
0x1802fdfd9  mov     dword ptr [rsp+200h+var_1C8], 0
0x1802fdfe1  mov     dword ptr [rsp+200h+var_1C8+4], 80000000h
0x1802fdfe9  lea     rcx, [rsp+200h+var_1D0]
0x1802fdfee  call    ??$NewTop@N@CArrayImpl@Ofc@@IEAAAEANXZ; Ofc::CArrayImpl::NewTop<double>(void)
0x1802fdff3  mov     rbx, 400C000000000000h
0x1802fdffd  mov     [rax], rbx
0x1802fe000  mov     eax, dword ptr [rsp+200h+var_1C8+4]
0x1802fe004  btr     eax, 1Fh
0x1802fe008  mov     ecx, dword ptr [rsp+200h+var_1C8]
0x1802fe00c  cmp     ecx, eax
0x1802fe00e  jb      short loc_1802FE030
0x1802fe010  mov     rdx, qword ptr [rsp+200h+var_1D0]
0x1802fe015  test    rdx, rdx
0x1802fe018  jz      short loc_1802FE030
0x1802fe01a  lea     r8, qword_180C45A38
0x1802fe021  cmp     rdx, r8
0x1802fe024  ja      short loc_1802FE030
0x1802fe026  lea     ecx, ds:0[rcx*8]
0x1802fe02d  add     rcx, rdx
0x1802fe030  lea     rcx, [rsp+200h+var_1D0]
0x1802fe035  call    ??$NewTop@N@CArrayImpl@Ofc@@IEAAAEANXZ; Ofc::CArrayImpl::NewTop<double>(void)
0x1802fe03a  mov     [rax], rbx
0x1802fe03d  mov     rcx, [rsp+200h+var_1C0]
0x1802fe042  mov     rax, [rcx]
0x1802fe045  lea     rdx, [rsp+200h+var_1D0]
0x1802fe04a  mov     rax, [rax+60h]
0x1802fe04e  call    cs:__guard_dispatch_icall_fptr
0x1802fe054  mov     rcx, [rsp+200h+var_1C0]
0x1802fe059  mov     rax, [rcx]
0x1802fe05c  xor     edx, edx
0x1802fe05e  mov     rax, [rax+70h]
0x1802fe062  call    cs:__guard_dispatch_icall_fptr
0x1802fe068  mov     rbx, qword ptr [rsp+200h+var_1B8]
0x1802fe06d  mov     rax, [rbx]
0x1802fe070  mov     rdi, [rax+90h]
0x1802fe077  mov     r8, [rsp+200h+var_1C0]
0x1802fe07c  mov     rdx, r14
0x1802fe07f  lea     rcx, [rbp+100h+arg_10]
0x1802fe086  call    cs:__imp_?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z; GEL::IEffectPennedPath::Create(GEL::IPath const &,GEL::IPen const &)
0x1802fe08c  nop
0x1802fe08d  mov     rdx, [rax]
0x1802fe090  mov     rcx, rbx
0x1802fe093  mov     rax, rdi
0x1802fe096  call    cs:__guard_dispatch_icall_fptr
0x1802fe09c  nop
0x1802fe09d  mov     rcx, [rbp+100h+arg_10]
0x1802fe0a4  test    rcx, rcx
0x1802fe0a7  jz      short loc_1802FE0B6
0x1802fe0a9  mov     rax, [rcx]
0x1802fe0ac  mov     rax, [rax+8]
  ... truncated ...
```
