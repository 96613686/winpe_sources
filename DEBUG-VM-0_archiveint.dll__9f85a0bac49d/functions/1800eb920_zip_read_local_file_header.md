# zip_read_local_file_header

- ea: `0x1800eb920`
- end: `0x1800ec400`
- name: `zip_read_local_file_header`
- size: `2784`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800e83e0`
- `0x1800e85f0`

## callees

- `0x180005914`
- `0x180005c7c`
- `0x180006c00`
- `0x180007c80`
- `0x18000a2d0`
- `0x18000c0ec`
- `0x18000e764`
- `0x18000e920`
- `0x18000e9a0`
- `0x18000ea00`
- `0x180014ab4`
- `0x1800b0a70`
- `0x1800b1f40`
- `0x1800e89d0`
- `0x1800e9360`
- `0x1800eab88`
- `0x1800eb2c0`
- `0x1800eb920`
- `0x1800ece24`
- `0x1800ecf00`
- `0x1800ed464`
- `0x1800ed4c8`
- `0x1800ed5e0`
- `0x1800ed6c0`
- `0x1800ee548`
- `0x1800ee578`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ebc1e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ec25d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ec291`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ebc1e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ec25d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800ec291`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ebdc8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ebf92`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ebdc8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ebf92`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800ebd30`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800ebd45`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800ebd30`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800ebd45`

## string_xrefs

- `0x1800ebc29`: `Can't allocate memory for Pathname`
- `0x1800ebc45`: `Pathname cannot be converted from %s to current locale.`
- `0x1800ec016`: `Inconsistent compressed size: %jd in central directory, %jd in local header`
- `0x1800ec05c`: `Inconsistent uncompressed size: %jd in central directory, %jd in local header`
- `0x1800ec13a`: `Zip file with oversized link entry`
- `0x1800ec1d5`: `Unsupported ZIP compression method during decompression of link entry (%d: %s)`
- `0x1800ec29c`: `Can't allocate memory for Symlink`
- `0x1800ec2cb`: `Symlink cannot be converted from %s to current locale.`
- `0x1800ec308`: `Read error skipping symlink target name`

## pseudocode

