# TIFFReadDirectory

- ea: `0x180161e70`
- end: `0x1801634f8`
- name: `TIFFReadDirectory`
- size: `5768`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `42`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18014d580`

## callees

- `0x18014dde0`
- `0x18014df00`
- `0x18014df40`
- `0x18014e3b0`
- `0x18014e440`
- `0x18014e470`
- `0x18014e5e0`
- `0x18014e620`
- `0x18014ee10`
- `0x18014ef80`
- `0x18014f300`
- `0x180151460`
- `0x180152940`
- `0x180152b70`
- `0x180152be0`
- `0x180159a80`
- `0x18015a210`
- `0x18015a320`
- `0x18015a5e0`
- `0x18015a710`
- `0x18015a980`
- `0x18015ab80`
- `0x18015b750`
- `0x18015b8a0`
- `0x18015bbb0`
- `0x18015bcf0`
- `0x18015c2d0`
- `0x18015d9d0`
- `0x18015dc30`
- `0x18015dcd0`
- `0x18015ead0`
- `0x180160650`
- `0x180160b20`
- `0x180160cb0`
- `0x180161e70`
- `0x180163500`
- `0x1801636f0`
- `0x180163b50`
- `0x180164140`
- `0x180164390`
- `0x18017b528`
- `0x1801ca010`

## string_xrefs

- `0x180162213`: `Compression`
- `0x18016222d`: `Compression`
- `0x180162247`: `Compression`
- `0x180162261`: `Compression`
- `0x18016227b`: `Compression`
- `0x180162295`: `Compression`
- `0x1801622af`: `Compression`
- `0x180161ee2`: `TIFFReadDirectory`
- `0x180162013`: `TIFFReadDirectory`
- `0x180162131`: `TIFFReadDirectory`
- `0x180162221`: `TIFFReadDirectory`
- `0x18016223b`: `TIFFReadDirectory`
- `0x180162255`: `TIFFReadDirectory`
- `0x18016226f`: `TIFFReadDirectory`
- `0x180162289`: `TIFFReadDirectory`
- `0x1801622a3`: `TIFFReadDirectory`
- `0x1801622bd`: `TIFFReadDirectory`
- `0x18016233f`: `TIFFReadDirectory`
- `0x18016249d`: `TIFFReadDirectory`
- `0x18016266e`: `TIFFReadDirectory`
- `0x1801626f8`: `TIFFReadDirectory`
- `0x180162740`: `TIFFReadDirectory`
- `0x18016277c`: `TIFFReadDirectory`
- `0x180162839`: `TIFFReadDirectory`
- `0x1801628ad`: `TIFFReadDirectory`
- `0x180162aec`: `TIFFReadDirectory`
- `0x180162b02`: `TIFFReadDirectory`
- `0x180162b18`: `TIFFReadDirectory`
- `0x180162b2e`: `TIFFReadDirectory`
- `0x180162b44`: `TIFFReadDirectory`
- `0x180162b89`: `TIFFReadDirectory`
- `0x180162b9f`: `TIFFReadDirectory`
- `0x180162bc2`: `TIFFReadDirectory`
- `0x180162be1`: `TIFFReadDirectory`
- `0x180162c21`: `TIFFReadDirectory`
- `0x180162c58`: `TIFFReadDirectory`
- `0x180162cf8`: `TIFFReadDirectory`
- `0x180162e9c`: `TIFFReadDirectory`
- `0x180162eeb`: `TIFFReadDirectory`
- `0x1801630ef`: `TIFFReadDirectory`
- `0x180163312`: `TIFFReadDirectory`
- `0x180163347`: `TIFFReadDirectory`
- `0x18016336c`: `TIFFReadDirectory`
- `0x180161f69`: `TIFFReadDirectoryCheckOrder`
- `0x180162234`: `Incompatible type for "%s"`
- `0x180162b82`: `Incompatible type for "%s"`
- `0x18016224e`: `IO error during reading of "%s"`
- `0x180162afb`: `IO error during reading of "%s"`
- `0x1801622b6`: `Out of memory reading of "%s"`
- `0x180162b98`: `Out of memory reading of "%s"`
- `0x1801628dd`: `Incompatible type for "%s"; tag ignored`
- `0x1801628e9`: `IO error during reading of "%s"; tag ignored`
- `0x180162919`: `Out of memory reading of "%s"; tag ignored`
- `0x180161edb`: `Failed to read directory at offset %llu`
- `0x18016200c`: `Failed to allocate memory for counting IFD data size at reading`
- `0x18016248f`: `Planarconfig tag value assumed incorrect, assuming data is contig instead of chunky`
- `0x180162ee4`: `Failed to allocate memory for temporary new sampleinfo array (%hu 16 bit elements)`
- `0x180162f9e`: `TIFF directory is missing required "StripByteCounts" field, calculating from imagelength`
- `0x180161f5f`: `Invalid TIFF directory; tags are not sorted in ascending order`
- `0x1801624b9`: `TIFF directory is missing required "%s" field`

## pseudocode

```c
__int64 __fastcall TIFFReadDirectory(__int64 a1)
{
  __int64 v1; // rdi
  int v4; // ecx
  __int64 v5; // rdx
  unsigned __int16 v6; // ax
  __int64 v7; // r15
  __int64 v8; // rdx
  int v9; // ecx
  _WORD *i; // r8
  unsigned __int16 v11; // cx
  _WORD *v12; // r12
  unsigned __int16 *v13; // rax
  unsigned int v14; // edx
  unsigned __int16 v15; // r9
  _WORD *v16; // rcx
  void (__fastcall *v17)(__int64, __int64, _WORD *); // rax
  __int64 v18; // rax
  _WORD *v19; // rdi
  __int16 v20; // ax
  __int16 v21; // ax
  _WORD *v22; // rdi
  unsigned __int16 v23; // r14
  unsigned __int16 *v24; // rsi
  int v25; // r8d
  unsigned int v26; // ebp
  __int64 v27; // r11
  int v28; // r10d
  int v29; // eax
  int v30; // edi
  unsigned int *v31; // rdx
  __int64 v32; // rax
  int v33; // r8d
  __int64 v34; // r11
  int v35; // r10d
  unsigned int v36; // r9d
  int v37; // eax
  unsigned int *v38; // rcx
  int v39; // eax
  unsigned __int16 v40; // r8
  unsigned int v41; // edx
  _WORD *v42; // rax
  __int16 v43; // cx
  _WORD *v44; // rax
  __int16 v45; // cx
  const char *v46; // r9
  __int64 v47; // r8
  unsigned __int16 v48; // r13
  unsigned __int16 *v49; // rbp
  const char *v50; // r12
  __int64 v51; // rdx
  __int64 v52; // rax
  __int64 v53; // r14
  int v54; // edi
  int v55; // eax
  int v56; // esi
  int v57; // eax
  int v58; // edi
  __int64 v59; // rax
  const char *v60; // r9
  void *v61; // rcx
  __int64 v62; // rax
  const char *v63; // r9
  __int64 v64; // r14
  __int64 v65; // rax
  const char *v66; // r9
  unsigned __int16 v67; // cx
  __int64 v68; // rax
  const char *v69; // r9
  unsigned int v70; // edi
  __int64 v71; // rcx
  __int64 v72; // rax
  int v73; // esi
  int v74; // eax
  __int64 v75; // rdx
  __int64 v76; // rax
  const char *v77; // r9
  int v78; // esi
  _WORD *v79; // rdi
  int v80; // edi
  __int16 v81; // dx
  _WORD *v82; // rcx
  __int16 v83; // ax
  __int16 v84; // dx
  __int64 v85; // rdx
  __int64 v86; // rax
  __int64 v87; // rax
  __int64 v88; // r8
  unsigned int v89; // eax
  __int64 v90; // rdx
  int v91; // r8d
  unsigned int v92; // r8d
  unsigned int v93; // r9d
  const char *v94; // r9
  int v95; // eax
  bool v96; // zf
  unsigned int v97; // ecx
  _WORD *v98; // rdx
  __int64 v99; // rbp
  unsigned __int16 v100; // ax
  void *v101; // rax
  void *v102; // rdi
  __int16 v103; // ax
  unsigned __int64 v104; // rdi
  unsigned __int64 v105; // rsi
  unsigned __int64 v106; // rax
  unsigned __int64 v107; // rax
  unsigned __int64 v108; // r8
  __int64 v109; // rdi
  unsigned __int16 v110; // cx
  unsigned __int64 v111; // rdx
  unsigned __int64 v112; // r14
  unsigned int v113; // edi
  unsigned __int64 v114; // rax
  unsigned __int64 v115; // rsi
  unsigned int v116; // eax
  unsigned int v117; // ecx
  unsigned int v118; // eax
  unsigned int v119; // ebp
  __int64 v120; // rax
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // [rsp+20h] [rbp-68h]
  _WORD *v124; // [rsp+30h] [rbp-58h]
  __int16 *v125; // [rsp+38h] [rbp-50h] BYREF
  void *Src; // [rsp+90h] [rbp+8h] BYREF
  __int16 v127; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v128; // [rsp+A0h] [rbp+18h]
  __int64 v129; // [rsp+A8h] [rbp+20h] BYREF

  v1 = *(_QWORD *)(a1 + 32);
  if ( !v1 )
  {
    *(_QWORD *)(a1 + 24) = 0;
    return 0;
  }
  v4 = *(_DWORD *)(a1 + 848);
  v5 = 0;
  if ( v4 != -1 )
    v5 = (unsigned int)(v4 + 1);
  if ( !(unsigned int)TIFFCheckDirNumberAndOffset(a1, v5, v1) )
    return 0;
  v6 = TIFFFetchDirectory(a1, v1, &Src, a1 + 32);
  v7 = v6;
  if ( !v6 )
  {
    TIFFErrorExtR(a1, "TIFFReadDirectory", "Failed to read directory at offset %llu", v1);
    return 0;
  }
  v8 = *(unsigned int *)(a1 + 848);
  v9 = 0;
  i = 0;
  if ( (_DWORD)v8 != -1 )
    v9 = v8 + 1;
  *(_DWORD *)(a1 + 848) = v9;
  v11 = 0;
  v12 = Src;
  v124 = Src;
  v13 = (unsigned __int16 *)Src;
  if ( (_WORD)v7 )
  {
    while ( 1 )
    {
      v14 = *v13;
      if ( v14 < (unsigned int)i )
        break;
      ++v11;
      LODWORD(i) = v14 + 1;
      v13 += 16;
      if ( v11 >= (unsigned __int16)v7 )
      {
        v15 = 0;
        goto LABEL_16;
      }
    }
    TIFFWarningExtR(a1, "TIFFReadDirectoryCheckOrder", "Invalid TIFF directory; tags are not sorted in ascending order");
    v15 = 0;
LABEL_16:
    for ( i = v12; ; i += 16 )
    {
      ++v15;
      v16 = i + 16;
      v8 = v15;
      if ( v15 >= (unsigned __int16)v7 )
        break;
      do
      {
        if ( *i == *v16 )
          *((_BYTE *)v16 + 24) = 1;
        v16 += 16;
        LOWORD(v8) = v8 + 1;
      }
      while ( (unsigned __int16)v8 < (unsigned __int16)v7 );
    }
  }
  v17 = *(void (__fastcall **)(__int64, __int64, _WORD *))(a1 + 1048);
  *(_DWORD *)(a1 + 16) &= 0xFBEFFFBF;
  v17(a1, v8, i);
  TIFFFreeDirectory(a1);
  TIFFDefaultDirectory(a1);
  *(_BYTE *)(a1 + 409) = 1;
  v18 = TIFFmallocExt(a1, 16 * v7);
  *(_QWORD *)(a1 + 440) = v18;
  if ( !v18 )
  {
    TIFFErrorExtR(a1, "TIFFReadDirectory", "Failed to allocate memory for counting IFD data size at reading");
    goto LABEL_104;
  }
  TIFFSetField(a1, 284, 1);
  v19 = v12;
  v20 = 0;
  if ( (_WORD)v7 )
  {
    while ( *v19 != 277 )
    {
      v19 += 16;
      if ( (unsigned __int16)++v20 >= (unsigned __int16)v7 )
      {
        v21 = 0;
        goto LABEL_29;
      }
    }
    TIFFFetchNormalTag(a1, v19, 0);
    v21 = 0;
    *((_BYTE *)v19 + 24) = 1;
LABEL_29:
    v22 = v12;
    while ( *v22 != 259 )
    {
      v22 += 16;
      if ( (unsigned __int16)++v21 >= (unsigned __int16)v7 )
        goto LABEL_32;
    }
    v39 = TIFFReadDirEntryShort(a1, v22, &Src);
    if ( v39 == 1 )
      v39 = TIFFReadDirEntryPersampleShort(a1, v22, &Src);
    if ( v39 )
    {
      switch ( v39 )
      {
        case 1:
          TIFFErrorExtR(a1, "TIFFReadDirectory", "Incorrect count for \"%s\"", "Compression");
          break;
        case 2:
          TIFFErrorExtR(a1, "TIFFReadDirectory", "Incompatible type for \"%s\"", "Compression");
          break;
        case 3:
          TIFFErrorExtR(a1, "TIFFReadDirectory", "IO error during reading of \"%s\"", "Compression");
          break;
        case 4:
          TIFFErrorExtR(a1, "TIFFReadDirectory", "Incorrect value for \"%s\"", "Compression");
          break;
        case 5:
          TIFFErrorExtR(a1, "TIFFReadDirectory", "Cannot handle different values per sample for \"%s\"", "Compression");
          break;
        case 6:
          TIFFErrorExtR(a1, "TIFFReadDirectory", "Sanity check on size of \"%s\" value failed", "Compression");
          break;
        case 7:
          TIFFErrorExtR(a1, "TIFFReadDirectory", "Out of memory reading of \"%s\"", "Compression");
          break;
        default:
          break;
      }
LABEL_104:
      if ( v124 )
        TIFFfreeExt(a1, v124);
      return 0;
    }
    if ( !(unsigned int)TIFFSetField(a1, 259, (unsigned __int16)Src) )
      goto LABEL_104;
    *((_BYTE *)v22 + 24) = 1;
    v23 = 0;
    goto LABEL_34;
  }
LABEL_32:
  if ( !(unsigned int)TIFFSetField(a1, 259, 1) )
    goto LABEL_104;
  v23 = 0;
  if ( (_WORD)v7 )
  {
LABEL_34:
    v24 = v12;
    while ( 1 )
    {
      if ( *((_BYTE *)v24 + 24) )
        goto LABEL_86;
      v25 = *(_DWORD *)(a1 + 1240);
      v26 = *v24;
      if ( !v25 )
        break;
      v27 = *(_QWORD *)(a1 + 1232);
      v28 = -1;
      while ( 1 )
      {
        v29 = (v25 + v28) / 2;
        v30 = v29;
        v31 = *(unsigned int **)(v27 + 8LL * v29);
        if ( *v31 == v26 )
          break;
        if ( *v31 >= v26 )
        {
          v25 = (v25 + v28) / 2;
          v30 = v28;
        }
        v28 = v30;
        if ( v30 + 1 == v25 )
          goto LABEL_42;
      }
      if ( v29 )
      {
        do
        {
          if ( **(_DWORD **)(v27 + 8LL * v30 - 8) != v26 )
            break;
          --v30;
        }
        while ( v30 );
      }
      if ( v30 == -1 )
        goto LABEL_43;
LABEL_75:
      if ( !*((_BYTE *)v24 + 24) )
      {
        v40 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 1232) + 8LL * (unsigned int)v30) + 24LL);
        if ( v40 )
        {
          v41 = *v24;
          if ( v41 <= 0x80E5 )
          {
            if ( v41 != 32997 )
            {
              switch ( *v24 )
              {
                case 0x100u:
                case 0x101u:
                case 0x116u:
                case 0x11Cu:
                case 0x142u:
                case 0x143u:
                case 0x152u:
                  goto LABEL_84;
                case 0x111u:
                case 0x117u:
                case 0x144u:
                case 0x145u:
                  *(_DWORD *)(a1 + 4 * ((unsigned __int64)v40 >> 5) + 72) |= 1 << (v40 & 0x1F);
                  goto LABEL_86;
                default:
                  goto LABEL_82;
              }
            }
            goto LABEL_84;
          }
          if ( v41 == 32998 )
          {
LABEL_84:
            if ( !(unsigned int)TIFFFetchNormalTag(a1, v24, 0) )
              goto LABEL_104;
          }
          else
          {
LABEL_82:
            if ( (unsigned int)TIFFCheckFieldIsValidForCodec(a1) )
              goto LABEL_86;
          }
        }
        *((_BYTE *)v24 + 24) = 1;
      }
