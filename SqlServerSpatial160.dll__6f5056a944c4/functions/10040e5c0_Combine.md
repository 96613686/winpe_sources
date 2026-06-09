# Combine

- ea: `0x10040e5c0`
- end: `0x10040ee70`
- name: `Combine`
- size: `2224`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x100401be0`
- `0x100403710`
- `0x10040d210`
- `0x10040dc20`
- `0x10040e5c0`
- `0x10041f9f0`
- `0x100421170`
- `0x100422970`
- `0x100423450`
- `0x100424ba0`
- `0x100425400`
- `0x10042d650`
- `0x100432b80`
- `0x10043b830`
- `0x100445370`
- `0x100468a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=89
__int64 __fastcall Combine(int a1, const struct GeoData *a2, const struct GeoData *a3, struct GeoDataAllocator *a4)
{
  __int64 v8; // rdx
  int v9; // edi
  __int64 v10; // r8
  __int64 v11; // r9
  bool v12; // dl
  int v14; // ebx
  _QWORD v15[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B8h]
  double v18; // [rsp+58h] [rbp-B0h] BYREF
  double v19; // [rsp+60h] [rbp-A8h]
  double v20; // [rsp+68h] [rbp-A0h]
  double v21; // [rsp+70h] [rbp-98h]
  unsigned int v22[2]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v23[2]; // [rsp+80h] [rbp-88h] BYREF
  double v24; // [rsp+90h] [rbp-78h] BYREF
  double v25; // [rsp+98h] [rbp-70h]
  double v26; // [rsp+A0h] [rbp-68h]
  double v27; // [rsp+A8h] [rbp-60h]
  double v28; // [rsp+B0h] [rbp-58h] BYREF
  double v29; // [rsp+B8h] [rbp-50h]
  double v30; // [rsp+C0h] [rbp-48h]
  double v31; // [rsp+C8h] [rbp-40h]
  __int64 v32; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v33[24]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v34[24]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v35[24]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v36[24]; // [rsp+128h] [rbp+20h] BYREF
  __int128 v37; // [rsp+140h] [rbp+38h]
  __int128 v38; // [rsp+150h] [rbp+48h]
  __int128 v39; // [rsp+160h] [rbp+58h]
  __int128 v40; // [rsp+170h] [rbp+68h]
  __int128 v41; // [rsp+180h] [rbp+78h]
  int v42; // [rsp+198h] [rbp+90h]
  __int64 v43; // [rsp+1B8h] [rbp+B0h]
  _QWORD *v44; // [rsp+1C0h] [rbp+B8h]
  _QWORD *v45; // [rsp+1C8h] [rbp+C0h]
  int v46[4]; // [rsp+1D8h] [rbp+D0h] BYREF
  __int128 v47; // [rsp+1E8h] [rbp+E0h]
  __int128 v48; // [rsp+1F8h] [rbp+F0h]
  __int128 v49; // [rsp+208h] [rbp+100h]
  __int128 v50; // [rsp+218h] [rbp+110h]
  int v51[4]; // [rsp+228h] [rbp+120h] BYREF
  __int128 v52; // [rsp+238h] [rbp+130h]
  __int128 v53; // [rsp+248h] [rbp+140h]
  __int128 v54; // [rsp+258h] [rbp+150h]
  __int128 v55; // [rsp+268h] [rbp+160h]
  _OWORD v56[5]; // [rsp+278h] [rbp+170h] BYREF
  void **v57; // [rsp+2C8h] [rbp+1C0h] BYREF
  _BYTE v58[48]; // [rsp+2D0h] [rbp+1C8h] BYREF
  _BYTE v59[8]; // [rsp+300h] [rbp+1F8h] BYREF
  _QWORD *v60; // [rsp+308h] [rbp+200h]
  double v61; // [rsp+320h] [rbp+218h]
  double v62; // [rsp+328h] [rbp+220h]
  _BYTE v63[64]; // [rsp+338h] [rbp+230h] BYREF
  _QWORD *v64; // [rsp+378h] [rbp+270h]
  _QWORD v65[71]; // [rsp+388h] [rbp+280h] BYREF
  int v66; // [rsp+5C0h] [rbp+4B8h]
  _QWORD v67[18]; // [rsp+5C8h] [rbp+4C0h] BYREF
  char v68; // [rsp+658h] [rbp+550h]
  _QWORD v69[2]; // [rsp+660h] [rbp+558h] BYREF
  double v70; // [rsp+670h] [rbp+568h]
  _QWORD *v71; // [rsp+688h] [rbp+580h]
  _QWORD v72[2]; // [rsp+690h] [rbp+588h] BYREF
  char v73; // [rsp+6A0h] [rbp+598h]
  __int64 v74; // [rsp+6A8h] [rbp+5A0h]
  __int64 v75; // [rsp+6B0h] [rbp+5A8h]
  char v76; // [rsp+6C0h] [rbp+5B8h]
  __int64 v77; // [rsp+6C8h] [rbp+5C0h]
  __int64 v78; // [rsp+6D0h] [rbp+5C8h]
  char v79; // [rsp+6D8h] [rbp+5D0h]
  _QWORD *v80; // [rsp+6E0h] [rbp+5D8h]
  unsigned int v81; // [rsp+6E8h] [rbp+5E0h]
  char v82; // [rsp+6ECh] [rbp+5E4h]

  v43 = -2;
  v8 = *(_QWORD *)a3;
  v23[0] = *(_QWORD *)a2;
  v23[1] = v8;
  GeometryDataBuilder::GeometryDataBuilder((GeometryDataBuilder *)&v32, a4, (struct COriginalPoints *)v23);
  v15[0] = &C2DMetadataResolver::`vftable';
  v15[1] = v23;
  CScannerModuleD::CScannerModuleD((CScannerModuleD *)&v57, (struct CScanner *)v65);
  v57 = &CStructuredBooleanModule::`vftable';
  *(_QWORD *)v22 = v65;
  C2ShapesProcessor::C2ShapesProcessor((C2ShapesProcessor *)v65, 0, 0);
  v65[0] = &CBoolean::`vftable';
  v65[70] = v67;
  v66 = a1;
  v44 = v67;
  CReconstructor::CReconstructor((CReconstructor *)v67, (struct IMglGeometrySink *)v59, 0, 0);
  v67[0] = &CStructuredReconstructor::`vftable';
  v68 = 0;
  v45 = v69;
  v69[1] = v58;
  v70 = 0.0;
  v69[0] = &CPlanarFlattener::`vftable';
  v71 = v72;
  v16 = (__int64)v72;
  v72[1] = &v32;
  v72[0] = &CArcReconstructor::`vftable';
  v73 = 0;
  v75 = 0;
  v74 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0x80000000;
  v82 = 0;
  v60 = v72;
  v64 = v72;
  v65[47] = v15;
  v30 = DOUBLE_1_797693134862316e308;
  v28 = DOUBLE_1_797693134862316e308;
  v31 = DOUBLE_2_225073858507201eN308;
  v29 = DOUBLE_2_225073858507201eN308;
  v26 = DOUBLE_1_797693134862316e308;
  v24 = DOUBLE_1_797693134862316e308;
  v27 = DOUBLE_2_225073858507201eN308;
  v25 = DOUBLE_2_225073858507201eN308;
  *(_OWORD *)v46 = *(_OWORD *)a2;
  v47 = *((_OWORD *)a2 + 1);
  v48 = *((_OWORD *)a2 + 2);
  v49 = *((_OWORD *)a2 + 3);
  v50 = *((_OWORD *)a2 + 4);
  v9 = ComputeBounds((int)v46);
  if ( v9 < 0 )
    goto LABEL_27;
  *(_OWORD *)v51 = *(_OWORD *)a3;
  v52 = *((_OWORD *)a3 + 1);
  v53 = *((_OWORD *)a3 + 2);
  v54 = *((_OWORD *)a3 + 3);
  v55 = *((_OWORD *)a3 + 4);
  v9 = ComputeBounds((int)v51);
  if ( v9 < 0 )
    goto LABEL_27;
  if ( (a1 != 1 || (unsigned __int8)CMglRect<double>::Intersects(&v28, &v24))
    && (v28 <= v29 && v30 <= v31 || v24 <= v25 && v26 <= v27) )
  {
    v18 = v28;
    v19 = v29;
    v20 = v30;
    v21 = v31;
    if ( v24 <= v25 && v26 <= v27 )
    {
      if ( v28 > v29 || v30 > v31 )
      {
        v18 = v24;
        v19 = v25;
        v20 = v26;
LABEL_23:
        v21 = v27;
        goto LABEL_24;
      }
      if ( v28 > v24 )
        v18 = v24;
      if ( v30 > v26 )
        v20 = v26;
      if ( v25 > v29 )
        v19 = v25;
      if ( v27 > v31 )
        goto LABEL_23;
    }
LABEL_24:
    v9 = CWorkspaceTransform::SetWithScaleFactor(v58, &v18);
    if ( v9 < 0
      || (v70 = fmin(v61, v62),
          v22[0] = 3,
          v65[63] = v63,
          v67[7] = v63,
          v9 = CAttributes::RegisterAttributes((CAttributes *)v63, 1u, v22),
          v9 < 0)
      || (v80 = v23,
          v9 = PopulateAsUnion(a2, (struct CGeometrySinkD *)v69, 0, v12, (struct C2DMetadataResolver *)v15, 0),
          v9 < 0) )
    {
LABEL_27:
      _mm_lfence();
      CStructuredBooleanModule::~CStructuredBooleanModule((CStructuredBooleanModule *)&v57);
      v15[0] = &CMetadataResolver::`vftable';
      ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v36);
      ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v35);
      ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v34);
      ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v33);
      return (unsigned int)v9;
    }
    v14 = PopulateAsUnion(a3, (struct CGeometrySinkD *)v69, 1, 1, (struct C2DMetadataResolver *)v15, 0);
    if ( v14 < 0 )
      goto LABEL_35;
    v56[0] = v37;
    v56[1] = v38;
    v56[2] = v39;
    v56[3] = v40;
    v56[4] = v41;
    v14 = ValidateOutput((struct GeoData *)v56, a4);
    if ( v14 < 0 )
      goto LABEL_35;
LABEL_36:
    CStructuredBooleanModule::~CStructuredBooleanModule((CStructuredBooleanModule *)&v57);
    v15[0] = &CMetadataResolver::`vftable';
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v36);
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v35);
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v34);
    ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v33);
    return (unsigned int)v14;
  }
  v42 = 1;
  v16 = -1;
  LOBYTE(v17) = 7;
  v14 = ArrayOverPages<Shape,SOS_Or_CRT_Allocator<Shape>>::Add(v35, &v16, v10, v11);
  if ( v14 >= 0 )
  {
    v14 = GeometryDataBuilder::EndGeometry((GeometryDataBuilder *)&v32, 1);
    if ( v14 >= 0 )
      goto LABEL_36;
  }
