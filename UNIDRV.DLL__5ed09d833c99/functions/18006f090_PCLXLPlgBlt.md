# PCLXLPlgBlt

- ea: `0x18006f090`
- end: `0x18006f41c`
- name: `PCLXLPlgBlt`
- size: `908`
- prototype: `BOOL __fastcall(SURFOBJ *psoTrg, SURFOBJ *psoSrc, SURFOBJ *psoMsk, CLIPOBJ *pco, XLATEOBJ *pxlo, COLORADJUSTMENT *pca, POINTL *pptlBrushOrg, POINTFIX *, RECTL *prclSrc, POINTL *pptlMask, ULONG iMode)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18004375c`
- `0x180049d00`
- `0x18006f090`

## import_xrefs

- `GDI32!EngPlgBlt` at `0x18006f318`
- `GDI32!EngPlgBlt` at `0x18006f3ef`
- `GDI32!EngPlgBlt` at `0x18006f318`
- `GDI32!EngPlgBlt` at `0x18006f3ef`
- `GDI32!EngStretchBlt` at `0x18006f161`
- `GDI32!EngStretchBlt` at `0x18006f377`
- `GDI32!EngStretchBlt` at `0x18006f161`
- `GDI32!EngStretchBlt` at `0x18006f377`
- `GDI32!EngUnlockSurface` at `0x18006f388`
- `GDI32!EngUnlockSurface` at `0x18006f388`
- `GDI32!EngDeleteSurface` at `0x18006f39d`
- `GDI32!EngDeleteSurface` at `0x18006f39d`

## pseudocode

