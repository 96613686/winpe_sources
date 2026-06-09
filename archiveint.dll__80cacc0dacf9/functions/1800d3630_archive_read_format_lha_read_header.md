# archive_read_format_lha_read_header

- ea: `0x1800d3630`
- end: `0x1800d3dbf`
- name: `archive_read_format_lha_read_header`
- size: `1935`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `reparse_path`

## callees

- `0x180005914`
- `0x180006c00`
- `0x18000e0e4`
- `0x18000e764`
- `0x18000e920`
- `0x18000e9a0`
- `0x18000ea00`
- `0x180013ec8`
- `0x180015810`
- `0x18001590c`
- `0x1800b1830`
- `0x1800b1880`
- `0x1800b2140`
- `0x1800b2770`
- `0x1800d3630`
- `0x1800d3de8`
- `0x1800d3fcc`
- `0x1800d4bcc`
- `0x1800d4df8`
- `0x1800d5004`
- `0x1800d51f4`
- `0x1800d53c4`
- `0x1800d54ac`
- `0x1800ece24`
- `0x1800ecf00`
- `0x1800ed464`
- `0x1800ed690`
- `0x1800ed6c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d39ab`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d39c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d3b15`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d3b2b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d3b93`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d3bc4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d39ab`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d39c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d3b15`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d3b2b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d3b93`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d3bc4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800d3a98`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800d3a98`

## string_xrefs

- `0x1800d396c`: `Pathname cannot be converted from %s to Unicode.`
- `0x1800d3a1e`: `Pathname cannot be converted from %s to Unicode.`
- `0x1800d3aec`: `Unknown symlink-name`

## pseudocode

```c
__int64 __fastcall archive_read_format_lha_read_header(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  _BYTE *filter_ahead; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  _BYTE *v8; // r9
  _BYTE *v9; // rax
  __int64 result; // rax
  _BYTE *v11; // r9
  unsigned __int8 v12; // al
  int v13; // ecx
  bool v14; // dl
  int v15; // ecx
  int v16; // ecx
  char v17; // al
  __int64 v18; // rax
  int v19; // r9d
  unsigned int v20; // r14d
  int file_header_1; // eax
  const char *v22; // rax
  const char *v23; // rax
  __int16 v24; // dx
  wchar_t *v25; // r13
  __int64 v26; // r12
  wchar_t *v27; // rdx
  __int64 v28; // r8
  __int16 v29; // cx
  __int16 v30; // ax
  int v31; // edx
  __int64 v32; // rax
  int v33; // edx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  void *Block[2]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v39; // [rsp+40h] [rbp-59h]
  void *v40[2]; // [rsp+48h] [rbp-51h] BYREF
  __int64 v41; // [rsp+58h] [rbp-41h]
  __int64 v42; // [rsp+60h] [rbp-39h] BYREF
  __int64 v43; // [rsp+68h] [rbp-31h]
  __int64 v44; // [rsp+70h] [rbp-29h]
  __int64 v45; // [rsp+78h] [rbp-21h]
  __int64 v46; // [rsp+80h] [rbp-19h]
  __int64 v47; // [rsp+88h] [rbp-11h]
  __int64 v48; // [rsp+90h] [rbp-9h] BYREF
  __int64 v49; // [rsp+98h] [rbp-1h]
  __int64 v50; // [rsp+A0h] [rbp+7h]
  __int64 v51; // [rsp+A8h] [rbp+Fh]
  __int64 v52; // [rsp+B0h] [rbp+17h]
  __int64 v53; // [rsp+B8h] [rbp+1Fh]
  __int64 v54; // [rsp+100h] [rbp+67h] BYREF

  v41 = 0;
  v39 = 0;
  *(_OWORD *)v40 = 0;
  *(_OWORD *)Block = 0;
  memset_0(&v42, 0, 0x68u);
  v54 = 0;
  lha_crc16_init();
  *(_DWORD *)(a1 + 16) = 720896;
  if ( !*(_QWORD *)(a1 + 24) )
    *(_QWORD *)(a1 + 24) = "lha";
  v4 = **(_QWORD **)(a1 + 2072);
  *(_WORD *)(v4 + 291) = 0;
  *(_BYTE *)(v4 + 293) = 0;
  *(_QWORD *)(v4 + 16) = 0;
  filter_ahead = (_BYTE *)_archive_read_filter_ahead(*(_QWORD *)(a1 + 632), 22, 0);
  v8 = filter_ahead;
  if ( !filter_ahead )
  {
    v9 = (_BYTE *)_archive_read_filter_ahead(*(_QWORD *)(a1 + 632), 1, 0);
    if ( !v9 || !*v9 )
      return 1;
    goto LABEL_38;
  }
  if ( !*(_BYTE *)(v4 + 289) && *filter_ahead == 77 && filter_ahead[1] == 90 )
  {
    result = lha_skip_sfx(a1, v6, v7, filter_ahead);
    if ( (int)result < -20 )
      return result;
    v8 = (_BYTE *)_archive_read_filter_ahead(*(_QWORD *)(a1 + 632), 1, 0);
    if ( !v8 )
      goto LABEL_38;
  }
  if ( !*v8 )
    return 1;
  if ( lha_check_header_format(v8) )
  {
    archive_set_error(a1, 42, "Bad LHa file");
    return 4294967266LL;
  }
  *(_BYTE *)(v4 + 289) = 1;
  *(_QWORD *)(v4 + 32) = 0;
  *(_BYTE *)(v4 + 40) = v11[20];
  *(_BYTE *)(v4 + 41) = v11[3];
  *(_BYTE *)(v4 + 42) = v11[4];
  v12 = v11[5];
  *(_BYTE *)(v4 + 43) = v12;
  v13 = *(unsigned __int16 *)(v4 + 41) - 26732;
  if ( *(_WORD *)(v4 + 41) == 26732 )
    v13 = v12 - 100;
  v14 = v13 == 0;
  *(_BYTE *)(v4 + 290) = v13 == 0;
  v15 = *(unsigned __int16 *)(v4 + 41) - 26732;
  if ( *(_WORD *)(v4 + 41) == 26732 )
    v15 = *(unsigned __int8 *)(v4 + 43) - 48;
  if ( !v15 )
    goto LABEL_25;
  v16 = *(unsigned __int16 *)(v4 + 41) - 31340;
  if ( *(_WORD *)(v4 + 41) == 31340 )
    v16 = *(unsigned __int8 *)(v4 + 43) - 52;
  v17 = 1;
  if ( !v16 )
LABEL_25:
    v17 = 0;
  *(_BYTE *)(v4 + 294) = v17;
  *(_QWORD *)(v4 + 48) = 0;
  *(_QWORD *)(v4 + 56) = 0;
  *(_DWORD *)(v4 + 64) = 0;
  *(_QWORD *)(v4 + 72) = 0;
  *(_WORD *)(v4 + 116) = v14 ? 511 : 438;
  v18 = *(_QWORD *)(v4 + 208);
  *(_DWORD *)(v4 + 80) = 0;
  *(_QWORD *)(v4 + 88) = 0;
  *(_DWORD *)(v4 + 96) = 0;
  *(_QWORD *)(v4 + 104) = 0;
  *(_DWORD *)(v4 + 112) = 0;
  *(_QWORD *)(v4 + 120) = 0;
  *(_QWORD *)(v4 + 128) = 0;
  *(_QWORD *)(v4 + 224) = 0;
  *(_QWORD *)(v4 + 248) = 0;
  *(_BYTE *)(v4 + 288) = 0;
  *(_QWORD *)(v4 + 192) = v18;
  *(_QWORD *)(v4 + 200) = v18;
  v19 = (unsigned __int8)v11[20];
  if ( v19 )
  {
    switch ( v19 )
    {
      case 1:
        file_header_1 = lha_read_file_header_1(a1, v4);
        break;
      case 2:
        file_header_1 = lha_read_file_header_2(a1, v4);
        break;
      case 3:
        file_header_1 = lha_read_file_header_3(a1, v4);
        break;
      default:
        archive_set_error(a1, 42, "Unsupported LHa header level %d", v19);
        return (unsigned int)-30;
    }
  }
  else
  {
    file_header_1 = lha_read_file_header_0(a1, v4);
  }
  v20 = file_header_1;
  if ( file_header_1 < -20 )
    return v20;
  if ( !*(_BYTE *)(v4 + 290) && !*(_QWORD *)(v4 + 248) )
  {
LABEL_38:
    archive_set_error(a1, 42, "Truncated LHa header");
    return 4294967266LL;
  }
  Block[0] = 0;
  Block[1] = 0;
  v39 = 0;
  v40[0] = 0;
  v40[1] = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  if ( (unsigned int)archive_mstring_copy_mbs_len_l(
                       &v42,
                       *(_QWORD *)(v4 + 216),
                       *(_QWORD *)(v4 + 224),
                       *(_QWORD *)(v4 + 192)) )
  {
    v22 = (const char *)archive_string_conversion_charset_name(*(_QWORD *)(v4 + 192));
    archive_set_error(a1, 42, "Pathname cannot be converted from %s to Unicode.", v22);
LABEL_42:
    archive_mstring_clean(&v42);
    Block[1] = 0;
    v39 = 0;
    free(Block[0]);
    Block[0] = 0;
    v40[1] = 0;
    v41 = 0;
    free(v40[0]);
    return 4294967266LL;
  }
  if ( (unsigned int)archive_mstring_get_wcs(a1, &v42, &v54) )
    goto LABEL_42;
  Block[1] = 0;
  archive_wstring_concat(Block, &v48);
  v43 = 0;
  v52 = 0;
  v46 = 0;
  v49 = 0;
  if ( (unsigned int)archive_mstring_copy_mbs_len_l(
                       &v42,
                       *(_QWORD *)(v4 + 240),
                       *(_QWORD *)(v4 + 248),
                       *(_QWORD *)(v4 + 200)) )
  {
    v23 = (const char *)archive_string_conversion_charset_name(*(_QWORD *)(v4 + 200));
    archive_set_error(a1, 42, "Pathname cannot be converted from %s to Unicode.", v23);
LABEL_46:
    archive_mstring_clean(&v42);
    v20 = -30;
LABEL_55:
    Block[1] = 0;
    v39 = 0;
    free(Block[0]);
    Block[0] = 0;
    v40[1] = 0;
    v41 = 0;
    free(v40[0]);
    return v20;
  }
  if ( (unsigned int)archive_mstring_get_wcs(a1, &v42, &v54) )
    goto LABEL_46;
  archive_wstring_concat(Block, &v48);
  archive_mstring_clean(&v42);
  v24 = *(_WORD *)(v4 + 116);
  if ( (v24 & 0xF000) == 0xA000 )
  {
    v25 = wcschr((const wchar_t *)Block[0], 0x7Cu);
    if ( !v25 )
    {
      archive_set_error(a1, 42, "Unknown symlink-name");
      v20 = -25;
      goto LABEL_55;
    }
    v26 = -1;
    v27 = v25 + 1;
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
    v40[1] = 0;
    archive_wstrncat(v40, v27);
    *v25 = 0;
    do
      ++v26;
    while ( *((_WORD *)Block[0] + v26) );
    Block[1] = (void *)v26;
    v29 = *(_WORD *)(v4 + 116);
  }
  else
  {
    v29 = v24 & 0xFFF | (*(_BYTE *)(v4 + 290) != 0 ? 0x4000 : 0x8000);
    *(_WORD *)(v4 + 116) = v29;
  }
  if ( (*(_BYTE *)(v4 + 288) & ((*(_BYTE *)(v4 + 64) & 4) == 0)) != 0 )
    *(_WORD *)(v4 + 116) = v29 & 0xFF6D;
  archive_mstring_copy_wcs(a2 + 488, Block[0]);
  Block[1] = 0;
  v39 = 0;
  free(Block[0]);
  Block[0] = 0;
  if ( v40[1] )
    archive_entry_copy_symlink_w(a2, v40[0]);
  else
    archive_entry_copy_symlink(a2, 0);
  v40[1] = 0;
  v41 = 0;
  free(v40[0]);
  v40[0] = 0;
  if ( !*(_BYTE *)(v4 + 40) )
    lha_replace_path_separator(v4, a2);
  v30 = *(_WORD *)(v4 + 116);
  *(_DWORD *)(a2 + 160) |= 0x600u;
  v31 = *(_DWORD *)(a2 + 160);
  *(_WORD *)(a2 + 1032) = v30;
  v32 = 0;
  *(_DWORD *)(a2 + 16) = 0;
  if ( *(__int64 *)(v4 + 120) >= 0 )
    v32 = *(_QWORD *)(v4 + 120);
  v33 = v31 | 0x800;
  *(_DWORD *)(a2 + 160) = v33;
  *(_QWORD *)(a2 + 120) = v32;
  v34 = 0;
  if ( *(__int64 *)(v4 + 128) >= 0 )
    v34 = *(_QWORD *)(v4 + 128);
  *(_DWORD *)(a2 + 160) = v33 | 0x1000;
  *(_QWORD *)(a2 + 88) = v34;
  if ( *(_QWORD *)(v4 + 144) )
    archive_mstring_copy_mbs(a2 + 592, *(_QWORD *)(v4 + 136));
  if ( *(_QWORD *)(v4 + 168) )
    archive_mstring_copy_mbs(a2 + 280, *(_QWORD *)(v4 + 160));
  if ( (*(_BYTE *)(v4 + 64) & 1) != 0 )
  {
    archive_entry_set_birthtime(a2, *(_QWORD *)(v4 + 72), *(unsigned int *)(v4 + 80));
    archive_entry_set_ctime(a2, *(_QWORD *)(v4 + 72), *(unsigned int *)(v4 + 80));
  }
  else
  {
    archive_entry_set_birthtime(a2, 0, 0);
    *(_DWORD *)(a2 + 160) &= ~0x20u;
    archive_entry_set_ctime(a2, 0, 0);
    *(_DWORD *)(a2 + 160) &= ~8u;
  }
  archive_entry_set_mtime(a2, *(_QWORD *)(v4 + 88), *(unsigned int *)(v4 + 96));
  if ( (*(_BYTE *)(v4 + 64) & 2) != 0 )
  {
    archive_entry_set_atime(a2, *(_QWORD *)(v4 + 104), *(unsigned int *)(v4 + 112));
  }
  else
  {
    archive_entry_set_atime(a2, 0, 0);
    *(_DWORD *)(a2 + 160) &= ~4u;
  }
  if ( *(_BYTE *)(v4 + 290) || archive_entry_symlink(a2) )
  {
    *(_DWORD *)(a2 + 160) &= ~0x40u;
    v36 = 0;
  }
  else
  {
    v35 = *(_QWORD *)(v4 + 56);
    v36 = 0;
    *(_DWORD *)(a2 + 160) |= 0x40u;
    if ( v35 >= 0 )
      v36 = v35;
  }
  *(_DWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 112) = v36;
  v37 = *(_QWORD *)(v4 + 48);
  *(_QWORD *)(v4 + 8) = v37;
  if ( v37 < 0 )
  {
    archive_set_error(a1, 42, "Invalid LHa entry size");
    return 4294967266LL;
  }
  *(_QWORD *)v4 = 0;
  *(_WORD *)(v4 + 24) = 0;
  if ( *(_BYTE *)(v4 + 290) || !v37 )
    *(_BYTE *)(v4 + 292) = 1;
  snprintf(
    (char *const)(v4 + 295),
    0x40u,
    "lha -%c%c%c-",
    (unsigned int)*(char *)(v4 + 41),
    *(char *)(v4 + 42),
    *(char *)(v4 + 43));
  *(_QWORD *)(a1 + 24) = v4 + 295;
  return v20;
}

