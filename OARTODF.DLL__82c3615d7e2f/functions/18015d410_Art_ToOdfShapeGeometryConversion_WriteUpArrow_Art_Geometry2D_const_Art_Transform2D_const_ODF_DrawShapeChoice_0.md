# Art::ToOdfShapeGeometryConversion::WriteUpArrow(Art::Geometry2D const &,Art::Transform2D const &,ODF::DrawShapeChoice_<0> &)

- ea: `0x18015d410`
- end: `0x18015d8c0`
- name: `?WriteUpArrow@ToOdfShapeGeometryConversion@Art@@CAXAEBVGeometry2D@2@AEBVTransform2D@2@AEAV?$DrawShapeChoice_@$0A@@ODF@@@Z`
- size: `1200`
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
- `0x18015d410`

## import_xrefs

- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015d584`
- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015d584`
- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015d54f`
- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015d54f`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015d871`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015d871`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015d625`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015d684`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015d625`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015d684`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015d5f0`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015d602`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015d5f0`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015d602`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015d87b`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015d87b`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015d567`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015d567`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015d77f`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015d77f`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015d885`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015d885`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015d5a1`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015d5a1`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015d5df`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015d5df`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015d83a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015d866`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015d83a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015d866`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Art::ToOdfShapeGeometryConversion::WriteUpArrow(
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
  double v16; // xmm6_8
  _QWORD *Cy; // rax
  double v18; // xmm9_8
  int v19; // ebx
  int v20; // edi
  double v21; // xmm6_8
  unsigned int v22; // r8d
  double v23; // xmm1_8
  double v24; // xmm0_8
  unsigned int v25; // r8d
  double v26; // xmm0_8
  const wchar_t *v27; // rdx
  int v28; // eax
  wchar_t *v29; // rbx
  Art::FeatureGates *v30; // rcx
  void *v31; // rdx
  Mso::Memory *v32; // rcx
  Mso::Memory *v33; // rcx
  unsigned int v34; // eax
  __int16 v35; // [rsp+38h] [rbp-D0h] BYREF
  char v36; // [rsp+3Ah] [rbp-CEh]
  wchar_t *v37; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t *v38; // [rsp+48h] [rbp-C0h] BYREF
  wchar_t *v39[3]; // [rsp+50h] [rbp-B8h] BYREF
  wchar_t *v40; // [rsp+68h] [rbp-A0h] BYREF
  wchar_t *v41; // [rsp+70h] [rbp-98h] BYREF
  wchar_t *v42; // [rsp+78h] [rbp-90h] BYREF
  wchar_t *v43[7]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v44[16]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v45[56]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v46[88]; // [rsp+100h] [rbp-8h] BYREF
  wchar_t *v47; // [rsp+190h] [rbp+88h] BYREF
  wchar_t *v48; // [rsp+1A0h] [rbp+98h] BYREF

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
  Ofc::CStr::operator=(v6 + 49, (Ofc *)L"0 ?f1 21600 ?f1");
  Ofc::CStr::operator=(v6 + 51, (Ofc *)L"-270, -90");
  Ofc::CStr::operator=(v6 + 48, (Ofc *)L"?f0 ?f7 ?f2 21600");
  LODWORD(v47) = 0;
  Ofc::TVariant<ODF::CustomShapeTypeIDsImpl>::operator=<enum ODF::DrawCustomShapeType>(v6 + 10, &v47);
  v16 = (double)(int)*(_QWORD *)Art::PosSize2D::GetCx(a2 + 16, &v47);
  Cy = (_QWORD *)Art::PosSize2D::GetCy(a2 + 16, &v47);
  v18 = (double)(int)*Cy / fmin(v16, (double)(int)*Cy);
  Art::Geometry2D::Geometry2D((Art::Geometry2D *)v44);
  Art::GeometryCompiler::GeometryCompiler(
    (Art::GeometryCompiler *)v45,
    a1,
    (const struct Art::PosSize2D *)(a2 + 16),
    (struct Art::Geometry2D *)v44,
    0xFFu);
  if ( !(unsigned __int8)Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(a1) )
    goto LABEL_23;
  if ( *((_QWORD *)a1 + 1) <= 1u )
    Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::DemandInit(a1);
  if ( !*(_QWORD *)a1 )
  {
LABEL_23:
    v34 = MsoReserveTag::operator unsigned int("bm5f");
    Ofc::CInvalidParamException::ThrowTag(v34);
    __debugbreak();
  }
  Art::PresetGeometry2D::PresetGeometry2D((Art::PresetGeometry2D *)v46, *(const struct Art::PresetGeometry2D **)a1);
  v19 = Art::GeomGuideName::MapStringToToken(L"adj1", 4);
  v20 = Art::GeomGuideName::MapStringToToken(L"adj2", 4);
  v47 = (wchar_t *)&dword_1801DBD74;
  v48 = (wchar_t *)&dword_1801DBD74;
  v21 = DOUBLE_0_5;
  v23 = (21600.0 - Art::GeometryCompiler::Lookup((Art::GeometryCompiler *)v45, v19) * 21600.0 / 100000.0) * 0.5;
  if ( v23 < 0.0 )
    v24 = DOUBLE_N0_5;
  else
    v24 = DOUBLE_0_5;
  Ofc::CStr::DecodeInt(&v48, (int)(v24 + v23), v22);
  v26 = Art::GeometryCompiler::Lookup((Art::GeometryCompiler *)v45, v20) * 21600.0 / (v18 * 100000.0);
  if ( v26 < 0.0 )
    v21 = DOUBLE_N0_5;
  Ofc::CStr::DecodeInt(&v47, (int)(v21 + v26), v25);
  Ofc::CVarStr::operator=(v6 + 53, &v47);
  v28 = Ofc::CchWzLen((Ofc *)L" ", v27);
  Ofc::CStr::Append((Ofc::CStr *)(v6 + 53), L" ", v28);
  v29 = v48;
  Ofc::CStr::Append((Ofc::CStr *)(v6 + 53), v48, *((_DWORD *)v48 - 1) / 2);
  Ofc::CStr::operator=(v6 + 47, (Ofc *)L"M ?f0 21600 L ?f0 ?f1 0 ?f1 10800 0 21600 ?f1 ?f2 ?f1 ?f2 21600 Z N");
  Art::ToOdfShapeGeometryConversion::AddArrowEquations(v6);
  v35 = 0;
  v36 = 0;
  v37 = (wchar_t *)&dword_1801DBD74;
  v38 = (wchar_t *)&dword_1801DBD74;
  v39[0] = (wchar_t *)&dword_1801DBD74;
  v39[1] = (wchar_t *)&dword_1801DBD74;
  v39[2] = (wchar_t *)&dword_1801DBD74;
  v40 = (wchar_t *)&dword_1801DBD74;
  v41 = (wchar_t *)&dword_1801DBD74;
  v42 = (wchar_t *)&dword_1801DBD74;
  v43[0] = (wchar_t *)&dword_1801DBD74;
  v43[1] = (wchar_t *)&dword_1801DBD74;
  v43[2] = (wchar_t *)&dword_1801DBD74;
  v43[3] = (wchar_t *)&dword_1801DBD74;
  v43[4] = (wchar_t *)&dword_1801DBD74;
  v43[5] = (wchar_t *)&dword_1801DBD74;
  if ( Art::FeatureGates::FUsingODF_1_4(v30) )
  {
    Ofc::CStr::operator=(&v38, (Ofc *)L"$1");
    Ofc::CStr::operator=(v39, (Ofc *)L"$0");
  }
  Ofc::CStr::operator=(&v37, (Ofc *)L"$1 $0");
  Ofc::CStr::operator=(&v40, (Ofc *)L"0");
  Ofc::CStr::operator=(&v41, (Ofc *)L"10800");
  Ofc::CStr::operator=(&v42, (Ofc *)L"0");
  Ofc::CStr::operator=(v43, (Ofc *)L"21600");
  Ofc::TVector<ODF::Handle,0,4294967295>::Push(v6 + 3, &v35);
  ODF::Handle::~Handle((ODF::Handle *)&v35);
  v32 = (Mso::Memory *)(v29 - 6);
  if ( *((_DWORD *)v29 - 2)
    && (*(_DWORD *)v32 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v32, 0xFFFFFFFF) == 1)
    && v29 != (wchar_t *)12 )
  {
    Mso::Memory::Free(v32, v31);
  }
  v33 = (Mso::Memory *)(v47 - 6);
  if ( *((_DWORD *)v47 - 2)
    && (*(_DWORD *)v33 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v33, 0xFFFFFFFF) == 1) )
  {
    if ( v33 )
      Mso::Memory::Free(v33, v31);
  }
  Art::PresetGeometry2D::~PresetGeometry2D((Art::PresetGeometry2D *)v46);
  Art::GeometryCompiler::~GeometryCompiler((Art::GeometryCompiler *)v45);
  Art::Geometry2D::~Geometry2D((Art::Geometry2D *)v44);
}

