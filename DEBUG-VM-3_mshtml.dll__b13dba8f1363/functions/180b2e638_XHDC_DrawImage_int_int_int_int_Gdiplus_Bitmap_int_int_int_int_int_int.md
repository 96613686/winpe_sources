# XHDC::DrawImage(int,int,int,int,Gdiplus::Bitmap *,int,int,int,int,int,int)

- ea: `0x180b2e638`
- end: `0x180b2ecf8`
- name: `?DrawImage@XHDC@@QEBAHHHHHPEAVBitmap@Gdiplus@@HHHHHH@Z`
- size: `1728`
- prototype: `__int64 __fastcall(XHDC *__hidden this, int, int, int, int, struct Gdiplus::Bitmap *, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1807f42e0`

## callees

- `0x1805da8b8`
- `0x180b2c680`
- `0x180b2e474`
- `0x180b2e638`
- `0x180b2f394`
- `0x180b2f524`
- `0x180b2fc28`
- `0x180b2fcc8`
- `0x180b2fd98`
- `0x180b32a60`
- `0x180b32bd0`
- `0x18109868c`
- `0x1810c2c3e`
- `0x1810c2c6e`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180b2ec0d`
- `KERNEL32!GetTickCount` at `0x180b2ec76`
- `KERNEL32!GetTickCount` at `0x180b2ec0d`
- `KERNEL32!GetTickCount` at `0x180b2ec76`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipCreateImageAttributes` at `0x180b2ea8d`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipCreateImageAttributes` at `0x180b2ea8d`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDisposeImageAttributes` at `0x180b2eca6`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDisposeImageAttributes` at `0x180b2ecbf`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDisposeImageAttributes` at `0x180b2eca6`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDisposeImageAttributes` at `0x180b2ecbf`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetImageAttributesWrapMode` at `0x180b2eaa7`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetImageAttributesWrapMode` at `0x180b2eaa7`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetPixelOffsetMode` at `0x180b2eae0`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetPixelOffsetMode` at `0x180b2eae0`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDeleteGraphics` at `0x180b2ec9c`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDeleteGraphics` at `0x180b2ecb5`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDeleteGraphics` at `0x180b2ec9c`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipDeleteGraphics` at `0x180b2ecb5`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetCompositingQuality` at `0x180b2eb12`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetCompositingQuality` at `0x180b2eb12`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipTranslateWorldTransform` at `0x180b2ebb7`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipTranslateWorldTransform` at `0x180b2ebb7`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipRotateWorldTransform` at `0x180b2ebda`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipRotateWorldTransform` at `0x180b2ebda`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetInterpolationMode` at `0x180b2eb61`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetInterpolationMode` at `0x180b2eb61`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetCompositingMode` at `0x180b2eaf9`
- `ext-ms-win-gdi-gdiplus-l1-1-0!GdipSetCompositingMode` at `0x180b2eaf9`

## pseudocode

