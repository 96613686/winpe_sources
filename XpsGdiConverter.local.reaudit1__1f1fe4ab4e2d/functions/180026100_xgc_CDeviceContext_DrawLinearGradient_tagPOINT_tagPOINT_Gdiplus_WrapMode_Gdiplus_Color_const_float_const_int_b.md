# xgc::CDeviceContext::DrawLinearGradient(tagPOINT,tagPOINT,Gdiplus::WrapMode,Gdiplus::Color const *,float const *,int,bool,tagPOINT const (&)[2])

- ea: `0x180026100`
- end: `0x18002642f`
- name: `?DrawLinearGradient@CDeviceContext@xgc@@QEAAXUtagPOINT@@0W4WrapMode@Gdiplus@@PEBVColor@5@PEBMH_NAEAY01$$CBU3@@Z`
- size: `815`
- prototype: `void __high(struct tagPOINT, struct tagPOINT, enum Gdiplus::WrapMode, const struct Gdiplus::Color *, const float *, int, bool, const struct tagPOINT (*)[2])`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18002e684`

## callees

- `0x180011b2c`
- `0x180011d1c`
- `0x180023ff0`
- `0x180024390`
- `0x1800246a8`
- `0x1800248b8`
- `0x180024928`
- `0x180025124`
- `0x180026100`
- `0x180027158`
- `0x180027184`

## import_xrefs

- `gdiplus!GdipFillRectangleI` at `0x18002632e`
- `gdiplus!GdipFillRectangleI` at `0x1800263ef`
- `gdiplus!GdipFillRectangleI` at `0x18002632e`
- `gdiplus!GdipFillRectangleI` at `0x1800263ef`
- `gdiplus!GdipDeleteBrush` at `0x1800263ff`
- `gdiplus!GdipDeleteBrush` at `0x1800263ff`
- `gdiplus!GdipSetLineWrapMode` at `0x1800263cf`
- `gdiplus!GdipSetLineWrapMode` at `0x1800263cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall xgc::CDeviceContext::DrawLinearGradient(
        __int64 a1,
        xgc *a2,
        struct tagPOINT a3,
        unsigned int a4,
        struct Gdiplus::Color *a5,
        __int64 a6,
        unsigned int a7,
        unsigned __int8 a8,
        struct tagPOINT a9)
{
  unsigned int v11; // r15d
  unsigned int v12; // r12d
  unsigned int v13; // esi
  unsigned int v14; // r13d
  struct Gdiplus::Color *v15; // r14
  __int64 v16; // rsi
  int v17; // r9d
  __int64 v18; // rdx
  signed int v19; // r11d
  int v20; // ecx
  int v21; // eax
  __m128i v22; // xmm0
  __m128i v23; // xmm1
  __m128i v24; // xmm2
  float v25; // xmm0_4
  float v26; // xmm2_4
  float v27; // xmm1_4
  unsigned int v28; // r8d
  __int64 v29; // r12
  _QWORD *v30; // rbx
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rbx
  _QWORD *v34; // rdi
  int v35; // eax
  struct Gdiplus::Point *v36; // [rsp+30h] [rbp-81h]
  struct tagPOINT v37[2]; // [rsp+38h] [rbp-79h] BYREF
  struct Gdiplus::Color *v38; // [rsp+48h] [rbp-69h] BYREF
  unsigned int v39; // [rsp+50h] [rbp-61h]
  unsigned int v40; // [rsp+54h] [rbp-5Dh]
  unsigned int v41; // [rsp+58h] [rbp-59h]
  unsigned int v42; // [rsp+5Ch] [rbp-55h]
  _BYTE v43[8]; // [rsp+60h] [rbp-51h] BYREF
  __int64 v44; // [rsp+68h] [rbp-49h]
  __int128 v45; // [rsp+78h] [rbp-39h] BYREF
  __int64 v46; // [rsp+88h] [rbp-29h]
  _QWORD *v47; // [rsp+90h] [rbp-21h] BYREF
  std::_Ref_count_base *v48; // [rsp+98h] [rbp-19h]
  _QWORD v49[9]; // [rsp+A0h] [rbp-11h] BYREF
  int v50; // [rsp+104h] [rbp+53h]
  struct tagPOINT v51; // [rsp+108h] [rbp+57h] BYREF
  unsigned int v52; // [rsp+110h] [rbp+5Fh]

