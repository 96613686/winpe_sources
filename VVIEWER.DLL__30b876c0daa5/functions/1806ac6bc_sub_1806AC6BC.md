# sub_1806AC6BC

- ea: `0x1806ac6bc`
- end: `0x1806ace6c`
- name: `sub_1806AC6BC`
- size: `1968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1806ac230`

## callees

- `0x1800164c0`
- `0x18007412c`
- `0x1800c4b08`
- `0x1805e796c`
- `0x1806a7c30`
- `0x1806ac6bc`
- `0x1806aeca8`
- `0x1806aecf0`
- `0x1809c10de`
- `0x1809c1263`
- `0x1809c12ab`
- `0x1809c130b`

## import_xrefs

- `gdiplus!GdipGetPenUnit` at `0x1806ac75d`
- `gdiplus!GdipGetPenUnit` at `0x1806ac75d`
- `gdiplus!GdipGetPenWidth` at `0x1806ac7a3`
- `gdiplus!GdipGetPenWidth` at `0x1806ac7a3`
- `gdiplus!GdipSetMatrixElements` at `0x1806acc31`
- `gdiplus!GdipSetMatrixElements` at `0x1806acc31`
- `gdiplus!GdipIsVisibleClipEmpty` at `0x1806ac965`
- `gdiplus!GdipIsVisibleClipEmpty` at `0x1806ac965`
- `gdiplus!GdipGetVisibleClipBounds` at `0x1806ac99b`
- `gdiplus!GdipGetVisibleClipBounds` at `0x1806ac99b`
- `gdiplus!GdipDrawImageRectRect` at `0x1806acd83`
- `gdiplus!GdipDrawImageRectRect` at `0x1806acd83`
- `gdiplus!GdipSetPageUnit` at `0x1806acb4d`
- `gdiplus!GdipSetPageUnit` at `0x1806acb4d`
- `gdiplus!GdipGetWorldTransform` at `0x1806ac7ed`
- `gdiplus!GdipGetWorldTransform` at `0x1806ac7ed`
- `gdiplus!GdipSetWorldTransform` at `0x1806acc4c`
- `gdiplus!GdipSetWorldTransform` at `0x1806acda7`
- `gdiplus!GdipSetWorldTransform` at `0x1806acc4c`
- `gdiplus!GdipSetWorldTransform` at `0x1806acda7`
- `gdiplus!GdipSetSmoothingMode` at `0x1806acc87`
- `gdiplus!GdipSetSmoothingMode` at `0x1806acc87`
- `gdiplus!GdipGetSmoothingMode` at `0x1806acc6d`
- `gdiplus!GdipGetSmoothingMode` at `0x1806acc6d`
- `gdiplus!GdipSetInterpolationMode` at `0x1806acd19`
- `gdiplus!GdipSetInterpolationMode` at `0x1806acd19`
- `gdiplus!GdipGetInterpolationMode` at `0x1806accff`
- `gdiplus!GdipGetInterpolationMode` at `0x1806accff`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1806acb12`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x1806acb12`
- `gdiplus!GdipGetPathWorldBounds` at `0x1806ac942`
- `gdiplus!GdipGetPathWorldBounds` at `0x1806ac942`
- `gdiplus!GdipDrawPath` at `0x1806acca3`
- `gdiplus!GdipDrawPath` at `0x1806acdda`
- `gdiplus!GdipDrawPath` at `0x1806acca3`
- `gdiplus!GdipDrawPath` at `0x1806acdda`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1806acb30`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1806acb30`
- `gdiplus!GdipGetMatrixElements` at `0x1806ac819`
- `gdiplus!GdipGetMatrixElements` at `0x1806acb6d`
- `gdiplus!GdipGetMatrixElements` at `0x1806ac819`
- `gdiplus!GdipGetMatrixElements` at `0x1806acb6d`
- `gdiplus!GdipDeleteMatrix` at `0x1806acdb6`
- `gdiplus!GdipDeleteMatrix` at `0x1806acded`
- `gdiplus!GdipDeleteMatrix` at `0x1806acdb6`
- `gdiplus!GdipDeleteMatrix` at `0x1806acded`
- `gdiplus!GdipCreateMatrix2` at `0x1806acc08`
- `gdiplus!GdipCreateMatrix2` at `0x1806acc08`
- `gdiplus!GdipCreateMatrix` at `0x1806ac7d3`
- `gdiplus!GdipCreateMatrix` at `0x1806ac7d3`
- `gdiplus!GdipDeleteGraphics` at `0x1806accc9`
- `gdiplus!GdipDeleteGraphics` at `0x1806accc9`
- `gdiplus!GdipDisposeImage` at `0x1806acdc9`
- `gdiplus!GdipDisposeImage` at `0x1806acdc9`

