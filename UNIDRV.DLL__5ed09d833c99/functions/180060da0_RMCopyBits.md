# RMCopyBits

- ea: `0x180060da0`
- end: `0x180060f1c`
- name: `RMCopyBits`
- size: `380`
- prototype: `BOOL __fastcall(SURFOBJ *psoDest, SURFOBJ *psoSrc, CLIPOBJ *pco, XLATEOBJ *pxlo, RECTL *prclDest, POINTL *pptlSrc)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180015fd0`
- `0x1800160e8`
- `0x180017148`
- `0x1800388f0`
- `0x180049d00`
- `0x180060da0`

## import_xrefs

- `GDI32!EngCopyBits` at `0x180060e37`
- `GDI32!EngCopyBits` at `0x180060e37`

## pseudocode

```c
BOOL __fastcall RMCopyBits(
        SURFOBJ *psoDest,
        SURFOBJ *psoSrc,
        CLIPOBJ *pco,
        XLATEOBJ *pxlo,
        RECTL *prclDest,
        POINTL *pptlSrc)
{
  DHPDEV dhpdev; // rsi
  __int64 v12; // r8
  __int64 v13; // r9
  RECTL v14; // xmm1
  LONG y; // r11d
  LONG cx; // ecx
  __int64 v17; // r8
  int v18; // esi
  LONG v19; // r9d
  LONG cy; // eax
  POINTL pptlHTOrg; // [rsp+60h] [rbp-29h] BYREF
  RECTL prclSrc; // [rsp+68h] [rbp-21h] BYREF
  RECTL v23; // [rsp+78h] [rbp-11h] BYREF

  dhpdev = psoDest->dhpdev;
  if ( ((_DWORD)dhpdev[28] & 0x8000) == 0 )
    return 1;
  if ( (unsigned int)IsHTCompatibleSurfObj(*((_QWORD *)dhpdev + 512), (__int64)psoDest, (__int64)psoSrc, (__int64)pxlo) )
  {
    DrawWhiteRect((__int64)dhpdev, &prclDest->left, pco);
    CheckBitmapSurface(psoDest, &prclDest->left, v12, v13);
    return EngCopyBits(psoDest, psoSrc, pco, pxlo, prclDest, pptlSrc);
  }
  else
  {
    v14 = *prclDest;
    y = pptlSrc->y;
    cx = psoSrc->sizlBitmap.cx;
    v17 = HIDWORD(*(_QWORD *)&prclDest->left);
    v18 = _mm_cvtsi128_si32(*(__m128i *)prclDest);
    v19 = y + HIDWORD(*(_QWORD *)&prclDest->right) - v17;
    prclSrc.left = pptlSrc->x;
    v23 = v14;
    prclSrc.top = y;
    prclSrc.right = prclDest->right + prclSrc.left - v18;
    prclSrc.bottom = v19;
    if ( prclSrc.right > cx || v19 > psoSrc->sizlBitmap.cy )
    {
      cy = psoSrc->sizlBitmap.cy;
      prclSrc.right = cx;
      prclSrc.bottom = cy;
      v23.right = v18 + cx - prclSrc.left;
      v23.bottom = v17 + cy - y;
    }
    pptlHTOrg = 0;
    return DrvStretchBlt(psoDest, psoSrc, 0, pco, pxlo, 0, &pptlHTOrg, &v23, &prclSrc, 0, 4u);
  }
}

```

## disassembly

