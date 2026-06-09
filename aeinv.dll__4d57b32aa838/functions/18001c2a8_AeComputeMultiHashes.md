# AeComputeMultiHashes

- ea: `0x18001c2a8`
- end: `0x18001c9ce`
- name: `AeComputeMultiHashes`
- size: `1830`
- prototype: `__int64 __fastcall(BYTE *pbData, unsigned __int64, wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001c1e0`

## callees

- `0x18001c2a8`
- `0x18001c9d4`
- `0x180059920`
- `0x18005a898`
- `0x1801167f0`
- `0x180116e60`
- `0x180116eac`

## import_xrefs

- `ADVAPI32!CryptAcquireContextW` at `0x18001c345`
- `ADVAPI32!CryptAcquireContextW` at `0x18001c874`
- `ADVAPI32!CryptAcquireContextW` at `0x18001c345`
- `ADVAPI32!CryptAcquireContextW` at `0x18001c874`
- `ADVAPI32!CryptCreateHash` at `0x18001c370`
- `ADVAPI32!CryptCreateHash` at `0x18001c89a`
- `ADVAPI32!CryptCreateHash` at `0x18001c370`
- `ADVAPI32!CryptCreateHash` at `0x18001c89a`
- `ADVAPI32!CryptHashData` at `0x18001c545`
- `ADVAPI32!CryptHashData` at `0x18001c8cd`
- `ADVAPI32!CryptHashData` at `0x18001c545`
- `ADVAPI32!CryptHashData` at `0x18001c8cd`
- `ADVAPI32!CryptDestroyHash` at `0x18001c99f`
- `ADVAPI32!CryptDestroyHash` at `0x18001c9ae`
- `ADVAPI32!CryptDestroyHash` at `0x18001c99f`
- `ADVAPI32!CryptDestroyHash` at `0x18001c9ae`
- `ADVAPI32!CryptGetHashParam` at `0x18001c3d1`
- `ADVAPI32!CryptGetHashParam` at `0x18001c3fc`
- `ADVAPI32!CryptGetHashParam` at `0x18001c44a`
- `ADVAPI32!CryptGetHashParam` at `0x18001c94e`
- `ADVAPI32!CryptGetHashParam` at `0x18001c3d1`
- `ADVAPI32!CryptGetHashParam` at `0x18001c3fc`
- `ADVAPI32!CryptGetHashParam` at `0x18001c44a`
- `ADVAPI32!CryptGetHashParam` at `0x18001c94e`
- `ADVAPI32!CryptReleaseContext` at `0x18001c4c7`
- `ADVAPI32!CryptReleaseContext` at `0x18001c9bf`
- `ADVAPI32!CryptReleaseContext` at `0x18001c4c7`
- `ADVAPI32!CryptReleaseContext` at `0x18001c9bf`
- `KERNEL32!GetLastError` at `0x18001c57d`
- `KERNEL32!GetLastError` at `0x18001c5bd`
- `KERNEL32!GetLastError` at `0x18001c5fd`
- `KERNEL32!GetLastError` at `0x18001c63d`
- `KERNEL32!GetLastError` at `0x18001c67d`
- `KERNEL32!GetLastError` at `0x18001c6c0`
- `KERNEL32!GetLastError` at `0x18001c703`
- `KERNEL32!GetLastError` at `0x18001c743`
- `KERNEL32!GetLastError` at `0x18001c783`
- `KERNEL32!GetLastError` at `0x18001c7c3`
- `KERNEL32!GetLastError` at `0x18001c57d`
- `KERNEL32!GetLastError` at `0x18001c5bd`
- `KERNEL32!GetLastError` at `0x18001c5fd`
- `KERNEL32!GetLastError` at `0x18001c63d`
- `KERNEL32!GetLastError` at `0x18001c67d`
- `KERNEL32!GetLastError` at `0x18001c6c0`
- `KERNEL32!GetLastError` at `0x18001c703`
- `KERNEL32!GetLastError` at `0x18001c743`
- `KERNEL32!GetLastError` at `0x18001c783`
- `KERNEL32!GetLastError` at `0x18001c7c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall AeComputeMultiHashes(BYTE *pbData, unsigned __int64 a2, wchar_t *a3, wchar_t *a4)
{
  unsigned __int64 v6; // rsi
  const BYTE *v8; // rbx
  BYTE *v9; // r12
  __int64 v10; // rdx
  __int64 v11; // rcx
  signed int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  DWORD v16; // esi
  DWORD v17; // r8d
  signed int LastError; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  signed int v28; // eax
  signed int v29; // eax
  DWORD pdwDataLen; // [rsp+30h] [rbp-41h] BYREF
  HCRYPTHASH phHash; // [rsp+38h] [rbp-39h] BYREF
  HCRYPTHASH hHash; // [rsp+40h] [rbp-31h] BYREF
  HCRYPTPROV hProv; // [rsp+48h] [rbp-29h] BYREF
  HCRYPTPROV phProv; // [rsp+50h] [rbp-21h] BYREF
  BYTE pbDataa[16]; // [rsp+58h] [rbp-19h] BYREF
  __int128 v36; // [rsp+68h] [rbp-9h]

  pdwDataLen = 0;
  phProv = 0;
  hProv = 0;
  phHash = 0;
  v6 = a2;
  hHash = 0;
  *(_OWORD *)pbDataa = 0;
  v36 = 0;
  if ( dwDataLen )
  {
    if ( dwDataLen > 0x40000000 )
      dwDataLen = 0x40000000;
  }
  else
  {
    dwDataLen = 0x2000000;
  }
  if ( !a3 && !a4 )
    return 1;
  if ( !a2 )
  {
    v12 = -2147467259;
    if ( a3 )
      wcscpy_s(a3, 0x2Du, L"0000da39a3ee5e6b4b0d3255bfef95601890afd80709");
    if ( a4 )
      wcscpy_s(a4, 0x41u, L"e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855");
    goto LABEL_25;
  }
  if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v20 = 23;
      goto LABEL_101;
    }
    goto LABEL_25;
  }
  if ( a3 && !CryptCreateHash(phProv, 0x8004u, 0, 0, &phHash) )
  {
    v21 = GetLastError();
    v12 = v21;
    if ( v21 > 0 )
      v12 = (unsigned __int16)v21 | 0x80070000;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v20 = 24;
      goto LABEL_101;
    }
    goto LABEL_25;
  }
  if ( a4 )
  {
    if ( !CryptAcquireContextW(&hProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000000) )
    {
      v22 = GetLastError();
      v12 = v22;
      if ( v22 > 0 )
        v12 = (unsigned __int16)v22 | 0x80070000;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v20 = 26;
        goto LABEL_101;
      }
      goto LABEL_25;
    }
    if ( !CryptCreateHash(hProv, 0x800Cu, 0, 0, &hHash) )
    {
      v23 = GetLastError();
      v12 = v23;
      if ( v23 > 0 )
        v12 = (unsigned __int16)v23 | 0x80070000;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v20 = 27;
        goto LABEL_101;
      }
      goto LABEL_25;
    }
  }
  else if ( v6 > 0x1E00000 )
  {
    v6 = 31457280;
  }
  v8 = pbData;
  v9 = &pbData[v6];
  while ( 1 )
  {
    if ( v8 >= v9 )
    {
      if ( a3 )
      {
        pdwDataLen = 0;
        *(_OWORD *)pbDataa = 0;
        v36 = 0;
        if ( !CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
        {
          v26 = GetLastError();
          v12 = v26;
          if ( v26 > 0 )
            v12 = (unsigned __int16)v26 | 0x80070000;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_25;
          v20 = 31;
          goto LABEL_101;
        }
        if ( pdwDataLen != 20 )
        {
          v12 = -2147418113;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_25;
          v14 = 32;
LABEL_24:
          WPP_SF_(v13[2], v14, WPP_60421427dd2a396270afbef62f846c6d_Traceguids);
          goto LABEL_25;
        }
        if ( !CryptGetHashParam(phHash, 2u, pbDataa, &pdwDataLen, 0) )
        {
          v27 = GetLastError();
          v12 = v27;
          if ( v27 > 0 )
            v12 = (unsigned __int16)v27 | 0x80070000;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_25;
          v20 = 33;
          goto LABEL_101;
        }
        v12 = FormatAeHashBuffer(v11, v10, pbDataa, a3);
        if ( v12 < 0 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_25;
          v20 = 34;
          goto LABEL_101;
        }
      }
      if ( !a4 )
        goto LABEL_119;
      pdwDataLen = 0;
      *(_OWORD *)pbDataa = 0;
      v36 = 0;
      if ( CryptGetHashParam(hHash, 2u, 0, &pdwDataLen, 0) )
      {
        if ( pdwDataLen != 32 )
        {
          v12 = -2147418113;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_25;
          v14 = 40;
          goto LABEL_24;
        }
        if ( CryptGetHashParam(hHash, 2u, pbDataa, &pdwDataLen, 0) )
        {
          v12 = FormatHashBuffer(pbDataa, pdwDataLen, a4);
          if ( v12 < 0 )
          {
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_25;
            v20 = 42;
            goto LABEL_101;
          }
LABEL_119:
          v12 = 0;
          goto LABEL_25;
        }
        v29 = GetLastError();
        v12 = v29;
        if ( v29 > 0 )
          v12 = (unsigned __int16)v29 | 0x80070000;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_25;
        v20 = 41;
      }
      else
      {
        v28 = GetLastError();
        v12 = v28;
        if ( v28 > 0 )
          v12 = (unsigned __int16)v28 | 0x80070000;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_25;
        v20 = 39;
      }
LABEL_101:
      WPP_SF_D(v19[2], v20, WPP_60421427dd2a396270afbef62f846c6d_Traceguids, (unsigned int)v12);
      goto LABEL_25;
    }
    v16 = (_DWORD)v9 - (_DWORD)v8;
    if ( (int)v9 - (int)v8 > dwDataLen )
      v16 = dwDataLen;
    if ( a3 && v8 < pbData + 31457280 )
    {
      v17 = &v8[v16] > pbData + 31457280 ? (_DWORD)pbData - (_DWORD)v8 + 31457280 : v16;
      if ( !CryptHashData(phHash, v8, v17, 0) )
        break;
    }
    if ( a4 && !CryptHashData(hHash, v8, v16, 0) )
    {
      v25 = GetLastError();
      v12 = v25;
      if ( v25 > 0 )
        v12 = (unsigned __int16)v25 | 0x80070000;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_25;
      v20 = 30;
      goto LABEL_101;
    }
    v8 += v16;
  }
  v24 = GetLastError();
  v12 = v24;
  if ( v24 > 0 )
    v12 = (unsigned __int16)v24 | 0x80070000;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v20 = 28;
    goto LABEL_101;
  }
LABEL_25:
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( hHash )
  {
    CryptDestroyHash(hHash);
    hHash = 0;
  }
  if ( hProv )
  {
    CryptReleaseContext(hProv, 0);
    hProv = 0;
  }
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001c2a8  push    rbp
0x18001c2aa  push    rbx
0x18001c2ab  push    rsi
0x18001c2ac  push    rdi
0x18001c2ad  push    r12
0x18001c2af  push    r13
0x18001c2b1  push    r14
0x18001c2b3  push    r15
0x18001c2b5  lea     rbp, [rsp-17h]
0x18001c2ba  sub     rsp, 88h
0x18001c2c1  mov     rax, cs:__security_cookie
0x18001c2c8  xor     rax, rsp
0x18001c2cb  mov     [rbp+4Fh+var_48], rax
0x18001c2cf  mov     eax, cs:dwDataLen
0x18001c2d5  xor     r12d, r12d
0x18001c2d8  mov     [rbp+4Fh+pdwDataLen], r12d
0x18001c2dc  xorps   xmm0, xmm0
0x18001c2df  mov     [rbp+4Fh+phProv], r12
0x18001c2e3  mov     r14, r9
0x18001c2e6  mov     [rbp+4Fh+hProv], r12
0x18001c2ea  mov     r15, r8
0x18001c2ed  mov     [rbp+4Fh+phHash], r12
0x18001c2f1  mov     rsi, rdx
0x18001c2f4  mov     [rbp+4Fh+hHash], r12
0x18001c2f8  mov     r13, rcx
0x18001c2fb  movups  xmmword ptr [rbp+4Fh+pbData], xmm0
0x18001c2ff  movups  [rbp+4Fh+var_58], xmm0
0x18001c303  test    eax, eax
0x18001c305  jnz     loc_18001C4EF
0x18001c30b  mov     cs:dwDataLen, 2000000h
0x18001c315  test    r15, r15
0x18001c318  jz      loc_18001C56B
0x18001c31e  test    rsi, rsi
0x18001c321  jz      loc_18001C800
0x18001c327  mov     edi, 1
0x18001c32c  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x18001c333  mov     ebx, 0F0000000h
0x18001c338  lea     rcx, [rbp+4Fh+phProv]; phProv
0x18001c33c  mov     r9d, edi; dwProvType
0x18001c33f  mov     [rsp+0C0h+dwFlags], ebx; dwFlags
0x18001c343  xor     edx, edx; szContainer
0x18001c345  call    cs:__imp_CryptAcquireContextW
0x18001c34b  test    eax, eax
0x18001c34d  jz      loc_18001C57D
0x18001c353  test    r15, r15
0x18001c356  jz      short loc_18001C37E
0x18001c358  mov     rcx, [rbp+4Fh+phProv]; hProv
0x18001c35c  lea     rax, [rbp+4Fh+phHash]
0x18001c360  xor     r9d, r9d; dwFlags
0x18001c363  mov     qword ptr [rsp+0C0h+dwFlags], rax; phHash
0x18001c368  xor     r8d, r8d; hKey
0x18001c36b  mov     edx, 8004h; Algid
0x18001c370  call    cs:__imp_CryptCreateHash
0x18001c376  test    eax, eax
0x18001c378  jz      loc_18001C5BD
0x18001c37e  mov     edx, 1E00000h
0x18001c383  test    r14, r14
0x18001c386  jnz     loc_18001C85D
0x18001c38c  cmp     rsi, rdx
0x18001c38f  cmova   rsi, rdx
0x18001c393  mov     rbx, r13
0x18001c396  lea     r12, [rsi+r13]
0x18001c39a  cmp     rbx, r12
0x18001c39d  jb      loc_18001C507
0x18001c3a3  xor     r12d, r12d
0x18001c3a6  mov     esi, 2
0x18001c3ab  test    r15, r15
0x18001c3ae  jz      short loc_18001C420
0x18001c3b0  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18001c3b4  lea     r9, [rbp+4Fh+pdwDataLen]; pdwDataLen
0x18001c3b8  xorps   xmm0, xmm0
0x18001c3bb  mov     [rbp+4Fh+pdwDataLen], r12d
0x18001c3bf  xor     r8d, r8d; pbData
0x18001c3c2  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x18001c3c7  mov     edx, esi; dwParam
0x18001c3c9  movups  xmmword ptr [rbp+4Fh+pbData], xmm0
0x18001c3cd  movups  [rbp+4Fh+var_58], xmm0
0x18001c3d1  call    cs:__imp_CryptGetHashParam
0x18001c3d7  test    eax, eax
0x18001c3d9  jz      loc_18001C703
0x18001c3df  cmp     [rbp+4Fh+pdwDataLen], 14h
0x18001c3e3  jnz     loc_18001C8E0
0x18001c3e9  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18001c3ed  lea     r9, [rbp+4Fh+pdwDataLen]; pdwDataLen
0x18001c3f1  lea     r8, [rbp+4Fh+pbData]; pbData
0x18001c3f5  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x18001c3fa  mov     edx, esi; dwParam
0x18001c3fc  call    cs:__imp_CryptGetHashParam
0x18001c402  test    eax, eax
0x18001c404  jz      loc_18001C743
0x18001c40a  mov     r9, r15
0x18001c40d  lea     r8, [rbp+4Fh+pbData]
0x18001c411  call    FormatAeHashBuffer
0x18001c416  mov     ebx, eax
0x18001c418  test    eax, eax
0x18001c41a  js      loc_18001C910
0x18001c420  test    r14, r14
0x18001c423  jz      loc_18001C997
0x18001c429  mov     rcx, [rbp+4Fh+hHash]; hHash
0x18001c42d  lea     r9, [rbp+4Fh+pdwDataLen]; pdwDataLen
0x18001c431  xorps   xmm0, xmm0
0x18001c434  mov     [rbp+4Fh+pdwDataLen], r12d
0x18001c438  xor     r8d, r8d; pbData
0x18001c43b  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x18001c440  mov     edx, esi; dwParam
0x18001c442  movups  xmmword ptr [rbp+4Fh+pbData], xmm0
0x18001c446  movups  [rbp+4Fh+var_58], xmm0
0x18001c44a  call    cs:__imp_CryptGetHashParam
0x18001c450  test    eax, eax
0x18001c452  jz      loc_18001C783
0x18001c458  cmp     [rbp+4Fh+pdwDataLen], 20h ; ' '
0x18001c45c  jz      loc_18001C93B
0x18001c462  mov     ebx, 8000FFFFh
0x18001c467  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c46e  lea     rax, WPP_GLOBAL_Control
0x18001c475  cmp     rcx, rax
0x18001c478  jz      short loc_18001C495
0x18001c47a  test    [rcx+1Ch], dil
0x18001c47e  jz      short loc_18001C495
0x18001c480  mov     edx, 28h ; '('
0x18001c485  mov     rcx, [rcx+10h]
0x18001c489  lea     r8, WPP_60421427dd2a396270afbef62f846c6d_Traceguids
0x18001c490  call    WPP_SF_
0x18001c495  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18001c499  test    rcx, rcx
0x18001c49c  jnz     loc_18001C99F
0x18001c4a2  mov     rcx, [rbp+4Fh+hHash]; hHash
0x18001c4a6  test    rcx, rcx
0x18001c4a9  jnz     loc_18001C9AE
0x18001c4af  mov     rcx, [rbp+4Fh+hProv]; hProv
0x18001c4b3  test    rcx, rcx
0x18001c4b6  jnz     loc_18001C9BD
0x18001c4bc  mov     rcx, [rbp+4Fh+phProv]; hProv
0x18001c4c0  test    rcx, rcx
0x18001c4c3  jz      short loc_18001C4CD
0x18001c4c5  xor     edx, edx; dwFlags
0x18001c4c7  call    cs:__imp_CryptReleaseContext
0x18001c4cd  mov     eax, ebx
0x18001c4cf  mov     rcx, [rbp+4Fh+var_48]
0x18001c4d3  xor     rcx, rsp; StackCookie
0x18001c4d6  call    __security_check_cookie
0x18001c4db  add     rsp, 88h
0x18001c4e2  pop     r15
0x18001c4e4  pop     r14
0x18001c4e6  pop     r13
0x18001c4e8  pop     r12
0x18001c4ea  pop     rdi
0x18001c4eb  pop     rsi
0x18001c4ec  pop     rbx
0x18001c4ed  pop     rbp
0x18001c4ee  retn
0x18001c4ef  mov     ecx, 40000000h
0x18001c4f4  cmp     eax, ecx
0x18001c4f6  jbe     loc_18001C315
0x18001c4fc  mov     cs:dwDataLen, ecx
0x18001c502  jmp     loc_18001C315
0x18001c507  mov     esi, r12d
0x18001c50a  sub     esi, ebx
0x18001c50c  cmp     esi, cs:dwDataLen
0x18001c512  cmova   esi, cs:dwDataLen
0x18001c519  test    r15, r15
0x18001c51c  jz      short loc_18001C553
0x18001c51e  lea     rcx, [r13+1E00000h]
0x18001c525  cmp     rbx, rcx
0x18001c528  jnb     short loc_18001C553
0x18001c52a  mov     eax, esi
0x18001c52c  add     rax, rbx
0x18001c52f  cmp     rax, rcx
0x18001c532  ja      loc_18001C8B2
0x18001c538  mov     r8d, esi; dwDataLen
0x18001c53b  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18001c53f  xor     r9d, r9d; dwFlags
0x18001c542  mov     rdx, rbx; pbData
0x18001c545  call    cs:__imp_CryptHashData
0x18001c54b  test    eax, eax
0x18001c54d  jz      loc_18001C67D
0x18001c553  test    r14, r14
0x18001c556  jnz     loc_18001C8C0
0x18001c55c  mov     eax, esi
0x18001c55e  mov     edx, 1E00000h
0x18001c563  add     rbx, rax
0x18001c566  jmp     loc_18001C39A
0x18001c56b  test    r14, r14
0x18001c56e  jnz     loc_18001C31E
0x18001c574  lea     ebx, [r14+1]
0x18001c578  jmp     loc_18001C4CD
0x18001c57d  call    cs:__imp_GetLastError
0x18001c583  mov     ebx, eax
0x18001c585  test    eax, eax
0x18001c587  jle     short loc_18001C592
0x18001c589  movzx   ebx, ax
0x18001c58c  or      ebx, 80070000h
0x18001c592  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c599  lea     rax, WPP_GLOBAL_Control
0x18001c5a0  cmp     rcx, rax
0x18001c5a3  jz      loc_18001C495
0x18001c5a9  test    [rcx+1Ch], dil
0x18001c5ad  jz      loc_18001C495
0x18001c5b3  mov     edx, 17h
0x18001c5b8  jmp     loc_18001C845
0x18001c5bd  call    cs:__imp_GetLastError
0x18001c5c3  mov     ebx, eax
0x18001c5c5  test    eax, eax
0x18001c5c7  jle     short loc_18001C5D2
0x18001c5c9  movzx   ebx, ax
0x18001c5cc  or      ebx, 80070000h
0x18001c5d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5d9  lea     rax, WPP_GLOBAL_Control
0x18001c5e0  cmp     rcx, rax
0x18001c5e3  jz      loc_18001C495
0x18001c5e9  test    [rcx+1Ch], dil
0x18001c5ed  jz      loc_18001C495
0x18001c5f3  mov     edx, 18h
0x18001c5f8  jmp     loc_18001C845
0x18001c5fd  call    cs:__imp_GetLastError
0x18001c603  mov     ebx, eax
0x18001c605  test    eax, eax
0x18001c607  jle     short loc_18001C612
0x18001c609  movzx   ebx, ax
0x18001c60c  or      ebx, 80070000h
0x18001c612  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c619  lea     rax, WPP_GLOBAL_Control
0x18001c620  cmp     rcx, rax
0x18001c623  jz      loc_18001C495
0x18001c629  test    [rcx+1Ch], dil
0x18001c62d  jz      loc_18001C495
0x18001c633  mov     edx, 1Ah
0x18001c638  jmp     loc_18001C845
0x18001c63d  call    cs:__imp_GetLastError
0x18001c643  mov     ebx, eax
0x18001c645  test    eax, eax
0x18001c647  jle     short loc_18001C652
0x18001c649  movzx   ebx, ax
0x18001c64c  or      ebx, 80070000h
0x18001c652  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c659  lea     rax, WPP_GLOBAL_Control
0x18001c660  cmp     rcx, rax
0x18001c663  jz      loc_18001C495
0x18001c669  test    [rcx+1Ch], dil
0x18001c66d  jz      loc_18001C495
0x18001c673  mov     edx, 1Bh
0x18001c678  jmp     loc_18001C845
0x18001c67d  call    cs:__imp_GetLastError
0x18001c683  xor     r12d, r12d
0x18001c686  mov     ebx, eax
0x18001c688  test    eax, eax
0x18001c68a  jle     short loc_18001C695
0x18001c68c  movzx   ebx, ax
0x18001c68f  or      ebx, 80070000h
0x18001c695  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c69c  lea     rax, WPP_GLOBAL_Control
0x18001c6a3  cmp     rcx, rax
0x18001c6a6  jz      loc_18001C495
0x18001c6ac  test    [rcx+1Ch], dil
0x18001c6b0  jz      loc_18001C495
0x18001c6b6  mov     edx, 1Ch
0x18001c6bb  jmp     loc_18001C845
0x18001c6c0  call    cs:__imp_GetLastError
0x18001c6c6  xor     r12d, r12d
0x18001c6c9  mov     ebx, eax
0x18001c6cb  test    eax, eax
0x18001c6cd  jle     short loc_18001C6D8
0x18001c6cf  movzx   ebx, ax
0x18001c6d2  or      ebx, 80070000h
0x18001c6d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6df  lea     rax, WPP_GLOBAL_Control
0x18001c6e6  cmp     rcx, rax
0x18001c6e9  jz      loc_18001C495
0x18001c6ef  test    [rcx+1Ch], dil
0x18001c6f3  jz      loc_18001C495
0x18001c6f9  mov     edx, 1Eh
0x18001c6fe  jmp     loc_18001C845
0x18001c703  call    cs:__imp_GetLastError
0x18001c709  mov     ebx, eax
0x18001c70b  test    eax, eax
0x18001c70d  jle     short loc_18001C718
0x18001c70f  movzx   ebx, ax
0x18001c712  or      ebx, 80070000h
0x18001c718  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c71f  lea     rax, WPP_GLOBAL_Control
0x18001c726  cmp     rcx, rax
0x18001c729  jz      loc_18001C495
0x18001c72f  test    [rcx+1Ch], dil
0x18001c733  jz      loc_18001C495
0x18001c739  mov     edx, 1Fh
0x18001c73e  jmp     loc_18001C845
0x18001c743  call    cs:__imp_GetLastError
0x18001c749  mov     ebx, eax
0x18001c74b  test    eax, eax
0x18001c74d  jle     short loc_18001C758
0x18001c74f  movzx   ebx, ax
0x18001c752  or      ebx, 80070000h
0x18001c758  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c75f  lea     rax, WPP_GLOBAL_Control
0x18001c766  cmp     rcx, rax
0x18001c769  jz      loc_18001C495
0x18001c76f  test    [rcx+1Ch], dil
0x18001c773  jz      loc_18001C495
0x18001c779  mov     edx, 21h ; '!'
0x18001c77e  jmp     loc_18001C845
  ... truncated ...
```