## pseudocode

```c
void __fastcall sub_1806AC6BC(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  char v7; // al
  unsigned int PenUnit; // eax
  bool v9; // al
  unsigned int PenWidth; // eax
  unsigned int v11; // eax
  unsigned int WorldTransform; // eax
  __int64 v13; // rbx
  unsigned int MatrixElements; // eax
  float v15; // xmm1_4
  float v16; // xmm0_4
  float v17; // xmm2_4
  float v18; // xmm3_4
  double v19; // xmm7_8
  double v20; // xmm9_8
  double v21; // xmm9_8
  bool v22; // cf
  bool v23; // zf
  float v24; // xmm13_4
  unsigned int PathWorldBounds; // eax
  unsigned int IsVisibleClipEmpty; // eax
  unsigned int VisibleClipBounds; // eax
  float v28; // xmm12_4
  float v29; // xmm8_4
  float v30; // xmm11_4
  float v31; // xmm9_4
  float v32; // xmm3_4
  float v33; // xmm1_4
  unsigned int v34; // edi
  unsigned int v35; // ebx
  unsigned int v36; // eax
  unsigned int ImageGraphicsContext; // eax
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rcx
  unsigned int v42; // eax
  unsigned int Matrix2; // eax
  __int64 v44; // rdx
  unsigned int v45; // eax
  __int64 v46; // rbx
  unsigned int SmoothingMode; // eax
  unsigned int v48; // eax
  unsigned int InterpolationMode; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  __int64 v52; // [rsp+78h] [rbp-90h] BYREF
  __int64 v53; // [rsp+80h] [rbp-88h] BYREF
  __int64 v54; // [rsp+88h] [rbp-80h]
  __int64 pExceptionObject; // [rsp+90h] [rbp-78h] BYREF
  __int64 v56; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v57[24]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v58; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v59; // [rsp+C0h] [rbp-48h]
  __int64 v60; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v61; // [rsp+D0h] [rbp-38h]
  __int64 v62; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v63[8]; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v64; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v65[8]; // [rsp+F0h] [rbp-18h] BYREF
  __int128 v66; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v67; // [rsp+108h] [rbp+0h]
  float v68; // [rsp+200h] [rbp+F8h] BYREF

  if ( a4 || (byte_181090000 < 0 ? (v7 = sub_1800C4B08(&byte_181090000)) : (v7 = byte_181090000 != 0), !v7) )
  {
    v9 = 0;
  }
  else
  {
    v68 = 0.0;
    PenUnit = GdipGetPenUnit(a2, &v68);
    sub_1805E796C(PenUnit, 39081232);
    v9 = LODWORD(v68) == 0;
  }
  v52 = 0;
  if ( !v9 )
    goto LABEL_40;
  v68 = 0.0;
  PenWidth = GdipGetPenWidth(a2, &v68);
  sub_1805E796C(PenWidth, 39081233);
  v11 = GdipCreateMatrix(&v52);
  sub_1805E796C(v11, 39081234);
  WorldTransform = GdipGetWorldTransform(a1, v52);
  sub_1805E796C(WorldTransform, 39081235);
  v13 = v52;
  if ( v52 )
  {
    MatrixElements = GdipGetMatrixElements(v52, v57);
    sub_1805E796C(MatrixElements, 38897232);
    v15 = *(float *)v57;
    v67 = *(_QWORD *)&v57[16];
    v13 = v52;
    LODWORD(v16) = _mm_shuffle_ps(*(__m128 *)v57, *(__m128 *)v57, 255).m128_u32[0];
    LODWORD(v17) = _mm_shuffle_ps(*(__m128 *)v57, *(__m128 *)v57, 170).m128_u32[0];
    LODWORD(v18) = _mm_shuffle_ps(*(__m128 *)v57, *(__m128 *)v57, 85).m128_u32[0];
  }
  else
  {
    v18 = 0.0;
    v17 = 0.0;
    v16 = 1.0;
    v15 = 1.0;
  }
  v19 = v68;
  v20 = sqrt(v16 * v16 + v18 * v18) * v19;
  v21 = fmin(v20, sqrt(v17 * v17 + v15 * v15) * v19);
  if ( v21 > 0.0 )
  {
    if ( dclass(v21) == 1 )
    {
      v22 = v21 > 1.0;
      v23 = v21 == 1.0;
    }
    else
    {
      v22 = v21 - 1.0 > -1.000000003627494e-15;
      v23 = v21 - 1.0 == -1.000000003627494e-15;
    }
    if ( !v22 && !v23 )
    {
      v24 = 2.0 / v21;
      v54 = 0;
      v53 = 0;
      PathWorldBounds = GdipGetPathWorldBounds(a3, &v53, v13, a2);
      sub_1805E796C(PathWorldBounds, 39081236);
      v68 = 0.0;
      IsVisibleClipEmpty = GdipIsVisibleClipEmpty(a1, &v68);
      sub_1805E796C(IsVisibleClipEmpty, 39081237);
      if ( v68 == 0.0 )
      {
        v59 = 0;
        v58 = 0;
        VisibleClipBounds = GdipGetVisibleClipBounds(a1, &v58);
        sub_1805E796C(VisibleClipBounds, 39081238);
        v28 = *(float *)&v53;
        v29 = *(float *)&v54;
        if ( *(float *)&v58 > *(float *)&v53 )
        {
          v29 = *(float *)&v54 - (float)(*(float *)&v58 - *(float *)&v53);
          *(float *)&v54 = v29;
          v28 = *(float *)&v58;
          LODWORD(v53) = v58;
        }
        v30 = *((float *)&v53 + 1);
        v31 = *((float *)&v54 + 1);
        if ( *((float *)&v58 + 1) > *((float *)&v53 + 1) )
        {
          v31 = *((float *)&v54 + 1) - (float)(*((float *)&v58 + 1) - *((float *)&v53 + 1));
          *((float *)&v54 + 1) = v31;
          v30 = *((float *)&v58 + 1);
          HIDWORD(v53) = HIDWORD(v58);
        }
        v32 = *(float *)&v59 + *(float *)&v58;
        if ( (float)(v29 + v28) > (float)(*(float *)&v59 + *(float *)&v58) )
        {
          v29 = v32 - v28;
          *(float *)&v54 = v32 - v28;
        }
        v33 = *((float *)&v59 + 1) + *((float *)&v58 + 1);
        if ( (float)(v31 + v30) > (float)(*((float *)&v59 + 1) + *((float *)&v58 + 1)) )
        {
          v31 = v33 - v30;
          *((float *)&v54 + 1) = v33 - v30;
        }
        if ( v29 > 0.0 && v31 > 0.0 )
        {
          v34 = (int)ceilf((float)(v29 * v24) + 1.0);
          v35 = (int)ceilf((float)(v31 * v24) + 1.0);
          ceilf((float)-(float)(v30 * v24) - 0.050000001);
          ceilf((float)-(float)(v28 * v24) - 0.050000001);
          v56 = 0;
          v36 = GdipCreateBitmapFromScan0(v34, v35, 0, 2498570, 0, &v56);
          sub_1805E796C(v36, 39081239);
          pExceptionObject = 0;
          ImageGraphicsContext = GdipGetImageGraphicsContext(v56, &pExceptionObject);
          sub_1805E796C(ImageGraphicsContext, 39081240);
          v38 = GdipSetPageUnit(pExceptionObject, 2);
          sub_1805E796C(v38, 39081241);
          v41 = v52;
          if ( v52 )
          {
            v42 = GdipGetMatrixElements(v52, &v66);
            sub_1805E796C(v42, 38897232);
            *(_OWORD *)v57 = v66;
            *(_QWORD *)&v57[16] = v67;
            v41 = v52;
          }
          else
          {
            *(__m128i *)&v57[4] = _mm_load_si128((const __m128i *)&xmmword_180F648A0);
          }
          if ( v41 )
          {
            Matrix2 = GdipSetMatrixElements(v41, v39, v40);
            v44 = 38897231;
          }
          else
          {
            Matrix2 = GdipCreateMatrix2(0, v39, v40);
            v44 = 38897230;
          }
          sub_1805E796C(Matrix2, v44);
          v45 = GdipSetWorldTransform(pExceptionObject, v52);
          sub_1805E796C(v45, 39081242);
          v46 = pExceptionObject;
          v62 = pExceptionObject;
          SmoothingMode = GdipGetSmoothingMode(pExceptionObject, v63);
          sub_1805E796C(SmoothingMode, 38322255);
          v48 = GdipSetSmoothingMode(v46, 5);
          sub_1805E796C(v48, 38322256);
          GdipDrawPath(pExceptionObject, a2, a3);
          sub_1806AECF0(&v62);
          if ( pExceptionObject )
            GdipDeleteGraphics();
          *(__m128i *)v57 = _mm_load_si128((const __m128i *)&xmmword_180F64AF0);
          *(_QWORD *)&v57[16] = 0;
          sub_1806A7C30(&v60, a1, v57);
          v64 = a1;
          InterpolationMode = GdipGetInterpolationMode(a1, v65);
          sub_1805E796C(InterpolationMode, 38322261);
          v50 = GdipSetInterpolationMode(a1, 7);
          sub_1805E796C(v50, 38322262);
          v51 = GdipDrawImageRectRect(a1, v56);
          sub_1805E796C(v51, 39081243);
          sub_1806AECA8(&v64);
          GdipSetWorldTransform(v60, v61);
          if ( v61 )
          {
            ((void (*)(void))GdipDeleteMatrix)();
            v61 = 0;
          }
          if ( v56 )
            GdipDisposeImage(v56);
        }
      }
      goto LABEL_41;
    }
LABEL_40:
    GdipDrawPath(a1, a2, a3);
LABEL_41:
    v13 = v52;
  }
  if ( v13 )
    GdipDeleteMatrix(v13);
}

```

