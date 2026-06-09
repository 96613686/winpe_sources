# write_header_1

- ea: `0x1800fd150`
- end: `0x1800fd5e1`
- name: `write_header_1`
- size: `1169`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `reparse_path`

## callers

- `0x1800fcd10`
- `0x1800fcde0`

## callees

- `0x180006c00`
- `0x18000e8d4`
- `0x180014fc0`
- `0x180015810`
- `0x1800b0b0c`
- `0x1800b1990`
- `0x1800b19b0`
- `0x1800b1b60`
- `0x1800b1f40`
- `0x1800b20d0`
- `0x1800b2100`
- `0x1800b2770`
- `0x1800ed038`
- `0x1800ed464`
- `0x1800ef2d4`
- `0x1800fd084`
- `0x1800fd10c`
- `0x1800fd150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fd201`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fd42b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fd201`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fd42b`

## string_xrefs

- `0x1800fd20c`: `Can't allocate memory for Pathname`
- `0x1800fd243`: `Can't translate pathname '%s' to %s`
- `0x1800fd45d`: `Can't translate linkname '%s' to %s`

## pseudocode

```c
__int64 __fastcall write_header_1(__int64 a1, __int64 a2)
{
  __int64 v2; // r13
  __int64 sconv_0; // r15
  __int64 v6; // rax
  __int64 v7; // r12
  unsigned int v9; // ebx
  const char *v10; // rbx
  const char *v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // r11d
  __int64 v15; // rax
  unsigned int v16; // r11d
  unsigned int v17; // r11d
  unsigned int v18; // r11d
  unsigned int v19; // r11d
  __int64 v20; // rdx
  unsigned int v21; // r11d
  __int64 v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // r11d
  unsigned int v25; // r11d
  unsigned int v26; // r11d
  const char *v27; // rbx
  const char *v28; // rax
  _BYTE *v29; // r14
  __int64 v30; // r15
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r8
  int v34; // eax
  int v35; // edx
  int v36; // [rsp+30h] [rbp-89h]
  __int64 v37; // [rsp+38h] [rbp-81h] BYREF
  _BYTE *v38; // [rsp+40h] [rbp-79h] BYREF
  __int64 v39; // [rsp+48h] [rbp-71h] BYREF
  __int64 v40; // [rsp+50h] [rbp-69h]
  _BYTE v41[6]; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v42[8]; // [rsp+66h] [rbp-53h] BYREF
  _BYTE v43[8]; // [rsp+6Eh] [rbp-4Bh] BYREF
  _BYTE v44[8]; // [rsp+76h] [rbp-43h] BYREF
  _BYTE v45[8]; // [rsp+7Eh] [rbp-3Bh] BYREF
  _BYTE v46[8]; // [rsp+86h] [rbp-33h] BYREF
  _BYTE v47[8]; // [rsp+8Eh] [rbp-2Bh] BYREF
  _BYTE v48[8]; // [rsp+96h] [rbp-23h] BYREF
  _BYTE v49[8]; // [rsp+9Eh] [rbp-1Bh] BYREF
  _BYTE v50[8]; // [rsp+A6h] [rbp-13h] BYREF
  _BYTE v51[8]; // [rsp+AEh] [rbp-Bh] BYREF
  _BYTE v52[8]; // [rsp+B6h] [rbp-3h] BYREF
  _BYTE v53[8]; // [rsp+BEh] [rbp+5h] BYREF
  _BYTE v54[10]; // [rsp+C6h] [rbp+Dh] BYREF

  v2 = *(_QWORD *)(a1 + 248);
  v38 = 0;
  v39 = 0;
  v37 = 0;
  sconv_0 = get_sconv_0();
  v6 = _la_win_entry_in_posix_pathseparator(a2);
  v7 = v6;
  if ( !v6 )
  {
    archive_set_error(a1, 12, "Can't allocate ustar data");
    return 4294967266LL;
  }
  v9 = 0;
  if ( a2 == v6 )
    v7 = 0;
  else
    a2 = v6;
  if ( (unsigned int)archive_mstring_get_mbs_l(
                       *(_QWORD *)a2,
                       (int)a2 + 488,
                       (unsigned int)&v39,
                       (unsigned int)&v37,
                       sconv_0) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      archive_set_error(a1, 12, "Can't allocate memory for Pathname");
      goto LABEL_9;
    }
    v10 = (const char *)archive_string_conversion_charset_name(sconv_0);
    v11 = (const char *)archive_entry_pathname(a2);
    archive_set_error(a1, 42, "Can't translate pathname '%s' to %s", v11, v10);
    v9 = -20;
  }
  v36 = v37 + 1;
  memset_0(v41, 0, 0x6Eu);
  format_hex(460545, v41, 6);
  v12 = archive_entry_devmajor(a2);
  format_hex(v12, v49, 8);
  v13 = archive_entry_devminor(a2);
  format_hex(v13, v50, 8);
  v15 = *(_QWORD *)(a2 + 96);
  v40 = v15;
  if ( v15 > 0xFFFFFFFFLL )
  {
    archive_set_error(a1, v14 + 26, "large inode number truncated");
    LODWORD(v15) = v40;
    v9 = -20;
    v14 = 8;
  }
  format_hex((unsigned int)v15, v42, v14);
  format_hex(*(unsigned __int16 *)(a2 + 1032), v43, v16);
  format_hex(*(_QWORD *)(a2 + 120), v44, v17);
  format_hex(*(_QWORD *)(a2 + 88), v45, v18);
  format_hex(*(unsigned int *)(a2 + 104), v46, v19);
  if ( (((*(_WORD *)(a2 + 1032) & 0xF000) - 0x2000) & 0xBFFF) != 0 )
  {
    format_hex(0, v51, 8);
    v22 = 0;
  }
  else
  {
    v23 = archive_entry_rdevmajor(a2, v20);
    format_hex(v23, v51, 8);
    v22 = (unsigned int)archive_entry_rdevminor(a2);
    v21 = 8;
  }
  format_hex(v22, v52, v21);
  format_hex(*(_QWORD *)(a2 + 56), v47, v24);
  format_hex(v36, v53, v25);
  format_hex(0, v54, v26);
  if ( (*(_WORD *)(a2 + 1032) & 0xF000) != 0x8000 )
  {
    *(_DWORD *)(a2 + 160) |= 0x40u;
    *(_DWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 112) = 0;
  }
  if ( (unsigned int)archive_entry_symlink_l(a2, &v38, &v37, sconv_0) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      archive_set_error(a1, 12, "Can't allocate memory for Likname");
      goto LABEL_9;
    }
    v27 = (const char *)archive_string_conversion_charset_name(sconv_0);
    v28 = (const char *)archive_entry_symlink(a2);
    archive_set_error(a1, 42, "Can't translate linkname '%s' to %s", v28, v27);
    v9 = -20;
  }
  v29 = v38;
  v30 = -1;
  if ( v37 && v38 && *v38 )
  {
    v31 = -1;
    do
      ++v31;
    while ( v38[v31] );
  }
  else
  {
    v31 = *(_QWORD *)(a2 + 112);
  }
  if ( (unsigned int)format_hex(v31, v48, 8) )
  {
    archive_set_error(a1, 34, "File is too large for this format.");
    v9 = -25;
    goto LABEL_44;
  }
  if ( !(unsigned int)_archive_write_filter(*(_QWORD *)(a1 + 232), v41, 110)
    && !(unsigned int)_archive_write_filter(*(_QWORD *)(a1 + 232), v39, v36)
    && (((-2 - (_BYTE)v36) & 3) == 0
     || !(unsigned int)_archive_write_filter(*(_QWORD *)(a1 + 232), &unk_1801408DC, (-2 - (_BYTE)v36) & 3)) )
  {
    v32 = *(_QWORD *)(a2 + 112);
    *(_QWORD *)v2 = v32;
    *(_DWORD *)(v2 + 8) = -(int)v32 & 3;
    if ( !v29 || !*v29 )
      goto LABEL_44;
    v33 = -1;
    do
      ++v33;
    while ( v29[v33] );
    if ( !(unsigned int)_archive_write_filter(*(_QWORD *)(a1 + 232), v29, v33) )
    {
      do
        ++v30;
      while ( v29[v30] );
      v34 = _archive_write_filter(*(_QWORD *)(a1 + 232), &unk_1801408DC, -(int)v30 & 3);
      v35 = v9;
      if ( v34 )
        v35 = -30;
      v9 = v35;
      goto LABEL_44;
    }
  }
LABEL_9:
  v9 = -30;
LABEL_44:
  archive_entry_free(v7);
  return v9;
}

```

