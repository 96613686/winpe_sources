# archive_write_zip_options

- ea: `0x180115c40`
- end: `0x18011610c`
- name: `archive_write_zip_options`
- size: `1228`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180006c00`
- `0x180014fc0`
- `0x180026460`
- `0x1800ba9f4`
- `0x1800ed47c`
- `0x180115c40`
- `0x180116778`
- `0x180119956`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180115daa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180115dce`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180115e65`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180115e89`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180115daa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180115dce`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180115e65`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180115e89`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x180115dc1`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x180115e7c`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x180115dc1`
- `api-ms-win-crt-private-l1-1-0!_o_strtoul` at `0x180115e7c`

## string_xrefs

- `0x180115d89`: `compression-level`
- `0x180115c6c`: `compression`
- `0x180115e44`: `threads`
- `0x180115d69`: `%s: compression option needs a compression name`

## pseudocode

```c
__int64 __fastcall archive_write_zip_options(__int64 a1, const char *a2, const char *a3)
{
  __int64 v3; // rbx
  unsigned int v7; // esi
  int v8; // edx
  const char *v9; // r8
  unsigned __int16 v11; // ax
  __int64 (__fastcall *v12)(); // rax
  __int64 v13; // rax
  unsigned int v14; // eax
  UCHAR pbBuffer[16]; // [rsp+30h] [rbp-48h] BYREF

  v3 = *(_QWORD *)(a1 + 248);
  v7 = -25;
  if ( !strcmp_0(a2, "compression") )
  {
    if ( a3 && *a3 )
    {
      if ( !strcmp_0(a3, "deflate") )
      {
        *(_DWORD *)(v3 + 288) = 8;
      }
      else if ( !strcmp_0(a3, "store") )
      {
        *(_DWORD *)(v3 + 288) = 0;
      }
      else if ( !strcmp_0(a3, "bzip2") )
      {
        *(_DWORD *)(v3 + 288) = 12;
      }
      else if ( !strcmp_0(a3, "lzma") )
      {
        *(_DWORD *)(v3 + 288) = 14;
      }
      else
      {
        v8 = *(unsigned __int8 *)a3 - 120;
        if ( *a3 == 120 )
        {
          v8 = *((unsigned __int8 *)a3 + 1) - 122;
          if ( a3[1] == 122 )
            v8 = *((unsigned __int8 *)a3 + 2);
        }
        if ( v8 )
        {
          if ( strcmp_0(a3, "zstd") )
            return v7;
          *(_DWORD *)(v3 + 288) = 93;
        }
        else
        {
          *(_DWORD *)(v3 + 288) = 95;
        }
      }
      return 0;
    }
    v9 = "%s: compression option needs a compression name";
LABEL_21:
    archive_set_error(a1, 0xFFFFFFFFLL, v9, *(_QWORD *)(a1 + 256));
    return v7;
  }
  if ( strcmp_0(a2, "compression-level") )
  {
    if ( !strcmp_0(a2, "threads") )
    {
      *(_QWORD *)pbBuffer = 0;
      if ( !a3 )
        return v7;
      *(_DWORD *)_o__errno() = 0;
      *(_WORD *)(v3 + 304) = _o_strtoul(a3, pbBuffer, 10);
      if ( *(_DWORD *)_o__errno() || **(_BYTE **)pbBuffer )
      {
        *(_WORD *)(v3 + 304) = 1;
        archive_set_error(a1, 0xFFFFFFFFLL, "Illegal value `%s'", a3);
        return v7;
      }
      if ( !*(_WORD *)(v3 + 304) )
        *(_WORD *)(v3 + 304) = lzma_cputhreads();
      return 0;
    }
    if ( !strcmp_0(a2, "encryption") )
    {
      if ( a3 )
      {
        if ( *a3 == 49 || !strcmp_0(a3, "traditional") || !strcmp_0(a3, "zipcrypt") || !strcmp_0(a3, "ZipCrypt") )
        {
          if ( !(unsigned int)archive_random(pbBuffer, 0xBu) )
          {
            *(_DWORD *)(v3 + 300) = 1;
            return 0;
          }
        }
        else if ( !strcmp_0(a3, "aes128") )
        {
          if ( (unsigned int)is_winzip_aes_encryption_supported(2) )
          {
            *(_DWORD *)(v3 + 300) = 2;
            return 0;
          }
        }
        else
        {
          if ( strcmp_0(a3, "aes256") )
          {
            archive_set_error(a1, 0xFFFFFFFFLL, "%s: unknown encryption '%s'", *(const char **)(a1 + 256), a3);
            return v7;
          }
          if ( (unsigned int)is_winzip_aes_encryption_supported(3) )
          {
            *(_DWORD *)(v3 + 300) = 3;
            return 0;
          }
        }
        archive_set_error(a1, 0xFFFFFFFFLL, "encryption not supported");
        return v7;
      }
      *(_DWORD *)(v3 + 300) = 0;
      return 0;
    }
    if ( !strcmp_0(a2, "experimental") )
    {
      if ( a3 && *a3 )
        *(_DWORD *)(v3 + 308) |= 4u;
      else
        *(_DWORD *)(v3 + 308) &= ~4u;
    }
    else
    {
      if ( !strcmp_0(a2, "fakecrc32") )
      {
        if ( !a3 || (v12 = archive_commoncrypto_version, !*a3) )
          v12 = real_crc32;
        *(_QWORD *)(v3 + 224) = v12;
        return 0;
      }
      if ( !strcmp_0(a2, "hdrcharset") )
      {
        if ( a3 && *a3 )
        {
          v13 = archive_string_conversion_to_charset(a1, a3, 0);
          *(_QWORD *)(v3 + 272) = v13;
          return v13 == 0 ? 0xFFFFFFE2 : 0;
        }
        v9 = "%s: hdrcharset option needs a character-set name";
        goto LABEL_21;
      }
      if ( strcmp_0(a2, "zip64") )
        return 4294967276LL;
      if ( a3 && *a3 )
      {
        *(_DWORD *)(v3 + 308) |= 2u;
        v14 = *(_DWORD *)(v3 + 308) & 0xFFFFFFFE;
      }
      else
      {
        *(_DWORD *)(v3 + 308) &= ~2u;
        v14 = *(_DWORD *)(v3 + 308) | 1;
      }
      *(_DWORD *)(v3 + 308) = v14;
    }
    return 0;
  }
  *(_QWORD *)pbBuffer = 0;
  if ( a3 )
  {
    *(_DWORD *)_o__errno() = 0;
    *(_WORD *)(v3 + 292) = _o_strtoul(a3, pbBuffer, 10);
    if ( !*(_DWORD *)_o__errno() && !**(_BYTE **)pbBuffer )
    {
      v11 = *(_WORD *)(v3 + 292);
      if ( v11 <= 9u )
      {
        if ( v11 )
        {
          if ( *(_DWORD *)(v3 + 288) == -1 )
            *(_DWORD *)(v3 + 288) = 8;
        }
        else
        {
          *(_DWORD *)(v3 + 288) = 0;
        }
        return 0;
      }
    }
    *(_WORD *)(v3 + 292) = 6;
  }
  return 4294967276LL;
}

