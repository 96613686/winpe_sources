# ClipBitmapWithComplexClip(_DEVOBJ *,_SURFOBJ *,_BRUSHOBJ *,_POINTL *,tagSIZE *,_POINTL *,tagSIZE *,_CLIPOBJ *,_XLATEOBJ *,_POINTL *)

- ea: `0x180064ae4`
- end: `0x180064ea1`
- name: `?ClipBitmapWithComplexClip@@YAHPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_BRUSHOBJ@@PEAU_POINTL@@PEAUtagSIZE@@34PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@3@Z`
- size: `957`
- prototype: `__int64 __fastcall(struct _DEVOBJ *, struct _SURFOBJ *, struct _BRUSHOBJ *, struct _POINTL *, struct tagSIZE *, struct _POINTL *, struct tagSIZE *, struct _CLIPOBJ *pco, struct _XLATEOBJ *, struct _POINTL *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800650d8`

## callees

- `0x180039f24`
- `0x180049d00`
- `0x180064a78`
- `0x180064ae4`
- `0x180066bc0`
- `0x180066fb4`
- `0x180067780`
- `0x180068000`
- `0x180068078`
- `0x1800686dc`
- `0x18006b184`
- `0x18006b780`
- `0x18006b9b4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180064e72`
- `KERNEL32!SetLastError` at `0x180064e72`
- `GDI32!CLIPOBJ_bEnum` at `0x180064d69`
- `GDI32!CLIPOBJ_bEnum` at `0x180064d69`
- `GDI32!CLIPOBJ_cEnumStart` at `0x180064d3d`
- `GDI32!CLIPOBJ_cEnumStart` at `0x180064d3d`
- `GDI32!PATHOBJ_vGetBounds` at `0x180064cbd`
- `GDI32!PATHOBJ_vGetBounds` at `0x180064cbd`
- `GDI32!CLIPOBJ_ppoGetPath` at `0x180064c92`
- `GDI32!CLIPOBJ_ppoGetPath` at `0x180064c92`
- `GDI32!EngDeletePath` at `0x180064dcf`
- `GDI32!EngDeletePath` at `0x180064dcf`

## pseudocode

