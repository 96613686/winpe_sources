# Art::ToOdfShapeGeometryConversion::WriteWedgeRRectCallout(Art::Geometry2D const &,Art::Transform2D const &,ODF::DrawShapeChoice_<0> &)

- ea: `0x18015ded0`
- end: `0x18015e2db`
- name: `?WriteWedgeRRectCallout@ToOdfShapeGeometryConversion@Art@@CAXAEBVGeometry2D@2@AEBVTransform2D@2@AEAV?$DrawShapeChoice_@$0A@@ODF@@@Z`
- size: `1035`
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
- `0x18015ded0`

## import_xrefs

- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015dffb`
- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015dffb`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015e28a`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015e28a`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015e093`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015e0e7`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015e093`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015e0e7`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015e061`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015e073`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015e061`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015e073`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015e294`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015e294`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015e1df`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015e1df`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015e2a5`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015e2a5`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015e01a`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015e01a`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015e050`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015e050`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015e256`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015e27f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015e256`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015e27f`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Art::ToOdfShapeGeometryConversion::WriteWedgeRRectCallout(
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
  Ofc::CStr::operator=(v6 + 48, (Ofc *)L"800 800 20800 20800");
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
    (Ofc *)L"M 3590 0 X 0 3590 L ?f2 ?f3 0 8970 0 12630 ?f4 ?f5 0 18010 Y 3590 21600 L ?f6 ?f7 8970 21600 12630 21600 ?f8 "
            "?f9 18010 21600 X 21600 18010 L ?f10 ?f11 21600 12630 21600 8970 ?f12 ?f13 21600 3590 Y 18010 0 L ?f14 ?f15 "
            "12630 0 8970 0 ?f16 ?f17 Z N");
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
0x18015ded0  mov     rax, rsp
0x18015ded3  mov     [rax+8], rbx
0x18015ded7  push    rbp
0x18015ded8  push    rsi
0x18015ded9  push    rdi
0x18015deda  push    r12
0x18015dedc  push    r14
0x18015dede  lea     rbp, [rax-68h]
0x18015dee2  sub     rsp, 140h
0x18015dee9  movaps  xmmword ptr [rax-38h], xmm6
0x18015deed  mov     rdi, rdx
0x18015def0  mov     rsi, rcx
0x18015def3  mov     rcx, r8
0x18015def6  call    ??$SwitchTo@UcustomShape@DrawShapeChoiceChoices@ODF@@@?$TChoice@VDrawShapeChoiceChoiceIDsImpl@ODF@@@Ofc@@QEAAAEAVCustomShape@ODF@@XZ; Ofc::TChoice<ODF::DrawShapeChoiceChoiceIDsImpl>::SwitchTo<ODF::DrawShapeChoiceChoices::customShape>(void)
0x18015defb  mov     rcx, [rax]
0x18015defe  add     rcx, 48h ; 'H'
0x18015df02  call    ?EnsureStorage@?$TOptional@VEnhancedGeometry@ODF@@@Ofc@@QEAAAEAVEnhancedGeometry@ODF@@XZ; Ofc::TOptional<ODF::EnhancedGeometry>::EnsureStorage(void)
0x18015df07  mov     r14, rax
0x18015df0a  lea     rcx, [rax+60h]
0x18015df0e  call    ?EnsureStorage@?$TOptional@V?$TArray@H@Ofc@@@Ofc@@QEAAAEAV?$TArray@H@2@XZ; Ofc::TOptional<Ofc::TArray<int>>::EnsureStorage(void)
0x18015df13  mov     rbx, rax
0x18015df16  lea     r12, ?Do@?$TCopyConstructRange@W4TextEmphasisType@ODF@@$00$00@Ofc@@SAXPEBEPEAEK@Z; Ofc::TCopyConstructRange<ODF::TextEmphasisType,1,1>::Do(uchar const *,uchar *,ulong)
0x18015df1d  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015df20  mov     edx, 4; unsigned int
0x18015df25  mov     rcx, rax; this
0x18015df28  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015df2d  mov     edx, [rbx+8]
0x18015df30  mov     rcx, [rbx]
0x18015df33  xor     eax, eax
0x18015df35  mov     [rcx+rdx*4], eax
0x18015df38  inc     dword ptr [rbx+8]
0x18015df3b  mov     [rcx+rdx*4], eax
0x18015df3e  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015df41  lea     edx, [rax+4]; unsigned int
0x18015df44  mov     rcx, rbx; this
0x18015df47  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015df4c  mov     ecx, [rbx+8]
0x18015df4f  mov     rax, [rbx]
0x18015df52  xor     edx, edx
0x18015df54  mov     [rax+rcx*4], edx
0x18015df57  inc     dword ptr [rbx+8]
0x18015df5a  mov     [rax+rcx*4], edx
0x18015df5d  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015df60  mov     edx, 4; unsigned int
0x18015df65  mov     rcx, rbx; this
0x18015df68  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015df6d  mov     ecx, [rbx+8]
0x18015df70  mov     rax, [rbx]
0x18015df73  xor     edx, edx
0x18015df75  mov     [rax+rcx*4], edx
0x18015df78  inc     dword ptr [rbx+8]
0x18015df7b  mov     dword ptr [rax+rcx*4], 5460h
0x18015df82  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015df85  lea     r12d, [rdx+4]
0x18015df89  mov     edx, r12d; unsigned int
0x18015df8c  mov     rcx, rbx; this
0x18015df8f  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015df94  mov     ecx, [rbx+8]
0x18015df97  mov     rax, [rbx]
0x18015df9a  xor     edx, edx
0x18015df9c  mov     [rax+rcx*4], edx
0x18015df9f  inc     dword ptr [rbx+8]
0x18015dfa2  mov     dword ptr [rax+rcx*4], 5460h
0x18015dfa9  lea     rcx, [r14+188h]; this
0x18015dfb0  lea     rdx, aF40F41; "?f40 ?f41"
0x18015dfb7  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015dfbc  lea     rcx, [r14+198h]; this
0x18015dfc3  lea     rdx, a180; "180"
0x18015dfca  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015dfcf  lea     rcx, [r14+180h]; this
0x18015dfd6  lea     rdx, a80080020800208; "800 800 20800 20800"
0x18015dfdd  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015dfe2  mov     dword ptr [rbp+60h+arg_8], 0
0x18015dfe9  lea     rcx, [r14+50h]
0x18015dfed  lea     rdx, [rbp+60h+arg_8]
0x18015dff1  call    ??$?4W4DrawCustomShapeType@ODF@@@?$TVariant@VCustomShapeTypeIDsImpl@ODF@@@Ofc@@QEAAAEAV01@AEBW4DrawCustomShapeType@ODF@@@Z; Ofc::TVariant<ODF::CustomShapeTypeIDsImpl>::operator=<ODF::DrawCustomShapeType>(ODF::DrawCustomShapeType const &)
0x18015dff6  lea     rcx, [rsp+160h+var_130]
0x18015dffb  call    cs:__imp_??0Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::Geometry2D(void)
0x18015e001  nop
0x18015e002  lea     r8, [rdi+10h]
0x18015e006  mov     [rsp+160h+var_140], 0FFh
0x18015e00e  lea     r9, [rsp+160h+var_130]
0x18015e013  mov     rdx, rsi
0x18015e016  lea     rcx, [rbp+60h+var_A0]
0x18015e01a  call    cs:__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z; Art::GeometryCompiler::GeometryCompiler(Art::Geometry2D const &,Art::PosSize2D const &,Art::Geometry2D &,ulong)
0x18015e020  nop
0x18015e021  mov     rcx, rsi
0x18015e024  call    ??$Is@UPreset@Geom@Art@@@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(void)
0x18015e029  test    al, al
0x18015e02b  jz      loc_18015E2C7
0x18015e031  cmp     qword ptr [rsi+8], 1
0x18015e036  ja      short loc_18015E040
0x18015e038  mov     rcx, rsi
0x18015e03b  call    ?DemandInit@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@AEBAXXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::DemandInit(void)
0x18015e040  mov     rdx, [rsi]
0x18015e043  test    rdx, rdx
0x18015e046  jz      loc_18015E2C7
0x18015e04c  lea     rcx, [rbp+60h+var_68]
0x18015e050  call    cs:__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z; Art::PresetGeometry2D::PresetGeometry2D(Art::PresetGeometry2D const &)
0x18015e056  nop
0x18015e057  mov     edx, r12d
0x18015e05a  lea     rcx, aAdj1; "adj1"
0x18015e061  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015e067  mov     ebx, eax
0x18015e069  mov     edx, r12d
0x18015e06c  lea     rcx, aAdj2; "adj2"
0x18015e073  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015e079  mov     edi, eax
0x18015e07b  lea     rsi, dword_1801DBD74
0x18015e082  mov     [rbp+60h+arg_8], rsi
0x18015e086  mov     [rbp+60h+arg_18], rsi
0x18015e08d  mov     edx, ebx
0x18015e08f  lea     rcx, [rbp+60h+var_A0]
0x18015e093  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015e099  mulsd   xmm0, cs:__real@40d5180000000000
0x18015e0a1  divsd   xmm0, cs:__real@40f86a0000000000
0x18015e0a9  addsd   xmm0, cs:__real@40c5180000000000
0x18015e0b1  movsd   xmm6, cs:__real@3fe0000000000000
0x18015e0b9  comisd  xmm0, cs:__real@0000000000000000
0x18015e0c1  jb      short loc_18015E0C8
0x18015e0c3  movaps  xmm1, xmm6
0x18015e0c6  jmp     short loc_18015E0D0
0x18015e0c8  movsd   xmm1, cs:__real@bfe0000000000000
0x18015e0d0  addsd   xmm1, xmm0
0x18015e0d4  cvttsd2si edx, xmm1; int
0x18015e0d8  lea     rcx, [rbp+60h+arg_8]; this
0x18015e0dc  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015e0e1  mov     edx, edi
0x18015e0e3  lea     rcx, [rbp+60h+var_A0]
0x18015e0e7  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015e0ed  mulsd   xmm0, cs:__real@40d5180000000000
0x18015e0f5  divsd   xmm0, cs:__real@40f86a0000000000
0x18015e0fd  addsd   xmm0, cs:__real@40c5180000000000
0x18015e105  comisd  xmm0, cs:__real@0000000000000000
0x18015e10d  jnb     short loc_18015E117
0x18015e10f  movsd   xmm6, cs:__real@bfe0000000000000
0x18015e117  addsd   xmm6, xmm0
0x18015e11b  cvttsd2si edx, xmm6; int
0x18015e11f  lea     rcx, [rbp+60h+arg_18]; this
0x18015e126  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015e12b  lea     rdi, [r14+1A8h]
0x18015e132  lea     rdx, [rbp+60h+arg_8]
0x18015e136  mov     rcx, rdi
0x18015e139  call    ??4CVarStr@Ofc@@QEAAAEAV01@AEBV01@@Z; Ofc::CVarStr::operator=(Ofc::CVarStr const &)
0x18015e13e  lea     rcx, asc_1801E05D8; " "
0x18015e145  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x18015e14a  mov     r8d, eax; int
0x18015e14d  lea     rdx, asc_1801E05D8; " "
0x18015e154  mov     rcx, rdi; this
0x18015e157  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015e15c  mov     rbx, [rbp+60h+arg_18]
0x18015e163  mov     eax, [rbx-4]
0x18015e166  cdq
0x18015e167  sub     eax, edx
0x18015e169  sar     eax, 1
0x18015e16b  mov     r8d, eax; int
0x18015e16e  mov     rdx, rbx; wchar_t *
0x18015e171  mov     rcx, rdi; this
0x18015e174  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015e179  lea     rcx, [r14+178h]; this
0x18015e180  lea     rdx, aM35900X03590LF; "M 3590 0 X 0 3590 L ?f2 ?f3 0 8970 0 12"...
0x18015e187  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015e18c  mov     rcx, r14
0x18015e18f  call    ?AddRectangularCalloutEquations@ToOdfShapeGeometryConversion@Art@@CAXAEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddRectangularCalloutEquations(Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015e194  mov     word ptr [rsp+160h+var_120], 0
0x18015e19b  mov     byte ptr [rsp+160h+var_120+2], 0
0x18015e1a0  mov     [rsp+160h+var_118], rsi
0x18015e1a5  mov     [rsp+160h+var_110], rsi
0x18015e1aa  mov     [rsp+160h+var_108], rsi
0x18015e1af  mov     [rsp+160h+var_100], rsi
0x18015e1b4  mov     [rsp+160h+var_F8], rsi
0x18015e1b9  mov     [rsp+160h+var_F0], rsi
0x18015e1be  mov     [rsp+160h+var_E8], rsi
0x18015e1c3  mov     [rbp+60h+var_E0], rsi
0x18015e1c7  mov     [rbp+60h+var_D8], rsi
0x18015e1cb  mov     [rbp+60h+var_D0], rsi
0x18015e1cf  mov     [rbp+60h+var_C8], rsi
0x18015e1d3  mov     [rbp+60h+var_C0], rsi
0x18015e1d7  mov     [rbp+60h+var_B8], rsi
0x18015e1db  mov     [rbp+60h+var_B0], rsi
0x18015e1df  call    cs:__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ; Art::FeatureGates::FUsingODF_1_4(void)
0x18015e1e5  test    al, al
0x18015e1e7  jz      short loc_18015E20B
0x18015e1e9  lea     rdx, a0_2; "$0"
0x18015e1f0  lea     rcx, [rsp+160h+var_110]; this
0x18015e1f5  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015e1fa  lea     rdx, a1_4; "$1"
0x18015e201  lea     rcx, [rsp+160h+var_108]; this
0x18015e206  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015e20b  lea     rdx, a01; "$0 $1"
0x18015e212  lea     rcx, [rsp+160h+var_118]; this
0x18015e217  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015e21c  lea     rcx, [r14+18h]
0x18015e220  lea     rdx, [rsp+160h+var_120]
0x18015e225  call    ?Push@?$TVector@VHandle@ODF@@$0A@$0PPPPPPPP@@Ofc@@QEAAXAEBVHandle@ODF@@@Z; Ofc::TVector<ODF::Handle,0,4294967295>::Push(ODF::Handle const &)
0x18015e22a  nop
0x18015e22b  lea     rcx, [rsp+160h+var_120]; this
0x18015e230  call    ??1Handle@ODF@@QEAA@XZ; ODF::Handle::~Handle(void)
0x18015e235  lea     rcx, [rbx-0Ch]
0x18015e239  or      ebx, 0FFFFFFFFh
0x18015e23c  cmp     dword ptr [rcx+4], 0
0x18015e240  jz      short loc_18015E25D
0x18015e242  cmp     dword ptr [rcx], 1
0x18015e245  jz      short loc_18015E251
0x18015e247  mov     eax, ebx
0x18015e249  lock xadd [rcx], eax
0x18015e24d  add     eax, ebx
0x18015e24f  jnz     short loc_18015E25D
0x18015e251  test    rcx, rcx
0x18015e254  jz      short loc_18015E25D
0x18015e256  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015e25c  nop
0x18015e25d  mov     rcx, [rbp+60h+arg_8]
0x18015e261  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18015e265  cmp     dword ptr [rcx+4], 0
0x18015e269  jz      short loc_18015E286
0x18015e26b  cmp     dword ptr [rcx], 1
0x18015e26e  jz      short loc_18015E27A
0x18015e270  mov     eax, ebx
0x18015e272  lock xadd [rcx], eax
0x18015e276  add     eax, ebx
0x18015e278  jnz     short loc_18015E286
0x18015e27a  test    rcx, rcx
0x18015e27d  jz      short loc_18015E286
0x18015e27f  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015e285  nop
0x18015e286  lea     rcx, [rbp+60h+var_68]
0x18015e28a  call    cs:__imp_??1PresetGeometry2D@Art@@QEAA@XZ; Art::PresetGeometry2D::~PresetGeometry2D(void)
0x18015e290  lea     rcx, [rbp+60h+var_A0]
0x18015e294  call    cs:__imp_??1GeometryCompiler@Art@@QEAA@XZ; Art::GeometryCompiler::~GeometryCompiler(void)
0x18015e29a  nop     word ptr [rax+rax+00h]
0x18015e2a0  lea     rcx, [rsp+160h+var_130]
0x18015e2a5  call    cs:__imp_??1Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::~Geometry2D(void)
0x18015e2ab  lea     r11, [rsp+160h+var_20]
0x18015e2b3  mov     rbx, [r11+30h]
0x18015e2b7  movaps  xmm6, xmmword ptr [r11-10h]
0x18015e2bc  mov     rsp, r11
0x18015e2bf  pop     r14
0x18015e2c1  pop     r12
0x18015e2c3  pop     rdi
0x18015e2c4  pop     rsi
0x18015e2c5  pop     rbp
0x18015e2c6  retn
0x18015e2c7  lea     rcx, ?tag_f5mb@Ofc@@3VMsoReserveTag@@B; "bm5f"
0x18015e2ce  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x18015e2d3  mov     ecx, eax; unsigned int
0x18015e2d5  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18015e2da  int     3; Trap to Debugger
```
