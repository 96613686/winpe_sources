# AeComputeMultiHashes

- ea: `0x18005284c`
- end: `0x18005316e`
- name: `AeComputeMultiHashes`
- size: `2338`
- prototype: `__int64 __fastcall(BYTE *pbData)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800e5358`

## callees

- `0x180004ea0`
- `0x1800058f0`
- `0x18005284c`
- `0x18005490c`
- `0x180054934`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005293f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052b6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052ff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005308c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005293f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800529b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052b6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052ff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005308c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180052b2e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180052b4a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180052b2e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180052b4a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800529af`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180052a7d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800529af`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180052a7d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180053132`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180053147`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180053132`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180053147`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005310a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005311d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005310a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18005311d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180052935`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180052a1b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180052935`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180052a1b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180052c30`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180052cd3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180052fef`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180053082`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180052c30`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180052cd3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180052fef`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180053082`

## pseudocode

```c
__int64 __fastcall AeComputeMultiHashes(BYTE *pbData, unsigned __int64 a2, __int64 a3, wchar_t *a4)
{
  unsigned __int64 v6; // r14
  unsigned int v8; // ebx
  signed int LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  BYTE *v15; // r12
  const BYTE *v16; // rbx
  DWORD v17; // r14d
  DWORD v18; // r8d
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  signed int v24; // eax
  BYTE v25; // cl
  unsigned __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  signed int v30; // eax
  signed int v31; // eax
  unsigned __int64 v32; // r8
  unsigned __int64 i; // rdx
  __int64 v34; // rcx
  DWORD pdwDataLen; // [rsp+30h] [rbp-50h] BYREF
  HCRYPTHASH phHash; // [rsp+38h] [rbp-48h] BYREF
  HCRYPTHASH hHash; // [rsp+40h] [rbp-40h] BYREF
  HCRYPTPROV hProv; // [rsp+48h] [rbp-38h] BYREF
  HCRYPTPROV phProv; // [rsp+50h] [rbp-30h] BYREF
  BYTE pbDataa[16]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v42; // [rsp+68h] [rbp-18h]

  pdwDataLen = 0;
  phProv = 0;
  hProv = 0;
  phHash = 0;
  v6 = a2;
  hHash = 0;
  *(_OWORD *)pbDataa = 0;
  v42 = 0;
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
      wcscpy_s((wchar_t *)a3, 0x2Du, L"0000da39a3ee5e6b4b0d3255bfef95601890afd80709");
    if ( a4 )
      wcscpy_s(a4, 0x41u, L"e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855");
    goto LABEL_105;
  }
  if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_105;
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
      goto LABEL_105;
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
        goto LABEL_105;
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
        goto LABEL_105;
      v11 = 27;
      goto LABEL_19;
    }
  }
  else if ( v6 > 0x1E00000 )
  {
    v6 = 31457280;
  }
  v15 = &pbData[v6];
  v16 = pbData;
  if ( pbData < &pbData[v6] )
  {
    while ( 1 )
    {
      v17 = (_DWORD)v15 - (_DWORD)v16;
      if ( (int)v15 - (int)v16 > dwDataLen )
        v17 = dwDataLen;
      if ( a3 && v16 < pbData + 31457280 )
      {
        v18 = &v16[v17] <= pbData + 31457280 ? v17 : (_DWORD)pbData - (_DWORD)v16 + 31457280;
        if ( !CryptHashData(phHash, v16, v18, 0) )
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
          goto LABEL_105;
        }
      }
      if ( a4 && !CryptHashData(hHash, v16, v17, 0) )
        break;
      v16 += v17;
      if ( v16 >= v15 )
        goto LABEL_65;
    }
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
    goto LABEL_105;
  }
LABEL_65:
  if ( a3 )
  {
    pdwDataLen = 0;
    *(_OWORD *)pbDataa = 0;
    v42 = 0;
    if ( !CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
    {
      v21 = GetLastError();
      v8 = v21;
      if ( v21 > 0 )
        v8 = (unsigned __int16)v21 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_105;
      v11 = 31;
      goto LABEL_19;
    }
    if ( pdwDataLen != 20 )
    {
      v8 = -2147418113;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_105;
      v23 = 32;
      goto LABEL_76;
    }
    if ( !CryptGetHashParam(phHash, 2u, pbDataa, &pdwDataLen, 0) )
    {
      v24 = GetLastError();
      v8 = v24;
      if ( v24 > 0 )
        v8 = (unsigned __int16)v24 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_105;
      v11 = 33;
      goto LABEL_19;
    }
    v25 = pbDataa[0];
    v26 = pbDataa[0];
    *(_DWORD *)a3 = 3145776;
    *(_DWORD *)(a3 + 4) = 3145776;
    *(_WORD *)(a3 + 8) = a0123456789abcd_0[v26 >> 4];
    *(_WORD *)(a3 + 10) = a0123456789abcd_0[v25 & 0xF];
    v27 = pbDataa[1] & 0xF;
    *(_WORD *)(a3 + 12) = a0123456789abcd_0[(unsigned __int64)pbDataa[1] >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27];
    LODWORD(v27) = pbDataa[2];
    *(_WORD *)(a3 + 14) = v26;
    *(_WORD *)(a3 + 16) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[3];
    *(_WORD *)(a3 + 18) = v26;
    *(_WORD *)(a3 + 20) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[4];
    *(_WORD *)(a3 + 22) = v26;
    *(_WORD *)(a3 + 24) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[5];
    *(_WORD *)(a3 + 26) = v26;
    *(_WORD *)(a3 + 28) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[6];
    *(_WORD *)(a3 + 30) = v26;
    *(_WORD *)(a3 + 32) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[7];
    *(_WORD *)(a3 + 34) = v26;
    *(_WORD *)(a3 + 36) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[8];
    *(_WORD *)(a3 + 38) = v26;
    *(_WORD *)(a3 + 40) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[9];
    *(_WORD *)(a3 + 42) = v26;
    *(_WORD *)(a3 + 44) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    *(_WORD *)(a3 + 46) = a0123456789abcd_0[v27 & 0xF];
    v28 = pbDataa[10] & 0xF;
    *(_WORD *)(a3 + 48) = a0123456789abcd_0[(unsigned __int64)pbDataa[10] >> 4];
    *(_WORD *)(a3 + 50) = a0123456789abcd_0[v28];
    v29 = pbDataa[11] & 0xF;
    *(_WORD *)(a3 + 52) = a0123456789abcd_0[(unsigned __int64)pbDataa[11] >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29];
    LODWORD(v29) = pbDataa[12];
    *(_WORD *)(a3 + 54) = v26;
    *(_WORD *)(a3 + 56) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = pbDataa[13];
    *(_WORD *)(a3 + 58) = v26;
    *(_WORD *)(a3 + 60) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = pbDataa[14];
    *(_WORD *)(a3 + 62) = v26;
    *(_WORD *)(a3 + 64) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = pbDataa[15];
    *(_WORD *)(a3 + 66) = v26;
    *(_WORD *)(a3 + 68) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = (unsigned __int8)v42;
    *(_WORD *)(a3 + 70) = v26;
    *(_WORD *)(a3 + 72) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = BYTE1(v42);
    *(_WORD *)(a3 + 74) = v26;
    *(_WORD *)(a3 + 76) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = BYTE2(v42);
    *(_WORD *)(a3 + 78) = v26;
    *(_WORD *)(a3 + 80) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = BYTE3(v42);
    *(_WORD *)(a3 + 82) = v26;
    *(_WORD *)(a3 + 84) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    *(_DWORD *)(a3 + 86) = a0123456789abcd_0[v29 & 0xF];
  }
  if ( !a4 )
  {
LABEL_104:
    v8 = 0;
    goto LABEL_105;
  }
  pdwDataLen = 0;
  *(_OWORD *)pbDataa = 0;
  v42 = 0;
  if ( !CryptGetHashParam(hHash, 2u, 0, &pdwDataLen, 0) )
  {
    v30 = GetLastError();
    v8 = v30;
    if ( v30 > 0 )
      v8 = (unsigned __int16)v30 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_105;
    v11 = 39;
    goto LABEL_19;
  }
  if ( pdwDataLen != 32 )
  {
    v8 = -2147418113;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_105;
    v23 = 40;
LABEL_76:
    WPP_SF_(v22[2], v23, WPP_60421427dd2a396270afbef62f846c6d_Traceguids);
    goto LABEL_105;
  }
  if ( CryptGetHashParam(hHash, 2u, pbDataa, &pdwDataLen, 0) )
  {
    v32 = pdwDataLen;
    for ( i = 0; i < v32; a4[2 * i++ + 1] = a0123456789abcd_0[v34] )
    {
      v34 = pbDataa[i] & 0xF;
      a4[2 * i] = a0123456789abcd_0[(unsigned __int64)pbDataa[i] >> 4];
    }
    a4[2 * i] = 0;
    goto LABEL_104;
  }
  v31 = GetLastError();
  v8 = v31;
  if ( v31 > 0 )
    v8 = (unsigned __int16)v31 | 0x80070000;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_105;
  v11 = 41;
LABEL_19:
  WPP_SF_D(v10[2], v11, WPP_60421427dd2a396270afbef62f846c6d_Traceguids, v8);
LABEL_105:
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
  return v8;
}

```

