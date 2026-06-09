# CommonRopBlt(_DEVOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_BRUSHOBJ *,_RECTL *,_RECTL *,_POINTL *,ulong,_POINTFIX *)

- ea: `0x18000fde0`
- end: `0x180010ff8`
- name: `?CommonRopBlt@@YAJPEAU_DEVOBJ@@PEAU_SURFOBJ@@PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_BRUSHOBJ@@PEAU_RECTL@@5PEAU_POINTL@@KPEAU_POINTFIX@@@Z`
- size: `4632`
- prototype: `__int64 __fastcall(struct _DEVOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _BRUSHOBJ *, RECTL *prclSrc, struct _RECTL *, struct _POINTL *, unsigned __int8)`
- caller_count: `5`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x18000f490`
- `0x18000f5d0`
- `0x18006ddc0`
- `0x18006deb0`
- `0x18006dfb0`

## callees

- `0x18000f364`
- `0x18000f578`
- `0x18000f6bc`
- `0x18000f700`
- `0x18000f7ac`
- `0x18000fa40`
- `0x18000faa8`
- `0x18000fb0c`
- `0x18000fde0`
- `0x1800113a0`
- `0x180011dd0`
- `0x180011e70`
- `0x180011f0c`
- `0x180011fc0`
- `0x180012118`
- `0x180012298`
- `0x180012328`
- `0x18001241c`
- `0x180012590`
- `0x18001265c`
- `0x18001348c`
- `0x180013944`
- `0x1800152e0`
- `0x1800155b0`
- `0x180042598`
- `0x180044100`
- `0x180044494`
- `0x1800446c4`
- `0x1800452d0`
- `0x180045348`
- `0x180045474`
- `0x1800487e0`
- `0x1800491dc`
- `0x18006c954`
- `0x18006cd2c`
- `0x18006cd74`
- `0x18006cdd4`
- `0x180074580`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800104f9`
- `KERNEL32!LocalFree` at `0x180010d0a`
- `KERNEL32!LocalFree` at `0x180010e7c`
- `KERNEL32!LocalFree` at `0x1800104f9`
- `KERNEL32!LocalFree` at `0x180010d0a`
- `KERNEL32!LocalFree` at `0x180010e7c`
- `KERNEL32!LocalAlloc` at `0x180010584`
- `KERNEL32!LocalAlloc` at `0x180010d4b`
- `KERNEL32!LocalAlloc` at `0x180010584`
- `KERNEL32!LocalAlloc` at `0x180010d4b`
- `GDI32!EngStretchBlt` at `0x180010196`
- `GDI32!EngStretchBlt` at `0x180010196`
- `GDI32!EngUnlockSurface` at `0x180010e8a`
- `GDI32!EngUnlockSurface` at `0x180010e8a`
- `GDI32!EngDeleteSurface` at `0x180010e9d`
- `GDI32!EngDeleteSurface` at `0x180010e9d`
- `GDI32!XLATEOBJ_piVector` at `0x180010c61`
- `GDI32!XLATEOBJ_piVector` at `0x180010cc9`
- `GDI32!XLATEOBJ_piVector` at `0x180010c61`
- `GDI32!XLATEOBJ_piVector` at `0x180010cc9`

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
  XLOutput *v13; // rax
  __int64 v14; // rdi
  int v15; // esi
  unsigned __int64 v16; // rdx
  int v17; // edi
  int v18; // esi
  struct _DEVOBJ *v19; // r14
  ULONG iBitmapFormat; // edi
  int v21; // r14d
  unsigned int v22; // eax
  POINTL v23; // r10
  int v24; // r8d
  int v25; // r9d
  int v26; // edx
  int v27; // ecx
  bool v28; // sf
  int v29; // eax
  int v30; // edx
  int v31; // ecx
  int v32; // eax
  __int64 v33; // rsi
  int v34; // edx
  XLWrite *v35; // rcx
  unsigned int v36; // edx
  unsigned __int8 *v37; // r13
  __int64 v38; // rax
  int v39; // r12d
  unsigned __int64 v40; // rcx
  SIZE_T v41; // rdx
  unsigned __int64 v42; // rsi
  const struct _POINTL *v43; // r8
  struct _POINTL *v44; // r8
  __int64 v45; // rdi
  unsigned int v46; // r14d
  unsigned int v47; // r13d
  unsigned int v48; // ecx
  unsigned __int8 *v49; // rbx
  unsigned __int8 *v50; // r14
  unsigned int v51; // edi
  unsigned int v52; // esi
  char *v53; // r9
  unsigned int v54; // r13d
  char *v55; // rbx
  unsigned int v56; // r11d
  unsigned __int8 *pvScan0; // r15
  XLOutput *v58; // rbx
  __int64 v59; // r8
  unsigned int v60; // ecx
  unsigned int v61; // r14d
  unsigned int v62; // ebx
  int v63; // esi
  int v64; // r13d
  unsigned int v65; // eax
  __int64 v66; // rcx
  char *v67; // r9
  struct _XLATEOBJ *v68; // r13
  unsigned int v69; // ebx
  int v70; // eax
  __int64 v71; // rdx
  __int64 v72; // r8
  unsigned __int64 v73; // rdx
  __int64 v74; // rcx
  unsigned __int64 v75; // r8
  void (*v76)(void *); // r9
  __int128 v77; // xmm1
  __int64 v78; // rcx
  __int128 v79; // xmm0
  __int128 v80; // xmm1
  __int128 v81; // xmm0
  __int128 v82; // xmm1
  __int64 v83; // rax
  unsigned __int64 v84; // rdx
  unsigned __int64 v85; // r8
  void (*v86)(void *); // r9
  unsigned __int64 v87; // rsi
  __int128 v88; // xmm1
  __int64 v89; // rcx
  __int128 v90; // xmm0
  __int128 v91; // xmm1
  __int128 v92; // xmm0
  __int128 v93; // xmm1
  int v94; // eax
  int v95; // eax
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rcx
  __int64 v100; // rax
  __int64 v101; // rax
  struct _POINTL *v102; // r8
  int v103; // esi
  unsigned int *pulXlate; // rax
  ULONG cEntries; // r8d
  unsigned int *v106; // rax
  unsigned int v107; // edx
  unsigned int *v108; // rsi
  int v109; // [rsp+60h] [rbp-A0h]
  XLWrite *v110; // [rsp+68h] [rbp-98h]
  unsigned int v111; // [rsp+70h] [rbp-90h]
  unsigned int v112; // [rsp+74h] [rbp-8Ch]
  unsigned int v113; // [rsp+78h] [rbp-88h]
  unsigned int v115; // [rsp+88h] [rbp-78h]
  unsigned int v116; // [rsp+8Ch] [rbp-74h]
  int v117; // [rsp+90h] [rbp-70h]
  unsigned int v118; // [rsp+94h] [rbp-6Ch]
  unsigned int v119; // [rsp+98h] [rbp-68h]
  char *v120; // [rsp+A0h] [rbp-60h]
  __int64 v121; // [rsp+A8h] [rbp-58h]
  unsigned int v122; // [rsp+B0h] [rbp-50h]
  char *hMem; // [rsp+C0h] [rbp-40h]
  unsigned __int8 *v125; // [rsp+C8h] [rbp-38h]
  SURFOBJ *pso; // [rsp+D0h] [rbp-30h]
  __int128 v127; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v128; // [rsp+F0h] [rbp-10h]
  __int128 v129; // [rsp+100h] [rbp+0h]
  size_t Size[2]; // [rsp+110h] [rbp+10h]
  __int128 v131; // [rsp+120h] [rbp+20h]
  __int128 v132; // [rsp+130h] [rbp+30h]
  __int64 v133; // [rsp+140h] [rbp+40h]
  POINTL pptlHTOrg; // [rsp+150h] [rbp+50h] BYREF
  HSURF hsurf; // [rsp+158h] [rbp+58h] BYREF
  __int128 v136; // [rsp+160h] [rbp+60h] BYREF
  __int128 v137; // [rsp+170h] [rbp+70h]
  __int128 v138; // [rsp+180h] [rbp+80h]
  __int128 v139; // [rsp+190h] [rbp+90h]
  __int128 v140; // [rsp+1A0h] [rbp+A0h]
  __int128 v141; // [rsp+1B0h] [rbp+B0h]
  __int64 v142; // [rsp+1C0h] [rbp+C0h]
  char *v143; // [rsp+1D0h] [rbp+D0h]
  RECTL prclDest[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  _QWORD v145[3]; // [rsp+200h] [rbp+100h] BYREF
  __int16 v146; // [rsp+21Ch] [rbp+11Ch]
  int v147; // [rsp+220h] [rbp+120h]
  unsigned int v148; // [rsp+224h] [rbp+124h]
  _OWORD v149[20]; // [rsp+228h] [rbp+128h] BYREF
  int v150; // [rsp+370h] [rbp+270h]
  int v151; // [rsp+374h] [rbp+274h]
  struct _XLATEOBJ *v152; // [rsp+380h] [rbp+280h] BYREF

  v9 = prclSrc;
  v152 = a4;
  if ( !a1 || !a7 )
    return 2147549183LL;
  if ( a7->right < a7->left || a7->bottom < a7->top )
    return 1;
  v121 = *((_QWORD *)a1 + 1);
  v11 = *(XLOutput **)(v121 + 160);
  v110 = v11;
  result = XLOutput::SetClip(v11, a3, a1);
  v109 = result;
  if ( (int)result >= 0 )
  {
    XLOutput::SetCursor(v11, a7->left, a7->top);
    v13 = v11;
    v14 = (__int64)v11 + 204;
    v15 = a9;
    if ( !v110 )
      v14 = 172;
    if ( a9 != *(_DWORD *)v14 )
    {
      if ( !(unsigned int)XLOutput::Send_ubyte(v110, a9) && !(unsigned int)XLOutput::Send_attr_ubyte(v110, 44) )
      {
        XLWrite::WriteByte(v110, 0x7Bu);
        *(_DWORD *)v14 = a9;
      }
      v13 = v110;
    }
    v16 = 0x180000000uLL;
    if ( a9 == 255 )
    {
LABEL_10:
      LOBYTE(v17) = 1;
    }
    else
    {
      switch ( a9 )
      {
        case 0u:
          v13 = v110;
          goto LABEL_10;
        case 0xFu:
        case 0xF0u:
          v13 = v110;
          LOBYTE(v17) = 2;
          break;
        case 0x11u:
        case 0x33u:
        case 0x44u:
        case 0x66u:
        case 0x77u:
        case 0x99u:
        case 0xCCu:
        case 0xDDu:
          v13 = v110;
          LOBYTE(v17) = 4;
          break;
        case 0xAAu:
          v13 = v110;
          LOBYTE(v17) = 8;
          break;
        default:
          v16 = ((a9 ^ (a9 >> 2)) & 0x33) != 0 ? 4 : 0;
          v17 = (((a9 ^ (a9 >> 2)) & 0x33) != 0 ? 4 : 0) | 2;
          if ( a9 >> 4 == (a9 & 0xF) )
            LOBYTE(v17) = ((a9 ^ (a9 >> 2)) & 0x33) != 0 ? 4 : 0;
          v13 = v110;
          if ( ((a9 ^ (a9 >> 1)) & 0x55) != 0 )
            LOBYTE(v17) = v17 | 8;
          break;
      }
    }
    if ( (v17 & 1) != 0 )
    {
      memset(prclDest, 0, 28);
      XLOutput::SetSourceTxMode(v13, 0);
      XLOutput::SetPaintTxMode(v110, 0);
      v95 = *((_DWORD *)v110 + 71);
      if ( a9 )
      {
        if ( v95 == 3 )
        {
          v15 = 0xFFFFFF;
          XLOutput::SetRGBColor(v110, 0xFFFFFFu);
        }
        else
        {
          XLOutput::SetGrayLevel(v110, 0xFFu);
          v15 = 0xFFFFFF;
        }
      }
      else if ( v95 == 3 )
      {
        XLOutput::SetRGBColor(v110, 0);
      }
      else
      {
        XLOutput::SetGrayLevel(v110, 0);
        v15 = 0;
      }
      v96 = (__int64)v110 + 84;
      if ( !v110 )
        v96 = 4;
      *(_DWORD *)v96 = 2;
      v97 = (__int64)v110 + 88;
      if ( !v110 )
        v97 = 8;
      *(_DWORD *)v97 = 0;
      v98 = (__int64)v110 + 92;
      if ( !v110 )
        v98 = 12;
      v99 = (__int64)v110 + 96;
      *(_DWORD *)v98 = -1;
      if ( !v110 )
        v99 = 16;
      *(_DWORD *)v99 = prclDest[1].left;
      v100 = (__int64)v110 + 100;
      if ( !v110 )
        v100 = 20;
      *(_DWORD *)v100 = v15;
      v101 = (__int64)v110 + 104;
      if ( !v110 )
        v101 = 24;
      *(_DWORD *)v101 = -1;
      XLWrite::WriteByte(v110, 0x63u);
      XLOutput::SetPenColor(v110, 0, v102, a1);
      v18 = v17 & 4;
      if ( (v17 & 4) == 0 )
      {
        XLWrite::WriteByte(v110, 0x85u);
        XLOutput::RectanglePath(v110, a7);
        XLWrite::WriteByte(v110, 0x86u);
      }
      XLWrite::Flush(v110, a1);
    }
    else
    {
      v18 = v17 & 4;
    }
    if ( (v17 & 0xA) != 0 )
    {
      XLOutput::SetSourceTxMode(v110, 0);
      XLOutput::SetPaintTxMode(v110, 0);
      XLOutput::SetBrush(v110, a5, v43, a1);
      v19 = a1;
      XLOutput::SetPenColor(v110, 0, v44, a1);
      if ( !v18 )
      {
        XLWrite::WriteByte(v110, 0x85u);
        XLOutput::RectanglePath(v110, a7);
        XLWrite::WriteByte(v110, 0x86u);
      }
      XLWrite::Flush(v110, a1);
    }
    else
    {
      v19 = a1;
    }
    if ( !v18 )
      return (unsigned int)v109;
    hsurf = 0;
    if ( a2 && prclSrc )
    {
      iBitmapFormat = a2->iBitmapFormat;
      if ( iBitmapFormat != 6
        && (iBitmapFormat != 1 && iBitmapFormat != 2 && iBitmapFormat != 3 && iBitmapFormat - 4 > 1 || iBitmapFormat == 7) )
      {
        return 2147549183LL;
      }
      v21 = 0;
      v22 = UlBPPtoNum(iBitmapFormat, v16);
      v24 = a7->right - a7->left;
      v25 = a7->bottom - a7->top;
      v26 = prclSrc->top - prclSrc->bottom;
      v116 = v22;
      pso = (SURFOBJ *)v23;
      if ( v26 < 0 )
        v26 = prclSrc->bottom - prclSrc->top;
      v27 = prclSrc->right - prclSrc->left;
      v28 = prclSrc->left - prclSrc->right < 0;
      v29 = prclSrc->left - prclSrc->right;
      prclDest[0] = 0;
      if ( v28 )
        v29 = v27;
      v30 = v29 * v26;
      v31 = -v25;
      if ( v25 > 0 )
        v31 = v25;
      v32 = -v24;
      if ( v24 > 0 )
        v32 = v24;
      if ( v32 * v31 < v30 )
      {
        pptlHTOrg = v23;
        prclDest[0].right = v24;
        prclDest[0].bottom = v25;
        if ( a8 )
          pptlHTOrg = *a8;
        pso = CreateBitmapSURFOBJ((__int64)a1, &hsurf, v24, v25, iBitmapFormat);
        if ( pso && EngStretchBlt(pso, a2, 0, 0, 0, 0, &pptlHTOrg, prclDest, prclSrc, 0, 3u) )
        {
          a2 = pso;
          v9 = prclDest;
        }
      }
      XLOutput::SetSourceTxMode(v110, (*((_DWORD *)a1 + 29) >> 7) & 1);
      v33 = (__int64)v110 + 260;
      if ( !v110 )
        v33 = 228;
      if ( *(_DWORD *)v33 && !(unsigned int)XLOutput::SetTxMode(v110, 0) )
      {
        XLWrite::WriteByte(v110, 0x78u);
        *(_DWORD *)v33 = 0;
      }
      v103 = *((_DWORD *)v110 + 71);
      switch ( iBitmapFormat )
      {
        case 1u:
        case 2u:
          v21 = 1;
          goto LABEL_187;
        case 3u:
        case 4u:
          v112 = 0;
          v21 = v103 == 3;
          if ( v103 != 3 )
            goto LABEL_32;
          if ( v21 == 1 )
          {
LABEL_187:
            v112 = v116;
            goto LABEL_188;
          }
          if ( (unsigned int)(v21 - 2) < 2 )
            goto LABEL_196;
          goto LABEL_38;
        case 5u:
        case 6u:
          if ( v103 == 3 )
          {
            v21 = 2;
LABEL_196:
            v112 = 24;
LABEL_38:
            if ( v21 != 1 )
            {
LABEL_39:
              XLOutput::SetColorSpace(v110, (unsigned int)(*((_DWORD *)v110 + 71) == 3) + 1);
              if ( v21 != 1 )
                goto LABEL_40;
              if ( a4 )
              {
                if ( (a4->flXlate & 2) != 0 )
                {
                  pulXlate = a4->pulXlate;
                  if ( pulXlate || (pulXlate = XLATEOBJ_piVector(a4)) != 0 )
                  {
                    cEntries = a4->cEntries;
                    if ( (*(_BYTE *)(v121 + 16) & 0x40) != 0 )
                    {
                      v106 = PdwChangeTransparentPalette(*(_DWORD *)(v121 + 184), pulXlate, cEntries);
                      v108 = v106;
                      if ( !v106 )
                      {
LABEL_212:
                        v62 = v109;
                        goto LABEL_104;
                      }
                      XLOutput::SetPalette(v110, v107, a4->cEntries, v106);
                      LocalFree(v108);
                    }
                    else
                    {
                      XLOutput::SetPalette(v110, v36, cEntries, pulXlate);
                    }
                  }
                }
              }
              v118 = 1;
LABEL_41:
              v37 = 0;
              v125 = 0;
              XLWrite::WriteByte(v110, 0x6Au);
              v38 = (unsigned int)(v9->right - v9->left);
              v39 = v9->bottom - v9->top;
              v40 = v38 * v112;
              v115 = v9->right - v9->left;
              v41 = ((unsigned int)v38 * v116 + 7) >> 3;
              v119 = ((unsigned int)v38 * v116 + 7) >> 3;
              if ( v40 > 0xFFFFFFFF
                || (v87 = (unsigned int)(v40 + 31), (unsigned int)v87 < (unsigned int)v40)
                || (v42 = (unsigned int)v39 * ((v87 >> 3) & 0x1FFFFFFC), v122 = v42, v42 > 0xFFFFFFFF)
                || (unsigned int)v42 > 0x4000 )
              {
                if ( (unsigned int)v41 <= 0x4000 )
                  LODWORD(v42) = 0x4000;
                else
                  LODWORD(v42) = (v41 + 3) & 0xFFFFFFFC;
                v122 = v42;
              }
              if ( (*(_BYTE *)(v121 + 16) & 0x40) != 0 && !v118 )
              {
                v125 = (unsigned __int8 *)LocalAlloc(0, v41);
                v37 = v125;
                if ( !v125 )
                  goto LABEL_212;
              }
              v120 = (char *)LocalAlloc(0, (unsigned int)v42);
              if ( !v120 )
              {
                v62 = v109;
                goto LABEL_102;
              }
              v63 = a7->bottom - a7->top;
              v64 = a7->right - a7->left;
              XLOutput::SetOutputBPP(v110, v118, v112);
              if ( !(unsigned int)XLOutput::Send_uint16(v110, v115) )
                XLOutput::Send_attr_ubyte(v110, 108);
              if ( !(unsigned int)XLOutput::Send_uint16(v110, v39) )
                XLOutput::Send_attr_ubyte(v110, 107);
              if ( !(unsigned int)XLOutput::Send_uint16_xy(v110, v64, v63) )
                XLOutput::Send_attr_ubyte(v110, 103);
              XLWrite::WriteByte(v110, 0xB0u);
              XLWrite::Flush(v110, a1);
              v52 = 0;
              hMem = v120;
              *((_QWORD *)&v137 + 1) = 0;
              v138 = 0u;
              *(_QWORD *)&v139 = 0;
              DWORD2(v139) = 0;
              *(_QWORD *)&v140 = 0;
              DWORD2(v140) = 0;
              *((_QWORD *)&v141 + 1) = 0;
              v142 = 0;
              *((_QWORD *)&v128 + 1) = 0;
              *(_QWORD *)&v129 = 0;
              HIDWORD(v129) = 0;
              Size[0] = 0;
              LODWORD(Size[1]) = 0;
              *(_QWORD *)&v131 = 0;
              DWORD2(v131) = 0;
              *((_QWORD *)&v132 + 1) = 0;
              v133 = 0;
              *(_QWORD *)&v136 = 1651339363;
              *(_QWORD *)&v127 = 0x1626D7063LL;
              DWORD2(v127) = iBitmapFormat;
              v65 = NumToBPP(v112);
              v68 = v152;
              v69 = v65;
              HIDWORD(v127) = v65;
              DWORD1(v128) = v21;
              if ( v152 )
              {
                *(_QWORD *)&v129 = v152;
                v70 = BMPConv::DwCheckXlateObj(v66, v152, iBitmapFormat);
                v67 = v120;
                DWORD1(v127) = v70 | 1;
              }
              v56 = v116;
              DWORD2(v129) = 1;
              if ( pso )
                pvScan0 = (unsigned __int8 *)a2->pvScan0;
              else
                pvScan0 = (unsigned __int8 *)a2->pvScan0
                        + v9->top * (__int64)a2->lDelta
                        + ((unsigned __int64)(v9->left * v116) >> 3);
              v71 = *((_QWORD *)a1 + 250);
              v72 = *(unsigned int *)(*(unsigned int *)(v71 + 8) + *(_QWORD *)(v71 + 104) + 176LL);
              if ( (_DWORD)v72 == -1 || !(*(unsigned int *)(v71 + 16) + *(_QWORD *)(v71 + 96) + 28 * v72) || v39 < 1 )
              {
                v45 = v121;
                v46 = v115;
              }
              else
              {
                BMPCompress::BMPCompress((BMPCompress *)v145);
                DWORD1(v136) = 1;
                *((_QWORD *)&v136 + 1) = __PAIR64__(v69, iBitmapFormat);
                DWORD1(v137) = v21;
                if ( v68 )
                {
                  *(_QWORD *)&v138 = v68;
                  DWORD1(v136) = BMPConv::DwCheckXlateObj(v74, v68, iBitmapFormat) | 1;
                }
                DWORD2(v138) = 3;
                if ( v148 >= 3 )
                {
                  v109 = -2147467259;
                  `vector destructor iterator'(v149, v73, v75, v76);
                  goto LABEL_100;
                }
                v62 = 0;
                v77 = v137;
                v78 = 104LL * v148;
                *(_OWORD *)((char *)v149 + v78) = v136;
                v79 = v138;
                *(_OWORD *)((char *)&v149[1] + v78) = v77;
                v80 = v139;
                *(_OWORD *)((char *)&v149[2] + v78) = v79;
                v81 = v140;
                *(_OWORD *)((char *)&v149[3] + v78) = v80;
                v82 = v141;
                *(_OWORD *)((char *)&v149[4] + v78) = v81;
                *(_OWORD *)((char *)&v149[5] + v78) = v82;
                *(_QWORD *)((char *)&v149[6] + v78) = 0;
                *((_DWORD *)&v149[19] + v148 + 2) = 0;
                v83 = v148 + 1;
                v148 = v83;
                if ( (unsigned int)v83 >= 3 )
                {
                  v62 = -2147467259;
                  `vector destructor iterator'(v149, v73, v75, v76);
LABEL_135:
                  BMPConv::~BMPConv((BMPConv *)&v127);
                  BMPConv::~BMPConv((BMPConv *)&v136);
                  goto LABEL_101;
                }
                v88 = v128;
                v46 = v115;
                v89 = 104 * v83;
                *(_OWORD *)((char *)v149 + v89) = v127;
                v90 = v129;
                *(_OWORD *)((char *)&v149[1] + v89) = v88;
                v91 = *(_OWORD *)Size;
                *(_OWORD *)((char *)&v149[2] + v89) = v90;
                v92 = v131;
                *(_OWORD *)((char *)&v149[3] + v89) = v91;
                v93 = v132;
                *(_OWORD *)((char *)&v149[4] + v89) = v92;
                *(_OWORD *)((char *)&v149[5] + v89) = v93;
                *(_QWORD *)((char *)&v149[6] + v89) = 0;
                *((_DWORD *)&v149[19] + v148++ + 2) = 0;
                v146 = 30;
                v94 = BMPCompress::hrSetSrcBitmap((BMPCompress *)v145, pvScan0, v115, v39, a2);
                v109 = v94;
                if ( v94 < 0 )
                {
                  `vector destructor iterator'(v149, v84, v85, v86);
LABEL_99:
                  BMPConv::~BMPConv((BMPConv *)&v127);
                  BMPConv::~BMPConv((BMPConv *)&v136);
LABEL_100:
                  v62 = v109;
LABEL_101:
                  LocalFree(hMem);
                  v37 = v125;
LABEL_102:
                  if ( v37 )
                    LocalFree(v37);
LABEL_104:
                  if ( pso )
                  {
                    EngUnlockSurface(pso);
                    if ( hsurf )
                    {
                      if ( !EngDeleteSurface(hsurf) )
                        return 0;
                    }
                  }
                  return v62;
                }
                v45 = v121;
                if ( (*(_BYTE *)(v121 + 16) & 0x40) == 0 || v118 )
                {
                  v62 = v94;
                }
                else
                {
                  v151 = *(_DWORD *)(v121 + 184);
                  v150 = 1;
                  v109 = 0;
                }
                if ( v148 && v145[0] && (int)BMPCompress::hrRunCompression((BMPCompress *)v145) < 0 )
                {
                  v52 = 255;
                  v147 = 255;
                }
                else
                {
                  v52 = v147;
                }
                `vector destructor iterator'(v149, v84, v85, v86);
                if ( v52 == 255 )
                  goto LABEL_135;
                v67 = v120;
                v56 = v116;
              }
              v47 = 255;
              v143 = &v67[v122];
              v48 = 0;
              v111 = 0;
              v117 = 0;
              v113 = 0;
              while ( v39 > 0 )
              {
                v49 = pvScan0;
                if ( (*(_BYTE *)(v45 + 16) & 0x40) != 0 && !v118 )
                {
                  v49 = v125;
                  v109 = hrChangePixelColorInScanLine(pvScan0, v56, v46, *(_DWORD *)(v45 + 184), v125, v119);
                  if ( v109 < 0 )
                    goto LABEL_99;
                }
                if ( v52 == 3 )
                {
                  v50 = BMPConv::PubConvertBMP((BMPConv *)&v136, v49, v119);
                  if ( DWORD2(v138) == 3 )
                  {
                    v51 = v141;
                  }
                  else
                  {
                    v51 = HIDWORD(v138);
                    if ( DWORD2(v138) == 1 )
                      v51 = HIDWORD(v139);
                  }
                }
                else
                {
                  DWORD2(v129) = 1;
                  v50 = BMPConv::PubConvertBMP((BMPConv *)&v127, v49, v119);
                  if ( DWORD2(v129) == 3 )
                  {
                    v51 = v132;
                  }
                  else
                  {
                    v51 = HIDWORD(v129);
                    if ( DWORD2(v129) == 1 )
                      v51 = HIDWORD(Size[1]);
                  }
                  if ( v51 >= v119 )
                  {
                    v52 = 0;
                    DWORD2(v129) = 0;
                    v50 = BMPConv::PubConvertBMP((BMPConv *)&v127, v49, v119);
                    if ( DWORD2(v129) == 3 )
                    {
                      v51 = v132;
                    }
                    else
                    {
                      v51 = HIDWORD(v129);
                      if ( DWORD2(v129) == 1 )
                        v51 = HIDWORD(Size[1]);
                    }
                  }
                  else
                  {
                    v52 = 1;
                  }
                }
                if ( v51 + v111 <= v122 && (v47 == v52 || v47 == 255) )
                {
                  v53 = v120;
                  v54 = v111;
                }
                else
                {
                  if ( v47 == 255 )
                    v47 = v52;
                  if ( v111 )
                  {
                    v58 = *(XLOutput **)(*((_QWORD *)a1 + 1) + 160LL);
                    XLOutput::Send_uint16(v58, v113);
                    XLOutput::Send_attr_ubyte(v58, 109);
                    XLOutput::Send_uint16(v58, v117);
                    XLOutput::Send_attr_ubyte(v58, 99);
                    XLOutput::SetCompressMode(v58, v47);
                    XLWrite::WriteByte(v58, 0xB1u);
                    XLWrite::Flush(v58, a1);
                    if ( v111 > 0xFF )
                    {
                      LOBYTE(v152) = -6;
                      v59 = 5;
                      *(_DWORD *)((char *)&v152 + 1) = v111;
                    }
                    else
                    {
                      LOBYTE(v152) = -5;
                      v59 = 2;
                      BYTE1(v152) = v111;
                    }
                    WriteSpoolBuf(a1, &v152, v59);
                    WriteSpoolBuf(a1, hMem, v111);
                    v60 = v117 + v113;
                    v113 += v117;
                    if ( v51 > v122 )
                    {
                      BSendReadImageData(a1, v47, v50, v60, 1, v51);
                      v51 = 0;
                      ++v113;
                    }
                  }
                  else
                  {
                    BSendReadImageData(a1, v47, v50, v113, 1, v51);
                    v51 = 0;
                    ++v113;
                  }
                  v53 = hMem;
                  v54 = 0;
                  v111 = 0;
                  v117 = 0;
                  v120 = hMem;
                }
                if ( !v50 )
                  goto LABEL_99;
                --v39;
                if ( v51 )
                {
                  v55 = &v53[v51];
                  if ( v55 <= v143 )
                  {
                    memcpy_0(v53, v50, v51);
                    v120 = v55;
                    ++v117;
                    v53 = v55;
                    v111 = v51 + v54;
                  }
                }
                v47 = v52;
                if ( v52 || (v61 = (((v115 * v112 + 31) >> 3) & 0x1FFFFFFC) - v51) == 0 )
                {
                  v48 = v111;
                }
                else
                {
                  memset_0(v53, 0, v61);
                  v48 = v61 + v111;
                  v120 += v61;
                  v111 += v61;
                }
                v45 = v121;
                v46 = v115;
                v56 = v116;
                pvScan0 += a2->lDelta;
              }
              if ( v48 )
                BSendReadImageData(a1, v52, hMem, v113, v117, v48);
              XLWrite::WriteByte(v110, 0xB2u);
              XLWrite::Flush(v110, a1);
              goto LABEL_99;
            }
LABEL_188:
            if ( a4 && (a4->flXlate & 2) != 0 && (a4->pulXlate || XLATEOBJ_piVector(a4)) )
              goto LABEL_39;
            v34 = 0;
            v35 = v110;
            if ( v103 == 3 )
            {
              v21 = 2;
              v112 = 24;
              goto LABEL_34;
            }
            v21 = 0;
          }
          else
          {
            v21 = 0;
LABEL_32:
            v34 = 0;
            v35 = v110;
          }
          v112 = 8;
LABEL_34:
          LOBYTE(v34) = *((_DWORD *)v110 + 71) == 3;
          XLOutput::SetColorSpace(v35, (unsigned int)(v34 + 1));
LABEL_40:
          v118 = 0;
          goto LABEL_41;
        default:
          goto LABEL_32;
      }
    }
    XLWrite::Flush(v110, v19);
    return 2147549183LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000fde0  push    rbp
0x18000fde2  push    rbx
0x18000fde3  push    rsi
0x18000fde4  push    rdi
0x18000fde5  push    r12
0x18000fde7  push    r13
0x18000fde9  push    r14
0x18000fdeb  push    r15
0x18000fded  lea     rbp, [rsp-298h]
0x18000fdf5  sub     rsp, 398h
0x18000fdfc  mov     rax, cs:__security_cookie
0x18000fe03  xor     rax, rsp
0x18000fe06  mov     [rbp+2D0h+var_48], rax
0x18000fe0d  mov     r15, [rbp+2D0h+arg_28]
0x18000fe14  mov     r13, r9
0x18000fe17  mov     rbx, [rbp+2D0h+arg_30]
0x18000fe1e  mov     r14, [rbp+2D0h+arg_20]
0x18000fe25  mov     r12, [rbp+2D0h+arg_38]
0x18000fe2c  mov     [rbp+2D0h+var_50], r9
0x18000fe33  mov     r9, r8
0x18000fe36  mov     [rbp+2D0h+psoSrc], rdx
0x18000fe3a  mov     [rbp+2D0h+var_350], rcx
0x18000fe3e  test    rcx, rcx
0x18000fe41  jz      loc_18001055F
0x18000fe47  test    rbx, rbx
0x18000fe4a  jz      loc_18001055F
0x18000fe50  mov     eax, [rbx]
0x18000fe52  cmp     [rbx+8], eax
0x18000fe55  jl      loc_180010ECB
0x18000fe5b  mov     eax, [rbx+4]
0x18000fe5e  cmp     [rbx+0Ch], eax
0x18000fe61  jl      loc_180010ECB
0x18000fe67  mov     rax, [rcx+8]
0x18000fe6b  mov     r8, rcx; struct _DEVOBJ *
0x18000fe6e  mov     rdx, r9; struct _CLIPOBJ *
0x18000fe71  mov     [rbp+2D0h+var_328], rax
0x18000fe75  mov     rdi, [rax+0A0h]
0x18000fe7c  mov     rcx, rdi; this
0x18000fe7f  mov     [rsp+3D0h+var_368], rdi
0x18000fe84  call    ?SetClip@XLOutput@@QEAAJPEAU_CLIPOBJ@@PEAU_DEVOBJ@@@Z; XLOutput::SetClip(_CLIPOBJ *,_DEVOBJ *)
0x18000fe89  mov     [rsp+3D0h+var_370], eax
0x18000fe8d  test    eax, eax
0x18000fe8f  js      loc_18001051B
0x18000fe95  mov     r8d, [rbx+4]; __int16
0x18000fe99  mov     rcx, rdi; this
0x18000fe9c  mov     edx, [rbx]; __int16
0x18000fe9e  call    ?SetCursor@XLOutput@@QEAAJJJ@Z; XLOutput::SetCursor(long,long)
0x18000fea3  mov     rax, [rsp+3D0h+var_368]
0x18000fea8  add     rdi, 0CCh
0x18000feaf  movzx   esi, byte ptr [rbp+2D0h+arg_40]
0x18000feb6  test    rax, rax
0x18000feb9  mov     ecx, 0ACh
0x18000febe  cmovz   rdi, rcx
0x18000fec2  cmp     esi, [rdi]
0x18000fec4  jnz     loc_1800101B4
0x18000feca  lea     rdx, cs:180000000h
0x18000fed1  cmp     esi, 0FFh
0x18000fed7  jnz     loc_1800109CD
0x18000fedd  mov     edi, 1
0x18000fee2  xor     r10d, r10d
0x18000fee5  test    dil, 1
0x18000fee9  jnz     loc_180010A5F
0x18000feef  mov     esi, edi
0x18000fef1  and     esi, 4
0x18000fef4  test    dil, 0Ah
0x18000fef8  mov     rdi, [rsp+3D0h+var_368]
0x18000fefd  jnz     loc_1800100C8
0x18000ff03  mov     r14, [rbp+2D0h+var_350]
0x18000ff07  test    esi, esi
0x18000ff09  jz      loc_180010EC2
0x18000ff0f  mov     rsi, [rbp+2D0h+psoSrc]
0x18000ff13  mov     [rbp+2D0h+hsurf], r10
0x18000ff17  test    rsi, rsi
0x18000ff1a  jz      loc_180010EB2
0x18000ff20  test    r15, r15
0x18000ff23  jz      loc_180010EB2
0x18000ff29  mov     edi, [rsi+48h]
0x18000ff2c  cmp     edi, 6
0x18000ff2f  jnz     loc_180010BC0
0x18000ff35  mov     ecx, edi
0x18000ff37  mov     r14d, r10d
0x18000ff3a  call    ?UlBPPtoNum@@YAKW4BPP@@@Z; UlBPPtoNum(BPP)
0x18000ff3f  mov     ecx, [r15+0Ch]
0x18000ff43  xorps   xmm0, xmm0
0x18000ff46  sub     ecx, [r15+4]
0x18000ff4a  mov     r8d, [rbx+8]
0x18000ff4e  mov     edx, ecx
0x18000ff50  sub     r8d, [rbx]; int
0x18000ff53  mov     r9d, [rbx+0Ch]
0x18000ff57  sub     r9d, [rbx+4]; int
0x18000ff5b  neg     edx
0x18000ff5d  mov     [rbp+2D0h+var_344], eax
0x18000ff60  mov     [rbp+2D0h+pso], r10
0x18000ff64  cmovs   edx, ecx
0x18000ff67  mov     ecx, [r15+8]
0x18000ff6b  sub     ecx, [r15]
0x18000ff6e  mov     eax, ecx
0x18000ff70  neg     eax
0x18000ff72  movdqu  xmmword ptr [rbp+2D0h+var_1F8.left], xmm0
0x18000ff7a  cmovs   eax, ecx
0x18000ff7d  mov     ecx, r9d
0x18000ff80  imul    edx, eax
0x18000ff83  mov     eax, r8d
0x18000ff86  neg     ecx
0x18000ff88  cmovs   ecx, r9d
0x18000ff8c  neg     eax
0x18000ff8e  cmovs   eax, r8d
0x18000ff92  imul    ecx, eax
0x18000ff95  cmp     ecx, edx
0x18000ff97  jl      loc_180010117
0x18000ff9d  mov     rax, [rbp+2D0h+var_350]
0x18000ffa1  mov     r12, [rsp+3D0h+var_368]
0x18000ffa6  mov     rcx, r12
0x18000ffa9  mov     edx, [rax+74h]
0x18000ffac  shr     edx, 7
0x18000ffaf  and     edx, 1
0x18000ffb2  call    ?SetSourceTxMode@XLOutput@@QEAAJW4TxMode@@@Z; XLOutput::SetSourceTxMode(TxMode)
0x18000ffb7  lea     rsi, [r12+104h]
0x18000ffbf  test    r12, r12
0x18000ffc2  jnz     short loc_18000FFC9
0x18000ffc4  mov     esi, 0E4h
0x18000ffc9  cmp     dword ptr [rsi], 0
0x18000ffcc  jnz     loc_180010BF4
0x18000ffd2  lea     eax, [rdi-1]; switch 6 cases
0x18000ffd5  cmp     eax, 5
0x18000ffd8  jbe     loc_180010C1B
0x18000ffde  xor     edx, edx; jumptable 0000000180010C36 default case
0x18000ffe0  mov     rcx, r12
0x18000ffe3  mov     [rsp+3D0h+var_35C], 8
0x18000ffeb  cmp     dword ptr [r12+11Ch], 3
0x18000fff4  setz    dl
0x18000fff7  inc     edx
0x18000fff9  call    ?SetColorSpace@XLOutput@@QEAAJW4ColorSpace@@@Z; XLOutput::SetColorSpace(ColorSpace)
0x18000fffe  jmp     short loc_180010061
0x180010000  xor     r14d, r14d; jumptable 0000000180010C36 cases 3,4
0x180010003  mov     [rsp+3D0h+var_35C], 0
0x18001000b  cmp     esi, 3
0x18001000e  setz    r14b
0x180010012  mov     ecx, r14d
0x180010015  test    r14d, r14d
0x180010018  jz      short def_180010C36; jumptable 0000000180010C36 default case
0x18001001a  sub     ecx, 1
0x18001001d  jz      loc_180010C3E
0x180010023  sub     ecx, 1
0x180010026  jz      loc_180010C9C
0x18001002c  cmp     ecx, 1
0x18001002f  jz      loc_180010C9C
0x180010035  cmp     r14d, 1
0x180010039  jz      loc_180010C45
0x18001003f  xor     edx, edx
0x180010041  mov     rcx, r12
0x180010044  cmp     dword ptr [r12+11Ch], 3
0x18001004d  setz    dl
0x180010050  inc     edx
0x180010052  call    ?SetColorSpace@XLOutput@@QEAAJW4ColorSpace@@@Z; XLOutput::SetColorSpace(ColorSpace)
0x180010057  cmp     r14d, 1
0x18001005b  jz      loc_180010CB1
0x180010061  mov     [rbp+2D0h+var_33C], 0
0x180010068  xor     r13d, r13d
0x18001006b  mov     dl, 6Ah ; 'j'; unsigned __int8
0x18001006d  mov     rcx, r12; this
0x180010070  mov     [rbp+2D0h+var_308], r13
0x180010074  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180010079  mov     eax, [r15+8]
0x18001007d  mov     r8d, 0FFFFFFFFh
0x180010083  sub     eax, [r15]
0x180010086  mov     ecx, [rsp+3D0h+var_35C]
0x18001008a  mov     edx, [rbp+2D0h+var_344]
0x18001008d  mov     r12d, [r15+0Ch]
0x180010091  sub     r12d, [r15+4]
0x180010095  imul    edx, eax
0x180010098  imul    rcx, rax
0x18001009c  add     edx, 7
0x18001009f  mov     [rbp+2D0h+var_348], eax
0x1800100a2  shr     edx, 3; uBytes
0x1800100a5  mov     [rbp+2D0h+var_338], edx
0x1800100a8  cmp     rcx, r8
0x1800100ab  jbe     loc_1800108A4
0x1800100b1  cmp     edx, 4000h
0x1800100b7  jbe     loc_180010D31
0x1800100bd  lea     esi, [rdx+3]
0x1800100c0  and     esi, 0FFFFFFFCh
0x1800100c3  jmp     loc_180010D36
0x1800100c8  xor     edx, edx
0x1800100ca  mov     rcx, rdi
0x1800100cd  call    ?SetSourceTxMode@XLOutput@@QEAAJW4TxMode@@@Z; XLOutput::SetSourceTxMode(TxMode)
0x1800100d2  xor     edx, edx
0x1800100d4  mov     rcx, rdi
0x1800100d7  call    ?SetPaintTxMode@XLOutput@@QEAAJW4TxMode@@@Z; XLOutput::SetPaintTxMode(TxMode)
0x1800100dc  mov     r9, [rbp+2D0h+var_350]; struct _DEVOBJ *
0x1800100e0  mov     rdx, r14; struct _BRUSHOBJ *
0x1800100e3  mov     rcx, rdi; this
0x1800100e6  call    ?SetBrush@XLOutput@@QEAAJPEAU_BRUSHOBJ@@PEBU_POINTL@@PEAU_DEVOBJ@@@Z; XLOutput::SetBrush(_BRUSHOBJ *,_POINTL const *,_DEVOBJ *)
0x1800100eb  mov     r14, [rbp+2D0h+var_350]
0x1800100ef  xor     edx, edx; struct _BRUSHOBJ *
0x1800100f1  mov     r9, r14; struct _DEVOBJ *
0x1800100f4  mov     rcx, rdi; this
0x1800100f7  call    ?SetPenColor@XLOutput@@QEAAJPEAU_BRUSHOBJ@@PEAU_POINTL@@PEAU_DEVOBJ@@@Z; XLOutput::SetPenColor(_BRUSHOBJ *,_POINTL *,_DEVOBJ *)
0x1800100fc  test    esi, esi
0x1800100fe  jz      loc_180010B9C
0x180010104  mov     rdx, r14; struct _DEVOBJ *
0x180010107  mov     rcx, rdi; this
0x18001010a  call    ?Flush@XLWrite@@QEAAJPEAU_DEVOBJ@@@Z; XLWrite::Flush(_DEVOBJ *)
0x18001010f  xor     r10d, r10d
0x180010112  jmp     loc_18000FF07
0x180010117  mov     qword ptr [rbp+2D0h+var_280.x], r10
0x18001011b  mov     [rbp+2D0h+var_1F8.right], r8d
0x180010122  mov     [rbp+2D0h+var_1F8.bottom], r9d
0x180010129  test    r12, r12
0x18001012c  jz      short loc_180010136
0x18001012e  mov     rax, [r12]
0x180010132  mov     qword ptr [rbp+2D0h+var_280.x], rax
0x180010136  mov     rcx, [rbp+2D0h+var_350]; int
0x18001013a  lea     rdx, [rbp+2D0h+hsurf]; int
0x18001013e  mov     dword ptr [rsp+3D0h+pxlo], edi; iFormat
0x180010142  call    CreateBitmapSURFOBJ
0x180010147  mov     [rbp+2D0h+pso], rax
0x18001014b  mov     r12, rax
0x18001014e  test    rax, rax
0x180010151  jz      loc_18000FF9D
0x180010157  mov     [rsp+3D0h+iMode], 3; iMode
0x18001015f  lea     rax, [rbp+2D0h+var_1F8]
0x180010166  xor     ecx, ecx
0x180010168  xor     r9d, r9d; pco
0x18001016b  mov     [rsp+3D0h+pptlMask], rcx; pptlMask
0x180010170  xor     r8d, r8d; psoMask
0x180010173  mov     [rsp+3D0h+prclSrc], r15; prclSrc
0x180010178  mov     rdx, rsi; psoSrc
0x18001017b  mov     [rsp+3D0h+prclDest], rax; prclDest
0x180010180  lea     rax, [rbp+2D0h+var_280]
0x180010184  mov     [rsp+3D0h+pptlHTOrg], rax; pptlHTOrg
0x180010189  mov     [rsp+3D0h+pca], rcx; pca
0x18001018e  mov     [rsp+3D0h+pxlo], rcx; pxlo
0x180010193  mov     rcx, r12; psoDest
0x180010196  call    cs:__imp_EngStretchBlt
0x18001019c  test    eax, eax
0x18001019e  jz      loc_18000FF9D
0x1800101a4  mov     [rbp+2D0h+psoSrc], r12
0x1800101a8  lea     r15, [rbp+2D0h+var_1F8]
0x1800101af  jmp     loc_18000FF9D
0x1800101b4  movzx   edx, sil; unsigned __int8
0x1800101b8  mov     rcx, rax; this
0x1800101bb  call    ?Send_ubyte@XLOutput@@QEAAJE@Z; XLOutput::Send_ubyte(uchar)
0x1800101c0  test    eax, eax
0x1800101c2  jz      loc_1800109A3
0x1800101c8  mov     rax, [rsp+3D0h+var_368]
0x1800101cd  jmp     loc_18000FECA
0x1800101d2  mov     rdi, [rbp+2D0h+var_328]
0x1800101d6  mov     r14d, [rbp+2D0h+var_348]
0x1800101da  mov     rax, [rbp+2D0h+var_320]
0x1800101de  mov     r13d, 0FFh
0x1800101e4  mov     eax, eax
0x1800101e6  add     rax, r9
0x1800101e9  mov     [rbp+2D0h+var_200], rax
0x1800101f0  xor     eax, eax
0x1800101f2  mov     ecx, eax
0x1800101f4  mov     [rsp+3D0h+var_360], eax
0x1800101f8  mov     [rbp+2D0h+var_340], eax
0x1800101fb  mov     [rsp+3D0h+var_358], eax
0x1800101ff  nop
0x180010200  test    r12d, r12d
0x180010203  jle     loc_1800104A2
0x180010209  test    byte ptr [rdi+10h], 40h
0x18001020d  mov     rbx, r15
0x180010210  jnz     loc_180010DD9
0x180010216  mov     rdx, rbx; unsigned __int8 *
0x180010219  cmp     esi, 3
0x18001021c  jz      loc_1800102E8
0x180010222  mov     esi, [rbp+2D0h+var_338]
0x180010225  lea     rcx, [rbp+2D0h+var_2F0]; this
0x180010229  mov     r8d, esi; unsigned int
0x18001022c  mov     dword ptr [rbp+2D0h+var_2D0+8], 1
0x180010233  call    ?PubConvertBMP@BMPConv@@QEAAPEAEPEAEK@Z; BMPConv::PubConvertBMP(uchar *,ulong)
0x180010238  mov     r14, rax
0x18001023b  mov     eax, dword ptr [rbp+2D0h+var_2D0+8]
0x18001023e  cmp     eax, 3
0x180010241  jz      loc_18001031C
0x180010247  mov     edi, dword ptr [rbp+2D0h+var_2D0+0Ch]
0x18001024a  cmp     eax, 1
0x18001024d  cmovz   edi, dword ptr [rbp+2D0h+Size+0Ch]
0x180010251  cmp     edi, esi
0x180010253  jnb     loc_18001046B
0x180010259  mov     esi, 1
0x18001025e  mov     ecx, [rsp+3D0h+var_360]
0x180010262  lea     eax, [rdi+rcx]
0x180010265  cmp     eax, dword ptr [rbp+2D0h+var_320]
0x180010268  ja      loc_180010331
0x18001026e  cmp     r13d, esi
0x180010271  jnz     loc_180010324
0x180010277  mov     r9, [rbp+2D0h+var_330]
0x18001027b  mov     r13d, [rsp+3D0h+var_360]
0x180010280  test    r14, r14
0x180010283  jz      loc_1800104DF
0x180010289  dec     r12d
0x18001028c  test    edi, edi
0x18001028e  jz      short loc_1800102BD
0x180010290  mov     r8d, edi; Size
0x180010293  lea     rbx, [r8+r9]
0x180010297  cmp     rbx, [rbp+2D0h+var_200]
0x18001029e  ja      short loc_1800102BD
  ... truncated ...
```
