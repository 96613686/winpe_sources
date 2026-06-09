# read_header_0

- ea: `0x1800db42c`
- end: `0x1800dc0a9`
- name: `read_header_0`
- size: `3197`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path`

## callers

- `0x1800d9680`

## callees

- `0x180004814`
- `0x180005914`
- `0x180005c7c`
- `0x180006c00`
- `0x18000c0ec`
- `0x18000e764`
- `0x18000e840`
- `0x18000e920`
- `0x18000e9a0`
- `0x18000ea00`
- `0x180015810`
- `0x1800aba54`
- `0x1800aba60`
- `0x1800db268`
- `0x1800db42c`
- `0x1800dc0b0`
- `0x1800ed464`
- `0x1800ed4c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800dbfe2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800dbfe2`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800dbd11`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800dbd11`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dbd01`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dbeef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dbf29`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dbd01`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dbeef`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800dbf29`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800db8ed`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800dbbe2`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800dbccb`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800db8ed`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800dbbe2`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800dbccb`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1800dbb37`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1800dbb58`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1800dbb37`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1800dbb58`

## string_xrefs

- `0x1800dbfed`: `Can't allocate memory for Pathname`
- `0x1800dc009`: `Pathname cannot be converted from %s to current locale.`
- `0x1800db572`: `Failed to read full header content.`
- `0x1800db899`: `Failed to read extended header data.`

## pseudocode