```c
__int64 __fastcall ClipBitmapWithComplexClip(
        struct _DEVOBJ *a1,
        struct _SURFOBJ *a2,
        struct _BRUSHOBJ *a3,
        struct _POINTL *a4,
        struct tagSIZE *a5,
        struct _POINTL *a6,
        struct tagSIZE *a7,
        struct _CLIPOBJ *pco,
        struct _XLATEOBJ *a9,
        struct _POINTL *a10)
{
  struct _POINTL *v11; // rbx
  struct _CLIPOBJ *v12; // r14
  int v13; // eax
  FIX *v14; // r9
  LONG cx; // ecx
  FIX v16; // r13d
  __int64 v17; // rsi
  LONG v18; // eax
  unsigned int v19; // ebx
  PATHOBJ *Path; // rax
  PATHOBJ *v21; // rsi
  int v22; // r13d
  ULONG v23; // esi
  ULONG v24; // r11d
  FIX v26; // [rsp+50h] [rbp-B0h]
  struct _RECTL v27; // [rsp+58h] [rbp-A8h] BYREF
  PATHOBJ *v28; // [rsp+68h] [rbp-98h]
  struct _POINTL *v29; // [rsp+70h] [rbp-90h]
  XLATEOBJ *v30; // [rsp+78h] [rbp-88h]
  struct _POINTL *v31; // [rsp+80h] [rbp-80h]
  struct _BRUSHOBJ *v32; // [rsp+88h] [rbp-78h]
  struct _SURFOBJ *v33; // [rsp+90h] [rbp-70h]
  struct _POINTL *v34; // [rsp+98h] [rbp-68h]
  _RECTFX prectfx; // [rsp+A0h] [rbp-60h] BYREF
  ULONG pul[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v37; // [rsp+C0h] [rbp-40h]
  _OWORD v38[3]; // [rsp+C8h] [rbp-38h] BYREF

  v11 = a4;
  v12 = pco;
  v30 = a9;
  v29 = a10;
  v34 = a4;
  v32 = a3;
  v33 = a2;
  v31 = a6;
  if ( a1 && a5 && a7 && a4 && a6 )
  {
    LOBYTE(v13) = BIsComplexClipPath(pco);
    if ( v13 )
    {
      cx = a5->cx;
      if ( a7->cx == a5->cx && a7->cy == a5->cy )
        return (unsigned int)BGenerateBitmapPCL(a1, v33, v32, v11, a5, v31, a7, v12, v30, v29);
      v16 = v14[1];
      v17 = *((_QWORD *)a1 + 1);
      v26 = *v14;
      v27.left = v26;
      v27.right = cx + v26;
      v18 = v16 + a5->cy;
      v27.top = v16;
      v27.bottom = v18;
      memset(v38, 0, 44);
      BChangeAndTrackObjectType((__int64)a1, 2);
      PCL_SelectTransparency((__int64)a1, 1, 1, 0);
      SelectRop3(a1, 102);
      if ( (unsigned int)BGenerateBitmapPCL(a1, v33, v32, v11, a5, v31, a7, 0, v30, v29) )
      {
        v19 = 1;
        BChangeAndTrackObjectType((__int64)a1, 1);
        SelectRop3(a1, 0);
        CreateSolidHPGLPenBrush(a1, (struct _HPGLMARKER *)v38, 0);
        DWORD1(v38[0]) = 0;
        *(_QWORD *)(v17 + 376) = 0;
        Path = CLIPOBJ_ppoGetPath(pco);
        v28 = Path;
        v21 = Path;
        if ( Path )
        {
          prectfx = 0;
          PATHOBJ_vGetBounds(Path, &prectfx);
          HPGL_ResetClippingRegion(a1);
          if ( prectfx.xLeft >> 4 < v26
            || prectfx.xRight >> 4 > v27.right
            || prectfx.yTop >> 4 < v16
            || prectfx.yBottom >> 4 > v27.bottom )
          {
            v37 = 0;
            prectfx = 0;
            *(_OWORD *)pul = 0;
            if ( CLIPOBJ_cEnumStart(pco, 1, 0, 0, 0x100u) )
            {
              DrawWithPen(a1, (struct _HPGLMARKER *)v38);
              while ( 1 )
              {
                v22 = CLIPOBJ_bEnum(pco, 0x14u, pul);
                if ( v22 == -1 )
                  break;
                v23 = 0;
                if ( pul[0] )
                {
                  do
                  {
                    if ( (unsigned int)BRectanglesIntersect(
                                         &v27,
                                         (struct _RECTL *)&pul[4 * v23 + 1],
                                         (struct _RECTL *)&prectfx) )
                    {
                      HPGL_DrawRectangle(a1, (struct _RECTL *)&prectfx);
                      v24 = pul[0];
                    }
                    ++v23;
                  }
                  while ( v23 < v24 );
                }
                if ( !v22 )
                  goto LABEL_24;
              }
              v19 = 0;
LABEL_24:
              v21 = v28;
            }
            else
            {
              v19 = 0;
            }
          }
          else
          {
            MarkPath(a1, v21, 0, (struct _HPGLMARKER *)v38);
          }
          EngDeletePath(v21);
          if ( !v19 )
            return v19;
          BChangeAndTrackObjectType((__int64)a1, 2);
          PCL_SelectTransparency((__int64)a1, 1, 1, 0);
          SelectRop3(a1, 102);
          v11 = v34;
          v12 = 0;
          return (unsigned int)BGenerateBitmapPCL(a1, v33, v32, v11, a5, v31, a7, v12, v30, v29);
        }
      }
    }
    return 0;
  }
  SetLastError(0xDu);
  return 0;
}

```

## disassembly