LABEL_86:
      ++v23;
      v24 += 16;
      if ( v23 >= (unsigned __int16)v7 )
        goto LABEL_87;
    }
LABEL_42:
    v30 = -1;
LABEL_43:
    TIFFWarningExtR(a1, "TIFFReadDirectory", "Unknown field with tag %hu (0x%hx) encountered", *v24, *v24);
    v32 = TIFFCreateAnonField(a1, *v24, v24[1]);
    if ( v32 && (unsigned int)TIFFMergeFields(a1, v32, 1) )
    {
      v33 = *(_DWORD *)(a1 + 1240);
      if ( v33 )
      {
        v34 = *(_QWORD *)(a1 + 1232);
        v35 = -1;
        v36 = *v24;
        while ( 1 )
        {
          v37 = (v33 + v35) / 2;
          v30 = v37;
          v38 = *(unsigned int **)(v34 + 8LL * v37);
          if ( *v38 == v36 )
            break;
          if ( *v38 >= v36 )
          {
            v33 = (v33 + v35) / 2;
            v30 = v35;
          }
          v35 = v30;
          if ( v30 + 1 == v33 )
            goto LABEL_51;
        }
        if ( v37 )
        {
          do
          {
            if ( **(_DWORD **)(v34 + 8LL * v30 - 8) != v36 )
              break;
            --v30;
          }
          while ( v30 );
        }
      }
      else
      {
LABEL_51:
        v30 = -1;
      }
    }
    else
    {
      TIFFWarningExtR(a1, "TIFFReadDirectory", "Registering anonymous field with tag %hu (0x%hx) failed", *v24, *v24);
      *((_BYTE *)v24 + 24) = 1;
    }
    goto LABEL_75;
  }
