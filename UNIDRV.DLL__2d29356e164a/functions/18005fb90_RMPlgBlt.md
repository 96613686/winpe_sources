# RMPlgBlt

- ea: `0x18005fb90`
- end: `0x18005ff47`
- name: `RMPlgBlt`
- size: `951`
- prototype: `__int64 __usercall@<rax>(SURFOBJ *psoTrg@<rcx>, SURFOBJ *psoSrc@<rdx>, __int64, COLORADJUSTMENT *, POINTL *, POINTFIX *, RECTL *, __int64, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180016e6c`
- `0x180042598`
- `0x1800487e0`
- `0x18005fb90`

## import_xrefs

- `GDI32!EngPlgBlt` at `0x18005fe42`
- `GDI32!EngPlgBlt` at `0x18005ff21`
- `GDI32!EngPlgBlt` at `0x18005fe42`
- `GDI32!EngPlgBlt` at `0x18005ff21`
- `GDI32!EngStretchBlt` at `0x18005fc86`
- `GDI32!EngStretchBlt` at `0x18005feaf`
- `GDI32!EngStretchBlt` at `0x18005fc86`
- `GDI32!EngStretchBlt` at `0x18005feaf`
- `GDI32!EngUnlockSurface` at `0x18005feba`
- `GDI32!EngUnlockSurface` at `0x18005feba`
- `GDI32!EngDeleteSurface` at `0x18005fec9`
- `GDI32!EngDeleteSurface` at `0x18005fec9`

## pseudocode