LABEL_35:
  _mm_lfence();
  CStructuredBooleanModule::~CStructuredBooleanModule((CStructuredBooleanModule *)&v57);
  v15[0] = &CMetadataResolver::`vftable';
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v36);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v35);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v34);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v33);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x10040e5c0  mov     rax, rsp
0x10040e5c3  push    rbp
0x10040e5c4  push    rsi
0x10040e5c5  push    rdi
0x10040e5c6  push    r12
0x10040e5c8  push    r13
0x10040e5ca  push    r14
0x10040e5cc  push    r15
0x10040e5ce  lea     rbp, [rax-658h]
0x10040e5d5  sub     rsp, 720h
0x10040e5dc  mov     [rbp+650h+var_5A0], 0FFFFFFFFFFFFFFFEh
0x10040e5e7  mov     [rax+8], rbx
0x10040e5eb  movaps  xmmword ptr [rax-48h], xmm6
0x10040e5ef  movaps  xmmword ptr [rax-58h], xmm7
0x10040e5f3  mov     rax, cs:__security_cookie
0x10040e5fa  xor     rax, rsp
0x10040e5fd  mov     [rbp+650h+var_60], rax
0x10040e604  mov     r15, r9
0x10040e607  mov     rbx, r8
0x10040e60a  mov     r14, rdx
0x10040e60d  mov     esi, ecx
0x10040e60f  mov     rdx, [r8]
0x10040e612  mov     rax, [r14]
0x10040e615  mov     [rsp+750h+var_6D8], rax
0x10040e61a  mov     [rbp+650h+var_6D0], rdx
0x10040e61e  lea     r8, [rsp+750h+var_6D8]; struct COriginalPoints *
0x10040e623  mov     rdx, r9; struct GeoDataAllocator *
0x10040e626  lea     rcx, [rbp+650h+var_680]; this
0x10040e62a  call    ??0GeometryDataBuilder@@QEAA@PEAUGeoDataAllocator@@PEAVCOriginalPoints@@@Z; GeometryDataBuilder::GeometryDataBuilder(GeoDataAllocator *,COriginalPoints *)
0x10040e62f  nop
0x10040e630  lea     r13, ??_7CMetadataResolver@@6B@; const CMetadataResolver::`vftable'
0x10040e637  mov     [rsp+750h+var_720], r13
0x10040e63c  lea     rax, ??_7C2DMetadataResolver@@6B@; const C2DMetadataResolver::`vftable'
0x10040e643  mov     [rsp+750h+var_720], rax
0x10040e648  lea     rax, [rsp+750h+var_6D8]
0x10040e64d  mov     [rsp+750h+var_718], rax
0x10040e652  lea     rdx, [rbp+650h+var_3D0]; struct CScanner *
0x10040e659  lea     rcx, [rbp+650h+var_490]; this
0x10040e660  call    ??0CScannerModuleD@@QEAA@AEAVCScanner@@@Z; CScannerModuleD::CScannerModuleD(CScanner &)
0x10040e665  nop
0x10040e666  lea     rax, ??_7CStructuredBooleanModule@@6B@; const CStructuredBooleanModule::`vftable'
0x10040e66d  mov     [rbp+650h+var_490], rax
0x10040e674  lea     rax, [rbp+650h+var_3D0]
0x10040e67b  mov     qword ptr [rsp+750h+var_6E0], rax
0x10040e680  xor     r8d, r8d; bool
0x10040e683  xor     edx, edx; bool
0x10040e685  lea     rcx, [rbp+650h+var_3D0]; this
0x10040e68c  call    ??0C2ShapesProcessor@@QEAA@_N0@Z; C2ShapesProcessor::C2ShapesProcessor(bool,bool)
0x10040e691  nop
0x10040e692  lea     rax, ??_7CBoolean@@6B@; const CBoolean::`vftable'
0x10040e699  mov     [rbp+650h+var_3D0], rax
0x10040e6a0  lea     rax, [rbp+650h+var_190]
0x10040e6a7  mov     [rbp+650h+var_1A0], rax
0x10040e6ae  mov     [rbp+650h+var_198], esi
0x10040e6b4  lea     rax, [rbp+650h+var_190]
0x10040e6bb  mov     [rbp+650h+var_598], rax
0x10040e6c2  xor     r9d, r9d; bool
0x10040e6c5  xor     r8d, r8d; bool
0x10040e6c8  lea     rdx, [rbp+650h+var_458]; struct IMglGeometrySink *
0x10040e6cf  lea     rcx, [rbp+650h+var_190]; this
0x10040e6d6  call    ??0CReconstructor@@QEAA@PEAUIMglGeometrySink@@_N1@Z; CReconstructor::CReconstructor(IMglGeometrySink *,bool,bool)
0x10040e6db  nop
0x10040e6dc  lea     rax, ??_7CStructuredReconstructor@@6B@; const CStructuredReconstructor::`vftable'
0x10040e6e3  mov     [rbp+650h+var_190], rax
0x10040e6ea  mov     [rbp+650h+var_100], 0
0x10040e6f1  lea     rax, [rbp+650h+var_F8]
0x10040e6f8  mov     [rbp+650h+var_590], rax
0x10040e6ff  lea     r12, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x10040e706  mov     [rbp+650h+var_F8], r12
0x10040e70d  lea     rdx, ??_7CGeometrySinkD@@6B@; const CGeometrySinkD::`vftable'
0x10040e714  mov     [rbp+650h+var_F8], rdx
0x10040e71b  lea     rcx, ??_7CDecorator@@6B@; const CDecorator::`vftable'
0x10040e722  mov     [rbp+650h+var_F8], rcx
0x10040e729  lea     rax, [rbp+650h+var_488]
0x10040e730  mov     [rbp+650h+var_F0], rax
0x10040e737  lea     rax, ??_7CFlattener@@6B@; const CFlattener::`vftable'
0x10040e73e  mov     [rbp+650h+var_F8], rax
0x10040e745  xorps   xmm0, xmm0
0x10040e748  movsd   [rbp+650h+var_E8], xmm0
0x10040e750  lea     rax, ??_7CPlanarFlattener@@6B@; const CPlanarFlattener::`vftable'
0x10040e757  mov     [rbp+650h+var_F8], rax
0x10040e75e  lea     rax, [rbp+650h+var_C8]
0x10040e765  mov     [rbp+650h+var_D0], rax
0x10040e76c  lea     rax, [rbp+650h+var_C8]
0x10040e773  mov     [rsp+750h+var_710], rax
0x10040e778  mov     [rbp+650h+var_C8], r12
0x10040e77f  mov     [rbp+650h+var_C8], rdx
0x10040e786  mov     [rbp+650h+var_C8], rcx
0x10040e78d  lea     rax, [rbp+650h+var_680]
0x10040e791  mov     [rbp+650h+var_C0], rax
0x10040e798  lea     rax, ??_7CArcReconstructor@@6B@; const CArcReconstructor::`vftable'
0x10040e79f  mov     [rbp+650h+var_C8], rax
0x10040e7a6  mov     [rbp+650h+var_B8], 0
0x10040e7ad  xor     eax, eax
0x10040e7af  mov     [rbp+650h+var_A8], rax
0x10040e7b6  mov     [rbp+650h+var_B0], rax
0x10040e7bd  mov     [rbp+650h+var_98], al
0x10040e7c3  mov     [rbp+650h+var_90], rax
0x10040e7ca  mov     [rbp+650h+var_88], rax
0x10040e7d1  mov     [rbp+650h+var_80], al
0x10040e7d7  mov     [rbp+650h+var_78], rax
0x10040e7de  mov     [rbp+650h+var_70], 80000000h
0x10040e7e8  mov     [rbp+650h+var_6C], al
0x10040e7ee  lea     rax, [rbp+650h+var_C8]
0x10040e7f5  mov     [rbp+650h+var_450], rax
0x10040e7fc  lea     rax, [rbp+650h+var_C8]
0x10040e803  mov     [rbp+650h+var_3E0], rax
0x10040e80a  lea     rax, [rsp+750h+var_720]
0x10040e80f  mov     [rbp+650h+var_258], rax
0x10040e816  movsd   xmm1, cs:__real@7fefffffffffffff
0x10040e81e  movsd   [rbp+650h+var_698], xmm1
0x10040e823  movsd   [rbp+650h+var_6A8], xmm1
0x10040e828  movsd   xmm0, cs:__real@0010000000000000
0x10040e830  movsd   [rbp+650h+var_690], xmm0
0x10040e835  movsd   [rbp+650h+var_6A0], xmm0
0x10040e83a  movsd   [rbp+650h+var_6B8], xmm1
0x10040e83f  movsd   [rbp+650h+var_6C8], xmm1
0x10040e844  movsd   [rbp+650h+var_6B0], xmm0
0x10040e849  movsd   [rbp+650h+var_6C0], xmm0
0x10040e84e  movups  xmm0, xmmword ptr [r14]
0x10040e852  movaps  xmmword ptr [rbp+650h+var_580], xmm0
0x10040e859  movups  xmm1, xmmword ptr [r14+10h]
0x10040e85e  movaps  [rbp+650h+var_570], xmm1
0x10040e865  movups  xmm0, xmmword ptr [r14+20h]
0x10040e86a  movaps  [rbp+650h+var_560], xmm0
0x10040e871  movups  xmm1, xmmword ptr [r14+30h]
0x10040e876  movaps  [rbp+650h+var_550], xmm1
0x10040e87d  movups  xmm0, xmmword ptr [r14+40h]
0x10040e882  movaps  [rbp+650h+var_540], xmm0
0x10040e889  lea     rdx, [rbp+650h+var_6A8]
0x10040e88d  lea     rcx, [rbp+650h+var_580]; int
0x10040e894  call    ?ComputeBounds@@YAJUGeoData@@PEAV?$CMglRect@N@@@Z; ComputeBounds(GeoData,CMglRect<double> *)
0x10040e899  mov     edi, eax
0x10040e89b  test    eax, eax
0x10040e89d  jns     short loc_10040E8EF
0x10040e89f  lfence
0x10040e8a2  lea     rcx, [rbp+650h+var_490]; this
0x10040e8a9  call    ??1CStructuredBooleanModule@@UEAA@XZ; CStructuredBooleanModule::~CStructuredBooleanModule(void)
0x10040e8ae  nop
0x10040e8af  lea     rax, ??_7C2DMetadataResolver@@6B@; const C2DMetadataResolver::`vftable'
0x10040e8b6  mov     [rsp+750h+var_720], rax
0x10040e8bb  mov     [rsp+750h+var_720], r13
0x10040e8c0  lea     rcx, [rbp+650h+var_630]
0x10040e8c4  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040e8c9  nop
0x10040e8ca  lea     rcx, [rbp+650h+var_648]
0x10040e8ce  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040e8d3  nop
0x10040e8d4  lea     rcx, [rbp+650h+var_660]
0x10040e8d8  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040e8dd  nop
0x10040e8de  lea     rcx, [rbp+650h+var_678]
0x10040e8e2  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040e8e7  nop
0x10040e8e8  mov     eax, edi
0x10040e8ea  jmp     loc_10040EE38
0x10040e8ef  movups  xmm0, xmmword ptr [rbx]
0x10040e8f2  movaps  xmmword ptr [rbp+650h+var_530], xmm0
0x10040e8f9  movups  xmm1, xmmword ptr [rbx+10h]
0x10040e8fd  movaps  [rbp+650h+var_520], xmm1
0x10040e904  movups  xmm0, xmmword ptr [rbx+20h]
0x10040e908  movaps  [rbp+650h+var_510], xmm0
0x10040e90f  movups  xmm1, xmmword ptr [rbx+30h]
0x10040e913  movaps  [rbp+650h+var_500], xmm1
0x10040e91a  movups  xmm0, xmmword ptr [rbx+40h]
0x10040e91e  movaps  [rbp+650h+var_4F0], xmm0
0x10040e925  lea     rdx, [rbp+650h+var_6C8]
0x10040e929  lea     rcx, [rbp+650h+var_530]; int
0x10040e930  call    ?ComputeBounds@@YAJUGeoData@@PEAV?$CMglRect@N@@@Z; ComputeBounds(GeoData,CMglRect<double> *)
0x10040e935  mov     edi, eax
0x10040e937  test    eax, eax
0x10040e939  jns     short loc_10040E98B
0x10040e93b  lfence
0x10040e93e  lea     rcx, [rbp+650h+var_490]; this
0x10040e945  call    ??1CStructuredBooleanModule@@UEAA@XZ; CStructuredBooleanModule::~CStructuredBooleanModule(void)
0x10040e94a  nop
0x10040e94b  lea     rax, ??_7C2DMetadataResolver@@6B@; const C2DMetadataResolver::`vftable'
0x10040e952  mov     [rsp+750h+var_720], rax
0x10040e957  mov     [rsp+750h+var_720], r13
0x10040e95c  lea     rcx, [rbp+650h+var_630]
0x10040e960  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040e965  nop
0x10040e966  lea     rcx, [rbp+650h+var_648]
0x10040e96a  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040e96f  nop
0x10040e970  lea     rcx, [rbp+650h+var_660]
0x10040e974  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040e979  nop
0x10040e97a  lea     rcx, [rbp+650h+var_678]
0x10040e97e  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040e983  nop
0x10040e984  mov     eax, edi
0x10040e986  jmp     loc_10040EE38
0x10040e98b  cmp     esi, 1
0x10040e98e  jnz     short loc_10040E9A5
0x10040e990  lea     rdx, [rbp+650h+var_6C8]
0x10040e994  lea     rcx, [rbp+650h+var_6A8]
0x10040e998  call    ?Intersects@?$CMglRect@N@@QEBA_NAEBV1@@Z; CMglRect<double>::Intersects(CMglRect<double> const &)
0x10040e99d  test    al, al
0x10040e99f  jz      loc_10040ED1A
0x10040e9a5  movsd   xmm0, [rbp+650h+var_6B0]
0x10040e9aa  movsd   xmm2, [rbp+650h+var_6B8]
0x10040e9af  movsd   xmm1, [rbp+650h+var_6C0]
0x10040e9b4  movsd   xmm3, [rbp+650h+var_6C8]
0x10040e9b9  movsd   xmm6, [rbp+650h+var_690]
0x10040e9be  movsd   xmm4, [rbp+650h+var_698]
0x10040e9c3  movsd   xmm5, [rbp+650h+var_6A8]
0x10040e9c8  movsd   xmm7, [rbp+650h+var_6A0]
0x10040e9cd  comisd  xmm5, xmm7
0x10040e9d1  ja      short loc_10040E9D9
0x10040e9d3  comisd  xmm4, xmm6
0x10040e9d7  jbe     short loc_10040E9ED
0x10040e9d9  comisd  xmm3, xmm1
0x10040e9dd  ja      loc_10040ED1A
0x10040e9e3  comisd  xmm2, xmm0
0x10040e9e7  ja      loc_10040ED1A
0x10040e9ed  movsd   [rsp+750h+var_700], xmm5
0x10040e9f3  movsd   [rsp+750h+var_6F8], xmm7
0x10040e9f9  movsd   [rsp+750h+var_6F0], xmm4
0x10040e9ff  movsd   [rsp+750h+var_6E8], xmm6
0x10040ea05  comisd  xmm3, xmm1
0x10040ea09  ja      short loc_10040EA61
0x10040ea0b  comisd  xmm2, xmm0
0x10040ea0f  ja      short loc_10040EA61
0x10040ea11  comisd  xmm5, xmm7
0x10040ea15  ja      short loc_10040EA49
0x10040ea17  comisd  xmm4, xmm6
0x10040ea1b  ja      short loc_10040EA49
0x10040ea1d  comisd  xmm5, xmm3
0x10040ea21  jbe     short loc_10040EA29
0x10040ea23  movsd   [rsp+750h+var_700], xmm3
0x10040ea29  comisd  xmm4, xmm2
0x10040ea2d  jbe     short loc_10040EA35
0x10040ea2f  movsd   [rsp+750h+var_6F0], xmm2
0x10040ea35  comisd  xmm1, xmm7
0x10040ea39  jbe     short loc_10040EA41
0x10040ea3b  movsd   [rsp+750h+var_6F8], xmm1
0x10040ea41  comisd  xmm0, xmm6
0x10040ea45  jbe     short loc_10040EA61
0x10040ea47  jmp     short loc_10040EA5B
0x10040ea49  movsd   [rsp+750h+var_700], xmm3
0x10040ea4f  movsd   [rsp+750h+var_6F8], xmm1
0x10040ea55  movsd   [rsp+750h+var_6F0], xmm2
0x10040ea5b  movsd   [rsp+750h+var_6E8], xmm0
0x10040ea61  movsd   xmm2, cs:__real@3ff0000000000000
0x10040ea69  lea     rdx, [rsp+750h+var_700]
0x10040ea6e  lea     rcx, [rbp+650h+var_488]
0x10040ea75  call    ?SetWithScaleFactor@CWorkspaceTransform@@QEAAJAEBV?$CMglRect@N@@N@Z; CWorkspaceTransform::SetWithScaleFactor(CMglRect<double> const &,double)
0x10040ea7a  mov     edi, eax
0x10040ea7c  test    eax, eax
0x10040ea7e  js      loc_10040ECCA
0x10040ea84  movsd   xmm0, [rbp+650h+var_438]
0x10040ea8c  minsd   xmm0, [rbp+650h+var_430]
0x10040ea94  movsd   [rbp+650h+var_E8], xmm0
0x10040ea9c  mov     [rsp+750h+var_6E0], 3
0x10040eaa4  lea     rax, [rbp+650h+var_420]
0x10040eaab  mov     [rbp+650h+var_1D8], rax
0x10040eab2  lea     rax, [rbp+650h+var_420]
0x10040eab9  mov     [rbp+650h+var_158], rax
0x10040eac0  lea     r8, [rsp+750h+var_6E0]; unsigned int *
0x10040eac5  mov     edx, 1; unsigned int
0x10040eaca  lea     rcx, [rbp+650h+var_420]; this
0x10040ead1  call    ?RegisterAttributes@CAttributes@@QEAAJIPEBI@Z; CAttributes::RegisterAttributes(uint,uint const *)
0x10040ead6  mov     edi, eax
0x10040ead8  test    eax, eax
0x10040eada  jns     short loc_10040EB2C
0x10040eadc  lfence
0x10040eadf  lea     rcx, [rbp+650h+var_490]; this
0x10040eae6  call    ??1CStructuredBooleanModule@@UEAA@XZ; CStructuredBooleanModule::~CStructuredBooleanModule(void)
0x10040eaeb  nop
0x10040eaec  lea     rax, ??_7C2DMetadataResolver@@6B@; const C2DMetadataResolver::`vftable'
0x10040eaf3  mov     [rsp+750h+var_720], rax
0x10040eaf8  mov     [rsp+750h+var_720], r13
0x10040eafd  lea     rcx, [rbp+650h+var_630]
0x10040eb01  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040eb06  nop
0x10040eb07  lea     rcx, [rbp+650h+var_648]
0x10040eb0b  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040eb10  nop
0x10040eb11  lea     rcx, [rbp+650h+var_660]
0x10040eb15  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040eb1a  nop
0x10040eb1b  lea     rcx, [rbp+650h+var_678]
0x10040eb1f  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10040eb24  nop
0x10040eb25  mov     eax, edi
0x10040eb27  jmp     loc_10040EE38
0x10040eb2c  lea     rax, [rsp+750h+var_6D8]
0x10040eb31  mov     [rbp+650h+var_78], rax
0x10040eb38  mov     [rsp+750h+var_728], 0; bool
0x10040eb3d  lea     rax, [rsp+750h+var_720]
0x10040eb42  mov     [rsp+750h+var_730], rax; struct C2DMetadataResolver *
0x10040eb47  movzx   r9d, dl; bool
0x10040eb4b  xor     r8d, r8d; bool
0x10040eb4e  lea     rdx, [rbp+650h+var_F8]; struct CGeometrySinkD *
0x10040eb55  mov     rcx, r14; struct GeoData *
0x10040eb58  call    ?PopulateAsUnion@@YAJAEBUGeoData@@PEAVCGeometrySinkD@@_N2PEAVC2DMetadataResolver@@2@Z; PopulateAsUnion(GeoData const &,CGeometrySinkD *,bool,bool,C2DMetadataResolver *,bool)
0x10040eb5d  mov     edi, eax
0x10040eb5f  test    eax, eax
0x10040eb61  jns     short loc_10040EBB3
  ... truncated ...
```
