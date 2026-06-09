# xar_read_header

- ea: `0x1800e5340`
- end: `0x1800e5941`
- name: `xar_read_header`
- size: `1537`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180006c00`
- `0x18000c0ec`
- `0x18000e764`
- `0x18000e920`
- `0x18000e9a0`
- `0x18000ea00`
- `0x1800148e0`
- `0x1800b0a70`
- `0x1800b1580`
- `0x1800b23b0`
- `0x1800b3930`
- `0x1800e3bdc`
- `0x1800e415c`
- `0x1800e45a0`
- `0x1800e4688`
- `0x1800e4838`
- `0x1800e4910`
- `0x1800e4970`
- `0x1800e5340`
- `0x1800ed464`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e54a1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e5536`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e55b6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e561b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e54a1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e5536`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e55b6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800e561b`

## string_xrefs

- `0x1800e55c1`: `Can't allocate memory for Pathname`
- `0x1800e55dc`: `Pathname cannot be converted from %s to current locale.`
- `0x1800e5626`: `Can't allocate memory for Linkname`
- `0x1800e5641`: `Linkname cannot be converted from %s to current locale.`
- `0x1800e58db`: `Decompressed size error`

## pseudocode

```c
__int64 __fastcall xar_read_header(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rax
  unsigned int v5; // ebx
  _QWORD *v6; // r15
  __int64 v7; // rax
  __int64 result; // rax
  __int64 entry_0; // rax
  __int64 v10; // rdi
  _DWORD *v11; // r14
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r8
  const char *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // r8
  const char *v19; // rax
  __int16 v20; // ax
  const char *v21; // rax
  __int64 v22; // r8
  const char *v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 **i; // r14
  __int64 *v30; // rdx
  __int64 *v31; // r12
  __int64 *v32; // rdx
  __int64 v33; // [rsp+20h] [rbp-48h]
  __int64 *v34; // [rsp+70h] [rbp+8h] BYREF
  __int64 v35; // [rsp+80h] [rbp+18h] BYREF
  __int64 v36; // [rsp+88h] [rbp+20h] BYREF

  v2 = *(_QWORD **)(a1 + 2072);
  v5 = 0;
  v6 = (_QWORD *)*v2;
  if ( *(_QWORD *)*v2 )
  {
    while ( 1 )
    {
LABEL_6:
      entry_0 = heap_get_entry_0(v6 + 70);
      v6[68] = entry_0;
      v10 = entry_0;
      if ( !entry_0 )
      {
        *((_DWORD *)v6 + 6) = 1;
        return 1;
      }
      v11 = (_DWORD *)(entry_0 + 28);
      if ( (*(_WORD *)(entry_0 + 288) & 0xF000) != 0x4000 || *v11 != 130 )
        break;
      file_free(entry_0);
    }
    if ( (*v11 & 0x20000) != 0 )
      archive_entry_set_atime(a2, *(_QWORD *)(entry_0 + 216), 0);
    if ( (*v11 & 0x8000) != 0 )
      archive_entry_set_ctime(a2, *(_QWORD *)(v10 + 200), 0);
    if ( (*v11 & 0x10000) != 0 )
      archive_entry_set_mtime(a2, *(_QWORD *)(v10 + 208), 0);
    v12 = *(_QWORD *)(v10 + 280);
    v13 = 0;
    *(_DWORD *)(a2 + 16) = 0;
    if ( v12 >= 0 )
      v13 = v12;
    *(_DWORD *)(a2 + 160) |= 0x1000u;
    *(_QWORD *)(a2 + 88) = v13;
    v14 = *(_QWORD *)(v10 + 264);
    if ( v14 && (unsigned int)archive_mstring_copy_mbs_len_l(a2 + 280, *(_QWORD *)(v10 + 256), v14, v6[90]) )
    {
      if ( *(_DWORD *)_o__errno() == 12 )
      {
        archive_set_error(a1, 12, "Can't allocate memory for Gname");
        return 4294967266LL;
      }
      v15 = (const char *)archive_string_conversion_charset_name(v6[90]);
      archive_set_error(a1, 42, "Gname cannot be converted from %s to current locale.", v15);
      v5 = -20;
    }
    v16 = *(_QWORD *)(v10 + 248);
    v17 = 0;
    *(_DWORD *)(a2 + 16) = 0;
    if ( v16 >= 0 )
      v17 = v16;
    *(_DWORD *)(a2 + 160) |= 0x800u;
    *(_QWORD *)(a2 + 120) = v17;
    v18 = *(_QWORD *)(v10 + 232);
    if ( v18 && (unsigned int)archive_mstring_copy_mbs_len_l(a2 + 592, *(_QWORD *)(v10 + 224), v18, v6[90]) )
    {
      if ( *(_DWORD *)_o__errno() == 12 )
      {
        archive_set_error(a1, 12, "Can't allocate memory for Uname");
        return 4294967266LL;
      }
      v19 = (const char *)archive_string_conversion_charset_name(v6[90]);
      archive_set_error(a1, 42, "Uname cannot be converted from %s to current locale.", v19);
      v5 = -20;
    }
    v20 = *(_WORD *)(v10 + 288);
    *(_DWORD *)(a2 + 160) |= 0x600u;
    *(_WORD *)(a2 + 1032) = v20;
    *(_DWORD *)(a2 + 16) = 0;
    if ( (unsigned int)archive_mstring_copy_mbs_len_l(a2 + 488, *(_QWORD *)(v10 + 152), *(_QWORD *)(v10 + 160), v6[90]) )
    {
      if ( *(_DWORD *)_o__errno() == 12 )
      {
        archive_set_error(a1, 12, "Can't allocate memory for Pathname");
        return 4294967266LL;
      }
      v21 = (const char *)archive_string_conversion_charset_name(v6[90]);
      archive_set_error(a1, 42, "Pathname cannot be converted from %s to current locale.", v21);
      v5 = -20;
    }
    v22 = *(_QWORD *)(v10 + 184);
    if ( v22 && (unsigned int)archive_entry_copy_symlink_l(a2, *(_QWORD *)(v10 + 176), v22, v6[90]) )
    {
      if ( *(_DWORD *)_o__errno() == 12 )
      {
        archive_set_error(a1, 12, "Can't allocate memory for Linkname");
        return 4294967266LL;
      }
      v23 = (const char *)archive_string_conversion_charset_name(v6[90]);
      archive_set_error(a1, 42, "Linkname cannot be converted from %s to current locale.", v23);
      v5 = -20;
    }
    if ( (*(_WORD *)(v10 + 288) & 0xF000) == 0x4000 )
      v24 = *(_DWORD *)(v10 + 24) + 2;
    else
      v24 = *(_DWORD *)(v10 + 340);
    *(_DWORD *)(a2 + 16) = 0;
    *(_DWORD *)(a2 + 104) = v24;
    v25 = 0;
    if ( *(__int64 *)(v10 + 56) >= 0 )
      v25 = *(_QWORD *)(v10 + 56);
    *(_DWORD *)(a2 + 160) |= 0x40u;
    *(_QWORD *)(a2 + 112) = v25;
    if ( *(_QWORD *)(v10 + 352) )
      archive_entry_set_hardlink(a2, *(_QWORD *)(v10 + 344));
    archive_entry_set_ino64(a2, *(_QWORD *)(v10 + 304));
    if ( (*v11 & 0x100) != 0 )
    {
      v26 = *(_DWORD *)(v10 + 292);
      *(_DWORD *)(a2 + 160) |= 0x100u;
      *(_DWORD *)(a2 + 16) = 0;
      *(_DWORD *)(a2 + 128) = 0;
      *(_DWORD *)(a2 + 132) = v26;
    }
    if ( (*v11 & 0x200) != 0 )
    {
      v27 = *(_DWORD *)(v10 + 296);
      *(_DWORD *)(a2 + 160) |= 0x100u;
      *(_DWORD *)(a2 + 16) = 0;
      *(_DWORD *)(a2 + 128) = 1;
      *(_DWORD *)(a2 + 136) = v27;
    }
    if ( (*v11 & 0x400) != 0 )
    {
      v28 = *(_DWORD *)(v10 + 300);
      *(_DWORD *)(a2 + 160) |= 0x100u;
      *(_DWORD *)(a2 + 16) = 0;
      *(_DWORD *)(a2 + 128) = 1;
      *(_DWORD *)(a2 + 140) = v28;
    }
    if ( *(_QWORD *)(v10 + 320) )
      archive_entry_copy_fflags_text(a2, *(_QWORD *)(v10 + 312));
    *((_DWORD *)v6 + 148) = 1;
    v6[75] = 0;
    v6[76] = *(_QWORD *)(v10 + 40);
    v6[78] = *(_QWORD *)(v10 + 56);
    *((_DWORD *)v6 + 158) = *(_DWORD *)(v10 + 64);
    *((_OWORD *)v6 + 40) = *(_OWORD *)(v10 + 72);
    *((_OWORD *)v6 + 41) = *(_OWORD *)(v10 + 88);
    v6[84] = *(_QWORD *)(v10 + 104);
    *(_OWORD *)(v6 + 85) = *(_OWORD *)(v10 + 112);
    *(_OWORD *)(v6 + 87) = *(_OWORD *)(v10 + 128);
    v6[89] = *(_QWORD *)(v10 + 144);
    for ( i = *(__int64 ***)(v10 + 368); i; i = (__int64 **)*i )
    {
      v30 = i[6];
      v34 = 0;
      v36 = 0;
      v5 = move_reading_point(a1, v30);
      if ( v5 )
        goto LABEL_69;
      v5 = rd_contents_init(a1, *((unsigned int *)i + 16), *((unsigned int *)i + 18), *((unsigned int *)i + 28));
      if ( v5 )
        goto LABEL_69;
      v33 = (__int64)i[5];
      v35 = 0;
      v5 = rd_contents(a1, (unsigned int)&v35, (unsigned int)&v34, (unsigned int)&v36, v33);
      if ( v5 )
        goto LABEL_69;
      v31 = v34;
      if ( v34 != i[7] )
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "Decompressed size error");
        v5 = -30;
        goto LABEL_69;
      }
      v5 = checksum_final(a1, (int)i + 88, (unsigned int)i[10], (int)i + 128, (__int64)i[15]);
      if ( v5 )
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "Xattr checksum error");
        goto LABEL_66;
      }
      v32 = i[1];
      if ( !v32 )
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "Xattr name error");
LABEL_66:
        v5 = -20;
        goto LABEL_69;
      }
      archive_entry_xattr_add_entry(a2, v32, v35, v31);
    }
    if ( !v5 )
    {
      if ( v6[76] )
        v5 = move_reading_point(a1, *(_QWORD *)(v10 + 48));
      else
        v5 = 0;
    }
LABEL_69:
    file_free(v10);
    return v5;
  }
  else if ( v6[90] || (v7 = archive_string_conversion_from_charset(a1, "UTF-8", 1), (v6[90] = v7) != 0) )
  {
    result = read_toc(a1);
    v5 = result;
    if ( !(_DWORD)result )
      goto LABEL_6;
  }
  else
  {
    return 4294967266LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800e5340  mov     [rsp+arg_8], rbx
0x1800e5345  push    rbp
0x1800e5346  push    rsi
0x1800e5347  push    rdi
0x1800e5348  push    r12
0x1800e534a  push    r13
0x1800e534c  push    r14
0x1800e534e  push    r15
0x1800e5350  sub     rsp, 30h
0x1800e5354  mov     rax, [rcx+818h]
0x1800e535b  xor     r13d, r13d
0x1800e535e  mov     rsi, rdx
0x1800e5361  mov     rbp, rcx
0x1800e5364  mov     ebx, r13d
0x1800e5367  mov     r15, [rax]
0x1800e536a  cmp     [r15], r13
0x1800e536d  jnz     short loc_1800E53B0
0x1800e536f  cmp     [r15+2D0h], r13
0x1800e5376  jnz     short loc_1800E539E
0x1800e5378  lea     r8d, [r13+1]
0x1800e537c  lea     rdx, Str2; "UTF-8"
0x1800e5383  call    archive_string_conversion_from_charset
0x1800e5388  mov     [r15+2D0h], rax
0x1800e538f  test    rax, rax
0x1800e5392  jnz     short loc_1800E539E
0x1800e5394  mov     eax, 0FFFFFFE2h
0x1800e5399  jmp     loc_1800E592C
0x1800e539e  mov     rcx, rbp
0x1800e53a1  call    read_toc
0x1800e53a6  mov     ebx, eax
0x1800e53a8  test    eax, eax
0x1800e53aa  jnz     loc_1800E592C
0x1800e53b0  lea     rcx, [r15+230h]
0x1800e53b7  call    heap_get_entry_0
0x1800e53bc  mov     [r15+220h], rax
0x1800e53c3  mov     rdi, rax
0x1800e53c6  test    rax, rax
0x1800e53c9  jz      loc_1800E591F
0x1800e53cf  lea     r14, [rax+1Ch]
0x1800e53d3  mov     ecx, 0F000h
0x1800e53d8  movzx   eax, word ptr [rax+120h]
0x1800e53df  and     ax, cx
0x1800e53e2  mov     ecx, 4000h
0x1800e53e7  cmp     ax, cx
0x1800e53ea  jnz     short loc_1800E53FF
0x1800e53ec  cmp     dword ptr [r14], 82h
0x1800e53f3  jnz     short loc_1800E53FF
0x1800e53f5  mov     rcx, rdi
0x1800e53f8  call    file_free
0x1800e53fd  jmp     short loc_1800E53B0
0x1800e53ff  test    dword ptr [r14], 20000h
0x1800e5406  jz      short loc_1800E541A
0x1800e5408  mov     rdx, [rdi+0D8h]
0x1800e540f  xor     r8d, r8d
0x1800e5412  mov     rcx, rsi
0x1800e5415  call    archive_entry_set_atime
0x1800e541a  test    dword ptr [r14], 8000h
0x1800e5421  jz      short loc_1800E5435
0x1800e5423  mov     rdx, [rdi+0C8h]
0x1800e542a  xor     r8d, r8d
0x1800e542d  mov     rcx, rsi
0x1800e5430  call    archive_entry_set_ctime
0x1800e5435  test    dword ptr [r14], 10000h
0x1800e543c  jz      short loc_1800E5450
0x1800e543e  mov     rdx, [rdi+0D0h]
0x1800e5445  xor     r8d, r8d
0x1800e5448  mov     rcx, rsi
0x1800e544b  call    archive_entry_set_mtime
0x1800e5450  mov     rcx, [rdi+118h]
0x1800e5457  mov     rax, r13
0x1800e545a  test    rcx, rcx
0x1800e545d  mov     [rsi+10h], r13d
0x1800e5461  mov     r12d, 0Ch
0x1800e5467  cmovns  rax, rcx
0x1800e546b  bts     dword ptr [rsi+0A0h], 0Ch
0x1800e5473  mov     [rsi+58h], rax
0x1800e5477  mov     r8, [rdi+108h]
0x1800e547e  test    r8, r8
0x1800e5481  jz      short loc_1800E54EB
0x1800e5483  mov     r9, [r15+2D0h]
0x1800e548a  lea     rcx, [rsi+118h]
0x1800e5491  mov     rdx, [rdi+100h]
0x1800e5498  call    archive_mstring_copy_mbs_len_l
0x1800e549d  test    eax, eax
0x1800e549f  jz      short loc_1800E54EB
0x1800e54a1  call    cs:__imp__o__errno
0x1800e54a7  cmp     [rax], r12d
0x1800e54aa  jnz     short loc_1800E54C3
0x1800e54ac  lea     r8, aCanTAllocateMe_9; "Can't allocate memory for Gname"
0x1800e54b3  mov     edx, r12d
0x1800e54b6  mov     rcx, rbp
0x1800e54b9  call    archive_set_error
0x1800e54be  jmp     loc_1800E5394
0x1800e54c3  mov     rcx, [r15+2D0h]
0x1800e54ca  call    archive_string_conversion_charset_name
0x1800e54cf  mov     r9, rax
0x1800e54d2  lea     r8, aGnameCannotBeC; "Gname cannot be converted from %s to cu"...
0x1800e54d9  mov     edx, 2Ah ; '*'
0x1800e54de  mov     rcx, rbp
0x1800e54e1  call    archive_set_error
0x1800e54e6  mov     ebx, 0FFFFFFECh
0x1800e54eb  mov     rcx, [rdi+0F8h]
0x1800e54f2  mov     rax, r13
0x1800e54f5  test    rcx, rcx
0x1800e54f8  mov     [rsi+10h], r13d
0x1800e54fc  cmovns  rax, rcx
0x1800e5500  bts     dword ptr [rsi+0A0h], 0Bh
0x1800e5508  mov     [rsi+78h], rax
0x1800e550c  mov     r8, [rdi+0E8h]
0x1800e5513  test    r8, r8
0x1800e5516  jz      short loc_1800E5575
0x1800e5518  mov     r9, [r15+2D0h]
0x1800e551f  lea     rcx, [rsi+250h]
0x1800e5526  mov     rdx, [rdi+0E0h]
0x1800e552d  call    archive_mstring_copy_mbs_len_l
0x1800e5532  test    eax, eax
0x1800e5534  jz      short loc_1800E5575
0x1800e5536  call    cs:__imp__o__errno
0x1800e553c  cmp     [rax], r12d
0x1800e553f  jnz     short loc_1800E554D
0x1800e5541  lea     r8, aCanTAllocateMe_22; "Can't allocate memory for Uname"
0x1800e5548  jmp     loc_1800E54B3
0x1800e554d  mov     rcx, [r15+2D0h]
0x1800e5554  call    archive_string_conversion_charset_name
0x1800e5559  mov     r9, rax
0x1800e555c  lea     r8, aUnameCannotBeC; "Uname cannot be converted from %s to cu"...
0x1800e5563  mov     edx, 2Ah ; '*'
0x1800e5568  mov     rcx, rbp
0x1800e556b  call    archive_set_error
0x1800e5570  mov     ebx, 0FFFFFFECh
0x1800e5575  movzx   eax, word ptr [rdi+120h]
0x1800e557c  lea     rcx, [rsi+1E8h]
0x1800e5583  or      dword ptr [rsi+0A0h], 600h
0x1800e558d  mov     [rsi+408h], ax
0x1800e5594  mov     [rsi+10h], r13d
0x1800e5598  mov     r9, [r15+2D0h]
0x1800e559f  mov     r8, [rdi+0A0h]
0x1800e55a6  mov     rdx, [rdi+98h]
0x1800e55ad  call    archive_mstring_copy_mbs_len_l
0x1800e55b2  test    eax, eax
0x1800e55b4  jz      short loc_1800E55F5
0x1800e55b6  call    cs:__imp__o__errno
0x1800e55bc  cmp     [rax], r12d
0x1800e55bf  jnz     short loc_1800E55CD
0x1800e55c1  lea     r8, aCanTAllocateMe_24; "Can't allocate memory for Pathname"
0x1800e55c8  jmp     loc_1800E54B3
0x1800e55cd  mov     rcx, [r15+2D0h]
0x1800e55d4  call    archive_string_conversion_charset_name
0x1800e55d9  mov     r9, rax
0x1800e55dc  lea     r8, aPathnameCannot_0; "Pathname cannot be converted from %s to"...
0x1800e55e3  mov     edx, 2Ah ; '*'
0x1800e55e8  mov     rcx, rbp
0x1800e55eb  call    archive_set_error
0x1800e55f0  mov     ebx, 0FFFFFFECh
0x1800e55f5  mov     r8, [rdi+0B8h]
0x1800e55fc  test    r8, r8
0x1800e55ff  jz      short loc_1800E565A
0x1800e5601  mov     r9, [r15+2D0h]
0x1800e5608  mov     rcx, rsi
0x1800e560b  mov     rdx, [rdi+0B0h]
0x1800e5612  call    _archive_entry_copy_symlink_l
0x1800e5617  test    eax, eax
0x1800e5619  jz      short loc_1800E565A
0x1800e561b  call    cs:__imp__o__errno
0x1800e5621  cmp     [rax], r12d
0x1800e5624  jnz     short loc_1800E5632
0x1800e5626  lea     r8, aCanTAllocateMe_15; "Can't allocate memory for Linkname"
0x1800e562d  jmp     loc_1800E54B3
0x1800e5632  mov     rcx, [r15+2D0h]
0x1800e5639  call    archive_string_conversion_charset_name
0x1800e563e  mov     r9, rax
0x1800e5641  lea     r8, aLinknameCannot; "Linkname cannot be converted from %s to"...
0x1800e5648  mov     edx, 2Ah ; '*'
0x1800e564d  mov     rcx, rbp
0x1800e5650  call    archive_set_error
0x1800e5655  mov     ebx, 0FFFFFFECh
0x1800e565a  movzx   eax, word ptr [rdi+120h]
0x1800e5661  mov     ecx, 0F000h
0x1800e5666  and     ax, cx
0x1800e5669  mov     ecx, 4000h
0x1800e566e  cmp     ax, cx
0x1800e5671  jnz     short loc_1800E567B
0x1800e5673  mov     eax, [rdi+18h]
0x1800e5676  add     eax, 2
0x1800e5679  jmp     short loc_1800E5681
0x1800e567b  mov     eax, [rdi+154h]
0x1800e5681  mov     [rsi+10h], r13d
0x1800e5685  mov     [rsi+68h], eax
0x1800e5688  mov     rax, r13
0x1800e568b  cmp     [rdi+38h], r13
0x1800e568f  cmovge  rax, [rdi+38h]
0x1800e5694  or      dword ptr [rsi+0A0h], 40h
0x1800e569b  mov     [rsi+70h], rax
0x1800e569f  cmp     [rdi+160h], r13
0x1800e56a6  jbe     short loc_1800E56B7
0x1800e56a8  mov     rdx, [rdi+158h]
0x1800e56af  mov     rcx, rsi
0x1800e56b2  call    archive_entry_set_hardlink
0x1800e56b7  mov     rdx, [rdi+130h]
0x1800e56be  mov     rcx, rsi
0x1800e56c1  call    archive_entry_set_ino64
0x1800e56c6  mov     ecx, 100h
0x1800e56cb  test    [r14], ecx
0x1800e56ce  jz      short loc_1800E56ED
0x1800e56d0  mov     eax, [rdi+124h]
0x1800e56d6  or      [rsi+0A0h], ecx
0x1800e56dc  mov     [rsi+10h], r13d
0x1800e56e0  mov     [rsi+80h], r13d
0x1800e56e7  mov     [rsi+84h], eax
0x1800e56ed  test    dword ptr [r14], 200h
0x1800e56f4  jz      short loc_1800E5716
0x1800e56f6  mov     eax, [rdi+128h]
0x1800e56fc  or      [rsi+0A0h], ecx
0x1800e5702  mov     [rsi+10h], r13d
0x1800e5706  mov     dword ptr [rsi+80h], 1
0x1800e5710  mov     [rsi+88h], eax
0x1800e5716  test    dword ptr [r14], 400h
0x1800e571d  jz      short loc_1800E573F
0x1800e571f  mov     eax, [rdi+12Ch]
0x1800e5725  or      [rsi+0A0h], ecx
0x1800e572b  mov     [rsi+10h], r13d
0x1800e572f  mov     dword ptr [rsi+80h], 1
0x1800e5739  mov     [rsi+8Ch], eax
0x1800e573f  cmp     [rdi+140h], r13
0x1800e5746  jbe     short loc_1800E5757
0x1800e5748  mov     rdx, [rdi+138h]
0x1800e574f  mov     rcx, rsi
0x1800e5752  call    archive_entry_copy_fflags_text
0x1800e5757  mov     dword ptr [r15+250h], 1
0x1800e5762  mov     [r15+258h], r13
0x1800e5769  mov     rax, [rdi+28h]
0x1800e576d  mov     [r15+260h], rax
0x1800e5774  mov     rax, [rdi+38h]
0x1800e5778  mov     [r15+270h], rax
0x1800e577f  mov     eax, [rdi+40h]
0x1800e5782  mov     [r15+278h], eax
0x1800e5789  movups  xmm0, xmmword ptr [rdi+48h]
0x1800e578d  movups  xmmword ptr [r15+280h], xmm0
0x1800e5795  movups  xmm1, xmmword ptr [rdi+58h]
0x1800e5799  movups  xmmword ptr [r15+290h], xmm1
0x1800e57a1  movsd   xmm0, qword ptr [rdi+68h]
0x1800e57a6  movsd   qword ptr [r15+2A0h], xmm0
0x1800e57af  movups  xmm0, xmmword ptr [rdi+70h]
0x1800e57b3  movups  xmmword ptr [r15+2A8h], xmm0
0x1800e57bb  movups  xmm1, xmmword ptr [rdi+80h]
0x1800e57c2  movups  xmmword ptr [r15+2B8h], xmm1
0x1800e57ca  movsd   xmm0, qword ptr [rdi+90h]
0x1800e57d2  movsd   qword ptr [r15+2C8h], xmm0
0x1800e57db  mov     r14, [rdi+170h]
0x1800e57e2  test    r14, r14
0x1800e57e5  jz      loc_1800E58F1
0x1800e57eb  mov     rdx, [r14+30h]
0x1800e57ef  mov     rcx, rbp
0x1800e57f2  mov     [rsp+68h+arg_0], r13
0x1800e57f7  mov     [rsp+68h+arg_18], r13
0x1800e57ff  call    move_reading_point
0x1800e5804  mov     ebx, eax
0x1800e5806  test    eax, eax
0x1800e5808  jnz     loc_1800E58F5
0x1800e580e  mov     r9d, [r14+70h]
0x1800e5812  mov     rcx, rbp
0x1800e5815  mov     r8d, [r14+48h]
0x1800e5819  mov     edx, [r14+40h]
0x1800e581d  call    rd_contents_init
0x1800e5822  mov     ebx, eax
0x1800e5824  test    eax, eax
0x1800e5826  jnz     loc_1800E58F5
0x1800e582c  mov     rax, [r14+28h]
0x1800e5830  lea     r9, [rsp+68h+arg_18]
0x1800e5838  lea     r8, [rsp+68h+arg_0]
0x1800e583d  mov     [rsp+68h+var_48], rax
0x1800e5842  lea     rdx, [rsp+68h+arg_10]
0x1800e584a  mov     [rsp+68h+arg_10], r13
0x1800e5852  mov     rcx, rbp
0x1800e5855  call    rd_contents
0x1800e585a  mov     ebx, eax
0x1800e585c  test    eax, eax
0x1800e585e  jnz     loc_1800E58F5
0x1800e5864  mov     r12, [rsp+68h+arg_0]
0x1800e5869  mov     rcx, rbp
0x1800e586c  cmp     r12, [r14+38h]
0x1800e5870  jnz     short loc_1800E58DB
0x1800e5872  mov     rax, [r14+78h]
0x1800e5876  lea     r9, [r14+80h]
0x1800e587d  mov     r8, [r14+50h]
0x1800e5881  lea     rdx, [r14+58h]
0x1800e5885  mov     [rsp+68h+var_48], rax
0x1800e588a  call    checksum_final
0x1800e588f  mov     ebx, eax
0x1800e5891  test    eax, eax
0x1800e5893  jnz     short loc_1800E58C2
0x1800e5895  mov     rdx, [r14+8]
0x1800e5899  test    rdx, rdx
0x1800e589c  jz      short loc_1800E58B9
0x1800e589e  mov     r8, [rsp+68h+arg_10]
0x1800e58a6  mov     r9, r12
0x1800e58a9  mov     rcx, rsi
0x1800e58ac  call    archive_entry_xattr_add_entry
0x1800e58b1  mov     r14, [r14]
0x1800e58b4  jmp     loc_1800E57E2
  ... truncated ...
```
