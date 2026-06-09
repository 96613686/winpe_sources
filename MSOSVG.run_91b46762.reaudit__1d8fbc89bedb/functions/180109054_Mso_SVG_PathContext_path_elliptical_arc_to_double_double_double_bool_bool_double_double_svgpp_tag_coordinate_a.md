# Mso::SVG::PathContext::path_elliptical_arc_to(double,double,double,bool,bool,double,double,svgpp::tag::coordinate::absolute)

- ea: `0x180109054`
- end: `0x18010924b`
- name: `?path_elliptical_arc_to@PathContext@SVG@Mso@@QEAAXNNN_N0NNUabsolute@coordinate@tag@svgpp@@@Z`
- size: `503`
- prototype: `__int64 __fastcall(__int64, int, int, int, char, char, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800b7fb0`
- `0x1800b8100`

## callees

- `0x1800e2d0c`
- `0x180109054`
- `0x18013b708`

## import_xrefs

- `gfx!?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x1801090b1`
- `gfx!?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x1801090b1`
- `gfx!?Arc@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TVector2@N@Math@@NN_NN@Z` at `0x180109208`
- `gfx!?Arc@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TVector2@N@Math@@NN_NN@Z` at `0x180109208`
- `gfx!?LineTo@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x1801090e7`
- `gfx!?LineTo@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x1801090e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Mso::SVG::PathContext::path_elliptical_arc_to(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        char a5,
        char a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // xmm1_8
  __int64 v9; // xmm2_8
  double v10; // xmm3_8
  __int64 v11; // rdi
  __int64 v13; // xmm1_8
  __int64 result; // rax
  __int64 v15; // xmm6_8
  __int64 v16; // xmm7_8
  __int64 v17; // [rsp+70h] [rbp-31h] BYREF
  __int64 v18; // [rsp+78h] [rbp-29h] BYREF
  __int64 v19[8]; // [rsp+80h] [rbp-21h] BYREF
  __int64 v20; // [rsp+E0h] [rbp+3Fh] BYREF
  __int64 v21; // [rsp+E8h] [rbp+47h] BYREF
  __int64 v22; // [rsp+F0h] [rbp+4Fh] BYREF

  v22 = v9;
  v21 = v8;
  v11 = a1 + 408;
  if ( !*(_DWORD *)(a1 + 424) )
  {
    if ( !*(_BYTE *)(a1 + 512) )
    {
      Ofc::CInvalidOperationException::ThrowTag(0x2324B616u);
      __debugbreak();
    }
    GEL::PathBuilder::BeginFigure(a1 + 408, a1 + 496);
  }
  if ( *(double *)&v8 == 0.0 || *(double *)&v9 == 0.0 )
  {
    v13 = a8;
    *(_QWORD *)(a1 + 480) = a7;
    *(_QWORD *)(a1 + 488) = v13;
    return GEL::PathBuilder::LineTo(v11);
  }
  else
  {
    if ( *(double *)&v8 < 0.0 )
      v21 = v8 ^ _xmm;
    if ( *(double *)&v9 < 0.0 )
      v22 = v9 ^ _xmm;
    v15 = a8;
    v16 = a7;
    v20 = 0;
    v17 = 0;
    svgpp::arc_endpoint_to_center<double>(
      a1,
      a2,
      a3,
      a4,
      (__int64)&v21,
      (__int64)&v22,
      v10 * 0.0174532925199433,
      a5,
      a6,
      (__int64)v19,
      (__int64)&v18,
      (__int64)&v20,
      (__int64)&v17);
    *(double *)v19 = *(double *)&v21 * 2.0;
    *(double *)&v19[1] = *(double *)&v22 * 2.0;
    result = GEL::PathBuilder::Arc(v11, v19);
    *(_QWORD *)(a1 + 480) = v16;
    *(_QWORD *)(a1 + 488) = v15;
  }
  return result;
}

```

## disassembly