```

## disassembly

```asm
0x1800d3630  mov     [rsp-8+arg_8], rbx
0x1800d3635  mov     [rsp-8+arg_10], rsi
0x1800d363a  push    rbp
0x1800d363b  push    rdi
0x1800d363c  push    r12
0x1800d363e  push    r13
0x1800d3640  push    r14
0x1800d3642  lea     rbp, [rsp-37h]
0x1800d3647  sub     rsp, 0D0h
0x1800d364e  xor     eax, eax
0x1800d3650  mov     rbx, rdx
0x1800d3653  mov     rsi, rcx
0x1800d3656  mov     [rbp+57h+var_98], rax
0x1800d365a  xorps   xmm0, xmm0
0x1800d365d  mov     [rbp+57h+var_B0], rax
0x1800d3661  xorps   xmm1, xmm1
0x1800d3664  lea     rcx, [rbp+57h+var_90]; void *
0x1800d3668  lea     r8d, [rax+68h]; Size
0x1800d366c  xor     edx, edx; Val
0x1800d366e  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800d3672  movups  xmmword ptr [rbp+57h+Block], xmm1
0x1800d3676  call    memset_0
0x1800d367b  xor     r13d, r13d
0x1800d367e  mov     [rbp+57h+arg_0], r13
0x1800d3682  call    lha_crc16_init
0x1800d3687  mov     dword ptr [rsi+10h], 0B0000h
0x1800d368e  cmp     [rsi+18h], r13
0x1800d3692  jnz     short loc_1800D369F
0x1800d3694  lea     rax, aLha; "lha"
0x1800d369b  mov     [rsi+18h], rax
0x1800d369f  mov     rax, [rsi+818h]
0x1800d36a6  xor     r8d, r8d
0x1800d36a9  mov     rdi, [rax]
0x1800d36ac  lea     edx, [r8+16h]
0x1800d36b0  mov     [rdi+123h], r13w
0x1800d36b8  mov     [rdi+125h], r13b
0x1800d36bf  mov     [rdi+10h], r13
0x1800d36c3  mov     rcx, [rsi+278h]
0x1800d36ca  call    __archive_read_filter_ahead
0x1800d36cf  mov     r9, rax
0x1800d36d2  test    rax, rax
0x1800d36d5  jnz     short loc_1800D36F9
0x1800d36d7  mov     rcx, [rsi+278h]
0x1800d36de  lea     edx, [rax+1]
0x1800d36e1  xor     r8d, r8d
0x1800d36e4  call    __archive_read_filter_ahead
0x1800d36e9  test    rax, rax
0x1800d36ec  jz      short loc_1800D3742
0x1800d36ee  cmp     [rax], r13b
0x1800d36f1  jnz     loc_1800D38E7
0x1800d36f7  jmp     short loc_1800D3742
0x1800d36f9  cmp     [rdi+121h], r13b
0x1800d3700  jnz     short loc_1800D373D
0x1800d3702  cmp     byte ptr [rax], 4Dh ; 'M'
0x1800d3705  jnz     short loc_1800D373D
0x1800d3707  cmp     byte ptr [rax+1], 5Ah ; 'Z'
0x1800d370b  jnz     short loc_1800D373D
0x1800d370d  mov     rcx, rsi
0x1800d3710  call    lha_skip_sfx
0x1800d3715  cmp     eax, 0FFFFFFECh
0x1800d3718  jl      loc_1800D3DA3
0x1800d371e  mov     rcx, [rsi+278h]
0x1800d3725  xor     r8d, r8d
0x1800d3728  lea     edx, [r8+1]
0x1800d372c  call    __archive_read_filter_ahead
0x1800d3731  mov     r9, rax
0x1800d3734  test    rax, rax
0x1800d3737  jz      loc_1800D38E7
0x1800d373d  cmp     [r9], r13b
0x1800d3740  jnz     short loc_1800D374C
0x1800d3742  mov     eax, 1
0x1800d3747  jmp     loc_1800D3DA3
0x1800d374c  mov     rcx, r9
0x1800d374f  call    lha_check_header_format
0x1800d3754  test    rax, rax
0x1800d3757  jz      short loc_1800D3777
0x1800d3759  lea     r8, aBadLhaFile; "Bad LHa file"
0x1800d3760  mov     edx, 2Ah ; '*'
0x1800d3765  mov     rcx, rsi
0x1800d3768  call    archive_set_error
0x1800d376d  mov     eax, 0FFFFFFE2h
0x1800d3772  jmp     loc_1800D3DA3
0x1800d3777  mov     byte ptr [rdi+121h], 1
0x1800d377e  mov     r8d, 686Ch
0x1800d3784  mov     [rdi+20h], r13
0x1800d3788  mov     al, [r9+14h]
0x1800d378c  mov     [rdi+28h], al
0x1800d378f  mov     al, [r9+3]
0x1800d3793  mov     [rdi+29h], al
0x1800d3796  mov     al, [r9+4]
0x1800d379a  mov     [rdi+2Ah], al
0x1800d379d  mov     al, [r9+5]
0x1800d37a1  mov     [rdi+2Bh], al
0x1800d37a4  movzx   ecx, word ptr [rdi+29h]
0x1800d37a8  sub     ecx, r8d
0x1800d37ab  jnz     short loc_1800D37B3
0x1800d37ad  movzx   ecx, al
0x1800d37b0  sub     ecx, 64h ; 'd'
0x1800d37b3  test    ecx, ecx
0x1800d37b5  setz    dl
0x1800d37b8  mov     [rdi+122h], dl
0x1800d37be  movzx   ecx, word ptr [rdi+29h]
0x1800d37c2  sub     ecx, r8d
0x1800d37c5  jnz     short loc_1800D37CE
0x1800d37c7  movzx   ecx, byte ptr [rdi+2Bh]
0x1800d37cb  sub     ecx, 30h ; '0'
0x1800d37ce  test    ecx, ecx
0x1800d37d0  jz      short loc_1800D37EC
0x1800d37d2  movzx   ecx, word ptr [rdi+29h]
0x1800d37d6  mov     eax, 7A6Ch
0x1800d37db  sub     ecx, eax
0x1800d37dd  jnz     short loc_1800D37E6
0x1800d37df  movzx   ecx, byte ptr [rdi+2Bh]
0x1800d37e3  sub     ecx, 34h ; '4'
0x1800d37e6  mov     al, 1
0x1800d37e8  test    ecx, ecx
0x1800d37ea  jnz     short loc_1800D37EF
0x1800d37ec  mov     al, r13b
0x1800d37ef  mov     [rdi+126h], al
0x1800d37f5  neg     dl
0x1800d37f7  mov     [rdi+30h], r13
0x1800d37fb  sbb     ax, ax
0x1800d37fe  mov     [rdi+38h], r13
0x1800d3802  and     ax, 49h
0x1800d3806  mov     [rdi+40h], r13d
0x1800d380a  add     ax, 1B6h
0x1800d380e  mov     [rdi+48h], r13
0x1800d3812  mov     [rdi+74h], ax
0x1800d3816  mov     rax, [rdi+0D0h]
0x1800d381d  mov     [rdi+50h], r13d
0x1800d3821  mov     [rdi+58h], r13
0x1800d3825  mov     [rdi+60h], r13d
0x1800d3829  mov     [rdi+68h], r13
0x1800d382d  mov     [rdi+70h], r13d
0x1800d3831  mov     [rdi+78h], r13
0x1800d3835  mov     [rdi+80h], r13
0x1800d383c  mov     [rdi+0E0h], r13
0x1800d3843  mov     [rdi+0F8h], r13
0x1800d384a  mov     [rdi+120h], r13b
0x1800d3851  mov     [rdi+0C0h], rax
0x1800d3858  mov     [rdi+0C8h], rax
0x1800d385f  movzx   r9d, byte ptr [r9+14h]
0x1800d3864  mov     ecx, r9d
0x1800d3867  test    r9d, r9d
0x1800d386a  jz      short loc_1800D38BE
0x1800d386c  sub     ecx, 1
0x1800d386f  jz      short loc_1800D38B1
0x1800d3871  sub     ecx, 1
0x1800d3874  jz      short loc_1800D38A4
0x1800d3876  cmp     ecx, 1
0x1800d3879  mov     rcx, rsi
0x1800d387c  jz      short loc_1800D389A
0x1800d387e  lea     r8, aUnsupportedLha; "Unsupported LHa header level %d"
0x1800d3885  mov     edx, 2Ah ; '*'
0x1800d388a  call    archive_set_error
0x1800d388f  mov     r14d, 0FFFFFFE2h
0x1800d3895  jmp     loc_1800D3DA0
0x1800d389a  mov     rdx, rdi
0x1800d389d  call    lha_read_file_header_3
0x1800d38a2  jmp     short loc_1800D38C9
0x1800d38a4  mov     rdx, rdi
0x1800d38a7  mov     rcx, rsi
0x1800d38aa  call    lha_read_file_header_2
0x1800d38af  jmp     short loc_1800D38C9
0x1800d38b1  mov     rdx, rdi
0x1800d38b4  mov     rcx, rsi
0x1800d38b7  call    lha_read_file_header_1
0x1800d38bc  jmp     short loc_1800D38C9
0x1800d38be  mov     rdx, rdi
0x1800d38c1  mov     rcx, rsi
0x1800d38c4  call    lha_read_file_header_0
0x1800d38c9  mov     r14d, eax
0x1800d38cc  cmp     eax, 0FFFFFFECh
0x1800d38cf  jl      loc_1800D3DA0
0x1800d38d5  cmp     [rdi+122h], r13b
0x1800d38dc  jnz     short loc_1800D38F3
0x1800d38de  cmp     [rdi+0F8h], r13
0x1800d38e5  jnz     short loc_1800D38F3
0x1800d38e7  lea     r8, aTruncatedLhaHe; "Truncated LHa header"
0x1800d38ee  jmp     loc_1800D3760
0x1800d38f3  mov     [rbp+57h+Block], r13
0x1800d38f7  lea     rcx, [rbp+57h+var_90]
0x1800d38fb  mov     [rbp+57h+Block+8], r13
0x1800d38ff  mov     [rbp+57h+var_B0], r13
0x1800d3903  mov     [rbp+57h+var_A8], r13
0x1800d3907  mov     [rbp+57h+var_A8+8], r13
0x1800d390b  mov     [rbp+57h+var_98], r13
0x1800d390f  mov     [rbp+57h+var_90], r13
0x1800d3913  mov     [rbp+57h+var_88], r13
0x1800d3917  mov     [rbp+57h+var_80], r13
0x1800d391b  mov     [rbp+57h+var_48], r13
0x1800d391f  mov     [rbp+57h+var_40], r13
0x1800d3923  mov     [rbp+57h+var_38], r13
0x1800d3927  mov     [rbp+57h+var_78], r13
0x1800d392b  mov     [rbp+57h+var_70], r13
0x1800d392f  mov     [rbp+57h+var_68], r13
0x1800d3933  mov     [rbp+57h+var_60], r13
0x1800d3937  mov     [rbp+57h+var_58], r13
0x1800d393b  mov     [rbp+57h+var_50], r13
0x1800d393f  mov     r9, [rdi+0C0h]
0x1800d3946  mov     r8, [rdi+0E0h]
0x1800d394d  mov     rdx, [rdi+0D8h]
0x1800d3954  call    archive_mstring_copy_mbs_len_l
0x1800d3959  test    eax, eax
0x1800d395b  jz      short loc_1800D3982
0x1800d395d  mov     rcx, [rdi+0C0h]
0x1800d3964  call    archive_string_conversion_charset_name
0x1800d3969  mov     r9, rax
0x1800d396c  lea     r8, aPathnameCannot; "Pathname cannot be converted from %s to"...
0x1800d3973  mov     edx, 2Ah ; '*'
0x1800d3978  mov     rcx, rsi
0x1800d397b  call    archive_set_error
0x1800d3980  jmp     short loc_1800D3996
0x1800d3982  lea     r8, [rbp+57h+arg_0]
0x1800d3986  mov     rcx, rsi
0x1800d3989  lea     rdx, [rbp+57h+var_90]
0x1800d398d  call    archive_mstring_get_wcs
0x1800d3992  test    eax, eax
0x1800d3994  jz      short loc_1800D39CC
0x1800d3996  lea     rcx, [rbp+57h+var_90]
0x1800d399a  call    archive_mstring_clean
0x1800d399f  mov     rcx, [rbp+57h+Block]; Block
0x1800d39a3  mov     [rbp+57h+Block+8], r13
0x1800d39a7  mov     [rbp+57h+var_B0], r13
0x1800d39ab  call    cs:__imp_free
0x1800d39b1  mov     rcx, [rbp+57h+var_A8]; Block
0x1800d39b5  mov     [rbp+57h+Block], r13
0x1800d39b9  mov     [rbp+57h+var_A8+8], r13
0x1800d39bd  mov     [rbp+57h+var_98], r13
0x1800d39c1  call    cs:__imp_free
0x1800d39c7  jmp     loc_1800D376D
0x1800d39cc  lea     rdx, [rbp+57h+var_60]
0x1800d39d0  mov     [rbp+57h+Block+8], r13
0x1800d39d4  lea     rcx, [rbp+57h+Block]
0x1800d39d8  call    archive_wstring_concat
0x1800d39dd  mov     [rbp+57h+var_88], r13
0x1800d39e1  lea     rcx, [rbp+57h+var_90]
0x1800d39e5  mov     [rbp+57h+var_40], r13
0x1800d39e9  mov     [rbp+57h+var_70], r13
0x1800d39ed  mov     [rbp+57h+var_58], r13
0x1800d39f1  mov     r9, [rdi+0C8h]
0x1800d39f8  mov     r8, [rdi+0F8h]
0x1800d39ff  mov     rdx, [rdi+0F0h]
0x1800d3a06  call    archive_mstring_copy_mbs_len_l
0x1800d3a0b  test    eax, eax
0x1800d3a0d  jz      short loc_1800D3A34
0x1800d3a0f  mov     rcx, [rdi+0C8h]
0x1800d3a16  call    archive_string_conversion_charset_name
0x1800d3a1b  mov     r9, rax
0x1800d3a1e  lea     r8, aPathnameCannot; "Pathname cannot be converted from %s to"...
0x1800d3a25  mov     edx, 2Ah ; '*'
0x1800d3a2a  mov     rcx, rsi
0x1800d3a2d  call    archive_set_error
0x1800d3a32  jmp     short loc_1800D3A48
0x1800d3a34  lea     r8, [rbp+57h+arg_0]
0x1800d3a38  mov     rcx, rsi
0x1800d3a3b  lea     rdx, [rbp+57h+var_90]
0x1800d3a3f  call    archive_mstring_get_wcs
0x1800d3a44  test    eax, eax
0x1800d3a46  jz      short loc_1800D3A5C
0x1800d3a48  lea     rcx, [rbp+57h+var_90]
0x1800d3a4c  call    archive_mstring_clean
0x1800d3a51  mov     r14d, 0FFFFFFE2h
0x1800d3a57  jmp     loc_1800D3B09
0x1800d3a5c  lea     rdx, [rbp+57h+var_60]
0x1800d3a60  lea     rcx, [rbp+57h+Block]
0x1800d3a64  call    archive_wstring_concat
0x1800d3a69  lea     rcx, [rbp+57h+var_90]
0x1800d3a6d  call    archive_mstring_clean
0x1800d3a72  movzx   edx, word ptr [rdi+74h]
0x1800d3a76  mov     ecx, 0F000h
0x1800d3a7b  movzx   eax, dx
0x1800d3a7e  and     ax, cx
0x1800d3a81  mov     ecx, 0A000h
0x1800d3a86  cmp     ax, cx
0x1800d3a89  jnz     loc_1800D3B36
0x1800d3a8f  mov     rcx, [rbp+57h+Block]; Str
0x1800d3a93  mov     edx, 7Ch ; '|'; Ch
0x1800d3a98  call    cs:__imp_wcschr
0x1800d3a9e  mov     r13, rax
0x1800d3aa1  xor     eax, eax
0x1800d3aa3  test    r13, r13
0x1800d3aa6  jz      short loc_1800D3AEC
0x1800d3aa8  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800d3aac  lea     rdx, [r13+2]
0x1800d3ab0  mov     r8, r12
0x1800d3ab3  inc     r8
0x1800d3ab6  cmp     [rdx+r8*2], ax
0x1800d3abb  jnz     short loc_1800D3AB3
0x1800d3abd  lea     rcx, [rbp+57h+var_A8]
0x1800d3ac1  mov     [rbp+57h+var_A8+8], rax
0x1800d3ac5  call    archive_wstrncat
0x1800d3aca  xor     eax, eax
0x1800d3acc  mov     [r13+0], ax
0x1800d3ad1  xor     r13d, r13d
0x1800d3ad4  mov     rax, [rbp+57h+Block]
0x1800d3ad8  inc     r12
0x1800d3adb  cmp     [rax+r12*2], r13w
0x1800d3ae0  jnz     short loc_1800D3AD8
0x1800d3ae2  mov     [rbp+57h+Block+8], r12
  ... truncated ...
```
