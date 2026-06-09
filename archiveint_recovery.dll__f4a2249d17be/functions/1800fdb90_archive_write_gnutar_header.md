# archive_write_gnutar_header

- ea: `0x1800fdb90`
- end: `0x1800fe375`
- name: `archive_write_gnutar_header`
- size: `2021`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `29`
- tags: `reparse_path`

## callees

- `0x180006c00`
- `0x180007c80`
- `0x18000a2d0`
- `0x18000b4d0`
- `0x18000e8d4`
- `0x180014ab4`
- `0x180014fc0`
- `0x1800b0ac4`
- `0x1800b0b0c`
- `0x1800b1b60`
- `0x1800b1bc0`
- `0x1800b1ce0`
- `0x1800b1ef0`
- `0x1800b1f40`
- `0x1800b2770`
- `0x1800b28d0`
- `0x1800ece24`
- `0x1800ece48`
- `0x1800ecf00`
- `0x1800ed038`
- `0x1800ed464`
- `0x1800ed554`
- `0x1800ed5e0`
- `0x1800ed6c0`
- `0x1800ef2d4`
- `0x1800efbb4`
- `0x1800f8774`
- `0x1800fd790`
- `0x1800fdb90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fde42`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fdebe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fdf28`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fdf8f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fdffc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fde42`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fdebe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fdf28`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fdf8f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fdffc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fdcd2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fdd33`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fdcd2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fdd33`

## string_xrefs

- `0x1800fdf99`: `Can't allocate memory for Linkname`
- `0x1800fde82`: `Can't translate pathname '%s' to %s`
- `0x1800fdfc0`: `Can't translate linkname '%s' to %s`
- `0x1800fe021`: `Can't translate linkname '%s' to %s`
- `0x1800fde4c`: `Can't allocate memory for pathname`
- `0x1800fe09b`: `././@LongLink`

## pseudocode

