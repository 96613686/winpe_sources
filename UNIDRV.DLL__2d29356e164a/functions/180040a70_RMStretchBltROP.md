# RMStretchBltROP

- ea: `0x180040a70`
- end: `0x180040dad`
- name: `RMStretchBltROP`
- size: `829`
- prototype: `BOOL __fastcall(SURFOBJ *psoDest, SURFOBJ *psoSrc, SURFOBJ *, CLIPOBJ *, XLATEOBJ *pxlo, COLORADJUSTMENT *, POINTL *, RECTL *prclTrg, RECTL *, POINTL *, int, BRUSHOBJ *, ROP4 rop4)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180015e68`
- `0x180016e6c`
- `0x180040a70`
- `0x180042598`
- `0x1800487e0`
- `0x18005f5b8`
- `0x18005f8bc`

## import_xrefs

- `GDI32!EngStretchBltROP` at `0x180040d80`
- `GDI32!EngStretchBltROP` at `0x180040d80`
- `GDI32!EngStretchBlt` at `0x180040c38`
- `GDI32!EngStretchBlt` at `0x180040c38`
- `GDI32!EngBitBlt` at `0x180040c92`
- `GDI32!EngBitBlt` at `0x180040c92`
- `GDI32!EngUnlockSurface` at `0x180040c9d`
- `GDI32!EngUnlockSurface` at `0x180040cbc`
- `GDI32!EngUnlockSurface` at `0x180040c9d`
- `GDI32!EngUnlockSurface` at `0x180040cbc`
- `GDI32!EngDeleteSurface` at `0x180040cac`
- `GDI32!EngDeleteSurface` at `0x180040ccb`
- `GDI32!EngDeleteSurface` at `0x180040cac`
- `GDI32!EngDeleteSurface` at `0x180040ccb`

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
  ULONG iBitmapFormat; // r10d
  unsigned int v21; // ecx
  int v22; // edx
  int v23; // r9d
  LONG left; // ecx
  LONG top; // eax
  unsigned int v26; // r8d
  int v27; // r9d
  SURFOBJ *v28; // rax
  SURFOBJ *v29; // r14
  BOOL v30; // ebx
  int v33; // [rsp+78h] [rbp-59h]
  int v34; // [rsp+7Ch] [rbp-55h]
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
    DrawWhiteRect(dhpdev, prclTrg, a4);
    v15 = a3;
  }
  if ( ((_BYTE)dhpdev[29] & 0x20) != 0 )
    v19 = InvertROPs(rop4);
  if ( v19 == 52428
    || v15
    || (((unsigned __int8)v19 ^ (unsigned __int8)(v19 >> 2)) & 0x33) == 0
    || (iBitmapFormat = psoDest->iBitmapFormat, iBitmapFormat > 2)
    || psoSrc->iBitmapFormat < 2 )
  {
LABEL_21:
    CheckBitmapSurface(psoDest, prclTrg);
    if ( v19 != 52428
      || psoSrc->iBitmapFormat != 1
      || psoDest->iBitmapFormat != 1
      || a11 != 3
      || a3
      || a4 && a4->iDComplexity
      || pxlo && (pxlo->flXlate & 1) == 0
      || !(unsigned int)Fast1bppScaling(psoSrc, psoDest, prclSrc, prclTrg) )
    {
      return EngStretchBltROP(psoDest, psoSrc, a3, a4, pxlo, pca, pptlHTOrg, prclTrg, prclSrc, pptlMask, 4u, pbo, v19);
    }
    return 1;
  }
  v21 = *((_DWORD *)dhpdev + 443);
  v22 = 0;
  v34 = 0;
  v23 = 0;
  hsurf = 0;
  *(_QWORD *)&prclDest.right = 0;
  v33 = 0;
  if ( v21 )
  {
    v23 = prclTrg->left % v21;
    v33 = v23;
    v22 = prclTrg->top % v21;
    v34 = v22;
  }
  left = prclTrg->left;
  top = prclTrg->top;
  *(_QWORD *)&prclDest.left = 0;
  v26 = v23 + prclTrg->right - left;
  v27 = prclTrg->bottom - top;
  pptlBrush.x = -left;
  prclDest.right = v26;
  prclDest.bottom = v22 + v27;
  pptlBrush.y = -top;
  v28 = CreateBitmapSURFOBJ((__int64)dhpdev, &hsurf, v26, v22 + v27, iBitmapFormat);
  v29 = v28;
  if ( !v28 )
  {
LABEL_19:
    if ( hsurf )
      EngDeleteSurface(hsurf);
    goto LABEL_21;
  }
  prclDest.left += v33;
  prclDest.top += v34;
  if ( !EngStretchBlt(v28, psoSrc, 0, 0, pxlo, 0, pptlHTOrg, &prclDest, prclSrc, 0, 4u) )
  {
    EngUnlockSurface(v29);
    goto LABEL_19;
  }
  pptlBrush = 0;
  CheckBitmapSurface(psoDest, prclTrg);
  v30 = EngBitBlt(psoDest, v29, 0, a4, 0, prclTrg, (POINTL *)&prclDest, pptlMask, pbo, &pptlBrush, v19);
  EngUnlockSurface(v29);
  if ( hsurf )
    EngDeleteSurface(hsurf);
  return v30;
}

