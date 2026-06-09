# Mso::SVG::PathContext::path_elliptical_arc_to(double,double,double,bool,bool,double,double,svgpp::tag::coordinate::absolute)

- ea: `0x180109024`
- end: `0x18010921b`
- name: `?path_elliptical_arc_to@PathContext@SVG@Mso@@QEAAXNNN_N0NNUabsolute@coordinate@tag@svgpp@@@Z`
- size: `503`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800b7f90`
- `0x1800b80e0`

## callees

- `0x1800e2cec`
- `0x180109024`
- `0x18013b658`

## import_xrefs

- `gfx!?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x180109081`
- `gfx!?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x180109081`
- `gfx!?Arc@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TVector2@N@Math@@NN_NN@Z` at `0x1801091d8`
- `gfx!?Arc@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TVector2@N@Math@@NN_NN@Z` at `0x1801091d8`
- `gfx!?LineTo@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x1801090b7`
- `gfx!?LineTo@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z` at `0x1801090b7`

## pseudocode

```c
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
0x180109024  mov     rax, rsp
0x180109027  mov     [rax+20h], rbx
0x18010902b  movsd   qword ptr [rax+18h], xmm2
0x180109030  movsd   qword ptr [rax+10h], xmm1
0x180109035  push    rbp
0x180109036  push    rsi
0x180109037  push    rdi
0x180109038  lea     rbp, [rax-37h]
0x18010903c  sub     rsp, 0C0h
0x180109043  movaps  xmmword ptr [rax-28h], xmm6
0x180109047  lea     rdi, [rcx+198h]
0x18010904e  cmp     dword ptr [rdi+10h], 0
0x180109052  movaps  xmm6, xmm2
0x180109055  movaps  xmmword ptr [rax-38h], xmm7
0x180109059  mov     rbx, rcx
0x18010905c  movaps  xmmword ptr [rax-48h], xmm8
0x180109061  movaps  xmm7, xmm1
0x180109064  movaps  xmm8, xmm3
0x180109068  jnz     short loc_180109087
0x18010906a  cmp     byte ptr [rcx+200h], 0
0x180109071  jz      loc_180109210
0x180109077  lea     rdx, [rcx+1F0h]
0x18010907e  mov     rcx, rdi
0x180109081  call    cs:__imp_?BeginFigure@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z; GEL::PathBuilder::BeginFigure(Math::TPoint2<double> const &)
0x180109087  xorps   xmm0, xmm0
0x18010908a  ucomisd xmm7, xmm0
0x18010908e  jp      short loc_180109092
0x180109090  jz      short loc_18010909A
0x180109092  ucomisd xmm6, xmm0
0x180109096  jp      short loc_1801090C2
0x180109098  jnz     short loc_1801090C2
0x18010909a  movsd   xmm0, [rbp+2Fh+arg_30]
0x18010909f  lea     rdx, [rbx+1E0h]
0x1801090a6  movsd   xmm1, [rbp+2Fh+arg_38]
0x1801090ab  mov     rcx, rdi
0x1801090ae  movsd   qword ptr [rdx], xmm0
0x1801090b2  movsd   qword ptr [rdx+8], xmm1
0x1801090b7  call    cs:__imp_?LineTo@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TPoint2@N@Math@@@Z; GEL::PathBuilder::LineTo(Math::TPoint2<double> const &)
0x1801090bd  jmp     loc_1801091EE
0x1801090c2  comisd  xmm0, xmm7
0x1801090c6  movsd   xmm1, qword ptr cs:__xmm@80000000000000008000000000000000
0x1801090ce  jbe     short loc_1801090D8
0x1801090d0  xorps   xmm7, xmm1
0x1801090d3  movsd   [rbp+2Fh+arg_8], xmm7
0x1801090d8  comisd  xmm0, xmm6
0x1801090dc  jbe     short loc_1801090E6
0x1801090de  xorps   xmm6, xmm1
0x1801090e1  movsd   [rbp+2Fh+arg_10], xmm6
0x1801090e6  mulsd   xmm8, cs:__real@3f91df46a2529d39
0x1801090ef  lea     rax, [rbp+2Fh+var_60]
0x1801090f3  mov     sil, [rbp+2Fh+arg_28]
0x1801090f7  movsd   xmm6, [rbp+2Fh+arg_38]
0x1801090fc  movsd   xmm7, [rbp+2Fh+arg_30]
0x180109101  movaps  xmm3, xmm6
0x180109104  movsd   xmm1, qword ptr [rbx+1E8h]
0x18010910c  movaps  xmm2, xmm7
0x18010910f  mov     [rsp+0D0h+var_70], rax; __int64
0x180109114  lea     rax, [rbp+2Fh+arg_0]
0x180109118  mov     [rsp+0D0h+var_78], rax; __int64
0x18010911d  lea     rax, [rbp+2Fh+var_58]
0x180109121  mov     [rsp+0D0h+var_80], rax; __int64
0x180109126  lea     rax, [rbp+2Fh+var_50]
0x18010912a  mov     [rsp+0D0h+var_88], rax; __int64
0x18010912f  mov     al, [rbp+2Fh+arg_20]
0x180109132  mov     [rsp+0D0h+var_90], sil; char
0x180109137  mov     [rsp+0D0h+var_98], al; char
0x18010913b  lea     rax, [rbp+2Fh+arg_10]
0x18010913f  movsd   [rsp+0D0h+X], xmm8; X
0x180109146  mov     [rsp+0D0h+var_A8], rax; __int64
0x18010914b  lea     rax, [rbp+2Fh+arg_8]
0x18010914f  movsd   [rbp+2Fh+arg_0], xmm0
0x180109154  movsd   [rbp+2Fh+var_60], xmm0
0x180109159  movsd   xmm0, qword ptr [rbx+1E0h]
0x180109161  mov     [rsp+0D0h+var_B0], rax; __int64
0x180109166  call    ??$arc_endpoint_to_center@N@svgpp@@YAXNNNNAEAN0N_N10000@Z; svgpp::arc_endpoint_to_center<double>(double,double,double,double,double &,double &,double,bool,bool,double &,double &,double &,double &)
0x18010916b  movsd   xmm2, [rbp+2Fh+arg_0]
0x180109170  movsd   xmm3, [rbp+2Fh+var_60]
0x180109175  comisd  xmm2, xmm3
0x180109179  jbe     short loc_18010918A
0x18010917b  test    sil, sil
0x18010917e  jz      short loc_18010918A
0x180109180  addsd   xmm3, cs:__real@401921fb54442d18
0x180109188  jmp     short loc_18010919D
0x18010918a  comisd  xmm3, xmm2
0x18010918e  jbe     short loc_18010919D
0x180109190  test    sil, sil
0x180109193  jnz     short loc_18010919D
0x180109195  addsd   xmm3, cs:__real@c01921fb54442d18
0x18010919d  movsd   xmm0, [rbp+2Fh+arg_8]
0x1801091a2  subsd   xmm3, xmm2
0x1801091a6  mulsd   xmm0, cs:__real@4000000000000000
0x1801091ae  lea     rdx, [rbp+2Fh+var_50]
0x1801091b2  mov     rcx, rdi
0x1801091b5  movsd   [rsp+0D0h+var_A8], xmm8
0x1801091bc  mov     byte ptr [rsp+0D0h+var_B0], 1
0x1801091c1  movsd   [rbp+2Fh+var_50], xmm0
0x1801091c6  movsd   xmm0, [rbp+2Fh+arg_10]
0x1801091cb  mulsd   xmm0, cs:__real@4000000000000000
0x1801091d3  movsd   [rbp+2Fh+var_48], xmm0
0x1801091d8  call    cs:__imp_?Arc@PathBuilder@GEL@@QEAAAEAV12@AEBU?$TVector2@N@Math@@NN_NN@Z; GEL::PathBuilder::Arc(Math::TVector2<double> const &,double,double,bool,double)
0x1801091de  movsd   qword ptr [rbx+1E0h], xmm7
0x1801091e6  movsd   qword ptr [rbx+1E8h], xmm6
0x1801091ee  lea     r11, [rsp+0D0h+var_10]
0x1801091f6  mov     rbx, [r11+38h]
0x1801091fa  movaps  xmm6, xmmword ptr [r11-10h]
0x1801091ff  movaps  xmm7, xmmword ptr [r11-20h]
0x180109204  movaps  xmm8, xmmword ptr [r11-30h]
0x180109209  mov     rsp, r11
0x18010920c  pop     rdi
0x18010920d  pop     rsi
0x18010920e  pop     rbp
0x18010920f  retn
0x180109210  mov     ecx, 2324B616h; unsigned int
0x180109215  call    ?ThrowTag@CInvalidOperationException@Ofc@@SAXK@Z; Ofc::CInvalidOperationException::ThrowTag(ulong)
0x18010921a  int     3; Trap to Debugger
```
