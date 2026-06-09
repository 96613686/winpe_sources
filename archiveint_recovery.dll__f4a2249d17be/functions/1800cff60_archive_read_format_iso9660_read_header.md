# archive_read_format_iso9660_read_header

- ea: `0x1800cff60`
- end: `0x1800d053d`
- name: `archive_read_format_iso9660_read_header`
- size: `1501`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `reparse_path`

## callees

- `0x180006c00`
- `0x18000a2d0`
- `0x18000c0ec`
- `0x18000c8c0`
- `0x18000e764`
- `0x18000e920`
- `0x18000e9a0`
- `0x18000ea00`
- `0x1800aba54`
- `0x1800b0a20`
- `0x1800b1830`
- `0x1800b1f40`
- `0x1800b2140`
- `0x1800b23b0`
- `0x1800cff60`
- `0x1800d0544`
- `0x1800d05d8`
- `0x1800d06b4`
- `0x1800d1920`
- `0x1800ece24`
- `0x1800ed464`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d00bf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d0320`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d00bf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800d0320`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800d004e`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800d004e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d002b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d002b`

## string_xrefs

- `0x1800d00e2`: `Pathname cannot be converted from %s to current locale.`
- `0x1800d0117`: `Pathname is too long`
- `0x1800d00ca`: `No memory for Pathname`
- `0x1800d032b`: `No memory for Linkname`
- `0x1800d0346`: `Linkname cannot be converted from %s to current locale.`

## pseudocode

