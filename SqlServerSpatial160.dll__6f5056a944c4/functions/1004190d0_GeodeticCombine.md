# GeodeticCombine

- ea: `0x1004190d0`
- end: `0x100419760`
- name: `GeodeticCombine`
- size: `1680`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x100409aa0`
- `0x10040a580`
- `0x10040acd0`
- `0x10040b270`
- `0x10040d0c0`
- `0x10040d210`
- `0x100416a80`
- `0x100418c60`
- `0x100418d90`
- `0x1004190d0`
- `0x100421170`
- `0x100425d60`
- `0x1004590b0`
- `0x1004591a0`
- `0x100461a80`
- `0x100468a30`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x100419691`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004196d6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100419718`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100419691`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004196d6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100419718`

## pseudocode

```c
// Hidden C++ exception states: #wind=118
__int64 __fastcall GeodeticCombine(unsigned int a1, GeoData *a2, GeoData *a3, double a4, struct GeoDataAllocator *a5)
{
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  int Complement; // ebx
  int Dimension; // ebx
  int v13; // eax
  int v14; // ebx
  double v15; // xmm6_8
  void **v17; // [rsp+48h] [rbp-C0h] BYREF
  double v18; // [rsp+50h] [rbp-B8h]
  __int64 v19; // [rsp+58h] [rbp-B0h]
  void *Block; // [rsp+60h] [rbp-A8h]
  _QWORD v21[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+78h] [rbp-90h]
  void *v23; // [rsp+80h] [rbp-88h]
  _QWORD v24[3]; // [rsp+88h] [rbp-80h] BYREF
  void *v25; // [rsp+A0h] [rbp-68h]
  int v26[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD *v27; // [rsp+B0h] [rbp-58h]
  _QWORD v28[2]; // [rsp+B8h] [rbp-50h] BYREF
  _OWORD v29[4]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v30; // [rsp+108h] [rbp+0h]
  __int64 v31; // [rsp+118h] [rbp+10h]
  void **v32; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v33[24]; // [rsp+130h] [rbp+28h] BYREF
  _BYTE v34[24]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v35[24]; // [rsp+160h] [rbp+58h] BYREF
  _BYTE v36[24]; // [rsp+178h] [rbp+70h] BYREF
  __int128 v37; // [rsp+190h] [rbp+88h]
  __int128 v38; // [rsp+1A0h] [rbp+98h]
  __int128 v39; // [rsp+1B0h] [rbp+A8h]
  __int128 v40; // [rsp+1C0h] [rbp+B8h]
  __int128 v41; // [rsp+1D0h] [rbp+C8h]
  int v42[2]; // [rsp+208h] [rbp+100h] BYREF
  _QWORD *v43; // [rsp+210h] [rbp+108h]
  CGeodeticScannerConstruction *v44; // [rsp+218h] [rbp+110h]
  struct COriginalPoints *v45; // [rsp+220h] [rbp+118h]
  _QWORD v46[2]; // [rsp+228h] [rbp+120h] BYREF
  int v47; // [rsp+238h] [rbp+130h]
  __int64 v48; // [rsp+240h] [rbp+138h]
  __int64 v49; // [rsp+248h] [rbp+140h]
  __int64 v50; // [rsp+250h] [rbp+148h]
  __int64 v51; // [rsp+258h] [rbp+150h]
  int v52; // [rsp+290h] [rbp+188h]
  struct CGeometrySinkD *v53; // [rsp+298h] [rbp+190h]
  _QWORD v54[3]; // [rsp+2A0h] [rbp+198h] BYREF
  void **v55; // [rsp+2B8h] [rbp+1B0h] BYREF
  double v56; // [rsp+2C0h] [rbp+1B8h]
  unsigned int v57; // [rsp+2C8h] [rbp+1C0h]
  _QWORD *v58; // [rsp+2D0h] [rbp+1C8h]
  _QWORD *v59; // [rsp+2D8h] [rbp+1D0h]
  __int64 v60; // [rsp+2E0h] [rbp+1D8h]
  double v61; // [rsp+2E8h] [rbp+1E0h]
  __int16 v62; // [rsp+2F0h] [rbp+1E8h]
  _QWORD v63[81]; // [rsp+2F8h] [rbp+1F0h] BYREF
  _QWORD *v64; // [rsp+580h] [rbp+478h]
  _QWORD *v65; // [rsp+588h] [rbp+480h]
  _BYTE *v66; // [rsp+5D8h] [rbp+4D0h]
  _BYTE *v67; // [rsp+5E0h] [rbp+4D8h]
  __int64 v68; // [rsp+5E8h] [rbp+4E0h]
  __int64 v69; // [rsp+5F0h] [rbp+4E8h]
  unsigned int v70; // [rsp+768h] [rbp+660h]
  _BYTE v71[8]; // [rsp+770h] [rbp+668h] BYREF
  __int64 v72; // [rsp+778h] [rbp+670h]
  _BYTE v73[8]; // [rsp+AA8h] [rbp+9A0h] BYREF
  __int64 v74; // [rsp+AB0h] [rbp+9A8h]
  _QWORD *v75; // [rsp+DE0h] [rbp+CD8h]

  v31 = -2;
  v24[1] = 0;
  v24[0] = &C1DGeometry::`vftable';
  v25 = 0;
  v24[2] = 0;
  v21[1] = 0;
  v21[0] = &C1DGeometry::`vftable';
  v23 = 0;
  v22 = 0;
  v18 = 0.0;
  v17 = &C1DGeometry::`vftable';
  Block = 0;
  v19 = 0;
  WORD6(v30) = 0;
  BYTE14(v30) = 1;
  GeometryDataBuilder::GeometryDataBuilder((GeometryDataBuilder *)&v32, a5, 0);
  CGeodeticScannerConstruction::CGeodeticScannerConstruction((CGeodeticScannerConstruction *)v63, a4);
  v63[0] = &CGeodeticBoolean::`vftable';
  v70 = a1;
  v8 = (*(__int64 (__fastcall **)(_QWORD *))(*v64 + 112LL))(v64);
  CProjectionBoolean::CProjectionBoolean(v71, v8, a1);
  v9 = (*(__int64 (__fastcall **)(_QWORD *))(*v65 + 112LL))(v65);
  CProjectionBoolean::CProjectionBoolean(v73, v9, v70);
  v75 = v21;
  v66 = v71;
  v68 = v72;
  v64[3] = v72;
  v67 = v73;
  v69 = v74;
  v65[3] = v74;
  v63[70] = v24;
  v10 = *(_QWORD *)a3;
  v28[0] = *(_QWORD *)a2;
  v28[1] = v10;
  v43 = v63;
  *(_QWORD *)v42 = &CMetadataEnabledGeodeticOperation::`vftable';
  v44 = (CGeodeticScannerConstruction *)v63;
  v45 = (struct COriginalPoints *)v28;
  *(_QWORD *)v26 = v46;
  v46[0] = &CMetadataFilter::`vftable';
  v46[1] = &v32;
  v47 = 0;
  v49 = 0;
  v48 = 0;
  v51 = 0;
  v50 = 0;
  v52 = 0;
  v53 = (struct CGeometrySinkD *)v46;
  v27 = v54;
  v54[0] = &C2DMetadataResolver::`vftable';
  v54[1] = v28;
  *(_QWORD *)(*((_QWORD *)v66 + 1) + 376LL) = v54;
  *(_QWORD *)(*((_QWORD *)v67 + 1) + 376LL) = v54;
  Complement = CGeodeticScannerConstruction::Set(v44, v45, v53, 1.0, 1);
  if ( Complement >= 0 )
  {
    Complement = InternalPopulate<CGeometrySinkD>((__int64)a2, (__int64)v42, 1u, 0, 0, 0, 1);
    if ( Complement >= 0 )
    {
      Complement = InternalPopulate<CGeometrySinkD>((__int64)a3, (__int64)v42, 1u, 1u, 1, 0, 1);
      if ( Complement >= 0 )
      {
        v29[0] = v37;
        v29[1] = v38;
        v29[2] = v39;
        v29[3] = v40;
        v30 = v41;
        if ( a1 )
          goto LABEL_9;
        _mm_lfence();
        Dimension = GeoData::GetDimension(a3);
        v13 = GeoData::GetDimension(a2);
        _mm_lfence();
        if ( v13 <= Dimension )
          a2 = a3;
        v14 = GeoData::GetDimension(a2);
        if ( v14 <= (int)GeoData::GetDimension((GeoData *)v29) )
        {
LABEL_9:
          Complement = ValidateGeodeticOutput((struct GeoData *)v29, a4, a5, (struct C1DGeometry *)&v17);
          if ( Complement >= 0 )
          {
            _mm_lfence();
            C1DGeometry::Compute((C1DGeometry *)v24);
            C1DGeometry::Compute((C1DGeometry *)v21);
            v56 = 0.0;
            v55 = &C1DBoolean::`vftable';
            v57 = a1;
            v61 = DOUBLE_1_797693134862316e308;
            v58 = v24;
            v59 = v21;
            v60 = 0;
            v62 = 0;
            C1DBoolean::Compute((C1DBoolean *)&v55);
            v26[0] = 0;
            v15 = v56;
            do
            {
              if ( (v18 >= 3.377699720527872e14 || v15 <= 1.125899906842624e15)
                && (v18 <= 1.914029841632461e15 || v15 >= 1.125899906842624e15) )
              {
                break;
              }
              Complement = GetComplement((struct GeoData *)v29, a4, a5, (struct C1DGeometry *)&v17, v26);
            }
            while ( Complement >= 0 );
            v55 = &C1D::`vftable';
          }
        }
        else
        {
          Complement = GetFullGlobe(a5, (struct GeoData *)v29);
        }
      }
    }
  }
  *(_QWORD *)v42 = &CMetadataEnabledGeodeticOperation::`vftable';
  v27 = v54;
  v54[0] = &CMetadataResolver::`vftable';
  CMetadataFilter::~CMetadataFilter((CMetadataFilter *)v46);
  *(_QWORD *)v42 = &IMglGeometrySink::`vftable';
  CGeodeticBoolean::~CGeodeticBoolean((CGeodeticBoolean *)v63);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v36);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v35);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v34);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v33);
  v32 = &IMglGeometrySink::`vftable';
  v17 = &C1DGeometry::`vftable';
  if ( g_SOSHost )
  {
    if ( Block )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(Block);
  }
  Block = 0;
  v19 = 0;
  v17 = &C1D::`vftable';
  v21[0] = &C1DGeometry::`vftable';
  if ( g_SOSHost )
  {
    if ( v23 )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(v23);
  }
  v23 = 0;
  v22 = 0;
  v21[0] = &C1D::`vftable';
  v24[0] = &C1DGeometry::`vftable';
  if ( g_SOSHost )
  {
    if ( v25 )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(v25);
  }
  return (unsigned int)Complement;
}