```c
__int64 __fastcall read_header_0(__int64 a1, __int64 a2, char a3)
{
  __int64 *v3; // rax
  __int64 v5; // r14
  __int64 *v6; // rbx
  unsigned __int8 *filter_ahead; // rax
  int v8; // esi
  int v9; // ebp
  unsigned __int64 v10; // rbx
  unsigned int v11; // edi
  __int64 v12; // rax
  __int64 v13; // r13
  const char *v14; // r8
  char *v15; // r12
  unsigned __int64 v16; // r8
  int v17; // ebp
  int v18; // esi
  int v19; // edi
  int v20; // ebx
  unsigned __int8 v21; // r10
  __int64 v22; // rcx
  bool v23; // zf
  unsigned __int64 v24; // r11
  unsigned __int64 v25; // r9
  signed __int64 v26; // r9
  unsigned __int64 v27; // r10
  __int64 v28; // r10
  unsigned __int64 v29; // rbp
  __int64 v30; // rdx
  char *v31; // r12
  __int64 v32; // rax
  size_t v33; // rcx
  size_t v34; // rdi
  unsigned int v35; // r13d
  unsigned __int64 v36; // rbx
  __int64 v37; // rax
  char *v38; // rsi
  __int64 v39; // rbx
  __int64 v40; // r8
  __int64 v41; // rbx
  char v42; // r9
  unsigned __int8 v43; // cl
  char v44; // r10
  bool v45; // cc
  __int64 v46; // rax
  int v47; // edx
  int v48; // edx
  int v49; // edx
  __int64 v50; // rax
  char v51; // r9
  char v52; // r11
  char v53; // cl
  char v54; // r9
  unsigned int v55; // edx
  __int64 v56; // r8
  __int64 v57; // r8
  __int64 v58; // r8
  __int64 v59; // r13
  __int64 v60; // rax
  char *i; // r8
  char *v62; // r12
  __int64 v63; // rax
  char *v64; // rax
  char *v65; // rax
  __int64 v66; // rbx
  unsigned __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // r8
  __int64 v72; // rcx
  void *v73; // rax
  const void *v74; // rdx
  void *v75; // rcx
  _QWORD *v76; // rax
  __int64 v77; // rax
  __int64 result; // rax
  __int64 v79; // rcx
  __int16 v80; // cx
  void *v81; // rcx
  int v82; // edi
  __int64 v83; // rcx
  __int64 v84; // rax
  __int16 v85; // ax
  const char *v86; // rax
  unsigned __int8 v87; // [rsp+20h] [rbp-98h]
  char v88; // [rsp+20h] [rbp-98h]
  unsigned __int8 v89; // [rsp+21h] [rbp-97h]
  char v90; // [rsp+21h] [rbp-97h]
  unsigned __int8 v91; // [rsp+22h] [rbp-96h]
  unsigned __int8 v92; // [rsp+22h] [rbp-96h]
  unsigned __int8 v93; // [rsp+23h] [rbp-95h]
  unsigned __int8 v95; // [rsp+25h] [rbp-93h]
  unsigned __int8 v96; // [rsp+26h] [rbp-92h]
  unsigned __int8 v97; // [rsp+27h] [rbp-91h]
  unsigned __int8 v98; // [rsp+28h] [rbp-90h]
  unsigned __int8 v99; // [rsp+29h] [rbp-8Fh]
  unsigned __int8 v100; // [rsp+2Ah] [rbp-8Eh]
  unsigned __int8 v101; // [rsp+2Bh] [rbp-8Dh]
  char v102; // [rsp+2Ch] [rbp-8Ch]
  unsigned __int8 v103; // [rsp+2Dh] [rbp-8Bh]
  unsigned __int64 v104; // [rsp+30h] [rbp-88h]
  unsigned __int64 v105; // [rsp+38h] [rbp-80h]
  char *v106; // [rsp+38h] [rbp-80h]
  __int64 v107; // [rsp+40h] [rbp-78h]
  __int64 v108; // [rsp+48h] [rbp-70h]
  unsigned int v109; // [rsp+50h] [rbp-68h]
  unsigned int v110; // [rsp+54h] [rbp-64h]
  int v112; // [rsp+7Ch] [rbp-3Ch]

  v3 = *(__int64 **)(a1 + 2072);
  v5 = *v3;
  v108 = *(_QWORD *)(*v3 + 20240);
  if ( !v108 )
  {
    v6 = (__int64 *)(v5 + 20232);
    if ( !*(_DWORD *)(v5 + 20224) )
    {
      *v6 = archive_string_default_conversion_for_read(a1);
      *(_DWORD *)(v5 + 20224) = 1;
    }
    v108 = *v6;
  }
  filter_ahead = (unsigned __int8 *)_archive_read_filter_ahead(*(_QWORD *)(a1 + 632), 7, 0);
  if ( !filter_ahead )
    return 4294967266LL;
  v8 = *filter_ahead;
  v9 = filter_ahead[1];
  v10 = *(unsigned __int16 *)(filter_ahead + 5);
  *(_DWORD *)(v5 + 16) = *(unsigned __int16 *)(filter_ahead + 3);
  v105 = v10;
  if ( v10 < 0x20 )
    goto LABEL_102;
  v11 = crc32(0, filter_ahead + 2, 5);
  _archive_read_filter_consume(*(_QWORD *)(a1 + 632), 7);
  if ( (*(_BYTE *)(v5 + 16) & 0x10) != 0 )
  {
    v14 = "RAR solid archive support unavailable.";
    goto LABEL_103;
  }
  *(_BYTE *)(v5 + 15) = 0;
  *(_QWORD *)(v5 + 24) = 0;
  *(_QWORD *)(v5 + 32) = 0;
  *(_WORD *)(v5 + 52) = 0;
  *(_QWORD *)(v5 + 88) = 0;
  *(_QWORD *)(v5 + 96) = 0;
  *(_DWORD *)(v5 + 104) = 0;
  *(_QWORD *)(v5 + 112) = 0;
  *(_DWORD *)(v5 + 120) = 0;
  *(_QWORD *)(v5 + 40) = 0;
  *(_DWORD *)(v5 + 48) = 0;
  *(_QWORD *)(v5 + 128) = 0;
  *(_DWORD *)(v5 + 136) = 0;
  v12 = _archive_read_filter_ahead(*(_QWORD *)(a1 + 632), v10 - 7, 0);
  v13 = v12;
  if ( !v12 )
  {
    v14 = "Failed to read full header content.";
    goto LABEL_103;
  }
  if ( (unsigned __int16)crc32(v11, v12, (unsigned int)(v10 - 7)) != (v8 | (v9 << 8)) )
  {
    v14 = "Header CRC error";
    goto LABEL_103;
  }
  v15 = (char *)(v13 + 25);
  v16 = v10 + v13 - 7;
  v17 = *(unsigned __int8 *)(v13 + 9);
  v18 = *(unsigned __int8 *)(v13 + 10);
  v19 = *(unsigned __int8 *)(v13 + 11);
  v20 = *(unsigned __int8 *)(v13 + 12);
  v87 = *(_BYTE *)v13;
  LOBYTE(v109) = *(_BYTE *)v13;
  v96 = *(_BYTE *)(v13 + 1);
  BYTE1(v109) = v96;
  v95 = *(_BYTE *)(v13 + 2);
  BYTE2(v109) = v95;
  v91 = *(_BYTE *)(v13 + 3);
  HIBYTE(v109) = v91;
  v89 = *(_BYTE *)(v13 + 4);
  LOBYTE(v110) = v89;
  v99 = *(_BYTE *)(v13 + 5);
  BYTE1(v110) = v99;
  v98 = *(_BYTE *)(v13 + 6);
  BYTE2(v110) = v98;
  v101 = *(_BYTE *)(v13 + 19);
  v97 = *(_BYTE *)(v13 + 7);
  HIBYTE(v110) = v97;
  v100 = *(_BYTE *)(v13 + 20);
  v104 = v16;
  v102 = *(_BYTE *)(v13 + 8);
  v93 = *(_BYTE *)(v13 + 21);
  v21 = *(_BYTE *)(v13 + 22);
  v22 = *(unsigned __int8 *)(v13 + 13)
      | ((*(unsigned __int8 *)(v13 + 14)
        | ((*(unsigned __int8 *)(v13 + 15) | (*(unsigned __int8 *)(v13 + 16) << 8)) << 8)) << 8);
  *(_BYTE *)(v5 + 15) = *(_BYTE *)(v13 + 18);
  v103 = v21;
  *(_QWORD *)(v5 + 40) = get_time(v22);
  v23 = (*(_BYTE *)(v5 + 16) & 4) == 0;
  *(_DWORD *)(v5 + 4) = v17 | ((v18 | ((v19 | (v20 << 8)) << 8)) << 8);
  if ( !v23 )
  {
    *(_BYTE *)(a2 + 800) |= 1u;
    *(_DWORD *)(v5 + 20296) = 1;
    archive_set_error(a1, 42, "RAR encryption support unavailable.");
  }
  v24 = v104;
  if ( (*(_DWORD *)(v5 + 16) & 0x100) != 0 )
  {
    if ( v13 + 33 > v104 )
      goto LABEL_102;
    v25 = ((unsigned __int8)BYTE2(*(_DWORD *)v15)
         | ((unsigned __int64)*(unsigned int *)v15 >> 16) & 0xFFFFFFFFFFFFFF00uLL) << 8;
    v112 = *(_DWORD *)v15;
    v15 = (char *)(v13 + 33);
    v26 = v87
        | ((v96
          | ((BYTE2(v109)
            | ((((unsigned __int64)v109 >> 24) | (((unsigned __int8)v112 | ((BYTE1(v112) | v25) << 8)) << 8)) << 8)) << 8)) << 8);
    v27 = v99
        | ((BYTE2(v110)
          | ((((unsigned __int64)v110 >> 24)
            | (((unsigned __int8)*(_DWORD *)(v13 + 29)
              | (((unsigned __int8)BYTE1(*(_DWORD *)(v13 + 29))
                | (((unsigned __int8)BYTE2(*(_DWORD *)(v13 + 29))
                  | ((unsigned __int64)*(unsigned int *)(v13 + 29) >> 16) & 0xFFFFFFFFFFFFFF00uLL) << 8)) << 8)) << 8)) << 8)) << 8);
  }
  else
  {
    v26 = v87 | ((v96 | ((v95 | ((unsigned __int64)v91 << 8)) << 8)) << 8);
    v27 = v99 | ((v98 | ((unsigned __int64)v97 << 8)) << 8);
  }
  v28 = v89 | (v27 << 8);
  *(_QWORD *)(v5 + 24) = v26;
  *(_QWORD *)(v5 + 32) = v28;
  if ( v26 < 0 || v28 < 0 )
  {
    v14 = "Invalid sizes specified.";
    goto LABEL_23;
  }
  v29 = v105;
  *(_QWORD *)(v5 + 152) = v26;
  if ( a3 == 122 )
  {
    if ( v26 > (__int64)(0x7FFFFFFFFFFFFFFFLL - v105) )
    {
      v14 = "Extended header size too large.";
LABEL_23:
      v30 = 42;
      goto LABEL_104;
    }
    v29 = v26 + v105;
    v31 = &v15[-v13];
    v32 = _archive_read_filter_ahead(*(_QWORD *)(a1 + 632), v26 + v105 - 7, 0);
    if ( !v32 )
    {
      v14 = "Failed to read extended header data.";
      goto LABEL_23;
    }
    v24 = v32 + v29 - 7;
    v104 = v24;
    v15 = &v31[v32];
  }
  v33 = v101 | (v100 << 8);
  v34 = v33;
  v106 = &v15[v33];
  if ( (unsigned __int64)&v15[v33] > v24 )
  {
    v14 = "Invalid filename size";
    goto LABEL_23;
  }
  v35 = 2 * v33;
  v36 = (unsigned int)(2 * v33 + 2);
  if ( *(_QWORD *)(v5 + 80) < v36 )
  {
    v37 = _o_realloc(*(_QWORD *)(v5 + 56), (unsigned int)v36);
    if ( !v37 )
      goto LABEL_133;
    *(_QWORD *)(v5 + 56) = v37;
    *(_QWORD *)(v5 + 80) = v36;
  }
  v38 = *(char **)(v5 + 56);
  memcpy_0(v38, v15, v34);
  v38[v34] = 0;
  if ( (*(_DWORD *)(v5 + 16) & 0x200) == 0 )
  {
    v59 = v108;
    while ( 1 )
    {
      v65 = strchr(v38, 92);
      if ( !v65 )
        break;
      *v65 = 47;
    }
    goto LABEL_83;
  }
  v39 = -1;
  do
    ++v39;
  while ( v38[v39] );
  if ( v34 == v39 )
  {
    v59 = *(_QWORD *)(v5 + 20248);
    if ( !v59 )
    {
      v63 = archive_string_conversion_from_charset(a1, "UTF-8", 1);
      *(_QWORD *)(v5 + 20248) = v63;
      v59 = v63;
      if ( !v63 )
        return 4294967266LL;
    }
    while ( 1 )
    {
      v64 = strchr(v38, 92);
      if ( !v64 )
        break;
      *v64 = 47;
    }
LABEL_83:
    v62 = v106;
    goto LABEL_84;
  }
  v40 = 0;
  v41 = (unsigned int)(v39 + 1);
  if ( (unsigned int)v41 >= (unsigned int)v34 )
    goto LABEL_64;
  v42 = v15[v41];
  v43 = 0;
  v88 = v42;
  v44 = 0;
  v92 = 0;
  LODWORD(v41) = v41 + 1;
  if ( (unsigned int)v41 >= (unsigned int)v34 )
    goto LABEL_64;
  while ( 1 )
  {
    v45 = (unsigned int)v40 <= v35;
    if ( (unsigned int)v40 >= v35 )
      break;
    if ( !v44 )
    {
      v46 = (unsigned int)v41;
      v44 = 8;
      LODWORD(v41) = v41 + 1;
      v43 = v15[v46];
      v92 = v43;
    }
    v44 -= 2;
    v47 = (v43 >> v44) & 3;
    if ( !v47 )
    {
      if ( (unsigned int)v41 >= (unsigned int)v34 )
        goto LABEL_64;
      v38[v40] = 0;
      goto LABEL_60;
    }
    v48 = v47 - 1;
    if ( !v48 )
    {
      if ( (unsigned int)v41 >= (unsigned int)v34 )
        goto LABEL_64;
      v38[v40] = v42;
LABEL_60:
      v58 = (unsigned int)(v40 + 1);
      v38[v58] = v15[(unsigned int)v41];
      v40 = (unsigned int)(v58 + 1);
      LODWORD(v41) = v41 + 1;
      goto LABEL_54;
    }
    v49 = v48 - 1;
    if ( v49 )
    {
      if ( v49 == 1 )
      {
        if ( (unsigned int)v41 >= (unsigned int)v34 )
          goto LABEL_64;
        v50 = (unsigned int)v41;
        v41 = (unsigned int)(v41 + 1);
        v51 = v15[v50];
        if ( v51 >= 0 )
        {
          v53 = 0;
          v52 = 0;
        }
        else
        {
          if ( (unsigned int)v41 >= (unsigned int)v34 )
            goto LABEL_64;
          v52 = v15[v41];
          LODWORD(v41) = v41 + 1;
          v53 = v88;
        }
        v90 = v53;
        v54 = (v51 & 0x7F) + 2;
        do
        {
          if ( (unsigned int)v40 >= v35 )
            break;
          v38[v40] = v53;
          v55 = v40;
          v53 = v90;
          v56 = (unsigned int)(v40 + 1);
          v38[v56] = v15[v55 >> 1] + v52;
          v40 = (unsigned int)(v56 + 1);
          --v54;
        }
        while ( v54 );
        v42 = v88;
      }
    }
    else
    {
      if ( (unsigned int)v41 >= (int)v34 - 1 )
      {
        LODWORD(v41) = v34;
        goto LABEL_64;
      }
      v38[v40] = v15[(unsigned int)v41 + 1];
      v57 = (unsigned int)(v40 + 1);
      v38[v57] = v15[(unsigned int)v41];
      v40 = (unsigned int)(v57 + 1);
      LODWORD(v41) = v41 + 2;
    }
LABEL_54:
    if ( (unsigned int)v41 >= (unsigned int)v34 )
    {
      v45 = (unsigned int)v40 <= v35;
      break;
    }
    v43 = v92;
  }
  if ( !v45 )
  {
    v14 = "Invalid filename";
    goto LABEL_103;
  }
LABEL_64:
  v38[v40] = 0;
  v34 = (unsigned int)(v40 + 1);
  v38[v34] = 0;
  v59 = *(_QWORD *)(v5 + 20256);
  if ( !v59 )
  {
    v60 = archive_string_conversion_from_charset(a1, "UTF-16BE", 1);
    *(_QWORD *)(v5 + 20256) = v60;
    v59 = v60;
    if ( !v60 )
      return 4294967266LL;
  }
  for ( i = v38; *(_WORD *)i; i += 2 )
  {
    if ( *(_WORD *)i == 23552 )
      i[1] = 47;
  }
  v62 = &v15[(unsigned int)v41];
LABEL_84:
  v66 = *(_QWORD *)(v5 + 64);
  if ( v66
    && (unsigned int)v34 == *(_QWORD *)(v5 + 72)
    && !memcmp_0(*(const void **)(v5 + 56), *(const void **)(v5 + 64), (unsigned int)(v34 + 1)) )
  {
    _archive_read_filter_consume(*(_QWORD *)(a1 + 632), v29 - 7);
    v67 = *(_QWORD *)(v5 + 256);
    ++*(_QWORD *)(v5 + 248);
    *(_QWORD *)(v5 + 20280) = 0;
    *(_QWORD *)(v5 + 20288) = 0;
    if ( *(_QWORD *)(v5 + 248) < v67 )
      goto LABEL_90;
    v68 = _o_realloc(*(_QWORD *)(v5 + 240), 24 * (v67 + 1));
    if ( v68 )
    {
      v69 = *(_QWORD *)(v5 + 248);
      ++*(_QWORD *)(v5 + 256);
      *(_QWORD *)(v5 + 240) = v68;
      *(_QWORD *)(v68 + 24 * v69) = v29;
      *(_QWORD *)(*(_QWORD *)(v5 + 240) + 24LL * *(_QWORD *)(v5 + 248) + 8) = -1;
      *(_QWORD *)(*(_QWORD *)(v5 + 240) + 24LL * *(_QWORD *)(v5 + 248) + 16) = -1;
LABEL_90:
      v70 = *(_QWORD *)(v5 + 248);
      v71 = *(_QWORD *)(v5 + 240);
      if ( *(__int64 *)(v71 + 24 * v70 + 8) < 0 )
      {
        v72 = **(_QWORD **)(a1 + 632);
        if ( *(_QWORD *)(v5 + 24) <= 0x7FFFFFFFFFFFFFFFLL - v72 )
        {
          *(_QWORD *)(v71 + 24 * v70 + 8) = v72;
          *(_QWORD *)(*(_QWORD *)(v5 + 240) + 24LL * *(_QWORD *)(v5 + 248) + 16) = *(_QWORD *)(v5 + 24)
                                                                                 + *(_QWORD *)(*(_QWORD *)(v5 + 240)
                                                                                             + 24LL
                                                                                             * *(_QWORD *)(v5 + 248)
                                                                                             + 8);
          return 0;
        }
LABEL_108:
        v14 = "Unable to store offsets.";
LABEL_103:
        v30 = 42;
LABEL_104:
        archive_set_error(a1, v30, v14);
        return 4294967266LL;
      }
      return 0;
    }
LABEL_133:
    v14 = "Couldn't allocate memory.";
LABEL_124:
    v30 = 12;
    goto LABEL_104;
  }
  if ( *(_BYTE *)(v5 + 264) )
  {
    v14 = "Mismatch of file parts split across multi-volume archive";
    goto LABEL_103;
  }
  v73 = (void *)_o_realloc(v66, (unsigned int)(v34 + 1));
  if ( !v73 )
    goto LABEL_133;
  v74 = *(const void **)(v5 + 56);
  *(_QWORD *)(v5 + 64) = v73;
  memcpy_0(v73, v74, (unsigned int)(v34 + 1));
  v75 = *(void **)(v5 + 240);
  v107 = (unsigned int)v34;
  *(_QWORD *)(v5 + 72) = (unsigned int)v34;
  free(v75);
  v76 = calloc(1u, 0x18u);
  *(_QWORD *)(v5 + 240) = v76;
  if ( !v76 )
    goto LABEL_133;
  *v76 = v29;
  *(_QWORD *)(*(_QWORD *)(v5 + 240) + 8LL) = -1;
  *(_QWORD *)(*(_QWORD *)(v5 + 240) + 16LL) = -1;
  v23 = (*(_DWORD *)(v5 + 16) & 0x400) == 0;
  *(_QWORD *)(v5 + 248) = 0;
  *(_QWORD *)(v5 + 256) = 1;
  if ( !v23 )
  {
    if ( (unsigned __int64)(v62 + 8) <= v104 )
    {
      v77 = *(_QWORD *)v62;
      v62 += 8;
      *(_QWORD *)(v5 + 88) = v77;
      goto LABEL_100;
    }
LABEL_102:
    v14 = "Invalid header size";
    goto LABEL_103;
  }
LABEL_100:
  if ( (*(_DWORD *)(v5 + 16) & 0x1000) != 0 && (int)read_exttime(v62, v5, v104) < 0 )
    goto LABEL_102;
  _archive_read_filter_consume(*(_QWORD *)(a1 + 632), v29 - 7);
  v79 = **(_QWORD **)(a1 + 632);
  if ( *(_QWORD *)(v5 + 24) > 0x7FFFFFFFFFFFFFFFLL - v79 )
    goto LABEL_108;
  *(_QWORD *)(*(_QWORD *)(v5 + 240) + 8LL) = v79;
  *(_QWORD *)(*(_QWORD *)(v5 + 240) + 16LL) = *(_QWORD *)(v5 + 24) + *(_QWORD *)(*(_QWORD *)(v5 + 240) + 8LL);
  if ( !v102 || v102 == 1 || v102 == 2 )
  {
    v80 = ((v93 & 0x10) != 0 ? 16457 : 0x8000) | 0x1A4;
  }
  else
  {
    if ( v102 != 3 && (unsigned int)(v102 - 4) >= 2 )
    {
      v14 = "Unknown file attributes from RAR file's host OS";
      goto LABEL_103;
    }
    v80 = v93 | (v103 << 8);
  }
  *(_WORD *)(v5 + 52) = v80;
  v81 = *(void **)(v5 + 208);
  *(_QWORD *)(v5 + 144) = 0;
  *(_QWORD *)(v5 + 160) = 0;
  *(_QWORD *)(v5 + 168) = 0;
  *(_QWORD *)(v5 + 856) = 0;
  *(_QWORD *)(v5 + 184) = 0;
  *(_DWORD *)(v5 + 216) = 0;
  *(_QWORD *)(v5 + 176) = 0;
  *(_DWORD *)(v5 + 20272) = 0;
  *(_QWORD *)(v5 + 20280) = 0;
  *(_QWORD *)(v5 + 20288) = 0;
  *(_DWORD *)(v5 + 224) = 0;
  *(_BYTE *)(v5 + 221) = 0;
  *(_BYTE *)(v5 + 192) = 1;
  *(_BYTE *)(v5 + 970) = 0;
  *(_BYTE *)(v5 + 896) = 1;
  free(v81);
  *(_QWORD *)(v5 + 208) = 0;
  *(_DWORD *)(v5 + 196) = 0;
  *(_DWORD *)(v5 + 200) = 0x20000;
  memset_0((void *)(v5 + 432), 0, 0x194u);
  free(*(void **)(v5 + 1040));
  *(_DWORD *)(v5 + 1028) = 0;
  *(_QWORD *)(v5 + 1040) = 0;
  *(_WORD *)(v5 + 968) = 0;
  *(_QWORD *)(v5 + 928) = 0x7FFFFFFFFFFFFFFFLL;
  if ( a3 == 122 )
    return 0;
  v82 = 0;
  archive_entry_set_mtime(a2, *(_QWORD *)(v5 + 40), *(unsigned int *)(v5 + 48));
  archive_entry_set_ctime(a2, *(_QWORD *)(v5 + 112), *(unsigned int *)(v5 + 120));
  archive_entry_set_atime(a2, *(_QWORD *)(v5 + 96), *(unsigned int *)(v5 + 104));
  v83 = *(_QWORD *)(v5 + 32);
  v84 = 0;
  *(_DWORD *)(a2 + 16) = 0;
  if ( v83 >= 0 )
    v84 = v83;
  *(_DWORD *)(a2 + 160) |= 0x40u;
  *(_QWORD *)(a2 + 112) = v84;
  v85 = *(_WORD *)(v5 + 52);
  *(_DWORD *)(a2 + 160) |= 0x600u;
  *(_WORD *)(a2 + 1032) = v85;
  if ( (unsigned int)archive_mstring_copy_mbs_len_l(a2 + 488, v38, v107, v59) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      v14 = "Can't allocate memory for Pathname";
      goto LABEL_124;
    }
    v86 = (const char *)archive_string_conversion_charset_name(v59);
    archive_set_error(a1, 42, "Pathname cannot be converted from %s to current locale.", v86);
    v82 = -20;
  }
  if ( (*(_WORD *)(v5 + 52) & 0xF000) == 0xA000 )
  {
    *(_QWORD *)(v5 + 152) = 0;
    *(_DWORD *)(a2 + 160) |= 0x40u;
    *(_DWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 112) = 0;
    result = read_symlink_stored(a1, a2, v108);
    if ( (int)result < -20 )
      return result;
    if ( v82 > (int)result )
      v82 = result;
  }
  if ( !*(_QWORD *)(v5 + 152) )
    *(_BYTE *)(v5 + 221) = 1;
  return (unsigned int)v82;
}

```

