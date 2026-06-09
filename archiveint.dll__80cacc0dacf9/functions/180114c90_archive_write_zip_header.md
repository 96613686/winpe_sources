# archive_write_zip_header

- ea: `0x180114c90`
- end: `0x180115c31`
- name: `archive_write_zip_header`
- size: `4001`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180006c00`
- `0x18000e8d4`
- `0x180014fc0`
- `0x180015810`
- `0x180015c20`
- `0x180023c20`
- `0x180023d50`
- `0x180024820`
- `0x180024c60`
- `0x18003c3d0`
- `0x18003d350`
- `0x1800415a0`
- `0x180042c60`
- `0x1800433f0`
- `0x180043400`
- `0x1800aba54`
- `0x1800b072c`
- `0x1800b0b0c`
- `0x1800b1300`
- `0x1800b1830`
- `0x1800b1b60`
- `0x1800b1f40`
- `0x1800b2770`
- `0x1800b3a6c`
- `0x1800ece24`
- `0x1800ed038`
- `0x1800ed464`
- `0x1800ed554`
- `0x1800ee68c`
- `0x1800ef2d4`
- `0x1800f8774`
- `0x180114c90`
- `0x1801163d0`
- `0x180116880`
- `0x180117818`
- `0x180119956`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180114f12`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180114fa1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180114f12`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180114fa1`

## string_xrefs

- `0x180114f1d`: `Can't allocate memory for Pathname`
- `0x180114d68`: `Files > 4GB require Zip64 extensions`
- `0x180114d88`: `Archives > 4GB require Zip64 extensions`
- `0x180114f45`: `Can't translate Pathname '%s' to %s`
- `0x180114fac`: `Can't allocate memory  for Symlink`
- `0x180115bdf`: `Can't init deflate compressor`
- `0x180115b80`: `Can't init bzip2 compressor`
- `0x180115a3d`: `Can't init zstd compressor`
- `0x180115b04`: `Can't init lzma compressor`
- `0x1801159e0`: `Can't init xz compressor`

## pseudocode

