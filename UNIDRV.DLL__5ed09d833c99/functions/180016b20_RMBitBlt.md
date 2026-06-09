# RMBitBlt

- ea: `0x180016b20`
- end: `0x180017140`
- name: `RMBitBlt`
- size: `1568`
- prototype: `BOOL __fastcall(SURFOBJ *psoTrg, SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *, POINTL *, BRUSHOBJ *, POINTL *, ROP4 rop4)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180015fd0`
- `0x1800160e8`
- `0x180016b20`
- `0x180017148`
- `0x18004375c`
- `0x180049d00`
- `0x180060cf4`

## import_xrefs

- `GDI32!CLIPOBJ_bEnum` at `0x180016cf4`
- `GDI32!CLIPOBJ_bEnum` at `0x180016cf4`
- `GDI32!CLIPOBJ_cEnumStart` at `0x180016c60`
- `GDI32!CLIPOBJ_cEnumStart` at `0x180016c60`
- `GDI32!EngStretchBlt` at `0x180016f87`
- `GDI32!EngStretchBlt` at `0x180017019`
- `GDI32!EngStretchBlt` at `0x180016f87`
- `GDI32!EngStretchBlt` at `0x180017019`
- `GDI32!EngBitBlt` at `0x1800170ee`
- `GDI32!EngBitBlt` at `0x1800170ee`
- `GDI32!EngUnlockSurface` at `0x180017104`
- `GDI32!EngUnlockSurface` at `0x180017104`
- `GDI32!EngDeleteSurface` at `0x180017118`
- `GDI32!EngDeleteSurface` at `0x180017118`

## pseudocode