```c
__int64 __fastcall archive_read_format_iso9660_read_header(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 result; // rax
  __int64 v6; // rdx
  unsigned int v7; // r15d
  int v8; // r12d
  __int64 v9; // rax
  void *v10; // rax
  void *v11; // rax
  const char *v12; // r8
  __int64 v13; // rsi
  __int64 v14; // rcx
  __int64 v15; // r9
  const char *v16; // rax
  __int64 v17; // rax
  const char *v18; // rax
  __int16 v19; // ax
  __int64 v20; // rcx
  int v21; // r8d
  int v22; // r8d
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // r14
  const char *v29; // rax
  unsigned __int64 v30; // rdx
  __int64 filter_seek; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // [rsp+90h] [rbp+8h] BYREF

  v4 = **(_QWORD **)(a1 + 2072);
  if ( !*(_DWORD *)(a1 + 16) )
  {
    *(_DWORD *)(a1 + 16) = 0x40000;
    *(_QWORD *)(a1 + 24) = "ISO9660";
  }
  if ( !*(_QWORD *)(v4 + 160) )
  {
    result = choose_volume(a1, v4);
    if ( (_DWORD)result )
      return result;
  }
  v38 = 0;
  result = next_entry_seek(a1, v4, &v38);
  if ( (_DWORD)result )
    return result;
  v7 = -20;
  v8 = 0;
  if ( *(_BYTE *)(v4 + 42) )
  {
    if ( !*(_QWORD *)(v4 + 464) )
    {
      v9 = archive_string_conversion_from_charset(a1, "UTF-16BE", 1);
      *(_QWORD *)(v4 + 464) = v9;
      if ( !v9 )
        return 4294967266LL;
    }
    if ( !*(_QWORD *)(v4 + 472) && (v10 = malloc(0x400u), (*(_QWORD *)(v4 + 472) = v10) == 0)
      || !*(_QWORD *)(v4 + 488) && (v11 = calloc(1u, 0x400u), (*(_QWORD *)(v4 + 488) = v11) == 0) )
    {
      v12 = "No memory";
LABEL_15:
      archive_set_error(a1, 12, v12);
      return 4294967266LL;
    }
    v13 = v38;
    v14 = *(_QWORD *)(v4 + 472);
    v15 = v38;
    *(_QWORD *)(v4 + 480) = 0;
    if ( !(unsigned int)build_pathname_utf16be(v14, v6, v4 + 480, v15) )
    {
      if ( (unsigned int)archive_mstring_copy_mbs_len_l(
                           a2 + 488,
                           *(_QWORD *)(v4 + 472),
                           *(_QWORD *)(v4 + 480),
                           *(_QWORD *)(v4 + 464)) )
      {
        if ( *(_DWORD *)_o__errno() == 12 )
        {
          v12 = "No memory for Pathname";
          goto LABEL_15;
        }
        v16 = (const char *)archive_string_conversion_charset_name(*(_QWORD *)(v4 + 464));
        archive_set_error(a1, 42, "Pathname cannot be converted from %s to current locale.", v16);
        v8 = -20;
      }
      goto LABEL_25;
    }
LABEL_23:
    archive_set_error(a1, 42, "Pathname is too long");
    return 4294967266LL;
  }
  v13 = v38;
  v17 = build_pathname(v4 + 16, v38, 0);
  if ( !v17 )
    goto LABEL_23;
  *(_QWORD *)(v4 + 24) = 0;
  archive_mstring_copy_mbs(a2 + 488, v17);
LABEL_25:
  *(_QWORD *)(v4 + 216) = *(_QWORD *)(v13 + 56);
  *(_QWORD *)(v4 + 208) = 0;
  if ( *(_QWORD *)(v13 + 48) + *(_QWORD *)(v13 + 56) > *(_QWORD *)(v4 + 176) )
  {
    v18 = (const char *)archive_entry_pathname(a2);
    archive_set_error(a1, -1, "File is beyond end-of-media: %s", v18);
LABEL_60:
    *(_QWORD *)(v4 + 216) = 0;
    return v7;
  }
  v19 = *(_WORD *)(v13 + 136);
  v20 = 0;
  *(_DWORD *)(a2 + 160) |= 0x600u;
  v21 = *(_DWORD *)(a2 + 160);
  *(_WORD *)(a2 + 1032) = v19;
  *(_DWORD *)(a2 + 16) = 0;
  if ( *(__int16 *)(v13 + 138) >= 0 )
    v20 = *(__int16 *)(v13 + 138);
  v22 = v21 | 0x800;
  *(_DWORD *)(a2 + 160) = v22;
  *(_QWORD *)(a2 + 120) = v20;
  v23 = 0;
  if ( *(__int16 *)(v13 + 140) >= 0 )
    v23 = *(__int16 *)(v13 + 140);
  *(_DWORD *)(a2 + 160) = v22 | 0x1000;
  *(_QWORD *)(a2 + 88) = v23;
  *(_DWORD *)(a2 + 104) = *(_DWORD *)(v13 + 152);
  if ( (*(_BYTE *)(v13 + 88) & 1) != 0 )
  {
    archive_entry_set_birthtime(a2, *(_QWORD *)(v13 + 96), 0);
  }
  else
  {
    archive_entry_set_birthtime(a2, 0, 0);
    *(_DWORD *)(a2 + 160) &= ~0x20u;
  }
  if ( (*(_BYTE *)(v13 + 88) & 2) != 0 )
  {
    archive_entry_set_mtime(a2, *(_QWORD *)(v13 + 104), 0);
  }
  else
  {
    archive_entry_set_mtime(a2, 0, 0);
    *(_DWORD *)(a2 + 160) &= ~0x10u;
  }
  if ( (*(_BYTE *)(v13 + 88) & 8) != 0 )
  {
    archive_entry_set_ctime(a2, *(_QWORD *)(v13 + 120), 0);
  }
  else
  {
    archive_entry_set_ctime(a2, 0, 0);
    *(_DWORD *)(a2 + 160) &= ~8u;
  }
  if ( (*(_BYTE *)(v13 + 88) & 4) != 0 )
  {
    archive_entry_set_atime(a2, *(_QWORD *)(v13 + 112), 0);
  }
  else
  {
    archive_entry_set_atime(a2, 0, 0);
    *(_DWORD *)(a2 + 160) &= ~4u;
  }
  v24 = *(_DWORD *)(v13 + 128);
  *(_DWORD *)(a2 + 160) |= 0x2000u;
  *(_DWORD *)(a2 + 148) = v24;
  v25 = 0;
  *(_DWORD *)(a2 + 16) = 0;
  *(_DWORD *)(a2 + 144) = 0;
  *(_QWORD *)(a2 + 152) = 0;
  if ( *(__int64 *)(v4 + 216) >= 0 )
    v25 = *(_QWORD *)(v4 + 216);
  *(_DWORD *)(a2 + 160) |= 0x40u;
  *(_QWORD *)(a2 + 112) = v25;
  v26 = *(_QWORD *)(v13 + 208);
  if ( v26 )
    archive_entry_copy_symlink(a2, v26);
  v27 = *(_QWORD *)(v13 + 144);
  v28 = -1;
  if ( v27 != -1 && v27 == *(_QWORD *)(v4 + 72) )
  {
    if ( *(_BYTE *)(v4 + 42) )
    {
      if ( (unsigned int)archive_entry_copy_hardlink_l(
                           a2,
                           *(_QWORD *)(v4 + 488),
                           *(_QWORD *)(v4 + 496),
                           *(_QWORD *)(v4 + 464)) )
      {
        if ( *(_DWORD *)_o__errno() == 12 )
        {
          v12 = "No memory for Linkname";
          goto LABEL_15;
        }
        v29 = (const char *)archive_string_conversion_charset_name(*(_QWORD *)(v4 + 464));
        archive_set_error(a1, 42, "Linkname cannot be converted from %s to current locale.", v29);
        v8 = -20;
      }
    }
    else
    {
      archive_entry_set_hardlink(a2, *(_QWORD *)(v4 + 80));
    }
    *(_DWORD *)(a2 + 160) &= ~0x40u;
    v7 = v8;
    *(_DWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 112) = 0;
    goto LABEL_60;
  }
  if ( (*(_WORD *)(v13 + 136) & 0xF000) != 0x4000 )
  {
    v30 = *(_QWORD *)(v13 + 48);
    if ( v30 < *(_QWORD *)(v4 + 160) )
    {
      filter_seek = _archive_read_filter_seek(*(_QWORD *)(a1 + 632), v30, 0);
      v32 = *(_QWORD *)(v13 + 48);
      if ( filter_seek != v32 )
      {
        archive_set_error(
          a1,
          0xFFFFFFFFLL,
          "Ignoring out-of-order file @%jx (%s) %jd < %jd",
          *(_QWORD *)(v13 + 144),
          *(const char **)(v4 + 16),
          v32,
          *(_QWORD *)(v4 + 160));
        goto LABEL_60;
      }
      *(_QWORD *)(v4 + 160) = filter_seek;
    }
  }
  *(_DWORD *)(v4 + 232) = *(_DWORD *)(v13 + 236);
  if ( *(_DWORD *)(v13 + 236) )
  {
    *(_DWORD *)(v4 + 248) = 0;
    *(_DWORD *)(v4 + 236) = *(_DWORD *)(v13 + 240);
    *(_QWORD *)(v4 + 240) = *(_QWORD *)(v13 + 248);
    v33 = 0;
    *(_DWORD *)(v4 + 272) = 0;
    *(_QWORD *)(v4 + 296) = 0;
    *(_DWORD *)(v4 + 304) = 0;
    *(_QWORD *)(v4 + 336) = 0;
    v34 = *(_QWORD *)(v13 + 248);
    *(_DWORD *)(a2 + 16) = 0;
    if ( v34 >= 0 )
      v33 = v34;
    *(_DWORD *)(a2 + 160) |= 0x40u;
    *(_QWORD *)(a2 + 112) = v33;
  }
  *(_QWORD *)(v4 + 72) = *(_QWORD *)(v13 + 144);
  if ( *(_BYTE *)(v4 + 42) )
  {
    memcpy_0(*(void **)(v4 + 488), *(const void **)(v4 + 472), *(_QWORD *)(v4 + 480));
    *(_QWORD *)(v4 + 496) = *(_QWORD *)(v4 + 480);
  }
  else
  {
    v35 = *(_QWORD *)(v4 + 16);
    *(_QWORD *)(v4 + 88) = 0;
    if ( v35 )
    {
      do
        ++v28;
      while ( *(_BYTE *)(v35 + v28) );
    }
    else
    {
      v28 = 0;
    }
    archive_strncat(v4 + 80, v35, v28);
  }
  v36 = *(_QWORD *)(v13 + 264);
  *(_QWORD *)(v4 + 456) = v36;
  if ( v36 )
    *(_QWORD *)(v4 + 216) = *(_QWORD *)(v36 + 8);
  if ( (*(_WORD *)(a2 + 1032) & 0xF000) == 0x4000 )
  {
    v37 = *(_DWORD *)(v13 + 32);
    *(_DWORD *)(a2 + 16) = 0;
    *(_DWORD *)(a2 + 104) = v37 + 2;
    *(_QWORD *)(v4 + 216) = 0;
  }
  return v8 & (unsigned int)-(v8 != 0);
}

```

