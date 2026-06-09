# write_header

- ea: `0x1800fc1fc`
- end: `0x1800fc62a`
- name: `write_header`
- size: `1070`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `reparse_path`

## callers

- `0x1800fbcc0`
- `0x1800fbe00`

## callees

- `0x180006c00`
- `0x18000e8d4`
- `0x180014fc0`
- `0x1800b0b0c`
- `0x1800b1940`
- `0x1800b1b60`
- `0x1800b1f40`
- `0x1800b2070`
- `0x1800b2770`
- `0x1800ed038`
- `0x1800ed464`
- `0x1800ef2d4`
- `0x1800efbb4`
- `0x1800fc0f0`
- `0x1800fc134`
- `0x1800fc1fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fc2b8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fc44b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fc2b8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fc44b`

## string_xrefs

- `0x1800fc2c3`: `Can't allocate memory for Pathname`
- `0x1800fc456`: `Can't allocate memory for Linkname`
- `0x1800fc2ed`: `Can't translate pathname '%s' to %s`
- `0x1800fc391`: `symbolic links cannot be represented in the PWB cpio format`
- `0x1800fc47d`: `Can't translate linkname '%s' to %s`
- `0x1800fc4b9`: `symlinks are not supported by UNIX V6 or by PWB cpio`

## pseudocode