```c
__int64 __fastcall archive_write_zip_header(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 v5; // rsi
  __int64 *v6; // rbx
  __int16 v7; // di
  bool v8; // zf
  _BYTE *v9; // r12
  _BYTE *v10; // rbx
  __int64 (__fastcall *v11)(_QWORD, _QWORD, _QWORD); // rax
  int v12; // eax
  __int64 v13; // rcx
  int v14; // edx
  __int64 *v15; // rax
  __int64 v17; // rcx
  const char *v18; // rbx
  const char *v19; // rax
  unsigned __int8 *v20; // rax
  unsigned __int8 v21; // cl
  __int64 v22; // rcx
  const char *v23; // rax
  __int64 v24; // rcx
  __int16 v25; // bx
  _BYTE *v26; // rax
  __int16 v27; // bx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  int *v33; // rsi
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // r9
  int v37; // ecx
  unsigned int v38; // ebx
  int v39; // r8d
  __int64 v40; // rdx
  int v41; // edx
  int v42; // ecx
  int v43; // r8d
  __m128i v44; // xmm6
  __m128i v45; // xmm6
  unsigned int v46; // edx
  unsigned int v47; // edx
  int v48; // ecx
  int v49; // ecx
  __int16 v50; // di
  char v51; // cl
  _OWORD *v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  int v55; // eax
  void *v56; // r9
  __int64 v57; // rax
  __int64 v58; // rcx
  int v59; // r8d
  _BYTE *v60; // rax
  _BYTE *v61; // rdi
  size_t v62; // rbx
  int *p_Src; // rdi
  int v64; // ecx
  int v65; // ecx
  __int64 v66; // rax
  int v67; // eax
  char v68; // al
  void *v69; // rax
  int v70; // r8d
  int v71; // r10d
  char v72; // r9
  int *v73; // r11
  int v74; // r8d
  _BYTE *v75; // rdi
  int v76; // r9d
  __int64 v77; // rdx
  int v78; // ecx
  int v79; // ecx
  int v80; // ecx
  char v81; // al
  int *v82; // r9
  __int16 v83; // cx
  __int64 v84; // rcx
  __int64 v85; // rcx
  int v86; // eax
  __int64 v87; // rdi
  __int64 v88; // r8
  __int64 v89; // rbx
  __m128i v90; // xmm0
  unsigned int v91; // ebx
  int v92; // eax
  int v93; // eax
  int v94; // ebx
  unsigned int v95; // eax
  __int64 v96; // rdx
  __int64 v97; // rcx
  int v98; // eax
  int v99; // eax
  unsigned int v100; // edx
  __int64 v101; // rt2
  unsigned int v102; // ebx
  __int64 CStream; // rax
  __int64 inited; // rax
  unsigned int v105; // esi
  __int64 v106; // rdx
  __int64 v107; // rdx
  __int64 v108; // rdx
  void *v109; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v110; // [rsp+50h] [rbp-B8h] BYREF
  __int16 v111; // [rsp+58h] [rbp-B0h]
  __int16 v112; // [rsp+5Ah] [rbp-AEh]
  unsigned int v113; // [rsp+5Ch] [rbp-ACh]
  int *v114; // [rsp+60h] [rbp-A8h]
  __m128i v115; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v116; // [rsp+78h] [rbp-90h]
  __int64 v117; // [rsp+80h] [rbp-88h] BYREF
  __int64 v118; // [rsp+88h] [rbp-80h]
  __int64 v119; // [rsp+90h] [rbp-78h]
  __int64 v120; // [rsp+98h] [rbp-70h]
  _DWORD v121[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v122; // [rsp+B0h] [rbp-58h]
  int v123; // [rsp+B8h] [rbp-50h]
  unsigned int v124; // [rsp+BCh] [rbp-4Ch]
  __int64 v125; // [rsp+C0h] [rbp-48h]
  __int128 v126; // [rsp+C8h] [rbp-40h]
  __int128 v127; // [rsp+D8h] [rbp-30h]
  __int64 v128; // [rsp+E8h] [rbp-20h]
  __int64 v129; // [rsp+F0h] [rbp-18h]
  __int64 v130; // [rsp+F8h] [rbp-10h]
  __int64 v131; // [rsp+100h] [rbp-8h]
  _OWORD v132[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v133; // [rsp+128h] [rbp+20h] BYREF
  __int128 v134; // [rsp+138h] [rbp+30h]
  int Src; // [rsp+148h] [rbp+40h] BYREF
  char v136; // [rsp+14Ch] [rbp+44h]
  char v137; // [rsp+14Dh] [rbp+45h]
  int v138; // [rsp+14Eh] [rbp+46h]
  char v139; // [rsp+152h] [rbp+4Ah]
  int v140; // [rsp+153h] [rbp+4Bh]
  char v141; // [rsp+157h] [rbp+4Fh] BYREF

  v2 = *(_QWORD *)(a1 + 248);
  v115.m128i_i64[1] = a2;
  v5 = *(_QWORD *)(v2 + 272);
  if ( !v5 )
  {
    v6 = (__int64 *)(v2 + 280);
    if ( !*(_DWORD *)(v2 + 296) )
    {
      *v6 = archive_string_default_conversion_for_write();
      *(_DWORD *)(v2 + 296) = 1;
    }
    v5 = *v6;
  }
  v7 = *(_WORD *)(a2 + 1032) & 0xF000;
  if ( ((v7 - 0x4000) & 0x9FFF) != 0 || v7 == 24576 )
  {
    _archive_write_entry_filetype_unsupported(a1, a2, "zip");
    return 4294967271LL;
  }
  v8 = (*(_BYTE *)(v2 + 308) & 1) == 0;
  v9 = (_BYTE *)(a2 + 160);
  v114 = (int *)(a2 + 160);
  if ( v8 )
    goto LABEL_13;
  if ( (*v9 & 0x40) == 0 || *(__int64 *)(a2 + 112) <= 0xFFFFFFFFLL )
  {
    if ( *(__int64 *)(v2 + 264) > 0xFFFFFFFFLL )
    {
      archive_set_error(a1, 0xFFFFFFFFLL, "Archives > 4GB require Zip64 extensions");
      return 4294967271LL;
    }
LABEL_13:
    v10 = (_BYTE *)(a2 + 160);
    if ( v7 != (__int16)0x8000 )
    {
      v10 = (_BYTE *)(a2 + 160);
      *(_DWORD *)(a2 + 16) = 0;
      *(_DWORD *)(a2 + 160) |= 0x40u;
      *(_QWORD *)(a2 + 112) = 0;
    }
    *(_QWORD *)v2 = *(_QWORD *)(v2 + 264);
    *(_QWORD *)(v2 + 8) = 0;
    *(_QWORD *)(v2 + 40) = 0x7FFFFFFFFFFFFFFFLL;
    v11 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v2 + 224);
    *(_QWORD *)(v2 + 16) = 0;
    *(_QWORD *)(v2 + 24) = 0;
    *(_QWORD *)(v2 + 32) = 0;
    *(_DWORD *)(v2 + 68) = 0;
    v12 = v11(0, 0, 0);
    v13 = *(_QWORD *)(v2 + 48);
    *(_DWORD *)(v2 + 56) = v12;
    *(_DWORD *)(v2 + 64) = 0;
    archive_entry_free(v13);
    *(_QWORD *)(v2 + 48) = 0;
    if ( *(_BYTE *)(v2 + 160) )
    {
      aes_ctr_release((void *)(v2 + 96));
      v10 = (_BYTE *)(a2 + 160);
    }
    if ( *(_BYTE *)(v2 + 200) )
    {
      _hmac_sha1_cleanup(v2 + 168);
    }
    else
    {
      v9 = v10;
      v114 = (int *)v10;
    }
    *(_BYTE *)(v2 + 200) = 0;
    *(_BYTE *)(v2 + 160) = 0;
    *(_BYTE *)(v2 + 88) = 0;
    if ( v7 == (__int16)0x8000 && ((*v9 & 0x40) == 0 || *(__int64 *)(a2 + 112) > 0) )
    {
      v14 = *(_DWORD *)(v2 + 300);
      if ( v14 == 1 || (unsigned int)(*(_DWORD *)(v2 + 300) - 2) <= 1 )
      {
        *(_DWORD *)(v2 + 68) |= 1u;
        *(_DWORD *)(v2 + 64) = v14;
      }
    }
    v15 = (__int64 *)_la_win_entry_in_posix_pathseparator(a2);
    *(_QWORD *)(v2 + 48) = v15;
    if ( v15 == (__int64 *)a2 )
    {
      v15 = (__int64 *)archive_entry_clone(a2);
      *(_QWORD *)(v2 + 48) = v15;
    }
    if ( !v15 )
    {
      archive_set_error(a1, 12, "Can't allocate zip header data");
      return 4294967266LL;
    }
    v113 = 0;
    if ( v5 )
    {
      v17 = *v15;
      v109 = 0;
      v110 = 0;
      if ( (unsigned int)archive_mstring_get_mbs_l(v17, (int)v15 + 488, (unsigned int)&v109, (unsigned int)&v110, v5) )
      {
        if ( *(_DWORD *)_o__errno() == 12 )
        {
          archive_set_error(a1, 12, "Can't allocate memory for Pathname");
          return 4294967266LL;
        }
        v18 = (const char *)archive_string_conversion_charset_name(v5);
        v19 = (const char *)archive_entry_pathname(*(_QWORD *)(v2 + 48));
        archive_set_error(a1, 42, "Can't translate Pathname '%s' to %s", v19, v18);
        v113 = -20;
      }
      if ( v110 )
        archive_mstring_copy_mbs(*(_QWORD *)(v2 + 48) + 488LL, v109);
      if ( v7 == -24576 )
      {
        if ( (unsigned int)archive_entry_symlink_l(*(_QWORD *)(v2 + 48), &v109, &v110, v5) )
        {
          if ( *(_DWORD *)_o__errno() == 12 )
          {
            archive_set_error(a1, 12, "Can't allocate memory  for Symlink");
            return 4294967266LL;
          }
        }
        else if ( v110 )
        {
          archive_entry_copy_symlink(*(_QWORD *)(v2 + 48), v109);
        }
      }
    }
    v20 = (unsigned __int8 *)archive_entry_pathname(*(_QWORD *)(v2 + 48));
    while ( 1 )
    {
      v21 = *v20;
      if ( !*v20 )
        break;
      ++v20;
      if ( v21 > 0x7Fu )
      {
        v22 = *(_QWORD *)(v2 + 272);
        if ( v22 )
        {
          v23 = (const char *)archive_string_conversion_charset_name(v22);
          if ( !strcmp_0(v23, "UTF-8") )
            *(_DWORD *)(v2 + 68) |= 0x800u;
        }
        break;
      }
    }
    v24 = *(_QWORD *)(v2 + 48);
    v25 = *(_WORD *)(v24 + 1032);
    v26 = (_BYTE *)archive_entry_pathname(v24);
    if ( v26 )
    {
      v27 = v25 & 0xF000;
      v28 = -1;
      do
        ++v28;
      while ( v26[v28] );
      v109 = (void *)v28;
      if ( v27 == 0x4000 && (!*v26 || v26[v28 - 1] != 47) )
        v109 = (void *)(v28 + 1);
    }
    else
    {
      v109 = 0;
    }
    if ( v7 == -24576 )
    {
      v116 = archive_entry_symlink(*(_QWORD *)(v2 + 48));
      v29 = v116;
      if ( v116 )
      {
        v30 = -1;
        do
          ++v30;
        while ( *(_BYTE *)(v116 + v30) );
      }
      else
      {
        v30 = 0;
      }
      v115.m128i_i64[0] = v30;
      *(_QWORD *)(v2 + 40) = v30;
      v31 = v29;
      v32 = *(unsigned int *)(v2 + 56);
      *(_QWORD *)(v2 + 8) = v30;
      *(_QWORD *)(v2 + 16) = v30;
      *(_DWORD *)(v2 + 56) = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(v2 + 224))(v32, v31, v30);
      v33 = (int *)(v2 + 60);
      goto LABEL_67;
    }
    v116 = 0;
    v115.m128i_i64[0] = 0;
    v33 = (int *)(v2 + 60);
    if ( v7 != (__int16)0x8000 )
    {
      *(_QWORD *)(v2 + 40) = 0;
LABEL_67:
      *v33 = 0;
LABEL_134:
      LOWORD(v38) = 20;
      goto LABEL_135;
    }
    v34 = *(_QWORD *)(v2 + 48);
    if ( (*(_BYTE *)(v34 + 160) & 0x40) != 0 )
    {
      v35 = *(_QWORD *)(v34 + 112);
      v36 = 0;
      v37 = *(_DWORD *)(v2 + 288);
      *(_QWORD *)(v2 + 40) = v35;
      *v33 = v37;
      if ( v37 == -1 )
      {
        *v33 = 8;
        v37 = 8;
        *(_QWORD *)(v2 + 16) = v35;
LABEL_76:
        if ( *(_WORD *)(v2 + 292) == 1 || *(_WORD *)(v2 + 292) == 2 )
        {
          *(_DWORD *)(v2 + 68) |= 6u;
        }
        else if ( *(_WORD *)(v2 + 292) == 3 || *(_WORD *)(v2 + 292) == 4 )
        {
          *(_DWORD *)(v2 + 68) |= 4u;
        }
        else if ( (unsigned int)(*(__int16 *)(v2 + 292) - 8) <= 1 )
        {
          *(_DWORD *)(v2 + 68) |= 2u;
        }
        v38 = 20;
LABEL_89:
        v39 = *(_DWORD *)(v2 + 68);
        if ( (v39 & 1) == 0 )
        {
LABEL_101:
          if ( (*(_BYTE *)(v2 + 308) & 2) != 0
            || (v40 = *(_QWORD *)(v2 + 16), v40 + v36 > 0xFFFFFFFFLL)
            || v40 > 4278190080LL && v37 )
          {
            if ( (int)v38 < 45 )
              LOWORD(v38) = 45;
          }
          *(_DWORD *)(v2 + 68) = v39 | 8;
          goto LABEL_135;
        }
        switch ( *(_DWORD *)(v2 + 64) )
        {
          case 1:
            v36 = 12;
            if ( v38 < 0x14 )
              v38 = 20;
            goto LABEL_99;
          case 2:
            v36 = 20;
            break;
          case 3:
            v36 = 28;
            break;
          default:
LABEL_99:
            v37 = *v33;
            if ( !*v33 )
              *(_QWORD *)(v2 + 8) += v36;
            goto LABEL_101;
        }
        if ( v38 < 0x14 )
          v38 = 20;
        goto LABEL_99;
      }
      *(_QWORD *)(v2 + 16) = v35;
      switch ( v37 )
      {
        case 0:
          *(_QWORD *)(v2 + 8) = v35;
          v38 = 10;
          goto LABEL_89;
        case 12:
          v38 = 46;
          goto LABEL_89;
        case 14:
          *(_DWORD *)(v2 + 68) |= 2u;
          break;
        case 93:
        case 95:
          break;
        default:
          goto LABEL_76;
      }
      v38 = 63;
      goto LABEL_89;
    }
    v41 = *(_DWORD *)(v2 + 288);
    *v33 = v41;
    if ( v41 == -1 )
    {
      *v33 = 8;
      v41 = 8;
    }
    *(_DWORD *)(v2 + 68) |= 8u;
    v42 = *(_DWORD *)(v2 + 68);
    v43 = *(_DWORD *)(v2 + 308) & 1;
    v38 = v43 != 0 ? 10 : 45;
    switch ( v41 )
    {
      case 0:
LABEL_130:
        if ( (v42 & 1) != 0
          && (*(_DWORD *)(v2 + 64) == 1 || (unsigned int)(*(_DWORD *)(v2 + 64) - 2) <= 1)
          && v38 < 0x14 )
        {
          goto LABEL_134;
        }
LABEL_135:
        v44 = _mm_loadl_epi64(&v115);
        v133 = 0;
        LOWORD(v110) = BYTE1(v38);
        v134 = 0;
        LODWORD(v133) = 67324752;
        WORD2(v133) = v38;
        WORD3(v133) = *(_WORD *)(v2 + 68);
        v45 = _mm_unpacklo_epi64(v44, v44);
        if ( (unsigned int)(*(_DWORD *)(v2 + 64) - 2) <= 1 )
          WORD4(v133) = 99;
        else
          WORD4(v133) = *(_WORD *)v33;
        *(_DWORD *)((char *)&v133 + 10) = unix_to_dos(*(_QWORD *)(*(_QWORD *)(v2 + 48) + 56LL));
        if ( (*(_BYTE *)(v2 + 68) & 8) != 0 )
        {
          LOBYTE(v47) = BYTE1(v134);
        }
        else
        {
          v46 = *(_DWORD *)(v2 + 56);
          LOBYTE(v134) = BYTE2(v46);
          HIWORD(v133) = v46;
          v47 = HIBYTE(v46);
          BYTE1(v134) = v47;
          v48 = *(_DWORD *)(v2 + 8);
          *(_DWORD *)((char *)&v134 + 2) = v48;
          v49 = *(_DWORD *)(v2 + 16);
          *(_DWORD *)((char *)&v134 + 6) = v49;
        }
        WORD5(v134) = (_WORD)v109;
        v50 = (unsigned __int16)v109 >> 8;
        if ( *(_DWORD *)(v2 + 64) == 1 )
        {
          v51 = v47;
          if ( (*(_BYTE *)(v2 + 68) & 8) != 0 )
            v51 = BYTE11(v133);
          *(_BYTE *)(v2 + 89) = v51;
        }
        v52 = (_OWORD *)cd_alloc(v2, 46);
        *(_QWORD *)(v2 + 208) = v52;
        ++*(_QWORD *)(v2 + 256);
        *v52 = 0;
        v111 = v38 + 768;
        v52[1] = 0;
        *(_OWORD *)((char *)v52 + 30) = 0;
        **(_DWORD **)(v2 + 208) = 33639248;
        *(_WORD *)(*(_QWORD *)(v2 + 208) + 4LL) = v38 + 768;
        v53 = *(_QWORD *)(v2 + 208);
        v112 = (unsigned __int16)(v38 + 768) >> 8;
        *(_BYTE *)(v53 + 7) = v110;
        *(_BYTE *)(v53 + 6) = v38;
        *(_WORD *)(*(_QWORD *)(v2 + 208) + 8LL) = *(_WORD *)(v2 + 68);
        v54 = *(_QWORD *)(v2 + 208);
        if ( (unsigned int)(*(_DWORD *)(v2 + 64) - 2) <= 1 )
          *(_WORD *)(v54 + 10) = 99;
        else
          *(_WORD *)(v54 + 10) = *(_WORD *)v33;
        v55 = unix_to_dos(*(_QWORD *)(*(_QWORD *)(v2 + 48) + 56LL));
        v56 = v109;
        *(_DWORD *)(*(_QWORD *)(v2 + 208) + 12LL) = v55;
        v57 = *(_QWORD *)(v2 + 208);
        *(_BYTE *)(v57 + 28) = (_BYTE)v56;
        *(_BYTE *)(v57 + 29) = v50;
        v58 = *(_QWORD *)(v2 + 208);
        v59 = *(unsigned __int16 *)(*(_QWORD *)(v2 + 48) + 1032LL);
        *(_BYTE *)(v58 + 40) = v59;
        v59 <<= 16;
        *(_WORD *)(v58 + 38) = v59;
        *(_BYTE *)(v58 + 41) = HIBYTE(v59);
        v109 = (void *)cd_alloc(v2, v56);
        v110 = *(_QWORD *)(v2 + 48);
        v60 = (_BYTE *)archive_entry_pathname(v110);
        v61 = v60;
        v62 = -1;
        do
          ++v62;
        while ( v60[v62] );
        LODWORD(v110) = *(_WORD *)(v110 + 1032) & 0xF000;
        memcpy_0(v109, v60, v62);
        if ( (_WORD)v110 == 0x4000 && v61[v62 - 1] != 47 )
          *((_BYTE *)v109 + v62) = 47;
        memset_0(&Src, 0, 0x90u);
        p_Src = &Src;
        if ( (*v114 & 0x1800) != 0 )
        {
          p_Src = (int *)&v141;
          strcpy((char *)&Src, "ux\v");
          v136 = 1;
          v64 = *(_DWORD *)(v115.m128i_i64[1] + 120);
          v138 = v64;
          v65 = *(_DWORD *)(v115.m128i_i64[1] + 88);
          v140 = v65;
          v137 = 4;
          v139 = 4;
        }
        if ( (*(_BYTE *)(v2 + 68) & 1) != 0 && (unsigned int)(*(_DWORD *)(v2 + 64) - 2) <= 1 )
        {
          *(_QWORD *)p_Src = 0x4541000100079901LL;
          v66 = *(_QWORD *)(v2 + 48);
          if ( (*(_BYTE *)(v66 + 160) & 0x40) != 0 && *(__int64 *)(v66 + 112) < 20 )
          {
            *((_WORD *)p_Src + 2) = 2;
            v67 = 2;
          }
          else
          {
            v67 = 1;
          }
          *(_DWORD *)(v2 + 92) = v67;
          v68 = 1;
          if ( *(_DWORD *)(v2 + 64) != 2 )
            v68 = 3;
          *((_BYTE *)p_Src + 8) = v68;
          *(_WORD *)((char *)p_Src + 9) = *(_WORD *)v33;
          p_Src = (int *)((char *)p_Src + 11);
        }
        *(_QWORD *)(v2 + 216) = *(_QWORD *)(v2 + 248);
        v69 = (void *)cd_alloc(v2, (char *)p_Src - (char *)&Src);
        memcpy_0(v69, &Src, (char *)p_Src - (char *)&Src);
        v70 = *v114;
        v71 = *v114 & 0x10;
        if ( v71 || (v70 & 0xC) != 0 )
        {
          *p_Src = 21589;
          v72 = v70;
          v73 = p_Src;
          v74 = v70 & 8;
          v75 = p_Src + 1;
          v76 = v72 & 4;
          *v75 = (v71 != 0) | (v76 != 0 ? 2 : 0) | (v74 != 0 ? 4 : 0);
          p_Src = (int *)(v75 + 1);
          v77 = v115.m128i_i64[1];
          if ( v71 )
          {
            v78 = *(_DWORD *)(v115.m128i_i64[1] + 56);
            *p_Src++ = v78;
          }
          if ( v76 )
          {
            v79 = *(_DWORD *)(v77 + 24);
            *p_Src++ = v79;
          }
          if ( v74 )
          {
            v80 = *(_DWORD *)(v77 + 40);
            *p_Src++ = v80;
          }
          *((_WORD *)v73 + 1) = (_WORD)p_Src - (_WORD)v73 - 4;
        }
        if ( (*(_BYTE *)(*(_QWORD *)(v2 + 48) + 160LL) & 0x40) != 0
          && (*(__int64 *)(v2 + 16) > 0xFFFFFFFFLL || *(__int64 *)(v2 + 8) > 0xFFFFFFFFLL) )
        {
          *p_Src++ = 1;
        }
        if ( (*(_BYTE *)(v2 + 308) & 4) != 0 )
        {
          v81 = v111;
          v82 = p_Src;
          *p_Src = 27768;
          *((_BYTE *)p_Src + 4) = 7;
          *((_BYTE *)p_Src + 5) = v81;
          *((_BYTE *)p_Src + 6) = v112;
          *(_WORD *)((char *)p_Src + 7) = 0;
          v83 = *(_WORD *)(*(_QWORD *)(v2 + 48) + 1032LL);
          *((_BYTE *)p_Src + 11) = v83;
          *((_BYTE *)p_Src + 9) = 0;
          *((_BYTE *)p_Src + 10) = 0;
          *((_BYTE *)p_Src + 12) = HIBYTE(v83);
          p_Src = (int *)((char *)p_Src + 13);
          *((_WORD *)v82 + 1) = (_WORD)p_Src - (_WORD)v82 - 4;
        }
        v84 = *(_QWORD *)(a1 + 232);
        WORD6(v134) = (_WORD)p_Src - ((unsigned __int16)v132 + 64);
        if ( (unsigned int)_archive_write_filter(v84, &v133, 30) )
          return 4294967266LL;
        v85 = *(_QWORD *)(v2 + 48);
        *(_QWORD *)(v2 + 264) += 30LL;
        v86 = write_path(v85, a1);
        if ( v86 <= 0 )
          return 4294967266LL;
        *(_QWORD *)(v2 + 264) += v86;
        v87 = (char *)p_Src - (char *)&Src;
        if ( (unsigned int)_archive_write_filter(*(_QWORD *)(a1 + 232), &Src, v87) )
          return 4294967266LL;
        *(_QWORD *)(v2 + 264) += v87;
        if ( v116 )
        {
          v89 = v115.m128i_i64[0];
          if ( (unsigned int)_archive_write_filter(*(_QWORD *)(a1 + 232), v116, v115.m128i_i64[0]) )
            return 4294967266LL;
          v90 = _mm_loadu_si128((const __m128i *)(v2 + 24));
          *(_QWORD *)(v2 + 264) += v89;
          *(__m128i *)(v2 + 24) = _mm_add_epi64(v45, v90);
        }
        switch ( *v33 )
        {
          case 8:
            v108 = (unsigned int)*(__int16 *)(v2 + 292);
            *(_QWORD *)(v2 + 328) = *(_QWORD *)(v2 + 576);
            *(_DWORD *)(v2 + 336) = *(_DWORD *)(v2 + 568);
            *(_QWORD *)(v2 + 360) = 0;
            *(_QWORD *)(v2 + 368) = 0;
            *(_QWORD *)(v2 + 376) = 0;
            if ( (unsigned int)deflateInit2_(v2 + 312, v108, v88, 4294967281LL) )
            {
              archive_set_error(a1, 12, "Can't init deflate compressor");
              return 4294967266LL;
            }
            break;
          case 12:
            memset_0((void *)(v2 + 312), 0, 0x50u);
            v107 = (unsigned int)*(__int16 *)(v2 + 292);
            *(_QWORD *)(v2 + 336) = *(_QWORD *)(v2 + 576);
            *(_DWORD *)(v2 + 344) = *(_DWORD *)(v2 + 568);
            if ( (unsigned int)BZ2_bzCompressInit(v2 + 312, v107, 0, 0) )
            {
              archive_set_error(a1, 12, "Can't init bzip2 compressor");
              return 4294967266LL;
            }
            break;
          case 14:
            v105 = *(__int16 *)(v2 + 292);
            v119 = -1;
            v117 = 0x4000000000000001LL;
            v118 = v2 + 320;
            v120 = 0;
            memset_0((void *)(v2 + 432), 0, 0x88u);
            v106 = v105;
            LODWORD(v106) = v105 | 0x80000000;
            if ( v105 != 9 )
              v106 = v105;
            lzma_lzma_preset(v2 + 320, v106);
            *(_BYTE *)(v2 + 312) = 1;
            if ( (unsigned int)lzma_raw_encoder(v2 + 432, &v117) )
            {
              archive_set_error(a1, 12, "Can't init lzma compressor");
              return 4294967266LL;
            }
LABEL_208:
            *(_QWORD *)(v2 + 456) = *(_QWORD *)(v2 + 576);
            *(_QWORD *)(v2 + 464) = *(unsigned int *)(v2 + 568);
            return v113;
          case 93:
            v94 = *(__int16 *)(v2 + 292);
            if ( *(_WORD *)(v2 + 292) == 1 )
            {
              v95 = ZSTD_minCLevel();
            }
            else
            {
              v98 = ZSTD_maxCLevel();
              v97 = 8;
              v100 = ((v94 - 1) * v98) >> 31;
              v99 = (v94 - 1) * v98;
              v96 = v100;
              v101 = __SPAIR64__(v100, v99) % 8;
              v95 = __SPAIR64__(v100, v99) / 8;
              LODWORD(v96) = v101;
            }
            v102 = v95;
            CStream = ZSTD_createCStream(v97, v96);
            *(_QWORD *)(v2 + 312) = CStream;
            inited = ZSTD_initCStream(CStream, v102);
            if ( (unsigned int)ZSTD_isError(inited) )
            {
              archive_set_error(a1, 12, "Can't init zstd compressor");
              return 4294967266LL;
            }
            ZSTD_CCtx_setParameter(*(_QWORD *)(v2 + 312), 400, (unsigned int)*(__int16 *)(v2 + 304));
            *(_QWORD *)(v2 + 344) = *(_QWORD *)(v2 + 576);
            *(_QWORD *)(v2 + 352) = *(_QWORD *)(v2 + 568);
            *(_QWORD *)(v2 + 360) = 0;
            break;
          case 95:
            v91 = *(__int16 *)(v2 + 292) | 0x80000000;
            if ( *(_WORD *)(v2 + 292) != 9 )
              v91 = *(__int16 *)(v2 + 292);
            memset_0((void *)(v2 + 432), 0, 0x88u);
            v92 = *(__int16 *)(v2 + 304);
            if ( *(_WORD *)(v2 + 304) == 1 )
            {
              v117 = 33;
              v118 = v2 + 320;
              v119 = -1;
              v120 = 0;
              lzma_lzma_preset(v2 + 320, v91);
              v93 = lzma_stream_encoder(v2 + 432, &v117, 0);
            }
            else
            {
              v121[0] = 0;
              memset(v132, 0, sizeof(v132));
              v121[1] = v92;
              v126 = 0;
              v122 = 0;
              v127 = 0;
              v123 = 0;
              v124 = v91;
              v125 = 0;
              v128 = 0;
              v129 = 0;
              v130 = 0;
              v131 = 0;
              v93 = lzma_stream_encoder_mt(v2 + 432, v121);
            }
            if ( v93 )
            {
              archive_set_error(a1, 12, "Can't init xz compressor");
              return 4294967266LL;
            }
            goto LABEL_208;
        }
        return v113;
      case 12:
        v38 = 46;
        goto LABEL_130;
      case 14:
        v42 |= 2u;
        *(_DWORD *)(v2 + 68) = v42;
        break;
      case 93:
      case 95:
        break;
      default:
        if ( *(_WORD *)(v2 + 292) == 1 || *(_WORD *)(v2 + 292) == 2 )
        {
          v42 |= 6u;
        }
        else if ( *(_WORD *)(v2 + 292) == 3 || *(_WORD *)(v2 + 292) == 4 )
        {
          v42 |= 4u;
        }
        else
        {
          if ( (unsigned int)(*(__int16 *)(v2 + 292) - 8) > 1 )
            goto LABEL_124;
          v42 |= 2u;
        }
        *(_DWORD *)(v2 + 68) = v42;
LABEL_124:
        if ( v43 )
          v38 = 20;
        goto LABEL_130;
    }
    v38 = 63;
    goto LABEL_130;
  }
  archive_set_error(a1, 0xFFFFFFFFLL, "Files > 4GB require Zip64 extensions");
  return 4294967271LL;
}

```