## disassembly

```asm
0x1800fd150  mov     [rsp-8+arg_10], rbx
0x1800fd155  push    rbp
0x1800fd156  push    rsi
0x1800fd157  push    rdi
0x1800fd158  push    r12
0x1800fd15a  push    r13
0x1800fd15c  push    r14
0x1800fd15e  push    r15
0x1800fd160  lea     rbp, [rsp-27h]
0x1800fd165  sub     rsp, 0E0h
0x1800fd16c  mov     rax, cs:__security_cookie
0x1800fd173  xor     rax, rsp
0x1800fd176  mov     [rbp+57h+var_40], rax
0x1800fd17a  mov     r13, [rcx+0F8h]
0x1800fd181  xor     r14d, r14d
0x1800fd184  mov     [rbp+57h+var_D0], r14
0x1800fd188  mov     rdi, rdx
0x1800fd18b  mov     [rbp+57h+var_C8], r14
0x1800fd18f  mov     rsi, rcx
0x1800fd192  mov     [rsp+110h+var_D8], r14
0x1800fd197  call    get_sconv_0
0x1800fd19c  mov     rcx, rdi
0x1800fd19f  mov     r15, rax
0x1800fd1a2  call    __la_win_entry_in_posix_pathseparator
0x1800fd1a7  mov     r12, rax
0x1800fd1aa  test    rax, rax
0x1800fd1ad  jnz     short loc_1800FD1CA
0x1800fd1af  lea     r8, aCanTAllocateUs; "Can't allocate ustar data"
0x1800fd1b6  mov     rcx, rsi
0x1800fd1b9  lea     edx, [rax+0Ch]
0x1800fd1bc  call    archive_set_error
0x1800fd1c1  lea     eax, [r14-1Eh]
0x1800fd1c5  jmp     loc_1800FD5BA
0x1800fd1ca  mov     ebx, r14d
0x1800fd1cd  cmp     rdi, rax
0x1800fd1d0  jz      short loc_1800FD1D7
0x1800fd1d2  mov     rdi, rax
0x1800fd1d5  jmp     short loc_1800FD1DA
0x1800fd1d7  mov     r12, r14
0x1800fd1da  mov     rcx, [rdi]
0x1800fd1dd  lea     rdx, [rdi+1E8h]
0x1800fd1e4  lea     r9, [rsp+110h+var_D8]
0x1800fd1e9  mov     [rsp+110h+var_F0], r15
0x1800fd1ee  lea     r8, [rbp+57h+var_C8]
0x1800fd1f2  call    archive_mstring_get_mbs_l
0x1800fd1f7  mov     r14d, 0Ch
0x1800fd1fd  test    eax, eax
0x1800fd1ff  jz      short loc_1800FD25C
0x1800fd201  call    cs:__imp__o__errno
0x1800fd207  cmp     [rax], r14d
0x1800fd20a  jnz     short loc_1800FD228
0x1800fd20c  lea     r8, aCanTAllocateMe_24; "Can't allocate memory for Pathname"
0x1800fd213  mov     edx, r14d
0x1800fd216  mov     rcx, rsi
0x1800fd219  call    archive_set_error
0x1800fd21e  mov     ebx, 0FFFFFFE2h
0x1800fd223  jmp     loc_1800FD5B0
0x1800fd228  mov     rcx, r15
0x1800fd22b  call    archive_string_conversion_charset_name
0x1800fd230  mov     rcx, rdi
0x1800fd233  mov     rbx, rax
0x1800fd236  call    archive_entry_pathname
0x1800fd23b  mov     r9, rax
0x1800fd23e  mov     [rsp+110h+var_F0], rbx
0x1800fd243  lea     r8, aCanTTranslateP; "Can't translate pathname '%s' to %s"
0x1800fd24a  mov     edx, 2Ah ; '*'
0x1800fd24f  mov     rcx, rsi
0x1800fd252  call    archive_set_error
0x1800fd257  mov     ebx, 0FFFFFFECh
0x1800fd25c  mov     eax, dword ptr [rsp+110h+var_D8]
0x1800fd260  lea     rcx, [rbp+57h+var_B0]; void *
0x1800fd264  xor     edx, edx; Val
0x1800fd266  inc     eax
0x1800fd268  mov     [rsp+110h+var_E0], eax
0x1800fd26c  lea     r8d, [rdx+6Eh]; Size
0x1800fd270  call    memset_0
0x1800fd275  mov     r8d, 6
0x1800fd27b  lea     rdx, [rbp+57h+var_B0]
0x1800fd27f  mov     ecx, 70701h
0x1800fd284  call    format_hex
0x1800fd289  mov     rcx, rdi
0x1800fd28c  call    archive_entry_devmajor
0x1800fd291  mov     ecx, eax
0x1800fd293  lea     rdx, [rbp+57h+var_72]
0x1800fd297  mov     r8d, 8
0x1800fd29d  call    format_hex
0x1800fd2a2  mov     rcx, rdi
0x1800fd2a5  call    archive_entry_devminor
0x1800fd2aa  mov     r11d, 8
0x1800fd2b0  mov     ecx, eax
0x1800fd2b2  mov     r8d, r11d
0x1800fd2b5  lea     rdx, [rbp+57h+var_6A]
0x1800fd2b9  call    format_hex
0x1800fd2be  mov     rax, [rdi+60h]
0x1800fd2c2  mov     ecx, 0FFFFFFFFh
0x1800fd2c7  mov     [rbp+57h+var_C0], rax
0x1800fd2cb  cmp     rax, rcx
0x1800fd2ce  jle     short loc_1800FD2F0
0x1800fd2d0  lea     r8, aLargeInodeNumb; "large inode number truncated"
0x1800fd2d7  mov     rcx, rsi
0x1800fd2da  lea     edx, [r11+1Ah]
0x1800fd2de  call    archive_set_error
0x1800fd2e3  mov     rax, [rbp+57h+var_C0]
0x1800fd2e7  mov     ebx, 0FFFFFFECh
0x1800fd2ec  lea     r11d, [rbx+1Ch]
0x1800fd2f0  mov     ecx, eax
0x1800fd2f2  lea     rdx, [rbp+57h+var_AA]
0x1800fd2f6  mov     r8d, r11d
0x1800fd2f9  call    format_hex
0x1800fd2fe  movzx   ecx, word ptr [rdi+408h]
0x1800fd305  lea     rdx, [rbp+57h+var_A2]
0x1800fd309  mov     r8d, r11d
0x1800fd30c  call    format_hex
0x1800fd311  mov     rcx, [rdi+78h]
0x1800fd315  lea     rdx, [rbp+57h+var_9A]
0x1800fd319  mov     r8d, r11d
0x1800fd31c  call    format_hex
0x1800fd321  mov     rcx, [rdi+58h]
0x1800fd325  lea     rdx, [rbp+57h+var_92]
0x1800fd329  mov     r8d, r11d
0x1800fd32c  call    format_hex
0x1800fd331  mov     ecx, [rdi+68h]
0x1800fd334  lea     rdx, [rbp+57h+var_8A]
0x1800fd338  mov     r8d, r11d
0x1800fd33b  call    format_hex
0x1800fd340  movzx   r11d, word ptr [rdi+408h]
0x1800fd348  mov     eax, 0F000h
0x1800fd34d  and     r11w, ax
0x1800fd351  mov     eax, 2000h
0x1800fd356  sub     r11w, ax
0x1800fd35a  mov     eax, 0BFFFh
0x1800fd35f  test    ax, r11w
0x1800fd363  jz      short loc_1800FD37D
0x1800fd365  mov     r11d, 8
0x1800fd36b  lea     rdx, [rbp+57h+var_62]
0x1800fd36f  mov     r8d, r11d
0x1800fd372  xor     ecx, ecx
0x1800fd374  call    format_hex
0x1800fd379  xor     ecx, ecx
0x1800fd37b  jmp     short loc_1800FD3A6
0x1800fd37d  mov     rcx, rdi
0x1800fd380  call    archive_entry_rdevmajor
0x1800fd385  mov     ecx, eax
0x1800fd387  lea     rdx, [rbp+57h+var_62]
0x1800fd38b  mov     r8d, 8
0x1800fd391  call    format_hex
0x1800fd396  mov     rcx, rdi
0x1800fd399  call    archive_entry_rdevminor
0x1800fd39e  mov     ecx, eax
0x1800fd3a0  mov     r11d, 8
0x1800fd3a6  mov     r8d, r11d
0x1800fd3a9  lea     rdx, [rbp+57h+var_5A]
0x1800fd3ad  call    format_hex
0x1800fd3b2  mov     rcx, [rdi+38h]
0x1800fd3b6  lea     rdx, [rbp+57h+var_82]
0x1800fd3ba  mov     r8d, r11d
0x1800fd3bd  call    format_hex
0x1800fd3c2  movsxd  rcx, [rsp+110h+var_E0]
0x1800fd3c7  lea     rdx, [rbp+57h+var_52]
0x1800fd3cb  mov     r8d, r11d
0x1800fd3ce  call    format_hex
0x1800fd3d3  mov     r8d, r11d
0x1800fd3d6  lea     rdx, [rbp+57h+var_4A]
0x1800fd3da  xor     ecx, ecx
0x1800fd3dc  call    format_hex
0x1800fd3e1  movzx   r11d, word ptr [rdi+408h]
0x1800fd3e9  mov     eax, 0F000h
0x1800fd3ee  and     r11w, ax
0x1800fd3f2  mov     eax, 8000h
0x1800fd3f7  cmp     r11w, ax
0x1800fd3fb  jz      short loc_1800FD413
0x1800fd3fd  or      dword ptr [rdi+0A0h], 40h
0x1800fd404  mov     dword ptr [rdi+10h], 0
0x1800fd40b  mov     qword ptr [rdi+70h], 0
0x1800fd413  mov     r9, r15
0x1800fd416  lea     r8, [rsp+110h+var_D8]
0x1800fd41b  lea     rdx, [rbp+57h+var_D0]
0x1800fd41f  mov     rcx, rdi
0x1800fd422  call    _archive_entry_symlink_l
0x1800fd427  test    eax, eax
0x1800fd429  jz      short loc_1800FD476
0x1800fd42b  call    cs:__imp__o__errno
0x1800fd431  cmp     [rax], r14d
0x1800fd434  jnz     short loc_1800FD442
0x1800fd436  lea     r8, aCanTAllocateMe_11; "Can't allocate memory for Likname"
0x1800fd43d  jmp     loc_1800FD213
0x1800fd442  mov     rcx, r15
0x1800fd445  call    archive_string_conversion_charset_name
0x1800fd44a  mov     rcx, rdi
0x1800fd44d  mov     rbx, rax
0x1800fd450  call    archive_entry_symlink
0x1800fd455  mov     r9, rax
0x1800fd458  mov     [rsp+110h+var_F0], rbx
0x1800fd45d  lea     r8, aCanTTranslateL; "Can't translate linkname '%s' to %s"
0x1800fd464  mov     edx, 2Ah ; '*'
0x1800fd469  mov     rcx, rsi
0x1800fd46c  call    archive_set_error
0x1800fd471  mov     ebx, 0FFFFFFECh
0x1800fd476  mov     r14, [rbp+57h+var_D0]
0x1800fd47a  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800fd47e  cmp     [rsp+110h+var_D8], 0
0x1800fd484  jbe     short loc_1800FD4A0
0x1800fd486  test    r14, r14
0x1800fd489  jz      short loc_1800FD4A0
0x1800fd48b  cmp     byte ptr [r14], 0
0x1800fd48f  jz      short loc_1800FD4A0
0x1800fd491  mov     rcx, r15
0x1800fd494  inc     rcx
0x1800fd497  cmp     byte ptr [r14+rcx], 0
0x1800fd49c  jnz     short loc_1800FD494
0x1800fd49e  jmp     short loc_1800FD4A4
0x1800fd4a0  mov     rcx, [rdi+70h]
0x1800fd4a4  mov     r8d, 8
0x1800fd4aa  lea     rdx, [rbp+57h+var_7A]
0x1800fd4ae  call    format_hex
0x1800fd4b3  test    eax, eax
0x1800fd4b5  jz      short loc_1800FD4D5
0x1800fd4b7  lea     r8, aFileIsTooLarge_2; "File is too large for this format."
0x1800fd4be  mov     edx, 22h ; '"'
0x1800fd4c3  mov     rcx, rsi
0x1800fd4c6  call    archive_set_error
0x1800fd4cb  mov     ebx, 0FFFFFFE7h
0x1800fd4d0  jmp     loc_1800FD5B0
0x1800fd4d5  mov     rcx, [rsi+0E8h]
0x1800fd4dc  lea     rdx, [rbp+57h+var_B0]
0x1800fd4e0  mov     r8d, 6Eh ; 'n'
0x1800fd4e6  call    __archive_write_filter
0x1800fd4eb  test    eax, eax
0x1800fd4ed  jnz     loc_1800FD21E
0x1800fd4f3  movsxd  r8, [rsp+110h+var_E0]
0x1800fd4f8  mov     rdx, [rbp+57h+var_C8]
0x1800fd4fc  mov     rcx, [rsi+0E8h]
0x1800fd503  call    __archive_write_filter
0x1800fd508  test    eax, eax
0x1800fd50a  jnz     loc_1800FD21E
0x1800fd510  mov     eax, 0FFFFFFFEh
0x1800fd515  sub     eax, [rsp+110h+var_E0]
0x1800fd519  and     eax, 3
0x1800fd51c  jz      short loc_1800FD53C
0x1800fd51e  mov     rcx, [rsi+0E8h]
0x1800fd525  lea     rdx, unk_1801408DC
0x1800fd52c  mov     r8d, eax
0x1800fd52f  call    __archive_write_filter
0x1800fd534  test    eax, eax
0x1800fd536  jnz     loc_1800FD21E
0x1800fd53c  mov     rax, [rdi+70h]
0x1800fd540  xor     edi, edi
0x1800fd542  mov     [r13+0], rax
0x1800fd546  neg     eax
0x1800fd548  and     eax, 3
0x1800fd54b  mov     [r13+8], eax
0x1800fd54f  test    r14, r14
0x1800fd552  jz      short loc_1800FD5B0
0x1800fd554  cmp     [r14], dil
0x1800fd557  jz      short loc_1800FD5B0
0x1800fd559  mov     r8, r15
0x1800fd55c  inc     r8
0x1800fd55f  cmp     [r14+r8], dil
0x1800fd563  jnz     short loc_1800FD55C
0x1800fd565  mov     rcx, [rsi+0E8h]
0x1800fd56c  mov     rdx, r14
0x1800fd56f  call    __archive_write_filter
0x1800fd574  test    eax, eax
0x1800fd576  jnz     loc_1800FD21E
0x1800fd57c  inc     r15
0x1800fd57f  cmp     [r14+r15], dil
0x1800fd583  jnz     short loc_1800FD57C
0x1800fd585  mov     rcx, [rsi+0E8h]
0x1800fd58c  lea     rdx, unk_1801408DC
0x1800fd593  mov     r8d, r15d
0x1800fd596  neg     r8d
0x1800fd599  and     r8d, 3
0x1800fd59d  call    __archive_write_filter
0x1800fd5a2  mov     edx, ebx
0x1800fd5a4  test    eax, eax
0x1800fd5a6  mov     ebx, 0FFFFFFE2h
0x1800fd5ab  cmovnz  edx, ebx
0x1800fd5ae  mov     ebx, edx
0x1800fd5b0  mov     rcx, r12
0x1800fd5b3  call    archive_entry_free
0x1800fd5b8  mov     eax, ebx
0x1800fd5ba  mov     rcx, [rbp+57h+var_40]
0x1800fd5be  xor     rcx, rsp; StackCookie
0x1800fd5c1  call    __security_check_cookie
0x1800fd5c6  mov     rbx, [rsp+110h+arg_10]
0x1800fd5ce  add     rsp, 0E0h
0x1800fd5d5  pop     r15
0x1800fd5d7  pop     r14
0x1800fd5d9  pop     r13
0x1800fd5db  pop     r12
0x1800fd5dd  pop     rdi
0x1800fd5de  pop     rsi
0x1800fd5df  pop     rbp
0x1800fd5e0  retn
```