```c
BOOL __fastcall RMBitBlt(
        SURFOBJ *psoTrg,
        SURFOBJ *a2,
        SURFOBJ *a3,
        CLIPOBJ *a4,
        XLATEOBJ *a5,
        RECTL *a6,
        POINTL *a7,
        POINTL *a8,
        BRUSHOBJ *a9,
        POINTL *a10,
        ROP4 rop4)
{
  POINTL *v12; // rcx
  XLATEOBJ *v13; // r8
  DHPDEV dhpdev; // rsi
  SURFOBJ *v16; // r10
  RECTL *v17; // r9
  bool v18; // zf
  ULONG iMode; // r12d
  ROP4 v20; // ebx
  ULONG v21; // eax
  BOOL v22; // r12d
  __int64 v23; // rdi
  __int64 v24; // rbx
  LONG left; // eax
  LONG top; // eax
  LONG right; // eax
  LONG bottom; // eax
  int v29; // r10d
  int v30; // edx
  int v31; // r15d
  int v32; // r8d
  unsigned int i; // r9d
  __int64 v34; // rcx
  int v35; // r11d
  int v36; // edx
  int v37; // edx
  HSURF v39; // rdi
  SURFOBJ *BitmapSURFOBJ; // r15
  LONG y; // eax
  LONG x; // ecx
  LONG v43; // ecx
  __int64 v44; // r8
  __int64 v45; // r9
  BRUSHOBJ *v46; // r12
  RECTL *v47; // rsi
  BOOL v48; // ebx
  POINTL pptlBrush; // [rsp+60h] [rbp-91h] BYREF
  RECTL *prclTrg; // [rsp+68h] [rbp-89h]
  XLATEOBJ *pxlo; // [rsp+70h] [rbp-81h]
  SURFOBJ *psoSrc; // [rsp+78h] [rbp-79h]
  int v53[2]; // [rsp+80h] [rbp-71h] BYREF
  BRUSHOBJ *pbo; // [rsp+88h] [rbp-69h]
  POINTL *pptlSrc; // [rsp+90h] [rbp-61h]
  POINTL *pptlHTOrg; // [rsp+98h] [rbp-59h]
  POINTL *pptlMask; // [rsp+A0h] [rbp-51h]
  SURFOBJ *psoMask; // [rsp+A8h] [rbp-49h]
  RECTL prclDest; // [rsp+B0h] [rbp-41h] BYREF
  RECTL prclSrc; // [rsp+C0h] [rbp-31h] BYREF
  ULONG pul[4]; // [rsp+D0h] [rbp-21h] BYREF
  LONG v62; // [rsp+E0h] [rbp-11h]

  v12 = a10;
  psoMask = a3;
  v13 = a5;
  dhpdev = psoTrg->dhpdev;
  v16 = a2;
  v17 = a6;
  psoSrc = a2;
  pptlSrc = a7;
  prclDest = 0;
  pptlBrush = 0;
  prclSrc = 0;
  v18 = ((_DWORD)dhpdev[28] & 0x8000) == 0;
  prclTrg = a6;
  pbo = a9;
  pxlo = a5;
  pptlMask = a8;
  pptlHTOrg = a10;
  if ( v18 )
    return 1;
  iMode = 4;
  v20 = rop4;
  if ( !*((_QWORD *)dhpdev + 220) || *((_DWORD *)dhpdev + 442) >= 0xFCu )
  {
    if ( rop4 == 61680 )
      goto LABEL_66;
LABEL_65:
    if ( rop4 != 52428 )
      goto LABEL_67;
    goto LABEL_66;
  }
  if ( rop4 != 61680 )
    goto LABEL_65;
  if ( a9 && !a5 && (!a4 || a4->iDComplexity != 3 || a4->iFComplexity == 2) )
  {
    if ( psoTrg->iBitmapFormat == 5 )
    {
      if ( !a9->iSolidColor )
      {
LABEL_14:
        if ( !a4 || a4->iFComplexity != 2 || (v21 = CLIPOBJ_cEnumStart(a4, 1, 0, 4u, 4u), v17 = prclTrg, v21 != -1) )
        {
          v22 = 0;
          while ( 1 )
          {
            v23 = *((_QWORD *)dhpdev + 220);
            v24 = 2LL * *((unsigned int *)dhpdev + 442);
            *(RECTL *)(v23 + 16LL * *((unsigned int *)dhpdev + 442)) = *v17;
            if ( !a4 )
              goto LABEL_38;
            if ( a4->iDComplexity == 1 )
              break;
            if ( a4->iFComplexity != 2 )
              goto LABEL_38;
            v62 = 0;
            *(_OWORD *)pul = 0;
            v22 = CLIPOBJ_bEnum(a4, 0x14u, pul);
            if ( pul[0] == 1 )
            {
              if ( *(_DWORD *)(v23 + 8 * v24) < (int)pul[1] )
                *(_DWORD *)(v23 + 8 * v24) = pul[1];
              if ( *(_DWORD *)(v23 + 8 * v24 + 4) < (int)pul[2] )
                *(_DWORD *)(v23 + 8 * v24 + 4) = pul[2];
              if ( *(_DWORD *)(v23 + 8 * v24 + 8) > (int)pul[3] )
                *(_DWORD *)(v23 + 8 * v24 + 8) = pul[3];
              bottom = v62;
              goto LABEL_36;
            }
LABEL_61:
            if ( v22 )
            {
              v17 = prclTrg;
              if ( *((_DWORD *)dhpdev + 442) < 0x100u )
                continue;
            }
            return 1;
          }
          left = a4->rclBounds.left;
          if ( *(_DWORD *)(v23 + 8 * v24) < left )
            *(_DWORD *)(v23 + 8 * v24) = left;
          top = a4->rclBounds.top;
          if ( *(_DWORD *)(v23 + 8 * v24 + 4) < top )
            *(_DWORD *)(v23 + 8 * v24 + 4) = top;
          right = a4->rclBounds.right;
          if ( *(_DWORD *)(v23 + 8 * v24 + 8) > right )
            *(_DWORD *)(v23 + 8 * v24 + 8) = right;
          bottom = a4->rclBounds.bottom;
LABEL_36:
          if ( *(_DWORD *)(v23 + 8 * v24 + 12) > bottom )
            *(_DWORD *)(v23 + 8 * v24 + 12) = bottom;
LABEL_38:
          v29 = *(_DWORD *)(v23 + 8 * v24 + 8);
          v30 = *(_DWORD *)(v23 + 8 * v24);
          if ( v30 < v29 )
          {
            v31 = *(_DWORD *)(v23 + 8 * v24 + 12);
            v32 = *(_DWORD *)(v23 + 8 * v24 + 4);
            if ( v32 < v31 )
            {
              for ( i = 0; i < *((_DWORD *)dhpdev + 442); ++i )
              {
                v34 = *((_QWORD *)dhpdev + 220);
                v35 = *(_DWORD *)(v34 + 16LL * i + 4);
                if ( v32 == v35
                  && v31 == *(_DWORD *)(v34 + 16LL * i + 12)
                  && v30 <= *(_DWORD *)(v34 + 16LL * i + 8)
                  && v29 >= *(_DWORD *)(v34 + 16LL * i) )
                {
                  if ( *(_DWORD *)(v34 + 16LL * i) > v30 )
                    *(_DWORD *)(v34 + 16LL * i) = v30;
                  v36 = *(_DWORD *)(v23 + 8 * v24 + 8);
                  if ( *(_DWORD *)(v34 + 16LL * i + 8) < v36 )
                    *(_DWORD *)(v34 + 16LL * i + 8) = v36;
                  goto LABEL_59;
                }
                if ( v30 == *(_DWORD *)(v34 + 16LL * i)
                  && v29 == *(_DWORD *)(v34 + 16LL * i + 8)
                  && v32 <= *(_DWORD *)(v34 + 16LL * i + 12)
                  && v31 >= v35 )
                {
                  if ( v35 > v32 )
                    *(_DWORD *)(v34 + 16LL * i + 4) = v32;
                  v37 = *(_DWORD *)(v23 + 8 * v24 + 12);
                  if ( *(_DWORD *)(v34 + 16LL * i + 12) < v37 )
                    *(_DWORD *)(v34 + 16LL * i + 12) = v37;
LABEL_59:
                  --*((_DWORD *)dhpdev + 442);
                  break;
                }
              }
              ++*((_DWORD *)dhpdev + 442);
            }
          }
          goto LABEL_61;
        }
      }
    }
    else if ( a9->iSolidColor == *(_DWORD *)(*((_QWORD *)dhpdev + 512) + 4LL) )
    {
      goto LABEL_14;
    }
  }
LABEL_66:
  DrawWhiteRect((__int64)dhpdev, &v17->left, a4);
  v13 = pxlo;
  v12 = pptlHTOrg;
  v16 = psoSrc;
LABEL_67:
  v39 = 0;
  BitmapSURFOBJ = 0;
  *(_QWORD *)v53 = 0;
  if ( (((BYTE1(rop4) ^ (unsigned __int8)(rop4 >> 12)) & 0xF) != 0
     || (((unsigned __int8)rop4 ^ (unsigned __int8)(rop4 >> 4)) & 0xF) != 0)
    && v12 )
  {
    pptlBrush = *v12;
    y = pptlBrush.y;
    x = pptlBrush.x;
  }
  else
  {
    y = 0;
    pptlBrush = 0;
    x = 0;
  }
  pptlBrush.x = x - *((_DWORD *)dhpdev + 495);
  pptlBrush.y = y - *((_DWORD *)dhpdev + 496);
  if ( (((BYTE1(rop4) ^ (unsigned __int8)(rop4 >> 10)) & 0x33) != 0
     || (((unsigned __int8)rop4 ^ (unsigned __int8)(rop4 >> 2)) & 0x33) != 0)
    && !(unsigned int)IsHTCompatibleSurfObj(*((_QWORD *)dhpdev + 512), (__int64)psoTrg, (__int64)v16, (__int64)v13) )
  {
    *(_QWORD *)&prclDest.left = 0;
    v43 = pptlSrc->y;
    v44 = (unsigned int)(prclTrg->right - prclTrg->left);
    v45 = (unsigned int)(prclTrg->bottom - prclTrg->top);
    prclSrc.left = pptlSrc->x;
    prclSrc.right = v44 + prclSrc.left;
    prclDest.right = v44;
    prclDest.bottom = v45;
    prclSrc.bottom = v43 + v45;
    prclSrc.top = v43;
    if ( rop4 == 52428 )
    {
      CheckBitmapSurface(psoTrg, &prclTrg->left, v44, v45);
      return EngStretchBlt(psoTrg, psoSrc, psoMask, a4, pxlo, 0, pptlHTOrg, prclTrg, &prclSrc, pptlMask, 4u);
    }
    BitmapSURFOBJ = CreateBitmapSURFOBJ((__int64)dhpdev, (HSURF *)v53, v44, v45, psoTrg->iBitmapFormat);
    if ( BitmapSURFOBJ )
    {
      if ( ((_DWORD)dhpdev[29] & 0x100000) != 0 && psoTrg->iBitmapFormat == 1 )
        iMode = 3;
      if ( EngStretchBlt(BitmapSURFOBJ, psoSrc, 0, 0, pxlo, 0, &pptlBrush, &prclDest, &prclSrc, 0, iMode) )
      {
        psoSrc = BitmapSURFOBJ;
        pptlSrc = (POINTL *)&prclDest;
        pxlo = 0;
      }
    }
    v39 = *(HSURF *)v53;
  }
  v46 = pbo;
  if ( ((_DWORD)dhpdev[28] & 0x800000) != 0
    || rop4 != 61680
    || !pbo
    || *((_QWORD *)dhpdev + 220) && *((_DWORD *)dhpdev + 442) )
  {
    goto LABEL_91;
  }
  if ( psoTrg->iBitmapFormat == 5 )
  {
    if ( pbo->iSolidColor != 0xFFFFFF )
      goto LABEL_91;
  }
  else if ( pbo->iSolidColor != **((_DWORD **)dhpdev + 512) )
  {
LABEL_91:
    if ( ((_BYTE)dhpdev[29] & 0x20) != 0 )
      v20 = InvertROPs(rop4);
    v47 = prclTrg;
    CheckBitmapSurface(psoTrg, &prclTrg->left, (__int64)v13, (__int64)v17);
    v48 = EngBitBlt(psoTrg, psoSrc, psoMask, a4, pxlo, v47, pptlSrc, pptlMask, v46, &pptlBrush, v20);
    goto LABEL_94;
  }
  v48 = 1;
LABEL_94:
  if ( BitmapSURFOBJ )
    EngUnlockSurface(BitmapSURFOBJ);
  if ( v39 )
    EngDeleteSurface(v39);
  return v48;
}

```

