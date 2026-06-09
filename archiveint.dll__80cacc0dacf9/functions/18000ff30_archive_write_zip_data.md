# archive_write_zip_data

- ea: `0x18000ff30`
- end: `0x180010744`
- name: `archive_write_zip_data`
- size: `2068`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006c00`
- `0x18000cfd4`
- `0x18000e8d4`
- `0x18000ff30`
- `0x180013e64`
- `0x180014fc0`
- `0x1800159e0`
- `0x180021bc0`
- `0x18003c3d0`
- `0x18003fd00`
- `0x1800b079c`
- `0x180116488`
- `0x1801165c4`
- `0x18011a010`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18001011a`
- `bcrypt!BCryptHashData` at `0x180010329`
- `bcrypt!BCryptHashData` at `0x1800103b9`
- `bcrypt!BCryptHashData` at `0x1800104c7`
- `bcrypt!BCryptHashData` at `0x1800105d4`
- `bcrypt!BCryptHashData` at `0x1800106ea`
- `bcrypt!BCryptHashData` at `0x18001011a`
- `bcrypt!BCryptHashData` at `0x180010329`
- `bcrypt!BCryptHashData` at `0x1800103b9`
- `bcrypt!BCryptHashData` at `0x1800104c7`
- `bcrypt!BCryptHashData` at `0x1800105d4`
- `bcrypt!BCryptHashData` at `0x1800106ea`

## string_xrefs

- `0x180010015`: `Invalid ZIP compression type`

## pseudocode

