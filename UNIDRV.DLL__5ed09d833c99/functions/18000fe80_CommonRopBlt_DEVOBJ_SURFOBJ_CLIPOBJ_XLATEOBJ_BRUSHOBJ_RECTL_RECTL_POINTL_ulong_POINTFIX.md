# CommonRopBlt(_DEVOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,ulong,_POINTFIX *)

- ea: `0x18000fe80`
- end: `0x1800110dc`
- name: `?CommonRopBlt@@YAJPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@KPEAU_POINTFIX@@@Z`
- size: `4700`
- prototype: `__int64 __fastcall(struct _DEVOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _BRUSHOBJ *, RECTL *prclSrc, struct _RECTL *, struct _POINTL *, unsigned __int8)`
- caller_count: `5`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x18000f510`
- `0x18000f660`
- `0x18006fcd0`
- `0x18006fdc0`
- `0x18006fed0`

## callees

- `0x18000f3d8`
- `0x18000f5f8`
- `0x18000f750`
- `0x18000f798`
- `0x18000f844`
- `0x18000fae0`
- `0x18000fb50`
- `0x18000fbb4`
- `0x18000fe80`
- `0x180011470`
- `0x180011ed0`
- `0x180012010`
- `0x1800120ac`
- `0x180012160`
- `0x1800122c4`
- `0x180012450`
- `0x1800124e0`
- `0x1800125d8`
- `0x180012780`
- `0x180012850`
- `0x1800136a8`
- `0x180013b70`
- `0x180015540`
- `0x180015814`
- `0x18004375c`
- `0x1800452f8`
- `0x18004574c`
- `0x1800459b4`
- `0x180046654`
- `0x1800466cc`
- `0x1800467fc`
- `0x180049d00`
- `0x18004a71c`
- `0x18006e3bc`
- `0x18006eb70`
- `0x18006ebb8`
- `0x18006ec1c`
- `0x180076660`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001059e`
- `KERNEL32!LocalFree` at `0x180010dd0`
- `KERNEL32!LocalFree` at `0x180010f4e`
- `KERNEL32!LocalFree` at `0x18001059e`
- `KERNEL32!LocalFree` at `0x180010dd0`
- `KERNEL32!LocalFree` at `0x180010f4e`
- `KERNEL32!LocalAlloc` at `0x180010630`
- `KERNEL32!LocalAlloc` at `0x180010e17`
- `KERNEL32!LocalAlloc` at `0x180010630`
- `KERNEL32!LocalAlloc` at `0x180010e17`
- `GDI32!EngStretchBlt` at `0x180010236`
- `GDI32!EngStretchBlt` at `0x180010236`
- `GDI32!EngUnlockSurface` at `0x180010f62`
- `GDI32!EngUnlockSurface` at `0x180010f62`
- `GDI32!EngDeleteSurface` at `0x180010f7b`
- `GDI32!EngDeleteSurface` at `0x180010f7b`
- `GDI32!XLATEOBJ_piVector` at `0x180010d1b`
- `GDI32!XLATEOBJ_piVector` at `0x180010d89`
- `GDI32!XLATEOBJ_piVector` at `0x180010d1b`
- `GDI32!XLATEOBJ_piVector` at `0x180010d89`

## pseudocode

