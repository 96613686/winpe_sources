# Art::ToOdfShapeGeometryConversion::WriteLeftArrow(Art::Geometry2D const &,Art::Transform2D const &,ODF::DrawShapeChoice_<0> &)

- ea: `0x18015bcb4`
- end: `0x18015c15f`
- name: `?WriteLeftArrow@ToOdfShapeGeometryConversion@Art@@CAXAEBVGeometry2D@2@AEBVTransform2D@2@AEAV?$DrawShapeChoice_@$0A@@ODF@@@Z`
- size: `1195`
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
- `0x18015aa8c`
- `0x18015af50`
- `0x18015bcb4`

## import_xrefs

- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015be2b`
- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015be2b`
- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015bdf3`
- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015bdf3`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015c110`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015c110`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015bec4`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015bf23`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015bec4`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015bf23`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015be8f`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015bea1`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015be8f`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015bea1`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015c11a`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015c11a`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015be0c`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015be0c`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015c01e`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015c01e`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015c124`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015c124`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015be48`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015be48`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015be7e`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015be7e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015c0d9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015c105`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015c0d9`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015c105`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Art::ToOdfShapeGeometryConversion::WriteLeftArrow(
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
  double v16; // xmm9_8
  double v17; // xmm9_8
  int v18; // ebx
  int v19; // edi
  double v20; // xmm6_8
  unsigned int v21; // r8d
  double v22; // xmm1_8
  double v23; // xmm0_8
  unsigned int v24; // r8d
  double v25; // xmm0_8
  const wchar_t *v26; // rdx
  int v27; // eax
  wchar_t *v28; // rbx
  Art::FeatureGates *v29; // rcx
  void *v30; // rdx
  Mso::Memory *v31; // rcx
  Mso::Memory *v32; // rcx
  unsigned int v33; // eax
  __int16 v34; // [rsp+38h] [rbp-D0h] BYREF
  char v35; // [rsp+3Ah] [rbp-CEh]
  wchar_t *v36; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t *v37; // [rsp+48h] [rbp-C0h] BYREF
  wchar_t *v38[3]; // [rsp+50h] [rbp-B8h] BYREF
  wchar_t *v39; // [rsp+68h] [rbp-A0h] BYREF
  wchar_t *v40; // [rsp+70h] [rbp-98h] BYREF
  wchar_t *v41; // [rsp+78h] [rbp-90h] BYREF
  wchar_t *v42[7]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v43[16]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v44[56]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v45[88]; // [rsp+100h] [rbp-8h] BYREF
  wchar_t *v46; // [rsp+190h] [rbp+88h] BYREF
  wchar_t *v47; // [rsp+1A0h] [rbp+98h] BYREF

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
  Ofc::CStr::operator=(v6 + 49, (Ofc *)L"?f1 0 ?f1 21600");
  Ofc::CStr::operator=(v6 + 51, (Ofc *)L"0, 180");
  Ofc::CStr::operator=(v6 + 48, (Ofc *)L"?f7 ?f0 21600 ?f2");
  LODWORD(v46) = 0;
  Ofc::TVariant<ODF::CustomShapeTypeIDsImpl>::operator=<enum ODF::DrawCustomShapeType>(v6 + 10, &v46);
  v16 = (double)(int)*(_QWORD *)Art::PosSize2D::GetCx(a2 + 16, &v46);
  v17 = v16 / fmin(v16, (double)(int)*(_QWORD *)Art::PosSize2D::GetCy(a2 + 16, &v46));
  Art::Geometry2D::Geometry2D((Art::Geometry2D *)v43);
  Art::GeometryCompiler::GeometryCompiler(
    (Art::GeometryCompiler *)v44,
    a1,
    (const struct Art::PosSize2D *)(a2 + 16),
    (struct Art::Geometry2D *)v43,
    0xFFu);
  if ( !(unsigned __int8)Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(a1) )
    goto LABEL_23;
  if ( *((_QWORD *)a1 + 1) <= 1u )
    Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::DemandInit(a1);
  if ( !*(_QWORD *)a1 )
  {
LABEL_23:
    v33 = MsoReserveTag::operator unsigned int("bm5f");
    Ofc::CInvalidParamException::ThrowTag(v33);
    __debugbreak();
  }
  Art::PresetGeometry2D::PresetGeometry2D((Art::PresetGeometry2D *)v45, *(const struct Art::PresetGeometry2D **)a1);
  v18 = Art::GeomGuideName::MapStringToToken(L"adj1", 4);
  v19 = Art::GeomGuideName::MapStringToToken(L"adj2", 4);
  v46 = (wchar_t *)&dword_1801DBD74;
  v47 = (wchar_t *)&dword_1801DBD74;
  v20 = DOUBLE_0_5;
  v22 = (21600.0 - Art::GeometryCompiler::Lookup((Art::GeometryCompiler *)v44, v18) * 21600.0 / 100000.0) * 0.5;
  if ( v22 < 0.0 )
    v23 = DOUBLE_N0_5;
  else
    v23 = DOUBLE_0_5;
  Ofc::CStr::DecodeInt(&v47, (int)(v23 + v22), v21);
  v25 = Art::GeometryCompiler::Lookup((Art::GeometryCompiler *)v44, v19) * 21600.0 / (v17 * 100000.0);
  if ( v25 < 0.0 )
    v20 = DOUBLE_N0_5;
  Ofc::CStr::DecodeInt(&v46, (int)(v20 + v25), v24);
  Ofc::CVarStr::operator=(v6 + 53, &v46);
  v27 = Ofc::CchWzLen((Ofc *)L" ", v26);
  Ofc::CStr::Append((Ofc::CStr *)(v6 + 53), L" ", v27);
  v28 = v47;
  Ofc::CStr::Append((Ofc::CStr *)(v6 + 53), v47, *((_DWORD *)v47 - 1) / 2);
  Ofc::CStr::operator=(v6 + 47, (Ofc *)L"M 21600 ?f0 L ?f1 ?f0 ?f1 0 0 10800 ?f1 21600 ?f1 ?f2 21600 ?f2 Z N");
  Art::ToOdfShapeGeometryConversion::AddArrowEquations(v6);
  v34 = 0;
  v35 = 0;
  v36 = (wchar_t *)&dword_1801DBD74;
  v37 = (wchar_t *)&dword_1801DBD74;
  v38[0] = (wchar_t *)&dword_1801DBD74;
  v38[1] = (wchar_t *)&dword_1801DBD74;
  v38[2] = (wchar_t *)&dword_1801DBD74;
  v39 = (wchar_t *)&dword_1801DBD74;
  v40 = (wchar_t *)&dword_1801DBD74;
  v41 = (wchar_t *)&dword_1801DBD74;
  v42[0] = (wchar_t *)&dword_1801DBD74;
  v42[1] = (wchar_t *)&dword_1801DBD74;
  v42[2] = (wchar_t *)&dword_1801DBD74;
  v42[3] = (wchar_t *)&dword_1801DBD74;
  v42[4] = (wchar_t *)&dword_1801DBD74;
  v42[5] = (wchar_t *)&dword_1801DBD74;
  if ( Art::FeatureGates::FUsingODF_1_4(v29) )
  {
    Ofc::CStr::operator=(&v37, (Ofc *)L"$0");
    Ofc::CStr::operator=(v38, (Ofc *)L"$1");
  }
  Ofc::CStr::operator=(&v36, (Ofc *)L"$0 $1");
  Ofc::CStr::operator=(&v39, (Ofc *)L"0");
  Ofc::CStr::operator=(&v40, (Ofc *)L"21600");
  Ofc::CStr::operator=(&v41, (Ofc *)L"0");
  Ofc::CStr::operator=(v42, (Ofc *)L"10800");
  Ofc::TVector<ODF::Handle,0,4294967295>::Push(v6 + 3, &v34);
  ODF::Handle::~Handle((ODF::Handle *)&v34);
  v31 = (Mso::Memory *)(v28 - 6);
  if ( *((_DWORD *)v28 - 2)
    && (*(_DWORD *)v31 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v31, 0xFFFFFFFF) == 1)
    && v28 != (wchar_t *)12 )
  {
    Mso::Memory::Free(v31, v30);
  }
  v32 = (Mso::Memory *)(v46 - 6);
  if ( *((_DWORD *)v46 - 2)
    && (*(_DWORD *)v32 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v32, 0xFFFFFFFF) == 1) )
  {
    if ( v32 )
      Mso::Memory::Free(v32, v30);
  }
  Art::PresetGeometry2D::~PresetGeometry2D((Art::PresetGeometry2D *)v45);
  Art::GeometryCompiler::~GeometryCompiler((Art::GeometryCompiler *)v44);
  Art::Geometry2D::~Geometry2D((Art::Geometry2D *)v43);
}