```c
__int64 __fastcall archive_write_gnutar_header(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  __int64 v5; // r12
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rbx
  _BYTE *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // edi
  const char *v15; // rbx
  const char *v16; // rax
  const char *v17; // rbx
  const char *v18; // rax
  const char *v19; // rbx
  const char *v20; // rax
  _QWORD *v21; // rbx
  __int64 v22; // r9
  const char *v23; // rbx
  const char *v24; // rax
  const char *v25; // rbx
  const char *v26; // rax
  __int64 v27; // r12
  __int64 v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // r9
  unsigned __int64 v31; // r12
  __int64 v32; // r12
  __int64 v33; // rbx
  __int64 v34; // rdx
  __int64 v35; // r9
  __int16 v36; // r13
  int v37; // eax
  int v38; // ebx
  int v39; // eax
  __int64 v40; // rax
  int v41; // [rsp+30h] [rbp-D0h]
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v43; // [rsp+40h] [rbp-C0h]
  __int64 v44; // [rsp+48h] [rbp-B8h]
  __int64 v45; // [rsp+50h] [rbp-B0h]
  __int64 v46; // [rsp+58h] [rbp-A8h]
  _BYTE v47[512]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = *(_QWORD *)(a1 + 248);
  v5 = *(_QWORD *)(v2 + 80);
  if ( !v5 )
  {
    if ( !*(_DWORD *)(v2 + 96) )
    {
      *(_QWORD *)(v2 + 88) = archive_string_default_conversion_for_write();
      *(_DWORD *)(v2 + 96) = 1;
    }
    v5 = *(_QWORD *)(v2 + 88);
  }
  if ( archive_entry_hardlink(a2) || archive_entry_symlink(a2) || (*(_WORD *)(a2 + 1032) & 0xF000) != 0x8000 )
  {
    *(_DWORD *)(a2 + 160) |= 0x40u;
    *(_DWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 112) = 0;
  }
  if ( (*(_WORD *)(a2 + 1032) & 0xF000) == 0x4000 )
  {
    v6 = archive_entry_pathname_w(a2);
    v7 = -1;
    v45 = v6;
    if ( v6 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(v6 + 2 * v8) );
      if ( *(_WORD *)(v6 + 2 * v8 - 2) != 47 )
      {
        Block = 0;
        v43 = 0;
        v44 = 0;
        if ( !archive_string_ensure(&Block, 2 * v8 + 4) )
        {
LABEL_15:
          archive_set_error(a1, 12, "Can't allocate ustar data");
          v43 = 0;
          v44 = 0;
          free(Block);
          return 4294967266LL;
        }
        if ( *(_WORD *)(v45 + 2 * v8 - 2) == 92 )
          --v8;
        v43 = 0;
        archive_wstrncat(&Block, v45, v8);
        archive_wstrappend_wchar(&Block, 47);
        archive_mstring_copy_wcs(a2 + 488, Block);
        goto LABEL_20;
      }
    }
    v10 = (_BYTE *)archive_entry_pathname(a2);
    if ( v10 && *v10 )
    {
      do
        ++v7;
      while ( v10[v7] );
      if ( v10[v7 - 1] != 47 )
      {
        Block = 0;
        v43 = 0;
        v44 = 0;
        if ( !archive_string_ensure(&Block, v7 + 2) )
          goto LABEL_15;
        v12 = -1;
        do
          ++v12;
        while ( v10[v12] );
        if ( v10[v12 - 1] != 92 )
        {
          v43 = 0;
          archive_strncat(&Block, v10, v7);
        }
        LOBYTE(v11) = 47;
        archive_strappend_char(&Block, v11);
        archive_mstring_copy_mbs(a2 + 488, Block);
LABEL_20:
        v43 = 0;
        v44 = 0;
        free(Block);
      }
    }
  }
  v13 = _la_win_entry_in_posix_pathseparator(a2);
  v45 = v13;
  if ( !v13 )
  {
    archive_set_error(a1, 12, "Can't allocate ustar data");
    return 4294967266LL;
  }
  v41 = 0;
  if ( a2 == v13 )
    v45 = 0;
  else
    a2 = v13;
  if ( !(unsigned int)archive_mstring_get_mbs_l(*(_QWORD *)a2, (int)a2 + 488, (int)v2 + 32, (int)v2 + 40, v5) )
  {
LABEL_41:
    if ( (unsigned int)archive_mstring_get_mbs_l(*(_QWORD *)a2, (int)a2 + 592, (int)v2 + 48, (int)v2 + 56, v5) )
    {
      if ( *(_DWORD *)_o__errno() == 12 )
      {
        archive_set_error(a1, 12, "Can't allocate memory for Uname");
        goto LABEL_39;
      }
      v17 = (const char *)archive_string_conversion_charset_name(v5);
      v18 = (const char *)archive_entry_uname(a2);
      archive_set_error(a1, 42, "Can't translate uname '%s' to %s", v18, v17);
      v41 = -20;
    }
    if ( (unsigned int)archive_mstring_get_mbs_l(*(_QWORD *)a2, (int)a2 + 280, (int)v2 + 64, (int)v2 + 72, v5) )
    {
      if ( *(_DWORD *)_o__errno() == 12 )
      {
        archive_set_error(a1, 12, "Can't allocate memory for Gname");
        goto LABEL_39;
      }
      v19 = (const char *)archive_string_conversion_charset_name(v5);
      v20 = (const char *)archive_entry_gname(a2);
      archive_set_error(a1, 42, "Can't translate gname '%s' to %s", v20, v19);
      v41 = -20;
    }
    v21 = (_QWORD *)(v2 + 24);
    if ( (unsigned int)archive_entry_hardlink_l(a2, v2 + 16, v2 + 24, v5) )
    {
      if ( *(_DWORD *)_o__errno() == 12 )
      {
LABEL_51:
        archive_set_error(a1, 12, "Can't allocate memory for Linkname");
        goto LABEL_39;
      }
      v23 = (const char *)archive_string_conversion_charset_name(v5);
      v24 = (const char *)archive_entry_hardlink(a2);
      archive_set_error(a1, 42, "Can't translate linkname '%s' to %s", v24, v23);
      v41 = -20;
      v21 = (_QWORD *)(v2 + 24);
    }
    if ( !*v21 && (unsigned int)archive_entry_symlink_l(a2, v2 + 16, v21, v5) )
    {
      if ( *(_DWORD *)_o__errno() == 12 )
        goto LABEL_51;
      v25 = (const char *)archive_string_conversion_charset_name(v5);
      v26 = (const char *)archive_entry_hardlink(a2);
      archive_set_error(a1, 42, "Can't translate linkname '%s' to %s", v26, v25);
      v41 = -20;
      v21 = (_QWORD *)(v2 + 24);
    }
    if ( *v21 > 0x64u )
    {
      v27 = *v21 + 1LL;
      v28 = archive_entry_new2(a1);
      archive_mstring_copy_mbs_len(v28 + 592, "root");
      archive_mstring_copy_mbs_len(v28 + 280, "wheel");
      archive_mstring_copy_mbs_len(v28 + 488, "././@LongLink");
      v29 = v27;
      *(_DWORD *)(v28 + 16) = 0;
      LOBYTE(v30) = 75;
      if ( v27 < 0 )
        v29 = 0;
      *(_DWORD *)(v28 + 160) |= 0x40u;
      *(_QWORD *)(v28 + 112) = v29;
      v14 = archive_format_gnutar_header(a1, v47, v28, v30);
      archive_entry_free(v28);
      if ( v14 < -20 )
        goto LABEL_93;
      v14 = _archive_write_filter(*(_QWORD *)(a1 + 232), v47, 512);
      if ( v14 < -20 )
        goto LABEL_93;
      v14 = _archive_write_filter(*(_QWORD *)(a1 + 232), *(_QWORD *)(v2 + 16), v27);
      if ( v14 < -20 )
        goto LABEL_93;
      v14 = _archive_write_nulls(a1, -(int)v27 & 0x1FF);
      if ( v14 < -20 )
        goto LABEL_93;
    }
    v31 = *(_QWORD *)(v2 + 40);
    if ( v31 > 0x64 )
    {
      v46 = *(_QWORD *)(v2 + 32);
      v32 = v31 + 1;
      v33 = archive_entry_new2(a1);
      archive_mstring_copy_mbs_len(v33 + 592, "root");
      archive_mstring_copy_mbs_len(v33 + 280, "wheel");
      archive_mstring_copy_mbs_len(v33 + 488, "././@LongName");
      v34 = v32;
      *(_DWORD *)(v33 + 16) = 0;
      LOBYTE(v35) = 76;
      if ( v32 < 0 )
        v34 = 0;
      *(_DWORD *)(v33 + 160) |= 0x40u;
      *(_QWORD *)(v33 + 112) = v34;
      v14 = archive_format_gnutar_header(a1, v47, v33, v35);
      archive_entry_free(v33);
      if ( v14 < -20 )
        goto LABEL_93;
      v14 = _archive_write_filter(*(_QWORD *)(a1 + 232), v47, 512);
      if ( v14 < -20 )
        goto LABEL_93;
      v14 = _archive_write_filter(*(_QWORD *)(a1 + 232), v46, v32);
      if ( v14 < -20 )
        goto LABEL_93;
      v14 = _archive_write_nulls(a1, -(int)v32 & 0x1FF);
      if ( v14 < -20 )
        goto LABEL_93;
    }
    if ( (*(_BYTE *)(a2 + 160) & 1) != 0 )
    {
      LOBYTE(v22) = 49;
    }
    else
    {
      v36 = *(_WORD *)(a2 + 1032) & 0xF000;
      switch ( v36 )
      {
        case 4096:
          LOBYTE(v22) = 54;
          break;
        case 8192:
          LOBYTE(v22) = 51;
          break;
        case 16384:
          LOBYTE(v22) = 53;
          break;
        case 24576:
          LOBYTE(v22) = 52;
          break;
        case -32768:
          LOBYTE(v22) = 48;
          break;
        case -24576:
          LOBYTE(v22) = 50;
          break;
        default:
          _archive_write_entry_filetype_unsupported(a1, a2, "gnutar");
          v14 = -25;
          goto LABEL_93;
      }
    }
    v37 = archive_format_gnutar_header(a1, v47, a2, v22);
    v14 = v37;
    if ( v37 >= -20 )
    {
      if ( v41 < v37 )
        v14 = v41;
      v38 = v14;
      v39 = _archive_write_filter(*(_QWORD *)(a1 + 232), v47, 512);
      v14 = v39;
      if ( v39 >= -20 )
      {
        if ( v39 < v38 )
          v38 = v39;
        v40 = *(_QWORD *)(a2 + 112);
        *(_QWORD *)v2 = v40;
        v14 = v38;
        *(_QWORD *)(v2 + 8) = -(int)v40 & 0x1FF;
      }
    }
    goto LABEL_93;
  }
  if ( *(_DWORD *)_o__errno() != 12 )
  {
    v15 = (const char *)archive_string_conversion_charset_name(v5);
    v16 = (const char *)archive_entry_pathname(a2);
    archive_set_error(a1, 42, "Can't translate pathname '%s' to %s", v16, v15);
    v41 = -20;
    goto LABEL_41;
  }
  archive_set_error(a1, 12, "Can't allocate memory for pathname");
LABEL_39:
  v14 = -30;
LABEL_93:
  archive_entry_free(v45);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800fdb90  mov     [rsp-8+arg_10], rbx
0x1800fdb95  push    rbp
0x1800fdb96  push    rsi
0x1800fdb97  push    rdi
0x1800fdb98  push    r12
0x1800fdb9a  push    r13
0x1800fdb9c  push    r14
0x1800fdb9e  push    r15
0x1800fdba0  lea     rbp, [rsp-170h]
0x1800fdba8  sub     rsp, 270h
0x1800fdbaf  mov     rax, cs:__security_cookie
0x1800fdbb6  xor     rax, rsp
0x1800fdbb9  mov     [rbp+1A0h+var_40], rax
0x1800fdbc0  mov     r15, [rcx+0F8h]
0x1800fdbc7  xor     edi, edi
0x1800fdbc9  mov     rsi, rdx
0x1800fdbcc  mov     r14, rcx
0x1800fdbcf  mov     r12, [r15+50h]
0x1800fdbd3  test    r12, r12
0x1800fdbd6  jnz     short loc_1800FDBF3
0x1800fdbd8  cmp     [r15+60h], edi
0x1800fdbdc  jnz     short loc_1800FDBEF
0x1800fdbde  call    archive_string_default_conversion_for_write
0x1800fdbe3  mov     [r15+58h], rax
0x1800fdbe7  mov     dword ptr [r15+60h], 1
0x1800fdbef  mov     r12, [r15+58h]
0x1800fdbf3  mov     rcx, rsi
0x1800fdbf6  call    archive_entry_hardlink
0x1800fdbfb  mov     ebx, 8000h
0x1800fdc00  mov     r13d, 0F000h
0x1800fdc06  test    rax, rax
0x1800fdc09  jnz     short loc_1800FDC28
0x1800fdc0b  mov     rcx, rsi
0x1800fdc0e  call    archive_entry_symlink
0x1800fdc13  test    rax, rax
0x1800fdc16  jnz     short loc_1800FDC28
0x1800fdc18  movzx   eax, word ptr [rsi+408h]
0x1800fdc1f  and     ax, r13w
0x1800fdc23  cmp     ax, bx
0x1800fdc26  jz      short loc_1800FDC36
0x1800fdc28  or      dword ptr [rsi+0A0h], 40h
0x1800fdc2f  mov     [rsi+10h], edi
0x1800fdc32  mov     [rsi+70h], rdi
0x1800fdc36  movzx   eax, word ptr [rsi+408h]
0x1800fdc3d  mov     ecx, 4000h
0x1800fdc42  and     ax, r13w
0x1800fdc46  cmp     cx, ax
0x1800fdc49  jnz     loc_1800FDDE1
0x1800fdc4f  mov     rcx, rsi
0x1800fdc52  call    archive_entry_pathname_w
0x1800fdc57  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800fdc5b  mov     [rsp+2A0h+var_250], rax
0x1800fdc60  xor     ecx, ecx
0x1800fdc62  lea     edx, [rdi+30h]
0x1800fdc65  test    rax, rax
0x1800fdc68  jz      loc_1800FDD3E
0x1800fdc6e  mov     rbx, rdi
0x1800fdc71  inc     rbx
0x1800fdc74  cmp     [rax+rbx*2], cx
0x1800fdc78  jnz     short loc_1800FDC71
0x1800fdc7a  cmp     [rax+rbx*2-2], dx
0x1800fdc7f  jz      loc_1800FDD3E
0x1800fdc85  xor     edi, edi
0x1800fdc87  lea     rdx, ds:4[rbx*2]
0x1800fdc8f  lea     rcx, [rsp+2A0h+Block]
0x1800fdc94  mov     [rsp+2A0h+Block], rdi
0x1800fdc99  mov     [rsp+2A0h+var_260], rdi
0x1800fdc9e  mov     [rsp+2A0h+var_258], rdi
0x1800fdca3  call    archive_string_ensure
0x1800fdca8  test    rax, rax
0x1800fdcab  jnz     short loc_1800FDCE2
0x1800fdcad  lea     r8, aCanTAllocateUs; "Can't allocate ustar data"
0x1800fdcb4  mov     edx, 0Ch
0x1800fdcb9  mov     rcx, r14
0x1800fdcbc  call    archive_set_error
0x1800fdcc1  mov     rcx, [rsp+2A0h+Block]; Block
0x1800fdcc6  xor     eax, eax
0x1800fdcc8  mov     [rsp+2A0h+var_260], rax
0x1800fdccd  mov     [rsp+2A0h+var_258], rax
0x1800fdcd2  call    cs:__imp_free
0x1800fdcd8  mov     eax, 0FFFFFFE2h
0x1800fdcdd  jmp     loc_1800FE34B
0x1800fdce2  mov     rdx, [rsp+2A0h+var_250]
0x1800fdce7  cmp     word ptr [rdx+rbx*2-2], 5Ch ; '\'
0x1800fdced  jnz     short loc_1800FDCF2
0x1800fdcef  dec     rbx
0x1800fdcf2  mov     r8, rbx
0x1800fdcf5  mov     [rsp+2A0h+var_260], rdi
0x1800fdcfa  lea     rcx, [rsp+2A0h+Block]
0x1800fdcff  call    archive_wstrncat
0x1800fdd04  mov     edx, 2Fh ; '/'
0x1800fdd09  lea     rcx, [rsp+2A0h+Block]
0x1800fdd0e  call    archive_wstrappend_wchar
0x1800fdd13  mov     rdx, [rsp+2A0h+Block]
0x1800fdd18  lea     rcx, [rsi+1E8h]
0x1800fdd1f  call    archive_mstring_copy_wcs
0x1800fdd24  mov     rcx, [rsp+2A0h+Block]; Block
0x1800fdd29  mov     [rsp+2A0h+var_260], rdi
0x1800fdd2e  mov     [rsp+2A0h+var_258], rdi
0x1800fdd33  call    cs:__imp_free
0x1800fdd39  jmp     loc_1800FDDE1
0x1800fdd3e  mov     rcx, rsi
0x1800fdd41  call    archive_entry_pathname
0x1800fdd46  mov     rbx, rax
0x1800fdd49  xor     eax, eax
0x1800fdd4b  test    rbx, rbx
0x1800fdd4e  jz      loc_1800FDDDF
0x1800fdd54  cmp     [rbx], al
0x1800fdd56  jz      loc_1800FDDDF
0x1800fdd5c  inc     rdi
0x1800fdd5f  cmp     [rbx+rdi], al
0x1800fdd62  jnz     short loc_1800FDD5C
0x1800fdd64  cmp     byte ptr [rdi+rbx-1], 2Fh ; '/'
0x1800fdd69  jz      short loc_1800FDDDF
0x1800fdd6b  lea     rdx, [rdi+2]
0x1800fdd6f  mov     [rsp+2A0h+Block], rax
0x1800fdd74  lea     rcx, [rsp+2A0h+Block]
0x1800fdd79  mov     [rsp+2A0h+var_260], rax
0x1800fdd7e  mov     [rsp+2A0h+var_258], rax
0x1800fdd83  call    archive_string_ensure
0x1800fdd88  xor     ecx, ecx
0x1800fdd8a  test    rax, rax
0x1800fdd8d  jz      loc_1800FDCAD
0x1800fdd93  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800fdd97  inc     rax
0x1800fdd9a  cmp     [rbx+rax], cl
0x1800fdd9d  jnz     short loc_1800FDD97
0x1800fdd9f  cmp     byte ptr [rax+rbx-1], 5Ch ; '\'
0x1800fdda4  jz      short loc_1800FDDBB
0x1800fdda6  mov     [rsp+2A0h+var_260], rcx
0x1800fddab  mov     r8, rdi
0x1800fddae  lea     rcx, [rsp+2A0h+Block]
0x1800fddb3  mov     rdx, rbx
0x1800fddb6  call    archive_strncat
0x1800fddbb  mov     dl, 2Fh ; '/'
0x1800fddbd  lea     rcx, [rsp+2A0h+Block]
0x1800fddc2  call    archive_strappend_char
0x1800fddc7  mov     rdx, [rsp+2A0h+Block]
0x1800fddcc  lea     rcx, [rsi+1E8h]
0x1800fddd3  call    archive_mstring_copy_mbs
0x1800fddd8  xor     edi, edi
0x1800fddda  jmp     loc_1800FDD24
0x1800fdddf  xor     edi, edi
0x1800fdde1  mov     rcx, rsi
0x1800fdde4  call    __la_win_entry_in_posix_pathseparator
0x1800fdde9  mov     [rsp+2A0h+var_250], rax
0x1800fddee  test    rax, rax
0x1800fddf1  jnz     short loc_1800FDE0A
0x1800fddf3  lea     r8, aCanTAllocateUs; "Can't allocate ustar data"
0x1800fddfa  mov     rcx, r14
0x1800fddfd  lea     edx, [rax+0Ch]
0x1800fde00  call    archive_set_error
0x1800fde05  jmp     loc_1800FDCD8
0x1800fde0a  mov     [rsp+2A0h+var_270], edi
0x1800fde0e  cmp     rsi, rax
0x1800fde11  jz      short loc_1800FDE18
0x1800fde13  mov     rsi, rax
0x1800fde16  jmp     short loc_1800FDE1D
0x1800fde18  mov     [rsp+2A0h+var_250], rdi
0x1800fde1d  mov     rcx, [rsi]
0x1800fde20  lea     r9, [r15+28h]
0x1800fde24  lea     r8, [r15+20h]
0x1800fde28  mov     [rsp+2A0h+var_280], r12
0x1800fde2d  lea     rdx, [rsi+1E8h]
0x1800fde34  call    archive_mstring_get_mbs_l
0x1800fde39  mov     edi, 0Ch
0x1800fde3e  test    eax, eax
0x1800fde40  jz      short loc_1800FDE9E
0x1800fde42  call    cs:__imp__o__errno
0x1800fde48  cmp     [rax], edi
0x1800fde4a  jnz     short loc_1800FDE67
0x1800fde4c  lea     r8, aCanTAllocateMe_23; "Can't allocate memory for pathname"
0x1800fde53  mov     edx, edi
0x1800fde55  mov     rcx, r14
0x1800fde58  call    archive_set_error
0x1800fde5d  mov     edi, 0FFFFFFE2h
0x1800fde62  jmp     loc_1800FE33F
0x1800fde67  mov     rcx, r12
0x1800fde6a  call    archive_string_conversion_charset_name
0x1800fde6f  mov     rcx, rsi
0x1800fde72  mov     rbx, rax
0x1800fde75  call    archive_entry_pathname
0x1800fde7a  mov     r9, rax
0x1800fde7d  mov     [rsp+2A0h+var_280], rbx
0x1800fde82  lea     r8, aCanTTranslateP; "Can't translate pathname '%s' to %s"
0x1800fde89  mov     edx, 2Ah ; '*'
0x1800fde8e  mov     rcx, r14
0x1800fde91  call    archive_set_error
0x1800fde96  mov     [rsp+2A0h+var_270], 0FFFFFFECh
0x1800fde9e  mov     rcx, [rsi]
0x1800fdea1  lea     r9, [r15+38h]
0x1800fdea5  lea     r8, [r15+30h]
0x1800fdea9  mov     [rsp+2A0h+var_280], r12
0x1800fdeae  lea     rdx, [rsi+250h]
0x1800fdeb5  call    archive_mstring_get_mbs_l
0x1800fdeba  test    eax, eax
0x1800fdebc  jz      short loc_1800FDF08
0x1800fdebe  call    cs:__imp__o__errno
0x1800fdec4  cmp     [rax], edi
0x1800fdec6  jnz     short loc_1800FDED1
0x1800fdec8  lea     r8, aCanTAllocateMe_22; "Can't allocate memory for Uname"
0x1800fdecf  jmp     short loc_1800FDE53
0x1800fded1  mov     rcx, r12
0x1800fded4  call    archive_string_conversion_charset_name
0x1800fded9  mov     rcx, rsi
0x1800fdedc  mov     rbx, rax
0x1800fdedf  call    archive_entry_uname
0x1800fdee4  mov     r9, rax
0x1800fdee7  mov     [rsp+2A0h+var_280], rbx
0x1800fdeec  lea     r8, aCanTTranslateU; "Can't translate uname '%s' to %s"
0x1800fdef3  mov     edx, 2Ah ; '*'
0x1800fdef8  mov     rcx, r14
0x1800fdefb  call    archive_set_error
0x1800fdf00  mov     [rsp+2A0h+var_270], 0FFFFFFECh
0x1800fdf08  mov     rcx, [rsi]
0x1800fdf0b  lea     r9, [r15+48h]
0x1800fdf0f  lea     r8, [r15+40h]
0x1800fdf13  mov     [rsp+2A0h+var_280], r12
0x1800fdf18  lea     rdx, [rsi+118h]
0x1800fdf1f  call    archive_mstring_get_mbs_l
0x1800fdf24  test    eax, eax
0x1800fdf26  jz      short loc_1800FDF75
0x1800fdf28  call    cs:__imp__o__errno
0x1800fdf2e  cmp     [rax], edi
0x1800fdf30  jnz     short loc_1800FDF3E
0x1800fdf32  lea     r8, aCanTAllocateMe_9; "Can't allocate memory for Gname"
0x1800fdf39  jmp     loc_1800FDE53
0x1800fdf3e  mov     rcx, r12
0x1800fdf41  call    archive_string_conversion_charset_name
0x1800fdf46  mov     rcx, rsi
0x1800fdf49  mov     rbx, rax
0x1800fdf4c  call    archive_entry_gname
0x1800fdf51  mov     r9, rax
0x1800fdf54  mov     [rsp+2A0h+var_280], rbx
0x1800fdf59  lea     r8, aCanTTranslateG; "Can't translate gname '%s' to %s"
0x1800fdf60  mov     edx, 2Ah ; '*'
0x1800fdf65  mov     rcx, r14
0x1800fdf68  call    archive_set_error
0x1800fdf6d  mov     [rsp+2A0h+var_270], 0FFFFFFECh
0x1800fdf75  lea     rbx, [r15+18h]
0x1800fdf79  mov     r9, r12
0x1800fdf7c  mov     r8, rbx
0x1800fdf7f  lea     rdx, [r15+10h]
0x1800fdf83  mov     rcx, rsi
0x1800fdf86  call    _archive_entry_hardlink_l
0x1800fdf8b  test    eax, eax
0x1800fdf8d  jz      short loc_1800FDFE0
0x1800fdf8f  call    cs:__imp__o__errno
0x1800fdf95  cmp     [rax], edi
0x1800fdf97  jnz     short loc_1800FDFA5
0x1800fdf99  lea     r8, aCanTAllocateMe_15; "Can't allocate memory for Linkname"
0x1800fdfa0  jmp     loc_1800FDE53
0x1800fdfa5  mov     rcx, r12
0x1800fdfa8  call    archive_string_conversion_charset_name
0x1800fdfad  mov     rcx, rsi
0x1800fdfb0  mov     rbx, rax
0x1800fdfb3  call    archive_entry_hardlink
0x1800fdfb8  mov     r9, rax
0x1800fdfbb  mov     [rsp+2A0h+var_280], rbx
0x1800fdfc0  lea     r8, aCanTTranslateL; "Can't translate linkname '%s' to %s"
0x1800fdfc7  mov     edx, 2Ah ; '*'
0x1800fdfcc  mov     rcx, r14
0x1800fdfcf  call    archive_set_error
0x1800fdfd4  mov     [rsp+2A0h+var_270], 0FFFFFFECh
0x1800fdfdc  lea     rbx, [r15+18h]
0x1800fdfe0  cmp     qword ptr [rbx], 0
0x1800fdfe4  jnz     short loc_1800FE041
0x1800fdfe6  mov     r9, r12
0x1800fdfe9  lea     rdx, [r15+10h]
0x1800fdfed  mov     r8, rbx
0x1800fdff0  mov     rcx, rsi
0x1800fdff3  call    _archive_entry_symlink_l
0x1800fdff8  test    eax, eax
0x1800fdffa  jz      short loc_1800FE041
0x1800fdffc  call    cs:__imp__o__errno
0x1800fe002  cmp     [rax], edi
0x1800fe004  jz      short loc_1800FDF99
0x1800fe006  mov     rcx, r12
0x1800fe009  call    archive_string_conversion_charset_name
0x1800fe00e  mov     rcx, rsi
0x1800fe011  mov     rbx, rax
0x1800fe014  call    archive_entry_hardlink
0x1800fe019  mov     r9, rax
0x1800fe01c  mov     [rsp+2A0h+var_280], rbx
0x1800fe021  lea     r8, aCanTTranslateL; "Can't translate linkname '%s' to %s"
0x1800fe028  mov     edx, 2Ah ; '*'
0x1800fe02d  mov     rcx, r14
0x1800fe030  call    archive_set_error
0x1800fe035  mov     [rsp+2A0h+var_270], 0FFFFFFECh
0x1800fe03d  lea     rbx, [r15+18h]
0x1800fe041  mov     r12, [rbx]
0x1800fe044  cmp     r12, 64h ; 'd'
0x1800fe048  jbe     loc_1800FE147
0x1800fe04e  mov     rcx, r14
0x1800fe051  inc     r12
0x1800fe054  call    archive_entry_new2
0x1800fe059  mov     r8d, 4
0x1800fe05f  lea     rdx, aRoot_0; "root"
0x1800fe066  mov     rbx, rax
0x1800fe069  lea     rcx, [rax+250h]
  ... truncated ...
```
