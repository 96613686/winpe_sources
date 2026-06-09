# archive_read_format_7zip_read_header

- ea: `0x1800c5f00`
- end: `0x1800c63b8`
- name: `archive_read_format_7zip_read_header`
- size: `1208`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path`

## callees

- `0x180004814`
- `0x180006c00`
- `0x18000c0ec`
- `0x18000e764`
- `0x18000e920`
- `0x18000e9a0`
- `0x18000ea00`
- `0x18000eda0`
- `0x18001590c`
- `0x1800aba54`
- `0x1800b0a70`
- `0x1800b1580`
- `0x1800c5f00`
- `0x1800c95e4`
- `0x1800ed464`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c60da`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800c60da`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c5f7e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c5f88`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c5f92`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c5f9c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c6237`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c62d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c6342`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c6361`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c5f7e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c5f88`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c5f92`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c5f9c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c6237`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c62d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c6342`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800c6361`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800c61cb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800c61cb`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800c62b2`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800c62b2`

## string_xrefs

- `0x1800c60e5`: `Can't allocate memory for Pathname`
- `0x1800c610d`: `Pathname cannot be converted from %s to current locale.`

## pseudocode

```c
__int64 __fastcall archive_read_format_7zip_read_header(__int64 a1, __int64 a2)
{
  __int64 *v2; // rax
  size_t v3; // r13
  __int64 v6; // rbx
  unsigned int v7; // edi
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  int v13; // r12d
  unsigned __int64 v14; // rdx
  unsigned __int64 *v15; // r8
  unsigned __int64 v16; // rax
  const char *v17; // rax
  __int16 v18; // ax
  __int64 v19; // rdx
  _QWORD *v20; // rax
  void *v21; // r15
  _QWORD *v22; // rcx
  void *v23; // r15
  size_t v24; // r12
  size_t v25; // rdx
  __int64 v26; // rax
  __int16 v27; // ax
  __int64 v28; // rax
  char *v29; // rbx
  _BYTE v30[8]; // [rsp+20h] [rbp-30h] BYREF
  void *Block[2]; // [rsp+28h] [rbp-28h] BYREF
  void *v32[2]; // [rsp+38h] [rbp-18h]
  void *v33; // [rsp+48h] [rbp-8h]
  int v34; // [rsp+90h] [rbp+40h]
  size_t Size; // [rsp+A0h] [rbp+50h] BYREF
  void *Src; // [rsp+A8h] [rbp+58h] BYREF

  v2 = *(__int64 **)(a1 + 2072);
  v3 = 0;
  v6 = *v2;
  if ( *(_DWORD *)(*v2 + 20712) == -1 )
    *(_DWORD *)(v6 + 20712) = 0;
  *(_DWORD *)(a1 + 16) = 917504;
  if ( !*(_QWORD *)(a1 + 24) )
    *(_QWORD *)(a1 + 24) = "7-Zip";
  if ( *(_QWORD *)(v6 + 160) )
  {
    *(_QWORD *)(v6 + 168) += 80LL;
    v9 = *(_QWORD *)(v6 + 168);
  }
  else
  {
    *(_OWORD *)Block = 0;
    v33 = 0;
    *(_OWORD *)v32 = 0;
    v7 = slurp_central_directory(a1, v6, Block);
    free(Block[1]);
    free(v32[0]);
    free(v32[1]);
    free(v33);
    if ( v7 )
      return v7;
    v9 = *(_QWORD *)(v6 + 160);
    *(_QWORD *)(v6 + 144) = *(_QWORD *)(v6 + 152);
    *(_QWORD *)(v6 + 168) = v9;
  }
  v10 = *(_QWORD *)(v6 + 144);
  if ( !v10 || !v9 )
    return 1;
  *(_QWORD *)(v6 + 184) = 0;
  *(_QWORD *)(v6 + 144) = v10 - 1;
  *(_BYTE *)(v6 + 204) = 0;
  *(_DWORD *)(v6 + 200) = crc32(0, 0, 0);
  if ( !*(_QWORD *)(v6 + 20640) )
  {
    v11 = archive_string_conversion_from_charset(a1, "UTF-16LE", 1);
    *(_QWORD *)(v6 + 20640) = v11;
    if ( !v11 )
      return 4294967266LL;
  }
  v12 = *(unsigned int *)(v9 + 16);
  v13 = 0;
  v34 = 0;
  if ( v12 < *(_QWORD *)(v6 + 48) )
  {
    v14 = 0;
    v15 = (unsigned __int64 *)(*(_QWORD *)(v6 + 56) + 104 * v12);
    if ( v15 )
    {
      while ( v14 < *v15 )
      {
        v16 = v15[1];
        if ( *(_DWORD *)(v16 + 40 * v14) == 116457729
          || *(_DWORD *)(v16 + 40 * v14) == 116458243
          || *(_DWORD *)(v16 + 40 * v14) == 116459265 )
        {
          *(_BYTE *)(a2 + 800) |= 1u;
          *(_DWORD *)(v6 + 20712) = 1;
        }
        ++v14;
      }
    }
  }
  if ( *(_DWORD *)(v6 + 20712) == -1 )
    *(_DWORD *)(v6 + 20712) = 0;
  if ( (unsigned int)archive_mstring_copy_mbs_len_l(
                       a2 + 488,
                       *(_QWORD *)(v9 + 8),
                       *(_QWORD *)v9,
                       *(_QWORD *)(v6 + 20640)) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      archive_set_error(a1, 12, "Can't allocate memory for Pathname");
      return 4294967266LL;
    }
    v17 = (const char *)archive_string_conversion_charset_name(*(_QWORD *)(v6 + 20640));
    archive_set_error(a1, 42, "Pathname cannot be converted from %s to current locale.", v17);
    v13 = -20;
    v34 = -20;
  }
  v18 = *(_WORD *)(v9 + 68);
  *(_DWORD *)(a2 + 160) |= 0x600u;
  *(_WORD *)(a2 + 1032) = v18;
  *(_DWORD *)(a2 + 16) = 0;
  if ( (*(_BYTE *)(v9 + 24) & 1) != 0 )
    archive_entry_set_mtime(a2, *(_QWORD *)(v9 + 32), *(unsigned int *)(v9 + 56));
  if ( (*(_BYTE *)(v9 + 24) & 4) != 0 )
    archive_entry_set_ctime(a2, *(_QWORD *)(v9 + 48), *(unsigned int *)(v9 + 64));
  if ( (*(_BYTE *)(v9 + 24) & 2) != 0 )
    archive_entry_set_atime(a2, *(_QWORD *)(v9 + 40), *(unsigned int *)(v9 + 60));
  if ( *(_DWORD *)(v9 + 20) == -1 )
  {
    *(_QWORD *)(v6 + 192) = 0;
    v19 = 0;
  }
  else
  {
    v19 = *(_QWORD *)(*(_QWORD *)(v6 + 80) + 8LL * *(unsigned int *)(v9 + 20));
    *(_QWORD *)(v6 + 192) = v19;
    if ( v19 < 0 )
      v19 = 0;
  }
  *(_DWORD *)(a2 + 160) |= 0x40u;
  *(_DWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 112) = v19;
  if ( (*(_BYTE *)(v9 + 72) & 7) != 0 )
  {
    v20 = malloc(0x16u);
    v21 = v20;
    if ( v20 )
    {
      if ( (*(_BYTE *)(v9 + 72) & 1) != 0 )
      {
        v22 = (_QWORD *)((char *)v20 + 7);
        *v20 = 0x796C6E6F64722CLL;
      }
      else
      {
        v22 = v20;
      }
      if ( (*(_BYTE *)(v9 + 72) & 2) != 0 )
      {
        *v22 = 0x6E65646469682CLL;
        v22 = (_QWORD *)((char *)v22 + 7);
      }
      if ( (*(_BYTE *)(v9 + 72) & 4) != 0 )
      {
        *v22 = 0x6D65747379732CLL;
        v22 = (_QWORD *)((char *)v22 + 7);
      }
      if ( v22 > v20 )
        archive_entry_copy_fflags_text(a2, (char *)v20 + 1);
      free(v21);
    }
  }
  if ( !*(_QWORD *)(v6 + 192) )
    *(_BYTE *)(v6 + 204) = 1;
  if ( (*(_WORD *)(v9 + 68) & 0xF000) == 0xA000 )
  {
    v23 = 0;
    while ( *(_QWORD *)(v6 + 192) )
    {
      Src = 0;
      Size = 0;
      v13 = archive_read_format_7zip_read_data(a1, &Src, &Size, v30);
      if ( v13 < -20 )
        goto LABEL_66;
      v24 = Size;
      v25 = Size + v3 + 1;
      Size += v3;
      v26 = _o_realloc(v23, v25);
      if ( !v26 )
      {
        free(v23);
        archive_set_error(a1, 12, "Can't allocate memory for Symname");
        return 4294967266LL;
      }
      v23 = (void *)v26;
      memcpy_0((void *)(v26 + v3), Src, v24);
      v3 = Size;
    }
    if ( v3 )
    {
      *((_BYTE *)v23 + v3) = 0;
      v28 = archive_string_conversion_from_charset(a1, "UTF-8", 1);
      if ( !v28 )
      {
        v13 = -30;
LABEL_66:
        free(v23);
        return (unsigned int)v13;
      }
      archive_entry_copy_symlink_l(a2, v23, v3, v28);
    }
    else
    {
      *(_WORD *)(v9 + 68) &= 0xFFFu;
      *(_WORD *)(v9 + 68) |= 0x8000u;
      v27 = *(_WORD *)(v9 + 68);
      *(_DWORD *)(a2 + 160) |= 0x600u;
      *(_WORD *)(a2 + 1032) = v27;
      *(_DWORD *)(a2 + 16) = 0;
    }
    free(v23);
    *(_DWORD *)(a2 + 160) |= 0x40u;
    *(_DWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 112) = 0;
    v13 = v34;
  }
  v29 = (char *)(v6 + 20648);
  snprintf(v29, 0x40u, "7-Zip");
  *(_QWORD *)(a1 + 24) = v29;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800c5f00  mov     [rsp-38h+arg_8], rbx
0x1800c5f05  push    rbp
0x1800c5f06  push    rsi
0x1800c5f07  push    rdi
0x1800c5f08  push    r12
0x1800c5f0a  push    r13
0x1800c5f0c  push    r14
0x1800c5f0e  push    r15
0x1800c5f10  mov     rbp, rsp
0x1800c5f13  sub     rsp, 50h
0x1800c5f17  mov     rax, [rcx+818h]
0x1800c5f1e  xor     r13d, r13d
0x1800c5f21  mov     rsi, rdx
0x1800c5f24  mov     r14, rcx
0x1800c5f27  mov     rbx, [rax]
0x1800c5f2a  cmp     dword ptr [rbx+50E8h], 0FFFFFFFFh
0x1800c5f31  jnz     short loc_1800C5F3A
0x1800c5f33  mov     [rbx+50E8h], r13d
0x1800c5f3a  lea     rax, a7Zip; "7-Zip"
0x1800c5f41  mov     dword ptr [rcx+10h], 0E0000h
0x1800c5f48  cmp     [rcx+18h], r13
0x1800c5f4c  jnz     short loc_1800C5F52
0x1800c5f4e  mov     [rcx+18h], rax
0x1800c5f52  cmp     [rbx+0A0h], r13
0x1800c5f59  jnz     short loc_1800C5FCB
0x1800c5f5b  xorps   xmm0, xmm0
0x1800c5f5e  lea     r8, [rbp+Block]
0x1800c5f62  xor     eax, eax
0x1800c5f64  mov     rdx, rbx
0x1800c5f67  movups  xmmword ptr [rbp+Block], xmm0
0x1800c5f6b  mov     [rbp+var_8], rax
0x1800c5f6f  movups  xmmword ptr [rbp+var_18], xmm0
0x1800c5f73  call    slurp_central_directory
0x1800c5f78  mov     rcx, [rbp+Block+8]; Block
0x1800c5f7c  mov     edi, eax
0x1800c5f7e  call    cs:__imp_free
0x1800c5f84  mov     rcx, [rbp+var_18]; Block
0x1800c5f88  call    cs:__imp_free
0x1800c5f8e  mov     rcx, [rbp+var_18+8]; Block
0x1800c5f92  call    cs:__imp_free
0x1800c5f98  mov     rcx, [rbp+var_8]; Block
0x1800c5f9c  call    cs:__imp_free
0x1800c5fa2  test    edi, edi
0x1800c5fa4  jz      short loc_1800C5FAD
0x1800c5fa6  mov     eax, edi
0x1800c5fa8  jmp     loc_1800C63A0
0x1800c5fad  mov     rax, [rbx+98h]
0x1800c5fb4  mov     rdi, [rbx+0A0h]
0x1800c5fbb  mov     [rbx+90h], rax
0x1800c5fc2  mov     [rbx+0A8h], rdi
0x1800c5fc9  jmp     short loc_1800C5FDA
0x1800c5fcb  add     qword ptr [rbx+0A8h], 50h ; 'P'
0x1800c5fd3  mov     rdi, [rbx+0A8h]
0x1800c5fda  mov     rax, [rbx+90h]
0x1800c5fe1  test    rax, rax
0x1800c5fe4  jz      loc_1800C639B
0x1800c5fea  test    rdi, rdi
0x1800c5fed  jz      loc_1800C639B
0x1800c5ff3  dec     rax
0x1800c5ff6  mov     [rbx+0B8h], r13
0x1800c5ffd  xor     r8d, r8d
0x1800c6000  mov     [rbx+90h], rax
0x1800c6007  xor     edx, edx
0x1800c6009  mov     [rbx+0CCh], r13b
0x1800c6010  xor     ecx, ecx
0x1800c6012  call    crc32
0x1800c6017  mov     [rbx+0C8h], eax
0x1800c601d  cmp     [rbx+50A0h], r13
0x1800c6024  jnz     short loc_1800C6051
0x1800c6026  mov     r8d, 1
0x1800c602c  lea     rdx, aUtf16le; "UTF-16LE"
0x1800c6033  mov     rcx, r14
0x1800c6036  call    archive_string_conversion_from_charset
0x1800c603b  mov     [rbx+50A0h], rax
0x1800c6042  test    rax, rax
0x1800c6045  jnz     short loc_1800C6051
0x1800c6047  mov     eax, 0FFFFFFE2h
0x1800c604c  jmp     loc_1800C63A0
0x1800c6051  mov     eax, [rdi+10h]
0x1800c6054  mov     r12d, r13d
0x1800c6057  mov     [rbp+arg_0], r13d
0x1800c605b  cmp     rax, [rbx+30h]
0x1800c605f  jnb     short loc_1800C60AC
0x1800c6061  imul    r8, rax, 68h ; 'h'
0x1800c6065  mov     rdx, r13
0x1800c6068  add     r8, [rbx+38h]
0x1800c606c  jz      short loc_1800C60AC
0x1800c606e  cmp     rdx, [r8]
0x1800c6071  jnb     short loc_1800C60AC
0x1800c6073  mov     rax, [r8+8]
0x1800c6077  lea     rcx, [rdx+rdx*4]
0x1800c607b  cmp     dword ptr [rax+rcx*8], 6F10101h
0x1800c6082  jz      short loc_1800C6096
0x1800c6084  cmp     dword ptr [rax+rcx*8], 6F10303h
0x1800c608b  jz      short loc_1800C6096
0x1800c608d  cmp     dword ptr [rax+rcx*8], 6F10701h
0x1800c6094  jnz     short loc_1800C60A7
0x1800c6096  or      byte ptr [rsi+320h], 1
0x1800c609d  mov     dword ptr [rbx+50E8h], 1
0x1800c60a7  inc     rdx
0x1800c60aa  jmp     short loc_1800C606E
0x1800c60ac  cmp     dword ptr [rbx+50E8h], 0FFFFFFFFh
0x1800c60b3  jnz     short loc_1800C60BC
0x1800c60b5  mov     [rbx+50E8h], r13d
0x1800c60bc  mov     r9, [rbx+50A0h]
0x1800c60c3  lea     rcx, [rsi+1E8h]
0x1800c60ca  mov     r8, [rdi]
0x1800c60cd  mov     rdx, [rdi+8]
0x1800c60d1  call    archive_mstring_copy_mbs_len_l
0x1800c60d6  test    eax, eax
0x1800c60d8  jz      short loc_1800C612B
0x1800c60da  call    cs:__imp__o__errno
0x1800c60e0  cmp     dword ptr [rax], 0Ch
0x1800c60e3  jnz     short loc_1800C60FE
0x1800c60e5  lea     r8, aCanTAllocateMe_24; "Can't allocate memory for Pathname"
0x1800c60ec  mov     edx, 0Ch
0x1800c60f1  mov     rcx, r14
0x1800c60f4  call    archive_set_error
0x1800c60f9  jmp     loc_1800C6047
0x1800c60fe  mov     rcx, [rbx+50A0h]
0x1800c6105  call    archive_string_conversion_charset_name
0x1800c610a  mov     r9, rax
0x1800c610d  lea     r8, aPathnameCannot_0; "Pathname cannot be converted from %s to"...
0x1800c6114  mov     edx, 2Ah ; '*'
0x1800c6119  mov     rcx, r14
0x1800c611c  call    archive_set_error
0x1800c6121  mov     r12d, 0FFFFFFECh
0x1800c6127  mov     [rbp+arg_0], r12d
0x1800c612b  movzx   eax, word ptr [rdi+44h]
0x1800c612f  or      dword ptr [rsi+0A0h], 600h
0x1800c6139  mov     [rsi+408h], ax
0x1800c6140  mov     [rsi+10h], r13d
0x1800c6144  test    byte ptr [rdi+18h], 1
0x1800c6148  jz      short loc_1800C615A
0x1800c614a  mov     r8d, [rdi+38h]
0x1800c614e  mov     rcx, rsi
0x1800c6151  mov     rdx, [rdi+20h]
0x1800c6155  call    archive_entry_set_mtime
0x1800c615a  test    byte ptr [rdi+18h], 4
0x1800c615e  jz      short loc_1800C6170
0x1800c6160  mov     r8d, [rdi+40h]
0x1800c6164  mov     rcx, rsi
0x1800c6167  mov     rdx, [rdi+30h]
0x1800c616b  call    archive_entry_set_ctime
0x1800c6170  test    byte ptr [rdi+18h], 2
0x1800c6174  jz      short loc_1800C6186
0x1800c6176  mov     r8d, [rdi+3Ch]
0x1800c617a  mov     rcx, rsi
0x1800c617d  mov     rdx, [rdi+28h]
0x1800c6181  call    archive_entry_set_atime
0x1800c6186  cmp     dword ptr [rdi+14h], 0FFFFFFFFh
0x1800c618a  jz      short loc_1800C61A7
0x1800c618c  mov     ecx, [rdi+14h]
0x1800c618f  mov     rax, [rbx+50h]
0x1800c6193  mov     rdx, [rax+rcx*8]
0x1800c6197  test    rdx, rdx
0x1800c619a  mov     [rbx+0C0h], rdx
0x1800c61a1  cmovs   rdx, r13
0x1800c61a5  jmp     short loc_1800C61B1
0x1800c61a7  mov     [rbx+0C0h], r13
0x1800c61ae  mov     rdx, r13
0x1800c61b1  or      dword ptr [rsi+0A0h], 40h
0x1800c61b8  mov     [rsi+10h], r13d
0x1800c61bc  mov     [rsi+70h], rdx
0x1800c61c0  test    byte ptr [rdi+48h], 7
0x1800c61c4  jz      short loc_1800C623D
0x1800c61c6  mov     ecx, 16h; Size
0x1800c61cb  call    cs:__imp_malloc
0x1800c61d1  mov     r15, rax
0x1800c61d4  test    rax, rax
0x1800c61d7  jz      short loc_1800C623D
0x1800c61d9  test    byte ptr [rdi+48h], 1
0x1800c61dd  jz      short loc_1800C61F2
0x1800c61df  mov     rax, 796C6E6F64722Ch
0x1800c61e9  lea     rcx, [r15+7]
0x1800c61ed  mov     [r15], rax
0x1800c61f0  jmp     short loc_1800C61F5
0x1800c61f2  mov     rcx, r15
0x1800c61f5  test    byte ptr [rdi+48h], 2
0x1800c61f9  jz      short loc_1800C620C
0x1800c61fb  mov     rax, 6E65646469682Ch
0x1800c6205  mov     [rcx], rax
0x1800c6208  add     rcx, 7
0x1800c620c  test    byte ptr [rdi+48h], 4
0x1800c6210  jz      short loc_1800C6223
0x1800c6212  mov     rax, 6D65747379732Ch
0x1800c621c  mov     [rcx], rax
0x1800c621f  add     rcx, 7
0x1800c6223  cmp     rcx, r15
0x1800c6226  jbe     short loc_1800C6234
0x1800c6228  lea     rdx, [r15+1]
0x1800c622c  mov     rcx, rsi
0x1800c622f  call    archive_entry_copy_fflags_text
0x1800c6234  mov     rcx, r15; Block
0x1800c6237  call    cs:__imp_free
0x1800c623d  cmp     qword ptr [rbx+0C0h], 1
0x1800c6245  jnb     short loc_1800C624E
0x1800c6247  mov     byte ptr [rbx+0CCh], 1
0x1800c624e  movzx   eax, word ptr [rdi+44h]
0x1800c6252  mov     ecx, 0F000h
0x1800c6257  and     ax, cx
0x1800c625a  mov     ecx, 0A000h
0x1800c625f  cmp     ax, cx
0x1800c6262  jnz     loc_1800C637A
0x1800c6268  mov     r15, r13
0x1800c626b  xor     r12d, r12d
0x1800c626e  cmp     [rbx+0C0h], r12
0x1800c6275  jbe     short loc_1800C62EB
0x1800c6277  lea     r9, [rbp+var_30]
0x1800c627b  mov     [rbp+Src], r12
0x1800c627f  lea     r8, [rbp+Size]
0x1800c6283  mov     [rbp+Size], r12
0x1800c6287  lea     rdx, [rbp+Src]
0x1800c628b  mov     rcx, r14
0x1800c628e  call    archive_read_format_7zip_read_data
0x1800c6293  mov     r12d, eax
0x1800c6296  cmp     eax, 0FFFFFFECh
0x1800c6299  jl      loc_1800C633F
0x1800c629f  mov     r12, [rbp+Size]
0x1800c62a3  mov     rcx, r15
0x1800c62a6  lea     rax, [r12+r13]
0x1800c62aa  lea     rdx, [rax+1]
0x1800c62ae  mov     [rbp+Size], rax
0x1800c62b2  call    cs:__imp__o_realloc
0x1800c62b8  test    rax, rax
0x1800c62bb  jz      short loc_1800C62D6
0x1800c62bd  mov     rdx, [rbp+Src]; Src
0x1800c62c1  lea     rcx, [rax+r13]; void *
0x1800c62c5  mov     r8, r12; Size
0x1800c62c8  mov     r15, rax
0x1800c62cb  call    memcpy_0
0x1800c62d0  mov     r13, [rbp+Size]
0x1800c62d4  jmp     short loc_1800C626B
0x1800c62d6  mov     rcx, r15; Block
0x1800c62d9  call    cs:__imp_free
0x1800c62df  lea     r8, aCanTAllocateMe_12; "Can't allocate memory for Symname"
0x1800c62e6  jmp     loc_1800C60EC
0x1800c62eb  test    r13, r13
0x1800c62ee  jnz     short loc_1800C631D
0x1800c62f0  mov     eax, 0FFFh
0x1800c62f5  and     [rdi+44h], ax
0x1800c62f9  mov     eax, 8000h
0x1800c62fe  or      [rdi+44h], ax
0x1800c6302  movzx   eax, word ptr [rdi+44h]
0x1800c6306  or      dword ptr [rsi+0A0h], 600h
0x1800c6310  mov     [rsi+408h], ax
0x1800c6317  mov     [rsi+10h], r12d
0x1800c631b  jmp     short loc_1800C635E
0x1800c631d  mov     r8d, 1
0x1800c6323  mov     [r15+r13], r12b
0x1800c6327  lea     rdx, Str2; "UTF-8"
0x1800c632e  mov     rcx, r14
0x1800c6331  call    archive_string_conversion_from_charset
0x1800c6336  test    rax, rax
0x1800c6339  jnz     short loc_1800C634D
0x1800c633b  lea     r12d, [rax-1Eh]
0x1800c633f  mov     rcx, r15; Block
0x1800c6342  call    cs:__imp_free
0x1800c6348  mov     eax, r12d
0x1800c634b  jmp     short loc_1800C63A0
0x1800c634d  mov     r9, rax
0x1800c6350  mov     r8, r13
0x1800c6353  mov     rdx, r15
0x1800c6356  mov     rcx, rsi
0x1800c6359  call    _archive_entry_copy_symlink_l
0x1800c635e  mov     rcx, r15; Block
0x1800c6361  call    cs:__imp_free
0x1800c6367  or      dword ptr [rsi+0A0h], 40h
0x1800c636e  mov     [rsi+10h], r12d
0x1800c6372  mov     [rsi+70h], r12
0x1800c6376  mov     r12d, [rbp+arg_0]
0x1800c637a  add     rbx, 50A8h
0x1800c6381  lea     r8, a7Zip; "7-Zip"
0x1800c6388  mov     rcx, rbx; Buffer
0x1800c638b  mov     edx, 40h ; '@'; BufferCount
0x1800c6390  call    snprintf
0x1800c6395  mov     [r14+18h], rbx
0x1800c6399  jmp     short loc_1800C6348
0x1800c639b  mov     eax, 1
0x1800c63a0  mov     rbx, [rsp+50h+arg_8]
0x1800c63a8  add     rsp, 50h
0x1800c63ac  pop     r15
0x1800c63ae  pop     r14
0x1800c63b0  pop     r13
0x1800c63b2  pop     r12
0x1800c63b4  pop     rdi
0x1800c63b5  pop     rsi
0x1800c63b6  pop     rbp
0x1800c63b7  retn
```