```c
BOOL __fastcall RMPlgBlt(
        SURFOBJ *psoTrg,
        SURFOBJ *psoSrc,
        SURFOBJ *a3,
        CLIPOBJ *a4,
        XLATEOBJ *pxlo,
        COLORADJUSTMENT *pca,
        POINTL *pptlHTOrg,
        POINTFIX *a8,
        RECTL *prclSrc,
        POINTL *pptlMask,
        ULONG iMode)
{
  POINTL *v14; // rsi
  DHPDEV dhpdev; // rax
  int x; // eax
  FIX y; // edx
  FIX v19; // eax
  FIX v20; // edx
  FIX v21; // r11d
  LONG v22; // r9d
  FIX v23; // r8d
  int v24; // edi
  int v25; // r10d
  FIX v26; // r9d
  LONG v27; // edx
  LONG v28; // r11d
  LONG v29; // edi
  LONG v30; // r8d
  LONG v31; // ecx
  LONG v32; // r9d
  int v33; // edx
  int v34; // ecx
  int v35; // eax
  int v36; // r8d
  int v37; // edx
  int v38; // eax
  SURFOBJ *v39; // rax
  SURFOBJ *v40; // rsi
  BOOL v41; // ebx
  ULONG v42; // edi
  signed int v43; // [rsp+70h] [rbp-81h]
  HSURF hsurf; // [rsp+90h] [rbp-61h] BYREF
  SURFOBJ *psoMask; // [rsp+98h] [rbp-59h]
  RECTL *prcl; // [rsp+A0h] [rbp-51h]
  RECTL v47; // [rsp+A8h] [rbp-49h] BYREF
  RECTL prclDest; // [rsp+B8h] [rbp-39h] BYREF
  POINTFIX pptfx; // [rsp+C8h] [rbp-29h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-21h]
  __int64 v51; // [rsp+D8h] [rbp-19h]

  v14 = pptlHTOrg;
  dhpdev = psoTrg->dhpdev;
  psoMask = a3;
  prcl = prclSrc;
  if ( ((_DWORD)dhpdev[28] & 0x8000) == 0 )
    return 1;
  x = a8->x;
  if ( a8->x == a8[2].x )
  {
    y = a8->y;
    if ( y == a8[1].y )
    {
      prclDest.left = x >> 4;
      prclDest.bottom = a8[2].y >> 4;
      v19 = a8[1].x >> 4;
      prclDest.top = y >> 4;
      prclDest.right = v19;
      CheckBitmapSurface(psoTrg, &prclDest.left);
      return EngStretchBlt(psoTrg, psoSrc, psoMask, a4, pxlo, pca, pptlHTOrg, &prclDest, prclSrc, pptlMask, 4u);
    }
  }
  if ( a3 )
    goto LABEL_36;
  v20 = a8[1].x;
  if ( x != v20 )
    goto LABEL_36;
  v21 = a8[2].y;
  if ( a8->y != v21 )
    goto LABEL_36;
  v22 = prclSrc->bottom - prclSrc->top;
  v23 = a8[1].y;
  v24 = a8[2].x + 15;
  *(_QWORD *)&v47.right = 0;
  hsurf = 0;
  *(_QWORD *)&v47.left = 0;
  v25 = prclSrc->right - prclSrc->left;
  v43 = v22;
  v47.right = v22;
  v26 = 16 * v22;
  v27 = (v20 + 15) >> 4;
  v28 = (v21 + 15) >> 4;
  v29 = v24 >> 4;
  v30 = (v23 + 15) >> 4;
  prclDest = 0;
  v47.bottom = v25;
  if ( a8[2].x >= x )
  {
    HIDWORD(v51) = 16 * v25;
    pptfx.y = 16 * v25;
    v31 = v27;
    LODWORD(v51) = v26;
    v32 = v30;
    prclDest.top = v30;
    v30 = v28;
    prclDest.left = v27;
    v27 = v29;
    v50 = 0;
    pptfx.x = 0;
    prclDest.bottom = v28;
  }
  else
  {
    HIDWORD(v50) = 16 * v25;
    v31 = v29;
    LODWORD(v50) = v26;
    pptfx.x = v26;
    v32 = v28;
    prclDest.left = v29;
    v51 = 0;
    pptfx.y = 0;
    prclDest.top = v28;
    prclDest.bottom = v30;
  }
  prclDest.right = v27;
  if ( a4 )
  {
    if ( a4->rclBounds.right - v27 == 1 )
      prclDest.right = ++v27;
    if ( a4->rclBounds.bottom - v30 == 1 )
      prclDest.bottom = ++v30;
  }
  v33 = v27 - v31;
  v34 = -v33;
  if ( v33 > 0 )
    v34 = v33;
  v35 = -v43;
  if ( v43 > 0 )
    v35 = v43;
  if ( v34 == v35 )
  {
    v36 = v30 - v32;
    v37 = -v36;
    if ( v36 > 0 )
      v37 = v36;
    v38 = -v25;
    if ( v25 > 0 )
      v38 = v25;
    if ( v37 == v38 )
      goto LABEL_36;
  }
  v39 = CreateBitmapSURFOBJ((__int64)psoTrg->dhpdev, &hsurf, v43, v25, psoSrc->iBitmapFormat);
  v40 = v39;
  if ( !v39 )
  {
    v14 = pptlHTOrg;
LABEL_36:
    CheckBitmapSurface(psoTrg, 0);
    return EngPlgBlt(psoTrg, psoSrc, psoMask, a4, pxlo, pca, v14, a8, prclSrc, pptlMask, 4u);
  }
  v41 = EngPlgBlt(v39, psoSrc, 0, 0, 0, pca, pptlHTOrg, &pptfx, prcl, pptlMask, iMode);
  if ( v41 )
  {
    v42 = 4;
    if ( psoSrc->iBitmapFormat == 1 )
      v42 = iMode;
    CheckBitmapSurface(psoTrg, &prclDest.left);
    v41 = EngStretchBlt(psoTrg, v40, 0, a4, pxlo, pca, pptlHTOrg, &prclDest, &v47, 0, v42);
  }
  EngUnlockSurface(v40);
  if ( hsurf )
    EngDeleteSurface(hsurf);
  return v41;
}

```

## disassembly

