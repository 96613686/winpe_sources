# Art::ToOdfShapeGeometryConversion::WriteRightArrow(Art::Geometry2D const &,Art::Transform2D const &,ODF::DrawShapeChoice_<0> &)

- ea: `0x18015c25c`
- end: `0x18015c710`
- name: `?WriteRightArrow@ToOdfShapeGeometryConversion@Art@@CAXAEBVGeometry2D@2@AEBVTransform2D@2@AEAV?$DrawShapeChoice_@$0A@@ODF@@@Z`
- size: `1204`
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
- `0x18015c25c`

## import_xrefs

- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015c3d8`
- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015c3d8`
- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015c3a0`
- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015c3a0`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015c6bc`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015c6bc`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015c471`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015c4cf`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015c471`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015c4cf`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015c43c`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015c44e`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015c43c`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015c44e`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015c6c6`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015c6c6`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015c3b9`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015c3b9`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015c5ca`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015c5ca`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015c6d0`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015c6d0`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015c3f5`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015c3f5`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015c42b`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015c42b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015c685`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015c6b1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015c685`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015c6b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Art::ToOdfShapeGeometryConversion::WriteRightArrow(
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
  Ofc::CStr::operator=(v6 + 49, (Ofc *)L"?f1 0 ?f1 21600");
  Ofc::CStr::operator=(v6 + 51, (Ofc *)L"0, 180");
  Ofc::CStr::operator=(v6 + 48, (Ofc *)L"0 ?f0 ?f5 ?f2");
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
  Ofc::CStr::operator=(v6 + 47, (Ofc *)L"M 0 ?f0 L ?f1 ?f0 ?f1 0 21600 10800 ?f1 21600 ?f1 ?f2 0 ?f2 Z N");
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
0x18015c25c  mov     rax, rsp
0x18015c25f  mov     [rax+8], rbx
0x18015c263  push    rbp
0x18015c264  push    rsi
0x18015c265  push    rdi
0x18015c266  push    r12
0x18015c268  push    r14
0x18015c26a  lea     rbp, [rsp-60h]
0x18015c26f  sub     rsp, 160h
0x18015c276  movaps  xmmword ptr [rax-38h], xmm6
0x18015c27a  movaps  xmmword ptr [rax-48h], xmm7
0x18015c27e  movaps  xmmword ptr [rax-58h], xmm9
0x18015c283  mov     rdi, rdx
0x18015c286  mov     rsi, rcx
0x18015c289  mov     rcx, r8
0x18015c28c  call    ??$SwitchTo@UcustomShape@DrawShapeChoiceChoices@ODF@@@?$TChoice@VDrawShapeChoiceChoiceIDsImpl@ODF@@@Ofc@@QEAAAEAVCustomShape@ODF@@XZ; Ofc::TChoice<ODF::DrawShapeChoiceChoiceIDsImpl>::SwitchTo<ODF::DrawShapeChoiceChoices::customShape>(void)
0x18015c291  mov     rcx, [rax]
0x18015c294  add     rcx, 48h ; 'H'
0x18015c298  call    ?EnsureStorage@?$TOptional@VEnhancedGeometry@ODF@@@Ofc@@QEAAAEAVEnhancedGeometry@ODF@@XZ; Ofc::TOptional<ODF::EnhancedGeometry>::EnsureStorage(void)
0x18015c29d  mov     r14, rax
0x18015c2a0  lea     rcx, [rax+60h]
0x18015c2a4  call    ?EnsureStorage@?$TOptional@V?$TArray@H@Ofc@@@Ofc@@QEAAAEAV?$TArray@H@2@XZ; Ofc::TOptional<Ofc::TArray<int>>::EnsureStorage(void)
0x18015c2a9  mov     rbx, rax
0x18015c2ac  lea     r12, ?Do@?$TCopyConstructRange@W4TextEmphasisType@ODF@@$00$00@Ofc@@SAXPEBEPEAEK@Z; Ofc::TCopyConstructRange<ODF::TextEmphasisType,1,1>::Do(uchar const *,uchar *,ulong)
0x18015c2b3  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015c2b6  mov     edx, 4; unsigned int
0x18015c2bb  mov     rcx, rax; this
0x18015c2be  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015c2c3  mov     edx, [rbx+8]
0x18015c2c6  mov     rcx, [rbx]
0x18015c2c9  xor     eax, eax
0x18015c2cb  mov     [rcx+rdx*4], eax
0x18015c2ce  inc     dword ptr [rbx+8]
0x18015c2d1  mov     [rcx+rdx*4], eax
0x18015c2d4  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015c2d7  lea     edx, [rax+4]; unsigned int
0x18015c2da  mov     rcx, rbx; this
0x18015c2dd  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015c2e2  mov     ecx, [rbx+8]
0x18015c2e5  mov     rax, [rbx]
0x18015c2e8  xor     edx, edx
0x18015c2ea  mov     [rax+rcx*4], edx
0x18015c2ed  inc     dword ptr [rbx+8]
0x18015c2f0  mov     [rax+rcx*4], edx
0x18015c2f3  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015c2f6  mov     edx, 4; unsigned int
0x18015c2fb  mov     rcx, rbx; this
0x18015c2fe  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015c303  mov     ecx, [rbx+8]
0x18015c306  mov     rax, [rbx]
0x18015c309  xor     edx, edx
0x18015c30b  mov     [rax+rcx*4], edx
0x18015c30e  inc     dword ptr [rbx+8]
0x18015c311  mov     dword ptr [rax+rcx*4], 5460h
0x18015c318  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015c31b  lea     r12d, [rdx+4]
0x18015c31f  mov     edx, r12d; unsigned int
0x18015c322  mov     rcx, rbx; this
0x18015c325  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015c32a  mov     ecx, [rbx+8]
0x18015c32d  mov     rax, [rbx]
0x18015c330  xor     edx, edx
0x18015c332  mov     [rax+rcx*4], edx
0x18015c335  inc     dword ptr [rbx+8]
0x18015c338  mov     dword ptr [rax+rcx*4], 5460h
0x18015c33f  lea     rcx, [r14+188h]; this
0x18015c346  lea     rdx, aF10F121600; "?f1 0 ?f1 21600"
0x18015c34d  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c352  lea     rcx, [r14+198h]; this
0x18015c359  lea     rdx, a0180; "0, 180"
0x18015c360  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c365  lea     rcx, [r14+180h]; this
0x18015c36c  lea     rdx, a0F0F5F2; "0 ?f0 ?f5 ?f2"
0x18015c373  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c378  mov     dword ptr [rbp+80h+arg_8], 0
0x18015c382  lea     rcx, [r14+50h]
0x18015c386  lea     rdx, [rbp+80h+arg_8]
0x18015c38d  call    ??$?4W4DrawCustomShapeType@ODF@@@?$TVariant@VCustomShapeTypeIDsImpl@ODF@@@Ofc@@QEAAAEAV01@AEBW4DrawCustomShapeType@ODF@@@Z; Ofc::TVariant<ODF::CustomShapeTypeIDsImpl>::operator=<ODF::DrawCustomShapeType>(ODF::DrawCustomShapeType const &)
0x18015c392  lea     rbx, [rdi+10h]
0x18015c396  lea     rdx, [rbp+80h+arg_8]
0x18015c39d  mov     rcx, rbx
0x18015c3a0  call    cs:__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ; Art::PosSize2D::GetCx(void)
0x18015c3a6  xorps   xmm9, xmm9
0x18015c3aa  cvtsi2sd xmm9, qword ptr [rax]
0x18015c3af  lea     rdx, [rbp+80h+arg_8]
0x18015c3b6  mov     rcx, rbx
0x18015c3b9  call    cs:__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ; Art::PosSize2D::GetCy(void)
0x18015c3bf  xorps   xmm0, xmm0
0x18015c3c2  cvtsi2sd xmm0, qword ptr [rax]
0x18015c3c7  movaps  xmm1, xmm9
0x18015c3cb  minsd   xmm1, xmm0
0x18015c3cf  divsd   xmm9, xmm1
0x18015c3d4  lea     rcx, [rbp+80h+var_D0]
0x18015c3d8  call    cs:__imp_??0Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::Geometry2D(void)
0x18015c3de  nop
0x18015c3df  mov     [rsp+180h+var_160], 0FFh
0x18015c3e7  lea     r9, [rbp+80h+var_D0]
0x18015c3eb  mov     r8, rbx
0x18015c3ee  mov     rdx, rsi
0x18015c3f1  lea     rcx, [rbp+80h+var_C0]
0x18015c3f5  call    cs:__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z; Art::GeometryCompiler::GeometryCompiler(Art::Geometry2D const &,Art::PosSize2D const &,Art::Geometry2D &,ulong)
0x18015c3fb  nop
0x18015c3fc  mov     rcx, rsi
0x18015c3ff  call    ??$Is@UPreset@Geom@Art@@@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(void)
0x18015c404  test    al, al
0x18015c406  jz      loc_18015C6FC
0x18015c40c  cmp     qword ptr [rsi+8], 1
0x18015c411  ja      short loc_18015C41B
0x18015c413  mov     rcx, rsi
0x18015c416  call    ?DemandInit@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@AEBAXXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::DemandInit(void)
0x18015c41b  mov     rdx, [rsi]
0x18015c41e  test    rdx, rdx
0x18015c421  jz      loc_18015C6FC
0x18015c427  lea     rcx, [rbp+80h+var_88]
0x18015c42b  call    cs:__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z; Art::PresetGeometry2D::PresetGeometry2D(Art::PresetGeometry2D const &)
0x18015c431  nop
0x18015c432  mov     edx, r12d
0x18015c435  lea     rcx, aAdj1; "adj1"
0x18015c43c  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015c442  mov     ebx, eax
0x18015c444  mov     edx, r12d
0x18015c447  lea     rcx, aAdj2; "adj2"
0x18015c44e  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015c454  mov     edi, eax
0x18015c456  lea     rsi, dword_1801DBD74
0x18015c45d  mov     [rbp+80h+arg_8], rsi
0x18015c464  mov     [rbp+80h+arg_18], rsi
0x18015c46b  mov     edx, ebx
0x18015c46d  lea     rcx, [rbp+80h+var_C0]
0x18015c471  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015c477  movsd   xmm6, cs:__real@40d5180000000000
0x18015c47f  mulsd   xmm0, xmm6
0x18015c483  divsd   xmm0, cs:__real@40f86a0000000000
0x18015c48b  movaps  xmm1, xmm6
0x18015c48e  subsd   xmm1, xmm0
0x18015c492  movsd   xmm7, cs:__real@3fe0000000000000
0x18015c49a  mulsd   xmm1, xmm7
0x18015c49e  comisd  xmm1, cs:__real@0000000000000000
0x18015c4a6  jb      short loc_18015C4AD
0x18015c4a8  movaps  xmm0, xmm7
0x18015c4ab  jmp     short loc_18015C4B5
0x18015c4ad  movsd   xmm0, cs:__real@bfe0000000000000
0x18015c4b5  addsd   xmm0, xmm1
0x18015c4b9  cvttsd2si edx, xmm0; int
0x18015c4bd  lea     rcx, [rbp+80h+arg_18]; this
0x18015c4c4  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015c4c9  mov     edx, edi
0x18015c4cb  lea     rcx, [rbp+80h+var_C0]
0x18015c4cf  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015c4d5  mulsd   xmm0, xmm6
0x18015c4d9  mulsd   xmm9, cs:__real@40f86a0000000000
0x18015c4e2  divsd   xmm0, xmm9
0x18015c4e7  subsd   xmm6, xmm0
0x18015c4eb  comisd  xmm6, cs:__real@0000000000000000
0x18015c4f3  jnb     short loc_18015C4FD
0x18015c4f5  movsd   xmm7, cs:__real@bfe0000000000000
0x18015c4fd  addsd   xmm7, xmm6
0x18015c501  cvttsd2si edx, xmm7; int
0x18015c505  lea     rcx, [rbp+80h+arg_8]; this
0x18015c50c  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015c511  lea     rdi, [r14+1A8h]
0x18015c518  lea     rdx, [rbp+80h+arg_8]
0x18015c51f  mov     rcx, rdi
0x18015c522  call    ??4CVarStr@Ofc@@QEAAAEAV01@AEBV01@@Z; Ofc::CVarStr::operator=(Ofc::CVarStr const &)
0x18015c527  lea     rcx, asc_1801E05D8; " "
0x18015c52e  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x18015c533  mov     r8d, eax; int
0x18015c536  lea     rdx, asc_1801E05D8; " "
0x18015c53d  mov     rcx, rdi; this
0x18015c540  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015c545  mov     rbx, [rbp+80h+arg_18]
0x18015c54c  mov     eax, [rbx-4]
0x18015c54f  cdq
0x18015c550  sub     eax, edx
0x18015c552  sar     eax, 1
0x18015c554  mov     r8d, eax; int
0x18015c557  mov     rdx, rbx; wchar_t *
0x18015c55a  mov     rcx, rdi; this
0x18015c55d  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015c562  lea     rcx, [r14+178h]; this
0x18015c569  lea     rdx, aM0F0LF1F0F1021; "M 0 ?f0 L ?f1 ?f0 ?f1 0 21600 10800 ?f1"...
0x18015c570  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c575  mov     rcx, r14
0x18015c578  call    ?AddArrowEquations@ToOdfShapeGeometryConversion@Art@@CAXAEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddArrowEquations(Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015c57d  mov     [rsp+180h+var_150], 0
0x18015c584  mov     [rsp+180h+var_14E], 0
0x18015c589  mov     [rsp+180h+var_148], rsi
0x18015c58e  mov     [rsp+180h+var_140], rsi
0x18015c593  mov     [rsp+180h+var_138], rsi
0x18015c598  mov     [rsp+180h+var_130], rsi
0x18015c59d  mov     [rsp+180h+var_128], rsi
0x18015c5a2  mov     [rsp+180h+var_120], rsi
0x18015c5a7  mov     [rsp+180h+var_118], rsi
0x18015c5ac  mov     [rsp+180h+var_110], rsi
0x18015c5b1  mov     [rsp+180h+var_108], rsi
0x18015c5b6  mov     [rbp+80h+var_100], rsi
0x18015c5ba  mov     [rbp+80h+var_F8], rsi
0x18015c5be  mov     [rbp+80h+var_F0], rsi
0x18015c5c2  mov     [rbp+80h+var_E8], rsi
0x18015c5c6  mov     [rbp+80h+var_E0], rsi
0x18015c5ca  call    cs:__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ; Art::FeatureGates::FUsingODF_1_4(void)
0x18015c5d0  test    al, al
0x18015c5d2  jz      short loc_18015C5F6
0x18015c5d4  lea     rdx, a0_2; "$0"
0x18015c5db  lea     rcx, [rsp+180h+var_140]; this
0x18015c5e0  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c5e5  lea     rdx, a1_4; "$1"
0x18015c5ec  lea     rcx, [rsp+180h+var_138]; this
0x18015c5f1  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c5f6  lea     rdx, a01; "$0 $1"
0x18015c5fd  lea     rcx, [rsp+180h+var_148]; this
0x18015c602  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c607  lea     rdx, a0_1; "0"
0x18015c60e  lea     rcx, [rsp+180h+var_120]; this
0x18015c613  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c618  lea     rdx, a21600; "21600"
0x18015c61f  lea     rcx, [rsp+180h+var_118]; this
0x18015c624  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c629  lea     rdx, a0_1; "0"
0x18015c630  lea     rcx, [rsp+180h+var_110]; this
0x18015c635  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c63a  lea     rdx, a10800; "10800"
0x18015c641  lea     rcx, [rsp+180h+var_108]; this
0x18015c646  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015c64b  lea     rcx, [r14+18h]
0x18015c64f  lea     rdx, [rsp+180h+var_150]
0x18015c654  call    ?Push@?$TVector@VHandle@ODF@@$0A@$0PPPPPPPP@@Ofc@@QEAAXAEBVHandle@ODF@@@Z; Ofc::TVector<ODF::Handle,0,4294967295>::Push(ODF::Handle const &)
0x18015c659  nop
0x18015c65a  lea     rcx, [rsp+180h+var_150]; this
0x18015c65f  call    ??1Handle@ODF@@QEAA@XZ; ODF::Handle::~Handle(void)
0x18015c664  lea     rcx, [rbx-0Ch]
0x18015c668  or      ebx, 0FFFFFFFFh
0x18015c66b  cmp     dword ptr [rcx+4], 0
0x18015c66f  jz      short loc_18015C68C
0x18015c671  cmp     dword ptr [rcx], 1
0x18015c674  jz      short loc_18015C680
0x18015c676  mov     eax, ebx
0x18015c678  lock xadd [rcx], eax
0x18015c67c  add     eax, ebx
0x18015c67e  jnz     short loc_18015C68C
0x18015c680  test    rcx, rcx
0x18015c683  jz      short loc_18015C68C
0x18015c685  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015c68b  nop
0x18015c68c  mov     rcx, [rbp+80h+arg_8]
0x18015c693  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18015c697  cmp     dword ptr [rcx+4], 0
0x18015c69b  jz      short loc_18015C6B8
0x18015c69d  cmp     dword ptr [rcx], 1
0x18015c6a0  jz      short loc_18015C6AC
0x18015c6a2  mov     eax, ebx
0x18015c6a4  lock xadd [rcx], eax
0x18015c6a8  add     eax, ebx
0x18015c6aa  jnz     short loc_18015C6B8
0x18015c6ac  test    rcx, rcx
0x18015c6af  jz      short loc_18015C6B8
0x18015c6b1  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015c6b7  nop
0x18015c6b8  lea     rcx, [rbp+80h+var_88]
0x18015c6bc  call    cs:__imp_??1PresetGeometry2D@Art@@QEAA@XZ; Art::PresetGeometry2D::~PresetGeometry2D(void)
0x18015c6c2  lea     rcx, [rbp+80h+var_C0]
0x18015c6c6  call    cs:__imp_??1GeometryCompiler@Art@@QEAA@XZ; Art::GeometryCompiler::~GeometryCompiler(void)
0x18015c6cc  lea     rcx, [rbp+80h+var_D0]
0x18015c6d0  call    cs:__imp_??1Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::~Geometry2D(void)
0x18015c6d6  lea     r11, [rsp+180h+var_20]
0x18015c6de  mov     rbx, [r11+30h]
0x18015c6e2  movaps  xmm6, xmmword ptr [r11-10h]
0x18015c6e7  movaps  xmm7, xmmword ptr [r11-20h]
0x18015c6ec  movaps  xmm9, xmmword ptr [r11-30h]
0x18015c6f1  mov     rsp, r11
0x18015c6f4  pop     r14
0x18015c6f6  pop     r12
0x18015c6f8  pop     rdi
0x18015c6f9  pop     rsi
0x18015c6fa  pop     rbp
0x18015c6fb  retn
0x18015c6fc  lea     rcx, ?tag_f5mb@Ofc@@3VMsoReserveTag@@B; "bm5f"
0x18015c703  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x18015c708  mov     ecx, eax; unsigned int
0x18015c70a  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18015c70f  int     3; Trap to Debugger
```
