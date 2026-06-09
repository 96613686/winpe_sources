# Art::ToOdfShapeGeometryConversion::WriteWedgeRectCallout(Art::Geometry2D const &,Art::Transform2D const &,ODF::DrawShapeChoice_<0> &)

- ea: `0x18015e2dc`
- end: `0x18015e6e1`
- name: `?WriteWedgeRectCallout@ToOdfShapeGeometryConversion@Art@@CAXAEBVGeometry2D@2@AEBVTransform2D@2@AEAV?$DrawShapeChoice_@$0A@@ODF@@@Z`
- size: `1029`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18015b06c`

## callees

- `0x18000403c`
- `0x1800048d4`
- `0x1800078b4`
- `0x180007da4`
- `0x180007e00`
- `0x1800080e8`
- `0x1800084b8`
- `0x180009df4`
- `0x18002fcb0`
- `0x180042368`
- `0x1800489f8`
- `0x180048aa8`
- `0x1800ff93c`
- `0x18012ad04`
- `0x180139000`
- `0x18015aba4`
- `0x18015af50`
- `0x18015e2dc`

## import_xrefs

- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015e407`
- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015e407`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015e696`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015e696`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015e49f`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015e4f3`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015e49f`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015e4f3`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015e46d`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015e47f`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015e46d`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015e47f`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015e6a0`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015e6a0`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015e5eb`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015e5eb`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015e6ab`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015e6ab`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015e426`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015e426`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015e45c`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015e45c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015e662`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015e68b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015e662`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015e68b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Art::ToOdfShapeGeometryConversion::WriteWedgeRectCallout(
        const struct Art::Geometry2D *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v5; // rax
  wchar_t **v6; // r14
  unsigned int *v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // ebx
  int v17; // edi
  unsigned int v18; // r8d
  double v19; // xmm0_8
  double v20; // xmm6_8
  double v21; // xmm1_8
  unsigned int v22; // r8d
  double v23; // xmm0_8
  const wchar_t *v24; // rdx
  int v25; // eax
  wchar_t *v26; // rbx
  Art::FeatureGates *v27; // rcx
  void *v28; // rdx
  Mso::Memory *v29; // rcx
  Mso::Memory *v30; // rcx
  unsigned int v31; // eax
  _BYTE v32[16]; // [rsp+38h] [rbp-D0h] BYREF
  __int16 v33; // [rsp+48h] [rbp-C0h] BYREF
  char v34; // [rsp+4Ah] [rbp-BEh]
  wchar_t *v35; // [rsp+50h] [rbp-B8h] BYREF
  wchar_t *v36; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t *v37[13]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v38[56]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v39[72]; // [rsp+100h] [rbp-8h] BYREF
  wchar_t *v40; // [rsp+180h] [rbp+78h] BYREF
  wchar_t *v41; // [rsp+190h] [rbp+88h] BYREF

  v5 = (_QWORD *)Ofc::TChoice<ODF::DrawShapeChoiceChoiceIDsImpl>::SwitchTo<ODF::DrawShapeChoiceChoices::customShape>(a3);
  v6 = (wchar_t **)Ofc::TOptional<ODF::EnhancedGeometry>::EnsureStorage(*v5 + 72LL);
  v7 = (unsigned int *)Ofc::TOptional<Ofc::TArray<int>>::EnsureStorage(v6 + 12);
  Ofc::CArrayImpl::EnsureCapacityForOneElem(
    (Ofc::CArrayImpl *)v7,
    4u,
    (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TCopyConstructRange<enum ODF::TextEmphasisType,1,1>::Do);
  v8 = v7[2];
  v9 = *(_QWORD *)v7;
  *(_DWORD *)(v9 + 4 * v8) = 0;
  ++v7[2];
  *(_DWORD *)(v9 + 4 * v8) = 0;
  Ofc::CArrayImpl::EnsureCapacityForOneElem(
    (Ofc::CArrayImpl *)v7,
    4u,
    (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TCopyConstructRange<enum ODF::TextEmphasisType,1,1>::Do);
  v10 = v7[2];
  v11 = *(_QWORD *)v7;
  *(_DWORD *)(v11 + 4 * v10) = 0;
  ++v7[2];
  *(_DWORD *)(v11 + 4 * v10) = 0;
  Ofc::CArrayImpl::EnsureCapacityForOneElem(
    (Ofc::CArrayImpl *)v7,
    4u,
    (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TCopyConstructRange<enum ODF::TextEmphasisType,1,1>::Do);
  v12 = v7[2];
  v13 = *(_QWORD *)v7;
  *(_DWORD *)(v13 + 4 * v12) = 0;
  ++v7[2];
  *(_DWORD *)(v13 + 4 * v12) = 21600;
  Ofc::CArrayImpl::EnsureCapacityForOneElem(
    (Ofc::CArrayImpl *)v7,
    4u,
    (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TCopyConstructRange<enum ODF::TextEmphasisType,1,1>::Do);
  v14 = v7[2];
  v15 = *(_QWORD *)v7;
  *(_DWORD *)(v15 + 4 * v14) = 0;
  ++v7[2];
  *(_DWORD *)(v15 + 4 * v14) = 21600;
  Ofc::CStr::operator=(v6 + 49, (Ofc *)L"?f40 ?f41");
  Ofc::CStr::operator=(v6 + 51, (Ofc *)L"180");
  Ofc::CStr::operator=(v6 + 48, (Ofc *)L"0 0 21600 21600");
  LODWORD(v40) = 0;
  Ofc::TVariant<ODF::CustomShapeTypeIDsImpl>::operator=<enum ODF::DrawCustomShapeType>(v6 + 10, &v40);
  Art::Geometry2D::Geometry2D((Art::Geometry2D *)v32);
  Art::GeometryCompiler::GeometryCompiler(
    (Art::GeometryCompiler *)v38,
    a1,
    (const struct Art::PosSize2D *)(a2 + 16),
    (struct Art::Geometry2D *)v32,
    0xFFu);
  if ( !(unsigned __int8)Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(a1) )
    goto LABEL_23;
  if ( *((_QWORD *)a1 + 1) <= 1u )
    Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::DemandInit(a1);
  if ( !*(_QWORD *)a1 )
  {
LABEL_23:
    v31 = MsoReserveTag::operator unsigned int("bm5f");
    Ofc::CInvalidParamException::ThrowTag(v31);
    __debugbreak();
  }
  Art::PresetGeometry2D::PresetGeometry2D((Art::PresetGeometry2D *)v39, *(const struct Art::PresetGeometry2D **)a1);
  v16 = Art::GeomGuideName::MapStringToToken(L"adj1", 4);
  v17 = Art::GeomGuideName::MapStringToToken(L"adj2", 4);
  v40 = (wchar_t *)&dword_1801DBD74;
  v41 = (wchar_t *)&dword_1801DBD74;
  v19 = Art::GeometryCompiler::Lookup((Art::GeometryCompiler *)v38, v16) * 21600.0 / 100000.0 + 10800.0;
  v20 = DOUBLE_0_5;
  if ( v19 < 0.0 )
    v21 = DOUBLE_N0_5;
  else
    v21 = DOUBLE_0_5;
  Ofc::CStr::DecodeInt(&v40, (int)(v21 + v19), v18);
  v23 = Art::GeometryCompiler::Lookup((Art::GeometryCompiler *)v38, v17) * 21600.0 / 100000.0 + 10800.0;
  if ( v23 < 0.0 )
    v20 = DOUBLE_N0_5;
  Ofc::CStr::DecodeInt(&v41, (int)(v20 + v23), v22);
  Ofc::CVarStr::operator=(v6 + 53, &v40);
  v25 = Ofc::CchWzLen((Ofc *)L" ", v24);
  Ofc::CStr::Append((Ofc::CStr *)(v6 + 53), L" ", v25);
  v26 = v41;
  Ofc::CStr::Append((Ofc::CStr *)(v6 + 53), v41, *((_DWORD *)v41 - 1) / 2);
  Ofc::CStr::operator=(
    v6 + 47,
    (Ofc *)L"M 0 0 L 0 3590 ?f2 ?f3 0 8970 0 12630 ?f4 ?f5 0 18010 0 21600 3590 21600 ?f6 ?f7 8970 21600 12630 21600 ?f8 ?"
            "f9 18010 21600 21600 21600 21600 18010 ?f10 ?f11 21600 12630 21600 8970 ?f12 ?f13 21600 3590 21600 0 18010 0"
            " ?f14 ?f15 12630 0 8970 0 ?f16 ?f17 3590 0 0 0 Z N");
  Art::ToOdfShapeGeometryConversion::AddRectangularCalloutEquations(v6);
  v33 = 0;
  v34 = 0;
  v35 = (wchar_t *)&dword_1801DBD74;
  v36 = (wchar_t *)&dword_1801DBD74;
  v37[0] = (wchar_t *)&dword_1801DBD74;
  v37[1] = (wchar_t *)&dword_1801DBD74;
  v37[2] = (wchar_t *)&dword_1801DBD74;
  v37[3] = (wchar_t *)&dword_1801DBD74;
  v37[4] = (wchar_t *)&dword_1801DBD74;
  v37[5] = (wchar_t *)&dword_1801DBD74;
  v37[6] = (wchar_t *)&dword_1801DBD74;
  v37[7] = (wchar_t *)&dword_1801DBD74;
  v37[8] = (wchar_t *)&dword_1801DBD74;
  v37[9] = (wchar_t *)&dword_1801DBD74;
  v37[10] = (wchar_t *)&dword_1801DBD74;
  v37[11] = (wchar_t *)&dword_1801DBD74;
  if ( Art::FeatureGates::FUsingODF_1_4(v27) )
  {
    Ofc::CStr::operator=(&v36, (Ofc *)L"$0");
    Ofc::CStr::operator=(v37, (Ofc *)L"$1");
  }
  Ofc::CStr::operator=(&v35, (Ofc *)L"$0 $1");
  Ofc::TVector<ODF::Handle,0,4294967295>::Push(v6 + 3, &v33);
  ODF::Handle::~Handle((ODF::Handle *)&v33);
  v29 = (Mso::Memory *)(v26 - 6);
  if ( *((_DWORD *)v26 - 2)
    && (*(_DWORD *)v29 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v29, 0xFFFFFFFF) == 1)
    && v26 != (wchar_t *)12 )
  {
    Mso::Memory::Free(v29, v28);
  }
  v30 = (Mso::Memory *)(v40 - 6);
  if ( *((_DWORD *)v40 - 2)
    && (*(_DWORD *)v30 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v30, 0xFFFFFFFF) == 1) )
  {
    if ( v30 )
      Mso::Memory::Free(v30, v28);
  }
  Art::PresetGeometry2D::~PresetGeometry2D((Art::PresetGeometry2D *)v39);
  Art::GeometryCompiler::~GeometryCompiler((Art::GeometryCompiler *)v38);
  Art::Geometry2D::~Geometry2D((Art::Geometry2D *)v32);
}

```

## disassembly

```asm
0x18015e2dc  mov     rax, rsp
0x18015e2df  mov     [rax+8], rbx
0x18015e2e3  push    rbp
0x18015e2e4  push    rsi
0x18015e2e5  push    rdi
0x18015e2e6  push    r12
0x18015e2e8  push    r14
0x18015e2ea  lea     rbp, [rax-68h]
0x18015e2ee  sub     rsp, 140h
0x18015e2f5  movaps  xmmword ptr [rax-38h], xmm6
0x18015e2f9  mov     rdi, rdx
0x18015e2fc  mov     rsi, rcx
0x18015e2ff  mov     rcx, r8
0x18015e302  call    ??$SwitchTo@UcustomShape@DrawShapeChoiceChoices@ODF@@@?$TChoice@VDrawShapeChoiceChoiceIDsImpl@ODF@@@Ofc@@QEAAAEAVCustomShape@ODF@@XZ; Ofc::TChoice<ODF::DrawShapeChoiceChoiceIDsImpl>::SwitchTo<ODF::DrawShapeChoiceChoices::customShape>(void)
0x18015e307  mov     rcx, [rax]
0x18015e30a  add     rcx, 48h ; 'H'
0x18015e30e  call    ?EnsureStorage@?$TOptional@VEnhancedGeometry@ODF@@@Ofc@@QEAAAEAVEnhancedGeometry@ODF@@XZ; Ofc::TOptional<ODF::EnhancedGeometry>::EnsureStorage(void)
0x18015e313  mov     r14, rax
0x18015e316  lea     rcx, [rax+60h]
0x18015e31a  call    ?EnsureStorage@?$TOptional@V?$TArray@H@Ofc@@@Ofc@@QEAAAEAV?$TArray@H@2@XZ; Ofc::TOptional<Ofc::TArray<int>>::EnsureStorage(void)
0x18015e31f  mov     rbx, rax
0x18015e322  lea     r12, ?Do@?$TCopyConstructRange@W4TextEmphasisType@ODF@@$00$00@Ofc@@SAXPEBEPEAEK@Z; Ofc::TCopyConstructRange<ODF::TextEmphasisType,1,1>::Do(uchar const *,uchar *,ulong)
0x18015e329  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015e32c  mov     edx, 4; unsigned int
0x18015e331  mov     rcx, rax; this
0x18015e334  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015e339  mov     edx, [rbx+8]
0x18015e33c  mov     rcx, [rbx]
0x18015e33f  xor     eax, eax
0x18015e341  mov     [rcx+rdx*4], eax
0x18015e344  inc     dword ptr [rbx+8]
0x18015e347  mov     [rcx+rdx*4], eax
0x18015e34a  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015e34d  lea     edx, [rax+4]; unsigned int
0x18015e350  mov     rcx, rbx; this
0x18015e353  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015e358  mov     ecx, [rbx+8]
0x18015e35b  mov     rax, [rbx]
0x18015e35e  xor     edx, edx
0x18015e360  mov     [rax+rcx*4], edx
0x18015e363  inc     dword ptr [rbx+8]
0x18015e366  mov     [rax+rcx*4], edx
0x18015e369  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015e36c  mov     edx, 4; unsigned int
0x18015e371  mov     rcx, rbx; this
0x18015e374  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015e379  mov     ecx, [rbx+8]
0x18015e37c  mov     rax, [rbx]
0x18015e37f  xor     edx, edx
0x18015e381  mov     [rax+rcx*4], edx
0x18015e384  inc     dword ptr [rbx+8]
0x18015e387  mov     dword ptr [rax+rcx*4], 5460h
0x18015e38e  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015e391  lea     r12d, [rdx+4]
0x18015e395  mov     edx, r12d; unsigned int
0x18015e398  mov     rcx, rbx; this
0x18015e39b  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015e3a0  mov     ecx, [rbx+8]
0x18015e3a3  mov     rax, [rbx]
0x18015e3a6  xor     edx, edx
0x18015e3a8  mov     [rax+rcx*4], edx
0x18015e3ab  inc     dword ptr [rbx+8]
0x18015e3ae  mov     dword ptr [rax+rcx*4], 5460h
0x18015e3b5  lea     rcx, [r14+188h]; this
0x18015e3bc  lea     rdx, aF40F41; "?f40 ?f41"
0x18015e3c3  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015e3c8  lea     rcx, [r14+198h]; this
0x18015e3cf  lea     rdx, a180; "180"
0x18015e3d6  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015e3db  lea     rcx, [r14+180h]; this
0x18015e3e2  lea     rdx, a002160021600; "0 0 21600 21600"
0x18015e3e9  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015e3ee  mov     dword ptr [rbp+60h+arg_8], 0
0x18015e3f5  lea     rcx, [r14+50h]
0x18015e3f9  lea     rdx, [rbp+60h+arg_8]
0x18015e3fd  call    ??$?4W4DrawCustomShapeType@ODF@@@?$TVariant@VCustomShapeTypeIDsImpl@ODF@@@Ofc@@QEAAAEAV01@AEBW4DrawCustomShapeType@ODF@@@Z; Ofc::TVariant<ODF::CustomShapeTypeIDsImpl>::operator=<ODF::DrawCustomShapeType>(ODF::DrawCustomShapeType const &)
0x18015e402  lea     rcx, [rsp+160h+var_130]
0x18015e407  call    cs:__imp_??0Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::Geometry2D(void)
0x18015e40d  nop
0x18015e40e  lea     r8, [rdi+10h]
0x18015e412  mov     [rsp+160h+var_140], 0FFh
0x18015e41a  lea     r9, [rsp+160h+var_130]
0x18015e41f  mov     rdx, rsi
0x18015e422  lea     rcx, [rbp+60h+var_A0]
0x18015e426  call    cs:__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z; Art::GeometryCompiler::GeometryCompiler(Art::Geometry2D const &,Art::PosSize2D const &,Art::Geometry2D &,ulong)
0x18015e42c  nop
0x18015e42d  mov     rcx, rsi
0x18015e430  call    ??$Is@UPreset@Geom@Art@@@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(void)
0x18015e435  test    al, al
0x18015e437  jz      loc_18015E6CD
0x18015e43d  cmp     qword ptr [rsi+8], 1
0x18015e442  ja      short loc_18015E44C
0x18015e444  mov     rcx, rsi
0x18015e447  call    ?DemandInit@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@AEBAXXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::DemandInit(void)
0x18015e44c  mov     rdx, [rsi]
0x18015e44f  test    rdx, rdx
0x18015e452  jz      loc_18015E6CD
0x18015e458  lea     rcx, [rbp+60h+var_68]
0x18015e45c  call    cs:__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z; Art::PresetGeometry2D::PresetGeometry2D(Art::PresetGeometry2D const &)
0x18015e462  nop
0x18015e463  mov     edx, r12d
0x18015e466  lea     rcx, aAdj1; "adj1"
0x18015e46d  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015e473  mov     ebx, eax
0x18015e475  mov     edx, r12d
0x18015e478  lea     rcx, aAdj2; "adj2"
0x18015e47f  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015e485  mov     edi, eax
0x18015e487  lea     rsi, dword_1801DBD74
0x18015e48e  mov     [rbp+60h+arg_8], rsi
0x18015e492  mov     [rbp+60h+arg_18], rsi
0x18015e499  mov     edx, ebx
0x18015e49b  lea     rcx, [rbp+60h+var_A0]
0x18015e49f  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015e4a5  mulsd   xmm0, cs:__real@40d5180000000000
0x18015e4ad  divsd   xmm0, cs:__real@40f86a0000000000
0x18015e4b5  addsd   xmm0, cs:__real@40c5180000000000
0x18015e4bd  movsd   xmm6, cs:__real@3fe0000000000000
0x18015e4c5  comisd  xmm0, cs:__real@0000000000000000
0x18015e4cd  jb      short loc_18015E4D4
0x18015e4cf  movaps  xmm1, xmm6
0x18015e4d2  jmp     short loc_18015E4DC
0x18015e4d4  movsd   xmm1, cs:__real@bfe0000000000000
0x18015e4dc  addsd   xmm1, xmm0
0x18015e4e0  cvttsd2si edx, xmm1; int
0x18015e4e4  lea     rcx, [rbp+60h+arg_8]; this
0x18015e4e8  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015e4ed  mov     edx, edi
0x18015e4ef  lea     rcx, [rbp+60h+var_A0]
0x18015e4f3  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015e4f9  mulsd   xmm0, cs:__real@40d5180000000000
0x18015e501  divsd   xmm0, cs:__real@40f86a0000000000
0x18015e509  addsd   xmm0, cs:__real@40c5180000000000
0x18015e511  comisd  xmm0, cs:__real@0000000000000000
0x18015e519  jnb     short loc_18015E523
0x18015e51b  movsd   xmm6, cs:__real@bfe0000000000000
0x18015e523  addsd   xmm6, xmm0
0x18015e527  cvttsd2si edx, xmm6; int
0x18015e52b  lea     rcx, [rbp+60h+arg_18]; this
0x18015e532  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015e537  lea     rdi, [r14+1A8h]
0x18015e53e  lea     rdx, [rbp+60h+arg_8]
0x18015e542  mov     rcx, rdi
0x18015e545  call    ??4CVarStr@Ofc@@QEAAAEAV01@AEBV01@@Z; Ofc::CVarStr::operator=(Ofc::CVarStr const &)
0x18015e54a  lea     rcx, asc_1801E05D8; " "
0x18015e551  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x18015e556  mov     r8d, eax; int
0x18015e559  lea     rdx, asc_1801E05D8; " "
0x18015e560  mov     rcx, rdi; this
0x18015e563  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015e568  mov     rbx, [rbp+60h+arg_18]
0x18015e56f  mov     eax, [rbx-4]
0x18015e572  cdq
0x18015e573  sub     eax, edx
0x18015e575  sar     eax, 1
0x18015e577  mov     r8d, eax; int
0x18015e57a  mov     rdx, rbx; wchar_t *
0x18015e57d  mov     rcx, rdi; this
0x18015e580  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015e585  lea     rcx, [r14+178h]; this
0x18015e58c  lea     rdx, aM00L03590F2F30; "M 0 0 L 0 3590 ?f2 ?f3 0 8970 0 12630 ?"...
0x18015e593  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015e598  mov     rcx, r14
0x18015e59b  call    ?AddRectangularCalloutEquations@ToOdfShapeGeometryConversion@Art@@CAXAEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddRectangularCalloutEquations(Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015e5a0  mov     word ptr [rsp+160h+var_120], 0
0x18015e5a7  mov     byte ptr [rsp+160h+var_120+2], 0
0x18015e5ac  mov     [rsp+160h+var_118], rsi
0x18015e5b1  mov     [rsp+160h+var_110], rsi
0x18015e5b6  mov     [rsp+160h+var_108], rsi
0x18015e5bb  mov     [rsp+160h+var_100], rsi
0x18015e5c0  mov     [rsp+160h+var_F8], rsi
0x18015e5c5  mov     [rsp+160h+var_F0], rsi
0x18015e5ca  mov     [rsp+160h+var_E8], rsi
0x18015e5cf  mov     [rbp+60h+var_E0], rsi
0x18015e5d3  mov     [rbp+60h+var_D8], rsi
0x18015e5d7  mov     [rbp+60h+var_D0], rsi
0x18015e5db  mov     [rbp+60h+var_C8], rsi
0x18015e5df  mov     [rbp+60h+var_C0], rsi
0x18015e5e3  mov     [rbp+60h+var_B8], rsi
0x18015e5e7  mov     [rbp+60h+var_B0], rsi
0x18015e5eb  call    cs:__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ; Art::FeatureGates::FUsingODF_1_4(void)
0x18015e5f1  test    al, al
0x18015e5f3  jz      short loc_18015E617
0x18015e5f5  lea     rdx, a0_2; "$0"
0x18015e5fc  lea     rcx, [rsp+160h+var_110]; this
0x18015e601  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015e606  lea     rdx, a1_4; "$1"
0x18015e60d  lea     rcx, [rsp+160h+var_108]; this
0x18015e612  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015e617  lea     rdx, a01; "$0 $1"
0x18015e61e  lea     rcx, [rsp+160h+var_118]; this
0x18015e623  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015e628  lea     rcx, [r14+18h]
0x18015e62c  lea     rdx, [rsp+160h+var_120]
0x18015e631  call    ?Push@?$TVector@VHandle@ODF@@$0A@$0PPPPPPPP@@Ofc@@QEAAXAEBVHandle@ODF@@@Z; Ofc::TVector<ODF::Handle,0,4294967295>::Push(ODF::Handle const &)
0x18015e636  nop
0x18015e637  lea     rcx, [rsp+160h+var_120]; this
0x18015e63c  call    ??1Handle@ODF@@QEAA@XZ; ODF::Handle::~Handle(void)
0x18015e641  lea     rcx, [rbx-0Ch]
0x18015e645  or      ebx, 0FFFFFFFFh
0x18015e648  cmp     dword ptr [rcx+4], 0
0x18015e64c  jz      short loc_18015E669
0x18015e64e  cmp     dword ptr [rcx], 1
0x18015e651  jz      short loc_18015E65D
0x18015e653  mov     eax, ebx
0x18015e655  lock xadd [rcx], eax
0x18015e659  add     eax, ebx
0x18015e65b  jnz     short loc_18015E669
0x18015e65d  test    rcx, rcx
0x18015e660  jz      short loc_18015E669
0x18015e662  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015e668  nop
0x18015e669  mov     rcx, [rbp+60h+arg_8]
0x18015e66d  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18015e671  cmp     dword ptr [rcx+4], 0
0x18015e675  jz      short loc_18015E692
0x18015e677  cmp     dword ptr [rcx], 1
0x18015e67a  jz      short loc_18015E686
0x18015e67c  mov     eax, ebx
0x18015e67e  lock xadd [rcx], eax
0x18015e682  add     eax, ebx
0x18015e684  jnz     short loc_18015E692
0x18015e686  test    rcx, rcx
0x18015e689  jz      short loc_18015E692
0x18015e68b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015e691  nop
0x18015e692  lea     rcx, [rbp+60h+var_68]
0x18015e696  call    cs:__imp_??1PresetGeometry2D@Art@@QEAA@XZ; Art::PresetGeometry2D::~PresetGeometry2D(void)
0x18015e69c  lea     rcx, [rbp+60h+var_A0]
0x18015e6a0  call    cs:__imp_??1GeometryCompiler@Art@@QEAA@XZ; Art::GeometryCompiler::~GeometryCompiler(void)
0x18015e6a6  lea     rcx, [rsp+160h+var_130]
0x18015e6ab  call    cs:__imp_??1Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::~Geometry2D(void)
0x18015e6b1  lea     r11, [rsp+160h+var_20]
0x18015e6b9  mov     rbx, [r11+30h]
0x18015e6bd  movaps  xmm6, xmmword ptr [r11-10h]
0x18015e6c2  mov     rsp, r11
0x18015e6c5  pop     r14
0x18015e6c7  pop     r12
0x18015e6c9  pop     rdi
0x18015e6ca  pop     rsi
0x18015e6cb  pop     rbp
0x18015e6cc  retn
0x18015e6cd  lea     rcx, ?tag_f5mb@Ofc@@3VMsoReserveTag@@B; "bm5f"
0x18015e6d4  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x18015e6d9  mov     ecx, eax; unsigned int
0x18015e6db  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18015e6e0  int     3; Trap to Debugger
```
