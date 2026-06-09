# HPGLTextOutAsBitmap

- ea: `0x180061920`
- end: `0x180061c61`
- name: `HPGLTextOutAsBitmap`
- size: `833`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18003949c`
- `0x1800487e0`
- `0x1800618bc`
- `0x180061920`
- `0x18006342c`
- `0x180063d60`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180061998`
- `KERNEL32!SetLastError` at `0x180061998`
- `GDI32!FONTOBJ_cGetGlyphs` at `0x180061a7d`
- `GDI32!FONTOBJ_cGetGlyphs` at `0x180061a7d`
- `GDI32!STROBJ_vEnumStart` at `0x180061a12`
- `GDI32!STROBJ_vEnumStart` at `0x180061a12`
- `GDI32!EngCreateBitmap` at `0x180061ab5`
- `GDI32!EngCreateBitmap` at `0x180061ab5`
- `GDI32!EngLockSurface` at `0x180061acb`
- `GDI32!EngLockSurface` at `0x180061acb`
- `GDI32!STROBJ_bEnum` at `0x180061a40`
- `GDI32!STROBJ_bEnum` at `0x180061a40`

## pseudocode

```c
__int64 __fastcall HPGLTextOutAsBitmap(
        struct _SURFOBJ *a1,
        STROBJ *a2,
        FONTOBJ *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        struct _BRUSHOBJ *a7,
        __int64 a8,
        __int64 a9,
        unsigned int a10)
{
  FONTOBJ *v10; // rsi
  DHPDEV dhpdev; // rcx
  __int64 v13; // r14
  unsigned int v15; // ebx
  ROP4 v16; // r15d
  struct _GLYPHPOS *pgp; // rcx
  ULONG i; // r12d
  SIZEL *v19; // rsi
  SIZEL v20; // r13
  HBITMAP Bitmap; // rax
  SURFOBJ *v22; // rax
  _BYTE *pvBits; // rcx
  SIZEL *v24; // r9
  int v25; // r8d
  int j; // r10d
  int k; // edx
  LONG v28; // r8d
  LONG v29; // edx
  LONG cy; // ecx
  bool v31; // zf
  LONG v32; // eax
  LONG v33; // eax
  struct _SURFOBJ *v34; // r11
  ULONG pc; // [rsp+60h] [rbp-91h] BYREF
  PGLYPHPOS ppgpos; // [rsp+68h] [rbp-89h] BYREF
  int v37; // [rsp+70h] [rbp-81h]
  POINTL v38; // [rsp+78h] [rbp-79h] BYREF
  FONTOBJ *v39; // [rsp+80h] [rbp-71h]
  PVOID ppvGlyph; // [rsp+88h] [rbp-69h] BYREF
  SIZEL v41; // [rsp+90h] [rbp-61h]
  HBITMAP v42; // [rsp+98h] [rbp-59h] BYREF
  struct _RECTL v43; // [rsp+A0h] [rbp-51h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-41h]
  struct _BRUSHOBJ *v45; // [rsp+B8h] [rbp-39h]
  struct _SURFOBJ *v46; // [rsp+C0h] [rbp-31h]
  struct _SURFOBJ *v47; // [rsp+C8h] [rbp-29h] BYREF
  RECTL v48; // [rsp+D0h] [rbp-21h] BYREF

  v46 = a1;
  ppgpos = 0;
  v45 = a7;
  pc = 0;
  v10 = a3;
  dhpdev = a1->dhpdev;
  ppvGlyph = 0;
  v38 = 0;
  v48 = 0;
  v13 = *((_QWORD *)dhpdev + 1);
  v44 = a4;
  v39 = a3;
  v43 = 0;
  if ( !v13 )
  {
    SetLastError(0xDu);
    return 0;
  }
  v15 = 1;
  BChangeAndTrackObjectType(dhpdev, 4);
  *(_DWORD *)(v13 + 204) = 1;
  *(_DWORD *)(v13 + 208) = 1;
  pc = a2->cGlyphs;
  if ( !pc )
    goto LABEL_35;
  v16 = 252;
  if ( a10 != 3341 )
    v16 = *((unsigned __int8 *)qword_180080280 + (a10 & 0xF))
        | (*((unsigned __int8 *)qword_180080280 + ((a10 >> 8) & 0xF)) << 8);
  if ( !a2->pgp )
    STROBJ_vEnumStart(a2);
  while ( 1 )
  {
    pgp = a2->pgp;
    if ( pgp )
    {
      pc = a2->cGlyphs;
      v37 = 0;
      ppgpos = pgp;
      goto LABEL_12;
    }
    v37 = STROBJ_bEnum(a2, &pc, &ppgpos);
    if ( v37 == -1 )
      break;
    pgp = ppgpos;
LABEL_12:
    for ( i = 0; i < pc; ++i )
    {
      if ( !FONTOBJ_cGetGlyphs(v10, 1u, 1u, &pgp->hg, &ppvGlyph) )
        goto LABEL_31;
      v19 = *(SIZEL **)ppvGlyph;
      v20 = *(SIZEL *)(*(_QWORD *)ppvGlyph + 8LL);
      v41 = v20;
      Bitmap = EngCreateBitmap(v20, v20.cx + 31, 1u, 1u, 0);
      v42 = Bitmap;
      if ( !Bitmap )
        goto LABEL_30;
      v22 = EngLockSurface((HSURF)Bitmap);
      v47 = v22;
      if ( !v22 )
      {
        DELETE_SURFOBJ(0, (HSURF *)&v42);
LABEL_30:
        v10 = v39;
LABEL_31:
        v15 = 0;
        break;
      }
      pvBits = v22->pvBits;
      v24 = v19 + 2;
      v25 = 0;
      for ( j = (v20.cx + 7) / 8; v25 < v41.cy; ++v25 )
      {
        for ( k = 0; k < j; ++pvBits )
        {
          ++k;
          *pvBits = v24->cx;
          v24 = (SIZEL *)((char *)v24 + 1);
        }
        pvBits += (int)(((j + 3) & 0xFFFFFFFC) - j);
      }
      v28 = v19->cx + ppgpos->ptl.x;
      v29 = v19->cy + ppgpos->ptl.y;
      v43.right = v28 + v19[1].cx;
      cy = v19[1].cy;
      v43.left = v28;
      v43.top = v29;
      v43.bottom = v29 + cy;
      v31 = *(_BYTE *)(v44 + 20) == 1;
      v38 = 0;
      if ( v31 )
      {
        v32 = *(_DWORD *)(v44 + 8);
        if ( v29 < v32 )
          v38.y = v32 - v29;
        v33 = *(_DWORD *)(v44 + 4);
        if ( v28 < v33 )
          v38.x = v33 - v28;
      }
      if ( (unsigned int)BRectanglesIntersect(&v43, (struct _RECTL *)(v44 + 4), &v48) )
        v15 = HPGLBitBlt(v46, v34, 0, 0, &v48, &v38, 0, v45, 0, v16);
      DELETE_SURFOBJ(&v47, (HSURF *)&v42);
      v10 = v39;
      pgp = ++ppgpos;
    }
    if ( !v37 )
      goto LABEL_35;
  }
  v15 = 0;
LABEL_35:
  *(_QWORD *)(v13 + 204) = 0;
  return v15;
}

```