## disassembly

```asm
0x1800cff60  push    rbx
0x1800cff62  push    rbp
0x1800cff63  push    rsi
0x1800cff64  push    rdi
0x1800cff65  push    r12
0x1800cff67  push    r13
0x1800cff69  push    r14
0x1800cff6b  push    r15
0x1800cff6d  sub     rsp, 48h
0x1800cff71  mov     rax, [rcx+818h]
0x1800cff78  xor     r13d, r13d
0x1800cff7b  mov     rdi, rdx
0x1800cff7e  mov     rbp, rcx
0x1800cff81  mov     rbx, [rax]
0x1800cff84  cmp     [rcx+10h], r13d
0x1800cff88  jnz     short loc_1800CFF9C
0x1800cff8a  lea     rax, aIso9660; "ISO9660"
0x1800cff91  mov     dword ptr [rcx+10h], 40000h
0x1800cff98  mov     [rcx+18h], rax
0x1800cff9c  cmp     [rbx+0A0h], r13
0x1800cffa3  jnz     short loc_1800CFFB5
0x1800cffa5  mov     rdx, rbx
0x1800cffa8  call    choose_volume
0x1800cffad  test    eax, eax
0x1800cffaf  jnz     loc_1800D052C
0x1800cffb5  lea     r8, [rsp+88h+arg_0]
0x1800cffbd  mov     [rsp+88h+arg_0], r13
0x1800cffc5  mov     rdx, rbx
0x1800cffc8  mov     rcx, rbp
0x1800cffcb  call    next_entry_seek
0x1800cffd0  test    eax, eax
0x1800cffd2  jnz     loc_1800D052C
0x1800cffd8  lea     r15d, [rax-14h]
0x1800cffdc  mov     r12d, r13d
0x1800cffdf  cmp     [rbx+2Ah], r13b
0x1800cffe3  jz      loc_1800D00FB
0x1800cffe9  cmp     [rbx+1D0h], r13
0x1800cfff0  jnz     short loc_1800D001B
0x1800cfff2  lea     r8d, [rax+1]
0x1800cfff6  mov     rcx, rbp
0x1800cfff9  lea     rdx, aUtf16be; "UTF-16BE"
0x1800d0000  call    archive_string_conversion_from_charset
0x1800d0005  mov     [rbx+1D0h], rax
0x1800d000c  test    rax, rax
0x1800d000f  jnz     short loc_1800D001B
0x1800d0011  mov     eax, 0FFFFFFE2h
0x1800d0016  jmp     loc_1800D052C
0x1800d001b  mov     esi, 400h
0x1800d0020  cmp     [rbx+1D8h], r13
0x1800d0027  jnz     short loc_1800D003D
0x1800d0029  mov     ecx, esi; Size
0x1800d002b  call    cs:__imp_malloc
0x1800d0031  mov     [rbx+1D8h], rax
0x1800d0038  test    rax, rax
0x1800d003b  jz      short loc_1800D0060
0x1800d003d  cmp     [rbx+1E8h], r13
0x1800d0044  jnz     short loc_1800D0076
0x1800d0046  mov     rdx, rsi; Size
0x1800d0049  mov     ecx, 1; Count
0x1800d004e  call    cs:__imp_calloc
0x1800d0054  mov     [rbx+1E8h], rax
0x1800d005b  test    rax, rax
0x1800d005e  jnz     short loc_1800D0076
0x1800d0060  lea     r8, aNoMemory_0; "No memory"
0x1800d0067  mov     edx, 0Ch
0x1800d006c  mov     rcx, rbp
0x1800d006f  call    archive_set_error
0x1800d0074  jmp     short loc_1800D0011
0x1800d0076  mov     rsi, [rsp+88h+arg_0]
0x1800d007e  lea     r14, [rbx+1E0h]
0x1800d0085  mov     rcx, [rbx+1D8h]
0x1800d008c  mov     r9, rsi
0x1800d008f  mov     r8, r14
0x1800d0092  mov     [r14], r13
0x1800d0095  call    build_pathname_utf16be
0x1800d009a  test    eax, eax
0x1800d009c  jnz     short loc_1800D0117
0x1800d009e  mov     r9, [rbx+1D0h]
0x1800d00a5  lea     rcx, [rdi+1E8h]
0x1800d00ac  mov     r8, [r14]
0x1800d00af  mov     rdx, [rbx+1D8h]
0x1800d00b6  call    archive_mstring_copy_mbs_len_l
0x1800d00bb  test    eax, eax
0x1800d00bd  jz      short loc_1800D013B
0x1800d00bf  call    cs:__imp__o__errno
0x1800d00c5  cmp     dword ptr [rax], 0Ch
0x1800d00c8  jnz     short loc_1800D00D3
0x1800d00ca  lea     r8, aNoMemoryForPat; "No memory for Pathname"
0x1800d00d1  jmp     short loc_1800D0067
0x1800d00d3  mov     rcx, [rbx+1D0h]
0x1800d00da  call    archive_string_conversion_charset_name
0x1800d00df  mov     r9, rax
0x1800d00e2  lea     r8, aPathnameCannot_0; "Pathname cannot be converted from %s to"...
0x1800d00e9  mov     edx, 2Ah ; '*'
0x1800d00ee  mov     rcx, rbp
0x1800d00f1  call    archive_set_error
0x1800d00f6  mov     r12d, r15d
0x1800d00f9  jmp     short loc_1800D013B
0x1800d00fb  mov     rsi, [rsp+88h+arg_0]
0x1800d0103  lea     rcx, [rbx+10h]
0x1800d0107  mov     rdx, rsi
0x1800d010a  xor     r8d, r8d
0x1800d010d  call    build_pathname
0x1800d0112  test    rax, rax
0x1800d0115  jnz     short loc_1800D0128
0x1800d0117  lea     r8, aPathnameIsTooL; "Pathname is too long"
0x1800d011e  mov     edx, 2Ah ; '*'
0x1800d0123  jmp     loc_1800D006C
0x1800d0128  lea     rcx, [rdi+1E8h]
0x1800d012f  mov     [rbx+18h], r13
0x1800d0133  mov     rdx, rax
0x1800d0136  call    archive_mstring_copy_mbs
0x1800d013b  mov     rax, [rsi+38h]
0x1800d013f  mov     [rbx+0D8h], rax
0x1800d0146  mov     [rbx+0D0h], r13
0x1800d014d  mov     rax, [rsi+38h]
0x1800d0151  add     rax, [rsi+30h]
0x1800d0155  cmp     rax, [rbx+0B0h]
0x1800d015c  jbe     short loc_1800D0181
0x1800d015e  mov     rcx, rdi
0x1800d0161  call    archive_entry_pathname
0x1800d0166  mov     r9, rax
0x1800d0169  lea     r8, aFileIsBeyondEn; "File is beyond end-of-media: %s"
0x1800d0170  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800d0174  mov     rcx, rbp
0x1800d0177  call    archive_set_error
0x1800d017c  jmp     loc_1800D03ED
0x1800d0181  movzx   eax, word ptr [rsi+88h]
0x1800d0188  mov     rcx, r13
0x1800d018b  or      dword ptr [rdi+0A0h], 600h
0x1800d0195  mov     r8d, [rdi+0A0h]
0x1800d019c  mov     [rdi+408h], ax
0x1800d01a3  mov     [rdi+10h], r13d
0x1800d01a7  movsx   rdx, word ptr [rsi+8Ah]
0x1800d01af  test    dx, dx
0x1800d01b2  cmovns  rcx, rdx
0x1800d01b6  bts     r8d, 0Bh
0x1800d01bb  mov     [rdi+0A0h], r8d
0x1800d01c2  mov     [rdi+78h], rcx
0x1800d01c6  mov     rcx, r13
0x1800d01c9  movsx   rdx, word ptr [rsi+8Ch]
0x1800d01d1  test    dx, dx
0x1800d01d4  cmovns  rcx, rdx
0x1800d01d8  bts     r8d, 0Ch
0x1800d01dd  mov     [rdi+0A0h], r8d
0x1800d01e4  xor     r8d, r8d
0x1800d01e7  mov     [rdi+58h], rcx
0x1800d01eb  mov     rcx, rdi
0x1800d01ee  mov     eax, [rsi+98h]
0x1800d01f4  mov     [rdi+68h], eax
0x1800d01f7  test    byte ptr [rsi+58h], 1
0x1800d01fb  jz      short loc_1800D0208
0x1800d01fd  mov     rdx, [rsi+60h]
0x1800d0201  call    archive_entry_set_birthtime
0x1800d0206  jmp     short loc_1800D0216
0x1800d0208  xor     edx, edx
0x1800d020a  call    archive_entry_set_birthtime
0x1800d020f  and     dword ptr [rdi+0A0h], 0FFFFFFDFh
0x1800d0216  xor     r8d, r8d
0x1800d0219  mov     rcx, rdi
0x1800d021c  test    byte ptr [rsi+58h], 2
0x1800d0220  jz      short loc_1800D022D
0x1800d0222  mov     rdx, [rsi+68h]
0x1800d0226  call    archive_entry_set_mtime
0x1800d022b  jmp     short loc_1800D023B
0x1800d022d  xor     edx, edx
0x1800d022f  call    archive_entry_set_mtime
0x1800d0234  and     dword ptr [rdi+0A0h], 0FFFFFFEFh
0x1800d023b  xor     r8d, r8d
0x1800d023e  mov     rcx, rdi
0x1800d0241  test    byte ptr [rsi+58h], 8
0x1800d0245  jz      short loc_1800D0252
0x1800d0247  mov     rdx, [rsi+78h]
0x1800d024b  call    archive_entry_set_ctime
0x1800d0250  jmp     short loc_1800D0260
0x1800d0252  xor     edx, edx
0x1800d0254  call    archive_entry_set_ctime
0x1800d0259  and     dword ptr [rdi+0A0h], 0FFFFFFF7h
0x1800d0260  xor     r8d, r8d
0x1800d0263  mov     rcx, rdi
0x1800d0266  test    byte ptr [rsi+58h], 4
0x1800d026a  jz      short loc_1800D0277
0x1800d026c  mov     rdx, [rsi+70h]
0x1800d0270  call    archive_entry_set_atime
0x1800d0275  jmp     short loc_1800D0285
0x1800d0277  xor     edx, edx
0x1800d0279  call    archive_entry_set_atime
0x1800d027e  and     dword ptr [rdi+0A0h], 0FFFFFFFBh
0x1800d0285  mov     eax, [rsi+80h]
0x1800d028b  bts     dword ptr [rdi+0A0h], 0Dh
0x1800d0293  mov     [rdi+94h], eax
0x1800d0299  mov     rax, r13
0x1800d029c  mov     [rdi+10h], r13d
0x1800d02a0  mov     [rdi+90h], r13d
0x1800d02a7  mov     [rdi+98h], r13
0x1800d02ae  mov     rcx, [rbx+0D8h]
0x1800d02b5  test    rcx, rcx
0x1800d02b8  cmovns  rax, rcx
0x1800d02bc  or      dword ptr [rdi+0A0h], 40h
0x1800d02c3  mov     [rdi+70h], rax
0x1800d02c7  mov     rdx, [rsi+0D0h]
0x1800d02ce  test    rdx, rdx
0x1800d02d1  jz      short loc_1800D02DB
0x1800d02d3  mov     rcx, rdi
0x1800d02d6  call    archive_entry_copy_symlink
0x1800d02db  mov     rax, [rsi+90h]
0x1800d02e2  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800d02e6  cmp     rax, r14
0x1800d02e9  jz      loc_1800D037C
0x1800d02ef  cmp     rax, [rbx+48h]
0x1800d02f3  jnz     loc_1800D037C
0x1800d02f9  mov     rcx, rdi
0x1800d02fc  cmp     [rbx+2Ah], r13b
0x1800d0300  jz      short loc_1800D035F
0x1800d0302  mov     r9, [rbx+1D0h]
0x1800d0309  mov     r8, [rbx+1F0h]
0x1800d0310  mov     rdx, [rbx+1E8h]
0x1800d0317  call    _archive_entry_copy_hardlink_l
0x1800d031c  test    eax, eax
0x1800d031e  jz      short loc_1800D0368
0x1800d0320  call    cs:__imp__o__errno
0x1800d0326  cmp     dword ptr [rax], 0Ch
0x1800d0329  jnz     short loc_1800D0337
0x1800d032b  lea     r8, aNoMemoryForLin; "No memory for Linkname"
0x1800d0332  jmp     loc_1800D0067
0x1800d0337  mov     rcx, [rbx+1D0h]
0x1800d033e  call    archive_string_conversion_charset_name
0x1800d0343  mov     r9, rax
0x1800d0346  lea     r8, aLinknameCannot; "Linkname cannot be converted from %s to"...
0x1800d034d  mov     edx, 2Ah ; '*'
0x1800d0352  mov     rcx, rbp
0x1800d0355  call    archive_set_error
0x1800d035a  mov     r12d, r15d
0x1800d035d  jmp     short loc_1800D0368
0x1800d035f  mov     rdx, [rbx+50h]
0x1800d0363  call    archive_entry_set_hardlink
0x1800d0368  and     dword ptr [rdi+0A0h], 0FFFFFFBFh
0x1800d036f  mov     r15d, r12d
0x1800d0372  mov     [rdi+10h], r13d
0x1800d0376  mov     [rdi+70h], r13
0x1800d037a  jmp     short loc_1800D03ED
0x1800d037c  movzx   eax, word ptr [rsi+88h]
0x1800d0383  mov     ecx, 0F000h
0x1800d0388  and     ax, cx
0x1800d038b  mov     ecx, 4000h
0x1800d0390  cmp     ax, cx
0x1800d0393  jz      short loc_1800D0403
0x1800d0395  mov     rdx, [rsi+30h]
0x1800d0399  cmp     rdx, [rbx+0A0h]
0x1800d03a0  jnb     short loc_1800D0403
0x1800d03a2  mov     rcx, [rbp+278h]
0x1800d03a9  xor     r8d, r8d
0x1800d03ac  call    __archive_read_filter_seek
0x1800d03b1  mov     rdx, [rsi+30h]
0x1800d03b5  cmp     rax, rdx
0x1800d03b8  jz      short loc_1800D03FC
0x1800d03ba  mov     rcx, [rbx+0A0h]
0x1800d03c1  lea     r8, aIgnoringOutOfO_1; "Ignoring out-of-order file @%jx (%s) %j"...
0x1800d03c8  mov     r9, [rsi+90h]
0x1800d03cf  mov     [rsp+88h+var_58], rcx
0x1800d03d4  mov     rcx, [rbx+10h]
0x1800d03d8  mov     [rsp+88h+var_60], rdx
0x1800d03dd  mov     edx, r14d
0x1800d03e0  mov     [rsp+88h+var_68], rcx
0x1800d03e5  mov     rcx, rbp
0x1800d03e8  call    archive_set_error
0x1800d03ed  mov     [rbx+0D8h], r13
0x1800d03f4  mov     eax, r15d
0x1800d03f7  jmp     loc_1800D052C
0x1800d03fc  mov     [rbx+0A0h], rax
0x1800d0403  mov     eax, [rsi+0ECh]
0x1800d0409  mov     [rbx+0E8h], eax
0x1800d040f  cmp     [rsi+0ECh], r13d
0x1800d0416  jz      short loc_1800D0475
0x1800d0418  mov     [rbx+0F8h], r13d
0x1800d041f  mov     eax, [rsi+0F0h]
0x1800d0425  mov     [rbx+0ECh], eax
0x1800d042b  mov     rax, [rsi+0F8h]
0x1800d0432  mov     [rbx+0F0h], rax
0x1800d0439  mov     rax, r13
0x1800d043c  mov     [rbx+110h], r13d
0x1800d0443  mov     [rbx+128h], r13
0x1800d044a  mov     [rbx+130h], r13d
0x1800d0451  mov     [rbx+150h], r13
0x1800d0458  mov     rcx, [rsi+0F8h]
0x1800d045f  test    rcx, rcx
0x1800d0462  mov     [rdi+10h], r13d
0x1800d0466  cmovns  rax, rcx
0x1800d046a  or      dword ptr [rdi+0A0h], 40h
0x1800d0471  mov     [rdi+70h], rax
0x1800d0475  mov     rax, [rsi+90h]
0x1800d047c  mov     [rbx+48h], rax
0x1800d0480  cmp     [rbx+2Ah], r13b
0x1800d0484  jz      short loc_1800D04B0
0x1800d0486  mov     r8, [rbx+1E0h]; Size
0x1800d048d  mov     rdx, [rbx+1D8h]; Src
0x1800d0494  mov     rcx, [rbx+1E8h]; void *
0x1800d049b  call    memcpy_0
0x1800d04a0  mov     rax, [rbx+1E0h]
0x1800d04a7  mov     [rbx+1F0h], rax
  ... truncated ...
```
