# RMCopyBits

- ea: `0x18005f960`
- end: `0x18005fad5`
- name: `RMCopyBits`
- size: `373`
- prototype: `__int64 __fastcall(SURFOBJ *psoDest, SURFOBJ *psoSrc, CLIPOBJ *pco, XLATEOBJ *pxlo, RECTL *, POINTL *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180015d64`
- `0x180015e68`
- `0x180016e6c`
- `0x180037e80`
- `0x1800487e0`
- `0x18005f960`

## import_xrefs

- `GDI32!EngCopyBits` at `0x18005f9f7`
- `GDI32!EngCopyBits` at `0x18005f9f7`

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
  RECTL v12; // xmm1
  LONG y; // r11d
  LONG cx; // ecx
  __int64 v15; // r8
  int v16; // esi
  LONG v17; // r9d
  LONG cy; // eax
  POINTL pptlHTOrg; // [rsp+60h] [rbp-29h] BYREF
  RECTL prclSrc; // [rsp+68h] [rbp-21h] BYREF
  RECTL v21; // [rsp+78h] [rbp-11h] BYREF

  dhpdev = psoDest->dhpdev;
  if ( ((_DWORD)dhpdev[28] & 0x8000) == 0 )
    return 1;
  if ( (unsigned int)IsHTCompatibleSurfObj(*((_QWORD *)dhpdev + 512), psoDest, psoSrc, pxlo) )
  {
    DrawWhiteRect(dhpdev, prclDest, pco);
    CheckBitmapSurface(psoDest, &prclDest->left);
    return EngCopyBits(psoDest, psoSrc, pco, pxlo, prclDest, pptlSrc);
  }
  else
  {
    v12 = *prclDest;
    y = pptlSrc->y;
    cx = psoSrc->sizlBitmap.cx;
    v15 = HIDWORD(*(_QWORD *)&prclDest->left);
    v16 = _mm_cvtsi128_si32(*(__m128i *)prclDest);
    v17 = y + HIDWORD(*(_QWORD *)&prclDest->right) - v15;
    prclSrc.left = pptlSrc->x;
    v21 = v12;
    prclSrc.top = y;
    prclSrc.right = prclDest->right + prclSrc.left - v16;
    prclSrc.bottom = v17;
    if ( prclSrc.right > cx || v17 > psoSrc->sizlBitmap.cy )
    {
      cy = psoSrc->sizlBitmap.cy;
      prclSrc.right = cx;
      prclSrc.bottom = cy;
      v21.right = v16 + cx - prclSrc.left;
      v21.bottom = v15 + cy - y;
    }
    pptlHTOrg = 0;
    return DrvStretchBlt(psoDest, psoSrc, 0, pco, pxlo, 0, &pptlHTOrg, &v21, &prclSrc, 0, 4u);
  }
}