```

## disassembly

```asm
0x1004190d0  mov     rax, rsp
0x1004190d3  push    rbp
0x1004190d4  push    rsi
0x1004190d5  push    rdi
0x1004190d6  push    r12
0x1004190d8  push    r13
0x1004190da  push    r14
0x1004190dc  push    r15
0x1004190de  lea     rbp, [rax-0D48h]
0x1004190e5  sub     rsp, 0E10h
0x1004190ec  mov     [rbp+0D40h+var_D30], 0FFFFFFFFFFFFFFFEh
0x1004190f4  mov     [rax+8], rbx
0x1004190f8  movaps  xmmword ptr [rax-48h], xmm6
0x1004190fc  movaps  xmmword ptr [rax-58h], xmm7
0x100419100  mov     rax, cs:__security_cookie
0x100419107  xor     rax, rsp
0x10041910a  mov     [rbp+0D40h+var_60], rax
0x100419111  movaps  xmm7, xmm3
0x100419114  mov     r14, r8
0x100419117  mov     rsi, rdx
0x10041911a  mov     r15d, ecx
0x10041911d  mov     rdi, [rbp+0D40h+arg_20]
0x100419124  lea     r13, ??_7C1D@@6B@; const C1D::`vftable'
0x10041912b  mov     [rbp+0D40h+var_DC0], r13
0x10041912f  xorps   xmm6, xmm6
0x100419132  movsd   [rbp+0D40h+var_DB8], xmm6
0x100419137  lea     rax, ??_7C1DGeometry@@6B@; const C1DGeometry::`vftable'
0x10041913e  mov     [rbp+0D40h+var_DC0], rax
0x100419142  xor     r12d, r12d
0x100419145  mov     [rbp+0D40h+var_DA8], r12
0x100419149  mov     [rbp+0D40h+var_DB0], r12
0x10041914d  mov     [rsp+0E40h+var_DE0], r13
0x100419152  movsd   [rsp+0E40h+var_DD8], xmm6
0x100419158  mov     [rsp+0E40h+var_DE0], rax
0x10041915d  mov     [rsp+0E40h+var_DC8], r12
0x100419162  mov     [rsp+0E40h+var_DD0], r12
0x100419167  mov     [rsp+0E40h+var_E00], r13
0x10041916c  movsd   [rsp+0E40h+var_DF8], xmm6
0x100419172  mov     [rsp+0E40h+var_E00], rax
0x100419177  mov     [rsp+0E40h+Block], r12
0x10041917c  mov     [rsp+0E40h+var_DF0], r12
0x100419181  mov     [rbp+0D40h+var_D34], r12w
0x100419186  mov     [rbp+0D40h+var_D32], 1
0x10041918a  xor     r8d, r8d; struct COriginalPoints *
0x10041918d  mov     rdx, rdi; struct GeoDataAllocator *
0x100419190  lea     rcx, [rbp+0D40h+var_D20]; this
0x100419194  call    ??0GeometryDataBuilder@@QEAA@PEAUGeoDataAllocator@@PEAVCOriginalPoints@@@Z; GeometryDataBuilder::GeometryDataBuilder(GeoDataAllocator *,COriginalPoints *)
0x100419199  nop
0x10041919a  movaps  xmm1, xmm7; double
0x10041919d  lea     rcx, [rbp+0D40h+var_B50]; this
0x1004191a4  call    ??0CGeodeticScannerConstruction@@QEAA@N@Z; CGeodeticScannerConstruction::CGeodeticScannerConstruction(double)
0x1004191a9  nop
0x1004191aa  lea     rax, ??_7CGeodeticBoolean@@6B@; const CGeodeticBoolean::`vftable'
0x1004191b1  mov     [rbp+0D40h+var_B50], rax
0x1004191b8  mov     [rbp+0D40h+var_6E0], r15d
0x1004191bf  mov     rcx, [rbp+0D40h+var_8C8]
0x1004191c6  mov     rax, [rcx]
0x1004191c9  call    qword ptr [rax+70h]
0x1004191cc  mov     rdx, rax
0x1004191cf  mov     r8d, r15d
0x1004191d2  lea     rcx, [rbp+0D40h+var_6D8]
0x1004191d9  call    ??0CProjectionBoolean@@QEAA@PEAUIMglGeometrySink@@W4MGL_COMBINE_MODE@@@Z; CProjectionBoolean::CProjectionBoolean(IMglGeometrySink *,MGL_COMBINE_MODE)
0x1004191de  nop
0x1004191df  mov     rcx, [rbp+0D40h+var_8C0]
0x1004191e6  mov     rax, [rcx]
0x1004191e9  call    qword ptr [rax+70h]
0x1004191ec  mov     rdx, rax
0x1004191ef  mov     r8d, [rbp+0D40h+var_6E0]
0x1004191f6  lea     rcx, [rbp+0D40h+var_3A0]
0x1004191fd  call    ??0CProjectionBoolean@@QEAA@PEAUIMglGeometrySink@@W4MGL_COMBINE_MODE@@@Z; CProjectionBoolean::CProjectionBoolean(IMglGeometrySink *,MGL_COMBINE_MODE)
0x100419202  nop
0x100419203  lea     rax, [rsp+0E40h+var_DE0]
0x100419208  mov     [rbp+0D40h+var_68], rax
0x10041920f  lea     rax, [rbp+0D40h+var_6D8]
0x100419216  mov     [rbp+0D40h+var_870], rax
0x10041921d  mov     rcx, [rbp+0D40h+var_6D0]
0x100419224  mov     [rbp+0D40h+var_860], rcx
0x10041922b  mov     rax, [rbp+0D40h+var_8C8]
0x100419232  mov     [rax+18h], rcx
0x100419236  lea     rax, [rbp+0D40h+var_3A0]
0x10041923d  mov     [rbp+0D40h+var_868], rax
0x100419244  mov     rcx, [rbp+0D40h+var_398]
0x10041924b  mov     [rbp+0D40h+var_858], rcx
0x100419252  mov     rax, [rbp+0D40h+var_8C0]
0x100419259  mov     [rax+18h], rcx
0x10041925d  lea     rax, [rbp+0D40h+var_DC0]
0x100419261  mov     [rbp+0D40h+var_920], rax
0x100419268  mov     rcx, [r14]
0x10041926b  mov     rax, [rsi]
0x10041926e  mov     [rbp+0D40h+var_D90], rax
0x100419272  mov     [rbp+0D40h+var_D88], rcx
0x100419276  lea     rdx, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x10041927d  mov     qword ptr [rbp+0D40h+var_C40], rdx
0x100419284  lea     rcx, ??_7CGeometrySinkD@@6B@; const CGeometrySinkD::`vftable'
0x10041928b  mov     qword ptr [rbp+0D40h+var_C40], rcx
0x100419292  lea     rax, ??_7CDecorator@@6B@; const CDecorator::`vftable'
0x100419299  mov     qword ptr [rbp+0D40h+var_C40], rax
0x1004192a0  lea     rax, [rbp+0D40h+var_B50]
0x1004192a7  mov     [rbp+0D40h+var_C38], rax
0x1004192ae  lea     rax, ??_7CMetadataEnabledGeodeticOperation@@6B@; const CMetadataEnabledGeodeticOperation::`vftable'
0x1004192b5  mov     qword ptr [rbp+0D40h+var_C40], rax
0x1004192bc  lea     rax, [rbp+0D40h+var_B50]
0x1004192c3  mov     [rbp+0D40h+var_C30], rax
0x1004192ca  lea     rax, [rbp+0D40h+var_D90]
0x1004192ce  mov     [rbp+0D40h+var_C28], rax
0x1004192d5  lea     rax, [rbp+0D40h+var_C20]
0x1004192dc  mov     qword ptr [rbp+0D40h+var_DA0], rax
0x1004192e0  mov     [rbp+0D40h+var_C20], rdx
0x1004192e7  mov     [rbp+0D40h+var_C20], rcx
0x1004192ee  lea     rax, ??_7CMetadataFilter@@6B@; const CMetadataFilter::`vftable'
0x1004192f5  mov     [rbp+0D40h+var_C20], rax
0x1004192fc  lea     rax, [rbp+0D40h+var_D20]
0x100419300  mov     [rbp+0D40h+var_C18], rax
0x100419307  mov     [rbp+0D40h+var_C10], r12d
0x10041930e  mov     [rbp+0D40h+var_C00], r12
0x100419315  mov     [rbp+0D40h+var_C08], r12
0x10041931c  mov     [rbp+0D40h+var_BF0], r12
0x100419323  mov     [rbp+0D40h+var_BF8], r12
0x10041932a  mov     [rbp+0D40h+var_BB8], r12d
0x100419331  lea     rax, [rbp+0D40h+var_C20]
0x100419338  mov     [rbp+0D40h+var_BB0], rax
0x10041933f  lea     rax, [rbp+0D40h+var_BA8]
0x100419346  mov     [rbp+0D40h+var_D98], rax
0x10041934a  lea     rax, ??_7CMetadataResolver@@6B@; const CMetadataResolver::`vftable'
0x100419351  mov     [rbp+0D40h+var_BA8], rax
0x100419358  lea     rax, ??_7C2DMetadataResolver@@6B@; const C2DMetadataResolver::`vftable'
0x10041935f  mov     [rbp+0D40h+var_BA8], rax
0x100419366  lea     rax, [rbp+0D40h+var_D90]
0x10041936a  mov     [rbp+0D40h+var_BA0], rax
0x100419371  mov     rax, [rbp+0D40h+var_870]
0x100419378  mov     rcx, [rax+8]
0x10041937c  lea     rax, [rbp+0D40h+var_BA8]
0x100419383  mov     [rcx+178h], rax
0x10041938a  mov     rax, [rbp+0D40h+var_868]
0x100419391  mov     rcx, [rax+8]
0x100419395  lea     rax, [rbp+0D40h+var_BA8]
0x10041939c  mov     [rcx+178h], rax
0x1004193a3  mov     byte ptr [rsp+0E40h+var_E20], 1; bool
0x1004193a8  movsd   xmm3, cs:__real@3ff0000000000000; double
0x1004193b0  mov     r8, [rbp+0D40h+var_BB0]; struct CGeometrySinkD *
0x1004193b7  mov     rdx, [rbp+0D40h+var_C28]; struct COriginalPoints *
0x1004193be  mov     rcx, [rbp+0D40h+var_C30]; this
0x1004193c5  call    ?Set@CGeodeticScannerConstruction@@QEAAJPEBVCOriginalPoints@@PEAVCGeometrySinkD@@N_N@Z; CGeodeticScannerConstruction::Set(COriginalPoints const *,CGeometrySinkD *,double,bool)
0x1004193ca  mov     ebx, eax
0x1004193cc  test    eax, eax
0x1004193ce  js      loc_1004195C3
0x1004193d4  mov     [rsp+0E40h+var_E10], 1; char
0x1004193d9  mov     [rsp+0E40h+var_E18], r12b; char
0x1004193de  mov     byte ptr [rsp+0E40h+var_E20], r12b; char
0x1004193e3  xor     r9d, r9d
0x1004193e6  lea     r8d, [r12+1]
0x1004193eb  lea     rdx, [rbp+0D40h+var_C40]; int
0x1004193f2  mov     rcx, rsi; int
0x1004193f5  call    ??$InternalPopulate@VCGeometrySinkD@@@@YAJAEBUGeoData@@PEAVCGeometrySinkD@@W4MGL_WINDING_RULE@@_NE33@Z; InternalPopulate<CGeometrySinkD>(GeoData const &,CGeometrySinkD *,MGL_WINDING_RULE,bool,uchar,bool,bool)
0x1004193fa  mov     ebx, eax
0x1004193fc  test    eax, eax
0x1004193fe  js      loc_1004195C3
0x100419404  mov     [rsp+0E40h+var_E10], 1; char
0x100419409  mov     [rsp+0E40h+var_E18], r12b; char
0x10041940e  mov     byte ptr [rsp+0E40h+var_E20], 1; char
0x100419413  mov     r9b, 1
0x100419416  lea     r8d, [r12+1]
0x10041941b  lea     rdx, [rbp+0D40h+var_C40]; int
0x100419422  mov     rcx, r14; int
0x100419425  call    ??$InternalPopulate@VCGeometrySinkD@@@@YAJAEBUGeoData@@PEAVCGeometrySinkD@@W4MGL_WINDING_RULE@@_NE33@Z; InternalPopulate<CGeometrySinkD>(GeoData const &,CGeometrySinkD *,MGL_WINDING_RULE,bool,uchar,bool,bool)
0x10041942a  mov     ebx, eax
0x10041942c  test    eax, eax
0x10041942e  js      loc_1004195C3
0x100419434  movups  xmm0, [rbp+0D40h+var_CB8]
0x10041943b  movaps  [rbp+0D40h+var_D80], xmm0
0x10041943f  movups  xmm1, [rbp+0D40h+var_CA8]
0x100419446  movaps  [rbp+0D40h+var_D70], xmm1
0x10041944a  movups  xmm0, [rbp+0D40h+var_C98]
0x100419451  movaps  [rbp+0D40h+var_D60], xmm0
0x100419455  movups  xmm1, [rbp+0D40h+var_C88]
0x10041945c  movaps  [rbp+0D40h+var_D50], xmm1
0x100419460  movups  xmm0, [rbp+0D40h+var_C78]
0x100419467  movaps  xmmword ptr [rbp+0], xmm0
0x10041946b  test    r15d, r15d
0x10041946e  jnz     short loc_1004194B9
0x100419470  lfence
0x100419473  mov     rcx, r14; this
0x100419476  call    ?GetDimension@GeoData@@QEBAHXZ; GeoData::GetDimension(void)
0x10041947b  mov     ebx, eax
0x10041947d  mov     rcx, rsi; this
0x100419480  call    ?GetDimension@GeoData@@QEBAHXZ; GeoData::GetDimension(void)
0x100419485  lfence
0x100419488  cmp     eax, ebx
0x10041948a  jg      short loc_10041948F
0x10041948c  mov     rsi, r14
0x10041948f  mov     rcx, rsi; this
0x100419492  call    ?GetDimension@GeoData@@QEBAHXZ; GeoData::GetDimension(void)
0x100419497  mov     ebx, eax
0x100419499  lea     rcx, [rbp+0D40h+var_D80]; this
0x10041949d  call    ?GetDimension@GeoData@@QEBAHXZ; GeoData::GetDimension(void)
0x1004194a2  cmp     ebx, eax
0x1004194a4  jle     short loc_1004194B9
0x1004194a6  lea     rdx, [rbp+0D40h+var_D80]; struct GeoData *
0x1004194aa  mov     rcx, rdi; struct GeoDataAllocator *
0x1004194ad  call    ?GetFullGlobe@@YAJPEAUGeoDataAllocator@@AEAUGeoData@@@Z; GetFullGlobe(GeoDataAllocator *,GeoData &)
0x1004194b2  mov     ebx, eax
0x1004194b4  jmp     loc_1004195C3
0x1004194b9  lea     r9, [rsp+0E40h+var_E00]; struct C1DGeometry *
0x1004194be  mov     r8, rdi; struct GeoDataAllocator *
0x1004194c1  movaps  xmm1, xmm7; double
0x1004194c4  lea     rcx, [rbp+0D40h+var_D80]; struct GeoData *
0x1004194c8  call    ?ValidateGeodeticOutput@@YAJAEAUGeoData@@NPEAUGeoDataAllocator@@PEAVC1DGeometry@@@Z; ValidateGeodeticOutput(GeoData &,double,GeoDataAllocator *,C1DGeometry *)
0x1004194cd  mov     ebx, eax
0x1004194cf  test    eax, eax
0x1004194d1  js      loc_1004195C3
0x1004194d7  lfence
0x1004194da  lea     rcx, [rbp+0D40h+var_DC0]; this
0x1004194de  call    ?Compute@C1DGeometry@@UEAAXXZ; C1DGeometry::Compute(void)
0x1004194e3  lea     rcx, [rsp+0E40h+var_DE0]; this
0x1004194e8  call    ?Compute@C1DGeometry@@UEAAXXZ; C1DGeometry::Compute(void)
0x1004194ed  mov     [rbp+0D40h+var_B90], r13
0x1004194f4  movsd   [rbp+0D40h+var_B88], xmm6
0x1004194fc  lea     rsi, ??_7C1DBoolean@@6B@; const C1DBoolean::`vftable'
0x100419503  mov     [rbp+0D40h+var_B90], rsi
0x10041950a  mov     [rbp+0D40h+var_B80], r15d
0x100419511  movsd   xmm0, cs:__real@7fefffffffffffff
0x100419519  movsd   [rbp+0D40h+var_B60], xmm0
0x100419521  lea     rax, [rbp+0D40h+var_DC0]
0x100419525  mov     [rbp+0D40h+var_B78], rax
0x10041952c  lea     rax, [rsp+0E40h+var_DE0]
0x100419531  mov     [rbp+0D40h+var_B70], rax
0x100419538  mov     [rbp+0D40h+var_B68], r12
0x10041953f  mov     [rbp+0D40h+var_B58], 0
0x100419548  lea     rcx, [rbp+0D40h+var_B90]; this
0x10041954f  call    ?Compute@C1DBoolean@@UEAAXXZ; C1DBoolean::Compute(void)
0x100419554  mov     [rbp+0D40h+var_DA0], r12d
0x100419558  movsd   xmm6, [rbp+0D40h+var_B88]
0x100419560  movsd   xmm0, cs:__real@42f3333333333333
0x100419568  movsd   xmm1, cs:__real@4310000000000000
0x100419570  movsd   xmm2, [rsp+0E40h+var_DF8]
0x100419576  comisd  xmm0, xmm2
0x10041957a  jbe     short loc_100419582
0x10041957c  comisd  xmm6, xmm1
0x100419580  ja      short loc_100419592
0x100419582  comisd  xmm2, cs:__real@431b333333333333
0x10041958a  jbe     short loc_1004195B5
0x10041958c  comisd  xmm1, xmm6
0x100419590  jbe     short loc_1004195B5
0x100419592  lea     rax, [rbp+0D40h+var_DA0]
0x100419596  mov     [rsp+0E40h+var_E20], rax; int *
0x10041959b  lea     r9, [rsp+0E40h+var_E00]; struct C1DGeometry *
0x1004195a0  mov     r8, rdi; struct GeoDataAllocator *
0x1004195a3  movaps  xmm1, xmm7; double
0x1004195a6  lea     rcx, [rbp+0D40h+var_D80]; struct GeoData *
0x1004195aa  call    ?GetComplement@@YAJPEAUGeoData@@NPEAUGeoDataAllocator@@PEAVC1DGeometry@@AEAH@Z; GetComplement(GeoData *,double,GeoDataAllocator *,C1DGeometry *,int &)
0x1004195af  mov     ebx, eax
0x1004195b1  test    eax, eax
0x1004195b3  jns     short loc_100419560
0x1004195b5  mov     [rbp+0D40h+var_B90], rsi
0x1004195bc  mov     [rbp+0D40h+var_B90], r13
0x1004195c3  lea     rax, ??_7CMetadataEnabledGeodeticOperation@@6B@; const CMetadataEnabledGeodeticOperation::`vftable'
0x1004195ca  mov     qword ptr [rbp+0D40h+var_C40], rax
0x1004195d1  lea     rax, [rbp+0D40h+var_BA8]
0x1004195d8  mov     [rbp+0D40h+var_D98], rax
0x1004195dc  lea     rax, ??_7C2DMetadataResolver@@6B@; const C2DMetadataResolver::`vftable'
0x1004195e3  mov     [rbp+0D40h+var_BA8], rax
0x1004195ea  lea     rax, ??_7CMetadataResolver@@6B@; const CMetadataResolver::`vftable'
0x1004195f1  mov     [rbp+0D40h+var_BA8], rax
0x1004195f8  lea     rcx, [rbp+0D40h+var_C20]; this
0x1004195ff  call    ??1CMetadataFilter@@UEAA@XZ; CMetadataFilter::~CMetadataFilter(void)
0x100419604  nop
0x100419605  lea     rax, ??_7CDecorator@@6B@; const CDecorator::`vftable'
0x10041960c  mov     qword ptr [rbp+0D40h+var_C40], rax
0x100419613  lea     rdi, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x10041961a  mov     qword ptr [rbp+0D40h+var_C40], rdi
0x100419621  lea     rcx, [rbp+0D40h+var_B50]; this
0x100419628  call    ??1CGeodeticBoolean@@UEAA@XZ; CGeodeticBoolean::~CGeodeticBoolean(void)
0x10041962d  nop
0x10041962e  lea     rcx, [rbp+0D40h+var_CD0]
0x100419632  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100419637  nop
0x100419638  lea     rcx, [rbp+0D40h+var_CE8]
0x10041963c  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100419641  nop
0x100419642  lea     rcx, [rbp+0D40h+var_D00]
0x100419646  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10041964b  nop
0x10041964c  lea     rcx, [rbp+0D40h+var_D18]
0x100419650  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100419655  nop
0x100419656  mov     [rbp+0D40h+var_D20], rdi
0x10041965a  lea     rdi, ??_7C1DGeometry@@6B@; const C1DGeometry::`vftable'
0x100419661  mov     [rsp+0E40h+var_E00], rdi
0x100419666  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10041966e  jz      short loc_10041968C
0x100419670  mov     rdx, [rsp+0E40h+Block]
0x100419675  test    rdx, rdx
0x100419678  jz      short loc_100419697
0x10041967a  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100419681  mov     rax, [rcx]
0x100419684  call    qword ptr [rax+80h]
0x10041968a  jmp     short loc_100419697
0x10041968c  mov     rcx, [rsp+0E40h+Block]; Block
0x100419691  call    cs:__imp_free
0x100419697  mov     [rsp+0E40h+Block], r12
  ... truncated ...
```