```c
__int64 __fastcall write_header(__int64 a1, __int64 a2)
{
  __int64 *v2; // r12
  __int64 sconv; // r15
  __int64 v6; // rax
  __int64 v7; // r13
  unsigned int v9; // ebx
  const char *v10; // r8
  __int64 v11; // rdx
  const char *v12; // rbx
  const char *v13; // rax
  int v14; // eax
  __int16 v15; // ax
  __int16 v16; // r12
  __int16 v17; // ax
  __int16 v18; // ax
  int v19; // ecx
  __int64 *v20; // r12
  const char *v21; // rbx
  const char *v22; // rax
  _BYTE *v23; // r14
  __int64 v24; // r15
  __int64 v25; // rcx
  __int16 v26; // eax^2
  __int64 v27; // rcx
  char v28; // si
  __int64 v29; // rax
  __int64 *v30; // rcx
  __int64 v31; // r8
  __int64 v32; // [rsp+30h] [rbp-50h] BYREF
  int v33; // [rsp+38h] [rbp-48h]
  _BYTE *v34; // [rsp+40h] [rbp-40h] BYREF
  __int64 v35; // [rsp+48h] [rbp-38h] BYREF
  __int64 *v36; // [rsp+50h] [rbp-30h]
  _OWORD v37[2]; // [rsp+58h] [rbp-28h] BYREF

  v2 = *(__int64 **)(a1 + 248);
  v36 = v2;
  memset(v37, 0, 26);
  v34 = 0;
  v35 = 0;
  v32 = 0;
  sconv = get_sconv();
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
                       (unsigned int)&v35,
                       (unsigned int)&v32,
                       sconv) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      v10 = "Can't allocate memory for Pathname";
LABEL_9:
      v11 = 12;
LABEL_61:
      archive_set_error(a1, v11, v10);
      goto LABEL_62;
    }
    v12 = (const char *)archive_string_conversion_charset_name(sconv);
    v13 = (const char *)archive_entry_pathname(a2);
    archive_set_error(a1, 42, "Can't translate pathname '%s' to %s", v13, v12);
    v9 = -20;
  }
  LOWORD(v37[0]) = 29127;
  WORD1(v37[0]) = archive_entry_dev(a2);
  v14 = synthesize_ino_value(v2, a2);
  if ( v14 < 0 )
  {
    v10 = "No memory for ino translation table";
    goto LABEL_9;
  }
  if ( v14 > 0x7FFF )
  {
    archive_set_error(a1, 34, "Too many files for this cpio format");
LABEL_62:
    v9 = -30;
    goto LABEL_63;
  }
  WORD2(v37[0]) = v14;
  WORD3(v37[0]) = *(_WORD *)(a2 + 1032);
  v15 = WORD3(v37[0]) & 0xF000;
  if ( (WORD3(v37[0]) & 0xF000) == 0xC000 || v15 == 4096 )
  {
    v10 = "sockets and fifos cannot be represented in the binary cpio formats";
    goto LABEL_60;
  }
  if ( *(_DWORD *)(a1 + 16) == 65543 && v15 == -24576 )
  {
    v10 = "symbolic links cannot be represented in the PWB cpio format";
LABEL_60:
    v11 = 22;
    goto LABEL_61;
  }
  WORD4(v37[0]) = *(_WORD *)(a2 + 120);
  v16 = v32 + 1;
  WORD5(v37[0]) = *(_WORD *)(a2 + 88);
  WORD6(v37[0]) = *(_WORD *)(a2 + 104);
  v17 = *(_WORD *)(a2 + 1032);
  v33 = v32 + 1;
  if ( (((v17 & 0xF000) - 0x2000) & 0xBFFF) != 0 )
    v18 = 0;
  else
    v18 = archive_entry_rdev(a2);
  HIWORD(v37[0]) = v18;
  v19 = *(_DWORD *)(a2 + 56);
  LOWORD(v37[1]) = HIWORD(v19);
  WORD1(v37[1]) = v19;
  WORD2(v37[1]) = v16;
  v20 = (__int64 *)(a2 + 112);
  if ( (*(_WORD *)(a2 + 1032) & 0xF000) != 0x8000 )
  {
    *(_DWORD *)(a2 + 160) |= 0x40u;
    *(_DWORD *)(a2 + 16) = 0;
    *v20 = 0;
  }
  if ( (unsigned int)archive_entry_symlink_l(a2, &v34, &v32, sconv) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      v10 = "Can't allocate memory for Linkname";
      goto LABEL_9;
    }
    v21 = (const char *)archive_string_conversion_charset_name(sconv);
    v22 = (const char *)archive_entry_symlink(a2);
    archive_set_error(a1, 42, "Can't translate linkname '%s' to %s", v22, v21);
    v9 = -20;
  }
  v23 = v34;
  v24 = -1;
  if ( v32 && v34 && *v34 )
  {
    if ( *(_DWORD *)(a1 + 16) == 65543 )
    {
      v10 = "symlinks are not supported by UNIX V6 or by PWB cpio";
      goto LABEL_60;
    }
    v25 = -1;
    do
      ++v25;
    while ( v34[v25] );
LABEL_44:
    v26 = WORD1(v25);
    WORD4(v37[1]) = v25;
    v27 = *(_QWORD *)(a1 + 232);
    WORD3(v37[1]) = v26;
    if ( !(unsigned int)_archive_write_filter(v27, v37, 26) )
    {
      v28 = v33;
      if ( !(unsigned int)_archive_write_filter(*(_QWORD *)(a1 + 232), v35, v33)
        && ((v28 & 1) == 0 || !(unsigned int)_archive_write_nulls(a1, 1)) )
      {
        v29 = *v20;
        v30 = v36;
        *v36 = *v20;
        if ( (v29 & 1) != 0 )
          *v30 = v29 + 1;
        if ( !v23 || !*v23 )
          goto LABEL_63;
        v31 = -1;
        do
          ++v31;
        while ( v23[v31] );
        if ( !(unsigned int)_archive_write_filter(*(_QWORD *)(a1 + 232), v23, v31) )
        {
          do
            ++v24;
          while ( v23[v24] );
          if ( (v24 & 1) == 0 || !(unsigned int)_archive_write_nulls(a1, 1) )
            goto LABEL_63;
        }
      }
    }
    goto LABEL_62;
  }
  v25 = a2 + 112;
  if ( *(_DWORD *)(a1 + 16) == 65543 && (v25 = a2 + 112, *(__int64 *)(a2 + 112) > 0xFFFFFF) )
  {
    archive_set_error(a1, 34, "File is too large for PWB binary cpio format.");
  }
  else
  {
    if ( *(__int64 *)v25 <= 0x7FFFFFFF )
    {
      LODWORD(v25) = *(_DWORD *)v25;
      goto LABEL_44;
    }
    archive_set_error(a1, 34, "File is too large for binary cpio format.");
  }
  v9 = -25;
LABEL_63:
  archive_entry_free(v7);
  return v9;
}

```

