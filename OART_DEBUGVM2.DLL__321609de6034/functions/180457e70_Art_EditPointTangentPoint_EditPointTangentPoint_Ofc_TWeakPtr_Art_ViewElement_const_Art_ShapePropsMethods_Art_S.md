# Art::EditPointTangentPoint::EditPointTangentPoint(Ofc::TWeakPtr<Art::ViewElement> const &,Art::ShapePropsMethods<Art::ShapePropsData_<0>> const &,GEL::Point const &,uint,Art::SelectionHandleInfo::HandleShape)

- ea: `0x180457e70`
- end: `0x180458574`
- name: `??0EditPointTangentPoint@Art@@QEAA@AEBV?$TWeakPtr@VViewElement@Art@@@Ofc@@AEBV?$ShapePropsMethods@V?$ShapePropsData_@$0A@@Art@@@1@AEBUPoint@GEL@@IW4HandleShape@SelectionHandleInfo@1@@Z`
- size: `1796`
- prototype: `__int64 __usercall@<rax>(Art::ViewElement *this@<rcx>, int)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1807b2310`

## callees

- `0x18000eb20`
- `0x18002a690`
- `0x18002a750`
- `0x18005ae40`
- `0x1800d1790`
- `0x1800ef520`
- `0x1801061d0`
- `0x18010ccd0`
- `0x18010de00`
- `0x18011efe4`
- `0x18014fd70`
- `0x1801b8328`
- `0x1801b8810`
- `0x180210de4`
- `0x180245520`
- `0x180278de0`
- `0x180279030`
- `0x180279050`
- `0x1802f3f98`
- `0x1802fd204`
- `0x18030e410`
- `0x180457e70`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x1804580b1`
- `KERNEL32!DecodePointer` at `0x1804580c3`
- `KERNEL32!DecodePointer` at `0x18045815c`
- `KERNEL32!DecodePointer` at `0x18045816e`
- `KERNEL32!DecodePointer` at `0x180458207`
- `KERNEL32!DecodePointer` at `0x180458219`
- `KERNEL32!DecodePointer` at `0x1804582ce`
- `KERNEL32!DecodePointer` at `0x1804582e0`
- `KERNEL32!DecodePointer` at `0x1804580b1`
- `KERNEL32!DecodePointer` at `0x1804580c3`
- `KERNEL32!DecodePointer` at `0x18045815c`
- `KERNEL32!DecodePointer` at `0x18045816e`
- `KERNEL32!DecodePointer` at `0x180458207`
- `KERNEL32!DecodePointer` at `0x180458219`
- `KERNEL32!DecodePointer` at `0x1804582ce`
- `KERNEL32!DecodePointer` at `0x1804582e0`
- `gfx!?GetEditPointTangentPointLength@SelectionHandleConfig@GEL@@SAMAEBV?$TConvertibleDPI2@M@Gfx@@@Z` at `0x180457fc9`
- `gfx!?GetEditPointTangentPointLength@SelectionHandleConfig@GEL@@SAMAEBV?$TConvertibleDPI2@M@Gfx@@@Z` at `0x180457fc9`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z` at `0x1804583e1`
- `gfx!?Create@IEffectFilledPath@GEL@@SA?AV?$TCntPtr@UIEffectFilledPath@GEL@@@Ofc@@AEBUIPath@2@AEBUColor@2@@Z` at `0x1804583e1`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@W4RenderingPolicy@Gfx@@@Z` at `0x1804584c5`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBUIEffect@2@AEBU?$TAffine3x3@N@Math@@W4RenderingPolicy@Gfx@@@Z` at `0x1804584c5`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x18045847e`
- `gfx!?Create@IEffectPennedPath@GEL@@SA?AV?$TCntPtr@UIEffectPennedPath@GEL@@@Ofc@@AEBUIPath@2@AEBUIPen@2@@Z` at `0x18045847e`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x18045845b`
- `gfx!?Create@IPen@GEL@@SA?AV?$TCntPtr@UIPen@GEL@@@Ofc@@NAEBUColor@2@@Z` at `0x18045845b`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x180457fe7`
- `gfx!?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ` at `0x180457fe7`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x18045839a`
- `gfx!?Create@IRectanglePath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@AEBU?$TRect@N@Math@@@Z` at `0x18045839a`

## pseudocode