```c
_BOOL8 __fastcall XHDC::DrawImage(
        HDC *this,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int a5,
        struct Gdiplus::Bitmap *a6,
        int a7,
        float a8,
        int a9,
        int a10,
        unsigned int a11,
        int a12)
{
  int v14; // r12d
  int v15; // r15d
  unsigned int v16; // r14d
  int v17; // r13d
  const struct tagSIZE *OffsetOnly; // rax
  LONG cx; // ecx
  LONG cy; // eax
  unsigned int v21; // r8d
  int v22; // edi
  int v23; // r13d
  int v24; // ecx
  unsigned int v25; // edx
  int v26; // esi
  CWorldTransform *v27; // rcx
  float v28; // xmm6_4
  float v29; // xmm0_4
  float v30; // xmm7_4
  float v31; // xmm9_4
  float v32; // xmm10_4
  int v33; // r8d
  int v34; // eax
  unsigned int v35; // r10d
  int v36; // r11d
  int v37; // r14d
  int v38; // esi
  int v39; // eax
  int v40; // r10d
  int v41; // edi
  int v42; // r11d
  int v43; // ebx
  float v44; // xmm2_4
  float v45; // xmm6_4
  float v46; // xmm0_4
  int v47; // r12d
  float v48; // xmm0_4
  int v49; // r15d
  __int64 v50; // rdx
  float v51; // xmm6_4
  float v52; // xmm7_4
  int v53; // eax
  int v54; // ecx
  unsigned int v55; // eax
  unsigned int v56; // eax
  unsigned int v57; // eax
  int v58; // eax
  __int64 v59; // rdx
  unsigned int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // r8
  unsigned int v63; // eax
  __int64 v64; // rdx
  unsigned int v65; // eax
  DWORD TickCount; // ebx
  int v67; // edi
  DWORD v68; // eax
  unsigned int v69; // ecx
  float v71[2]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v72; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v73; // [rsp+78h] [rbp-90h]
  int v74; // [rsp+7Ch] [rbp-8Ch]
  int v75; // [rsp+80h] [rbp-88h] BYREF
  int v76; // [rsp+84h] [rbp-84h]
  int v77; // [rsp+88h] [rbp-80h]
  unsigned __int64 v78; // [rsp+90h] [rbp-78h] BYREF
  int v79; // [rsp+98h] [rbp-70h]
  int v80; // [rsp+9Ch] [rbp-6Ch]
  unsigned int v81; // [rsp+A0h] [rbp-68h]
  unsigned __int64 v82; // [rsp+A4h] [rbp-64h]
  int v83; // [rsp+ACh] [rbp-5Ch]
  int TrivialRotationAngle; // [rsp+B0h] [rbp-58h]
  __int64 v85; // [rsp+B8h] [rbp-50h] BYREF
  int v86; // [rsp+C0h] [rbp-48h]
  unsigned __int64 v87; // [rsp+C8h] [rbp-40h] BYREF
  int v88; // [rsp+D0h] [rbp-38h]
  int v89; // [rsp+D4h] [rbp-34h]

  v14 = a4;
  v15 = a5;
  v16 = a2 + a4;
  v17 = a3 + a5;
  v79 = a2 + a4;
  v80 = a3 + a5;
  v78 = __PAIR64__(a3, a2);
  if ( a4 <= 0 || a5 <= 0 )
    return 0;
  OffsetOnly = XHDC::GetOffsetOnly((XHDC *)this);
  if ( OffsetOnly )
  {
    cx = OffsetOnly->cx;
    TrivialRotationAngle = 0;
    cy = OffsetOnly->cy;
    v21 = cx + a2;
    *(float *)&v75 = a8;
    v22 = a10;
    v23 = cx + v16;
    v24 = a3 + a5;
    v25 = cy + a3;
    LODWORD(v72) = v21;
    v26 = a9;
    v81 = v25;
    v83 = cy + v24;
    v76 = a9;
    v82 = __PAIR64__(v25, v21);
    LODWORD(v71[0]) = a10;
    v77 = a7;
  }
  else
  {
    v27 = (CWorldTransform *)this[14];
    v72 = __PAIR64__(a3, a2);
    v73 = v16;
    v74 = v17;
    v71[0] = 1.0;
    *(float *)&v75 = 1.0;
    CWorldTransform::GetScales(v27, v71, (float *)&v75);
    v28 = v71[0];
    v29 = floorf_0((float)((float)a7 * v71[0]) + 0.5);
    v30 = *(float *)&v75;
    v31 = v29;
    v32 = floorf_0((float)((float)SLODWORD(a8) * *(float *)&v75) + 0.5);
    v26 = (int)floorf_0((float)((float)a9 * v28) + 0.5);
    if ( v26 < 1 )
      v26 = 1;
    v76 = v26;
    v22 = (int)floorf_0((float)((float)a10 * v30) + 0.5);
    if ( v22 < 1 )
      v22 = 1;
    LODWORD(v71[0]) = v22;
    v14 = (int)floorf_0((float)((float)v14 * v28) + 0.5);
    if ( v14 < 1 )
      v14 = 1;
    v15 = (int)floorf_0((float)((float)a5 * v30) + 0.5);
    if ( v15 < 1 )
      v15 = 1;
    XHDC::TransformRect((XHDC *)this, (struct CRect *)&v72);
    if ( !(unsigned int)XHDC::TransformRect((XHDC *)this, (struct CRect *)&v78) )
      return 0;
    v23 = v79;
    v33 = v80;
    v82 = v78;
    v77 = (int)v31;
    v75 = (int)v32;
    if ( (int)v78 + 1 > v79 )
      v23 = v78 + 1;
    if ( HIDWORD(v78) + 1 > v80 )
      v33 = HIDWORD(v78) + 1;
    v83 = v33;
    TrivialRotationAngle = XHDC::GetTrivialRotationAngle((XHDC *)this);
    v81 = HIDWORD(v72);
  }
  if ( !v26 || !v22 || !v14 || !a11 || !a12 )
    return 0;
  v34 = GreatestCommonDivisor<int>(a11, (unsigned int)v26);
  v37 = v36 / v34;
  v38 = v26 / v34;
  v39 = GreatestCommonDivisor<int>(v35, (unsigned int)v22);
  v41 = v40 / v39;
  v43 = SLODWORD(v71[0]) / v39;
  v44 = (float)v76 / (float)v42;
  v45 = (float)SLODWORD(v71[0]) / (float)v40;
  v76 = (int)(float)((float)v77 / v44) - (int)(float)((float)v77 / v44) % v37;
  LODWORD(v71[0]) = (int)(float)((float)v75 / v45) - (int)(float)((float)v75 / v45) % (v40 / v39);
  v46 = ceilf_0((float)v76 * v44);
  v47 = v37 * ((v14 + v38 - (int)v46 + v77 - 1) / v38);
  v48 = ceilf_0((float)SLODWORD(v71[0]) * v45);
  v85 = 0;
  v49 = v41 * ((v15 + v43 - (int)v48 + v75 - 1) / v43);
  *(float *)&v78 = (float)((int)v72 + v76 * v38 / v37 - v77);
  *((float *)&v78 + 1) = (float)(int)(v81 + LODWORD(v71[0]) * v43 / v41 - v75);
  v50 = (unsigned int)(v49 >> 31);
  LODWORD(v50) = v49 % v41;
  v51 = (float)(v38 * (v47 / v37));
  *(float *)&v79 = v51;
  v52 = (float)(v43 * (v49 / v41));
  *(float *)&v80 = v52;
  v86 = GdipCreateImageAttributes(&v85, v50);
  v53 = GdipSetImageAttributesWrapMode(v85, 3, 4278190080LL);
  v54 = v86;
  if ( v53 )
    v54 = v53;
  v86 = v54;
  Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)&v72, this[4]);
  Gdiplus::Graphics::SetPageUnit(&v72);
  v55 = GdipSetPixelOffsetMode(v72, 4);
  Gdiplus::Graphics::SetStatus(&v72, v55);
  v56 = GdipSetCompositingMode(v72, 0);
  Gdiplus::Graphics::SetStatus(&v72, v56);
  v57 = GdipSetCompositingQuality(v72, 4);
  Gdiplus::Graphics::SetStatus(&v72, v57);
  v58 = *((_DWORD *)this + 56);
  v59 = 5;
  if ( (v58 & 1) != 0 && (v51 != (float)v47 || v52 != (float)v49) )
    v59 = (2 * (~(_BYTE)v58 & 2)) | 3u;
  v60 = GdipSetInterpolationMode(v72, v59);
  Gdiplus::Graphics::SetStatus(&v72, v60);
  v87 = v82;
  v89 = v83 - HIDWORD(v82);
  v88 = v23 - v82;
  Gdiplus::Graphics::SetClip(&v72, &v87);
  if ( TrivialRotationAngle )
  {
    v63 = GdipTranslateWorldTransform(v72, v61, v62, 0);
    Gdiplus::Graphics::SetStatus(&v72, v63);
    v65 = GdipRotateWorldTransform(v72, v64, 0);
    Gdiplus::Graphics::SetStatus(&v72, v65);
    v78 = 0;
  }
  if ( !XHDC::ValidateImageDestArea((XHDC *)this, (int)v51, (int)v52) )
  {
    GdipDeleteGraphics(v72);
    GdipDisposeImageAttributes(v85);
    return 0;
  }
  TickCount = GetTickCount();
  do
  {
    v67 = Gdiplus::Graphics::DrawImage(&v72, a6, &v78);
    if ( v67 != 4 )
      break;
    v68 = GetTickCount();
    v69 = v68 - TickCount - 1;
    if ( v68 >= TickCount )
      v69 = v68 - TickCount;
  }
  while ( v69 < 0xFA0 );
  GdipDeleteGraphics(v72);
  GdipDisposeImageAttributes(v85);
  return v67 == 0;
}

```