```c
BOOL __fastcall PCLXLPlgBlt(
        SURFOBJ *psoTrg,
        SURFOBJ *psoSrc,
        SURFOBJ *psoMsk,
        CLIPOBJ *pco,
        XLATEOBJ *pxlo,
        COLORADJUSTMENT *pca,
        POINTL *pptlBrushOrg,
        POINTFIX *a8,
        RECTL *prclSrc,
        POINTL *pptlMask,
        ULONG iMode)
{
  SURFOBJ *v12; // r11
  SURFOBJ *v14; // r10
  int x; // r9d
  FIX y; // ecx
  FIX v18; // r8d
  FIX v19; // edi
  int v20; // r10d
  int v21; // r11d
  FIX v22; // edx
  LONG v23; // r8d
  LONG v24; // edi
  LONG v25; // edx
  LONG v26; // r9d
  LONG v27; // ecx
  int v28; // r8d
  int v29; // ecx
  int v30; // eax
  int v31; // edx
  int v32; // ecx
  int v33; // eax
  SURFOBJ *v34; // rax
  SURFOBJ *v35; // rdi
  BOOL v36; // ebx
  ULONG v37; // eax
  int v38; // [rsp+64h] [rbp-7Dh]
  HSURF hsurf; // [rsp+80h] [rbp-61h] BYREF
  SURFOBJ *v41; // [rsp+88h] [rbp-59h]
  RECTL *prcl; // [rsp+90h] [rbp-51h]
  RECTL v43; // [rsp+98h] [rbp-49h] BYREF
  RECTL prclDest; // [rsp+A8h] [rbp-39h] BYREF
  POINTFIX pptfx; // [rsp+B8h] [rbp-29h] BYREF
  _BYTE v46[12]; // [rsp+C0h] [rbp-21h]
  int v47; // [rsp+CCh] [rbp-15h]

  v12 = psoMsk;
  v14 = psoTrg;
  x = a8->x;
  v41 = psoMsk;
  prcl = prclSrc;
  if ( x == a8[2].x )
  {
    y = a8->y;
    if ( y == a8[1].y )
    {
      prclDest.bottom = a8[2].y >> 4;
      prclDest.right = a8[1].x >> 4;
      prclDest.top = y >> 4;
      prclDest.left = x >> 4;
      return EngStretchBlt(v14, psoSrc, psoMsk, pco, pxlo, pca, pptlBrushOrg, &prclDest, prclSrc, pptlMask, 4u);
    }
  }
  if ( psoMsk )
    return EngPlgBlt(v14, psoSrc, v12, pco, pxlo, pca, pptlBrushOrg, a8, prclSrc, pptlMask, 4u);
  v18 = a8[1].x;
  if ( x != v18 )
    return EngPlgBlt(v14, psoSrc, v12, pco, pxlo, pca, pptlBrushOrg, a8, prclSrc, pptlMask, 4u);
  v19 = a8[2].y;
  if ( a8->y != v19 )
    return EngPlgBlt(v14, psoSrc, v12, pco, pxlo, pca, pptlBrushOrg, a8, prclSrc, pptlMask, 4u);
  v20 = a8[2].x + 15;
  v21 = prclSrc->right - prclSrc->left;
  v22 = a8[1].y;
  *(_QWORD *)&prclDest.right = 0;
  hsurf = 0;
  *(_QWORD *)&prclDest.left = 0;
  v38 = prclSrc->bottom - prclSrc->top;
  prclDest.right = v38;
  v23 = (v18 + 15) >> 4;
  v24 = (v19 + 15) >> 4;
  v25 = (v22 + 15) >> 4;
  v43 = 0;
  prclDest.bottom = v21;
  if ( a8[2].x >= x )
  {
    *(_DWORD *)&v46[8] = 16 * v38;
    v26 = v25;
    v27 = v23;
    v43.top = v25;
    v23 = v20 >> 4;
    v25 = v24;
    v47 = 16 * v21;
    pptfx.y = 16 * v21;
    *(_QWORD *)v46 = 0;
    pptfx.x = 0;
  }
  else
  {
    *(_DWORD *)v46 = 16 * v38;
    v26 = v24;
    pptfx.x = 16 * v38;
    v27 = v20 >> 4;
    v47 = 0;
    pptfx.y = 0;
    *(_QWORD *)&v46[4] = (unsigned int)(16 * v21);
    v43.top = v24;
  }
  v14 = psoTrg;
  v43.right = v23;
  v43.bottom = v25;
  v43.left = v27;
  if ( pco )
  {
    if ( pco->rclBounds.right - v23 == 1 )
      v43.right = ++v23;
    if ( pco->rclBounds.bottom - v25 == 1 )
      v43.bottom = ++v25;
  }
  v28 = v23 - v27;
  v29 = -v28;
  if ( v28 > 0 )
    v29 = v28;
  v30 = -v38;
  if ( v38 > 0 )
    v30 = v38;
  if ( v29 == v30 )
  {
    v31 = v25 - v26;
    v32 = -v31;
    if ( v31 > 0 )
      v32 = v31;
    v33 = -v21;
    if ( v21 > 0 )
      v33 = v21;
    if ( v32 == v33 )
    {
LABEL_34:
      v12 = v41;
      return EngPlgBlt(v14, psoSrc, v12, pco, pxlo, pca, pptlBrushOrg, a8, prclSrc, pptlMask, 4u);
    }
  }
  v34 = CreateBitmapSURFOBJ(*(_QWORD *)(*((_QWORD *)psoTrg->dhpdev + 1) + 8LL), &hsurf, v38, v21, psoSrc->iBitmapFormat);
  v35 = v34;
  if ( !v34 )
  {
    v14 = psoTrg;
    goto LABEL_34;
  }
  v36 = EngPlgBlt(v34, psoSrc, 0, 0, 0, pca, pptlBrushOrg, &pptfx, prcl, pptlMask, iMode);
  if ( v36 )
  {
    v37 = 4;
    if ( psoSrc->iBitmapFormat == 1 )
      v37 = iMode;
    v36 = EngStretchBlt(psoTrg, v35, 0, pco, pxlo, pca, pptlBrushOrg, &v43, &prclDest, 0, v37);
  }
  EngUnlockSurface(v35);
  if ( hsurf )
    EngDeleteSurface(hsurf);
  return v36;
}

```

## disassembly