## disassembly

```asm
0x180061920  push    rbp
0x180061922  push    rbx
0x180061923  push    rsi
0x180061924  push    rdi
0x180061925  push    r12
0x180061927  push    r13
0x180061929  push    r14
0x18006192b  push    r15
0x18006192d  lea     rbp, [rsp-7]
0x180061932  sub     rsp, 0F8h
0x180061939  mov     rax, cs:__security_cookie
0x180061940  xor     rax, rsp
0x180061943  mov     [rbp+3Fh+var_50], rax
0x180061947  xor     r13d, r13d
0x18006194a  mov     [rbp+3Fh+var_70], rcx
0x18006194e  mov     rax, rcx
0x180061951  mov     [rsp+130h+ppgpos], r13
0x180061956  mov     rcx, [rbp+3Fh+arg_30]
0x18006195a  xorps   xmm1, xmm1
0x18006195d  mov     [rbp+3Fh+var_78], rcx
0x180061961  xorps   xmm0, xmm0
0x180061964  mov     [rsp+130h+pc], r13d
0x180061969  mov     rsi, r8
0x18006196c  mov     rcx, [rax+10h]
0x180061970  mov     rdi, rdx
0x180061973  mov     [rbp+3Fh+var_A8], r13
0x180061977  mov     qword ptr [rbp+3Fh+var_B8.x], r13
0x18006197b  movups  xmmword ptr [rbp+3Fh+var_60.left], xmm1
0x18006197f  mov     r14, [rcx+8]
0x180061983  mov     [rbp+3Fh+var_80], r9
0x180061987  mov     [rbp+3Fh+var_B0], r8
0x18006198b  movups  xmmword ptr [rbp+3Fh+var_90.left], xmm0
0x18006198f  test    r14, r14
0x180061992  jnz     short loc_1800619A5
0x180061994  lea     ecx, [r13+0Dh]; dwErrCode
0x180061998  call    cs:__imp_SetLastError
0x18006199e  xor     eax, eax
0x1800619a0  jmp     loc_180061C41
0x1800619a5  mov     ebx, 1
0x1800619aa  lea     edx, [rbx+3]
0x1800619ad  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x1800619b2  mov     [r14+0CCh], ebx
0x1800619b9  mov     [r14+0D0h], ebx
0x1800619c0  mov     eax, [rdi]
0x1800619c2  mov     [rsp+130h+pc], eax
0x1800619c6  test    eax, eax
0x1800619c8  jz      loc_180061C34
0x1800619ce  cmp     [rbp+3Fh+arg_48], 0D0Dh
0x1800619d8  mov     r15d, 0FCh
0x1800619de  jz      short loc_180061A09
0x1800619e0  mov     ecx, [rbp+3Fh+arg_48]
0x1800619e6  lea     rdx, qword_180080280
0x1800619ed  mov     eax, ecx
0x1800619ef  and     ecx, 0Fh
0x1800619f2  shr     rax, 8
0x1800619f6  and     eax, 0Fh
0x1800619f9  movzx   r15d, byte ptr [rax+rdx]
0x1800619fe  movzx   eax, byte ptr [rcx+rdx]
0x180061a02  shl     r15d, 8
0x180061a06  or      r15d, eax
0x180061a09  cmp     [rdi+20h], r13
0x180061a0d  jnz     short loc_180061A18
0x180061a0f  mov     rcx, rdi; pstro
0x180061a12  call    cs:__imp_STROBJ_vEnumStart
0x180061a18  mov     rcx, [rdi+20h]
0x180061a1c  test    rcx, rcx
0x180061a1f  jz      short loc_180061A33
0x180061a21  mov     eax, [rdi]
0x180061a23  mov     [rsp+130h+pc], eax
0x180061a27  mov     [rsp+130h+var_C0], r13d
0x180061a2c  mov     [rsp+130h+ppgpos], rcx
0x180061a31  jmp     short loc_180061A58
0x180061a33  lea     r8, [rsp+130h+ppgpos]; ppgpos
0x180061a38  mov     rcx, rdi; pstro
0x180061a3b  lea     rdx, [rsp+130h+pc]; pc
0x180061a40  call    cs:__imp_STROBJ_bEnum
0x180061a46  mov     [rsp+130h+var_C0], eax
0x180061a4a  cmp     eax, 0FFFFFFFFh
0x180061a4d  jz      loc_180061C31
0x180061a53  mov     rcx, [rsp+130h+ppgpos]
0x180061a58  mov     r12d, r13d
0x180061a5b  cmp     r12d, [rsp+130h+pc]
0x180061a60  jnb     loc_180061C24
0x180061a66  mov     edx, 1; iMode
0x180061a6b  lea     rax, [rbp+3Fh+var_A8]
0x180061a6f  mov     r9, rcx; phg
0x180061a72  mov     [rsp+130h+ppvGlyph], rax; ppvGlyph
0x180061a77  mov     r8d, edx; cGlyph
0x180061a7a  mov     rcx, rsi; pfo
0x180061a7d  call    cs:__imp_FONTOBJ_cGetGlyphs
0x180061a83  test    eax, eax
0x180061a85  jz      loc_180061C21
0x180061a8b  mov     rax, [rbp+3Fh+var_A8]
0x180061a8f  mov     r9d, 1; fl
0x180061a95  mov     r8d, r9d; iFormat
0x180061a98  mov     [rsp+130h+ppvGlyph], 0; pvBits
0x180061aa1  mov     rsi, [rax]
0x180061aa4  mov     r13, [rsi+8]
0x180061aa8  mov     edx, r13d
0x180061aab  mov     [rbp+3Fh+var_A0], r13
0x180061aaf  add     edx, 1Fh; lWidth
0x180061ab2  mov     rcx, r13; sizl
0x180061ab5  call    cs:__imp_EngCreateBitmap
0x180061abb  mov     [rbp+3Fh+var_98], rax
0x180061abf  test    rax, rax
0x180061ac2  jz      loc_180061C1A
0x180061ac8  mov     rcx, rax; hsurf
0x180061acb  call    cs:__imp_EngLockSurface
0x180061ad1  mov     [rbp+3Fh+var_68], rax
0x180061ad5  mov     r11, rax
0x180061ad8  test    rax, rax
0x180061adb  jz      loc_180061C0F
0x180061ae1  mov     rcx, [rax+30h]
0x180061ae5  lea     r9, [rsi+10h]
0x180061ae9  lea     eax, [r13+7]
0x180061aed  mov     r8d, 8
0x180061af3  cdq
0x180061af4  xor     r13d, r13d
0x180061af7  idiv    r8d
0x180061afa  mov     r8d, r13d
0x180061afd  mov     r10d, eax
0x180061b00  add     eax, 3
0x180061b03  and     eax, 0FFFFFFFCh
0x180061b06  sub     eax, r10d
0x180061b09  cmp     dword ptr [rbp+3Fh+var_A0+4], r13d
0x180061b0d  jle     short loc_180061B3A
0x180061b0f  movsxd  r13, eax
0x180061b12  xor     edx, edx
0x180061b14  test    r10d, r10d
0x180061b17  jle     short loc_180061B2B
0x180061b19  mov     al, [r9]
0x180061b1c  inc     edx
0x180061b1e  mov     [rcx], al
0x180061b20  inc     r9
0x180061b23  inc     rcx
0x180061b26  cmp     edx, r10d
0x180061b29  jl      short loc_180061B19
0x180061b2b  add     rcx, r13
0x180061b2e  inc     r8d
0x180061b31  cmp     r8d, dword ptr [rbp+3Fh+var_A0+4]
0x180061b35  jl      short loc_180061B12
0x180061b37  xor     r13d, r13d
0x180061b3a  mov     ecx, [rsi+8]
0x180061b3d  mov     rdx, [rsp+130h+ppgpos]
0x180061b42  mov     r8d, [rdx+10h]
0x180061b46  add     r8d, [rsi]
0x180061b49  mov     edx, [rdx+14h]
0x180061b4c  add     ecx, r8d
0x180061b4f  add     edx, [rsi+4]
0x180061b52  mov     [rbp+3Fh+var_90.right], ecx
0x180061b55  mov     ecx, [rsi+0Ch]
0x180061b58  mov     rsi, [rbp+3Fh+var_80]
0x180061b5c  add     ecx, edx
0x180061b5e  mov     [rbp+3Fh+var_90.left], r8d
0x180061b62  mov     [rbp+3Fh+var_90.top], edx
0x180061b65  mov     [rbp+3Fh+var_90.bottom], ecx
0x180061b68  cmp     byte ptr [rsi+14h], 1
0x180061b6c  mov     qword ptr [rbp+3Fh+var_B8.x], 0
0x180061b74  jnz     short loc_180061B90
0x180061b76  mov     eax, [rsi+8]
0x180061b79  cmp     edx, eax
0x180061b7b  jge     short loc_180061B82
0x180061b7d  sub     eax, edx
0x180061b7f  mov     [rbp+3Fh+var_B8.y], eax
0x180061b82  mov     eax, [rsi+4]
0x180061b85  cmp     r8d, eax
0x180061b88  jge     short loc_180061B90
0x180061b8a  sub     eax, r8d
0x180061b8d  mov     [rbp+3Fh+var_B8.x], eax
0x180061b90  lea     rdx, [rsi+4]; struct _RECTL *
0x180061b94  lea     r8, [rbp+3Fh+var_60]; struct _RECTL *
0x180061b98  lea     rcx, [rbp+3Fh+var_90]; struct _RECTL *
0x180061b9c  call    ?BRectanglesIntersect@@YAHPEAU_RECTL@@00@Z; BRectanglesIntersect(_RECTL *,_RECTL *,_RECTL *)
0x180061ba1  test    eax, eax
0x180061ba3  jz      short loc_180061BE8
0x180061ba5  mov     rax, [rbp+3Fh+var_78]
0x180061ba9  xor     r9d, r9d
0x180061bac  mov     rcx, [rbp+3Fh+var_70]; struct _SURFOBJ *
0x180061bb0  xor     r8d, r8d; struct _SURFOBJ *
0x180061bb3  mov     [rsp+130h+var_E0], r15d; ROP4
0x180061bb8  mov     rdx, r11; struct _SURFOBJ *
0x180061bbb  mov     [rsp+130h+var_E8], r13; __int64
0x180061bc0  mov     [rsp+130h+var_F0], rax; struct _BRUSHOBJ *
0x180061bc5  lea     rax, [rbp+3Fh+var_B8]
0x180061bc9  mov     [rsp+130h+var_F8], r13; struct _POINTL *
0x180061bce  mov     [rsp+130h+var_100], rax; POINTL *
0x180061bd3  lea     rax, [rbp+3Fh+var_60]
0x180061bd7  mov     [rsp+130h+var_108], rax; RECTL *
0x180061bdc  mov     [rsp+130h+ppvGlyph], r13; struct _XLATEOBJ *
0x180061be1  call    HPGLBitBlt
0x180061be6  mov     ebx, eax
0x180061be8  lea     rdx, [rbp+3Fh+var_98]; HBITMAP *
0x180061bec  lea     rcx, [rbp+3Fh+var_68]; struct _SURFOBJ **
0x180061bf0  call    ?DELETE_SURFOBJ@@YAXPEAPEAU_SURFOBJ@@PEAPEAUHBITMAP__@@@Z; DELETE_SURFOBJ(_SURFOBJ * *,HBITMAP__ * *)
0x180061bf5  mov     rcx, [rsp+130h+ppgpos]
0x180061bfa  mov     rsi, [rbp+3Fh+var_B0]
0x180061bfe  add     rcx, 18h
0x180061c02  mov     [rsp+130h+ppgpos], rcx
0x180061c07  inc     r12d
0x180061c0a  jmp     loc_180061A5B
0x180061c0f  lea     rdx, [rbp+3Fh+var_98]; HBITMAP *
0x180061c13  xor     ecx, ecx; struct _SURFOBJ **
0x180061c15  call    ?DELETE_SURFOBJ@@YAXPEAPEAU_SURFOBJ@@PEAPEAUHBITMAP__@@@Z; DELETE_SURFOBJ(_SURFOBJ * *,HBITMAP__ * *)
0x180061c1a  mov     rsi, [rbp+3Fh+var_B0]
0x180061c1e  xor     r13d, r13d
0x180061c21  mov     ebx, r13d
0x180061c24  cmp     [rsp+130h+var_C0], r13d
0x180061c29  jnz     loc_180061A18
0x180061c2f  jmp     short loc_180061C34
0x180061c31  mov     ebx, r13d
0x180061c34  mov     qword ptr [r14+0CCh], 0
0x180061c3f  mov     eax, ebx
0x180061c41  mov     rcx, [rbp+3Fh+var_50]
0x180061c45  xor     rcx, rsp; StackCookie
0x180061c48  call    __security_check_cookie
0x180061c4d  add     rsp, 0F8h
0x180061c54  pop     r15
0x180061c56  pop     r14
0x180061c58  pop     r13
0x180061c5a  pop     r12
0x180061c5c  pop     rdi
0x180061c5d  pop     rsi
0x180061c5e  pop     rbx
0x180061c5f  pop     rbp
0x180061c60  retn
```