## disassembly

```asm
0x1806ac6bc  mov     rax, rsp
0x1806ac6bf  mov     [rax+8], rbx
0x1806ac6c3  mov     [rax+10h], rsi
0x1806ac6c7  push    rbp
0x1806ac6c8  push    rdi
0x1806ac6c9  push    r12
0x1806ac6cb  push    r14
0x1806ac6cd  push    r15
0x1806ac6cf  lea     rbp, [rax-0D8h]
0x1806ac6d6  sub     rsp, 1B0h
0x1806ac6dd  movaps  xmmword ptr [rax-38h], xmm6
0x1806ac6e1  movaps  xmmword ptr [rax-48h], xmm7
0x1806ac6e5  movaps  xmmword ptr [rax-58h], xmm8
0x1806ac6ea  movaps  xmmword ptr [rax-68h], xmm9
0x1806ac6ef  movaps  xmmword ptr [rax-78h], xmm10
0x1806ac6f4  movaps  xmmword ptr [rax-88h], xmm11
0x1806ac6fc  movaps  xmmword ptr [rax-98h], xmm12
0x1806ac704  movaps  xmmword ptr [rax-0A8h], xmm13
0x1806ac70c  movaps  xmmword ptr [rax-0B8h], xmm14
0x1806ac714  movaps  xmmword ptr [rax-0C8h], xmm15
0x1806ac71c  mov     r15, r8
0x1806ac71f  mov     r14, rdx
0x1806ac722  mov     rsi, rcx
0x1806ac725  xor     r12d, r12d
0x1806ac728  test    r9b, r9b
0x1806ac72b  jnz     short loc_1806AC77B
0x1806ac72d  mov     al, cs:byte_181090000
0x1806ac733  test    al, al
0x1806ac735  js      short loc_1806AC73C
0x1806ac737  setnz   al
0x1806ac73a  jmp     short loc_1806AC748
0x1806ac73c  lea     rcx, byte_181090000
0x1806ac743  call    sub_1800C4B08
0x1806ac748  test    al, al
0x1806ac74a  jz      short loc_1806AC77B
0x1806ac74c  mov     [rbp+0D0h+arg_18], r12d
0x1806ac753  lea     rdx, [rbp+0D0h+arg_18]
0x1806ac75a  mov     rcx, r14
0x1806ac75d  call    cs:GdipGetPenUnit
0x1806ac763  mov     ecx, eax
0x1806ac765  mov     edx, 2545510h
0x1806ac76a  call    sub_1805E796C
0x1806ac76f  cmp     [rbp+0D0h+arg_18], r12d
0x1806ac776  setz    al
0x1806ac779  jmp     short loc_1806AC77E
0x1806ac77b  mov     al, r12b
0x1806ac77e  mov     [rsp+1D0h+var_160], r12
0x1806ac783  test    al, al
0x1806ac785  jz      loc_1806ACDD1
0x1806ac78b  xorps   xmm10, xmm10
0x1806ac78f  mov     [rbp+0D0h+arg_18], 0
0x1806ac799  lea     rdx, [rbp+0D0h+arg_18]
0x1806ac7a0  mov     rcx, r14
0x1806ac7a3  call    cs:GdipGetPenWidth
0x1806ac7a9  mov     ecx, eax
0x1806ac7ab  mov     edx, 2545511h
0x1806ac7b0  call    sub_1805E796C
0x1806ac7b5  cmp     [rsp+1D0h+var_160], r12
0x1806ac7ba  jz      short loc_1806AC7CE
0x1806ac7bc  call    sub_1800164C0
0x1806ac7c1  test    al, al
0x1806ac7c3  jnz     loc_1806ACE54
0x1806ac7c9  jmp     loc_1806ACE47
0x1806ac7ce  lea     rcx, [rsp+1D0h+var_160]
0x1806ac7d3  call    cs:GdipCreateMatrix
0x1806ac7d9  mov     ecx, eax
0x1806ac7db  mov     edx, 2545512h
0x1806ac7e0  call    sub_1805E796C
0x1806ac7e5  mov     rdx, [rsp+1D0h+var_160]
0x1806ac7ea  mov     rcx, rsi
0x1806ac7ed  call    cs:GdipGetWorldTransform
0x1806ac7f3  mov     ecx, eax
0x1806ac7f5  mov     edx, 2545513h
0x1806ac7fa  call    sub_1805E796C
0x1806ac7ff  movss   xmm14, cs:Number
0x1806ac808  mov     rbx, [rsp+1D0h+var_160]
0x1806ac80d  test    rbx, rbx
0x1806ac810  jz      short loc_1806AC855
0x1806ac812  lea     rdx, [rbp+0D0h+var_138]
0x1806ac816  mov     rcx, rbx
0x1806ac819  call    cs:GdipGetMatrixElements
0x1806ac81f  mov     ecx, eax
0x1806ac821  mov     edx, 2518650h
0x1806ac826  call    sub_1805E796C
0x1806ac82b  movups  xmm1, [rbp+0D0h+var_138]
0x1806ac82f  movsd   xmm0, [rbp+0D0h+var_128]
0x1806ac834  movsd   [rbp+0D0h+var_D0], xmm0
0x1806ac839  mov     rbx, [rsp+1D0h+var_160]
0x1806ac83e  movaps  xmm0, xmm1
0x1806ac841  shufps  xmm0, xmm1, 0FFh
0x1806ac845  movaps  xmm2, xmm1
0x1806ac848  shufps  xmm2, xmm1, 0AAh
0x1806ac84c  movaps  xmm3, xmm1
0x1806ac84f  shufps  xmm3, xmm1, 55h ; 'U'
0x1806ac853  jmp     short loc_1806AC863
0x1806ac855  xorps   xmm3, xmm3
0x1806ac858  xorps   xmm2, xmm2
0x1806ac85b  movaps  xmm0, xmm14
0x1806ac85f  movaps  xmm1, xmm14
0x1806ac863  xorps   xmm8, xmm8
0x1806ac867  cvtss2sd xmm8, xmm1
0x1806ac86c  xorps   xmm1, xmm1
0x1806ac86f  cvtss2sd xmm1, xmm3
0x1806ac873  xorps   xmm6, xmm6
0x1806ac876  cvtss2sd xmm6, xmm2
0x1806ac87a  cvtss2sd xmm0, xmm0
0x1806ac87e  movss   xmm7, [rbp+0D0h+arg_18]
0x1806ac886  cvtps2pd xmm7, xmm7
0x1806ac889  mulsd   xmm0, xmm0
0x1806ac88d  mulsd   xmm1, xmm1
0x1806ac891  addsd   xmm0, xmm1; X
0x1806ac895  call    sqrt
0x1806ac89a  movaps  xmm9, xmm0
0x1806ac89e  mulsd   xmm9, xmm7
0x1806ac8a3  mulsd   xmm6, xmm6
0x1806ac8a7  mulsd   xmm8, xmm8
0x1806ac8ac  addsd   xmm6, xmm8
0x1806ac8b1  movaps  xmm0, xmm6; X
0x1806ac8b4  call    sqrt
0x1806ac8b9  mulsd   xmm0, xmm7
0x1806ac8bd  minsd   xmm9, xmm0
0x1806ac8c2  xorps   xmm0, xmm0
0x1806ac8c5  comisd  xmm0, xmm9
0x1806ac8ca  jnb     loc_1806ACDE5
0x1806ac8d0  movaps  xmm0, xmm9; X
0x1806ac8d4  call    _dclass
0x1806ac8d9  cmp     ax, 1
0x1806ac8dd  jz      short loc_1806AC8F9
0x1806ac8df  movaps  xmm1, xmm9
0x1806ac8e3  subsd   xmm1, cs:qword_180F63BF8
0x1806ac8eb  movsd   xmm0, cs:qword_180F645B8
0x1806ac8f3  comisd  xmm0, xmm1
0x1806ac8f7  jmp     short loc_1806AC906
0x1806ac8f9  movsd   xmm0, cs:qword_180F63BF8
0x1806ac901  comisd  xmm0, xmm9
0x1806ac906  setnbe  al
0x1806ac909  test    al, al
0x1806ac90b  jz      loc_1806ACDD1
0x1806ac911  movsd   xmm0, cs:dbl_180F63C68
0x1806ac919  divsd   xmm0, xmm9
0x1806ac91e  cvtpd2ps xmm13, xmm0
0x1806ac923  mov     [rbp+0D0h+var_150], 0
0x1806ac92b  mov     [rsp+1D0h+var_158], 0
0x1806ac934  mov     r9, r14
0x1806ac937  mov     r8, rbx
0x1806ac93a  lea     rdx, [rsp+1D0h+var_158]
0x1806ac93f  mov     rcx, r15
0x1806ac942  call    cs:GdipGetPathWorldBounds
0x1806ac948  mov     ecx, eax
0x1806ac94a  mov     edx, 2545514h
0x1806ac94f  call    sub_1805E796C
0x1806ac954  mov     [rbp+0D0h+arg_18], r12d
0x1806ac95b  lea     rdx, [rbp+0D0h+arg_18]
0x1806ac962  mov     rcx, rsi
0x1806ac965  call    cs:GdipIsVisibleClipEmpty
0x1806ac96b  mov     ecx, eax
0x1806ac96d  mov     edx, 2545515h
0x1806ac972  call    sub_1805E796C
0x1806ac977  cmp     [rbp+0D0h+arg_18], r12d
0x1806ac97e  jnz     loc_1806ACDE0
0x1806ac984  mov     [rbp+0D0h+var_118], 0
0x1806ac98c  mov     [rbp+0D0h+var_120], 0
0x1806ac994  lea     rdx, [rbp+0D0h+var_120]
0x1806ac998  mov     rcx, rsi
0x1806ac99b  call    cs:GdipGetVisibleClipBounds
0x1806ac9a1  mov     ecx, eax
0x1806ac9a3  mov     edx, 2545516h
0x1806ac9a8  call    sub_1805E796C
0x1806ac9ad  movss   xmm1, dword ptr [rbp+0D0h+var_120]
0x1806ac9b2  movss   xmm12, dword ptr [rsp+1D0h+var_158]
0x1806ac9b9  movss   xmm8, dword ptr [rbp+0D0h+var_150]
0x1806ac9bf  comiss  xmm1, xmm12
0x1806ac9c3  jbe     short loc_1806AC9E2
0x1806ac9c5  movaps  xmm0, xmm1
0x1806ac9c8  subss   xmm0, xmm12
0x1806ac9cd  subss   xmm8, xmm0
0x1806ac9d2  movss   dword ptr [rbp+0D0h+var_150], xmm8
0x1806ac9d8  movaps  xmm12, xmm1
0x1806ac9dc  movss   dword ptr [rsp+1D0h+var_158], xmm1
0x1806ac9e2  movss   xmm2, dword ptr [rbp+0D0h+var_120+4]
0x1806ac9e7  movss   xmm11, dword ptr [rsp+1D0h+var_158+4]
0x1806ac9ee  movss   xmm9, dword ptr [rbp+0D0h+var_150+4]
0x1806ac9f4  comiss  xmm2, xmm11
0x1806ac9f8  jbe     short loc_1806ACA17
0x1806ac9fa  movaps  xmm0, xmm2
0x1806ac9fd  subss   xmm0, xmm11
0x1806aca02  subss   xmm9, xmm0
0x1806aca07  movss   dword ptr [rbp+0D0h+var_150+4], xmm9
0x1806aca0d  movaps  xmm11, xmm2
0x1806aca11  movss   dword ptr [rsp+1D0h+var_158+4], xmm2
0x1806aca17  movss   xmm3, dword ptr [rbp+0D0h+var_118]
0x1806aca1c  addss   xmm3, xmm1
0x1806aca20  movaps  xmm0, xmm8
0x1806aca24  addss   xmm0, xmm12
0x1806aca29  comiss  xmm0, xmm3
0x1806aca2c  jbe     short loc_1806ACA3D
0x1806aca2e  movaps  xmm8, xmm3
0x1806aca32  subss   xmm8, xmm12
0x1806aca37  movss   dword ptr [rbp+0D0h+var_150], xmm8
0x1806aca3d  movss   xmm1, dword ptr [rbp+0D0h+var_118+4]
0x1806aca42  addss   xmm1, xmm2
0x1806aca46  movaps  xmm0, xmm9
0x1806aca4a  addss   xmm0, xmm11
0x1806aca4f  comiss  xmm0, xmm1
0x1806aca52  jbe     short loc_1806ACA63
0x1806aca54  movaps  xmm9, xmm1
0x1806aca58  subss   xmm9, xmm11
0x1806aca5d  movss   dword ptr [rbp+0D0h+var_150+4], xmm9
0x1806aca63  comiss  xmm10, xmm8
0x1806aca67  jnb     loc_1806ACDE0
0x1806aca6d  comiss  xmm10, xmm9
0x1806aca71  jnb     loc_1806ACDE0
0x1806aca77  mulss   xmm9, xmm13
0x1806aca7c  mulss   xmm8, xmm13
0x1806aca81  mulss   xmm11, xmm13
0x1806aca86  mulss   xmm12, xmm13
0x1806aca8b  movaps  xmm0, xmm8
0x1806aca8f  addss   xmm0, xmm14; X
0x1806aca94  call    ceilf
0x1806aca99  cvttss2si edi, xmm0
0x1806aca9d  movaps  xmm0, xmm9
0x1806acaa1  addss   xmm0, xmm14; X
0x1806acaa6  call    ceilf
0x1806acaab  cvttss2si ebx, xmm0
0x1806acaaf  movaps  xmm0, xmm11
0x1806acab3  xorps   xmm0, cs:xmmword_180F65330
0x1806acaba  subss   xmm0, cs:dword_180F6378C; X
0x1806acac2  call    ceilf
0x1806acac7  movaps  xmm15, xmm0
0x1806acacb  movaps  xmm0, xmm12
0x1806acacf  xorps   xmm0, cs:xmmword_180F65330
0x1806acad6  subss   xmm0, cs:dword_180F6378C; X
0x1806acade  call    ceilf
0x1806acae3  movaps  xmm6, xmm0
0x1806acae6  movaps  xmm7, xmm0
0x1806acae9  addss   xmm7, xmm12
0x1806acaee  addss   xmm11, xmm15
0x1806acaf3  mov     [rbp+0D0h+var_140], r12
0x1806acaf7  lea     rax, [rbp+0D0h+var_140]
0x1806acafb  mov     [rsp+1D0h+var_1A8], rax
0x1806acb00  mov     [rsp+1D0h+var_1B0], r12
0x1806acb05  mov     r9d, 26200Ah
0x1806acb0b  xor     r8d, r8d
0x1806acb0e  mov     edx, ebx
0x1806acb10  mov     ecx, edi
0x1806acb12  call    cs:GdipCreateBitmapFromScan0
0x1806acb18  mov     ecx, eax
0x1806acb1a  mov     edx, 2545517h
0x1806acb1f  call    sub_1805E796C
0x1806acb24  mov     [rbp+0D0h+pExceptionObject], r12
0x1806acb28  lea     rdx, [rbp+0D0h+pExceptionObject]
0x1806acb2c  mov     rcx, [rbp+0D0h+var_140]
0x1806acb30  call    cs:GdipGetImageGraphicsContext
0x1806acb36  mov     ecx, eax
0x1806acb38  mov     edx, 2545518h
0x1806acb3d  call    sub_1805E796C
0x1806acb42  mov     edi, 2
0x1806acb47  mov     edx, edi
0x1806acb49  mov     rcx, [rbp+0D0h+pExceptionObject]
0x1806acb4d  call    cs:GdipSetPageUnit
0x1806acb53  mov     ecx, eax
0x1806acb55  mov     edx, 2545519h
0x1806acb5a  call    sub_1805E796C
0x1806acb5f  mov     rcx, [rsp+1D0h+var_160]
0x1806acb64  test    rcx, rcx
0x1806acb67  jz      short loc_1806ACB9E
0x1806acb69  lea     rdx, [rbp+0D0h+var_E0]
0x1806acb6d  call    cs:GdipGetMatrixElements
0x1806acb73  mov     ecx, eax
0x1806acb75  mov     edx, 2518650h
0x1806acb7a  call    sub_1805E796C
0x1806acb7f  movups  xmm4, [rbp+0D0h+var_E0]
0x1806acb83  movups  [rbp+0D0h+var_138], xmm4
0x1806acb87  movsd   xmm0, [rbp+0D0h+var_D0]
0x1806acb8c  movsd   [rbp+0D0h+var_128], xmm0
0x1806acb91  mov     rcx, [rsp+1D0h+var_160]
0x1806acb96  movss   xmm10, dword ptr [rbp+0D0h+var_128+4]
0x1806acb9c  jmp     short loc_1806ACBAE
0x1806acb9e  movdqa  xmm0, cs:xmmword_180F648A0
0x1806acba6  movups  [rbp+0D0h+var_138+4], xmm0
0x1806acbaa  movaps  xmm4, xmm14
0x1806acbae  mulss   xmm4, xmm13
0x1806acbb3  movss   xmm1, dword ptr [rbp+0D0h+var_138+4]
0x1806acbb8  mulss   xmm1, xmm13
0x1806acbbd  movss   xmm2, dword ptr [rbp+0D0h+var_138+8]
0x1806acbc2  mulss   xmm2, xmm13
0x1806acbc7  movss   xmm3, dword ptr [rbp+0D0h+var_138+0Ch]
0x1806acbcc  mulss   xmm3, xmm13
0x1806acbd1  movss   xmm0, dword ptr [rbp+0D0h+var_128]
0x1806acbd6  mulss   xmm0, xmm13
0x1806acbdb  addss   xmm0, xmm6
0x1806acbdf  mulss   xmm10, xmm13
0x1806acbe4  addss   xmm10, xmm15
0x1806acbe9  test    rcx, rcx
0x1806acbec  jnz     short loc_1806ACC15
0x1806acbee  lea     rax, [rsp+1D0h+var_160]
0x1806acbf3  mov     qword ptr [rsp+1D0h+var_1A0], rax
0x1806acbf8  movss   dword ptr [rsp+1D0h+var_1A8], xmm10
0x1806acbff  movss   dword ptr [rsp+1D0h+var_1B0], xmm0
0x1806acc05  movaps  xmm0, xmm4
  ... truncated ...
```
