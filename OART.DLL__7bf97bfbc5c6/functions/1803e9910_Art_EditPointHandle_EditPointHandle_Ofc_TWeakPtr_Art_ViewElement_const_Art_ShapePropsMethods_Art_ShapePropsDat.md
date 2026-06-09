# Art::EditPointHandle::EditPointHandle(Ofc::TWeakPtr<Art::ViewElement> const &,Art::ShapePropsMethods<Art::ShapePropsData_<0>> const &,GEL::Point const &,uint,Art::SelectionHandleInfo::HandleShape)

- ea: `0x1803e9910`
- end: `0x1803e9e8a`
- name: `??0EditPointHandle@Art@@QEAA@AEBV?$TWeakPtr@VViewElement@Art@@@Ofc@@AEBV?$ShapePropsMethods@V?$ShapePropsData_@$0A@@Art@@@1@AEBUPoint@GEL@@IW4HandleShape@SelectionHandleInfo@1@@Z`
- size: `1402`
- prototype: `__int64 __usercall@<rax>(Art::ViewElement *this@<rcx>, int)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1803e9858`

## callees

- `0x180009c30`
- `0x18001df00`
- `0x180024f50`
- `0x180037370`
- `0x180070fe0`
- `0x1800713c0`
- `0x180071720`
- `0x18014bc30`
- `0x180152a10`
- `0x180185e40`
- `0x1801895a8`
- `0x1801c0940`
- `0x1801c2ad8`
- `0x1801c81e0`
- `0x1801f47c0`
- `0x1801fa040`
- `0x1801fb5f0`
- `0x180213758`
- `0x1803503a0`
- `0x1803e9910`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`

## import_xrefs

- `gfx!?GetSmallHandleLength@SelectionHandleConfig@GEL@@SAMAEBV?$TConvertibleDPI2@M@Gfx@@@Z` at `0x1803e9a6b`
- `gfx!?GetSmallHandleLength@SelectionHandleConfig@GEL@@SAMAEBV?$TConvertibleDPI2@M@Gfx@@@Z` at `0x1803e9cc1`
- `gfx!?GetSmallHandleLength@SelectionHandleConfig@GEL@@SAMAEBV?$TConvertibleDPI2@M@Gfx@@@Z` at `0x1803e9a6b`
- `gfx!?GetSmallHandleLength@SelectionHandleConfig@GEL@@SAMAEBV?$TConvertibleDPI2@M@Gfx@@@Z` at `0x1803e9cc1`
- `gfx!?Create@IEffectAliased@GEL@@SA?AV?$TCntPtr@UIEffectAliased@GEL@@@Ofc@@AEBUIEffect@2@@Z` at `0x1803e9c6f`
- `gfx!?Create@IEffectAliased@GEL@@SA?AV?$TCntPtr@UIEffectAliased@GEL@@@Ofc@@AEBUIEffect@2@@Z` at `0x1803e9d76`
- `gfx!?Create@IEffectAliased@GEL@@SA?AV?$TCntPtr@UIEffectAliased@GEL@@@Ofc@@AEBUIEffect@2@@Z` at `0x1803e9c6f`
- `gfx!?Create@IEffectAliased@GEL@@SA?AV?$TCntPtr@UIEffectAliased@GEL@@@Ofc@@AEBUIEffect@2@@Z` at `0x1803e9d76`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z` at `0x1803e9c61`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z` at `0x1803e9d67`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z` at `0x1803e9c61`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z` at `0x1803e9d67`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@W4RenderingPolicy@Gfx@@@Z` at `0x1803e9dd5`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@W4RenderingPolicy@Gfx@@@Z` at `0x1803e9dd5`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1803e9a89`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x1803e9a89`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x1803e9c1b`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x1803e9d21`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x1803e9c1b`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x1803e9d21`

## pseudocode

```c
Art::ViewElement *__fastcall Art::EditPointHandle::EditPointHandle(
        Art::ViewElement *this,
        struct Ofc::CProxyPtrImpl **a2,
        __int64 a3,
        double *a4,
        int a5)
{
  struct Ofc::CProxyPtrImpl **View; // rax
  char *Checked; // rbx
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  double ViewPixelToHostEMUScale; // xmm7_8
  char *v15; // rax
  double v16; // xmm6_8
  Art *v17; // rcx
  char *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // r10
  void (__fastcall *v22)(__int64, double *, __int64, struct Ofc::CProxyPtrImpl **, __int64 *); // rax
  __int64 v23; // r8
  __int64 v24; // r10
  void (__fastcall *v25)(__int64, double *, _QWORD, __int64 *, struct Ofc::CProxyPtrImpl **); // rax
  double v26; // xmm3_8
  double v27; // xmm2_8
  __int64 *v28; // rax
  __int64 v29; // rsi
  __int64 v30; // rbx
  void (__fastcall *v31)(__int64, _QWORD); // rdi
  _QWORD *v32; // rax
  _QWORD *v33; // rax
  char *v34; // rax
  double v35; // xmm3_8
  double v36; // xmm2_8
  __int64 *v37; // rax
  __int64 v38; // r14
  __int64 v39; // rbx
  void (__fastcall *v40)(__int64, _QWORD); // rdi
  _QWORD *v41; // rax
  _QWORD *v42; // rax
  unsigned int RenderingPolicy; // eax
  struct GEL::ITopLevelEffect **v44; // rax
  struct Ofc::CProxyPtrImpl *v46; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A8h] BYREF
  Ofc::CProxyPtrImpl *v48; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v49; // [rsp+70h] [rbp-98h] BYREF
  __int64 v50; // [rsp+78h] [rbp-90h] BYREF
  double v51; // [rsp+80h] [rbp-88h] BYREF
  __int128 v52; // [rsp+88h] [rbp-80h]
  double v53; // [rsp+98h] [rbp-70h]
  double v54; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v55; // [rsp+A8h] [rbp-60h]
  double v56; // [rsp+B8h] [rbp-50h]
  __int128 v57; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v58; // [rsp+D0h] [rbp-38h] BYREF
  Art::ViewElement *v59; // [rsp+E0h] [rbp-28h]
  __int64 v60; // [rsp+E8h] [rbp-20h]
  __int64 v61; // [rsp+F0h] [rbp-18h]
  _BYTE v62[48]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v63[160]; // [rsp+128h] [rbp+20h] BYREF
  int v64; // [rsp+1C8h] [rbp+C0h]

  v59 = this;
  Art::SelectionHandleViewElement::SelectionHandleViewElement(this, 6, 65, 0, 0, 0);
  *(_QWORD *)this = &Art::EditPointHandle::`vftable';
  *((_DWORD *)this + 72) = a5;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  View = (struct Ofc::CProxyPtrImpl **)Art::ViewElement::GetView(this);
  v48 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*View);
  v46 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*a2);
  Checked = (char *)Ofc::CProxyPtrImpl::GetChecked(v46);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v46);
  v11 = Ofc::TPropertySet<Art::SolidColorFillPropsIDs>::GetIfValid<Art::FlPr::color>(a3, Checked + 72);
  Art::GetGelTransform(v62, v11);
  v12 = Ofc::Round<__int64,double>();
  Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator=((char *)this + 296, v12);
  v13 = Ofc::Round<__int64,double>();
  Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator=((char *)this + 304, v13);
  Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator+=((char *)this + 296, v11);
  Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator+=((char *)this + 304, v11 + 8);
  ViewPixelToHostEMUScale = Art::GetViewPixelToHostEMUScale(&v48);
  v15 = (char *)Ofc::CProxyPtrImpl::GetChecked(v48);
  v16 = GEL::SelectionHandleConfig::GetSmallHandleLength(v15 + 160) * ViewPixelToHostEMUScale * 0.5;
  GEL::IEffectContainer::Create(&v49);
  v58 = 0;
  v57 = 0;
  Art::SelectionHandleConfig::GetSelectionAdornmentColor(&v58, 11);
  Art::SelectionHandleConfig::GetSelectionAdornmentColor(&v57, 12);
  if ( Art::FInHighContrastMode(v17) )
  {
    Art::View::Info::Info((Art::View::Info *)v63);
    v18 = (char *)Ofc::CProxyPtrImpl::GetChecked(v48);
    Art::View::Info::operator=(v63, v18 + 40);
    v54 = 0.0;
    v55 = 0;
    v51 = 0.0;
    v52 = 0;
    v19 = Ofc::TSingleton<Art::GelTranslator>::Instance();
    (*(void (__fastcall **)(__int64, __int128 *, double *))(*(_QWORD *)v19 + 120LL))(v19, &v58, &v54);
    v20 = Ofc::TSingleton<Art::GelTranslator>::Instance();
    (*(void (__fastcall **)(__int64, __int128 *, double *))(*(_QWORD *)v20 + 120LL))(v20, &v57, &v51);
    v21 = Ofc::TSingleton<Art::GelTranslator>::Instance();
    v22 = *(void (__fastcall **)(__int64, double *, __int64, struct Ofc::CProxyPtrImpl **, __int64 *))(*(_QWORD *)v21 + 40LL);
    LODWORD(v47) = 1;
    LODWORD(v46) = v64;
    LOBYTE(v23) = 1;
    v22(v21, &v51, v23, &v46, &v47);
    v24 = Ofc::TSingleton<Art::GelTranslator>::Instance();
    v25 = *(void (__fastcall **)(__int64, double *, _QWORD, __int64 *, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)v24 + 40LL);
    LODWORD(v46) = 1;
    LODWORD(v47) = v64;
    v25(v24, &v54, 0, &v47, &v46);
    Art::Color::~Color((Art::Color *)&v51);
    Art::Color::~Color((Art::Color *)&v54);
    Art::View::Info::~Info((Art::View::Info *)v63);
  }
  v26 = a4[1];
  v27 = *a4;
  v54 = *a4 - v16;
  *(double *)&v55 = v26 - v16;
  *((double *)&v55 + 1) = v27 + v16;
  v56 = v26 + v16;
  v28 = (__int64 *)GEL::IRectanglePath::Create(&v46, &v54);
  v29 = *v28;
  *v28 = 0;
  v60 = v29;
  if ( v46 )
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v46 + 8LL))(v46);
  v30 = v49;
  v31 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 144LL);
  v32 = (_QWORD *)GEL::IEffectFilledPath::Create(&v50, v29, &v57);
  v33 = (_QWORD *)GEL::IEffectAliased::Create(&v47, *v32);
  v31(v30, *v33);
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
  v34 = (char *)Ofc::CProxyPtrImpl::GetChecked(v48);
  v35 = (GEL::SelectionHandleConfig::GetSmallHandleLength(v34 + 160) * 0.5 - 1.0) * ViewPixelToHostEMUScale;
  v36 = *a4;
  v51 = *a4 - v35;
  *(double *)&v52 = a4[1] - v35;
  *((double *)&v52 + 1) = v36 + v35;
  v53 = v35 + a4[1];
  v37 = (__int64 *)GEL::IRectanglePath::Create(&v50, &v51);
  v38 = *v37;
  *v37 = 0;
  v61 = v38;
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
  v39 = v49;
  v40 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 144LL);
  v41 = (_QWORD *)GEL::IEffectFilledPath::Create(&v47, v38, &v58);
  v42 = (_QWORD *)GEL::IEffectAliased::Create(&v46, *v41);
  v40(v39, *v42);
  if ( v46 )
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v46 + 8LL))(v46);
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
  RenderingPolicy = Art::SelectionHandleViewElement::GetRenderingPolicy(this);
  v44 = (struct GEL::ITopLevelEffect **)GEL::ITopLevelEffect::Create(&v46, v49, v62, RenderingPolicy);
  Art::ViewElement::SetEffect(this, *v44);
  if ( v46 )
    (*(void (__fastcall **)(char *))(*((_QWORD *)v46 + 1) + 8LL))((char *)v46 + 8);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 8LL))(v38);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v48);
  return this;
}

```