## disassembly

```asm
0x18005284c  push    rbp
0x18005284e  push    rbx
0x18005284f  push    rsi
0x180052850  push    r12
0x180052852  push    r13
0x180052854  push    r14
0x180052856  push    r15
0x180052858  mov     rbp, rsp
0x18005285b  sub     rsp, 80h
0x180052862  mov     rax, cs:__security_cookie
0x180052869  xor     rax, rsp
0x18005286c  mov     [rbp+var_8], rax
0x180052870  mov     eax, cs:dwDataLen
0x180052876  xor     r12d, r12d
0x180052879  mov     [rbp+pdwDataLen], r12d
0x18005287d  xorps   xmm0, xmm0
0x180052880  mov     [rbp+phProv], r12
0x180052884  mov     rsi, r9
0x180052887  mov     [rbp+hProv], r12
0x18005288b  mov     r15, r8
0x18005288e  mov     [rbp+phHash], r12
0x180052892  mov     r14, rdx
0x180052895  mov     [rbp+hHash], r12
0x180052899  mov     r13, rcx
0x18005289c  movups  xmmword ptr [rbp+pbData], xmm0
0x1800528a0  movups  [rbp+var_18], xmm0
0x1800528a4  test    eax, eax
0x1800528a6  jnz     short loc_1800528B4
0x1800528a8  mov     cs:dwDataLen, 2000000h
0x1800528b2  jmp     short loc_1800528C3
0x1800528b4  mov     ecx, 40000000h
0x1800528b9  cmp     eax, ecx
0x1800528bb  jbe     short loc_1800528C3
0x1800528bd  mov     cs:dwDataLen, ecx
0x1800528c3  test    r15, r15
0x1800528c6  jnz     short loc_1800528D5
0x1800528c8  test    rsi, rsi
0x1800528cb  jnz     short loc_1800528D5
0x1800528cd  lea     ebx, [rsi+1]
0x1800528d0  jmp     loc_18005314D
0x1800528d5  test    r14, r14
0x1800528d8  jnz     short loc_180052919
0x1800528da  mov     ebx, 80004005h
0x1800528df  test    r15, r15
0x1800528e2  jz      short loc_1800528F7
0x1800528e4  lea     r8, a0000da39a3ee5e; "0000da39a3ee5e6b4b0d3255bfef95601890afd"...
0x1800528eb  mov     rcx, r15; Destination
0x1800528ee  lea     edx, [r14+2Dh]; SizeInWords
0x1800528f2  call    wcscpy_s
0x1800528f7  test    rsi, rsi
0x1800528fa  jz      loc_180053101
0x180052900  lea     r8, aE3b0c44298fc1c; "e3b0c44298fc1c149afbf4c8996fb92427ae41e"...
0x180052907  mov     edx, 41h ; 'A'; SizeInWords
0x18005290c  mov     rcx, rsi; Destination
0x18005290f  call    wcscpy_s
0x180052914  jmp     loc_180053101
0x180052919  mov     ebx, 0F0000000h
0x18005291e  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x180052925  mov     r9d, 1; dwProvType
0x18005292b  mov     [rsp+80h+dwFlags], ebx; dwFlags
0x18005292f  xor     edx, edx; szContainer
0x180052931  lea     rcx, [rbp+phProv]; phProv
0x180052935  call    cs:__imp_CryptAcquireContextW
0x18005293b  test    eax, eax
0x18005293d  jnz     short loc_180052992
0x18005293f  call    cs:__imp_GetLastError
0x180052945  mov     ebx, eax
0x180052947  test    eax, eax
0x180052949  jle     short loc_180052954
0x18005294b  movzx   ebx, ax
0x18005294e  or      ebx, 80070000h
0x180052954  mov     rcx, cs:WPP_GLOBAL_Control
0x18005295b  lea     rax, WPP_GLOBAL_Control
0x180052962  cmp     rcx, rax
0x180052965  jz      loc_180053101
0x18005296b  test    byte ptr [rcx+1Ch], 1
0x18005296f  jz      loc_180053101
0x180052975  mov     edx, 17h
0x18005297a  mov     rcx, [rcx+10h]
0x18005297e  lea     r8, WPP_60421427dd2a396270afbef62f846c6d_Traceguids
0x180052985  mov     r9d, ebx
0x180052988  call    WPP_SF_D
0x18005298d  jmp     loc_180053101
0x180052992  test    r15, r15
0x180052995  jz      short loc_1800529F6
0x180052997  mov     rcx, [rbp+phProv]; hProv
0x18005299b  lea     rax, [rbp+phHash]
0x18005299f  xor     r9d, r9d; dwFlags
0x1800529a2  mov     qword ptr [rsp+80h+dwFlags], rax; phHash
0x1800529a7  xor     r8d, r8d; hKey
0x1800529aa  mov     edx, 8004h; Algid
0x1800529af  call    cs:__imp_CryptCreateHash
0x1800529b5  test    eax, eax
0x1800529b7  jnz     short loc_1800529F6
0x1800529b9  call    cs:__imp_GetLastError
0x1800529bf  mov     ebx, eax
0x1800529c1  test    eax, eax
0x1800529c3  jle     short loc_1800529CE
0x1800529c5  movzx   ebx, ax
0x1800529c8  or      ebx, 80070000h
0x1800529ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800529d5  lea     rax, WPP_GLOBAL_Control
0x1800529dc  cmp     rcx, rax
0x1800529df  jz      loc_180053101
0x1800529e5  test    byte ptr [rcx+1Ch], 1
0x1800529e9  jz      loc_180053101
0x1800529ef  mov     edx, 18h
0x1800529f4  jmp     short loc_18005297A
0x1800529f6  mov     edx, 1E00000h
0x1800529fb  test    rsi, rsi
0x1800529fe  jz      loc_180052AC7
0x180052a04  mov     r9d, 18h; dwProvType
0x180052a0a  mov     [rsp+80h+dwFlags], ebx; dwFlags
0x180052a0e  lea     r8, aMicrosoftEnhan; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180052a15  xor     edx, edx; szContainer
0x180052a17  lea     rcx, [rbp+hProv]; phProv
0x180052a1b  call    cs:__imp_CryptAcquireContextW
0x180052a21  test    eax, eax
0x180052a23  jnz     short loc_180052A65
0x180052a25  call    cs:__imp_GetLastError
0x180052a2b  mov     ebx, eax
0x180052a2d  test    eax, eax
0x180052a2f  jle     short loc_180052A3A
0x180052a31  movzx   ebx, ax
0x180052a34  or      ebx, 80070000h
0x180052a3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180052a41  lea     rax, WPP_GLOBAL_Control
0x180052a48  cmp     rcx, rax
0x180052a4b  jz      loc_180053101
0x180052a51  test    byte ptr [rcx+1Ch], 1
0x180052a55  jz      loc_180053101
0x180052a5b  mov     edx, 1Ah
0x180052a60  jmp     loc_18005297A
0x180052a65  mov     rcx, [rbp+hProv]; hProv
0x180052a69  lea     rax, [rbp+hHash]
0x180052a6d  xor     r9d, r9d; dwFlags
0x180052a70  mov     qword ptr [rsp+80h+dwFlags], rax; phHash
0x180052a75  xor     r8d, r8d; hKey
0x180052a78  mov     edx, 800Ch; Algid
0x180052a7d  call    cs:__imp_CryptCreateHash
0x180052a83  test    eax, eax
0x180052a85  jnz     short loc_180052AD0
0x180052a87  call    cs:__imp_GetLastError
0x180052a8d  mov     ebx, eax
0x180052a8f  test    eax, eax
0x180052a91  jle     short loc_180052A9C
0x180052a93  movzx   ebx, ax
0x180052a96  or      ebx, 80070000h
0x180052a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180052aa3  lea     rax, WPP_GLOBAL_Control
0x180052aaa  cmp     rcx, rax
0x180052aad  jz      loc_180053101
0x180052ab3  test    byte ptr [rcx+1Ch], 1
0x180052ab7  jz      loc_180053101
0x180052abd  mov     edx, 1Bh
0x180052ac2  jmp     loc_18005297A
0x180052ac7  cmp     r14, rdx
0x180052aca  cmova   r14, rdx
0x180052ace  jmp     short loc_180052AD5
0x180052ad0  mov     edx, 1E00000h
0x180052ad5  lea     r12, [r14+r13]
0x180052ad9  mov     rbx, r13
0x180052adc  cmp     r13, r12
0x180052adf  jnb     loc_180052BF3
0x180052ae5  mov     r14d, r12d
0x180052ae8  sub     r14d, ebx
0x180052aeb  cmp     r14d, cs:dwDataLen
0x180052af2  cmova   r14d, cs:dwDataLen
0x180052afa  test    r15, r15
0x180052afd  jz      short loc_180052B38
0x180052aff  lea     rcx, [r13+1E00000h]
0x180052b06  cmp     rbx, rcx
0x180052b09  jnb     short loc_180052B38
0x180052b0b  mov     eax, r14d
0x180052b0e  add     rax, rbx
0x180052b11  cmp     rax, rcx
0x180052b14  jbe     short loc_180052B21
0x180052b16  mov     r8d, r13d
0x180052b19  sub     r8d, ebx
0x180052b1c  add     r8d, edx
0x180052b1f  jmp     short loc_180052B24
0x180052b21  mov     r8d, r14d; dwDataLen
0x180052b24  mov     rcx, [rbp+phHash]; hHash
0x180052b28  xor     r9d, r9d; dwFlags
0x180052b2b  mov     rdx, rbx; pbData
0x180052b2e  call    cs:__imp_CryptHashData
0x180052b34  test    eax, eax
0x180052b36  jz      short loc_180052B6D
0x180052b38  test    rsi, rsi
0x180052b3b  jz      short loc_180052B54
0x180052b3d  mov     rcx, [rbp+hHash]; hHash
0x180052b41  xor     r9d, r9d; dwFlags
0x180052b44  mov     r8d, r14d; dwDataLen
0x180052b47  mov     rdx, rbx; pbData
0x180052b4a  call    cs:__imp_CryptHashData
0x180052b50  test    eax, eax
0x180052b52  jz      short loc_180052BB0
0x180052b54  mov     eax, r14d
0x180052b57  add     rbx, rax
0x180052b5a  cmp     rbx, r12
0x180052b5d  jnb     loc_180052BF3
0x180052b63  mov     edx, 1E00000h
0x180052b68  jmp     loc_180052AE5
0x180052b6d  call    cs:__imp_GetLastError
0x180052b73  xor     r12d, r12d
0x180052b76  mov     ebx, eax
0x180052b78  test    eax, eax
0x180052b7a  jle     short loc_180052B85
0x180052b7c  movzx   ebx, ax
0x180052b7f  or      ebx, 80070000h
0x180052b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b8c  lea     rax, WPP_GLOBAL_Control
0x180052b93  cmp     rcx, rax
0x180052b96  jz      loc_180053101
0x180052b9c  test    byte ptr [rcx+1Ch], 1
0x180052ba0  jz      loc_180053101
0x180052ba6  mov     edx, 1Ch
0x180052bab  jmp     loc_18005297A
0x180052bb0  call    cs:__imp_GetLastError
0x180052bb6  xor     r12d, r12d
0x180052bb9  mov     ebx, eax
0x180052bbb  test    eax, eax
0x180052bbd  jle     short loc_180052BC8
0x180052bbf  movzx   ebx, ax
0x180052bc2  or      ebx, 80070000h
0x180052bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180052bcf  lea     rax, WPP_GLOBAL_Control
0x180052bd6  cmp     rcx, rax
0x180052bd9  jz      loc_180053101
0x180052bdf  test    byte ptr [rcx+1Ch], 1
0x180052be3  jz      loc_180053101
0x180052be9  mov     edx, 1Eh
0x180052bee  jmp     loc_18005297A
0x180052bf3  mov     ebx, 2
0x180052bf8  lea     r14, a0123456789abcd_0; "0123456789abcdef"
0x180052bff  xor     r12d, r12d
0x180052c02  lea     r13d, [rbx+0Dh]
0x180052c06  test    r15, r15
0x180052c09  jz      loc_180052FC5
0x180052c0f  mov     rcx, [rbp+phHash]; hHash
0x180052c13  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180052c17  xorps   xmm0, xmm0
0x180052c1a  mov     [rbp+pdwDataLen], r12d
0x180052c1e  xor     r8d, r8d; pbData
0x180052c21  mov     [rsp+80h+dwFlags], r12d; dwFlags
0x180052c26  mov     edx, ebx; dwParam
0x180052c28  movups  xmmword ptr [rbp+pbData], xmm0
0x180052c2c  movups  [rbp+var_18], xmm0
0x180052c30  call    cs:__imp_CryptGetHashParam
0x180052c36  test    eax, eax
0x180052c38  jnz     short loc_180052C7A
0x180052c3a  call    cs:__imp_GetLastError
0x180052c40  mov     ebx, eax
0x180052c42  test    eax, eax
0x180052c44  jle     short loc_180052C4F
0x180052c46  movzx   ebx, ax
0x180052c49  or      ebx, 80070000h
0x180052c4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c56  lea     rax, WPP_GLOBAL_Control
0x180052c5d  cmp     rcx, rax
0x180052c60  jz      loc_180053101
0x180052c66  test    byte ptr [rcx+1Ch], 1
0x180052c6a  jz      loc_180053101
0x180052c70  mov     edx, 1Fh
0x180052c75  jmp     loc_18005297A
0x180052c7a  cmp     [rbp+pdwDataLen], 14h
0x180052c7e  jz      short loc_180052CC0
0x180052c80  mov     ebx, 8000FFFFh
0x180052c85  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c8c  lea     rax, WPP_GLOBAL_Control
0x180052c93  cmp     rcx, rax
0x180052c96  jz      loc_180053101
0x180052c9c  test    byte ptr [rcx+1Ch], 1
0x180052ca0  jz      loc_180053101
0x180052ca6  mov     edx, 20h ; ' '
0x180052cab  mov     rcx, [rcx+10h]
0x180052caf  lea     r8, WPP_60421427dd2a396270afbef62f846c6d_Traceguids
0x180052cb6  call    WPP_SF_
0x180052cbb  jmp     loc_180053101
0x180052cc0  mov     rcx, [rbp+phHash]; hHash
0x180052cc4  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180052cc8  lea     r8, [rbp+pbData]; pbData
0x180052ccc  mov     [rsp+80h+dwFlags], r12d; dwFlags
0x180052cd1  mov     edx, ebx; dwParam
0x180052cd3  call    cs:__imp_CryptGetHashParam
0x180052cd9  test    eax, eax
0x180052cdb  jnz     short loc_180052D1D
0x180052cdd  call    cs:__imp_GetLastError
0x180052ce3  mov     ebx, eax
0x180052ce5  test    eax, eax
0x180052ce7  jle     short loc_180052CF2
0x180052ce9  movzx   ebx, ax
0x180052cec  or      ebx, 80070000h
0x180052cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180052cf9  lea     rax, WPP_GLOBAL_Control
0x180052d00  cmp     rcx, rax
0x180052d03  jz      loc_180053101
0x180052d09  test    byte ptr [rcx+1Ch], 1
0x180052d0d  jz      loc_180053101
0x180052d13  mov     edx, 21h ; '!'
  ... truncated ...
```