```asm
0x18005fb90  push    rbp
0x18005fb92  push    rbx
0x18005fb93  push    rsi
0x18005fb94  push    rdi
0x18005fb95  push    r12
0x18005fb97  push    r13
0x18005fb99  push    r14
0x18005fb9b  push    r15
0x18005fb9d  lea     rbp, [rsp-7]
0x18005fba2  sub     rsp, 0F8h
0x18005fba9  mov     rax, cs:__security_cookie
0x18005fbb0  xor     rax, rsp
0x18005fbb3  mov     [rbp+3Fh+var_50], rax
0x18005fbb7  mov     rax, [rbp+3Fh+arg_20]
0x18005fbbb  mov     r15, r9
0x18005fbbe  mov     r12, [rbp+3Fh+arg_40]
0x18005fbc5  mov     r13, rdx
0x18005fbc8  mov     rdi, [rbp+3Fh+arg_28]
0x18005fbcc  mov     r14, rcx
0x18005fbcf  mov     rsi, [rbp+3Fh+arg_30]
0x18005fbd3  mov     rbx, [rbp+3Fh+arg_38]
0x18005fbda  mov     [rbp+3Fh+var_A8], rax
0x18005fbde  mov     rax, [rbp+3Fh+arg_48]
0x18005fbe5  mov     [rbp+3Fh+pptl], rax
0x18005fbe9  mov     rax, [rcx+10h]
0x18005fbed  mov     [rbp+3Fh+psoMask], r8
0x18005fbf1  mov     [rbp+3Fh+prcl], r12
0x18005fbf5  mov     [rsp+130h+var_C8], rdi
0x18005fbfa  test    dword ptr [rax+70h], 8000h
0x18005fc01  mov     [rbp+3Fh+pptlBrushOrg], rsi
0x18005fc05  jnz     short loc_18005FC11
0x18005fc07  mov     eax, 1
0x18005fc0c  jmp     loc_18005FF27
0x18005fc11  mov     eax, [rbx]
0x18005fc13  cmp     eax, [rbx+10h]
0x18005fc16  jnz     short loc_18005FC91
0x18005fc18  mov     edx, [rbx+4]
0x18005fc1b  cmp     edx, [rbx+0Ch]
0x18005fc1e  jnz     short loc_18005FC91
0x18005fc20  sar     eax, 4
0x18005fc23  mov     [rbp+3Fh+var_78.left], eax
0x18005fc26  mov     eax, [rbx+14h]
0x18005fc29  sar     eax, 4
0x18005fc2c  mov     [rbp+3Fh+var_78.bottom], eax
0x18005fc2f  mov     eax, [rbx+8]
0x18005fc32  sar     edx, 4
0x18005fc35  sar     eax, 4
0x18005fc38  mov     [rbp+3Fh+var_78.top], edx
0x18005fc3b  lea     rdx, [rbp+3Fh+var_78]
0x18005fc3f  mov     [rbp+3Fh+var_78.right], eax
0x18005fc42  call    CheckBitmapSurface
0x18005fc47  mov     rax, [rbp+3Fh+pptl]
0x18005fc4b  mov     r9, r15; pco
0x18005fc4e  mov     r8, [rbp+3Fh+psoMask]; psoMask
0x18005fc52  mov     rdx, r13; psoSrc
0x18005fc55  mov     [rsp+130h+iMode], 4; iMode
0x18005fc5d  mov     rcx, r14; psoDest
0x18005fc60  mov     [rsp+130h+pptlMask], rax; pptlMask
0x18005fc65  lea     rax, [rbp+3Fh+var_78]
0x18005fc69  mov     [rsp+130h+prclSrc], r12; prclSrc
0x18005fc6e  mov     [rsp+130h+prclDest], rax; prclDest
0x18005fc73  mov     rax, [rbp+3Fh+var_A8]
0x18005fc77  mov     [rsp+130h+pptlHTOrg], rsi; pptlHTOrg
0x18005fc7c  mov     [rsp+130h+pca], rdi; pca
0x18005fc81  mov     [rsp+130h+pxlo], rax; pxlo
0x18005fc86  call    cs:__imp_EngStretchBlt
0x18005fc8c  jmp     loc_18005FF27
0x18005fc91  xor     r10d, r10d
0x18005fc94  test    r8, r8
0x18005fc97  jnz     loc_18005FED7
0x18005fc9d  mov     edx, [rbx+8]
0x18005fca0  cmp     eax, edx
0x18005fca2  jnz     loc_18005FED7
0x18005fca8  mov     r11d, [rbx+14h]
0x18005fcac  cmp     [rbx+4], r11d
0x18005fcb0  jnz     loc_18005FED7
0x18005fcb6  mov     r9d, [r12+0Ch]
0x18005fcbb  add     edx, 0Fh
0x18005fcbe  sub     r9d, [r12+4]
0x18005fcc3  add     r11d, 0Fh
0x18005fcc7  mov     edi, [rbx+10h]
0x18005fcca  xorps   xmm0, xmm0
0x18005fccd  mov     r8d, [rbx+0Ch]
0x18005fcd1  add     edi, 0Fh
0x18005fcd4  mov     qword ptr [rbp+3Fh+var_88.right], r10
0x18005fcd8  add     r8d, 0Fh
0x18005fcdc  mov     [rbp+3Fh+hsurf], r10
0x18005fce0  mov     qword ptr [rbp+3Fh+var_88.left], r10
0x18005fce4  mov     r10d, [r12+8]
0x18005fce9  sub     r10d, [r12]
0x18005fced  mov     ecx, r10d
0x18005fcf0  mov     [rsp+130h+var_C0], r9d
0x18005fcf5  mov     [rbp+3Fh+var_88.right], r9d
0x18005fcf9  shl     ecx, 4
0x18005fcfc  shl     r9d, 4
0x18005fd00  sar     edx, 4
0x18005fd03  sar     r11d, 4
0x18005fd07  sar     edi, 4
0x18005fd0a  sar     r8d, 4
0x18005fd0e  movups  xmmword ptr [rbp+3Fh+var_78.left], xmm0
0x18005fd12  mov     [rbp+3Fh+var_88.bottom], r10d
0x18005fd16  cmp     [rbx+10h], eax
0x18005fd19  jge     short loc_18005FD41
0x18005fd1b  xor     eax, eax
0x18005fd1d  mov     dword ptr [rbp+3Fh+var_60+4], ecx
0x18005fd20  mov     ecx, edi
0x18005fd22  mov     dword ptr [rbp+3Fh+var_60], r9d
0x18005fd26  mov     [rbp+3Fh+pptfx.x], r9d
0x18005fd2a  mov     r9d, r11d
0x18005fd2d  mov     [rbp+3Fh+var_78.left], ecx
0x18005fd30  mov     [rbp+3Fh+var_58], rax
0x18005fd34  mov     [rbp+3Fh+pptfx.y], eax
0x18005fd37  mov     [rbp+3Fh+var_78.top], r11d
0x18005fd3b  mov     [rbp+3Fh+var_78.bottom], r8d
0x18005fd3f  jmp     short loc_18005FD69
0x18005fd41  xor     eax, eax
0x18005fd43  mov     dword ptr [rbp+3Fh+var_58+4], ecx
0x18005fd46  mov     [rbp+3Fh+pptfx.y], ecx
0x18005fd49  mov     ecx, edx
0x18005fd4b  mov     dword ptr [rbp+3Fh+var_58], r9d
0x18005fd4f  mov     r9d, r8d
0x18005fd52  mov     [rbp+3Fh+var_78.top], r8d
0x18005fd56  mov     r8d, r11d
0x18005fd59  mov     [rbp+3Fh+var_78.left], edx
0x18005fd5c  mov     edx, edi
0x18005fd5e  mov     [rbp+3Fh+var_60], rax
0x18005fd62  mov     [rbp+3Fh+pptfx.x], eax
0x18005fd65  mov     [rbp+3Fh+var_78.bottom], r11d
0x18005fd69  mov     rdi, [rsp+130h+var_C8]
0x18005fd6e  mov     [rbp+3Fh+var_78.right], edx
0x18005fd71  test    r15, r15
0x18005fd74  jz      short loc_18005FD99
0x18005fd76  mov     eax, [r15+0Ch]
0x18005fd7a  sub     eax, edx
0x18005fd7c  cmp     eax, 1
0x18005fd7f  jnz     short loc_18005FD86
0x18005fd81  inc     edx
0x18005fd83  mov     [rbp+3Fh+var_78.right], edx
0x18005fd86  mov     eax, [r15+10h]
0x18005fd8a  sub     eax, r8d
0x18005fd8d  cmp     eax, 1
0x18005fd90  jnz     short loc_18005FD99
0x18005fd92  inc     r8d
0x18005fd95  mov     [rbp+3Fh+var_78.bottom], r8d
0x18005fd99  mov     r11d, [rsp+130h+var_C0]
0x18005fd9e  sub     edx, ecx
0x18005fda0  mov     ecx, edx
0x18005fda2  mov     eax, r11d
0x18005fda5  neg     ecx
0x18005fda7  cmovs   ecx, edx
0x18005fdaa  neg     eax
0x18005fdac  cmovs   eax, r11d
0x18005fdb0  cmp     ecx, eax
0x18005fdb2  jnz     short loc_18005FDD1
0x18005fdb4  sub     r8d, r9d
0x18005fdb7  mov     eax, r10d
0x18005fdba  mov     edx, r8d
0x18005fdbd  neg     edx
0x18005fdbf  cmovs   edx, r8d
0x18005fdc3  neg     eax
0x18005fdc5  cmovs   eax, r10d
0x18005fdc9  cmp     edx, eax
0x18005fdcb  jz      loc_18005FED7
0x18005fdd1  mov     eax, [r13+48h]
0x18005fdd5  lea     rdx, [rbp+3Fh+hsurf]; int
0x18005fdd9  mov     rcx, [r14+10h]; int
0x18005fddd  mov     r9d, r10d; int
0x18005fde0  mov     r8d, r11d; int
0x18005fde3  mov     dword ptr [rsp+130h+pxlo], eax; iFormat
0x18005fde7  call    CreateBitmapSURFOBJ
0x18005fdec  mov     rsi, rax
0x18005fdef  test    rax, rax
0x18005fdf2  jz      loc_18005FED3
0x18005fdf8  mov     rax, [rbp+3Fh+pptl]
0x18005fdfc  xor     r9d, r9d; pco
0x18005fdff  mov     r12d, [rbp+3Fh+arg_50]
0x18005fe06  xor     r8d, r8d; psoMsk
0x18005fe09  mov     [rsp+130h+iMode], r12d; iMode
0x18005fe0e  mov     rdx, r13; psoSrc
0x18005fe11  mov     [rsp+130h+pptlMask], rax; pptl
0x18005fe16  mov     rcx, rsi; psoTrg
0x18005fe19  mov     rax, [rbp+3Fh+prcl]
0x18005fe1d  mov     [rsp+130h+prclSrc], rax; prcl
0x18005fe22  lea     rax, [rbp+3Fh+pptfx]
0x18005fe26  mov     [rsp+130h+prclDest], rax; pptfx
0x18005fe2b  mov     rax, [rbp+3Fh+pptlBrushOrg]
0x18005fe2f  mov     [rsp+130h+pptlHTOrg], rax; pptlBrushOrg
0x18005fe34  mov     [rsp+130h+pca], rdi; pca
0x18005fe39  mov     [rsp+130h+pxlo], 0; pxlo
0x18005fe42  call    cs:__imp_EngPlgBlt
0x18005fe48  mov     ebx, eax
0x18005fe4a  test    eax, eax
0x18005fe4c  jz      short loc_18005FEB7
0x18005fe4e  cmp     dword ptr [r13+48h], 1
0x18005fe53  lea     rdx, [rbp+3Fh+var_78]
0x18005fe57  mov     edi, 4
0x18005fe5c  mov     rcx, r14
0x18005fe5f  cmovz   edi, r12d
0x18005fe63  call    CheckBitmapSurface
0x18005fe68  mov     [rsp+130h+iMode], edi; iMode
0x18005fe6c  lea     rax, [rbp+3Fh+var_88]
0x18005fe70  mov     [rsp+130h+pptlMask], 0; pptlMask
0x18005fe79  mov     r9, r15; pco
0x18005fe7c  mov     [rsp+130h+prclSrc], rax; prclSrc
0x18005fe81  xor     r8d, r8d; psoMask
0x18005fe84  lea     rax, [rbp+3Fh+var_78]
0x18005fe88  mov     rdx, rsi; psoSrc
0x18005fe8b  mov     [rsp+130h+prclDest], rax; prclDest
0x18005fe90  mov     rcx, r14; psoDest
0x18005fe93  mov     rax, [rbp+3Fh+pptlBrushOrg]
0x18005fe97  mov     [rsp+130h+pptlHTOrg], rax; pptlHTOrg
0x18005fe9c  mov     rax, [rsp+130h+var_C8]
0x18005fea1  mov     [rsp+130h+pca], rax; pca
0x18005fea6  mov     rax, [rbp+3Fh+var_A8]
0x18005feaa  mov     [rsp+130h+pxlo], rax; pxlo
0x18005feaf  call    cs:__imp_EngStretchBlt
0x18005feb5  mov     ebx, eax
0x18005feb7  mov     rcx, rsi; pso
0x18005feba  call    cs:__imp_EngUnlockSurface
0x18005fec0  mov     rcx, [rbp+3Fh+hsurf]; hsurf
0x18005fec4  test    rcx, rcx
0x18005fec7  jz      short loc_18005FECF
0x18005fec9  call    cs:__imp_EngDeleteSurface
0x18005fecf  mov     eax, ebx
0x18005fed1  jmp     short loc_18005FF27
0x18005fed3  mov     rsi, [rbp+3Fh+pptlBrushOrg]
0x18005fed7  xor     edx, edx
0x18005fed9  mov     rcx, r14
0x18005fedc  call    CheckBitmapSurface
0x18005fee1  mov     rax, [rbp+3Fh+pptl]
0x18005fee5  mov     r9, r15; pco
0x18005fee8  mov     r8, [rbp+3Fh+psoMask]; psoMsk
0x18005feec  mov     rdx, r13; psoSrc
0x18005feef  mov     [rsp+130h+iMode], 4; iMode
0x18005fef7  mov     rcx, r14; psoTrg
0x18005fefa  mov     [rsp+130h+pptlMask], rax; pptl
0x18005feff  mov     rax, [rsp+130h+var_C8]
0x18005ff04  mov     [rsp+130h+prclSrc], r12; prcl
0x18005ff09  mov     [rsp+130h+prclDest], rbx; pptfx
0x18005ff0e  mov     [rsp+130h+pptlHTOrg], rsi; pptlBrushOrg
0x18005ff13  mov     [rsp+130h+pca], rax; pca
0x18005ff18  mov     rax, [rbp+3Fh+var_A8]
0x18005ff1c  mov     [rsp+130h+pxlo], rax; pxlo
0x18005ff21  call    cs:__imp_EngPlgBlt
0x18005ff27  mov     rcx, [rbp+3Fh+var_50]
0x18005ff2b  xor     rcx, rsp; StackCookie
0x18005ff2e  call    __security_check_cookie
0x18005ff33  add     rsp, 0F8h
0x18005ff3a  pop     r15
0x18005ff3c  pop     r14
0x18005ff3e  pop     r13
0x18005ff40  pop     r12
0x18005ff42  pop     rdi
0x18005ff43  pop     rsi
0x18005ff44  pop     rbx
0x18005ff45  pop     rbp
0x18005ff46  retn
```