## disassembly

```asm
0x1800db42c  mov     [rsp+arg_10], rbx
0x1800db431  push    rbp
0x1800db432  push    rsi
0x1800db433  push    rdi
0x1800db434  push    r12
0x1800db436  push    r13
0x1800db438  push    r14
0x1800db43a  push    r15
0x1800db43c  sub     rsp, 80h
0x1800db443  mov     rax, [rcx+818h]
0x1800db44a  xor     r12d, r12d
0x1800db44d  mov     [rsp+0B8h+var_94], r8b
0x1800db452  mov     r15, rcx
0x1800db455  mov     [rsp+0B8h+var_48], rdx
0x1800db45a  mov     r14, [rax]
0x1800db45d  mov     rbx, [r14+4F10h]
0x1800db464  mov     [rsp+0B8h+var_70], rbx
0x1800db469  test    rbx, rbx
0x1800db46c  jnz     short loc_1800DB499
0x1800db46e  lea     rbx, [r14+4F08h]
0x1800db475  cmp     [r14+4F00h], r12d
0x1800db47c  jnz     short loc_1800DB491
0x1800db47e  call    archive_string_default_conversion_for_read
0x1800db483  mov     [rbx], rax
0x1800db486  mov     dword ptr [r14+4F00h], 1
0x1800db491  mov     rax, [rbx]
0x1800db494  mov     [rsp+0B8h+var_70], rax
0x1800db499  mov     rcx, [r15+278h]
0x1800db4a0  xor     r8d, r8d
0x1800db4a3  lea     r13d, [r8+7]
0x1800db4a7  mov     edx, r13d
0x1800db4aa  call    __archive_read_filter_ahead
0x1800db4af  test    rax, rax
0x1800db4b2  jz      loc_1800DBDAA
0x1800db4b8  movzx   ebx, byte ptr [rax+6]
0x1800db4bc  movzx   edx, byte ptr [rax+4]
0x1800db4c0  movzx   r9d, byte ptr [rax+5]
0x1800db4c5  movzx   ecx, byte ptr [rax+3]
0x1800db4c9  movzx   esi, byte ptr [rax]
0x1800db4cc  movzx   ebp, byte ptr [rax+1]
0x1800db4d0  shl     edx, 8
0x1800db4d3  shl     rbx, 8
0x1800db4d7  or      edx, ecx
0x1800db4d9  or      rbx, r9
0x1800db4dc  mov     [r14+10h], edx
0x1800db4e0  mov     [rsp+0B8h+var_80], rbx
0x1800db4e5  cmp     rbx, 20h ; ' '
0x1800db4e9  jb      loc_1800DBD96
0x1800db4ef  lea     rdx, [rax+2]
0x1800db4f3  xor     ecx, ecx
0x1800db4f5  lea     r8d, [r13-2]
0x1800db4f9  call    crc32
0x1800db4fe  mov     rcx, [r15+278h]
0x1800db505  mov     edx, r13d
0x1800db508  mov     edi, eax
0x1800db50a  call    __archive_read_filter_consume
0x1800db50f  test    byte ptr [r14+10h], 10h
0x1800db514  jnz     loc_1800DC09D
0x1800db51a  mov     [r14+0Fh], r12b
0x1800db51e  lea     rdx, [rbx-7]
0x1800db522  mov     [r14+18h], r12
0x1800db526  xor     eax, eax
0x1800db528  mov     [r14+20h], r12
0x1800db52c  xor     r8d, r8d
0x1800db52f  mov     [r14+34h], r12w
0x1800db534  mov     [r14+58h], rax
0x1800db538  mov     [r14+60h], r12
0x1800db53c  mov     [r14+68h], r12d
0x1800db540  mov     [r14+70h], r12
0x1800db544  mov     [r14+78h], r12d
0x1800db548  mov     [r14+28h], r12
0x1800db54c  mov     [r14+30h], r12d
0x1800db550  mov     [r14+80h], r12
0x1800db557  mov     [r14+88h], r12d
0x1800db55e  mov     rcx, [r15+278h]
0x1800db565  call    __archive_read_filter_ahead
0x1800db56a  mov     r13, rax
0x1800db56d  test    rax, rax
0x1800db570  jnz     short loc_1800DB57E
0x1800db572  lea     r8, aFailedToReadFu_0; "Failed to read full header content."
0x1800db579  jmp     loc_1800DBD9D
0x1800db57e  lea     r8d, [rbx-7]
0x1800db582  mov     rdx, r13
0x1800db585  mov     ecx, edi
0x1800db587  call    crc32
0x1800db58c  mov     ecx, ebp
0x1800db58e  movzx   edx, ax
0x1800db591  shl     ecx, 8
0x1800db594  or      ecx, esi
0x1800db596  cmp     edx, ecx
0x1800db598  jz      short loc_1800DB5A6
0x1800db59a  lea     r8, aHeaderCrcError; "Header CRC error"
0x1800db5a1  jmp     loc_1800DBD9D
0x1800db5a6  mov     al, [r13+0]
0x1800db5aa  lea     r8, [r13-7]
0x1800db5ae  mov     r10b, [r13+13h]
0x1800db5b2  lea     r12, [r13+19h]
0x1800db5b6  movzx   ecx, byte ptr [r13+10h]
0x1800db5bb  add     r8, rbx
0x1800db5be  movzx   edx, byte ptr [r13+0Fh]
0x1800db5c3  movzx   r9d, byte ptr [r13+0Dh]
0x1800db5c8  movzx   ebp, byte ptr [r13+9]
0x1800db5cd  movzx   esi, byte ptr [r13+0Ah]
0x1800db5d2  movzx   edi, byte ptr [r13+0Bh]
0x1800db5d7  movzx   ebx, byte ptr [r13+0Ch]
0x1800db5dc  mov     [rsp+0B8h+var_98], al
0x1800db5e0  mov     byte ptr [rsp+0B8h+var_68], al
0x1800db5e4  mov     al, [r13+1]
0x1800db5e8  mov     [rsp+0B8h+var_92], al
0x1800db5ec  mov     byte ptr [rsp+0B8h+var_68+1], al
0x1800db5f0  mov     al, [r13+2]
0x1800db5f4  mov     [rsp+0B8h+var_93], al
0x1800db5f8  mov     byte ptr [rsp+0B8h+var_68+2], al
0x1800db5fc  mov     al, [r13+3]
0x1800db600  mov     [rsp+0B8h+var_96], al
0x1800db604  mov     byte ptr [rsp+0B8h+var_68+3], al
0x1800db608  mov     al, [r13+4]
0x1800db60c  mov     [rsp+0B8h+var_97], al
0x1800db610  mov     byte ptr [rsp+0B8h+var_64], al
0x1800db614  mov     al, [r13+5]
0x1800db618  shl     ecx, 8
0x1800db61b  mov     [rsp+0B8h+var_8F], al
0x1800db61f  or      ecx, edx
0x1800db621  mov     byte ptr [rsp+0B8h+var_64+1], al
0x1800db625  mov     al, [r13+6]
0x1800db629  mov     [rsp+0B8h+var_90], al
0x1800db62d  mov     byte ptr [rsp+0B8h+var_64+2], al
0x1800db631  mov     al, [r13+7]
0x1800db635  mov     [rsp+0B8h+var_8D], r10b
0x1800db63a  mov     r10b, [r13+14h]
0x1800db63e  shl     ecx, 8
0x1800db641  mov     [rsp+0B8h+var_91], al
0x1800db645  mov     byte ptr [rsp+0B8h+var_64+3], al
0x1800db649  mov     al, [r13+8]
0x1800db64d  mov     [rsp+0B8h+var_8E], r10b
0x1800db652  mov     r10b, [r13+15h]
0x1800db656  mov     [rsp+0B8h+var_88], r8
0x1800db65b  movzx   r8d, byte ptr [r13+0Eh]
0x1800db660  or      ecx, r8d
0x1800db663  mov     [rsp+0B8h+var_8C], al
0x1800db667  mov     al, [r13+12h]
0x1800db66b  mov     [rsp+0B8h+var_95], r10b
0x1800db670  mov     r10b, [r13+16h]
0x1800db674  shl     ecx, 8
0x1800db677  or      ecx, r9d
0x1800db67a  mov     [r14+0Fh], al
0x1800db67e  mov     [rsp+0B8h+var_8B], r10b
0x1800db683  call    get_time
0x1800db688  mov     ecx, ebx
0x1800db68a  mov     [r14+28h], rax
0x1800db68e  shl     ecx, 8
0x1800db691  or      ecx, edi
0x1800db693  shl     ecx, 8
0x1800db696  or      ecx, esi
0x1800db698  mov     esi, 2Ah ; '*'
0x1800db69d  shl     ecx, 8
0x1800db6a0  or      ecx, ebp
0x1800db6a2  test    byte ptr [r14+10h], 4
0x1800db6a7  mov     [r14+4], ecx
0x1800db6ab  jz      short loc_1800DB6D5
0x1800db6ad  mov     rax, [rsp+0B8h+var_48]
0x1800db6b2  lea     r8, aRarEncryptionS; "RAR encryption support unavailable."
0x1800db6b9  mov     edx, esi
0x1800db6bb  mov     rcx, r15
0x1800db6be  or      byte ptr [rax+320h], 1
0x1800db6c5  mov     dword ptr [r14+4F48h], 1
0x1800db6d0  call    archive_set_error
0x1800db6d5  test    dword ptr [r14+10h], 100h
0x1800db6dd  mov     r11, [rsp+0B8h+var_88]
0x1800db6e2  jz      loc_1800DB7DA
0x1800db6e8  lea     rax, [r12+8]
0x1800db6ed  cmp     rax, r11
0x1800db6f0  ja      loc_1800DBD96
0x1800db6f6  mov     edx, [r12]
0x1800db6fa  mov     rbx, 0FFFFFFFFFFFFFF00h
0x1800db701  mov     r8d, [r12+4]
0x1800db706  mov     eax, edx
0x1800db708  shr     eax, 10h
0x1800db70b  mov     r9d, edx
0x1800db70e  shr     r9, 10h
0x1800db712  mov     r10d, r8d
0x1800db715  and     r9, rbx
0x1800db718  movzx   ecx, al
0x1800db71b  or      r9, rcx
0x1800db71e  shr     r10, 10h
0x1800db722  shl     r9, 8
0x1800db726  and     r10, rbx
0x1800db729  mov     [rsp+0B8h+var_3C], edx
0x1800db72d  add     r12, 8
0x1800db731  shr     edx, 8
0x1800db734  movzx   eax, dl
0x1800db737  or      r9, rax
0x1800db73a  mov     [rsp+0B8h+var_74], r8d
0x1800db73f  movzx   eax, byte ptr [rsp+0B8h+var_3C]
0x1800db744  shl     r9, 8
0x1800db748  or      r9, rax
0x1800db74b  mov     eax, [rsp+0B8h+var_68]
0x1800db74f  mov     ecx, eax
0x1800db751  shl     r9, 8
0x1800db755  shr     rcx, 18h
0x1800db759  or      r9, rcx
0x1800db75c  mov     ecx, eax
0x1800db75e  shr     ecx, 10h
0x1800db761  movzx   edx, cl
0x1800db764  shr     eax, 8
0x1800db767  movzx   ecx, al
0x1800db76a  movzx   eax, [rsp+0B8h+var_98]
0x1800db76f  shl     r9, 8
0x1800db773  or      r9, rdx
0x1800db776  shl     r9, 8
0x1800db77a  or      r9, rcx
0x1800db77d  shl     r9, 8
0x1800db781  or      r9, rax
0x1800db784  mov     eax, r8d
0x1800db787  shr     eax, 10h
0x1800db78a  movzx   ecx, al
0x1800db78d  or      r10, rcx
0x1800db790  shr     r8d, 8
0x1800db794  shl     r10, 8
0x1800db798  movzx   eax, r8b
0x1800db79c  or      r10, rax
0x1800db79f  movzx   eax, byte ptr [rsp+0B8h+var_74]
0x1800db7a4  shl     r10, 8
0x1800db7a8  or      r10, rax
0x1800db7ab  mov     eax, [rsp+0B8h+var_64]
0x1800db7af  shl     r10, 8
0x1800db7b3  mov     ecx, eax
0x1800db7b5  shr     rcx, 18h
0x1800db7b9  or      r10, rcx
0x1800db7bc  mov     ecx, eax
0x1800db7be  shr     ecx, 10h
0x1800db7c1  shl     r10, 8
0x1800db7c5  movzx   edx, cl
0x1800db7c8  or      r10, rdx
0x1800db7cb  shr     eax, 8
0x1800db7ce  shl     r10, 8
0x1800db7d2  movzx   ecx, al
0x1800db7d5  or      r10, rcx
0x1800db7d8  jmp     short loc_1800DB822
0x1800db7da  movzx   eax, [rsp+0B8h+var_93]
0x1800db7df  movzx   r9d, [rsp+0B8h+var_96]
0x1800db7e5  movzx   r10d, [rsp+0B8h+var_91]
0x1800db7eb  shl     r9, 8
0x1800db7ef  or      r9, rax
0x1800db7f2  shl     r10, 8
0x1800db7f6  movzx   eax, [rsp+0B8h+var_92]
0x1800db7fb  shl     r9, 8
0x1800db7ff  or      r9, rax
0x1800db802  movzx   eax, [rsp+0B8h+var_98]
0x1800db807  shl     r9, 8
0x1800db80b  or      r9, rax
0x1800db80e  movzx   eax, [rsp+0B8h+var_90]
0x1800db813  or      r10, rax
0x1800db816  movzx   eax, [rsp+0B8h+var_8F]
0x1800db81b  shl     r10, 8
0x1800db81f  or      r10, rax
0x1800db822  movzx   eax, [rsp+0B8h+var_97]
0x1800db827  shl     r10, 8
0x1800db82b  or      r10, rax
0x1800db82e  mov     [r14+18h], r9
0x1800db832  mov     [r14+20h], r10
0x1800db836  test    r9, r9
0x1800db839  js      loc_1800DC091
0x1800db83f  test    r10, r10
0x1800db842  js      loc_1800DC091
0x1800db848  cmp     [rsp+0B8h+var_94], 7Ah ; 'z'
0x1800db84d  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800db857  mov     rbp, [rsp+0B8h+var_80]
0x1800db85c  mov     [r14+98h], r9
0x1800db863  jnz     short loc_1800DB8B1
0x1800db865  sub     rax, rbp
0x1800db868  cmp     r9, rax
0x1800db86b  jle     short loc_1800DB87B
0x1800db86d  lea     r8, aExtendedHeader; "Extended header size too large."
0x1800db874  mov     edx, esi
0x1800db876  jmp     loc_1800DBDA2
0x1800db87b  mov     rcx, [r15+278h]
0x1800db882  add     rbp, r9
0x1800db885  xor     r8d, r8d
0x1800db888  sub     r12, r13
0x1800db88b  lea     rdx, [rbp-7]
0x1800db88f  call    __archive_read_filter_ahead
0x1800db894  test    rax, rax
0x1800db897  jnz     short loc_1800DB8A2
0x1800db899  lea     r8, aFailedToReadEx; "Failed to read extended header data."
0x1800db8a0  jmp     short loc_1800DB874
0x1800db8a2  lea     r11, [rbp-7]
0x1800db8a6  add     r11, rax
0x1800db8a9  mov     [rsp+0B8h+var_88], r11
0x1800db8ae  add     r12, rax
0x1800db8b1  movzx   ecx, [rsp+0B8h+var_8E]
0x1800db8b6  movzx   eax, [rsp+0B8h+var_8D]
0x1800db8bb  shl     ecx, 8
0x1800db8be  or      ecx, eax
0x1800db8c0  mov     edi, ecx
0x1800db8c2  lea     rax, [rcx+r12]
0x1800db8c6  mov     [rsp+0B8h+var_80], rax
0x1800db8cb  cmp     rax, r11
0x1800db8ce  jbe     short loc_1800DB8D9
0x1800db8d0  lea     r8, aInvalidFilenam_0; "Invalid filename size"
  ... truncated ...
```
