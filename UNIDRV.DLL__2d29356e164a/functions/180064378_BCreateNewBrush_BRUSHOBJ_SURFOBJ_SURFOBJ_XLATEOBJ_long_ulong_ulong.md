# BCreateNewBrush(_BRUSHOBJ *,_SURFOBJ *,_SURFOBJ *,_XLATEOBJ *,long,ulong,ulong)

- ea: `0x180064378`
- end: `0x1800647cf`
- name: `?BCreateNewBrush@@YAHPEAU_BRUSHOBJ@@PEAU_SURFOBJ@@1PEAU_XLATEOBJ@@JKK@Z`
- size: `1111`
- prototype: `__int64 __usercall@<rax>(BRUSHOBJ *pbo@<rcx>, struct _SURFOBJ *@<rdx>, struct _SURFOBJ *@<r8>, struct _XLATEOBJ *@<r9>, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180064870`

## callees

- `0x180045410`
- `0x1800618bc`
- `0x180064378`
- `0x180067ed4`
- `0x180068714`
- `0x18006a6e4`
- `0x18006a824`
- `0x18006a944`
- `0x18006ab18`
- `0x18006acc8`
- `0x18006b334`
- `0x18006b864`
- `0x18006b9f4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006478b`
- `KERNEL32!LocalFree` at `0x180064799`
- `KERNEL32!LocalFree` at `0x18006478b`
- `KERNEL32!LocalFree` at `0x180064799`
- `KERNEL32!SetLastError` at `0x1800647ac`
- `KERNEL32!SetLastError` at `0x1800647ac`
- `GDI32!BRUSHOBJ_pvAllocRbrush` at `0x180064734`
- `GDI32!BRUSHOBJ_pvAllocRbrush` at `0x180064734`
- `GDI32!XLATEOBJ_piVector` at `0x180064595`
- `GDI32!XLATEOBJ_piVector` at `0x180064595`

## pseudocode

