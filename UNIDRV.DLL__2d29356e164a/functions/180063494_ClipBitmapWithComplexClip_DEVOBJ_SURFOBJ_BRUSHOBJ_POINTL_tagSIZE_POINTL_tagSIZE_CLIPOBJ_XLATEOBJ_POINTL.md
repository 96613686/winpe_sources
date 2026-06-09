# ClipBitmapWithComplexClip(_DEVOBJ *,_SURFOBJ *,_BRUSHOBJ *,_POINTL *,tagSIZE *,_POINTL *,tagSIZE *,_CLIPOBJ *,_XLATEOBJ *,_POINTL *)

- ea: `0x180063494`
- end: `0x18006382c`
- name: `?ClipBitmapWithComplexClip@@YAHPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_BRUSHOBJ@@PEAU_POINTL@@PEAUtagSIZE@@34PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@3@Z`
- size: `920`
- prototype: `__int64 __usercall@<rax>(struct _DEVOBJ *@<rcx>, struct _SURFOBJ *@<rdx>, struct _BRUSHOBJ *@<r8>, struct _POINTL *@<r9>, struct tagSIZE *, struct _POINTL *, struct tagSIZE *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _POINTL *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180063a48`

## callees

- `0x18003949c`
- `0x1800487e0`
- `0x18006342c`
- `0x180063494`
- `0x18006548c`
- `0x180065874`
- `0x180065fdc`
- `0x180066820`
- `0x180066890`
- `0x180066edc`
- `0x180069890`
- `0x180069e7c`
- `0x18006a0a8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180063804`
- `KERNEL32!SetLastError` at `0x180063804`
- `GDI32!CLIPOBJ_bEnum` at `0x180063707`
- `GDI32!CLIPOBJ_bEnum` at `0x180063707`
- `GDI32!CLIPOBJ_cEnumStart` at `0x1800636e1`
- `GDI32!CLIPOBJ_cEnumStart` at `0x1800636e1`
- `GDI32!PATHOBJ_vGetBounds` at `0x180063667`
- `GDI32!PATHOBJ_vGetBounds` at `0x180063667`
- `GDI32!CLIPOBJ_ppoGetPath` at `0x180063642`
- `GDI32!CLIPOBJ_ppoGetPath` at `0x180063642`
- `GDI32!EngDeletePath` at `0x180063767`
- `GDI32!EngDeletePath` at `0x180063767`

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
  FIX *v13; // r9
  LONG cx; // ecx
  FIX v15; // r13d
  __int64 v16; // rsi
  LONG v17; // eax
  unsigned int v18; // ebx
  PATHOBJ *Path; // rax
  PATHOBJ *v20; // rsi
  unsigned int v21; // edx
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
    if ( (unsigned int)BIsComplexClipPath(pco) )
    {
      cx = a5->cx;
      if ( a7->cx == a5->cx && a7->cy == a5->cy )
        return (unsigned int)BGenerateBitmapPCL(a1, v33, v32, v11, a5, v31, a7, v12, v30, v29);
      v15 = v13[1];
      v16 = *((_QWORD *)a1 + 1);
      v26 = *v13;
      v27.left = v26;
      v27.right = cx + v26;
      v17 = v15 + a5->cy;
      v27.top = v15;
      v27.bottom = v17;
      memset(v38, 0, 44);
      BChangeAndTrackObjectType(a1, 2);
      PCL_SelectTransparency(a1, 1, 1);
      SelectRop3(a1, 0x66u);
      if ( (unsigned int)BGenerateBitmapPCL(a1, v33, v32, v11, a5, v31, a7, 0, v30, v29) )
      {
        v18 = 1;
        BChangeAndTrackObjectType(a1, 1);
        SelectRop3(a1, 0);
        CreateSolidHPGLPenBrush(a1, (struct _HPGLMARKER *)v38, 0);
        DWORD1(v38[0]) = 0;
        *(_QWORD *)(v16 + 376) = 0;
        Path = CLIPOBJ_ppoGetPath(pco);
        v28 = Path;
        v20 = Path;
        if ( Path )
        {
          prectfx = 0;
          PATHOBJ_vGetBounds(Path, &prectfx);
          HPGL_ResetClippingRegion(a1, v21);
          if ( prectfx.xLeft >> 4 < v26
            || prectfx.xRight >> 4 > v27.right
            || prectfx.yTop >> 4 < v15
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
              v18 = 0;
LABEL_24:
              v20 = v28;
            }
            else
            {
              v18 = 0;
            }
          }
          else
          {
            MarkPath(a1, v20, 0, (struct _HPGLMARKER *)v38);
          }
          EngDeletePath(v20);
          if ( !v18 )
            return v18;
          BChangeAndTrackObjectType(a1, 2);
          PCL_SelectTransparency(a1, 1, 1);
          SelectRop3(a1, 0x66u);
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
0x180063494  push    rbp
0x180063496  push    rbx
0x180063497  push    rsi
0x180063498  push    rdi
0x180063499  push    r12
0x18006349b  push    r13
0x18006349d  push    r14
0x18006349f  push    r15
0x1800634a1  lea     rbp, [rsp-8]
0x1800634a6  sub     rsp, 108h
0x1800634ad  mov     rax, cs:__security_cookie
0x1800634b4  xor     rax, rsp
0x1800634b7  mov     [rbp+40h+var_48], rax
0x1800634bb  mov     rax, [rbp+40h+arg_28]
0x1800634bf  mov     rdi, rcx
0x1800634c2  mov     rcx, [rbp+40h+arg_40]
0x1800634c9  mov     rbx, r9
0x1800634cc  mov     r12, [rbp+40h+arg_30]
0x1800634d3  mov     r15, [rbp+40h+arg_20]
0x1800634d7  mov     r14, [rbp+40h+pco]
0x1800634de  mov     [rsp+140h+var_C8], rcx
0x1800634e3  mov     rcx, [rbp+40h+arg_48]
0x1800634ea  mov     [rsp+140h+var_D0], rcx
0x1800634ef  mov     [rbp+40h+var_A8], rbx
0x1800634f3  mov     [rbp+40h+var_B8], r8
0x1800634f7  mov     [rbp+40h+var_B0], rdx
0x1800634fb  mov     [rbp+40h+var_C0], rax
0x1800634ff  test    rdi, rdi
0x180063502  jz      loc_1800637FF
0x180063508  test    r15, r15
0x18006350b  jz      loc_1800637FF
0x180063511  test    r12, r12
0x180063514  jz      loc_1800637FF
0x18006351a  test    rbx, rbx
0x18006351d  jz      loc_1800637FF
0x180063523  test    rax, rax
0x180063526  jz      loc_1800637FF
0x18006352c  mov     rcx, r14; struct _CLIPOBJ *
0x18006352f  call    ?BIsComplexClipPath@@YAHPEAU_CLIPOBJ@@@Z; BIsComplexClipPath(_CLIPOBJ *)
0x180063534  test    eax, eax
0x180063536  jz      loc_1800637F9
0x18006353c  mov     ecx, [r15]
0x18006353f  cmp     [r12], ecx
0x180063543  jnz     short loc_180063554
0x180063545  mov     eax, [r15+4]
0x180063549  cmp     [r12+4], eax
0x18006354e  jz      loc_1800637A8
0x180063554  mov     eax, [r9]
0x180063557  xorps   xmm0, xmm0
0x18006355a  mov     r13d, [r9+4]
0x18006355e  mov     edx, 2
0x180063563  mov     rsi, [rdi+8]
0x180063567  mov     [rsp+140h+var_F0], eax
0x18006356b  mov     [rsp+140h+var_E8.left], eax
0x18006356f  add     eax, ecx
0x180063571  mov     [rsp+140h+var_E8.right], eax
0x180063575  mov     rcx, rdi
0x180063578  mov     eax, [r15+4]
0x18006357c  add     eax, r13d
0x18006357f  mov     [rsp+140h+var_E8.top], r13d
0x180063584  movups  xmmword ptr [rbp+40h+var_68], xmm0
0x180063588  mov     [rsp+140h+var_E8.bottom], eax
0x18006358c  movups  [rbp+40h+var_78], xmm0
0x180063590  movups  xmmword ptr [rbp+40h+var_68+0Ch], xmm0
0x180063594  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180063599  xor     r9d, r9d
0x18006359c  mov     rcx, rdi
0x18006359f  lea     eax, [r9+1]
0x1800635a3  mov     r8d, eax
0x1800635a6  mov     edx, eax
0x1800635a8  call    ?PCL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@1E@Z; PCL_SelectTransparency(_DEVOBJ *,ETransparency,ETransparency,uchar)
0x1800635ad  mov     edx, 66h ; 'f'; unsigned int
0x1800635b2  mov     rcx, rdi; struct _DEVOBJ *
0x1800635b5  call    ?SelectRop3@@YAHPEAU_DEVOBJ@@K@Z; SelectRop3(_DEVOBJ *,ulong)
0x1800635ba  mov     rax, [rsp+140h+var_D0]
0x1800635bf  mov     r9, rbx; struct _POINTL *
0x1800635c2  mov     r8, [rbp+40h+var_B8]; struct _BRUSHOBJ *
0x1800635c6  mov     rcx, rdi; struct _DEVOBJ *
0x1800635c9  mov     rdx, [rbp+40h+var_B0]; struct _SURFOBJ *
0x1800635cd  mov     [rsp+140h+var_F8], rax; struct _POINTL *
0x1800635d2  mov     rax, [rsp+140h+var_C8]
0x1800635d7  mov     [rsp+140h+var_100], rax; XLATEOBJ *
0x1800635dc  mov     rax, [rbp+40h+var_C0]
0x1800635e0  mov     [rsp+140h+var_108], 0; struct _CLIPOBJ *
0x1800635e9  mov     [rsp+140h+var_110], r12; struct tagSIZE *
0x1800635ee  mov     [rsp+140h+var_118], rax; struct _POINTL *
0x1800635f3  mov     qword ptr [rsp+140h+cLimit], r15; struct tagSIZE *
0x1800635f8  call    ?BGenerateBitmapPCL@@YAHPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_BRUSHOBJ@@PEAU_POINTL@@PEAUtagSIZE@@34PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@3@Z; BGenerateBitmapPCL(_DEVOBJ *,_SURFOBJ *,_BRUSHOBJ *,_POINTL *,tagSIZE *,_POINTL *,tagSIZE *,_CLIPOBJ *,_XLATEOBJ *,_POINTL *)
0x1800635fd  test    eax, eax
0x1800635ff  jz      loc_1800637F9
0x180063605  mov     ebx, 1
0x18006360a  mov     rcx, rdi
0x18006360d  mov     edx, ebx
0x18006360f  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180063614  xor     edx, edx; unsigned int
0x180063616  mov     rcx, rdi; struct _DEVOBJ *
0x180063619  call    ?SelectRop3@@YAHPEAU_DEVOBJ@@K@Z; SelectRop3(_DEVOBJ *,ulong)
0x18006361e  xor     r8d, r8d; unsigned int
0x180063621  lea     rdx, [rbp+40h+var_78]; struct _HPGLMARKER *
0x180063625  mov     rcx, rdi; struct _DEVOBJ *
0x180063628  call    ?CreateSolidHPGLPenBrush@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@K@Z; CreateSolidHPGLPenBrush(_DEVOBJ *,_HPGLMARKER *,ulong)
0x18006362d  mov     dword ptr [rbp+40h+var_78+4], 0
0x180063634  mov     rcx, r14; pco
0x180063637  mov     qword ptr [rsi+178h], 0
0x180063642  call    cs:__imp_CLIPOBJ_ppoGetPath
0x180063648  mov     [rsp+140h+var_D8], rax
0x18006364d  mov     rsi, rax
0x180063650  test    rax, rax
0x180063653  jz      loc_1800637F9
0x180063659  xorps   xmm0, xmm0
0x18006365c  lea     rdx, [rbp+40h+prectfx]; prectfx
0x180063660  mov     rcx, rax; ppo
0x180063663  movups  xmmword ptr [rbp+40h+prectfx.xLeft], xmm0
0x180063667  call    cs:__imp_PATHOBJ_vGetBounds
0x18006366d  mov     rcx, rdi; struct _DEVOBJ *
0x180063670  call    ?HPGL_ResetClippingRegion@@YAHPEAU_DEVOBJ@@I@Z; HPGL_ResetClippingRegion(_DEVOBJ *,uint)
0x180063675  mov     ecx, [rbp+40h+prectfx.xLeft]
0x180063678  sar     ecx, 4
0x18006367b  cmp     ecx, [rsp+140h+var_F0]
0x18006367f  jl      short loc_1800636BB
0x180063681  mov     eax, [rbp+40h+prectfx.xRight]
0x180063684  sar     eax, 4
0x180063687  cmp     eax, [rsp+140h+var_E8.right]
0x18006368b  jg      short loc_1800636BB
0x18006368d  mov     eax, [rbp+40h+prectfx.yTop]
0x180063690  sar     eax, 4
0x180063693  cmp     eax, r13d
0x180063696  jl      short loc_1800636BB
0x180063698  mov     eax, [rbp+40h+prectfx.yBottom]
0x18006369b  sar     eax, 4
0x18006369e  cmp     eax, [rsp+140h+var_E8.bottom]
0x1800636a2  jg      short loc_1800636BB
0x1800636a4  lea     r9, [rbp+40h+var_78]; struct _HPGLMARKER *
0x1800636a8  xor     r8d, r8d; struct _HPGLMARKER *
0x1800636ab  mov     rdx, rsi; struct _PATHOBJ *
0x1800636ae  mov     rcx, rdi; struct _DEVOBJ *
0x1800636b1  call    ?MarkPath@@YAHPEAU_DEVOBJ@@PEAU_PATHOBJ@@PEAU_HPGLMARKER@@2@Z; MarkPath(_DEVOBJ *,_PATHOBJ *,_HPGLMARKER *,_HPGLMARKER *)
0x1800636b6  jmp     loc_180063764
0x1800636bb  xorps   xmm0, xmm0
0x1800636be  mov     [rsp+140h+cLimit], 100h; cLimit
0x1800636c6  xorps   xmm1, xmm1
0x1800636c9  xor     eax, eax
0x1800636cb  xor     r9d, r9d; iDirection
0x1800636ce  mov     [rbp+40h+var_80], eax
0x1800636d1  xor     r8d, r8d; iType
0x1800636d4  mov     edx, ebx; bAll
0x1800636d6  mov     rcx, r14; pco
0x1800636d9  movups  xmmword ptr [rbp+40h+prectfx.xLeft], xmm0
0x1800636dd  movups  xmmword ptr [rbp+40h+pul], xmm1
0x1800636e1  call    cs:__imp_CLIPOBJ_cEnumStart
0x1800636e7  test    eax, eax
0x1800636e9  jz      loc_1800637F2
0x1800636ef  lea     rdx, [rbp+40h+var_78]; struct _HPGLMARKER *
0x1800636f3  mov     rcx, rdi; struct _DEVOBJ *
0x1800636f6  call    ?DrawWithPen@@YAHPEAU_DEVOBJ@@PEAU_HPGLMARKER@@@Z; DrawWithPen(_DEVOBJ *,_HPGLMARKER *)
0x1800636fb  lea     r8, [rbp+40h+pul]; pul
0x1800636ff  mov     edx, 14h; cj
0x180063704  mov     rcx, r14; pco
0x180063707  call    cs:__imp_CLIPOBJ_bEnum
0x18006370d  mov     r13d, eax
0x180063710  cmp     eax, 0FFFFFFFFh
0x180063713  jz      loc_1800637EB
0x180063719  mov     r11d, [rbp+40h+pul]
0x18006371d  xor     esi, esi
0x18006371f  test    r11d, r11d
0x180063722  jz      short loc_18006375A
0x180063724  mov     ecx, esi
0x180063726  lea     rdx, [rbp+40h+pul+4]
0x18006372a  shl     rcx, 4
0x18006372e  lea     r8, [rbp+40h+prectfx]; struct _RECTL *
0x180063732  add     rdx, rcx; struct _RECTL *
0x180063735  lea     rcx, [rsp+140h+var_E8]; struct _RECTL *
0x18006373a  call    ?BRectanglesIntersect@@YAHPEAU_RECTL@@00@Z; BRectanglesIntersect(_RECTL *,_RECTL *,_RECTL *)
0x18006373f  test    eax, eax
0x180063741  jz      short loc_180063753
0x180063743  lea     rdx, [rbp+40h+prectfx]; struct _RECTL *
0x180063747  mov     rcx, rdi; struct _DEVOBJ *
0x18006374a  call    ?HPGL_DrawRectangle@@YAHPEAU_DEVOBJ@@PEAU_RECTL@@@Z; HPGL_DrawRectangle(_DEVOBJ *,_RECTL *)
0x18006374f  mov     r11d, [rbp+40h+pul]
0x180063753  inc     esi
0x180063755  cmp     esi, r11d
0x180063758  jb      short loc_180063724
0x18006375a  test    r13d, r13d
0x18006375d  jnz     short loc_1800636FB
0x18006375f  mov     rsi, [rsp+140h+var_D8]
0x180063764  mov     rcx, rsi; ppo
0x180063767  call    cs:__imp_EngDeletePath
0x18006376d  test    ebx, ebx
0x18006376f  jz      loc_1800637FB
0x180063775  mov     edx, 2
0x18006377a  mov     rcx, rdi
0x18006377d  call    ?BChangeAndTrackObjectType@@YAHPEAU_DEVOBJ@@W4EObjectType@@@Z; BChangeAndTrackObjectType(_DEVOBJ *,EObjectType)
0x180063782  xor     r9d, r9d
0x180063785  mov     rcx, rdi
0x180063788  lea     edx, [r9+1]
0x18006378c  mov     r8d, edx
0x18006378f  call    ?PCL_SelectTransparency@@YAHPEAU_DEVOBJ@@W4ETransparency@@1E@Z; PCL_SelectTransparency(_DEVOBJ *,ETransparency,ETransparency,uchar)
0x180063794  mov     edx, 66h ; 'f'; unsigned int
0x180063799  mov     rcx, rdi; struct _DEVOBJ *
0x18006379c  call    ?SelectRop3@@YAHPEAU_DEVOBJ@@K@Z; SelectRop3(_DEVOBJ *,ulong)
0x1800637a1  mov     rbx, [rbp+40h+var_A8]
0x1800637a5  xor     r14d, r14d
0x1800637a8  mov     rax, [rsp+140h+var_D0]
0x1800637ad  mov     r9, rbx; struct _POINTL *
0x1800637b0  mov     r8, [rbp+40h+var_B8]; struct _BRUSHOBJ *
0x1800637b4  mov     rcx, rdi; struct _DEVOBJ *
0x1800637b7  mov     rdx, [rbp+40h+var_B0]; struct _SURFOBJ *
0x1800637bb  mov     [rsp+140h+var_F8], rax; struct _POINTL *
0x1800637c0  mov     rax, [rsp+140h+var_C8]
0x1800637c5  mov     [rsp+140h+var_100], rax; XLATEOBJ *
0x1800637ca  mov     rax, [rbp+40h+var_C0]
0x1800637ce  mov     [rsp+140h+var_108], r14; struct _CLIPOBJ *
0x1800637d3  mov     [rsp+140h+var_110], r12; struct tagSIZE *
0x1800637d8  mov     [rsp+140h+var_118], rax; struct _POINTL *
0x1800637dd  mov     qword ptr [rsp+140h+cLimit], r15; struct tagSIZE *
0x1800637e2  call    ?BGenerateBitmapPCL@@YAHPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_BRUSHOBJ@@PEAU_POINTL@@PEAUtagSIZE@@34PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@3@Z; BGenerateBitmapPCL(_DEVOBJ *,_SURFOBJ *,_BRUSHOBJ *,_POINTL *,tagSIZE *,_POINTL *,tagSIZE *,_CLIPOBJ *,_XLATEOBJ *,_POINTL *)
0x1800637e7  mov     ebx, eax
0x1800637e9  jmp     short loc_1800637FB
0x1800637eb  xor     ebx, ebx
0x1800637ed  jmp     loc_18006375F
0x1800637f2  xor     ebx, ebx
0x1800637f4  jmp     loc_180063764
0x1800637f9  xor     ebx, ebx
0x1800637fb  mov     eax, ebx
0x1800637fd  jmp     short loc_18006380C
0x1800637ff  mov     ecx, 0Dh; dwErrCode
0x180063804  call    cs:__imp_SetLastError
0x18006380a  xor     eax, eax
0x18006380c  mov     rcx, [rbp+40h+var_48]
0x180063810  xor     rcx, rsp; StackCookie
0x180063813  call    __security_check_cookie
0x180063818  add     rsp, 108h
0x18006381f  pop     r15
0x180063821  pop     r14
0x180063823  pop     r13
0x180063825  pop     r12
0x180063827  pop     rdi
0x180063828  pop     rsi
0x180063829  pop     rbx
0x18006382a  pop     rbp
0x18006382b  retn
```
