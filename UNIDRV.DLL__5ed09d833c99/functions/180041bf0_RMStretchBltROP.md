# RMStretchBltROP

- ea: `0x180041bf0`
- end: `0x180041f5c`
- name: `RMStretchBltROP`
- size: `876`
- prototype: `BOOL __fastcall(SURFOBJ *psoDest, SURFOBJ *psoSrc, SURFOBJ *, CLIPOBJ *, XLATEOBJ *pxlo, COLORADJUSTMENT *, POINTL *, RECTL *prclTrg, RECTL *, POINTL *, int, BRUSHOBJ *, ROP4 rop4)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800160e8`
- `0x180017148`
- `0x180041bf0`
- `0x18004375c`
- `0x180049d00`
- `0x1800609e4`
- `0x180060cf4`

## import_xrefs

- `GDI32!EngStretchBltROP` at `0x180041f28`
- `GDI32!EngStretchBltROP` at `0x180041f28`
- `GDI32!EngStretchBlt` at `0x180041db8`
- `GDI32!EngStretchBlt` at `0x180041db8`
- `GDI32!EngBitBlt` at `0x180041e1c`
- `GDI32!EngBitBlt` at `0x180041e1c`
- `GDI32!EngUnlockSurface` at `0x180041e2d`
- `GDI32!EngUnlockSurface` at `0x180041e58`
- `GDI32!EngUnlockSurface` at `0x180041e2d`
- `GDI32!EngUnlockSurface` at `0x180041e58`
- `GDI32!EngDeleteSurface` at `0x180041e42`
- `GDI32!EngDeleteSurface` at `0x180041e6d`
- `GDI32!EngDeleteSurface` at `0x180041e42`
- `GDI32!EngDeleteSurface` at `0x180041e6d`

## pseudocode

