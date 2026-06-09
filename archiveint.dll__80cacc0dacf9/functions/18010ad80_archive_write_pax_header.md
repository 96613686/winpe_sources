# archive_write_pax_header

- ea: `0x18010ad80`
- end: `0x18010c1ec`
- name: `archive_write_pax_header`
- size: `5228`
- prototype: ``
- caller_count: `1`
- callee_count: `56`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x18010ad80`

## callees

- `0x180006c00`
- `0x180007c80`
- `0x18000a2d0`
- `0x18000b4d0`
- `0x18000e8d4`
- `0x18000e920`
- `0x18000e9a0`
- `0x18000ea00`
- `0x180014ab4`
- `0x180014fc0`
- `0x1800aba6c`
- `0x1800b1300`
- `0x1800b1830`
- `0x1800b1a60`
- `0x1800b1b60`
- `0x1800b1bc0`
- `0x1800b1ef0`
- `0x1800b1f40`
- `0x1800b20d0`
- `0x1800b2100`
- `0x1800b23b0`
- `0x1800b28d0`
- `0x1800b3580`
- `0x1800b3660`
- `0x1800b36b0`
- `0x1800b39d0`
- `0x1800ece24`
- `0x1800ecf00`
- `0x1800ed464`
- `0x1800ed47c`
- `0x1800ed5e0`
- `0x1800ed6c0`
- `0x1800ee548`
- `0x1800ef2d4`
- `0x1800efbb4`
- `0x1800f8774`
- `0x18010a844`
- `0x18010a934`
- `0x18010a950`
- `0x18010aa40`
- `0x18010aa94`
- `0x18010ab60`
- `0x18010ac50`
- `0x18010ad80`
- `0x18010c344`
- `0x18010c8d8`
- `0x18010c9cc`
- `0x18010cc20`
- `0x18010cc84`
- `0x18010cce8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010afe0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010b0f1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010b1de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010b3ac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010c1ac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010afe0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010b0f1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010b1de`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010b3ac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010c1ac`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18010b147`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18010b147`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18010b7bf`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18010b7d7`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18010b7bf`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18010b7d7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18010b19b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18010b19b`

## string_xrefs

- `0x18010b85c`: `linkpath`
- `0x18010b4d0`: `Can't translate pathname '%s' to %s`
- `0x18010aeb9`: `Can't translate linkname '%s' to %s`
- `0x18010b65c`: `Can't translate linkname '%s' to %s`
- `0x18010ae0b`: `Can't record entry in tar file without pathname`
- `0x18010b87a`: `././@LongHardLink`
- `0x18010b883`: `././@LongSymLink`
- `0x18010be06`: `LIBARCHIVE.symlinktype`
- `0x18010c085`: `archive_write_pax_header: 'x' header failed?!  This can't happen.\n`

## pseudocode

