# AeComputeMultiHashes

- ea: `0x180036fa0`
- end: `0x18003763f`
- name: `AeComputeMultiHashes`
- size: `1695`
- prototype: `__int64 __fastcall(BYTE *pbData)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800e3e30`

## callees

- `0x180005890`
- `0x1800068fc`
- `0x180036fa0`
- `0x18003807c`
- `0x1800380a4`
- `0x18003866c`
- `0x180038c70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003717e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800371e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003741a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800374cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003755e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003717e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800371e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003741a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800374cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003755e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800375da`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800375ed`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800375da`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800375ed`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180037108`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800371d6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180037108`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800371d6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18003708e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180037174`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18003708e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180037174`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180037283`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18003729f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180037283`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18003729f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180037602`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180037617`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180037602`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180037617`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18003736d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180037410`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800374c1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180037554`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18003736d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180037410`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x1800374c1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180037554`

## pseudocode

```c
__int64 __fastcall AeComputeMultiHashes(BYTE *pbData, unsigned __int64 a2, wchar_t *a3, wchar_t *a4)
{
  unsigned __int64 v6; // rsi
  signed int v8; // ebx
  signed int LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  const BYTE *v15; // rbx
  BYTE *v16; // r12
  DWORD v17; // esi
  DWORD v18; // r8d
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rcx
  signed int v26; // eax
  signed int v27; // eax
  signed int v28; // eax
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
    v8 = -2147467259;
    if ( a3 )
      wcscpy_s(a3, 0x2Du, L"0000da39a3ee5e6b4b0d3255bfef95601890afd80709");
    if ( a4 )
      wcscpy_s(a4, 0x41u, L"e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855");
    goto LABEL_109;
  }
  if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_109;
    v11 = 23;
    goto LABEL_19;
  }
  if ( a3 && !CryptCreateHash(phProv, 0x8004u, 0, 0, &phHash) )
  {
    v12 = GetLastError();
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_109;
    v11 = 24;
    goto LABEL_19;
  }
  if ( a4 )
  {
    if ( !CryptAcquireContextW(&hProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000000) )
    {
      v13 = GetLastError();
      v8 = v13;
      if ( v13 > 0 )
        v8 = (unsigned __int16)v13 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_109;
      v11 = 26;
      goto LABEL_19;
    }
    if ( !CryptCreateHash(hProv, 0x800Cu, 0, 0, &hHash) )
    {
      v14 = GetLastError();
      v8 = v14;
      if ( v14 > 0 )
        v8 = (unsigned __int16)v14 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_109;
      v11 = 27;
      goto LABEL_19;
    }
  }
  else if ( v6 > 0x1E00000 )
  {
    v6 = 31457280;
  }
  v15 = pbData;
  v16 = &pbData[v6];
  while ( v15 < v16 )
  {
    v17 = (_DWORD)v16 - (_DWORD)v15;
    if ( (int)v16 - (int)v15 > dwDataLen )
      v17 = dwDataLen;
    if ( a3 && v15 < pbData + 31457280 )
    {
      v18 = &v15[v17] <= pbData + 31457280 ? v17 : (_DWORD)pbData - (_DWORD)v15 + 31457280;
      if ( !CryptHashData(phHash, v15, v18, 0) )
      {
        v19 = GetLastError();
        v8 = v19;
        if ( v19 > 0 )
          v8 = (unsigned __int16)v19 | 0x80070000;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 28;
          goto LABEL_19;
        }
        goto LABEL_109;
      }
    }
    if ( a4 && !CryptHashData(hHash, v15, v17, 0) )
    {
      v20 = GetLastError();
      v8 = v20;
      if ( v20 > 0 )
        v8 = (unsigned __int16)v20 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 30;
        goto LABEL_19;
      }
      goto LABEL_109;
    }
    v15 += v17;
  }
  if ( !a3 )
    goto LABEL_87;
  pdwDataLen = 0;
  *(_OWORD *)pbDataa = 0;
  v36 = 0;
  if ( CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
  {
    if ( pdwDataLen != 20 )
    {
      v8 = -2147418113;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_109;
      v23 = 32;
      goto LABEL_76;
    }
    if ( !CryptGetHashParam(phHash, 2u, pbDataa, &pdwDataLen, 0) )
    {
      v26 = GetLastError();
      v8 = v26;
      if ( v26 > 0 )
        v8 = (unsigned __int16)v26 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_109;
      v11 = 33;
      goto LABEL_19;
    }
    v8 = FormatAeHashBuffer(v25, v24, pbDataa, a3);
    if ( v8 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_109;
      v11 = 34;
      goto LABEL_19;
    }
LABEL_87:
    if ( a4 )
    {
      pdwDataLen = 0;
      *(_OWORD *)pbDataa = 0;
      v36 = 0;
      if ( !CryptGetHashParam(hHash, 2u, 0, &pdwDataLen, 0) )
      {
        v27 = GetLastError();
        v8 = v27;
        if ( v27 > 0 )
          v8 = (unsigned __int16)v27 | 0x80070000;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_109;
        v11 = 39;
        goto LABEL_19;
      }
      if ( pdwDataLen != 32 )
      {
        v8 = -2147418113;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_109;
        v23 = 40;
LABEL_76:
        WPP_SF_(v22[2], v23, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids);
        goto LABEL_109;
      }
      if ( !CryptGetHashParam(hHash, 2u, pbDataa, &pdwDataLen, 0) )
      {
        v28 = GetLastError();
        v8 = v28;
        if ( v28 > 0 )
          v8 = (unsigned __int16)v28 | 0x80070000;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_109;
        v11 = 41;
LABEL_19:
        WPP_SF_D(v10[2], v11, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids, (unsigned int)v8);
        goto LABEL_109;
      }
      v8 = FormatHashBuffer(pbDataa, pdwDataLen, a4);
      if ( v8 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_109;
        v11 = 42;
        goto LABEL_19;
      }
    }
    v8 = 0;
    goto LABEL_109;
  }
  v21 = GetLastError();
  v8 = v21;
  if ( v21 > 0 )
    v8 = (unsigned __int16)v21 | 0x80070000;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 31;
    goto LABEL_19;
  }