```c
__int64 __fastcall zip_read_local_file_header(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 (__fastcall *v7)(_QWORD, _QWORD, _QWORD); // rax
  __int128 v8; // xmm1
  __m128i v9; // xmm7
  __int128 v10; // xmm8
  __m128i v11; // xmm6
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm0
  __int64 filter_ahead; // rax
  __int64 v17; // r14
  const char *v18; // r8
  __int64 v19; // rdx
  __int16 v20; // cx
  _BYTE *v21; // rax
  bool v22; // zf
  __int64 v23; // rcx
  __int64 v24; // r12
  __int64 v25; // r13
  __int64 v26; // r14
  const char *v27; // rax
  unsigned __int64 v28; // r14
  __int64 v29; // rax
  __int16 v30; // cx
  const wchar_t *v31; // rax
  const wchar_t *v32; // r14
  __int64 v33; // r8
  unsigned __int64 v34; // rcx
  unsigned __int64 i; // rax
  __int16 v36; // cx
  __int64 v37; // rax
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rax
  unsigned __int64 v48; // r9
  __int64 v49; // rax
  __int16 v50; // ax
  int v51; // ecx
  __int64 v52; // rax
  int v53; // ecx
  __int64 v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r13
  __int64 v57; // rax
  char v58; // cl
  int v59; // eax
  __int64 v60; // r12
  const char *v61; // rax
  int v62; // ecx
  __int64 result; // rax
  __int64 v64; // r14
  const char *v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rax
  const char *v70; // rax
  int v71; // r9d
  int v72; // r10d
  unsigned int v73; // [rsp+38h] [rbp-D0h]
  void *Block; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int64 v75; // [rsp+48h] [rbp-C0h]
  __int64 v76; // [rsp+50h] [rbp-B8h]
  __int64 v77; // [rsp+58h] [rbp-B0h]
  _OWORD v78[12]; // [rsp+68h] [rbp-A0h]
  __int64 v79; // [rsp+168h] [rbp+60h] BYREF
  __int64 v80; // [rsp+178h] [rbp+70h] BYREF
  char v81; // [rsp+180h] [rbp+78h]

  v3 = *(_QWORD *)(a3 + 112);
  v7 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(a3 + 152);
  v8 = *(_OWORD *)(v3 + 16);
  v9 = *(__m128i *)(v3 + 32);
  v10 = *(_OWORD *)(v3 + 48);
  v11 = *(__m128i *)(v3 + 112);
  v78[0] = *(_OWORD *)v3;
  v12 = *(_OWORD *)(v3 + 64);
  v78[1] = v8;
  v13 = *(_OWORD *)(v3 + 80);
  v78[4] = v12;
  v14 = *(_OWORD *)(v3 + 96);
  v78[5] = v13;
  v78[6] = v14;
  v15 = *(_OWORD *)(v3 + 128);
  *(_WORD *)(a3 + 161) = 0;
  *(_QWORD *)(a3 + 136) = 0;
  *(_QWORD *)(a3 + 128) = 0;
  v78[8] = v15;
  *(_DWORD *)(a3 + 144) = v7(0, 0, 0);
  if ( !*(_QWORD *)(a3 + 7952) && !*(_DWORD *)(a3 + 7976) )
  {
    *(_QWORD *)(a3 + 7960) = archive_string_default_conversion_for_read(a1);
    *(_DWORD *)(a3 + 7976) = 1;
  }
  filter_ahead = _archive_read_filter_ahead(*(_QWORD *)(a1 + 632), 30, 0);
  v17 = filter_ahead;
  if ( !filter_ahead )
    goto LABEL_135;
  if ( *(_DWORD *)filter_ahead != 67324752 )
  {
    v18 = "Damaged Zip archive";
LABEL_7:
    v19 = 0xFFFFFFFFLL;
LABEL_136:
    archive_set_error(a1, v19, v18);
    return 4294967266LL;
  }
  v81 = *(_BYTE *)(filter_ahead + 4);
  *(_BYTE *)(v3 + 129) = *(_BYTE *)(filter_ahead + 5);
  v20 = *(_WORD *)(filter_ahead + 6);
  *(_WORD *)(v3 + 126) = v20;
  if ( (v20 & 0x41) != 0 )
  {
    *(_DWORD *)(a3 + 56) = 1;
    *(_BYTE *)(a2 + 800) |= 1u;
    if ( (*(_WORD *)(v3 + 126) & 0x2041) == 0x2041 )
    {
      *(_BYTE *)(a2 + 800) |= 2u;
      return 4294967266LL;
    }
  }
  *(_BYTE *)(a3 + 7984) = *(_BYTE *)(v3 + 126) & 1;
  *(_BYTE *)(v3 + 128) = *(_BYTE *)(filter_ahead + 8);
  *(_QWORD *)(v3 + 96) = dos_to_unix(
                           *(unsigned __int8 *)(filter_ahead + 10)
                         | ((*(unsigned __int8 *)(filter_ahead + 11) | (*(unsigned __int16 *)(filter_ahead + 12) << 8)) << 8));
  v21 = (_BYTE *)(v17 + 11);
  v22 = (*(_BYTE *)(v3 + 126) & 8) == 0;
  *(_DWORD *)(v3 + 120) = *(unsigned __int8 *)(v17 + 14)
                        | ((*(unsigned __int8 *)(v17 + 15) | (*(unsigned __int16 *)(v17 + 16) << 8)) << 8);
  if ( v22 )
    v21 = (_BYTE *)(v17 + 17);
  *(_BYTE *)(v3 + 131) = *v21;
  *(_QWORD *)(v3 + 40) = *(unsigned __int8 *)(v17 + 18)
                       | ((*(unsigned __int8 *)(v17 + 19) | ((unsigned __int64)*(unsigned __int16 *)(v17 + 20) << 8)) << 8);
  *(_QWORD *)(v3 + 48) = *(unsigned __int8 *)(v17 + 22)
                       | ((*(unsigned __int8 *)(v17 + 23) | ((unsigned __int64)*(unsigned __int16 *)(v17 + 24) << 8)) << 8);
  v23 = *(_QWORD *)(a1 + 632);
  v24 = *(unsigned __int16 *)(v17 + 26);
  LOBYTE(v79) = *(_BYTE *)(v17 + 29);
  LOBYTE(v80) = *(_BYTE *)(v17 + 28);
  _archive_read_filter_consume(v23, 30);
  v25 = _archive_read_filter_ahead(*(_QWORD *)(a1 + 632), v24, 0);
  if ( !v25 )
    goto LABEL_135;
  if ( (*(_WORD *)(v3 + 126) & 0x800) != 0 )
  {
    v26 = *(_QWORD *)(a3 + 7968);
    if ( !v26 )
    {
      v26 = archive_string_conversion_from_charset(a1, "UTF-8", 1);
      *(_QWORD *)(a3 + 7968) = v26;
      if ( !v26 )
        return 4294967266LL;
    }
  }
  else
  {
    v26 = *(_QWORD *)(a3 + 7952);
    if ( !v26 )
      v26 = *(_QWORD *)(a3 + 7960);
  }
  v73 = 0;
  if ( (unsigned int)archive_mstring_copy_mbs_len_l(a2 + 488, v25, v24, v26) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      v18 = "Can't allocate memory for Pathname";
LABEL_23:
      v19 = 12;
      goto LABEL_136;
    }
    v27 = (const char *)archive_string_conversion_charset_name(v26);
    archive_set_error(a1, 42, "Pathname cannot be converted from %s to current locale.", v27);
    v73 = -20;
  }
  v28 = (unsigned __int8)v80 | ((unsigned __int64)(unsigned __int8)v79 << 8);
  _archive_read_filter_consume(*(_QWORD *)(a1 + 632), v24);
  v29 = _archive_read_filter_ahead(*(_QWORD *)(a1 + 632), v28, 0);
  if ( !v29 )
  {
LABEL_135:
    v18 = "Truncated ZIP file header";
    v19 = 42;
    goto LABEL_136;
  }
  if ( (unsigned int)process_extra(a1, a2, v29, v28, v3) )
    return 4294967266LL;
  _archive_read_filter_consume(*(_QWORD *)(a1 + 632), v28);
  v30 = *(_WORD *)(v3 + 124);
  if ( (v30 & 0xF000) == 0x1000 )
  {
    v30 = v30 & 0xFFF | 0x8000;
    *(_WORD *)(v3 + 124) = v30;
  }
  if ( !v30 )
    *(_WORD *)(v3 + 124) = 436;
  if ( !*(_BYTE *)(v3 + 129) )
  {
    v31 = (const wchar_t *)archive_entry_pathname_w(a2);
    v32 = v31;
    if ( v31 )
    {
      if ( !wcschr(v31, 0x2Fu) && wcschr(v32, 0x5Cu) )
      {
        Block = 0;
        v33 = -1;
        v76 = 0;
        v75 = 0;
        do
          ++v33;
        while ( v32[v33] );
        archive_wstrncat(&Block, v32);
        v34 = v75;
        for ( i = 0; i < v34; ++i )
        {
          if ( *((_WORD *)Block + i) == 92 )
          {
            *((_WORD *)Block + i) = 47;
            v34 = v75;
          }
        }
        archive_mstring_copy_wcs(a2 + 488, Block);
        v75 = 0;
        v76 = 0;
        free(Block);
      }
    }
  }
  v36 = *(_WORD *)(v3 + 124);
  if ( (v36 & 0xF000) != 0x4000 )
  {
    v37 = archive_entry_pathname_w(a2);
    if ( v37 )
    {
      v38 = -1;
      do
        ++v38;
      while ( *(_WORD *)(v37 + 2 * v38) );
      if ( !v38 || (v22 = *(_WORD *)(v37 + 2 * v38 - 2) == 47, v39 = 1, !v22) )
        v39 = 0;
      v36 = *(_WORD *)(v3 + 124);
      if ( v39 )
        goto LABEL_57;
    }
    else
    {
      v40 = archive_entry_pathname(a2);
      if ( v40 )
      {
        v41 = -1;
        do
          ++v41;
        while ( *(_BYTE *)(v40 + v41) );
        if ( v41 && *(_BYTE *)(v41 + v40 - 1) == 47 )
        {
          v36 = *(_WORD *)(v3 + 124);
LABEL_57:
          v36 = v36 & 0xFB6 | 0x4049;
          *(_WORD *)(v3 + 124) = v36;
          goto LABEL_58;
        }
      }
      v36 = *(_WORD *)(v3 + 124);
    }
    if ( (v36 & 0xF000) == 0 )
    {
      v36 |= 0x8000u;
      *(_WORD *)(v3 + 124) = v36;
    }
  }
LABEL_58:
  if ( (v36 & 0xF000) != 0x4000 )
    goto LABEL_75;
  v42 = archive_entry_pathname_w(a2);
  if ( v42 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *(_WORD *)(v42 + 2 * v43) );
    if ( v43 && *(_WORD *)(v42 + 2 * v43 - 2) != 47 )
    {
      Block = 0;
      v75 = 0;
      v76 = 0;
      archive_wstrncat(&Block, v42);
      archive_wstrappend_wchar(&Block, 47);
      archive_mstring_copy_wcs(a2 + 488, Block);
LABEL_74:
      v75 = 0;
      v76 = 0;
      free(Block);
    }
  }
  else
  {
    v44 = archive_entry_pathname(a2);
    if ( v44 )
    {
      v45 = -1;
      do
        ++v45;
      while ( *(_BYTE *)(v44 + v45) );
      if ( v45 && *(_BYTE *)(v45 + v44 - 1) != 47 )
      {
        Block = 0;
        v75 = 0;
        v76 = 0;
        archive_strncat(&Block, v44, 0x1000000);
        LOBYTE(v46) = 47;
        archive_strappend_char(&Block, v46);
        archive_mstring_copy_mbs(a2 + 488, Block);
        goto LABEL_74;
      }
    }
  }
LABEL_75:
  if ( (*(_BYTE *)(v3 + 130) & 2) != 0 )
  {
    *(_WORD *)(v3 + 126) &= ~8u;
    if ( *(_DWORD *)(v3 + 120) )
    {
      if ( !*(_BYTE *)(a3 + 160) && *(_DWORD *)(v3 + 120) != _mm_cvtsi128_si32(_mm_srli_si128(v11, 8)) )
      {
        archive_set_error(a1, 42, "Inconsistent CRC32 values");
        v73 = -20;
      }
    }
    else
    {
      *(_DWORD *)(v3 + 120) = _mm_cvtsi128_si32(_mm_srli_si128(v11, 8));
    }
    v47 = *(_QWORD *)(v3 + 40);
    if ( !v47 || v47 == 0xFFFFFFFFLL )
    {
      *(_QWORD *)(v3 + 40) = _mm_srli_si128(v9, 8).m128i_u64[0];
    }
    else
    {
      v48 = _mm_srli_si128(v9, 8).m128i_u64[0];
      if ( v47 != v48 )
      {
        archive_set_error(
          a1,
          42,
          "Inconsistent compressed size: %jd in central directory, %jd in local header",
          v48,
          *(_QWORD *)(v3 + 40));
        v73 = -20;
      }
    }
    v49 = *(_QWORD *)(v3 + 48);
    if ( !v49 || v49 == 0xFFFFFFFFLL )
    {
      *(_QWORD *)(v3 + 48) = v10;
    }
    else if ( v49 != (_QWORD)v10 )
    {
      archive_set_error(
        a1,
        42,
        "Inconsistent uncompressed size: %jd in central directory, %jd in local header",
        (intmax_t)v10,
        *(_QWORD *)(v3 + 48));
      v73 = -20;
    }
  }
  v50 = *(_WORD *)(v3 + 124);
  *(_DWORD *)(a2 + 160) |= 0x600u;
  v51 = *(_DWORD *)(a2 + 160);
  *(_WORD *)(a2 + 1032) = v50;
  v52 = 0;
  *(_DWORD *)(a2 + 16) = 0;
  if ( *(__int64 *)(v3 + 64) >= 0 )
    v52 = *(_QWORD *)(v3 + 64);
  v53 = v51 | 0x800;
  *(_DWORD *)(a2 + 160) = v53;
  *(_QWORD *)(a2 + 120) = v52;
  v54 = 0;
  if ( *(__int64 *)(v3 + 56) >= 0 )
    v54 = *(_QWORD *)(v3 + 56);
  *(_DWORD *)(a2 + 160) = v53 | 0x1000;
  *(_QWORD *)(a2 + 88) = v54;
  archive_entry_set_mtime(a2, *(_QWORD *)(v3 + 96), 0);
  archive_entry_set_ctime(a2, *(_QWORD *)(v3 + 112), 0);
  archive_entry_set_atime(a2, *(_QWORD *)(v3 + 104), 0);
  if ( (*(_WORD *)(*(_QWORD *)(a3 + 112) + 124LL) & 0xF000) != 0xA000 )
  {
    if ( (*(_BYTE *)(v3 + 126) & 8) == 0 || *(__int64 *)(v3 + 48) > 0 && *(_QWORD *)(v3 + 48) != 0xFFFFFFFFLL )
    {
      v67 = *(_QWORD *)(v3 + 48);
      v68 = 0;
      *(_DWORD *)(a2 + 16) = 0;
      if ( v67 >= 0 )
        v68 = v67;
      *(_DWORD *)(a2 + 160) |= 0x40u;
      *(_QWORD *)(a2 + 112) = v68;
    }
    goto LABEL_131;
  }
  v55 = *(_QWORD *)(v3 + 40);
  v77 = v55;
  if ( v55 > 0x10000 )
  {
    v18 = "Zip file with oversized link entry";
    goto LABEL_7;
  }
  *(_DWORD *)(a2 + 160) |= 0x40u;
  v56 = v55;
  *(_DWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 112) = 0;
  v57 = *(_QWORD *)(a3 + 112);
  v80 = v55;
  v58 = *(_BYTE *)(v57 + 128);
  if ( !v58 )
  {
    v60 = _archive_read_filter_ahead(*(_QWORD *)(a1 + 632), v55, 0);
    goto LABEL_107;
  }
  v79 = 0;
  if ( v58 == 8 )
  {
    *(_QWORD *)(a3 + 120) = *(_QWORD *)(v3 + 40);
    v59 = zip_read_data_deflate(a1, &v79, &v80);
  }
  else
  {
    if ( v58 != 14 )
    {
LABEL_105:
      v61 = (const char *)compression_name(*(unsigned __int8 *)(*(_QWORD *)(a3 + 112) + 128LL));
      archive_set_error(
        a1,
        42,
        "Unsupported ZIP compression method during decompression of link entry (%d: %s)",
        v62,
        v61);
      return 4294967271LL;
    }
    *(_QWORD *)(a3 + 120) = *(_QWORD *)(v3 + 40);
    v59 = zip_read_data_zipx_lzma_alone(a1, &v79, &v80);
  }
  if ( v59 )
    goto LABEL_105;
  v60 = v79;
  v56 = v80;
LABEL_107:
  if ( !v60 )
  {
    v18 = "Truncated Zip file";
    goto LABEL_7;
  }
  v64 = *(_QWORD *)(a3 + 7952);
  if ( !v64 && ((*(_WORD *)(*(_QWORD *)(a3 + 112) + 126LL) & 0x800) == 0 || (v64 = *(_QWORD *)(a3 + 7968)) == 0) )
    v64 = *(_QWORD *)(a3 + 7960);
  if ( (unsigned int)archive_entry_copy_symlink_l(a2, v60, v56, v64) )
  {
    if ( *(_DWORD *)_o__errno() != 12
      && v64 == *(_QWORD *)(a3 + 7968)
      && (*(_WORD *)(*(_QWORD *)(a3 + 112) + 126LL) & 0x800) != 0 )
    {
      archive_entry_copy_symlink_l(a2, v60, v56, 0);
    }
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      v18 = "Can't allocate memory for Symlink";
      goto LABEL_23;
    }
    if ( v64 != *(_QWORD *)(a3 + 7968) || (*(_WORD *)(*(_QWORD *)(a3 + 112) + 126LL) & 0x800) == 0 )
    {
      v65 = (const char *)archive_string_conversion_charset_name(v64);
      archive_set_error(a1, 42, "Symlink cannot be converted from %s to current locale.", v65);
      v73 = -20;
    }
  }
  v66 = v77;
  *(_QWORD *)(v3 + 40) = 0;
  *(_QWORD *)(v3 + 48) = 0;
  if ( _archive_read_filter_consume(*(_QWORD *)(a1 + 632), v66) < 0 )
  {
    v18 = "Read error skipping symlink target name";
    goto LABEL_7;
  }
LABEL_131:
  v69 = *(_QWORD *)(v3 + 40);
  *(_QWORD *)(a3 + 120) = v69;
  if ( (*(_BYTE *)(v3 + 126) & 8) == 0 && v69 < 1 )
    *(_BYTE *)(a3 + 162) = 1;
  *(_QWORD *)(a3 + 8) = 0;
  v70 = (const char *)compression_name(*(unsigned __int8 *)(*(_QWORD *)(a3 + 112) + 128LL));
  archive_string_sprintf(a3, "ZIP %d.%d (%s)", v72, v71 - 10 * v72, v70);
  result = v73;
  *(_QWORD *)(a1 + 24) = *(_QWORD *)a3;
  return result;
}

```

