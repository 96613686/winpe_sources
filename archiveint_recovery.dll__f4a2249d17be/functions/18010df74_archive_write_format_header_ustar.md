# __archive_write_format_header_ustar

- ea: `0x18010df74`
- end: `0x18010e69f`
- name: `__archive_write_format_header_ustar`
- size: `1835`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path`

## callers

- `0x18010ad80`
- `0x18010e7b0`

## callees

- `0x180006c00`
- `0x1800aba54`
- `0x1800b0ac4`
- `0x1800b0b0c`
- `0x1800b20d0`
- `0x1800b2100`
- `0x1800ed038`
- `0x1800ed464`
- `0x1800f8774`
- `0x18010df74`
- `0x18010eb0c`
- `0x18010eb70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010e031`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010e14c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010e1b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010e25d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010e30f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010e031`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010e14c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010e1b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010e25d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010e30f`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18010e0a6`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18010e0c1`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18010e0a6`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x18010e0c1`

## string_xrefs

- `0x18010e03c`: `Can't allocate memory for Pathname`
- `0x18010e1bc`: `Can't allocate memory for Linkname`
- `0x18010e06a`: `Can't translate pathname '%s' to %s`
- `0x18010e167`: `Can't translate linkname '%s' to %s`
- `0x18010e1d4`: `Can't translate linkname '%s' to %s`
- `0x18010e0e5`: `Pathname too long`
- `0x18010e20b`: `Link contents too long`

## pseudocode