```

## disassembly

```asm
0x18015d410  mov     rax, rsp
0x18015d413  mov     [rax+8], rbx
0x18015d417  push    rbp
0x18015d418  push    rsi
0x18015d419  push    rdi
0x18015d41a  push    r12
0x18015d41c  push    r14
0x18015d41e  lea     rbp, [rax-78h]
0x18015d422  sub     rsp, 150h
0x18015d429  movaps  xmmword ptr [rax-38h], xmm6
0x18015d42d  movaps  xmmword ptr [rax-48h], xmm9
0x18015d432  mov     rdi, rdx
0x18015d435  mov     rsi, rcx
0x18015d438  mov     rcx, r8
0x18015d43b  call    ??$SwitchTo@UcustomShape@DrawShapeChoiceChoices@ODF@@@?$TChoice@VDrawShapeChoiceChoiceIDsImpl@ODF@@@Ofc@@QEAAAEAVCustomShape@ODF@@XZ; Ofc::TChoice<ODF::DrawShapeChoiceChoiceIDsImpl>::SwitchTo<ODF::DrawShapeChoiceChoices::customShape>(void)
0x18015d440  mov     rcx, [rax]
0x18015d443  add     rcx, 48h ; 'H'
0x18015d447  call    ?EnsureStorage@?$TOptional@VEnhancedGeometry@ODF@@@Ofc@@QEAAAEAVEnhancedGeometry@ODF@@XZ; Ofc::TOptional<ODF::EnhancedGeometry>::EnsureStorage(void)
0x18015d44c  mov     r14, rax
0x18015d44f  lea     rcx, [rax+60h]
0x18015d453  call    ?EnsureStorage@?$TOptional@V?$TArray@H@Ofc@@@Ofc@@QEAAAEAV?$TArray@H@2@XZ; Ofc::TOptional<Ofc::TArray<int>>::EnsureStorage(void)
0x18015d458  mov     rbx, rax
0x18015d45b  lea     r12, ?Do@?$TCopyConstructRange@W4TextEmphasisType@ODF@@$00$00@Ofc@@SAXPEBEPEAEK@Z; Ofc::TCopyConstructRange<ODF::TextEmphasisType,1,1>::Do(uchar const *,uchar *,ulong)
0x18015d462  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015d465  mov     edx, 4; unsigned int
0x18015d46a  mov     rcx, rax; this
0x18015d46d  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015d472  mov     edx, [rbx+8]
0x18015d475  mov     rcx, [rbx]
0x18015d478  xor     eax, eax
0x18015d47a  mov     [rcx+rdx*4], eax
0x18015d47d  inc     dword ptr [rbx+8]
0x18015d480  mov     [rcx+rdx*4], eax
0x18015d483  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015d486  lea     edx, [rax+4]; unsigned int
0x18015d489  mov     rcx, rbx; this
0x18015d48c  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015d491  mov     ecx, [rbx+8]
0x18015d494  mov     rax, [rbx]
0x18015d497  xor     edx, edx
0x18015d499  mov     [rax+rcx*4], edx
0x18015d49c  inc     dword ptr [rbx+8]
0x18015d49f  mov     [rax+rcx*4], edx
0x18015d4a2  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015d4a5  mov     edx, 4; unsigned int
0x18015d4aa  mov     rcx, rbx; this
0x18015d4ad  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015d4b2  mov     ecx, [rbx+8]
0x18015d4b5  mov     rax, [rbx]
0x18015d4b8  xor     edx, edx
0x18015d4ba  mov     [rax+rcx*4], edx
0x18015d4bd  inc     dword ptr [rbx+8]
0x18015d4c0  mov     dword ptr [rax+rcx*4], 5460h
0x18015d4c7  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015d4ca  lea     r12d, [rdx+4]
0x18015d4ce  mov     edx, r12d; unsigned int
0x18015d4d1  mov     rcx, rbx; this
0x18015d4d4  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015d4d9  mov     ecx, [rbx+8]
0x18015d4dc  mov     rax, [rbx]
0x18015d4df  xor     edx, edx
0x18015d4e1  mov     [rax+rcx*4], edx
0x18015d4e4  inc     dword ptr [rbx+8]
0x18015d4e7  mov     dword ptr [rax+rcx*4], 5460h
0x18015d4ee  lea     rcx, [r14+188h]; this
0x18015d4f5  lea     rdx, a0F121600F1; "0 ?f1 21600 ?f1"
0x18015d4fc  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d501  lea     rcx, [r14+198h]; this
0x18015d508  lea     rdx, a27090; "-270, -90"
0x18015d50f  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d514  lea     rcx, [r14+180h]; this
0x18015d51b  lea     rdx, aF0F7F221600; "?f0 ?f7 ?f2 21600"
0x18015d522  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d527  mov     dword ptr [rbp+70h+arg_8], 0
0x18015d531  lea     rcx, [r14+50h]
0x18015d535  lea     rdx, [rbp+70h+arg_8]
0x18015d53c  call    ??$?4W4DrawCustomShapeType@ODF@@@?$TVariant@VCustomShapeTypeIDsImpl@ODF@@@Ofc@@QEAAAEAV01@AEBW4DrawCustomShapeType@ODF@@@Z; Ofc::TVariant<ODF::CustomShapeTypeIDsImpl>::operator=<ODF::DrawCustomShapeType>(ODF::DrawCustomShapeType const &)
0x18015d541  lea     rbx, [rdi+10h]
0x18015d545  lea     rdx, [rbp+70h+arg_8]
0x18015d54c  mov     rcx, rbx
0x18015d54f  call    cs:__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ; Art::PosSize2D::GetCx(void)
0x18015d555  xorps   xmm6, xmm6
0x18015d558  cvtsi2sd xmm6, qword ptr [rax]
0x18015d55d  lea     rdx, [rbp+70h+arg_8]
0x18015d564  mov     rcx, rbx
0x18015d567  call    cs:__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ; Art::PosSize2D::GetCy(void)
0x18015d56d  xorps   xmm9, xmm9
0x18015d571  cvtsi2sd xmm9, qword ptr [rax]
0x18015d576  minsd   xmm6, xmm9
0x18015d57b  divsd   xmm9, xmm6
0x18015d580  lea     rcx, [rbp+70h+var_C0]
0x18015d584  call    cs:__imp_??0Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::Geometry2D(void)
0x18015d58a  nop
0x18015d58b  mov     [rsp+170h+var_150], 0FFh
0x18015d593  lea     r9, [rbp+70h+var_C0]
0x18015d597  mov     r8, rbx
0x18015d59a  mov     rdx, rsi
0x18015d59d  lea     rcx, [rbp+70h+var_B0]
0x18015d5a1  call    cs:__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z; Art::GeometryCompiler::GeometryCompiler(Art::Geometry2D const &,Art::PosSize2D const &,Art::Geometry2D &,ulong)
0x18015d5a7  nop
0x18015d5a8  nop     dword ptr [rax+rax+00000000h]
0x18015d5b0  mov     rcx, rsi
0x18015d5b3  call    ??$Is@UPreset@Geom@Art@@@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(void)
0x18015d5b8  test    al, al
0x18015d5ba  jz      loc_18015D8AC
0x18015d5c0  cmp     qword ptr [rsi+8], 1
0x18015d5c5  ja      short loc_18015D5CF
0x18015d5c7  mov     rcx, rsi
0x18015d5ca  call    ?DemandInit@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@AEBAXXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::DemandInit(void)
0x18015d5cf  mov     rdx, [rsi]
0x18015d5d2  test    rdx, rdx
0x18015d5d5  jz      loc_18015D8AC
0x18015d5db  lea     rcx, [rbp+70h+var_78]
0x18015d5df  call    cs:__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z; Art::PresetGeometry2D::PresetGeometry2D(Art::PresetGeometry2D const &)
0x18015d5e5  nop
0x18015d5e6  mov     edx, r12d
0x18015d5e9  lea     rcx, aAdj1; "adj1"
0x18015d5f0  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015d5f6  mov     ebx, eax
0x18015d5f8  mov     edx, r12d
0x18015d5fb  lea     rcx, aAdj2; "adj2"
0x18015d602  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015d608  mov     edi, eax
0x18015d60a  lea     rsi, dword_1801DBD74
0x18015d611  mov     [rbp+70h+arg_8], rsi
0x18015d618  mov     [rbp+70h+arg_18], rsi
0x18015d61f  mov     edx, ebx
0x18015d621  lea     rcx, [rbp+70h+var_B0]
0x18015d625  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015d62b  mulsd   xmm0, cs:__real@40d5180000000000
0x18015d633  divsd   xmm0, cs:__real@40f86a0000000000
0x18015d63b  movsd   xmm1, cs:__real@40d5180000000000
0x18015d643  subsd   xmm1, xmm0
0x18015d647  movsd   xmm6, cs:__real@3fe0000000000000
0x18015d64f  mulsd   xmm1, xmm6
0x18015d653  comisd  xmm1, cs:__real@0000000000000000
0x18015d65b  jb      short loc_18015D662
0x18015d65d  movaps  xmm0, xmm6
0x18015d660  jmp     short loc_18015D66A
0x18015d662  movsd   xmm0, cs:__real@bfe0000000000000
0x18015d66a  addsd   xmm0, xmm1
0x18015d66e  cvttsd2si edx, xmm0; int
0x18015d672  lea     rcx, [rbp+70h+arg_18]; this
0x18015d679  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015d67e  mov     edx, edi
0x18015d680  lea     rcx, [rbp+70h+var_B0]
0x18015d684  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015d68a  mulsd   xmm0, cs:__real@40d5180000000000
0x18015d692  mulsd   xmm9, cs:__real@40f86a0000000000
0x18015d69b  divsd   xmm0, xmm9
0x18015d6a0  comisd  xmm0, cs:__real@0000000000000000
0x18015d6a8  jnb     short loc_18015D6B2
0x18015d6aa  movsd   xmm6, cs:__real@bfe0000000000000
0x18015d6b2  addsd   xmm6, xmm0
0x18015d6b6  cvttsd2si edx, xmm6; int
0x18015d6ba  lea     rcx, [rbp+70h+arg_8]; this
0x18015d6c1  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015d6c6  lea     rdi, [r14+1A8h]
0x18015d6cd  lea     rdx, [rbp+70h+arg_8]
0x18015d6d4  mov     rcx, rdi
0x18015d6d7  call    ??4CVarStr@Ofc@@QEAAAEAV01@AEBV01@@Z; Ofc::CVarStr::operator=(Ofc::CVarStr const &)
0x18015d6dc  lea     rcx, asc_1801E05D8; " "
0x18015d6e3  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x18015d6e8  mov     r8d, eax; int
0x18015d6eb  lea     rdx, asc_1801E05D8; " "
0x18015d6f2  mov     rcx, rdi; this
0x18015d6f5  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015d6fa  mov     rbx, [rbp+70h+arg_18]
0x18015d701  mov     eax, [rbx-4]
0x18015d704  cdq
0x18015d705  sub     eax, edx
0x18015d707  sar     eax, 1
0x18015d709  mov     r8d, eax; int
0x18015d70c  mov     rdx, rbx; wchar_t *
0x18015d70f  mov     rcx, rdi; this
0x18015d712  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015d717  lea     rcx, [r14+178h]; this
0x18015d71e  lea     rdx, aMF021600LF0F10; "M ?f0 21600 L ?f0 ?f1 0 ?f1 10800 0 216"...
0x18015d725  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d72a  mov     rcx, r14
0x18015d72d  call    ?AddArrowEquations@ToOdfShapeGeometryConversion@Art@@CAXAEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddArrowEquations(Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015d732  mov     word ptr [rsp+170h+var_140], 0
0x18015d739  mov     byte ptr [rsp+170h+var_140+2], 0
0x18015d73e  mov     [rsp+170h+var_138], rsi
0x18015d743  mov     [rsp+170h+var_130], rsi
0x18015d748  mov     [rsp+170h+var_128], rsi
0x18015d74d  mov     [rsp+170h+var_120], rsi
0x18015d752  mov     [rsp+170h+var_118], rsi
0x18015d757  mov     [rsp+170h+var_110], rsi
0x18015d75c  mov     [rsp+170h+var_108], rsi
0x18015d761  mov     [rsp+170h+var_100], rsi
0x18015d766  mov     [rsp+170h+var_F8], rsi
0x18015d76b  mov     [rbp+70h+var_F0], rsi
0x18015d76f  mov     [rbp+70h+var_E8], rsi
0x18015d773  mov     [rbp+70h+var_E0], rsi
0x18015d777  mov     [rbp+70h+var_D8], rsi
0x18015d77b  mov     [rbp+70h+var_D0], rsi
0x18015d77f  call    cs:__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ; Art::FeatureGates::FUsingODF_1_4(void)
0x18015d785  test    al, al
0x18015d787  jz      short loc_18015D7AB
0x18015d789  lea     rdx, a1_4; "$1"
0x18015d790  lea     rcx, [rsp+170h+var_130]; this
0x18015d795  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d79a  lea     rdx, a0_2; "$0"
0x18015d7a1  lea     rcx, [rsp+170h+var_128]; this
0x18015d7a6  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d7ab  lea     rdx, a10_0; "$1 $0"
0x18015d7b2  lea     rcx, [rsp+170h+var_138]; this
0x18015d7b7  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d7bc  lea     rdx, a0_1; "0"
0x18015d7c3  lea     rcx, [rsp+170h+var_110]; this
0x18015d7c8  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d7cd  lea     rdx, a10800; "10800"
0x18015d7d4  lea     rcx, [rsp+170h+var_108]; this
0x18015d7d9  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d7de  lea     rdx, a0_1; "0"
0x18015d7e5  lea     rcx, [rsp+170h+var_100]; this
0x18015d7ea  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d7ef  lea     rdx, a21600; "21600"
0x18015d7f6  lea     rcx, [rsp+170h+var_F8]; this
0x18015d7fb  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015d800  lea     rcx, [r14+18h]
0x18015d804  lea     rdx, [rsp+170h+var_140]
0x18015d809  call    ?Push@?$TVector@VHandle@ODF@@$0A@$0PPPPPPPP@@Ofc@@QEAAXAEBVHandle@ODF@@@Z; Ofc::TVector<ODF::Handle,0,4294967295>::Push(ODF::Handle const &)
0x18015d80e  nop
0x18015d80f  lea     rcx, [rsp+170h+var_140]; this
0x18015d814  call    ??1Handle@ODF@@QEAA@XZ; ODF::Handle::~Handle(void)
0x18015d819  lea     rcx, [rbx-0Ch]
0x18015d81d  or      ebx, 0FFFFFFFFh
0x18015d820  cmp     dword ptr [rcx+4], 0
0x18015d824  jz      short loc_18015D841
0x18015d826  cmp     dword ptr [rcx], 1
0x18015d829  jz      short loc_18015D835
0x18015d82b  mov     eax, ebx
0x18015d82d  lock xadd [rcx], eax
0x18015d831  add     eax, ebx
0x18015d833  jnz     short loc_18015D841
0x18015d835  test    rcx, rcx
0x18015d838  jz      short loc_18015D841
0x18015d83a  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015d840  nop
0x18015d841  mov     rcx, [rbp+70h+arg_8]
0x18015d848  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18015d84c  cmp     dword ptr [rcx+4], 0
0x18015d850  jz      short loc_18015D86D
0x18015d852  cmp     dword ptr [rcx], 1
0x18015d855  jz      short loc_18015D861
0x18015d857  mov     eax, ebx
0x18015d859  lock xadd [rcx], eax
0x18015d85d  add     eax, ebx
0x18015d85f  jnz     short loc_18015D86D
0x18015d861  test    rcx, rcx
0x18015d864  jz      short loc_18015D86D
0x18015d866  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015d86c  nop
0x18015d86d  lea     rcx, [rbp+70h+var_78]
0x18015d871  call    cs:__imp_??1PresetGeometry2D@Art@@QEAA@XZ; Art::PresetGeometry2D::~PresetGeometry2D(void)
0x18015d877  lea     rcx, [rbp+70h+var_B0]
0x18015d87b  call    cs:__imp_??1GeometryCompiler@Art@@QEAA@XZ; Art::GeometryCompiler::~GeometryCompiler(void)
0x18015d881  lea     rcx, [rbp+70h+var_C0]
0x18015d885  call    cs:__imp_??1Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::~Geometry2D(void)
0x18015d88b  lea     r11, [rsp+170h+var_20]
0x18015d893  mov     rbx, [r11+30h]
0x18015d897  movaps  xmm6, xmmword ptr [r11-10h]
0x18015d89c  movaps  xmm9, xmmword ptr [r11-20h]
0x18015d8a1  mov     rsp, r11
0x18015d8a4  pop     r14
0x18015d8a6  pop     r12
0x18015d8a8  pop     rdi
0x18015d8a9  pop     rsi
0x18015d8aa  pop     rbp
0x18015d8ab  retn
0x18015d8ac  lea     rcx, ?tag_f5mb@Ofc@@3VMsoReserveTag@@B; "bm5f"
0x18015d8b3  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x18015d8b8  mov     ecx, eax; unsigned int
0x18015d8ba  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18015d8bf  int     3; Trap to Debugger
```