```c
__int64 __fastcall archive_write_zip_data(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v4; // rsi
  __int64 result; // rax
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  char v13; // cl
  int v14; // ecx
  unsigned __int64 i; // r14
  __int64 v16; // rax
  __int64 v17; // r9
  _BYTE *v18; // r8
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rax
  unsigned __int64 v27; // r14
  unsigned __int64 v28; // r15
  __int64 v29; // rax
  __int64 v30; // r9
  int v31; // r8d
  __int64 v32; // r8
  __int64 v33; // rax
  ULONG cbInput[2]; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v35[9]; // [rsp+38h] [rbp-18h] BYREF
  _BYTE v36[7]; // [rsp+41h] [rbp-Fh] BYREF

  v3 = *(_QWORD *)(a1 + 248);
  v4 = a3;
  if ( a3 > *(_QWORD *)(v3 + 40) )
    v4 = *(_QWORD *)(v3 + 40);
  *(_QWORD *)(v3 + 32) += v4;
  if ( !v4 )
    return 0;
  if ( (*(_BYTE *)(v3 + 68) & 1) != 0 )
  {
    if ( *(_DWORD *)(v3 + 64) == 1 )
    {
      if ( !*(_BYTE *)(v3 + 88) )
      {
        LODWORD(result) = init_traditional_pkware_encryption(a1);
        if ( (_DWORD)result )
          return (int)result;
        *(_BYTE *)(v3 + 88) = 1;
      }
    }
    else if ( (unsigned int)(*(_DWORD *)(v3 + 64) - 2) <= 1 && !*(_BYTE *)(v3 + 160) )
    {
      LODWORD(result) = init_winzip_aes_encryption(a1);
      if ( (_DWORD)result )
        return (int)result;
      *(_BYTE *)(v3 + 200) = 1;
      *(_BYTE *)(v3 + 160) = 1;
    }
  }
  v8 = *(_DWORD *)(v3 + 60);
  if ( v8 == -1 )
  {
LABEL_22:
    archive_set_error(a1, 0xFFFFFFFFLL, "Invalid ZIP compression type");
    return -30;
  }
  if ( v8 )
  {
    if ( v8 == 8 )
    {
      *(_DWORD *)(v3 + 320) = v4;
      *(_QWORD *)(v3 + 312) = a2;
      while ( (unsigned int)deflate(v3 + 312, 0) != -2 )
      {
        if ( !*(_DWORD *)(v3 + 336) )
        {
          if ( *(_BYTE *)(v3 + 88) )
          {
            trad_enc_encrypt_update(
              v3 + 76,
              *(_QWORD *)(v3 + 576),
              *(_QWORD *)(v3 + 568),
              *(_QWORD *)(v3 + 576),
              *(_QWORD *)(v3 + 568));
          }
          else if ( *(_BYTE *)(v3 + 160) )
          {
            v25 = *(_QWORD *)(v3 + 576);
            *(_QWORD *)cbInput = *(_QWORD *)(v3 + 568);
            if ( (int)aes_ctr_update((int)v3 + 96, v25, cbInput[0], v25, (__int64)cbInput) < 0 )
              goto LABEL_102;
            BCryptHashData(*(BCRYPT_HASH_HANDLE *)(v3 + 176), *(PUCHAR *)(v3 + 576), *(_DWORD *)(v3 + 568), 0);
          }
          LODWORD(result) = _archive_write_filter(*(_QWORD *)(a1 + 232), *(_QWORD *)(v3 + 576), *(_QWORD *)(v3 + 568));
          if ( (_DWORD)result )
            return (int)result;
          v26 = *(_QWORD *)(v3 + 568);
          *(_QWORD *)(v3 + 24) += v26;
          *(_QWORD *)(v3 + 264) += v26;
          *(_QWORD *)(v3 + 328) = *(_QWORD *)(v3 + 576);
          *(_DWORD *)(v3 + 336) = *(_DWORD *)(v3 + 568);
        }
        if ( !*(_DWORD *)(v3 + 320) )
          goto LABEL_35;
      }
      return -30;
    }
    if ( v8 == 12 )
    {
      *(_DWORD *)(v3 + 320) = v4;
      *(_QWORD *)(v3 + 312) = a2;
      while ( (unsigned int)BZ2_bzCompress(v3 + 312, 0) == 1 )
      {
        if ( !*(_DWORD *)(v3 + 344) )
        {
          if ( *(_BYTE *)(v3 + 88) )
          {
            trad_enc_encrypt_update(
              v3 + 76,
              *(_QWORD *)(v3 + 576),
              *(_QWORD *)(v3 + 568),
              *(_QWORD *)(v3 + 576),
              *(_QWORD *)(v3 + 568));
          }
          else if ( *(_BYTE *)(v3 + 160) )
          {
            v23 = *(_QWORD *)(v3 + 576);
            *(_QWORD *)cbInput = *(_QWORD *)(v3 + 568);
            if ( (int)aes_ctr_update((int)v3 + 96, v23, cbInput[0], v23, (__int64)cbInput) < 0 )
              goto LABEL_102;
            BCryptHashData(*(BCRYPT_HASH_HANDLE *)(v3 + 176), *(PUCHAR *)(v3 + 576), *(_DWORD *)(v3 + 568), 0);
          }
          LODWORD(result) = _archive_write_filter(*(_QWORD *)(a1 + 232), *(_QWORD *)(v3 + 576), *(_QWORD *)(v3 + 568));
          if ( (_DWORD)result )
            return (int)result;
          v24 = *(_QWORD *)(v3 + 568);
          *(_QWORD *)(v3 + 24) += v24;
          *(_QWORD *)(v3 + 264) += v24;
          *(_QWORD *)(v3 + 336) = *(_QWORD *)(v3 + 576);
          *(_DWORD *)(v3 + 344) = *(_DWORD *)(v3 + 568);
        }
        if ( !*(_DWORD *)(v3 + 320) )
          goto LABEL_35;
      }
      return -30;
    }
    if ( v8 != 14 )
    {
      if ( v8 == 93 )
      {
        *(_QWORD *)(v3 + 328) = v4;
        *(_QWORD *)(v3 + 320) = a2;
        *(_QWORD *)(v3 + 336) = 0;
        while ( 1 )
        {
          v9 = ZSTD_compressStream(*(_QWORD *)(v3 + 312), v3 + 344, v3 + 320);
          if ( (unsigned int)ZSTD_isError(v9) )
            return -30;
          if ( *(_QWORD *)(v3 + 360) == *(_QWORD *)(v3 + 352) )
          {
            if ( *(_BYTE *)(v3 + 88) )
            {
              trad_enc_encrypt_update(
                v3 + 76,
                *(_QWORD *)(v3 + 576),
                *(_QWORD *)(v3 + 568),
                *(_QWORD *)(v3 + 576),
                *(_QWORD *)(v3 + 568));
            }
            else if ( *(_BYTE *)(v3 + 160) )
            {
              v10 = *(_QWORD *)(v3 + 576);
              *(_QWORD *)cbInput = *(_QWORD *)(v3 + 568);
              if ( (int)aes_ctr_update((int)v3 + 96, v10, cbInput[0], v10, (__int64)cbInput) < 0 )
                goto LABEL_102;
              BCryptHashData(*(BCRYPT_HASH_HANDLE *)(v3 + 176), *(PUCHAR *)(v3 + 576), *(_DWORD *)(v3 + 568), 0);
            }
            LODWORD(result) = _archive_write_filter(*(_QWORD *)(a1 + 232), *(_QWORD *)(v3 + 576), *(_QWORD *)(v3 + 568));
            if ( (_DWORD)result )
              return (int)result;
            v11 = *(_QWORD *)(v3 + 568);
            *(_QWORD *)(v3 + 24) += v11;
            v12 = *(_QWORD *)(v3 + 576);
            *(_QWORD *)(v3 + 264) += v11;
            *(_QWORD *)(v3 + 344) = v12;
            *(_QWORD *)(v3 + 352) = v11;
            *(_QWORD *)(v3 + 360) = 0;
          }
          if ( *(_QWORD *)(v3 + 336) == *(_QWORD *)(v3 + 328) )
            goto LABEL_35;
        }
      }
      if ( v8 != 95 )
        goto LABEL_22;
LABEL_45:
      *(_QWORD *)(v3 + 432) = a2;
      *(_QWORD *)(v3 + 440) = (unsigned int)v4;
      while ( (unsigned int)lzma_code(v3 + 432, 0) != 5 )
      {
        if ( !*(_QWORD *)(v3 + 464) )
        {
          if ( *(_BYTE *)(v3 + 88) )
          {
            trad_enc_encrypt_update(
              v3 + 76,
              *(_QWORD *)(v3 + 576),
              *(_QWORD *)(v3 + 568),
              *(_QWORD *)(v3 + 576),
              *(_QWORD *)(v3 + 568));
          }
          else if ( *(_BYTE *)(v3 + 160) )
          {
            v21 = *(_QWORD *)(v3 + 576);
            *(_QWORD *)cbInput = *(_QWORD *)(v3 + 568);
            if ( (int)aes_ctr_update((int)v3 + 96, v21, cbInput[0], v21, (__int64)cbInput) < 0 )
              goto LABEL_102;
            BCryptHashData(*(BCRYPT_HASH_HANDLE *)(v3 + 176), *(PUCHAR *)(v3 + 576), *(_DWORD *)(v3 + 568), 0);
          }
          LODWORD(result) = _archive_write_filter(*(_QWORD *)(a1 + 232), *(_QWORD *)(v3 + 576), *(_QWORD *)(v3 + 568));
          if ( (_DWORD)result )
            return (int)result;
          v22 = *(_QWORD *)(v3 + 568);
          *(_QWORD *)(v3 + 24) += v22;
          *(_QWORD *)(v3 + 264) += v22;
          *(_QWORD *)(v3 + 456) = *(_QWORD *)(v3 + 576);
          *(_QWORD *)(v3 + 464) = *(unsigned int *)(v3 + 568);
        }
        if ( !*(_QWORD *)(v3 + 440) )
          goto LABEL_35;
      }
      return -30;
    }
    if ( !*(_BYTE *)(v3 + 312) )
      goto LABEL_45;
    v13 = *(_BYTE *)(v3 + 348);
    *(_QWORD *)v35 = 329733;
    v35[4] = *(_BYTE *)(v3 + 340) + 9 * (*(_BYTE *)(v3 + 344) + 5 * v13);
    v14 = *(_DWORD *)(v3 + 320);
    *(_DWORD *)&v35[5] = v14;
    if ( *(_BYTE *)(v3 + 88) || *(_BYTE *)(v3 + 160) )
    {
      for ( i = (unsigned __int64)v35; i < (unsigned __int64)v36; i += v20 )
      {
        v16 = *(_QWORD *)(v3 + 568);
        v17 = *(_QWORD *)(v3 + 576);
        v18 = &v36[-i];
        *(_QWORD *)cbInput = 0;
        if ( *(_BYTE *)(v3 + 88) )
        {
          v19 = (unsigned int)trad_enc_encrypt_update((int)v3 + 76, i, (_DWORD)v18, v17, v16);
          *(_QWORD *)cbInput = v19;
        }
        else
        {
          *(_QWORD *)cbInput = v16;
          if ( (int)aes_ctr_update((int)v3 + 96, i, (_DWORD)v18, v17, (__int64)cbInput) < 0 )
            goto LABEL_102;
          BCryptHashData(*(BCRYPT_HASH_HANDLE *)(v3 + 176), *(PUCHAR *)(v3 + 576), cbInput[0], 0);
          v19 = *(_QWORD *)cbInput;
        }
        LODWORD(result) = _archive_write_filter(*(_QWORD *)(a1 + 232), *(_QWORD *)(v3 + 576), v19);
        if ( (_DWORD)result )
          return (int)result;
        v20 = *(_QWORD *)cbInput;
        *(_QWORD *)(v3 + 24) += *(_QWORD *)cbInput;
        *(_QWORD *)(v3 + 264) += v20;
      }
      goto LABEL_44;
    }
    LODWORD(result) = _archive_write_filter(*(_QWORD *)(a1 + 232), v35, 9);
    if ( !(_DWORD)result )
    {
      *(_QWORD *)(v3 + 264) += 9LL;
      *(_QWORD *)(v3 + 24) += 9LL;
LABEL_44:
      *(_BYTE *)(v3 + 312) = 0;
      goto LABEL_45;
    }
    return (int)result;
  }
  if ( *(_BYTE *)(v3 + 88) || *(_BYTE *)(v3 + 160) )
  {
    v27 = a2;
    v28 = v4 + a2;
    while ( v27 < v28 )
    {
      v29 = *(_QWORD *)(v3 + 568);
      v30 = *(_QWORD *)(v3 + 576);
      v31 = v28 - v27;
      *(_QWORD *)cbInput = 0;
      if ( *(_BYTE *)(v3 + 88) )
      {
        v32 = (unsigned int)trad_enc_encrypt_update((int)v3 + 76, v27, v31, v30, v29);
        *(_QWORD *)cbInput = v32;
      }
      else
      {
        *(_QWORD *)cbInput = v29;
        if ( (int)aes_ctr_update((int)v3 + 96, v27, v31, v30, (__int64)cbInput) < 0 )
        {
LABEL_102:
          archive_set_error(a1, 0xFFFFFFFFLL, "Failed to encrypt file");
          return -25;
        }
        BCryptHashData(*(BCRYPT_HASH_HANDLE *)(v3 + 176), *(PUCHAR *)(v3 + 576), cbInput[0], 0);
        v32 = *(_QWORD *)cbInput;
      }
      LODWORD(result) = _archive_write_filter(*(_QWORD *)(a1 + 232), *(_QWORD *)(v3 + 576), v32);
      if ( (_DWORD)result )
        return (int)result;
      v33 = *(_QWORD *)cbInput;
      *(_QWORD *)(v3 + 24) += *(_QWORD *)cbInput;
      *(_QWORD *)(v3 + 264) += v33;
      v27 += v33;
    }
  }
  else
  {
    LODWORD(result) = _archive_write_filter(*(_QWORD *)(a1 + 232), a2, v4);
    if ( (_DWORD)result )
      return (int)result;
    *(_QWORD *)(v3 + 264) += v4;
    *(_QWORD *)(v3 + 24) += v4;
  }
LABEL_35:
  *(_QWORD *)(v3 + 40) -= v4;
  if ( !*(_BYTE *)(v3 + 160) || *(_DWORD *)(v3 + 92) != 2 )
    *(_DWORD *)(v3 + 56) = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD))(v3 + 224))(
                             *(unsigned int *)(v3 + 56),
                             a2,
                             (unsigned int)v4);
  return v4;
}

```