```asm
0x180060da0  push    rbp
0x180060da2  push    rbx
0x180060da3  push    rsi
0x180060da4  push    rdi
0x180060da5  push    r12
0x180060da7  push    r13
0x180060da9  push    r14
0x180060dab  push    r15
0x180060dad  lea     rbp, [rsp-0Fh]
0x180060db2  sub     rsp, 98h
0x180060db9  mov     rax, cs:__security_cookie
0x180060dc0  xor     rax, rsp
0x180060dc3  mov     [rbp+47h+var_48], rax
0x180060dc7  mov     rsi, [rcx+10h]
0x180060dcb  mov     r15, r9
0x180060dce  mov     r13, [rbp+47h+arg_28]
0x180060dd2  mov     r12, r8
0x180060dd5  mov     r14, [rbp+47h+arg_20]
0x180060dd9  mov     rbx, rdx
0x180060ddc  mov     rdi, rcx
0x180060ddf  test    dword ptr [rsi+70h], 8000h
0x180060de6  jnz     short loc_180060DF2
0x180060de8  mov     eax, 1
0x180060ded  jmp     loc_180060EFB
0x180060df2  mov     rcx, [rsi+1000h]
0x180060df9  mov     r8, rbx
0x180060dfc  mov     rdx, rdi
0x180060dff  call    IsHTCompatibleSurfObj
0x180060e04  test    eax, eax
0x180060e06  jz      short loc_180060E48
0x180060e08  mov     r8, r12
0x180060e0b  mov     rdx, r14
0x180060e0e  mov     rcx, rsi
0x180060e11  call    DrawWhiteRect
0x180060e16  mov     rdx, r14
0x180060e19  mov     rcx, rdi
0x180060e1c  call    CheckBitmapSurface
0x180060e21  mov     r9, r15; pxlo
0x180060e24  mov     [rsp+0D0h+pptlSrc], r13; pptlSrc
0x180060e29  mov     r8, r12; pco
0x180060e2c  mov     [rsp+0D0h+prclDest], r14; prclDest
0x180060e31  mov     rdx, rbx; psoSrc
0x180060e34  mov     rcx, rdi; psoDest
0x180060e37  call    cs:__imp_EngCopyBits
0x180060e3e  nop     dword ptr [rax+rax+00h]
0x180060e43  jmp     loc_180060EFB
0x180060e48  movups  xmm1, xmmword ptr [r14]
0x180060e4c  mov     r10d, [r13+0]
0x180060e50  mov     edx, r10d
0x180060e53  mov     r11d, [r13+4]
0x180060e57  mov     r9, [r14+8]
0x180060e5b  movq    r8, xmm1
0x180060e60  mov     ecx, [rbx+20h]
0x180060e63  shr     r9, 20h
0x180060e67  shr     r8, 20h
0x180060e6b  sub     r9d, r8d
0x180060e6e  movd    esi, xmm1
0x180060e72  add     r9d, r11d
0x180060e75  mov     [rbp+47h+var_68.left], r10d
0x180060e79  movups  xmmword ptr [rbp+47h+var_58.left], xmm1
0x180060e7d  sub     edx, esi
0x180060e7f  mov     [rbp+47h+var_68.top], r11d
0x180060e83  add     edx, [r14+8]
0x180060e87  mov     [rbp+47h+var_68.right], edx
0x180060e8a  mov     [rbp+47h+var_68.bottom], r9d
0x180060e8e  cmp     edx, ecx
0x180060e90  jg      short loc_180060E98
0x180060e92  cmp     r9d, [rbx+24h]
0x180060e96  jle     short loc_180060EB2
0x180060e98  mov     eax, [rbx+24h]
0x180060e9b  mov     [rbp+47h+var_68.right], ecx
0x180060e9e  sub     ecx, r10d
0x180060ea1  mov     [rbp+47h+var_68.bottom], eax
0x180060ea4  add     ecx, esi
0x180060ea6  sub     eax, r11d
0x180060ea9  mov     [rbp+47h+var_58.right], ecx
0x180060eac  add     eax, r8d
0x180060eaf  mov     [rbp+47h+var_58.bottom], eax
0x180060eb2  mov     [rsp+0D0h+iMode], 4; iMode
0x180060eba  lea     rax, [rbp+47h+var_68]
0x180060ebe  xor     ecx, ecx
0x180060ec0  mov     r9, r12; pco
0x180060ec3  mov     [rsp+0D0h+pptlMask], rcx; pptlMask
0x180060ec8  xor     r8d, r8d; psoMask
0x180060ecb  mov     [rsp+0D0h+prclSrc], rax; prclSrc
0x180060ed0  mov     rdx, rbx; psoSrc
0x180060ed3  lea     rax, [rbp+47h+var_58]
0x180060ed7  mov     qword ptr [rbp+47h+var_70.x], rcx
0x180060edb  mov     [rsp+0D0h+var_98], rax; prclDest
0x180060ee0  lea     rax, [rbp+47h+var_70]
0x180060ee4  mov     [rsp+0D0h+pptlHTOrg], rax; pptlHTOrg
0x180060ee9  mov     [rsp+0D0h+pptlSrc], rcx; pca
0x180060eee  mov     rcx, rdi; psoDest
0x180060ef1  mov     [rsp+0D0h+prclDest], r15; pxlo
0x180060ef6  call    DrvStretchBlt
0x180060efb  mov     rcx, [rbp+47h+var_48]
0x180060eff  xor     rcx, rsp; StackCookie
0x180060f02  call    __security_check_cookie
0x180060f07  add     rsp, 98h
0x180060f0e  pop     r15
0x180060f10  pop     r14
0x180060f12  pop     r13
0x180060f14  pop     r12
0x180060f16  pop     rdi
0x180060f17  pop     rsi
0x180060f18  pop     rbx
0x180060f19  pop     rbp
0x180060f1a  retn
```