## disassembly

```asm
0x1800fc1fc  mov     [rsp-38h+arg_10], rbx
0x1800fc201  push    rbp
0x1800fc202  push    rsi
0x1800fc203  push    rdi
0x1800fc204  push    r12
0x1800fc206  push    r13
0x1800fc208  push    r14
0x1800fc20a  push    r15
0x1800fc20c  mov     rbp, rsp
0x1800fc20f  sub     rsp, 80h
0x1800fc216  mov     rax, cs:__security_cookie
0x1800fc21d  xor     rax, rsp
0x1800fc220  mov     [rbp+var_8], rax
0x1800fc224  mov     r12, [rcx+0F8h]
0x1800fc22b  xorps   xmm0, xmm0
0x1800fc22e  xor     r14d, r14d
0x1800fc231  mov     [rbp+var_30], r12
0x1800fc235  movups  [rbp+var_28], xmm0
0x1800fc239  mov     rsi, rdx
0x1800fc23c  mov     rdi, rcx
0x1800fc23f  movups  [rbp+var_28+0Ah], xmm0
0x1800fc243  mov     [rbp+var_40], r14
0x1800fc247  mov     [rbp+var_38], r14
0x1800fc24b  mov     [rbp+var_50], r14
0x1800fc24f  call    get_sconv
0x1800fc254  mov     rcx, rsi
0x1800fc257  mov     r15, rax
0x1800fc25a  call    __la_win_entry_in_posix_pathseparator
0x1800fc25f  mov     r13, rax
0x1800fc262  test    rax, rax
0x1800fc265  jnz     short loc_1800FC282
0x1800fc267  lea     r8, aCanTAllocateUs; "Can't allocate ustar data"
0x1800fc26e  mov     rcx, rdi
0x1800fc271  lea     edx, [rax+0Ch]
0x1800fc274  call    archive_set_error
0x1800fc279  lea     eax, [r14-1Eh]
0x1800fc27d  jmp     loc_1800FC603
0x1800fc282  mov     ebx, r14d
0x1800fc285  cmp     rsi, rax
0x1800fc288  jz      short loc_1800FC28F
0x1800fc28a  mov     rsi, rax
0x1800fc28d  jmp     short loc_1800FC292
0x1800fc28f  mov     r13, r14
0x1800fc292  mov     rcx, [rsi]
0x1800fc295  lea     rdx, [rsi+1E8h]
0x1800fc29c  lea     r9, [rbp+var_50]
0x1800fc2a0  mov     [rsp+80h+var_60], r15
0x1800fc2a5  lea     r8, [rbp+var_38]
0x1800fc2a9  call    archive_mstring_get_mbs_l
0x1800fc2ae  mov     r14d, 0Ch
0x1800fc2b4  test    eax, eax
0x1800fc2b6  jz      short loc_1800FC306
0x1800fc2b8  call    cs:__imp__o__errno
0x1800fc2be  cmp     [rax], r14d
0x1800fc2c1  jnz     short loc_1800FC2D2
0x1800fc2c3  lea     r8, aCanTAllocateMe_24; "Can't allocate memory for Pathname"
0x1800fc2ca  mov     edx, r14d
0x1800fc2cd  jmp     loc_1800FC5EC
0x1800fc2d2  mov     rcx, r15
0x1800fc2d5  call    archive_string_conversion_charset_name
0x1800fc2da  mov     rcx, rsi
0x1800fc2dd  mov     rbx, rax
0x1800fc2e0  call    archive_entry_pathname
0x1800fc2e5  mov     r9, rax
0x1800fc2e8  mov     [rsp+80h+var_60], rbx
0x1800fc2ed  lea     r8, aCanTTranslateP; "Can't translate pathname '%s' to %s"
0x1800fc2f4  mov     edx, 2Ah ; '*'
0x1800fc2f9  mov     rcx, rdi
0x1800fc2fc  call    archive_set_error
0x1800fc301  mov     ebx, 0FFFFFFECh
0x1800fc306  mov     eax, 71C7h
0x1800fc30b  mov     rcx, rsi
0x1800fc30e  mov     word ptr [rbp+var_28], ax
0x1800fc312  call    archive_entry_dev
0x1800fc317  mov     rdx, rsi
0x1800fc31a  mov     word ptr [rbp+var_28+2], ax
0x1800fc31e  mov     rcx, r12
0x1800fc321  call    synthesize_ino_value
0x1800fc326  test    eax, eax
0x1800fc328  jns     short loc_1800FC333
0x1800fc32a  lea     r8, aNoMemoryForIno; "No memory for ino translation table"
0x1800fc331  jmp     short loc_1800FC2CA
0x1800fc333  cmp     eax, 7FFFh
0x1800fc338  jle     short loc_1800FC34B
0x1800fc33a  lea     r8, aTooManyFilesFo; "Too many files for this cpio format"
0x1800fc341  mov     edx, 22h ; '"'
0x1800fc346  jmp     loc_1800FC5EC
0x1800fc34b  mov     word ptr [rbp+var_28+4], ax
0x1800fc34f  mov     edx, 0F000h
0x1800fc354  movzx   eax, word ptr [rsi+408h]
0x1800fc35b  mov     ecx, 0C000h
0x1800fc360  mov     word ptr [rbp+var_28+6], ax
0x1800fc364  and     ax, dx
0x1800fc367  cmp     ax, cx
0x1800fc36a  jz      loc_1800FC5E0
0x1800fc370  mov     ecx, 1000h
0x1800fc375  cmp     ax, cx
0x1800fc378  jz      loc_1800FC5E0
0x1800fc37e  cmp     dword ptr [rdi+10h], 10007h
0x1800fc385  jnz     short loc_1800FC39D
0x1800fc387  mov     ecx, 0A000h
0x1800fc38c  cmp     ax, cx
0x1800fc38f  jnz     short loc_1800FC39D
0x1800fc391  lea     r8, aSymbolicLinksC; "symbolic links cannot be represented in"...
0x1800fc398  jmp     loc_1800FC5E7
0x1800fc39d  movzx   eax, word ptr [rsi+78h]
0x1800fc3a1  mov     ecx, 2000h
0x1800fc3a6  mov     r12d, dword ptr [rbp+var_50]
0x1800fc3aa  mov     word ptr [rbp+var_28+8], ax
0x1800fc3ae  inc     r12d
0x1800fc3b1  movzx   eax, word ptr [rsi+58h]
0x1800fc3b5  mov     word ptr [rbp+var_28+0Ah], ax
0x1800fc3b9  movzx   eax, word ptr [rsi+68h]
0x1800fc3bd  mov     word ptr [rbp+var_28+0Ch], ax
0x1800fc3c1  movzx   eax, word ptr [rsi+408h]
0x1800fc3c8  and     ax, dx
0x1800fc3cb  mov     [rbp+var_48], r12d
0x1800fc3cf  sub     ax, cx
0x1800fc3d2  mov     ecx, 0BFFFh
0x1800fc3d7  test    cx, ax
0x1800fc3da  jz      short loc_1800FC3E0
0x1800fc3dc  xor     eax, eax
0x1800fc3de  jmp     short loc_1800FC3ED
0x1800fc3e0  mov     rcx, rsi
0x1800fc3e3  call    archive_entry_rdev
0x1800fc3e8  mov     edx, 0F000h
0x1800fc3ed  mov     word ptr [rbp+var_28+0Eh], ax
0x1800fc3f1  mov     ecx, [rsi+38h]
0x1800fc3f4  mov     eax, ecx
0x1800fc3f6  shr     eax, 10h
0x1800fc3f9  mov     [rbp+var_18], ax
0x1800fc3fd  mov     [rbp+var_16], cx
0x1800fc401  mov     ecx, 8000h
0x1800fc406  mov     [rbp+var_14], r12w
0x1800fc40b  lea     r12, [rsi+70h]
0x1800fc40f  movzx   eax, word ptr [rsi+408h]
0x1800fc416  and     ax, dx
0x1800fc419  cmp     ax, cx
0x1800fc41c  jz      short loc_1800FC434
0x1800fc41e  or      dword ptr [rsi+0A0h], 40h
0x1800fc425  mov     dword ptr [rsi+10h], 0
0x1800fc42c  mov     qword ptr [r12], 0
0x1800fc434  mov     r9, r15
0x1800fc437  lea     r8, [rbp+var_50]
0x1800fc43b  lea     rdx, [rbp+var_40]
0x1800fc43f  mov     rcx, rsi
0x1800fc442  call    _archive_entry_symlink_l
0x1800fc447  test    eax, eax
0x1800fc449  jz      short loc_1800FC496
0x1800fc44b  call    cs:__imp__o__errno
0x1800fc451  cmp     [rax], r14d
0x1800fc454  jnz     short loc_1800FC462
0x1800fc456  lea     r8, aCanTAllocateMe_15; "Can't allocate memory for Linkname"
0x1800fc45d  jmp     loc_1800FC2CA
0x1800fc462  mov     rcx, r15
0x1800fc465  call    archive_string_conversion_charset_name
0x1800fc46a  mov     rcx, rsi
0x1800fc46d  mov     rbx, rax
0x1800fc470  call    archive_entry_symlink
0x1800fc475  mov     r9, rax
0x1800fc478  mov     [rsp+80h+var_60], rbx
0x1800fc47d  lea     r8, aCanTTranslateL; "Can't translate linkname '%s' to %s"
0x1800fc484  mov     edx, 2Ah ; '*'
0x1800fc489  mov     rcx, rdi
0x1800fc48c  call    archive_set_error
0x1800fc491  mov     ebx, 0FFFFFFECh
0x1800fc496  mov     r14, [rbp+var_40]
0x1800fc49a  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800fc49e  xor     eax, eax
0x1800fc4a0  cmp     [rbp+var_50], rax
0x1800fc4a4  jbe     short loc_1800FC4D3
0x1800fc4a6  test    r14, r14
0x1800fc4a9  jz      short loc_1800FC4D3
0x1800fc4ab  cmp     [r14], al
0x1800fc4ae  jz      short loc_1800FC4D3
0x1800fc4b0  cmp     dword ptr [rdi+10h], 10007h
0x1800fc4b7  jnz     short loc_1800FC4C5
0x1800fc4b9  lea     r8, aSymlinksAreNot; "symlinks are not supported by UNIX V6 o"...
0x1800fc4c0  jmp     loc_1800FC5E7
0x1800fc4c5  mov     rcx, r15
0x1800fc4c8  inc     rcx
0x1800fc4cb  cmp     [r14+rcx], al
0x1800fc4cf  jnz     short loc_1800FC4C8
0x1800fc4d1  jmp     short loc_1800FC51E
0x1800fc4d3  cmp     dword ptr [rdi+10h], 10007h
0x1800fc4da  mov     rcx, r12
0x1800fc4dd  jnz     short loc_1800FC50A
0x1800fc4df  lea     rcx, [rsi+70h]
0x1800fc4e3  cmp     qword ptr [rcx], 0FFFFFFh
0x1800fc4ea  jle     short loc_1800FC50A
0x1800fc4ec  lea     r8, aFileIsTooLarge_1; "File is too large for PWB binary cpio f"...
0x1800fc4f3  mov     edx, 22h ; '"'
0x1800fc4f8  mov     rcx, rdi
0x1800fc4fb  call    archive_set_error
0x1800fc500  mov     ebx, 0FFFFFFE7h
0x1800fc505  jmp     loc_1800FC5F9
0x1800fc50a  cmp     qword ptr [rcx], 7FFFFFFFh
0x1800fc511  jle     short loc_1800FC51C
0x1800fc513  lea     r8, aFileIsTooLarge; "File is too large for binary cpio forma"...
0x1800fc51a  jmp     short loc_1800FC4F3
0x1800fc51c  mov     ecx, [rcx]
0x1800fc51e  mov     eax, ecx
0x1800fc520  mov     [rbp+var_10], cx
0x1800fc524  mov     rcx, [rdi+0E8h]
0x1800fc52b  lea     rdx, [rbp+var_28]
0x1800fc52f  shr     eax, 10h
0x1800fc532  mov     r8d, 1Ah
0x1800fc538  mov     [rbp+var_12], ax
0x1800fc53c  call    __archive_write_filter
0x1800fc541  test    eax, eax
0x1800fc543  jnz     loc_1800FC5F4
0x1800fc549  movsxd  rsi, [rbp+var_48]
0x1800fc54d  mov     rdx, [rbp+var_38]
0x1800fc551  mov     r8, rsi
0x1800fc554  mov     rcx, [rdi+0E8h]
0x1800fc55b  call    __archive_write_filter
0x1800fc560  test    eax, eax
0x1800fc562  jnz     loc_1800FC5F4
0x1800fc568  test    sil, 1
0x1800fc56c  jz      short loc_1800FC57D
0x1800fc56e  lea     edx, [rax+1]
0x1800fc571  mov     rcx, rdi
0x1800fc574  call    __archive_write_nulls
0x1800fc579  test    eax, eax
0x1800fc57b  jnz     short loc_1800FC5F4
0x1800fc57d  mov     rax, [r12]
0x1800fc581  mov     rcx, [rbp+var_30]
0x1800fc585  mov     [rcx], rax
0x1800fc588  test    al, 1
0x1800fc58a  jz      short loc_1800FC592
0x1800fc58c  inc     rax
0x1800fc58f  mov     [rcx], rax
0x1800fc592  test    r14, r14
0x1800fc595  jz      short loc_1800FC5F9
0x1800fc597  cmp     byte ptr [r14], 0
0x1800fc59b  jz      short loc_1800FC5F9
0x1800fc59d  mov     r8, r15
0x1800fc5a0  inc     r8
0x1800fc5a3  cmp     byte ptr [r14+r8], 0
0x1800fc5a8  jnz     short loc_1800FC5A0
0x1800fc5aa  mov     rcx, [rdi+0E8h]
0x1800fc5b1  mov     rdx, r14
0x1800fc5b4  call    __archive_write_filter
0x1800fc5b9  test    eax, eax
0x1800fc5bb  jnz     short loc_1800FC5F4
0x1800fc5bd  inc     r15
0x1800fc5c0  cmp     byte ptr [r14+r15], 0
0x1800fc5c5  jnz     short loc_1800FC5BD
0x1800fc5c7  test    r15b, 1
0x1800fc5cb  jz      short loc_1800FC5F9
0x1800fc5cd  mov     edx, 1
0x1800fc5d2  mov     rcx, rdi
0x1800fc5d5  call    __archive_write_nulls
0x1800fc5da  test    eax, eax
0x1800fc5dc  jz      short loc_1800FC5F9
0x1800fc5de  jmp     short loc_1800FC5F4
0x1800fc5e0  lea     r8, aSocketsAndFifo; "sockets and fifos cannot be represented"...
0x1800fc5e7  mov     edx, 16h
0x1800fc5ec  mov     rcx, rdi
0x1800fc5ef  call    archive_set_error
0x1800fc5f4  mov     ebx, 0FFFFFFE2h
0x1800fc5f9  mov     rcx, r13
0x1800fc5fc  call    archive_entry_free
0x1800fc601  mov     eax, ebx
0x1800fc603  mov     rcx, [rbp+var_8]
0x1800fc607  xor     rcx, rsp; StackCookie
0x1800fc60a  call    __security_check_cookie
0x1800fc60f  mov     rbx, [rsp+80h+arg_10]
0x1800fc617  add     rsp, 80h
0x1800fc61e  pop     r15
0x1800fc620  pop     r14
0x1800fc622  pop     r13
0x1800fc624  pop     r12
0x1800fc626  pop     rdi
0x1800fc627  pop     rsi
0x1800fc628  pop     rbp
0x1800fc629  retn
```