## disassembly

```asm
0x1800eb920  mov     rax, rsp
0x1800eb923  mov     [rax+10h], rbx
0x1800eb927  push    rbp
0x1800eb928  push    rsi
0x1800eb929  push    rdi
0x1800eb92a  push    r12
0x1800eb92c  push    r13
0x1800eb92e  push    r14
0x1800eb930  push    r15
0x1800eb932  lea     rbp, [rax-58h]
0x1800eb936  sub     rsp, 120h
0x1800eb93d  mov     rbx, [r8+70h]
0x1800eb941  mov     rdi, r8
0x1800eb944  movaps  xmmword ptr [rax-48h], xmm6
0x1800eb948  xor     r12d, r12d
0x1800eb94b  movaps  xmmword ptr [rax-58h], xmm7
0x1800eb94f  mov     r15, rdx
0x1800eb952  movaps  xmmword ptr [rax-68h], xmm8
0x1800eb957  mov     rsi, rcx
0x1800eb95a  movups  xmm0, xmmword ptr [rbx]
0x1800eb95d  mov     rax, [rdi+98h]
0x1800eb964  xor     edx, edx
0x1800eb966  movups  xmm1, xmmword ptr [rbx+10h]
0x1800eb96a  xor     ecx, ecx
0x1800eb96c  movups  xmm7, xmmword ptr [rbx+20h]
0x1800eb970  movups  xmm8, xmmword ptr [rbx+30h]
0x1800eb975  movups  xmm6, xmmword ptr [rbx+70h]
0x1800eb979  movups  [rsp+150h+var_F8+8], xmm0
0x1800eb97e  movups  xmm0, xmmword ptr [rbx+40h]
0x1800eb982  movups  xmmword ptr [rsp+150h+var_E8+8], xmm1
0x1800eb987  movups  xmm1, xmmword ptr [rbx+50h]
0x1800eb98b  movups  [rbp+50h+var_B0], xmm0
0x1800eb98f  movups  xmm0, xmmword ptr [rbx+60h]
0x1800eb993  movups  [rbp+50h+var_A0], xmm1
0x1800eb997  movups  [rbp+50h+var_90], xmm0
0x1800eb99b  movups  xmm0, xmmword ptr [rbx+80h]
0x1800eb9a2  mov     [r8+0A1h], r12w
0x1800eb9aa  mov     [r8+88h], r12
0x1800eb9b1  mov     [r8+80h], r12
0x1800eb9b8  xor     r8d, r8d
0x1800eb9bb  movups  [rbp+50h+var_70], xmm0
0x1800eb9bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb9c4  mov     [rdi+90h], eax
0x1800eb9ca  cmp     [rdi+1F10h], r12
0x1800eb9d1  jnz     short loc_1800EB9F5
0x1800eb9d3  cmp     [rdi+1F28h], r12d
0x1800eb9da  jnz     short loc_1800EB9F5
0x1800eb9dc  mov     rcx, rsi
0x1800eb9df  call    archive_string_default_conversion_for_read
0x1800eb9e4  mov     [rdi+1F18h], rax
0x1800eb9eb  mov     dword ptr [rdi+1F28h], 1
0x1800eb9f5  mov     rcx, [rsi+278h]
0x1800eb9fc  xor     r8d, r8d
0x1800eb9ff  lea     r13d, [r8+1Eh]
0x1800eba03  mov     edx, r13d
0x1800eba06  call    __archive_read_filter_ahead
0x1800eba0b  mov     r14, rax
0x1800eba0e  test    rax, rax
0x1800eba11  jz      loc_1800EC3BD
0x1800eba17  cmp     dword ptr [rax], 4034B50h
0x1800eba1d  jz      short loc_1800EBA2E
0x1800eba1f  lea     r8, aDamagedZipArch; "Damaged Zip archive"
0x1800eba26  or      edx, 0FFFFFFFFh
0x1800eba29  jmp     loc_1800EC3C9
0x1800eba2e  mov     al, [rax+4]
0x1800eba31  mov     [rbp+50h+arg_18], al
0x1800eba34  mov     al, [r14+5]
0x1800eba38  mov     [rbx+81h], al
0x1800eba3e  movzx   ecx, byte ptr [r14+7]
0x1800eba43  movzx   eax, byte ptr [r14+6]
0x1800eba48  shl     cx, 8
0x1800eba4c  or      cx, ax
0x1800eba4f  mov     [rbx+7Eh], cx
0x1800eba53  test    cl, 41h
0x1800eba56  jz      short loc_1800EBA85
0x1800eba58  mov     dword ptr [rdi+38h], 1
0x1800eba5f  mov     edx, 2041h
0x1800eba64  or      byte ptr [r15+320h], 1
0x1800eba6c  movzx   eax, word ptr [rbx+7Eh]
0x1800eba70  and     ax, dx
0x1800eba73  cmp     ax, dx
0x1800eba76  jnz     short loc_1800EBA85
0x1800eba78  or      byte ptr [r15+320h], 2
0x1800eba80  jmp     loc_1800EC3D1
0x1800eba85  mov     al, [rbx+7Eh]
0x1800eba88  and     al, 1
0x1800eba8a  mov     [rdi+1F30h], al
0x1800eba90  mov     al, [r14+8]
0x1800eba94  mov     [rbx+80h], al
0x1800eba9a  movzx   eax, byte ptr [r14+0Ch]
0x1800eba9f  movzx   ecx, byte ptr [r14+0Dh]
0x1800ebaa4  shl     ecx, 8
0x1800ebaa7  or      ecx, eax
0x1800ebaa9  movzx   eax, byte ptr [r14+0Bh]
0x1800ebaae  shl     ecx, 8
0x1800ebab1  or      ecx, eax
0x1800ebab3  movzx   eax, byte ptr [r14+0Ah]
0x1800ebab8  shl     ecx, 8
0x1800ebabb  or      ecx, eax
0x1800ebabd  call    dos_to_unix
0x1800ebac2  mov     [rbx+60h], rax
0x1800ebac6  movzx   eax, byte ptr [r14+10h]
0x1800ebacb  movzx   ecx, byte ptr [r14+11h]
0x1800ebad0  shl     ecx, 8
0x1800ebad3  or      ecx, eax
0x1800ebad5  movzx   eax, byte ptr [r14+0Fh]
0x1800ebada  shl     ecx, 8
0x1800ebadd  or      ecx, eax
0x1800ebadf  movzx   eax, byte ptr [r14+0Eh]
0x1800ebae4  shl     ecx, 8
0x1800ebae7  or      ecx, eax
0x1800ebae9  lea     rax, [r14+0Bh]
0x1800ebaed  test    byte ptr [rbx+7Eh], 8
0x1800ebaf1  mov     [rbx+78h], ecx
0x1800ebaf4  jnz     short loc_1800EBAFA
0x1800ebaf6  lea     rax, [r14+11h]
0x1800ebafa  mov     al, [rax]
0x1800ebafc  mov     rdx, r13
0x1800ebaff  mov     [rbx+83h], al
0x1800ebb05  movzx   eax, byte ptr [r14+14h]
0x1800ebb0a  movzx   ecx, byte ptr [r14+15h]
0x1800ebb0f  shl     rcx, 8
0x1800ebb13  or      rcx, rax
0x1800ebb16  movzx   eax, byte ptr [r14+13h]
0x1800ebb1b  shl     rcx, 8
0x1800ebb1f  or      rcx, rax
0x1800ebb22  movzx   eax, byte ptr [r14+12h]
0x1800ebb27  shl     rcx, 8
0x1800ebb2b  or      rcx, rax
0x1800ebb2e  mov     [rbx+28h], rcx
0x1800ebb32  movzx   eax, byte ptr [r14+18h]
0x1800ebb37  movzx   ecx, byte ptr [r14+19h]
0x1800ebb3c  shl     rcx, 8
0x1800ebb40  or      rcx, rax
0x1800ebb43  movzx   eax, byte ptr [r14+17h]
0x1800ebb48  shl     rcx, 8
0x1800ebb4c  or      rcx, rax
0x1800ebb4f  movzx   eax, byte ptr [r14+16h]
0x1800ebb54  shl     rcx, 8
0x1800ebb58  or      rcx, rax
0x1800ebb5b  mov     [rbx+30h], rcx
0x1800ebb5f  movzx   eax, byte ptr [r14+1Ah]
0x1800ebb64  movzx   r12d, byte ptr [r14+1Bh]
0x1800ebb69  mov     rcx, [rsi+278h]
0x1800ebb70  shl     r12, 8
0x1800ebb74  or      r12, rax
0x1800ebb77  mov     al, [r14+1Dh]
0x1800ebb7b  mov     byte ptr [rbp+50h+arg_0], al
0x1800ebb7e  mov     al, [r14+1Ch]
0x1800ebb82  mov     byte ptr [rbp+50h+arg_10], al
0x1800ebb85  call    __archive_read_filter_consume
0x1800ebb8a  mov     rcx, [rsi+278h]
0x1800ebb91  xor     r8d, r8d
0x1800ebb94  mov     rdx, r12
0x1800ebb97  call    __archive_read_filter_ahead
0x1800ebb9c  mov     r13, rax
0x1800ebb9f  xor     eax, eax
0x1800ebba1  test    r13, r13
0x1800ebba4  jz      loc_1800EC3BD
0x1800ebbaa  mov     ecx, 800h
0x1800ebbaf  test    [rbx+7Eh], cx
0x1800ebbb3  jz      short loc_1800EBBEB
0x1800ebbb5  mov     r14, [rdi+1F20h]
0x1800ebbbc  test    r14, r14
0x1800ebbbf  jnz     short loc_1800EBBFE
0x1800ebbc1  lea     r8d, [rax+1]
0x1800ebbc5  mov     rcx, rsi
0x1800ebbc8  lea     rdx, Str2; "UTF-8"
0x1800ebbcf  call    archive_string_conversion_from_charset
0x1800ebbd4  mov     r14, rax
0x1800ebbd7  mov     [rdi+1F20h], rax
0x1800ebbde  xor     eax, eax
0x1800ebbe0  test    r14, r14
0x1800ebbe3  jz      loc_1800EC3D1
0x1800ebbe9  jmp     short loc_1800EBBFE
0x1800ebbeb  mov     r14, [rdi+1F10h]
0x1800ebbf2  test    r14, r14
0x1800ebbf5  jnz     short loc_1800EBBFE
0x1800ebbf7  mov     r14, [rdi+1F18h]
0x1800ebbfe  mov     rdx, r13
0x1800ebc01  mov     dword ptr [rsp+150h+var_120], eax
0x1800ebc05  lea     r13, [r15+1E8h]
0x1800ebc0c  mov     r9, r14
0x1800ebc0f  mov     rcx, r13
0x1800ebc12  mov     r8, r12
0x1800ebc15  call    archive_mstring_copy_mbs_len_l
0x1800ebc1a  test    eax, eax
0x1800ebc1c  jz      short loc_1800EBC61
0x1800ebc1e  call    cs:__imp__o__errno
0x1800ebc24  cmp     dword ptr [rax], 0Ch
0x1800ebc27  jnz     short loc_1800EBC3A
0x1800ebc29  lea     r8, aCanTAllocateMe_24; "Can't allocate memory for Pathname"
0x1800ebc30  mov     edx, 0Ch
0x1800ebc35  jmp     loc_1800EC3C9
0x1800ebc3a  mov     rcx, r14
0x1800ebc3d  call    archive_string_conversion_charset_name
0x1800ebc42  mov     r9, rax
0x1800ebc45  lea     r8, aPathnameCannot_0; "Pathname cannot be converted from %s to"...
0x1800ebc4c  mov     edx, 2Ah ; '*'
0x1800ebc51  mov     rcx, rsi
0x1800ebc54  call    archive_set_error
0x1800ebc59  mov     dword ptr [rsp+150h+var_120], 0FFFFFFECh
0x1800ebc61  movzx   eax, byte ptr [rbp+50h+arg_10]
0x1800ebc65  mov     rdx, r12
0x1800ebc68  movzx   r14d, byte ptr [rbp+50h+arg_0]
0x1800ebc6d  mov     rcx, [rsi+278h]
0x1800ebc74  shl     r14, 8
0x1800ebc78  or      r14, rax
0x1800ebc7b  call    __archive_read_filter_consume
0x1800ebc80  mov     rcx, [rsi+278h]
0x1800ebc87  xor     r8d, r8d
0x1800ebc8a  mov     rdx, r14
0x1800ebc8d  call    __archive_read_filter_ahead
0x1800ebc92  xor     r12d, r12d
0x1800ebc95  test    rax, rax
0x1800ebc98  jz      loc_1800EC3BD
0x1800ebc9e  mov     r9, r14
0x1800ebca1  mov     [rsp+150h+var_130], rbx
0x1800ebca6  mov     r8, rax
0x1800ebca9  mov     rdx, r15
0x1800ebcac  mov     rcx, rsi
0x1800ebcaf  call    process_extra
0x1800ebcb4  test    eax, eax
0x1800ebcb6  jnz     loc_1800EC3D1
0x1800ebcbc  mov     rcx, [rsi+278h]
0x1800ebcc3  mov     rdx, r14
0x1800ebcc6  call    __archive_read_filter_consume
0x1800ebccb  movzx   ecx, word ptr [rbx+7Ch]
0x1800ebccf  mov     edx, 0F000h
0x1800ebcd4  movzx   eax, cx
0x1800ebcd7  mov     r8d, 1000h
0x1800ebcdd  and     ax, dx
0x1800ebce0  cmp     ax, r8w
0x1800ebce4  jnz     short loc_1800EBCF6
0x1800ebce6  lea     eax, [r8-1]
0x1800ebcea  and     cx, ax
0x1800ebced  or      cx, 8000h
0x1800ebcf2  mov     [rbx+7Ch], cx
0x1800ebcf6  test    cx, cx
0x1800ebcf9  jnz     short loc_1800EBD01
0x1800ebcfb  mov     word ptr [rbx+7Ch], 1B4h
0x1800ebd01  mov     r14d, 2Fh ; '/'
0x1800ebd07  cmp     [rbx+81h], r12b
0x1800ebd0e  jnz     loc_1800EBDD4
0x1800ebd14  mov     rcx, r15
0x1800ebd17  call    archive_entry_pathname_w
0x1800ebd1c  mov     r14, rax
0x1800ebd1f  test    rax, rax
0x1800ebd22  jz      loc_1800EBDCE
0x1800ebd28  mov     edx, 2Fh ; '/'; Ch
0x1800ebd2d  mov     rcx, rax; Str
0x1800ebd30  call    cs:__imp_wcschr
0x1800ebd36  test    rax, rax
0x1800ebd39  jnz     loc_1800EBDCE
0x1800ebd3f  lea     edx, [rax+5Ch]; Ch
0x1800ebd42  mov     rcx, r14; Str
0x1800ebd45  call    cs:__imp_wcschr
0x1800ebd4b  test    rax, rax
0x1800ebd4e  jz      short loc_1800EBDCE
0x1800ebd50  mov     [rsp+150h+Block], r12
0x1800ebd55  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ebd59  mov     [rsp+150h+var_108], r12
0x1800ebd5e  mov     [rsp+150h+var_110], r12
0x1800ebd63  inc     r8
0x1800ebd66  cmp     [r14+r8*2], r12w
0x1800ebd6b  jnz     short loc_1800EBD63
0x1800ebd6d  mov     rdx, r14
0x1800ebd70  lea     rcx, [rsp+150h+Block]
0x1800ebd75  call    archive_wstrncat
0x1800ebd7a  mov     rcx, [rsp+150h+var_110]
0x1800ebd7f  mov     rax, r12
0x1800ebd82  test    rcx, rcx
0x1800ebd85  jz      short loc_1800EBDAC
0x1800ebd87  mov     r9d, 5Ch ; '\'
0x1800ebd8d  mov     rdx, [rsp+150h+Block]
0x1800ebd92  cmp     [rdx+rax*2], r9w
0x1800ebd97  jnz     short loc_1800EBDA4
0x1800ebd99  mov     word ptr [rdx+rax*2], 2Fh ; '/'
0x1800ebd9f  mov     rcx, [rsp+150h+var_110]
0x1800ebda4  inc     rax
0x1800ebda7  cmp     rax, rcx
0x1800ebdaa  jb      short loc_1800EBD8D
0x1800ebdac  mov     rdx, [rsp+150h+Block]
0x1800ebdb1  mov     rcx, r13
0x1800ebdb4  call    archive_mstring_copy_wcs
0x1800ebdb9  mov     rcx, [rsp+150h+Block]; Block
0x1800ebdbe  mov     [rsp+150h+var_110], r12
0x1800ebdc3  mov     [rsp+150h+var_108], r12
0x1800ebdc8  call    cs:__imp_free
0x1800ebdce  mov     r14d, 2Fh ; '/'
0x1800ebdd4  movzx   ecx, word ptr [rbx+7Ch]
0x1800ebdd8  mov     edx, 0F000h
0x1800ebddd  movzx   eax, cx
0x1800ebde0  and     ax, dx
0x1800ebde3  mov     edx, 4000h
0x1800ebde8  cmp     ax, dx
0x1800ebdeb  jz      loc_1800EBE76
0x1800ebdf1  mov     rcx, r15
0x1800ebdf4  call    archive_entry_pathname_w
0x1800ebdf9  test    rax, rax
  ... truncated ...
```