LABEL_87:
  if ( *(_WORD *)(a1 + 120) == 6 && *(_WORD *)(a1 + 170) == 2 )
  {
    if ( !(unsigned int)TIFFFillStrilesInternal(a1, 1) )
      goto LABEL_104;
    v42 = v12;
    v43 = 0;
    if ( (_WORD)v7 )
    {
      while ( *v42 != 273 )
      {
        v42 += 16;
        if ( (unsigned __int16)++v43 >= (unsigned __int16)v7 )
          goto LABEL_101;
      }
      if ( *((_QWORD *)v42 + 1) == 1 )
      {
        v44 = v12;
        v45 = 0;
        while ( *v44 != 279 )
        {
          v44 += 16;
          if ( (unsigned __int16)++v45 >= (unsigned __int16)v7 )
            goto LABEL_101;
        }
        if ( *((_QWORD *)v44 + 1) == 1 )
        {
          *(_WORD *)(a1 + 170) = 1;
          TIFFWarningExtR(
            a1,
            "TIFFReadDirectory",
            "Planarconfig tag value assumed incorrect, assuming data is contig instead of chunky");
        }
      }
    }
  }
LABEL_101:
  if ( (*(_BYTE *)(a1 + 72) & 2) == 0 )
  {
    v46 = "ImageLength";
LABEL_103:
    TIFFErrorExtR(a1, "MissingRequired", "TIFF directory is missing required \"%s\" field", v46);
    goto LABEL_104;
  }
  v128 = 0;
  v47 = 0;
  v48 = 0;
  v49 = v12;
  if ( (_WORD)v7 )
  {
    v50 = "unknown tagname";
    while ( 1 )
    {
      if ( !*((_BYTE *)v49 + 24) )
      {
        v51 = *v49;
        if ( (unsigned int)v51 > 0x80E4 )
        {
LABEL_204:
          TIFFFetchNormalTag(a1, v49, 1);
        }
        else if ( (_DWORD)v51 == 32996 )
        {
LABEL_189:
          v80 = TIFFReadDirEntryShort(a1, v49, &Src);
          if ( !(unsigned __int8)EvaluateIFDdatasizeReading(a1, v49) )
            goto LABEL_104;
          if ( v80 == 1 && *((_QWORD *)v49 + 1) >= (unsigned __int64)*(unsigned __int16 *)(a1 + 130) )
          {
            v80 = TIFFReadDirEntryShortArray(a1, v49, &v125);
            if ( !v80 )
            {
              if ( v125 )
              {
                v81 = *(_WORD *)(a1 + 130);
                v82 = v125 + 1;
                v83 = *v125;
                LOWORD(Src) = *v125;
                v84 = v81 - 1;
                if ( v84 )
                {
                  while ( *v82 == v83 )
                  {
                    ++v82;
                    if ( !--v84 )
                      goto LABEL_199;
                  }
                  v80 = 5;
                }
LABEL_199:
                TIFFfreeExt(a1, v125);
              }
            }
          }
          v85 = *v49;
          if ( v80 )
          {
            v87 = TIFFFieldWithTag(a1, v85);
            if ( v87 )
              v50 = *(const char **)(v87 + 32);
            switch ( v80 )
            {
              case 1:
                goto LABEL_208;
              case 2:
                goto LABEL_216;
              case 3:
                goto LABEL_209;
              case 4:
                goto LABEL_210;
              case 5:
                goto LABEL_211;
              case 6:
                goto LABEL_212;
              case 7:
                goto LABEL_217;
              default:
                goto LABEL_104;
            }
            goto LABEL_104;
          }
          if ( !(unsigned int)TIFFSetField(a1, v85, (unsigned __int16)Src) )
            goto LABEL_104;
          if ( *v49 == 258 )
          {
            v47 = 1;
            v128 = 1;
            goto LABEL_171;
          }
        }
        else
        {
          switch ( *v49 )
          {
            case 0xFFu:
              if ( !(unsigned int)TIFFReadDirEntryShort(a1, v49, &v127) )
              {
                if ( v127 == 2 )
                {
                  TIFFSetField(a1, 254, 1);
                }
                else if ( v127 == 3 )
                {
                  TIFFSetField(a1, 254, 2);
                }
              }
              break;
            case 0x102u:
            case 0x118u:
            case 0x119u:
            case 0x153u:
              goto LABEL_189;
            case 0x111u:
            case 0x144u:
              if ( v49[1] != 3
                && v49[1] != 4
                && v49[1] != 16
                && (*(_DWORD *)(a1 + 12) != 2 || *((_QWORD *)v49 + 1) || v49[1] || *((_QWORD *)v49 + 2)) )
              {
                v59 = TIFFFieldWithTag(a1, v51);
                if ( v59 )
                  v60 = *(const char **)(v59 + 32);
                else
                  v60 = "unknown tagname";
                TIFFWarningExtR(a1, "TIFFReadDirectory", "Invalid data type for tag %s", v60);
              }
              v61 = (void *)(a1 + 256);
              goto LABEL_132;
            case 0x117u:
            case 0x145u:
              if ( v49[1] != 3
                && v49[1] != 4
                && v49[1] != 16
                && (*(_DWORD *)(a1 + 12) != 2 || *((_QWORD *)v49 + 1) || v49[1] || *((_QWORD *)v49 + 2)) )
              {
                v62 = TIFFFieldWithTag(a1, v51);
                if ( v62 )
                  v63 = *(const char **)(v62 + 32);
                else
                  v63 = "unknown tagname";
                TIFFWarningExtR(a1, "TIFFReadDirectory", "Invalid data type for tag %s", v63);
              }
              v61 = (void *)(a1 + 288);
LABEL_132:
              TIFFmemcpy(v61, v49, 0x20u);
              if ( (unsigned __int8)EvaluateIFDdatasizeReading(a1, v49) )
                break;
              goto LABEL_104;
            case 0x12Du:
            case 0x140u:
              v129 = 0;
              v64 = 0;
              if ( (_DWORD)v47 )
              {
                v67 = *(_WORD *)(a1 + 116);
                if ( v67 <= 0x18u )
                {
                  v70 = 1 << v67;
                  v71 = *((_QWORD *)v49 + 1);
                  if ( (_WORD)v51 == 301 && v71 == v70 )
                  {
                    v72 = v70;
                    v70 = 0;
                  }
                  else
                  {
                    v72 = 3 * v70;
                  }
                  if ( v71 == v72 )
                  {
                    v74 = TIFFReadDirEntryShortArray(a1, v49, &v129);
                    v64 = v129;
                    v73 = v74;
                  }
                  else
                  {
                    v73 = 1;
                  }
                  if ( !(unsigned __int8)EvaluateIFDdatasizeReading(a1, v49) )
                    goto LABEL_104;
                  v75 = *v49;
                  if ( v73 )
                  {
                    v76 = TIFFFieldWithTag(a1, v75);
                    if ( v76 )
                      v77 = *(const char **)(v76 + 32);
                    else
                      v77 = "unknown tagname";
                    switch ( v73 )
                    {
                      case 1:
                        TIFFWarningExtR(a1, "TIFFReadDirectory", "Incorrect count for \"%s\"; tag ignored", v77);
                        break;
                      case 2:
                        TIFFWarningExtR(a1, "TIFFReadDirectory", "Incompatible type for \"%s\"; tag ignored", v77);
                        break;
                      case 3:
                        TIFFWarningExtR(a1, "TIFFReadDirectory", "IO error during reading of \"%s\"; tag ignored", v77);
                        break;
                      case 4:
                        TIFFWarningExtR(a1, "TIFFReadDirectory", "Incorrect value for \"%s\"; tag ignored", v77);
                        break;
                      case 5:
                        TIFFWarningExtR(
                          a1,
                          "TIFFReadDirectory",
                          "Cannot handle different values per sample for \"%s\"; tag ignored",
                          v77);
                        break;
                      case 6:
                        TIFFWarningExtR(
                          a1,
                          "TIFFReadDirectory",
                          "Sanity check on size of \"%s\" value failed; tag ignored",
                          v77);
                        break;
                      case 7:
                        TIFFWarningExtR(a1, "TIFFReadDirectory", "Out of memory reading of \"%s\"; tag ignored", v77);
                        break;
                      default:
                        goto LABEL_170;
                    }
                  }
                  else
                  {
                    v123 = v64 + 4LL * v70;
                    TIFFSetField(a1, v75, v64);
                    TIFFfreeExt(a1, v64);
                  }
                }
                else
                {
                  v68 = TIFFFieldWithTag(a1, v51);
                  if ( v68 )
                    v69 = *(const char **)(v68 + 32);
                  else
                    v69 = "unknown tagname";
                  TIFFWarningExtR(
                    a1,
                    "TIFFReadDirectory",
                    "Ignoring %s because BitsPerSample=%hu>24",
                    v69,
                    *(unsigned __int16 *)(a1 + 116));
                }
              }
              else
              {
                v65 = TIFFFieldWithTag(a1, v51);
                if ( v65 )
                  v66 = *(const char **)(v65 + 32);
                else
                  v66 = "unknown tagname";
                TIFFWarningExtR(a1, "TIFFReadDirectory", "Ignoring %s since BitsPerSample tag not found", v66);
              }
              break;
            case 0x154u:
            case 0x155u:
              v52 = *(unsigned __int16 *)(a1 + 130);
              v53 = 0;
              v129 = 0;
              if ( *((_QWORD *)v49 + 1) == v52 )
              {
                v55 = TIFFReadDirEntryDoubleArray(a1, v49, &v129, 301, v123);
                v53 = v129;
                v54 = v55;
              }
              else
              {
                v54 = 1;
              }
              if ( !(unsigned __int8)EvaluateIFDdatasizeReading(a1, v49) )
                goto LABEL_104;
              if ( v54 )
              {
                v86 = TIFFFieldWithTag(a1, *v49);
                if ( v86 )
                  v50 = *(const char **)(v86 + 32);
                switch ( v54 )
                {
                  case 1:
LABEL_208:
                    TIFFErrorExtR(a1, "TIFFReadDirectory", "Incorrect count for \"%s\"", v50);
                    break;
                  case 2:
LABEL_216:
                    TIFFErrorExtR(a1, "TIFFReadDirectory", "Incompatible type for \"%s\"", v50);
                    break;
                  case 3:
LABEL_209:
                    TIFFErrorExtR(a1, "TIFFReadDirectory", "IO error during reading of \"%s\"", v50);
                    break;
                  case 4:
LABEL_210:
                    TIFFErrorExtR(a1, "TIFFReadDirectory", "Incorrect value for \"%s\"", v50);
                    break;
                  case 5:
LABEL_211:
                    TIFFErrorExtR(a1, "TIFFReadDirectory", "Cannot handle different values per sample for \"%s\"", v50);
                    break;
                  case 6:
LABEL_212:
                    TIFFErrorExtR(a1, "TIFFReadDirectory", "Sanity check on size of \"%s\" value failed", v50);
                    break;
                  case 7:
LABEL_217:
                    TIFFErrorExtR(a1, "TIFFReadDirectory", "Out of memory reading of \"%s\"", v50);
                    break;
                  default:
                    goto LABEL_104;
                }
                goto LABEL_104;
              }
              v56 = *(_DWORD *)(a1 + 16);
              *(_DWORD *)(a1 + 16) = v56 | 0x400000;
              v57 = TIFFSetField(a1, *v49, v53);
              *(_DWORD *)(a1 + 16) = v56;
              v58 = v57;
              TIFFfreeExt(a1, v53);
              if ( !v58 )
                goto LABEL_104;
              break;
            default:
              goto LABEL_204;
          }
        }
LABEL_170:
        v47 = v128;
      }
LABEL_171:
      ++v48;
      v49 += 16;
      if ( v48 >= (unsigned __int16)v7 )
      {
        v12 = v124;
        break;
      }
    }
  }
  CalcFinalIFDdatasizeReading(a1, (unsigned __int16)v7, v47);
  v78 = 3;
  if ( *(_WORD *)(a1 + 120) == 6 )
  {
    if ( (*(_DWORD *)(a1 + 72) & 0x100) != 0 )
    {
      v79 = (_WORD *)(a1 + 122);
      if ( *(_WORD *)(a1 + 122) == 2 )
      {
        *v79 = 6;
        TIFFWarningExtR(
          a1,
          "TIFFReadDirectory",
          "Photometric tag value assumed incorrect, assuming data is YCbCr instead of RGB");
      }
    }
    else
    {
      TIFFWarningExtR(a1, "TIFFReadDirectory", "Photometric tag is missing, assuming data is YCbCr");
      if ( !(unsigned int)TIFFSetField(a1, 262, 6) )
        goto LABEL_104;
      v79 = (_WORD *)(a1 + 122);
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x40) == 0 )
    {
      TIFFWarningExtR(a1, "TIFFReadDirectory", "BitsPerSample tag is missing, assuming 8 bits per sample");
      if ( !(unsigned int)TIFFSetField(a1, 258, 8) )
        goto LABEL_104;
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x10000) == 0 )
    {
      if ( *v79 == 2 )
      {
        TIFFWarningExtR(
          a1,
          "TIFFReadDirectory",
          "SamplesPerPixel tag is missing, assuming correct SamplesPerPixel value is 3");
        if ( !(unsigned int)TIFFSetField(a1, 277, 3) )
          goto LABEL_104;
      }
      if ( *v79 == 6 )
      {
        TIFFWarningExtR(
          a1,
          "TIFFReadDirectory",
          "SamplesPerPixel tag is missing, applying correct SamplesPerPixel value of 3");
        v88 = 3;
      }
      else
      {
        if ( *v79 > 1u )
          goto LABEL_230;
        v88 = 1;
      }
      if ( !(unsigned int)TIFFSetField(a1, 277, v88) )
        goto LABEL_104;
    }
  }
