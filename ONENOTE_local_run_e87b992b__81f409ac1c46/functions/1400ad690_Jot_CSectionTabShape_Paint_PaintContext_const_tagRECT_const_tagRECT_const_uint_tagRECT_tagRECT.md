# Jot::CSectionTabShape::Paint(PaintContext const &,tagRECT const *,tagRECT const *,uint,tagRECT *,tagRECT *)

- ea: `0x1400ad690`
- end: `0x1400ad98a`
- name: `?Paint@CSectionTabShape@Jot@@UEAAXAEBVPaintContext@@PEBUtagRECT@@1IPEAU4@2@Z`
- size: `762`
- prototype: `void __fastcall(Jot::CSectionTabShape *__hidden this, const struct PaintContext *, const struct tagRECT *, const struct tagRECT *, unsigned int, struct tagRECT *, struct tagRECT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140038864`
- `0x1400ad690`

## import_xrefs

- `gdiplus!GdipClosePathFigure` at `0x1400ad8b3`
- `gdiplus!GdipClosePathFigure` at `0x1400ad8b3`
- `gdiplus!GdipAddPathArc` at `0x1400ad824`
- `gdiplus!GdipAddPathArc` at `0x1400ad89e`
- `gdiplus!GdipAddPathArc` at `0x1400ad824`
- `gdiplus!GdipAddPathArc` at `0x1400ad89e`
- `gdiplus!GdipSetSmoothingMode` at `0x1400ad734`
- `gdiplus!GdipSetSmoothingMode` at `0x1400ad734`
- `gdiplus!GdipGetSmoothingMode` at `0x1400ad720`
- `gdiplus!GdipGetSmoothingMode` at `0x1400ad720`
- `gdiplus!GdipFillPath` at `0x1400ad8e8`
- `gdiplus!GdipFillPath` at `0x1400ad8e8`
- `gdiplus!GdipAddPathLineI` at `0x1400ad7da`
- `gdiplus!GdipAddPathLineI` at `0x1400ad854`
- `gdiplus!GdipAddPathLineI` at `0x1400ad7da`
- `gdiplus!GdipAddPathLineI` at `0x1400ad854`
- `gdiplus!GdipDeletePath` at `0x1400ad906`
- `gdiplus!GdipDeletePath` at `0x1400ad906`
- `gdiplus!GdipCreatePath` at `0x1400ad74e`
- `gdiplus!GdipCreatePath` at `0x1400ad74e`
- `gdiplus!GdipDeleteGraphics` at `0x1400ad91c`
- `gdiplus!GdipDeleteGraphics` at `0x1400ad91c`
- `gdiplus!GdipDeleteBrush` at `0x1400ad8fc`
- `gdiplus!GdipDeleteBrush` at `0x1400ad8fc`
- `gdiplus!GdipCreateSolidFill` at `0x1400ad8d7`
- `gdiplus!GdipCreateSolidFill` at `0x1400ad8d7`
- `gdiplus!GdipCreateFromHDC` at `0x1400ad701`
- `gdiplus!GdipCreateFromHDC` at `0x1400ad701`
- `mso40uiWin32Client!__imp_?Paint@Element@NetUI@@UEAAXAEBVPaintContext@@PEBUtagRECT@@1IPEAU4@2@Z` at `0x1400ad6e7`
- `mso40uiWin32Client!__imp_?Paint@Element@NetUI@@UEAAXAEBVPaintContext@@PEBUtagRECT@@1IPEAU4@2@Z` at `0x1400ad6e7`

## pseudocode