```c
BOOL __fastcall RMStretchBltROP(
        SURFOBJ *psoDest,
        SURFOBJ *psoSrc,
        SURFOBJ *a3,
        CLIPOBJ *a4,
        XLATEOBJ *pxlo,
        COLORADJUSTMENT *a6,
        POINTL *a7,
        RECTL *prclTrg,
        RECTL *a9,
        POINTL *a10,
        int a11,
        BRUSHOBJ *a12,
        ROP4 rop4)
{
  DHPDEV dhpdev; // r14
  SURFOBJ *v15; // r9
  bool v18; // zf
  DWORD v19; // ebx
  __int64 v20; // r8
  ULONG iBitmapFormat; // r10d
  unsigned int v22; // ecx
  int v23; // edx
  int v24; // r9d
  LONG left; // ecx
  LONG top; // eax
  unsigned int v27; // r8d
  int v28; // r9d
  SURFOBJ *v29; // rax
  SURFOBJ *v30; // r14
  __int64 v31; // r8
  __int64 v32; // r9
  BOOL v33; // ebx
  int v36; // [rsp+78h] [rbp-59h]
  int v37; // [rsp+7Ch] [rbp-55h]
  POINTL pptlBrush; // [rsp+80h] [rbp-51h] BYREF
  HSURF hsurf; // [rsp+88h] [rbp-49h] BYREF
  RECTL *prclSrc; // [rsp+90h] [rbp-41h]
  BRUSHOBJ *pbo; // [rsp+98h] [rbp-39h]
  POINTL *pptlMask; // [rsp+A0h] [rbp-31h]
  POINTL *pptlHTOrg; // [rsp+A8h] [rbp-29h]
  COLORADJUSTMENT *pca; // [rsp+B0h] [rbp-21h]
  RECTL prclDest; // [rsp+B8h] [rbp-19h] BYREF

  dhpdev = psoDest->dhpdev;
  v15 = a3;
  pca = a6;
  v18 = ((_DWORD)dhpdev[28] & 0x8000) == 0;
  pptlHTOrg = a7;
  prclSrc = a9;
  pptlMask = a10;
  pbo = a12;
  if ( v18 )
    return 1;
  v19 = rop4;
  if ( rop4 == 52428 )
  {
    DrawWhiteRect((__int64)dhpdev, &prclTrg->left, a4);
    v15 = a3;
  }
  if ( ((_BYTE)dhpdev[29] & 0x20) != 0 )
    v19 = InvertROPs(rop4);
  v20 = 0;
  if ( v19 == 52428
    || v15
    || (((unsigned __int8)v19 ^ (unsigned __int8)(v19 >> 2)) & 0x33) == 0
    || (iBitmapFormat = psoDest->iBitmapFormat, iBitmapFormat > 2)
    || psoSrc->iBitmapFormat < 2 )
  {
LABEL_21:
    CheckBitmapSurface(psoDest, &prclTrg->left, v20, (__int64)v15);
    if ( v19 != 52428
      || psoSrc->iBitmapFormat != 1
      || psoDest->iBitmapFormat != 1
      || a11 != 3
      || a3
      || a4 && a4->iDComplexity
      || pxlo && (pxlo->flXlate & 1) == 0
      || !(unsigned int)Fast1bppScaling((__int64)psoSrc, (__int64)psoDest, prclSrc, &prclTrg->left) )
    {
      return EngStretchBltROP(psoDest, psoSrc, a3, a4, pxlo, pca, pptlHTOrg, prclTrg, prclSrc, pptlMask, 4u, pbo, v19);
    }
    return 1;
  }
  v22 = *((_DWORD *)dhpdev + 443);
  v23 = 0;
  v37 = 0;
  v24 = 0;
  hsurf = 0;
  *(_QWORD *)&prclDest.right = 0;
  v36 = 0;
  if ( v22 )
  {
    v24 = prclTrg->left % v22;
    v36 = v24;
    v23 = prclTrg->top % v22;
    v37 = v23;
  }
  left = prclTrg->left;
  top = prclTrg->top;
  *(_QWORD *)&prclDest.left = 0;
  v27 = v24 + prclTrg->right - left;
  v28 = prclTrg->bottom - top;
  pptlBrush.x = -left;
  prclDest.right = v27;
  prclDest.bottom = v23 + v28;
  pptlBrush.y = -top;
  v29 = CreateBitmapSURFOBJ((__int64)dhpdev, &hsurf, v27, v23 + v28, iBitmapFormat);
  v30 = v29;
  if ( !v29 )
  {
LABEL_19:
    if ( hsurf )
      EngDeleteSurface(hsurf);
    goto LABEL_21;
  }
  prclDest.left += v36;
  prclDest.top += v37;
  if ( !EngStretchBlt(v29, psoSrc, 0, 0, pxlo, 0, pptlHTOrg, &prclDest, prclSrc, 0, 4u) )
  {
    EngUnlockSurface(v30);
    goto LABEL_19;
  }
  pptlBrush = 0;
  CheckBitmapSurface(psoDest, &prclTrg->left, v31, v32);
  v33 = EngBitBlt(psoDest, v30, 0, a4, 0, prclTrg, (POINTL *)&prclDest, pptlMask, pbo, &pptlBrush, v19);
  EngUnlockSurface(v30);
  if ( hsurf )
    EngDeleteSurface(hsurf);
  return v33;
}

```

## disassembly