## disassembly

```asm
0x18000ff30  mov     [rsp-38h+arg_18], rbx
0x18000ff35  push    rbp
0x18000ff36  push    rsi
0x18000ff37  push    rdi
0x18000ff38  push    r12
0x18000ff3a  push    r13
0x18000ff3c  push    r14
0x18000ff3e  push    r15
0x18000ff40  mov     rbp, rsp
0x18000ff43  sub     rsp, 50h
0x18000ff47  mov     rax, cs:__security_cookie
0x18000ff4e  xor     rax, rsp
0x18000ff51  mov     [rbp+var_8], rax
0x18000ff55  mov     rbx, [rcx+0F8h]
0x18000ff5c  mov     rsi, r8
0x18000ff5f  mov     r12, rdx
0x18000ff62  mov     rdi, rcx
0x18000ff65  cmp     r8, [rbx+28h]
0x18000ff69  cmovg   rsi, [rbx+28h]
0x18000ff6e  xor     r13d, r13d
0x18000ff71  add     [rbx+20h], rsi
0x18000ff75  test    rsi, rsi
0x18000ff78  jnz     short loc_18000FF81
0x18000ff7a  xor     eax, eax
0x18000ff7c  jmp     loc_18001002E
0x18000ff81  test    byte ptr [rbx+44h], 1
0x18000ff85  jz      short loc_18000FFD8
0x18000ff87  mov     ecx, [rbx+40h]
0x18000ff8a  sub     ecx, 1
0x18000ff8d  jz      short loc_18000FFBE
0x18000ff8f  sub     ecx, 1
0x18000ff92  jz      short loc_18000FF99
0x18000ff94  cmp     ecx, 1
0x18000ff97  jnz     short loc_18000FFD8
0x18000ff99  cmp     [rbx+0A0h], r13b
0x18000ffa0  jnz     short loc_18000FFD8
0x18000ffa2  mov     rcx, rdi
0x18000ffa5  call    init_winzip_aes_encryption
0x18000ffaa  test    eax, eax
0x18000ffac  jnz     short loc_18000FFD0
0x18000ffae  mov     byte ptr [rbx+0C8h], 1
0x18000ffb5  mov     byte ptr [rbx+0A0h], 1
0x18000ffbc  jmp     short loc_18000FFD8
0x18000ffbe  cmp     [rbx+58h], r13b
0x18000ffc2  jnz     short loc_18000FFD8
0x18000ffc4  mov     rcx, rdi
0x18000ffc7  call    init_traditional_pkware_encryption
0x18000ffcc  test    eax, eax
0x18000ffce  jz      short loc_18000FFD4
0x18000ffd0  cdqe
0x18000ffd2  jmp     short loc_18001002E
0x18000ffd4  mov     byte ptr [rbx+58h], 1
0x18000ffd8  mov     eax, [rbx+3Ch]
0x18000ffdb  or      r15d, 0FFFFFFFFh
0x18000ffdf  cmp     eax, r15d
0x18000ffe2  jz      short loc_180010015
0x18000ffe4  test    eax, eax
0x18000ffe6  jz      loc_18001063A
0x18000ffec  cmp     eax, 8
0x18000ffef  jz      loc_18001052D
0x18000fff5  cmp     eax, 0Ch
0x18000fff8  jz      loc_180010420
0x18000fffe  cmp     eax, 0Eh
0x180010001  jz      loc_1800101B3
0x180010007  cmp     eax, 5Dh ; ']'
0x18001000a  jz      short loc_180010052
0x18001000c  cmp     eax, 5Fh ; '_'
0x18001000f  jz      loc_180010253
0x180010015  lea     r8, aInvalidZipComp; "Invalid ZIP compression type"
0x18001001c  mov     edx, r15d
0x18001001f  mov     rcx, rdi
0x180010022  call    archive_set_error
0x180010027  mov     rax, 0FFFFFFFFFFFFFFE2h
0x18001002e  mov     rcx, [rbp+var_8]
0x180010032  xor     rcx, rsp; StackCookie
0x180010035  call    __security_check_cookie
0x18001003a  mov     rbx, [rsp+50h+arg_18]
0x180010042  add     rsp, 50h
0x180010046  pop     r15
0x180010048  pop     r14
0x18001004a  pop     r13
0x18001004c  pop     r12
0x18001004e  pop     rdi
0x18001004f  pop     rsi
0x180010050  pop     rbp
0x180010051  retn
0x180010052  lea     r14, [rbx+140h]
0x180010059  mov     [rbx+148h], rsi
0x180010060  mov     [r14], r12
0x180010063  lea     r15, [rbx+158h]
0x18001006a  mov     [rbx+150h], r13
0x180010071  mov     rcx, [rbx+138h]
0x180010078  mov     r8, r14
0x18001007b  mov     rdx, r15
0x18001007e  call    ZSTD_compressStream
0x180010083  mov     rcx, rax
0x180010086  call    ZSTD_isError
0x18001008b  test    eax, eax
0x18001008d  jnz     short loc_180010027
0x18001008f  mov     rax, [rbx+160h]
0x180010096  cmp     [rbx+168h], rax
0x18001009d  jnz     loc_18001016C
0x1800100a3  cmp     [rbx+58h], r13b
0x1800100a7  jz      short loc_1800100CA
0x1800100a9  mov     rdx, [rbx+240h]
0x1800100b0  lea     rcx, [rbx+4Ch]
0x1800100b4  mov     r8, [rbx+238h]
0x1800100bb  mov     r9, rdx
0x1800100be  mov     [rsp+50h+var_30], r8
0x1800100c3  call    trad_enc_encrypt_update
0x1800100c8  jmp     short loc_180010120
0x1800100ca  cmp     [rbx+0A0h], r13b
0x1800100d1  jz      short loc_180010120
0x1800100d3  mov     rdx, [rbx+240h]
0x1800100da  lea     rax, [rbp+cbInput]
0x1800100de  mov     r8, [rbx+238h]
0x1800100e5  lea     rcx, [rbx+60h]
0x1800100e9  mov     r9, rdx
0x1800100ec  mov     qword ptr [rbp+cbInput], r8
0x1800100f0  mov     [rsp+50h+var_30], rax
0x1800100f5  call    aes_ctr_update
0x1800100fa  test    eax, eax
0x1800100fc  js      loc_180010726
0x180010102  mov     r8d, [rbx+238h]; cbInput
0x180010109  xor     r9d, r9d; dwFlags
0x18001010c  mov     rdx, [rbx+240h]; pbInput
0x180010113  mov     rcx, [rbx+0B0h]; hHash
0x18001011a  call    cs:__imp_BCryptHashData
0x180010120  mov     r8, [rbx+238h]
0x180010127  mov     rdx, [rbx+240h]
0x18001012e  mov     rcx, [rdi+0E8h]
0x180010135  call    __archive_write_filter
0x18001013a  test    eax, eax
0x18001013c  jnz     loc_18000FFD0
0x180010142  mov     rcx, [rbx+238h]
0x180010149  add     [rbx+18h], rcx
0x18001014d  mov     rax, [rbx+240h]
0x180010154  add     [rbx+108h], rcx
0x18001015b  mov     [r15], rax
0x18001015e  mov     [rbx+160h], rcx
0x180010165  mov     [rbx+168h], r13
0x18001016c  mov     rax, [rbx+148h]
0x180010173  cmp     [rbx+150h], rax
0x18001017a  jnz     loc_180010071
0x180010180  sub     [rbx+28h], rsi
0x180010184  cmp     [rbx+0A0h], r13b
0x18001018b  jz      short loc_180010193
0x18001018d  cmp     dword ptr [rbx+5Ch], 2
0x180010191  jz      short loc_1800101AB
0x180010193  mov     ecx, [rbx+38h]
0x180010196  mov     rdx, r12
0x180010199  mov     rax, [rbx+0E0h]
0x1800101a0  mov     r8d, esi
0x1800101a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101a8  mov     [rbx+38h], eax
0x1800101ab  mov     rax, rsi
0x1800101ae  jmp     loc_18001002E
0x1800101b3  cmp     [rbx+138h], r13b
0x1800101ba  jz      loc_180010253
0x1800101c0  mov     cl, [rbx+15Ch]
0x1800101c6  mov     al, cl
0x1800101c8  mov     [rbp+var_18], 50805h
0x1800101d0  shl     al, 2
0x1800101d3  add     cl, al
0x1800101d5  add     cl, [rbx+158h]
0x1800101db  mov     al, cl
0x1800101dd  shl     al, 3
0x1800101e0  add     cl, al
0x1800101e2  add     cl, [rbx+154h]
0x1800101e8  mov     byte ptr [rbp+var_18+4], cl
0x1800101eb  mov     ecx, [rbx+140h]
0x1800101f1  mov     eax, ecx
0x1800101f3  shr     eax, 8
0x1800101f6  mov     byte ptr [rbp+var_18+6], al
0x1800101f9  mov     eax, ecx
0x1800101fb  shr     eax, 10h
0x1800101fe  mov     byte ptr [rbp+var_18+5], cl
0x180010201  shr     ecx, 18h
0x180010204  mov     byte ptr [rbp+var_18+7], al
0x180010207  mov     [rbp+var_10], cl
0x18001020a  cmp     [rbx+58h], r13b
0x18001020e  jnz     loc_1800102B4
0x180010214  cmp     [rbx+0A0h], r13b
0x18001021b  jnz     loc_1800102B4
0x180010221  mov     rcx, [rdi+0E8h]
0x180010228  lea     rdx, [rbp+var_18]
0x18001022c  mov     r8d, 9
0x180010232  call    __archive_write_filter
0x180010237  test    eax, eax
0x180010239  jnz     loc_18000FFD0
0x18001023f  add     qword ptr [rbx+108h], 9
0x180010247  add     qword ptr [rbx+18h], 9
0x18001024c  mov     [rbx+138h], r13b
0x180010253  lea     r14, [rbx+1B0h]
0x18001025a  mov     eax, esi
0x18001025c  mov     [r14], r12
0x18001025f  mov     [rbx+1B8h], rax
0x180010266  xor     edx, edx
0x180010268  mov     rcx, r14
0x18001026b  call    lzma_code
0x180010270  cmp     eax, 5
0x180010273  jz      loc_180010027
0x180010279  cmp     [rbx+1D0h], r13
0x180010280  jnz     loc_18001040E
0x180010286  cmp     [rbx+58h], r13b
0x18001028a  jz      loc_18001036D
0x180010290  mov     rdx, [rbx+240h]
0x180010297  lea     rcx, [rbx+4Ch]
0x18001029b  mov     r8, [rbx+238h]
0x1800102a2  mov     r9, rdx
0x1800102a5  mov     [rsp+50h+var_30], r8
0x1800102aa  call    trad_enc_encrypt_update
0x1800102af  jmp     loc_1800103BF
0x1800102b4  lea     r14, [rbp+var_18]
0x1800102b8  lea     rax, [rbp+var_F]
0x1800102bc  cmp     r14, rax
0x1800102bf  jnb     short loc_18001024C
0x1800102c1  mov     rax, [rbx+238h]
0x1800102c8  lea     r8, [rbp+var_F]
0x1800102cc  mov     r9, [rbx+240h]
0x1800102d3  sub     r8, r14
0x1800102d6  mov     rdx, r14
0x1800102d9  mov     qword ptr [rbp+cbInput], r13
0x1800102dd  cmp     [rbx+58h], r13b
0x1800102e1  jz      short loc_1800102FA
0x1800102e3  lea     rcx, [rbx+4Ch]
0x1800102e7  mov     [rsp+50h+var_30], rax
0x1800102ec  call    trad_enc_encrypt_update
0x1800102f1  mov     r8d, eax
0x1800102f4  mov     qword ptr [rbp+cbInput], r8
0x1800102f8  jmp     short loc_180010333
0x1800102fa  mov     qword ptr [rbp+cbInput], rax
0x1800102fe  lea     rcx, [rbx+60h]
0x180010302  lea     rax, [rbp+cbInput]
0x180010306  mov     [rsp+50h+var_30], rax
0x18001030b  call    aes_ctr_update
0x180010310  test    eax, eax
0x180010312  js      short loc_180010365
0x180010314  mov     r8d, [rbp+cbInput]; cbInput
0x180010318  xor     r9d, r9d; dwFlags
0x18001031b  mov     rdx, [rbx+240h]; pbInput
0x180010322  mov     rcx, [rbx+0B0h]; hHash
0x180010329  call    cs:__imp_BCryptHashData
0x18001032f  mov     r8, qword ptr [rbp+cbInput]
0x180010333  mov     rdx, [rbx+240h]
0x18001033a  mov     rcx, [rdi+0E8h]
0x180010341  call    __archive_write_filter
0x180010346  test    eax, eax
0x180010348  jnz     loc_18000FFD0
0x18001034e  mov     rax, qword ptr [rbp+cbInput]
0x180010352  add     [rbx+18h], rax
0x180010356  add     [rbx+108h], rax
0x18001035d  add     r14, rax
0x180010360  jmp     loc_1800102B8
0x180010365  mov     edx, r15d
0x180010368  jmp     loc_180010729
0x18001036d  cmp     [rbx+0A0h], r13b
0x180010374  jz      short loc_1800103BF
0x180010376  mov     rdx, [rbx+240h]
0x18001037d  lea     rax, [rbp+cbInput]
0x180010381  mov     r8, [rbx+238h]
0x180010388  lea     rcx, [rbx+60h]
0x18001038c  mov     r9, rdx
0x18001038f  mov     qword ptr [rbp+cbInput], r8
0x180010393  mov     [rsp+50h+var_30], rax
0x180010398  call    aes_ctr_update
0x18001039d  test    eax, eax
0x18001039f  js      short loc_180010365
0x1800103a1  mov     r8d, [rbx+238h]; cbInput
0x1800103a8  xor     r9d, r9d; dwFlags
0x1800103ab  mov     rdx, [rbx+240h]; pbInput
0x1800103b2  mov     rcx, [rbx+0B0h]; hHash
0x1800103b9  call    cs:__imp_BCryptHashData
0x1800103bf  mov     r8, [rbx+238h]
0x1800103c6  mov     rdx, [rbx+240h]
0x1800103cd  mov     rcx, [rdi+0E8h]
0x1800103d4  call    __archive_write_filter
0x1800103d9  test    eax, eax
0x1800103db  jnz     loc_18000FFD0
0x1800103e1  mov     rax, [rbx+238h]
0x1800103e8  add     [rbx+18h], rax
0x1800103ec  add     [rbx+108h], rax
0x1800103f3  mov     rax, [rbx+240h]
0x1800103fa  mov     [rbx+1C8h], rax
0x180010401  mov     eax, [rbx+238h]
0x180010407  mov     [rbx+1D0h], rax
0x18001040e  cmp     [rbx+1B8h], r13
0x180010415  jnz     loc_180010266
0x18001041b  jmp     loc_180010180
0x180010420  lea     r14, [rbx+138h]
0x180010427  mov     [rbx+140h], esi
0x18001042d  mov     [r14], r12
0x180010430  xor     edx, edx
0x180010432  mov     rcx, r14
0x180010435  call    BZ2_bzCompress
0x18001043a  cmp     eax, 1
0x18001043d  jnz     loc_180010027
0x180010443  cmp     [rbx+158h], r13d
0x18001044a  jnz     loc_18001051B
0x180010450  cmp     [rbx+58h], r13b
  ... truncated ...
```