## disassembly

```asm
0x180114c90  mov     rax, rsp
0x180114c93  mov     [rax+18h], rbx
0x180114c97  push    rbp
0x180114c98  push    rsi
0x180114c99  push    rdi
0x180114c9a  push    r12
0x180114c9c  push    r13
0x180114c9e  push    r14
0x180114ca0  push    r15
0x180114ca2  lea     rbp, [rax-128h]
0x180114ca9  sub     rsp, 1F0h
0x180114cb0  movaps  xmmword ptr [rax-48h], xmm6
0x180114cb4  mov     rax, cs:__security_cookie
0x180114cbb  xor     rax, rsp
0x180114cbe  mov     [rbp+120h+var_50], rax
0x180114cc5  mov     r15, [rcx+0F8h]
0x180114ccc  mov     r14, rdx
0x180114ccf  mov     [rsp+220h+var_1B8], rdx
0x180114cd4  mov     r13, rcx
0x180114cd7  xor     edx, edx
0x180114cd9  mov     rsi, [r15+110h]
0x180114ce0  lea     r12d, [rdx+1]
0x180114ce4  test    rsi, rsi
0x180114ce7  jnz     short loc_180114D0D
0x180114ce9  lea     rbx, [r15+118h]
0x180114cf0  cmp     [r15+128h], edx
0x180114cf7  jnz     short loc_180114D0A
0x180114cf9  call    archive_string_default_conversion_for_write
0x180114cfe  mov     [rbx], rax
0x180114d01  xor     edx, edx
0x180114d03  mov     [r15+128h], r12d
0x180114d0a  mov     rsi, [rbx]
0x180114d0d  mov     ecx, 4000h
0x180114d12  mov     edi, 0F000h
0x180114d17  and     di, [r14+408h]
0x180114d1f  movzx   eax, di
0x180114d22  sub     ax, cx
0x180114d25  mov     ecx, 9FFFh
0x180114d2a  test    cx, ax
0x180114d2d  jnz     loc_180115BEB
0x180114d33  mov     eax, 6000h
0x180114d38  cmp     di, ax
0x180114d3b  jz      loc_180115BEB
0x180114d41  test    [r15+134h], r12b
0x180114d48  mov     eax, 0FFFFFFFFh
0x180114d4d  lea     r12, [r14+0A0h]
0x180114d54  mov     [rsp+220h+var_1C8], r12
0x180114d59  jz      short loc_180114D91
0x180114d5b  test    byte ptr [r12], 40h
0x180114d60  jz      short loc_180114D7F
0x180114d62  cmp     [r14+70h], rax
0x180114d66  jle     short loc_180114D7F
0x180114d68  lea     r8, aFiles4gbRequir; "Files > 4GB require Zip64 extensions"
0x180114d6f  or      edx, 0FFFFFFFFh
0x180114d72  mov     rcx, r13
0x180114d75  call    archive_set_error
0x180114d7a  jmp     loc_180115BFD
0x180114d7f  cmp     [r15+108h], rax
0x180114d86  jle     short loc_180114D91
0x180114d88  lea     r8, aArchives4gbReq; "Archives > 4GB require Zip64 extensions"
0x180114d8f  jmp     short loc_180114D6F
0x180114d91  mov     eax, 8000h
0x180114d96  mov     rbx, r12
0x180114d99  cmp     di, ax
0x180114d9c  jz      short loc_180114DB0
0x180114d9e  lea     rbx, [r14+0A0h]
0x180114da5  mov     [r14+10h], edx
0x180114da9  or      dword ptr [rbx], 40h
0x180114dac  mov     [r14+70h], rdx
0x180114db0  mov     rax, [r15+108h]
0x180114db7  xor     r8d, r8d
0x180114dba  mov     [r15], rax
0x180114dbd  xor     ecx, ecx
0x180114dbf  mov     rax, 7FFFFFFFFFFFFFFFh
0x180114dc9  mov     [r15+8], rdx
0x180114dcd  mov     [r15+28h], rax
0x180114dd1  mov     rax, [r15+0E0h]
0x180114dd8  mov     [r15+10h], rdx
0x180114ddc  mov     [r15+18h], rdx
0x180114de0  mov     [r15+20h], rdx
0x180114de4  mov     [r15+44h], edx
0x180114de8  xor     edx, edx
0x180114dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114def  mov     rcx, [r15+30h]
0x180114df3  mov     [r15+38h], eax
0x180114df7  mov     dword ptr [r15+40h], 0
0x180114dff  call    archive_entry_free
0x180114e04  xor     eax, eax
0x180114e06  mov     [r15+30h], rax
0x180114e0a  cmp     [r15+0A0h], al
0x180114e11  jz      short loc_180114E21
0x180114e13  lea     rcx, [r15+60h]; void *
0x180114e17  call    aes_ctr_release
0x180114e1c  xor     eax, eax
0x180114e1e  mov     rbx, r12
0x180114e21  cmp     [r15+0C8h], al
0x180114e28  jz      short loc_180114E3A
0x180114e2a  lea     rcx, [r15+0A8h]
0x180114e31  call    __hmac_sha1_cleanup
0x180114e36  xor     eax, eax
0x180114e38  jmp     short loc_180114E42
0x180114e3a  mov     r12, rbx
0x180114e3d  mov     [rsp+220h+var_1C8], rbx
0x180114e42  mov     ecx, 8000h
0x180114e47  mov     [r15+0C8h], al
0x180114e4e  mov     [r15+0A0h], al
0x180114e55  mov     [r15+58h], al
0x180114e59  cmp     di, cx
0x180114e5c  jnz     short loc_180114E8C
0x180114e5e  test    byte ptr [r12], 40h
0x180114e63  jz      short loc_180114E6B
0x180114e65  cmp     [r14+70h], rax
0x180114e69  jle     short loc_180114E8C
0x180114e6b  mov     edx, [r15+12Ch]
0x180114e72  mov     ecx, edx
0x180114e74  sub     ecx, 1
0x180114e77  jz      short loc_180114E83
0x180114e79  sub     ecx, 1
0x180114e7c  jz      short loc_180114E83
0x180114e7e  cmp     ecx, 1
0x180114e81  jnz     short loc_180114E8C
0x180114e83  or      dword ptr [r15+44h], 1
0x180114e88  mov     [r15+40h], edx
0x180114e8c  mov     rcx, r14
0x180114e8f  call    __la_win_entry_in_posix_pathseparator
0x180114e94  mov     [r15+30h], rax
0x180114e98  cmp     rax, r14
0x180114e9b  jnz     short loc_180114EA9
0x180114e9d  mov     rcx, r14
0x180114ea0  call    archive_entry_clone
0x180114ea5  mov     [r15+30h], rax
0x180114ea9  xor     r14d, r14d
0x180114eac  test    rax, rax
0x180114eaf  jnz     short loc_180114ECD
0x180114eb1  lea     r8, aCanTAllocateZi; "Can't allocate zip header data"
0x180114eb8  lea     edx, [rax+0Ch]
0x180114ebb  mov     rcx, r13
0x180114ebe  call    archive_set_error
0x180114ec3  mov     eax, 0FFFFFFE2h
0x180114ec8  jmp     loc_180115C02
0x180114ecd  mov     dword ptr [rsp+220h+var_1D0+4], r14d
0x180114ed2  mov     ebx, 0A000h
0x180114ed7  mov     r12d, 0Ch
0x180114edd  test    rsi, rsi
0x180114ee0  jz      loc_180114FCD
0x180114ee6  mov     rcx, [rax]
0x180114ee9  lea     rdx, [rax+1E8h]
0x180114ef0  lea     r9, [rsp+220h+var_1D8]
0x180114ef5  mov     [rsp+220h+var_1E0], r14
0x180114efa  lea     r8, [rsp+220h+var_1E0]
0x180114eff  mov     [rsp+220h+var_1D8], r14
0x180114f04  mov     [rsp+220h+var_200], rsi
0x180114f09  call    archive_mstring_get_mbs_l
0x180114f0e  test    eax, eax
0x180114f10  jz      short loc_180114F66
0x180114f12  call    cs:__imp__o__errno
0x180114f18  cmp     [rax], r12d
0x180114f1b  jnz     short loc_180114F29
0x180114f1d  lea     r8, aCanTAllocateMe_24; "Can't allocate memory for Pathname"
0x180114f24  mov     edx, r12d
0x180114f27  jmp     short loc_180114EBB
0x180114f29  mov     rcx, rsi
0x180114f2c  call    archive_string_conversion_charset_name
0x180114f31  mov     rcx, [r15+30h]
0x180114f35  mov     rbx, rax
0x180114f38  call    archive_entry_pathname
0x180114f3d  mov     r9, rax
0x180114f40  mov     [rsp+220h+var_200], rbx
0x180114f45  lea     r8, aCanTTranslateP_1; "Can't translate Pathname '%s' to %s"
0x180114f4c  mov     edx, 2Ah ; '*'
0x180114f51  mov     rcx, r13
0x180114f54  call    archive_set_error
0x180114f59  mov     dword ptr [rsp+220h+var_1D0+4], 0FFFFFFECh
0x180114f61  mov     ebx, 0A000h
0x180114f66  cmp     [rsp+220h+var_1D8], r14
0x180114f6b  jbe     short loc_180114F82
0x180114f6d  mov     rcx, [r15+30h]
0x180114f71  mov     rdx, [rsp+220h+var_1E0]
0x180114f76  add     rcx, 1E8h
0x180114f7d  call    archive_mstring_copy_mbs
0x180114f82  cmp     di, bx
0x180114f85  jnz     short loc_180114FCD
0x180114f87  mov     rcx, [r15+30h]
0x180114f8b  lea     r8, [rsp+220h+var_1D8]
0x180114f90  mov     r9, rsi
0x180114f93  lea     rdx, [rsp+220h+var_1E0]
0x180114f98  call    _archive_entry_symlink_l
0x180114f9d  test    eax, eax
0x180114f9f  jz      short loc_180114FB8
0x180114fa1  call    cs:__imp__o__errno
0x180114fa7  cmp     [rax], r12d
0x180114faa  jnz     short loc_180114FCD
0x180114fac  lea     r8, aCanTAllocateMe_0; "Can't allocate memory  for Symlink"
0x180114fb3  jmp     loc_180114F24
0x180114fb8  cmp     [rsp+220h+var_1D8], r14
0x180114fbd  jbe     short loc_180114FCD
0x180114fbf  mov     rdx, [rsp+220h+var_1E0]
0x180114fc4  mov     rcx, [r15+30h]
0x180114fc8  call    archive_entry_copy_symlink
0x180114fcd  mov     rcx, [r15+30h]
0x180114fd1  call    archive_entry_pathname
0x180114fd6  mov     cl, [rax]
0x180114fd8  test    cl, cl
0x180114fda  jz      short loc_18011500E
0x180114fdc  inc     rax
0x180114fdf  cmp     cl, 7Fh
0x180114fe2  jbe     short loc_180114FD6
0x180114fe4  mov     rcx, [r15+110h]
0x180114feb  test    rcx, rcx
0x180114fee  jz      short loc_18011500E
0x180114ff0  call    archive_string_conversion_charset_name
0x180114ff5  mov     rcx, rax; Str1
0x180114ff8  lea     rdx, Str2; "UTF-8"
0x180114fff  call    strcmp_0
0x180115004  test    eax, eax
0x180115006  jnz     short loc_18011500E
0x180115008  bts     dword ptr [r15+44h], 0Bh
0x18011500e  mov     rcx, [r15+30h]
0x180115012  movzx   ebx, word ptr [rcx+408h]
0x180115019  call    archive_entry_pathname
0x18011501e  test    rax, rax
0x180115021  jnz     short loc_18011502A
0x180115023  mov     [rsp+220h+var_1E0], r14
0x180115028  jmp     short loc_180115062
0x18011502a  mov     ecx, 0F000h
0x18011502f  and     bx, cx
0x180115032  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180115036  inc     rcx
0x180115039  cmp     [rax+rcx], r14b
0x18011503d  jnz     short loc_180115036
0x18011503f  mov     edx, 4000h
0x180115044  mov     [rsp+220h+var_1E0], rcx
0x180115049  cmp     bx, dx
0x18011504c  jnz     short loc_180115062
0x18011504e  cmp     [rax], r14b
0x180115051  jz      short loc_18011505A
0x180115053  cmp     byte ptr [rcx+rax-1], 2Fh ; '/'
0x180115058  jz      short loc_180115062
0x18011505a  inc     rcx
0x18011505d  mov     [rsp+220h+var_1E0], rcx
0x180115062  mov     eax, 0A000h
0x180115067  mov     r10d, 8
0x18011506d  cmp     di, ax
0x180115070  jnz     short loc_1801150CB
0x180115072  mov     rcx, [r15+30h]
0x180115076  call    archive_entry_symlink
0x18011507b  mov     [rsp+220h+var_1B0], rax
0x180115080  mov     rcx, rax
0x180115083  test    rax, rax
0x180115086  jz      short loc_180115097
0x180115088  or      rax, 0FFFFFFFFFFFFFFFFh
0x18011508c  inc     rax
0x18011508f  cmp     [rcx+rax], r14b
0x180115093  jnz     short loc_18011508C
0x180115095  jmp     short loc_18011509A
0x180115097  mov     rax, r14
0x18011509a  mov     [rsp+220h+var_1C0], rax
0x18011509f  mov     r8, rax
0x1801150a2  mov     [r15+28h], rax
0x1801150a6  mov     rdx, rcx
0x1801150a9  mov     ecx, [r15+38h]
0x1801150ad  mov     [r15+8], rax
0x1801150b1  mov     [r15+10h], rax
0x1801150b5  mov     rax, [r15+0E0h]
0x1801150bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801150c1  mov     [r15+38h], eax
0x1801150c5  lea     rsi, [r15+3Ch]
0x1801150c9  jmp     short loc_1801150E7
0x1801150cb  mov     eax, 8000h
0x1801150d0  mov     [rsp+220h+var_1B0], r14
0x1801150d5  mov     [rsp+220h+var_1C0], r14
0x1801150da  lea     rsi, [r15+3Ch]
0x1801150de  cmp     di, ax
0x1801150e1  jz      short loc_1801150F5
0x1801150e3  mov     [r15+28h], r14
0x1801150e7  mov     [rsi], r14d
0x1801150ea  mov     r14d, 14h
0x1801150f0  jmp     loc_1801152EE
0x1801150f5  mov     rax, [r15+30h]
0x1801150f9  test    byte ptr [rax+0A0h], 40h
0x180115100  jz      loc_18011522C
0x180115106  mov     rax, [rax+70h]
0x18011510a  mov     r9, r14
0x18011510d  mov     ecx, [r15+120h]
0x180115114  mov     r14d, 14h
0x18011511a  mov     [r15+28h], rax
0x18011511e  mov     [rsi], ecx
0x180115120  cmp     ecx, 0FFFFFFFFh
0x180115123  jnz     short loc_180115131
0x180115125  mov     [rsi], r10d
0x180115128  mov     ecx, r10d
0x18011512b  mov     [r15+10h], rax
0x18011512f  jmp     short loc_18011514D
0x180115131  mov     [r15+10h], rax
0x180115135  test    ecx, ecx
0x180115137  jz      short loc_18011519E
0x180115139  cmp     ecx, r12d
0x18011513c  jz      short loc_180115197
0x18011513e  cmp     ecx, 0Eh
0x180115141  jz      short loc_18011518B
  ... truncated ...
```
