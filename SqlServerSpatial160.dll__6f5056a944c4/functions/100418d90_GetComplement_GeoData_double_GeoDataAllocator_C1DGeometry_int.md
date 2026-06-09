# GetComplement(GeoData *,double,GeoDataAllocator *,C1DGeometry *,int &)

- ea: `0x100418d90`
- end: `0x1004190bf`
- name: `?GetComplement@@YAJPEAUGeoData@@NPEAUGeoDataAllocator@@PEAVC1DGeometry@@AEAH@Z`
- size: `815`
- prototype: `__int64 __usercall@<rax>(struct GeoData *@<rcx>, double@<xmm1>, struct GeoDataAllocator *@<r8>, struct C1DGeometry *@<r9>, int *)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x100416c90`
- `0x1004190d0`
- `0x10041aca0`
- `0x10041bd30`
- `0x10041c700`

## callees

- `0x10040abd0`
- `0x10040acd0`
- `0x10040b270`
- `0x10040d210`
- `0x100416a80`
- `0x100418d90`
- `0x100421170`
- `0x100425d60`
- `0x100461a80`
- `0x100468a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=85
__int64 __fastcall GetComplement(
        struct GeoData *a1,
        double a2,
        struct GeoDataAllocator *a3,
        struct C1DGeometry *a4,
        int *a5)
{
  __int64 v9; // rdx
  __int64 v10; // rax
  int v11; // edi
  _QWORD v12[5]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v14[24]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v15[24]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v16[24]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v17[24]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v18; // [rsp+D8h] [rbp-28h]
  __int128 v19; // [rsp+E8h] [rbp-18h]
  __int128 v20; // [rsp+F8h] [rbp-8h]
  __int128 v21; // [rsp+108h] [rbp+8h]
  __int128 v22; // [rsp+118h] [rbp+18h]
  int v23[2]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE *v24; // [rsp+158h] [rbp+58h]
  CGeodeticScannerConstruction *v25; // [rsp+160h] [rbp+60h]
  struct COriginalPoints *v26; // [rsp+168h] [rbp+68h]
  _QWORD v27[2]; // [rsp+170h] [rbp+70h] BYREF
  int v28; // [rsp+180h] [rbp+80h]
  __int64 v29; // [rsp+188h] [rbp+88h]
  __int64 v30; // [rsp+190h] [rbp+90h]
  __int64 v31; // [rsp+198h] [rbp+98h]
  __int64 v32; // [rsp+1A0h] [rbp+A0h]
  int v33; // [rsp+1D8h] [rbp+D8h]
  struct CGeometrySinkD *v34; // [rsp+1E0h] [rbp+E0h]
  _QWORD v35[3]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v36[736]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v37; // [rsp+4E0h] [rbp+3E0h]
  __int64 v38; // [rsp+4E8h] [rbp+3E8h]

  v12[2] = -2;
  if ( *a5 > 10 )
    return 2147500037LL;
  ++*a5;
  GeometryDataBuilder::GeometryDataBuilder((GeometryDataBuilder *)&v13, a3, 0);
  CGeodeticBoolean::CGeodeticBoolean(v36, v9, 3, 0, 0);
  v10 = *(_QWORD *)a1;
  v12[0] = 0;
  v12[1] = v10;
  v24 = v36;
  *(_QWORD *)v23 = &CMetadataEnabledGeodeticOperation::`vftable';
  v25 = (CGeodeticScannerConstruction *)v36;
  v26 = (struct COriginalPoints *)v12;
  v12[3] = v27;
  v27[0] = &CMetadataFilter::`vftable';
  v27[1] = &v13;
  v28 = 0;
  v30 = 0;
  v29 = 0;
  v32 = 0;
  v31 = 0;
  v33 = 0;
  v34 = (struct CGeometrySinkD *)v27;
  v35[0] = &C2DMetadataResolver::`vftable';
  v35[1] = v12;
  *(_QWORD *)(*(_QWORD *)(v37 + 8) + 376LL) = v35;
  *(_QWORD *)(*(_QWORD *)(v38 + 8) + 376LL) = v35;
  v11 = CGeodeticScannerConstruction::Set(v25, v26, v34, 1.0, 1);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_BYTE *, _QWORD, _QWORD))(*(_QWORD *)v24 + 24LL))(v24, 0, 0);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(_BYTE *, __int64, _QWORD))(*(_QWORD *)v24 + 8LL))(v24, 6, 0);
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(_BYTE *, _QWORD))(*(_QWORD *)v24 + 72LL))(v24, 0);
        if ( v11 >= 0 )
        {
          v11 = InternalPopulate<CGeometrySinkD>((__int64)a1, (__int64)v23, 0, 1u, 1, 0, 1);
          if ( v11 >= 0 )
          {
            _mm_lfence();
            *(_OWORD *)a1 = v18;
            *((_OWORD *)a1 + 1) = v19;
            *((_OWORD *)a1 + 2) = v20;
            *((_OWORD *)a1 + 3) = v21;
            *((_OWORD *)a1 + 4) = v22;
            *((_DWORD *)a4 + 5) = 0;
            *((_QWORD *)a4 + 1) = 0;
            v11 = ValidateGeodeticOutput(a1, a2, a3, a4);
          }
        }
      }
    }
  }
  *(_QWORD *)v23 = &CMetadataEnabledGeodeticOperation::`vftable';
  v35[0] = &CMetadataResolver::`vftable';
  CMetadataFilter::~CMetadataFilter((CMetadataFilter *)v27);
  *(_QWORD *)v23 = &IMglGeometrySink::`vftable';
  CGeodeticBoolean::~CGeodeticBoolean((CGeodeticBoolean *)v36);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v17);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v16);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v15);
  ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(v14);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x100418d90  push    rbp
0x100418d92  push    rbx
0x100418d93  push    rsi
0x100418d94  push    rdi
0x100418d95  push    r12
0x100418d97  push    r13
0x100418d99  push    r14
0x100418d9b  push    r15
0x100418d9d  lea     rbp, [rsp-0C18h]
0x100418da5  sub     rsp, 0D18h
0x100418dac  mov     [rsp+0D50h+var_CF8], 0FFFFFFFFFFFFFFFEh
0x100418db5  movaps  [rsp+0D50h+var_50], xmm6
0x100418dbd  mov     rax, cs:__security_cookie
0x100418dc4  xor     rax, rsp
0x100418dc7  mov     [rbp+0C50h+var_60], rax
0x100418dce  mov     r14, r9
0x100418dd1  mov     r15, r8
0x100418dd4  movaps  xmm6, xmm1
0x100418dd7  mov     rsi, rcx
0x100418dda  mov     rcx, [rbp+0C50h+arg_20]
0x100418de1  mov     eax, [rcx]
0x100418de3  cmp     eax, 0Ah
0x100418de6  jle     short loc_100418DF2
0x100418de8  mov     eax, 80004005h
0x100418ded  jmp     loc_100419094
0x100418df2  inc     eax
0x100418df4  mov     [rcx], eax
0x100418df6  xor     r8d, r8d; struct COriginalPoints *
0x100418df9  mov     rdx, r15; struct GeoDataAllocator *
0x100418dfc  lea     rcx, [rsp+0D50h+var_CE0]; this
0x100418e01  call    ??0GeometryDataBuilder@@QEAA@PEAUGeoDataAllocator@@PEAVCOriginalPoints@@@Z; GeometryDataBuilder::GeometryDataBuilder(GeoDataAllocator *,COriginalPoints *)
0x100418e06  nop
0x100418e07  xor     ebx, ebx
0x100418e09  mov     qword ptr [rsp+0D50h+var_D30], rbx
0x100418e0e  xor     r9d, r9d
0x100418e11  lea     r8d, [rbx+3]
0x100418e15  movaps  xmm1, xmm6
0x100418e18  lea     rcx, [rbp+0C50h+var_B50]
0x100418e1f  call    ??0CGeodeticBoolean@@QEAA@NW4MGL_COMBINE_MODE@@PEAVC1DGeometry@@1@Z; CGeodeticBoolean::CGeodeticBoolean(double,MGL_COMBINE_MODE,C1DGeometry *,C1DGeometry *)
0x100418e24  nop
0x100418e25  mov     rax, [rsi]
0x100418e28  mov     [rsp+0D50h+var_D08], rbx
0x100418e2d  mov     [rsp+0D50h+var_D00], rax
0x100418e32  lea     r12, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x100418e39  mov     qword ptr [rbp+0C50h+var_C00], r12
0x100418e3d  lea     rcx, ??_7CGeometrySinkD@@6B@; const CGeometrySinkD::`vftable'
0x100418e44  mov     qword ptr [rbp+0C50h+var_C00], rcx
0x100418e48  lea     r13, ??_7CDecorator@@6B@; const CDecorator::`vftable'
0x100418e4f  mov     qword ptr [rbp+0C50h+var_C00], r13
0x100418e53  lea     rax, [rbp+0C50h+var_B50]
0x100418e5a  mov     [rbp+0C50h+var_BF8], rax
0x100418e5e  lea     rax, ??_7CMetadataEnabledGeodeticOperation@@6B@; const CMetadataEnabledGeodeticOperation::`vftable'
0x100418e65  mov     qword ptr [rbp+0C50h+var_C00], rax
0x100418e69  lea     rax, [rbp+0C50h+var_B50]
0x100418e70  mov     [rbp+0C50h+var_BF0], rax
0x100418e74  lea     rax, [rsp+0D50h+var_D08]
0x100418e79  mov     [rbp+0C50h+var_BE8], rax
0x100418e7d  lea     rax, [rbp+0C50h+var_BE0]
0x100418e81  mov     [rsp+0D50h+var_CF0], rax
0x100418e86  mov     [rbp+0C50h+var_BE0], r12
0x100418e8a  mov     [rbp+0C50h+var_BE0], rcx
0x100418e8e  lea     rax, ??_7CMetadataFilter@@6B@; const CMetadataFilter::`vftable'
0x100418e95  mov     [rbp+0C50h+var_BE0], rax
0x100418e99  lea     rax, [rsp+0D50h+var_CE0]
0x100418e9e  mov     [rbp+0C50h+var_BD8], rax
0x100418ea2  mov     [rbp+0C50h+var_BD0], ebx
0x100418ea8  mov     [rbp+0C50h+var_BC0], rbx
0x100418eaf  mov     [rbp+0C50h+var_BC8], rbx
0x100418eb6  mov     [rbp+0C50h+var_BB0], rbx
0x100418ebd  mov     [rbp+0C50h+var_BB8], rbx
0x100418ec4  mov     [rbp+0C50h+var_B78], ebx
0x100418eca  lea     rax, [rbp+0C50h+var_BE0]
0x100418ece  mov     [rbp+0C50h+var_B70], rax
0x100418ed5  lea     rax, [rbp+0C50h+var_B68]
0x100418edc  mov     [rsp+0D50h+var_D10], rax
0x100418ee1  lea     rax, ??_7CMetadataResolver@@6B@; const CMetadataResolver::`vftable'
0x100418ee8  mov     [rbp+0C50h+var_B68], rax
0x100418eef  lea     rax, ??_7C2DMetadataResolver@@6B@; const C2DMetadataResolver::`vftable'
0x100418ef6  mov     [rbp+0C50h+var_B68], rax
0x100418efd  lea     rax, [rsp+0D50h+var_D08]
0x100418f02  mov     [rbp+0C50h+var_B60], rax
0x100418f09  mov     rax, [rbp+0C50h+var_870]
0x100418f10  mov     rcx, [rax+8]
0x100418f14  lea     rax, [rbp+0C50h+var_B68]
0x100418f1b  mov     [rcx+178h], rax
0x100418f22  mov     rax, [rbp+0C50h+var_868]
0x100418f29  mov     rcx, [rax+8]
0x100418f2d  lea     rax, [rbp+0C50h+var_B68]
0x100418f34  mov     [rcx+178h], rax
0x100418f3b  mov     [rsp+0D50h+var_D30], 1; bool
0x100418f40  movsd   xmm3, cs:__real@3ff0000000000000; double
0x100418f48  mov     r8, [rbp+0C50h+var_B70]; struct CGeometrySinkD *
0x100418f4f  mov     rdx, [rbp+0C50h+var_BE8]; struct COriginalPoints *
0x100418f53  mov     rcx, [rbp+0C50h+var_BF0]; this
0x100418f57  call    ?Set@CGeodeticScannerConstruction@@QEAAJPEBVCOriginalPoints@@PEAVCGeometrySinkD@@N_N@Z; CGeodeticScannerConstruction::Set(COriginalPoints const *,CGeometrySinkD *,double,bool)
0x100418f5c  mov     edi, eax
0x100418f5e  test    eax, eax
0x100418f60  js      loc_100419012
0x100418f66  mov     rcx, [rbp+0C50h+var_BF8]
0x100418f6a  mov     rax, [rcx]
0x100418f6d  mov     r8d, ebx
0x100418f70  xor     edx, edx
0x100418f72  call    qword ptr [rax+18h]
0x100418f75  mov     edi, eax
0x100418f77  test    eax, eax
0x100418f79  js      loc_100419012
0x100418f7f  mov     rcx, [rbp+0C50h+var_BF8]
0x100418f83  mov     rax, [rcx]
0x100418f86  xor     r8d, r8d
0x100418f89  lea     edx, [rbx+6]
0x100418f8c  call    qword ptr [rax+8]
0x100418f8f  mov     edi, eax
0x100418f91  test    eax, eax
0x100418f93  js      short loc_100419012
0x100418f95  mov     rcx, [rbp+0C50h+var_BF8]
0x100418f99  mov     rax, [rcx]
0x100418f9c  xor     edx, edx
0x100418f9e  call    qword ptr [rax+48h]
0x100418fa1  mov     edi, eax
0x100418fa3  test    eax, eax
0x100418fa5  js      short loc_100419012
0x100418fa7  mov     [rsp+0D50h+var_D20], 1; char
0x100418fac  mov     [rsp+0D50h+var_D28], bl; char
0x100418fb0  mov     [rsp+0D50h+var_D30], 1; char
0x100418fb5  mov     r9b, 1
0x100418fb8  xor     r8d, r8d
0x100418fbb  lea     rdx, [rbp+0C50h+var_C00]; int
0x100418fbf  mov     rcx, rsi; int
0x100418fc2  call    ??$InternalPopulate@VCGeometrySinkD@@@@YAJAEBUGeoData@@PEAVCGeometrySinkD@@W4MGL_WINDING_RULE@@_NE33@Z; InternalPopulate<CGeometrySinkD>(GeoData const &,CGeometrySinkD *,MGL_WINDING_RULE,bool,uchar,bool,bool)
0x100418fc7  mov     edi, eax
0x100418fc9  test    eax, eax
0x100418fcb  js      short loc_100419012
0x100418fcd  lfence
0x100418fd0  movups  xmm0, [rbp+0C50h+var_C78]
0x100418fd4  movups  xmmword ptr [rsi], xmm0
0x100418fd7  movups  xmm2, [rbp+0C50h+var_C68]
0x100418fdb  movups  xmmword ptr [rsi+10h], xmm2
0x100418fdf  movups  xmm0, [rbp+0C50h+var_C58]
0x100418fe3  movups  xmmword ptr [rsi+20h], xmm0
0x100418fe7  movups  xmm2, [rbp+0C50h+var_C48]
0x100418feb  movups  xmmword ptr [rsi+30h], xmm2
0x100418fef  movups  xmm0, [rbp+0C50h+var_C38]
0x100418ff3  movups  xmmword ptr [rsi+40h], xmm0
0x100418ff7  mov     [r14+14h], ebx
0x100418ffb  mov     [r14+8], rbx
0x100418fff  mov     r9, r14; struct C1DGeometry *
0x100419002  mov     r8, r15; struct GeoDataAllocator *
0x100419005  movaps  xmm1, xmm6; double
0x100419008  mov     rcx, rsi; struct GeoData *
0x10041900b  call    ?ValidateGeodeticOutput@@YAJAEAUGeoData@@NPEAUGeoDataAllocator@@PEAVC1DGeometry@@@Z; ValidateGeodeticOutput(GeoData &,double,GeoDataAllocator *,C1DGeometry *)
0x100419010  mov     edi, eax
0x100419012  lea     rax, ??_7CMetadataEnabledGeodeticOperation@@6B@; const CMetadataEnabledGeodeticOperation::`vftable'
0x100419019  mov     qword ptr [rbp+0C50h+var_C00], rax
0x10041901d  lea     rax, [rbp+0C50h+var_B68]
0x100419024  mov     [rsp+0D50h+var_D10], rax
0x100419029  lea     rax, ??_7C2DMetadataResolver@@6B@; const C2DMetadataResolver::`vftable'
0x100419030  mov     [rbp+0C50h+var_B68], rax
0x100419037  lea     rax, ??_7CMetadataResolver@@6B@; const CMetadataResolver::`vftable'
0x10041903e  mov     [rbp+0C50h+var_B68], rax
0x100419045  lea     rcx, [rbp+0C50h+var_BE0]; this
0x100419049  call    ??1CMetadataFilter@@UEAA@XZ; CMetadataFilter::~CMetadataFilter(void)
0x10041904e  nop
0x10041904f  mov     qword ptr [rbp+0C50h+var_C00], r13
0x100419053  mov     qword ptr [rbp+0C50h+var_C00], r12
0x100419057  lea     rcx, [rbp+0C50h+var_B50]; this
0x10041905e  call    ??1CGeodeticBoolean@@UEAA@XZ; CGeodeticBoolean::~CGeodeticBoolean(void)
0x100419063  nop
0x100419064  lea     rcx, [rbp+0C50h+var_C90]
0x100419068  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10041906d  nop
0x10041906e  lea     rcx, [rbp+0C50h+var_CA8]
0x100419072  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100419077  nop
0x100419078  lea     rcx, [rbp+0C50h+var_CC0]
0x10041907c  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x100419081  nop
0x100419082  lea     rcx, [rsp+0D50h+var_CD8]
0x100419087  call    ??1?$ArrayOverPages@VCLineSegmentIntersection@RobustIntersections@@V?$SOS_Or_CRT_Allocator@VCLineSegmentIntersection@RobustIntersections@@@@@@QEAA@XZ; ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>::~ArrayOverPages<RobustIntersections::CLineSegmentIntersection,SOS_Or_CRT_Allocator<RobustIntersections::CLineSegmentIntersection>>(void)
0x10041908c  nop
0x10041908d  mov     [rsp+0D50h+var_CE0], r12
0x100419092  mov     eax, edi
0x100419094  mov     rcx, [rbp+0C50h+var_60]
0x10041909b  xor     rcx, rsp; StackCookie
0x10041909e  call    __security_check_cookie
0x1004190a3  movaps  xmm6, [rsp+0D50h+var_50]
0x1004190ab  add     rsp, 0D18h
0x1004190b2  pop     r15
0x1004190b4  pop     r14
0x1004190b6  pop     r13
0x1004190b8  pop     r12
0x1004190ba  pop     rdi
0x1004190bb  pop     rsi
0x1004190bc  pop     rbx
0x1004190bd  pop     rbp
0x1004190be  retn
```