LABEL_109:
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
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180036fa0  push    rbp
0x180036fa2  push    rbx
0x180036fa3  push    rsi
0x180036fa4  push    rdi
0x180036fa5  push    r12
0x180036fa7  push    r13
0x180036fa9  push    r14
0x180036fab  push    r15
0x180036fad  lea     rbp, [rsp-17h]
0x180036fb2  sub     rsp, 88h
0x180036fb9  mov     rax, cs:__security_cookie
0x180036fc0  xor     rax, rsp
0x180036fc3  mov     [rbp+4Fh+var_48], rax
0x180036fc7  mov     eax, cs:dwDataLen
0x180036fcd  xor     r12d, r12d
0x180036fd0  mov     [rbp+4Fh+pdwDataLen], r12d
0x180036fd4  xorps   xmm0, xmm0
0x180036fd7  mov     [rbp+4Fh+phProv], r12
0x180036fdb  mov     r14, r9
0x180036fde  mov     [rbp+4Fh+hProv], r12
0x180036fe2  mov     r15, r8
0x180036fe5  mov     [rbp+4Fh+phHash], r12
0x180036fe9  mov     rsi, rdx
0x180036fec  mov     [rbp+4Fh+hHash], r12
0x180036ff0  mov     r13, rcx
0x180036ff3  movups  xmmword ptr [rbp+4Fh+pbData], xmm0
0x180036ff7  movups  [rbp+4Fh+var_58], xmm0
0x180036ffb  test    eax, eax
0x180036ffd  jnz     short loc_18003700B
0x180036fff  mov     cs:dwDataLen, 2000000h
0x180037009  jmp     short loc_18003701A
0x18003700b  mov     ecx, 40000000h
0x180037010  cmp     eax, ecx
0x180037012  jbe     short loc_18003701A
0x180037014  mov     cs:dwDataLen, ecx
0x18003701a  test    r15, r15
0x18003701d  jnz     short loc_18003702D
0x18003701f  test    r14, r14
0x180037022  jnz     short loc_18003702D
0x180037024  lea     ebx, [r15+1]
0x180037028  jmp     loc_18003761D
0x18003702d  test    rsi, rsi
0x180037030  jnz     short loc_180037070
0x180037032  mov     ebx, 80004005h
0x180037037  test    r15, r15
0x18003703a  jz      short loc_18003704E
0x18003703c  lea     r8, a0000da39a3ee5e; "0000da39a3ee5e6b4b0d3255bfef95601890afd"...
0x180037043  mov     rcx, r15; Destination
0x180037046  lea     edx, [rsi+2Dh]; SizeInWords
0x180037049  call    wcscpy_s
0x18003704e  test    r14, r14
0x180037051  jz      loc_1800375D1
0x180037057  lea     r8, aE3b0c44298fc1c; "e3b0c44298fc1c149afbf4c8996fb92427ae41e"...
0x18003705e  mov     edx, 41h ; 'A'; SizeInWords
0x180037063  mov     rcx, r14; Destination
0x180037066  call    wcscpy_s
0x18003706b  jmp     loc_1800375D1
0x180037070  mov     edi, 1
0x180037075  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x18003707c  mov     ebx, 0F0000000h
0x180037081  lea     rcx, [rbp+4Fh+phProv]; phProv
0x180037085  mov     r9d, edi; dwProvType
0x180037088  mov     [rsp+0C0h+dwFlags], ebx; dwFlags
0x18003708c  xor     edx, edx; szContainer
0x18003708e  call    cs:__imp_CryptAcquireContextW
0x180037094  test    eax, eax
0x180037096  jnz     short loc_1800370EB
0x180037098  call    cs:__imp_GetLastError
0x18003709e  mov     ebx, eax
0x1800370a0  test    eax, eax
0x1800370a2  jle     short loc_1800370AD
0x1800370a4  movzx   ebx, ax
0x1800370a7  or      ebx, 80070000h
0x1800370ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370b4  lea     rax, WPP_GLOBAL_Control
0x1800370bb  cmp     rcx, rax
0x1800370be  jz      loc_1800375D1
0x1800370c4  test    [rcx+1Ch], dil
0x1800370c8  jz      loc_1800375D1
0x1800370ce  mov     edx, 17h
0x1800370d3  mov     rcx, [rcx+10h]
0x1800370d7  lea     r8, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids
0x1800370de  mov     r9d, ebx
0x1800370e1  call    WPP_SF_D
0x1800370e6  jmp     loc_1800375D1
0x1800370eb  test    r15, r15
0x1800370ee  jz      short loc_18003714F
0x1800370f0  mov     rcx, [rbp+4Fh+phProv]; hProv
0x1800370f4  lea     rax, [rbp+4Fh+phHash]
0x1800370f8  xor     r9d, r9d; dwFlags
0x1800370fb  mov     qword ptr [rsp+0C0h+dwFlags], rax; phHash
0x180037100  xor     r8d, r8d; hKey
0x180037103  mov     edx, 8004h; Algid
0x180037108  call    cs:__imp_CryptCreateHash
0x18003710e  test    eax, eax
0x180037110  jnz     short loc_18003714F
0x180037112  call    cs:__imp_GetLastError
0x180037118  mov     ebx, eax
0x18003711a  test    eax, eax
0x18003711c  jle     short loc_180037127
0x18003711e  movzx   ebx, ax
0x180037121  or      ebx, 80070000h
0x180037127  mov     rcx, cs:WPP_GLOBAL_Control
0x18003712e  lea     rax, WPP_GLOBAL_Control
0x180037135  cmp     rcx, rax
0x180037138  jz      loc_1800375D1
0x18003713e  test    [rcx+1Ch], dil
0x180037142  jz      loc_1800375D1
0x180037148  mov     edx, 18h
0x18003714d  jmp     short loc_1800370D3
0x18003714f  mov     edx, 1E00000h
0x180037154  test    r14, r14
0x180037157  jz      loc_180037220
0x18003715d  mov     r9d, 18h; dwProvType
0x180037163  mov     [rsp+0C0h+dwFlags], ebx; dwFlags
0x180037167  lea     r8, aMicrosoftEnhan; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18003716e  xor     edx, edx; szContainer
0x180037170  lea     rcx, [rbp+4Fh+hProv]; phProv
0x180037174  call    cs:__imp_CryptAcquireContextW
0x18003717a  test    eax, eax
0x18003717c  jnz     short loc_1800371BE
0x18003717e  call    cs:__imp_GetLastError
0x180037184  mov     ebx, eax
0x180037186  test    eax, eax
0x180037188  jle     short loc_180037193
0x18003718a  movzx   ebx, ax
0x18003718d  or      ebx, 80070000h
0x180037193  mov     rcx, cs:WPP_GLOBAL_Control
0x18003719a  lea     rax, WPP_GLOBAL_Control
0x1800371a1  cmp     rcx, rax
0x1800371a4  jz      loc_1800375D1
0x1800371aa  test    [rcx+1Ch], dil
0x1800371ae  jz      loc_1800375D1
0x1800371b4  mov     edx, 1Ah
0x1800371b9  jmp     loc_1800370D3
0x1800371be  mov     rcx, [rbp+4Fh+hProv]; hProv
0x1800371c2  lea     rax, [rbp+4Fh+hHash]
0x1800371c6  xor     r9d, r9d; dwFlags
0x1800371c9  mov     qword ptr [rsp+0C0h+dwFlags], rax; phHash
0x1800371ce  xor     r8d, r8d; hKey
0x1800371d1  mov     edx, 800Ch; Algid
0x1800371d6  call    cs:__imp_CryptCreateHash
0x1800371dc  test    eax, eax
0x1800371de  jnz     short loc_180037229
0x1800371e0  call    cs:__imp_GetLastError
0x1800371e6  mov     ebx, eax
0x1800371e8  test    eax, eax
0x1800371ea  jle     short loc_1800371F5
0x1800371ec  movzx   ebx, ax
0x1800371ef  or      ebx, 80070000h
0x1800371f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800371fc  lea     rax, WPP_GLOBAL_Control
0x180037203  cmp     rcx, rax
0x180037206  jz      loc_1800375D1
0x18003720c  test    [rcx+1Ch], dil
0x180037210  jz      loc_1800375D1
0x180037216  mov     edx, 1Bh
0x18003721b  jmp     loc_1800370D3
0x180037220  cmp     rsi, rdx
0x180037223  cmova   rsi, rdx
0x180037227  jmp     short loc_18003722E
0x180037229  mov     edx, 1E00000h
0x18003722e  mov     rbx, r13
0x180037231  lea     r12, [rsi+r13]
0x180037235  cmp     rbx, r12
0x180037238  jnb     loc_18003733B
0x18003723e  mov     esi, r12d
0x180037241  sub     esi, ebx
0x180037243  cmp     esi, cs:dwDataLen
0x180037249  cmova   esi, cs:dwDataLen
0x180037250  test    r15, r15
0x180037253  jz      short loc_18003728D
0x180037255  lea     rcx, [r13+1E00000h]
0x18003725c  cmp     rbx, rcx
0x18003725f  jnb     short loc_18003728D
0x180037261  mov     eax, esi
0x180037263  add     rax, rbx
0x180037266  cmp     rax, rcx
0x180037269  jbe     short loc_180037276
0x18003726b  mov     r8d, r13d
0x18003726e  sub     r8d, ebx
0x180037271  add     r8d, edx
0x180037274  jmp     short loc_180037279
0x180037276  mov     r8d, esi; dwDataLen
0x180037279  mov     rcx, [rbp+4Fh+phHash]; hHash
0x18003727d  xor     r9d, r9d; dwFlags
0x180037280  mov     rdx, rbx; pbData
0x180037283  call    cs:__imp_CryptHashData
0x180037289  test    eax, eax
0x18003728b  jz      short loc_1800372B5
0x18003728d  test    r14, r14
0x180037290  jz      short loc_1800372A9
0x180037292  mov     rcx, [rbp+4Fh+hHash]; hHash
0x180037296  xor     r9d, r9d; dwFlags
0x180037299  mov     r8d, esi; dwDataLen
0x18003729c  mov     rdx, rbx; pbData
0x18003729f  call    cs:__imp_CryptHashData
0x1800372a5  test    eax, eax
0x1800372a7  jz      short loc_1800372F8
0x1800372a9  mov     eax, esi
0x1800372ab  mov     edx, 1E00000h
0x1800372b0  add     rbx, rax
0x1800372b3  jmp     short loc_180037235
0x1800372b5  call    cs:__imp_GetLastError
0x1800372bb  xor     r12d, r12d
0x1800372be  mov     ebx, eax
0x1800372c0  test    eax, eax
0x1800372c2  jle     short loc_1800372CD
0x1800372c4  movzx   ebx, ax
0x1800372c7  or      ebx, 80070000h
0x1800372cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372d4  lea     rax, WPP_GLOBAL_Control
0x1800372db  cmp     rcx, rax
0x1800372de  jz      loc_1800375D1
0x1800372e4  test    [rcx+1Ch], dil
0x1800372e8  jz      loc_1800375D1
0x1800372ee  mov     edx, 1Ch
0x1800372f3  jmp     loc_1800370D3
0x1800372f8  call    cs:__imp_GetLastError
0x1800372fe  xor     r12d, r12d
0x180037301  mov     ebx, eax
0x180037303  test    eax, eax
0x180037305  jle     short loc_180037310
0x180037307  movzx   ebx, ax
0x18003730a  or      ebx, 80070000h
0x180037310  mov     rcx, cs:WPP_GLOBAL_Control
0x180037317  lea     rax, WPP_GLOBAL_Control
0x18003731e  cmp     rcx, rax
0x180037321  jz      loc_1800375D1
0x180037327  test    [rcx+1Ch], dil
0x18003732b  jz      loc_1800375D1
0x180037331  mov     edx, 1Eh
0x180037336  jmp     loc_1800370D3
0x18003733b  xor     r12d, r12d
0x18003733e  mov     esi, 2
0x180037343  test    r15, r15
0x180037346  jz      loc_180037497
0x18003734c  mov     rcx, [rbp+4Fh+phHash]; hHash
0x180037350  lea     r9, [rbp+4Fh+pdwDataLen]; pdwDataLen
0x180037354  xorps   xmm0, xmm0
0x180037357  mov     [rbp+4Fh+pdwDataLen], r12d
0x18003735b  xor     r8d, r8d; pbData
0x18003735e  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x180037363  mov     edx, esi; dwParam
0x180037365  movups  xmmword ptr [rbp+4Fh+pbData], xmm0
0x180037369  movups  [rbp+4Fh+var_58], xmm0
0x18003736d  call    cs:__imp_CryptGetHashParam
0x180037373  test    eax, eax
0x180037375  jnz     short loc_1800373B7
0x180037377  call    cs:__imp_GetLastError
0x18003737d  mov     ebx, eax
0x18003737f  test    eax, eax
0x180037381  jle     short loc_18003738C
0x180037383  movzx   ebx, ax
0x180037386  or      ebx, 80070000h
0x18003738c  mov     rcx, cs:WPP_GLOBAL_Control
0x180037393  lea     rax, WPP_GLOBAL_Control
0x18003739a  cmp     rcx, rax
0x18003739d  jz      loc_1800375D1
0x1800373a3  test    [rcx+1Ch], dil
0x1800373a7  jz      loc_1800375D1
0x1800373ad  mov     edx, 1Fh
0x1800373b2  jmp     loc_1800370D3
0x1800373b7  cmp     [rbp+4Fh+pdwDataLen], 14h
0x1800373bb  jz      short loc_1800373FD
0x1800373bd  mov     ebx, 8000FFFFh
0x1800373c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800373c9  lea     rax, WPP_GLOBAL_Control
0x1800373d0  cmp     rcx, rax
0x1800373d3  jz      loc_1800375D1
0x1800373d9  test    [rcx+1Ch], dil
0x1800373dd  jz      loc_1800375D1
0x1800373e3  mov     edx, 20h ; ' '
0x1800373e8  mov     rcx, [rcx+10h]
0x1800373ec  lea     r8, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids
0x1800373f3  call    WPP_SF_
0x1800373f8  jmp     loc_1800375D1
0x1800373fd  mov     rcx, [rbp+4Fh+phHash]; hHash
0x180037401  lea     r9, [rbp+4Fh+pdwDataLen]; pdwDataLen
0x180037405  lea     r8, [rbp+4Fh+pbData]; pbData
0x180037409  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x18003740e  mov     edx, esi; dwParam
0x180037410  call    cs:__imp_CryptGetHashParam
0x180037416  test    eax, eax
0x180037418  jnz     short loc_18003745A
0x18003741a  call    cs:__imp_GetLastError
0x180037420  mov     ebx, eax
0x180037422  test    eax, eax
0x180037424  jle     short loc_18003742F
0x180037426  movzx   ebx, ax
0x180037429  or      ebx, 80070000h
0x18003742f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037436  lea     rax, WPP_GLOBAL_Control
0x18003743d  cmp     rcx, rax
0x180037440  jz      loc_1800375D1
0x180037446  test    [rcx+1Ch], dil
0x18003744a  jz      loc_1800375D1
0x180037450  mov     edx, 21h ; '!'
0x180037455  jmp     loc_1800370D3
0x18003745a  mov     r9, r15
  ... truncated ...
```
