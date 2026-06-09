# format_header_v7tar

- ea: `0x18010f038`
- end: `0x18010f440`
- name: `format_header_v7tar`
- size: `1032`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x18010ecd0`

## callees

- `0x180006c00`
- `0x1800aba54`
- `0x1800b0ac4`
- `0x1800b0b0c`
- `0x1800ed038`
- `0x1800ed464`
- `0x1800f8774`
- `0x18010eb70`
- `0x18010f038`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010f0ea`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010f189`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010f1e9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010f0ea`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010f189`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010f1e9`

## string_xrefs

- `0x18010f0f5`: `Can't allocate memory for Pathname`
- `0x18010f1f4`: `Can't allocate memory for Linkname`
- `0x18010f11f`: `Can't translate pathname '%s' to %s`
- `0x18010f1a4`: `Can't translate linkname '%s' to %s`
- `0x18010f20c`: `Can't translate linkname '%s' to %s`
- `0x18010f155`: `Pathname too long`
- `0x18010f242`: `Link contents too long`

## pseudocode

```c
__int64 __fastcall format_header_v7tar(__int64 a1, _BYTE *a2, __int64 a3, __int64 a4, __int64 a5)
{
  _OWORD *v6; // rax
  __int64 v9; // rdx
  unsigned int v10; // esi
  _OWORD *v11; // rcx
  __int128 v12; // xmm1
  __int64 v13; // r15
  __int64 result; // rax
  const char *v15; // rax
  int v16; // eax
  const char *v17; // r12
  const char *v18; // rax
  size_t v19; // r8
  int v20; // r13d
  const char *v21; // rax
  __int16 v22; // ax
  __m128i v23; // xmm1
  __int64 v24; // rax
  __m128i v25; // xmm0
  __m128i v26; // xmm0
  __m128i v27; // xmm0
  __m128i v28; // xmm1
  void *Src; // [rsp+30h] [rbp-10h] BYREF
  size_t Size; // [rsp+88h] [rbp+48h] BYREF
  void *v31; // [rsp+90h] [rbp+50h] BYREF

  v6 = a2;
  Size = 0;
  v31 = 0;
  Src = 0;
  v9 = 4;
  v10 = 0;
  v11 = &unk_1801429D0;
  do
  {
    *v6 = *v11;
    v6[1] = v11[1];
    v6[2] = v11[2];
    v6[3] = v11[3];
    v6[4] = v11[4];
    v6[5] = v11[5];
    v6[6] = v11[6];
    v12 = v11[7];
    v11 += 8;
    v6[7] = v12;
    v6 += 8;
    --v9;
  }
  while ( v9 );
  v13 = a5;
  if ( (unsigned int)archive_mstring_get_mbs_l(
                       *(_QWORD *)a3,
                       (int)a3 + 488,
                       (unsigned int)&Src,
                       (unsigned int)&Size,
                       a5) )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
      archive_set_error(a1, 12, "Can't allocate memory for Pathname");
      return 4294967266LL;
    }
    v15 = (const char *)archive_string_conversion_charset_name(v13);
    archive_set_error(a1, 42, "Can't translate pathname '%s' to %s", (const char *)Src, v15);
    v10 = -20;
  }
  if ( Size >= 0x64 )
  {
    archive_set_error(a1, 38, "Pathname too long");
    v10 = -25;
  }
  else
  {
    memcpy_0(a2, Src, Size);
  }
  v16 = archive_entry_hardlink_l(a3, &v31, &Size, v13);
  v17 = (const char *)v31;
  if ( v16 )
  {
    if ( *(_DWORD *)_o__errno() == 12 )
    {
LABEL_18:
      archive_set_error(a1, 12, "Can't allocate memory for Linkname");
      return 4294967266LL;
    }
    v18 = (const char *)archive_string_conversion_charset_name(v13);
    archive_set_error(a1, 42, "Can't translate linkname '%s' to %s", v17, v18);
    v10 = -20;
  }
  v19 = Size;
  if ( !Size )
  {
    v20 = -1;
    if ( (unsigned int)archive_entry_symlink_l(a3, &v31, &Size, v13) )
    {
      if ( *(_DWORD *)_o__errno() == 12 )
        goto LABEL_18;
      v21 = (const char *)archive_string_conversion_charset_name(v13);
      v17 = (const char *)v31;
      archive_set_error(a1, 42, "Can't translate linkname '%s' to %s", (const char *)v31, v21);
      v10 = -20;
    }
    else
    {
      v17 = (const char *)v31;
    }
    v19 = Size;
    goto LABEL_22;
  }
  v20 = 49;
LABEL_22:
  if ( v19 )
  {
    if ( v19 >= 0x64 )
    {
      archive_set_error(a1, 38, "Link contents too long");
      v10 = -25;
      v19 = 100;
    }
    memcpy_0(a2 + 157, v17, v19);
  }
  if ( (unsigned int)format_octal_2(*(_WORD *)(a3 + 1032) & 0xFFF, a2 + 100, 6) )
  {
    archive_set_error(a1, 34, "Numeric mode too large");
    v10 = -25;
  }
  if ( (unsigned int)format_octal_2(*(_QWORD *)(a3 + 120), a2 + 108, 6) )
  {
    archive_set_error(a1, 34, "Numeric user ID too large");
    v10 = -25;
  }
  if ( (unsigned int)format_octal_2(*(_QWORD *)(a3 + 88), a2 + 116, 6) )
  {
    archive_set_error(a1, 34, "Numeric group ID too large");
    v10 = -25;
  }
  if ( (unsigned int)format_octal_2(*(_QWORD *)(a3 + 112), a2 + 124, 11) )
  {
    archive_set_error(a1, 34, "File size out of range");
    v10 = -25;
  }
  if ( (unsigned int)format_octal_2(*(_QWORD *)(a3 + 56), a2 + 136, 11) )
  {
    archive_set_error(a1, 34, "File modification time too large");
    v10 = -25;
  }
  if ( v20 < 0 )
  {
    v22 = *(_WORD *)(a3 + 1032) & 0xF000;
    if ( v22 != 0x4000 && v22 != (__int16)0x8000 )
    {
      if ( v22 == -24576 )
      {
        a2[156] = 50;
      }
      else
      {
        _archive_write_entry_filetype_unsupported(a1, a3, "v7tar");
        v10 = -25;
      }
    }
  }
  else
  {
    a2[156] = v20;
  }
  v23 = 0;
  v24 = 0;
  do
  {
    v25 = _mm_cvtsi32_si128(*(_DWORD *)&a2[v24]);
    v24 += 4;
    v26 = _mm_unpacklo_epi8(v25, v25);
    v27 = _mm_add_epi32(
            (__m128i)_mm_and_ps((__m128)_mm_srai_epi32(_mm_unpacklo_epi16(v26, v26), 0x18u), (__m128)_xmm),
            v23);
    v23 = v27;
  }
  while ( v24 != 512 );
  v28 = _mm_add_epi32(v27, _mm_srli_si128(v27, 8));
  format_octal_2((unsigned int)_mm_cvtsi128_si32(_mm_add_epi32(v28, _mm_srli_si128(v28, 4))), a2 + 148, 6);
  result = v10;
  a2[154] = 0;
  return result;
}

```