## disassembly

```asm
0x180016b20  push    rbp
0x180016b22  push    rbx
0x180016b23  push    rsi
0x180016b24  push    rdi
0x180016b25  push    r12
0x180016b27  push    r13
0x180016b29  push    r14
0x180016b2b  push    r15
0x180016b2d  lea     rbp, [rsp-7]
0x180016b32  sub     rsp, 0F8h
0x180016b39  mov     rax, cs:__security_cookie
0x180016b40  xor     rax, rsp
0x180016b43  mov     [rbp+3Fh+var_48], rax
0x180016b47  mov     rax, [rbp+3Fh+arg_30]
0x180016b4b  mov     r13, rcx
0x180016b4e  mov     rcx, [rbp+3Fh+arg_48]
0x180016b55  xorps   xmm0, xmm0
0x180016b58  xorps   xmm1, xmm1
0x180016b5b  mov     [rbp+3Fh+psoMask], r8
0x180016b5f  mov     r8, [rbp+3Fh+arg_20]
0x180016b63  mov     r14, r9
0x180016b66  mov     rsi, [r13+10h]
0x180016b6a  mov     r10, rdx
0x180016b6d  mov     r9, [rbp+3Fh+arg_28]
0x180016b71  mov     r15d, 1
0x180016b77  mov     [rbp+3Fh+psoSrc], rdx
0x180016b7b  mov     rdx, [rbp+3Fh+arg_40]
0x180016b82  mov     [rbp+3Fh+pptlSrc], rax
0x180016b86  mov     rax, [rbp+3Fh+arg_38]
0x180016b8d  movups  xmmword ptr [rbp+3Fh+var_80.left], xmm0
0x180016b91  mov     qword ptr [rsp+130h+pptlBrush.x], 0
0x180016b9a  movups  xmmword ptr [rbp+3Fh+var_70.left], xmm1
0x180016b9e  test    dword ptr [rsi+70h], 8000h
0x180016ba5  mov     [rsp+130h+prclTrg], r9
0x180016baa  mov     [rbp+3Fh+pbo], rdx
0x180016bae  mov     [rsp+130h+pxlo], r8
0x180016bb3  mov     [rbp+3Fh+var_90], rax
0x180016bb7  mov     [rbp+3Fh+var_98], rcx
0x180016bbb  jz      loc_180016E1C
0x180016bc1  cmp     qword ptr [rsi+6E0h], 0
0x180016bc9  lea     r12d, [r15+3]
0x180016bcd  mov     ebx, [rbp+3Fh+rop4]
0x180016bd3  mov     eax, 0F0F0h
0x180016bd8  jz      loc_180016E40
0x180016bde  cmp     dword ptr [rsi+6E8h], 0FCh
0x180016be8  jnb     loc_180016E40
0x180016bee  cmp     ebx, eax
0x180016bf0  jnz     loc_180016E44
0x180016bf6  test    rdx, rdx
0x180016bf9  jz      loc_180016E4C
0x180016bff  test    r8, r8
0x180016c02  jnz     loc_180016E4C
0x180016c08  test    r14, r14
0x180016c0b  jz      short loc_180016C1F
0x180016c0d  cmp     byte ptr [r14+14h], 3
0x180016c12  jnz     short loc_180016C1F
0x180016c14  cmp     byte ptr [r14+15h], 2
0x180016c19  jnz     loc_180016E4C
0x180016c1f  cmp     dword ptr [r13+48h], 5
0x180016c24  jz      short loc_180016C3A
0x180016c26  mov     rax, [rsi+1000h]
0x180016c2d  mov     ecx, [rax+4]
0x180016c30  cmp     [rdx], ecx
0x180016c32  jnz     loc_180016E4C
0x180016c38  jmp     short loc_180016C43
0x180016c3a  cmp     dword ptr [rdx], 0
0x180016c3d  jnz     loc_180016E4C
0x180016c43  test    r14, r14
0x180016c46  jz      short loc_180016C7A
0x180016c48  cmp     byte ptr [r14+15h], 2
0x180016c4d  jnz     short loc_180016C7A
0x180016c4f  mov     r9d, r12d; iDirection
0x180016c52  mov     [rsp+130h+cLimit], r12d; cLimit
0x180016c57  xor     r8d, r8d; iType
0x180016c5a  mov     edx, r15d; bAll
0x180016c5d  mov     rcx, r14; pco
0x180016c60  call    cs:__imp_CLIPOBJ_cEnumStart
0x180016c67  nop     dword ptr [rax+rax+00h]
0x180016c6c  mov     r9, [rsp+130h+prclTrg]
0x180016c71  cmp     eax, 0FFFFFFFFh
0x180016c74  jz      loc_180016E4C
0x180016c7a  xor     r12d, r12d
0x180016c7d  or      r13d, 0FFFFFFFFh
0x180016c81  mov     ebx, [rsi+6E8h]
0x180016c87  mov     rdi, [rsi+6E0h]
0x180016c8e  add     rbx, rbx
0x180016c91  movups  xmm0, xmmword ptr [r9]
0x180016c95  movdqu  xmmword ptr [rdi+rbx*8], xmm0
0x180016c9a  test    r14, r14
0x180016c9d  jz      loc_180016D3F
0x180016ca3  cmp     [r14+14h], r15b
0x180016ca7  jnz     short loc_180016CD7
0x180016ca9  mov     eax, [r14+4]
0x180016cad  cmp     [rdi+rbx*8], eax
0x180016cb0  jge     short loc_180016CB5
0x180016cb2  mov     [rdi+rbx*8], eax
0x180016cb5  mov     eax, [r14+8]
0x180016cb9  cmp     [rdi+rbx*8+4], eax
0x180016cbd  jge     short loc_180016CC3
0x180016cbf  mov     [rdi+rbx*8+4], eax
0x180016cc3  mov     eax, [r14+0Ch]
0x180016cc7  cmp     [rdi+rbx*8+8], eax
0x180016ccb  jle     short loc_180016CD1
0x180016ccd  mov     [rdi+rbx*8+8], eax
0x180016cd1  mov     eax, [r14+10h]
0x180016cd5  jmp     short loc_180016D35
0x180016cd7  cmp     byte ptr [r14+15h], 2
0x180016cdc  jnz     short loc_180016D3F
0x180016cde  xor     eax, eax
0x180016ce0  lea     r8, [rbp+3Fh+pul]; pul
0x180016ce4  xorps   xmm0, xmm0
0x180016ce7  mov     [rbp+3Fh+var_50], eax
0x180016cea  mov     rcx, r14; pco
0x180016ced  movups  xmmword ptr [rbp+3Fh+pul], xmm0
0x180016cf1  lea     edx, [rax+14h]; cj
0x180016cf4  call    cs:__imp_CLIPOBJ_bEnum
0x180016cfb  nop     dword ptr [rax+rax+00h]
0x180016d00  mov     r12d, eax
0x180016d03  cmp     [rbp+3Fh+pul], r15d
0x180016d07  jnz     loc_180016E02
0x180016d0d  mov     ecx, [rbp+3Fh+pul+4]
0x180016d10  cmp     [rdi+rbx*8], ecx
0x180016d13  jge     short loc_180016D18
0x180016d15  mov     [rdi+rbx*8], ecx
0x180016d18  mov     ecx, [rbp+3Fh+pul+8]
0x180016d1b  cmp     [rdi+rbx*8+4], ecx
0x180016d1f  jge     short loc_180016D25
0x180016d21  mov     [rdi+rbx*8+4], ecx
0x180016d25  mov     eax, [rbp+3Fh+pul+0Ch]
0x180016d28  cmp     [rdi+rbx*8+8], eax
0x180016d2c  jle     short loc_180016D32
0x180016d2e  mov     [rdi+rbx*8+8], eax
0x180016d32  mov     eax, [rbp+3Fh+var_50]
0x180016d35  cmp     [rdi+rbx*8+0Ch], eax
0x180016d39  jle     short loc_180016D3F
0x180016d3b  mov     [rdi+rbx*8+0Ch], eax
0x180016d3f  mov     r10d, [rdi+rbx*8+8]
0x180016d44  mov     edx, [rdi+rbx*8]
0x180016d47  cmp     edx, r10d
0x180016d4a  jge     loc_180016E02
0x180016d50  mov     r15d, [rdi+rbx*8+0Ch]
0x180016d55  mov     r8d, [rdi+rbx*8+4]
0x180016d5a  cmp     r8d, r15d
0x180016d5d  jge     loc_180016DFC
0x180016d63  xor     r9d, r9d
0x180016d66  cmp     r9d, [rsi+6E8h]
0x180016d6d  jnb     short loc_180016DED
0x180016d6f  mov     rcx, [rsi+6E0h]
0x180016d76  mov     eax, r9d
0x180016d79  add     rax, rax
0x180016d7c  mov     r11d, [rcx+rax*8+4]
0x180016d81  cmp     r8d, r11d
0x180016d84  jnz     short loc_180016D99
0x180016d86  cmp     r15d, [rcx+rax*8+0Ch]
0x180016d8b  jnz     short loc_180016D99
0x180016d8d  cmp     edx, [rcx+rax*8+8]
0x180016d91  jg      short loc_180016D99
0x180016d93  cmp     r10d, [rcx+rax*8]
0x180016d97  jge     short loc_180016DB6
0x180016d99  cmp     edx, [rcx+rax*8]
0x180016d9c  jnz     short loc_180016DB1
0x180016d9e  cmp     r10d, [rcx+rax*8+8]
0x180016da3  jnz     short loc_180016DB1
0x180016da5  cmp     r8d, [rcx+rax*8+0Ch]
0x180016daa  jg      short loc_180016DB1
0x180016dac  cmp     r15d, r11d
0x180016daf  jge     short loc_180016DCE
0x180016db1  inc     r9d
0x180016db4  jmp     short loc_180016D66
0x180016db6  cmp     [rcx+rax*8], edx
0x180016db9  jle     short loc_180016DBE
0x180016dbb  mov     [rcx+rax*8], edx
0x180016dbe  mov     edx, [rdi+rbx*8+8]
0x180016dc2  cmp     [rcx+rax*8+8], edx
0x180016dc6  jge     short loc_180016DE6
0x180016dc8  mov     [rcx+rax*8+8], edx
0x180016dcc  jmp     short loc_180016DE6
0x180016dce  cmp     r11d, r8d
0x180016dd1  jle     short loc_180016DD8
0x180016dd3  mov     [rcx+rax*8+4], r8d
0x180016dd8  mov     edx, [rdi+rbx*8+0Ch]
0x180016ddc  cmp     [rcx+rax*8+0Ch], edx
0x180016de0  jge     short loc_180016DE6
0x180016de2  mov     [rcx+rax*8+0Ch], edx
0x180016de6  add     [rsi+6E8h], r13d
0x180016ded  mov     r15d, 1
0x180016df3  add     [rsi+6E8h], r15d
0x180016dfa  jmp     short loc_180016E02
0x180016dfc  mov     r15d, 1
0x180016e02  test    r12d, r12d
0x180016e05  jz      short loc_180016E1C
0x180016e07  cmp     dword ptr [rsi+6E8h], 100h
0x180016e11  mov     r9, [rsp+130h+prclTrg]
0x180016e16  jb      loc_180016C81
0x180016e1c  mov     eax, r15d
0x180016e1f  mov     rcx, [rbp+3Fh+var_48]
0x180016e23  xor     rcx, rsp; StackCookie
0x180016e26  call    __security_check_cookie
0x180016e2b  add     rsp, 0F8h
0x180016e32  pop     r15
0x180016e34  pop     r14
0x180016e36  pop     r13
0x180016e38  pop     r12
0x180016e3a  pop     rdi
0x180016e3b  pop     rsi
0x180016e3c  pop     rbx
0x180016e3d  pop     rbp
0x180016e3e  retn
0x180016e40  cmp     ebx, eax
0x180016e42  jz      short loc_180016E4C
0x180016e44  cmp     ebx, 0CCCCh
0x180016e4a  jnz     short loc_180016E67
0x180016e4c  mov     r8, r14
0x180016e4f  mov     rdx, r9
0x180016e52  mov     rcx, rsi
0x180016e55  call    DrawWhiteRect
0x180016e5a  mov     r8, [rsp+130h+pxlo]
0x180016e5f  mov     rcx, [rbp+3Fh+var_98]
0x180016e63  mov     r10, [rbp+3Fh+psoSrc]
0x180016e67  xor     edi, edi
0x180016e69  mov     edx, ebx
0x180016e6b  shr     edx, 8
0x180016e6e  mov     eax, ebx
0x180016e70  shr     eax, 0Ch
0x180016e73  xor     r15d, r15d
0x180016e76  xor     eax, edx
0x180016e78  mov     qword ptr [rbp+3Fh+var_B0], rdi
0x180016e7c  test    al, 0Fh
0x180016e7e  jnz     short loc_180016E8B
0x180016e80  mov     eax, ebx
0x180016e82  shr     eax, 4
0x180016e85  xor     eax, ebx
0x180016e87  test    al, 0Fh
0x180016e89  jz      short loc_180016EA2
0x180016e8b  test    rcx, rcx
0x180016e8e  jz      short loc_180016EA2
0x180016e90  mov     rax, [rcx]
0x180016e93  mov     qword ptr [rsp+130h+pptlBrush.x], rax
0x180016e98  mov     eax, [rsp+130h+pptlBrush.y]
0x180016e9c  mov     ecx, [rsp+130h+pptlBrush.x]
0x180016ea0  jmp     short loc_180016EAB
0x180016ea2  xor     eax, eax
0x180016ea4  mov     qword ptr [rsp+130h+pptlBrush.x], rax
0x180016ea9  xor     ecx, ecx
0x180016eab  sub     ecx, [rsi+7BCh]
0x180016eb1  mov     [rsp+130h+pptlBrush.x], ecx
0x180016eb5  sub     eax, [rsi+7C0h]
0x180016ebb  mov     [rsp+130h+pptlBrush.y], eax
0x180016ebf  mov     eax, ebx
0x180016ec1  shr     eax, 0Ah
0x180016ec4  xor     eax, edx
0x180016ec6  test    al, 33h
0x180016ec8  jnz     short loc_180016ED9
0x180016eca  mov     eax, ebx
0x180016ecc  shr     eax, 2
0x180016ecf  xor     eax, ebx
0x180016ed1  test    al, 33h
0x180016ed3  jz      loc_180017042
0x180016ed9  mov     rcx, [rsi+1000h]
0x180016ee0  mov     r9, r8
0x180016ee3  mov     r8, r10
0x180016ee6  mov     rdx, r13
0x180016ee9  call    IsHTCompatibleSurfObj
0x180016eee  test    eax, eax
0x180016ef0  jnz     loc_180017042
0x180016ef6  mov     rcx, [rbp+3Fh+pptlSrc]
0x180016efa  mov     qword ptr [rbp+3Fh+var_80.left], rdi
0x180016efe  mov     rdi, [rsp+130h+prclTrg]
0x180016f03  mov     eax, [rcx]
0x180016f05  mov     ecx, [rcx+4]
0x180016f08  mov     r8d, [rdi+8]
0x180016f0c  sub     r8d, [rdi]; int
0x180016f0f  mov     r9d, [rdi+0Ch]
0x180016f13  sub     r9d, [rdi+4]; int
0x180016f17  mov     [rbp+3Fh+var_70.left], eax
0x180016f1a  add     eax, r8d
0x180016f1d  mov     [rbp+3Fh+var_70.right], eax
0x180016f20  mov     [rbp+3Fh+var_80.right], r8d
0x180016f24  mov     [rbp+3Fh+var_80.bottom], r9d
0x180016f28  lea     eax, [rcx+r9]
0x180016f2c  mov     [rbp+3Fh+var_70.bottom], eax
0x180016f2f  mov     [rbp+3Fh+var_70.top], ecx
0x180016f32  cmp     ebx, 0CCCCh
0x180016f38  jnz     short loc_180016F98
0x180016f3a  mov     rdx, rdi
0x180016f3d  mov     rcx, r13
0x180016f40  call    CheckBitmapSurface
0x180016f45  mov     rax, [rbp+3Fh+var_90]
0x180016f49  mov     r9, r14; pco
0x180016f4c  mov     r8, [rbp+3Fh+psoMask]; psoMask
0x180016f50  mov     rcx, r13; psoDest
0x180016f53  mov     rdx, [rbp+3Fh+psoSrc]; psoSrc
0x180016f57  mov     [rsp+130h+iMode], r12d; iMode
0x180016f5c  mov     [rsp+130h+pptlMask], rax; pptlMask
0x180016f61  lea     rax, [rbp+3Fh+var_70]
0x180016f65  mov     [rsp+130h+prclSrc], rax; prclSrc
0x180016f6a  mov     rax, [rbp+3Fh+var_98]
0x180016f6e  mov     [rsp+130h+prclDest], rdi; prclDest
0x180016f73  mov     [rsp+130h+pptlHTOrg], rax; pptlHTOrg
0x180016f78  mov     rax, [rsp+130h+pxlo]
  ... truncated ...
```