```asm
0x180109054  mov     rax, rsp
0x180109057  mov     [rax+20h], rbx
0x18010905b  movsd   qword ptr [rax+18h], xmm2
0x180109060  movsd   qword ptr [rax+10h], xmm1
0x180109065  push    rbp
0x180109066  push    rsi
0x180109067  push    rdi
0x180109068  lea     rbp, [rax-37h]
0x18010906c  sub     rsp, 0C0h
0x180109073  movaps  xmmword ptr [rax-28h], xmm6
0x180109077  lea     rdi, [rcx+198h]
0x18010907e  cmp     dword ptr [rdi+10h], 0
0x180109082  movaps  xmm6, xmm2
0x180109085  movaps  xmmword ptr [rax-38h], xmm7
0x180109089  mov     rbx, rcx
0x18010908c  movaps  xmmword ptr [rax-48h], xmm8
0x180109091  movaps  xmm7, xmm1
0x180109094  movaps  xmm8, xmm3
0x180109098  jnz     short loc_1801090B7
0x18010909a  cmp     byte ptr [rcx+200h], 0
0x1801090a1  jz      loc_180109240
0x1801090a7  lea     rdx, [rcx+1F0h]
0x1801090ae  mov     rcx, rdi
0x1801090b1  call    cs:__imp_?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z; GEL::PathBuilder::BeginFigure(Math::TPoint2<double> const &)
0x1801090b7  xorps   xmm0, xmm0
0x1801090ba  ucomisd xmm7, xmm0
0x1801090be  jp      short loc_1801090C2
0x1801090c0  jz      short loc_1801090CA
0x1801090c2  ucomisd xmm6, xmm0
0x1801090c6  jp      short loc_1801090F2
0x1801090c8  jnz     short loc_1801090F2
0x1801090ca  movsd   xmm0, [rbp+2Fh+arg_30]
0x1801090cf  lea     rdx, [rbx+1E0h]
0x1801090d6  movsd   xmm1, [rbp+2Fh+arg_38]
0x1801090db  mov     rcx, rdi
0x1801090de  movsd   qword ptr [rdx], xmm0
0x1801090e2  movsd   qword ptr [rdx+8], xmm1
0x1801090e7  call    cs:__imp_?LineTo@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z; GEL::PathBuilder::LineTo(Math::TPoint2<double> const &)
0x1801090ed  jmp     loc_18010921E
0x1801090f2  comisd  xmm0, xmm7
0x1801090f6  movsd   xmm1, qword ptr cs:__xmm@80000000000000008000000000000000
0x1801090fe  jbe     short loc_180109108
0x180109100  xorps   xmm7, xmm1
0x180109103  movsd   [rbp+2Fh+arg_8], xmm7
0x180109108  comisd  xmm0, xmm6
0x18010910c  jbe     short loc_180109116
0x18010910e  xorps   xmm6, xmm1
0x180109111  movsd   [rbp+2Fh+arg_10], xmm6
0x180109116  mulsd   xmm8, cs:__real@3f91df46a2529d39
0x18010911f  lea     rax, [rbp+2Fh+var_60]
0x180109123  mov     sil, [rbp+2Fh+arg_28]
0x180109127  movsd   xmm6, [rbp+2Fh+arg_38]
0x18010912c  movsd   xmm7, [rbp+2Fh+arg_30]
0x180109131  movaps  xmm3, xmm6
0x180109134  movsd   xmm1, qword ptr [rbx+1E8h]
0x18010913c  movaps  xmm2, xmm7
0x18010913f  mov     [rsp+0D0h+var_70], rax; __int64
0x180109144  lea     rax, [rbp+2Fh+arg_0]
0x180109148  mov     [rsp+0D0h+var_78], rax; __int64
0x18010914d  lea     rax, [rbp+2Fh+var_58]
0x180109151  mov     [rsp+0D0h+var_80], rax; __int64
0x180109156  lea     rax, [rbp+2Fh+var_50]
0x18010915a  mov     [rsp+0D0h+var_88], rax; __int64
0x18010915f  mov     al, [rbp+2Fh+arg_20]
0x180109162  mov     [rsp+0D0h+var_90], sil; char
0x180109167  mov     [rsp+0D0h+var_98], al; char
0x18010916b  lea     rax, [rbp+2Fh+arg_10]
0x18010916f  movsd   [rsp+0D0h+X], xmm8; X
0x180109176  mov     [rsp+0D0h+var_A8], rax; __int64
0x18010917b  lea     rax, [rbp+2Fh+arg_8]
0x18010917f  movsd   [rbp+2Fh+arg_0], xmm0
0x180109184  movsd   [rbp+2Fh+var_60], xmm0
0x180109189  movsd   xmm0, qword ptr [rbx+1E0h]
0x180109191  mov     [rsp+0D0h+var_B0], rax; __int64
0x180109196  call    ??$arc_endpoint_to_center@N@svgpp@@YAXNNNNAEAN0N_N10000@Z; svgpp::arc_endpoint_to_center<double>(double,double,double,double,double &,double &,double,bool,bool,double &,double &,double &,double &)
0x18010919b  movsd   xmm2, [rbp+2Fh+arg_0]
0x1801091a0  movsd   xmm3, [rbp+2Fh+var_60]
0x1801091a5  comisd  xmm2, xmm3
0x1801091a9  jbe     short loc_1801091BA
0x1801091ab  test    sil, sil
0x1801091ae  jz      short loc_1801091BA
0x1801091b0  addsd   xmm3, cs:__real@401921fb54442d18
0x1801091b8  jmp     short loc_1801091CD
0x1801091ba  comisd  xmm3, xmm2
0x1801091be  jbe     short loc_1801091CD
0x1801091c0  test    sil, sil
0x1801091c3  jnz     short loc_1801091CD
0x1801091c5  addsd   xmm3, cs:__real@c01921fb54442d18
0x1801091cd  movsd   xmm0, [rbp+2Fh+arg_8]
0x1801091d2  subsd   xmm3, xmm2
0x1801091d6  mulsd   xmm0, cs:__real@4000000000000000
0x1801091de  lea     rdx, [rbp+2Fh+var_50]
0x1801091e2  mov     rcx, rdi
0x1801091e5  movsd   [rsp+0D0h+var_A8], xmm8
0x1801091ec  mov     byte ptr [rsp+0D0h+var_B0], 1
0x1801091f1  movsd   [rbp+2Fh+var_50], xmm0
0x1801091f6  movsd   xmm0, [rbp+2Fh+arg_10]
0x1801091fb  mulsd   xmm0, cs:__real@4000000000000000
0x180109203  movsd   [rbp+2Fh+var_48], xmm0
0x180109208  call    cs:__imp_?Arc@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TVector2@N@Math@@NN_NN@Z; GEL::PathBuilder::Arc(Math::TVector2<double> const &,double,double,bool,double)
0x18010920e  movsd   qword ptr [rbx+1E0h], xmm7
0x180109216  movsd   qword ptr [rbx+1E8h], xmm6
0x18010921e  lea     r11, [rsp+0D0h+var_10]
0x180109226  mov     rbx, [r11+38h]
0x18010922a  movaps  xmm6, xmmword ptr [r11-10h]
0x18010922f  movaps  xmm7, xmmword ptr [r11-20h]
0x180109234  movaps  xmm8, xmmword ptr [r11-30h]
0x180109239  mov     rsp, r11
0x18010923c  pop     rdi
0x18010923d  pop     rsi
0x18010923e  pop     rbp
0x18010923f  retn
0x180109240  mov     ecx, 2324B616h; unsigned int
0x180109245  call    ?ThrowTag@CInvalidOperationException@Ofc@@SAXK@Z; Ofc::CInvalidOperationException::ThrowTag(ulong)
0x18010924a  int     3; Trap to Debugger
```