## disassembly

```asm
0x18010f038  mov     [rsp-38h+arg_0], rbx
0x18010f03d  push    rbp
0x18010f03e  push    rsi
0x18010f03f  push    rdi
0x18010f040  push    r12
0x18010f042  push    r13
0x18010f044  push    r14
0x18010f046  push    r15
0x18010f048  mov     rbp, rsp
0x18010f04b  sub     rsp, 40h
0x18010f04f  xor     r13d, r13d
0x18010f052  mov     rdi, rdx
0x18010f055  mov     rax, rdx
0x18010f058  mov     [rbp+Size], r13
0x18010f05c  mov     r14, r8
0x18010f05f  mov     [rbp+arg_10], r13
0x18010f063  mov     rbx, rcx
0x18010f066  mov     [rbp+Src], r13
0x18010f06a  lea     edx, [r13+4]
0x18010f06e  mov     esi, r13d
0x18010f071  lea     r8d, [rdx+7Ch]
0x18010f075  lea     rcx, unk_1801429D0
0x18010f07c  movups  xmm0, xmmword ptr [rcx]
0x18010f07f  movups  xmmword ptr [rax], xmm0
0x18010f082  movups  xmm1, xmmword ptr [rcx+10h]
0x18010f086  movups  xmmword ptr [rax+10h], xmm1
0x18010f08a  movups  xmm0, xmmword ptr [rcx+20h]
0x18010f08e  movups  xmmword ptr [rax+20h], xmm0
0x18010f092  movups  xmm1, xmmword ptr [rcx+30h]
0x18010f096  movups  xmmword ptr [rax+30h], xmm1
0x18010f09a  movups  xmm0, xmmword ptr [rcx+40h]
0x18010f09e  movups  xmmword ptr [rax+40h], xmm0
0x18010f0a2  movups  xmm1, xmmword ptr [rcx+50h]
0x18010f0a6  movups  xmmword ptr [rax+50h], xmm1
0x18010f0aa  movups  xmm0, xmmword ptr [rcx+60h]
0x18010f0ae  movups  xmmword ptr [rax+60h], xmm0
0x18010f0b2  movups  xmm1, xmmword ptr [rcx+70h]
0x18010f0b6  add     rcx, r8
0x18010f0b9  movups  xmmword ptr [rax+70h], xmm1
0x18010f0bd  add     rax, r8
0x18010f0c0  sub     rdx, 1
0x18010f0c4  jnz     short loc_18010F07C
0x18010f0c6  mov     r15, [rbp+arg_20]
0x18010f0ca  lea     rdx, [r14+1E8h]
0x18010f0d1  mov     rcx, [r14]
0x18010f0d4  lea     r9, [rbp+Size]
0x18010f0d8  lea     r8, [rbp+Src]
0x18010f0dc  mov     [rsp+40h+var_20], r15
0x18010f0e1  call    archive_mstring_get_mbs_l
0x18010f0e6  test    eax, eax
0x18010f0e8  jz      short loc_18010F13D
0x18010f0ea  call    cs:__imp__o__errno
0x18010f0f0  cmp     dword ptr [rax], 0Ch
0x18010f0f3  jnz     short loc_18010F113
0x18010f0f5  lea     r8, aCanTAllocateMe_24; "Can't allocate memory for Pathname"
0x18010f0fc  mov     edx, 0Ch
0x18010f101  mov     rcx, rbx
0x18010f104  call    archive_set_error
0x18010f109  mov     eax, 0FFFFFFE2h
0x18010f10e  jmp     loc_18010F428
0x18010f113  mov     rcx, r15
0x18010f116  call    archive_string_conversion_charset_name
0x18010f11b  mov     r9, [rbp+Src]
0x18010f11f  lea     r8, aCanTTranslateP; "Can't translate pathname '%s' to %s"
0x18010f126  mov     edx, 2Ah ; '*'
0x18010f12b  mov     [rsp+40h+var_20], rax
0x18010f130  mov     rcx, rbx
0x18010f133  call    archive_set_error
0x18010f138  mov     esi, 0FFFFFFECh
0x18010f13d  mov     r8, [rbp+Size]; Size
0x18010f141  cmp     r8, 64h ; 'd'
0x18010f145  jnb     short loc_18010F155
0x18010f147  mov     rdx, [rbp+Src]; Src
0x18010f14b  mov     rcx, rdi; void *
0x18010f14e  call    memcpy_0
0x18010f153  jmp     short loc_18010F16E
0x18010f155  lea     r8, aPathnameTooLon; "Pathname too long"
0x18010f15c  mov     edx, 26h ; '&'
0x18010f161  mov     rcx, rbx
0x18010f164  call    archive_set_error
0x18010f169  mov     esi, 0FFFFFFE7h
0x18010f16e  mov     r9, r15
0x18010f171  lea     r8, [rbp+Size]
0x18010f175  lea     rdx, [rbp+arg_10]
0x18010f179  mov     rcx, r14
0x18010f17c  call    _archive_entry_hardlink_l
0x18010f181  mov     r12, [rbp+arg_10]
0x18010f185  test    eax, eax
0x18010f187  jz      short loc_18010F1BD
0x18010f189  call    cs:__imp__o__errno
0x18010f18f  cmp     dword ptr [rax], 0Ch
0x18010f192  jz      short loc_18010F1F4
0x18010f194  mov     rcx, r15
0x18010f197  call    archive_string_conversion_charset_name
0x18010f19c  mov     r9, r12
0x18010f19f  mov     [rsp+40h+var_20], rax
0x18010f1a4  lea     r8, aCanTTranslateL; "Can't translate linkname '%s' to %s"
0x18010f1ab  mov     edx, 2Ah ; '*'
0x18010f1b0  mov     rcx, rbx
0x18010f1b3  call    archive_set_error
0x18010f1b8  mov     esi, 0FFFFFFECh
0x18010f1bd  mov     r8, [rbp+Size]
0x18010f1c1  test    r8, r8
0x18010f1c4  jz      short loc_18010F1CE
0x18010f1c6  mov     r13d, 31h ; '1'
0x18010f1cc  jmp     short loc_18010F237
0x18010f1ce  mov     r9, r15
0x18010f1d1  lea     r8, [rbp+Size]
0x18010f1d5  lea     rdx, [rbp+arg_10]
0x18010f1d9  mov     rcx, r14
0x18010f1dc  or      r13d, 0FFFFFFFFh
0x18010f1e0  call    _archive_entry_symlink_l
0x18010f1e5  test    eax, eax
0x18010f1e7  jz      short loc_18010F22F
0x18010f1e9  call    cs:__imp__o__errno
0x18010f1ef  cmp     dword ptr [rax], 0Ch
0x18010f1f2  jnz     short loc_18010F200
0x18010f1f4  lea     r8, aCanTAllocateMe_15; "Can't allocate memory for Linkname"
0x18010f1fb  jmp     loc_18010F0FC
0x18010f200  mov     rcx, r15
0x18010f203  call    archive_string_conversion_charset_name
0x18010f208  mov     r12, [rbp+arg_10]
0x18010f20c  lea     r8, aCanTTranslateL; "Can't translate linkname '%s' to %s"
0x18010f213  mov     r9, r12
0x18010f216  mov     [rsp+40h+var_20], rax
0x18010f21b  mov     edx, 2Ah ; '*'
0x18010f220  mov     rcx, rbx
0x18010f223  call    archive_set_error
0x18010f228  mov     esi, 0FFFFFFECh
0x18010f22d  jmp     short loc_18010F233
0x18010f22f  mov     r12, [rbp+arg_10]
0x18010f233  mov     r8, [rbp+Size]
0x18010f237  test    r8, r8
0x18010f23a  jz      short loc_18010F26E
0x18010f23c  cmp     r8, 64h ; 'd'
0x18010f240  jb      short loc_18010F25F
0x18010f242  lea     r8, aLinkContentsTo; "Link contents too long"
0x18010f249  mov     edx, 26h ; '&'
0x18010f24e  mov     rcx, rbx
0x18010f251  call    archive_set_error
0x18010f256  mov     esi, 0FFFFFFE7h
0x18010f25b  lea     r8d, [rsi+7Dh]; Size
0x18010f25f  lea     rcx, [rdi+9Dh]; void *
0x18010f266  mov     rdx, r12; Src
0x18010f269  call    memcpy_0
0x18010f26e  movzx   ecx, word ptr [r14+408h]
0x18010f276  lea     rdx, [rdi+64h]
0x18010f27a  and     ecx, 0FFFh
0x18010f280  mov     r8d, 6
0x18010f286  call    format_octal_2
0x18010f28b  mov     r12d, 22h ; '"'
0x18010f291  test    eax, eax
0x18010f293  jz      short loc_18010F2B1
0x18010f295  lea     r8, aNumericModeToo; "Numeric mode too large"
0x18010f29c  mov     edx, r12d
0x18010f29f  mov     rcx, rbx
0x18010f2a2  call    archive_set_error
0x18010f2a7  lea     r15d, [r12-3Bh]
0x18010f2ac  mov     esi, r15d
0x18010f2af  jmp     short loc_18010F2B7
0x18010f2b1  mov     r15d, 0FFFFFFE7h
0x18010f2b7  mov     rcx, [r14+78h]
0x18010f2bb  lea     rdx, [rdi+6Ch]
0x18010f2bf  mov     r8d, 6
0x18010f2c5  call    format_octal_2
0x18010f2ca  test    eax, eax
0x18010f2cc  jz      short loc_18010F2E3
0x18010f2ce  lea     r8, aNumericUserIdT; "Numeric user ID too large"
0x18010f2d5  mov     edx, r12d
0x18010f2d8  mov     rcx, rbx
0x18010f2db  call    archive_set_error
0x18010f2e0  mov     esi, r15d
0x18010f2e3  mov     rcx, [r14+58h]
0x18010f2e7  lea     rdx, [rdi+74h]
0x18010f2eb  mov     r8d, 6
0x18010f2f1  call    format_octal_2
0x18010f2f6  test    eax, eax
0x18010f2f8  jz      short loc_18010F30F
0x18010f2fa  lea     r8, aNumericGroupId_0; "Numeric group ID too large"
0x18010f301  mov     edx, r12d
0x18010f304  mov     rcx, rbx
0x18010f307  call    archive_set_error
0x18010f30c  mov     esi, r15d
0x18010f30f  mov     rcx, [r14+70h]
0x18010f313  lea     rdx, [rdi+7Ch]
0x18010f317  mov     r8d, 0Bh
0x18010f31d  call    format_octal_2
0x18010f322  test    eax, eax
0x18010f324  jz      short loc_18010F33B
0x18010f326  lea     r8, aFileSizeOutOfR; "File size out of range"
0x18010f32d  mov     edx, r12d
0x18010f330  mov     rcx, rbx
0x18010f333  call    archive_set_error
0x18010f338  mov     esi, r15d
0x18010f33b  mov     rcx, [r14+38h]
0x18010f33f  lea     rdx, [rdi+88h]
0x18010f346  mov     r8d, 0Bh
0x18010f34c  call    format_octal_2
0x18010f351  test    eax, eax
0x18010f353  jz      short loc_18010F36A
0x18010f355  lea     r8, aFileModificati; "File modification time too large"
0x18010f35c  mov     edx, r12d
0x18010f35f  mov     rcx, rbx
0x18010f362  call    archive_set_error
0x18010f367  mov     esi, r15d
0x18010f36a  test    r13d, r13d
0x18010f36d  js      short loc_18010F378
0x18010f36f  mov     [rdi+9Ch], r13b
0x18010f376  jmp     short loc_18010F3C1
0x18010f378  mov     eax, 0F000h
0x18010f37d  mov     ecx, 4000h
0x18010f382  and     ax, [r14+408h]
0x18010f38a  cmp     ax, cx
0x18010f38d  jz      short loc_18010F3C1
0x18010f38f  mov     ecx, 8000h
0x18010f394  cmp     ax, cx
0x18010f397  jz      short loc_18010F3C1
0x18010f399  mov     ecx, 0A000h
0x18010f39e  cmp     ax, cx
0x18010f3a1  jz      short loc_18010F3BA
0x18010f3a3  lea     r8, aV7tar; "v7tar"
0x18010f3aa  mov     rdx, r14
0x18010f3ad  mov     rcx, rbx
0x18010f3b0  call    __archive_write_entry_filetype_unsupported
0x18010f3b5  mov     esi, r15d
0x18010f3b8  jmp     short loc_18010F3C1
0x18010f3ba  mov     byte ptr [rdi+9Ch], 32h ; '2'
0x18010f3c1  xorps   xmm1, xmm1
0x18010f3c4  xor     eax, eax
0x18010f3c6  movd    xmm0, dword ptr [rdi+rax]
0x18010f3cb  add     rax, 4
0x18010f3cf  punpcklbw xmm0, xmm0
0x18010f3d3  punpcklwd xmm0, xmm0
0x18010f3d7  psrad   xmm0, 18h
0x18010f3dc  andps   xmm0, cs:__xmm@000000ff000000ff000000ff000000ff
0x18010f3e3  paddd   xmm0, xmm1
0x18010f3e7  movdqa  xmm1, xmm0
0x18010f3eb  cmp     rax, 200h
0x18010f3f1  jnz     short loc_18010F3C6
0x18010f3f3  psrldq  xmm0, 8
0x18010f3f8  lea     rdx, [rdi+94h]
0x18010f3ff  paddd   xmm1, xmm0
0x18010f403  mov     r8d, 6
0x18010f409  movdqa  xmm0, xmm1
0x18010f40d  psrldq  xmm0, 4
0x18010f412  paddd   xmm1, xmm0
0x18010f416  movd    ecx, xmm1
0x18010f41a  call    format_octal_2
0x18010f41f  mov     eax, esi
0x18010f421  mov     byte ptr [rdi+9Ah], 0
0x18010f428  mov     rbx, [rsp+40h+arg_0]
0x18010f430  add     rsp, 40h
0x18010f434  pop     r15
0x18010f436  pop     r14
0x18010f438  pop     r13
0x18010f43a  pop     r12
0x18010f43c  pop     rdi
0x18010f43d  pop     rsi
0x18010f43e  pop     rbp
0x18010f43f  retn
```