  v52 = a4;
  v51 = a3;
  v50 = HIDWORD(a2);
  if ( a2 != *(xgc **)&a3 )
  {
    xgc::GdiSurface::GdiSurface((xgc::GdiSurface *)&v47, *(HDC *)(a1 + 32), (unsigned __int64 *)(a1 + 312));
    v11 = *(_DWORD *)(*(_QWORD *)&a9 + 4LL);
    v41 = v11;
    v12 = *(_DWORD *)(*(_QWORD *)&a9 + 12LL) - v11;
    v39 = v12;
    v13 = *(_DWORD *)a9.x;
    v42 = v13;
    v14 = *(_DWORD *)(*(_QWORD *)&a9 + 8LL) - v13;
    v15 = a5;
    v38 = (struct Gdiplus::Color *)((char *)a5 + 4 * (int)a7 - 4);
    if ( v52 == 4 )
    {
      v37[0] = 0;
      v37[1] = 0;
      xgc::CalculateNewStartEnd(a2, a3, a9, (const struct tagPOINT (*)[2])v37, (struct Gdiplus::Point *)&v37[1], v36);
      Gdiplus::LinearGradientBrush::LinearGradientBrush(
        (Gdiplus::LinearGradientBrush *)v43,
        (const struct Gdiplus::Point *)v37,
        (const struct Gdiplus::Point *)&v37[1],
        v15,
        v38);
      v45 = 0;
      v46 = 0;
      v40 = a7 + 2;
      v16 = (int)(a7 + 2);
      std::vector<Gdiplus::Color>::_Construct_n<>(&v45, v16);
      std::vector<float>::vector<float>(v49, v16);
      *(_DWORD *)v45 = *(_DWORD *)v15;
      v17 = a7 + 1;
      v18 = (int)a7;
      *(_DWORD *)(v45 + 4LL * (int)a7 + 4) = *(_DWORD *)v38;
      *(_DWORD *)v49[0] = 0;
      *(_DWORD *)(v49[0] + 4 * v18 + 4) = 1065353216;
      v19 = v37[0].x - v37[1].x;
      v20 = v37[1].y - v37[0].y;
      if ( v37[1].y - v37[0].y < 0 )
        v20 = v37[0].y - v37[1].y;
      v21 = v37[1].x - v37[0].x;
      if ( v19 > 0 )
        v21 = v37[0].x - v37[1].x;
      if ( v20 <= v21 )
      {
        v22 = _mm_cvtsi32_si128(v19);
        v23 = _mm_cvtsi32_si128(v37[0].x - (int)a2);
        v24 = _mm_cvtsi32_si128((int)a2 - a3.x);
      }
      else
      {
        v22 = _mm_cvtsi32_si128(v37[0].y - v37[1].y);
        v23 = _mm_cvtsi32_si128(v37[0].y - v50);
        v24 = _mm_cvtsi32_si128(v50 - v51.y);
      }
      v25 = _mm_cvtepi32_ps(v22).m128_f32[0];
      v26 = _mm_cvtepi32_ps(v24).m128_f32[0] / v25;
      v27 = _mm_cvtepi32_ps(v23).m128_f32[0] / v25;
      v28 = 1;
      if ( v17 > 1 )
      {
        v29 = a6;
        do
        {
          *(_DWORD *)(v45 + 4LL * v28) = *((_DWORD *)v15 + v28 - 1);
          *(float *)(v49[0] + 4LL * v28) = (float)(v26 * *(float *)(v29 + 4LL * v28 - 4)) + v27;
          ++v28;
        }
        while ( (int)v28 < v17 );
        v12 = v39;
      }
      Gdiplus::LinearGradientBrush::SetInterpolationColors(v43, v45, v49[0], v40);
      Gdiplus::LinearGradientBrush::SetGammaCorrection(v43, a8);
      v30 = v47;
      v31 = GdipFillRectangleI(*v47, v44, v42, v41, v14, v12);
      if ( v31 )
        *((_DWORD *)v30 + 2) = v31;
      std::vector<tagRGBQUAD>::_Tidy(v49);
      std::vector<tagRGBQUAD>::_Tidy(&v45);
      v32 = v44;
    }
    else
    {
      *(float *)&v38 = (float)a3.x;
      *((float *)&v38 + 1) = (float)v51.y;
      *(float *)&v51.x = (float)(int)a2;
      *(float *)&v51.y = (float)v50;
      Gdiplus::LinearGradientBrush::LinearGradientBrush(
        (Gdiplus::LinearGradientBrush *)v43,
        (const struct Gdiplus::PointF *)&v51,
        (const struct Gdiplus::PointF *)&v38,
        a5,
        (struct Gdiplus::Color *)((char *)a5 + 4 * (int)a7 - 4));
      Gdiplus::LinearGradientBrush::SetInterpolationColors(v43, v15, a6, a7);
      Gdiplus::LinearGradientBrush::SetGammaCorrection(v43, a8);
      v33 = v44;
      GdipSetLineWrapMode(v44, v52);
      v34 = v47;
      v35 = GdipFillRectangleI(*v47, v33, v13, v11, v14, v12);
      if ( v35 )
        *((_DWORD *)v34 + 2) = v35;
      v32 = v33;
    }
    GdipDeleteBrush(v32);
    if ( v48 )
      std::_Ref_count_base::_Decref(v48);
  }
}

