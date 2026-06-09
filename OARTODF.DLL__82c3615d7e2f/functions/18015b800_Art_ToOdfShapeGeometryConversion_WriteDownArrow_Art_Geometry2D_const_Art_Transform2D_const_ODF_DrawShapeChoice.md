# Art::ToOdfShapeGeometryConversion::WriteDownArrow(Art::Geometry2D const &,Art::Transform2D const &,ODF::DrawShapeChoice_<0> &)

- ea: `0x18015b800`
- end: `0x18015bcb1`
- name: `?WriteDownArrow@ToOdfShapeGeometryConversion@Art@@CAXAEBVGeometry2D@2@AEBVTransform2D@2@AEAV?$DrawShapeChoice_@$0A@@ODF@@@Z`
- size: `1201`
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
- `0x18015b800`

## import_xrefs

- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015b979`
- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015b979`
- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015b944`
- `oart!__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015b944`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015bc5d`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015bc5d`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015ba12`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015ba70`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015ba12`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015ba70`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015b9dd`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015b9ef`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015b9dd`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015b9ef`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015bc67`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015bc67`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015b95c`
- `oart!__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ` at `0x18015b95c`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015bb6b`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015bb6b`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015bc71`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015bc71`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015b996`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015b996`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015b9cc`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015b9cc`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015bc26`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015bc52`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015bc26`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015bc52`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Art::ToOdfShapeGeometryConversion::WriteDownArrow(
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
  double v21; // xmm7_8
  unsigned int v22; // r8d
  double v23; // xmm1_8
  double v24; // xmm0_8
  unsigned int v25; // r8d
  double v26; // xmm6_8
  const wchar_t *v27; // rdx
  int v28; // eax
  wchar_t *v29; // rbx
  Art::FeatureGates *v30; // rcx
  void *v31; // rdx
  Mso::Memory *v32; // rcx
  Mso::Memory *v33; // rcx
  unsigned int v34; // eax
  __int16 v35; // [rsp+30h] [rbp-D0h] BYREF
  char v36; // [rsp+32h] [rbp-CEh]
  wchar_t *v37; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v38; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v39[3]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v40; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v41; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v42; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v43[7]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v44[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v45[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v46[104]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t *v47; // [rsp+198h] [rbp+98h] BYREF
  wchar_t *v48; // [rsp+1A8h] [rbp+A8h] BYREF

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
  Ofc::CStr::operator=(v6 + 48, (Ofc *)L"?f0 0 ?f2 ?f5");
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
  v26 = 21600.0 - Art::GeometryCompiler::Lookup((Art::GeometryCompiler *)v45, v20) * 21600.0 / (v18 * 100000.0);
  if ( v26 < 0.0 )
    v21 = DOUBLE_N0_5;
  Ofc::CStr::DecodeInt(&v47, (int)(v21 + v26), v25);
  Ofc::CVarStr::operator=(v6 + 53, &v47);
  v28 = Ofc::CchWzLen((Ofc *)L" ", v27);
  Ofc::CStr::Append((Ofc::CStr *)(v6 + 53), L" ", v28);
  v29 = v48;
  Ofc::CStr::Append((Ofc::CStr *)(v6 + 53), v48, *((_DWORD *)v48 - 1) / 2);
  Ofc::CStr::operator=(v6 + 47, (Ofc *)L"M ?f0 0 L ?f0 ?f1 0 ?f1 10800 21600 21600 ?f1 ?f2 ?f1 ?f2 0 Z N");
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
0x18015b800  mov     rax, rsp
0x18015b803  mov     [rax+8], rbx
0x18015b807  push    rbp
0x18015b808  push    rsi
0x18015b809  push    rdi
0x18015b80a  push    r12
0x18015b80c  push    r14
0x18015b80e  lea     rbp, [rsp-60h]
0x18015b813  sub     rsp, 160h
0x18015b81a  movaps  xmmword ptr [rax-38h], xmm6
0x18015b81e  movaps  xmmword ptr [rax-48h], xmm7
0x18015b822  movaps  xmmword ptr [rax-58h], xmm9
0x18015b827  mov     rdi, rdx
0x18015b82a  mov     rsi, rcx
0x18015b82d  mov     rcx, r8
0x18015b830  call    ??$SwitchTo@UcustomShape@DrawShapeChoiceChoices@ODF@@@?$TChoice@VDrawShapeChoiceChoiceIDsImpl@ODF@@@Ofc@@QEAAAEAVCustomShape@ODF@@XZ; Ofc::TChoice<ODF::DrawShapeChoiceChoiceIDsImpl>::SwitchTo<ODF::DrawShapeChoiceChoices::customShape>(void)
0x18015b835  mov     rcx, [rax]
0x18015b838  add     rcx, 48h ; 'H'
0x18015b83c  call    ?EnsureStorage@?$TOptional@VEnhancedGeometry@ODF@@@Ofc@@QEAAAEAVEnhancedGeometry@ODF@@XZ; Ofc::TOptional<ODF::EnhancedGeometry>::EnsureStorage(void)
0x18015b841  mov     r14, rax
0x18015b844  lea     rcx, [rax+60h]
0x18015b848  call    ?EnsureStorage@?$TOptional@V?$TArray@H@Ofc@@@Ofc@@QEAAAEAV?$TArray@H@2@XZ; Ofc::TOptional<Ofc::TArray<int>>::EnsureStorage(void)
0x18015b84d  mov     rbx, rax
0x18015b850  lea     r12, ?Do@?$TCopyConstructRange@W4TextEmphasisType@ODF@@$00$00@Ofc@@SAXPEBEPEAEK@Z; Ofc::TCopyConstructRange<ODF::TextEmphasisType,1,1>::Do(uchar const *,uchar *,ulong)
0x18015b857  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015b85a  mov     edx, 4; unsigned int
0x18015b85f  mov     rcx, rax; this
0x18015b862  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015b867  mov     edx, [rbx+8]
0x18015b86a  mov     rcx, [rbx]
0x18015b86d  xor     eax, eax
0x18015b86f  mov     [rcx+rdx*4], eax
0x18015b872  inc     dword ptr [rbx+8]
0x18015b875  mov     [rcx+rdx*4], eax
0x18015b878  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015b87b  lea     edx, [rax+4]; unsigned int
0x18015b87e  mov     rcx, rbx; this
0x18015b881  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015b886  mov     ecx, [rbx+8]
0x18015b889  mov     rax, [rbx]
0x18015b88c  xor     edx, edx
0x18015b88e  mov     [rax+rcx*4], edx
0x18015b891  inc     dword ptr [rbx+8]
0x18015b894  mov     [rax+rcx*4], edx
0x18015b897  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015b89a  mov     edx, 4; unsigned int
0x18015b89f  mov     rcx, rbx; this
0x18015b8a2  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015b8a7  mov     ecx, [rbx+8]
0x18015b8aa  mov     rax, [rbx]
0x18015b8ad  xor     edx, edx
0x18015b8af  mov     [rax+rcx*4], edx
0x18015b8b2  inc     dword ptr [rbx+8]
0x18015b8b5  mov     dword ptr [rax+rcx*4], 5460h
0x18015b8bc  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015b8bf  lea     r12d, [rdx+4]
0x18015b8c3  mov     edx, r12d; unsigned int
0x18015b8c6  mov     rcx, rbx; this
0x18015b8c9  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015b8ce  mov     ecx, [rbx+8]
0x18015b8d1  mov     rax, [rbx]
0x18015b8d4  xor     edx, edx
0x18015b8d6  mov     [rax+rcx*4], edx
0x18015b8d9  inc     dword ptr [rbx+8]
0x18015b8dc  mov     dword ptr [rax+rcx*4], 5460h
0x18015b8e3  lea     rcx, [r14+188h]; this
0x18015b8ea  lea     rdx, a0F121600F1; "0 ?f1 21600 ?f1"
0x18015b8f1  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015b8f6  lea     rcx, [r14+198h]; this
0x18015b8fd  lea     rdx, a27090; "-270, -90"
0x18015b904  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015b909  lea     rcx, [r14+180h]; this
0x18015b910  lea     rdx, aF00F2F5; "?f0 0 ?f2 ?f5"
0x18015b917  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015b91c  mov     dword ptr [rbp+80h+arg_8], 0
0x18015b926  lea     rcx, [r14+50h]
0x18015b92a  lea     rdx, [rbp+80h+arg_8]
0x18015b931  call    ??$?4W4DrawCustomShapeType@ODF@@@?$TVariant@VCustomShapeTypeIDsImpl@ODF@@@Ofc@@QEAAAEAV01@AEBW4DrawCustomShapeType@ODF@@@Z; Ofc::TVariant<ODF::CustomShapeTypeIDsImpl>::operator=<ODF::DrawCustomShapeType>(ODF::DrawCustomShapeType const &)
0x18015b936  lea     rbx, [rdi+10h]
0x18015b93a  lea     rdx, [rbp+80h+arg_8]
0x18015b941  mov     rcx, rbx
0x18015b944  call    cs:__imp_?GetCx@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ; Art::PosSize2D::GetCx(void)
0x18015b94a  xorps   xmm6, xmm6
0x18015b94d  cvtsi2sd xmm6, qword ptr [rax]
0x18015b952  lea     rdx, [rbp+80h+arg_8]
0x18015b959  mov     rcx, rbx
0x18015b95c  call    cs:__imp_?GetCy@PosSize2D@Art@@QEBA?BV?$CoordMethods@V?$TRangeRestricted@_JUPosCoordRange@Art@@@Ofc@@@2@XZ; Art::PosSize2D::GetCy(void)
0x18015b962  xorps   xmm9, xmm9
0x18015b966  cvtsi2sd xmm9, qword ptr [rax]
0x18015b96b  minsd   xmm6, xmm9
0x18015b970  divsd   xmm9, xmm6
0x18015b975  lea     rcx, [rbp+80h+var_D0]
0x18015b979  call    cs:__imp_??0Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::Geometry2D(void)
0x18015b97f  nop
0x18015b980  mov     [rsp+180h+var_160], 0FFh
0x18015b988  lea     r9, [rbp+80h+var_D0]
0x18015b98c  mov     r8, rbx
0x18015b98f  mov     rdx, rsi
0x18015b992  lea     rcx, [rbp+80h+var_C0]
0x18015b996  call    cs:__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z; Art::GeometryCompiler::GeometryCompiler(Art::Geometry2D const &,Art::PosSize2D const &,Art::Geometry2D &,ulong)
0x18015b99c  nop
0x18015b99d  mov     rcx, rsi
0x18015b9a0  call    ??$Is@UPreset@Geom@Art@@@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(void)
0x18015b9a5  test    al, al
0x18015b9a7  jz      loc_18015BC9D
0x18015b9ad  cmp     qword ptr [rsi+8], 1
0x18015b9b2  ja      short loc_18015B9BC
0x18015b9b4  mov     rcx, rsi
0x18015b9b7  call    ?DemandInit@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@AEBAXXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::DemandInit(void)
0x18015b9bc  mov     rdx, [rsi]
0x18015b9bf  test    rdx, rdx
0x18015b9c2  jz      loc_18015BC9D
0x18015b9c8  lea     rcx, [rbp+80h+var_88]
0x18015b9cc  call    cs:__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z; Art::PresetGeometry2D::PresetGeometry2D(Art::PresetGeometry2D const &)
0x18015b9d2  nop
0x18015b9d3  mov     edx, r12d
0x18015b9d6  lea     rcx, aAdj1; "adj1"
0x18015b9dd  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015b9e3  mov     ebx, eax
0x18015b9e5  mov     edx, r12d
0x18015b9e8  lea     rcx, aAdj2; "adj2"
0x18015b9ef  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015b9f5  mov     edi, eax
0x18015b9f7  lea     rsi, dword_1801DBD74
0x18015b9fe  mov     [rbp+80h+arg_8], rsi
0x18015ba05  mov     [rbp+80h+arg_18], rsi
0x18015ba0c  mov     edx, ebx
0x18015ba0e  lea     rcx, [rbp+80h+var_C0]
0x18015ba12  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015ba18  movsd   xmm6, cs:__real@40d5180000000000
0x18015ba20  mulsd   xmm0, xmm6
0x18015ba24  divsd   xmm0, cs:__real@40f86a0000000000
0x18015ba2c  movaps  xmm1, xmm6
0x18015ba2f  subsd   xmm1, xmm0
0x18015ba33  movsd   xmm7, cs:__real@3fe0000000000000
0x18015ba3b  mulsd   xmm1, xmm7
0x18015ba3f  comisd  xmm1, cs:__real@0000000000000000
0x18015ba47  jb      short loc_18015BA4E
0x18015ba49  movaps  xmm0, xmm7
0x18015ba4c  jmp     short loc_18015BA56
0x18015ba4e  movsd   xmm0, cs:__real@bfe0000000000000
0x18015ba56  addsd   xmm0, xmm1
0x18015ba5a  cvttsd2si edx, xmm0; int
0x18015ba5e  lea     rcx, [rbp+80h+arg_18]; this
0x18015ba65  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015ba6a  mov     edx, edi
0x18015ba6c  lea     rcx, [rbp+80h+var_C0]
0x18015ba70  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015ba76  mulsd   xmm0, xmm6
0x18015ba7a  mulsd   xmm9, cs:__real@40f86a0000000000
0x18015ba83  divsd   xmm0, xmm9
0x18015ba88  subsd   xmm6, xmm0
0x18015ba8c  comisd  xmm6, cs:__real@0000000000000000
0x18015ba94  jnb     short loc_18015BA9E
0x18015ba96  movsd   xmm7, cs:__real@bfe0000000000000
0x18015ba9e  addsd   xmm7, xmm6
0x18015baa2  cvttsd2si edx, xmm7; int
0x18015baa6  lea     rcx, [rbp+80h+arg_8]; this
0x18015baad  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015bab2  lea     rdi, [r14+1A8h]
0x18015bab9  lea     rdx, [rbp+80h+arg_8]
0x18015bac0  mov     rcx, rdi
0x18015bac3  call    ??4CVarStr@Ofc@@QEAAAEAV01@AEBV01@@Z; Ofc::CVarStr::operator=(Ofc::CVarStr const &)
0x18015bac8  lea     rcx, asc_1801E05D8; " "
0x18015bacf  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x18015bad4  mov     r8d, eax; int
0x18015bad7  lea     rdx, asc_1801E05D8; " "
0x18015bade  mov     rcx, rdi; this
0x18015bae1  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015bae6  mov     rbx, [rbp+80h+arg_18]
0x18015baed  mov     eax, [rbx-4]
0x18015baf0  cdq
0x18015baf1  sub     eax, edx
0x18015baf3  sar     eax, 1
0x18015baf5  mov     r8d, eax; int
0x18015baf8  mov     rdx, rbx; wchar_t *
0x18015bafb  mov     rcx, rdi; this
0x18015bafe  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015bb03  lea     rcx, [r14+178h]; this
0x18015bb0a  lea     rdx, aMF00LF0F10F110; "M ?f0 0 L ?f0 ?f1 0 ?f1 10800 21600 216"...
0x18015bb11  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015bb16  mov     rcx, r14
0x18015bb19  call    ?AddArrowEquations@ToOdfShapeGeometryConversion@Art@@CAXAEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddArrowEquations(Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015bb1e  mov     [rsp+180h+var_150], 0
0x18015bb25  mov     [rsp+180h+var_14E], 0
0x18015bb2a  mov     [rsp+180h+var_148], rsi
0x18015bb2f  mov     [rsp+180h+var_140], rsi
0x18015bb34  mov     [rsp+180h+var_138], rsi
0x18015bb39  mov     [rsp+180h+var_130], rsi
0x18015bb3e  mov     [rsp+180h+var_128], rsi
0x18015bb43  mov     [rsp+180h+var_120], rsi
0x18015bb48  mov     [rsp+180h+var_118], rsi
0x18015bb4d  mov     [rsp+180h+var_110], rsi
0x18015bb52  mov     [rsp+180h+var_108], rsi
0x18015bb57  mov     [rbp+80h+var_100], rsi
0x18015bb5b  mov     [rbp+80h+var_F8], rsi
0x18015bb5f  mov     [rbp+80h+var_F0], rsi
0x18015bb63  mov     [rbp+80h+var_E8], rsi
0x18015bb67  mov     [rbp+80h+var_E0], rsi
0x18015bb6b  call    cs:__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ; Art::FeatureGates::FUsingODF_1_4(void)
0x18015bb71  test    al, al
0x18015bb73  jz      short loc_18015BB97
0x18015bb75  lea     rdx, a1_4; "$1"
0x18015bb7c  lea     rcx, [rsp+180h+var_140]; this
0x18015bb81  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015bb86  lea     rdx, a0_2; "$0"
0x18015bb8d  lea     rcx, [rsp+180h+var_138]; this
0x18015bb92  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015bb97  lea     rdx, a10_0; "$1 $0"
0x18015bb9e  lea     rcx, [rsp+180h+var_148]; this
0x18015bba3  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015bba8  lea     rdx, a0_1; "0"
0x18015bbaf  lea     rcx, [rsp+180h+var_120]; this
0x18015bbb4  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015bbb9  lea     rdx, a10800; "10800"
0x18015bbc0  lea     rcx, [rsp+180h+var_118]; this
0x18015bbc5  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015bbca  lea     rdx, a0_1; "0"
0x18015bbd1  lea     rcx, [rsp+180h+var_110]; this
0x18015bbd6  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015bbdb  lea     rdx, a21600; "21600"
0x18015bbe2  lea     rcx, [rsp+180h+var_108]; this
0x18015bbe7  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015bbec  lea     rcx, [r14+18h]
0x18015bbf0  lea     rdx, [rsp+180h+var_150]
0x18015bbf5  call    ?Push@?$TVector@VHandle@ODF@@$0A@$0PPPPPPPP@@Ofc@@QEAAXAEBVHandle@ODF@@@Z; Ofc::TVector<ODF::Handle,0,4294967295>::Push(ODF::Handle const &)
0x18015bbfa  nop
0x18015bbfb  lea     rcx, [rsp+180h+var_150]; this
0x18015bc00  call    ??1Handle@ODF@@QEAA@XZ; ODF::Handle::~Handle(void)
0x18015bc05  lea     rcx, [rbx-0Ch]
0x18015bc09  or      ebx, 0FFFFFFFFh
0x18015bc0c  cmp     dword ptr [rcx+4], 0
0x18015bc10  jz      short loc_18015BC2D
0x18015bc12  cmp     dword ptr [rcx], 1
0x18015bc15  jz      short loc_18015BC21
0x18015bc17  mov     eax, ebx
0x18015bc19  lock xadd [rcx], eax
0x18015bc1d  add     eax, ebx
0x18015bc1f  jnz     short loc_18015BC2D
0x18015bc21  test    rcx, rcx
0x18015bc24  jz      short loc_18015BC2D
0x18015bc26  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015bc2c  nop
0x18015bc2d  mov     rcx, [rbp+80h+arg_8]
0x18015bc34  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18015bc38  cmp     dword ptr [rcx+4], 0
0x18015bc3c  jz      short loc_18015BC59
0x18015bc3e  cmp     dword ptr [rcx], 1
0x18015bc41  jz      short loc_18015BC4D
0x18015bc43  mov     eax, ebx
0x18015bc45  lock xadd [rcx], eax
0x18015bc49  add     eax, ebx
0x18015bc4b  jnz     short loc_18015BC59
0x18015bc4d  test    rcx, rcx
0x18015bc50  jz      short loc_18015BC59
0x18015bc52  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015bc58  nop
0x18015bc59  lea     rcx, [rbp+80h+var_88]
0x18015bc5d  call    cs:__imp_??1PresetGeometry2D@Art@@QEAA@XZ; Art::PresetGeometry2D::~PresetGeometry2D(void)
0x18015bc63  lea     rcx, [rbp+80h+var_C0]
0x18015bc67  call    cs:__imp_??1GeometryCompiler@Art@@QEAA@XZ; Art::GeometryCompiler::~GeometryCompiler(void)
0x18015bc6d  lea     rcx, [rbp+80h+var_D0]
0x18015bc71  call    cs:__imp_??1Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::~Geometry2D(void)
0x18015bc77  lea     r11, [rsp+180h+var_20]
0x18015bc7f  mov     rbx, [r11+30h]
0x18015bc83  movaps  xmm6, xmmword ptr [r11-10h]
0x18015bc88  movaps  xmm7, xmmword ptr [r11-20h]
0x18015bc8d  movaps  xmm9, xmmword ptr [r11-30h]
0x18015bc92  mov     rsp, r11
0x18015bc95  pop     r14
0x18015bc97  pop     r12
0x18015bc99  pop     rdi
0x18015bc9a  pop     rsi
0x18015bc9b  pop     rbp
0x18015bc9c  retn
0x18015bc9d  lea     rcx, ?tag_f5mb@Ofc@@3VMsoReserveTag@@B; "bm5f"
0x18015bca4  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x18015bca9  mov     ecx, eax; unsigned int
0x18015bcab  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18015bcb0  int     3; Trap to Debugger
```
