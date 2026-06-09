# TIFFReadDirectory

- ea: `0x180164d70`
- end: `0x1801663f8`
- name: `TIFFReadDirectory`
- size: `5768`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180150480`

## callees

- `0x180150ce0`
- `0x180150e00`
- `0x180150e40`
- `0x1801512b0`
- `0x180151340`
- `0x180151370`
- `0x1801514e0`
- `0x180151520`
- `0x180151d10`
- `0x180151e80`
- `0x180152200`
- `0x180154360`
- `0x180155840`
- `0x180155a70`
- `0x180155ae0`
- `0x18015c980`
- `0x18015d110`
- `0x18015d220`
- `0x18015d4e0`
- `0x18015d610`
- `0x18015d880`
- `0x18015da80`
- `0x18015e650`
- `0x18015e7a0`
- `0x18015eab0`
- `0x18015ebf0`
- `0x18015f1d0`
- `0x1801608d0`
- `0x180160b30`
- `0x180160bd0`
- `0x1801619d0`
- `0x180163550`
- `0x180163a20`
- `0x180163bb0`
- `0x180164d70`
- `0x180166400`
- `0x1801665f0`
- `0x180166a50`
- `0x180167040`
- `0x180167290`
- `0x18017e438`
- `0x1801ce010`

## string_xrefs

- `0x180165113`: `Compression`
- `0x18016512d`: `Compression`
- `0x180165147`: `Compression`
- `0x180165161`: `Compression`
- `0x18016517b`: `Compression`
- `0x180165195`: `Compression`
- `0x1801651af`: `Compression`
- `0x180164de2`: `TIFFReadDirectory`
- `0x180164f13`: `TIFFReadDirectory`
- `0x180165031`: `TIFFReadDirectory`
- `0x180165121`: `TIFFReadDirectory`
- `0x18016513b`: `TIFFReadDirectory`
- `0x180165155`: `TIFFReadDirectory`
- `0x18016516f`: `TIFFReadDirectory`
- `0x180165189`: `TIFFReadDirectory`
- `0x1801651a3`: `TIFFReadDirectory`
- `0x1801651bd`: `TIFFReadDirectory`
- `0x18016523f`: `TIFFReadDirectory`
- `0x18016539d`: `TIFFReadDirectory`
- `0x18016556e`: `TIFFReadDirectory`
- `0x1801655f8`: `TIFFReadDirectory`
- `0x180165640`: `TIFFReadDirectory`
- `0x18016567c`: `TIFFReadDirectory`
- `0x180165739`: `TIFFReadDirectory`
- `0x1801657ad`: `TIFFReadDirectory`
- `0x1801659ec`: `TIFFReadDirectory`
- `0x180165a02`: `TIFFReadDirectory`
- `0x180165a18`: `TIFFReadDirectory`
- `0x180165a2e`: `TIFFReadDirectory`
- `0x180165a44`: `TIFFReadDirectory`
- `0x180165a89`: `TIFFReadDirectory`
- `0x180165a9f`: `TIFFReadDirectory`
- `0x180165ac2`: `TIFFReadDirectory`
- `0x180165ae1`: `TIFFReadDirectory`
- `0x180165b21`: `TIFFReadDirectory`
- `0x180165b58`: `TIFFReadDirectory`
- `0x180165bf8`: `TIFFReadDirectory`
- `0x180165d9c`: `TIFFReadDirectory`
- `0x180165deb`: `TIFFReadDirectory`
- `0x180165fef`: `TIFFReadDirectory`
- `0x180166212`: `TIFFReadDirectory`
- `0x180166247`: `TIFFReadDirectory`
- `0x18016626c`: `TIFFReadDirectory`
- `0x180164e69`: `TIFFReadDirectoryCheckOrder`
- `0x180165134`: `Incompatible type for "%s"`
- `0x180165a82`: `Incompatible type for "%s"`
- `0x18016514e`: `IO error during reading of "%s"`
- `0x1801659fb`: `IO error during reading of "%s"`
- `0x1801651b6`: `Out of memory reading of "%s"`
- `0x180165a98`: `Out of memory reading of "%s"`
- `0x1801657dd`: `Incompatible type for "%s"; tag ignored`
- `0x1801657e9`: `IO error during reading of "%s"; tag ignored`
- `0x180165819`: `Out of memory reading of "%s"; tag ignored`
- `0x180164ddb`: `Failed to read directory at offset %llu`
- `0x180164f0c`: `Failed to allocate memory for counting IFD data size at reading`
- `0x18016538f`: `Planarconfig tag value assumed incorrect, assuming data is contig instead of chunky`
- `0x180165de4`: `Failed to allocate memory for temporary new sampleinfo array (%hu 16 bit elements)`
- `0x180165e9e`: `TIFF directory is missing required "StripByteCounts" field, calculating from imagelength`
- `0x180164e5f`: `Invalid TIFF directory; tags are not sorted in ascending order`
- `0x1801653b9`: `TIFF directory is missing required "%s" field`

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
  __int64 v19; // r9
  _WORD *v20; // rdi
  __int16 v21; // ax
  __int16 v22; // ax
  _WORD *v23; // rdi
  unsigned __int16 v24; // r14
  unsigned __int16 *v25; // rsi
  int v26; // r8d
  unsigned int v27; // ebp
  __int64 v28; // r11
  int v29; // r10d
  int v30; // eax
  int v31; // edi
  unsigned int *v32; // rdx
  __int64 v33; // rax
  int v34; // r8d
  __int64 v35; // r11
  int v36; // r10d
  unsigned int v37; // r9d
  int v38; // eax
  unsigned int *v39; // rcx
  int v40; // eax
  const char *v41; // r9
  const char *v42; // r8
  const char *v43; // rdx
  unsigned __int16 v44; // r8
  unsigned int v45; // edx
  _WORD *v46; // rax
  __int16 v47; // cx
  _WORD *v48; // rax
  __int16 v49; // cx
  __int64 v50; // r8
  unsigned __int16 v51; // r13
  unsigned __int16 *v52; // rbp
  const char *v53; // r12
  __int64 v54; // rdx
  __int64 v55; // rax
  __int64 v56; // r14
  int v57; // edi
  int v58; // eax
  int v59; // esi
  int v60; // eax
  int v61; // edi
  __int64 v62; // rax
  const char *v63; // r9
  void *v64; // rcx
  __int64 v65; // rax
  const char *v66; // r9
  __int64 v67; // r14
  __int64 v68; // rax
  const char *v69; // r9
  unsigned __int16 v70; // cx
  __int64 v71; // rax
  const char *v72; // r9
  unsigned int v73; // edi
  __int64 v74; // rcx
  __int64 v75; // rax
  int v76; // esi
  int v77; // eax
  __int64 v78; // rdx
  __int64 v79; // rax
  const char *v80; // r9
  __int64 v81; // rdx
  __int64 v82; // r8
  __int64 v83; // r9
  int v84; // esi
  _WORD *v85; // rdi
  int v86; // edi
  __int16 v87; // dx
  _WORD *v88; // rcx
  __int16 v89; // ax
  __int16 v90; // dx
  __int64 v91; // rdx
  __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // r8
  unsigned int v95; // eax
  __int64 v96; // rdx
  int v97; // r8d
  unsigned int v98; // r8d
  unsigned int v99; // r9d
  int v100; // eax
  bool v101; // zf
  unsigned int v102; // ecx
  _WORD *v103; // rdx
  __int64 v104; // rbp
  unsigned __int16 v105; // ax
  void *v106; // rax
  void *v107; // rdi
  __int16 v108; // ax
  unsigned __int64 v109; // rdi
  __int64 v110; // r8
  unsigned __int64 v111; // rsi
  unsigned __int64 v112; // rax
  __int64 v113; // rdx
  __int64 v114; // r8
  __int64 v115; // r9
  unsigned __int64 v116; // rax
  unsigned __int64 v117; // r8
  __int64 v118; // rdi
  unsigned __int16 v119; // cx
  unsigned __int64 v120; // rdx
  __int64 v121; // r8
  unsigned __int64 v122; // r14
  unsigned int v123; // edi
  unsigned __int64 v124; // rax
  unsigned __int64 v125; // rsi
  unsigned int v126; // eax
  unsigned int v127; // ecx
  unsigned int v128; // eax
  unsigned int v129; // ebp
  __int64 v130; // rax
  __int64 v131; // rax
  __int64 v132; // r9
  __int64 v133; // rax
  __int64 v134; // r9
  __int64 v135; // r9
  __int64 v136; // [rsp+20h] [rbp-68h]
  _WORD *v137; // [rsp+30h] [rbp-58h]
  __int16 *v138; // [rsp+38h] [rbp-50h] BYREF
  void *Src; // [rsp+90h] [rbp+8h] BYREF
  __int16 v140; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v141; // [rsp+A0h] [rbp+18h]
  __int64 v142; // [rsp+A8h] [rbp+20h] BYREF

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
  v137 = Src;
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
    TIFFErrorExtR(a1, "TIFFReadDirectory", "Failed to allocate memory for counting IFD data size at reading", v19);
    goto LABEL_105;
  }
  TIFFSetField(a1, 284, 1);
  v20 = v12;
  v21 = 0;
  if ( (_WORD)v7 )
  {
    while ( *v20 != 277 )
    {
      v20 += 16;
      if ( (unsigned __int16)++v21 >= (unsigned __int16)v7 )
      {
        v22 = 0;
        goto LABEL_29;
      }
    }
    TIFFFetchNormalTag(a1, v20, 0);
    v22 = 0;
    *((_BYTE *)v20 + 24) = 1;
LABEL_29:
    v23 = v12;
    while ( *v23 != 259 )
    {
      v23 += 16;
      if ( (unsigned __int16)++v22 >= (unsigned __int16)v7 )
        goto LABEL_32;
    }
    v40 = TIFFReadDirEntryShort(a1, v23, &Src);
    if ( v40 == 1 )
      v40 = TIFFReadDirEntryPersampleShort(a1, v23, &Src);
    if ( v40 )
    {
      switch ( v40 )
      {
        case 1:
          v41 = "Compression";
          v42 = "Incorrect count for \"%s\"";
          v43 = "TIFFReadDirectory";
          goto LABEL_104;
        case 2:
          v41 = "Compression";
          v42 = "Incompatible type for \"%s\"";
          v43 = "TIFFReadDirectory";
          goto LABEL_104;
        case 3:
          v41 = "Compression";
          v42 = "IO error during reading of \"%s\"";
          v43 = "TIFFReadDirectory";
          goto LABEL_104;
        case 4:
          v41 = "Compression";
          v42 = "Incorrect value for \"%s\"";
          v43 = "TIFFReadDirectory";
          goto LABEL_104;
        case 5:
          v41 = "Compression";
          v42 = "Cannot handle different values per sample for \"%s\"";
          v43 = "TIFFReadDirectory";
          goto LABEL_104;
        case 6:
          v41 = "Compression";
          v42 = "Sanity check on size of \"%s\" value failed";
          v43 = "TIFFReadDirectory";
          goto LABEL_104;
        case 7:
          v41 = "Compression";
          v42 = "Out of memory reading of \"%s\"";
          v43 = "TIFFReadDirectory";
          goto LABEL_104;
        default:
          break;
      }
LABEL_105:
      if ( v137 )
        TIFFfreeExt(a1, v137);
      return 0;
    }
    if ( !(unsigned int)TIFFSetField(a1, 259, (unsigned __int16)Src) )
      goto LABEL_105;
    *((_BYTE *)v23 + 24) = 1;
    v24 = 0;
    goto LABEL_34;
  }
LABEL_32:
  if ( !(unsigned int)TIFFSetField(a1, 259, 1) )
    goto LABEL_105;
  v24 = 0;
  if ( (_WORD)v7 )
  {
LABEL_34:
    v25 = v12;
    while ( 1 )
    {
      if ( *((_BYTE *)v25 + 24) )
        goto LABEL_86;
      v26 = *(_DWORD *)(a1 + 1240);
      v27 = *v25;
      if ( !v26 )
        break;
      v28 = *(_QWORD *)(a1 + 1232);
      v29 = -1;
      while ( 1 )
      {
        v30 = (v26 + v29) / 2;
        v31 = v30;
        v32 = *(unsigned int **)(v28 + 8LL * v30);
        if ( *v32 == v27 )
          break;
        if ( *v32 >= v27 )
        {
          v26 = (v26 + v29) / 2;
          v31 = v29;
        }
        v29 = v31;
        if ( v31 + 1 == v26 )
          goto LABEL_42;
      }
      if ( v30 )
      {
        do
        {
          if ( **(_DWORD **)(v28 + 8LL * v31 - 8) != v27 )
            break;
          --v31;
        }
        while ( v31 );
      }
      if ( v31 == -1 )
        goto LABEL_43;
LABEL_75:
      if ( !*((_BYTE *)v25 + 24) )
      {
        v44 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 1232) + 8LL * (unsigned int)v31) + 24LL);
        if ( v44 )
        {
          v45 = *v25;
          if ( v45 <= 0x80E5 )
          {
            if ( v45 != 32997 )
            {
              switch ( *v25 )
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
                  *(_DWORD *)(a1 + 4 * ((unsigned __int64)v44 >> 5) + 72) |= 1 << (v44 & 0x1F);
                  goto LABEL_86;
                default:
                  goto LABEL_82;
              }
            }
            goto LABEL_84;
          }
          if ( v45 == 32998 )
          {
LABEL_84:
            if ( !(unsigned int)TIFFFetchNormalTag(a1, v25, 0) )
              goto LABEL_105;
          }
          else
          {
LABEL_82:
            if ( (unsigned int)TIFFCheckFieldIsValidForCodec(a1) )
              goto LABEL_86;
          }
        }
        *((_BYTE *)v25 + 24) = 1;
      }
LABEL_86:
      ++v24;
      v25 += 16;
      if ( v24 >= (unsigned __int16)v7 )
        goto LABEL_87;
    }
LABEL_42:
    v31 = -1;
LABEL_43:
    TIFFWarningExtR(a1, "TIFFReadDirectory", "Unknown field with tag %hu (0x%hx) encountered", *v25, *v25);
    v33 = TIFFCreateAnonField(a1, *v25, v25[1]);
    if ( v33 && (unsigned int)TIFFMergeFields(a1, v33, 1) )
    {
      v34 = *(_DWORD *)(a1 + 1240);
      if ( v34 )
      {
        v35 = *(_QWORD *)(a1 + 1232);
        v36 = -1;
        v37 = *v25;
        while ( 1 )
        {
          v38 = (v34 + v36) / 2;
          v31 = v38;
          v39 = *(unsigned int **)(v35 + 8LL * v38);
          if ( *v39 == v37 )
            break;
          if ( *v39 >= v37 )
          {
            v34 = (v34 + v36) / 2;
            v31 = v36;
          }
          v36 = v31;
          if ( v31 + 1 == v34 )
            goto LABEL_51;
        }
        if ( v38 )
        {
          do
          {
            if ( **(_DWORD **)(v35 + 8LL * v31 - 8) != v37 )
              break;
            --v31;
          }
          while ( v31 );
        }
      }
      else
      {
LABEL_51:
        v31 = -1;
      }
    }
    else
    {
      TIFFWarningExtR(a1, "TIFFReadDirectory", "Registering anonymous field with tag %hu (0x%hx) failed", *v25, *v25);
      *((_BYTE *)v25 + 24) = 1;
    }
    goto LABEL_75;
  }
LABEL_87:
  if ( *(_WORD *)(a1 + 120) == 6 && *(_WORD *)(a1 + 170) == 2 )
  {
    if ( !(unsigned int)TIFFFillStrilesInternal(a1, 1) )
      goto LABEL_105;
    v46 = v12;
    v47 = 0;
    if ( (_WORD)v7 )
    {
      while ( *v46 != 273 )
      {
        v46 += 16;
        if ( (unsigned __int16)++v47 >= (unsigned __int16)v7 )
          goto LABEL_101;
      }
      if ( *((_QWORD *)v46 + 1) == 1 )
      {
        v48 = v12;
        v49 = 0;
        while ( *v48 != 279 )
        {
          v48 += 16;
          if ( (unsigned __int16)++v49 >= (unsigned __int16)v7 )
            goto LABEL_101;
        }
        if ( *((_QWORD *)v48 + 1) == 1 )
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
    v41 = "ImageLength";
LABEL_103:
    v42 = "TIFF directory is missing required \"%s\" field";
    v43 = "MissingRequired";
LABEL_104:
    TIFFErrorExtR(a1, v43, v42, v41);
    goto LABEL_105;
  }
  v141 = 0;
  v50 = 0;
  v51 = 0;
  v52 = v12;
  if ( (_WORD)v7 )
  {
    v53 = "unknown tagname";
    while ( 1 )
    {
      if ( !*((_BYTE *)v52 + 24) )
      {
        v54 = *v52;
        if ( (unsigned int)v54 > 0x80E4 )
        {
LABEL_205:
          TIFFFetchNormalTag(a1, v52, 1);
        }
        else if ( (_DWORD)v54 == 32996 )
        {
LABEL_190:
          v86 = TIFFReadDirEntryShort(a1, v52, &Src);
          if ( !(unsigned __int8)EvaluateIFDdatasizeReading(a1, v52) )
            goto LABEL_105;
          if ( v86 == 1 && *((_QWORD *)v52 + 1) >= (unsigned __int64)*(unsigned __int16 *)(a1 + 130) )
          {
            v86 = TIFFReadDirEntryShortArray(a1, v52, &v138);
            if ( !v86 )
            {
              if ( v138 )
              {
                v87 = *(_WORD *)(a1 + 130);
                v88 = v138 + 1;
                v89 = *v138;
                LOWORD(Src) = *v138;
                v90 = v87 - 1;
                if ( v90 )
                {
                  while ( *v88 == v89 )
                  {
                    ++v88;
                    if ( !--v90 )
                      goto LABEL_200;
                  }
                  v86 = 5;
                }
LABEL_200:
                TIFFfreeExt(a1, v138);
              }
            }
          }
          v91 = *v52;
          if ( v86 )
          {
            v93 = TIFFFieldWithTag(a1, v91);
            if ( v93 )
              v53 = *(const char **)(v93 + 32);
            switch ( v86 )
            {
              case 1:
                goto LABEL_209;
              case 2:
                goto LABEL_217;
              case 3:
                goto LABEL_210;
              case 4:
                goto LABEL_211;
              case 5:
                goto LABEL_212;
              case 6:
                goto LABEL_213;
              case 7:
                goto LABEL_218;
              default:
                goto LABEL_105;
            }
            goto LABEL_105;
          }
          if ( !(unsigned int)TIFFSetField(a1, v91, (unsigned __int16)Src) )
            goto LABEL_105;
          if ( *v52 == 258 )
          {
            v50 = 1;
            v141 = 1;
            goto LABEL_172;
          }
        }
        else
        {
          switch ( *v52 )
          {
            case 0xFFu:
              if ( !(unsigned int)TIFFReadDirEntryShort(a1, v52, &v140) )
              {
                if ( v140 == 2 )
                {
                  TIFFSetField(a1, 254, 1);
                }
                else if ( v140 == 3 )
                {
                  TIFFSetField(a1, 254, 2);
                }
              }
              break;
            case 0x102u:
            case 0x118u:
            case 0x119u:
            case 0x153u:
              goto LABEL_190;
            case 0x111u:
            case 0x144u:
              if ( v52[1] != 3
                && v52[1] != 4
                && v52[1] != 16
                && (*(_DWORD *)(a1 + 12) != 2 || *((_QWORD *)v52 + 1) || v52[1] || *((_QWORD *)v52 + 2)) )
              {
                v62 = TIFFFieldWithTag(a1, v54);
                if ( v62 )
                  v63 = *(const char **)(v62 + 32);
                else
                  v63 = "unknown tagname";
                TIFFWarningExtR(a1, "TIFFReadDirectory", "Invalid data type for tag %s", v63);
              }
              v64 = (void *)(a1 + 256);
              goto LABEL_133;
            case 0x117u:
            case 0x145u:
              if ( v52[1] != 3
                && v52[1] != 4
                && v52[1] != 16
                && (*(_DWORD *)(a1 + 12) != 2 || *((_QWORD *)v52 + 1) || v52[1] || *((_QWORD *)v52 + 2)) )
              {
                v65 = TIFFFieldWithTag(a1, v54);
                if ( v65 )
                  v66 = *(const char **)(v65 + 32);
                else
                  v66 = "unknown tagname";
                TIFFWarningExtR(a1, "TIFFReadDirectory", "Invalid data type for tag %s", v66);
              }
              v64 = (void *)(a1 + 288);
LABEL_133:
              TIFFmemcpy(v64, v52, 0x20u);
              if ( (unsigned __int8)EvaluateIFDdatasizeReading(a1, v52) )
                break;
              goto LABEL_105;
            case 0x12Du:
            case 0x140u:
              v142 = 0;
              v67 = 0;
              if ( (_DWORD)v50 )
              {
                v70 = *(_WORD *)(a1 + 116);
                if ( v70 <= 0x18u )
                {
                  v73 = 1 << v70;
                  v74 = *((_QWORD *)v52 + 1);
                  if ( (_WORD)v54 == 301 && v74 == v73 )
                  {
                    v75 = v73;
                    v73 = 0;
                  }
                  else
                  {
                    v75 = 3 * v73;
                  }
                  if ( v74 == v75 )
                  {
                    v77 = TIFFReadDirEntryShortArray(a1, v52, &v142);
                    v67 = v142;
                    v76 = v77;
                  }
                  else
                  {
                    v76 = 1;
                  }
                  if ( !(unsigned __int8)EvaluateIFDdatasizeReading(a1, v52) )
                    goto LABEL_105;
                  v78 = *v52;
                  if ( v76 )
                  {
                    v79 = TIFFFieldWithTag(a1, v78);
                    if ( v79 )
                      v80 = *(const char **)(v79 + 32);
                    else
                      v80 = "unknown tagname";
                    switch ( v76 )
                    {
                      case 1:
                        TIFFWarningExtR(a1, "TIFFReadDirectory", "Incorrect count for \"%s\"; tag ignored", v80);
                        break;
                      case 2:
                        TIFFWarningExtR(a1, "TIFFReadDirectory", "Incompatible type for \"%s\"; tag ignored", v80);
                        break;
                      case 3:
                        TIFFWarningExtR(a1, "TIFFReadDirectory", "IO error during reading of \"%s\"; tag ignored", v80);
                        break;
                      case 4:
                        TIFFWarningExtR(a1, "TIFFReadDirectory", "Incorrect value for \"%s\"; tag ignored", v80);
                        break;
                      case 5:
                        TIFFWarningExtR(
                          a1,
                          "TIFFReadDirectory",
                          "Cannot handle different values per sample for \"%s\"; tag ignored",
                          v80);
                        break;
                      case 6:
                        TIFFWarningExtR(
                          a1,
                          "TIFFReadDirectory",
                          "Sanity check on size of \"%s\" value failed; tag ignored",
                          v80);
                        break;
                      case 7:
                        TIFFWarningExtR(a1, "TIFFReadDirectory", "Out of memory reading of \"%s\"; tag ignored", v80);
                        break;
                      default:
                        goto LABEL_171;
                    }
                  }
                  else
                  {
                    v136 = v67 + 4LL * v73;
                    TIFFSetField(a1, v78, v67);
                    TIFFfreeExt(a1, v67);
                  }
                }
                else
                {
                  v71 = TIFFFieldWithTag(a1, v54);
                  if ( v71 )
                    v72 = *(const char **)(v71 + 32);
                  else
                    v72 = "unknown tagname";
                  TIFFWarningExtR(
                    a1,
                    "TIFFReadDirectory",
                    "Ignoring %s because BitsPerSample=%hu>24",
                    v72,
                    *(unsigned __int16 *)(a1 + 116));
                }
              }
              else
              {
                v68 = TIFFFieldWithTag(a1, v54);
                if ( v68 )
                  v69 = *(const char **)(v68 + 32);
                else
                  v69 = "unknown tagname";
                TIFFWarningExtR(a1, "TIFFReadDirectory", "Ignoring %s since BitsPerSample tag not found", v69);
              }
              break;
            case 0x154u:
            case 0x155u:
              v55 = *(unsigned __int16 *)(a1 + 130);
              v56 = 0;
              v142 = 0;
              if ( *((_QWORD *)v52 + 1) == v55 )
              {
                v58 = TIFFReadDirEntryDoubleArray(a1, v52, &v142, 301, v136);
                v56 = v142;
                v57 = v58;
              }
              else
              {
                v57 = 1;
              }
              if ( !(unsigned __int8)EvaluateIFDdatasizeReading(a1, v52) )
                goto LABEL_105;
              if ( v57 )
              {
                v92 = TIFFFieldWithTag(a1, *v52);
                if ( v92 )
                  v53 = *(const char **)(v92 + 32);
                switch ( v57 )
                {
                  case 1:
LABEL_209:
                    v41 = v53;
                    v42 = "Incorrect count for \"%s\"";
                    v43 = "TIFFReadDirectory";
                    goto LABEL_104;
                  case 2:
LABEL_217:
                    v41 = v53;
                    v42 = "Incompatible type for \"%s\"";
                    v43 = "TIFFReadDirectory";
                    goto LABEL_104;
                  case 3:
LABEL_210:
                    v41 = v53;
                    v42 = "IO error during reading of \"%s\"";
                    v43 = "TIFFReadDirectory";
                    goto LABEL_104;
                  case 4:
LABEL_211:
                    v41 = v53;
                    v42 = "Incorrect value for \"%s\"";
                    v43 = "TIFFReadDirectory";
                    goto LABEL_104;
                  case 5:
LABEL_212:
                    v41 = v53;
                    v42 = "Cannot handle different values per sample for \"%s\"";
                    v43 = "TIFFReadDirectory";
                    goto LABEL_104;
                  case 6:
LABEL_213:
                    v41 = v53;
                    v42 = "Sanity check on size of \"%s\" value failed";
                    v43 = "TIFFReadDirectory";
                    goto LABEL_104;
                  case 7:
LABEL_218:
                    v41 = v53;
                    v42 = "Out of memory reading of \"%s\"";
                    v43 = "TIFFReadDirectory";
                    goto LABEL_104;
                  default:
                    goto LABEL_105;
                }
                goto LABEL_105;
              }
              v59 = *(_DWORD *)(a1 + 16);
              *(_DWORD *)(a1 + 16) = v59 | 0x400000;
              v60 = TIFFSetField(a1, *v52, v56);
              *(_DWORD *)(a1 + 16) = v59;
              v61 = v60;
              TIFFfreeExt(a1, v56);
              if ( !v61 )
                goto LABEL_105;
              break;
            default:
              goto LABEL_205;
          }
        }
LABEL_171:
        v50 = v141;
      }
LABEL_172:
      ++v51;
      v52 += 16;
      if ( v51 >= (unsigned __int16)v7 )
      {
        v12 = v137;
        break;
      }
    }
  }
  CalcFinalIFDdatasizeReading(a1, (unsigned __int16)v7, v50);
  v84 = 3;
  if ( *(_WORD *)(a1 + 120) == 6 )
  {
    if ( (*(_DWORD *)(a1 + 72) & 0x100) != 0 )
    {
      v85 = (_WORD *)(a1 + 122);
      if ( *(_WORD *)(a1 + 122) == 2 )
      {
        *v85 = 6;
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
        goto LABEL_105;
      v85 = (_WORD *)(a1 + 122);
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x40) == 0 )
    {
      TIFFWarningExtR(a1, "TIFFReadDirectory", "BitsPerSample tag is missing, assuming 8 bits per sample");
      if ( !(unsigned int)TIFFSetField(a1, 258, 8) )
        goto LABEL_105;
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x10000) == 0 )
    {
      if ( *v85 == 2 )
      {
        TIFFWarningExtR(
          a1,
          "TIFFReadDirectory",
          "SamplesPerPixel tag is missing, assuming correct SamplesPerPixel value is 3");
        if ( !(unsigned int)TIFFSetField(a1, 277, 3) )
          goto LABEL_105;
      }
      if ( *v85 == 6 )
      {
        TIFFWarningExtR(
          a1,
          "TIFFReadDirectory",
          "SamplesPerPixel tag is missing, applying correct SamplesPerPixel value of 3");
        v94 = 3;
      }
      else
      {
        if ( *v85 > 1u )
          goto LABEL_231;
        v94 = 1;
      }
      if ( !(unsigned int)TIFFSetField(a1, 277, v94) )
        goto LABEL_105;
    }
  }
LABEL_231:
  if ( (*(_BYTE *)(a1 + 72) & 4) != 0 )
  {
    v95 = TIFFNumberOfTiles(a1, v81, v82, v83);
    v98 = *(_DWORD *)(a1 + 16) | 0x400;
  }
  else
  {
    v95 = TIFFNumberOfStrips(a1, v81, v82, v83);
    v97 = *(_DWORD *)(a1 + 16);
    *(_DWORD *)(a1 + 100) = *(_DWORD *)(a1 + 88);
    v98 = v97 & 0xFFFFFBFF;
    *(_DWORD *)(a1 + 104) = *(_DWORD *)(a1 + 132);
    *(_DWORD *)(a1 + 108) = *(_DWORD *)(a1 + 96);
  }
  *(_DWORD *)(a1 + 16) = v98;
  *(_DWORD *)(a1 + 228) = v95;
  v99 = v95;
  if ( !v95 )
  {
    v41 = "strips";
    if ( (v98 & 0x400) != 0 )
      v41 = "tiles";
    v42 = "Cannot handle zero number of %s";
    v43 = "TIFFReadDirectory";
    goto LABEL_104;
  }
  v101 = *(_WORD *)(a1 + 170) == 2;
  *(_DWORD *)(a1 + 224) = v95;
  if ( v101 )
  {
    v96 = v95 % *(unsigned __int16 *)(a1 + 130);
    *(_DWORD *)(a1 + 224) = v95 / *(unsigned __int16 *)(a1 + 130);
  }
  v100 = *(_DWORD *)(a1 + 72);
  if ( (v100 & 0x2000000) == 0 )
  {
    if ( *(_WORD *)(a1 + 120) == 6 )
    {
      v101 = (v98 & 0x400) == 0;
      if ( (v98 & 0x400) != 0 )
        goto LABEL_256;
      if ( v99 == 1 )
      {
        *(_DWORD *)(a1 + 72) = v100 | 0x2000000;
        goto LABEL_245;
      }
    }
    v101 = (v98 & 0x400) == 0;
LABEL_256:
    v41 = "StripOffsets";
    if ( !v101 )
      v41 = "TileOffsets";
    goto LABEL_103;
  }
LABEL_245:
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
    if ( (v98 & 0x1000000) == 0
      && (*(_WORD *)(a1 + 256)
       && !(unsigned int)TIFFFetchStripThing(a1, a1 + 256, *(unsigned int *)(a1 + 228), a1 + 232)
       || *(_WORD *)(a1 + 288)
       && !(unsigned int)TIFFFetchStripThing(a1, a1 + 288, *(unsigned int *)(a1 + 228), a1 + 240)) )
    {
      goto LABEL_105;
    }
  }
  else
  {
    TIFFSetupStrips(a1, v96);
  }
  v102 = *(unsigned __int16 *)(a1 + 122);
  v103 = (_WORD *)(a1 + 122);
  if ( v102 <= 0x8023 )
  {
    switch ( *(_WORD *)(a1 + 122) )
    {
      case 0:
      case 1:
      case 3:
        v84 = 1;
        goto LABEL_269;
      case 2:
      case 6:
      case 8:
      case 9:
      case 0xA:
        goto LABEL_269;
      case 4:
      case 5:
        v84 = 4;
        goto LABEL_269;
      default:
        goto LABEL_275;
    }
  }
  if ( v102 == 32845 )
  {
LABEL_269:
    if ( *(unsigned __int16 *)(a1 + 130) - *(unsigned __int16 *)(a1 + 212) > v84 )
    {
      TIFFWarningExtR(
        a1,
        "TIFFReadDirectory",
        "Sum of Photometric type-related color channels and ExtraSamples doesn't match SamplesPerPixel. Defining non-colo"
        "r channels as ExtraSamples.");
      v104 = *(unsigned __int16 *)(a1 + 212);
      v105 = *(_WORD *)(a1 + 130) - v84;
      *(_WORD *)(a1 + 212) = v105;
      v106 = (void *)TIFFcallocExt(a1, v105, 2);
      v107 = v106;
      if ( !v106 )
      {
        TIFFErrorExtR(
          a1,
          "TIFFReadDirectory",
          "Failed to allocate memory for temporary new sampleinfo array (%hu 16 bit elements)",
          *(unsigned __int16 *)(a1 + 212));
        goto LABEL_105;
      }
      if ( (_WORD)v104 )
        memcpy_0(v106, *(const void **)(a1 + 216), 2 * v104);
      TIFFsetShortArrayExt(a1, a1 + 216, v107, *(unsigned __int16 *)(a1 + 212));
      TIFFfreeExt(a1, v107);
      v103 = (_WORD *)(a1 + 122);
    }
  }
LABEL_275:
  if ( *v103 == 3 && (*(_DWORD *)(a1 + 72) & 0x4000000) == 0 )
  {
    if ( *(_WORD *)(a1 + 116) < 8u )
    {
      v41 = "Colormap";
      goto LABEL_103;
    }
    if ( *(_WORD *)(a1 + 130) == 3 )
      *v103 = 2;
    else
      *v103 = 1;
  }
  if ( *(_WORD *)(a1 + 120) != 6 )
  {
    if ( (*(_DWORD *)(a1 + 72) & 0x1000000) != 0 )
    {
      if ( *(_DWORD *)(a1 + 228) == 1
        && (*(_DWORD *)(a1 + 16) & 0x400) == 0
        && (v109 = TIFFGetStrileByteCount(a1, 0), (v111 = TIFFGetStrileOffset(a1, 0, v110)) != 0)
        && (!v109
         || *(_WORD *)(a1 + 120) == 1
         && ((v112 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 1216))(*(_QWORD *)(a1 + 1176)), v111 <= v112)
          && v109 > v112 - v111
          || !*(_DWORD *)(a1 + 12)
          && ((v116 = TIFFScanlineSize64(a1, v113, v114, v115), v117 = *(unsigned int *)(a1 + 92), (_DWORD)v117)
           && v116 > 0xFFFFFFFFFFFFFFFFuLL / v117
           || v109 < v117 * v116))) )
      {
        TIFFWarningExtR(
          a1,
          "TIFFReadDirectory",
          "Bogus \"StripByteCounts\" field, ignoring and calculating from imagelength");
      }
      else
      {
        if ( (*(_DWORD *)(a1 + 16) & 0x1000000) != 0 )
          goto LABEL_311;
        if ( *(_WORD *)(a1 + 170) != 1 )
          goto LABEL_311;
        if ( *(_DWORD *)(a1 + 228) <= 2u )
          goto LABEL_311;
        if ( *(_WORD *)(a1 + 120) != 1 )
          goto LABEL_311;
        v118 = TIFFGetStrileByteCount(a1, 1);
        if ( TIFFGetStrileByteCount(a1, 0) == v118 || !TIFFGetStrileByteCount(a1, 0) || !TIFFGetStrileByteCount(a1, 1) )
          goto LABEL_311;
        TIFFWarningExtR(
          a1,
          "TIFFReadDirectory",
          "Wrong \"StripByteCounts\" field, ignoring and calculating from imagelength");
      }
      goto LABEL_310;
    }
    v108 = *(_WORD *)(a1 + 170);
    if ( v108 == 1 )
    {
      if ( *(_DWORD *)(a1 + 228) <= 1u )
      {
LABEL_284:
        TIFFWarningExtR(
          a1,
          "TIFFReadDirectory",
          "TIFF directory is missing required \"StripByteCounts\" field, calculating from imagelength");
LABEL_310:
        if ( (int)EstimateStripByteCounts(a1, v12, (unsigned __int16)v7) < 0 )
          goto LABEL_105;
        goto LABEL_311;
      }
    }
    else if ( v108 != 2 || *(_DWORD *)(a1 + 228) == *(unsigned __int16 *)(a1 + 130) )
    {
      goto LABEL_284;
    }
    v41 = "StripByteCounts";
    goto LABEL_103;
  }
LABEL_311:
  if ( v12 )
    TIFFfreeExt(a1, v12);
  if ( (*(_DWORD *)(a1 + 72) & 0x80000) == 0 )
  {
    v119 = *(_WORD *)(a1 + 116);
    if ( v119 < 0x10u )
      *(_WORD *)(a1 + 138) = (1 << v119) - 1;
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
      v122 = TIFFGetStrileByteCount(a1, 0);
      if ( *(_WORD *)(a1 + 122) != 6 || (*(_DWORD *)(a1 + 16) & 0x4000) != 0 )
        v123 = 1;
      else
        v123 = *(unsigned __int16 *)(a1 + 338);
      v124 = TIFFVTileSize64(a1, v123);
      v125 = v124;
      if ( v124 > 0x2000 )
      {
LABEL_330:
        if ( v123 < *(_DWORD *)(a1 + 132) )
        {
          if ( v123 )
          {
            v127 = *(_DWORD *)(a1 + 92);
            if ( v127 < -v123 )
            {
              v120 = (v123 + v127 - 1) % v123;
              v128 = (v123 + v127 - 1) / v123;
              v129 = v128;
              if ( v128 )
              {
                if ( *(_DWORD *)(a1 + 12)
                  || v128 <= 0xF4240
                  || v122 < (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(a1 + 1216))(
                              *(_QWORD *)(a1 + 1176),
                              v120)
                  && (v130 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 1216))(*(_QWORD *)(a1 + 1176)),
                      v120 = (v130 - v122) % (v129 - 1),
                      v125 <= (v130 - v122) / (v129 - 1)) )
                {
                  allocChoppedUpStripArrays(a1, v129, v125, v123);
                }
              }
            }
          }
        }
        goto LABEL_339;
      }
      if ( v124 )
      {
        v126 = 0x2000 / v124;
        v120 = 0x2000 % v125;
        v123 *= v126;
        v125 *= v126;
        goto LABEL_330;
      }
    }
LABEL_339:
    if ( *(_WORD *)(a1 + 170) == 1
      && *(_WORD *)(a1 + 120) == 1
      && (*(_DWORD *)(a1 + 16) & 0x8400) == 0x8000
      && (unsigned __int64)TIFFStripSize64(a1, v120) > 0x7FFFFFFF )
    {
      TryChopUpUncompressedBigTiff(a1);
    }
  }
  *(_DWORD *)(a1 + 16) &= 0xFFDFFFF7;
  *(_DWORD *)(a1 + 844) = -1;
  *(_DWORD *)(a1 + 856) = -1;
  *(_QWORD *)(a1 + 904) = -1;
  *(_QWORD *)(a1 + 912) = -1;
  v131 = TIFFScanlineSize(a1, v120, v121);
  *(_QWORD *)(a1 + 1080) = v131;
  if ( !v131 )
  {
    TIFFErrorExtR(a1, "TIFFReadDirectory", "Cannot handle zero scanline size", v132);
    return 0;
  }
  if ( (*(_DWORD *)(a1 + 16) & 0x400) != 0 )
  {
    v133 = TIFFTileSize(a1);
    *(_QWORD *)(a1 + 912) = v133;
    if ( !v133 )
    {
      TIFFErrorExtR(a1, "TIFFReadDirectory", "Cannot handle zero tile size", v134);
      return 0;
    }
  }
  else if ( !TIFFStripSize(a1) )
  {
    TIFFErrorExtR(a1, "TIFFReadDirectory", "Cannot handle zero strip size", v135);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180164d70  push    rbx
0x180164d72  push    rsi
0x180164d73  push    rdi
0x180164d74  sub     rsp, 70h
0x180164d78  mov     rdi, [rcx+20h]
0x180164d7c  mov     rbx, rcx
0x180164d7f  test    rdi, rdi
0x180164d82  jnz     short loc_180164D92
0x180164d84  mov     [rcx+18h], rdi
0x180164d88  xor     eax, eax
0x180164d8a  add     rsp, 70h
0x180164d8e  pop     rdi
0x180164d8f  pop     rsi
0x180164d90  pop     rbx
0x180164d91  retn
0x180164d92  mov     ecx, [rcx+350h]
0x180164d98  xor     edx, edx
0x180164d9a  cmp     ecx, 0FFFFFFFFh
0x180164d9d  mov     r8, rdi
0x180164da0  lea     eax, [rcx+1]
0x180164da3  mov     rcx, rbx
0x180164da6  cmovnz  edx, eax
0x180164da9  call    _TIFFCheckDirNumberAndOffset
0x180164dae  test    eax, eax
0x180164db0  jz      short loc_180164D88
0x180164db2  lea     r9, [rbx+20h]
0x180164db6  mov     [rsp+88h+var_40], r15
0x180164dbb  lea     r8, [rsp+88h+Src]
0x180164dc3  mov     rdx, rdi
0x180164dc6  mov     rcx, rbx
0x180164dc9  call    TIFFFetchDirectory
0x180164dce  movzx   r15d, ax
0x180164dd2  test    r15w, r15w
0x180164dd6  jnz     short loc_180164E00
0x180164dd8  mov     r9, rdi
0x180164ddb  lea     r8, aFailedToReadDi; "Failed to read directory at offset %llu"
0x180164de2  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180164de9  mov     rcx, rbx
0x180164dec  call    TIFFErrorExtR
0x180164df1  mov     r15, [rsp+88h+var_40]
0x180164df6  xor     eax, eax
0x180164df8  add     rsp, 70h
0x180164dfc  pop     rdi
0x180164dfd  pop     rsi
0x180164dfe  pop     rbx
0x180164dff  retn
0x180164e00  mov     edx, [rbx+350h]
0x180164e06  xor     esi, esi
0x180164e08  cmp     edx, 0FFFFFFFFh
0x180164e0b  mov     [rsp+88h+var_28], r12
0x180164e10  mov     ecx, esi
0x180164e12  mov     r8d, esi
0x180164e15  lea     eax, [rdx+1]
0x180164e18  cmovnz  ecx, eax
0x180164e1b  mov     [rbx+350h], ecx
0x180164e21  movzx   ecx, si
0x180164e24  mov     r12, [rsp+88h+Src]
0x180164e2c  mov     [rsp+88h+var_58], r12
0x180164e31  mov     rax, r12
0x180164e34  cmp     si, r15w
0x180164e38  jnb     short loc_180164EB2
0x180164e3a  nop     word ptr [rax+rax+00h]
0x180164e40  movzx   edx, word ptr [rax]
0x180164e43  cmp     edx, r8d
0x180164e46  jb      short loc_180164E5F
0x180164e48  inc     cx
0x180164e4b  lea     r8d, [rdx+1]
0x180164e4f  add     rax, 20h ; ' '
0x180164e53  cmp     cx, r15w
0x180164e57  jb      short loc_180164E40
0x180164e59  movzx   r9d, si
0x180164e5d  jmp     short loc_180164E78
0x180164e5f  lea     r8, aInvalidTiffDir; "Invalid TIFF directory; tags are not so"...
0x180164e66  mov     rcx, rbx
0x180164e69  lea     rdx, aTiffreaddirect_0; "TIFFReadDirectoryCheckOrder"
0x180164e70  call    TIFFWarningExtR
0x180164e75  mov     r9d, esi
0x180164e78  mov     r8, r12
0x180164e7b  nop     dword ptr [rax+rax+00h]
0x180164e80  inc     r9w
0x180164e84  lea     rcx, [r8+20h]
0x180164e88  movzx   edx, r9w
0x180164e8c  cmp     r9w, r15w
0x180164e90  jnb     short loc_180164EB2
0x180164e92  movzx   eax, word ptr [rcx]
0x180164e95  cmp     [r8], ax
0x180164e99  jnz     short loc_180164E9F
0x180164e9b  mov     byte ptr [rcx+18h], 1
0x180164e9f  add     rcx, 20h ; ' '
0x180164ea3  inc     dx
0x180164ea6  cmp     dx, r15w
0x180164eaa  jb      short loc_180164E92
0x180164eac  add     r8, 20h ; ' '
0x180164eb0  jmp     short loc_180164E80
0x180164eb2  mov     rax, [rbx+418h]
0x180164eb9  mov     rcx, rbx
0x180164ebc  and     dword ptr [rbx+10h], 0FBEFFFBFh
0x180164ec3  mov     [rsp+88h+var_20], rbp
0x180164ec8  mov     [rsp+88h+var_30], r13
0x180164ecd  mov     [rsp+88h+var_38], r14
0x180164ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164ed7  mov     rcx, rbx
0x180164eda  call    TIFFFreeDirectory
0x180164edf  mov     rcx, rbx
0x180164ee2  call    TIFFDefaultDirectory
0x180164ee7  mov     rdx, r15
0x180164eea  mov     byte ptr [rbx+199h], 1
0x180164ef1  shl     rdx, 4
0x180164ef5  mov     rcx, rbx
0x180164ef8  call    _TIFFmallocExt
0x180164efd  mov     [rbx+1B8h], rax
0x180164f04  mov     rcx, rbx
0x180164f07  test    rax, rax
0x180164f0a  jnz     short loc_180164F24
0x180164f0c  lea     r8, aFailedToAlloca_3; "Failed to allocate memory for counting "...
0x180164f13  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180164f1a  call    TIFFErrorExtR
0x180164f1f  jmp     def_180165111; jumptable 0000000180165111 default case
0x180164f24  mov     r14d, 1
0x180164f2a  mov     edx, 11Ch
0x180164f2f  mov     r8d, r14d
0x180164f32  call    TIFFSetField
0x180164f37  lea     r13, __ImageBase
0x180164f3e  mov     rdi, r12
0x180164f41  movzx   eax, si
0x180164f44  mov     ecx, 115h
0x180164f49  mov     ebp, 103h
0x180164f4e  cmp     si, r15w
0x180164f52  jnb     short loc_180164F98
0x180164f54  cmp     [rdi], cx
0x180164f57  jz      short loc_180164F6B
0x180164f59  add     rdi, 20h ; ' '
0x180164f5d  inc     ax
0x180164f60  cmp     ax, r15w
0x180164f64  jb      short loc_180164F54
0x180164f66  movzx   eax, si
0x180164f69  jmp     short loc_180164F7F
0x180164f6b  xor     r8d, r8d
0x180164f6e  mov     rdx, rdi
0x180164f71  mov     rcx, rbx
0x180164f74  call    TIFFFetchNormalTag
0x180164f79  mov     eax, esi
0x180164f7b  mov     [rdi+18h], r14b
0x180164f7f  mov     rdi, r12
0x180164f82  cmp     [rdi], bp
0x180164f85  jz      loc_1801650C6
0x180164f8b  add     rdi, 20h ; ' '
0x180164f8f  inc     ax
0x180164f92  cmp     ax, r15w
0x180164f96  jb      short loc_180164F82
0x180164f98  mov     r8d, r14d
0x180164f9b  mov     edx, ebp
0x180164f9d  mov     rcx, rbx
0x180164fa0  call    TIFFSetField
0x180164fa5  test    eax, eax
0x180164fa7  jz      def_180165111; jumptable 0000000180165111 default case
0x180164fad  mov     r14d, esi
0x180164fb0  cmp     si, r15w
0x180164fb4  jnb     loc_18016530A
0x180164fba  mov     edi, 0FFFFFFFFh
0x180164fbf  mov     rsi, r12
0x180164fc2  cmp     byte ptr [rsi+18h], 0
0x180164fc6  jnz     loc_1801652F6
0x180164fcc  mov     r8d, [rbx+4D8h]
0x180164fd3  movzx   ebp, word ptr [rsi]
0x180164fd6  test    r8d, r8d
0x180164fd9  jz      short loc_18016501B
0x180164fdb  mov     r11, [rbx+4D0h]
0x180164fe2  mov     r10d, 0FFFFFFFFh
0x180164fe8  nop     dword ptr [rax+rax+00000000h]
0x180164ff0  lea     eax, [r8+r10]
0x180164ff4  cdq
0x180164ff5  sub     eax, edx
0x180164ff7  sar     eax, 1
0x180164ff9  movsxd  rdi, eax
0x180164ffc  mov     rdx, [r11+rdi*8]
0x180165000  cmp     [rdx], ebp
0x180165002  jz      loc_1801651F1
0x180165008  cmovnb  r8d, edi
0x18016500c  cmovnb  edi, r10d
0x180165010  mov     r10d, edi
0x180165013  lea     eax, [rdi+1]
0x180165016  cmp     eax, r8d
0x180165019  jnz     short loc_180164FF0
0x18016501b  mov     edi, 0FFFFFFFFh
0x180165020  mov     r9d, ebp
0x180165023  mov     dword ptr [rsp+88h+var_68], ebp
0x180165027  lea     r8, aUnknownFieldWi; "Unknown field with tag %hu (0x%hx) enco"...
0x18016502e  mov     rcx, rbx
0x180165031  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180165038  call    TIFFWarningExtR
0x18016503d  movzx   r8d, word ptr [rsi+2]
0x180165042  mov     rcx, rbx
0x180165045  movzx   edx, word ptr [rsi]
0x180165048  call    _TIFFCreateAnonField
0x18016504d  test    rax, rax
0x180165050  jz      loc_180165234
0x180165056  mov     r8d, 1
0x18016505c  mov     rdx, rax
0x18016505f  mov     rcx, rbx
0x180165062  call    _TIFFMergeFields
0x180165067  test    eax, eax
0x180165069  jz      loc_180165234
0x18016506f  mov     r8d, [rbx+4D8h]
0x180165076  test    r8d, r8d
0x180165079  jz      short loc_1801650BC
0x18016507b  mov     r11, [rbx+4D0h]
0x180165082  mov     r10d, 0FFFFFFFFh
0x180165088  movzx   r9d, word ptr [rsi]
0x18016508c  nop     dword ptr [rax+00h]
0x180165090  lea     eax, [r8+r10]
0x180165094  cdq
0x180165095  sub     eax, edx
0x180165097  sar     eax, 1
0x180165099  movsxd  rdi, eax
0x18016509c  mov     rcx, [r11+rdi*8]
0x1801650a0  cmp     [rcx], r9d
0x1801650a3  jz      loc_18016521B
0x1801650a9  cmovnb  r8d, edi
0x1801650ad  cmovnb  edi, r10d
0x1801650b1  mov     r10d, edi
0x1801650b4  lea     eax, [rdi+1]
0x1801650b7  cmp     eax, r8d
0x1801650ba  jnz     short loc_180165090
0x1801650bc  mov     edi, 0FFFFFFFFh
0x1801650c1  jmp     loc_180165257
0x1801650c6  lea     r8, [rsp+88h+Src]
0x1801650ce  mov     rdx, rdi
0x1801650d1  mov     rcx, rbx
0x1801650d4  call    TIFFReadDirEntryShort
0x1801650d9  cmp     eax, r14d
0x1801650dc  jnz     short loc_1801650F1
0x1801650de  lea     r8, [rsp+88h+Src]
0x1801650e6  mov     rdx, rdi
0x1801650e9  mov     rcx, rbx
0x1801650ec  call    TIFFReadDirEntryPersampleShort
0x1801650f1  test    eax, eax
0x1801650f3  jz      loc_1801651C9
0x1801650f9  dec     eax; switch 7 cases
0x1801650fb  cmp     eax, 6
0x1801650fe  ja      def_180165111; jumptable 0000000180165111 default case
0x180165104  cdqe
0x180165106  mov     ecx, ds:(jpt_180165111 - 180000000h)[r13+rax*4]
0x18016510e  add     rcx, r13
0x180165111  jmp     rcx; switch jump
0x180165113  lea     r9, aCompression; jumptable 0000000180165111 case 1
0x18016511a  lea     r8, aIncorrectCount_1; "Incorrect count for \"%s\""
0x180165121  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180165128  jmp     loc_1801653C7
0x18016512d  lea     r9, aCompression; jumptable 0000000180165111 case 2
0x180165134  lea     r8, aIncompatibleTy_0; "Incompatible type for \"%s\""
0x18016513b  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180165142  jmp     loc_1801653C7
0x180165147  lea     r9, aCompression; jumptable 0000000180165111 case 3
0x18016514e  lea     r8, aIoErrorDuringR_0; "IO error during reading of \"%s\""
0x180165155  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x18016515c  jmp     loc_1801653C7
0x180165161  lea     r9, aCompression; jumptable 0000000180165111 case 4
0x180165168  lea     r8, aIncorrectValue; "Incorrect value for \"%s\""
0x18016516f  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180165176  jmp     loc_1801653C7
0x18016517b  lea     r9, aCompression; jumptable 0000000180165111 case 5
0x180165182  lea     r8, aCannotHandleDi; "Cannot handle different values per samp"...
0x180165189  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x180165190  jmp     loc_1801653C7
0x180165195  lea     r9, aCompression; jumptable 0000000180165111 case 6
0x18016519c  lea     r8, aSanityCheckOnS; "Sanity check on size of \"%s\" value fa"...
0x1801651a3  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x1801651aa  jmp     loc_1801653C7
0x1801651af  lea     r9, aCompression; jumptable 0000000180165111 case 7
0x1801651b6  lea     r8, aOutOfMemoryRea; "Out of memory reading of \"%s\""
0x1801651bd  lea     rdx, aTiffreaddirect; "TIFFReadDirectory"
0x1801651c4  jmp     loc_1801653C7
0x1801651c9  movzx   r8d, word ptr [rsp+88h+Src]
0x1801651d2  mov     edx, ebp
0x1801651d4  mov     rcx, rbx
0x1801651d7  call    TIFFSetField
0x1801651dc  test    eax, eax
0x1801651de  jz      def_180165111; jumptable 0000000180165111 default case
0x1801651e4  mov     [rdi+18h], r14b
0x1801651e8  movzx   r14d, si
0x1801651ec  jmp     loc_180164FBA
0x1801651f1  test    eax, eax
0x1801651f3  jz      short loc_180165211
0x1801651f5  nop     word ptr [rax+rax+00000000h]
0x180165200  movsxd  rax, edi
0x180165203  mov     rcx, [r11+rax*8-8]
0x180165208  cmp     [rcx], ebp
0x18016520a  jnz     short loc_180165211
0x18016520c  sub     edi, 1
0x18016520f  jnz     short loc_180165200
0x180165211  cmp     edi, 0FFFFFFFFh
0x180165214  jnz     short loc_180165257
0x180165216  jmp     loc_180165020
0x18016521b  test    eax, eax
0x18016521d  jz      short loc_180165257
0x18016521f  nop
0x180165220  movsxd  rax, edi
0x180165223  mov     rcx, [r11+rax*8-8]
0x180165228  cmp     [rcx], r9d
  ... truncated ...
```