## disassembly

```asm
0x180b2e638  mov     rax, rsp
0x180b2e63b  mov     [rax+20h], r9d
0x180b2e63f  mov     [rax+18h], r8d
0x180b2e643  mov     [rax+10h], edx
0x180b2e646  mov     [rax+8], rcx
0x180b2e64a  push    rbp
0x180b2e64b  push    rbx
0x180b2e64c  push    rsi
0x180b2e64d  push    rdi
0x180b2e64e  push    r12
0x180b2e650  push    r13
0x180b2e652  push    r14
0x180b2e654  push    r15
0x180b2e656  lea     rbp, [rax-68h]
0x180b2e65a  sub     rsp, 128h
0x180b2e661  mov     edi, [rbp+60h+arg_8]
0x180b2e664  mov     esi, [rbp+60h+arg_10]
0x180b2e66a  mov     r12d, [rbp+60h+arg_18]
0x180b2e671  mov     r15d, [rbp+60h+arg_20]
0x180b2e678  movaps  xmmword ptr [rax-58h], xmm6
0x180b2e67c  movaps  xmmword ptr [rax-68h], xmm7
0x180b2e680  movaps  xmmword ptr [rax-78h], xmm8
0x180b2e685  lea     r14d, [rdi+r12]
0x180b2e689  movaps  xmmword ptr [rax-88h], xmm9
0x180b2e691  lea     r13d, [rsi+r15]
0x180b2e695  mov     [rbp+60h+var_D0], r14d
0x180b2e699  mov     [rbp+60h+var_CC], r13d
0x180b2e69d  movaps  xmmword ptr [rax-98h], xmm10
0x180b2e6a5  mov     dword ptr [rbp+60h+var_D8], edi
0x180b2e6a8  mov     dword ptr [rbp+60h+var_D8+4], esi
0x180b2e6ab  test    r12d, r12d
0x180b2e6ae  jle     loc_180B2ECC5
0x180b2e6b4  test    r15d, r15d
0x180b2e6b7  jle     loc_180B2ECC5
0x180b2e6bd  mov     rbx, [rbp+60h+arg_0]
0x180b2e6c1  mov     rcx, rbx; this
0x180b2e6c4  call    ?GetOffsetOnly@XHDC@@QEBAPEBUtagSIZE@@XZ; XHDC::GetOffsetOnly(void)
0x180b2e6c9  mov     rdx, rax
0x180b2e6cc  test    rax, rax
0x180b2e6cf  jz      short loc_180B2E72E
0x180b2e6d1  mov     ecx, [rdx]
0x180b2e6d3  xor     eax, eax
0x180b2e6d5  mov     r10d, [rbp+60h+arg_38]
0x180b2e6dc  mov     [rbp+60h+var_B8], eax
0x180b2e6df  mov     eax, [rdx+4]
0x180b2e6e2  lea     r8d, [rcx+rdi]
0x180b2e6e6  mov     [rsp+160h+var_E8], r10d
0x180b2e6eb  mov     edi, [rbp+60h+arg_48]
0x180b2e6f1  lea     r13d, [rcx+r14]
0x180b2e6f5  mov     r10d, [rbp+60h+arg_30]
0x180b2e6fc  lea     ecx, [rsi+r15]
0x180b2e700  lea     edx, [rax+rsi]
0x180b2e703  mov     [rsp+160h+var_F8], r8d
0x180b2e708  mov     esi, [rbp+60h+arg_40]
0x180b2e70e  add     ecx, eax
0x180b2e710  mov     [rbp+60h+var_C8], edx
0x180b2e713  mov     dword ptr [rbp+60h+var_C4+4], edx
0x180b2e716  mov     [rbp+60h+var_BC], ecx
0x180b2e719  mov     [rsp+160h+var_E4], esi
0x180b2e71d  mov     dword ptr [rbp+60h+var_C4], r8d
0x180b2e721  mov     [rsp+160h+var_100], edi
0x180b2e725  mov     [rbp+60h+var_E0], r10d
0x180b2e729  jmp     loc_180B2E8D4
0x180b2e72e  mov     rcx, [rbx+70h]; this
0x180b2e732  lea     r8, [rsp+160h+var_E8]; float *
0x180b2e737  lea     rdx, [rsp+160h+var_100]; float *
0x180b2e73c  mov     [rsp+160h+var_F8], edi
0x180b2e740  mov     [rsp+160h+var_F4], esi
0x180b2e744  mov     [rsp+160h+var_F0], r14d
0x180b2e749  mov     [rsp+160h+var_EC], r13d
0x180b2e74e  mov     [rsp+160h+var_100], 3F800000h
0x180b2e756  mov     [rsp+160h+var_E8], 3F800000h
0x180b2e75e  call    ?GetScales@CWorldTransform@@QEBAXPEAM0@Z; CWorldTransform::GetScales(float *,float *)
0x180b2e763  movd    xmm0, [rbp+60h+arg_30]
0x180b2e76b  movss   xmm6, [rsp+160h+var_100]
0x180b2e771  movss   xmm8, cs:__real@3f000000
0x180b2e77a  cvtdq2ps xmm0, xmm0
0x180b2e77d  mulss   xmm0, xmm6
0x180b2e781  addss   xmm0, xmm8; X
0x180b2e786  call    floorf_0
0x180b2e78b  movss   xmm7, [rsp+160h+var_E8]
0x180b2e791  movaps  xmm9, xmm0
0x180b2e795  movd    xmm0, [rbp+60h+arg_38]
0x180b2e79d  cvtdq2ps xmm0, xmm0
0x180b2e7a0  mulss   xmm0, xmm7
0x180b2e7a4  addss   xmm0, xmm8; X
0x180b2e7a9  call    floorf_0
0x180b2e7ae  movaps  xmm10, xmm0
0x180b2e7b2  movd    xmm0, [rbp+60h+arg_40]
0x180b2e7ba  cvtdq2ps xmm0, xmm0
0x180b2e7bd  mulss   xmm0, xmm6
0x180b2e7c1  addss   xmm0, xmm8; X
0x180b2e7c6  call    floorf_0
0x180b2e7cb  cvttss2si esi, xmm0
0x180b2e7cf  mov     r14d, 1
0x180b2e7d5  movd    xmm0, [rbp+60h+arg_48]
0x180b2e7dd  cvtdq2ps xmm0, xmm0
0x180b2e7e0  cmp     esi, r14d
0x180b2e7e3  cmovl   esi, r14d
0x180b2e7e7  mov     [rsp+160h+var_E4], esi
0x180b2e7eb  mulss   xmm0, xmm7
0x180b2e7ef  addss   xmm0, xmm8; X
0x180b2e7f4  call    floorf_0
0x180b2e7f9  cvttss2si edi, xmm0
0x180b2e7fd  movd    xmm0, r12d
0x180b2e802  cvtdq2ps xmm0, xmm0
0x180b2e805  cmp     edi, r14d
0x180b2e808  cmovl   edi, r14d
0x180b2e80c  mov     [rsp+160h+var_100], edi
0x180b2e810  mulss   xmm0, xmm6
0x180b2e814  addss   xmm0, xmm8; X
0x180b2e819  call    floorf_0
0x180b2e81e  cvttss2si r12d, xmm0
0x180b2e823  movd    xmm0, r15d
0x180b2e828  cvtdq2ps xmm0, xmm0
0x180b2e82b  cmp     r12d, r14d
0x180b2e82e  cmovl   r12d, r14d
0x180b2e832  mulss   xmm0, xmm7
0x180b2e836  addss   xmm0, xmm8; X
0x180b2e83b  call    floorf_0
0x180b2e840  cvttss2si r15d, xmm0
0x180b2e845  lea     rdx, [rsp+160h+var_F8]; struct CRect *
0x180b2e84a  mov     rcx, rbx; this
0x180b2e84d  cmp     r15d, r14d
0x180b2e850  cmovl   r15d, r14d
0x180b2e854  call    ?TransformRect@XHDC@@IEBAHPEAVCRect@@@Z; XHDC::TransformRect(CRect *)
0x180b2e859  mov     rax, qword ptr [rsp+160h+var_F8]
0x180b2e85e  lea     rdx, [rbp+60h+var_D8]; struct CRect *
0x180b2e862  mov     rcx, rbx; this
0x180b2e865  mov     qword ptr [rsp+160h+var_F8], rax
0x180b2e86a  call    ?TransformRect@XHDC@@IEBAHPEAVCRect@@@Z; XHDC::TransformRect(CRect *)
0x180b2e86f  test    eax, eax
0x180b2e871  jz      loc_180B2ECC5
0x180b2e877  mov     r9d, dword ptr [rbp+60h+var_D8]
0x180b2e87b  mov     rcx, rbx; this
0x180b2e87e  mov     r13d, [rbp+60h+var_D0]
0x180b2e882  mov     r8d, [rbp+60h+var_CC]
0x180b2e886  cvttss2si eax, xmm9
0x180b2e88b  mov     dword ptr [rbp+60h+var_C4], r9d
0x180b2e88f  mov     [rbp+60h+var_E0], eax
0x180b2e892  cvttss2si eax, xmm10
0x180b2e897  mov     [rsp+160h+var_E8], eax
0x180b2e89b  lea     eax, [r9+1]
0x180b2e89f  mov     r9d, dword ptr [rbp+60h+var_D8+4]
0x180b2e8a3  cmp     eax, r13d
0x180b2e8a6  mov     dword ptr [rbp+60h+var_C4+4], r9d
0x180b2e8aa  cmovg   r13d, eax
0x180b2e8ae  lea     eax, [r9+1]
0x180b2e8b2  cmp     eax, r8d
0x180b2e8b5  cmovg   r8d, eax
0x180b2e8b9  mov     [rbp+60h+var_BC], r8d
0x180b2e8bd  call    ?GetTrivialRotationAngle@XHDC@@QEBAHXZ; XHDC::GetTrivialRotationAngle(void)
0x180b2e8c2  mov     [rbp+60h+var_B8], eax
0x180b2e8c5  mov     eax, [rsp+160h+var_F4]
0x180b2e8c9  mov     [rbp+60h+var_C8], eax
0x180b2e8cc  mov     eax, [rsp+160h+var_F8]
0x180b2e8d0  mov     [rsp+160h+var_F8], eax
0x180b2e8d4  test    esi, esi
0x180b2e8d6  jz      loc_180B2ECC5
0x180b2e8dc  test    edi, edi
0x180b2e8de  jz      loc_180B2ECC5
0x180b2e8e4  test    r12d, r12d
0x180b2e8e7  jz      loc_180B2ECC5
0x180b2e8ed  test    r15d, r15d
0x180b2e8f0  jz      loc_180B2ECC5
0x180b2e8f6  mov     r11d, [rbp+60h+arg_50]
0x180b2e8fd  test    r11d, r11d
0x180b2e900  jz      loc_180B2ECC5
0x180b2e906  mov     r10d, [rbp+60h+arg_58]
0x180b2e90d  test    r10d, r10d
0x180b2e910  jz      loc_180B2ECC5
0x180b2e916  mov     edx, esi
0x180b2e918  mov     ecx, r11d
0x180b2e91b  call    ??$GreatestCommonDivisor@H@@YAHHH@Z; GreatestCommonDivisor<int>(int,int)
0x180b2e920  mov     r9d, eax
0x180b2e923  mov     ecx, r10d
0x180b2e926  mov     eax, r11d
0x180b2e929  cdq
0x180b2e92a  idiv    r9d
0x180b2e92d  mov     r14d, eax
0x180b2e930  mov     eax, esi
0x180b2e932  cdq
0x180b2e933  idiv    r9d
0x180b2e936  mov     edx, edi
0x180b2e938  mov     esi, eax
0x180b2e93a  call    ??$GreatestCommonDivisor@H@@YAHHH@Z; GreatestCommonDivisor<int>(int,int)
0x180b2e93f  mov     ecx, [rsp+160h+var_100]
0x180b2e943  mov     r9d, eax
0x180b2e946  movd    xmm2, [rsp+160h+var_E4]
0x180b2e94c  mov     eax, r10d
0x180b2e94f  movd    xmm1, [rbp+60h+var_E0]
0x180b2e954  cdq
0x180b2e955  idiv    r9d
0x180b2e958  movd    xmm6, ecx
0x180b2e95c  mov     edi, eax
0x180b2e95e  movd    xmm0, r11d
0x180b2e963  cvtdq2ps xmm0, xmm0
0x180b2e966  mov     eax, ecx
0x180b2e968  cdq
0x180b2e969  idiv    r9d
0x180b2e96c  cvtdq2ps xmm2, xmm2
0x180b2e96f  mov     ebx, eax
0x180b2e971  cvtdq2ps xmm1, xmm1
0x180b2e974  divss   xmm2, xmm0
0x180b2e978  movd    xmm0, r10d
0x180b2e97d  cvtdq2ps xmm0, xmm0
0x180b2e980  divss   xmm1, xmm2
0x180b2e984  cvtdq2ps xmm6, xmm6
0x180b2e987  cvttss2si ecx, xmm1
0x180b2e98b  divss   xmm6, xmm0
0x180b2e98f  mov     eax, ecx
0x180b2e991  cdq
0x180b2e992  movd    xmm0, [rsp+160h+var_E8]
0x180b2e998  idiv    r14d
0x180b2e99b  cvtdq2ps xmm0, xmm0
0x180b2e99e  sub     ecx, edx
0x180b2e9a0  mov     [rsp+160h+var_E4], ecx
0x180b2e9a4  divss   xmm0, xmm6
0x180b2e9a8  cvttss2si r8d, xmm0
0x180b2e9ad  movd    xmm0, ecx
0x180b2e9b1  mov     eax, r8d
0x180b2e9b4  cdq
0x180b2e9b5  idiv    edi
0x180b2e9b7  cvtdq2ps xmm0, xmm0
0x180b2e9ba  sub     r8d, edx
0x180b2e9bd  mov     [rsp+160h+var_100], r8d
0x180b2e9c2  mulss   xmm0, xmm2; X
0x180b2e9c6  call    ceilf_0
0x180b2e9cb  cvttss2si eax, xmm0
0x180b2e9cf  mov     ecx, esi
0x180b2e9d1  movd    xmm0, [rsp+160h+var_100]
0x180b2e9d7  sub     ecx, eax
0x180b2e9d9  mov     eax, [rbp+60h+var_E0]
0x180b2e9dc  dec     eax
0x180b2e9de  add     ecx, r12d
0x180b2e9e1  add     eax, ecx
0x180b2e9e3  cdq
0x180b2e9e4  idiv    esi
0x180b2e9e6  cvtdq2ps xmm0, xmm0
0x180b2e9e9  mov     r12d, eax
0x180b2e9ec  imul    r12d, r14d
0x180b2e9f0  mulss   xmm0, xmm6; X
0x180b2e9f4  call    ceilf_0
0x180b2e9f9  cvttss2si ecx, xmm0
0x180b2e9fd  mov     edx, ebx
0x180b2e9ff  sub     edx, ecx
0x180b2ea01  mov     ecx, [rsp+160h+var_E8]
0x180b2ea05  add     edx, r15d
0x180b2ea08  lea     eax, [rcx-1]
0x180b2ea0b  add     eax, edx
0x180b2ea0d  cdq
0x180b2ea0e  idiv    ebx
0x180b2ea10  mov     r15d, eax
0x180b2ea13  mov     [rbp+60h+var_B0], 0
0x180b2ea1b  mov     eax, esi
0x180b2ea1d  imul    r15d, edi
0x180b2ea21  imul    eax, [rsp+160h+var_E4]
0x180b2ea26  cdq
0x180b2ea27  idiv    r14d
0x180b2ea2a  sub     eax, [rbp+60h+var_E0]
0x180b2ea2d  add     eax, [rsp+160h+var_F8]
0x180b2ea31  movd    xmm8, eax
0x180b2ea36  mov     eax, ebx
0x180b2ea38  imul    eax, [rsp+160h+var_100]
0x180b2ea3d  cvtdq2ps xmm8, xmm8
0x180b2ea41  cdq
0x180b2ea42  idiv    edi
0x180b2ea44  movss   dword ptr [rbp+60h+var_D8], xmm8
0x180b2ea4a  sub     eax, ecx
0x180b2ea4c  lea     rcx, [rbp+60h+var_B0]
0x180b2ea50  add     eax, [rbp+60h+var_C8]
0x180b2ea53  movd    xmm9, eax
0x180b2ea58  mov     eax, r12d
0x180b2ea5b  cdq
0x180b2ea5c  idiv    r14d
0x180b2ea5f  cvtdq2ps xmm9, xmm9
0x180b2ea63  imul    eax, esi
0x180b2ea66  movss   dword ptr [rbp+60h+var_D8+4], xmm9
0x180b2ea6c  movd    xmm6, eax
0x180b2ea70  mov     eax, r15d
0x180b2ea73  cdq
0x180b2ea74  idiv    edi
0x180b2ea76  cvtdq2ps xmm6, xmm6
0x180b2ea79  imul    eax, ebx
0x180b2ea7c  movss   [rbp+60h+var_D0], xmm6
0x180b2ea81  movd    xmm7, eax
0x180b2ea85  cvtdq2ps xmm7, xmm7
0x180b2ea88  movss   [rbp+60h+var_CC], xmm7
0x180b2ea8d  call    cs:__imp_GdipCreateImageAttributes
0x180b2ea93  mov     rcx, [rbp+60h+var_B0]
0x180b2ea97  xor     r9d, r9d
0x180b2ea9a  mov     r8d, 0FF000000h
0x180b2eaa0  mov     [rbp+60h+var_A8], eax
0x180b2eaa3  lea     edx, [r9+3]
0x180b2eaa7  call    cs:__imp_GdipSetImageAttributesWrapMode
0x180b2eaad  mov     ecx, [rbp+60h+var_A8]
0x180b2eab0  test    eax, eax
0x180b2eab2  mov     rbx, [rbp+60h+arg_0]
0x180b2eab6  cmovnz  ecx, eax
0x180b2eab9  mov     [rbp+60h+var_A8], ecx
  ... truncated ...
```