```c
_BOOL8 __fastcall BCreateNewBrush(
        BRUSHOBJ *pbo,
        struct _SURFOBJ *a2,
        struct _SURFOBJ *a3,
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
  unsigned int v31; // eax
  struct _BRUSHINFO *CompatiblePatternBrush; // rax
  struct _RECTL *v33; // r8
  __int64 v34; // r13
  DHPDEV v35; // r12
  __int64 v36; // rcx
  int v37; // r10d
  struct _RASTER_DATA *v38; // rcx
  struct _BRUSHINFO *v40; // rax
  int v42; // [rsp+28h] [rbp-A1h]
  unsigned int v43; // [rsp+38h] [rbp-91h]
  int v44; // [rsp+48h] [rbp-81h]
  int v45; // [rsp+4Ch] [rbp-7Dh]
  unsigned int v46; // [rsp+50h] [rbp-79h]
  unsigned int v47; // [rsp+50h] [rbp-79h]
  unsigned int v48; // [rsp+50h] [rbp-79h]
  int v49; // [rsp+54h] [rbp-75h]
  HBITMAP v50; // [rsp+58h] [rbp-71h] BYREF
  __int128 v51; // [rsp+60h] [rbp-69h] BYREF
  DHPDEV v52; // [rsp+70h] [rbp-59h]
  struct _SURFOBJ *v53; // [rsp+78h] [rbp-51h] BYREF
  _OWORD hMem[2]; // [rsp+80h] [rbp-49h] BYREF
  __int128 v55; // [rsp+A0h] [rbp-29h]

  memset(hMem, 0, sizeof(hMem));
  v55 = 0;
  v51 = 0;
  if ( pbo && a2 && a3 && a4 && (dhpdev = a2->dhpdev, (v52 = dhpdev) != 0) && (v10 = *((_QWORD *)dhpdev + 1)) != 0 )
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
          v45 = 0;
          v15 = *(_DWORD *)(v12 + 36 * v14);
          IndexedImageFromDirect = (struct _RASTER_DATA *)hMem;
          v46 = v15;
          IndexedPaletteFromImage = 0;
          if ( v15 == 3 )
          {
            v49 = 0;
            v18 = 0;
            v53 = 0;
            v50 = 0;
            DeviceResolution = HPGL_GetDeviceResolution((struct _DEVOBJ *)dhpdev);
            v20 = *(_DWORD *)(v10 + 4472);
            v21 = DeviceResolution;
            v22 = 1;
            if ( !v20 )
              v20 = 1;
            v44 = 1;
            v47 = v20;
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
              v49 = v23;
            }
            if ( v21 >= 0x258 )
            {
              if ( v23 != 4 )
                v22 = 2;
              v44 = v22;
            }
            v24 = v52;
            if ( !*(_DWORD *)(*((_QWORD *)v52 + 1) + 4464LL) && (a3->iBitmapFormat != 1 || v23 == 4) )
            {
              if ( !(unsigned int)bCreateHTImage((struct _RASTER_DATA *)hMem, a2, a3, &v53, &v50, a4, v43) )
                goto LABEL_28;
LABEL_34:
              if ( *(_DWORD *)(*((_QWORD *)v24 + 1) + 4464LL) )
              {
                LODWORD(v51) = 32;
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
                DWORD1(v51) = cEntries;
                if ( a4->iSrcType == 1 || cEntries )
                {
                  pulXlate = a4->pulXlate;
                  if ( pulXlate )
                  {
                    *((_QWORD *)&v51 + 1) = a4->pulXlate;
                  }
                  else
                  {
                    pulXlate = XLATEOBJ_piVector(a4);
                    *((_QWORD *)&v51 + 1) = pulXlate;
                    cEntries = DWORD1(v51);
                  }
                }
                else
                {
                  pulXlate = (ULONG *)*((_QWORD *)&v51 + 1);
                }
                if ( pulXlate && cEntries && DWORD1(v55) )
                {
                  IndexedImageFromDirect = (struct _RASTER_DATA *)hMem;
                  v45 = 0;
                  IndexedPaletteFromImage = (struct _PALETTE *)&v51;
                }
                else
                {
                  v45 = 1;
                  IndexedPaletteFromImage = CreateIndexedPaletteFromImage((struct _RASTER_DATA *)hMem);
                  IndexedImageFromDirect = CreateIndexedImageFromDirect(
                                             (struct _RASTER_DATA *)hMem,
                                             IndexedPaletteFromImage);
                  TranslatePalette(IndexedPaletteFromImage, IndexedImageFromDirect, a4);
                  if ( !IndexedImageFromDirect || !IndexedPaletteFromImage )
                    goto LABEL_28;
                }
              }
              if ( v49 == 4 )
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
                    v30 = 2 * v44;
LABEL_55:
                    v31 = v30 / v47;
                    if ( !v31 )
                      v31 = 1;
                    v48 = v31;
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
                      v35 = v52;
                      v36 = *((_QWORD *)v52 + 1);
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
                        if ( v48 <= 1 )
                          v25 = CopyRasterImageRect(v38, IndexedImageFromDirect, v33, a4, v37) != 0;
                        else
                          v25 = StretchCopyImage(v38, IndexedImageFromDirect, a4, v48, v37) != 0;
LABEL_29:
                        v26 = v45;
                        if ( v50 )
                          DELETE_SURFOBJ(&v53, (HSURF *)&v50);
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
              v30 = v44;
              goto LABEL_55;
            }
            if ( (unsigned int)InitRasterDataFromSURFOBJ((struct _RASTER_DATA *)hMem, a3, 0) )
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
              if ( v46 == 2 )
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
0x180064378  mov     rax, rsp
0x18006437b  mov     [rax+20h], rbx
0x18006437f  mov     [rax+18h], r8
0x180064383  mov     [rax+10h], rdx
0x180064387  mov     [rax+8], rcx
0x18006438b  push    rbp
0x18006438c  push    rsi
0x18006438d  push    rdi
0x18006438e  push    r12
0x180064390  push    r13
0x180064392  push    r14
0x180064394  push    r15
0x180064396  lea     rbp, [rax-47h]
0x18006439a  sub     rsp, 0D0h
0x1800643a1  xorps   xmm0, xmm0
0x1800643a4  xor     r10d, r10d
0x1800643a7  mov     rbx, r9
0x1800643aa  mov     rax, rdx
0x1800643ad  mov     r12, rcx
0x1800643b0  movups  [rbp+3Fh+hMem], xmm0
0x1800643b4  movups  [rbp+3Fh+var_78], xmm0
0x1800643b8  movups  [rbp+3Fh+var_68], xmm0
0x1800643bc  movups  [rbp+3Fh+var_A8], xmm0
0x1800643c0  test    rcx, rcx
0x1800643c3  jz      loc_1800647A7
0x1800643c9  test    rax, rax
0x1800643cc  jz      loc_1800647A7
0x1800643d2  test    r8, r8
0x1800643d5  jz      loc_1800647A7
0x1800643db  test    rbx, rbx
0x1800643de  jz      loc_1800647A7
0x1800643e4  mov     r8, [rdx+10h]
0x1800643e8  mov     [rbp+3Fh+var_98], r8
0x1800643ec  test    r8, r8
0x1800643ef  jz      loc_1800647A7
0x1800643f5  mov     r13, [r8+8]
0x1800643f9  test    r13, r13
0x1800643fc  jz      loc_1800647A7
0x180064402  mov     rax, [r13+1138h]
0x180064409  mov     rdx, [rax+10h]
0x18006440d  test    rdx, rdx
0x180064410  jz      loc_1800647B2
0x180064416  mov     ecx, [rax+4]
0x180064419  test    ecx, ecx
0x18006441b  jz      loc_1800647B2
0x180064421  mov     r9d, [rbp+3Fh+arg_30]
0x180064425  dec     r9d
0x180064428  cmp     [rax+8], r10d
0x18006442c  jnz     short loc_180064430
0x18006442e  mov     ecx, [rax]
0x180064430  cmp     r9d, ecx
0x180064433  jnb     loc_1800647B2
0x180064439  lea     rax, [r9+r9*8]
0x18006443d  mov     [rbp+3Fh+var_BC], r10d
0x180064441  mov     eax, [rdx+rax*4]
0x180064444  lea     rsi, [rbp+3Fh+hMem]
0x180064448  mov     [rbp+3Fh+var_B8], eax
0x18006444b  mov     r15, r10
0x18006444e  cmp     eax, 3
0x180064451  jnz     loc_18006471C
0x180064457  mov     rcx, r8; struct _DEVOBJ *
0x18006445a  mov     [rbp+3Fh+var_B4], r10d
0x18006445e  mov     r14, r10
0x180064461  mov     [rbp+3Fh+var_90], r10
0x180064465  mov     [rbp+3Fh+var_B0], r10
0x180064469  call    ?HPGL_GetDeviceResolution@@YAKPEAU_DEVOBJ@@@Z; HPGL_GetDeviceResolution(_DEVOBJ *)
0x18006446e  mov     ecx, [r13+1178h]
0x180064475  mov     edi, 1
0x18006447a  test    ecx, ecx
0x18006447c  mov     edx, eax
0x18006447e  mov     eax, edi
0x180064480  cmovz   ecx, edi
0x180064483  mov     [rsp+40h], eax
0x180064487  mov     [rbp+3Fh+var_B8], ecx
0x18006448a  lea     r8d, [rdi+3]
0x18006448e  mov     ecx, [rbp+3Fh+arg_20]
0x180064491  test    ecx, ecx
0x180064493  jns     short loc_1800644AC
0x180064495  mov     eax, ecx
0x180064497  mov     ecx, r14d
0x18006449a  btr     eax, 1Fh
0x18006449e  cmp     eax, 6
0x1800644a1  mov     eax, edi
0x1800644a3  cmovb   ecx, r8d
0x1800644a7  mov     [rbp+3Fh+var_B4], ecx
0x1800644aa  jmp     short loc_1800644AF
0x1800644ac  mov     ecx, r14d
0x1800644af  mov     r12d, 2
0x1800644b5  cmp     edx, 258h
0x1800644bb  jb      short loc_1800644C8
0x1800644bd  cmp     ecx, r8d
0x1800644c0  cmovnz  eax, r12d
0x1800644c4  mov     [rsp+40h], eax
0x1800644c8  mov     r13, [rbp+3Fh+var_98]
0x1800644cc  mov     rdx, [rbp+3Fh+arg_10]; struct _SURFOBJ *
0x1800644d0  mov     rax, [r13+8]
0x1800644d4  cmp     [rax+1170h], r14d
0x1800644db  jnz     short loc_180064534
0x1800644dd  cmp     [rdx+48h], edi
0x1800644e0  jnz     short loc_1800644E7
0x1800644e2  cmp     ecx, r8d
0x1800644e5  jnz     short loc_180064534
0x1800644e7  lea     rax, [rbp+3Fh+var_B0]
0x1800644eb  mov     qword ptr [rsp+100h+var_E0+8], rbx; struct _XLATEOBJ *
0x1800644f0  mov     r8, rdx; struct _SURFOBJ *
0x1800644f3  mov     qword ptr [rsp+100h+var_E0], rax; HBITMAP *
0x1800644f8  mov     rdx, [rbp+3Fh+arg_8]; struct _SURFOBJ *
0x1800644fc  lea     r9, [rbp+3Fh+var_90]; struct _SURFOBJ **
0x180064500  lea     rcx, [rbp+3Fh+hMem]; struct _RASTER_DATA *
0x180064504  call    ?bCreateHTImage@@YAHPEAU_RASTER_DATA@@PEAU_SURFOBJ@@1PEAPEAU2@PEAPEAUHBITMAP__@@PEAU_XLATEOBJ@@K@Z; bCreateHTImage(_RASTER_DATA *,_SURFOBJ *,_SURFOBJ *,_SURFOBJ * *,HBITMAP__ * *,_XLATEOBJ *,ulong)
0x180064509  test    eax, eax
0x18006450b  jnz     short loc_180064548
0x18006450d  xor     ebx, ebx
0x18006450f  cmp     [rbp+3Fh+var_B0], 0
0x180064514  mov     r13d, [rbp+3Fh+var_BC]
0x180064518  jz      short loc_180064527
0x18006451a  lea     rdx, [rbp+3Fh+var_B0]; HBITMAP *
0x18006451e  lea     rcx, [rbp+3Fh+var_90]; struct _SURFOBJ **
0x180064522  call    ?DELETE_SURFOBJ@@YAXPEAPEAU_SURFOBJ@@PEAPEAUHBITMAP__@@@Z; DELETE_SURFOBJ(_SURFOBJ * *,HBITMAP__ * *)
0x180064527  test    ebx, ebx
0x180064529  jnz     loc_18006476B
0x18006452f  jmp     loc_18006477E
0x180064534  xor     r8d, r8d; int
0x180064537  lea     rcx, [rbp+3Fh+hMem]; struct _RASTER_DATA *
0x18006453b  call    ?InitRasterDataFromSURFOBJ@@YAHPEAU_RASTER_DATA@@PEAU_SURFOBJ@@H@Z; InitRasterDataFromSURFOBJ(_RASTER_DATA *,_SURFOBJ *,int)
0x180064540  test    eax, eax
0x180064542  jz      loc_1800647A1
0x180064548  mov     rax, [r13+8]
0x18006454c  cmp     [rax+1170h], r14d
0x180064553  jz      loc_180064607
0x180064559  mov     dword ptr [rbp+3Fh+var_A8], 20h ; ' '
0x180064560  test    [rbx+4], r12b
0x180064564  jz      short loc_180064574
0x180064566  mov     eax, 302h
0x18006456b  cmp     [rbx+0Ch], eax
0x18006456e  cmovb   eax, [rbx+0Ch]
0x180064572  jmp     short loc_180064576
0x180064574  xor     eax, eax
0x180064576  mov     dword ptr [rbp+3Fh+var_A8+4], eax
0x180064579  cmp     [rbx+8], di
0x18006457d  jz      short loc_180064589
0x18006457f  test    eax, eax
0x180064581  jnz     short loc_180064589
0x180064583  mov     rcx, qword ptr [rbp+3Fh+var_A8+8]
0x180064587  jmp     short loc_1800645AB
0x180064589  mov     rcx, [rbx+10h]
0x18006458d  test    rcx, rcx
0x180064590  jnz     short loc_1800645A7
0x180064592  mov     rcx, rbx; pxlo
0x180064595  call    cs:__imp_XLATEOBJ_piVector
0x18006459b  mov     rcx, rax
0x18006459e  mov     qword ptr [rbp+3Fh+var_A8+8], rax
0x1800645a2  mov     eax, dword ptr [rbp+3Fh+var_A8+4]
0x1800645a5  jmp     short loc_1800645AB
0x1800645a7  mov     qword ptr [rbp+3Fh+var_A8+8], rcx
0x1800645ab  test    rcx, rcx
0x1800645ae  jz      short loc_1800645C9
0x1800645b0  test    eax, eax
0x1800645b2  jz      short loc_1800645C9
0x1800645b4  cmp     dword ptr [rbp+3Fh+var_68+4], r14d
0x1800645b8  jz      short loc_1800645C9
0x1800645ba  xor     eax, eax
0x1800645bc  lea     rsi, [rbp+3Fh+hMem]
0x1800645c0  mov     [rbp+3Fh+var_BC], eax
0x1800645c3  lea     r15, [rbp+3Fh+var_A8]
0x1800645c7  jmp     short loc_180064607
0x1800645c9  lea     rcx, [rbp+3Fh+hMem]; struct _RASTER_DATA *
0x1800645cd  mov     [rbp+3Fh+var_BC], edi
0x1800645d0  call    ?CreateIndexedPaletteFromImage@@YAPEAU_PALETTE@@PEAU_RASTER_DATA@@@Z; CreateIndexedPaletteFromImage(_RASTER_DATA *)
0x1800645d5  mov     rdx, rax; struct _PALETTE *
0x1800645d8  lea     rcx, [rbp+3Fh+hMem]; struct _RASTER_DATA *
0x1800645dc  mov     r15, rax
0x1800645df  call    ?CreateIndexedImageFromDirect@@YAPEAU_RASTER_DATA@@PEAU1@PEAU_PALETTE@@@Z; CreateIndexedImageFromDirect(_RASTER_DATA *,_PALETTE *)
0x1800645e4  mov     r8, rbx; struct _XLATEOBJ *
0x1800645e7  mov     rdx, rax; struct _RASTER_DATA *
0x1800645ea  mov     rcx, r15; struct _PALETTE *
0x1800645ed  mov     rsi, rax
0x1800645f0  call    ?TranslatePalette@@YAXPEAU_PALETTE@@PEAU_RASTER_DATA@@PEAU_XLATEOBJ@@@Z; TranslatePalette(_PALETTE *,_RASTER_DATA *,_XLATEOBJ *)
0x1800645f5  test    rsi, rsi
0x1800645f8  jz      loc_18006450D
0x1800645fe  test    r15, r15
0x180064601  jz      loc_18006450D
0x180064607  cmp     [rbp+3Fh+var_B4], 4
0x18006460b  jnz     loc_1800646CA
0x180064611  mov     r12d, edi
0x180064614  mov     eax, [rsp+40h]
0x180064618  mov     ecx, [rbp+3Fh+arg_20]
0x18006461b  xor     edx, edx
0x18006461d  div     [rbp+3Fh+var_B8]
0x180064620  mov     [rsp+100h+var_E0+8], ecx; int
0x180064624  mov     r8, r15; struct _PALETTE *
0x180064627  mov     rcx, [rbp+3Fh+arg_0]; struct _BRUSHOBJ *
0x18006462b  cmp     eax, edi
0x18006462d  mov     rdx, rsi; struct _RASTER_DATA *
0x180064630  cmovb   eax, edi
0x180064633  mov     r9d, eax; unsigned int
0x180064636  mov     [rbp+3Fh+var_B8], eax
0x180064639  call    ?CreateCompatiblePatternBrush@@YAPEAU_BRUSHINFO@@PEAU_BRUSHOBJ@@PEAU_RASTER_DATA@@PEAU_PALETTE@@KJJ@Z; CreateCompatiblePatternBrush(_BRUSHOBJ *,_RASTER_DATA *,_PALETTE *,ulong,long,long)
0x18006463e  mov     r14, rax
0x180064641  test    rax, rax
0x180064644  jz      loc_18006450D
0x18006464a  mov     r13, [rax+18h]
0x18006464e  mov     [r13+50h], r12d
0x180064652  mov     r12, [rbp+3Fh+var_98]
0x180064656  mov     rcx, [r12+8]
0x18006465b  cmp     dword ptr [rcx+1170h], 0
0x180064662  jz      short loc_180064678
0x180064664  lea     rcx, [r13+40h]; struct _PALETTE *
0x180064668  mov     rdx, r15; struct _PALETTE *
0x18006466b  call    ?CopyPalette@@YAHPEAU_PALETTE@@0@Z; CopyPalette(_PALETTE *,_PALETTE *)
0x180064670  test    eax, eax
0x180064672  jz      loc_18006450D
0x180064678  mov     rax, [r12+8]
0x18006467d  xor     r10d, r10d
0x180064680  cmp     [rax+1170h], r10d
0x180064687  jnz     short loc_1800646A1
0x180064689  cmp     [rbx+10h], r10
0x18006468d  jz      short loc_18006469E
0x18006468f  mov     edx, [rsi+20h]; unsigned int
0x180064692  mov     r8, rbx; struct _XLATEOBJ *
0x180064695  call    ?BImageNeedsInversion@@YAHPEAU_DEVOBJ@@KPEAU_XLATEOBJ@@@Z; BImageNeedsInversion(_DEVOBJ *,ulong,_XLATEOBJ *)
0x18006469a  test    eax, eax
0x18006469c  jz      short loc_1800646A1
0x18006469e  mov     r10d, edi
0x1800646a1  mov     r9d, [rbp+3Fh+var_B8]; unsigned int
0x1800646a5  lea     rcx, [r13+8]; struct _RASTER_DATA *
0x1800646a9  mov     [rsp+100h+var_E0], r10d; int
0x1800646ae  mov     rdx, rsi; struct _RASTER_DATA *
0x1800646b1  cmp     r9d, edi
0x1800646b4  jbe     short loc_180064709
0x1800646b6  mov     r8, rbx; struct _XLATEOBJ *
0x1800646b9  call    ?StretchCopyImage@@YAHPEAU_RASTER_DATA@@0PEAU_XLATEOBJ@@KH@Z; StretchCopyImage(_RASTER_DATA *,_RASTER_DATA *,_XLATEOBJ *,ulong,int)
0x1800646be  xor     ebx, ebx
0x1800646c0  test    eax, eax
0x1800646c2  setnz   bl
0x1800646c5  jmp     loc_18006450F
0x1800646ca  xor     r12d, r12d
0x1800646cd  test    rsi, rsi
0x1800646d0  jz      loc_180064614
0x1800646d6  cmp     [rsi+20h], edi
0x1800646d9  jz      short loc_1800646E1
0x1800646db  cmp     dword ptr [rsi+20h], 8
0x1800646df  jnz     short loc_1800646F1
0x1800646e1  mov     eax, [rsi+18h]
0x1800646e4  imul    eax, [rsi+14h]
0x1800646e8  cmp     eax, 40h ; '@'
0x1800646eb  jle     short loc_1800646F1
0x1800646ed  xor     eax, eax
0x1800646ef  jmp     short loc_1800646F3
0x1800646f1  mov     eax, edi
0x1800646f3  cmp     eax, edi
0x1800646f5  jnz     loc_180064614
0x1800646fb  mov     eax, [rsp+40h]
0x1800646ff  mov     r12d, edi
0x180064702  add     eax, eax
0x180064704  jmp     loc_180064618
0x180064709  mov     r9, rbx; struct _XLATEOBJ *
0x18006470c  call    ?CopyRasterImageRect@@YAHPEAU_RASTER_DATA@@0PEAU_RECTL@@PEAU_XLATEOBJ@@H@Z; CopyRasterImageRect(_RASTER_DATA *,_RASTER_DATA *,_RECTL *,_XLATEOBJ *,int)
0x180064711  neg     eax
0x180064713  sbb     ebx, ebx
0x180064715  and     ebx, edi
0x180064717  jmp     loc_18006450F
0x18006471c  dec     eax
0x18006471e  mov     edi, 1
0x180064723  cmp     eax, edi
0x180064725  jbe     short loc_18006472C
0x180064727  mov     ebx, r10d
0x18006472a  jmp     short loc_1800647A3
0x18006472c  mov     edx, 30h ; '0'; cj
0x180064731  mov     rcx, r12; pbo
0x180064734  call    cs:__imp_BRUSHOBJ_pvAllocRbrush
0x18006473a  mov     r14, rax
0x18006473d  test    rax, rax
0x180064740  jz      short loc_1800647A1
0x180064742  xorps   xmm0, xmm0
0x180064745  mov     r13d, r15d
0x180064748  movups  xmmword ptr [rax], xmm0
0x18006474b  movups  xmmword ptr [rax+10h], xmm0
0x18006474f  movups  xmmword ptr [rax+20h], xmm0
0x180064753  mov     [r12+8], rax
0x180064758  mov     r12d, 2
0x18006475e  cmp     [rbp+3Fh+var_B8], r12d
0x180064762  jnz     short loc_18006476B
0x180064764  mov     eax, [rbp+3Fh+arg_20]
0x180064767  mov     [r14+24h], eax
0x18006476b  mov     eax, [rbp+3Fh+arg_30]
0x18006476e  mov     ebx, edi
0x180064770  mov     [r14], eax
0x180064773  mov     eax, [rbp+3Fh+arg_28]
0x180064776  mov     [r14+20h], eax
0x18006477a  mov     [r14+8], edi
0x18006477e  test    r13d, r13d
0x180064781  jz      short loc_1800647A3
0x180064783  test    rsi, rsi
0x180064786  jz      short loc_180064791
0x180064788  mov     rcx, rsi; hMem
0x18006478b  call    cs:__imp_LocalFree
0x180064791  test    r15, r15
0x180064794  jz      short loc_1800647A3
0x180064796  mov     rcx, r15; hMem
  ... truncated ...
```