```

## disassembly

```asm
0x18005f960  push    rbp
0x18005f962  push    rbx
0x18005f963  push    rsi
0x18005f964  push    rdi
0x18005f965  push    r12
0x18005f967  push    r13
0x18005f969  push    r14
0x18005f96b  push    r15
0x18005f96d  lea     rbp, [rsp-0Fh]
0x18005f972  sub     rsp, 98h
0x18005f979  mov     rax, cs:__security_cookie
0x18005f980  xor     rax, rsp
0x18005f983  mov     [rbp+47h+var_48], rax
0x18005f987  mov     rsi, [rcx+10h]
0x18005f98b  mov     r15, r9
0x18005f98e  mov     r13, [rbp+47h+arg_28]
0x18005f992  mov     r12, r8
0x18005f995  mov     r14, [rbp+47h+arg_20]
0x18005f999  mov     rbx, rdx
0x18005f99c  mov     rdi, rcx
0x18005f99f  test    dword ptr [rsi+70h], 8000h
0x18005f9a6  jnz     short loc_18005F9B2
0x18005f9a8  mov     eax, 1
0x18005f9ad  jmp     loc_18005FAB5
0x18005f9b2  mov     rcx, [rsi+1000h]
0x18005f9b9  mov     r8, rbx
0x18005f9bc  mov     rdx, rdi
0x18005f9bf  call    IsHTCompatibleSurfObj
0x18005f9c4  test    eax, eax
0x18005f9c6  jz      short loc_18005FA02
0x18005f9c8  mov     r8, r12
0x18005f9cb  mov     rdx, r14
0x18005f9ce  mov     rcx, rsi
0x18005f9d1  call    DrawWhiteRect
0x18005f9d6  mov     rdx, r14
0x18005f9d9  mov     rcx, rdi
0x18005f9dc  call    CheckBitmapSurface
0x18005f9e1  mov     r9, r15; pxlo
0x18005f9e4  mov     [rsp+0D0h+pptlSrc], r13; pptlSrc
0x18005f9e9  mov     r8, r12; pco
0x18005f9ec  mov     [rsp+0D0h+prclDest], r14; prclDest
0x18005f9f1  mov     rdx, rbx; psoSrc
0x18005f9f4  mov     rcx, rdi; psoDest
0x18005f9f7  call    cs:__imp_EngCopyBits
0x18005f9fd  jmp     loc_18005FAB5
0x18005fa02  movups  xmm1, xmmword ptr [r14]
0x18005fa06  mov     r10d, [r13+0]
0x18005fa0a  mov     edx, r10d
0x18005fa0d  mov     r11d, [r13+4]
0x18005fa11  mov     r9, [r14+8]
0x18005fa15  movq    r8, xmm1
0x18005fa1a  mov     ecx, [rbx+20h]
0x18005fa1d  shr     r9, 20h
0x18005fa21  shr     r8, 20h
0x18005fa25  sub     r9d, r8d
0x18005fa28  movd    esi, xmm1
0x18005fa2c  add     r9d, r11d
0x18005fa2f  mov     [rbp+47h+var_68.left], r10d
0x18005fa33  movups  xmmword ptr [rbp+47h+var_58.left], xmm1
0x18005fa37  sub     edx, esi
0x18005fa39  mov     [rbp+47h+var_68.top], r11d
0x18005fa3d  add     edx, [r14+8]
0x18005fa41  mov     [rbp+47h+var_68.right], edx
0x18005fa44  mov     [rbp+47h+var_68.bottom], r9d
0x18005fa48  cmp     edx, ecx
0x18005fa4a  jg      short loc_18005FA52
0x18005fa4c  cmp     r9d, [rbx+24h]
0x18005fa50  jle     short loc_18005FA6C
0x18005fa52  mov     eax, [rbx+24h]
0x18005fa55  mov     [rbp+47h+var_68.right], ecx
0x18005fa58  sub     ecx, r10d
0x18005fa5b  mov     [rbp+47h+var_68.bottom], eax
0x18005fa5e  add     ecx, esi
0x18005fa60  sub     eax, r11d
0x18005fa63  mov     [rbp+47h+var_58.right], ecx
0x18005fa66  add     eax, r8d
0x18005fa69  mov     [rbp+47h+var_58.bottom], eax
0x18005fa6c  mov     [rsp+0D0h+iMode], 4; iMode
0x18005fa74  lea     rax, [rbp+47h+var_68]
0x18005fa78  xor     ecx, ecx
0x18005fa7a  mov     r9, r12; pco
0x18005fa7d  mov     [rsp+0D0h+pptlMask], rcx; pptlMask
0x18005fa82  xor     r8d, r8d; psoMask
0x18005fa85  mov     [rsp+0D0h+prclSrc], rax; prclSrc
0x18005fa8a  mov     rdx, rbx; psoSrc
0x18005fa8d  lea     rax, [rbp+47h+var_58]
0x18005fa91  mov     qword ptr [rbp+47h+var_70.x], rcx
0x18005fa95  mov     [rsp+0D0h+var_98], rax; prclDest
0x18005fa9a  lea     rax, [rbp+47h+var_70]
0x18005fa9e  mov     [rsp+0D0h+pptlHTOrg], rax; pptlHTOrg
0x18005faa3  mov     [rsp+0D0h+pptlSrc], rcx; pca
0x18005faa8  mov     rcx, rdi; psoDest
0x18005faab  mov     [rsp+0D0h+prclDest], r15; pxlo
0x18005fab0  call    DrvStretchBlt
0x18005fab5  mov     rcx, [rbp+47h+var_48]
0x18005fab9  xor     rcx, rsp; StackCookie
0x18005fabc  call    __security_check_cookie
0x18005fac1  add     rsp, 98h
0x18005fac8  pop     r15
0x18005faca  pop     r14
0x18005facc  pop     r13
0x18005face  pop     r12
0x18005fad0  pop     rdi
0x18005fad1  pop     rsi
0x18005fad2  pop     rbx
0x18005fad3  pop     rbp
0x18005fad4  retn
```
