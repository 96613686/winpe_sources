# RMPlgBlt

- ea: `0x180060fe0`
- end: `0x1800613bc`
- name: `RMPlgBlt`
- size: `988`
- prototype: `BOOL __fastcall(SURFOBJ *psoTrg, SURFOBJ *psoSrc, __int64, __int64, XLATEOBJ *pxlo, COLORADJUSTMENT *pca, POINTL *pptlHTOrg, POINTFIX *, RECTL *prclSrc, POINTL *pptlMask, ULONG iMode)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180017148`
- `0x18004375c`
- `0x180049d00`
- `0x180060fe0`

## import_xrefs

- `GDI32!EngPlgBlt` at `0x180061298`
- `GDI32!EngPlgBlt` at `0x18006138f`
- `GDI32!EngPlgBlt` at `0x180061298`
- `GDI32!EngPlgBlt` at `0x18006138f`
- `GDI32!EngStretchBlt` at `0x1800610d6`
- `GDI32!EngStretchBlt` at `0x18006130b`
- `GDI32!EngStretchBlt` at `0x1800610d6`
- `GDI32!EngStretchBlt` at `0x18006130b`
- `GDI32!EngUnlockSurface` at `0x18006131c`
- `GDI32!EngUnlockSurface` at `0x18006131c`
- `GDI32!EngDeleteSurface` at `0x180061331`
- `GDI32!EngDeleteSurface` at `0x180061331`

## pseudocode

```c
BOOL __fastcall RMPlgBlt(
        SURFOBJ *psoTrg,
        SURFOBJ *psoSrc,
        __int64 a3,
        __int64 a4,
        XLATEOBJ *pxlo,
        COLORADJUSTMENT *pca,
        POINTL *pptlHTOrg,
        POINTFIX *a8,
        RECTL *prclSrc,
        POINTL *pptlMask,
        ULONG iMode)
{
  CLIPOBJ *v11; // r15
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
  unsigned int v28; // r11d
  LONG v29; // edi
  unsigned int v30; // r8d
  LONG v31; // ecx
  int v32; // edx
  int v33; // ecx
  int v34; // eax
  int v35; // edx
  int v36; // eax
  SURFOBJ *v37; // rax
  SURFOBJ *v38; // rsi
  BOOL v39; // ebx
  __int64 v40; // r8
  __int64 v41; // r9
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

  v11 = (CLIPOBJ *)a4;
  v14 = pptlHTOrg;
  dhpdev = psoTrg->dhpdev;
  psoMask = (SURFOBJ *)a3;
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
      CheckBitmapSurface(psoTrg, &prclDest.left, a3, a4);
      return EngStretchBlt(psoTrg, psoSrc, psoMask, v11, pxlo, pca, pptlHTOrg, &prclDest, prclSrc, pptlMask, 4u);
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
    a4 = v30;
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
    a4 = v28;
    prclDest.left = v29;
    v51 = 0;
    pptfx.y = 0;
    prclDest.top = v28;
    prclDest.bottom = v30;
  }
  prclDest.right = v27;
  if ( v11 )
  {
    if ( v11->rclBounds.right - v27 == 1 )
      prclDest.right = ++v27;
    if ( v11->rclBounds.bottom - v30 == 1 )
      prclDest.bottom = ++v30;
  }
  v32 = v27 - v31;
  v33 = -v32;
  if ( v32 > 0 )
    v33 = v32;
  v34 = -v43;
  if ( v43 > 0 )
    v34 = v43;
  if ( v33 == v34 )
  {
    a3 = v30 - (unsigned int)a4;
    v35 = -(int)a3;
    if ( (int)a3 > 0 )
      v35 = a3;
    v36 = -v25;
    if ( v25 > 0 )
      v36 = v25;
    if ( v35 == v36 )
      goto LABEL_36;
  }
  v37 = CreateBitmapSURFOBJ((__int64)psoTrg->dhpdev, &hsurf, v43, v25, psoSrc->iBitmapFormat);
  v38 = v37;
  if ( !v37 )
  {
    v14 = pptlHTOrg;
LABEL_36:
    CheckBitmapSurface(psoTrg, 0, a3, a4);
    return EngPlgBlt(psoTrg, psoSrc, psoMask, v11, pxlo, pca, v14, a8, prclSrc, pptlMask, 4u);
  }
  v39 = EngPlgBlt(v37, psoSrc, 0, 0, 0, pca, pptlHTOrg, &pptfx, prcl, pptlMask, iMode);
  if ( v39 )
  {
    v42 = 4;
    if ( psoSrc->iBitmapFormat == 1 )
      v42 = iMode;
    CheckBitmapSurface(psoTrg, &prclDest.left, v40, v41);
    v39 = EngStretchBlt(psoTrg, v38, 0, v11, pxlo, pca, pptlHTOrg, &prclDest, &v47, 0, v42);
  }
  EngUnlockSurface(v38);
  if ( hsurf )
    EngDeleteSurface(hsurf);
  return v39;
}

```