```asm
0x180041bf0  push    rbp
0x180041bf2  push    rbx
0x180041bf3  push    rsi
0x180041bf4  push    rdi
0x180041bf5  push    r12
0x180041bf7  push    r13
0x180041bf9  push    r14
0x180041bfb  push    r15
0x180041bfd  lea     rbp, [rsp-7]
0x180041c02  sub     rsp, 0D8h
0x180041c09  mov     rax, cs:__security_cookie
0x180041c10  xor     rax, rsp
0x180041c13  mov     [rbp+3Fh+var_48], rax
0x180041c17  mov     rax, [rbp+3Fh+arg_28]
0x180041c1b  mov     r15, r9
0x180041c1e  mov     r14, [rcx+10h]
0x180041c22  mov     r9, r8
0x180041c25  mov     rdi, [rbp+3Fh+prclTrg]
0x180041c2c  mov     r12, rdx
0x180041c2f  mov     r13, [rbp+3Fh+arg_20]
0x180041c33  mov     rsi, rcx
0x180041c36  mov     [rbp+3Fh+var_60], rax
0x180041c3a  test    dword ptr [r14+70h], 8000h
0x180041c42  mov     rax, [rbp+3Fh+arg_30]
0x180041c46  mov     [rbp+3Fh+var_68], rax
0x180041c4a  mov     rax, [rbp+3Fh+arg_40]
0x180041c51  mov     [rbp+3Fh+var_80], rax
0x180041c55  mov     rax, [rbp+3Fh+arg_48]
0x180041c5c  mov     [rbp+3Fh+var_70], rax
0x180041c60  mov     rax, [rbp+3Fh+arg_58]
0x180041c67  mov     [rbp+3Fh+pbo], rax
0x180041c6b  mov     [rbp+3Fh+psoMask], r8
0x180041c6f  jz      loc_180041F36
0x180041c75  mov     ebx, [rbp+3Fh+rop4]
0x180041c7b  cmp     ebx, 0CCCCh
0x180041c81  jnz     short loc_180041C95
0x180041c83  mov     r8, r15
0x180041c86  mov     rdx, rdi
0x180041c89  mov     rcx, r14
0x180041c8c  call    DrawWhiteRect
0x180041c91  mov     r9, [rbp+3Fh+psoMask]
0x180041c95  test    byte ptr [r14+74h], 20h
0x180041c9a  jz      short loc_180041CA5
0x180041c9c  mov     ecx, ebx
0x180041c9e  call    InvertROPs
0x180041ca3  mov     ebx, eax
0x180041ca5  xor     r8d, r8d
0x180041ca8  cmp     ebx, 0CCCCh
0x180041cae  jz      loc_180041E79
0x180041cb4  test    r9, r9
0x180041cb7  jnz     loc_180041E79
0x180041cbd  mov     eax, ebx
0x180041cbf  shr     eax, 2
0x180041cc2  xor     eax, ebx
0x180041cc4  test    al, 33h
0x180041cc6  jz      loc_180041E79
0x180041ccc  mov     r10d, [rsi+48h]
0x180041cd0  cmp     r10d, 2
0x180041cd4  ja      loc_180041E79
0x180041cda  cmp     dword ptr [r12+48h], 2
0x180041ce0  jb      loc_180041E79
0x180041ce6  mov     ecx, [r14+6ECh]
0x180041ced  mov     edx, r8d
0x180041cf0  mov     [rbp+3Fh+var_94], edx
0x180041cf3  mov     r9d, r8d
0x180041cf6  mov     [rbp+3Fh+hsurf], r8
0x180041cfa  mov     qword ptr [rbp+3Fh+var_58.right], r8
0x180041cfe  mov     [rbp+3Fh+var_98], r8d
0x180041d02  test    ecx, ecx
0x180041d04  jz      short loc_180041D1A
0x180041d06  mov     eax, [rdi]
0x180041d08  div     ecx
0x180041d0a  mov     eax, [rdi+4]
0x180041d0d  mov     r9d, edx
0x180041d10  mov     [rbp+3Fh+var_98], edx
0x180041d13  xor     edx, edx
0x180041d15  div     ecx
0x180041d17  mov     [rbp+3Fh+var_94], edx
0x180041d1a  mov     ecx, [rdi]
0x180041d1c  mov     eax, [rdi+4]
0x180041d1f  mov     qword ptr [rbp+3Fh+var_58.left], r8
0x180041d23  mov     r8d, [rdi+8]
0x180041d27  sub     r8d, ecx
0x180041d2a  mov     dword ptr [rsp+110h+pxlo], r10d; iFormat
0x180041d2f  add     r8d, r9d; int
0x180041d32  neg     ecx
0x180041d34  mov     r9d, [rdi+0Ch]
0x180041d38  sub     r9d, eax
0x180041d3b  mov     [rbp+3Fh+pptlBrush.x], ecx
0x180041d3e  add     r9d, edx; int
0x180041d41  mov     [rbp+3Fh+var_58.right], r8d
0x180041d45  neg     eax
0x180041d47  mov     [rbp+3Fh+var_58.bottom], r9d
0x180041d4b  lea     rdx, [rbp+3Fh+hsurf]; int
0x180041d4f  mov     [rbp+3Fh+pptlBrush.y], eax
0x180041d52  mov     rcx, r14; int
0x180041d55  call    CreateBitmapSURFOBJ
0x180041d5a  mov     r14, rax
0x180041d5d  test    rax, rax
0x180041d60  jz      loc_180041E64
0x180041d66  mov     eax, [rbp+3Fh+var_98]
0x180041d69  xor     r9d, r9d; pco
0x180041d6c  add     [rbp+3Fh+var_58.left], eax
0x180041d6f  xor     r8d, r8d; psoMask
0x180041d72  mov     eax, [rbp+3Fh+var_94]
0x180041d75  mov     rdx, r12; psoSrc
0x180041d78  add     [rbp+3Fh+var_58.top], eax
0x180041d7b  mov     rcx, r14; psoDest
0x180041d7e  mov     rax, [rbp+3Fh+var_80]
0x180041d82  mov     [rsp+110h+iMode], 4; iMode
0x180041d8a  mov     [rsp+110h+pptlMask], 0; pptlMask
0x180041d93  mov     [rsp+110h+prclSrc], rax; prclSrc
0x180041d98  lea     rax, [rbp+3Fh+var_58]
0x180041d9c  mov     [rsp+110h+prclDest], rax; prclDest
0x180041da1  mov     rax, [rbp+3Fh+var_68]
0x180041da5  mov     [rsp+110h+pptlHTOrg], rax; pptlHTOrg
0x180041daa  mov     [rsp+110h+pca], 0; pca
0x180041db3  mov     [rsp+110h+pxlo], r13; pxlo
0x180041db8  call    cs:__imp_EngStretchBlt
0x180041dbf  nop     dword ptr [rax+rax+00h]
0x180041dc4  test    eax, eax
0x180041dc6  jz      loc_180041E55
0x180041dcc  xor     r12d, r12d
0x180041dcf  mov     rdx, rdi
0x180041dd2  mov     rcx, rsi
0x180041dd5  mov     qword ptr [rbp+3Fh+pptlBrush.x], r12
0x180041dd9  call    CheckBitmapSurface
0x180041dde  mov     [rsp+110h+iMode], ebx; rop4
0x180041de2  lea     rax, [rbp+3Fh+pptlBrush]
0x180041de6  mov     [rsp+110h+pptlMask], rax; pptlBrush
0x180041deb  mov     r9, r15; pco
0x180041dee  mov     rax, [rbp+3Fh+pbo]
0x180041df2  xor     r8d, r8d; psoMask
0x180041df5  mov     [rsp+110h+prclSrc], rax; pbo
0x180041dfa  mov     rdx, r14; psoSrc
0x180041dfd  mov     rax, [rbp+3Fh+var_70]
0x180041e01  mov     rcx, rsi; psoTrg
0x180041e04  mov     [rsp+110h+prclDest], rax; pptlMask
0x180041e09  lea     rax, [rbp+3Fh+var_58]
0x180041e0d  mov     [rsp+110h+pptlHTOrg], rax; pptlSrc
0x180041e12  mov     [rsp+110h+pca], rdi; prclTrg
0x180041e17  mov     [rsp+110h+pxlo], r12; pxlo
0x180041e1c  call    cs:__imp_EngBitBlt
0x180041e23  nop     dword ptr [rax+rax+00h]
0x180041e28  mov     rcx, r14; pso
0x180041e2b  mov     ebx, eax
0x180041e2d  call    cs:__imp_EngUnlockSurface
0x180041e34  nop     dword ptr [rax+rax+00h]
0x180041e39  mov     rcx, [rbp+3Fh+hsurf]; hsurf
0x180041e3d  test    rcx, rcx
0x180041e40  jz      short loc_180041E4E
0x180041e42  call    cs:__imp_EngDeleteSurface
0x180041e49  nop     dword ptr [rax+rax+00h]
0x180041e4e  mov     eax, ebx
0x180041e50  jmp     loc_180041F3B
0x180041e55  mov     rcx, r14; pso
0x180041e58  call    cs:__imp_EngUnlockSurface
0x180041e5f  nop     dword ptr [rax+rax+00h]
0x180041e64  mov     rcx, [rbp+3Fh+hsurf]; hsurf
0x180041e68  test    rcx, rcx
0x180041e6b  jz      short loc_180041E79
0x180041e6d  call    cs:__imp_EngDeleteSurface
0x180041e74  nop     dword ptr [rax+rax+00h]
0x180041e79  mov     rdx, rdi
0x180041e7c  mov     rcx, rsi
0x180041e7f  call    CheckBitmapSurface
0x180041e84  mov     r14, [rbp+3Fh+psoMask]
0x180041e88  cmp     ebx, 0CCCCh
0x180041e8e  jnz     short loc_180041ED9
0x180041e90  cmp     dword ptr [r12+48h], 1
0x180041e96  jnz     short loc_180041ED9
0x180041e98  cmp     dword ptr [rsi+48h], 1
0x180041e9c  jnz     short loc_180041ED9
0x180041e9e  cmp     [rbp+3Fh+arg_50], 3
0x180041ea5  jnz     short loc_180041ED9
0x180041ea7  test    r14, r14
0x180041eaa  jnz     short loc_180041ED9
0x180041eac  test    r15, r15
0x180041eaf  jz      short loc_180041EB7
0x180041eb1  cmp     [r15+14h], r14b
0x180041eb5  jnz     short loc_180041ED9
0x180041eb7  test    r13, r13
0x180041eba  jz      short loc_180041EC3
0x180041ebc  test    byte ptr [r13+4], 1
0x180041ec1  jz      short loc_180041ED9
0x180041ec3  mov     r8, [rbp+3Fh+var_80]
0x180041ec7  mov     r9, rdi
0x180041eca  mov     rdx, rsi
0x180041ecd  mov     rcx, r12
0x180041ed0  call    Fast1bppScaling
0x180041ed5  test    eax, eax
0x180041ed7  jnz     short loc_180041F36
0x180041ed9  mov     rax, [rbp+3Fh+pbo]
0x180041edd  mov     r9, r15; pco
0x180041ee0  mov     [rsp+110h+var_B0], ebx; rop4
0x180041ee4  mov     r8, r14; psoMask
0x180041ee7  mov     [rsp+110h+var_B8], rax; pbo
0x180041eec  mov     rdx, r12; psoSrc
0x180041eef  mov     rax, [rbp+3Fh+var_70]
0x180041ef3  mov     rcx, rsi; psoDest
0x180041ef6  mov     [rsp+110h+iMode], 4; iMode
0x180041efe  mov     [rsp+110h+pptlMask], rax; pptlMask
0x180041f03  mov     rax, [rbp+3Fh+var_80]
0x180041f07  mov     [rsp+110h+prclSrc], rax; prclSrc
0x180041f0c  mov     rax, [rbp+3Fh+var_68]
0x180041f10  mov     [rsp+110h+prclDest], rdi; prclDest
0x180041f15  mov     [rsp+110h+pptlHTOrg], rax; pptlHTOrg
0x180041f1a  mov     rax, [rbp+3Fh+var_60]
0x180041f1e  mov     [rsp+110h+pca], rax; pca
0x180041f23  mov     [rsp+110h+pxlo], r13; pxlo
0x180041f28  call    cs:__imp_EngStretchBltROP
0x180041f2f  nop     dword ptr [rax+rax+00h]
0x180041f34  jmp     short loc_180041F3B
0x180041f36  mov     eax, 1
0x180041f3b  mov     rcx, [rbp+3Fh+var_48]
0x180041f3f  xor     rcx, rsp; StackCookie
0x180041f42  call    __security_check_cookie
0x180041f47  add     rsp, 0D8h
0x180041f4e  pop     r15
0x180041f50  pop     r14
0x180041f52  pop     r13
0x180041f54  pop     r12
0x180041f56  pop     rdi
0x180041f57  pop     rsi
0x180041f58  pop     rbx
0x180041f59  pop     rbp
0x180041f5a  retn
```