## disassembly

```asm
0x1803e9910  mov     rax, rsp
0x1803e9913  push    rbp
0x1803e9914  push    rbx
0x1803e9915  push    rsi
0x1803e9916  push    rdi
0x1803e9917  push    r12
0x1803e9919  push    r14
0x1803e991b  push    r15
0x1803e991d  lea     rbp, [rax-148h]
0x1803e9924  sub     rsp, 210h
0x1803e992b  movaps  xmmword ptr [rax-48h], xmm6
0x1803e992f  movaps  xmmword ptr [rax-58h], xmm7
0x1803e9933  mov     rax, cs:__security_cookie
0x1803e993a  xor     rax, rsp
0x1803e993d  mov     [rbp+140h+var_60], rax
0x1803e9944  mov     r15, r9
0x1803e9947  mov     r14, r8
0x1803e994a  mov     rbx, rdx
0x1803e994d  mov     r12, rcx
0x1803e9950  mov     [rbp+140h+var_168], rcx
0x1803e9954  mov     [rsp+240h+var_200], 0; struct Art::Transform2D *
0x1803e995d  mov     [rsp+240h+var_208], 0; char
0x1803e9962  mov     [rsp+240h+var_210], 0; char
0x1803e9967  mov     [rsp+240h+var_218], 41h ; 'A'; int
0x1803e996f  mov     [rsp+240h+var_220], 6; int
0x1803e9977  xor     r9d, r9d
0x1803e997a  lea     r8d, [r9+2]
0x1803e997e  call    ??0SelectionHandleViewElement@Art@@IEAA@AEBV?$TWeakPtr@VViewElement@Art@@@Ofc@@W4HandleType@SelectionHandleInfo@1@W4HandleId@51@W4HandleShape@51@W4CursorID@Cursor@1@_N5PEBVTransform2D@1@@Z; Art::SelectionHandleViewElement::SelectionHandleViewElement(Ofc::TWeakPtr<Art::ViewElement> const &,Art::SelectionHandleInfo::HandleType,Art::SelectionHandleInfo::HandleId,Art::SelectionHandleInfo::HandleShape,Art::Cursor::CursorID,bool,bool,Art::Transform2D const *)
0x1803e9983  lea     rax, ??_7EditPointHandle@Art@@6B@; const Art::EditPointHandle::`vftable'
0x1803e998a  mov     [r12], rax
0x1803e998e  mov     eax, [rbp+140h+arg_20]
0x1803e9994  mov     [r12+120h], eax
0x1803e999c  lea     rdi, [r12+128h]
0x1803e99a4  mov     qword ptr [rdi], 0
0x1803e99ab  lea     rsi, [rdi+8]
0x1803e99af  mov     qword ptr [rsi], 0
0x1803e99b6  mov     rcx, r12
0x1803e99b9  call    ?GetView@ViewElement@Art@@QEAAAEBV?$TWeakPtr@VView@Art@@@Ofc@@XZ; Art::ViewElement::GetView(void)
0x1803e99be  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x1803e99c1  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1803e99c6  mov     [rsp+240h+var_1E0], rax
0x1803e99cb  mov     rcx, [rbx]; struct Ofc::CProxyPtrImpl *
0x1803e99ce  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1803e99d3  mov     [rsp+240h+var_1F0], rax
0x1803e99d8  mov     rcx, rax; this
0x1803e99db  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803e99e0  mov     rbx, rax
0x1803e99e3  lea     rcx, [rsp+240h+var_1F0]; struct Ofc::CProxyPtrImpl **
0x1803e99e8  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1803e99ed  lea     rdx, [rbx+48h]
0x1803e99f1  mov     rcx, r14
0x1803e99f4  call    ??$GetIfValid@Ucolor@FlPr@Art@@@?$TPropertySet@VSolidColorFillPropsIDs@Art@@@Ofc@@QEBAAEBVColor@Art@@AEBV23@@Z; Ofc::TPropertySet<Art::SolidColorFillPropsIDs>::GetIfValid<Art::FlPr::color>(Art::Color const &)
0x1803e99f9  mov     rbx, rax
0x1803e99fc  mov     rdx, rax
0x1803e99ff  lea     rcx, [rbp+140h+var_150]
0x1803e9a03  call    ?GetGelTransform@Art@@YA?AU?$TAffine3x3@N@Math@@AEBVTransform2D@1@@Z; Art::GetGelTransform(Art::Transform2D const &)
0x1803e9a08  movsd   xmm0, qword ptr [r15]
0x1803e9a0d  call    ??$Round@_JN@Ofc@@YA_JN@Z; Ofc::Round<__int64,double>(double)
0x1803e9a12  mov     rdx, rax
0x1803e9a15  mov     rcx, rdi
0x1803e9a18  call    ??4?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAAAEAV01@_J@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator=(__int64)
0x1803e9a1d  movsd   xmm0, qword ptr [r15+8]
0x1803e9a23  call    ??$Round@_JN@Ofc@@YA_JN@Z; Ofc::Round<__int64,double>(double)
0x1803e9a28  mov     rdx, rax
0x1803e9a2b  mov     rcx, rsi
0x1803e9a2e  call    ??4?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAAAEAV01@_J@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator=(__int64)
0x1803e9a33  mov     rdx, rbx
0x1803e9a36  mov     rcx, rdi
0x1803e9a39  call    ??Y?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAAAEAV01@AEBV01@@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator+=(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &)
0x1803e9a3e  lea     rdx, [rbx+8]
0x1803e9a42  mov     rcx, rsi
0x1803e9a45  call    ??Y?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAAAEAV01@AEBV01@@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator+=(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &)
0x1803e9a4a  lea     rcx, [rsp+240h+var_1E0]
0x1803e9a4f  call    ?GetViewPixelToHostEMUScale@Art@@YANAEBV?$TSharedPtr@$$CBVView@Art@@@Ofc@@@Z; Art::GetViewPixelToHostEMUScale(Ofc::TSharedPtr<Art::View const> const &)
0x1803e9a54  movaps  xmm7, xmm0
0x1803e9a57  mov     rcx, [rsp+240h+var_1E0]; this
0x1803e9a5c  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803e9a61  mov     r14d, 0A0h
0x1803e9a67  lea     rcx, [r14+rax]
0x1803e9a6b  call    cs:__imp_?GetSmallHandleLength@SelectionHandleConfig@GEL@@SAMAEBV?$TConvertibleDPI2@M@Gfx@@@Z; GEL::SelectionHandleConfig::GetSmallHandleLength(Gfx::TConvertibleDPI2<float> const &)
0x1803e9a71  xorps   xmm6, xmm6
0x1803e9a74  cvtss2sd xmm6, xmm0
0x1803e9a78  mulsd   xmm6, xmm7
0x1803e9a7c  mulsd   xmm6, cs:__real@3fe0000000000000
0x1803e9a84  lea     rcx, [rsp+240h+var_1D8]
0x1803e9a89  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x1803e9a8f  nop
0x1803e9a90  xorps   xmm0, xmm0
0x1803e9a93  movups  [rbp+140h+var_178], xmm0
0x1803e9a97  xorps   xmm1, xmm1
0x1803e9a9a  movups  [rbp+140h+var_188], xmm1
0x1803e9a9e  mov     edx, 0Bh
0x1803e9aa3  lea     rcx, [rbp+140h+var_178]
0x1803e9aa7  call    ?GetSelectionAdornmentColor@SelectionHandleConfig@Art@@SAXAEAUColor@GEL@@W4OartSelectionAdornmentsSwatch@UIColor@Mso@@@Z; Art::SelectionHandleConfig::GetSelectionAdornmentColor(GEL::Color &,Mso::UIColor::OartSelectionAdornmentsSwatch)
0x1803e9aac  mov     edx, 0Ch
0x1803e9ab1  lea     rcx, [rbp+140h+var_188]
0x1803e9ab5  call    ?GetSelectionAdornmentColor@SelectionHandleConfig@Art@@SAXAEAUColor@GEL@@W4OartSelectionAdornmentsSwatch@UIColor@Mso@@@Z; Art::SelectionHandleConfig::GetSelectionAdornmentColor(GEL::Color &,Mso::UIColor::OartSelectionAdornmentsSwatch)
0x1803e9aba  call    ?FInHighContrastMode@Art@@YA_NXZ; Art::FInHighContrastMode(void)
0x1803e9abf  test    al, al
0x1803e9ac1  jz      loc_1803E9BDD
0x1803e9ac7  lea     rcx, [rbp+140h+var_120]; this
0x1803e9acb  call    ??0Info@View@Art@@QEAA@XZ; Art::View::Info::Info(void)
0x1803e9ad0  mov     rcx, [rsp+240h+var_1E0]; this
0x1803e9ad5  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803e9ada  lea     rdx, [rax+28h]
0x1803e9ade  lea     rcx, [rbp+140h+var_120]
0x1803e9ae2  call    ??4Info@View@Art@@QEAAAEAU012@AEBU012@@Z; Art::View::Info::operator=(Art::View::Info const &)
0x1803e9ae7  xor     eax, eax
0x1803e9ae9  mov     [rbp+140h+var_1A8], rax
0x1803e9aed  xorps   xmm0, xmm0
0x1803e9af0  movdqu  [rbp+140h+var_1A0], xmm0
0x1803e9af5  mov     [rsp+240h+var_1C8], rax
0x1803e9afa  movdqu  [rbp+140h+var_1C0], xmm0
0x1803e9aff  call    ?Instance@?$TSingleton@VGelTranslator@Art@@@Ofc@@SAAEAVGelTranslator@Art@@XZ; Ofc::TSingleton<Art::GelTranslator>::Instance(void)
0x1803e9b04  mov     r9, rax
0x1803e9b07  mov     rcx, [rax]
0x1803e9b0a  mov     rax, [rcx+78h]
0x1803e9b0e  lea     r8, [rbp+140h+var_1A8]
0x1803e9b12  lea     rdx, [rbp+140h+var_178]
0x1803e9b16  mov     rcx, r9
0x1803e9b19  call    cs:__guard_dispatch_icall_fptr
0x1803e9b1f  nop
0x1803e9b20  call    ?Instance@?$TSingleton@VGelTranslator@Art@@@Ofc@@SAAEAVGelTranslator@Art@@XZ; Ofc::TSingleton<Art::GelTranslator>::Instance(void)
0x1803e9b25  mov     r9, rax
0x1803e9b28  mov     rcx, [rax]
0x1803e9b2b  mov     rax, [rcx+78h]
0x1803e9b2f  lea     r8, [rsp+240h+var_1C8]
0x1803e9b34  lea     rdx, [rbp+140h+var_188]
0x1803e9b38  mov     rcx, r9
0x1803e9b3b  call    cs:__guard_dispatch_icall_fptr
0x1803e9b41  nop
0x1803e9b42  call    ?Instance@?$TSingleton@VGelTranslator@Art@@@Ofc@@SAAEAVGelTranslator@Art@@XZ; Ofc::TSingleton<Art::GelTranslator>::Instance(void)
0x1803e9b47  mov     r10, rax
0x1803e9b4a  mov     rcx, [rax]
0x1803e9b4d  mov     rax, [rcx+28h]
0x1803e9b51  mov     ebx, 1
0x1803e9b56  mov     dword ptr [rsp+240h+var_1E8], ebx
0x1803e9b5a  mov     ecx, [rbp+140h+var_80]
0x1803e9b60  mov     dword ptr [rsp+240h+var_1F0], ecx
0x1803e9b64  lea     rcx, [rsp+240h+var_1E8]
0x1803e9b69  mov     qword ptr [rsp+240h+var_220], rcx
0x1803e9b6e  lea     r9, [rsp+240h+var_1F0]
0x1803e9b73  mov     r8b, bl
0x1803e9b76  lea     rdx, [rsp+240h+var_1C8]
0x1803e9b7b  mov     rcx, r10
0x1803e9b7e  call    cs:__guard_dispatch_icall_fptr
0x1803e9b84  nop
0x1803e9b85  call    ?Instance@?$TSingleton@VGelTranslator@Art@@@Ofc@@SAAEAVGelTranslator@Art@@XZ; Ofc::TSingleton<Art::GelTranslator>::Instance(void)
0x1803e9b8a  mov     r10, rax
0x1803e9b8d  mov     rcx, [rax]
0x1803e9b90  mov     rax, [rcx+28h]
0x1803e9b94  mov     dword ptr [rsp+240h+var_1F0], ebx
0x1803e9b98  mov     ecx, [rbp+140h+var_80]
0x1803e9b9e  mov     dword ptr [rsp+240h+var_1E8], ecx
0x1803e9ba2  lea     rcx, [rsp+240h+var_1F0]
0x1803e9ba7  mov     qword ptr [rsp+240h+var_220], rcx
0x1803e9bac  lea     r9, [rsp+240h+var_1E8]
0x1803e9bb1  xor     r8d, r8d
0x1803e9bb4  lea     rdx, [rbp+140h+var_1A8]
0x1803e9bb8  mov     rcx, r10
0x1803e9bbb  call    cs:__guard_dispatch_icall_fptr
0x1803e9bc1  lea     rcx, [rsp+240h+var_1C8]; this
0x1803e9bc6  call    ??1Color@Art@@QEAA@XZ; Art::Color::~Color(void)
0x1803e9bcb  lea     rcx, [rbp+140h+var_1A8]; this
0x1803e9bcf  call    ??1Color@Art@@QEAA@XZ; Art::Color::~Color(void)
0x1803e9bd4  lea     rcx, [rbp+140h+var_120]; this
0x1803e9bd8  call    ??1Info@View@Art@@QEAA@XZ; Art::View::Info::~Info(void)
0x1803e9bdd  movsd   xmm3, qword ptr [r15+8]
0x1803e9be3  movsd   xmm2, qword ptr [r15]
0x1803e9be8  movaps  xmm0, xmm2
0x1803e9beb  subsd   xmm0, xmm6
0x1803e9bef  movsd   [rbp+140h+var_1A8], xmm0
0x1803e9bf4  movaps  xmm1, xmm3
0x1803e9bf7  subsd   xmm1, xmm6
0x1803e9bfb  movsd   qword ptr [rbp+140h+var_1A0], xmm1
0x1803e9c00  addsd   xmm2, xmm6
0x1803e9c04  movsd   qword ptr [rbp+140h+var_1A0+8], xmm2
0x1803e9c09  addsd   xmm3, xmm6
0x1803e9c0d  movsd   [rbp+140h+var_190], xmm3
0x1803e9c12  lea     rdx, [rbp+140h+var_1A8]
0x1803e9c16  lea     rcx, [rsp+240h+var_1F0]
0x1803e9c1b  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x1803e9c21  mov     rsi, [rax]
0x1803e9c24  mov     qword ptr [rax], 0
0x1803e9c2b  mov     [rbp+140h+var_160], rsi
0x1803e9c2f  mov     rcx, [rsp+240h+var_1F0]
0x1803e9c34  test    rcx, rcx
0x1803e9c37  jz      short loc_1803E9C46
0x1803e9c39  mov     rax, [rcx]
0x1803e9c3c  mov     rax, [rax+8]
0x1803e9c40  call    cs:__guard_dispatch_icall_fptr
0x1803e9c46  mov     rbx, [rsp+240h+var_1D8]
0x1803e9c4b  mov     rax, [rbx]
0x1803e9c4e  mov     rdi, [rax+90h]
0x1803e9c55  lea     r8, [rbp+140h+var_188]
0x1803e9c59  mov     rdx, rsi
0x1803e9c5c  lea     rcx, [rsp+240h+var_1D0]
0x1803e9c61  call    cs:__imp_?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::Color const &)
0x1803e9c67  mov     rdx, [rax]
0x1803e9c6a  lea     rcx, [rsp+240h+var_1E8]
0x1803e9c6f  call    cs:__imp_?Create@IEffectAliased@GEL@@SA?AV?$TCntPtr@UIEffectAliased@GEL@@@Ofc@@AEBUIEffect@2@@Z; GEL::IEffectAliased::Create(GEL::IEffect const &)
0x1803e9c75  mov     rdx, [rax]
0x1803e9c78  mov     rcx, rbx
0x1803e9c7b  mov     rax, rdi
0x1803e9c7e  call    cs:__guard_dispatch_icall_fptr
0x1803e9c84  mov     rcx, [rsp+240h+var_1E8]
0x1803e9c89  test    rcx, rcx
0x1803e9c8c  jz      short loc_1803E9C9C
0x1803e9c8e  mov     rax, [rcx]
0x1803e9c91  mov     rax, [rax+8]
0x1803e9c95  call    cs:__guard_dispatch_icall_fptr
0x1803e9c9b  nop
0x1803e9c9c  mov     rcx, [rsp+240h+var_1D0]
0x1803e9ca1  test    rcx, rcx
0x1803e9ca4  jz      short loc_1803E9CB3
0x1803e9ca6  mov     rax, [rcx]
0x1803e9ca9  mov     rax, [rax+8]
0x1803e9cad  call    cs:__guard_dispatch_icall_fptr
0x1803e9cb3  mov     rcx, [rsp+240h+var_1E0]; this
0x1803e9cb8  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1803e9cbd  lea     rcx, [r14+rax]
0x1803e9cc1  call    cs:__imp_?GetSmallHandleLength@SelectionHandleConfig@GEL@@SAMAEBV?$TConvertibleDPI2@M@Gfx@@@Z; GEL::SelectionHandleConfig::GetSmallHandleLength(Gfx::TConvertibleDPI2<float> const &)
0x1803e9cc7  xorps   xmm3, xmm3
0x1803e9cca  cvtss2sd xmm3, xmm0
0x1803e9cce  mulsd   xmm3, cs:__real@3fe0000000000000
0x1803e9cd6  subsd   xmm3, cs:__real@3ff0000000000000
0x1803e9cde  mulsd   xmm3, xmm7
0x1803e9ce2  movsd   xmm2, qword ptr [r15]
0x1803e9ce7  movaps  xmm0, xmm2
0x1803e9cea  subsd   xmm0, xmm3
0x1803e9cee  movsd   [rsp+240h+var_1C8], xmm0
0x1803e9cf4  movsd   xmm1, qword ptr [r15+8]
0x1803e9cfa  subsd   xmm1, xmm3
0x1803e9cfe  movsd   qword ptr [rbp+140h+var_1C0], xmm1
0x1803e9d03  addsd   xmm2, xmm3
0x1803e9d07  movsd   qword ptr [rbp+140h+var_1C0+8], xmm2
0x1803e9d0c  addsd   xmm3, qword ptr [r15+8]
0x1803e9d12  movsd   [rbp+140h+var_1B0], xmm3
0x1803e9d17  lea     rdx, [rsp+240h+var_1C8]
0x1803e9d1c  lea     rcx, [rsp+240h+var_1D0]
0x1803e9d21  call    cs:__imp_?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z; GEL::IRectanglePath::Create(Math::TRect<double> const &)
0x1803e9d27  mov     r14, [rax]
0x1803e9d2a  mov     qword ptr [rax], 0
0x1803e9d31  mov     [rbp+140h+var_158], r14
0x1803e9d35  mov     rcx, [rsp+240h+var_1D0]
0x1803e9d3a  test    rcx, rcx
0x1803e9d3d  jz      short loc_1803E9D4C
0x1803e9d3f  mov     rax, [rcx]
0x1803e9d42  mov     rax, [rax+8]
0x1803e9d46  call    cs:__guard_dispatch_icall_fptr
0x1803e9d4c  mov     rbx, [rsp+240h+var_1D8]
0x1803e9d51  mov     rax, [rbx]
0x1803e9d54  mov     rdi, [rax+90h]
0x1803e9d5b  lea     r8, [rbp+140h+var_178]
0x1803e9d5f  mov     rdx, r14
0x1803e9d62  lea     rcx, [rsp+240h+var_1E8]
0x1803e9d67  call    cs:__imp_?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z; GEL::IEffectFilledPath::Create(GEL::IPath const &,GEL::Color const &)
0x1803e9d6d  nop
0x1803e9d6e  mov     rdx, [rax]
0x1803e9d71  lea     rcx, [rsp+240h+var_1F0]
0x1803e9d76  call    cs:__imp_?Create@IEffectAliased@GEL@@SA?AV?$TCntPtr@UIEffectAliased@GEL@@@Ofc@@AEBUIEffect@2@@Z; GEL::IEffectAliased::Create(GEL::IEffect const &)
0x1803e9d7c  nop
0x1803e9d7d  mov     rdx, [rax]
0x1803e9d80  mov     rcx, rbx
0x1803e9d83  mov     rax, rdi
0x1803e9d86  call    cs:__guard_dispatch_icall_fptr
0x1803e9d8c  nop
0x1803e9d8d  mov     rcx, [rsp+240h+var_1F0]
0x1803e9d92  test    rcx, rcx
0x1803e9d95  jz      short loc_1803E9DA5
0x1803e9d97  mov     rax, [rcx]
0x1803e9d9a  mov     rax, [rax+8]
0x1803e9d9e  call    cs:__guard_dispatch_icall_fptr
0x1803e9da4  nop
0x1803e9da5  mov     rcx, [rsp+240h+var_1E8]
0x1803e9daa  test    rcx, rcx
0x1803e9dad  jz      short loc_1803E9DBC
0x1803e9daf  mov     rax, [rcx]
0x1803e9db2  mov     rax, [rax+8]
0x1803e9db6  call    cs:__guard_dispatch_icall_fptr
0x1803e9dbc  mov     rcx, r12
0x1803e9dbf  call    ?GetRenderingPolicy@SelectionHandleViewElement@Art@@UEBA?AW4RenderingPolicy@Gfx@@XZ; Art::SelectionHandleViewElement::GetRenderingPolicy(void)
0x1803e9dc4  mov     r9d, eax
0x1803e9dc7  lea     r8, [rbp+140h+var_150]
0x1803e9dcb  mov     rdx, [rsp+240h+var_1D8]
0x1803e9dd0  lea     rcx, [rsp+240h+var_1F0]
0x1803e9dd5  call    cs:__imp_?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@W4RenderingPolicy@Gfx@@@Z; GEL::ITopLevelEffect::Create(GEL::IEffect const &,Math::TAffine3x3<double> const &,Gfx::RenderingPolicy)
0x1803e9ddb  mov     rdx, [rax]; struct GEL::ITopLevelEffect *
0x1803e9dde  mov     rcx, r12; this
0x1803e9de1  call    ?SetEffect@ViewElement@Art@@IEAAXAEAUITopLevelEffect@GEL@@@Z; Art::ViewElement::SetEffect(GEL::ITopLevelEffect &)
0x1803e9de6  mov     rax, [rsp+240h+var_1F0]
0x1803e9deb  test    rax, rax
0x1803e9dee  jz      short loc_1803E9E02
0x1803e9df0  lea     rcx, [rax+8]
0x1803e9df4  mov     rax, [rcx]
0x1803e9df7  mov     rax, [rax+8]
0x1803e9dfb  call    cs:__guard_dispatch_icall_fptr
0x1803e9e01  nop
0x1803e9e02  test    r14, r14
0x1803e9e05  jz      short loc_1803E9E20
  ... truncated ...
```