LABEL_230:
  if ( (*(_BYTE *)(a1 + 72) & 4) != 0 )
  {
    v89 = TIFFNumberOfTiles(a1);
    v92 = *(_DWORD *)(a1 + 16) | 0x400;
  }
  else
  {
    v89 = TIFFNumberOfStrips(a1);
    v91 = *(_DWORD *)(a1 + 16);
    *(_DWORD *)(a1 + 100) = *(_DWORD *)(a1 + 88);
    v92 = v91 & 0xFFFFFBFF;
    *(_DWORD *)(a1 + 104) = *(_DWORD *)(a1 + 132);
    *(_DWORD *)(a1 + 108) = *(_DWORD *)(a1 + 96);
  }
  *(_DWORD *)(a1 + 16) = v92;
  *(_DWORD *)(a1 + 228) = v89;
  v93 = v89;
  if ( !v89 )
  {
    v94 = "strips";
    if ( (v92 & 0x400) != 0 )
      v94 = "tiles";
    TIFFErrorExtR(a1, "TIFFReadDirectory", "Cannot handle zero number of %s", v94);
    goto LABEL_104;
  }
  v96 = *(_WORD *)(a1 + 170) == 2;
  *(_DWORD *)(a1 + 224) = v89;
  if ( v96 )
  {
    v90 = v89 % *(unsigned __int16 *)(a1 + 130);
    *(_DWORD *)(a1 + 224) = v89 / *(unsigned __int16 *)(a1 + 130);
  }
  v95 = *(_DWORD *)(a1 + 72);
  if ( (v95 & 0x2000000) == 0 )
  {
    if ( *(_WORD *)(a1 + 120) == 6 )
    {
      v96 = (v92 & 0x400) == 0;
      if ( (v92 & 0x400) != 0 )
        goto LABEL_255;
      if ( v93 == 1 )
      {
        *(_DWORD *)(a1 + 72) = v95 | 0x2000000;
        goto LABEL_244;
      }
    }
    v96 = (v92 & 0x400) == 0;
LABEL_255:
    v46 = "StripOffsets";
    if ( !v96 )
      v46 = "TileOffsets";
    goto LABEL_103;
  }
