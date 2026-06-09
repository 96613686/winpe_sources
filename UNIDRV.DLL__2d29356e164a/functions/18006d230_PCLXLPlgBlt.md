# PCLXLPlgBlt

- ea: `0x18006d230`
- end: `0x18006d597`
- name: `PCLXLPlgBlt`
- size: `871`
- prototype: `__int64 __fastcall(SURFOBJ *psoTrg, SURFOBJ *psoSrc, SURFOBJ *psoMsk, CLIPOBJ *pco, __int64, COLORADJUSTMENT *, POINTL *pptlBrushOrg, POINTFIX *, RECTL *, __int64, ULONG)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180042598`
- `0x1800487e0`
- `0x18006d230`

## import_xrefs

- `GDI32!EngPlgBlt` at `0x18006d4b2`
- `GDI32!EngPlgBlt` at `0x18006d571`
- `GDI32!EngPlgBlt` at `0x18006d4b2`
- `GDI32!EngPlgBlt` at `0x18006d571`
- `GDI32!EngStretchBlt` at `0x18006d301`
- `GDI32!EngStretchBlt` at `0x18006d50b`
- `GDI32!EngStretchBlt` at `0x18006d301`
- `GDI32!EngStretchBlt` at `0x18006d50b`
- `GDI32!EngUnlockSurface` at `0x18006d516`
- `GDI32!EngUnlockSurface` at `0x18006d516`
- `GDI32!EngDeleteSurface` at `0x18006d525`
- `GDI32!EngDeleteSurface` at `0x18006d525`

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
0x18006d230  push    rbp
0x18006d232  push    rbx
0x18006d233  push    rsi
0x18006d234  push    rdi
0x18006d235  push    r12
0x18006d237  push    r13
0x18006d239  push    r14
0x18006d23b  push    r15
0x18006d23d  lea     rbp, [rsp-7]
0x18006d242  sub     rsp, 0E8h
0x18006d249  mov     rax, cs:__security_cookie
0x18006d250  xor     rax, rsp
0x18006d253  mov     [rbp+3Fh+var_50], rax
0x18006d257  mov     rbx, [rbp+3Fh+arg_38]
0x18006d25e  mov     rsi, r9
0x18006d261  mov     rax, [rbp+3Fh+arg_20]
0x18006d265  mov     r11, r8
0x18006d268  mov     r15, [rbp+3Fh+arg_40]
0x18006d26f  mov     r14, rdx
0x18006d272  mov     r12, [rbp+3Fh+arg_28]
0x18006d276  mov     r10, rcx
0x18006d279  mov     r9d, [rbx]
0x18006d27c  mov     r13, [rbp+3Fh+pptlBrushOrg]
0x18006d280  mov     [rbp+3Fh+var_A8], rax
0x18006d284  mov     rax, [rbp+3Fh+arg_48]
0x18006d28b  mov     [rbp+3Fh+var_98], r8
0x18006d28f  mov     [rbp+3Fh+psoDest], rcx
0x18006d293  mov     [rbp+3Fh+prcl], r15
0x18006d297  mov     [rbp+3Fh+pptl], rax
0x18006d29b  cmp     r9d, [rbx+10h]
0x18006d29f  jnz     short loc_18006D30C
0x18006d2a1  mov     ecx, [rbx+4]
0x18006d2a4  cmp     ecx, [rbx+0Ch]
0x18006d2a7  jnz     short loc_18006D30C
0x18006d2a9  mov     eax, [rbx+14h]
0x18006d2ac  sar     eax, 4
0x18006d2af  mov     [rbp+3Fh+var_78.bottom], eax
0x18006d2b2  mov     eax, [rbx+8]
0x18006d2b5  mov     [rsp+120h+iMode], 4; iMode
0x18006d2bd  sar     eax, 4
0x18006d2c0  mov     [rbp+3Fh+var_78.right], eax
0x18006d2c3  mov     rax, [rbp+3Fh+pptl]
0x18006d2c7  mov     [rsp+120h+pptlMask], rax; pptlMask
0x18006d2cc  lea     rax, [rbp+3Fh+var_78]
0x18006d2d0  mov     [rsp+120h+prclSrc], r15; prclSrc
0x18006d2d5  mov     [rsp+120h+prclDest], rax; prclDest
0x18006d2da  mov     rax, [rbp+3Fh+var_A8]
0x18006d2de  sar     ecx, 4
0x18006d2e1  sar     r9d, 4
0x18006d2e5  mov     [rsp+120h+pptlHTOrg], r13; pptlHTOrg
0x18006d2ea  mov     [rbp+3Fh+var_78.top], ecx
0x18006d2ed  mov     rcx, r10; psoDest
0x18006d2f0  mov     [rbp+3Fh+var_78.left], r9d
0x18006d2f4  mov     r9, rsi; pco
0x18006d2f7  mov     [rsp+120h+pca], r12; pca
0x18006d2fc  mov     [rsp+120h+pxlo], rax; pxlo
0x18006d301  call    cs:__imp_EngStretchBlt
0x18006d307  jmp     loc_18006D577
0x18006d30c  xor     ecx, ecx
0x18006d30e  test    r8, r8
0x18006d311  jnz     loc_18006D537
0x18006d317  mov     r8d, [rbx+8]
0x18006d31b  cmp     r9d, r8d
0x18006d31e  jnz     loc_18006D537
0x18006d324  mov     edi, [rbx+14h]
0x18006d327  cmp     [rbx+4], edi
0x18006d32a  jnz     loc_18006D537
0x18006d330  mov     r10d, [rbx+10h]
0x18006d334  add     r8d, 0Fh
0x18006d338  mov     r11d, [r15+8]
0x18006d33c  add     r10d, 0Fh
0x18006d340  sub     r11d, [r15]
0x18006d343  add     edi, 0Fh
0x18006d346  mov     edx, [rbx+0Ch]
0x18006d349  mov     eax, r11d
0x18006d34c  mov     qword ptr [rbp+3Fh+var_78.right], rcx
0x18006d350  add     edx, 0Fh
0x18006d353  mov     [rbp+3Fh+hsurf], rcx
0x18006d357  xorps   xmm0, xmm0
0x18006d35a  mov     qword ptr [rbp+3Fh+var_78.left], rcx
0x18006d35e  mov     ecx, [r15+0Ch]
0x18006d362  sub     ecx, [r15+4]
0x18006d366  sar     r10d, 4
0x18006d36a  mov     [rsp+120h+var_C0], r10d
0x18006d36f  xor     r10d, r10d
0x18006d372  mov     [rbp+3Fh+var_BC], ecx
0x18006d375  mov     [rbp+3Fh+var_78.right], ecx
0x18006d378  shl     eax, 4
0x18006d37b  shl     ecx, 4
0x18006d37e  sar     r8d, 4
0x18006d382  sar     edi, 4
0x18006d385  sar     edx, 4
0x18006d388  movups  xmmword ptr [rbp+3Fh+var_88.left], xmm0
0x18006d38c  mov     [rbp+3Fh+var_78.bottom], r11d
0x18006d390  cmp     [rbx+10h], r9d
0x18006d394  jge     short loc_18006D3B3
0x18006d396  mov     dword ptr [rbp+3Fh+var_60], ecx
0x18006d399  mov     r9d, edi
0x18006d39c  mov     [rbp+3Fh+pptfx.x], ecx
0x18006d39f  mov     ecx, [rsp+120h+var_C0]
0x18006d3a3  mov     [rbp+3Fh+var_58], r10
0x18006d3a7  mov     [rbp+3Fh+pptfx.y], r10d
0x18006d3ab  mov     dword ptr [rbp+3Fh+var_60+4], eax
0x18006d3ae  mov     [rbp+3Fh+var_88.top], edi
0x18006d3b1  jmp     short loc_18006D3D4
0x18006d3b3  mov     dword ptr [rbp+3Fh+var_58], ecx
0x18006d3b6  mov     r9d, edx
0x18006d3b9  mov     ecx, r8d
0x18006d3bc  mov     [rbp+3Fh+var_88.top], edx
0x18006d3bf  mov     r8d, [rsp+120h+var_C0]
0x18006d3c4  mov     edx, edi
0x18006d3c6  mov     dword ptr [rbp+3Fh+var_58+4], eax
0x18006d3c9  mov     [rbp+3Fh+pptfx.y], eax
0x18006d3cc  mov     [rbp+3Fh+var_60], r10
0x18006d3d0  mov     [rbp+3Fh+pptfx.x], r10d
0x18006d3d4  mov     r10, [rbp+3Fh+psoDest]
0x18006d3d8  mov     [rbp+3Fh+var_88.right], r8d
0x18006d3dc  mov     [rbp+3Fh+var_88.bottom], edx
0x18006d3df  mov     [rbp+3Fh+var_88.left], ecx
0x18006d3e2  test    rsi, rsi
0x18006d3e5  jz      short loc_18006D408
0x18006d3e7  mov     eax, [rsi+0Ch]
0x18006d3ea  sub     eax, r8d
0x18006d3ed  cmp     eax, 1
0x18006d3f0  jnz     short loc_18006D3F9
0x18006d3f2  inc     r8d
0x18006d3f5  mov     [rbp+3Fh+var_88.right], r8d
0x18006d3f9  mov     eax, [rsi+10h]
0x18006d3fc  sub     eax, edx
0x18006d3fe  cmp     eax, 1
0x18006d401  jnz     short loc_18006D408
0x18006d403  inc     edx
0x18006d405  mov     [rbp+3Fh+var_88.bottom], edx
0x18006d408  sub     r8d, ecx
0x18006d40b  mov     ecx, r8d
0x18006d40e  neg     ecx
0x18006d410  cmovs   ecx, r8d
0x18006d414  mov     r8d, [rbp+3Fh+var_BC]; int
0x18006d418  mov     eax, r8d
0x18006d41b  neg     eax
0x18006d41d  cmovs   eax, r8d
0x18006d421  cmp     ecx, eax
0x18006d423  jnz     short loc_18006D440
0x18006d425  sub     edx, r9d
0x18006d428  mov     eax, r11d
0x18006d42b  mov     ecx, edx
0x18006d42d  neg     ecx
0x18006d42f  cmovs   ecx, edx
0x18006d432  neg     eax
0x18006d434  cmovs   eax, r11d
0x18006d438  cmp     ecx, eax
0x18006d43a  jz      loc_18006D533
0x18006d440  mov     rax, [r10+10h]
0x18006d444  lea     rdx, [rbp+3Fh+hsurf]; int
0x18006d448  mov     r9d, r11d; int
0x18006d44b  mov     rcx, [rax+8]
0x18006d44f  mov     eax, [r14+48h]
0x18006d453  mov     dword ptr [rsp+120h+pxlo], eax; iFormat
0x18006d457  mov     rcx, [rcx+8]; int
0x18006d45b  call    CreateBitmapSURFOBJ
0x18006d460  mov     rdi, rax
0x18006d463  test    rax, rax
0x18006d466  jz      loc_18006D52F
0x18006d46c  mov     rax, [rbp+3Fh+pptl]
0x18006d470  xor     r9d, r9d; pco
0x18006d473  mov     r15d, [rbp+3Fh+arg_50]
0x18006d47a  xor     r8d, r8d; psoMsk
0x18006d47d  mov     [rsp+120h+iMode], r15d; iMode
0x18006d482  mov     rdx, r14; psoSrc
0x18006d485  mov     [rsp+120h+pptlMask], rax; pptl
0x18006d48a  mov     rcx, rdi; psoTrg
0x18006d48d  mov     rax, [rbp+3Fh+prcl]
0x18006d491  mov     [rsp+120h+prclSrc], rax; prcl
0x18006d496  lea     rax, [rbp+3Fh+pptfx]
0x18006d49a  mov     [rsp+120h+prclDest], rax; pptfx
0x18006d49f  mov     [rsp+120h+pptlHTOrg], r13; pptlBrushOrg
0x18006d4a4  mov     [rsp+120h+pca], r12; pca
0x18006d4a9  mov     [rsp+120h+pxlo], 0; pxlo
0x18006d4b2  call    cs:__imp_EngPlgBlt
0x18006d4b8  mov     ebx, eax
0x18006d4ba  test    eax, eax
0x18006d4bc  jz      short loc_18006D513
0x18006d4be  cmp     dword ptr [r14+48h], 1
0x18006d4c3  mov     eax, 4
0x18006d4c8  mov     rcx, [rbp+3Fh+psoDest]; psoDest
0x18006d4cc  mov     r9, rsi; pco
0x18006d4cf  cmovz   eax, r15d
0x18006d4d3  mov     rdx, rdi; psoSrc
0x18006d4d6  mov     [rsp+120h+iMode], eax; iMode
0x18006d4da  xor     r8d, r8d; psoMask
0x18006d4dd  mov     [rsp+120h+pptlMask], 0; pptlMask
0x18006d4e6  lea     rax, [rbp+3Fh+var_78]
0x18006d4ea  mov     [rsp+120h+prclSrc], rax; prclSrc
0x18006d4ef  lea     rax, [rbp+3Fh+var_88]
0x18006d4f3  mov     [rsp+120h+prclDest], rax; prclDest
0x18006d4f8  mov     rax, [rbp+3Fh+var_A8]
0x18006d4fc  mov     [rsp+120h+pptlHTOrg], r13; pptlHTOrg
0x18006d501  mov     [rsp+120h+pca], r12; pca
0x18006d506  mov     [rsp+120h+pxlo], rax; pxlo
0x18006d50b  call    cs:__imp_EngStretchBlt
0x18006d511  mov     ebx, eax
0x18006d513  mov     rcx, rdi; pso
0x18006d516  call    cs:__imp_EngUnlockSurface
0x18006d51c  mov     rcx, [rbp+3Fh+hsurf]; hsurf
0x18006d520  test    rcx, rcx
0x18006d523  jz      short loc_18006D52B
0x18006d525  call    cs:__imp_EngDeleteSurface
0x18006d52b  mov     eax, ebx
0x18006d52d  jmp     short loc_18006D577
0x18006d52f  mov     r10, [rbp+3Fh+psoDest]
0x18006d533  mov     r11, [rbp+3Fh+var_98]
0x18006d537  mov     rax, [rbp+3Fh+pptl]
0x18006d53b  mov     r9, rsi; pco
0x18006d53e  mov     [rsp+120h+iMode], 4; iMode
0x18006d546  mov     r8, r11; psoMsk
0x18006d549  mov     [rsp+120h+pptlMask], rax; pptl
0x18006d54e  mov     rdx, r14; psoSrc
0x18006d551  mov     rax, [rbp+3Fh+var_A8]
0x18006d555  mov     rcx, r10; psoTrg
0x18006d558  mov     [rsp+120h+prclSrc], r15; prcl
0x18006d55d  mov     [rsp+120h+prclDest], rbx; pptfx
0x18006d562  mov     [rsp+120h+pptlHTOrg], r13; pptlBrushOrg
0x18006d567  mov     [rsp+120h+pca], r12; pca
0x18006d56c  mov     [rsp+120h+pxlo], rax; pxlo
0x18006d571  call    cs:__imp_EngPlgBlt
0x18006d577  mov     rcx, [rbp+3Fh+var_50]
0x18006d57b  xor     rcx, rsp; StackCookie
0x18006d57e  call    __security_check_cookie
0x18006d583  add     rsp, 0E8h
0x18006d58a  pop     r15
0x18006d58c  pop     r14
0x18006d58e  pop     r13
0x18006d590  pop     r12
0x18006d592  pop     rdi
0x18006d593  pop     rsi
0x18006d594  pop     rbx
0x18006d595  pop     rbp
0x18006d596  retn
```