```

## disassembly

```asm
0x180040a70  push    rbp
0x180040a72  push    rbx
0x180040a73  push    rsi
0x180040a74  push    rdi
0x180040a75  push    r12
0x180040a77  push    r13
0x180040a79  push    r14
0x180040a7b  push    r15
0x180040a7d  lea     rbp, [rsp-7]
0x180040a82  sub     rsp, 0D8h
0x180040a89  mov     rax, cs:__security_cookie
0x180040a90  xor     rax, rsp
0x180040a93  mov     [rbp+3Fh+var_48], rax
0x180040a97  mov     rax, [rbp+3Fh+arg_28]
0x180040a9b  mov     r15, r9
0x180040a9e  mov     r14, [rcx+10h]
0x180040aa2  mov     r9, r8
0x180040aa5  mov     rdi, [rbp+3Fh+prclTrg]
0x180040aac  mov     r12, rdx
0x180040aaf  mov     r13, [rbp+3Fh+arg_20]
0x180040ab3  mov     rsi, rcx
0x180040ab6  mov     [rbp+3Fh+var_60], rax
0x180040aba  test    dword ptr [r14+70h], 8000h
0x180040ac2  mov     rax, [rbp+3Fh+arg_30]
0x180040ac6  mov     [rbp+3Fh+var_68], rax
0x180040aca  mov     rax, [rbp+3Fh+arg_40]
0x180040ad1  mov     [rbp+3Fh+var_80], rax
0x180040ad5  mov     rax, [rbp+3Fh+arg_48]
0x180040adc  mov     [rbp+3Fh+var_70], rax
0x180040ae0  mov     rax, [rbp+3Fh+arg_58]
0x180040ae7  mov     [rbp+3Fh+pbo], rax
0x180040aeb  mov     [rbp+3Fh+psoMask], r8
0x180040aef  jz      loc_180040D88
0x180040af5  mov     ebx, [rbp+3Fh+rop4]
0x180040afb  cmp     ebx, 0CCCCh
0x180040b01  jnz     short loc_180040B15
0x180040b03  mov     r8, r15
0x180040b06  mov     rdx, rdi
0x180040b09  mov     rcx, r14
0x180040b0c  call    DrawWhiteRect
0x180040b11  mov     r9, [rbp+3Fh+psoMask]
0x180040b15  test    byte ptr [r14+74h], 20h
0x180040b1a  jz      short loc_180040B25
0x180040b1c  mov     ecx, ebx
0x180040b1e  call    InvertROPs
0x180040b23  mov     ebx, eax
0x180040b25  xor     r8d, r8d
0x180040b28  cmp     ebx, 0CCCCh
0x180040b2e  jz      loc_180040CD1
0x180040b34  test    r9, r9
0x180040b37  jnz     loc_180040CD1
0x180040b3d  mov     eax, ebx
0x180040b3f  shr     eax, 2
0x180040b42  xor     eax, ebx
0x180040b44  test    al, 33h
0x180040b46  jz      loc_180040CD1
0x180040b4c  mov     r10d, [rsi+48h]
0x180040b50  cmp     r10d, 2
0x180040b54  ja      loc_180040CD1
0x180040b5a  cmp     dword ptr [r12+48h], 2
0x180040b60  jb      loc_180040CD1
0x180040b66  mov     ecx, [r14+6ECh]
0x180040b6d  mov     edx, r8d
0x180040b70  mov     [rbp+3Fh+var_94], edx
0x180040b73  mov     r9d, r8d
0x180040b76  mov     [rbp+3Fh+hsurf], r8
0x180040b7a  mov     qword ptr [rbp+3Fh+var_58.right], r8
0x180040b7e  mov     [rbp+3Fh+var_98], r8d
0x180040b82  test    ecx, ecx
0x180040b84  jz      short loc_180040B9A
0x180040b86  mov     eax, [rdi]
0x180040b88  div     ecx
0x180040b8a  mov     eax, [rdi+4]
0x180040b8d  mov     r9d, edx
0x180040b90  mov     [rbp+3Fh+var_98], edx
0x180040b93  xor     edx, edx
0x180040b95  div     ecx
0x180040b97  mov     [rbp+3Fh+var_94], edx
0x180040b9a  mov     ecx, [rdi]
0x180040b9c  mov     eax, [rdi+4]
0x180040b9f  mov     qword ptr [rbp+3Fh+var_58.left], r8
0x180040ba3  mov     r8d, [rdi+8]
0x180040ba7  sub     r8d, ecx
0x180040baa  mov     dword ptr [rsp+110h+pxlo], r10d; iFormat
0x180040baf  add     r8d, r9d; int
0x180040bb2  neg     ecx
0x180040bb4  mov     r9d, [rdi+0Ch]
0x180040bb8  sub     r9d, eax
0x180040bbb  mov     [rbp+3Fh+pptlBrush.x], ecx
0x180040bbe  add     r9d, edx; int
0x180040bc1  mov     [rbp+3Fh+var_58.right], r8d
0x180040bc5  neg     eax
0x180040bc7  mov     [rbp+3Fh+var_58.bottom], r9d
0x180040bcb  lea     rdx, [rbp+3Fh+hsurf]; int
0x180040bcf  mov     [rbp+3Fh+pptlBrush.y], eax
0x180040bd2  mov     rcx, r14; int
0x180040bd5  call    CreateBitmapSURFOBJ
0x180040bda  mov     r14, rax
0x180040bdd  test    rax, rax
0x180040be0  jz      loc_180040CC2
0x180040be6  mov     eax, [rbp+3Fh+var_98]
0x180040be9  xor     r9d, r9d; pco
0x180040bec  add     [rbp+3Fh+var_58.left], eax
0x180040bef  xor     r8d, r8d; psoMask
0x180040bf2  mov     eax, [rbp+3Fh+var_94]
0x180040bf5  mov     rdx, r12; psoSrc
0x180040bf8  add     [rbp+3Fh+var_58.top], eax
0x180040bfb  mov     rcx, r14; psoDest
0x180040bfe  mov     rax, [rbp+3Fh+var_80]
0x180040c02  mov     [rsp+110h+iMode], 4; iMode
0x180040c0a  mov     [rsp+110h+pptlMask], 0; pptlMask
0x180040c13  mov     [rsp+110h+prclSrc], rax; prclSrc
0x180040c18  lea     rax, [rbp+3Fh+var_58]
0x180040c1c  mov     [rsp+110h+prclDest], rax; prclDest
0x180040c21  mov     rax, [rbp+3Fh+var_68]
0x180040c25  mov     [rsp+110h+pptlHTOrg], rax; pptlHTOrg
0x180040c2a  mov     [rsp+110h+pca], 0; pca
0x180040c33  mov     [rsp+110h+pxlo], r13; pxlo
0x180040c38  call    cs:__imp_EngStretchBlt
0x180040c3e  test    eax, eax
0x180040c40  jz      short loc_180040CB9
0x180040c42  xor     r12d, r12d
0x180040c45  mov     rdx, rdi
0x180040c48  mov     rcx, rsi
0x180040c4b  mov     qword ptr [rbp+3Fh+pptlBrush.x], r12
0x180040c4f  call    CheckBitmapSurface
0x180040c54  mov     [rsp+110h+iMode], ebx; rop4
0x180040c58  lea     rax, [rbp+3Fh+pptlBrush]
0x180040c5c  mov     [rsp+110h+pptlMask], rax; pptlBrush
0x180040c61  mov     r9, r15; pco
0x180040c64  mov     rax, [rbp+3Fh+pbo]
0x180040c68  xor     r8d, r8d; psoMask
0x180040c6b  mov     [rsp+110h+prclSrc], rax; pbo
0x180040c70  mov     rdx, r14; psoSrc
0x180040c73  mov     rax, [rbp+3Fh+var_70]
0x180040c77  mov     rcx, rsi; psoTrg
0x180040c7a  mov     [rsp+110h+prclDest], rax; pptlMask
0x180040c7f  lea     rax, [rbp+3Fh+var_58]
0x180040c83  mov     [rsp+110h+pptlHTOrg], rax; pptlSrc
0x180040c88  mov     [rsp+110h+pca], rdi; prclTrg
0x180040c8d  mov     [rsp+110h+pxlo], r12; pxlo
0x180040c92  call    cs:__imp_EngBitBlt
0x180040c98  mov     rcx, r14; pso
0x180040c9b  mov     ebx, eax
0x180040c9d  call    cs:__imp_EngUnlockSurface
0x180040ca3  mov     rcx, [rbp+3Fh+hsurf]; hsurf
0x180040ca7  test    rcx, rcx
0x180040caa  jz      short loc_180040CB2
0x180040cac  call    cs:__imp_EngDeleteSurface
0x180040cb2  mov     eax, ebx
0x180040cb4  jmp     loc_180040D8D
0x180040cb9  mov     rcx, r14; pso
0x180040cbc  call    cs:__imp_EngUnlockSurface
0x180040cc2  mov     rcx, [rbp+3Fh+hsurf]; hsurf
0x180040cc6  test    rcx, rcx
0x180040cc9  jz      short loc_180040CD1
0x180040ccb  call    cs:__imp_EngDeleteSurface
0x180040cd1  mov     rdx, rdi
0x180040cd4  mov     rcx, rsi
0x180040cd7  call    CheckBitmapSurface
0x180040cdc  mov     r14, [rbp+3Fh+psoMask]
0x180040ce0  cmp     ebx, 0CCCCh
0x180040ce6  jnz     short loc_180040D31
0x180040ce8  cmp     dword ptr [r12+48h], 1
0x180040cee  jnz     short loc_180040D31
0x180040cf0  cmp     dword ptr [rsi+48h], 1
0x180040cf4  jnz     short loc_180040D31
0x180040cf6  cmp     [rbp+3Fh+arg_50], 3
0x180040cfd  jnz     short loc_180040D31
0x180040cff  test    r14, r14
0x180040d02  jnz     short loc_180040D31
0x180040d04  test    r15, r15
0x180040d07  jz      short loc_180040D0F
0x180040d09  cmp     [r15+14h], r14b
0x180040d0d  jnz     short loc_180040D31
0x180040d0f  test    r13, r13
0x180040d12  jz      short loc_180040D1B
0x180040d14  test    byte ptr [r13+4], 1
0x180040d19  jz      short loc_180040D31
0x180040d1b  mov     r8, [rbp+3Fh+var_80]
0x180040d1f  mov     r9, rdi
0x180040d22  mov     rdx, rsi
0x180040d25  mov     rcx, r12
0x180040d28  call    Fast1bppScaling
0x180040d2d  test    eax, eax
0x180040d2f  jnz     short loc_180040D88
0x180040d31  mov     rax, [rbp+3Fh+pbo]
0x180040d35  mov     r9, r15; pco
0x180040d38  mov     [rsp+110h+var_B0], ebx; rop4
0x180040d3c  mov     r8, r14; psoMask
0x180040d3f  mov     [rsp+110h+var_B8], rax; pbo
0x180040d44  mov     rdx, r12; psoSrc
0x180040d47  mov     rax, [rbp+3Fh+var_70]
0x180040d4b  mov     rcx, rsi; psoDest
0x180040d4e  mov     [rsp+110h+iMode], 4; iMode
0x180040d56  mov     [rsp+110h+pptlMask], rax; pptlMask
0x180040d5b  mov     rax, [rbp+3Fh+var_80]
0x180040d5f  mov     [rsp+110h+prclSrc], rax; prclSrc
0x180040d64  mov     rax, [rbp+3Fh+var_68]
0x180040d68  mov     [rsp+110h+prclDest], rdi; prclDest
0x180040d6d  mov     [rsp+110h+pptlHTOrg], rax; pptlHTOrg
0x180040d72  mov     rax, [rbp+3Fh+var_60]
0x180040d76  mov     [rsp+110h+pca], rax; pca
0x180040d7b  mov     [rsp+110h+pxlo], r13; pxlo
0x180040d80  call    cs:__imp_EngStretchBltROP
0x180040d86  jmp     short loc_180040D8D
0x180040d88  mov     eax, 1
0x180040d8d  mov     rcx, [rbp+3Fh+var_48]
0x180040d91  xor     rcx, rsp; StackCookie
0x180040d94  call    __security_check_cookie
0x180040d99  add     rsp, 0D8h
0x180040da0  pop     r15
0x180040da2  pop     r14
0x180040da4  pop     r13
0x180040da6  pop     r12
0x180040da8  pop     rdi
0x180040da9  pop     rsi
0x180040daa  pop     rbx
0x180040dab  pop     rbp
0x180040dac  retn
```