```c
__int64 __fastcall _archive_write_format_header_ustar(__int64 a1, _BYTE *a2, __int64 a3, int a4, int a5, __int64 a6)
{
  _OWORD *v7; // rax
  __int64 v10; // rdx
  unsigned int v11; // r15d
  _OWORD *v12; // rcx
  __int128 v13; // xmm1
  __int64 v14; // rbx
  int mbs_l; // eax
  const char *v16; // r14
  const char *v18; // rax
  unsigned __int64 v19; // r12
  size_t v20; // r8
  const char *v21; // rdx
  char *v22; // rax
  unsigned __int64 v23; // rbx
  __int64 v24; // r14
  int v25; // eax
  const char *v26; // rbx
  const char *v27; // rax
  size_t v28; // r8
  const char *v29; // rax
  const char *v30; // rax
  size_t v31; // r8
  int v32; // r12d
  int v33; // eax
  const char *v34; // rbx
  const char *v35; // rax
  size_t v36; // r8
  unsigned __int64 v37; // rax
  int v38; // r12d
  int v39; // eax
  int v40; // eax
  char v41; // al
  __int16 v42; // r14
  __m128i v43; // xmm1
  __int64 v44; // rax
  __m128i v45; // xmm0
  __m128i v46; // xmm0
  __m128i v47; // xmm0
  __m128i v48; // xmm1
  void *v49[2]; // [rsp+30h] [rbp-10h] BYREF
  void *Src; // [rsp+88h] [rbp+48h] BYREF
  unsigned __int64 v51; // [rsp+90h] [rbp+50h] BYREF
  int v52; // [rsp+98h] [rbp+58h]

  v52 = a4;
  v7 = a2;
  v51 = 0;
  v49[0] = 0;
  Src = 0;
  v10 = 4;
  v11 = 0;
  v12 = &unk_180142790;
  do
  {
    *v7 = *v12;
    v7[1] = v12[1];
    v7[2] = v12[2];
    v7[3] = v12[3];
    v7[4] = v12[4];
    v7[5] = v12[5];
    v7[6] = v12[6];
    v13 = v12[7];
    v12 += 8;
    v7[7] = v13;
    v7 += 8;
    --v10;
  }
  while ( v10 );
  v14 = a6;
  mbs_l = archive_mstring_get_mbs_l(*(_QWORD *)a3, (int)a3 + 488, (unsigned int)&Src, (unsigned int)&v51, a6);
  v16 = (const char *)Src;
  if ( mbs_l )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      archive_set_error(a1, 12, "Can't allocate memory for Pathname");
      return 4294967266LL;
    }
    v18 = (const char *)archive_string_conversion_charset_name(v14);
    archive_set_error(a1, 42, "Can't translate pathname '%s' to %s", v16, v18);
    v11 = -20;
  }
  v19 = v51;
  if ( v51 > 0x64 )
  {
    v22 = strchr(&v16[v51 - 101], 47);
    v49[0] = v22;
    v23 = (unsigned __int64)v22;
    if ( v22 == v16 )
    {
      v22 = strchr(v22 + 1, 47);
      v23 = (unsigned __int64)v22;
      v49[0] = v22;
    }
    if ( !v23 || !v22[1] || v23 > (unsigned __int64)(v16 + 155) )
    {
      archive_set_error(a1, 38, "Pathname too long");
      v11 = -25;
      goto LABEL_18;
    }
    memcpy_0(a2 + 345, v16, v23 - (_QWORD)v16);
    v20 = (size_t)&v16[v19 - 1 - v23];
    v21 = (const char *)(v23 + 1);
  }
  else
  {
    v20 = v51;
    v21 = v16;
  }
  memcpy_0(a2, v21, v20);
LABEL_18:
  v24 = a6;
  v25 = archive_entry_hardlink_l(a3, v49, &v51, a6);
  v26 = (const char *)v49[0];
  if ( v25 )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
LABEL_25:
      archive_set_error(a1, 12, "Can't allocate memory for Linkname");
      return 4294967266LL;
    }
    v27 = (const char *)archive_string_conversion_charset_name(v24);
    archive_set_error(a1, 42, "Can't translate linkname '%s' to %s", v26, v27);
    v11 = -20;
  }
  v28 = v51;
  if ( v51 )
  {
    LODWORD(Src) = 49;
    goto LABEL_29;
  }
  LODWORD(Src) = -1;
  if ( (unsigned int)archive_entry_symlink_l(a3, v49, &v51, v24) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
      goto LABEL_25;
    v29 = (const char *)archive_string_conversion_charset_name(v24);
    v26 = (const char *)v49[0];
    archive_set_error(a1, 42, "Can't translate linkname '%s' to %s", (const char *)v49[0], v29);
    v11 = -20;
  }
  else
  {
    v26 = (const char *)v49[0];
  }
  v28 = v51;
LABEL_29:
  if ( v28 )
  {
    if ( v28 > 0x64 )
    {
      archive_set_error(a1, 38, "Link contents too long");
      v11 = -25;
      v28 = 100;
      v51 = 100;
    }
    memcpy_0(a2 + 157, v26, v28);
  }
  if ( (unsigned int)archive_mstring_get_mbs_l(*(_QWORD *)a3, (int)a3 + 592, (unsigned int)v49, (unsigned int)&v51, v24) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      archive_set_error(a1, 12, "Can't allocate memory for Uname");
      return 4294967266LL;
    }
    v30 = (const char *)archive_string_conversion_charset_name(v24);
    archive_set_error(a1, 42, "Can't translate uname '%s' to %s", (const char *)v49[0], v30);
    v11 = -20;
  }
  v31 = v51;
  v32 = v52;
  if ( v51 )
  {
    if ( v51 > 0x20 )
    {
      if ( v52 != 120 )
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "Username too long");
        v11 = -25;
      }
      v31 = 32;
      v51 = 32;
    }
    memcpy_0(a2 + 265, v49[0], v31);
  }
  v33 = archive_mstring_get_mbs_l(*(_QWORD *)a3, (int)a3 + 280, (unsigned int)v49, (unsigned int)&v51, v24);
  v34 = (const char *)v49[0];
  if ( v33 )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      archive_set_error(a1, 12, "Can't allocate memory for Gname");
      return 4294967266LL;
    }
    v35 = (const char *)archive_string_conversion_charset_name(v24);
    archive_set_error(a1, 42, "Can't translate gname '%s' to %s", v34, v35);
    v11 = -20;
  }
  v36 = v51;
  if ( v51 )
  {
    v37 = -1;
    do
      ++v37;
    while ( v34[v37] );
    if ( v37 > 0x20 )
    {
      if ( v32 != 120 )
      {
        archive_set_error(a1, 0xFFFFFFFFLL, "Group name too long");
        v11 = -25;
      }
      v36 = 32;
    }
    memcpy_0(a2 + 297, v34, v36);
  }
  v38 = a5;
  if ( (unsigned int)format_number_0(*(_WORD *)(a3 + 1032) & 0xFFF, (int)a2 + 100, 6, 8, a5) )
  {
    archive_set_error(a1, 34, "Numeric mode too large");
    v11 = -25;
  }
  if ( (unsigned int)format_number_0(*(_QWORD *)(a3 + 120), (int)a2 + 108, 6, 8, v38) )
  {
    archive_set_error(a1, 34, "Numeric user ID too large");
    v11 = -25;
  }
  if ( (unsigned int)format_number_0(*(_QWORD *)(a3 + 88), (int)a2 + 116, 6, 8, v38) )
  {
    archive_set_error(a1, 34, "Numeric group ID too large");
    v11 = -25;
  }
  if ( (unsigned int)format_number_0(*(_QWORD *)(a3 + 112), (int)a2 + 124, 11, 12, v38) )
  {
    archive_set_error(a1, 34, "File size out of range");
    v11 = -25;
  }
  if ( (unsigned int)format_number_0(*(_QWORD *)(a3 + 56), (int)a2 + 136, 11, 11, v38) )
  {
    archive_set_error(a1, 34, "File modification time too large");
    v11 = -25;
  }
  if ( (((*(_WORD *)(a3 + 1032) & 0xF000) - 0x2000) & 0xBFFF) == 0 )
  {
    v39 = archive_entry_rdevmajor(a3, 0x2000);
    if ( (unsigned int)format_number_0(v39, (int)a2 + 329, 6, 8, v38) )
    {
      archive_set_error(a1, 34, "Major device number too large");
      v11 = -25;
    }
    v40 = archive_entry_rdevminor(a3);
    if ( (unsigned int)format_number_0(v40, (int)a2 + 337, 6, 8, v38) )
    {
      archive_set_error(a1, 34, "Minor device number too large");
      v11 = -25;
    }
  }
  v41 = v52;
  if ( v52 < 0 && (v41 = (char)Src, (int)Src < 0) )
  {
    v42 = *(_WORD *)(a3 + 1032) & 0xF000;
    switch ( v42 )
    {
      case 4096:
        a2[156] = 54;
        break;
      case 8192:
        a2[156] = 51;
        break;
      case 16384:
        a2[156] = 53;
        break;
      case 24576:
        a2[156] = 52;
        break;
      case -32768:
        a2[156] = 48;
        break;
      case -24576:
        a2[156] = 50;
        break;
      default:
        _archive_write_entry_filetype_unsupported(a1, a3, "ustar");
        v11 = -25;
        break;
    }
  }
  else
  {
    a2[156] = v41;
  }
  v43 = 0;
  v44 = 0;
  do
  {
    v45 = _mm_cvtsi32_si128(*(_DWORD *)&a2[v44]);
    v44 += 4;
    v46 = _mm_unpacklo_epi8(v45, v45);
    v47 = _mm_add_epi32(
            (__m128i)_mm_and_ps((__m128)_mm_srai_epi32(_mm_unpacklo_epi16(v46, v46), 0x18u), (__m128)_xmm),
            v43);
    v43 = v47;
  }
  while ( v44 != 512 );
  v48 = _mm_add_epi32(v47, _mm_srli_si128(v47, 8));
  a2[154] = 0;
  format_octal_2((unsigned int)_mm_cvtsi128_si32(_mm_add_epi32(v48, _mm_srli_si128(v48, 4))), a2 + 148, 6);
  return v11;
}

```