```c
Art::ViewElement *__fastcall Art::EditPointTangentPoint::EditPointTangentPoint(
        Art::ViewElement *this,
        struct Ofc::CProxyPtrImpl **a2,
        __int64 a3,
        __m128d *a4,
        int a5)
{
  struct Ofc::CProxyPtrImpl **View; // rax
  char *Checked; // rbx
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  double ViewPixelToHostEMUScale; // xmm6_8
  char *v15; // rax
  __m128d v16; // xmm7
  __m128d v17; // xmm6
  Art *v18; // rcx
  char *v19; // rax
  void (*v20)(void); // rdx
  bool v21; // r8
  void *v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned int v24; // r8d
  __int64 (__fastcall *v25)(__int64); // rax
  _QWORD *v26; // rax
  void (*v27)(void); // rdx
  bool v28; // r8
  void *v29; // rcx
  unsigned __int64 v30; // rdx
  unsigned int v31; // r8d
  __int64 (__fastcall *v32)(__int64); // rax
  _QWORD *v33; // rax
  void (*v34)(void); // rdx
  _BOOL8 v35; // r8
  __int64 *v36; // rcx
  unsigned __int64 v37; // rdx
  unsigned int v38; // r8d
  __int64 (__fastcall *v39)(__int64); // rax
  _QWORD *v40; // rax
  __int64 v41; // rax
  void (*v42)(void); // rdx
  bool v43; // r8
  __int64 *v44; // rcx
  unsigned __int64 v45; // rdx
  unsigned int v46; // r8d
  __int64 (__fastcall *v47)(__int64); // rax
  _QWORD *v48; // rax
  __int64 v49; // rax
  __m128d v50; // xmm1
  __int64 *v51; // rax
  __int64 v52; // rsi
  __int64 v53; // rbx
  void (__fastcall *v54)(__int64, _QWORD); // rdi
  _QWORD *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rbx
  void (__fastcall *v58)(__int64, _QWORD); // rdi
  _QWORD *v59; // rax
  unsigned int RenderingPolicy; // eax
  struct GEL::ITopLevelEffect **v61; // rax
  struct Ofc::CProxyPtrImpl *v63; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD *v64; // [rsp+60h] [rbp-A8h] BYREF
  Ofc::CProxyPtrImpl *v65; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v66; // [rsp+70h] [rbp-98h] BYREF
  __int64 v67; // [rsp+78h] [rbp-90h] BYREF
  __int64 v68; // [rsp+80h] [rbp-88h] BYREF
  __int128 v69; // [rsp+88h] [rbp-80h] BYREF
  __int128 v70; // [rsp+98h] [rbp-70h] BYREF
  __m256i v71; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v72; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v73; // [rsp+D0h] [rbp-38h]
  Art::ViewElement *v74; // [rsp+E0h] [rbp-28h]
  _BYTE v75[48]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v76[160]; // [rsp+118h] [rbp+10h] BYREF
  int v77; // [rsp+1B8h] [rbp+B0h]

  v74 = this;
  Art::SelectionHandleViewElement::SelectionHandleViewElement(this, 6, 65, 0, 0, 0);
  *(_QWORD *)this = &Art::EditPointTangentPoint::`vftable';
  *((_DWORD *)this + 72) = a5;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  View = (struct Ofc::CProxyPtrImpl **)Art::ViewElement::GetView(this);
  v65 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*View);
  v63 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*a2);
  Checked = (char *)Ofc::CProxyPtrImpl::GetChecked(v63);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v63);
  v11 = Ofc::TPropertySet<Art::SolidColorFillPropsIDs>::GetIfValid<Art::FlPr::color>(a3, Checked + 72);
  Art::GetGelTransform(v75, v11);
  v12 = Ofc::Round<__int64,double>();
  Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator=((char *)this + 296, v12);
  v13 = Ofc::Round<__int64,double>();
  Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator=((char *)this + 304, v13);
  Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator+=((char *)this + 296, v11);
  Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator+=((char *)this + 304, v11 + 8);
  ViewPixelToHostEMUScale = Art::GetViewPixelToHostEMUScale(&v65);
  v15 = (char *)Ofc::CProxyPtrImpl::GetChecked(v65);
  v16 = 0;
  v16.m128d_f64[0] = GEL::SelectionHandleConfig::GetEditPointTangentPointLength(v15 + 160)
                   * ViewPixelToHostEMUScale
                   * 0.5;
  GEL::IEffectContainer::Create(&v67);
  v69 = 0;
  v70 = 0;
  Art::SelectionHandleConfig::GetSelectionAdornmentColor(&v69, 14);
  Art::SelectionHandleConfig::GetSelectionAdornmentColor(&v70, 15);
  v17 = _mm_unpacklo_pd(v16, v16);
  if ( Art::FInHighContrastMode(v18) )
  {
    Art::View::Info::Info((Art::View::Info *)v76);
    v19 = (char *)Ofc::CProxyPtrImpl::GetChecked(v65);
    Art::View::Info::operator=(v76, v19 + 40);
    memset(&v71, 0, 24);
    v72 = 0;
    v73 = 0;
    v22 = Ofc::TSingleton<Art::GelTranslator>::s_pInstance;
    if ( (unsigned __int64)Ofc::TSingleton<Art::GelTranslator>::s_pInstance <= 1 )
    {
      while ( (unsigned __int64)Ofc::TSingleton<Art::GelTranslator>::s_pInstance <= 1 )
      {
        if ( _InterlockedCompareExchange64(
               (volatile signed __int64 *)&Ofc::TSingleton<Art::GelTranslator>::s_pInstance,
               1,
               0) )
        {
          v63 = 0;
          std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v63);
        }
        else
        {
          LOBYTE(v20) = 1;
          Ofc::AtExit(Ofc::TSingleton<Art::GelTranslator>::Shutdown, v20, v21);
          if ( DecodePointer(Ptr) )
          {
            v25 = (__int64 (__fastcall *)(__int64))DecodePointer(Ptr);
            v26 = (_QWORD *)v25(8);
          }
          else
          {
            v26 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v23, v24);
          }
          *v26 = &Art::GelTranslator::`vftable';
          _InterlockedCompareExchange64(
            (volatile signed __int64 *)&Ofc::TSingleton<Art::GelTranslator>::s_pInstance,
            (signed __int64)v26,
            1);
        }
      }
      v22 = Ofc::TSingleton<Art::GelTranslator>::s_pInstance;
    }
    (*(void (__fastcall **)(void *, __int128 *, __m256i *))(*(_QWORD *)v22 + 120LL))(v22, &v70, &v71);
    v29 = Ofc::TSingleton<Art::GelTranslator>::s_pInstance;
    if ( (unsigned __int64)Ofc::TSingleton<Art::GelTranslator>::s_pInstance <= 1 )
    {
      while ( (unsigned __int64)Ofc::TSingleton<Art::GelTranslator>::s_pInstance <= 1 )
      {
        if ( _InterlockedCompareExchange64(
               (volatile signed __int64 *)&Ofc::TSingleton<Art::GelTranslator>::s_pInstance,
               1,
               0) )
        {
          v63 = 0;
          std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v63);
        }
        else
        {
          LOBYTE(v27) = 1;
          Ofc::AtExit(Ofc::TSingleton<Art::GelTranslator>::Shutdown, v27, v28);
          if ( DecodePointer(Ptr) )
          {
            v32 = (__int64 (__fastcall *)(__int64))DecodePointer(Ptr);
            v33 = (_QWORD *)v32(8);
          }
          else
          {
            v33 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v30, v31);
          }
          *v33 = &Art::GelTranslator::`vftable';
          _InterlockedCompareExchange64(
            (volatile signed __int64 *)&Ofc::TSingleton<Art::GelTranslator>::s_pInstance,
            (signed __int64)v33,
            1);
        }
      }
      v29 = Ofc::TSingleton<Art::GelTranslator>::s_pInstance;
    }
    (*(void (__fastcall **)(void *, __int128 *, __int64 *))(*(_QWORD *)v29 + 120LL))(v29, &v69, &v72);
    v36 = (__int64 *)Ofc::TSingleton<Art::GelTranslator>::s_pInstance;
    if ( (unsigned __int64)Ofc::TSingleton<Art::GelTranslator>::s_pInstance <= 1 )
    {
      while ( (unsigned __int64)Ofc::TSingleton<Art::GelTranslator>::s_pInstance <= 1 )
      {
        if ( _InterlockedCompareExchange64(
               (volatile signed __int64 *)&Ofc::TSingleton<Art::GelTranslator>::s_pInstance,
               1,
               0) )
        {
          v64 = 0;
          std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v64);
        }
        else
        {
          LOBYTE(v34) = 1;
          Ofc::AtExit(Ofc::TSingleton<Art::GelTranslator>::Shutdown, v34, v35);
          if ( DecodePointer(Ptr) )
          {
            v39 = (__int64 (__fastcall *)(__int64))DecodePointer(Ptr);
            v40 = (_QWORD *)v39(8);
          }
          else
          {
            v40 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v37, v38);
          }
          *v40 = &Art::GelTranslator::`vftable';
          _InterlockedCompareExchange64(
            (volatile signed __int64 *)&Ofc::TSingleton<Art::GelTranslator>::s_pInstance,
            (signed __int64)v40,
            1);
        }
      }
      v36 = (__int64 *)Ofc::TSingleton<Art::GelTranslator>::s_pInstance;
    }
    v41 = *v36;
    LODWORD(v66) = 1;
    LODWORD(v63) = v77;
    LOBYTE(v35) = 1;
    (*(void (__fastcall **)(__int64 *, __m256i *, _BOOL8, struct Ofc::CProxyPtrImpl **, __int64 *))(v41 + 40))(
      v36,
      &v71,
      v35,
      &v63,
      &v66);
    v44 = (__int64 *)Ofc::TSingleton<Art::GelTranslator>::s_pInstance;
    if ( (unsigned __int64)Ofc::TSingleton<Art::GelTranslator>::s_pInstance <= 1 )
    {
      while ( (unsigned __int64)Ofc::TSingleton<Art::GelTranslator>::s_pInstance <= 1 )
      {
        if ( _InterlockedCompareExchange64(
               (volatile signed __int64 *)&Ofc::TSingleton<Art::GelTranslator>::s_pInstance,
               1,
               0) )
        {
          v64 = 0;
          std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v64);
        }
        else
        {
          LOBYTE(v42) = 1;
          Ofc::AtExit(Ofc::TSingleton<Art::GelTranslator>::Shutdown, v42, v43);
          if ( DecodePointer(Ptr) )
          {
            v47 = (__int64 (__fastcall *)(__int64))DecodePointer(Ptr);
            v48 = (_QWORD *)v47(8);
          }
          else
          {
            v48 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v45, v46);
          }
          *v48 = &Art::GelTranslator::`vftable';
          _InterlockedCompareExchange64(
            (volatile signed __int64 *)&Ofc::TSingleton<Art::GelTranslator>::s_pInstance,
            (signed __int64)v48,
            1);
        }
      }
      v44 = (__int64 *)Ofc::TSingleton<Art::GelTranslator>::s_pInstance;
    }
    v49 = *v44;
    LODWORD(v63) = 1;
    LODWORD(v66) = v77;
    (*(void (__fastcall **)(__int64 *, __int64 *, _QWORD, __int64 *, struct Ofc::CProxyPtrImpl **))(v49 + 40))(
      v44,
      &v72,
      0,
      &v66,
      &v63);
    Art::Color::~Color((Art::Color *)&v72);
    Art::Color::~Color((Art::Color *)&v71);
    Art::View::Info::~Info((Art::View::Info *)v76);
  }
  v50 = *a4;
  *(__m128d *)v71.m256i_i8 = _mm_sub_pd(*a4, v17);
  *(__m128d *)&v71.m256i_u64[2] = _mm_add_pd(v50, v17);
  v51 = (__int64 *)GEL::IRectanglePath::Create(&v64, &v71);
  v52 = *v51;
  *v51 = 0;
  v66 = v52;
  if ( v64 )
    (*(void (__fastcall **)(_QWORD *))(*v64 + 8LL))(v64);
  v53 = v67;
  v54 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v67 + 144LL);
  v55 = (_QWORD *)GEL::IEffectFilledPath::Create(&v63, v52, &v69);
  v54(v53, *v55);
  if ( v63 )
    (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v63 + 8LL))(v63);
  Ofc::CProxyPtrImpl::GetChecked(v65);
  Ofc::Round<__int64,double>();
  GEL::IPen::Create(&v68, v56, &v70);
  v57 = v67;
  v58 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v67 + 144LL);
  v59 = (_QWORD *)GEL::IEffectPennedPath::Create(&v64, v52, v68);
  v58(v57, *v59);
  if ( v64 )
    (*(void (__fastcall **)(_QWORD *))(*v64 + 8LL))(v64);
  RenderingPolicy = Art::SelectionHandleViewElement::GetRenderingPolicy(this);
  v61 = (struct GEL::ITopLevelEffect **)GEL::ITopLevelEffect::Create(&v64, v67, v75, RenderingPolicy);
  Art::ViewElement::SetEffect(this, *v61);
  if ( v64 )
    (*(void (__fastcall **)(_QWORD *))(v64[1] + 8LL))(v64 + 1);
  if ( v68 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 8LL))(v68);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
  if ( v67 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 8LL))(v67);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v65);
  return this;
}