```c
__int64 __fastcall archive_write_pax_header(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 result; // rax
  __int64 v6; // rbx
  __int64 v7; // rax
  int entry_hardlink; // eax
  unsigned int v9; // r15d
  int v10; // r12d
  const char *v11; // rax
  char *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // r8
  __int16 v15; // ax
  __int64 v16; // rax
  size_t v17; // rdi
  char *v18; // rcx
  _BYTE *v19; // rax
  size_t v20; // rdi
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rdi
  const char *v24; // rcx
  __int64 v25; // rax
  char *v26; // rax
  char *v27; // rcx
  char *v28; // rax
  char *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int16 v32; // cx
  __int16 v33; // ax
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // edi
  __int64 v41; // rdi
  const char *v42; // rax
  __int64 v43; // r8
  __int64 v44; // rdx
  int entry_pathname; // eax
  const char *v46; // rax
  int entry_uname; // eax
  const char *v48; // rax
  int entry_gname; // eax
  const char *v50; // rax
  int entry_symlink; // eax
  const char *v52; // rax
  char *v53; // r8
  char *v54; // r9
  BOOL v55; // ebx
  char *v56; // rax
  __int64 v57; // rax
  char *v58; // rdx
  char *v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // r9
  const char *v64; // rdx
  const char *v65; // rdx
  int v66; // eax
  _BYTE *v67; // rax
  __int64 v68; // rdx
  __int64 v69; // r8
  int v70; // eax
  int v71; // eax
  __int64 v72; // r8
  __int64 v73; // r8
  __int64 v74; // r8
  unsigned __int64 v75; // r8
  _BYTE *v76; // rax
  __int64 v77; // r9
  __int16 v78; // bx
  __int64 v79; // r9
  __int64 v80; // rax
  char *i; // r8
  char *v82; // rax
  unsigned __int64 v83; // rbx
  int v84; // eax
  __int64 v85; // r9
  const char *v86; // r8
  char *v87; // rax
  __int64 v88; // rcx
  __int64 v89; // rbx
  __int64 v90; // rax
  __int64 v91; // rcx
  __int64 v92; // rdx
  __int64 v93; // r8
  __int64 v94; // rbx
  __int64 v95; // rax
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // rax
  int v99; // edx
  __int64 v100; // rcx
  int v101; // edx
  __int64 v102; // rax
  __int64 v103; // rcx
  int v104; // edx
  __int16 v105; // ax
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rdx
  __int64 v109; // r8
  __int64 v110; // rdx
  __int64 v111; // rcx
  int v112; // eax
  __int64 v113; // [rsp+30h] [rbp-D0h] BYREF
  size_t Count; // [rsp+38h] [rbp-C8h] BYREF
  int v115; // [rsp+40h] [rbp-C0h]
  char *Str; // [rsp+48h] [rbp-B8h]
  char *v117; // [rsp+50h] [rbp-B0h] BYREF
  char *v118[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v119; // [rsp+68h] [rbp-98h]
  char *v120; // [rsp+70h] [rbp-90h] BYREF
  const char *v121; // [rsp+78h] [rbp-88h] BYREF
  char *Source; // [rsp+80h] [rbp-80h] BYREF
  const char *v123; // [rsp+88h] [rbp-78h]
  void *Block; // [rsp+90h] [rbp-70h] BYREF
  __int64 v125; // [rsp+98h] [rbp-68h]
  __int64 v126; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v127; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v128; // [rsp+B0h] [rbp-50h] BYREF
  const char *v129; // [rsp+B8h] [rbp-48h] BYREF
  const char *v130; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v131; // [rsp+C8h] [rbp-38h]
  char v132[256]; // [rsp+D0h] [rbp-30h] BYREF
  char Destination[256]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v134[256]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v135[512]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v136[512]; // [rsp+5D0h] [rbp+4D0h] BYREF

  v2 = *(_QWORD *)(a1 + 248);
  v117 = 0;
  Source = 0;
  v130 = 0;
  v129 = 0;
  v121 = 0;
  Count = 0;
  v127 = 0;
  v128 = 0;
  *(_OWORD *)v118 = 0;
  v119 = 0;
  if ( !archive_entry_pathname_w(a2) && !archive_entry_pathname(a2) )
  {
    archive_set_error(a1, 0xFFFFFFFFLL, "Can't record entry in tar file without pathname");
    return 4294967271LL;
  }
  if ( *(_DWORD *)(v2 + 120) )
  {
    v6 = 0;
  }
  else
  {
    v6 = *(_QWORD *)(v2 + 112);
    if ( !v6 )
    {
      v7 = archive_string_conversion_to_charset(a1, "UTF-8", 1);
      *(_QWORD *)(v2 + 112) = v7;
      v6 = v7;
      if ( !v7 )
        return 4294967271LL;
    }
  }
  entry_hardlink = get_entry_hardlink(a1, a2, (unsigned int)&v117, (unsigned int)&v121, v6);
  v9 = -30;
  if ( entry_hardlink == -30 )
    return v9;
  v10 = 0;
  if ( entry_hardlink )
  {
    if ( (unsigned int)get_entry_hardlink(a1, a2, (unsigned int)&v117, (unsigned int)&v121, 0) == -30 )
      return v9;
    v11 = (const char *)archive_string_conversion_charset_name(v6);
    v12 = v117;
    archive_set_error(a1, 42, "Can't translate linkname '%s' to %s", v117, v11);
    v6 = 0;
    v10 = -20;
  }
  else
  {
    v12 = v117;
  }
  v13 = 0x8000;
  v14 = 4096;
  if ( !v12 )
  {
    v15 = *(_WORD *)(a2 + 1032) & 0xF000;
    if ( v15 != 4096 && v15 != 0x2000 )
    {
      if ( v15 != 0x4000 )
      {
        if ( v15 != 24576 && v15 != (__int16)0x8000 && v15 != -24576 )
        {
          _archive_write_entry_filetype_unsupported(a1, a2, "pax");
          return 4294967271LL;
        }
        goto LABEL_45;
      }
      v16 = archive_entry_pathname_w(a2);
      v113 = v16;
      if ( !v16 )
        goto LABEL_32;
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)(v16 + 2 * v17) );
      if ( *(_WORD *)(v16 + 2 * v17 - 2) == 47 )
      {
LABEL_32:
        v19 = (_BYTE *)archive_entry_pathname(a2);
        v113 = (__int64)v19;
        if ( !v19 )
          goto LABEL_45;
        if ( !*v19 )
          goto LABEL_45;
        v20 = -1;
        do
          ++v20;
        while ( v19[v20] );
        if ( v19[v20 - 1] == 47 )
          goto LABEL_45;
        Count = v20;
        Block = 0;
        v125 = 0;
        v126 = 0;
        if ( !archive_string_ensure(&Block, v20 + 2) )
        {
LABEL_27:
          archive_set_error(a1, 12, "Can't allocate pax data");
          v18 = (char *)Block;
          v125 = 0;
          v126 = 0;
LABEL_28:
          free(v18);
          return v9;
        }
        v21 = v113;
        v22 = -1;
        do
          ++v22;
        while ( *(_BYTE *)(v113 + v22) );
        if ( *(_BYTE *)(v22 + v113 - 1) == 92 )
        {
          Count = v20 - 1;
        }
        else
        {
          v125 = 0;
          archive_strncat(&Block, v113, v20);
        }
        LOBYTE(v21) = 47;
        archive_strappend_char(&Block, v21);
        archive_mstring_copy_mbs(a2 + 488, Block);
      }
      else
      {
        Block = 0;
        v125 = 0;
        v126 = 0;
        Count = v17;
        if ( !archive_string_ensure(&Block, 2 * v17 + 4) )
          goto LABEL_27;
        if ( *(_WORD *)(v113 + 2 * v17 - 2) == 92 )
          Count = v17 - 1;
        v125 = 0;
        archive_wstrncat(&Block, v113);
        archive_wstrappend_wchar(&Block, 47);
        archive_mstring_copy_wcs(a2 + 488, Block);
      }
      v125 = 0;
      v126 = 0;
      free(Block);
    }
  }
LABEL_45:
  v131 = *(_QWORD *)(a2 + 808);
  if ( v131 )
  {
    v113 = *(_QWORD *)(a2 + 816);
    v23 = archive_entry_new2(a1, v13, v14);
    v24 = (const char *)archive_entry_pathname(a2);
    v120 = (char *)v24;
    v25 = -1;
    do
      ++v25;
    while ( v24[v25] );
    v123 = (const char *)v25;
    v26 = (char *)malloc(v25 + 3);
    Str = v26;
    v27 = v26;
    if ( !v26 || !v23 )
    {
      archive_entry_free(v23);
      free(Str);
      return 4294967271LL;
    }
    strcpy(v26, v120);
    while ( 1 )
    {
      v28 = strrchr(v27, 47);
      if ( !v28 )
      {
        memmove_0(Str + 2, Str, (size_t)(v123 + 1));
        v29 = Str;
        *(_WORD *)Str = 24366;
        goto LABEL_55;
      }
      if ( v28[1] )
        break;
      *v28 = 0;
      v27 = Str;
    }
    v42 = v28 + 1;
    v120 = (char *)v42;
    v43 = -1;
    do
      ++v43;
    while ( v42[v43] );
    memmove_0((void *)(v42 + 2), v42, v43 + 1);
    *(_WORD *)v120 = 24366;
    v29 = Str;
LABEL_55:
    archive_mstring_copy_mbs(v23 + 488, v29);
    free(Str);
    v30 = v113;
    *(_DWORD *)(v23 + 16) = 0;
    v31 = v30;
    if ( v30 < 0 )
      v31 = 0;
    *(_DWORD *)(v23 + 160) |= 0x440u;
    *(_QWORD *)(v23 + 112) = v31;
    *(_WORD *)(v23 + 1032) &= 0xFFFu;
    *(_WORD *)(v23 + 1032) |= 0x8000u;
    v32 = *(_WORD *)(v23 + 1032);
    v33 = *(_WORD *)(a2 + 1032) ^ v32;
    *(_DWORD *)(v23 + 160) |= 0x200u;
    *(_WORD *)(v23 + 1032) = v32 ^ v33 & 0xFFF;
    archive_entry_set_mtime(v23, *(_QWORD *)(a2 + 56), *(unsigned int *)(a2 + 64));
    v34 = *(_QWORD *)(a2 + 88);
    *(_DWORD *)(v23 + 16) = 0;
    v35 = 0;
    if ( v34 >= 0 )
      v35 = v34;
    *(_DWORD *)(v23 + 160) |= 0x1000u;
    *(_QWORD *)(v23 + 88) = v35;
    v36 = archive_entry_gname(a2);
    archive_mstring_copy_mbs(v23 + 280, v36);
    v37 = *(_QWORD *)(a2 + 120);
    *(_DWORD *)(v23 + 16) = 0;
    v38 = 0;
    if ( v37 >= 0 )
      v38 = v37;
    *(_DWORD *)(v23 + 160) |= 0x800u;
    *(_QWORD *)(v23 + 120) = v38;
    v39 = archive_entry_uname(a2);
    archive_mstring_copy_mbs(v23 + 592, v39);
    v115 = archive_write_pax_header(a1, v23);
    archive_entry_free(v23);
    result = (unsigned int)v115;
    if ( v115 < -20 )
      return result;
    if ( v115 < v10 )
      v10 = v115;
    v40 = v10;
    result = archive_write_pax_data(a1, v131, v113);
    v10 = result;
    if ( (int)result < -20 )
      return result;
    if ( (int)result >= v40 )
      v10 = v40;
    result = archive_write_pax_finish_entry(a1);
    if ( (int)result < -20 )
      return result;
    if ( (int)result < v10 )
      v10 = result;
  }
  v41 = _la_win_entry_in_posix_pathseparator(a2);
  if ( v41 == a2 )
    v41 = archive_entry_clone(a2);
  if ( !v41 )
  {
    archive_set_error(a1, 12, "Can't allocate pax data");
    return v9;
  }
  *(_QWORD *)(v2 + 48) = 0;
  *(_QWORD *)(v2 + 72) = 0;
  sparse_list_clear(v2);
  if ( v117 || (*(_WORD *)(v41 + 1032) & 0xF000) != 0x8000 )
  {
    v115 = 0;
  }
  else
  {
    *(_QWORD *)(v41 + 1120) = *(_QWORD *)(v41 + 1104);
    v115 = archive_entry_sparse_count(v41);
    if ( v115 )
    {
      v120 = 0;
      v113 = 0;
      v123 = 0;
      while ( !(unsigned int)archive_entry_sparse_next(v41, &v120, &v113) )
        v123 = &v120[v113];
      v44 = *(_QWORD *)(v41 + 112);
      if ( (__int64)v123 < v44 )
        archive_entry_sparse_add_entry(v41, v44, 0);
      *(_QWORD *)(v41 + 1120) = *(_QWORD *)(v41 + 1104);
      v115 = archive_entry_sparse_count(v41);
    }
  }
  entry_pathname = get_entry_pathname(a1, v41, (unsigned int)&Source, (unsigned int)&Count, v6);
  if ( entry_pathname == -30 )
    goto LABEL_272;
  if ( entry_pathname )
  {
    if ( (unsigned int)get_entry_pathname(a1, v41, (unsigned int)&Source, (unsigned int)&Count, 0) == -30 )
      goto LABEL_272;
    v46 = (const char *)archive_string_conversion_charset_name(v6);
    archive_set_error(a1, 42, "Can't translate pathname '%s' to %s", Source, v46);
    v6 = 0;
    v10 = -20;
  }
  entry_uname = get_entry_uname(a1, v41, (unsigned int)&v130, (unsigned int)&v127, v6);
  if ( entry_uname == -30 )
    goto LABEL_272;
  if ( entry_uname )
  {
    if ( (unsigned int)get_entry_uname(a1, v41, (unsigned int)&v130, (unsigned int)&v127, 0) == -30 )
      goto LABEL_272;
    v48 = (const char *)archive_string_conversion_charset_name(v6);
    archive_set_error(a1, 42, "Can't translate uname '%s' to %s", v130, v48);
    v6 = 0;
    v10 = -20;
  }
  entry_gname = get_entry_gname(a1, v41, (unsigned int)&v129, (unsigned int)&v128, v6);
  if ( entry_gname == -30 )
    goto LABEL_272;
  if ( entry_gname )
  {
    if ( (unsigned int)get_entry_gname(a1, v41, (unsigned int)&v129, (unsigned int)&v128, 0) == -30 )
      goto LABEL_272;
    v50 = (const char *)archive_string_conversion_charset_name(v6);
    archive_set_error(a1, 42, "Can't translate gname '%s' to %s", v129, v50);
    v10 = -20;
    v6 = 0;
  }
  Str = v117;
  v120 = v117;
  v123 = v121;
  v113 = (__int64)v121;
  if ( v117 )
    goto LABEL_106;
  entry_symlink = get_entry_symlink(a1, v41, (unsigned int)&v120, (unsigned int)&v113, v6);
  if ( entry_symlink == -30 )
    goto LABEL_272;
  if ( !entry_symlink )
  {
    Str = v120;
    v123 = (const char *)v113;
LABEL_106:
    if ( v6 )
      goto LABEL_114;
    goto LABEL_107;
  }
  if ( (unsigned int)get_entry_symlink(a1, v41, (unsigned int)&v120, (unsigned int)&v113, 0) == -30 )
    goto LABEL_272;
  v52 = (const char *)archive_string_conversion_charset_name(v6);
  Str = v120;
  archive_set_error(a1, 42, "Can't translate linkname '%s' to %s", v120, v52);
  v6 = 0;
  v123 = (const char *)v113;
  v10 = -20;
LABEL_107:
  if ( *(_DWORD *)(v2 + 120) )
    goto LABEL_114;
  if ( v117 )
  {
    if ( (unsigned int)get_entry_hardlink(a1, v41, (unsigned int)&v117, (unsigned int)&v121, 0) != -30 )
    {
      Str = v117;
      v123 = v121;
      goto LABEL_111;
    }
LABEL_272:
    archive_entry_free(v41);
    return v9;
  }
LABEL_111:
  if ( (unsigned int)get_entry_pathname(a1, v41, (unsigned int)&Source, (unsigned int)&Count, 0) == -30
    || (unsigned int)get_entry_uname(a1, v41, (unsigned int)&v130, (unsigned int)&v127, 0) == -30
    || (unsigned int)get_entry_gname(a1, v41, (unsigned int)&v129, (unsigned int)&v128, 0) == -30 )
  {
    goto LABEL_272;
  }
LABEL_114:
  v121 = 0;
  if ( !v6 )
    add_pax_attr_binary(v2 + 40, "hdrcharset", "BINARY", 6);
  if ( (unsigned int)has_non_ASCII(Source) )
    goto LABEL_123;
  v55 = (int)v54;
  if ( Count > 0x64 )
  {
    v56 = strchr(&v53[Count - 101], 47);
    v53 = Source;
    if ( v56 == Source )
    {
      v56 = strchr(v56 + 1, 47);
      v53 = Source;
    }
    v54 = 0;
    if ( !v56 || !v56[1] || v56 - v53 > 155 )
    {
LABEL_123:
      add_pax_attr(v2 + 40, "path", v53, v54);
      v57 = build_ustar_entry_name(Destination, Source, Count);
      archive_mstring_copy_mbs(v41 + 488, v57);
      v54 = 0;
      v55 = 1;
    }
  }
  v58 = Str;
  if ( Str && ((unsigned __int64)v123 > 0x64 || (unsigned int)has_non_ASCII(Str)) )
  {
    add_pax_attr(v2 + 40, "linkpath", v58, v54);
    if ( (unsigned __int64)v123 <= 0x64 )
    {
      v59 = Str;
      if ( v117 )
        goto LABEL_136;
    }
    else
    {
      if ( v117 )
      {
        v59 = "././@LongHardLink";
LABEL_136:
        archive_entry_set_hardlink(v41, v59);
        goto LABEL_132;
      }
      v59 = "././@LongSymLink";
    }
    archive_entry_copy_symlink(v41, v59);
LABEL_132:
    v55 = 1;
    v54 = 0;
  }
  v118[0] = v54;
  v119 = v54;
  v118[1] = v54;
  if ( archive_entry_pathname(v41) )
  {
    v60 = archive_entry_pathname(v41);
    v61 = -1;
    do
      ++v61;
    while ( *(_BYTE *)(v60 + v61) );
    v113 = v61;
  }
  else
  {
    v113 = 0;
  }
  v62 = archive_entry_pathname(v41);
  archive_strncat(v118, v62, v113);
  v63 = 1;
  if ( *(__int64 *)(v41 + 112) >= 0x200000000LL )
    v55 = 1;
  if ( *(_DWORD *)(v41 + 88) >= 0x40000u )
  {
    add_pax_attr_int(v2 + 40, "gid", *(_QWORD *)(v41 + 88));
    v63 = 1;
    v55 = 1;
  }
  v64 = v129;
  if ( v129 && (v128 > 0x1F || (unsigned int)has_non_ASCII(v129)) )
  {
    add_pax_attr(v2 + 40, "gname", v64, v63);
    v63 = 1;
    v55 = 1;
  }
  if ( *(_DWORD *)(v41 + 120) >= 0x40000u )
  {
    add_pax_attr_int(v2 + 40, "uid", *(_QWORD *)(v41 + 120));
    v63 = 1;
    v55 = 1;
  }
  v65 = v130;
  if ( v130 && (v127 > 0x1F || (unsigned int)has_non_ASCII(v130)) )
  {
    add_pax_attr(v2 + 40, "uname", v65, v63);
    LODWORD(v63) = 1;
    v55 = 1;
  }
  if ( (((*(_WORD *)(v41 + 1032) & 0xF000) - 0x2000) & 0xBFFF) != 0
    || ((LODWORD(Str) = archive_entry_rdevmajor(v41, 0x1FFFFFFFELL),
         v66 = archive_entry_rdevminor(v41),
         LODWORD(Count) = v66,
         (int)Str < 0x40000)
      ? (LODWORD(v63) = 1)
      : (add_pax_attr_int(v2 + 40, "SCHILY.devmajor", (int)Str), v66 = Count, LODWORD(v63) = 1, v55 = 1),
        v66 < 0x40000) )
  {
    if ( !v55 && *(_QWORD *)(v41 + 56) > 0x1FFFFFFFEuLL )
      v55 = v63;
  }
  else
  {
    add_pax_attr_int(v2 + 40, "SCHILY.devminor", v66);
    v55 = 1;
  }
  v67 = (_BYTE *)archive_entry_fflags_text(v41);
  v69 = 0;
  if ( !v55 )
  {
    if ( v67 && *v67 || (v70 = archive_entry_xattr_count(a2, v68, 0), v69 = 0, v70 > 0) )
    {
      v55 = 1;
    }
    else if ( v115 > 0 )
    {
      v55 = 1;
    }
  }
  v71 = *(_DWORD *)(a2 + 1080);
  LODWORD(Count) = v71;
  if ( !v55 )
  {
    if ( v71 )
      v55 = 1;
    else
      v55 = *(_DWORD *)(v41 + 1140) > 0;
  }
  if ( *(_DWORD *)(a1 + 16) != 196611 )
  {
    v72 = *(_QWORD *)(v41 + 40);
    if ( v72 || *(_DWORD *)(v41 + 48) )
      add_pax_attr_time(v2 + 40, "ctime", v72, *(unsigned int *)(v41 + 48));
    v73 = *(_QWORD *)(v41 + 24);
    if ( v73 || *(_DWORD *)(v41 + 32) )
      add_pax_attr_time(v2 + 40, "atime", v73, *(unsigned int *)(v41 + 32));
    if ( (*(_BYTE *)(v41 + 160) & 0x20) != 0 )
    {
      v74 = *(_QWORD *)(v41 + 72);
      if ( v74 < *(_QWORD *)(v41 + 56) )
        add_pax_attr_time(v2 + 40, "LIBARCHIVE.creationtime", v74, *(unsigned int *)(v41 + 80));
    }
    v69 = 0;
    if ( *(_DWORD *)(a1 + 16) != 196611 )
      goto LABEL_186;
  }
  if ( v55 )
  {
LABEL_186:
    v75 = *(_QWORD *)(v41 + 56);
    if ( v75 > 0x1FFFFFFFELL || *(_DWORD *)(v41 + 64) )
      add_pax_attr_time(v2 + 40, "mtime", v75, *(unsigned int *)(v41 + 64));
    v76 = (_BYTE *)archive_entry_fflags_text(v41);
    if ( v76 && *v76 )
      add_pax_attr(v2 + 40, "SCHILY.fflags", v76, v77);
    v78 = Count;
    if ( (Count & 0x3C00) != 0 )
    {
      v10 = add_pax_acl(a1, a2, v2, 25);
      if ( v10 == -30 )
        goto LABEL_194;
    }
    if ( (v78 & 0x100) != 0 )
    {
      v10 = add_pax_acl(a1, a2, v2, 265);
      if ( v10 == -30 )
        goto LABEL_194;
    }
    if ( (v78 & 0x200) != 0 )
    {
      v10 = add_pax_acl(a1, a2, v2, 521);
      if ( v10 == -30 )
        goto LABEL_194;
    }
    if ( v115 > 0 )
    {
      v127 = 0;
      v128 = 0;
      add_pax_attr_int(v2 + 40, "GNU.sparse.major", 1);
      add_pax_attr_int(v2 + 40, "GNU.sparse.minor", 0);
      add_pax_attr(v2 + 40, "GNU.sparse.name", Source, v79);
      add_pax_attr_int(v2 + 40, "GNU.sparse.realsize", *(_QWORD *)(v41 + 112));
      if ( v118[0] && *v118[0] )
      {
        v80 = -1;
        do
          ++v80;
        while ( v118[0][v80] );
        for ( i = &v118[0][v80]; ; --i )
        {
          v82 = i - 1;
          if ( (i <= v118[0] || *v82 != 47) && (i <= v118[0] + 1 || *v82 != 46 || *(i - 2) != 47) )
            break;
        }
        build_ustar_entry_name(v132, v118[0], i - v118[0]);
      }
      else
      {
        strcpy(v132, "GNUSparseFile/blank");
      }
      archive_mstring_copy_mbs(v41 + 488, v132);
      archive_string_sprintf(v2 + 64, "%d\n", v115);
      while ( !(unsigned int)archive_entry_sparse_next(v41, &v127, &v128) )
      {
        v83 = v128;
        archive_string_sprintf(v2 + 64, "%jd\n%jd\n", v127, v128);
        v121 += v83;
        if ( (unsigned int)sparse_list_add(v2, v127, v83) )
        {
          archive_set_error(a1, 12, "Can't allocate memory");
          goto LABEL_194;
        }
      }
    }
    if ( (unsigned int)archive_write_pax_header_xattrs(a1, v2, a2) == -30 )
      goto LABEL_194;
    v84 = *(_DWORD *)(v41 + 1140);
    if ( v84 == 1 )
    {
      v85 = 4;
      v86 = "file";
    }
    else
    {
      if ( v84 != 2 )
      {
LABEL_224:
        v69 = 0;
        goto LABEL_225;
      }
      v85 = 3;
      v86 = "dir";
    }
    add_pax_attr_binary(v2 + 40, "LIBARCHIVE.symlinktype", v86, v85);
    goto LABEL_224;
  }
LABEL_225:
  if ( (*(_WORD *)(v41 + 1032) & 0xF000) != 0x8000 )
  {
    *(_DWORD *)(v41 + 160) |= 0x40u;
    *(_DWORD *)(v41 + 16) = 0;
    *(_QWORD *)(v41 + 112) = 0;
  }
  v87 = v117;
  if ( *(_DWORD *)(a1 + 16) == 196610 )
    goto LABEL_230;
  if ( v117 )
  {
    *(_DWORD *)(v41 + 160) |= 0x40u;
    *(_DWORD *)(v41 + 16) = 0;
    *(_QWORD *)(v41 + 112) = 0;
LABEL_230:
    if ( v87 )
    {
      *(_DWORD *)(v41 + 160) |= 0x40u;
      *(_DWORD *)(v41 + 16) = 0;
      *(_QWORD *)(v41 + 112) = 0;
    }
  }
  v88 = *(_QWORD *)(v2 + 72);
  v89 = *(_QWORD *)(v41 + 112);
  v131 = v89;
  if ( v88 )
  {
    v90 = -(int)v88 & 0x1FF;
    *(_QWORD *)(v2 + 88) = v90;
    v91 = (__int64)&v121[v88 + v90];
    *(_DWORD *)(v41 + 16) = 0;
    if ( v91 >= 0 )
      v69 = v91;
    *(_DWORD *)(v41 + 160) |= 0x40u;
    *(_QWORD *)(v41 + 112) = v69;
  }
  else
  {
    v69 = v89;
  }
  if ( v69 >= 0x200000000LL )
    add_pax_attr_int(v2 + 40, "size", v69);
  if ( (unsigned int)_archive_write_format_header_ustar(a1, v136, v41, 0xFFFFFFFFLL, 0, 0) == -30 )
    goto LABEL_194;
  if ( *(_QWORD *)(v2 + 48) )
  {
    v94 = archive_entry_new2(a1, v92, v93);
    v95 = build_pax_attribute_name(v134);
    archive_mstring_copy_mbs(v94 + 488, v95);
    v96 = *(_QWORD *)(v2 + 48);
    *(_DWORD *)(v94 + 16) = 0;
    v97 = 0;
    if ( v96 >= 0 )
      v97 = v96;
    v98 = 0;
    *(_DWORD *)(v94 + 160) |= 0x40u;
    v99 = *(_DWORD *)(v94 + 160);
    *(_QWORD *)(v94 + 112) = v97;
    v100 = *(_QWORD *)(v41 + 120);
    if ( v100 >= 0x40000 )
      v100 = 0x3FFFF;
    if ( v100 >= 0 )
      v98 = v100;
    v101 = v99 | 0x800;
    *(_DWORD *)(v94 + 160) = v101;
    *(_QWORD *)(v94 + 120) = v98;
    v102 = 0;
    v103 = *(_QWORD *)(v41 + 88);
    if ( v103 >= 0x40000 )
      v103 = 0x3FFFF;
    if ( v103 >= 0 )
      v102 = v103;
    v104 = v101 | 0x1000;
    *(_DWORD *)(v94 + 160) = v104;
    *(_QWORD *)(v94 + 88) = v102;
    v105 = *(_WORD *)(v41 + 1032) & 0xF1FF;
    *(_DWORD *)(v94 + 160) = v104 | 0x600;
    *(_WORD *)(v94 + 1032) = v105;
    v106 = archive_entry_uname(v41);
    archive_mstring_copy_mbs(v94 + 592, v106);
    v107 = archive_entry_gname(v41);
    archive_mstring_copy_mbs(v94 + 280, v107);
    v108 = 0;
    if ( *(__int64 *)(v41 + 56) >= 0 )
      v108 = *(_QWORD *)(v41 + 56);
    if ( v108 > 0x1FFFFFFFFLL )
      v108 = 0x1FFFFFFFFLL;
    archive_entry_set_mtime(v94, v108, 0);
    archive_entry_set_atime(v94, 0, 0);
    archive_entry_set_ctime(v94, 0, 0);
    LODWORD(Count) = _archive_write_format_header_ustar(a1, v135, v94, 120, 1, 0);
    archive_entry_free(v94);
    if ( (int)Count < -20 )
    {
      archive_set_error(a1, 0xFFFFFFFFLL, "archive_write_pax_header: 'x' header failed?!  This can't happen.\n");
LABEL_194:
      archive_entry_free(v41);
      v118[1] = 0;
      v119 = 0;
      v18 = v118[0];
      goto LABEL_28;
    }
    if ( (int)Count < v10 )
      v10 = Count;
    if ( (unsigned int)_archive_write_filter(*(_QWORD *)(a1 + 232), v135, 512) )
    {
      sparse_list_clear(v2);
      *(_QWORD *)v2 = 0;
      *(_QWORD *)(v2 + 8) = 0;
      goto LABEL_194;
    }
    v109 = *(_QWORD *)(v2 + 48);
    v110 = *(_QWORD *)(v2 + 40);
    *(_QWORD *)v2 = v109;
    *(_QWORD *)(v2 + 8) = -(int)v109 & 0x1FF;
    if ( (unsigned int)_archive_write_filter(*(_QWORD *)(a1 + 232), v110, v109)
      || (unsigned int)_archive_write_nulls(a1, *(_QWORD *)(v2 + 8)) )
    {
      goto LABEL_194;
    }
    *(_QWORD *)(v2 + 8) = 0;
    *(_QWORD *)v2 = 0;
    v89 = v131;
  }
  v9 = _archive_write_filter(*(_QWORD *)(a1 + 232), v136, 512);
  if ( v9 )
    goto LABEL_194;
  *(_DWORD *)(a2 + 16) = 0;
  v111 = v89;
  if ( v89 < 0 )
    v111 = 0;
  *(_DWORD *)(a2 + 160) |= 0x40u;
  *(_QWORD *)(a2 + 112) = v111;
  if ( *(_QWORD *)(v2 + 96) || !v89 )
  {
    v112 = (int)v121;
  }
  else
  {
    sparse_list_add(v2, 0, v89);
    v112 = v89;
  }
  *(_QWORD *)(v2 + 8) = -v112 & 0x1FF;
  archive_entry_free(v41);
  v118[1] = 0;
  v119 = 0;
  free(v118[0]);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18010ad80  mov     [rsp-8+arg_10], rbx
0x18010ad85  push    rbp
0x18010ad86  push    rsi
0x18010ad87  push    rdi
0x18010ad88  push    r12
0x18010ad8a  push    r13
0x18010ad8c  push    r14
0x18010ad8e  push    r15
0x18010ad90  lea     rbp, [rsp-6E0h]
0x18010ad98  sub     rsp, 7E0h
0x18010ad9f  mov     rax, cs:__security_cookie
0x18010ada6  xor     rax, rsp
0x18010ada9  mov     [rbp+710h+var_40], rax
0x18010adb0  mov     rsi, [rcx+0F8h]
0x18010adb7  xor     edi, edi
0x18010adb9  mov     r14, rcx
0x18010adbc  mov     [rsp+810h+var_7C0], rdi
0x18010adc1  xorps   xmm0, xmm0
0x18010adc4  mov     [rbp+710h+Source], rdi
0x18010adc8  xor     eax, eax
0x18010adca  mov     [rbp+710h+var_750], rdi
0x18010adce  mov     rcx, rdx
0x18010add1  mov     [rbp+710h+var_758], rdi
0x18010add5  mov     [rsp+810h+var_798], rdi
0x18010adda  mov     r13, rdx
0x18010addd  mov     [rsp+810h+Count], rdi
0x18010ade2  mov     [rbp+710h+var_768], rdi
0x18010ade6  mov     [rbp+710h+var_760], rdi
0x18010adea  movups  xmmword ptr [rsp+810h+var_7B8], xmm0
0x18010adef  mov     [rsp+810h+var_7A8], rax
0x18010adf4  call    archive_entry_pathname_w
0x18010adf9  test    rax, rax
0x18010adfc  jnz     short loc_18010AE27
0x18010adfe  mov     rcx, r13
0x18010ae01  call    archive_entry_pathname
0x18010ae06  test    rax, rax
0x18010ae09  jnz     short loc_18010AE27
0x18010ae0b  lea     r8, aCanTRecordEntr; "Can't record entry in tar file without "...
0x18010ae12  or      edx, 0FFFFFFFFh
0x18010ae15  mov     rcx, r14
0x18010ae18  call    archive_set_error
0x18010ae1d  mov     eax, 0FFFFFFE7h
0x18010ae22  jmp     loc_18010C1C2
0x18010ae27  cmp     [rsi+78h], edi
0x18010ae2a  jz      short loc_18010AE31
0x18010ae2c  mov     rbx, rdi
0x18010ae2f  jmp     short loc_18010AE59
0x18010ae31  mov     rbx, [rsi+70h]
0x18010ae35  test    rbx, rbx
0x18010ae38  jnz     short loc_18010AE59
0x18010ae3a  lea     r8d, [rbx+1]
0x18010ae3e  mov     rcx, r14
0x18010ae41  lea     rdx, Str2; "UTF-8"
0x18010ae48  call    archive_string_conversion_to_charset
0x18010ae4d  mov     [rsi+70h], rax
0x18010ae51  mov     rbx, rax
0x18010ae54  test    rax, rax
0x18010ae57  jz      short loc_18010AE1D
0x18010ae59  lea     r9, [rsp+810h+var_798]
0x18010ae5e  mov     [rsp+810h+var_7F0], rbx
0x18010ae63  lea     r8, [rsp+810h+var_7C0]
0x18010ae68  mov     rdx, r13
0x18010ae6b  mov     rcx, r14
0x18010ae6e  call    get_entry_hardlink
0x18010ae73  mov     r15d, 0FFFFFFE2h
0x18010ae79  cmp     eax, r15d
0x18010ae7c  jz      loc_18010C1BF
0x18010ae82  mov     r12d, edi
0x18010ae85  test    eax, eax
0x18010ae87  jz      short loc_18010AEDC
0x18010ae89  lea     r9, [rsp+810h+var_798]
0x18010ae8e  mov     [rsp+810h+var_7F0], rdi
0x18010ae93  lea     r8, [rsp+810h+var_7C0]
0x18010ae98  mov     rdx, r13
0x18010ae9b  mov     rcx, r14
0x18010ae9e  call    get_entry_hardlink
0x18010aea3  cmp     eax, r15d
0x18010aea6  jz      loc_18010C1BF
0x18010aeac  mov     rcx, rbx
0x18010aeaf  call    archive_string_conversion_charset_name
0x18010aeb4  mov     rdi, [rsp+810h+var_7C0]
0x18010aeb9  lea     r8, aCanTTranslateL; "Can't translate linkname '%s' to %s"
0x18010aec0  mov     r9, rdi
0x18010aec3  mov     [rsp+810h+var_7F0], rax
0x18010aec8  lea     edx, [r15+48h]
0x18010aecc  mov     rcx, r14
0x18010aecf  call    archive_set_error
0x18010aed4  xor     ebx, ebx
0x18010aed6  lea     r12d, [r15+0Ah]
0x18010aeda  jmp     short loc_18010AEE1
0x18010aedc  mov     rdi, [rsp+810h+var_7C0]
0x18010aee1  mov     edx, 8000h
0x18010aee6  mov     ecx, 2000h
0x18010aeeb  mov     r8d, 1000h
0x18010aef1  test    rdi, rdi
0x18010aef4  jnz     loc_18010B0F7
0x18010aefa  mov     eax, 0F000h
0x18010aeff  and     ax, [r13+408h]
0x18010af07  cmp     ax, r8w
0x18010af0b  jz      loc_18010B0F7
0x18010af11  cmp     ax, cx
0x18010af14  jz      loc_18010B0F7
0x18010af1a  mov     ecx, 4000h
0x18010af1f  cmp     ax, cx
0x18010af22  jz      short loc_18010AF60
0x18010af24  mov     ecx, 6000h
0x18010af29  cmp     ax, cx
0x18010af2c  jz      loc_18010B0F7
0x18010af32  cmp     ax, dx
0x18010af35  jz      loc_18010B0F7
0x18010af3b  mov     ecx, 0A000h
0x18010af40  cmp     ax, cx
0x18010af43  jz      loc_18010B0F7
0x18010af49  lea     r8, aPax; "pax"
0x18010af50  mov     rdx, r13
0x18010af53  mov     rcx, r14
0x18010af56  call    __archive_write_entry_filetype_unsupported
0x18010af5b  jmp     loc_18010AE1D
0x18010af60  mov     rcx, r13
0x18010af63  call    archive_entry_pathname_w
0x18010af68  xor     ecx, ecx
0x18010af6a  mov     [rsp+810h+var_7E0], rax
0x18010af6f  test    rax, rax
0x18010af72  jz      loc_18010B033
0x18010af78  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18010af7c  inc     rdi
0x18010af7f  cmp     [rax+rdi*2], cx
0x18010af83  jnz     short loc_18010AF7C
0x18010af85  mov     edx, 2Fh ; '/'
0x18010af8a  cmp     [rax+rdi*2-2], dx
0x18010af8f  jz      loc_18010B033
0x18010af95  mov     [rbp+710h+Block], rcx
0x18010af99  lea     rdx, ds:4[rdi*2]
0x18010afa1  mov     [rbp+710h+var_778], rcx
0x18010afa5  mov     [rbp+710h+var_770], rcx
0x18010afa9  lea     rcx, [rbp+710h+Block]
0x18010afad  mov     [rsp+810h+Count], rdi
0x18010afb2  call    archive_string_ensure
0x18010afb7  xor     ecx, ecx
0x18010afb9  test    rax, rax
0x18010afbc  jnz     short loc_18010AFEB
0x18010afbe  lea     r8, aCanTAllocatePa; "Can't allocate pax data"
0x18010afc5  mov     edx, 0Ch
0x18010afca  mov     rcx, r14
0x18010afcd  call    archive_set_error
0x18010afd2  mov     rcx, [rbp+710h+Block]; Block
0x18010afd6  xor     eax, eax
0x18010afd8  mov     [rbp+710h+var_778], rax
0x18010afdc  mov     [rbp+710h+var_770], rax
0x18010afe0  call    cs:__imp_free
0x18010afe6  jmp     loc_18010C1BF
0x18010afeb  mov     rdx, [rsp+810h+var_7E0]
0x18010aff0  cmp     word ptr [rdx+rdi*2-2], 5Ch ; '\'
0x18010aff6  jnz     short loc_18010B000
0x18010aff8  dec     rdi
0x18010affb  mov     [rsp+810h+Count], rdi
0x18010b000  mov     [rbp+710h+var_778], rcx
0x18010b004  mov     r8, rdi
0x18010b007  lea     rcx, [rbp+710h+Block]
0x18010b00b  call    archive_wstrncat
0x18010b010  mov     edx, 2Fh ; '/'
0x18010b015  lea     rcx, [rbp+710h+Block]
0x18010b019  call    archive_wstrappend_wchar
0x18010b01e  mov     rdx, [rbp+710h+Block]
0x18010b022  lea     rcx, [r13+1E8h]
0x18010b029  call    archive_mstring_copy_wcs
0x18010b02e  jmp     loc_18010B0E3
0x18010b033  mov     rcx, r13
0x18010b036  call    archive_entry_pathname
0x18010b03b  mov     [rsp+810h+var_7E0], rax
0x18010b040  test    rax, rax
0x18010b043  jz      loc_18010B0F7
0x18010b049  cmp     byte ptr [rax], 0
0x18010b04c  jz      loc_18010B0F7
0x18010b052  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18010b056  inc     rdi
0x18010b059  cmp     byte ptr [rax+rdi], 0
0x18010b05d  jnz     short loc_18010B056
0x18010b05f  cmp     byte ptr [rdi+rax-1], 2Fh ; '/'
0x18010b064  jz      loc_18010B0F7
0x18010b06a  xor     eax, eax
0x18010b06c  mov     [rsp+810h+Count], rdi
0x18010b071  lea     rdx, [rdi+2]
0x18010b075  mov     [rbp+710h+Block], rax
0x18010b079  lea     rcx, [rbp+710h+Block]
0x18010b07d  mov     [rbp+710h+var_778], rax
0x18010b081  mov     [rbp+710h+var_770], rax
0x18010b085  call    archive_string_ensure
0x18010b08a  xor     ecx, ecx
0x18010b08c  test    rax, rax
0x18010b08f  jz      loc_18010AFBE
0x18010b095  mov     rdx, [rsp+810h+var_7E0]
0x18010b09a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010b09e  inc     rax
0x18010b0a1  cmp     [rdx+rax], cl
0x18010b0a4  jnz     short loc_18010B09E
0x18010b0a6  cmp     byte ptr [rax+rdx-1], 5Ch ; '\'
0x18010b0ab  jnz     short loc_18010B0B8
0x18010b0ad  lea     rax, [rdi-1]
0x18010b0b1  mov     [rsp+810h+Count], rax
0x18010b0b6  jmp     short loc_18010B0C8
0x18010b0b8  mov     [rbp+710h+var_778], rcx
0x18010b0bc  mov     r8, rdi
0x18010b0bf  lea     rcx, [rbp+710h+Block]
0x18010b0c3  call    archive_strncat
0x18010b0c8  mov     dl, 2Fh ; '/'
0x18010b0ca  lea     rcx, [rbp+710h+Block]
0x18010b0ce  call    archive_strappend_char
0x18010b0d3  mov     rdx, [rbp+710h+Block]
0x18010b0d7  lea     rcx, [r13+1E8h]
0x18010b0de  call    archive_mstring_copy_mbs
0x18010b0e3  mov     rcx, [rbp+710h+Block]; Block
0x18010b0e7  xor     eax, eax
0x18010b0e9  mov     [rbp+710h+var_778], rax
0x18010b0ed  mov     [rbp+710h+var_770], rax
0x18010b0f1  call    cs:__imp_free
0x18010b0f7  mov     rax, [r13+328h]
0x18010b0fe  mov     [rbp+710h+var_748], rax
0x18010b102  test    rax, rax
0x18010b105  jz      loc_18010B32E
0x18010b10b  mov     rax, [r13+330h]
0x18010b112  mov     rcx, r14
0x18010b115  mov     [rsp+810h+var_7E0], rax
0x18010b11a  call    archive_entry_new2
0x18010b11f  mov     rcx, r13
0x18010b122  mov     rdi, rax
0x18010b125  call    archive_entry_pathname
0x18010b12a  mov     rcx, rax
0x18010b12d  mov     [rsp+810h+var_7A0], rax
0x18010b132  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010b136  inc     rax
0x18010b139  cmp     byte ptr [rcx+rax], 0
0x18010b13d  jnz     short loc_18010B136
0x18010b13f  lea     rcx, [rax+3]; Size
0x18010b143  mov     [rbp+710h+var_788], rax
0x18010b147  call    cs:__imp_malloc
0x18010b14d  mov     [rsp+810h+Str], rax
0x18010b152  mov     rcx, rax
0x18010b155  test    rax, rax
0x18010b158  jz      loc_18010B39F
0x18010b15e  test    rdi, rdi
0x18010b161  jz      loc_18010B39F
0x18010b167  mov     rdx, [rsp+810h+var_7A0]
0x18010b16c  mov     r8, rax
0x18010b16f  mov     r10d, 1
0x18010b175  mov     al, [rdx]
0x18010b177  add     rdx, r10
0x18010b17a  mov     [r8], al
0x18010b17d  add     r8, r10
0x18010b180  test    al, al
0x18010b182  jnz     short loc_18010B175
0x18010b184  jmp     short loc_18010B196
0x18010b186  cmp     [rax+1], cl
0x18010b189  jnz     loc_18010B367
0x18010b18f  mov     [rax], cl
0x18010b191  mov     rcx, [rsp+810h+Str]; Str
0x18010b196  mov     edx, 2Fh ; '/'; Ch
0x18010b19b  call    cs:__imp_strrchr
0x18010b1a1  xor     ecx, ecx
0x18010b1a3  test    rax, rax
0x18010b1a6  jnz     short loc_18010B186
0x18010b1a8  mov     rax, [rsp+810h+Str]
0x18010b1ad  mov     r8, [rbp+710h+var_788]
0x18010b1b1  mov     rdx, rax; Src
0x18010b1b4  inc     r8; Size
0x18010b1b7  lea     rcx, [rax+2]; void *
0x18010b1bb  call    memmove_0
0x18010b1c0  mov     rax, [rsp+810h+Str]
0x18010b1c5  mov     word ptr [rax], 5F2Eh
0x18010b1ca  lea     rcx, [rdi+1E8h]
0x18010b1d1  mov     rdx, rax
0x18010b1d4  call    archive_mstring_copy_mbs
0x18010b1d9  mov     rcx, [rsp+810h+Str]; Block
0x18010b1de  call    cs:__imp_free
0x18010b1e4  mov     rdx, [rsp+810h+var_7E0]
0x18010b1e9  xor     r8d, r8d
0x18010b1ec  mov     [rdi+10h], r8d
0x18010b1f0  test    rdx, rdx
0x18010b1f3  mov     rcx, rdx
0x18010b1f6  mov     eax, 8000h
0x18010b1fb  cmovs   rcx, r8
0x18010b1ff  or      dword ptr [rdi+0A0h], 440h
0x18010b209  mov     [rdi+70h], rcx
0x18010b20d  mov     r8d, 0FFFh
0x18010b213  and     [rdi+408h], r8w
0x18010b21b  or      [rdi+408h], ax
0x18010b222  movzx   ecx, word ptr [rdi+408h]
0x18010b229  movzx   eax, cx
0x18010b22c  xor     ax, [r13+408h]
0x18010b234  bts     dword ptr [rdi+0A0h], 9
0x18010b23c  and     ax, r8w
0x18010b240  xor     ax, cx
0x18010b243  mov     rcx, rdi
0x18010b246  mov     [rdi+408h], ax
0x18010b24d  mov     r8d, [r13+40h]
0x18010b251  mov     rdx, [r13+38h]
0x18010b255  call    archive_entry_set_mtime
0x18010b25a  mov     rcx, [r13+58h]
0x18010b25e  xor     edx, edx
0x18010b260  test    rcx, rcx
  ... truncated ...
```