LABEL_244:
  if ( *(_DWORD *)(a1 + 12) != 2
    || !*(_WORD *)(a1 + 256)
    || *(_QWORD *)(a1 + 264)
    || *(_WORD *)(a1 + 258)
    || *(_QWORD *)(a1 + 272)
    || !*(_WORD *)(a1 + 288)
    || *(_QWORD *)(a1 + 296)
    || *(_WORD *)(a1 + 290)
    || *(_QWORD *)(a1 + 304) )
  {
    if ( (v92 & 0x1000000) == 0
      && (*(_WORD *)(a1 + 256)
       && !(unsigned int)TIFFFetchStripThing(a1, a1 + 256, *(unsigned int *)(a1 + 228), a1 + 232)
       || *(_WORD *)(a1 + 288)
       && !(unsigned int)TIFFFetchStripThing(a1, a1 + 288, *(unsigned int *)(a1 + 228), a1 + 240)) )
    {
      goto LABEL_104;
    }
  }
  else
  {
    TIFFSetupStrips(a1, v90);
  }
  v97 = *(unsigned __int16 *)(a1 + 122);
  v98 = (_WORD *)(a1 + 122);
  if ( v97 <= 0x8023 )
  {
    switch ( *(_WORD *)(a1 + 122) )
    {
      case 0:
      case 1:
      case 3:
        v78 = 1;
        goto LABEL_268;
      case 2:
      case 6:
      case 8:
      case 9:
      case 0xA:
        goto LABEL_268;
      case 4:
      case 5:
        v78 = 4;
        goto LABEL_268;
      default:
        goto LABEL_274;
    }
  }
  if ( v97 == 32845 )
  {
LABEL_268:
    if ( *(unsigned __int16 *)(a1 + 130) - *(unsigned __int16 *)(a1 + 212) > v78 )
    {
      TIFFWarningExtR(
        a1,
        "TIFFReadDirectory",
        "Sum of Photometric type-related color channels and ExtraSamples doesn't match SamplesPerPixel. Defining non-colo"
        "r channels as ExtraSamples.");
      v99 = *(unsigned __int16 *)(a1 + 212);
      v100 = *(_WORD *)(a1 + 130) - v78;
      *(_WORD *)(a1 + 212) = v100;
      v101 = (void *)TIFFcallocExt(a1, v100, 2);
      v102 = v101;
      if ( !v101 )
      {
        TIFFErrorExtR(
          a1,
          "TIFFReadDirectory",
          "Failed to allocate memory for temporary new sampleinfo array (%hu 16 bit elements)",
          *(unsigned __int16 *)(a1 + 212));
        goto LABEL_104;
      }
      if ( (_WORD)v99 )
        memcpy_0(v101, *(const void **)(a1 + 216), 2 * v99);
      TIFFsetShortArrayExt(a1, a1 + 216, v102, *(unsigned __int16 *)(a1 + 212));
      TIFFfreeExt(a1, v102);
      v98 = (_WORD *)(a1 + 122);
    }
  }
