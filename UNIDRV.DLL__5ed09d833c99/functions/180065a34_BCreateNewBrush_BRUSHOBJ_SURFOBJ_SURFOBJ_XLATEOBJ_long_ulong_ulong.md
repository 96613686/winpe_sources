# BCreateNewBrush(_BRUSHOBJ *,_SURFOBJ *,_SURFOBJ *,_XLATEOBJ *,long,ulong,ulong)

- ea: `0x180065a34`
- end: `0x180065ead`
- name: `?BCreateNewBrush@@YAHPEAU_BRUSHOBJ@@PEAU_SURFOBJ@@1PEAU_XLATEOBJ@@JKK@Z`
- size: `1145`
- prototype: `_BOOL8 __fastcall(BRUSHOBJ *pbo, struct _SURFOBJ *, struct _RECTL *, struct _XLATEOBJ *, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180065f50`

## callees

- `0x180046790`
- `0x180062e04`
- `0x180065a34`
- `0x180069728`
- `0x180069f98`
- `0x18006c03c`
- `0x18006c17c`
- `0x18006c29c`
- `0x18006c47c`
- `0x18006c634`
- `0x18006ccc0`
- `0x18006d200`
- `0x18006d390`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180065e56`
- `KERNEL32!LocalFree` at `0x180065e6a`
- `KERNEL32!LocalFree` at `0x180065e56`
- `KERNEL32!LocalFree` at `0x180065e6a`
- `KERNEL32!SetLastError` at `0x180065e83`
- `KERNEL32!SetLastError` at `0x180065e83`
- `GDI32!BRUSHOBJ_pvAllocRbrush` at `0x180065df9`
- `GDI32!BRUSHOBJ_pvAllocRbrush` at `0x180065df9`
- `GDI32!XLATEOBJ_piVector` at `0x180065c51`
- `GDI32!XLATEOBJ_piVector` at `0x180065c51`

## pseudocode

```c
_BOOL8 __fastcall BCreateNewBrush(
        BRUSHOBJ *pbo,
        struct _SURFOBJ *a2,
        struct _RECTL *a3,
        struct _XLATEOBJ *a4,
        int a5,
        unsigned int a6,
        unsigned int a7)
{
  DHPDEV dhpdev; // r8
  __int64 v10; // r13
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // ecx
  __int64 v14; // r9
  unsigned int v15; // eax
  struct _RASTER_DATA *IndexedImageFromDirect; // rsi
  struct _PALETTE *IndexedPaletteFromImage; // r15
  struct _BRUSHINFO *v18; // r14
  unsigned int DeviceResolution; // eax
  int v20; // ecx
  unsigned int v21; // edx
  int v22; // eax
  int v23; // ecx
  DHPDEV v24; // r13
  BOOL v25; // ebx
  int v26; // r13d
  ULONG cEntries; // eax
  ULONG *pulXlate; // rcx
  int v29; // r12d
  unsigned int v30; // eax
  int v31; // eax
  struct _BRUSHINFO *CompatiblePatternBrush; // rax
  struct _RECTL *v33; // r8
  __int64 v34; // r13
  DHPDEV v35; // r12
  __int64 v36; // rcx
  int v37; // r10d
  struct _RASTER_DATA *v38; // rcx
  struct _BRUSHINFO *v40; // rax
  int v42; // [rsp+28h] [rbp-A1h]
  int v43; // [rsp+48h] [rbp-81h]
  int v44; // [rsp+4Ch] [rbp-7Dh]
  unsigned int v45; // [rsp+50h] [rbp-79h]
  unsigned int v46; // [rsp+50h] [rbp-79h]
  unsigned int v47; // [rsp+50h] [rbp-79h]
  int v48; // [rsp+54h] [rbp-75h]
  HBITMAP v49; // [rsp+58h] [rbp-71h] BYREF
  __int128 v50; // [rsp+60h] [rbp-69h] BYREF
  DHPDEV v51; // [rsp+70h] [rbp-59h]
  struct _SURFOBJ *v52; // [rsp+78h] [rbp-51h] BYREF
  _OWORD hMem[2]; // [rsp+80h] [rbp-49h] BYREF
  __int128 v54; // [rsp+A0h] [rbp-29h]

  memset(hMem, 0, sizeof(hMem));
  v54 = 0;
  v50 = 0;
  if ( pbo && a2 && a3 && a4 && (dhpdev = a2->dhpdev, (v51 = dhpdev) != 0) && (v10 = *((_QWORD *)dhpdev + 1)) != 0 )
  {
    v11 = *(_QWORD *)(v10 + 4408);
    v12 = *(_QWORD *)(v11 + 16);
    if ( v12 )
    {
      v13 = *(_DWORD *)(v11 + 4);
      if ( v13 )
      {
        v14 = a7 - 1;
        if ( !*(_DWORD *)(v11 + 8) )
          v13 = *(_DWORD *)v11;
        if ( (unsigned int)v14 < v13 )
        {
          v44 = 0;
          v15 = *(_DWORD *)(v12 + 36 * v14);
          IndexedImageFromDirect = (struct _RASTER_DATA *)hMem;
          v45 = v15;
          IndexedPaletteFromImage = 0;
          if ( v15 == 3 )
          {
            v48 = 0;
            v18 = 0;
            v52 = 0;
            v49 = 0;
            DeviceResolution = HPGL_GetDeviceResolution((struct _DEVOBJ *)dhpdev);
            v20 = *(_DWORD *)(v10 + 4472);
            v21 = DeviceResolution;
            v22 = 1;
            if ( !v20 )
              v20 = 1;
            v43 = 1;
            v46 = v20;
            if ( a5 >= 0 )
            {
              v23 = 0;
            }
            else
            {
              v23 = 0;
              v22 = 1;
              if ( (a5 & 0x7FFFFFFFu) < 6 )
                v23 = 4;
              v48 = v23;
            }
            if ( v21 >= 0x258 )
            {
              if ( v23 != 4 )
                v22 = 2;
              v43 = v22;
            }
            v24 = v51;
            if ( !*(_DWORD *)(*((_QWORD *)v51 + 1) + 4464LL) && (a3[4].right != 1 || v23 == 4) )
            {
              if ( !(unsigned int)bCreateHTImage((struct _RASTER_DATA *)hMem, a2, a3, (struct _RECTL **)&v52, &v49, a4) )
                goto LABEL_28;
LABEL_34:
              if ( *(_DWORD *)(*((_QWORD *)v24 + 1) + 4464LL) )
              {
                LODWORD(v50) = 32;
                if ( (a4->flXlate & 2) != 0 )
                {
                  cEntries = 770;
                  if ( a4->cEntries < 0x302 )
                    cEntries = a4->cEntries;
                }
                else
                {
                  cEntries = 0;
                }
                DWORD1(v50) = cEntries;
                if ( a4->iSrcType == 1 || cEntries )
                {
                  pulXlate = a4->pulXlate;
                  if ( pulXlate )
                  {
                    *((_QWORD *)&v50 + 1) = a4->pulXlate;
                  }
                  else
                  {
                    pulXlate = XLATEOBJ_piVector(a4);
                    *((_QWORD *)&v50 + 1) = pulXlate;
                    cEntries = DWORD1(v50);
                  }
                }
                else
                {
                  pulXlate = (ULONG *)*((_QWORD *)&v50 + 1);
                }
                if ( pulXlate && cEntries && DWORD1(v54) )
                {
                  IndexedImageFromDirect = (struct _RASTER_DATA *)hMem;
                  v44 = 0;
                  IndexedPaletteFromImage = (struct _PALETTE *)&v50;
                }
                else
                {
                  v44 = 1;
                  IndexedPaletteFromImage = CreateIndexedPaletteFromImage((struct _RASTER_DATA *)hMem);
                  IndexedImageFromDirect = CreateIndexedImageFromDirect(
                                             (struct _RASTER_DATA *)hMem,
                                             IndexedPaletteFromImage);
                  TranslatePalette(IndexedPaletteFromImage, IndexedImageFromDirect, a4);
                  if ( !IndexedImageFromDirect || !IndexedPaletteFromImage )
                    goto LABEL_28;
                }
              }
              if ( v48 == 4 )
              {
                v29 = 1;
              }
              else
              {
                v29 = 0;
                if ( IndexedImageFromDirect )
                {
                  if ( *((_DWORD *)IndexedImageFromDirect + 8) != 1 && *((_DWORD *)IndexedImageFromDirect + 8) != 8
                    || *((_DWORD *)IndexedImageFromDirect + 5) * *((_DWORD *)IndexedImageFromDirect + 6) <= 64 )
                  {
                    v29 = 1;
                    v30 = 2 * v43;
LABEL_55:
                    v31 = v30 / v46;
                    if ( !v31 )
                      v31 = 1;
                    v47 = v31;
                    CompatiblePatternBrush = CreateCompatiblePatternBrush(
                                               pbo,
                                               IndexedImageFromDirect,
                                               IndexedPaletteFromImage,
                                               v31,
                                               v42,
                                               a5);
                    v18 = CompatiblePatternBrush;
                    if ( CompatiblePatternBrush )
                    {
                      v34 = *((_QWORD *)CompatiblePatternBrush + 3);
                      *(_DWORD *)(v34 + 80) = v29;
                      v35 = v51;
                      v36 = *((_QWORD *)v51 + 1);
                      if ( !*(_DWORD *)(v36 + 4464)
                        || (unsigned int)CopyPalette((struct _PALETTE *)(v34 + 64), IndexedPaletteFromImage) )
                      {
                        v37 = 0;
                        if ( !*(_DWORD *)(*((_QWORD *)v35 + 1) + 4464LL)
                          && (!a4->pulXlate
                           || (unsigned int)BImageNeedsInversion(
                                              (struct _DEVOBJ *)v36,
                                              *((_DWORD *)IndexedImageFromDirect + 8),
                                              a4)) )
                        {
                          v37 = 1;
                        }
                        v38 = (struct _RASTER_DATA *)(v34 + 8);
                        if ( v47 <= 1 )
                          v25 = CopyRasterImageRect(v38, IndexedImageFromDirect, v33, a4, v37) != 0;
                        else
                          v25 = StretchCopyImage(v38, IndexedImageFromDirect, a4, v47, v37) != 0;
LABEL_29:
                        v26 = v44;
                        if ( v49 )
                          DELETE_SURFOBJ(&v52, (HSURF *)&v49);
                        if ( !v25 )
                          goto LABEL_81;
                        goto LABEL_80;
                      }
                    }
LABEL_28:
                    v25 = 0;
                    goto LABEL_29;
                  }
                }
              }
              v30 = v43;
              goto LABEL_55;
            }
            if ( (unsigned int)InitRasterDataFromSURFOBJ((struct _RASTER_DATA *)hMem, (struct _SURFOBJ *)a3, 0) )
              goto LABEL_34;
          }
          else
          {
            if ( v15 - 1 > 1 )
              return 0;
            v40 = (struct _BRUSHINFO *)BRUSHOBJ_pvAllocRbrush(pbo, 0x30u);
            v18 = v40;
            if ( v40 )
            {
              v26 = 0;
              *(_OWORD *)v40 = 0;
              *((_OWORD *)v40 + 1) = 0;
              *((_OWORD *)v40 + 2) = 0;
              pbo->pvRbrush = v40;
              if ( v45 == 2 )
                *((_DWORD *)v40 + 9) = a5;
LABEL_80:
              v25 = 1;
              *(_DWORD *)v18 = a7;
              *((_DWORD *)v18 + 8) = a6;
              *((_DWORD *)v18 + 2) = 1;
LABEL_81:
              if ( v26 )
              {
                if ( IndexedImageFromDirect )
                  LocalFree(IndexedImageFromDirect);
                if ( IndexedPaletteFromImage )
                  LocalFree(IndexedPaletteFromImage);
              }
              return v25;
            }
          }
          return 0;
        }
      }
    }
  }
  else
  {
    SetLastError(0xDu);
  }
  return 0;
}