```asm
0x180064ae4  push    rbp
0x180064ae6  push    rbx
0x180064ae7  push    rsi
0x180064ae8  push    rdi
0x180064ae9  push    r12
0x180064aeb  push    r13
0x180064aed  push    r14
0x180064aef  push    r15
0x180064af1  lea     rbp, [rsp-8]
0x180064af6  sub     rsp, 108h
0x180064afd  mov     rax, cs:__security_cookie
0x180064b04  xor     rax, rsp
0x180064b07  mov     [rbp+40h+var_48], rax
0x180064b0b  mov     rax, [rbp+40h+arg_28]
0x180064b0f  mov     rdi, rcx
0x180064b12  mov     rcx, [rbp+40h+arg_40]
0x180064b19  mov     rbx, r9
0x180064b1c  mov     r12, [rbp+40h+arg_30]
0x180064b23  mov     r15, [rbp+40h+arg_20]
0x180064b27  mov     r14, [rbp+40h+pco]
0x180064b2e  mov     [rsp+140h+var_C8], rcx
0x180064b33  mov     rcx, [rbp+40h+arg_48]
0x180064b3a  mov     [rsp+140h+var_D0], rcx
0x180064b3f  mov     [rbp+40h+var_A8], rbx
0x180064b43  mov     [rbp+40h+var_B8], r8
0x180064b47  mov     [rbp+40h+var_B0], rdx
0x180064b4b  mov     [rbp+40h+var_C0], rax
0x180064b4f  test    rdi, rdi
0x180064b52  jz      loc_180064E6D
0x180064b58  test    r15, r15
0x180064b5b  jz      loc_180064E6D
0x180064b61  test    r12, r12
0x180064b64  jz      loc_180064E6D
0x180064b6a  test    rbx, rbx
0x180064b6d  jz      loc_180064E6D
0x180064b73  test    rax, rax
0x180064b76  jz      loc_180064E6D
0x180064b7c  mov     rcx, r14; struct _CLIPOBJ *
0x180064b7f  call    ?BIsComplexClipPath@@YAHPEAU_CLIPOBJ@@@Z; BIsComplexClipPath(_CLIPOBJ *)
0x180064b84  test    eax, eax
0x180064b86  jz      loc_180064E67
0x180064b8c  mov     ecx, [r15]
0x180064b8f  cmp     [r12], ecx
0x180064b93  jnz     short loc_180064BA4
0x180064b95  mov     eax, [r15+4]
0x180064b99  cmp     [r12+4], eax
0x180064b9e  jz      loc_180064E16
0x180064ba4  mov     eax, [r9]
0x180064ba7  xorps   xmm0, xmm0
0x180064baa  mov     r13d, [r9+4]
0x180064bae  mov     edx, 2
0x180064bb3  mov     rsi, [rdi+8]
0x180064bb7  mov     [rsp+140h+var_F0], eax
0x180064bbb  mov     [rsp+140h+var_E8.left], eax
0x180064bbf  add     eax, ecx
0x180064bc1  mov     [rsp+140h+var_E8.right], eax
0x180064bc5  mov     rcx, rdi
0x180064bc8  mov     eax, [r15+4]
0x180064bcc  add     eax, r13d
0x180064bcf  mov     [rsp+140h+var_E8.top], r13d
0x180064bd4  movups  xmmword ptr [rbp+40h+var_68], xmm0
0x180064bd8  mov     [rsp+140h+var_E8.bottom], eax
0x180064bdc  movups  [rbp+40h+var_78], xmm0
0x180064be0  movups  xmmword ptr [rbp+40h+var_68+0Ch], xmm0
0x180064be4  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180064be9  xor     r9d, r9d
0x180064bec  mov     rcx, rdi
0x180064bef  lea     eax, [r9+1]
0x180064bf3  mov     r8d, eax
0x180064bf6  mov     edx, eax
0x180064bf8  call    ?PCL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@1E@Z; PCL_SelectTransparency(_DEVOBJ *,ETransparency,ETransparency,uchar)
0x180064bfd  mov     edx, 66h ; 'f'; unsigned int
0x180064c02  mov     rcx, rdi; struct _DEVOBJ *
0x180064c05  call    ?SelectRop3@@YAHPEAU_DEVOBJ@@K@Z; SelectRop3(_DEVOBJ *,ulong)
0x180064c0a  mov     rax, [rsp+140h+var_D0]
0x180064c0f  mov     r9, rbx; struct _POINTL *
0x180064c12  mov     r8, [rbp+40h+var_B8]; struct _BRUSHOBJ *
0x180064c16  mov     rcx, rdi; struct _DEVOBJ *
0x180064c19  mov     rdx, [rbp+40h+var_B0]; struct _SURFOBJ *
0x180064c1d  mov     [rsp+140h+var_F8], rax; struct _POINTL *
0x180064c22  mov     rax, [rsp+140h+var_C8]
0x180064c27  mov     [rsp+140h+var_100], rax; XLATEOBJ *
0x180064c2c  mov     rax, [rbp+40h+var_C0]
0x180064c30  mov     [rsp+140h+var_108], 0; struct _CLIPOBJ *
0x180064c39  mov     [rsp+140h+var_110], r12; struct tagSIZE *
0x180064c3e  mov     [rsp+140h+var_118], rax; struct _POINTL *
0x180064c43  mov     qword ptr [rsp+140h+cLimit], r15; struct tagSIZE *
0x180064c48  call    ?BGenerateBitmapPCL@@YAHPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_BRUSHOBJ@@PEAU_POINTL@@PEAUtagSIZE@@34PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@3@Z; BGenerateBitmapPCL(_DEVOBJ *,_SURFOBJ *,_BRUSHOBJ *,_POINTL *,tagSIZE *,_POINTL *,tagSIZE *,_CLIPOBJ *,_XLATEOBJ *,_POINTL *)
0x180064c4d  test    eax, eax
0x180064c4f  jz      loc_180064E67
0x180064c55  mov     ebx, 1
0x180064c5a  mov     rcx, rdi
0x180064c5d  mov     edx, ebx
0x180064c5f  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180064c64  xor     edx, edx; unsigned int
0x180064c66  mov     rcx, rdi; struct _DEVOBJ *
0x180064c69  call    ?SelectRop3@@YAHPEAU_DEVOBJ@@K@Z; SelectRop3(_DEVOBJ *,ulong)
0x180064c6e  xor     r8d, r8d; unsigned int
0x180064c71  lea     rdx, [rbp+40h+var_78]; struct _HPGLMARKER *
0x180064c75  mov     rcx, rdi; struct _DEVOBJ *
0x180064c78  call    ?CreateSolidHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@K@Z; CreateSolidHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *,ulong)
0x180064c7d  mov     dword ptr [rbp+40h+var_78+4], 0
0x180064c84  mov     rcx, r14; pco
0x180064c87  mov     qword ptr [rsi+178h], 0
0x180064c92  call    cs:__imp_CLIPOBJ_ppoGetPath
0x180064c99  nop     dword ptr [rax+rax+00h]
0x180064c9e  mov     [rsp+140h+var_D8], rax
0x180064ca3  mov     rsi, rax
0x180064ca6  test    rax, rax
0x180064ca9  jz      loc_180064E67
0x180064caf  xorps   xmm0, xmm0
0x180064cb2  lea     rdx, [rbp+40h+prectfx]; prectfx
0x180064cb6  mov     rcx, rax; ppo
0x180064cb9  movups  xmmword ptr [rbp+40h+prectfx.xLeft], xmm0
0x180064cbd  call    cs:__imp_PATHOBJ_vGetBounds
0x180064cc4  nop     dword ptr [rax+rax+00h]
0x180064cc9  mov     rcx, rdi; struct _DEVOBJ *
0x180064ccc  call    ?HPGL_ResetClippingRegion@@YAHPEAU_DEVOBJ@@I@Z; HPGL_ResetClippingRegion(_DEVOBJ *,uint)
0x180064cd1  mov     ecx, [rbp+40h+prectfx.xLeft]
0x180064cd4  sar     ecx, 4
0x180064cd7  cmp     ecx, [rsp+140h+var_F0]
0x180064cdb  jl      short loc_180064D17
0x180064cdd  mov     eax, [rbp+40h+prectfx.xRight]
0x180064ce0  sar     eax, 4
0x180064ce3  cmp     eax, [rsp+140h+var_E8.right]
0x180064ce7  jg      short loc_180064D17
0x180064ce9  mov     eax, [rbp+40h+prectfx.yTop]
0x180064cec  sar     eax, 4
0x180064cef  cmp     eax, r13d
0x180064cf2  jl      short loc_180064D17
0x180064cf4  mov     eax, [rbp+40h+prectfx.yBottom]
0x180064cf7  sar     eax, 4
0x180064cfa  cmp     eax, [rsp+140h+var_E8.bottom]
0x180064cfe  jg      short loc_180064D17
0x180064d00  lea     r9, [rbp+40h+var_78]; struct _HPGLMARKER *
0x180064d04  xor     r8d, r8d; struct _HPGLMARKER *
0x180064d07  mov     rdx, rsi; struct _PATHOBJ *
0x180064d0a  mov     rcx, rdi; struct _DEVOBJ *
0x180064d0d  call    ?MarkPath@@YAHPEAU_DEVOBJ@@PEAU_PATHOBJ@@PEAU_HPGLMARKER@@2@Z; MarkPath(_DEVOBJ *,_PATHOBJ *,_HPGLMARKER *,_HPGLMARKER *)
0x180064d12  jmp     loc_180064DCC
0x180064d17  xorps   xmm0, xmm0
0x180064d1a  mov     [rsp+140h+cLimit], 100h; cLimit
0x180064d22  xorps   xmm1, xmm1
0x180064d25  xor     eax, eax
0x180064d27  xor     r9d, r9d; iDirection
0x180064d2a  mov     [rbp+40h+var_80], eax
0x180064d2d  xor     r8d, r8d; iType
0x180064d30  mov     edx, ebx; bAll
0x180064d32  mov     rcx, r14; pco
0x180064d35  movups  xmmword ptr [rbp+40h+prectfx.xLeft], xmm0
0x180064d39  movups  xmmword ptr [rbp+40h+pul], xmm1
0x180064d3d  call    cs:__imp_CLIPOBJ_cEnumStart
0x180064d44  nop     dword ptr [rax+rax+00h]
0x180064d49  test    eax, eax
0x180064d4b  jz      loc_180064E60
0x180064d51  lea     rdx, [rbp+40h+var_78]; struct _HPGLMARKER *
0x180064d55  mov     rcx, rdi; struct _DEVOBJ *
0x180064d58  call    ?DrawWithPen@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@@Z; DrawWithPen(_DEVOBJ *,_HPGLMARKER *)
0x180064d5d  lea     r8, [rbp+40h+pul]; pul
0x180064d61  mov     edx, 14h; cj
0x180064d66  mov     rcx, r14; pco
0x180064d69  call    cs:__imp_CLIPOBJ_bEnum
0x180064d70  nop     dword ptr [rax+rax+00h]
0x180064d75  mov     r13d, eax
0x180064d78  cmp     eax, 0FFFFFFFFh
0x180064d7b  jz      loc_180064E59
0x180064d81  mov     r11d, [rbp+40h+pul]
0x180064d85  xor     esi, esi
0x180064d87  test    r11d, r11d
0x180064d8a  jz      short loc_180064DC2
0x180064d8c  mov     ecx, esi
0x180064d8e  lea     rdx, [rbp+40h+pul+4]
0x180064d92  shl     rcx, 4
0x180064d96  lea     r8, [rbp+40h+prectfx]; struct _RECTL *
0x180064d9a  add     rdx, rcx; struct _RECTL *
0x180064d9d  lea     rcx, [rsp+140h+var_E8]; struct _RECTL *
0x180064da2  call    ?BRectanglesIntersect@@YAHPEAU_RECTL@@00@Z; BRectanglesIntersect(_RECTL *,_RECTL *,_RECTL *)
0x180064da7  test    eax, eax
0x180064da9  jz      short loc_180064DBB
0x180064dab  lea     rdx, [rbp+40h+prectfx]; struct _RECTL *
0x180064daf  mov     rcx, rdi; struct _DEVOBJ *
0x180064db2  call    ?HPGL_DrawRectangle@@YAHPEAU_DEVOBJ@@PEAU_RECTL@@@Z; HPGL_DrawRectangle(_DEVOBJ *,_RECTL *)
0x180064db7  mov     r11d, [rbp+40h+pul]
0x180064dbb  inc     esi
0x180064dbd  cmp     esi, r11d
0x180064dc0  jb      short loc_180064D8C
0x180064dc2  test    r13d, r13d
0x180064dc5  jnz     short loc_180064D5D
0x180064dc7  mov     rsi, [rsp+140h+var_D8]
0x180064dcc  mov     rcx, rsi; ppo
0x180064dcf  call    cs:__imp_EngDeletePath
0x180064dd6  nop     dword ptr [rax+rax+00h]
0x180064ddb  test    ebx, ebx
0x180064ddd  jz      loc_180064E69
0x180064de3  mov     edx, 2
0x180064de8  mov     rcx, rdi
0x180064deb  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180064df0  xor     r9d, r9d
0x180064df3  mov     rcx, rdi
0x180064df6  lea     edx, [r9+1]
0x180064dfa  mov     r8d, edx
0x180064dfd  call    ?PCL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@1E@Z; PCL_SelectTransparency(_DEVOBJ *,ETransparency,ETransparency,uchar)
0x180064e02  mov     edx, 66h ; 'f'; unsigned int
0x180064e07  mov     rcx, rdi; struct _DEVOBJ *
0x180064e0a  call    ?SelectRop3@@YAHPEAU_DEVOBJ@@K@Z; SelectRop3(_DEVOBJ *,ulong)
0x180064e0f  mov     rbx, [rbp+40h+var_A8]
0x180064e13  xor     r14d, r14d
0x180064e16  mov     rax, [rsp+140h+var_D0]
0x180064e1b  mov     r9, rbx; struct _POINTL *
0x180064e1e  mov     r8, [rbp+40h+var_B8]; struct _BRUSHOBJ *
0x180064e22  mov     rcx, rdi; struct _DEVOBJ *
0x180064e25  mov     rdx, [rbp+40h+var_B0]; struct _SURFOBJ *
0x180064e29  mov     [rsp+140h+var_F8], rax; struct _POINTL *
0x180064e2e  mov     rax, [rsp+140h+var_C8]
0x180064e33  mov     [rsp+140h+var_100], rax; XLATEOBJ *
0x180064e38  mov     rax, [rbp+40h+var_C0]
0x180064e3c  mov     [rsp+140h+var_108], r14; struct _CLIPOBJ *
0x180064e41  mov     [rsp+140h+var_110], r12; struct tagSIZE *
0x180064e46  mov     [rsp+140h+var_118], rax; struct _POINTL *
0x180064e4b  mov     qword ptr [rsp+140h+cLimit], r15; struct tagSIZE *
0x180064e50  call    ?BGenerateBitmapPCL@@YAHPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_BRUSHOBJ@@PEAU_POINTL@@PEAUtagSIZE@@34PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@3@Z; BGenerateBitmapPCL(_DEVOBJ *,_SURFOBJ *,_BRUSHOBJ *,_POINTL *,tagSIZE *,_POINTL *,tagSIZE *,_CLIPOBJ *,_XLATEOBJ *,_POINTL *)
0x180064e55  mov     ebx, eax
0x180064e57  jmp     short loc_180064E69
0x180064e59  xor     ebx, ebx
0x180064e5b  jmp     loc_180064DC7
0x180064e60  xor     ebx, ebx
0x180064e62  jmp     loc_180064DCC
0x180064e67  xor     ebx, ebx
0x180064e69  mov     eax, ebx
0x180064e6b  jmp     short loc_180064E80
0x180064e6d  mov     ecx, 0Dh; dwErrCode
0x180064e72  call    cs:__imp_SetLastError
0x180064e79  nop     dword ptr [rax+rax+00h]
0x180064e7e  xor     eax, eax
0x180064e80  mov     rcx, [rbp+40h+var_48]
0x180064e84  xor     rcx, rsp; StackCookie
0x180064e87  call    __security_check_cookie
0x180064e8c  add     rsp, 108h
0x180064e93  pop     r15
0x180064e95  pop     r14
0x180064e97  pop     r13
0x180064e99  pop     r12
0x180064e9b  pop     rdi
0x180064e9c  pop     rsi
0x180064e9d  pop     rbx
0x180064e9e  pop     rbp
0x180064e9f  retn
```
