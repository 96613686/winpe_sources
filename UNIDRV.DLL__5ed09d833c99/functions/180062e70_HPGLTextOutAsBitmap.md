# HPGLTextOutAsBitmap

- ea: `0x180062e70`
- end: `0x1800631d6`
- name: `HPGLTextOutAsBitmap`
- size: `870`
- prototype: `__int64 __fastcall(struct _SURFOBJ *, STROBJ *, FONTOBJ *, __int64, __int64, __int64, struct _BRUSHOBJ *, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180039f24`
- `0x180049d00`
- `0x180062e04`
- `0x180062e70`
- `0x180064a78`
- `0x180065400`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180062ee8`
- `KERNEL32!SetLastError` at `0x180062ee8`
- `GDI32!FONTOBJ_cGetGlyphs` at `0x180062fdf`
- `GDI32!FONTOBJ_cGetGlyphs` at `0x180062fdf`
- `GDI32!STROBJ_vEnumStart` at `0x180062f68`
- `GDI32!STROBJ_vEnumStart` at `0x180062f68`
- `GDI32!EngCreateBitmap` at `0x18006301d`
- `GDI32!EngCreateBitmap` at `0x18006301d`
- `GDI32!EngLockSurface` at `0x180063039`
- `GDI32!EngLockSurface` at `0x180063039`
- `GDI32!STROBJ_bEnum` at `0x180062f9c`
- `GDI32!STROBJ_bEnum` at `0x180062f9c`

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
  GLYPHPOS *pgp; // rcx
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
  BChangeAndTrackObjectType((__int64)dhpdev, 4);
  *(_DWORD *)(v13 + 204) = 1;
  *(_DWORD *)(v13 + 208) = 1;
  pc = a2->cGlyphs;
  if ( !pc )
    goto LABEL_35;
  v16 = 252;
  if ( a10 != 3341 )
    v16 = *((unsigned __int8 *)qword_180082240 + (a10 & 0xF))
        | (*((unsigned __int8 *)qword_180082240 + ((a10 >> 8) & 0xF)) << 8);
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
        v15 = HPGLBitBlt(v46, v34, 0, 0, 0, &v48, &v38, 0, v45, 0, v16);
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
0x180062e70  push    rbp
0x180062e72  push    rbx
0x180062e73  push    rsi
0x180062e74  push    rdi
0x180062e75  push    r12
0x180062e77  push    r13
0x180062e79  push    r14
0x180062e7b  push    r15
0x180062e7d  lea     rbp, [rsp-7]
0x180062e82  sub     rsp, 0F8h
0x180062e89  mov     rax, cs:__security_cookie
0x180062e90  xor     rax, rsp
0x180062e93  mov     [rbp+3Fh+var_50], rax
0x180062e97  xor     r13d, r13d
0x180062e9a  mov     [rbp+3Fh+var_70], rcx
0x180062e9e  mov     rax, rcx
0x180062ea1  mov     [rsp+130h+ppgpos], r13
0x180062ea6  mov     rcx, [rbp+3Fh+arg_30]
0x180062eaa  xorps   xmm1, xmm1
0x180062ead  mov     [rbp+3Fh+var_78], rcx
0x180062eb1  xorps   xmm0, xmm0
0x180062eb4  mov     [rsp+130h+pc], r13d
0x180062eb9  mov     rsi, r8
0x180062ebc  mov     rcx, [rax+10h]
0x180062ec0  mov     rdi, rdx
0x180062ec3  mov     [rbp+3Fh+var_A8], r13
0x180062ec7  mov     qword ptr [rbp+3Fh+var_B8.x], r13
0x180062ecb  movups  xmmword ptr [rbp+3Fh+var_60.left], xmm1
0x180062ecf  mov     r14, [rcx+8]
0x180062ed3  mov     [rbp+3Fh+var_80], r9
0x180062ed7  mov     [rbp+3Fh+var_B0], r8
0x180062edb  movups  xmmword ptr [rbp+3Fh+var_90.left], xmm0
0x180062edf  test    r14, r14
0x180062ee2  jnz     short loc_180062EFB
0x180062ee4  lea     ecx, [r13+0Dh]; dwErrCode
0x180062ee8  call    cs:__imp_SetLastError
0x180062eef  nop     dword ptr [rax+rax+00h]
0x180062ef4  xor     eax, eax
0x180062ef6  jmp     loc_1800631B5
0x180062efb  mov     ebx, 1
0x180062f00  lea     edx, [rbx+3]
0x180062f03  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180062f08  mov     [r14+0CCh], ebx
0x180062f0f  mov     [r14+0D0h], ebx
0x180062f16  mov     eax, [rdi]
0x180062f18  mov     [rsp+130h+pc], eax
0x180062f1c  test    eax, eax
0x180062f1e  jz      loc_1800631A8
0x180062f24  cmp     [rbp+3Fh+arg_48], 0D0Dh
0x180062f2e  mov     r15d, 0FCh
0x180062f34  jz      short loc_180062F5F
0x180062f36  mov     ecx, [rbp+3Fh+arg_48]
0x180062f3c  lea     rdx, qword_180082240
0x180062f43  mov     eax, ecx
0x180062f45  and     ecx, 0Fh
0x180062f48  shr     rax, 8
0x180062f4c  and     eax, 0Fh
0x180062f4f  movzx   r15d, byte ptr [rax+rdx]
0x180062f54  movzx   eax, byte ptr [rcx+rdx]
0x180062f58  shl     r15d, 8
0x180062f5c  or      r15d, eax
0x180062f5f  cmp     [rdi+20h], r13
0x180062f63  jnz     short loc_180062F74
0x180062f65  mov     rcx, rdi; pstro
0x180062f68  call    cs:__imp_STROBJ_vEnumStart
0x180062f6f  nop     dword ptr [rax+rax+00h]
0x180062f74  mov     rcx, [rdi+20h]
0x180062f78  test    rcx, rcx
0x180062f7b  jz      short loc_180062F8F
0x180062f7d  mov     eax, [rdi]
0x180062f7f  mov     [rsp+130h+pc], eax
0x180062f83  mov     [rsp+130h+var_C0], r13d
0x180062f88  mov     [rsp+130h+ppgpos], rcx
0x180062f8d  jmp     short loc_180062FBA
0x180062f8f  lea     r8, [rsp+130h+ppgpos]; ppgpos
0x180062f94  mov     rcx, rdi; pstro
0x180062f97  lea     rdx, [rsp+130h+pc]; pc
0x180062f9c  call    cs:__imp_STROBJ_bEnum
0x180062fa3  nop     dword ptr [rax+rax+00h]
0x180062fa8  mov     [rsp+130h+var_C0], eax
0x180062fac  cmp     eax, 0FFFFFFFFh
0x180062faf  jz      loc_1800631A5
0x180062fb5  mov     rcx, [rsp+130h+ppgpos]
0x180062fba  mov     r12d, r13d
0x180062fbd  cmp     r12d, [rsp+130h+pc]
0x180062fc2  jnb     loc_180063198
0x180062fc8  mov     edx, 1; iMode
0x180062fcd  lea     rax, [rbp+3Fh+var_A8]
0x180062fd1  mov     r9, rcx; phg
0x180062fd4  mov     [rsp+130h+ppvGlyph], rax; ppvGlyph
0x180062fd9  mov     r8d, edx; cGlyph
0x180062fdc  mov     rcx, rsi; pfo
0x180062fdf  call    cs:__imp_FONTOBJ_cGetGlyphs
0x180062fe6  nop     dword ptr [rax+rax+00h]
0x180062feb  test    eax, eax
0x180062fed  jz      loc_180063195
0x180062ff3  mov     rax, [rbp+3Fh+var_A8]
0x180062ff7  mov     r9d, 1; fl
0x180062ffd  mov     r8d, r9d; iFormat
0x180063000  mov     [rsp+130h+ppvGlyph], 0; pvBits
0x180063009  mov     rsi, [rax]
0x18006300c  mov     r13, [rsi+8]
0x180063010  mov     edx, r13d
0x180063013  mov     [rbp+3Fh+var_A0], r13
0x180063017  add     edx, 1Fh; lWidth
0x18006301a  mov     rcx, r13; sizl
0x18006301d  call    cs:__imp_EngCreateBitmap
0x180063024  nop     dword ptr [rax+rax+00h]
0x180063029  mov     [rbp+3Fh+var_98], rax
0x18006302d  test    rax, rax
0x180063030  jz      loc_18006318E
0x180063036  mov     rcx, rax; hsurf
0x180063039  call    cs:__imp_EngLockSurface
0x180063040  nop     dword ptr [rax+rax+00h]
0x180063045  mov     [rbp+3Fh+var_68], rax
0x180063049  mov     r11, rax
0x18006304c  test    rax, rax
0x18006304f  jz      loc_180063183
0x180063055  mov     rcx, [rax+30h]
0x180063059  lea     r9, [rsi+10h]
0x18006305d  lea     eax, [r13+7]
0x180063061  mov     r8d, 8
0x180063067  cdq
0x180063068  xor     r13d, r13d
0x18006306b  idiv    r8d
0x18006306e  mov     r8d, r13d
0x180063071  mov     r10d, eax
0x180063074  add     eax, 3
0x180063077  and     eax, 0FFFFFFFCh
0x18006307a  sub     eax, r10d
0x18006307d  cmp     dword ptr [rbp+3Fh+var_A0+4], r13d
0x180063081  jle     short loc_1800630AE
0x180063083  movsxd  r13, eax
0x180063086  xor     edx, edx
0x180063088  test    r10d, r10d
0x18006308b  jle     short loc_18006309F
0x18006308d  mov     al, [r9]
0x180063090  inc     edx
0x180063092  mov     [rcx], al
0x180063094  inc     r9
0x180063097  inc     rcx
0x18006309a  cmp     edx, r10d
0x18006309d  jl      short loc_18006308D
0x18006309f  add     rcx, r13
0x1800630a2  inc     r8d
0x1800630a5  cmp     r8d, dword ptr [rbp+3Fh+var_A0+4]
0x1800630a9  jl      short loc_180063086
0x1800630ab  xor     r13d, r13d
0x1800630ae  mov     ecx, [rsi+8]
0x1800630b1  mov     rdx, [rsp+130h+ppgpos]
0x1800630b6  mov     r8d, [rdx+10h]
0x1800630ba  add     r8d, [rsi]
0x1800630bd  mov     edx, [rdx+14h]
0x1800630c0  add     ecx, r8d
0x1800630c3  add     edx, [rsi+4]
0x1800630c6  mov     [rbp+3Fh+var_90.right], ecx
0x1800630c9  mov     ecx, [rsi+0Ch]
0x1800630cc  mov     rsi, [rbp+3Fh+var_80]
0x1800630d0  add     ecx, edx
0x1800630d2  mov     [rbp+3Fh+var_90.left], r8d
0x1800630d6  mov     [rbp+3Fh+var_90.top], edx
0x1800630d9  mov     [rbp+3Fh+var_90.bottom], ecx
0x1800630dc  cmp     byte ptr [rsi+14h], 1
0x1800630e0  mov     qword ptr [rbp+3Fh+var_B8.x], 0
0x1800630e8  jnz     short loc_180063104
0x1800630ea  mov     eax, [rsi+8]
0x1800630ed  cmp     edx, eax
0x1800630ef  jge     short loc_1800630F6
0x1800630f1  sub     eax, edx
0x1800630f3  mov     [rbp+3Fh+var_B8.y], eax
0x1800630f6  mov     eax, [rsi+4]
0x1800630f9  cmp     r8d, eax
0x1800630fc  jge     short loc_180063104
0x1800630fe  sub     eax, r8d
0x180063101  mov     [rbp+3Fh+var_B8.x], eax
0x180063104  lea     rdx, [rsi+4]; struct _RECTL *
0x180063108  lea     r8, [rbp+3Fh+var_60]; struct _RECTL *
0x18006310c  lea     rcx, [rbp+3Fh+var_90]; struct _RECTL *
0x180063110  call    ?BRectanglesIntersect@@YAHPEAU_RECTL@@00@Z; BRectanglesIntersect(_RECTL *,_RECTL *,_RECTL *)
0x180063115  test    eax, eax
0x180063117  jz      short loc_18006315C
0x180063119  mov     rax, [rbp+3Fh+var_78]
0x18006311d  xor     r9d, r9d
0x180063120  mov     rcx, [rbp+3Fh+var_70]; struct _SURFOBJ *
0x180063124  xor     r8d, r8d; struct _SURFOBJ *
0x180063127  mov     [rsp+130h+var_E0], r15d; ROP4
0x18006312c  mov     rdx, r11; struct _SURFOBJ *
0x18006312f  mov     [rsp+130h+var_E8], r13; __int64
0x180063134  mov     [rsp+130h+var_F0], rax; struct _BRUSHOBJ *
0x180063139  lea     rax, [rbp+3Fh+var_B8]
0x18006313d  mov     [rsp+130h+var_F8], r13; struct _POINTL *
0x180063142  mov     [rsp+130h+var_100], rax; POINTL *
0x180063147  lea     rax, [rbp+3Fh+var_60]
0x18006314b  mov     [rsp+130h+var_108], rax; RECTL *
0x180063150  mov     [rsp+130h+ppvGlyph], r13; struct _XLATEOBJ *
0x180063155  call    HPGLBitBlt
0x18006315a  mov     ebx, eax
0x18006315c  lea     rdx, [rbp+3Fh+var_98]; HBITMAP *
0x180063160  lea     rcx, [rbp+3Fh+var_68]; struct _SURFOBJ **
0x180063164  call    ?DELETE_SURFOBJ@@YAXPEAPEAU_SURFOBJ@@PEAPEAUHBITMAP__@@@Z; DELETE_SURFOBJ(_SURFOBJ * *,HBITMAP__ * *)
0x180063169  mov     rcx, [rsp+130h+ppgpos]
0x18006316e  mov     rsi, [rbp+3Fh+var_B0]
0x180063172  add     rcx, 18h
0x180063176  mov     [rsp+130h+ppgpos], rcx
0x18006317b  inc     r12d
0x18006317e  jmp     loc_180062FBD
0x180063183  lea     rdx, [rbp+3Fh+var_98]; HBITMAP *
0x180063187  xor     ecx, ecx; struct _SURFOBJ **
0x180063189  call    ?DELETE_SURFOBJ@@YAXPEAPEAU_SURFOBJ@@PEAPEAUHBITMAP__@@@Z; DELETE_SURFOBJ(_SURFOBJ * *,HBITMAP__ * *)
0x18006318e  mov     rsi, [rbp+3Fh+var_B0]
0x180063192  xor     r13d, r13d
0x180063195  mov     ebx, r13d
0x180063198  cmp     [rsp+130h+var_C0], r13d
0x18006319d  jnz     loc_180062F74
0x1800631a3  jmp     short loc_1800631A8
0x1800631a5  mov     ebx, r13d
0x1800631a8  mov     qword ptr [r14+0CCh], 0
0x1800631b3  mov     eax, ebx
0x1800631b5  mov     rcx, [rbp+3Fh+var_50]
0x1800631b9  xor     rcx, rsp; StackCookie
0x1800631bc  call    __security_check_cookie
0x1800631c1  add     rsp, 0F8h
0x1800631c8  pop     r15
0x1800631ca  pop     r14
0x1800631cc  pop     r13
0x1800631ce  pop     r12
0x1800631d0  pop     rdi
0x1800631d1  pop     rsi
0x1800631d2  pop     rbx
0x1800631d3  pop     rbp
0x1800631d4  retn
```