```

## disassembly

```asm
0x180065a34  mov     rax, rsp
0x180065a37  mov     [rax+20h], rbx
0x180065a3b  mov     [rax+18h], r8
0x180065a3f  mov     [rax+10h], rdx
0x180065a43  mov     [rax+8], rcx
0x180065a47  push    rbp
0x180065a48  push    rsi
0x180065a49  push    rdi
0x180065a4a  push    r12
0x180065a4c  push    r13
0x180065a4e  push    r14
0x180065a50  push    r15
0x180065a52  lea     rbp, [rax-47h]
0x180065a56  sub     rsp, 0D0h
0x180065a5d  xorps   xmm0, xmm0
0x180065a60  xor     r10d, r10d
0x180065a63  mov     rbx, r9
0x180065a66  mov     rax, rdx
0x180065a69  mov     r12, rcx
0x180065a6c  movups  [rbp+3Fh+hMem], xmm0
0x180065a70  movups  [rbp+3Fh+var_78], xmm0
0x180065a74  movups  [rbp+3Fh+var_68], xmm0
0x180065a78  movups  [rbp+3Fh+var_A8], xmm0
0x180065a7c  test    rcx, rcx
0x180065a7f  jz      loc_180065E7E
0x180065a85  test    rax, rax
0x180065a88  jz      loc_180065E7E
0x180065a8e  test    r8, r8
0x180065a91  jz      loc_180065E7E
0x180065a97  test    rbx, rbx
0x180065a9a  jz      loc_180065E7E
0x180065aa0  mov     r8, [rdx+10h]
0x180065aa4  mov     [rbp+3Fh+var_98], r8
0x180065aa8  test    r8, r8
0x180065aab  jz      loc_180065E7E
0x180065ab1  mov     r13, [r8+8]
0x180065ab5  test    r13, r13
0x180065ab8  jz      loc_180065E7E
0x180065abe  mov     rax, [r13+1138h]
0x180065ac5  mov     rdx, [rax+10h]
0x180065ac9  test    rdx, rdx
0x180065acc  jz      loc_180065E8F
0x180065ad2  mov     ecx, [rax+4]
0x180065ad5  test    ecx, ecx
0x180065ad7  jz      loc_180065E8F
0x180065add  mov     r9d, [rbp+3Fh+arg_30]
0x180065ae1  dec     r9d
0x180065ae4  cmp     [rax+8], r10d
0x180065ae8  jnz     short loc_180065AEC
0x180065aea  mov     ecx, [rax]
0x180065aec  cmp     r9d, ecx
0x180065aef  jnb     loc_180065E8F
0x180065af5  lea     rax, [r9+r9*8]
0x180065af9  mov     [rbp+3Fh+var_BC], r10d
0x180065afd  mov     eax, [rdx+rax*4]
0x180065b00  lea     rsi, [rbp+3Fh+hMem]
0x180065b04  mov     [rbp+3Fh+var_B8], eax
0x180065b07  mov     r15, r10
0x180065b0a  cmp     eax, 3
0x180065b0d  jnz     loc_180065DDE
0x180065b13  mov     rcx, r8; struct _DEVOBJ *
0x180065b16  mov     [rbp+3Fh+var_B4], r10d
0x180065b1a  mov     r14, r10
0x180065b1d  mov     [rbp+3Fh+var_90], r10
0x180065b21  mov     [rbp+3Fh+var_B0], r10
0x180065b25  call    ?HPGL_GetDeviceResolution@@YAKPEAU_DEVOBJ@@@Z; HPGL_GetDeviceResolution(_DEVOBJ *)
0x180065b2a  mov     ecx, [r13+1178h]
0x180065b31  mov     edi, 1
0x180065b36  test    ecx, ecx
0x180065b38  mov     edx, eax
0x180065b3a  mov     eax, edi
0x180065b3c  cmovz   ecx, edi
0x180065b3f  mov     [rsp+40h], eax
0x180065b43  mov     [rbp+3Fh+var_B8], ecx
0x180065b46  lea     r8d, [rdi+3]
0x180065b4a  mov     ecx, [rbp+3Fh+arg_20]
0x180065b4d  test    ecx, ecx
0x180065b4f  jns     short loc_180065B68
0x180065b51  mov     eax, ecx
0x180065b53  mov     ecx, r14d
0x180065b56  btr     eax, 1Fh
0x180065b5a  cmp     eax, 6
0x180065b5d  mov     eax, edi
0x180065b5f  cmovb   ecx, r8d
0x180065b63  mov     [rbp+3Fh+var_B4], ecx
0x180065b66  jmp     short loc_180065B6B
0x180065b68  mov     ecx, r14d
0x180065b6b  mov     r12d, 2
0x180065b71  cmp     edx, 258h
0x180065b77  jb      short loc_180065B84
0x180065b79  cmp     ecx, r8d
0x180065b7c  cmovnz  eax, r12d
0x180065b80  mov     [rsp+40h], eax
0x180065b84  mov     r13, [rbp+3Fh+var_98]
0x180065b88  mov     rdx, [rbp+3Fh+arg_10]; struct _SURFOBJ *
0x180065b8c  mov     rax, [r13+8]
0x180065b90  cmp     [rax+1170h], r14d
0x180065b97  jnz     short loc_180065BF0
0x180065b99  cmp     [rdx+48h], edi
0x180065b9c  jnz     short loc_180065BA3
0x180065b9e  cmp     ecx, r8d
0x180065ba1  jnz     short loc_180065BF0
0x180065ba3  lea     rax, [rbp+3Fh+var_B0]
0x180065ba7  mov     qword ptr [rsp+100h+var_E0+8], rbx; struct _XLATEOBJ *
0x180065bac  mov     r8, rdx; struct _SURFOBJ *
0x180065baf  mov     qword ptr [rsp+100h+var_E0], rax; HBITMAP *
0x180065bb4  mov     rdx, [rbp+3Fh+arg_8]; struct _SURFOBJ *
0x180065bb8  lea     r9, [rbp+3Fh+var_90]; struct _SURFOBJ **
0x180065bbc  lea     rcx, [rbp+3Fh+hMem]; struct _RASTER_DATA *
0x180065bc0  call    ?bCreateHTImage@@YAHPEAU_RASTER_DATA@@PEAU_SURFOBJ@@1PEAPEAU2@PEAPEAUHBITMAP__@@PEAU_XLATEOBJ@@K@Z; bCreateHTImage(_RASTER_DATA *,_SURFOBJ *,_SURFOBJ *,_SURFOBJ * *,HBITMAP__ * *,_XLATEOBJ *,ulong)
0x180065bc5  test    eax, eax
0x180065bc7  jnz     short loc_180065C04
0x180065bc9  xor     ebx, ebx
0x180065bcb  cmp     [rbp+3Fh+var_B0], 0
0x180065bd0  mov     r13d, [rbp+3Fh+var_BC]
0x180065bd4  jz      short loc_180065BE3
0x180065bd6  lea     rdx, [rbp+3Fh+var_B0]; HBITMAP *
0x180065bda  lea     rcx, [rbp+3Fh+var_90]; struct _SURFOBJ **
0x180065bde  call    ?DELETE_SURFOBJ@@YAXPEAPEAU_SURFOBJ@@PEAPEAUHBITMAP__@@@Z; DELETE_SURFOBJ(_SURFOBJ * *,HBITMAP__ * *)
0x180065be3  test    ebx, ebx
0x180065be5  jnz     loc_180065E36
0x180065beb  jmp     loc_180065E49
0x180065bf0  xor     r8d, r8d; int
0x180065bf3  lea     rcx, [rbp+3Fh+hMem]; struct _RASTER_DATA *
0x180065bf7  call    ?InitRasterDataFromSURFOBJ@@YAHPEAU_RASTER_DATA@@PEAU_SURFOBJ@@H@Z; InitRasterDataFromSURFOBJ(_RASTER_DATA *,_SURFOBJ *,int)
0x180065bfc  test    eax, eax
0x180065bfe  jz      loc_180065E78
0x180065c04  mov     rax, [r13+8]
0x180065c08  cmp     [rax+1170h], r14d
0x180065c0f  jz      loc_180065CC9
0x180065c15  mov     dword ptr [rbp+3Fh+var_A8], 20h ; ' '
0x180065c1c  test    [rbx+4], r12b
0x180065c20  jz      short loc_180065C30
0x180065c22  mov     eax, 302h
0x180065c27  cmp     [rbx+0Ch], eax
0x180065c2a  cmovb   eax, [rbx+0Ch]
0x180065c2e  jmp     short loc_180065C32
0x180065c30  xor     eax, eax
0x180065c32  mov     dword ptr [rbp+3Fh+var_A8+4], eax
0x180065c35  cmp     [rbx+8], di
0x180065c39  jz      short loc_180065C45
0x180065c3b  test    eax, eax
0x180065c3d  jnz     short loc_180065C45
0x180065c3f  mov     rcx, qword ptr [rbp+3Fh+var_A8+8]
0x180065c43  jmp     short loc_180065C6D
0x180065c45  mov     rcx, [rbx+10h]
0x180065c49  test    rcx, rcx
0x180065c4c  jnz     short loc_180065C69
0x180065c4e  mov     rcx, rbx; pxlo
0x180065c51  call    cs:__imp_XLATEOBJ_piVector
0x180065c58  nop     dword ptr [rax+rax+00h]
0x180065c5d  mov     rcx, rax
0x180065c60  mov     qword ptr [rbp+3Fh+var_A8+8], rax
0x180065c64  mov     eax, dword ptr [rbp+3Fh+var_A8+4]
0x180065c67  jmp     short loc_180065C6D
0x180065c69  mov     qword ptr [rbp+3Fh+var_A8+8], rcx
0x180065c6d  test    rcx, rcx
0x180065c70  jz      short loc_180065C8B
0x180065c72  test    eax, eax
0x180065c74  jz      short loc_180065C8B
0x180065c76  cmp     dword ptr [rbp+3Fh+var_68+4], r14d
0x180065c7a  jz      short loc_180065C8B
0x180065c7c  xor     eax, eax
0x180065c7e  lea     rsi, [rbp+3Fh+hMem]
0x180065c82  mov     [rbp+3Fh+var_BC], eax
0x180065c85  lea     r15, [rbp+3Fh+var_A8]
0x180065c89  jmp     short loc_180065CC9
0x180065c8b  lea     rcx, [rbp+3Fh+hMem]; struct _RASTER_DATA *
0x180065c8f  mov     [rbp+3Fh+var_BC], edi
0x180065c92  call    ?CreateIndexedPaletteFromImage@@YAPEAU_PALETTE@@PEAU_RASTER_DATA@@@Z; CreateIndexedPaletteFromImage(_RASTER_DATA *)
0x180065c97  mov     rdx, rax; struct _PALETTE *
0x180065c9a  lea     rcx, [rbp+3Fh+hMem]; struct _RASTER_DATA *
0x180065c9e  mov     r15, rax
0x180065ca1  call    ?CreateIndexedImageFromDirect@@YAPEAU_RASTER_DATA@@PEAU1@PEAU_PALETTE@@@Z; CreateIndexedImageFromDirect(_RASTER_DATA *,_PALETTE *)
0x180065ca6  mov     r8, rbx; struct _XLATEOBJ *
0x180065ca9  mov     rdx, rax; struct _RASTER_DATA *
0x180065cac  mov     rcx, r15; struct _PALETTE *
0x180065caf  mov     rsi, rax
0x180065cb2  call    ?TranslatePalette@@YAXPEAU_PALETTE@@PEAU_RASTER_DATA@@PEAU_XLATEOBJ@@@Z; TranslatePalette(_PALETTE *,_RASTER_DATA *,_XLATEOBJ *)
0x180065cb7  test    rsi, rsi
0x180065cba  jz      loc_180065BC9
0x180065cc0  test    r15, r15
0x180065cc3  jz      loc_180065BC9
0x180065cc9  cmp     [rbp+3Fh+var_B4], 4
0x180065ccd  jnz     loc_180065D8C
0x180065cd3  mov     r12d, edi
0x180065cd6  mov     eax, [rsp+40h]
0x180065cda  mov     ecx, [rbp+3Fh+arg_20]
0x180065cdd  xor     edx, edx
0x180065cdf  div     [rbp+3Fh+var_B8]
0x180065ce2  mov     [rsp+100h+var_E0+8], ecx; int
0x180065ce6  mov     r8, r15; struct _PALETTE *
0x180065ce9  mov     rcx, [rbp+3Fh+arg_0]; struct _BRUSHOBJ *
0x180065ced  cmp     eax, edi
0x180065cef  mov     rdx, rsi; struct _RASTER_DATA *
0x180065cf2  cmovb   eax, edi
0x180065cf5  mov     r9d, eax; unsigned int
0x180065cf8  mov     [rbp+3Fh+var_B8], eax
0x180065cfb  call    ?CreateCompatiblePatternBrush@@YAPEAU_BRUSHINFO@@PEAU_BRUSHOBJ@@PEAU_RASTER_DATA@@PEAU_PALETTE@@KJJ@Z; CreateCompatiblePatternBrush(_BRUSHOBJ *,_RASTER_DATA *,_PALETTE *,ulong,long,long)
0x180065d00  mov     r14, rax
0x180065d03  test    rax, rax
0x180065d06  jz      loc_180065BC9
0x180065d0c  mov     r13, [rax+18h]
0x180065d10  mov     [r13+50h], r12d
0x180065d14  mov     r12, [rbp+3Fh+var_98]
0x180065d18  mov     rcx, [r12+8]
0x180065d1d  cmp     dword ptr [rcx+1170h], 0
0x180065d24  jz      short loc_180065D3A
0x180065d26  lea     rcx, [r13+40h]; struct _PALETTE *
0x180065d2a  mov     rdx, r15; struct _PALETTE *
0x180065d2d  call    ?CopyPalette@@YAHPEAU_PALETTE@@0@Z; CopyPalette(_PALETTE *,_PALETTE *)
0x180065d32  test    eax, eax
0x180065d34  jz      loc_180065BC9
0x180065d3a  mov     rax, [r12+8]
0x180065d3f  xor     r10d, r10d
0x180065d42  cmp     [rax+1170h], r10d
0x180065d49  jnz     short loc_180065D63
0x180065d4b  cmp     [rbx+10h], r10
0x180065d4f  jz      short loc_180065D60
0x180065d51  mov     edx, [rsi+20h]; unsigned int
0x180065d54  mov     r8, rbx; struct _XLATEOBJ *
0x180065d57  call    ?BImageNeedsInversion@@YAHPEAU_DEVOBJ@@KPEAU_XLATEOBJ@@@Z; BImageNeedsInversion(_DEVOBJ *,ulong,_XLATEOBJ *)
0x180065d5c  test    eax, eax
0x180065d5e  jz      short loc_180065D63
0x180065d60  mov     r10d, edi
0x180065d63  mov     r9d, [rbp+3Fh+var_B8]; unsigned int
0x180065d67  lea     rcx, [r13+8]; struct _RASTER_DATA *
0x180065d6b  mov     [rsp+100h+var_E0], r10d; int
0x180065d70  mov     rdx, rsi; struct _RASTER_DATA *
0x180065d73  cmp     r9d, edi
0x180065d76  jbe     short loc_180065DCB
0x180065d78  mov     r8, rbx; struct _XLATEOBJ *
0x180065d7b  call    ?StretchCopyImage@@YAHPEAU_RASTER_DATA@@0PEAU_XLATEOBJ@@KH@Z; StretchCopyImage(_RASTER_DATA *,_RASTER_DATA *,_XLATEOBJ *,ulong,int)
0x180065d80  xor     ebx, ebx
0x180065d82  test    eax, eax
0x180065d84  setnz   bl
0x180065d87  jmp     loc_180065BCB
0x180065d8c  xor     r12d, r12d
0x180065d8f  test    rsi, rsi
0x180065d92  jz      loc_180065CD6
0x180065d98  cmp     [rsi+20h], edi
0x180065d9b  jz      short loc_180065DA3
0x180065d9d  cmp     dword ptr [rsi+20h], 8
0x180065da1  jnz     short loc_180065DB3
0x180065da3  mov     eax, [rsi+18h]
0x180065da6  imul    eax, [rsi+14h]
0x180065daa  cmp     eax, 40h ; '@'
0x180065dad  jle     short loc_180065DB3
0x180065daf  xor     eax, eax
0x180065db1  jmp     short loc_180065DB5
0x180065db3  mov     eax, edi
0x180065db5  cmp     eax, edi
0x180065db7  jnz     loc_180065CD6
0x180065dbd  mov     eax, [rsp+40h]
0x180065dc1  mov     r12d, edi
0x180065dc4  add     eax, eax
0x180065dc6  jmp     loc_180065CDA
0x180065dcb  mov     r9, rbx; struct _XLATEOBJ *
0x180065dce  call    ?CopyRasterImageRect@@YAHPEAU_RASTER_DATA@@0PEAU_RECTL@@PEAU_XLATEOBJ@@H@Z; CopyRasterImageRect(_RASTER_DATA *,_RASTER_DATA *,_RECTL *,_XLATEOBJ *,int)
0x180065dd3  neg     eax
0x180065dd5  sbb     ebx, ebx
0x180065dd7  and     ebx, edi
0x180065dd9  jmp     loc_180065BCB
0x180065dde  dec     eax
0x180065de0  mov     edi, 1
0x180065de5  cmp     eax, edi
0x180065de7  jbe     short loc_180065DF1
0x180065de9  mov     ebx, r10d
0x180065dec  jmp     loc_180065E7A
0x180065df1  mov     edx, 30h ; '0'; cj
0x180065df6  mov     rcx, r12; pbo
0x180065df9  call    cs:__imp_BRUSHOBJ_pvAllocRbrush
0x180065e00  nop     dword ptr [rax+rax+00h]
0x180065e05  mov     r14, rax
0x180065e08  test    rax, rax
0x180065e0b  jz      short loc_180065E78
0x180065e0d  xorps   xmm0, xmm0
0x180065e10  mov     r13d, r15d
0x180065e13  movups  xmmword ptr [rax], xmm0
0x180065e16  movups  xmmword ptr [rax+10h], xmm0
0x180065e1a  movups  xmmword ptr [rax+20h], xmm0
0x180065e1e  mov     [r12+8], rax
0x180065e23  mov     r12d, 2
0x180065e29  cmp     [rbp+3Fh+var_B8], r12d
0x180065e2d  jnz     short loc_180065E36
0x180065e2f  mov     eax, [rbp+3Fh+arg_20]
0x180065e32  mov     [r14+24h], eax
0x180065e36  mov     eax, [rbp+3Fh+arg_30]
0x180065e39  mov     ebx, edi
0x180065e3b  mov     [r14], eax
0x180065e3e  mov     eax, [rbp+3Fh+arg_28]
0x180065e41  mov     [r14+20h], eax
0x180065e45  mov     [r14+8], edi
0x180065e49  test    r13d, r13d
0x180065e4c  jz      short loc_180065E7A
0x180065e4e  test    rsi, rsi
0x180065e51  jz      short loc_180065E62
0x180065e53  mov     rcx, rsi; hMem
0x180065e56  call    cs:__imp_LocalFree
0x180065e5d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