```

## disassembly

```asm
0x180115c40  mov     [rsp+arg_8], rbx
0x180115c45  push    rbp
0x180115c46  push    rsi
0x180115c47  push    rdi
0x180115c48  push    r14
0x180115c4a  push    r15
0x180115c4c  sub     rsp, 50h
0x180115c50  mov     rax, cs:__security_cookie
0x180115c57  xor     rax, rsp
0x180115c5a  mov     [rsp+78h+var_38], rax
0x180115c5f  mov     rbx, [rcx+0F8h]
0x180115c66  mov     r14, rdx
0x180115c69  mov     rbp, rcx
0x180115c6c  lea     rdx, aCompression; "compression"
0x180115c73  mov     rcx, r14; Str1
0x180115c76  mov     rdi, r8
0x180115c79  mov     esi, 0FFFFFFE7h
0x180115c7e  call    strcmp_0
0x180115c83  xor     r15d, r15d
0x180115c86  test    eax, eax
0x180115c88  jnz     loc_180115D89
0x180115c8e  test    rdi, rdi
0x180115c91  jz      loc_180115D69
0x180115c97  cmp     [rdi], r15b
0x180115c9a  jz      loc_180115D69
0x180115ca0  lea     rdx, aDeflate; "deflate"
0x180115ca7  mov     rcx, rdi; Str1
0x180115caa  call    strcmp_0
0x180115caf  test    eax, eax
0x180115cb1  jnz     short loc_180115CC2
0x180115cb3  mov     dword ptr [rbx+120h], 8
0x180115cbd  jmp     loc_180115D45
0x180115cc2  lea     rdx, aStore; "store"
0x180115cc9  mov     rcx, rdi; Str1
0x180115ccc  call    strcmp_0
0x180115cd1  test    eax, eax
0x180115cd3  jnz     short loc_180115CDE
0x180115cd5  mov     [rbx+120h], r15d
0x180115cdc  jmp     short loc_180115D45
0x180115cde  lea     rdx, aBzip2_0; "bzip2"
0x180115ce5  mov     rcx, rdi; Str1
0x180115ce8  call    strcmp_0
0x180115ced  test    eax, eax
0x180115cef  jnz     short loc_180115CFD
0x180115cf1  mov     dword ptr [rbx+120h], 0Ch
0x180115cfb  jmp     short loc_180115D45
0x180115cfd  lea     rdx, aLzma; "lzma"
0x180115d04  mov     rcx, rdi; Str1
0x180115d07  call    strcmp_0
0x180115d0c  test    eax, eax
0x180115d0e  jnz     short loc_180115D1C
0x180115d10  mov     dword ptr [rbx+120h], 0Eh
0x180115d1a  jmp     short loc_180115D45
0x180115d1c  movzx   edx, byte ptr [rdi]
0x180115d1f  sub     edx, 78h ; 'x'
0x180115d22  jnz     short loc_180115D37
0x180115d24  movzx   edx, byte ptr [rdi+1]
0x180115d28  sub     edx, 7Ah ; 'z'
0x180115d2b  jnz     short loc_180115D37
0x180115d2d  movzx   edx, byte ptr [rdi+2]
0x180115d31  movzx   ecx, r15b
0x180115d35  sub     edx, ecx
0x180115d37  test    edx, edx
0x180115d39  jnz     short loc_180115D4A
0x180115d3b  mov     dword ptr [rbx+120h], 5Fh ; '_'
0x180115d45  mov     esi, r15d
0x180115d48  jmp     short loc_180115D82
0x180115d4a  lea     rdx, aZstd; "zstd"
0x180115d51  mov     rcx, rdi; Str1
0x180115d54  call    strcmp_0
0x180115d59  test    eax, eax
0x180115d5b  jnz     short loc_180115D82
0x180115d5d  mov     dword ptr [rbx+120h], 5Dh ; ']'
0x180115d67  jmp     short loc_180115D45
0x180115d69  lea     r8, aSCompressionOp; "%s: compression option needs a compress"...
0x180115d70  mov     r9, [rbp+100h]
0x180115d77  or      edx, 0FFFFFFFFh
0x180115d7a  mov     rcx, rbp
0x180115d7d  call    archive_set_error
0x180115d82  mov     eax, esi
0x180115d84  jmp     loc_180115E23
0x180115d89  lea     rdx, aCompressionLev_0; "compression-level"
0x180115d90  mov     rcx, r14; Str1
0x180115d93  call    strcmp_0
0x180115d98  test    eax, eax
0x180115d9a  jnz     loc_180115E44
0x180115da0  mov     qword ptr [rsp+78h+pbBuffer], r15
0x180115da5  test    rdi, rdi
0x180115da8  jz      short loc_180115E1E
0x180115daa  call    cs:__imp__o__errno
0x180115db0  mov     r8d, 0Ah
0x180115db6  lea     rdx, [rsp+78h+pbBuffer]
0x180115dbb  mov     rcx, rdi
0x180115dbe  mov     [rax], r15d
0x180115dc1  call    cs:__imp__o_strtoul
0x180115dc7  mov     [rbx+124h], ax
0x180115dce  call    cs:__imp__o__errno
0x180115dd4  cmp     [rax], r15d
0x180115dd7  jnz     short loc_180115E15
0x180115dd9  mov     rax, qword ptr [rsp+78h+pbBuffer]
0x180115dde  cmp     [rax], r15b
0x180115de1  jnz     short loc_180115E15
0x180115de3  movzx   eax, word ptr [rbx+124h]
0x180115dea  cmp     ax, 9
0x180115dee  ja      short loc_180115E15
0x180115df0  test    ax, ax
0x180115df3  jnz     short loc_180115E00
0x180115df5  mov     [rbx+120h], r15d
0x180115dfc  xor     eax, eax
0x180115dfe  jmp     short loc_180115E23
0x180115e00  cmp     dword ptr [rbx+120h], 0FFFFFFFFh
0x180115e07  jnz     short loc_180115DFC
0x180115e09  mov     dword ptr [rbx+120h], 8
0x180115e13  jmp     short loc_180115DFC
0x180115e15  mov     word ptr [rbx+124h], 6
0x180115e1e  mov     eax, 0FFFFFFECh
0x180115e23  mov     rcx, [rsp+78h+var_38]
0x180115e28  xor     rcx, rsp; StackCookie
0x180115e2b  call    __security_check_cookie
0x180115e30  mov     rbx, [rsp+78h+arg_8]
0x180115e38  add     rsp, 50h
0x180115e3c  pop     r15
0x180115e3e  pop     r14
0x180115e40  pop     rdi
0x180115e41  pop     rsi
0x180115e42  pop     rbp
0x180115e43  retn
0x180115e44  lea     rdx, aThreads; "threads"
0x180115e4b  mov     rcx, r14; Str1
0x180115e4e  call    strcmp_0
0x180115e53  test    eax, eax
0x180115e55  jnz     short loc_180115ED5
0x180115e57  mov     qword ptr [rsp+78h+pbBuffer], r15
0x180115e5c  test    rdi, rdi
0x180115e5f  jz      loc_180115D82
0x180115e65  call    cs:__imp__o__errno
0x180115e6b  mov     r8d, 0Ah
0x180115e71  lea     rdx, [rsp+78h+pbBuffer]
0x180115e76  mov     rcx, rdi
0x180115e79  mov     [rax], r15d
0x180115e7c  call    cs:__imp__o_strtoul
0x180115e82  mov     [rbx+130h], ax
0x180115e89  call    cs:__imp__o__errno
0x180115e8f  cmp     [rax], r15d
0x180115e92  jnz     short loc_180115EBD
0x180115e94  mov     rax, qword ptr [rsp+78h+pbBuffer]
0x180115e99  cmp     [rax], r15b
0x180115e9c  jnz     short loc_180115EBD
0x180115e9e  cmp     [rbx+130h], r15w
0x180115ea6  jnz     loc_180115DFC
0x180115eac  call    lzma_cputhreads
0x180115eb1  mov     [rbx+130h], ax
0x180115eb8  jmp     loc_180115DFC
0x180115ebd  mov     word ptr [rbx+130h], 1
0x180115ec6  lea     r8, aIllegalValueS; "Illegal value `%s'"
0x180115ecd  mov     r9, rdi
0x180115ed0  jmp     loc_180115D77
0x180115ed5  lea     rdx, aEncryption; "encryption"
0x180115edc  mov     rcx, r14; Str1
0x180115edf  call    strcmp_0
0x180115ee4  test    eax, eax
0x180115ee6  jnz     loc_180116005
0x180115eec  test    rdi, rdi
0x180115eef  jnz     short loc_180115EFD
0x180115ef1  mov     [rbx+12Ch], r15d
0x180115ef8  jmp     loc_180115D45
0x180115efd  cmp     byte ptr [rdi], 31h ; '1'
0x180115f00  jz      loc_180115FCC
0x180115f06  lea     rdx, aTraditional; "traditional"
0x180115f0d  mov     rcx, rdi; Str1
0x180115f10  call    strcmp_0
0x180115f15  test    eax, eax
0x180115f17  jz      loc_180115FCC
0x180115f1d  lea     rdx, aZipcrypt; "zipcrypt"
0x180115f24  mov     rcx, rdi; Str1
0x180115f27  call    strcmp_0
0x180115f2c  test    eax, eax
0x180115f2e  jz      loc_180115FCC
0x180115f34  lea     rdx, aZipcrypt_0; "ZipCrypt"
0x180115f3b  mov     rcx, rdi; Str1
0x180115f3e  call    strcmp_0
0x180115f43  test    eax, eax
0x180115f45  jz      loc_180115FCC
0x180115f4b  lea     rdx, aAes128; "aes128"
0x180115f52  mov     rcx, rdi; Str1
0x180115f55  call    strcmp_0
0x180115f5a  test    eax, eax
0x180115f5c  jnz     short loc_180115F7D
0x180115f5e  lea     ecx, [rax+2]
0x180115f61  call    is_winzip_aes_encryption_supported
0x180115f66  test    eax, eax
0x180115f68  jz      loc_180115FEE
0x180115f6e  mov     dword ptr [rbx+12Ch], 2
0x180115f78  jmp     loc_180115D45
0x180115f7d  lea     rdx, aAes256; "aes256"
0x180115f84  mov     rcx, rdi; Str1
0x180115f87  call    strcmp_0
0x180115f8c  test    eax, eax
0x180115f8e  jnz     short loc_180115FA9
0x180115f90  lea     edi, [rax+3]
0x180115f93  mov     ecx, edi
0x180115f95  call    is_winzip_aes_encryption_supported
0x180115f9a  test    eax, eax
0x180115f9c  jz      short loc_180115FEE
0x180115f9e  mov     [rbx+12Ch], edi
0x180115fa4  jmp     loc_180115D45
0x180115fa9  mov     r9, [rbp+100h]
0x180115fb0  lea     r8, aSUnknownEncryp; "%s: unknown encryption '%s'"
0x180115fb7  or      edx, 0FFFFFFFFh
0x180115fba  mov     [rsp+78h+var_58], rdi
0x180115fbf  mov     rcx, rbp
0x180115fc2  call    archive_set_error
0x180115fc7  jmp     loc_180115D82
0x180115fcc  mov     edx, 0Bh; cbBuffer
0x180115fd1  lea     rcx, [rsp+78h+pbBuffer]; pbBuffer
0x180115fd6  call    archive_random
0x180115fdb  test    eax, eax
0x180115fdd  jnz     short loc_180115FEE
0x180115fdf  mov     dword ptr [rbx+12Ch], 1
0x180115fe9  jmp     loc_180115D45
0x180115fee  lea     r8, aEncryptionNotS; "encryption not supported"
0x180115ff5  or      edx, 0FFFFFFFFh
0x180115ff8  mov     rcx, rbp
0x180115ffb  call    archive_set_error
0x180116000  jmp     loc_180115D82
0x180116005  lea     rdx, aExperimental; "experimental"
0x18011600c  mov     rcx, r14; Str1
0x18011600f  call    strcmp_0
0x180116014  test    eax, eax
0x180116016  jnz     short loc_18011603A
0x180116018  test    rdi, rdi
0x18011601b  jz      short loc_18011602E
0x18011601d  cmp     [rdi], r15b
0x180116020  jz      short loc_18011602E
0x180116022  or      dword ptr [rbx+134h], 4
0x180116029  jmp     loc_180115DFC
0x18011602e  and     dword ptr [rbx+134h], 0FFFFFFFBh
0x180116035  jmp     loc_180115DFC
0x18011603a  lea     rdx, aFakecrc32; "fakecrc32"
0x180116041  mov     rcx, r14; Str1
0x180116044  call    strcmp_0
0x180116049  test    eax, eax
0x18011604b  jnz     short loc_180116071
0x18011604d  test    rdi, rdi
0x180116050  jz      short loc_18011605E
0x180116052  lea     rax, archive_commoncrypto_version
0x180116059  cmp     [rdi], r15b
0x18011605c  jnz     short loc_180116065
0x18011605e  lea     rax, real_crc32
0x180116065  mov     [rbx+0E0h], rax
0x18011606c  jmp     loc_180115DFC
0x180116071  lea     rdx, aHdrcharset; "hdrcharset"
0x180116078  mov     rcx, r14; Str1
0x18011607b  call    strcmp_0
0x180116080  test    eax, eax
0x180116082  jnz     short loc_1801160BE
0x180116084  test    rdi, rdi
0x180116087  jz      short loc_1801160B2
0x180116089  cmp     [rdi], r15b
0x18011608c  jz      short loc_1801160B2
0x18011608e  xor     r8d, r8d
0x180116091  mov     rdx, rdi
0x180116094  mov     rcx, rbp
0x180116097  call    archive_string_conversion_to_charset
0x18011609c  mov     [rbx+110h], rax
0x1801160a3  neg     rax
0x1801160a6  sbb     esi, esi
0x1801160a8  not     esi
0x1801160aa  and     esi, 0FFFFFFE2h
0x1801160ad  jmp     loc_180115D82
0x1801160b2  lea     r8, aSHdrcharsetOpt; "%s: hdrcharset option needs a character"...
0x1801160b9  jmp     loc_180115D70
0x1801160be  lea     rdx, aZip64; "zip64"
0x1801160c5  mov     rcx, r14; Str1
0x1801160c8  call    strcmp_0
0x1801160cd  test    eax, eax
0x1801160cf  jnz     loc_180115E1E
0x1801160d5  test    rdi, rdi
0x1801160d8  jz      short loc_1801160F1
0x1801160da  cmp     [rdi], r15b
0x1801160dd  jz      short loc_1801160F1
0x1801160df  or      dword ptr [rbx+134h], 2
0x1801160e6  mov     eax, [rbx+134h]
0x1801160ec  and     eax, 0FFFFFFFEh
0x1801160ef  jmp     short loc_180116101
0x1801160f1  and     dword ptr [rbx+134h], 0FFFFFFFDh
0x1801160f8  mov     eax, [rbx+134h]
0x1801160fe  or      eax, 1
0x180116101  mov     [rbx+134h], eax
0x180116107  jmp     loc_180115DFC
```