```c
__int64 __fastcall CommonRopBlt(
        struct _DEVOBJ *a1,
        struct _SURFOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _XLATEOBJ *a4,
        struct _BRUSHOBJ *a5,
        RECTL *prclSrc,
        struct _RECTL *a7,
        struct _POINTL *a8,
        unsigned __int8 a9)
{
  RECTL *v9; // r15
  XLOutput *v11; // rdi
  __int64 result; // rax
  XLWrite *v13; // rax
  __int64 v14; // rdi
  int v15; // esi
  char v16; // di
  int v17; // esi
  struct _DEVOBJ *v18; // r14
  ULONG iBitmapFormat; // edi
  int v20; // r14d
  unsigned int v21; // eax
  POINTL v22; // r10
  int v23; // r8d
  int v24; // r9d
  int v25; // edx
  int v26; // ecx
  bool v27; // sf
  int v28; // eax
  int v29; // edx
  int v30; // ecx
  int v31; // eax
  __int64 v32; // rsi
  XLWrite *v33; // rcx
  __int64 v34; // rdx
  unsigned __int8 *v35; // r13
  __int64 v36; // rax
  int v37; // r12d
  unsigned __int64 v38; // rcx
  SIZE_T v39; // rdx
  unsigned __int64 v40; // rsi
  const struct _POINTL *v41; // r8
  struct _POINTL *v42; // r8
  __int64 v43; // rdi
  unsigned int v44; // r14d
  unsigned int v45; // r13d
  unsigned int v46; // ecx
  unsigned __int8 *v47; // rbx
  unsigned __int8 *v48; // r14
  unsigned int v49; // edi
  unsigned int v50; // esi
  char *v51; // r9
  unsigned int v52; // r13d
  char *v53; // rbx
  unsigned int v54; // r11d
  unsigned __int8 *pvScan0; // r15
  XLOutput *v56; // rbx
  int v57; // r8d
  unsigned __int16 v58; // cx
  unsigned int v59; // r14d
  unsigned int v60; // ebx
  int v61; // esi
  int v62; // r13d
  unsigned int v63; // eax
  __int64 v64; // rcx
  char *v65; // r9
  struct _XLATEOBJ *v66; // r13
  unsigned int v67; // ebx
  int v68; // eax
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // r8
  void (*v74)(void *); // r9
  __int128 v75; // xmm1
  __int64 v76; // rcx
  __int128 v77; // xmm0
  __int128 v78; // xmm1
  __int128 v79; // xmm0
  __int128 v80; // xmm1
  __int64 v81; // rax
  __int64 v82; // rdx
  __int64 v83; // r8
  void (*v84)(void *); // r9
  unsigned __int64 v85; // rsi
  __int128 v86; // xmm1
  __int64 v87; // rcx
  __int128 v88; // xmm0
  __int128 v89; // xmm1
  __int128 v90; // xmm0
  __int128 v91; // xmm1
  int v92; // eax
  int v93; // edx
  int v94; // eax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rcx
  __int64 v99; // rax
  __int64 v100; // rax
  struct _POINTL *v101; // r8
  int v102; // esi
  unsigned int *pulXlate; // rax
  ULONG cEntries; // r8d
  unsigned int *v105; // rax
  __int64 v106; // rdx
  unsigned int *v107; // rsi
  int v108; // [rsp+60h] [rbp-A0h]
  XLWrite *v109; // [rsp+68h] [rbp-98h]
  unsigned int v110; // [rsp+70h] [rbp-90h]
  unsigned int v111; // [rsp+74h] [rbp-8Ch]
  int v112; // [rsp+78h] [rbp-88h]
  unsigned int v114; // [rsp+88h] [rbp-78h]
  unsigned int v115; // [rsp+8Ch] [rbp-74h]
  int v116; // [rsp+90h] [rbp-70h]
  int v117; // [rsp+94h] [rbp-6Ch]
  unsigned int v118; // [rsp+98h] [rbp-68h]
  char *v119; // [rsp+A0h] [rbp-60h]
  __int64 v120; // [rsp+A8h] [rbp-58h]
  unsigned int v121; // [rsp+B0h] [rbp-50h]
  char *hMem; // [rsp+C0h] [rbp-40h]
  unsigned __int8 *v124; // [rsp+C8h] [rbp-38h]
  SURFOBJ *pso; // [rsp+D0h] [rbp-30h]
  __int128 v126; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v127; // [rsp+F0h] [rbp-10h]
  __int128 v128; // [rsp+100h] [rbp+0h]
  size_t Size[2]; // [rsp+110h] [rbp+10h]
  __int128 v130; // [rsp+120h] [rbp+20h]
  __int128 v131; // [rsp+130h] [rbp+30h]
  __int64 v132; // [rsp+140h] [rbp+40h]
  POINTL pptlHTOrg; // [rsp+150h] [rbp+50h] BYREF
  HSURF hsurf; // [rsp+158h] [rbp+58h] BYREF
  __int128 v135; // [rsp+160h] [rbp+60h] BYREF
  __int128 v136; // [rsp+170h] [rbp+70h]
  __int128 v137; // [rsp+180h] [rbp+80h]
  __int128 v138; // [rsp+190h] [rbp+90h]
  __int128 v139; // [rsp+1A0h] [rbp+A0h]
  __int128 v140; // [rsp+1B0h] [rbp+B0h]
  __int64 v141; // [rsp+1C0h] [rbp+C0h]
  char *v142; // [rsp+1D0h] [rbp+D0h]
  RECTL prclDest[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  _QWORD v144[3]; // [rsp+200h] [rbp+100h] BYREF
  __int16 v145; // [rsp+21Ch] [rbp+11Ch]
  int v146; // [rsp+220h] [rbp+120h]
  unsigned int v147; // [rsp+224h] [rbp+124h]
  _OWORD v148[20]; // [rsp+228h] [rbp+128h] BYREF
  int v149; // [rsp+370h] [rbp+270h]
  int v150; // [rsp+374h] [rbp+274h]
  struct _XLATEOBJ *v151; // [rsp+380h] [rbp+280h] BYREF

  v9 = prclSrc;
  v151 = a4;
  if ( !a1 || !a7 )
    return 2147549183LL;
  if ( a7->right < a7->left || a7->bottom < a7->top )
    return 1;
  v120 = *((_QWORD *)a1 + 1);
  v11 = *(XLOutput **)(v120 + 160);
  v109 = v11;
  result = XLOutput::SetClip(v11, a3, a1);
  v108 = result;
  if ( (int)result >= 0 )
  {
    XLOutput::SetCursor(v11, a7->left, a7->top);
    v13 = v11;
    v14 = (__int64)v11 + 204;
    v15 = a9;
    if ( !v109 )
      v14 = 172;
    if ( a9 != *(_DWORD *)v14 )
    {
      if ( !(unsigned int)XLOutput::Send_ubyte(v109, a9) && !(unsigned int)XLOutput::Send_attr_ubyte((__int64)v109, 44) )
      {
        XLWrite::WriteByte(v109, 123);
        *(_DWORD *)v14 = a9;
      }
      v13 = v109;
    }
    if ( a9 == 255 )
    {
LABEL_10:
      v16 = 1;
    }
    else
    {
      switch ( a9 )
      {
        case 0u:
          v13 = v109;
          goto LABEL_10;
        case 0xFu:
        case 0xF0u:
          v13 = v109;
          v16 = 2;
          break;
        case 0x11u:
        case 0x33u:
        case 0x44u:
        case 0x66u:
        case 0x77u:
        case 0x99u:
        case 0xCCu:
        case 0xDDu:
          v13 = v109;
          v16 = 4;
          break;
        case 0xAAu:
          v13 = v109;
          v16 = 8;
          break;
        default:
          v93 = ((a9 ^ (a9 >> 2)) & 0x33) != 0 ? 4 : 0;
          v16 = v93 | 2;
          if ( a9 >> 4 == (a9 & 0xF) )
            v16 = v93;
          v13 = v109;
          if ( ((a9 ^ (a9 >> 1)) & 0x55) != 0 )
            v16 |= 8u;
          break;
      }
    }
    if ( (v16 & 1) != 0 )
    {
      memset(prclDest, 0, 28);
      XLOutput::SetSourceTxMode(v13, 0);
      XLOutput::SetPaintTxMode(v109, 0);
      v94 = *((_DWORD *)v109 + 71);
      if ( a9 )
      {
        if ( v94 == 3 )
        {
          v15 = 0xFFFFFF;
          XLOutput::SetRGBColor(v109, 0xFFFFFF);
        }
        else
        {
          XLOutput::SetGrayLevel(v109, 255);
          v15 = 0xFFFFFF;
        }
      }
      else if ( v94 == 3 )
      {
        XLOutput::SetRGBColor(v109, 0);
      }
      else
      {
        XLOutput::SetGrayLevel(v109, 0);
        v15 = 0;
      }
      v95 = (__int64)v109 + 84;
      if ( !v109 )
        v95 = 4;
      *(_DWORD *)v95 = 2;
      v96 = (__int64)v109 + 88;
      if ( !v109 )
        v96 = 8;
      *(_DWORD *)v96 = 0;
      v97 = (__int64)v109 + 92;
      if ( !v109 )
        v97 = 12;
      v98 = (__int64)v109 + 96;
      *(_DWORD *)v97 = -1;
      if ( !v109 )
        v98 = 16;
      *(_DWORD *)v98 = prclDest[1].left;
      v99 = (__int64)v109 + 100;
      if ( !v109 )
        v99 = 20;
      *(_DWORD *)v99 = v15;
      v100 = (__int64)v109 + 104;
      if ( !v109 )
        v100 = 24;
      *(_DWORD *)v100 = -1;
      XLWrite::WriteByte(v109, 99);
      XLOutput::SetPenColor(v109, 0, v101, a1);
      v17 = v16 & 4;
      if ( (v16 & 4) == 0 )
      {
        XLWrite::WriteByte(v109, 133);
        XLOutput::RectanglePath(v109, a7);
        XLWrite::WriteByte(v109, 134);
      }
      XLWrite::Flush(v109, a1);
    }
    else
    {
      v17 = v16 & 4;
    }
    if ( (v16 & 0xA) != 0 )
    {
      XLOutput::SetSourceTxMode(v109, 0);
      XLOutput::SetPaintTxMode(v109, 0);
      XLOutput::SetBrush(v109, a5, v41, a1);
      v18 = a1;
      XLOutput::SetPenColor(v109, 0, v42, a1);
      if ( !v17 )
      {
        XLWrite::WriteByte(v109, 133);
        XLOutput::RectanglePath(v109, a7);
        XLWrite::WriteByte(v109, 134);
      }
      XLWrite::Flush(v109, a1);
    }
    else
    {
      v18 = a1;
    }
    if ( !v17 )
      return (unsigned int)v108;
    hsurf = 0;
    if ( a2 && prclSrc )
    {
      iBitmapFormat = a2->iBitmapFormat;
      if ( iBitmapFormat != 6
        && (iBitmapFormat != 1 && iBitmapFormat != 2 && iBitmapFormat != 3 && iBitmapFormat - 4 > 1 || iBitmapFormat == 7) )
      {
        return 2147549183LL;
      }
      v20 = 0;
      v21 = UlBPPtoNum(iBitmapFormat);
      v23 = a7->right - a7->left;
      v24 = a7->bottom - a7->top;
      v25 = prclSrc->top - prclSrc->bottom;
      v115 = v21;
      pso = (SURFOBJ *)v22;
      if ( v25 < 0 )
        v25 = prclSrc->bottom - prclSrc->top;
      v26 = prclSrc->right - prclSrc->left;
      v27 = prclSrc->left - prclSrc->right < 0;
      v28 = prclSrc->left - prclSrc->right;
      prclDest[0] = 0;
      if ( v27 )
        v28 = v26;
      v29 = v28 * v25;
      v30 = -v24;
      if ( v24 > 0 )
        v30 = v24;
      v31 = -v23;
      if ( v23 > 0 )
        v31 = v23;
      if ( v31 * v30 < v29 )
      {
        pptlHTOrg = v22;
        prclDest[0].right = v23;
        prclDest[0].bottom = v24;
        if ( a8 )
          pptlHTOrg = *a8;
        pso = CreateBitmapSURFOBJ((__int64)a1, &hsurf, v23, v24, iBitmapFormat);
        if ( pso && EngStretchBlt(pso, a2, 0, 0, 0, 0, &pptlHTOrg, prclDest, prclSrc, 0, 3u) )
        {
          a2 = pso;
          v9 = prclDest;
        }
      }
      XLOutput::SetSourceTxMode(v109, (*((_DWORD *)a1 + 29) >> 7) & 1);
      v32 = (__int64)v109 + 260;
      if ( !v109 )
        v32 = 228;
      if ( *(_DWORD *)v32 && !(unsigned int)XLOutput::SetTxMode(v109, 0) )
      {
        XLWrite::WriteByte(v109, 120);
        *(_DWORD *)v32 = 0;
      }
      v102 = *((_DWORD *)v109 + 71);
      switch ( iBitmapFormat )
      {
        case 1u:
        case 2u:
          v20 = 1;
          goto LABEL_186;
        case 3u:
        case 4u:
          v111 = 0;
          v20 = v102 == 3;
          if ( v102 != 3 )
            goto LABEL_32;
          if ( v20 == 1 )
          {
LABEL_186:
            v111 = v115;
            goto LABEL_187;
          }
          if ( (unsigned int)(v20 - 2) < 2 )
            goto LABEL_195;
          goto LABEL_38;
        case 5u:
        case 6u:
          if ( v102 == 3 )
          {
            v20 = 2;
LABEL_195:
            v111 = 24;
LABEL_38:
            if ( v20 != 1 )
            {
LABEL_39:
              XLOutput::SetColorSpace(v109, (*((_DWORD *)v109 + 71) == 3) + 1);
              if ( v20 != 1 )
                goto LABEL_40;
              if ( a4 )
              {
                if ( (a4->flXlate & 2) != 0 )
                {
                  pulXlate = a4->pulXlate;
                  if ( pulXlate || (pulXlate = XLATEOBJ_piVector(a4)) != 0 )
                  {
                    cEntries = a4->cEntries;
                    if ( (*(_BYTE *)(v120 + 16) & 0x40) != 0 )
                    {
                      v105 = PdwChangeTransparentPalette(*(_DWORD *)(v120 + 184), pulXlate, cEntries);
                      v107 = v105;
                      if ( !v105 )
                      {
LABEL_211:
                        v60 = v108;
                        goto LABEL_103;
                      }
                      XLOutput::SetPalette(v109, v106, a4->cEntries, v105);
                      LocalFree(v107);
                    }
                    else
                    {
                      XLOutput::SetPalette(v109, v34, cEntries, pulXlate);
                    }
                  }
                }
              }
              v117 = 1;
LABEL_41:
              v35 = 0;
              v124 = 0;
              XLWrite::WriteByte(v109, 106);
              v36 = (unsigned int)(v9->right - v9->left);
              v37 = v9->bottom - v9->top;
              v38 = v36 * v111;
              v114 = v9->right - v9->left;
              v39 = ((unsigned int)v36 * v115 + 7) >> 3;
              v118 = ((unsigned int)v36 * v115 + 7) >> 3;
              if ( v38 > 0xFFFFFFFF
                || (v85 = (unsigned int)(v38 + 31), (unsigned int)v85 < (unsigned int)v38)
                || (v40 = (unsigned int)v37 * ((v85 >> 3) & 0x1FFFFFFC), v121 = v40, v40 > 0xFFFFFFFF)
                || (unsigned int)v40 > 0x4000 )
              {
                if ( (unsigned int)v39 <= 0x4000 )
                  LODWORD(v40) = 0x4000;
                else
                  LODWORD(v40) = (v39 + 3) & 0xFFFFFFFC;
                v121 = v40;
              }
              if ( (*(_BYTE *)(v120 + 16) & 0x40) != 0 && !v117 )
              {
                v124 = (unsigned __int8 *)LocalAlloc(0, v39);
                v35 = v124;
                if ( !v124 )
                  goto LABEL_211;
              }
              v119 = (char *)LocalAlloc(0, (unsigned int)v40);
              if ( !v119 )
              {
                v60 = v108;
                goto LABEL_101;
              }
              v61 = a7->bottom - a7->top;
              v62 = a7->right - a7->left;
              XLOutput::SetOutputBPP(v109, v117, v111);
              if ( !(unsigned int)XLOutput::Send_uint16(v109, v114) )
                XLOutput::Send_attr_ubyte((__int64)v109, 108);
              if ( !(unsigned int)XLOutput::Send_uint16(v109, v37) )
                XLOutput::Send_attr_ubyte((__int64)v109, 107);
              if ( !(unsigned int)XLOutput::Send_uint16_xy(v109, v62, v61) )
                XLOutput::Send_attr_ubyte((__int64)v109, 103);
              XLWrite::WriteByte(v109, 176);
              XLWrite::Flush(v109, a1);
              v50 = 0;
              hMem = v119;
              *((_QWORD *)&v136 + 1) = 0;
              v137 = 0u;
              *(_QWORD *)&v138 = 0;
              DWORD2(v138) = 0;
              *(_QWORD *)&v139 = 0;
              DWORD2(v139) = 0;
              *((_QWORD *)&v140 + 1) = 0;
              v141 = 0;
              *((_QWORD *)&v127 + 1) = 0;
              *(_QWORD *)&v128 = 0;
              HIDWORD(v128) = 0;
              Size[0] = 0;
              LODWORD(Size[1]) = 0;
              *(_QWORD *)&v130 = 0;
              DWORD2(v130) = 0;
              *((_QWORD *)&v131 + 1) = 0;
              v132 = 0;
              *(_QWORD *)&v135 = 1651339363;
              *(_QWORD *)&v126 = 0x1626D7063LL;
              DWORD2(v126) = iBitmapFormat;
              v63 = NumToBPP(v111);
              v66 = v151;
              v67 = v63;
              HIDWORD(v126) = v63;
              DWORD1(v127) = v20;
              if ( v151 )
              {
                *(_QWORD *)&v128 = v151;
                v68 = BMPConv::DwCheckXlateObj(v64, (__int64)v151, iBitmapFormat);
                v65 = v119;
                DWORD1(v126) = v68 | 1;
              }
              v54 = v115;
              DWORD2(v128) = 1;
              if ( pso )
                pvScan0 = (unsigned __int8 *)a2->pvScan0;
              else
                pvScan0 = (unsigned __int8 *)a2->pvScan0
                        + v9->top * (__int64)a2->lDelta
                        + ((unsigned __int64)(v9->left * v115) >> 3);
              v69 = *((_QWORD *)a1 + 250);
              v70 = *(unsigned int *)(*(unsigned int *)(v69 + 8) + *(_QWORD *)(v69 + 104) + 176LL);
              if ( (_DWORD)v70 != -1 && *(unsigned int *)(v69 + 16) + *(_QWORD *)(v69 + 96) + 28 * v70 && v37 >= 1 )
              {
                BMPCompress::BMPCompress((BMPCompress *)v144);
                DWORD1(v135) = 1;
                *((_QWORD *)&v135 + 1) = __PAIR64__(v67, iBitmapFormat);
                DWORD1(v136) = v20;
                if ( v66 )
                {
                  *(_QWORD *)&v137 = v66;
                  DWORD1(v135) = BMPConv::DwCheckXlateObj(v72, (__int64)v66, iBitmapFormat) | 1;
                }
                DWORD2(v137) = 3;
                if ( v147 >= 3 )
                {
                  v108 = -2147467259;
                  `vector destructor iterator'((char *)v148, v71, v73, v74);
                }
                else
                {
                  v60 = 0;
                  v75 = v136;
                  v76 = 104LL * v147;
                  *(_OWORD *)((char *)v148 + v76) = v135;
                  v77 = v137;
                  *(_OWORD *)((char *)&v148[1] + v76) = v75;
                  v78 = v138;
                  *(_OWORD *)((char *)&v148[2] + v76) = v77;
                  v79 = v139;
                  *(_OWORD *)((char *)&v148[3] + v76) = v78;
                  v80 = v140;
                  *(_OWORD *)((char *)&v148[4] + v76) = v79;
                  *(_OWORD *)((char *)&v148[5] + v76) = v80;
                  *(_QWORD *)((char *)&v148[6] + v76) = 0;
                  *((_DWORD *)&v148[19] + v147 + 2) = 0;
                  v81 = v147 + 1;
                  v147 = v81;
                  if ( (unsigned int)v81 >= 3 )
                  {
                    v60 = -2147467259;
                    `vector destructor iterator'((char *)v148, v71, v73, v74);
LABEL_134:
                    BMPConv::~BMPConv((BMPConv *)&v126);
                    BMPConv::~BMPConv((BMPConv *)&v135);
                    goto LABEL_100;
                  }
                  v86 = v127;
                  v44 = v114;
                  v87 = 104 * v81;
                  *(_OWORD *)((char *)v148 + v87) = v126;
                  v88 = v128;
                  *(_OWORD *)((char *)&v148[1] + v87) = v86;
                  v89 = *(_OWORD *)Size;
                  *(_OWORD *)((char *)&v148[2] + v87) = v88;
                  v90 = v130;
                  *(_OWORD *)((char *)&v148[3] + v87) = v89;
                  v91 = v131;
                  *(_OWORD *)((char *)&v148[4] + v87) = v90;
                  *(_OWORD *)((char *)&v148[5] + v87) = v91;
                  *(_QWORD *)((char *)&v148[6] + v87) = 0;
                  *((_DWORD *)&v148[19] + v147++ + 2) = 0;
                  v145 = 30;
                  v92 = BMPCompress::hrSetSrcBitmap((BMPCompress *)v144, pvScan0, v114, v37, a2);
                  v108 = v92;
                  if ( v92 >= 0 )
                  {
                    v43 = v120;
                    if ( (*(_BYTE *)(v120 + 16) & 0x40) == 0 || v117 )
                    {
                      v60 = v92;
                    }
                    else
                    {
                      v150 = *(_DWORD *)(v120 + 184);
                      v149 = 1;
                      v108 = 0;
                    }
                    if ( v147 && v144[0] && (int)BMPCompress::hrRunCompression((BMPCompress *)v144) < 0 )
                    {
                      v50 = 255;
                      v146 = 255;
                    }
                    else
                    {
                      v50 = v146;
                    }
                    `vector destructor iterator'((char *)v148, v82, v83, v84);
                    if ( v50 == 255 )
                      goto LABEL_134;
                    v65 = v119;
                    v54 = v115;
                    goto LABEL_55;
                  }
                  `vector destructor iterator'((char *)v148, v82, v83, v84);
                }
LABEL_99:
                BMPConv::~BMPConv((BMPConv *)&v126);
                BMPConv::~BMPConv((BMPConv *)&v135);
                v60 = v108;
LABEL_100:
                LocalFree(hMem);
                v35 = v124;
LABEL_101:
                if ( v35 )
                  LocalFree(v35);
LABEL_103:
                if ( pso )
                {
                  EngUnlockSurface(pso);
                  if ( hsurf )
                  {
                    if ( !EngDeleteSurface(hsurf) )
                      return 0;
                  }
                }
                return v60;
              }
              v43 = v120;
              v44 = v114;
LABEL_55:
              v45 = 255;
              v142 = &v65[v121];
              v46 = 0;
              v110 = 0;
              v116 = 0;
              v112 = 0;
              while ( v37 > 0 )
              {
                v47 = pvScan0;
                if ( (*(_BYTE *)(v43 + 16) & 0x40) != 0 && !v117 )
                {
                  v47 = v124;
                  v108 = hrChangePixelColorInScanLine(pvScan0, v54, v44, *(_DWORD *)(v43 + 184), v124, v118);
                  if ( v108 < 0 )
                    goto LABEL_99;
                }
                if ( v50 == 3 )
                {
                  v48 = BMPConv::PubConvertBMP((BMPConv *)&v135, v47, v118);
                  if ( DWORD2(v137) == 3 )
                  {
                    v49 = v140;
                  }
                  else
                  {
                    v49 = HIDWORD(v137);
                    if ( DWORD2(v137) == 1 )
                      v49 = HIDWORD(v138);
                  }
                }
                else
                {
                  DWORD2(v128) = 1;
                  v48 = BMPConv::PubConvertBMP((BMPConv *)&v126, v47, v118);
                  if ( DWORD2(v128) == 3 )
                  {
                    v49 = v131;
                  }
                  else
                  {
                    v49 = HIDWORD(v128);
                    if ( DWORD2(v128) == 1 )
                      v49 = HIDWORD(Size[1]);
                  }
                  if ( v49 >= v118 )
                  {
                    v50 = 0;
                    DWORD2(v128) = 0;
                    v48 = BMPConv::PubConvertBMP((BMPConv *)&v126, v47, v118);
                    if ( DWORD2(v128) == 3 )
                    {
                      v49 = v131;
                    }
                    else
                    {
                      v49 = HIDWORD(v128);
                      if ( DWORD2(v128) == 1 )
                        v49 = HIDWORD(Size[1]);
                    }
                  }
                  else
                  {
                    v50 = 1;
                  }
                }
                if ( v49 + v110 <= v121 && (v45 == v50 || v45 == 255) )
                {
                  v51 = v119;
                  v52 = v110;
                }
                else
                {
                  if ( v45 == 255 )
                    v45 = v50;
                  if ( v110 )
                  {
                    v56 = *(XLOutput **)(*((_QWORD *)a1 + 1) + 160LL);
                    XLOutput::Send_uint16(v56, v112);
                    XLOutput::Send_attr_ubyte((__int64)v56, 109);
                    XLOutput::Send_uint16(v56, v116);
                    XLOutput::Send_attr_ubyte((__int64)v56, 99);
                    XLOutput::SetCompressMode(v56, v45);
                    XLWrite::WriteByte(v56, 177);
                    XLWrite::Flush(v56, a1);
                    if ( v110 > 0xFF )
                    {
                      LOBYTE(v151) = -6;
                      v57 = 5;
                      *(_DWORD *)((char *)&v151 + 1) = v110;
                    }
                    else
                    {
                      LOBYTE(v151) = -5;
                      v57 = 2;
                      BYTE1(v151) = v110;
                    }
                    WriteSpoolBuf((__int64)a1, &v151, v57);
                    WriteSpoolBuf((__int64)a1, hMem, v110);
                    v58 = v116 + v112;
                    v112 += v116;
                    if ( v49 > v121 )
                    {
                      BSendReadImageData((__int64)a1, v45, v48, v58, 1u, v49);
                      v49 = 0;
                      ++v112;
                    }
                  }
                  else
                  {
                    BSendReadImageData((__int64)a1, v45, v48, v112, 1u, v49);
                    v49 = 0;
                    ++v112;
                  }
                  v51 = hMem;
                  v52 = 0;
                  v110 = 0;
                  v116 = 0;
                  v119 = hMem;
                }
                if ( !v48 )
                  goto LABEL_99;
                --v37;
                if ( v49 )
                {
                  v53 = &v51[v49];
                  if ( v53 <= v142 )
                  {
                    memcpy_0(v51, v48, v49);
                    v119 = v53;
                    ++v116;
                    v51 = v53;
                    v110 = v49 + v52;
                  }
                }
                v45 = v50;
                if ( v50 || (v59 = (((v114 * v111 + 31) >> 3) & 0x1FFFFFFC) - v49) == 0 )
                {
                  v46 = v110;
                }
                else
                {
                  memset_0(v51, 0, v59);
                  v46 = v59 + v110;
                  v119 += v59;
                  v110 += v59;
                }
                v43 = v120;
                v44 = v114;
                v54 = v115;
                pvScan0 += a2->lDelta;
              }
              if ( v46 )
                BSendReadImageData((__int64)a1, v50, hMem, v112, v116, v46);
              XLWrite::WriteByte(v109, 178);
              XLWrite::Flush(v109, a1);
              goto LABEL_99;
            }
LABEL_187:
            if ( a4 && (a4->flXlate & 2) != 0 && (a4->pulXlate || XLATEOBJ_piVector(a4)) )
              goto LABEL_39;
            v33 = v109;
            if ( v102 == 3 )
            {
              v20 = 2;
              v111 = 24;
              goto LABEL_34;
            }
            v20 = 0;
          }
          else
          {
            v20 = 0;
LABEL_32:
            v33 = v109;
          }
          v111 = 8;
LABEL_34:
          XLOutput::SetColorSpace(v33, (*((_DWORD *)v109 + 71) == 3) + 1);
LABEL_40:
          v117 = 0;
          goto LABEL_41;
        default:
          goto LABEL_32;
      }
    }
    XLWrite::Flush(v109, v18);
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000fe80  push    rbp
0x18000fe82  push    rbx
0x18000fe83  push    rsi
0x18000fe84  push    rdi
0x18000fe85  push    r12
0x18000fe87  push    r13
0x18000fe89  push    r14
0x18000fe8b  push    r15
0x18000fe8d  lea     rbp, [rsp-298h]
0x18000fe95  sub     rsp, 398h
0x18000fe9c  mov     rax, cs:__security_cookie
0x18000fea3  xor     rax, rsp
0x18000fea6  mov     [rbp+2D0h+var_48], rax
0x18000fead  mov     r15, [rbp+2D0h+arg_28]
0x18000feb4  mov     r13, r9
0x18000feb7  mov     rbx, [rbp+2D0h+arg_30]
0x18000febe  mov     r14, [rbp+2D0h+arg_20]
0x18000fec5  mov     r12, [rbp+2D0h+arg_38]
0x18000fecc  mov     [rbp+2D0h+var_50], r9
0x18000fed3  mov     r9, r8
0x18000fed6  mov     [rbp+2D0h+psoSrc], rdx
0x18000feda  mov     [rbp+2D0h+var_350], rcx
0x18000fede  test    rcx, rcx
0x18000fee1  jz      loc_18001060B
0x18000fee7  test    rbx, rbx
0x18000feea  jz      loc_18001060B
0x18000fef0  mov     eax, [rbx]
0x18000fef2  cmp     [rbx+8], eax
0x18000fef5  jl      loc_180010FAF
0x18000fefb  mov     eax, [rbx+4]
0x18000fefe  cmp     [rbx+0Ch], eax
0x18000ff01  jl      loc_180010FAF
0x18000ff07  mov     rax, [rcx+8]
0x18000ff0b  mov     r8, rcx; struct _DEVOBJ *
0x18000ff0e  mov     rdx, r9; struct _CLIPOBJ *
0x18000ff11  mov     [rbp+2D0h+var_328], rax
0x18000ff15  mov     rdi, [rax+0A0h]
0x18000ff1c  mov     rcx, rdi; this
0x18000ff1f  mov     [rsp+3D0h+var_368], rdi
0x18000ff24  call    ?SetClip@XLOutput@@QEAAJPEAU_CLIPOBJ@@PEAU_DEVOBJ@@@Z; XLOutput::SetClip(_CLIPOBJ *,_DEVOBJ *)
0x18000ff29  mov     [rsp+3D0h+var_370], eax
0x18000ff2d  test    eax, eax
0x18000ff2f  js      loc_1800105C6
0x18000ff35  mov     r8d, [rbx+4]; __int16
0x18000ff39  mov     rcx, rdi; this
0x18000ff3c  mov     edx, [rbx]; __int16
0x18000ff3e  call    ?SetCursor@XLOutput@@QEAAJJJ@Z; XLOutput::SetCursor(long,long)
0x18000ff43  mov     rax, [rsp+3D0h+var_368]
0x18000ff48  add     rdi, 0CCh
0x18000ff4f  movzx   esi, byte ptr [rbp+2D0h+arg_40]
0x18000ff56  test    rax, rax
0x18000ff59  mov     ecx, 0ACh
0x18000ff5e  cmovz   rdi, rcx
0x18000ff62  cmp     esi, [rdi]
0x18000ff64  jnz     loc_18001025A
0x18000ff6a  lea     rdx, cs:180000000h
0x18000ff71  cmp     esi, 0FFh
0x18000ff77  jnz     loc_180010A7F
0x18000ff7d  mov     edi, 1
0x18000ff82  xor     r10d, r10d
0x18000ff85  test    dil, 1
0x18000ff89  jnz     loc_180010B15
0x18000ff8f  mov     esi, edi
0x18000ff91  and     esi, 4
0x18000ff94  test    dil, 0Ah
0x18000ff98  mov     rdi, [rsp+3D0h+var_368]
0x18000ff9d  jnz     loc_180010168
0x18000ffa3  mov     r14, [rbp+2D0h+var_350]
0x18000ffa7  test    esi, esi
0x18000ffa9  jz      loc_180010FA6
0x18000ffaf  mov     rsi, [rbp+2D0h+psoSrc]
0x18000ffb3  mov     [rbp+2D0h+hsurf], r10
0x18000ffb7  test    rsi, rsi
0x18000ffba  jz      loc_180010F96
0x18000ffc0  test    r15, r15
0x18000ffc3  jz      loc_180010F96
0x18000ffc9  mov     edi, [rsi+48h]
0x18000ffcc  cmp     edi, 6
0x18000ffcf  jnz     loc_180010C76
0x18000ffd5  mov     ecx, edi
0x18000ffd7  mov     r14d, r10d
0x18000ffda  call    ?UlBPPtoNum@@YAKW4BPP@@@Z; UlBPPtoNum(BPP)
0x18000ffdf  mov     ecx, [r15+0Ch]
0x18000ffe3  xorps   xmm0, xmm0
0x18000ffe6  sub     ecx, [r15+4]
0x18000ffea  mov     r8d, [rbx+8]
0x18000ffee  mov     edx, ecx
0x18000fff0  sub     r8d, [rbx]; int
0x18000fff3  mov     r9d, [rbx+0Ch]
0x18000fff7  sub     r9d, [rbx+4]; int
0x18000fffb  neg     edx
0x18000fffd  mov     [rbp+2D0h+var_344], eax
0x180010000  mov     [rbp+2D0h+pso], r10
0x180010004  cmovs   edx, ecx
0x180010007  mov     ecx, [r15+8]
0x18001000b  sub     ecx, [r15]
0x18001000e  mov     eax, ecx
0x180010010  neg     eax
0x180010012  movdqu  xmmword ptr [rbp+2D0h+var_1F8.left], xmm0
0x18001001a  cmovs   eax, ecx
0x18001001d  mov     ecx, r9d
0x180010020  imul    edx, eax
0x180010023  mov     eax, r8d
0x180010026  neg     ecx
0x180010028  cmovs   ecx, r9d
0x18001002c  neg     eax
0x18001002e  cmovs   eax, r8d
0x180010032  imul    ecx, eax
0x180010035  cmp     ecx, edx
0x180010037  jl      loc_1800101B7
0x18001003d  mov     rax, [rbp+2D0h+var_350]
0x180010041  mov     r12, [rsp+3D0h+var_368]
0x180010046  mov     rcx, r12
0x180010049  mov     edx, [rax+74h]
0x18001004c  shr     edx, 7
0x18001004f  and     edx, 1
0x180010052  call    ?SetSourceTxMode@XLOutput@@QEAAJW4TxMode@@@Z; XLOutput::SetSourceTxMode(TxMode)
0x180010057  lea     rsi, [r12+104h]
0x18001005f  test    r12, r12
0x180010062  jnz     short loc_180010069
0x180010064  mov     esi, 0E4h
0x180010069  cmp     dword ptr [rsi], 0
0x18001006c  jnz     loc_180010CAA
0x180010072  lea     eax, [rdi-1]; switch 6 cases
0x180010075  cmp     eax, 5
0x180010078  jbe     loc_180010CD1
0x18001007e  xor     edx, edx; jumptable 0000000180010CEC default case
0x180010080  mov     rcx, r12
0x180010083  mov     [rsp+3D0h+var_35C], 8
0x18001008b  cmp     dword ptr [r12+11Ch], 3
0x180010094  setz    dl
0x180010097  inc     edx
0x180010099  call    ?SetColorSpace@XLOutput@@QEAAJW4ColorSpace@@@Z; XLOutput::SetColorSpace(ColorSpace)
0x18001009e  jmp     short loc_180010101
0x1800100a0  xor     r14d, r14d; jumptable 0000000180010CEC cases 3,4
0x1800100a3  mov     [rsp+3D0h+var_35C], 0
0x1800100ab  cmp     esi, 3
0x1800100ae  setz    r14b
0x1800100b2  mov     ecx, r14d
0x1800100b5  test    r14d, r14d
0x1800100b8  jz      short def_180010CEC; jumptable 0000000180010CEC default case
0x1800100ba  sub     ecx, 1
0x1800100bd  jz      loc_180010CF8
0x1800100c3  sub     ecx, 1
0x1800100c6  jz      loc_180010D5C
0x1800100cc  cmp     ecx, 1
0x1800100cf  jz      loc_180010D5C
0x1800100d5  cmp     r14d, 1
0x1800100d9  jz      loc_180010CFF
0x1800100df  xor     edx, edx
0x1800100e1  mov     rcx, r12
0x1800100e4  cmp     dword ptr [r12+11Ch], 3
0x1800100ed  setz    dl
0x1800100f0  inc     edx
0x1800100f2  call    ?SetColorSpace@XLOutput@@QEAAJW4ColorSpace@@@Z; XLOutput::SetColorSpace(ColorSpace)
0x1800100f7  cmp     r14d, 1
0x1800100fb  jz      loc_180010D71
0x180010101  mov     [rbp+2D0h+var_33C], 0
0x180010108  xor     r13d, r13d
0x18001010b  mov     dl, 6Ah ; 'j'; unsigned __int8
0x18001010d  mov     rcx, r12; this
0x180010110  mov     [rbp+2D0h+var_308], r13
0x180010114  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180010119  mov     eax, [r15+8]
0x18001011d  mov     r8d, 0FFFFFFFFh
0x180010123  sub     eax, [r15]
0x180010126  mov     ecx, [rsp+3D0h+var_35C]
0x18001012a  mov     edx, [rbp+2D0h+var_344]
0x18001012d  mov     r12d, [r15+0Ch]
0x180010131  sub     r12d, [r15+4]
0x180010135  imul    edx, eax
0x180010138  imul    rcx, rax
0x18001013c  add     edx, 7
0x18001013f  mov     [rbp+2D0h+var_348], eax
0x180010142  shr     edx, 3; uBytes
0x180010145  mov     [rbp+2D0h+var_338], edx
0x180010148  cmp     rcx, r8
0x18001014b  jbe     loc_180010956
0x180010151  cmp     edx, 4000h
0x180010157  jbe     loc_180010DFD
0x18001015d  lea     esi, [rdx+3]
0x180010160  and     esi, 0FFFFFFFCh
0x180010163  jmp     loc_180010E02
0x180010168  xor     edx, edx
0x18001016a  mov     rcx, rdi
0x18001016d  call    ?SetSourceTxMode@XLOutput@@QEAAJW4TxMode@@@Z; XLOutput::SetSourceTxMode(TxMode)
0x180010172  xor     edx, edx
0x180010174  mov     rcx, rdi
0x180010177  call    ?SetPaintTxMode@XLOutput@@QEAAJW4TxMode@@@Z; XLOutput::SetPaintTxMode(TxMode)
0x18001017c  mov     r9, [rbp+2D0h+var_350]; struct _DEVOBJ *
0x180010180  mov     rdx, r14; struct _BRUSHOBJ *
0x180010183  mov     rcx, rdi; this
0x180010186  call    ?SetBrush@XLOutput@@QEAAJPEAU_BRUSHOBJ@@PEBU_POINTL@@PEAU_DEVOBJ@@@Z; XLOutput::SetBrush(_BRUSHOBJ *,_POINTL const *,_DEVOBJ *)
0x18001018b  mov     r14, [rbp+2D0h+var_350]
0x18001018f  xor     edx, edx; struct _BRUSHOBJ *
0x180010191  mov     r9, r14; struct _DEVOBJ *
0x180010194  mov     rcx, rdi; this
0x180010197  call    ?SetPenColor@XLOutput@@QEAAJPEAU_BRUSHOBJ@@PEAU_POINTL@@PEAU_DEVOBJ@@@Z; XLOutput::SetPenColor(_BRUSHOBJ *,_POINTL *,_DEVOBJ *)
0x18001019c  test    esi, esi
0x18001019e  jz      loc_180010C52
0x1800101a4  mov     rdx, r14; struct _DEVOBJ *
0x1800101a7  mov     rcx, rdi; this
0x1800101aa  call    ?Flush@XLWrite@@QEAAJPEAU_DEVOBJ@@@Z; XLWrite::Flush(_DEVOBJ *)
0x1800101af  xor     r10d, r10d
0x1800101b2  jmp     loc_18000FFA7
0x1800101b7  mov     qword ptr [rbp+2D0h+var_280.x], r10
0x1800101bb  mov     [rbp+2D0h+var_1F8.right], r8d
0x1800101c2  mov     [rbp+2D0h+var_1F8.bottom], r9d
0x1800101c9  test    r12, r12
0x1800101cc  jz      short loc_1800101D6
0x1800101ce  mov     rax, [r12]
0x1800101d2  mov     qword ptr [rbp+2D0h+var_280.x], rax
0x1800101d6  mov     rcx, [rbp+2D0h+var_350]; int
0x1800101da  lea     rdx, [rbp+2D0h+hsurf]; int
0x1800101de  mov     dword ptr [rsp+3D0h+pxlo], edi; iFormat
0x1800101e2  call    CreateBitmapSURFOBJ
0x1800101e7  mov     [rbp+2D0h+pso], rax
0x1800101eb  mov     r12, rax
0x1800101ee  test    rax, rax
0x1800101f1  jz      loc_18001003D
0x1800101f7  mov     [rsp+3D0h+iMode], 3; iMode
0x1800101ff  lea     rax, [rbp+2D0h+var_1F8]
0x180010206  xor     ecx, ecx
0x180010208  xor     r9d, r9d; pco
0x18001020b  mov     [rsp+3D0h+pptlMask], rcx; pptlMask
0x180010210  xor     r8d, r8d; psoMask
0x180010213  mov     [rsp+3D0h+prclSrc], r15; prclSrc
0x180010218  mov     rdx, rsi; psoSrc
0x18001021b  mov     [rsp+3D0h+prclDest], rax; prclDest
0x180010220  lea     rax, [rbp+2D0h+var_280]
0x180010224  mov     [rsp+3D0h+pptlHTOrg], rax; pptlHTOrg
0x180010229  mov     [rsp+3D0h+pca], rcx; pca
0x18001022e  mov     [rsp+3D0h+pxlo], rcx; pxlo
0x180010233  mov     rcx, r12; psoDest
0x180010236  call    cs:__imp_EngStretchBlt
0x18001023d  nop     dword ptr [rax+rax+00h]
0x180010242  test    eax, eax
0x180010244  jz      loc_18001003D
0x18001024a  mov     [rbp+2D0h+psoSrc], r12
0x18001024e  lea     r15, [rbp+2D0h+var_1F8]
0x180010255  jmp     loc_18001003D
0x18001025a  movzx   edx, sil; unsigned __int8
0x18001025e  mov     rcx, rax; this
0x180010261  call    ?Send_ubyte@XLOutput@@QEAAJE@Z; XLOutput::Send_ubyte(uchar)
0x180010266  test    eax, eax
0x180010268  jz      loc_180010A55
0x18001026e  mov     rax, [rsp+3D0h+var_368]
0x180010273  jmp     loc_18000FF6A
0x180010278  mov     rdi, [rbp+2D0h+var_328]
0x18001027c  mov     r14d, [rbp+2D0h+var_348]
0x180010280  mov     rax, [rbp+2D0h+var_320]
0x180010284  mov     r13d, 0FFh
0x18001028a  mov     eax, eax
0x18001028c  add     rax, r9
0x18001028f  mov     [rbp+2D0h+var_200], rax
0x180010296  xor     eax, eax
0x180010298  mov     ecx, eax
0x18001029a  mov     [rsp+3D0h+var_360], eax
0x18001029e  mov     [rbp+2D0h+var_340], eax
0x1800102a1  mov     [rsp+3D0h+var_358], eax
0x1800102a5  test    r12d, r12d
0x1800102a8  jle     loc_180010547
0x1800102ae  test    byte ptr [rdi+10h], 40h
0x1800102b2  mov     rbx, r15
0x1800102b5  jnz     loc_180010EAB
0x1800102bb  mov     rdx, rbx; unsigned __int8 *
0x1800102be  cmp     esi, 3
0x1800102c1  jz      loc_18001038D
0x1800102c7  mov     esi, [rbp+2D0h+var_338]
0x1800102ca  lea     rcx, [rbp+2D0h+var_2F0]; this
0x1800102ce  mov     r8d, esi; unsigned int
0x1800102d1  mov     dword ptr [rbp+2D0h+var_2D0+8], 1
0x1800102d8  call    ?PubConvertBMP@BMPConv@@QEAAPEAEPEAEK@Z; BMPConv::PubConvertBMP(uchar *,ulong)
0x1800102dd  mov     r14, rax
0x1800102e0  mov     eax, dword ptr [rbp+2D0h+var_2D0+8]
0x1800102e3  cmp     eax, 3
0x1800102e6  jz      loc_1800103C1
0x1800102ec  mov     edi, dword ptr [rbp+2D0h+var_2D0+0Ch]
0x1800102ef  cmp     eax, 1
0x1800102f2  cmovz   edi, dword ptr [rbp+2D0h+Size+0Ch]
0x1800102f6  cmp     edi, esi
0x1800102f8  jnb     loc_180010510
0x1800102fe  mov     esi, 1
0x180010303  mov     ecx, [rsp+3D0h+var_360]
0x180010307  lea     eax, [rdi+rcx]
0x18001030a  cmp     eax, dword ptr [rbp+2D0h+var_320]
0x18001030d  ja      loc_1800103D6
0x180010313  cmp     r13d, esi
0x180010316  jnz     loc_1800103C9
0x18001031c  mov     r9, [rbp+2D0h+var_330]
0x180010320  mov     r13d, [rsp+3D0h+var_360]
0x180010325  test    r14, r14
0x180010328  jz      loc_180010584
0x18001032e  dec     r12d
0x180010331  test    edi, edi
0x180010333  jz      short loc_180010362
0x180010335  mov     r8d, edi; Size
0x180010338  lea     rbx, [r8+r9]
0x18001033c  cmp     rbx, [rbp+2D0h+var_200]
0x180010343  ja      short loc_180010362
  ... truncated ...
```
