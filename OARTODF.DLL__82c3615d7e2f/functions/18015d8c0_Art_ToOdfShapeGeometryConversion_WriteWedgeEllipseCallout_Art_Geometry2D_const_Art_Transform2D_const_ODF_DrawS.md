# Art::ToOdfShapeGeometryConversion::WriteWedgeEllipseCallout(Art::Geometry2D const &,Art::Transform2D const &,ODF::DrawShapeChoice_<0> &)

- ea: `0x18015d8c0`
- end: `0x18015decd`
- name: `?WriteWedgeEllipseCallout@ToOdfShapeGeometryConversion@Art@@CAXAEBVGeometry2D@2@AEBVTransform2D@2@AEAV?$DrawShapeChoice_@$0A@@ODF@@@Z`
- size: `1549`
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
- `0x18015ab48`
- `0x18015af50`
- `0x18015d8c0`

## import_xrefs

- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015d9eb`
- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015d9eb`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015de82`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015de82`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015da83`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015dad7`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015da83`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015dad7`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015da51`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015da63`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015da51`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015da63`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015de8c`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015de8c`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015ddd7`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015ddd7`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015de97`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015de97`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015da0a`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015da0a`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015da40`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015da40`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015de4e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015de77`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015de4e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015de77`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Art::ToOdfShapeGeometryConversion::WriteWedgeEllipseCallout(
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
  Ofc::CStr::operator=(v6 + 49, (Ofc *)L"3160 3160 3160 18440 18440 18440 18440 3160 ?f14 ?f15");
  Ofc::CStr::operator=(v6 + 51, (Ofc *)L"0, 180, 180, 0, -194.0324");
  Ofc::CStr::operator=(v6 + 48, (Ofc *)L"3200 3200 18400 18400");
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
  Ofc::CStr::operator=(v6 + 47, (Ofc *)L"W 0 0 21600 21600 ?f22 ?f23 ?f18 ?f19 L ?f14 ?f15 Z N");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f0", (Ofc *)L"$0 -10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f1", (Ofc *)L"$1 -10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f2", (Ofc *)L"?f0 *?f0 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f3", (Ofc *)L"?f1 *?f1 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f4", (Ofc *)L"?f2 +?f3 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f5", (Ofc *)L"sqrt(?f4 )");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f6", (Ofc *)L"?f5 -10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f7", (Ofc *)L"atan2(?f1 ,?f0 )/(pi/180)");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f8", (Ofc *)L"?f7 -10");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f9", (Ofc *)L"?f7 +10");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f10", (Ofc *)L"10800*cos(?f7 *(pi/180))");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f11", (Ofc *)L"10800*sin(?f7 *(pi/180))");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f12", (Ofc *)L"?f10 +10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f13", (Ofc *)L"?f11 +10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f14", (Ofc *)L"if(?f6 ,$0 ,?f12 )");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f15", (Ofc *)L"if(?f6 ,$1 ,?f13 )");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f16", (Ofc *)L"10800*cos(?f8 *(pi/180))");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f17", (Ofc *)L"10800*sin(?f8 *(pi/180))");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f18", (Ofc *)L"?f16 +10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f19", (Ofc *)L"?f17 +10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f20", (Ofc *)L"10800*cos(?f9 *(pi/180))");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f21", (Ofc *)L"10800*sin(?f9 *(pi/180))");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f22", (Ofc *)L"?f20 +10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f23", (Ofc *)L"?f21 +10800");
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
0x18015d8c0  mov     rax, rsp
0x18015d8c3  mov     [rax+8], rbx
0x18015d8c7  push    rbp
0x18015d8c8  push    rsi
0x18015d8c9  push    rdi
0x18015d8ca  push    r12
0x18015d8cc  push    r14
0x18015d8ce  lea     rbp, [rax-68h]
0x18015d8d2  sub     rsp, 140h
0x18015d8d9  movaps  xmmword ptr [rax-38h], xmm6
0x18015d8dd  mov     rdi, rdx
0x18015d8e0  mov     rsi, rcx
0x18015d8e3  mov     rcx, r8
0x18015d8e6  call    ??$SwitchTo@UcustomShape@DrawShapeChoiceChoices@ODF@@@?$TChoice@VDrawShapeChoiceChoiceIDsImpl@ODF@@@Ofc@@QEAAAEAVCustomShape@ODF@@XZ; Ofc::TChoice<ODF::DrawShapeChoiceChoiceIDsImpl>::SwitchTo<ODF::DrawShapeChoiceChoices::customShape>(void)
0x18015d8eb  mov     rcx, [rax]
0x18015d8ee  add     rcx, 48h ; 'H'
0x18015d8f2  call    ?EnsureStorage@?$TOptional@VEnhancedGeometry@ODF@@@Ofc@@QEAAAEAVEnhancedGeometry@ODF@@XZ; Ofc::TOptional<ODF::EnhancedGeometry>::EnsureStorage(void)
0x18015d8f7  mov     r14, rax
0x18015d8fa  lea     rcx, [rax+60h]
0x18015d8fe  call    ?EnsureStorage@?$TOptional@V?$TArray@H@Ofc@@@Ofc@@QEAAAEAV?$TArray@H@2@XZ; Ofc::TOptional<Ofc::TArray<int>>::EnsureStorage(void)
0x18015d903  mov     rbx, rax
0x18015d906  lea     r12, ?Do@?$TCopyConstructRange@W4TextEmphasisType@ODF@@$00$00@Ofc@@SAXPEBEPEAEK@Z; Ofc::TCopyConstructRange<ODF::TextEmphasisType,1,1>::Do(uchar const *,uchar *,ulong)
0x18015d90d  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015d910  mov     edx, 4; unsigned int
0x18015d915  mov     rcx, rax; this
0x18015d918  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015d91d  mov     edx, [rbx+8]
0x18015d920  mov     rcx, [rbx]
0x18015d923  xor     eax, eax
0x18015d925  mov     [rcx+rdx*4], eax
0x18015d928  inc     dword ptr [rbx+8]
0x18015d92b  mov     [rcx+rdx*4], eax
0x18015d92e  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015d931  lea     edx, [rax+4]; unsigned int
0x18015d934  mov     rcx, rbx; this
0x18015d937  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015d93c  mov     ecx, [rbx+8]
0x18015d93f  mov     rax, [rbx]
0x18015d942  xor     edx, edx
0x18015d944  mov     [rax+rcx*4], edx
0x18015d947  inc     dword ptr [rbx+8]
0x18015d94a  mov     [rax+rcx*4], edx
0x18015d94d  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015d950  mov     edx, 4; unsigned int
0x18015d955  mov     rcx, rbx; this
0x18015d958  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015d95d  mov     ecx, [rbx+8]
0x18015d960  mov     rax, [rbx]
0x18015d963  xor     edx, edx
0x18015d965  mov     [rax+rcx*4], edx
0x18015d968  inc     dword ptr [rbx+8]
0x18015d96b  mov     dword ptr [rax+rcx*4], 5460h
0x18015d972  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015d975  lea     r12d, [rdx+4]
0x18015d979  mov     edx, r12d; unsigned int
0x18015d97c  mov     rcx, rbx; this
0x18015d97f  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015d984  mov     ecx, [rbx+8]
0x18015d987  mov     rax, [rbx]
0x18015d98a  xor     edx, edx
0x18015d98c  mov     [rax+rcx*4], edx
0x18015d98f  inc     dword ptr [rbx+8]
0x18015d992  mov     dword ptr [rax+rcx*4], 5460h
0x18015d999  lea     rcx, [r14+188h]; this
0x18015d9a0  lea     rdx, a31603160316018; "3160 3160 3160 18440 18440 18440 18440 "...
0x18015d9a7  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d9ac  lea     rcx, [r14+198h]; this
0x18015d9b3  lea     rdx, a01801800194032; "0, 180, 180, 0, -194.0324"
0x18015d9ba  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d9bf  lea     rcx, [r14+180h]; this
0x18015d9c6  lea     rdx, a32003200184001; "3200 3200 18400 18400"
0x18015d9cd  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d9d2  mov     dword ptr [rbp+60h+arg_8], 0
0x18015d9d9  lea     rcx, [r14+50h]
0x18015d9dd  lea     rdx, [rbp+60h+arg_8]
0x18015d9e1  call    ??$?4W4DrawCustomShapeType@ODF@@@?$TVariant@VCustomShapeTypeIDsImpl@ODF@@@Ofc@@QEAAAEAV01@AEBW4DrawCustomShapeType@ODF@@@Z; Ofc::TVariant<ODF::CustomShapeTypeIDsImpl>::operator=<ODF::DrawCustomShapeType>(ODF::DrawCustomShapeType const &)
0x18015d9e6  lea     rcx, [rsp+160h+var_130]
0x18015d9eb  call    cs:__imp_??0Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::Geometry2D(void)
0x18015d9f1  nop
0x18015d9f2  lea     r8, [rdi+10h]
0x18015d9f6  mov     [rsp+160h+var_140], 0FFh
0x18015d9fe  lea     r9, [rsp+160h+var_130]
0x18015da03  mov     rdx, rsi
0x18015da06  lea     rcx, [rbp+60h+var_A0]
0x18015da0a  call    cs:__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z; Art::GeometryCompiler::GeometryCompiler(Art::Geometry2D const &,Art::PosSize2D const &,Art::Geometry2D &,ulong)
0x18015da10  nop
0x18015da11  mov     rcx, rsi
0x18015da14  call    ??$Is@UPreset@Geom@Art@@@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(void)
0x18015da19  test    al, al
0x18015da1b  jz      loc_18015DEB9
0x18015da21  cmp     qword ptr [rsi+8], 1
0x18015da26  ja      short loc_18015DA30
0x18015da28  mov     rcx, rsi
0x18015da2b  call    ?DemandInit@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@AEBAXXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::DemandInit(void)
0x18015da30  mov     rdx, [rsi]
0x18015da33  test    rdx, rdx
0x18015da36  jz      loc_18015DEB9
0x18015da3c  lea     rcx, [rbp+60h+var_68]
0x18015da40  call    cs:__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z; Art::PresetGeometry2D::PresetGeometry2D(Art::PresetGeometry2D const &)
0x18015da46  nop
0x18015da47  mov     edx, r12d
0x18015da4a  lea     rcx, aAdj1; "adj1"
0x18015da51  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015da57  mov     ebx, eax
0x18015da59  mov     edx, r12d
0x18015da5c  lea     rcx, aAdj2; "adj2"
0x18015da63  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015da69  mov     edi, eax
0x18015da6b  lea     rsi, dword_1801DBD74
0x18015da72  mov     [rbp+60h+arg_8], rsi
0x18015da76  mov     [rbp+60h+arg_18], rsi
0x18015da7d  mov     edx, ebx
0x18015da7f  lea     rcx, [rbp+60h+var_A0]
0x18015da83  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015da89  mulsd   xmm0, cs:__real@40d5180000000000
0x18015da91  divsd   xmm0, cs:__real@40f86a0000000000
0x18015da99  addsd   xmm0, cs:__real@40c5180000000000
0x18015daa1  movsd   xmm6, cs:__real@3fe0000000000000
0x18015daa9  comisd  xmm0, cs:__real@0000000000000000
0x18015dab1  jb      short loc_18015DAB8
0x18015dab3  movaps  xmm1, xmm6
0x18015dab6  jmp     short loc_18015DAC0
0x18015dab8  movsd   xmm1, cs:__real@bfe0000000000000
0x18015dac0  addsd   xmm1, xmm0
0x18015dac4  cvttsd2si edx, xmm1; int
0x18015dac8  lea     rcx, [rbp+60h+arg_8]; this
0x18015dacc  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015dad1  mov     edx, edi
0x18015dad3  lea     rcx, [rbp+60h+var_A0]
0x18015dad7  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015dadd  mulsd   xmm0, cs:__real@40d5180000000000
0x18015dae5  divsd   xmm0, cs:__real@40f86a0000000000
0x18015daed  addsd   xmm0, cs:__real@40c5180000000000
0x18015daf5  comisd  xmm0, cs:__real@0000000000000000
0x18015dafd  jnb     short loc_18015DB07
0x18015daff  movsd   xmm6, cs:__real@bfe0000000000000
0x18015db07  addsd   xmm6, xmm0
0x18015db0b  cvttsd2si edx, xmm6; int
0x18015db0f  lea     rcx, [rbp+60h+arg_18]; this
0x18015db16  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015db1b  lea     rdi, [r14+1A8h]
0x18015db22  lea     rdx, [rbp+60h+arg_8]
0x18015db26  mov     rcx, rdi
0x18015db29  call    ??4CVarStr@Ofc@@QEAAAEAV01@AEBV01@@Z; Ofc::CVarStr::operator=(Ofc::CVarStr const &)
0x18015db2e  lea     rcx, asc_1801E05D8; " "
0x18015db35  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x18015db3a  mov     r8d, eax; int
0x18015db3d  lea     rdx, asc_1801E05D8; " "
0x18015db44  mov     rcx, rdi; this
0x18015db47  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015db4c  mov     rbx, [rbp+60h+arg_18]
0x18015db53  mov     eax, [rbx-4]
0x18015db56  cdq
0x18015db57  sub     eax, edx
0x18015db59  sar     eax, 1
0x18015db5b  mov     r8d, eax; int
0x18015db5e  mov     rdx, rbx; wchar_t *
0x18015db61  mov     rcx, rdi; this
0x18015db64  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015db69  lea     rcx, [r14+178h]; this
0x18015db70  lea     rdx, aW002160021600F; "W 0 0 21600 21600 ?f22 ?f23 ?f18 ?f19 L"...
0x18015db77  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015db7c  mov     r8, r14
0x18015db7f  lea     rdx, a010800; "$0 -10800"
0x18015db86  lea     rcx, aF0; "f0"
0x18015db8d  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015db92  mov     r8, r14
0x18015db95  lea     rdx, a110800; "$1 -10800"
0x18015db9c  lea     rcx, aF1; "f1"
0x18015dba3  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dba8  mov     r8, r14
0x18015dbab  lea     rdx, aF0F0; "?f0 *?f0 "
0x18015dbb2  lea     rcx, aF2; "f2"
0x18015dbb9  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dbbe  mov     r8, r14
0x18015dbc1  lea     rdx, aF1F1; "?f1 *?f1 "
0x18015dbc8  lea     rcx, aF3; "f3"
0x18015dbcf  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dbd4  mov     r8, r14
0x18015dbd7  lea     rdx, aF2F3; "?f2 +?f3 "
0x18015dbde  lea     rcx, aF4; "f4"
0x18015dbe5  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dbea  mov     r8, r14
0x18015dbed  lea     rdx, aSqrtF4; "sqrt(?f4 )"
0x18015dbf4  lea     rcx, aF5; "f5"
0x18015dbfb  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dc00  mov     r8, r14
0x18015dc03  lea     rdx, aF510800; "?f5 -10800"
0x18015dc0a  lea     rcx, aF6; "f6"
0x18015dc11  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dc16  mov     r8, r14
0x18015dc19  lea     rdx, aAtan2F1F0Pi180; "atan2(?f1 ,?f0 )/(pi/180)"
0x18015dc20  lea     rcx, aF7; "f7"
0x18015dc27  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dc2c  mov     r8, r14
0x18015dc2f  lea     rdx, aF710; "?f7 -10"
0x18015dc36  lea     rcx, aF8; "f8"
0x18015dc3d  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dc42  mov     r8, r14
0x18015dc45  lea     rdx, aF710_0; "?f7 +10"
0x18015dc4c  lea     rcx, aF9; "f9"
0x18015dc53  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dc58  mov     r8, r14
0x18015dc5b  lea     rdx, a10800CosF7Pi18; "10800*cos(?f7 *(pi/180))"
0x18015dc62  lea     rcx, aF10; "f10"
0x18015dc69  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dc6e  mov     r8, r14
0x18015dc71  lea     rdx, a10800SinF7Pi18; "10800*sin(?f7 *(pi/180))"
0x18015dc78  lea     rcx, aF11; "f11"
0x18015dc7f  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dc84  mov     r8, r14
0x18015dc87  lea     rdx, aF1010800; "?f10 +10800"
0x18015dc8e  lea     rcx, aF12; "f12"
0x18015dc95  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dc9a  mov     r8, r14
0x18015dc9d  lea     rdx, aF1110800; "?f11 +10800"
0x18015dca4  lea     rcx, aF13; "f13"
0x18015dcab  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dcb0  mov     r8, r14
0x18015dcb3  lea     rdx, aIfF60F12; "if(?f6 ,$0 ,?f12 )"
0x18015dcba  lea     rcx, aF14; "f14"
0x18015dcc1  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dcc6  mov     r8, r14
0x18015dcc9  lea     rdx, aIfF61F13; "if(?f6 ,$1 ,?f13 )"
0x18015dcd0  lea     rcx, aF15; "f15"
0x18015dcd7  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dcdc  mov     r8, r14
0x18015dcdf  lea     rdx, a10800CosF8Pi18; "10800*cos(?f8 *(pi/180))"
0x18015dce6  lea     rcx, aF16; "f16"
0x18015dced  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dcf2  mov     r8, r14
0x18015dcf5  lea     rdx, a10800SinF8Pi18; "10800*sin(?f8 *(pi/180))"
0x18015dcfc  lea     rcx, aF17; "f17"
0x18015dd03  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dd08  mov     r8, r14
0x18015dd0b  lea     rdx, aF1610800; "?f16 +10800"
0x18015dd12  lea     rcx, aF18; "f18"
0x18015dd19  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dd1e  mov     r8, r14
0x18015dd21  lea     rdx, aF1710800; "?f17 +10800"
0x18015dd28  lea     rcx, aF19; "f19"
0x18015dd2f  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dd34  mov     r8, r14
0x18015dd37  lea     rdx, a10800CosF9Pi18; "10800*cos(?f9 *(pi/180))"
0x18015dd3e  lea     rcx, aF20; "f20"
0x18015dd45  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dd4a  mov     r8, r14
0x18015dd4d  lea     rdx, a10800SinF9Pi18; "10800*sin(?f9 *(pi/180))"
0x18015dd54  lea     rcx, aF21; "f21"
0x18015dd5b  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dd60  mov     r8, r14
0x18015dd63  lea     rdx, aF2010800; "?f20 +10800"
0x18015dd6a  lea     rcx, aF22; "f22"
0x18015dd71  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dd76  mov     r8, r14
0x18015dd79  lea     rdx, aF2110800; "?f21 +10800"
0x18015dd80  lea     rcx, aF23; "f23"
0x18015dd87  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015dd8c  mov     word ptr [rsp+160h+var_120], 0
0x18015dd93  mov     byte ptr [rsp+160h+var_120+2], 0
0x18015dd98  mov     [rsp+160h+var_118], rsi
0x18015dd9d  mov     [rsp+160h+var_110], rsi
0x18015dda2  mov     [rsp+160h+var_108], rsi
0x18015dda7  mov     [rsp+160h+var_100], rsi
0x18015ddac  mov     [rsp+160h+var_F8], rsi
0x18015ddb1  mov     [rsp+160h+var_F0], rsi
0x18015ddb6  mov     [rsp+160h+var_E8], rsi
0x18015ddbb  mov     [rbp+60h+var_E0], rsi
0x18015ddbf  mov     [rbp+60h+var_D8], rsi
0x18015ddc3  mov     [rbp+60h+var_D0], rsi
0x18015ddc7  mov     [rbp+60h+var_C8], rsi
0x18015ddcb  mov     [rbp+60h+var_C0], rsi
0x18015ddcf  mov     [rbp+60h+var_B8], rsi
0x18015ddd3  mov     [rbp+60h+var_B0], rsi
0x18015ddd7  call    cs:__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ; Art::FeatureGates::FUsingODF_1_4(void)
0x18015dddd  test    al, al
0x18015dddf  jz      short loc_18015DE03
0x18015dde1  lea     rdx, a0_2; "$0"
0x18015dde8  lea     rcx, [rsp+160h+var_110]; this
0x18015dded  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015ddf2  lea     rdx, a1_4; "$1"
0x18015ddf9  lea     rcx, [rsp+160h+var_108]; this
0x18015ddfe  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015de03  lea     rdx, a01; "$0 $1"
0x18015de0a  lea     rcx, [rsp+160h+var_118]; this
0x18015de0f  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015de14  lea     rcx, [r14+18h]
0x18015de18  lea     rdx, [rsp+160h+var_120]
0x18015de1d  call    ?Push@?$TVector@VHandle@ODF@@$0A@$0PPPPPPPP@@Ofc@@QEAAXAEBVHandle@ODF@@@Z; Ofc::TVector<ODF::Handle,0,4294967295>::Push(ODF::Handle const &)
0x18015de22  nop
0x18015de23  lea     rcx, [rsp+160h+var_120]; this
0x18015de28  call    ??1Handle@ODF@@QEAA@XZ; ODF::Handle::~Handle(void)
0x18015de2d  lea     rcx, [rbx-0Ch]
0x18015de31  or      ebx, 0FFFFFFFFh
0x18015de34  cmp     dword ptr [rcx+4], 0
0x18015de38  jz      short loc_18015DE55
0x18015de3a  cmp     dword ptr [rcx], 1
0x18015de3d  jz      short loc_18015DE49
0x18015de3f  mov     eax, ebx
0x18015de41  lock xadd [rcx], eax
  ... truncated ...
```
