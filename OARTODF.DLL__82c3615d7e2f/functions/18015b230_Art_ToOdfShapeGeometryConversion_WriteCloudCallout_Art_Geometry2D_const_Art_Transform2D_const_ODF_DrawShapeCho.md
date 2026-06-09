# Art::ToOdfShapeGeometryConversion::WriteCloudCallout(Art::Geometry2D const &,Art::Transform2D const &,ODF::DrawShapeChoice_<0> &)

- ea: `0x18015b230`
- end: `0x18015b7fb`
- name: `?WriteCloudCallout@ToOdfShapeGeometryConversion@Art@@CAXAEBVGeometry2D@2@AEBVTransform2D@2@AEAV?$DrawShapeChoice_@$0A@@ODF@@@Z`
- size: `1483`
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
- `0x18015b230`

## import_xrefs

- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015b35b`
- `oart!__imp_??0Geometry2D@Art@@QEAA@XZ` at `0x18015b35b`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015b7b0`
- `oart!__imp_??1PresetGeometry2D@Art@@QEAA@XZ` at `0x18015b7b0`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015b3f3`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015b447`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015b3f3`
- `oart!__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z` at `0x18015b447`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015b3c1`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015b3d3`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015b3c1`
- `oart!__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z` at `0x18015b3d3`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015b7ba`
- `oart!__imp_??1GeometryCompiler@Art@@QEAA@XZ` at `0x18015b7ba`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015b705`
- `oart!__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ` at `0x18015b705`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015b7c5`
- `oart!__imp_??1Geometry2D@Art@@QEAA@XZ` at `0x18015b7c5`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015b37a`
- `oart!__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z` at `0x18015b37a`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015b3b0`
- `oart!__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z` at `0x18015b3b0`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015b77c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015b7a5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015b77c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18015b7a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Art::ToOdfShapeGeometryConversion::WriteCloudCallout(
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
  Ofc::CStr::operator=(v6 + 49, (Ofc *)L"0 10800 10800 21600 21600 10800 10800 0 ?f13 ?f14");
  Ofc::CStr::operator=(v6 + 51, (Ofc *)L"-270, 180, -90, 0, -212.2042");
  Ofc::CStr::operator=(v6 + 48, (Ofc *)L"3000 3320 17110 17330");
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
    (Ofc *)L"M 1930 7160 C 1530 4490 3400 1970 5270 1970 5860 1950 6470 2210 6970 2600 7450 1390 8340 650 9340 650 10004 6"
            "90 10710 1050 11210 1700 11570 630 12330 0 13150 0 13840 0 14470 460 14870 1160 15330 440 16020 0 16740 0 17"
            "910 0 18900 1130 19110 2710 20240 3150 21060 4580 21060 6220 21060 6720 21000 7200 20830 7660 21310 8460 216"
            "00 9450 21600 10460 21600 12750 20310 14680 18650 15010 18650 17200 17370 18920 15770 18920 15220 18920 1470"
            "0 18710 14240 18310 13820 20240 12490 21600 11000 21600 9890 21600 8840 20790 8210 19510 7620 20000 7930 202"
            "90 6240 20290 4850 20290 3570 19280 2900 17640 1300 17600 480 16300 480 14660 480 13900 690 13210 1070 12640"
            " 380 12160 0 11210 0 10120 0 8590 840 7330 1930 7160 Z N M 1930 7160 C 1950 7410 2040 7690 2090 7920 F N M 6"
            "970 2600 C 7200 2790 7480 3050 7670 3310 F N M 11210 1700 C 11130 1910 11080 2160 11030 2400 F N M 14870 116"
            "0 C 14720 1400 14640 1720 14540 2010 F N M 19110 2710 C 19130 2890 19230 3290 19190 3380 F N M 20830 7660 C "
            "20660 8170 20430 8620 20110 8990 F N M 18660 15010 C 18740 14200 18280 12200 17000 11450 F N M 14240 18310 C"
            " 14320 17980 14350 17680 14370 17360 F N M 8220 19510 C 8060 19250 7960 18950 7860 18640 F N M 2900 17640 C "
            "3090 17600 3280 17540 3460 17450 F N M 1070 12640 C 1400 12900 1780 13130 2330 13040 F N U ?f17 ?f18 1800 18"
            "00 0 23592960 Z N U ?f19 ?f20 1200 1200 0 23592960 Z N U ?f13 ?f14 700 700 0 23592960 Z N");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f0", (Ofc *)L"$0 -10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f1", (Ofc *)L"$1 -10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f2", (Ofc *)L"atan2(?f1 ,?f0 )/(pi/180)");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f3", (Ofc *)L"10800*cos(?f2 *(pi/180))");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f4", (Ofc *)L"10800*sin(?f2 *(pi/180))");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f5", (Ofc *)L"?f3 +10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f6", (Ofc *)L"?f4 +10800");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f7", (Ofc *)L"$0 -?f5 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f8", (Ofc *)L"$1 -?f6 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f9", (Ofc *)L"?f7 /3");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f10", (Ofc *)L"?f8 /3");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f11", (Ofc *)L"?f7 *2/3");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f12", (Ofc *)L"?f8 *2/3");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f13", (Ofc *)L"$0 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f14", (Ofc *)L"$1 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f15", (Ofc *)L"?f3 /12");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f16", (Ofc *)L"?f4 /12");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f17", (Ofc *)L"?f9 +?f5 -?f15 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f18", (Ofc *)L"?f10 +?f6 -?f16 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f19", (Ofc *)L"?f11 +?f5 ");
  Art::ToOdfShapeGeometryConversion::AddEquation((Ofc *)L"f20", (Ofc *)L"?f12 +?f6 ");
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
0x18015b230  mov     rax, rsp
0x18015b233  mov     [rax+8], rbx
0x18015b237  push    rbp
0x18015b238  push    rsi
0x18015b239  push    rdi
0x18015b23a  push    r12
0x18015b23c  push    r14
0x18015b23e  lea     rbp, [rax-68h]
0x18015b242  sub     rsp, 140h
0x18015b249  movaps  xmmword ptr [rax-38h], xmm6
0x18015b24d  mov     rdi, rdx
0x18015b250  mov     rsi, rcx
0x18015b253  mov     rcx, r8
0x18015b256  call    ??$SwitchTo@UcustomShape@DrawShapeChoiceChoices@ODF@@@?$TChoice@VDrawShapeChoiceChoiceIDsImpl@ODF@@@Ofc@@QEAAAEAVCustomShape@ODF@@XZ; Ofc::TChoice<ODF::DrawShapeChoiceChoiceIDsImpl>::SwitchTo<ODF::DrawShapeChoiceChoices::customShape>(void)
0x18015b25b  mov     rcx, [rax]
0x18015b25e  add     rcx, 48h ; 'H'
0x18015b262  call    ?EnsureStorage@?$TOptional@VEnhancedGeometry@ODF@@@Ofc@@QEAAAEAVEnhancedGeometry@ODF@@XZ; Ofc::TOptional<ODF::EnhancedGeometry>::EnsureStorage(void)
0x18015b267  mov     r14, rax
0x18015b26a  lea     rcx, [rax+60h]
0x18015b26e  call    ?EnsureStorage@?$TOptional@V?$TArray@H@Ofc@@@Ofc@@QEAAAEAV?$TArray@H@2@XZ; Ofc::TOptional<Ofc::TArray<int>>::EnsureStorage(void)
0x18015b273  mov     rbx, rax
0x18015b276  lea     r12, ?Do@?$TCopyConstructRange@W4TextEmphasisType@ODF@@$00$00@Ofc@@SAXPEBEPEAEK@Z; Ofc::TCopyConstructRange<ODF::TextEmphasisType,1,1>::Do(uchar const *,uchar *,ulong)
0x18015b27d  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015b280  mov     edx, 4; unsigned int
0x18015b285  mov     rcx, rax; this
0x18015b288  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015b28d  mov     edx, [rbx+8]
0x18015b290  mov     rcx, [rbx]
0x18015b293  xor     eax, eax
0x18015b295  mov     [rcx+rdx*4], eax
0x18015b298  inc     dword ptr [rbx+8]
0x18015b29b  mov     [rcx+rdx*4], eax
0x18015b29e  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015b2a1  lea     edx, [rax+4]; unsigned int
0x18015b2a4  mov     rcx, rbx; this
0x18015b2a7  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015b2ac  mov     ecx, [rbx+8]
0x18015b2af  mov     rax, [rbx]
0x18015b2b2  xor     edx, edx
0x18015b2b4  mov     [rax+rcx*4], edx
0x18015b2b7  inc     dword ptr [rbx+8]
0x18015b2ba  mov     [rax+rcx*4], edx
0x18015b2bd  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015b2c0  mov     edx, 4; unsigned int
0x18015b2c5  mov     rcx, rbx; this
0x18015b2c8  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015b2cd  mov     ecx, [rbx+8]
0x18015b2d0  mov     rax, [rbx]
0x18015b2d3  xor     edx, edx
0x18015b2d5  mov     [rax+rcx*4], edx
0x18015b2d8  inc     dword ptr [rbx+8]
0x18015b2db  mov     dword ptr [rax+rcx*4], 5460h
0x18015b2e2  mov     r8, r12; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18015b2e5  lea     r12d, [rdx+4]
0x18015b2e9  mov     edx, r12d; unsigned int
0x18015b2ec  mov     rcx, rbx; this
0x18015b2ef  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18015b2f4  mov     ecx, [rbx+8]
0x18015b2f7  mov     rax, [rbx]
0x18015b2fa  xor     edx, edx
0x18015b2fc  mov     [rax+rcx*4], edx
0x18015b2ff  inc     dword ptr [rbx+8]
0x18015b302  mov     dword ptr [rax+rcx*4], 5460h
0x18015b309  lea     rcx, [r14+188h]; this
0x18015b310  lea     rdx, a01080010800216; "0 10800 10800 21600 21600 10800 10800 0"...
0x18015b317  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015b31c  lea     rcx, [r14+198h]; this
0x18015b323  lea     rdx, a27018090021220; "-270, 180, -90, 0, -212.2042"
0x18015b32a  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015b32f  lea     rcx, [r14+180h]; this
0x18015b336  lea     rdx, a30003320171101; "3000 3320 17110 17330"
0x18015b33d  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015b342  mov     dword ptr [rbp+60h+arg_8], 0
0x18015b349  lea     rcx, [r14+50h]
0x18015b34d  lea     rdx, [rbp+60h+arg_8]
0x18015b351  call    ??$?4W4DrawCustomShapeType@ODF@@@?$TVariant@VCustomShapeTypeIDsImpl@ODF@@@Ofc@@QEAAAEAV01@AEBW4DrawCustomShapeType@ODF@@@Z; Ofc::TVariant<ODF::CustomShapeTypeIDsImpl>::operator=<ODF::DrawCustomShapeType>(ODF::DrawCustomShapeType const &)
0x18015b356  lea     rcx, [rsp+160h+var_130]
0x18015b35b  call    cs:__imp_??0Geometry2D@Art@@QEAA@XZ; Art::Geometry2D::Geometry2D(void)
0x18015b361  nop
0x18015b362  lea     r8, [rdi+10h]
0x18015b366  mov     [rsp+160h+var_140], 0FFh
0x18015b36e  lea     r9, [rsp+160h+var_130]
0x18015b373  mov     rdx, rsi
0x18015b376  lea     rcx, [rbp+60h+var_A0]
0x18015b37a  call    cs:__imp_??0GeometryCompiler@Art@@QEAA@AEBVGeometry2D@1@AEBVPosSize2D@1@AEAV21@K@Z; Art::GeometryCompiler::GeometryCompiler(Art::Geometry2D const &,Art::PosSize2D const &,Art::Geometry2D &,ulong)
0x18015b380  nop
0x18015b381  mov     rcx, rsi
0x18015b384  call    ??$Is@UPreset@Geom@Art@@@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(void)
0x18015b389  test    al, al
0x18015b38b  jz      loc_18015B7E7
0x18015b391  cmp     qword ptr [rsi+8], 1
0x18015b396  ja      short loc_18015B3A0
0x18015b398  mov     rcx, rsi
0x18015b39b  call    ?DemandInit@?$TChoice@VGeometry2DDataChoiceIDsImpl@Art@@@Ofc@@AEBAXXZ; Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::DemandInit(void)
0x18015b3a0  mov     rdx, [rsi]
0x18015b3a3  test    rdx, rdx
0x18015b3a6  jz      loc_18015B7E7
0x18015b3ac  lea     rcx, [rbp+60h+var_68]
0x18015b3b0  call    cs:__imp_??0PresetGeometry2D@Art@@QEAA@AEBV01@@Z; Art::PresetGeometry2D::PresetGeometry2D(Art::PresetGeometry2D const &)
0x18015b3b6  nop
0x18015b3b7  mov     edx, r12d
0x18015b3ba  lea     rcx, aAdj1; "adj1"
0x18015b3c1  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015b3c7  mov     ebx, eax
0x18015b3c9  mov     edx, r12d
0x18015b3cc  lea     rcx, aAdj2; "adj2"
0x18015b3d3  call    cs:__imp_?MapStringToToken@GeomGuideName@Art@@SAHPEB_WH@Z; Art::GeomGuideName::MapStringToToken(wchar_t const *,int)
0x18015b3d9  mov     edi, eax
0x18015b3db  lea     rsi, dword_1801DBD74
0x18015b3e2  mov     [rbp+60h+arg_8], rsi
0x18015b3e6  mov     [rbp+60h+arg_18], rsi
0x18015b3ed  mov     edx, ebx
0x18015b3ef  lea     rcx, [rbp+60h+var_A0]
0x18015b3f3  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015b3f9  mulsd   xmm0, cs:__real@40d5180000000000
0x18015b401  divsd   xmm0, cs:__real@40f86a0000000000
0x18015b409  addsd   xmm0, cs:__real@40c5180000000000
0x18015b411  movsd   xmm6, cs:__real@3fe0000000000000
0x18015b419  comisd  xmm0, cs:__real@0000000000000000
0x18015b421  jb      short loc_18015B428
0x18015b423  movaps  xmm1, xmm6
0x18015b426  jmp     short loc_18015B430
0x18015b428  movsd   xmm1, cs:__real@bfe0000000000000
0x18015b430  addsd   xmm1, xmm0
0x18015b434  cvttsd2si edx, xmm1; int
0x18015b438  lea     rcx, [rbp+60h+arg_8]; this
0x18015b43c  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015b441  mov     edx, edi
0x18015b443  lea     rcx, [rbp+60h+var_A0]
0x18015b447  call    cs:__imp_?Lookup@GeometryCompiler@Art@@QEAANH@Z; Art::GeometryCompiler::Lookup(int)
0x18015b44d  mulsd   xmm0, cs:__real@40d5180000000000
0x18015b455  divsd   xmm0, cs:__real@40f86a0000000000
0x18015b45d  addsd   xmm0, cs:__real@40c5180000000000
0x18015b465  comisd  xmm0, cs:__real@0000000000000000
0x18015b46d  jnb     short loc_18015B477
0x18015b46f  movsd   xmm6, cs:__real@bfe0000000000000
0x18015b477  addsd   xmm6, xmm0
0x18015b47b  cvttsd2si edx, xmm6; int
0x18015b47f  lea     rcx, [rbp+60h+arg_18]; this
0x18015b486  call    ?DecodeInt@CStr@Ofc@@QEAAXHI@Z; Ofc::CStr::DecodeInt(int,uint)
0x18015b48b  lea     rdi, [r14+1A8h]
0x18015b492  lea     rdx, [rbp+60h+arg_8]
0x18015b496  mov     rcx, rdi
0x18015b499  call    ??4CVarStr@Ofc@@QEAAAEAV01@AEBV01@@Z; Ofc::CVarStr::operator=(Ofc::CVarStr const &)
0x18015b49e  lea     rcx, asc_1801E05D8; " "
0x18015b4a5  call    ?CchWzLen@Ofc@@YAHPEB_W@Z; Ofc::CchWzLen(wchar_t const *)
0x18015b4aa  mov     r8d, eax; int
0x18015b4ad  lea     rdx, asc_1801E05D8; " "
0x18015b4b4  mov     rcx, rdi; this
0x18015b4b7  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015b4bc  mov     rbx, [rbp+60h+arg_18]
0x18015b4c3  mov     eax, [rbx-4]
0x18015b4c6  cdq
0x18015b4c7  sub     eax, edx
0x18015b4c9  sar     eax, 1
0x18015b4cb  mov     r8d, eax; int
0x18015b4ce  mov     rdx, rbx; wchar_t *
0x18015b4d1  mov     rcx, rdi; this
0x18015b4d4  call    ?Append@CStr@Ofc@@IEAAAEAV12@PEB_WH@Z; Ofc::CStr::Append(wchar_t const *,int)
0x18015b4d9  lea     rcx, [r14+178h]; this
0x18015b4e0  lea     rdx, aM19307160C1530; "M 1930 7160 C 1530 4490 3400 1970 5270 "...
0x18015b4e7  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015b4ec  mov     r8, r14
0x18015b4ef  lea     rdx, a010800; "$0 -10800"
0x18015b4f6  lea     rcx, aF0; "f0"
0x18015b4fd  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b502  mov     r8, r14
0x18015b505  lea     rdx, a110800; "$1 -10800"
0x18015b50c  lea     rcx, aF1; "f1"
0x18015b513  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b518  mov     r8, r14
0x18015b51b  lea     rdx, aAtan2F1F0Pi180; "atan2(?f1 ,?f0 )/(pi/180)"
0x18015b522  lea     rcx, aF2; "f2"
0x18015b529  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b52e  mov     r8, r14
0x18015b531  lea     rdx, a10800CosF2Pi18; "10800*cos(?f2 *(pi/180))"
0x18015b538  lea     rcx, aF3; "f3"
0x18015b53f  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b544  mov     r8, r14
0x18015b547  lea     rdx, a10800SinF2Pi18; "10800*sin(?f2 *(pi/180))"
0x18015b54e  lea     rcx, aF4; "f4"
0x18015b555  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b55a  mov     r8, r14
0x18015b55d  lea     rdx, aF310800; "?f3 +10800"
0x18015b564  lea     rcx, aF5; "f5"
0x18015b56b  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b570  mov     r8, r14
0x18015b573  lea     rdx, aF410800; "?f4 +10800"
0x18015b57a  lea     rcx, aF6; "f6"
0x18015b581  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b586  mov     r8, r14
0x18015b589  lea     rdx, a0F5; "$0 -?f5 "
0x18015b590  lea     rcx, aF7; "f7"
0x18015b597  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b59c  mov     r8, r14
0x18015b59f  lea     rdx, a1F6; "$1 -?f6 "
0x18015b5a6  lea     rcx, aF8; "f8"
0x18015b5ad  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b5b2  mov     r8, r14
0x18015b5b5  lea     rdx, aF73; "?f7 /3"
0x18015b5bc  lea     rcx, aF9; "f9"
0x18015b5c3  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b5c8  mov     r8, r14
0x18015b5cb  lea     rdx, aF83; "?f8 /3"
0x18015b5d2  lea     rcx, aF10; "f10"
0x18015b5d9  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b5de  mov     r8, r14
0x18015b5e1  lea     rdx, aF723; "?f7 *2/3"
0x18015b5e8  lea     rcx, aF11; "f11"
0x18015b5ef  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b5f4  mov     r8, r14
0x18015b5f7  lea     rdx, aF823; "?f8 *2/3"
0x18015b5fe  lea     rcx, aF12; "f12"
0x18015b605  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b60a  mov     r8, r14
0x18015b60d  lea     rdx, a0_5; "$0 "
0x18015b614  lea     rcx, aF13; "f13"
0x18015b61b  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b620  mov     r8, r14
0x18015b623  lea     rdx, a1_2; "$1 "
0x18015b62a  lea     rcx, aF14; "f14"
0x18015b631  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b636  mov     r8, r14
0x18015b639  lea     rdx, aF312; "?f3 /12"
0x18015b640  lea     rcx, aF15; "f15"
0x18015b647  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b64c  mov     r8, r14
0x18015b64f  lea     rdx, aF412; "?f4 /12"
0x18015b656  lea     rcx, aF16; "f16"
0x18015b65d  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b662  mov     r8, r14
0x18015b665  lea     rdx, aF9F5F15; "?f9 +?f5 -?f15 "
0x18015b66c  lea     rcx, aF17; "f17"
0x18015b673  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b678  mov     r8, r14
0x18015b67b  lea     rdx, aF10F6F16; "?f10 +?f6 -?f16 "
0x18015b682  lea     rcx, aF18; "f18"
0x18015b689  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b68e  mov     r8, r14
0x18015b691  lea     rdx, aF11F5; "?f11 +?f5 "
0x18015b698  lea     rcx, aF19; "f19"
0x18015b69f  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b6a4  mov     r8, r14
0x18015b6a7  lea     rdx, aF12F6; "?f12 +?f6 "
0x18015b6ae  lea     rcx, aF20; "f20"
0x18015b6b5  call    ?AddEquation@ToOdfShapeGeometryConversion@Art@@CAXPEB_W0AEAV?$TVector@VEquation@ODF@@$0A@$0PPPPPPPP@@Ofc@@@Z; Art::ToOdfShapeGeometryConversion::AddEquation(wchar_t const *,wchar_t const *,Ofc::TVector<ODF::Equation,0,4294967295> &)
0x18015b6ba  mov     word ptr [rsp+160h+var_120], 0
0x18015b6c1  mov     byte ptr [rsp+160h+var_120+2], 0
0x18015b6c6  mov     [rsp+160h+var_118], rsi
0x18015b6cb  mov     [rsp+160h+var_110], rsi
0x18015b6d0  mov     [rsp+160h+var_108], rsi
0x18015b6d5  mov     [rsp+160h+var_100], rsi
0x18015b6da  mov     [rsp+160h+var_F8], rsi
0x18015b6df  mov     [rsp+160h+var_F0], rsi
0x18015b6e4  mov     [rsp+160h+var_E8], rsi
0x18015b6e9  mov     [rbp+60h+var_E0], rsi
0x18015b6ed  mov     [rbp+60h+var_D8], rsi
0x18015b6f1  mov     [rbp+60h+var_D0], rsi
0x18015b6f5  mov     [rbp+60h+var_C8], rsi
0x18015b6f9  mov     [rbp+60h+var_C0], rsi
0x18015b6fd  mov     [rbp+60h+var_B8], rsi
0x18015b701  mov     [rbp+60h+var_B0], rsi
0x18015b705  call    cs:__imp_?FUsingODF_1_4@FeatureGates@Art@@YA_NXZ; Art::FeatureGates::FUsingODF_1_4(void)
0x18015b70b  test    al, al
0x18015b70d  jz      short loc_18015B731
0x18015b70f  lea     rdx, a0_2; "$0"
0x18015b716  lea     rcx, [rsp+160h+var_110]; this
0x18015b71b  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015b720  lea     rdx, a1_4; "$1"
0x18015b727  lea     rcx, [rsp+160h+var_108]; this
0x18015b72c  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015b731  lea     rdx, a01; "$0 $1"
0x18015b738  lea     rcx, [rsp+160h+var_118]; this
0x18015b73d  call    ??4CStr@Ofc@@QEAAAEAV01@PEB_W@Z; Ofc::CStr::operator=(wchar_t const *)
0x18015b742  lea     rcx, [r14+18h]
0x18015b746  lea     rdx, [rsp+160h+var_120]
0x18015b74b  call    ?Push@?$TVector@VHandle@ODF@@$0A@$0PPPPPPPP@@Ofc@@QEAAXAEBVHandle@ODF@@@Z; Ofc::TVector<ODF::Handle,0,4294967295>::Push(ODF::Handle const &)
0x18015b750  nop
0x18015b751  lea     rcx, [rsp+160h+var_120]; this
0x18015b756  call    ??1Handle@ODF@@QEAA@XZ; ODF::Handle::~Handle(void)
0x18015b75b  lea     rcx, [rbx-0Ch]
0x18015b75f  or      ebx, 0FFFFFFFFh
0x18015b762  cmp     dword ptr [rcx+4], 0
0x18015b766  jz      short loc_18015B783
0x18015b768  cmp     dword ptr [rcx], 1
0x18015b76b  jz      short loc_18015B777
0x18015b76d  mov     eax, ebx
0x18015b76f  lock xadd [rcx], eax
0x18015b773  add     eax, ebx
0x18015b775  jnz     short loc_18015B783
0x18015b777  test    rcx, rcx
0x18015b77a  jz      short loc_18015B783
0x18015b77c  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18015b782  nop
0x18015b783  mov     rcx, [rbp+60h+arg_8]
0x18015b787  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18015b78b  cmp     dword ptr [rcx+4], 0
0x18015b78f  jz      short loc_18015B7AC
0x18015b791  cmp     dword ptr [rcx], 1
0x18015b794  jz      short loc_18015B7A0
  ... truncated ...
```