## disassembly

```asm
0x18010df74  mov     [rsp-38h+arg_0], rbx
0x18010df79  mov     [rsp-38h+arg_18], r9d
0x18010df7e  push    rbp
0x18010df7f  push    rsi
0x18010df80  push    rdi
0x18010df81  push    r12
0x18010df83  push    r13
0x18010df85  push    r14
0x18010df87  push    r15
0x18010df89  mov     rbp, rsp
0x18010df8c  sub     rsp, 40h
0x18010df90  xor     r12d, r12d
0x18010df93  mov     rdi, rdx
0x18010df96  mov     rax, rdx
0x18010df99  mov     [rbp+arg_10], r12
0x18010df9d  mov     r13, r8
0x18010dfa0  mov     [rbp+var_10], r12
0x18010dfa4  mov     rsi, rcx
0x18010dfa7  mov     [rbp+Src], r12
0x18010dfab  lea     edx, [r12+4]
0x18010dfb0  mov     r15d, r12d
0x18010dfb3  lea     r8d, [rdx+7Ch]
0x18010dfb7  lea     rcx, unk_180142790
0x18010dfbe  movups  xmm0, xmmword ptr [rcx]
0x18010dfc1  movups  xmmword ptr [rax], xmm0
0x18010dfc4  movups  xmm1, xmmword ptr [rcx+10h]
0x18010dfc8  movups  xmmword ptr [rax+10h], xmm1
0x18010dfcc  movups  xmm0, xmmword ptr [rcx+20h]
0x18010dfd0  movups  xmmword ptr [rax+20h], xmm0
0x18010dfd4  movups  xmm1, xmmword ptr [rcx+30h]
0x18010dfd8  movups  xmmword ptr [rax+30h], xmm1
0x18010dfdc  movups  xmm0, xmmword ptr [rcx+40h]
0x18010dfe0  movups  xmmword ptr [rax+40h], xmm0
0x18010dfe4  movups  xmm1, xmmword ptr [rcx+50h]
0x18010dfe8  movups  xmmword ptr [rax+50h], xmm1
0x18010dfec  movups  xmm0, xmmword ptr [rcx+60h]
0x18010dff0  movups  xmmword ptr [rax+60h], xmm0
0x18010dff4  movups  xmm1, xmmword ptr [rcx+70h]
0x18010dff8  add     rcx, r8
0x18010dffb  movups  xmmword ptr [rax+70h], xmm1
0x18010dfff  add     rax, r8
0x18010e002  sub     rdx, 1
0x18010e006  jnz     short loc_18010DFBE
0x18010e008  mov     rbx, [rbp+arg_28]
0x18010e00c  lea     rdx, [r13+1E8h]
0x18010e013  mov     rcx, [r13+0]
0x18010e017  lea     r9, [rbp+arg_10]
0x18010e01b  lea     r8, [rbp+Src]
0x18010e01f  mov     [rsp+40h+var_20], rbx
0x18010e024  call    archive_mstring_get_mbs_l
0x18010e029  mov     r14, [rbp+Src]
0x18010e02d  test    eax, eax
0x18010e02f  jz      short loc_18010E084
0x18010e031  call    cs:__imp__o__errno
0x18010e037  cmp     dword ptr [rax], 0Ch
0x18010e03a  jnz     short loc_18010E05A
0x18010e03c  lea     r8, aCanTAllocateMe_24; "Can't allocate memory for Pathname"
0x18010e043  mov     edx, 0Ch
0x18010e048  mov     rcx, rsi
0x18010e04b  call    archive_set_error
0x18010e050  mov     eax, 0FFFFFFE2h
0x18010e055  jmp     loc_18010E687
0x18010e05a  mov     rcx, rbx
0x18010e05d  call    archive_string_conversion_charset_name
0x18010e062  mov     r9, r14
0x18010e065  mov     [rsp+40h+var_20], rax
0x18010e06a  lea     r8, aCanTTranslateP; "Can't translate pathname '%s' to %s"
0x18010e071  mov     edx, 2Ah ; '*'
0x18010e076  mov     rcx, rsi
0x18010e079  call    archive_set_error
0x18010e07e  mov     r15d, 0FFFFFFECh
0x18010e084  mov     r12, [rbp+arg_10]
0x18010e088  cmp     r12, 64h ; 'd'
0x18010e08c  ja      short loc_18010E099
0x18010e08e  mov     r8, r12
0x18010e091  mov     rdx, r14
0x18010e094  jmp     loc_18010E125
0x18010e099  lea     rcx, [r12-65h]
0x18010e09e  mov     edx, 2Fh ; '/'; Val
0x18010e0a3  add     rcx, r14; Str
0x18010e0a6  call    cs:__imp_strchr
0x18010e0ac  mov     [rbp+var_10], rax
0x18010e0b0  mov     rbx, rax
0x18010e0b3  cmp     rax, r14
0x18010e0b6  jnz     short loc_18010E0CE
0x18010e0b8  lea     rcx, [rax+1]; Str
0x18010e0bc  mov     edx, 2Fh ; '/'; Val
0x18010e0c1  call    cs:__imp_strchr
0x18010e0c7  mov     rbx, rax
0x18010e0ca  mov     [rbp+var_10], rax
0x18010e0ce  test    rbx, rbx
0x18010e0d1  jz      short loc_18010E0E5
0x18010e0d3  cmp     byte ptr [rax+1], 0
0x18010e0d7  jz      short loc_18010E0E5
0x18010e0d9  lea     rax, [r14+9Bh]
0x18010e0e0  cmp     rbx, rax
0x18010e0e3  jbe     short loc_18010E101
0x18010e0e5  lea     r8, aPathnameTooLon; "Pathname too long"
0x18010e0ec  mov     edx, 26h ; '&'
0x18010e0f1  mov     rcx, rsi
0x18010e0f4  call    archive_set_error
0x18010e0f9  mov     r15d, 0FFFFFFE7h
0x18010e0ff  jmp     short loc_18010E12D
0x18010e101  mov     r8, rbx
0x18010e104  lea     rcx, [rdi+159h]; void *
0x18010e10b  sub     r8, r14; Size
0x18010e10e  mov     rdx, r14; Src
0x18010e111  call    memcpy_0
0x18010e116  lea     r8, [r12-1]
0x18010e11b  sub     r14, rbx
0x18010e11e  add     r8, r14; Size
0x18010e121  lea     rdx, [rbx+1]; Src
0x18010e125  mov     rcx, rdi; void *
0x18010e128  call    memcpy_0
0x18010e12d  mov     r14, [rbp+arg_28]
0x18010e131  lea     r8, [rbp+arg_10]
0x18010e135  mov     r9, r14
0x18010e138  lea     rdx, [rbp+var_10]
0x18010e13c  mov     rcx, r13
0x18010e13f  call    _archive_entry_hardlink_l
0x18010e144  mov     rbx, [rbp+var_10]
0x18010e148  test    eax, eax
0x18010e14a  jz      short loc_18010E181
0x18010e14c  call    cs:__imp__o__errno
0x18010e152  cmp     dword ptr [rax], 0Ch
0x18010e155  jz      short loc_18010E1BC
0x18010e157  mov     rcx, r14
0x18010e15a  call    archive_string_conversion_charset_name
0x18010e15f  mov     r9, rbx
0x18010e162  mov     [rsp+40h+var_20], rax
0x18010e167  lea     r8, aCanTTranslateL; "Can't translate linkname '%s' to %s"
0x18010e16e  mov     edx, 2Ah ; '*'
0x18010e173  mov     rcx, rsi
0x18010e176  call    archive_set_error
0x18010e17b  mov     r15d, 0FFFFFFECh
0x18010e181  mov     r8, [rbp+arg_10]
0x18010e185  test    r8, r8
0x18010e188  jz      short loc_18010E193
0x18010e18a  mov     dword ptr [rbp+Src], 31h ; '1'
0x18010e191  jmp     short loc_18010E200
0x18010e193  mov     r9, r14
0x18010e196  mov     dword ptr [rbp+Src], 0FFFFFFFFh
0x18010e19d  lea     r8, [rbp+arg_10]
0x18010e1a1  mov     rcx, r13
0x18010e1a4  lea     rdx, [rbp+var_10]
0x18010e1a8  call    _archive_entry_symlink_l
0x18010e1ad  test    eax, eax
0x18010e1af  jz      short loc_18010E1F8
0x18010e1b1  call    cs:__imp__o__errno
0x18010e1b7  cmp     dword ptr [rax], 0Ch
0x18010e1ba  jnz     short loc_18010E1C8
0x18010e1bc  lea     r8, aCanTAllocateMe_15; "Can't allocate memory for Linkname"
0x18010e1c3  jmp     loc_18010E043
0x18010e1c8  mov     rcx, r14
0x18010e1cb  call    archive_string_conversion_charset_name
0x18010e1d0  mov     rbx, [rbp+var_10]
0x18010e1d4  lea     r8, aCanTTranslateL; "Can't translate linkname '%s' to %s"
0x18010e1db  mov     r9, rbx
0x18010e1de  mov     [rsp+40h+var_20], rax
0x18010e1e3  mov     edx, 2Ah ; '*'
0x18010e1e8  mov     rcx, rsi
0x18010e1eb  call    archive_set_error
0x18010e1f0  mov     r15d, 0FFFFFFECh
0x18010e1f6  jmp     short loc_18010E1FC
0x18010e1f8  mov     rbx, [rbp+var_10]
0x18010e1fc  mov     r8, [rbp+arg_10]
0x18010e200  test    r8, r8
0x18010e203  jz      short loc_18010E23C
0x18010e205  cmp     r8, 64h ; 'd'
0x18010e209  jbe     short loc_18010E22D
0x18010e20b  lea     r8, aLinkContentsTo; "Link contents too long"
0x18010e212  mov     edx, 26h ; '&'
0x18010e217  mov     rcx, rsi
0x18010e21a  call    archive_set_error
0x18010e21f  mov     r15d, 0FFFFFFE7h
0x18010e225  lea     r8d, [r15+7Dh]; Size
0x18010e229  mov     [rbp+arg_10], r8
0x18010e22d  lea     rcx, [rdi+9Dh]; void *
0x18010e234  mov     rdx, rbx; Src
0x18010e237  call    memcpy_0
0x18010e23c  mov     rcx, [r13+0]
0x18010e240  lea     rdx, [r13+250h]
0x18010e247  lea     r9, [rbp+arg_10]
0x18010e24b  mov     [rsp+40h+var_20], r14
0x18010e250  lea     r8, [rbp+var_10]
0x18010e254  call    archive_mstring_get_mbs_l
0x18010e259  test    eax, eax
0x18010e25b  jz      short loc_18010E29F
0x18010e25d  call    cs:__imp__o__errno
0x18010e263  cmp     dword ptr [rax], 0Ch
0x18010e266  jnz     short loc_18010E274
0x18010e268  lea     r8, aCanTAllocateMe_22; "Can't allocate memory for Uname"
0x18010e26f  jmp     loc_18010E043
0x18010e274  mov     rcx, r14
0x18010e277  call    archive_string_conversion_charset_name
0x18010e27c  mov     r9, [rbp+var_10]
0x18010e280  lea     r8, aCanTTranslateU; "Can't translate uname '%s' to %s"
0x18010e287  mov     edx, 2Ah ; '*'
0x18010e28c  mov     [rsp+40h+var_20], rax
0x18010e291  mov     rcx, rsi
0x18010e294  call    archive_set_error
0x18010e299  mov     r15d, 0FFFFFFECh
0x18010e29f  mov     r8, [rbp+arg_10]
0x18010e2a3  mov     r12d, [rbp+arg_18]
0x18010e2a7  test    r8, r8
0x18010e2aa  jz      short loc_18010E2EA
0x18010e2ac  cmp     r8, 20h ; ' '
0x18010e2b0  jbe     short loc_18010E2DA
0x18010e2b2  cmp     r12d, 78h ; 'x'
0x18010e2b6  jz      short loc_18010E2D0
0x18010e2b8  lea     r8, aUsernameTooLon; "Username too long"
0x18010e2bf  or      edx, 0FFFFFFFFh
0x18010e2c2  mov     rcx, rsi
0x18010e2c5  call    archive_set_error
0x18010e2ca  mov     r15d, 0FFFFFFE7h
0x18010e2d0  mov     r8d, 20h ; ' '; Size
0x18010e2d6  mov     [rbp+arg_10], r8
0x18010e2da  mov     rdx, [rbp+var_10]; Src
0x18010e2de  lea     rcx, [rdi+109h]; void *
0x18010e2e5  call    memcpy_0
0x18010e2ea  mov     rcx, [r13+0]
0x18010e2ee  lea     rdx, [r13+118h]
0x18010e2f5  lea     r9, [rbp+arg_10]
0x18010e2f9  mov     [rsp+40h+var_20], r14
0x18010e2fe  lea     r8, [rbp+var_10]
0x18010e302  call    archive_mstring_get_mbs_l
0x18010e307  mov     rbx, [rbp+var_10]
0x18010e30b  test    eax, eax
0x18010e30d  jz      short loc_18010E350
0x18010e30f  call    cs:__imp__o__errno
0x18010e315  cmp     dword ptr [rax], 0Ch
0x18010e318  jnz     short loc_18010E326
0x18010e31a  lea     r8, aCanTAllocateMe_9; "Can't allocate memory for Gname"
0x18010e321  jmp     loc_18010E043
0x18010e326  mov     rcx, r14
0x18010e329  call    archive_string_conversion_charset_name
0x18010e32e  mov     r9, rbx
0x18010e331  mov     [rsp+40h+var_20], rax
0x18010e336  lea     r8, aCanTTranslateG; "Can't translate gname '%s' to %s"
0x18010e33d  mov     edx, 2Ah ; '*'
0x18010e342  mov     rcx, rsi
0x18010e345  call    archive_set_error
0x18010e34a  mov     r15d, 0FFFFFFECh
0x18010e350  mov     r8, [rbp+arg_10]
0x18010e354  test    r8, r8
0x18010e357  jz      short loc_18010E3A1
0x18010e359  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18010e35d  mov     rax, rcx
0x18010e360  inc     rax
0x18010e363  cmp     byte ptr [rbx+rax], 0
0x18010e367  jnz     short loc_18010E360
0x18010e369  cmp     rax, 20h ; ' '
0x18010e36d  jbe     short loc_18010E392
0x18010e36f  cmp     r12d, 78h ; 'x'
0x18010e373  jz      short loc_18010E38C
0x18010e375  mov     edx, ecx
0x18010e377  lea     r8, aGroupNameTooLo; "Group name too long"
0x18010e37e  mov     rcx, rsi
0x18010e381  call    archive_set_error
0x18010e386  mov     r15d, 0FFFFFFE7h
0x18010e38c  mov     r8d, 20h ; ' '; Size
0x18010e392  lea     rcx, [rdi+129h]; void *
0x18010e399  mov     rdx, rbx; Src
0x18010e39c  call    memcpy_0
0x18010e3a1  movzx   ecx, word ptr [r13+408h]
0x18010e3a9  lea     rdx, [rdi+64h]
0x18010e3ad  mov     r12d, [rbp+arg_20]
0x18010e3b1  mov     r9d, 8
0x18010e3b7  and     ecx, 0FFFh
0x18010e3bd  mov     dword ptr [rsp+40h+var_20], r12d
0x18010e3c2  lea     r8d, [r9-2]
0x18010e3c6  call    format_number_0
0x18010e3cb  mov     ebx, 22h ; '"'
0x18010e3d0  test    eax, eax
0x18010e3d2  jz      short loc_18010E3EE
0x18010e3d4  lea     r8, aNumericModeToo; "Numeric mode too large"
0x18010e3db  mov     edx, ebx
0x18010e3dd  mov     rcx, rsi
0x18010e3e0  call    archive_set_error
0x18010e3e5  lea     r14d, [rbx-3Bh]
0x18010e3e9  mov     r15d, r14d
0x18010e3ec  jmp     short loc_18010E3F4
0x18010e3ee  mov     r14d, 0FFFFFFE7h
0x18010e3f4  mov     rcx, [r13+78h]
0x18010e3f8  lea     rdx, [rdi+6Ch]
0x18010e3fc  mov     r9d, 8
0x18010e402  mov     dword ptr [rsp+40h+var_20], r12d
0x18010e407  lea     r8d, [r9-2]
0x18010e40b  call    format_number_0
0x18010e410  test    eax, eax
0x18010e412  jz      short loc_18010E428
0x18010e414  lea     r8, aNumericUserIdT; "Numeric user ID too large"
0x18010e41b  mov     edx, ebx
0x18010e41d  mov     rcx, rsi
0x18010e420  call    archive_set_error
0x18010e425  mov     r15d, r14d
0x18010e428  mov     rcx, [r13+58h]
0x18010e42c  lea     rdx, [rdi+74h]
0x18010e430  mov     r9d, 8
0x18010e436  mov     dword ptr [rsp+40h+var_20], r12d
  ... truncated ...
```