```

## disassembly

```asm
0x180026100  mov     rax, rsp
0x180026103  mov     [rax+8], rbx
0x180026107  mov     [rax+20h], r9d
0x18002610b  mov     [rax+18h], r8
0x18002610f  mov     [rax+10h], rdx
0x180026113  push    rbp
0x180026114  push    rsi
0x180026115  push    rdi
0x180026116  push    r12
0x180026118  push    r13
0x18002611a  push    r14
0x18002611c  push    r15
0x18002611e  lea     rbp, [rax-3Fh]
0x180026122  sub     rsp, 0B0h
0x180026129  mov     rdi, r8
0x18002612c  mov     rbx, rdx
0x18002612f  cmp     edx, r8d
0x180026132  jnz     short loc_180026147
0x180026134  shr     rdx, 20h
0x180026138  mov     rax, r8
0x18002613b  shr     rax, 20h
0x18002613f  cmp     edx, eax
0x180026141  jz      loc_180026414
0x180026147  lea     r8, [rcx+138h]; unsigned __int64 *
0x18002614e  mov     rdx, [rcx+20h]; HDC
0x180026152  lea     rcx, [rbp+37h+var_58]; this
0x180026156  call    ??0GdiSurface@xgc@@QEAA@PEAUHDC__@@AEA_K@Z; xgc::GdiSurface::GdiSurface(HDC__ *,unsigned __int64 &)
0x18002615b  nop
0x18002615c  mov     r8, qword ptr [rbp+37h+arg_40.x]; struct tagPOINT
0x180026163  mov     r15d, [r8+4]
0x180026167  mov     [rbp+37h+var_90], r15d
0x18002616b  mov     r12d, [r8+0Ch]
0x18002616f  sub     r12d, r15d
0x180026172  mov     [rbp+37h+var_98], r12d
0x180026176  mov     esi, [r8]
0x180026179  mov     [rbp+37h+var_8C], esi
0x18002617c  mov     r13d, [r8+8]
0x180026180  sub     r13d, esi
0x180026183  movsxd  rax, [rbp+37h+arg_30]
0x180026187  mov     r14, [rbp+37h+arg_20]
0x18002618b  dec     rax
0x18002618e  lea     rax, [r14+rax*4]
0x180026192  mov     [rbp+37h+var_A0], rax
0x180026196  cmp     [rbp+37h+arg_18], 4
0x18002619a  jnz     loc_180026358
0x1800261a0  xor     r15d, r15d
0x1800261a3  mov     qword ptr [rbp+37h+var_B0.x], r15
0x1800261a7  mov     qword ptr [rbp+37h+var_B0.x+8], r15
0x1800261ab  lea     rax, [rbp+37h+var_B0.x+8]
0x1800261af  mov     [rsp+0E0h+var_C0], rax; struct Gdiplus::Point *
0x1800261b4  lea     r9, [rbp+37h+var_B0]; struct tagPOINT (*)[2]
0x1800261b8  mov     rdx, rdi; struct tagPOINT
0x1800261bb  mov     rcx, rbx; this
0x1800261be  call    ?CalculateNewStartEnd@xgc@@YAXUtagPOINT@@0AEAY01$$CBU2@AEAVPoint@Gdiplus@@2@Z; xgc::CalculateNewStartEnd(tagPOINT,tagPOINT,tagPOINT const (&)[2],Gdiplus::Point &,Gdiplus::Point &)
0x1800261c3  mov     rax, [rbp+37h+var_A0]
0x1800261c7  mov     [rsp+0E0h+var_C0], rax; struct Gdiplus::Color *
0x1800261cc  mov     r9, r14; struct Gdiplus::Color *
0x1800261cf  lea     r8, [rbp+37h+var_B0.x+8]; struct Gdiplus::Point *
0x1800261d3  lea     rdx, [rbp+37h+var_B0]; struct Gdiplus::Point *
0x1800261d7  lea     rcx, [rbp+37h+var_88]; this
0x1800261db  call    ??0LinearGradientBrush@Gdiplus@@QEAA@AEBVPoint@1@0AEBVColor@1@1@Z; Gdiplus::LinearGradientBrush::LinearGradientBrush(Gdiplus::Point const &,Gdiplus::Point const &,Gdiplus::Color const &,Gdiplus::Color const &)
0x1800261e0  nop
0x1800261e1  xorps   xmm0, xmm0
0x1800261e4  movdqu  [rbp+37h+var_70], xmm0
0x1800261e9  mov     [rbp+37h+var_60], r15
0x1800261ed  mov     eax, [rbp+37h+arg_30]
0x1800261f0  add     eax, 2
0x1800261f3  mov     [rbp+37h+var_94], eax
0x1800261f6  movsxd  rsi, eax
0x1800261f9  mov     rdx, rsi
0x1800261fc  lea     rcx, [rbp+37h+var_70]
0x180026200  call    ??$_Construct_n@$$V@?$vector@VColor@Gdiplus@@V?$allocator@VColor@Gdiplus@@@std@@@std@@AEAAX_K@Z; std::vector<Gdiplus::Color>::_Construct_n<>(unsigned __int64)
0x180026205  nop
0x180026206  mov     rdx, rsi
0x180026209  lea     rcx, [rbp+37h+var_48]
0x18002620d  call    ??0?$vector@MV?$allocator@M@std@@@std@@QEAA@_KAEBV?$allocator@M@1@@Z; std::vector<float>::vector<float>(unsigned __int64,std::allocator<float> const &)
0x180026212  nop
0x180026213  mov     ecx, [r14]
0x180026216  mov     rax, qword ptr [rbp+37h+var_70]
0x18002621a  mov     [rax], ecx
0x18002621c  mov     r9d, [rbp+37h+arg_30]
0x180026220  inc     r9d
0x180026223  mov     rax, [rbp+37h+var_A0]
0x180026227  mov     ecx, [rax]
0x180026229  mov     rax, qword ptr [rbp+37h+var_70]
0x18002622d  movsxd  rdx, [rbp+37h+arg_30]
0x180026231  mov     [rax+rdx*4+4], ecx
0x180026235  mov     rax, [rbp+37h+var_48]
0x180026239  mov     [rax], r15d
0x18002623c  mov     rax, [rbp+37h+var_48]
0x180026240  mov     dword ptr [rax+rdx*4+4], 3F800000h
0x180026248  mov     r8d, [rbp+37h+var_B0.x]
0x18002624c  mov     r11d, r8d
0x18002624f  sub     r11d, [rbp+37h+var_B0.x+8]
0x180026253  mov     edx, [rbp+37h+var_B0.y]
0x180026256  mov     r10d, edx
0x180026259  sub     r10d, [rbp+37h+var_B0.y+8]
0x18002625d  mov     ecx, r10d
0x180026260  neg     ecx
0x180026262  cmovs   ecx, r10d
0x180026266  mov     eax, r11d
0x180026269  neg     eax
0x18002626b  cmovs   eax, r11d
0x18002626f  cmp     ecx, eax
0x180026271  jle     short loc_18002628A
0x180026273  movd    xmm0, r10d
0x180026278  mov     eax, [rbp+37h+arg_C]
0x18002627b  sub     edx, eax
0x18002627d  movd    xmm1, edx
0x180026281  sub     eax, [rbp+37h+arg_14]
0x180026284  movd    xmm2, eax
0x180026288  jmp     short loc_18002629D
0x18002628a  movd    xmm0, r11d
0x18002628f  sub     r8d, ebx
0x180026292  movd    xmm1, r8d
0x180026297  sub     ebx, edi
0x180026299  movd    xmm2, ebx
0x18002629d  cvtdq2ps xmm0, xmm0
0x1800262a0  cvtdq2ps xmm2, xmm2
0x1800262a3  cvtdq2ps xmm1, xmm1
0x1800262a6  divss   xmm2, xmm0
0x1800262aa  divss   xmm1, xmm0
0x1800262ae  mov     r8d, 1
0x1800262b4  cmp     r9d, r8d
0x1800262b7  jle     short loc_1800262EF
0x1800262b9  mov     r12, [rbp+37h+arg_28]
0x1800262bd  mov     edx, r8d
0x1800262c0  mov     ecx, [r14+rdx*4-4]
0x1800262c5  mov     rax, qword ptr [rbp+37h+var_70]
0x1800262c9  mov     [rax+rdx*4], ecx
0x1800262cc  movaps  xmm0, xmm2
0x1800262cf  mulss   xmm0, dword ptr [r12+rdx*4-4]
0x1800262d6  addss   xmm0, xmm1
0x1800262da  mov     rax, [rbp+37h+var_48]
0x1800262de  movss   dword ptr [rax+rdx*4], xmm0
0x1800262e3  inc     r8d
0x1800262e6  cmp     r8d, r9d
0x1800262e9  jl      short loc_1800262BD
0x1800262eb  mov     r12d, [rbp+37h+var_98]
0x1800262ef  mov     r9d, [rbp+37h+var_94]
0x1800262f3  mov     r8, [rbp+37h+var_48]
0x1800262f7  mov     rdx, qword ptr [rbp+37h+var_70]
0x1800262fb  lea     rcx, [rbp+37h+var_88]
0x1800262ff  call    ?SetInterpolationColors@LinearGradientBrush@Gdiplus@@QEAA?AW4Status@2@PEBVColor@2@PEBMH@Z; Gdiplus::LinearGradientBrush::SetInterpolationColors(Gdiplus::Color const *,float const *,int)
0x180026304  movzx   edx, [rbp+37h+arg_38]
0x180026308  lea     rcx, [rbp+37h+var_88]
0x18002630c  call    ?SetGammaCorrection@LinearGradientBrush@Gdiplus@@QEAA?AW4Status@2@H@Z; Gdiplus::LinearGradientBrush::SetGammaCorrection(int)
0x180026311  mov     rbx, [rbp+37h+var_58]
0x180026315  mov     [rsp+28h], r12d
0x18002631a  mov     dword ptr [rsp+0E0h+var_C0], r13d
0x18002631f  mov     r9d, [rbp+37h+var_90]
0x180026323  mov     r8d, [rbp+37h+var_8C]
0x180026327  mov     rdx, [rbp+37h+var_80]
0x18002632b  mov     rcx, [rbx]
0x18002632e  call    cs:__imp_GdipFillRectangleI
0x180026334  test    eax, eax
0x180026336  jz      short loc_18002633B
0x180026338  mov     [rbx+8], eax
0x18002633b  lea     rcx, [rbp+37h+var_48]
0x18002633f  call    ?_Tidy@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@AEAAXXZ; std::vector<tagRGBQUAD>::_Tidy(void)
0x180026344  nop
0x180026345  lea     rcx, [rbp+37h+var_70]
0x180026349  call    ?_Tidy@?$vector@UtagRGBQUAD@@V?$allocator@UtagRGBQUAD@@@std@@@std@@AEAAXXZ; std::vector<tagRGBQUAD>::_Tidy(void)
0x18002634e  nop
0x18002634f  mov     rcx, [rbp+37h+var_80]
0x180026353  jmp     loc_1800263FF
0x180026358  movd    xmm0, edi
0x18002635c  cvtdq2ps xmm0, xmm0
0x18002635f  movss   dword ptr [rbp+37h+var_A0], xmm0
0x180026364  movd    xmm1, [rbp+37h+arg_14]
0x180026369  cvtdq2ps xmm1, xmm1
0x18002636c  movss   dword ptr [rbp+37h+var_A0+4], xmm1
0x180026371  movd    xmm0, ebx
0x180026375  cvtdq2ps xmm0, xmm0
0x180026378  movss   [rbp+37h+arg_10], xmm0
0x18002637d  movd    xmm1, [rbp+37h+arg_C]
0x180026382  cvtdq2ps xmm1, xmm1
0x180026385  movss   [rbp+37h+arg_14], xmm1
0x18002638a  mov     [rsp+0E0h+var_C0], rax; struct Gdiplus::Color *
0x18002638f  mov     r9, r14; struct Gdiplus::Color *
0x180026392  lea     r8, [rbp+37h+var_A0]; struct Gdiplus::PointF *
0x180026396  lea     rdx, [rbp+37h+arg_10]; struct Gdiplus::PointF *
0x18002639a  lea     rcx, [rbp+37h+var_88]; this
0x18002639e  call    ??0LinearGradientBrush@Gdiplus@@QEAA@AEBVPointF@1@0AEBVColor@1@1@Z; Gdiplus::LinearGradientBrush::LinearGradientBrush(Gdiplus::PointF const &,Gdiplus::PointF const &,Gdiplus::Color const &,Gdiplus::Color const &)
0x1800263a3  nop
0x1800263a4  mov     r9d, [rbp+37h+arg_30]
0x1800263a8  mov     r8, [rbp+37h+arg_28]
0x1800263ac  mov     rdx, r14
0x1800263af  lea     rcx, [rbp+37h+var_88]
0x1800263b3  call    ?SetInterpolationColors@LinearGradientBrush@Gdiplus@@QEAA?AW4Status@2@PEBVColor@2@PEBMH@Z; Gdiplus::LinearGradientBrush::SetInterpolationColors(Gdiplus::Color const *,float const *,int)
0x1800263b8  movzx   edx, [rbp+37h+arg_38]
0x1800263bc  lea     rcx, [rbp+37h+var_88]
0x1800263c0  call    ?SetGammaCorrection@LinearGradientBrush@Gdiplus@@QEAA?AW4Status@2@H@Z; Gdiplus::LinearGradientBrush::SetGammaCorrection(int)
0x1800263c5  mov     edx, [rbp+37h+arg_18]
0x1800263c8  mov     rbx, [rbp+37h+var_80]
0x1800263cc  mov     rcx, rbx
0x1800263cf  call    cs:__imp_GdipSetLineWrapMode
0x1800263d5  mov     rdi, [rbp+37h+var_58]
0x1800263d9  mov     [rsp+28h], r12d
0x1800263de  mov     dword ptr [rsp+0E0h+var_C0], r13d
0x1800263e3  mov     r9d, r15d
0x1800263e6  mov     r8d, esi
0x1800263e9  mov     rdx, rbx
0x1800263ec  mov     rcx, [rdi]
0x1800263ef  call    cs:__imp_GdipFillRectangleI
0x1800263f5  test    eax, eax
0x1800263f7  jz      short loc_1800263FC
0x1800263f9  mov     [rdi+8], eax
0x1800263fc  mov     rcx, rbx
0x1800263ff  call    cs:__imp_GdipDeleteBrush
0x180026405  nop
0x180026406  mov     rcx, [rbp+37h+var_50]; this
0x18002640a  test    rcx, rcx
0x18002640d  jz      short loc_180026414
0x18002640f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180026414  mov     rbx, [rsp+0E0h+arg_0]
0x18002641c  add     rsp, 0B0h
0x180026423  pop     r15
0x180026425  pop     r14
0x180026427  pop     r13
0x180026429  pop     r12
0x18002642b  pop     rdi
0x18002642c  pop     rsi
0x18002642d  pop     rbp
0x18002642e  retn
```