```c
void __fastcall Jot::CSectionTabShape::Paint(
        Jot::CSectionTabShape *this,
        const struct PaintContext *a2,
        const struct tagRECT *a3,
        const struct tagRECT *a4,
        unsigned int a5,
        struct tagRECT *a6,
        struct tagRECT *a7)
{
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // eax
  __int64 v14; // r15
  __int64 v15; // rcx
  int v16; // r14d
  int SmoothingMode; // eax
  int v18; // eax
  int v19; // eax
  char v20; // cl
  LONG right; // eax
  char v22; // cl
  LONG left; // edx
  unsigned int v24; // esi
  unsigned int v25; // r10d
  int v26; // r12d
  int v27; // eax
  int v28; // ecx
  int v29; // eax
  int v30; // ecx
  LONG top; // r8d
  int v32; // eax
  int v33; // ecx
  int v34; // eax
  int v35; // ecx
  int v36; // eax
  int v37; // edx
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // [rsp+48h] [rbp-61h] BYREF
  int v41; // [rsp+50h] [rbp-59h]
  __int64 v42; // [rsp+58h] [rbp-51h] BYREF
  __int128 v43; // [rsp+60h] [rbp-49h]
  __int64 v44; // [rsp+F8h] [rbp+4Fh] BYREF
  __int64 v45; // [rsp+100h] [rbp+57h] BYREF

  NetUI::Element::Paint(this, a2, a3, a4, a5, a6, a7);
  v10 = *((_QWORD *)a2 + 2);
  *((_BYTE *)a2 + 48) = 1;
  v44 = 0;
  v13 = GdipCreateFromHDC(v10, &v44, v11, v12);
  v14 = v44;
  v15 = v44;
  v42 = v44;
  v16 = v13;
  LODWORD(v44) = -1;
  SmoothingMode = GdipGetSmoothingMode(v15, &v44);
  if ( SmoothingMode )
    v16 = SmoothingMode;
  v18 = GdipSetSmoothingMode(v14, 4);
  v40 = 0;
  if ( v18 )
    v16 = v18;
  v19 = GdipCreatePath(0, &v40);
  v20 = *((_BYTE *)this + 195);
  v41 = v19;
  right = a3->right;
  v22 = v20 & 1;
  if ( v22 )
  {
    left = a3->left;
    v24 = right - 1;
  }
  else
  {
    v24 = a3->left;
    left = a3->left;
  }
  v25 = left - 1;
  if ( !v22 )
    v25 = a3->right;
  v26 = (right - left) / 2;
  v27 = GdipAddPathLineI(v40, v25, (unsigned int)(a3->bottom - 1), v25, a3->top);
  v28 = v41;
  if ( v27 )
    v28 = v27;
  v41 = v28;
  v29 = GdipAddPathArc(v40);
  v30 = v41;
  top = a3->top;
  if ( v29 )
    v30 = v29;
  v41 = v30;
  v32 = GdipAddPathLineI(v40, v24, (unsigned int)(2 * v26 + top), v24, a3->bottom + ~(2 * v26));
  v33 = v41;
  if ( v32 )
    v33 = v32;
  v41 = v33;
  v34 = GdipAddPathArc(v40);
  v35 = v41;
  if ( v34 )
    v35 = v34;
  v41 = v35;
  v36 = GdipClosePathFigure(v40);
  v37 = v41;
  v38 = *((unsigned int *)this + 52);
  if ( v36 )
    v37 = v36;
  v45 = 0;
  v41 = v37;
  GdipCreateSolidFill(v38, &v45);
  v39 = GdipFillPath(v14, v45, v40);
  if ( v39 )
    v16 = v39;
  LODWORD(v43) = v16;
  GdipDeleteBrush(v45);
  GdipDeletePath(v40);
  Gdiplus::Graphics::SetSmoothingMode(&v42, (unsigned int)v44);
  GdipDeleteGraphics(v42);
}

```

## disassembly