```

## disassembly

```asm
0x180457e70  mov     rax, rsp
0x180457e73  push    rbp
0x180457e74  push    rbx
0x180457e75  push    rsi
0x180457e76  push    rdi
0x180457e77  push    r12
0x180457e79  push    r14
0x180457e7b  push    r15
0x180457e7d  lea     rbp, [rax-138h]
0x180457e84  sub     rsp, 200h
0x180457e8b  movaps  xmmword ptr [rax-48h], xmm6
0x180457e8f  movaps  xmmword ptr [rax-58h], xmm7
0x180457e93  mov     rax, cs:__security_cookie
0x180457e9a  xor     rax, rsp
0x180457e9d  mov     [rbp+130h+var_60], rax
0x180457ea4  mov     r12, r9
0x180457ea7  mov     r14, r8
0x180457eaa  mov     rbx, rdx
0x180457ead  mov     r15, rcx
0x180457eb0  mov     [rbp+130h+var_158], rcx
0x180457eb4  mov     [rsp+230h+var_1F0], 0; struct Art::Transform2D *
0x180457ebd  mov     [rsp+230h+var_1F8], 0; char
0x180457ec2  mov     [rsp+230h+var_200], 0; char
0x180457ec7  mov     [rsp+230h+var_208], 41h ; 'A'; int
0x180457ecf  mov     [rsp+230h+var_210], 6; int
0x180457ed7  xor     r9d, r9d
0x180457eda  lea     r8d, [r9+2]
0x180457ede  call    ??0SelectionHandleViewElement@Art@@IEAA@AEBV?$TWeakPtr@VViewElement@Art@@@Ofc@@W4HandleType@SelectionHandleInfo@1@W4HandleId@51@W4HandleShape@51@W4CursorID@Cursor@1@_N5PEBVTransform2D@1@@Z; Art::SelectionHandleViewElement::SelectionHandleViewElement(Ofc::TWeakPtr<Art::ViewElement> const &,Art::SelectionHandleInfo::HandleType,Art::SelectionHandleInfo::HandleId,Art::SelectionHandleInfo::HandleShape,Art::Cursor::CursorID,bool,bool,Art::Transform2D const *)
0x180457ee3  lea     rax, ??_7EditPointTangentPoint@Art@@6B@; const Art::EditPointTangentPoint::`vftable'
0x180457eea  mov     [r15], rax
0x180457eed  mov     eax, [rbp+130h+arg_20]
0x180457ef3  mov     [r15+120h], eax
0x180457efa  lea     rsi, [r15+128h]
0x180457f01  mov     qword ptr [rsi], 0
0x180457f08  mov     qword ptr [rsi+8], 0
0x180457f10  mov     rcx, r15
0x180457f13  call    ?GetView@ViewElement@Art@@QEAAAEBV?$TWeakPtr@VView@Art@@@Ofc@@XZ; Art::ViewElement::GetView(void)
0x180457f18  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x180457f1b  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180457f20  mov     [rsp+230h+var_1D0], rax
0x180457f25  mov     rcx, [rbx]; struct Ofc::CProxyPtrImpl *
0x180457f28  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180457f2d  mov     [rsp+230h+var_1E0], rax
0x180457f32  mov     rcx, rax; this
0x180457f35  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180457f3a  mov     rbx, rax
0x180457f3d  lea     rcx, [rsp+230h+var_1E0]; struct Ofc::CProxyPtrImpl **
0x180457f42  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180457f47  lea     rdx, [rbx+48h]
0x180457f4b  mov     rcx, r14
0x180457f4e  call    ??$GetIfValid@Ucolor@FlPr@Art@@@?$TPropertySet@VSolidColorFillPropsIDs@Art@@@Ofc@@QEBAAEBVColor@Art@@AEBV23@@Z; Ofc::TPropertySet<Art::SolidColorFillPropsIDs>::GetIfValid<Art::FlPr::color>(Art::Color const &)
0x180457f53  mov     rbx, rax
0x180457f56  mov     rdx, rax
0x180457f59  lea     rcx, [rbp+130h+var_150]
0x180457f5d  call    ?GetGelTransform@Art@@YA?AU?$TAffine3x3@N@Math@@AEBVTransform2D@1@@Z; Art::GetGelTransform(Art::Transform2D const &)
0x180457f62  movsd   xmm0, qword ptr [r12]
0x180457f68  call    ??$Round@_JN@Ofc@@YA_JN@Z; Ofc::Round<__int64,double>(double)
0x180457f6d  mov     rdx, rax
0x180457f70  mov     rcx, rsi
0x180457f73  call    ??4?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAAAEAV01@_J@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator=(__int64)
0x180457f78  movsd   xmm0, qword ptr [r12+8]
0x180457f7f  call    ??$Round@_JN@Ofc@@YA_JN@Z; Ofc::Round<__int64,double>(double)
0x180457f84  lea     rcx, [r15+130h]
0x180457f8b  mov     rdx, rax
0x180457f8e  call    ??4?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAAAEAV01@_J@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator=(__int64)
0x180457f93  mov     rdx, rbx
0x180457f96  mov     rcx, rsi
0x180457f99  call    ??Y?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAAAEAV01@AEBV01@@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator+=(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &)
0x180457f9e  lea     rdx, [rbx+8]
0x180457fa2  lea     rcx, [rsi+8]
0x180457fa6  call    ??Y?$CoordMethods@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@QEAAAEAV01@AEBV01@@Z; Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator+=(Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>> const &)
0x180457fab  lea     rcx, [rsp+230h+var_1D0]
0x180457fb0  call    ?GetViewPixelToHostEMUScale@Art@@YANAEBV?$TSharedPtr@$$CBVView@Art@@@Ofc@@@Z; Art::GetViewPixelToHostEMUScale(Ofc::TSharedPtr<Art::View const> const &)
0x180457fb5  movaps  xmm6, xmm0
0x180457fb8  mov     rcx, [rsp+230h+var_1D0]; this
0x180457fbd  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180457fc2  lea     rcx, [rax+0A0h]
0x180457fc9  call    cs:__imp_?GetEditPointTangentPointLength@SelectionHandleConfig@GEL@@SAMAEBV?$TConvertibleDPI2@M@Gfx@@@Z; GEL::SelectionHandleConfig::GetEditPointTangentPointLength(Gfx::TConvertibleDPI2<float> const &)
0x180457fcf  xorps   xmm7, xmm7
0x180457fd2  cvtss2sd xmm7, xmm0
0x180457fd6  mulsd   xmm7, xmm6
0x180457fda  mulsd   xmm7, cs:__real@3fe0000000000000
0x180457fe2  lea     rcx, [rsp+230h+var_1C0]
0x180457fe7  call    cs:__imp_?Create@IEffectContainer@GEL@@SA?AV?$TCntPtr@UIEffectContainer@GEL@@@Ofc@@XZ; GEL::IEffectContainer::Create(void)
0x180457fed  nop
0x180457fee  xorps   xmm0, xmm0
0x180457ff1  movups  [rbp+130h+var_1B0], xmm0
0x180457ff5  xorps   xmm1, xmm1
0x180457ff8  movups  [rbp+130h+var_1A0], xmm1
0x180457ffc  mov     edx, 0Eh
0x180458001  lea     rcx, [rbp+130h+var_1B0]
0x180458005  call    ?GetSelectionAdornmentColor@SelectionHandleConfig@Art@@SAXAEAUColor@GEL@@W4OartSelectionAdornmentsSwatch@UIColor@Mso@@@Z; Art::SelectionHandleConfig::GetSelectionAdornmentColor(GEL::Color &,Mso::UIColor::OartSelectionAdornmentsSwatch)
0x18045800a  mov     edx, 0Fh
0x18045800f  lea     rcx, [rbp+130h+var_1A0]
0x180458013  call    ?GetSelectionAdornmentColor@SelectionHandleConfig@Art@@SAXAEAUColor@GEL@@W4OartSelectionAdornmentsSwatch@UIColor@Mso@@@Z; Art::SelectionHandleConfig::GetSelectionAdornmentColor(GEL::Color &,Mso::UIColor::OartSelectionAdornmentsSwatch)
0x180458018  movaps  xmm6, xmm7
0x18045801b  unpcklpd xmm6, xmm6
0x18045801f  call    ?FInHighContrastMode@Art@@YA_NXZ; Art::FInHighContrastMode(void)
0x180458024  test    al, al
0x180458026  jz      loc_180458379
0x18045802c  lea     rcx, [rbp+130h+var_120]; this
0x180458030  call    ??0Info@View@Art@@QEAA@XZ; Art::View::Info::Info(void)
0x180458035  mov     rcx, [rsp+230h+var_1D0]; this
0x18045803a  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18045803f  lea     rdx, [rax+28h]
0x180458043  lea     rcx, [rbp+130h+var_120]
0x180458047  call    ??4Info@View@Art@@QEAAAEAU012@AEBU012@@Z; Art::View::Info::operator=(Art::View::Info const &)
0x18045804c  xor     eax, eax
0x18045804e  mov     qword ptr [rbp+130h+var_190], rax
0x180458052  xorps   xmm0, xmm0
0x180458055  movdqu  [rbp+130h+var_190+8], xmm0
0x18045805a  mov     [rbp+130h+var_170], rax
0x18045805e  movdqu  [rbp+130h+var_168], xmm0
0x180458063  lea     r14, ?Shutdown@?$TSingleton@VGelTranslator@Art@@@Ofc@@SAXXZ; Ofc::TSingleton<Art::GelTranslator>::Shutdown(void)
0x18045806a  lea     edi, [rax+8]
0x18045806d  lea     rsi, ??_7GelTranslator@Art@@6B@; const Art::GelTranslator::`vftable'
0x180458074  mov     rcx, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x18045807b  lea     ebx, [rax+1]
0x18045807e  cmp     rcx, rbx
0x180458081  ja      loc_18045810C
0x180458087  mov     rax, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x18045808e  cmp     rax, rbx
0x180458091  ja      short loc_180458105
0x180458093  xor     eax, eax
0x180458095  lock cmpxchg cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA, rbx; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x18045809e  jnz     short loc_1804580F0
0x1804580a0  mov     dl, bl; void (*)(void)
0x1804580a2  mov     rcx, r14; Ptr
0x1804580a5  call    ?AtExit@Ofc@@YAXP6AXXZ_N@Z; Ofc::AtExit(void (*)(void),bool)
0x1804580aa  mov     rcx, cs:Ptr; Ptr
0x1804580b1  call    cs:__imp_DecodePointer
0x1804580b7  test    rax, rax
0x1804580ba  jz      short loc_1804580D4
0x1804580bc  mov     rcx, cs:Ptr; Ptr
0x1804580c3  call    cs:__imp_DecodePointer
0x1804580c9  mov     rcx, rdi
0x1804580cc  call    cs:__guard_dispatch_icall_fptr
0x1804580d2  jmp     short loc_1804580DC
0x1804580d4  mov     rcx, rdi; this
0x1804580d7  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1804580dc  mov     [rax], rsi
0x1804580df  mov     rcx, rax
0x1804580e2  mov     rax, rbx
0x1804580e5  lock cmpxchg cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA, rcx; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x1804580ee  jmp     short loc_180458087
0x1804580f0  mov     [rsp+230h+var_1E0], 0
0x1804580f9  lea     rcx, [rsp+230h+var_1E0]
0x1804580fe  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x180458103  jmp     short loc_180458087
0x180458105  mov     rcx, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x18045810c  mov     rax, [rcx]
0x18045810f  lea     r8, [rbp+130h+var_190]
0x180458113  lea     rdx, [rbp+130h+var_1A0]
0x180458117  mov     rax, [rax+78h]
0x18045811b  call    cs:__guard_dispatch_icall_fptr
0x180458121  nop
0x180458122  mov     rcx, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x180458129  cmp     rcx, rbx
0x18045812c  ja      loc_1804581B7
0x180458132  mov     rax, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x180458139  cmp     rax, rbx
0x18045813c  ja      short loc_1804581B0
0x18045813e  xor     eax, eax
0x180458140  lock cmpxchg cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA, rbx; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x180458149  jnz     short loc_18045819B
0x18045814b  mov     dl, bl; void (*)(void)
0x18045814d  mov     rcx, r14; Ptr
0x180458150  call    ?AtExit@Ofc@@YAXP6AXXZ_N@Z; Ofc::AtExit(void (*)(void),bool)
0x180458155  mov     rcx, cs:Ptr; Ptr
0x18045815c  call    cs:__imp_DecodePointer
0x180458162  test    rax, rax
0x180458165  jz      short loc_18045817F
0x180458167  mov     rcx, cs:Ptr; Ptr
0x18045816e  call    cs:__imp_DecodePointer
0x180458174  mov     rcx, rdi
0x180458177  call    cs:__guard_dispatch_icall_fptr
0x18045817d  jmp     short loc_180458187
0x18045817f  mov     rcx, rdi; this
0x180458182  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180458187  mov     [rax], rsi
0x18045818a  mov     rcx, rax
0x18045818d  mov     rax, rbx
0x180458190  lock cmpxchg cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA, rcx; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x180458199  jmp     short loc_180458132
0x18045819b  mov     [rsp+230h+var_1E0], 0
0x1804581a4  lea     rcx, [rsp+230h+var_1E0]
0x1804581a9  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1804581ae  jmp     short loc_180458132
0x1804581b0  mov     rcx, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x1804581b7  mov     rax, [rcx]
0x1804581ba  lea     r8, [rbp+130h+var_170]
0x1804581be  lea     rdx, [rbp+130h+var_1B0]
0x1804581c2  mov     rax, [rax+78h]
0x1804581c6  call    cs:__guard_dispatch_icall_fptr
0x1804581cc  nop
0x1804581cd  mov     rcx, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x1804581d4  cmp     rcx, rbx
0x1804581d7  ja      loc_180458262
0x1804581dd  mov     rax, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x1804581e4  cmp     rax, rbx
0x1804581e7  ja      short loc_18045825B
0x1804581e9  xor     eax, eax
0x1804581eb  lock cmpxchg cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA, rbx; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x1804581f4  jnz     short loc_180458246
0x1804581f6  mov     dl, bl; void (*)(void)
0x1804581f8  mov     rcx, r14; Ptr
0x1804581fb  call    ?AtExit@Ofc@@YAXP6AXXZ_N@Z; Ofc::AtExit(void (*)(void),bool)
0x180458200  mov     rcx, cs:Ptr; Ptr
0x180458207  call    cs:__imp_DecodePointer
0x18045820d  test    rax, rax
0x180458210  jz      short loc_18045822A
0x180458212  mov     rcx, cs:Ptr; Ptr
0x180458219  call    cs:__imp_DecodePointer
0x18045821f  mov     rcx, rdi
0x180458222  call    cs:__guard_dispatch_icall_fptr
0x180458228  jmp     short loc_180458232
0x18045822a  mov     rcx, rdi; this
0x18045822d  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180458232  mov     [rax], rsi
0x180458235  mov     rcx, rax
0x180458238  mov     rax, rbx
0x18045823b  lock cmpxchg cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA, rcx; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x180458244  jmp     short loc_1804581DD
0x180458246  mov     [rsp+230h+var_1D8], 0
0x18045824f  lea     rcx, [rsp+230h+var_1D8]
0x180458254  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x180458259  jmp     short loc_1804581DD
0x18045825b  mov     rcx, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x180458262  mov     rax, [rcx]
0x180458265  mov     dword ptr [rsp+230h+var_1C8], ebx
0x180458269  mov     edx, [rbp+130h+var_80]
0x18045826f  mov     dword ptr [rsp+230h+var_1E0], edx
0x180458273  lea     rdx, [rsp+230h+var_1C8]
0x180458278  mov     qword ptr [rsp+230h+var_210], rdx
0x18045827d  lea     r9, [rsp+230h+var_1E0]
0x180458282  mov     r8b, bl
0x180458285  lea     rdx, [rbp+130h+var_190]
0x180458289  mov     rax, [rax+28h]
0x18045828d  call    cs:__guard_dispatch_icall_fptr
0x180458293  nop
0x180458294  mov     rcx, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x18045829b  cmp     rcx, rbx
0x18045829e  ja      loc_180458329
0x1804582a4  mov     rax, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x1804582ab  cmp     rax, rbx
0x1804582ae  ja      short loc_180458322
0x1804582b0  xor     eax, eax
0x1804582b2  lock cmpxchg cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA, rbx; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x1804582bb  jnz     short loc_18045830D
0x1804582bd  mov     dl, bl; void (*)(void)
0x1804582bf  mov     rcx, r14; Ptr
0x1804582c2  call    ?AtExit@Ofc@@YAXP6AXXZ_N@Z; Ofc::AtExit(void (*)(void),bool)
0x1804582c7  mov     rcx, cs:Ptr; Ptr
0x1804582ce  call    cs:__imp_DecodePointer
0x1804582d4  test    rax, rax
0x1804582d7  jz      short loc_1804582F1
0x1804582d9  mov     rcx, cs:Ptr; Ptr
0x1804582e0  call    cs:__imp_DecodePointer
0x1804582e6  mov     rcx, rdi
0x1804582e9  call    cs:__guard_dispatch_icall_fptr
0x1804582ef  jmp     short loc_1804582F9
0x1804582f1  mov     rcx, rdi; this
0x1804582f4  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1804582f9  mov     [rax], rsi
0x1804582fc  mov     rcx, rax
0x1804582ff  mov     rax, rbx
0x180458302  lock cmpxchg cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA, rcx; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x18045830b  jmp     short loc_1804582A4
0x18045830d  mov     [rsp+230h+var_1D8], 0
0x180458316  lea     rcx, [rsp+230h+var_1D8]
0x18045831b  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x180458320  jmp     short loc_1804582A4
0x180458322  mov     rcx, cs:?s_pInstance@?$TSingleton@VGelTranslator@Art@@@Ofc@@0PEAVGelTranslator@Art@@EA; Art::GelTranslator * Ofc::TSingleton<Art::GelTranslator>::s_pInstance
0x180458329  mov     rax, [rcx]
0x18045832c  mov     dword ptr [rsp+230h+var_1E0], ebx
0x180458330  mov     edx, [rbp+130h+var_80]
0x180458336  mov     dword ptr [rsp+230h+var_1C8], edx
0x18045833a  lea     rdx, [rsp+230h+var_1E0]
0x18045833f  mov     qword ptr [rsp+230h+var_210], rdx
0x180458344  lea     r9, [rsp+230h+var_1C8]
0x180458349  xor     r8d, r8d
0x18045834c  lea     rdx, [rbp+130h+var_170]
0x180458350  mov     rax, [rax+28h]
0x180458354  call    cs:__guard_dispatch_icall_fptr
0x18045835a  nop
0x18045835b  lea     rcx, [rbp+130h+var_170]; this
0x18045835f  call    ??1Color@Art@@QEAA@XZ; Art::Color::~Color(void)
0x180458364  lea     rcx, [rbp+130h+var_190]; this
0x180458368  call    ??1Color@Art@@QEAA@XZ; Art::Color::~Color(void)
0x18045836d  nop     dword ptr [rax]
0x180458370  lea     rcx, [rbp+130h+var_120]; this
0x180458374  call    ??1Info@View@Art@@QEAA@XZ; Art::View::Info::~Info(void)
0x180458379  movups  xmm1, xmmword ptr [r12]
0x18045837e  movaps  xmm0, xmm1
0x180458381  subpd   xmm0, xmm6
0x180458385  movups  [rbp+130h+var_190], xmm0
0x180458389  addpd   xmm1, xmm6
0x18045838d  movups  [rbp+130h+var_180], xmm1
0x180458391  lea     rdx, [rbp+130h+var_190]
0x180458395  lea     rcx, [rsp+230h+var_1D8]
  ... truncated ...
```