LABEL_274:
  if ( *v98 == 3 && (*(_DWORD *)(a1 + 72) & 0x4000000) == 0 )
  {
    if ( *(_WORD *)(a1 + 116) < 8u )
    {
      v46 = "Colormap";
      goto LABEL_103;
    }
    if ( *(_WORD *)(a1 + 130) == 3 )
      *v98 = 2;
    else
      *v98 = 1;
  }
  if ( *(_WORD *)(a1 + 120) != 6 )
  {
    if ( (*(_DWORD *)(a1 + 72) & 0x1000000) != 0 )
    {
      if ( *(_DWORD *)(a1 + 228) == 1
        && (*(_DWORD *)(a1 + 16) & 0x400) == 0
        && (v104 = TIFFGetStrileByteCount(a1, 0), (v105 = TIFFGetStrileOffset(a1, 0)) != 0)
        && (!v104
         || *(_WORD *)(a1 + 120) == 1
         && ((v106 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 1216))(*(_QWORD *)(a1 + 1176)), v105 <= v106)
          && v104 > v106 - v105
          || !*(_DWORD *)(a1 + 12)
          && ((v107 = TIFFScanlineSize64(a1), v108 = *(unsigned int *)(a1 + 92), (_DWORD)v108)
           && v107 > 0xFFFFFFFFFFFFFFFFuLL / v108
           || v104 < v108 * v107))) )
      {
        TIFFWarningExtR(
          a1,
          "TIFFReadDirectory",
          "Bogus \"StripByteCounts\" field, ignoring and calculating from imagelength");
      }
      else
      {
        if ( (*(_DWORD *)(a1 + 16) & 0x1000000) != 0 )
          goto LABEL_310;
        if ( *(_WORD *)(a1 + 170) != 1 )
          goto LABEL_310;
        if ( *(_DWORD *)(a1 + 228) <= 2u )
          goto LABEL_310;
        if ( *(_WORD *)(a1 + 120) != 1 )
          goto LABEL_310;
        v109 = TIFFGetStrileByteCount(a1, 1);
        if ( TIFFGetStrileByteCount(a1, 0) == v109 || !TIFFGetStrileByteCount(a1, 0) || !TIFFGetStrileByteCount(a1, 1) )
          goto LABEL_310;
        TIFFWarningExtR(
          a1,
          "TIFFReadDirectory",
          "Wrong \"StripByteCounts\" field, ignoring and calculating from imagelength");
      }
      goto LABEL_309;
    }
    v103 = *(_WORD *)(a1 + 170);
    if ( v103 == 1 )
    {
      if ( *(_DWORD *)(a1 + 228) <= 1u )
      {
LABEL_283:
        TIFFWarningExtR(
          a1,
          "TIFFReadDirectory",
          "TIFF directory is missing required \"StripByteCounts\" field, calculating from imagelength");
LABEL_309:
        if ( (int)EstimateStripByteCounts(a1, v12, (unsigned __int16)v7) < 0 )
          goto LABEL_104;
        goto LABEL_310;
      }
    }
    else if ( v103 != 2 || *(_DWORD *)(a1 + 228) == *(unsigned __int16 *)(a1 + 130) )
    {
      goto LABEL_283;
    }
    v46 = "StripByteCounts";
    goto LABEL_103;
  }
LABEL_310:
  if ( v12 )
    TIFFfreeExt(a1, v12);
  if ( (*(_DWORD *)(a1 + 72) & 0x80000) == 0 )
  {
    v110 = *(_WORD *)(a1 + 116);
    if ( v110 < 0x10u )
      *(_WORD *)(a1 + 138) = (1 << v110) - 1;
    else
      *(_WORD *)(a1 + 138) = -1;
  }
  (*(void (__fastcall **)(__int64))(a1 + 928))(a1);
  if ( *(_WORD *)(a1 + 170) == 1 )
  {
    if ( *(_DWORD *)(a1 + 228) == 1
      && *(_WORD *)(a1 + 120) == 1
      && (*(_DWORD *)(a1 + 16) & 0x8400) == 0x8000
      && (TIFFGetStrileByteCount(a1, 0) || !*(_DWORD *)(a1 + 12)) )
    {
      v112 = TIFFGetStrileByteCount(a1, 0);
      if ( *(_WORD *)(a1 + 122) != 6 || (*(_DWORD *)(a1 + 16) & 0x4000) != 0 )
        v113 = 1;
      else
        v113 = *(unsigned __int16 *)(a1 + 338);
      v114 = TIFFVTileSize64(a1, v113);
      v115 = v114;
      if ( v114 > 0x2000 )
      {
LABEL_329:
        if ( v113 < *(_DWORD *)(a1 + 132) )
        {
          if ( v113 )
          {
            v117 = *(_DWORD *)(a1 + 92);
            if ( v117 < -v113 )
            {
              v111 = (v113 + v117 - 1) % v113;
              v118 = (v113 + v117 - 1) / v113;
              v119 = v118;
              if ( v118 )
              {
                if ( *(_DWORD *)(a1 + 12)
                  || v118 <= 0xF4240
                  || v112 < (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(a1 + 1216))(
                              *(_QWORD *)(a1 + 1176),
                              v111)
                  && (v120 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 1216))(*(_QWORD *)(a1 + 1176)),
                      v111 = (v120 - v112) % (v119 - 1),
                      v115 <= (v120 - v112) / (v119 - 1)) )
                {
                  allocChoppedUpStripArrays(a1, v119, v115, v113);
                }
              }
            }
          }
        }
        goto LABEL_338;
      }
      if ( v114 )
      {
        v116 = 0x2000 / v114;
        v111 = 0x2000 % v115;
        v113 *= v116;
        v115 *= v116;
        goto LABEL_329;
      }
    }