```asm
0x18006f090  push    rbp
0x18006f092  push    rbx
0x18006f093  push    rsi
0x18006f094  push    rdi
0x18006f095  push    r12
0x18006f097  push    r13
0x18006f099  push    r14
0x18006f09b  push    r15
0x18006f09d  lea     rbp, [rsp-7]
0x18006f0a2  sub     rsp, 0E8h
0x18006f0a9  mov     rax, cs:__security_cookie
0x18006f0b0  xor     rax, rsp
0x18006f0b3  mov     [rbp+3Fh+var_50], rax
0x18006f0b7  mov     rbx, [rbp+3Fh+arg_38]
0x18006f0be  mov     rsi, r9
0x18006f0c1  mov     rax, [rbp+3Fh+arg_20]
0x18006f0c5  mov     r11, r8
0x18006f0c8  mov     r15, [rbp+3Fh+arg_40]
0x18006f0cf  mov     r14, rdx
0x18006f0d2  mov     r12, [rbp+3Fh+arg_28]
0x18006f0d6  mov     r10, rcx
0x18006f0d9  mov     r9d, [rbx]
0x18006f0dc  mov     r13, [rbp+3Fh+pptlBrushOrg]
0x18006f0e0  mov     [rbp+3Fh+var_A8], rax
0x18006f0e4  mov     rax, [rbp+3Fh+arg_48]
0x18006f0eb  mov     [rbp+3Fh+var_98], r8
0x18006f0ef  mov     [rbp+3Fh+psoDest], rcx
0x18006f0f3  mov     [rbp+3Fh+prcl], r15
0x18006f0f7  mov     [rbp+3Fh+pptl], rax
0x18006f0fb  cmp     r9d, [rbx+10h]
0x18006f0ff  jnz     short loc_18006F172
0x18006f101  mov     ecx, [rbx+4]
0x18006f104  cmp     ecx, [rbx+0Ch]
0x18006f107  jnz     short loc_18006F172
0x18006f109  mov     eax, [rbx+14h]
0x18006f10c  sar     eax, 4
0x18006f10f  mov     [rbp+3Fh+var_78.bottom], eax
0x18006f112  mov     eax, [rbx+8]
0x18006f115  mov     [rsp+120h+iMode], 4; iMode
0x18006f11d  sar     eax, 4
0x18006f120  mov     [rbp+3Fh+var_78.right], eax
0x18006f123  mov     rax, [rbp+3Fh+pptl]
0x18006f127  mov     [rsp+120h+pptlMask], rax; pptlMask
0x18006f12c  lea     rax, [rbp+3Fh+var_78]
0x18006f130  mov     [rsp+120h+prclSrc], r15; prclSrc
0x18006f135  mov     [rsp+120h+prclDest], rax; prclDest
0x18006f13a  mov     rax, [rbp+3Fh+var_A8]
0x18006f13e  sar     ecx, 4
0x18006f141  sar     r9d, 4
0x18006f145  mov     [rsp+120h+pptlHTOrg], r13; pptlHTOrg
0x18006f14a  mov     [rbp+3Fh+var_78.top], ecx
0x18006f14d  mov     rcx, r10; psoDest
0x18006f150  mov     [rbp+3Fh+var_78.left], r9d
0x18006f154  mov     r9, rsi; pco
0x18006f157  mov     [rsp+120h+pca], r12; pca
0x18006f15c  mov     [rsp+120h+pxlo], rax; pxlo
0x18006f161  call    cs:__imp_EngStretchBlt
0x18006f168  nop     dword ptr [rax+rax+00h]
0x18006f16d  jmp     loc_18006F3FB
0x18006f172  xor     ecx, ecx
0x18006f174  test    r8, r8
0x18006f177  jnz     loc_18006F3B5
0x18006f17d  mov     r8d, [rbx+8]
0x18006f181  cmp     r9d, r8d
0x18006f184  jnz     loc_18006F3B5
0x18006f18a  mov     edi, [rbx+14h]
0x18006f18d  cmp     [rbx+4], edi
0x18006f190  jnz     loc_18006F3B5
0x18006f196  mov     r10d, [rbx+10h]
0x18006f19a  add     r8d, 0Fh
0x18006f19e  mov     r11d, [r15+8]
0x18006f1a2  add     r10d, 0Fh
0x18006f1a6  sub     r11d, [r15]
0x18006f1a9  add     edi, 0Fh
0x18006f1ac  mov     edx, [rbx+0Ch]
0x18006f1af  mov     eax, r11d
0x18006f1b2  mov     qword ptr [rbp+3Fh+var_78.right], rcx
0x18006f1b6  add     edx, 0Fh
0x18006f1b9  mov     [rbp+3Fh+hsurf], rcx
0x18006f1bd  xorps   xmm0, xmm0
0x18006f1c0  mov     qword ptr [rbp+3Fh+var_78.left], rcx
0x18006f1c4  mov     ecx, [r15+0Ch]
0x18006f1c8  sub     ecx, [r15+4]
0x18006f1cc  sar     r10d, 4
0x18006f1d0  mov     [rsp+120h+var_C0], r10d
0x18006f1d5  xor     r10d, r10d
0x18006f1d8  mov     [rbp+3Fh+var_BC], ecx
0x18006f1db  mov     [rbp+3Fh+var_78.right], ecx
0x18006f1de  shl     eax, 4
0x18006f1e1  shl     ecx, 4
0x18006f1e4  sar     r8d, 4
0x18006f1e8  sar     edi, 4
0x18006f1eb  sar     edx, 4
0x18006f1ee  movups  xmmword ptr [rbp+3Fh+var_88.left], xmm0
0x18006f1f2  mov     [rbp+3Fh+var_78.bottom], r11d
0x18006f1f6  cmp     [rbx+10h], r9d
0x18006f1fa  jge     short loc_18006F219
0x18006f1fc  mov     dword ptr [rbp+3Fh+var_60], ecx
0x18006f1ff  mov     r9d, edi
0x18006f202  mov     [rbp+3Fh+pptfx.x], ecx
0x18006f205  mov     ecx, [rsp+120h+var_C0]
0x18006f209  mov     [rbp+3Fh+var_58], r10
0x18006f20d  mov     [rbp+3Fh+pptfx.y], r10d
0x18006f211  mov     dword ptr [rbp+3Fh+var_60+4], eax
0x18006f214  mov     [rbp+3Fh+var_88.top], edi
0x18006f217  jmp     short loc_18006F23A
0x18006f219  mov     dword ptr [rbp+3Fh+var_58], ecx
0x18006f21c  mov     r9d, edx
0x18006f21f  mov     ecx, r8d
0x18006f222  mov     [rbp+3Fh+var_88.top], edx
0x18006f225  mov     r8d, [rsp+120h+var_C0]
0x18006f22a  mov     edx, edi
0x18006f22c  mov     dword ptr [rbp+3Fh+var_58+4], eax
0x18006f22f  mov     [rbp+3Fh+pptfx.y], eax
0x18006f232  mov     [rbp+3Fh+var_60], r10
0x18006f236  mov     [rbp+3Fh+pptfx.x], r10d
0x18006f23a  mov     r10, [rbp+3Fh+psoDest]
0x18006f23e  mov     [rbp+3Fh+var_88.right], r8d
0x18006f242  mov     [rbp+3Fh+var_88.bottom], edx
0x18006f245  mov     [rbp+3Fh+var_88.left], ecx
0x18006f248  test    rsi, rsi
0x18006f24b  jz      short loc_18006F26E
0x18006f24d  mov     eax, [rsi+0Ch]
0x18006f250  sub     eax, r8d
0x18006f253  cmp     eax, 1
0x18006f256  jnz     short loc_18006F25F
0x18006f258  inc     r8d
0x18006f25b  mov     [rbp+3Fh+var_88.right], r8d
0x18006f25f  mov     eax, [rsi+10h]
0x18006f262  sub     eax, edx
0x18006f264  cmp     eax, 1
0x18006f267  jnz     short loc_18006F26E
0x18006f269  inc     edx
0x18006f26b  mov     [rbp+3Fh+var_88.bottom], edx
0x18006f26e  sub     r8d, ecx
0x18006f271  mov     ecx, r8d
0x18006f274  neg     ecx
0x18006f276  cmovs   ecx, r8d
0x18006f27a  mov     r8d, [rbp+3Fh+var_BC]; int
0x18006f27e  mov     eax, r8d
0x18006f281  neg     eax
0x18006f283  cmovs   eax, r8d
0x18006f287  cmp     ecx, eax
0x18006f289  jnz     short loc_18006F2A6
0x18006f28b  sub     edx, r9d
0x18006f28e  mov     eax, r11d
0x18006f291  mov     ecx, edx
0x18006f293  neg     ecx
0x18006f295  cmovs   ecx, edx
0x18006f298  neg     eax
0x18006f29a  cmovs   eax, r11d
0x18006f29e  cmp     ecx, eax
0x18006f2a0  jz      loc_18006F3B1
0x18006f2a6  mov     rax, [r10+10h]
0x18006f2aa  lea     rdx, [rbp+3Fh+hsurf]; int
0x18006f2ae  mov     r9d, r11d; int
0x18006f2b1  mov     rcx, [rax+8]
0x18006f2b5  mov     eax, [r14+48h]
0x18006f2b9  mov     dword ptr [rsp+120h+pxlo], eax; iFormat
0x18006f2bd  mov     rcx, [rcx+8]; int
0x18006f2c1  call    CreateBitmapSURFOBJ
0x18006f2c6  mov     rdi, rax
0x18006f2c9  test    rax, rax
0x18006f2cc  jz      loc_18006F3AD
0x18006f2d2  mov     rax, [rbp+3Fh+pptl]
0x18006f2d6  xor     r9d, r9d; pco
0x18006f2d9  mov     r15d, [rbp+3Fh+arg_50]
0x18006f2e0  xor     r8d, r8d; psoMsk
0x18006f2e3  mov     [rsp+120h+iMode], r15d; iMode
0x18006f2e8  mov     rdx, r14; psoSrc
0x18006f2eb  mov     [rsp+120h+pptlMask], rax; pptl
0x18006f2f0  mov     rcx, rdi; psoTrg
0x18006f2f3  mov     rax, [rbp+3Fh+prcl]
0x18006f2f7  mov     [rsp+120h+prclSrc], rax; prcl
0x18006f2fc  lea     rax, [rbp+3Fh+pptfx]
0x18006f300  mov     [rsp+120h+prclDest], rax; pptfx
0x18006f305  mov     [rsp+120h+pptlHTOrg], r13; pptlBrushOrg
0x18006f30a  mov     [rsp+120h+pca], r12; pca
0x18006f30f  mov     [rsp+120h+pxlo], 0; pxlo
0x18006f318  call    cs:__imp_EngPlgBlt
0x18006f31f  nop     dword ptr [rax+rax+00h]
0x18006f324  mov     ebx, eax
0x18006f326  test    eax, eax
0x18006f328  jz      short loc_18006F385
0x18006f32a  cmp     dword ptr [r14+48h], 1
0x18006f32f  mov     eax, 4
0x18006f334  mov     rcx, [rbp+3Fh+psoDest]; psoDest
0x18006f338  mov     r9, rsi; pco
0x18006f33b  cmovz   eax, r15d
0x18006f33f  mov     rdx, rdi; psoSrc
0x18006f342  mov     [rsp+120h+iMode], eax; iMode
0x18006f346  xor     r8d, r8d; psoMask
0x18006f349  mov     [rsp+120h+pptlMask], 0; pptlMask
0x18006f352  lea     rax, [rbp+3Fh+var_78]
0x18006f356  mov     [rsp+120h+prclSrc], rax; prclSrc
0x18006f35b  lea     rax, [rbp+3Fh+var_88]
0x18006f35f  mov     [rsp+120h+prclDest], rax; prclDest
0x18006f364  mov     rax, [rbp+3Fh+var_A8]
0x18006f368  mov     [rsp+120h+pptlHTOrg], r13; pptlHTOrg
0x18006f36d  mov     [rsp+120h+pca], r12; pca
0x18006f372  mov     [rsp+120h+pxlo], rax; pxlo
0x18006f377  call    cs:__imp_EngStretchBlt
0x18006f37e  nop     dword ptr [rax+rax+00h]
0x18006f383  mov     ebx, eax
0x18006f385  mov     rcx, rdi; pso
0x18006f388  call    cs:__imp_EngUnlockSurface
0x18006f38f  nop     dword ptr [rax+rax+00h]
0x18006f394  mov     rcx, [rbp+3Fh+hsurf]; hsurf
0x18006f398  test    rcx, rcx
0x18006f39b  jz      short loc_18006F3A9
0x18006f39d  call    cs:__imp_EngDeleteSurface
0x18006f3a4  nop     dword ptr [rax+rax+00h]
0x18006f3a9  mov     eax, ebx
0x18006f3ab  jmp     short loc_18006F3FB
0x18006f3ad  mov     r10, [rbp+3Fh+psoDest]
0x18006f3b1  mov     r11, [rbp+3Fh+var_98]
0x18006f3b5  mov     rax, [rbp+3Fh+pptl]
0x18006f3b9  mov     r9, rsi; pco
0x18006f3bc  mov     [rsp+120h+iMode], 4; iMode
0x18006f3c4  mov     r8, r11; psoMsk
0x18006f3c7  mov     [rsp+120h+pptlMask], rax; pptl
0x18006f3cc  mov     rdx, r14; psoSrc
0x18006f3cf  mov     rax, [rbp+3Fh+var_A8]
0x18006f3d3  mov     rcx, r10; psoTrg
0x18006f3d6  mov     [rsp+120h+prclSrc], r15; prcl
0x18006f3db  mov     [rsp+120h+prclDest], rbx; pptfx
0x18006f3e0  mov     [rsp+120h+pptlHTOrg], r13; pptlBrushOrg
0x18006f3e5  mov     [rsp+120h+pca], r12; pca
0x18006f3ea  mov     [rsp+120h+pxlo], rax; pxlo
0x18006f3ef  call    cs:__imp_EngPlgBlt
0x18006f3f6  nop     dword ptr [rax+rax+00h]
0x18006f3fb  mov     rcx, [rbp+3Fh+var_50]
0x18006f3ff  xor     rcx, rsp; StackCookie
0x18006f402  call    __security_check_cookie
0x18006f407  add     rsp, 0E8h
0x18006f40e  pop     r15
0x18006f410  pop     r14
0x18006f412  pop     r13
0x18006f414  pop     r12
0x18006f416  pop     rdi
0x18006f417  pop     rsi
0x18006f418  pop     rbx
0x18006f419  pop     rbp
0x18006f41a  retn
```