```asm
0x1400ad690  mov     rax, rsp
0x1400ad693  mov     [rax+18h], rbx
0x1400ad697  push    rbp
0x1400ad698  push    rsi
0x1400ad699  push    rdi
0x1400ad69a  push    r12
0x1400ad69c  push    r13
0x1400ad69e  push    r14
0x1400ad6a0  push    r15
0x1400ad6a2  lea     rbp, [rax-47h]
0x1400ad6a6  sub     rsp, 0B0h
0x1400ad6ad  movaps  xmmword ptr [rax-48h], xmm6
0x1400ad6b1  mov     rdi, r8
0x1400ad6b4  movaps  xmmword ptr [rax-58h], xmm7
0x1400ad6b8  mov     rbx, rdx
0x1400ad6bb  movaps  xmmword ptr [rax-68h], xmm8
0x1400ad6c0  mov     r13, rcx
0x1400ad6c3  movaps  xmmword ptr [rax-78h], xmm9
0x1400ad6c8  mov     rax, [rbp+3Fh+arg_30]
0x1400ad6cc  mov     [rsp+0E0h+var_B0], rax
0x1400ad6d1  mov     rax, [rbp+3Fh+arg_28]
0x1400ad6d5  mov     [rsp+0E0h+var_B8], rax
0x1400ad6da  mov     eax, [rbp+3Fh+arg_20]
0x1400ad6dd  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1400ad6e1  movaps  [rsp+0E0h+var_88+8], xmm10
0x1400ad6e7  call    cs:__imp_?Paint@Element@NetUI@@UEAAXAEBVPaintContext@@PEBUtagRECT@@1IPEAU4@2@Z; NetUI::Element::Paint(PaintContext const &,tagRECT const *,tagRECT const *,uint,tagRECT *,tagRECT *)
0x1400ad6ed  mov     rcx, [rbx+10h]
0x1400ad6f1  lea     rdx, [rbp+3Fh+arg_0]
0x1400ad6f5  mov     byte ptr [rbx+30h], 1
0x1400ad6f9  mov     [rbp+3Fh+arg_0], 0
0x1400ad701  call    cs:__imp_GdipCreateFromHDC
0x1400ad707  mov     r15, [rbp+3Fh+arg_0]
0x1400ad70b  lea     rdx, [rbp+3Fh+arg_0]
0x1400ad70f  mov     rcx, r15
0x1400ad712  mov     [rbp+3Fh+var_90], r15
0x1400ad716  mov     r14d, eax
0x1400ad719  mov     dword ptr [rbp+3Fh+arg_0], 0FFFFFFFFh
0x1400ad720  call    cs:__imp_GdipGetSmoothingMode
0x1400ad726  mov     edx, 4
0x1400ad72b  mov     rcx, r15
0x1400ad72e  test    eax, eax
0x1400ad730  cmovnz  r14d, eax
0x1400ad734  call    cs:__imp_GdipSetSmoothingMode
0x1400ad73a  lea     rdx, [rbp+3Fh+var_A0]
0x1400ad73e  mov     [rbp+3Fh+var_A0], 0
0x1400ad746  test    eax, eax
0x1400ad748  cmovnz  r14d, eax
0x1400ad74c  xor     ecx, ecx
0x1400ad74e  call    cs:__imp_GdipCreatePath
0x1400ad754  mov     cl, [r13+0C3h]
0x1400ad75b  mov     [rbp+3Fh+var_98], eax
0x1400ad75e  mov     eax, [rdi+8]
0x1400ad761  and     cl, 1
0x1400ad764  jz      loc_1400AD956
0x1400ad76a  mov     edx, [rdi]
0x1400ad76c  lea     esi, [rax-1]
0x1400ad76f  lea     r10d, [rdx-1]
0x1400ad773  test    cl, cl
0x1400ad775  mov     r8d, 2
0x1400ad77b  mov     ebx, esi
0x1400ad77d  cmovz   r10d, eax
0x1400ad781  sub     eax, edx
0x1400ad783  cdq
0x1400ad784  idiv    r8d
0x1400ad787  mov     r12d, eax
0x1400ad78a  test    cl, cl
0x1400ad78c  jz      loc_1400AD95F
0x1400ad792  sub     ebx, eax
0x1400ad794  test    cl, cl
0x1400ad796  jz      loc_1400AD95F
0x1400ad79c  movss   xmm10, cs:__real@439d8000
0x1400ad7a5  test    cl, cl
0x1400ad7a7  jz      loc_1400AD96D
0x1400ad7ad  xorps   xmm9, xmm9
0x1400ad7b1  test    cl, cl
0x1400ad7b3  jz      loc_1400AD97B
0x1400ad7b9  movss   xmm8, cs:__real@42340000
0x1400ad7c2  mov     r8d, [rdi+0Ch]
0x1400ad7c6  mov     r9d, r10d
0x1400ad7c9  mov     eax, [rdi+4]
0x1400ad7cc  dec     r8d
0x1400ad7cf  mov     rcx, [rbp+3Fh+var_A0]
0x1400ad7d3  mov     edx, r10d
0x1400ad7d6  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1400ad7da  call    cs:__imp_GdipAddPathLineI
0x1400ad7e0  mov     ecx, [rbp+3Fh+var_98]
0x1400ad7e3  test    eax, eax
0x1400ad7e5  movd    xmm2, dword ptr [rdi+4]
0x1400ad7ea  cmovnz  ecx, eax
0x1400ad7ed  movss   dword ptr [rsp+0E0h+var_B0], xmm8
0x1400ad7f4  cvtdq2ps xmm2, xmm2
0x1400ad7f7  mov     [rbp+3Fh+var_98], ecx
0x1400ad7fa  mov     rcx, [rbp+3Fh+var_A0]
0x1400ad7fe  movss   dword ptr [rsp+0E0h+var_B8], xmm10
0x1400ad805  movd    xmm7, r12d
0x1400ad80a  cvtdq2ps xmm7, xmm7
0x1400ad80d  movd    xmm6, ebx
0x1400ad811  cvtdq2ps xmm6, xmm6
0x1400ad814  addss   xmm2, xmm7
0x1400ad818  movss   dword ptr [rsp+0E0h+var_C0], xmm7
0x1400ad81e  movaps  xmm3, xmm7
0x1400ad821  movaps  xmm1, xmm6
0x1400ad824  call    cs:__imp_GdipAddPathArc
0x1400ad82a  mov     ecx, [rbp+3Fh+var_98]
0x1400ad82d  lea     ebx, [r12+r12]
0x1400ad831  mov     r8d, [rdi+4]
0x1400ad835  test    eax, eax
0x1400ad837  mov     r9d, esi
0x1400ad83a  mov     edx, esi
0x1400ad83c  cmovnz  ecx, eax
0x1400ad83f  mov     eax, ebx
0x1400ad841  not     eax
0x1400ad843  mov     [rbp+3Fh+var_98], ecx
0x1400ad846  add     eax, [rdi+0Ch]
0x1400ad849  add     r8d, ebx
0x1400ad84c  mov     rcx, [rbp+3Fh+var_A0]
0x1400ad850  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1400ad854  call    cs:__imp_GdipAddPathLineI
0x1400ad85a  mov     ecx, [rbp+3Fh+var_98]
0x1400ad85d  movaps  xmm3, xmm7
0x1400ad860  movd    xmm2, dword ptr [rdi+0Ch]
0x1400ad865  test    eax, eax
0x1400ad867  cvtdq2ps xmm2, xmm2
0x1400ad86a  cmovnz  ecx, eax
0x1400ad86d  mov     [rbp+3Fh+var_98], ecx
0x1400ad870  mov     rcx, [rbp+3Fh+var_A0]
0x1400ad874  movss   dword ptr [rsp+0E0h+var_B0], xmm8
0x1400ad87b  movaps  xmm1, xmm6
0x1400ad87e  movd    xmm0, ebx
0x1400ad882  cvtdq2ps xmm0, xmm0
0x1400ad885  movss   dword ptr [rsp+0E0h+var_B8], xmm9
0x1400ad88c  subss   xmm2, xmm0
0x1400ad890  movss   dword ptr [rsp+0E0h+var_C0], xmm7
0x1400ad896  subss   xmm2, cs:__real@3f800000
0x1400ad89e  call    cs:__imp_GdipAddPathArc
0x1400ad8a4  mov     ecx, [rbp+3Fh+var_98]
0x1400ad8a7  test    eax, eax
0x1400ad8a9  cmovnz  ecx, eax
0x1400ad8ac  mov     [rbp+3Fh+var_98], ecx
0x1400ad8af  mov     rcx, [rbp+3Fh+var_A0]
0x1400ad8b3  call    cs:__imp_GdipClosePathFigure
0x1400ad8b9  mov     edx, [rbp+3Fh+var_98]
0x1400ad8bc  test    eax, eax
0x1400ad8be  mov     ecx, [r13+0D0h]
0x1400ad8c5  cmovnz  edx, eax
0x1400ad8c8  mov     [rbp+3Fh+arg_8], 0
0x1400ad8d0  mov     [rbp+3Fh+var_98], edx
0x1400ad8d3  lea     rdx, [rbp+3Fh+arg_8]
0x1400ad8d7  call    cs:__imp_GdipCreateSolidFill
0x1400ad8dd  mov     r8, [rbp+3Fh+var_A0]
0x1400ad8e1  mov     rcx, r15
0x1400ad8e4  mov     rdx, [rbp+3Fh+arg_8]
0x1400ad8e8  call    cs:__imp_GdipFillPath
0x1400ad8ee  mov     rcx, [rbp+3Fh+arg_8]
0x1400ad8f2  test    eax, eax
0x1400ad8f4  cmovnz  r14d, eax
0x1400ad8f8  mov     dword ptr [rbp+3Fh+var_88], r14d
0x1400ad8fc  call    cs:__imp_GdipDeleteBrush
0x1400ad902  mov     rcx, [rbp+3Fh+var_A0]
0x1400ad906  call    cs:__imp_GdipDeletePath
0x1400ad90c  mov     edx, dword ptr [rbp+3Fh+arg_0]
0x1400ad90f  lea     rcx, [rbp+3Fh+var_90]
0x1400ad913  call    ?SetSmoothingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4SmoothingMode@2@@Z; Gdiplus::Graphics::SetSmoothingMode(Gdiplus::SmoothingMode)
0x1400ad918  mov     rcx, [rbp+3Fh+var_90]
0x1400ad91c  call    cs:__imp_GdipDeleteGraphics
0x1400ad922  lea     r11, [rsp+0E0h+var_30]
0x1400ad92a  mov     rbx, [r11+50h]
0x1400ad92e  movaps  xmm6, xmmword ptr [r11-10h]
0x1400ad933  movaps  xmm7, xmmword ptr [r11-20h]
0x1400ad938  movaps  xmm8, xmmword ptr [r11-30h]
0x1400ad93d  movaps  xmm9, xmmword ptr [r11-40h]
0x1400ad942  movaps  xmm10, xmmword ptr [r11-50h]
0x1400ad947  mov     rsp, r11
0x1400ad94a  pop     r15
0x1400ad94c  pop     r14
0x1400ad94e  pop     r13
0x1400ad950  pop     r12
0x1400ad952  pop     rdi
0x1400ad953  pop     rsi
0x1400ad954  pop     rbp
0x1400ad955  retn
0x1400ad956  mov     esi, [rdi]
0x1400ad958  mov     edx, esi
0x1400ad95a  jmp     loc_1400AD76F
0x1400ad95f  movss   xmm10, cs:__real@43610000
0x1400ad968  jmp     loc_1400AD7A5
0x1400ad96d  movss   xmm9, cs:__real@43340000
0x1400ad976  jmp     loc_1400AD7B1
0x1400ad97b  movss   xmm8, cs:__real@c2340000
0x1400ad984  jmp     loc_1400AD7C2
```