LABEL_338:
    if ( *(_WORD *)(a1 + 170) == 1
      && *(_WORD *)(a1 + 120) == 1
      && (*(_DWORD *)(a1 + 16) & 0x8400) == 0x8000
      && (unsigned __int64)TIFFStripSize64(a1, v111) > 0x7FFFFFFF )
    {
      TryChopUpUncompressedBigTiff(a1);
    }
  }
  *(_DWORD *)(a1 + 16) &= 0xFFDFFFF7;
  *(_DWORD *)(a1 + 844) = -1;
  *(_DWORD *)(a1 + 856) = -1;
  *(_QWORD *)(a1 + 904) = -1;
  *(_QWORD *)(a1 + 912) = -1;
  v121 = TIFFScanlineSize(a1);
  *(_QWORD *)(a1 + 1080) = v121;
  if ( !v121 )
  {
    TIFFErrorExtR(a1, "TIFFReadDirectory", "Cannot handle zero scanline size");
    return 0;
  }
  if ( (*(_DWORD *)(a1 + 16) & 0x400) != 0 )
  {
    v122 = TIFFTileSize(a1);
    *(_QWORD *)(a1 + 912) = v122;
    if ( !v122 )
    {
      TIFFErrorExtR(a1, "TIFFReadDirectory", "Cannot handle zero tile size");
      return 0;
    }
  }
  else if ( !TIFFStripSize(a1) )
  {
    TIFFErrorExtR(a1, "TIFFReadDirectory", "Cannot handle zero strip size");
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180161e70  push    rbx
0x180161e72  push    rsi
0x180161e73  push    rdi
0x180161e74  sub     rsp, 70h
0x180161e78  mov     rdi, [rcx+20h]
0x180161e7c  mov     rbx, rcx
0x180161e7f  test    rdi, rdi
0x180161e82  jnz     short loc_180161E92
0x180161e84  mov     [rcx+18h], rdi
0x180161e88  xor     eax, eax
0x180161e8a  add     rsp, 70h
0x180161e8e  pop     rdi
0x180161e8f  pop     rsi
0x180161e90  pop     rbx
0x180161e91  retn
0x180161e92  mov     ecx, [rcx+350h]
0x180161e98  xor     edx, edx
0x180161e9a  cmp     ecx, 0FFFFFFFFh
0x180161e9d  mov     r8, rdi
0x180161ea0  lea     eax, [rcx+1]
0x180161ea3  mov     rcx, rbx
0x180161ea6  cmovnz  edx, eax
0x180161ea9  call    _TIFFCheckDirNumberAndOffset
0x180161eae  test    eax, eax
0x180161eb0  jz      short loc_180161E88
0x180161eb2  lea     r9, [rbx+20h]
0x180161eb6  mov     [rsp+88h+var_40], r15
0x180161ebb  lea     r8, [rsp+88h+Src]
0x180161ec3  mov     rdx, rdi
0x180161ec6  mov     rcx, rbx
0x180161ec9  call    TIFFFetchDirectory
0x180161ece  movzx   r15d, ax
0x180161ed2  test    r15w, r15w
0x180161ed6  jnz     short loc_180161F00
0x180161ed8  mov     r9, rdi
0x180161edb  lea     r8, aFailedToReadDi; "Failed to read directory at offset %llu"
0x180161ee2  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180161ee9  mov     rcx, rbx
0x180161eec  call    TIFFErrorExtR
0x180161ef1  mov     r15, [rsp+88h+var_40]
0x180161ef6  xor     eax, eax
0x180161ef8  add     rsp, 70h
0x180161efc  pop     rdi
0x180161efd  pop     rsi
0x180161efe  pop     rbx
0x180161eff  retn
0x180161f00  mov     edx, [rbx+350h]
0x180161f06  xor     esi, esi
0x180161f08  cmp     edx, 0FFFFFFFFh
0x180161f0b  mov     [rsp+88h+var_28], r12
0x180161f10  mov     ecx, esi
0x180161f12  mov     r8d, esi
0x180161f15  lea     eax, [rdx+1]
0x180161f18  cmovnz  ecx, eax
0x180161f1b  mov     [rbx+350h], ecx
0x180161f21  movzx   ecx, si
0x180161f24  mov     r12, [rsp+88h+Src]
0x180161f2c  mov     [rsp+88h+var_58], r12
0x180161f31  mov     rax, r12
0x180161f34  cmp     si, r15w
0x180161f38  jnb     short loc_180161FB2
0x180161f3a  nop     word ptr [rax+rax+00h]
0x180161f40  movzx   edx, word ptr [rax]
0x180161f43  cmp     edx, r8d
0x180161f46  jb      short loc_180161F5F
0x180161f48  inc     cx
0x180161f4b  lea     r8d, [rdx+1]
0x180161f4f  add     rax, 20h ; ' '
0x180161f53  cmp     cx, r15w
0x180161f57  jb      short loc_180161F40
0x180161f59  movzx   r9d, si
0x180161f5d  jmp     short loc_180161F78
0x180161f5f  lea     r8, aInvalidTiffDir; "Invalid TIFF directory; tags are not so"...
0x180161f66  mov     rcx, rbx
0x180161f69  lea     rdx, aTiffreaddirect_0; "TIFFReadDirectoryCheckOrder"
0x180161f70  call    TIFFWarningExtR
0x180161f75  mov     r9d, esi
0x180161f78  mov     r8, r12
0x180161f7b  nop     dword ptr [rax+rax+00h]
0x180161f80  inc     r9w
0x180161f84  lea     rcx, [r8+20h]
0x180161f88  movzx   edx, r9w
0x180161f8c  cmp     r9w, r15w
0x180161f90  jnb     short loc_180161FB2
0x180161f92  movzx   eax, word ptr [rcx]
0x180161f95  cmp     [r8], ax
0x180161f99  jnz     short loc_180161F9F
0x180161f9b  mov     byte ptr [rcx+18h], 1
0x180161f9f  add     rcx, 20h ; ' '
0x180161fa3  inc     dx
0x180161fa6  cmp     dx, r15w
0x180161faa  jb      short loc_180161F92
0x180161fac  add     r8, 20h ; ' '
0x180161fb0  jmp     short loc_180161F80
0x180161fb2  mov     rax, [rbx+418h]
0x180161fb9  mov     rcx, rbx
0x180161fbc  and     dword ptr [rbx+10h], 0FBEFFFBFh
0x180161fc3  mov     [rsp+88h+var_20], rbp
0x180161fc8  mov     [rsp+88h+var_30], r13
0x180161fcd  mov     [rsp+88h+var_38], r14
0x180161fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180161fd7  mov     rcx, rbx
0x180161fda  call    TIFFFreeDirectory
0x180161fdf  mov     rcx, rbx
0x180161fe2  call    TIFFDefaultDirectory
0x180161fe7  mov     rdx, r15
0x180161fea  mov     byte ptr [rbx+199h], 1
0x180161ff1  shl     rdx, 4
0x180161ff5  mov     rcx, rbx
0x180161ff8  call    _TIFFmallocExt
0x180161ffd  mov     [rbx+1B8h], rax
0x180162004  mov     rcx, rbx
0x180162007  test    rax, rax
0x18016200a  jnz     short loc_180162024
0x18016200c  lea     r8, aFailedToAlloca_3; "Failed to allocate memory for counting "...
0x180162013  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x18016201a  call    TIFFErrorExtR
0x18016201f  jmp     def_180162211; jumptable 0000000180162211 default case
0x180162024  mov     r14d, 1
0x18016202a  mov     edx, 11Ch
0x18016202f  mov     r8d, r14d
0x180162032  call    TIFFSetField
0x180162037  lea     r13, __ImageBase
0x18016203e  mov     rdi, r12
0x180162041  movzx   eax, si
0x180162044  mov     ecx, 115h
0x180162049  mov     ebp, 103h
0x18016204e  cmp     si, r15w
0x180162052  jnb     short loc_180162098
0x180162054  cmp     [rdi], cx
0x180162057  jz      short loc_18016206B
0x180162059  add     rdi, 20h ; ' '
0x18016205d  inc     ax
0x180162060  cmp     ax, r15w
0x180162064  jb      short loc_180162054
0x180162066  movzx   eax, si
0x180162069  jmp     short loc_18016207F
0x18016206b  xor     r8d, r8d
0x18016206e  mov     rdx, rdi
0x180162071  mov     rcx, rbx
0x180162074  call    TIFFFetchNormalTag
0x180162079  mov     eax, esi
0x18016207b  mov     [rdi+18h], r14b
0x18016207f  mov     rdi, r12
0x180162082  cmp     [rdi], bp
0x180162085  jz      loc_1801621C6
0x18016208b  add     rdi, 20h ; ' '
0x18016208f  inc     ax
0x180162092  cmp     ax, r15w
0x180162096  jb      short loc_180162082
0x180162098  mov     r8d, r14d
0x18016209b  mov     edx, ebp
0x18016209d  mov     rcx, rbx
0x1801620a0  call    TIFFSetField
0x1801620a5  test    eax, eax
0x1801620a7  jz      def_180162211; jumptable 0000000180162211 default case
0x1801620ad  mov     r14d, esi
0x1801620b0  cmp     si, r15w
0x1801620b4  jnb     loc_18016240A
0x1801620ba  mov     edi, 0FFFFFFFFh
0x1801620bf  mov     rsi, r12
0x1801620c2  cmp     byte ptr [rsi+18h], 0
0x1801620c6  jnz     loc_1801623F6
0x1801620cc  mov     r8d, [rbx+4D8h]
0x1801620d3  movzx   ebp, word ptr [rsi]
0x1801620d6  test    r8d, r8d
0x1801620d9  jz      short loc_18016211B
0x1801620db  mov     r11, [rbx+4D0h]
0x1801620e2  mov     r10d, 0FFFFFFFFh
0x1801620e8  nop     dword ptr [rax+rax+00000000h]
0x1801620f0  lea     eax, [r8+r10]
0x1801620f4  cdq
0x1801620f5  sub     eax, edx
0x1801620f7  sar     eax, 1
0x1801620f9  movsxd  rdi, eax
0x1801620fc  mov     rdx, [r11+rdi*8]
0x180162100  cmp     [rdx], ebp
0x180162102  jz      loc_1801622F1
0x180162108  cmovnb  r8d, edi
0x18016210c  cmovnb  edi, r10d
0x180162110  mov     r10d, edi
0x180162113  lea     eax, [rdi+1]
0x180162116  cmp     eax, r8d
0x180162119  jnz     short loc_1801620F0
0x18016211b  mov     edi, 0FFFFFFFFh
0x180162120  mov     r9d, ebp
0x180162123  mov     dword ptr [rsp+88h+var_68], ebp
0x180162127  lea     r8, aUnknownFieldWi; "Unknown field with tag %hu (0x%hx) enco"...
0x18016212e  mov     rcx, rbx
0x180162131  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180162138  call    TIFFWarningExtR
0x18016213d  movzx   r8d, word ptr [rsi+2]
0x180162142  mov     rcx, rbx
0x180162145  movzx   edx, word ptr [rsi]
0x180162148  call    _TIFFCreateAnonField
0x18016214d  test    rax, rax
0x180162150  jz      loc_180162334
0x180162156  mov     r8d, 1
0x18016215c  mov     rdx, rax
0x18016215f  mov     rcx, rbx
0x180162162  call    _TIFFMergeFields
0x180162167  test    eax, eax
0x180162169  jz      loc_180162334
0x18016216f  mov     r8d, [rbx+4D8h]
0x180162176  test    r8d, r8d
0x180162179  jz      short loc_1801621BC
0x18016217b  mov     r11, [rbx+4D0h]
0x180162182  mov     r10d, 0FFFFFFFFh
0x180162188  movzx   r9d, word ptr [rsi]
0x18016218c  nop     dword ptr [rax+00h]
0x180162190  lea     eax, [r8+r10]
0x180162194  cdq
0x180162195  sub     eax, edx
0x180162197  sar     eax, 1
0x180162199  movsxd  rdi, eax
0x18016219c  mov     rcx, [r11+rdi*8]
0x1801621a0  cmp     [rcx], r9d
0x1801621a3  jz      loc_18016231B
0x1801621a9  cmovnb  r8d, edi
0x1801621ad  cmovnb  edi, r10d
0x1801621b1  mov     r10d, edi
0x1801621b4  lea     eax, [rdi+1]
0x1801621b7  cmp     eax, r8d
0x1801621ba  jnz     short loc_180162190
0x1801621bc  mov     edi, 0FFFFFFFFh
0x1801621c1  jmp     loc_180162357
0x1801621c6  lea     r8, [rsp+88h+Src]
0x1801621ce  mov     rdx, rdi
0x1801621d1  mov     rcx, rbx
0x1801621d4  call    TIFFReadDirEntryShort
0x1801621d9  cmp     eax, r14d
0x1801621dc  jnz     short loc_1801621F1
0x1801621de  lea     r8, [rsp+88h+Src]
0x1801621e6  mov     rdx, rdi
0x1801621e9  mov     rcx, rbx
0x1801621ec  call    TIFFReadDirEntryPersampleShort
0x1801621f1  test    eax, eax
0x1801621f3  jz      loc_1801622C9
0x1801621f9  dec     eax; switch 7 cases
0x1801621fb  cmp     eax, 6
0x1801621fe  ja      def_180162211; jumptable 0000000180162211 default case
0x180162204  cdqe
0x180162206  mov     ecx, ds:(jpt_180162211 - 180000000h)[r13+rax*4]
0x18016220e  add     rcx, r13
0x180162211  jmp     rcx; switch jump
0x180162213  lea     r9, aCompression; jumptable 0000000180162211 case 1
0x18016221a  lea     r8, aIncorrectCount_1; "Incorrect count for \"%s\""
0x180162221  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180162228  jmp     loc_1801624C7
0x18016222d  lea     r9, aCompression; jumptable 0000000180162211 case 2
0x180162234  lea     r8, aIncompatibleTy_0; "Incompatible type for \"%s\""
0x18016223b  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180162242  jmp     loc_1801624C7
0x180162247  lea     r9, aCompression; jumptable 0000000180162211 case 3
0x18016224e  lea     r8, aIoErrorDuringR_0; "IO error during reading of \"%s\""
0x180162255  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x18016225c  jmp     loc_1801624C7
0x180162261  lea     r9, aCompression; jumptable 0000000180162211 case 4
0x180162268  lea     r8, aIncorrectValue; "Incorrect value for \"%s\""
0x18016226f  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180162276  jmp     loc_1801624C7
0x18016227b  lea     r9, aCompression; jumptable 0000000180162211 case 5
0x180162282  lea     r8, aCannotHandleDi; "Cannot handle different values per samp"...
0x180162289  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180162290  jmp     loc_1801624C7
0x180162295  lea     r9, aCompression; jumptable 0000000180162211 case 6
0x18016229c  lea     r8, aSanityCheckOnS; "Sanity check on size of \"%s\" value fa"...
0x1801622a3  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x1801622aa  jmp     loc_1801624C7
0x1801622af  lea     r9, aCompression; jumptable 0000000180162211 case 7
0x1801622b6  lea     r8, aOutOfMemoryRea; "Out of memory reading of \"%s\""
0x1801622bd  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x1801622c4  jmp     loc_1801624C7
0x1801622c9  movzx   r8d, word ptr [rsp+88h+Src]
0x1801622d2  mov     edx, ebp
0x1801622d4  mov     rcx, rbx
0x1801622d7  call    TIFFSetField
0x1801622dc  test    eax, eax
0x1801622de  jz      def_180162211; jumptable 0000000180162211 default case
0x1801622e4  mov     [rdi+18h], r14b
0x1801622e8  movzx   r14d, si
0x1801622ec  jmp     loc_1801620BA
0x1801622f1  test    eax, eax
0x1801622f3  jz      short loc_180162311
0x1801622f5  nop     word ptr [rax+rax+00000000h]
0x180162300  movsxd  rax, edi
0x180162303  mov     rcx, [r11+rax*8-8]
0x180162308  cmp     [rcx], ebp
0x18016230a  jnz     short loc_180162311
0x18016230c  sub     edi, 1
0x18016230f  jnz     short loc_180162300
0x180162311  cmp     edi, 0FFFFFFFFh
0x180162314  jnz     short loc_180162357
0x180162316  jmp     loc_180162120
0x18016231b  test    eax, eax
0x18016231d  jz      short loc_180162357
0x18016231f  nop
0x180162320  movsxd  rax, edi
0x180162323  mov     rcx, [r11+rax*8-8]
0x180162328  cmp     [rcx], r9d
  ... truncated ...
```
