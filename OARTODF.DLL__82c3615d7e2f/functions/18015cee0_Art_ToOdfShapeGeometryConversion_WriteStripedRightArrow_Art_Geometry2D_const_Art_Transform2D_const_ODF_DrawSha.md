# Art::ToOdfShapeGeometryConversion::WriteStripedRightArrow(Art::Geometry2D const &,Art::Transform2D const &,ODF::DrawShapeChoice_<0> &)

- ea: `0x18015cee0`
- end: `0x18015d410`
- name: `?WriteStripedRightArrow@ToOdfShapeGeometryConversion@Art@@CAXAEBVGeometry2D@2@AEBVTransform2D@2@AEAV?$DrawShapeChoice_@$0A@@ODF@@@Z`
- size: `1328`
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
- `0x18015cee0`

## import_xrefs

- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015d05c`
- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015d05c`
- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015d024`
- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015d024`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015d3bc`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015d3bc`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015d0f5`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015d153`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015d0f5`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015d153`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015d0c0`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015d0d2`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015d0c0`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015d0d2`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015d3c6`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015d3c6`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015d03d`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015d03d`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015d2ca`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015d2ca`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015d3d0`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015d3d0`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015d079`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015d079`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015d0af`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015d0af`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015d385`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015d3b1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015d385`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015d3b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Art::ToOdfShapeGeometryConversion::WriteStripedRightArrow(
        const struct Art::Geometry2D *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v5; // rax
  wchar_t **v6; // rsi
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
  double v20; // xmm7_8
  unsigned int v21; // r8d
  double v22; // xmm1_8
  double v23; // xmm0_8
  unsigned int v24; // r8d
  double v25; // xmm6_8
  const wchar_t *v26; // rdx
  int v27; // eax
  wchar_t *v28; // rbx
  Art::FeatureGates *v29; // rcx
  void *v30; // rdx
  Mso::Memory *v31; // rcx
  Mso::Memory *v32; // rcx
  unsigned int v33; // eax
  __int16 v34; // [rsp+30h] [rbp-D0h] BYREF
  char v35; // [rsp+32h] [rbp-CEh]
  wchar_t *v36; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v37; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v38[3]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v39; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v40; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v41; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v42[7]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v43[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v44[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v45[104]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t *v46; // [rsp+198h] [rbp+98h] BYREF
  wchar_t *v47; // [rsp+1A8h] [rbp+A8h] BYREF

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
  Ofc::CStr::operator=(v6 + 49, (Ofc *)L"?f0 0 ?f0 21600");
  Ofc::CStr::operator=(v6 + 51, (Ofc *)L"0, 180");
  Ofc::CStr::operator=(v6 + 48, (Ofc *)L"4000 ?f1 ?f5 ?f2");
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
  v25 = 21600.0 - Art::GeometryCompiler::Lookup((Art::GeometryCompiler *)v44, v19) * 21600.0 / (v17 * 100000.0);
  if ( v25 < 0.0 )
    v20 = DOUBLE_N0_5;
  Ofc::CStr::DecodeInt(&v46, (int)(v20 + v25), v24);
  Ofc::CVarStr::operator=(v6 + 53, &v46);
  v27 = Ofc::CchWzLen((Ofc *)L" ", v26);
  Ofc::CStr::Append((Ofc::CStr *)(v6 + 53), L" ", v27);
  v28 = v47;
  Ofc::CStr::Append((Ofc::CStr *)(v6 + 53), v47, *((_DWORD *)v47 - 1) / 2);
  Ofc::CStr::operator=(
    v6 + 47,
    (Ofc *)L"M ?f0 0 L 21600 10800 ?f0 21800 ?f0 ?f2 4000 ?f2 4000 ?f1 ?f0 ?f1 ?f0 0 M 0 ?f1 L 0 ?f2 1000 ?f2 1000 ?f1 0 ?"
            "f1 M 2000 ?f1 L 2000 ?f2 3000 ?f2 3000 ?f1 2000 ?f1 Z N");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f0", (Ofc *)L"$0 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f1", (Ofc *)L"$1 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f2", (Ofc *)L"bottom-$1 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f3", (Ofc *)L"right-$0 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f4", (Ofc *)L"?f3 *$1 /10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f5", (Ofc *)L"$0 +?f4 ");
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
  Ofc::CStr::operator=(&v39, (Ofc *)L"4000");
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
0x18015cee0  mov     rax, rsp
0x18015cee3  mov     [rax+8], rbx
0x18015cee7  push    rbp
0x18015cee8  push    rsi
0x18015cee9  push    rdi
0x18015ceea  push    r12
0x18015ceec  push    r14
0x18015ceee  lea     rbp, [rsp-60h]
0x18015cef3  sub     rsp, 160h
0x18015cefa  movaps  xmmword ptr [rax-38h], xmm6
0x18015cefe  movaps  xmmword ptr [rax-48h], xmm7
0x18015cf02  movaps  xmmword ptr [rax-58h], xmm9
0x18015cf07  mov     rdi, rdx
0x18015cf0a  mov     r14, rcx
0x18015cf0d  mov     rcx, r8
0x18015cf10  call    ??$SwitchTo@UcustomShape@DrawShapeChoiceChoices@ODF@@@?$TChoice@VDrawShapeChoiceChoiceIDsImpl@ODF@@@Ofc@@QEAAAEAVCustomShape@ODF@@XZ; Ofc::TChoice<ODF::DrawShapeChoiceChoiceIDsImpl>::SwitchTo<ODF::DrawShapeChoiceChoices::customShape>(void)
0x18015cf15  mov     rcx, [rax]
0x18015cf18  add     rcx, 48h ; 'H'
0x18015cf1c  call    ?EnsureStorage@?$TOptional@VEnhancedGeometry@ODF@@@Ofc@@QEAAAEAVEnhancedGeometry@ODF@@XZ; Ofc::TOptional<ODF::EnhancedGeometry>::EnsureStorage(void)
0x18015cf21  mov     rsi, rax
0x18015cf24  lea     rcx, [rax+60h]
0x18015cf28  call    ?EnsureStorage@?$TOptional@V?$TArray@H@Ofc@@@Ofc@@QEAAAEAV?$TArray@H@2@XZ; Ofc::TOptional<Ofc::TArray<int>>::EnsureStorage(void)
0x18015cf2d  mov     rbx, rax
0x18015cf30  lea     r12, ?Do@?$TCopyConstructRange@W4TextEmphasisType@ODF@@$00$00@Ofc@@SAXPEBEPEAEK@Z; Ofc::TCopyConstructRange<ODF::TextEmphasisType,1,1>::Do(uchar const *,uchar *,ulong)
0x18015cf37  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015cf3a  mov     edx, 4; unsigned int
0x18015cf3f  mov     rcx, rax; this
0x18015cf42  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015cf47  mov     edx, [rbx+8]
0x18015cf4a  mov     rcx, [rbx]
0x18015cf4d  xor     eax, eax
0x18015cf4f  mov     [rcx+rdx*4], eax
0x18015cf52  inc     dword ptr [rbx+8]
0x18015cf55  mov     [rcx+rdx*4], eax
0x18015cf58  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015cf5b  lea     edx, [rax+4]; unsigned int
0x18015cf5e  mov     rcx, rbx; this
0x18015cf61  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015cf66  mov     ecx, [rbx+8]
0x18015cf69  mov     rax, [rbx]
0x18015cf6c  xor     edx, edx
0x18015cf6e  mov     [rax+rcx*4], edx
0x18015cf71  inc     dword ptr [rbx+8]
0x18015cf74  mov     [rax+rcx*4], edx
0x18015cf77  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015cf7a  mov     edx, 4; unsigned int
0x18015cf7f  mov     rcx, rbx; this
0x18015cf82  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015cf87  mov     ecx, [rbx+8]
0x18015cf8a  mov     rax, [rbx]
0x18015cf8d  xor     edx, edx
0x18015cf8f  mov     [rax+rcx*4], edx
0x18015cf92  inc     dword ptr [rbx+8]
0x18015cf95  mov     dword ptr [rax+rcx*4], 5460h
0x18015cf9c  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015cf9f  lea     r12d, [rdx+4]
0x18015cfa3  mov     edx, r12d; unsigned int
0x18015cfa6  mov     rcx, rbx; this
0x18015cfa9  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015cfae  mov     ecx, [rbx+8]
0x18015cfb1  mov     rax, [rbx]
0x18015cfb4  xor     edx, edx
0x18015cfb6  mov     [rax+rcx*4], edx
0x18015cfb9  inc     dword ptr [rbx+8]
0x18015cfbc  mov     dword ptr [rax+rcx*4], 5460h
0x18015cfc3  lea     rcx, [rsi+188h]; this
0x18015cfca  lea     rdx, aF00F021600; "?f0 0 ?f0 21600"
0x18015cfd1  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015cfd6  lea     rcx, [rsi+198h]; this
0x18015cfdd  lea     rdx, a0180; "0, 180"
0x18015cfe4  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015cfe9  lea     rcx, [rsi+180h]; this
0x18015cff0  lea     rdx, a4000F1F5F2; "4000 ?f1 ?f5 ?f2"
0x18015cff7  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015cffc  mov     dword ptr [rbp+80h+arg_8], 0
0x18015d006  lea     rcx, [rsi+50h]
0x18015d00a  lea     rdx, [rbp+80h+arg_8]
0x18015d011  call    ??$?4W4DrawCustomShapeType@ODF@@@?$TVariant@VCustomShapeTypeIDsImpl@ODF@@@Ofc@@QEAAAEAV01@AEBW4DrawCustomShapeType@ODF@@@Z; Ofc::TVariant<ODF::CustomShapeTypeIDsImpl>::operator=<ODF::DrawCustomShapeType>(ODF::DrawCustomShapeType const &)
0x18015d016  lea     rbx, [rdi+10h]
0x18015d01a  lea     rdx, [rbp+80h+arg_8]
0x18015d021  mov     rcx, rbx
0x18015d024  call    cs:__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ; Art::PosSize2D::GetCx(void)
0x18015d02a  xorps   xmm9, xmm9
0x18015d02e  cvtsi2sd xmm9, qword ptr [rax]
0x18015d033  lea     rdx, [rbp+80h+arg_8]
0x18015d03a  mov     rcx, rbx
0x18015d03d  call    cs:__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ; Art::PosSize2D::GetCy(void)
0x18015d043  xorps   xmm0, xmm0
0x18015d046  cvtsi2sd xmm0, qword ptr [rax]
0x18015d04b  movaps  xmm1, xmm9
0x18015d04f  minsd   xmm1, xmm0
0x18015d053  divsd   xmm9, xmm1
0x18015d058  lea     rcx, [rbp+80h+var_D0]
0x18015d05c  call    cs:__imp_??0Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::Geometry2D(void)
0x18015d062  nop
0x18015d063  mov     [rsp+180h+var_160], 0FFh
0x18015d06b  lea     r9, [rbp+80h+var_D0]
0x18015d06f  mov     r8, rbx
0x18015d072  mov     rdx, r14
0x18015d075  lea     rcx, [rbp+80h+var_C0]
0x18015d079  call    cs:__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z; Art::GeometryCompiler::GeometryCompiler(Art::Geometry2D const &,Art::PosSize2D const &,Art::Geometry2D &,ulong)
0x18015d07f  nop
0x18015d080  mov     rcx, r14
0x18015d083  call    ??$Is@UPreset@Geom@Art@@@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(void)
0x18015d088  test    al, al
0x18015d08a  jz      loc_18015D3FC
0x18015d090  cmp     qword ptr [r14+8], 1
0x18015d095  ja      short loc_18015D09F
0x18015d097  mov     rcx, r14
0x18015d09a  call    ?DemandInit@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@AEBAXXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::DemandInit(void)
0x18015d09f  mov     rdx, [r14]
0x18015d0a2  test    rdx, rdx
0x18015d0a5  jz      loc_18015D3FC
0x18015d0ab  lea     rcx, [rbp+80h+var_88]
0x18015d0af  call    cs:__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z; Art::PresetGeometry2D::PresetGeometry2D(Art::PresetGeometry2D const &)
0x18015d0b5  nop
0x18015d0b6  mov     edx, r12d
0x18015d0b9  lea     rcx, aAdj1; "adj1"
0x18015d0c0  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015d0c6  mov     ebx, eax
0x18015d0c8  mov     edx, r12d
0x18015d0cb  lea     rcx, aAdj2; "adj2"
0x18015d0d2  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015d0d8  mov     edi, eax
0x18015d0da  lea     r14, dword_1801DBD74
0x18015d0e1  mov     [rbp+80h+arg_8], r14
0x18015d0e8  mov     [rbp+80h+arg_18], r14
0x18015d0ef  mov     edx, ebx
0x18015d0f1  lea     rcx, [rbp+80h+var_C0]
0x18015d0f5  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015d0fb  movsd   xmm6, cs:__real@40d5180000000000
0x18015d103  mulsd   xmm0, xmm6
0x18015d107  divsd   xmm0, cs:__real@40f86a0000000000
0x18015d10f  movaps  xmm1, xmm6
0x18015d112  subsd   xmm1, xmm0
0x18015d116  movsd   xmm7, cs:__real@3fe0000000000000
0x18015d11e  mulsd   xmm1, xmm7
0x18015d122  comisd  xmm1, cs:__real@0000000000000000
0x18015d12a  jb      short loc_18015D131
0x18015d12c  movaps  xmm0, xmm7
0x18015d12f  jmp     short loc_18015D139
0x18015d131  movsd   xmm0, cs:__real@bfe0000000000000
0x18015d139  addsd   xmm0, xmm1
0x18015d13d  cvttsd2si edx, xmm0; int
0x18015d141  lea     rcx, [rbp+80h+arg_18]; this
0x18015d148  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015d14d  mov     edx, edi
0x18015d14f  lea     rcx, [rbp+80h+var_C0]
0x18015d153  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015d159  mulsd   xmm0, xmm6
0x18015d15d  mulsd   xmm9, cs:__real@40f86a0000000000
0x18015d166  divsd   xmm0, xmm9
0x18015d16b  subsd   xmm6, xmm0
0x18015d16f  comisd  xmm6, cs:__real@0000000000000000
0x18015d177  jnb     short loc_18015D181
0x18015d179  movsd   xmm7, cs:__real@bfe0000000000000
0x18015d181  addsd   xmm7, xmm6
0x18015d185  cvttsd2si edx, xmm7; int
0x18015d189  lea     rcx, [rbp+80h+arg_8]; this
0x18015d190  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015d195  lea     rdi, [rsi+1A8h]
0x18015d19c  lea     rdx, [rbp+80h+arg_8]
0x18015d1a3  mov     rcx, rdi
0x18015d1a6  call    ??4CVarStr@Ofc@@QEAAAEAV01@AEBV01@@Z; Ofc::CVarStr::operator=(Ofc::CVarStr const &)
0x18015d1ab  lea     rcx, asc_1801E05D8; " "
0x18015d1b2  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x18015d1b7  mov     r8d, eax; int
0x18015d1ba  lea     rdx, asc_1801E05D8; " "
0x18015d1c1  mov     rcx, rdi; this
0x18015d1c4  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015d1c9  mov     rbx, [rbp+80h+arg_18]
0x18015d1d0  mov     eax, [rbx-4]
0x18015d1d3  cdq
0x18015d1d4  sub     eax, edx
0x18015d1d6  sar     eax, 1
0x18015d1d8  mov     r8d, eax; int
0x18015d1db  mov     rdx, rbx; wchar_t *
0x18015d1de  mov     rcx, rdi; this
0x18015d1e1  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015d1e6  lea     rcx, [rsi+178h]; this
0x18015d1ed  lea     rdx, aMF00L216001080; "M ?f0 0 L 21600 10800 ?f0 21800 ?f0 ?f2"...
0x18015d1f4  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d1f9  mov     r8, rsi
0x18015d1fc  lea     rdx, a0_5; "$0 "
0x18015d203  lea     rcx, aF0; "f0"
0x18015d20a  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015d20f  mov     r8, rsi
0x18015d212  lea     rdx, a1_2; "$1 "
0x18015d219  lea     rcx, aF1; "f1"
0x18015d220  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015d225  mov     r8, rsi
0x18015d228  lea     rdx, aBottom1; "bottom-$1 "
0x18015d22f  lea     rcx, aF2; "f2"
0x18015d236  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015d23b  mov     r8, rsi
0x18015d23e  lea     rdx, aRight0; "right-$0 "
0x18015d245  lea     rcx, aF3; "f3"
0x18015d24c  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015d251  mov     r8, rsi
0x18015d254  lea     rdx, aF3110800; "?f3 *$1 /10800"
0x18015d25b  lea     rcx, aF4; "f4"
0x18015d262  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015d267  mov     r8, rsi
0x18015d26a  lea     rdx, a0F4; "$0 +?f4 "
0x18015d271  lea     rcx, aF5; "f5"
0x18015d278  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015d27d  mov     [rsp+180h+var_150], 0
0x18015d284  mov     [rsp+180h+var_14E], 0
0x18015d289  mov     [rsp+180h+var_148], r14
0x18015d28e  mov     [rsp+180h+var_140], r14
0x18015d293  mov     [rsp+180h+var_138], r14
0x18015d298  mov     [rsp+180h+var_130], r14
0x18015d29d  mov     [rsp+180h+var_128], r14
0x18015d2a2  mov     [rsp+180h+var_120], r14
0x18015d2a7  mov     [rsp+180h+var_118], r14
0x18015d2ac  mov     [rsp+180h+var_110], r14
0x18015d2b1  mov     [rsp+180h+var_108], r14
0x18015d2b6  mov     [rbp+80h+var_100], r14
0x18015d2ba  mov     [rbp+80h+var_F8], r14
0x18015d2be  mov     [rbp+80h+var_F0], r14
0x18015d2c2  mov     [rbp+80h+var_E8], r14
0x18015d2c6  mov     [rbp+80h+var_E0], r14
0x18015d2ca  call    cs:__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ; Art::FeatureGates::FUsingODF_1_4(void)
0x18015d2d0  test    al, al
0x18015d2d2  jz      short loc_18015D2F6
0x18015d2d4  lea     rdx, a0_2; "$0"
0x18015d2db  lea     rcx, [rsp+180h+var_140]; this
0x18015d2e0  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d2e5  lea     rdx, a1_4; "$1"
0x18015d2ec  lea     rcx, [rsp+180h+var_138]; this
0x18015d2f1  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d2f6  lea     rdx, a01; "$0 $1"
0x18015d2fd  lea     rcx, [rsp+180h+var_148]; this
0x18015d302  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d307  lea     rdx, a4000; "4000"
0x18015d30e  lea     rcx, [rsp+180h+var_120]; this
0x18015d313  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d318  lea     rdx, a21600; "21600"
0x18015d31f  lea     rcx, [rsp+180h+var_118]; this
0x18015d324  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d329  lea     rdx, a0_1; "0"
0x18015d330  lea     rcx, [rsp+180h+var_110]; this
0x18015d335  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d33a  lea     rdx, a10800; "10800"
0x18015d341  lea     rcx, [rsp+180h+var_108]; this
0x18015d346  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d34b  lea     rcx, [rsi+18h]
0x18015d34f  lea     rdx, [rsp+180h+var_150]
0x18015d354  call    ?Push@?$TVector@VHandle@ODF@@$0A@$0PPPPPPPP@@Ofc@@QEAAXAEBVHandle@ODF@@@Z; Ofc::TVector<ODF::Handle,0,4294967295>::Push(ODF::Handle const &)
0x18015d359  nop
0x18015d35a  lea     rcx, [rsp+180h+var_150]; this
0x18015d35f  call    ??1Handle@ODF@@QEAA@XZ; ODF::Handle::~Handle(void)
0x18015d364  lea     rcx, [rbx-0Ch]
0x18015d368  or      ebx, 0FFFFFFFFh
0x18015d36b  cmp     dword ptr [rcx+4], 0
0x18015d36f  jz      short loc_18015D38C
0x18015d371  cmp     dword ptr [rcx], 1
0x18015d374  jz      short loc_18015D380
0x18015d376  mov     eax, ebx
0x18015d378  lock xadd [rcx], eax
0x18015d37c  add     eax, ebx
0x18015d37e  jnz     short loc_18015D38C
0x18015d380  test    rcx, rcx
0x18015d383  jz      short loc_18015D38C
0x18015d385  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015d38b  nop
0x18015d38c  mov     rcx, [rbp+80h+arg_8]
0x18015d393  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18015d397  cmp     dword ptr [rcx+4], 0
0x18015d39b  jz      short loc_18015D3B8
0x18015d39d  cmp     dword ptr [rcx], 1
0x18015d3a0  jz      short loc_18015D3AC
0x18015d3a2  mov     eax, ebx
0x18015d3a4  lock xadd [rcx], eax
0x18015d3a8  add     eax, ebx
0x18015d3aa  jnz     short loc_18015D3B8
0x18015d3ac  test    rcx, rcx
0x18015d3af  jz      short loc_18015D3B8
0x18015d3b1  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015d3b7  nop
0x18015d3b8  lea     rcx, [rbp+80h+var_88]
0x18015d3bc  call    cs:__imp_??1PresetGeometry2D@Art@@QEAA@XZ; Art::PresetGeometry2D::~PresetGeometry2D(void)
0x18015d3c2  lea     rcx, [rbp+80h+var_C0]
0x18015d3c6  call    cs:__imp_??1GeometryCompiler@Art@@QEAA@XZ; Art::GeometryCompiler::~GeometryCompiler(void)
0x18015d3cc  lea     rcx, [rbp+80h+var_D0]
0x18015d3d0  call    cs:__imp_??1Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::~Geometry2D(void)
0x18015d3d6  lea     r11, [rsp+180h+var_20]
0x18015d3de  mov     rbx, [r11+30h]
0x18015d3e2  movaps  xmm6, xmmword ptr [r11-10h]
0x18015d3e7  movaps  xmm7, xmmword ptr [r11-20h]
0x18015d3ec  movaps  xmm9, xmmword ptr [r11-30h]
0x18015d3f1  mov     rsp, r11
0x18015d3f4  pop     r14
0x18015d3f6  pop     r12
0x18015d3f8  pop     rdi
0x18015d3f9  pop     rsi
0x18015d3fa  pop     rbp
0x18015d3fb  retn
0x18015d3fc  lea     rcx, ?tag_f5mb@Ofc@@3VMsoReserveTag@@B; "bm5f"
0x18015d403  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
  ... truncated ...
```