```

## disassembly

```asm
0x18015bcb4  mov     rax, rsp
0x18015bcb7  mov     [rax+8], rbx
0x18015bcbb  push    rbp
0x18015bcbc  push    rsi
0x18015bcbd  push    rdi
0x18015bcbe  push    r12
0x18015bcc0  push    r14
0x18015bcc2  lea     rbp, [rax-78h]
0x18015bcc6  sub     rsp, 150h
0x18015bccd  movaps  xmmword ptr [rax-38h], xmm6
0x18015bcd1  movaps  xmmword ptr [rax-48h], xmm9
0x18015bcd6  mov     rdi, rdx
0x18015bcd9  mov     rsi, rcx
0x18015bcdc  mov     rcx, r8
0x18015bcdf  call    ??$SwitchTo@UcustomShape@DrawShapeChoiceChoices@ODF@@@?$TChoice@VDrawShapeChoiceChoiceIDsImpl@ODF@@@Ofc@@QEAAAEAVCustomShape@ODF@@XZ; Ofc::TChoice<ODF::DrawShapeChoiceChoiceIDsImpl>::SwitchTo<ODF::DrawShapeChoiceChoices::customShape>(void)
0x18015bce4  mov     rcx, [rax]
0x18015bce7  add     rcx, 48h ; 'H'
0x18015bceb  call    ?EnsureStorage@?$TOptional@VEnhancedGeometry@ODF@@@Ofc@@QEAAAEAVEnhancedGeometry@ODF@@XZ; Ofc::TOptional<ODF::EnhancedGeometry>::EnsureStorage(void)
0x18015bcf0  mov     r14, rax
0x18015bcf3  lea     rcx, [rax+60h]
0x18015bcf7  call    ?EnsureStorage@?$TOptional@V?$TArray@H@Ofc@@@Ofc@@QEAAAEAV?$TArray@H@2@XZ; Ofc::TOptional<Ofc::TArray<int>>::EnsureStorage(void)
0x18015bcfc  mov     rbx, rax
0x18015bcff  lea     r12, ?Do@?$TCopyConstructRange@W4TextEmphasisType@ODF@@$00$00@Ofc@@SAXPEBEPEAEK@Z; Ofc::TCopyConstructRange<ODF::TextEmphasisType,1,1>::Do(uchar const *,uchar *,ulong)
0x18015bd06  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015bd09  mov     edx, 4; unsigned int
0x18015bd0e  mov     rcx, rax; this
0x18015bd11  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015bd16  mov     edx, [rbx+8]
0x18015bd19  mov     rcx, [rbx]
0x18015bd1c  xor     eax, eax
0x18015bd1e  mov     [rcx+rdx*4], eax
0x18015bd21  inc     dword ptr [rbx+8]
0x18015bd24  mov     [rcx+rdx*4], eax
0x18015bd27  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015bd2a  lea     edx, [rax+4]; unsigned int
0x18015bd2d  mov     rcx, rbx; this
0x18015bd30  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015bd35  mov     ecx, [rbx+8]
0x18015bd38  mov     rax, [rbx]
0x18015bd3b  xor     edx, edx
0x18015bd3d  mov     [rax+rcx*4], edx
0x18015bd40  inc     dword ptr [rbx+8]
0x18015bd43  mov     [rax+rcx*4], edx
0x18015bd46  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015bd49  mov     edx, 4; unsigned int
0x18015bd4e  mov     rcx, rbx; this
0x18015bd51  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015bd56  mov     ecx, [rbx+8]
0x18015bd59  mov     rax, [rbx]
0x18015bd5c  xor     edx, edx
0x18015bd5e  mov     [rax+rcx*4], edx
0x18015bd61  inc     dword ptr [rbx+8]
0x18015bd64  mov     dword ptr [rax+rcx*4], 5460h
0x18015bd6b  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015bd6e  lea     r12d, [rdx+4]
0x18015bd72  mov     edx, r12d; unsigned int
0x18015bd75  mov     rcx, rbx; this
0x18015bd78  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015bd7d  mov     ecx, [rbx+8]
0x18015bd80  mov     rax, [rbx]
0x18015bd83  xor     edx, edx
0x18015bd85  mov     [rax+rcx*4], edx
0x18015bd88  inc     dword ptr [rbx+8]
0x18015bd8b  mov     dword ptr [rax+rcx*4], 5460h
0x18015bd92  lea     rcx, [r14+188h]; this
0x18015bd99  lea     rdx, aF10F121600; "?f1 0 ?f1 21600"
0x18015bda0  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015bda5  lea     rcx, [r14+198h]; this
0x18015bdac  lea     rdx, a0180; "0, 180"
0x18015bdb3  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015bdb8  lea     rcx, [r14+180h]; this
0x18015bdbf  lea     rdx, aF7F021600F2; "?f7 ?f0 21600 ?f2"
0x18015bdc6  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015bdcb  mov     dword ptr [rbp+70h+arg_8], 0
0x18015bdd5  lea     rcx, [r14+50h]
0x18015bdd9  lea     rdx, [rbp+70h+arg_8]
0x18015bde0  call    ??$?4W4DrawCustomShapeType@ODF@@@?$TVariant@VCustomShapeTypeIDsImpl@ODF@@@Ofc@@QEAAAEAV01@AEBW4DrawCustomShapeType@ODF@@@Z; Ofc::TVariant<ODF::CustomShapeTypeIDsImpl>::operator=<ODF::DrawCustomShapeType>(ODF::DrawCustomShapeType const &)
0x18015bde5  lea     rbx, [rdi+10h]
0x18015bde9  lea     rdx, [rbp+70h+arg_8]
0x18015bdf0  mov     rcx, rbx
0x18015bdf3  call    cs:__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ; Art::PosSize2D::GetCx(void)
0x18015bdf9  xorps   xmm9, xmm9
0x18015bdfd  cvtsi2sd xmm9, qword ptr [rax]
0x18015be02  lea     rdx, [rbp+70h+arg_8]
0x18015be09  mov     rcx, rbx
0x18015be0c  call    cs:__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ; Art::PosSize2D::GetCy(void)
0x18015be12  xorps   xmm0, xmm0
0x18015be15  cvtsi2sd xmm0, qword ptr [rax]
0x18015be1a  movaps  xmm1, xmm9
0x18015be1e  minsd   xmm1, xmm0
0x18015be22  divsd   xmm9, xmm1
0x18015be27  lea     rcx, [rbp+70h+var_C0]
0x18015be2b  call    cs:__imp_??0Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::Geometry2D(void)
0x18015be31  nop
0x18015be32  mov     [rsp+170h+var_150], 0FFh
0x18015be3a  lea     r9, [rbp+70h+var_C0]
0x18015be3e  mov     r8, rbx
0x18015be41  mov     rdx, rsi
0x18015be44  lea     rcx, [rbp+70h+var_B0]
0x18015be48  call    cs:__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z; Art::GeometryCompiler::GeometryCompiler(Art::Geometry2D const &,Art::PosSize2D const &,Art::Geometry2D &,ulong)
0x18015be4e  nop
0x18015be4f  mov     rcx, rsi
0x18015be52  call    ??$Is@UPreset@Geom@Art@@@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(void)
0x18015be57  test    al, al
0x18015be59  jz      loc_18015C14B
0x18015be5f  cmp     qword ptr [rsi+8], 1
0x18015be64  ja      short loc_18015BE6E
0x18015be66  mov     rcx, rsi
0x18015be69  call    ?DemandInit@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@AEBAXXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::DemandInit(void)
0x18015be6e  mov     rdx, [rsi]
0x18015be71  test    rdx, rdx
0x18015be74  jz      loc_18015C14B
0x18015be7a  lea     rcx, [rbp+70h+var_78]
0x18015be7e  call    cs:__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z; Art::PresetGeometry2D::PresetGeometry2D(Art::PresetGeometry2D const &)
0x18015be84  nop
0x18015be85  mov     edx, r12d
0x18015be88  lea     rcx, aAdj1; "adj1"
0x18015be8f  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015be95  mov     ebx, eax
0x18015be97  mov     edx, r12d
0x18015be9a  lea     rcx, aAdj2; "adj2"
0x18015bea1  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015bea7  mov     edi, eax
0x18015bea9  lea     rsi, dword_1801DBD74
0x18015beb0  mov     [rbp+70h+arg_8], rsi
0x18015beb7  mov     [rbp+70h+arg_18], rsi
0x18015bebe  mov     edx, ebx
0x18015bec0  lea     rcx, [rbp+70h+var_B0]
0x18015bec4  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015beca  mulsd   xmm0, cs:__real@40d5180000000000
0x18015bed2  divsd   xmm0, cs:__real@40f86a0000000000
0x18015beda  movsd   xmm1, cs:__real@40d5180000000000
0x18015bee2  subsd   xmm1, xmm0
0x18015bee6  movsd   xmm6, cs:__real@3fe0000000000000
0x18015beee  mulsd   xmm1, xmm6
0x18015bef2  comisd  xmm1, cs:__real@0000000000000000
0x18015befa  jb      short loc_18015BF01
0x18015befc  movaps  xmm0, xmm6
0x18015beff  jmp     short loc_18015BF09
0x18015bf01  movsd   xmm0, cs:__real@bfe0000000000000
0x18015bf09  addsd   xmm0, xmm1
0x18015bf0d  cvttsd2si edx, xmm0; int
0x18015bf11  lea     rcx, [rbp+70h+arg_18]; this
0x18015bf18  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015bf1d  mov     edx, edi
0x18015bf1f  lea     rcx, [rbp+70h+var_B0]
0x18015bf23  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015bf29  mulsd   xmm0, cs:__real@40d5180000000000
0x18015bf31  mulsd   xmm9, cs:__real@40f86a0000000000
0x18015bf3a  divsd   xmm0, xmm9
0x18015bf3f  comisd  xmm0, cs:__real@0000000000000000
0x18015bf47  jnb     short loc_18015BF51
0x18015bf49  movsd   xmm6, cs:__real@bfe0000000000000
0x18015bf51  addsd   xmm6, xmm0
0x18015bf55  cvttsd2si edx, xmm6; int
0x18015bf59  lea     rcx, [rbp+70h+arg_8]; this
0x18015bf60  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015bf65  lea     rdi, [r14+1A8h]
0x18015bf6c  lea     rdx, [rbp+70h+arg_8]
0x18015bf73  mov     rcx, rdi
0x18015bf76  call    ??4CVarStr@Ofc@@QEAAAEAV01@AEBV01@@Z; Ofc::CVarStr::operator=(Ofc::CVarStr const &)
0x18015bf7b  lea     rcx, asc_1801E05D8; " "
0x18015bf82  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x18015bf87  mov     r8d, eax; int
0x18015bf8a  lea     rdx, asc_1801E05D8; " "
0x18015bf91  mov     rcx, rdi; this
0x18015bf94  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015bf99  mov     rbx, [rbp+70h+arg_18]
0x18015bfa0  mov     eax, [rbx-4]
0x18015bfa3  cdq
0x18015bfa4  sub     eax, edx
0x18015bfa6  sar     eax, 1
0x18015bfa8  mov     r8d, eax; int
0x18015bfab  mov     rdx, rbx; wchar_t *
0x18015bfae  mov     rcx, rdi; this
0x18015bfb1  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015bfb6  lea     rcx, [r14+178h]; this
0x18015bfbd  lea     rdx, aM21600F0LF1F0F; "M 21600 ?f0 L ?f1 ?f0 ?f1 0 0 10800 ?f1"...
0x18015bfc4  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015bfc9  mov     rcx, r14
0x18015bfcc  call    ?AddArrowEquations@ToOdfShapeGeometryConversion@Art@@CAXAEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddArrowEquations(Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015bfd1  mov     word ptr [rsp+170h+var_140], 0
0x18015bfd8  mov     byte ptr [rsp+170h+var_140+2], 0
0x18015bfdd  mov     [rsp+170h+var_138], rsi
0x18015bfe2  mov     [rsp+170h+var_130], rsi
0x18015bfe7  mov     [rsp+170h+var_128], rsi
0x18015bfec  mov     [rsp+170h+var_120], rsi
0x18015bff1  mov     [rsp+170h+var_118], rsi
0x18015bff6  mov     [rsp+170h+var_110], rsi
0x18015bffb  mov     [rsp+170h+var_108], rsi
0x18015c000  mov     [rsp+170h+var_100], rsi
0x18015c005  mov     [rsp+170h+var_F8], rsi
0x18015c00a  mov     [rbp+70h+var_F0], rsi
0x18015c00e  mov     [rbp+70h+var_E8], rsi
0x18015c012  mov     [rbp+70h+var_E0], rsi
0x18015c016  mov     [rbp+70h+var_D8], rsi
0x18015c01a  mov     [rbp+70h+var_D0], rsi
0x18015c01e  call    cs:__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ; Art::FeatureGates::FUsingODF_1_4(void)
0x18015c024  test    al, al
0x18015c026  jz      short loc_18015C04A
0x18015c028  lea     rdx, a0_2; "$0"
0x18015c02f  lea     rcx, [rsp+170h+var_130]; this
0x18015c034  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c039  lea     rdx, a1_4; "$1"
0x18015c040  lea     rcx, [rsp+170h+var_128]; this
0x18015c045  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c04a  lea     rdx, a01; "$0 $1"
0x18015c051  lea     rcx, [rsp+170h+var_138]; this
0x18015c056  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c05b  lea     rdx, a0_1; "0"
0x18015c062  lea     rcx, [rsp+170h+var_110]; this
0x18015c067  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c06c  lea     rdx, a21600; "21600"
0x18015c073  lea     rcx, [rsp+170h+var_108]; this
0x18015c078  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c07d  lea     rdx, a0_1; "0"
0x18015c084  lea     rcx, [rsp+170h+var_100]; this
0x18015c089  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c08e  lea     rdx, a10800; "10800"
0x18015c095  lea     rcx, [rsp+170h+var_F8]; this
0x18015c09a  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c09f  lea     rcx, [r14+18h]
0x18015c0a3  lea     rdx, [rsp+170h+var_140]
0x18015c0a8  call    ?Push@?$TVector@VHandle@ODF@@$0A@$0PPPPPPPP@@Ofc@@QEAAXAEBVHandle@ODF@@@Z; Ofc::TVector<ODF::Handle,0,4294967295>::Push(ODF::Handle const &)
0x18015c0ad  nop
0x18015c0ae  lea     rcx, [rsp+170h+var_140]; this
0x18015c0b3  call    ??1Handle@ODF@@QEAA@XZ; ODF::Handle::~Handle(void)
0x18015c0b8  lea     rcx, [rbx-0Ch]
0x18015c0bc  or      ebx, 0FFFFFFFFh
0x18015c0bf  cmp     dword ptr [rcx+4], 0
0x18015c0c3  jz      short loc_18015C0E0
0x18015c0c5  cmp     dword ptr [rcx], 1
0x18015c0c8  jz      short loc_18015C0D4
0x18015c0ca  mov     eax, ebx
0x18015c0cc  lock xadd [rcx], eax
0x18015c0d0  add     eax, ebx
0x18015c0d2  jnz     short loc_18015C0E0
0x18015c0d4  test    rcx, rcx
0x18015c0d7  jz      short loc_18015C0E0
0x18015c0d9  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015c0df  nop
0x18015c0e0  mov     rcx, [rbp+70h+arg_8]
0x18015c0e7  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18015c0eb  cmp     dword ptr [rcx+4], 0
0x18015c0ef  jz      short loc_18015C10C
0x18015c0f1  cmp     dword ptr [rcx], 1
0x18015c0f4  jz      short loc_18015C100
0x18015c0f6  mov     eax, ebx
0x18015c0f8  lock xadd [rcx], eax
0x18015c0fc  add     eax, ebx
0x18015c0fe  jnz     short loc_18015C10C
0x18015c100  test    rcx, rcx
0x18015c103  jz      short loc_18015C10C
0x18015c105  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015c10b  nop
0x18015c10c  lea     rcx, [rbp+70h+var_78]
0x18015c110  call    cs:__imp_??1PresetGeometry2D@Art@@QEAA@XZ; Art::PresetGeometry2D::~PresetGeometry2D(void)
0x18015c116  lea     rcx, [rbp+70h+var_B0]
0x18015c11a  call    cs:__imp_??1GeometryCompiler@Art@@QEAA@XZ; Art::GeometryCompiler::~GeometryCompiler(void)
0x18015c120  lea     rcx, [rbp+70h+var_C0]
0x18015c124  call    cs:__imp_??1Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::~Geometry2D(void)
0x18015c12a  lea     r11, [rsp+170h+var_20]
0x18015c132  mov     rbx, [r11+30h]
0x18015c136  movaps  xmm6, xmmword ptr [r11-10h]
0x18015c13b  movaps  xmm9, xmmword ptr [r11-20h]
0x18015c140  mov     rsp, r11
0x18015c143  pop     r14
0x18015c145  pop     r12
0x18015c147  pop     rdi
0x18015c148  pop     rsi
0x18015c149  pop     rbp
0x18015c14a  retn
0x18015c14b  lea     rcx, ?tag_f5mb@Ofc@@3VMsoReserveTag@@B; "bm5f"
0x18015c152  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x18015c157  mov     ecx, eax; unsigned int
0x18015c159  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18015c15e  int     3; Trap to Debugger
```