## disassembly

```asm
0x180060fe0  push    rbp
0x180060fe2  push    rbx
0x180060fe3  push    rsi
0x180060fe4  push    rdi
0x180060fe5  push    r12
0x180060fe7  push    r13
0x180060fe9  push    r14
0x180060feb  push    r15
0x180060fed  lea     rbp, [rsp-7]
0x180060ff2  sub     rsp, 0F8h
0x180060ff9  mov     rax, cs:__security_cookie
0x180061000  xor     rax, rsp
0x180061003  mov     [rbp+3Fh+var_50], rax
0x180061007  mov     rax, [rbp+3Fh+arg_20]
0x18006100b  mov     r15, r9
0x18006100e  mov     r12, [rbp+3Fh+arg_40]
0x180061015  mov     r13, rdx
0x180061018  mov     rdi, [rbp+3Fh+arg_28]
0x18006101c  mov     r14, rcx
0x18006101f  mov     rsi, [rbp+3Fh+arg_30]
0x180061023  mov     rbx, [rbp+3Fh+arg_38]
0x18006102a  mov     [rbp+3Fh+var_A8], rax
0x18006102e  mov     rax, [rbp+3Fh+arg_48]
0x180061035  mov     [rbp+3Fh+pptl], rax
0x180061039  mov     rax, [rcx+10h]
0x18006103d  mov     [rbp+3Fh+psoMask], r8
0x180061041  mov     [rbp+3Fh+prcl], r12
0x180061045  mov     [rsp+130h+var_C8], rdi
0x18006104a  test    dword ptr [rax+70h], 8000h
0x180061051  mov     [rbp+3Fh+pptlBrushOrg], rsi
0x180061055  jnz     short loc_180061061
0x180061057  mov     eax, 1
0x18006105c  jmp     loc_18006139B
0x180061061  mov     eax, [rbx]
0x180061063  cmp     eax, [rbx+10h]
0x180061066  jnz     short loc_1800610E7
0x180061068  mov     edx, [rbx+4]
0x18006106b  cmp     edx, [rbx+0Ch]
0x18006106e  jnz     short loc_1800610E7
0x180061070  sar     eax, 4
0x180061073  mov     [rbp+3Fh+var_78.left], eax
0x180061076  mov     eax, [rbx+14h]
0x180061079  sar     eax, 4
0x18006107c  mov     [rbp+3Fh+var_78.bottom], eax
0x18006107f  mov     eax, [rbx+8]
0x180061082  sar     edx, 4
0x180061085  sar     eax, 4
0x180061088  mov     [rbp+3Fh+var_78.top], edx
0x18006108b  lea     rdx, [rbp+3Fh+var_78]
0x18006108f  mov     [rbp+3Fh+var_78.right], eax
0x180061092  call    CheckBitmapSurface
0x180061097  mov     rax, [rbp+3Fh+pptl]
0x18006109b  mov     r9, r15; pco
0x18006109e  mov     r8, [rbp+3Fh+psoMask]; psoMask
0x1800610a2  mov     rdx, r13; psoSrc
0x1800610a5  mov     [rsp+130h+iMode], 4; iMode
0x1800610ad  mov     rcx, r14; psoDest
0x1800610b0  mov     [rsp+130h+pptlMask], rax; pptlMask
0x1800610b5  lea     rax, [rbp+3Fh+var_78]
0x1800610b9  mov     [rsp+130h+prclSrc], r12; prclSrc
0x1800610be  mov     [rsp+130h+prclDest], rax; prclDest
0x1800610c3  mov     rax, [rbp+3Fh+var_A8]
0x1800610c7  mov     [rsp+130h+pptlHTOrg], rsi; pptlHTOrg
0x1800610cc  mov     [rsp+130h+pca], rdi; pca
0x1800610d1  mov     [rsp+130h+pxlo], rax; pxlo
0x1800610d6  call    cs:__imp_EngStretchBlt
0x1800610dd  nop     dword ptr [rax+rax+00h]
0x1800610e2  jmp     loc_18006139B
0x1800610e7  xor     r10d, r10d
0x1800610ea  test    r8, r8
0x1800610ed  jnz     loc_180061345
0x1800610f3  mov     edx, [rbx+8]
0x1800610f6  cmp     eax, edx
0x1800610f8  jnz     loc_180061345
0x1800610fe  mov     r11d, [rbx+14h]
0x180061102  cmp     [rbx+4], r11d
0x180061106  jnz     loc_180061345
0x18006110c  mov     r9d, [r12+0Ch]
0x180061111  add     edx, 0Fh
0x180061114  sub     r9d, [r12+4]
0x180061119  add     r11d, 0Fh
0x18006111d  mov     edi, [rbx+10h]
0x180061120  xorps   xmm0, xmm0
0x180061123  mov     r8d, [rbx+0Ch]
0x180061127  add     edi, 0Fh
0x18006112a  mov     qword ptr [rbp+3Fh+var_88.right], r10
0x18006112e  add     r8d, 0Fh
0x180061132  mov     [rbp+3Fh+hsurf], r10
0x180061136  mov     qword ptr [rbp+3Fh+var_88.left], r10
0x18006113a  mov     r10d, [r12+8]
0x18006113f  sub     r10d, [r12]
0x180061143  mov     ecx, r10d
0x180061146  mov     [rsp+130h+var_C0], r9d
0x18006114b  mov     [rbp+3Fh+var_88.right], r9d
0x18006114f  shl     ecx, 4
0x180061152  shl     r9d, 4
0x180061156  sar     edx, 4
0x180061159  sar     r11d, 4
0x18006115d  sar     edi, 4
0x180061160  sar     r8d, 4
0x180061164  movups  xmmword ptr [rbp+3Fh+var_78.left], xmm0
0x180061168  mov     [rbp+3Fh+var_88.bottom], r10d
0x18006116c  cmp     [rbx+10h], eax
0x18006116f  jge     short loc_180061197
0x180061171  xor     eax, eax
0x180061173  mov     dword ptr [rbp+3Fh+var_60+4], ecx
0x180061176  mov     ecx, edi
0x180061178  mov     dword ptr [rbp+3Fh+var_60], r9d
0x18006117c  mov     [rbp+3Fh+pptfx.x], r9d
0x180061180  mov     r9d, r11d
0x180061183  mov     [rbp+3Fh+var_78.left], ecx
0x180061186  mov     [rbp+3Fh+var_58], rax
0x18006118a  mov     [rbp+3Fh+pptfx.y], eax
0x18006118d  mov     [rbp+3Fh+var_78.top], r11d
0x180061191  mov     [rbp+3Fh+var_78.bottom], r8d
0x180061195  jmp     short loc_1800611BF
0x180061197  xor     eax, eax
0x180061199  mov     dword ptr [rbp+3Fh+var_58+4], ecx
0x18006119c  mov     [rbp+3Fh+pptfx.y], ecx
0x18006119f  mov     ecx, edx
0x1800611a1  mov     dword ptr [rbp+3Fh+var_58], r9d
0x1800611a5  mov     r9d, r8d
0x1800611a8  mov     [rbp+3Fh+var_78.top], r8d
0x1800611ac  mov     r8d, r11d
0x1800611af  mov     [rbp+3Fh+var_78.left], edx
0x1800611b2  mov     edx, edi
0x1800611b4  mov     [rbp+3Fh+var_60], rax
0x1800611b8  mov     [rbp+3Fh+pptfx.x], eax
0x1800611bb  mov     [rbp+3Fh+var_78.bottom], r11d
0x1800611bf  mov     rdi, [rsp+130h+var_C8]
0x1800611c4  mov     [rbp+3Fh+var_78.right], edx
0x1800611c7  test    r15, r15
0x1800611ca  jz      short loc_1800611EF
0x1800611cc  mov     eax, [r15+0Ch]
0x1800611d0  sub     eax, edx
0x1800611d2  cmp     eax, 1
0x1800611d5  jnz     short loc_1800611DC
0x1800611d7  inc     edx
0x1800611d9  mov     [rbp+3Fh+var_78.right], edx
0x1800611dc  mov     eax, [r15+10h]
0x1800611e0  sub     eax, r8d
0x1800611e3  cmp     eax, 1
0x1800611e6  jnz     short loc_1800611EF
0x1800611e8  inc     r8d
0x1800611eb  mov     [rbp+3Fh+var_78.bottom], r8d
0x1800611ef  mov     r11d, [rsp+130h+var_C0]
0x1800611f4  sub     edx, ecx
0x1800611f6  mov     ecx, edx
0x1800611f8  mov     eax, r11d
0x1800611fb  neg     ecx
0x1800611fd  cmovs   ecx, edx
0x180061200  neg     eax
0x180061202  cmovs   eax, r11d
0x180061206  cmp     ecx, eax
0x180061208  jnz     short loc_180061227
0x18006120a  sub     r8d, r9d
0x18006120d  mov     eax, r10d
0x180061210  mov     edx, r8d
0x180061213  neg     edx
0x180061215  cmovs   edx, r8d
0x180061219  neg     eax
0x18006121b  cmovs   eax, r10d
0x18006121f  cmp     edx, eax
0x180061221  jz      loc_180061345
0x180061227  mov     eax, [r13+48h]
0x18006122b  lea     rdx, [rbp+3Fh+hsurf]; int
0x18006122f  mov     rcx, [r14+10h]; int
0x180061233  mov     r9d, r10d; int
0x180061236  mov     r8d, r11d; int
0x180061239  mov     dword ptr [rsp+130h+pxlo], eax; iFormat
0x18006123d  call    CreateBitmapSURFOBJ
0x180061242  mov     rsi, rax
0x180061245  test    rax, rax
0x180061248  jz      loc_180061341
0x18006124e  mov     rax, [rbp+3Fh+pptl]
0x180061252  xor     r9d, r9d; pco
0x180061255  mov     r12d, [rbp+3Fh+arg_50]
0x18006125c  xor     r8d, r8d; psoMsk
0x18006125f  mov     [rsp+130h+iMode], r12d; iMode
0x180061264  mov     rdx, r13; psoSrc
0x180061267  mov     [rsp+130h+pptlMask], rax; pptl
0x18006126c  mov     rcx, rsi; psoTrg
0x18006126f  mov     rax, [rbp+3Fh+prcl]
0x180061273  mov     [rsp+130h+prclSrc], rax; prcl
0x180061278  lea     rax, [rbp+3Fh+pptfx]
0x18006127c  mov     [rsp+130h+prclDest], rax; pptfx
0x180061281  mov     rax, [rbp+3Fh+pptlBrushOrg]
0x180061285  mov     [rsp+130h+pptlHTOrg], rax; pptlBrushOrg
0x18006128a  mov     [rsp+130h+pca], rdi; pca
0x18006128f  mov     [rsp+130h+pxlo], 0; pxlo
0x180061298  call    cs:__imp_EngPlgBlt
0x18006129f  nop     dword ptr [rax+rax+00h]
0x1800612a4  mov     ebx, eax
0x1800612a6  test    eax, eax
0x1800612a8  jz      short loc_180061319
0x1800612aa  cmp     dword ptr [r13+48h], 1
0x1800612af  lea     rdx, [rbp+3Fh+var_78]
0x1800612b3  mov     edi, 4
0x1800612b8  mov     rcx, r14
0x1800612bb  cmovz   edi, r12d
0x1800612bf  call    CheckBitmapSurface
0x1800612c4  mov     [rsp+130h+iMode], edi; iMode
0x1800612c8  lea     rax, [rbp+3Fh+var_88]
0x1800612cc  mov     [rsp+130h+pptlMask], 0; pptlMask
0x1800612d5  mov     r9, r15; pco
0x1800612d8  mov     [rsp+130h+prclSrc], rax; prclSrc
0x1800612dd  xor     r8d, r8d; psoMask
0x1800612e0  lea     rax, [rbp+3Fh+var_78]
0x1800612e4  mov     rdx, rsi; psoSrc
0x1800612e7  mov     [rsp+130h+prclDest], rax; prclDest
0x1800612ec  mov     rcx, r14; psoDest
0x1800612ef  mov     rax, [rbp+3Fh+pptlBrushOrg]
0x1800612f3  mov     [rsp+130h+pptlHTOrg], rax; pptlHTOrg
0x1800612f8  mov     rax, [rsp+130h+var_C8]
0x1800612fd  mov     [rsp+130h+pca], rax; pca
0x180061302  mov     rax, [rbp+3Fh+var_A8]
0x180061306  mov     [rsp+130h+pxlo], rax; pxlo
0x18006130b  call    cs:__imp_EngStretchBlt
0x180061312  nop     dword ptr [rax+rax+00h]
0x180061317  mov     ebx, eax
0x180061319  mov     rcx, rsi; pso
0x18006131c  call    cs:__imp_EngUnlockSurface
0x180061323  nop     dword ptr [rax+rax+00h]
0x180061328  mov     rcx, [rbp+3Fh+hsurf]; hsurf
0x18006132c  test    rcx, rcx
0x18006132f  jz      short loc_18006133D
0x180061331  call    cs:__imp_EngDeleteSurface
0x180061338  nop     dword ptr [rax+rax+00h]
0x18006133d  mov     eax, ebx
0x18006133f  jmp     short loc_18006139B
0x180061341  mov     rsi, [rbp+3Fh+pptlBrushOrg]
0x180061345  xor     edx, edx
0x180061347  mov     rcx, r14
0x18006134a  call    CheckBitmapSurface
0x18006134f  mov     rax, [rbp+3Fh+pptl]
0x180061353  mov     r9, r15; pco
0x180061356  mov     r8, [rbp+3Fh+psoMask]; psoMsk
0x18006135a  mov     rdx, r13; psoSrc
0x18006135d  mov     [rsp+130h+iMode], 4; iMode
0x180061365  mov     rcx, r14; psoTrg
0x180061368  mov     [rsp+130h+pptlMask], rax; pptl
0x18006136d  mov     rax, [rsp+130h+var_C8]
0x180061372  mov     [rsp+130h+prclSrc], r12; prcl
0x180061377  mov     [rsp+130h+prclDest], rbx; pptfx
0x18006137c  mov     [rsp+130h+pptlHTOrg], rsi; pptlBrushOrg
0x180061381  mov     [rsp+130h+pca], rax; pca
0x180061386  mov     rax, [rbp+3Fh+var_A8]
0x18006138a  mov     [rsp+130h+pxlo], rax; pxlo
0x18006138f  call    cs:__imp_EngPlgBlt
0x180061396  nop     dword ptr [rax+rax+00h]
0x18006139b  mov     rcx, [rbp+3Fh+var_50]
0x18006139f  xor     rcx, rsp; StackCookie
0x1800613a2  call    __security_check_cookie
0x1800613a7  add     rsp, 0F8h
0x1800613ae  pop     r15
0x1800613b0  pop     r14
0x1800613b2  pop     r13
0x1800613b4  pop     r12
0x1800613b6  pop     rdi
0x1800613b7  pop     rsi
0x1800613b8  pop     rbx
0x1800613b9  pop     rbp
0x1800613ba  retn
```
