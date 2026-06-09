# MdmCrypto::ComputeHMAC(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)

- ea: `0x1800078ec`
- end: `0x180007fac`
- name: `?ComputeHMAC@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@0PEAU2@@Z`
- size: `1728`
- prototype: `__int64 __fastcall(const struct _CRYPTOAPI_BLOB *, const struct _CRYPTOAPI_BLOB *, DWORD *pdwDataLen)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800067d8`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x180001f6a`
- `0x180001fd4`
- `0x180006548`
- `0x180006620`
- `0x1800078ec`
- `0x180007fb4`
- `0x18000886c`
- `0x180008910`
- `0x180008d58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007b3e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007e9d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007b3e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007f60`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x180007f0d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x180007f0d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180007d5b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180007e39`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180007d5b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180007e39`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetHashParam` at `0x180007cbe`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetHashParam` at `0x180007cbe`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180007c63`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180007c63`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x180007c05`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x180007c05`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180007f88`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180007f88`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180007efe`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180007f77`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180007efe`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180007f77`

## string_xrefs

- `0x180007976`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x1800079df`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180007e79`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180007ed4`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180007a50`: `CHR(CreateHash(hProv, ((4 << 13) | (0) | 12), &hHash))`
- `0x180007c8f`: `CBR(CryptCreateHash(hProv, ((4 << 13) | (0) | 9), hKey, 0, &hHMACHash))`

## pseudocode

```c
__int64 __fastcall MdmCrypto::ComputeHMAC(
        const struct _CRYPTOAPI_BLOB *a1,
        const struct _CRYPTOAPI_BLOB *a2,
        DWORD *pdwDataLen)
{
  signed int Provider; // ebx
  int v7; // ecx
  int v8; // r8d
  unsigned int v9; // eax
  int v10; // ecx
  signed int v11; // eax
  int v12; // ecx
  signed int v13; // eax
  int v14; // ecx
  signed int v15; // eax
  int v16; // ecx
  HCRYPTHASH v17; // rcx
  int v18; // ecx
  signed int v19; // eax
  int v20; // ecx
  void *v21; // rax
  int v22; // ecx
  signed int LastError; // eax
  int v24; // ecx
  void *v25; // rcx
  BYTE *v26; // rax
  __int64 cbData; // rcx
  _BYTE *v28; // rcx
  __int64 v29; // rax
  char phKey; // [rsp+20h] [rbp-39h]
  const char *v32; // [rsp+28h] [rbp-31h]
  HCRYPTPROV hProv; // [rsp+30h] [rbp-29h] BYREF
  HCRYPTHASH hBaseData; // [rsp+38h] [rbp-21h] BYREF
  HCRYPTKEY hKey; // [rsp+40h] [rbp-19h] BYREF
  void *Source[2]; // [rsp+48h] [rbp-11h] BYREF
  _CRYPTOAPI_BLOB v37; // [rsp+58h] [rbp-1h] BYREF
  BYTE pbData[16]; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v39; // [rsp+78h] [rbp+1Fh]
  __int64 v40; // [rsp+88h] [rbp+2Fh]
  int v41; // [rsp+C0h] [rbp+67h] BYREF
  HCRYPTHASH phHash; // [rsp+D8h] [rbp+7Fh] BYREF

  hProv = 0;
  hBaseData = 0;
  phHash = 0;
  hKey = 0;
  *(_OWORD *)pbData = 0;
  v40 = 0;
  v39 = 0;
  *(_OWORD *)Source = 0;
  v37 = 0;
  if ( !a1->pbData )
  {
    Provider = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        148,
        (__int64)"CPR(blobToHash.pbData)");
    goto LABEL_70;
  }
  if ( !a1->cbData )
  {
    Provider = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a1,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        149,
        (__int64)"CBR(blobToHash.cbData > 0)");
LABEL_70:
    if ( !pdwDataLen )
      goto LABEL_78;
LABEL_76:
    v25 = (void *)*((_QWORD *)pdwDataLen + 1);
    if ( v25 )
    {
      operator delete(v25, (unsigned __int64)a2);
      *((_QWORD *)pdwDataLen + 1) = 0;
      *pdwDataLen = 0;
    }
    goto LABEL_78;
  }
  if ( !pdwDataLen )
  {
    Provider = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_82;
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
      150,
      (__int64)"CPR(pblobHMACHash)");
    goto LABEL_78;
  }
  Provider = MdmCrypto::GetProvider(&hProv);
  if ( Provider < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_76;
    v32 = "CHR(GetProvider(&hProv))";
    phKey = -103;
LABEL_13:
    v8 = Provider;
LABEL_75:
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      (_DWORD)a2,
      v8,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
      phKey,
      (__int64)v32);
    goto LABEL_76;
  }
  Provider = MdmCrypto::CreateHash(hProv, (unsigned int)a2, &hBaseData);
  if ( Provider < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_76;
    v32 = "CHR(CreateHash(hProv, ((4 << 13) | (0) | 12), &hHash))";
    phKey = -100;
    goto LABEL_13;
  }
  Provider = MdmCrypto::UnprotectData(a2, (struct _CRYPTOAPI_BLOB *)Source);
  if ( Provider < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_76;
    v32 = "CHR(UnprotectData(blobSharedSecret, &blobUnprotectedSecret))";
    phKey = -97;
    goto LABEL_13;
  }
  if ( !LODWORD(Source[0]) )
  {
    Provider = -2147418113;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        (_DWORD)a2,
        -2147418113,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        162,
        (__int64)"CBR(blobUnprotectedSecret.cbData > 0)");
    goto LABEL_76;
  }
  v37.pbData = (BYTE *)operator new[](
                         (unsigned int)(LODWORD(Source[0]) + 4),
                         (const struct std::nothrow_t *)&std::nothrow);
  if ( !v37.pbData )
  {
    Provider = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        (_DWORD)a2,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        166,
        (__int64)"CPR(blobPrefixedSecret.pbData)");
    goto LABEL_76;
  }
  memset_0(v37.pbData, 0, (unsigned int)(LODWORD(Source[0]) + 4));
  v9 = LODWORD(Source[0]) + 4;
  v37.cbData = LODWORD(Source[0]) + 4;
  if ( !v37.pbData )
  {
    *(_DWORD *)_o__errno() = 22;
LABEL_73:
    invalid_parameter_noinfo();
    v8 = -2147467259;
    Provider = -2147467259;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_76;
    v32 = "CBR(memcpy_s(blobPrefixedSecret.pbData, c_cbCcpHmacPrefix + blobUnprotectedSecret.cbData, c_szCcpHmacPrefix, c"
          "_cbCcpHmacPrefix) == 0)";
    phKey = -83;
    goto LABEL_75;
  }
  if ( v9 < 4 )
  {
    memset_0(v37.pbData, 0, v9);
    *(_DWORD *)_o__errno() = 34;
    goto LABEL_73;
  }
  *(_DWORD *)v37.pbData = 1213415752;
  if ( memcpy_s(v37.pbData + 4, LODWORD(Source[0]), Source[1], LODWORD(Source[0])) )
  {
    Provider = -2147467259;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        (_DWORD)a2,
        -2147467259,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        178,
        (__int64)"CBR(memcpy_s(blobPrefixedSecret.pbData + c_cbCcpHmacPrefix, blobUnprotectedSecret.cbData, blobUnprotect"
                 "edSecret.pbData, blobUnprotectedSecret.cbData) == 0)");
    goto LABEL_76;
  }
  v41 = 0;
  Provider = MdmCrypto::HashData(hBaseData, &v37, &v41);
  if ( Provider < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_76;
    v32 = "CHR(HashData(hHash, blobPrefixedSecret, 0))";
    phKey = -75;
    goto LABEL_13;
  }
  if ( CryptDeriveKey(hProv, 0x6801u, hBaseData, 0x800000u, &hKey) )
  {
    if ( CryptCreateHash(hProv, 0x8009u, hKey, 0, &phHash) )
    {
      *(_DWORD *)pbData = 32780;
      if ( CryptSetHashParam(phHash, 5u, pbData, 0) )
      {
        v41 = 0;
        Provider = MdmCrypto::HashData(phHash, a1, &v41);
        if ( Provider < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
            goto LABEL_76;
          v32 = "CHR(HashData(hHMACHash, blobToHash, 0))";
          phKey = -52;
          goto LABEL_13;
        }
        v17 = phHash;
        *pdwDataLen = 0;
        if ( CryptGetHashParam(v17, 2u, 0, pdwDataLen, 0) )
        {
          if ( !*pdwDataLen )
          {
            Provider = -2147418113;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v18,
                (_DWORD)a2,
                -2147418113,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
                216,
                (__int64)"CBR(pblobHMACHash->cbData > 0)");
            goto LABEL_76;
          }
          v21 = operator new[](*pdwDataLen, (const struct std::nothrow_t *)&std::nothrow);
          *((_QWORD *)pdwDataLen + 1) = v21;
          if ( !v21 )
          {
            Provider = -2147024882;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v22,
                (_DWORD)a2,
                -2147024882,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
                219,
                (__int64)"CPR(pblobHMACHash->pbData)");
            goto LABEL_76;
          }
          memset_0(v21, 0, *pdwDataLen);
          if ( CryptGetHashParam(phHash, 2u, *((BYTE **)pdwDataLen + 1), pdwDataLen, 0) )
            goto LABEL_78;
          LastError = GetLastError();
          Provider = LastError;
          if ( LastError > 0 )
            Provider = (unsigned __int16)LastError | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v24,
              (_DWORD)a2,
              Provider,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
              228,
              (__int64)"CBR(CryptGetHashParam(hHMACHash, 0x0002, pblobHMACHash->pbData, &pblobHMACHash->cbData, 0))");
        }
        else
        {
          v19 = GetLastError();
          Provider = v19;
          if ( v19 > 0 )
            Provider = (unsigned __int16)v19 | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v20,
              (_DWORD)a2,
              Provider,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
              213,
              (__int64)"CBR(CryptGetHashParam(hHMACHash, 0x0002, 0, &pblobHMACHash->cbData, 0))");
        }
      }
      else
      {
        v15 = GetLastError();
        Provider = v15;
        if ( v15 > 0 )
          Provider = (unsigned __int16)v15 | 0x80070000;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v16,
            (_DWORD)a2,
            Provider,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
            201,
            (__int64)"CBR(CryptSetHashParam(hHMACHash, 0x0005, (BYTE*)&hmacInfo, 0))");
      }
    }
    else
    {
      v13 = GetLastError();
      Provider = v13;
      if ( v13 > 0 )
        Provider = (unsigned __int16)v13 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v14,
          (_DWORD)a2,
          Provider,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
          193,
          (__int64)"CBR(CryptCreateHash(hProv, ((4 << 13) | (0) | 9), hKey, 0, &hHMACHash))");
    }
  }
  else
  {
    v11 = GetLastError();
    Provider = v11;
    if ( v11 > 0 )
      Provider = (unsigned __int16)v11 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        (_DWORD)a2,
        Provider,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        185,
        (__int64)"CBR(CryptDeriveKey(hProv, ((3 << 13)|(4 << 9)|1), hHash, 0x00800000, &hKey))");
  }
  if ( Provider < 0 )
    goto LABEL_70;
LABEL_78:
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( hKey )
    CryptDestroyKey(hKey);
LABEL_82:
  v26 = v37.pbData;
  if ( v37.pbData )
  {
    cbData = v37.cbData;
    if ( v37.cbData )
    {
      do
      {
        *v26++ = 0;
        --cbData;
      }
      while ( cbData );
    }
    operator delete(v37.pbData, (unsigned __int64)a2);
    v37.pbData = 0;
    v37.cbData = 0;
  }
  v28 = Source[1];
  if ( Source[1] )
  {
    v29 = LODWORD(Source[0]);
    if ( LODWORD(Source[0]) )
    {
      do
      {
        *v28++ = 0;
        --v29;
      }
      while ( v29 );
      v28 = Source[1];
    }
    LocalFree(v28);
    Source[1] = 0;
    LODWORD(Source[0]) = 0;
  }
  if ( hBaseData )
    CryptDestroyHash(hBaseData);
  if ( hProv )
    CryptReleaseContext(hProv, 0);
  return (unsigned int)Provider;
}

```

## disassembly

```asm
0x1800078ec  mov     [rsp-8+arg_8], rbx
0x1800078f1  mov     [rsp-8+arg_10], rsi
0x1800078f6  push    rbp
0x1800078f7  push    rdi
0x1800078f8  push    r12
0x1800078fa  push    r14
0x1800078fc  push    r15
0x1800078fe  lea     rbp, [rsp-37h]
0x180007903  sub     rsp, 90h
0x18000790a  xor     r15d, r15d
0x18000790d  xorps   xmm0, xmm0
0x180007910  xor     eax, eax
0x180007912  mov     [rbp+57h+hProv], r15
0x180007916  xorps   xmm1, xmm1
0x180007919  mov     rdi, r8
0x18000791c  mov     r14, rdx
0x18000791f  mov     rsi, rcx
0x180007922  lea     r12d, [r15+1]
0x180007926  mov     [rbp+57h+hBaseData], r15
0x18000792a  mov     [rbp+57h+phHash], r15
0x18000792e  mov     [rbp+57h+hKey], r15
0x180007932  movups  xmmword ptr [rbp+57h+pbData], xmm0
0x180007936  mov     [rbp+57h+var_28], rax
0x18000793a  movups  [rbp+57h+var_38], xmm0
0x18000793e  movups  xmmword ptr [rbp+57h+Source], xmm0
0x180007942  movups  xmmword ptr [rbp+57h+var_58.cbData], xmm1
0x180007946  cmp     [rcx+8], r15
0x18000794a  jnz     short loc_180007987
0x18000794c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007953  mov     r8d, 80070057h
0x180007959  mov     ebx, r8d
0x18000795c  jz      loc_180007E8C
0x180007962  lea     rax, aCprBlobtohashP; "CPR(blobToHash.pbData)"
0x180007969  mov     [rsp+0B0h+var_88], rax
0x18000796e  mov     dword ptr [rsp+0B0h+phKey], 194h
0x180007976  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000797d  call    McTemplateU0dsqs_EventWriteTransfer
0x180007982  jmp     loc_180007E8C
0x180007987  cmp     [rcx], r15d
0x18000798a  ja      short loc_1800079B8
0x18000798c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007993  mov     r8d, 80070057h
0x180007999  mov     ebx, r8d
0x18000799c  jz      loc_180007E8C
0x1800079a2  lea     rax, aCbrBlobtohashC; "CBR(blobToHash.cbData > 0)"
0x1800079a9  mov     [rsp+0B0h+var_88], rax
0x1800079ae  mov     dword ptr [rsp+0B0h+phKey], 195h
0x1800079b6  jmp     short loc_180007976
0x1800079b8  test    rdi, rdi
0x1800079bb  jnz     short loc_1800079F8
0x1800079bd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x1800079c4  mov     r8d, 80070057h
0x1800079ca  mov     ebx, r8d
0x1800079cd  jz      loc_180007F13
0x1800079d3  lea     rax, aCprPblobhmacha_0; "CPR(pblobHMACHash)"
0x1800079da  mov     [rsp+0B0h+var_88], rax
0x1800079df  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800079e6  mov     dword ptr [rsp+0B0h+phKey], 196h
0x1800079ee  call    McTemplateU0dsqs_EventWriteTransfer
0x1800079f3  jmp     loc_180007EF5
0x1800079f8  lea     rcx, [rbp+57h+hProv]; unsigned __int64 *
0x1800079fc  call    ?GetProvider@MdmCrypto@@CAJPEA_K@Z; MdmCrypto::GetProvider(unsigned __int64 *)
0x180007a01  mov     ebx, eax
0x180007a03  test    eax, eax
0x180007a05  jns     short loc_180007A30
0x180007a07  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007a0e  jz      loc_180007EE0
0x180007a14  lea     rax, aChrGetprovider; "CHR(GetProvider(&hProv))"
0x180007a1b  mov     [rsp+0B0h+var_88], rax
0x180007a20  mov     dword ptr [rsp+0B0h+phKey], 199h
0x180007a28  mov     r8d, ebx
0x180007a2b  jmp     loc_180007ED4
0x180007a30  mov     rcx, [rbp+57h+hProv]; unsigned __int64
0x180007a34  lea     r8, [rbp+57h+hBaseData]; unsigned __int64 *
0x180007a38  call    ?CreateHash@MdmCrypto@@CAJ_KIPEA_K@Z; MdmCrypto::CreateHash(unsigned __int64,uint,unsigned __int64 *)
0x180007a3d  mov     ebx, eax
0x180007a3f  test    eax, eax
0x180007a41  jns     short loc_180007A66
0x180007a43  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007a4a  jz      loc_180007EE0
0x180007a50  lea     rax, aChrCreatehashH; "CHR(CreateHash(hProv, ((4 << 13) | (0) "...
0x180007a57  mov     [rsp+0B0h+var_88], rax
0x180007a5c  mov     dword ptr [rsp+0B0h+phKey], 19Ch
0x180007a64  jmp     short loc_180007A28
0x180007a66  lea     rdx, [rbp+57h+Source]; struct _CRYPTOAPI_BLOB *
0x180007a6a  mov     rcx, r14; struct _CRYPTOAPI_BLOB *
0x180007a6d  call    ?UnprotectData@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@PEAU2@@Z; MdmCrypto::UnprotectData(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)
0x180007a72  mov     ebx, eax
0x180007a74  test    eax, eax
0x180007a76  jns     short loc_180007A9B
0x180007a78  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007a7f  jz      loc_180007EE0
0x180007a85  lea     rax, aChrUnprotectda; "CHR(UnprotectData(blobSharedSecret, &bl"...
0x180007a8c  mov     [rsp+0B0h+var_88], rax
0x180007a91  mov     dword ptr [rsp+0B0h+phKey], 19Fh
0x180007a99  jmp     short loc_180007A28
0x180007a9b  cmp     dword ptr [rbp+57h+Source], r15d
0x180007a9f  ja      short loc_180007AD0
0x180007aa1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007aa8  mov     r8d, 8000FFFFh
0x180007aae  mov     ebx, r8d
0x180007ab1  jz      loc_180007EE0
0x180007ab7  lea     rax, aCbrBlobunprote; "CBR(blobUnprotectedSecret.cbData > 0)"
0x180007abe  mov     [rsp+0B0h+var_88], rax
0x180007ac3  mov     dword ptr [rsp+0B0h+phKey], 1A2h
0x180007acb  jmp     loc_180007ED4
0x180007ad0  mov     ecx, dword ptr [rbp+57h+Source]
0x180007ad3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007ada  add     ecx, 4; unsigned __int64
0x180007add  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007ae2  mov     [rbp+57h+var_58.pbData], rax
0x180007ae6  mov     rcx, rax; void *
0x180007ae9  test    rax, rax
0x180007aec  jnz     short loc_180007B1D
0x180007aee  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007af5  mov     r8d, 8007000Eh
0x180007afb  mov     ebx, r8d
0x180007afe  jz      loc_180007EE0
0x180007b04  lea     rax, aCprBlobprefixe; "CPR(blobPrefixedSecret.pbData)"
0x180007b0b  mov     [rsp+0B0h+var_88], rax
0x180007b10  mov     dword ptr [rsp+0B0h+phKey], 1A6h
0x180007b18  jmp     loc_180007ED4
0x180007b1d  mov     r8d, dword ptr [rbp+57h+Source]
0x180007b21  xor     edx, edx; Val
0x180007b23  add     r8d, 4; Size
0x180007b27  call    memset_0
0x180007b2c  mov     eax, dword ptr [rbp+57h+Source]
0x180007b2f  mov     rcx, [rbp+57h+var_58.pbData]; void *
0x180007b33  add     eax, 4
0x180007b36  mov     [rbp+57h+var_58.cbData], eax
0x180007b39  test    rcx, rcx
0x180007b3c  jnz     short loc_180007B4F
0x180007b3e  call    cs:__imp__o__errno
0x180007b44  mov     dword ptr [rax], 16h
0x180007b4a  jmp     loc_180007EA9
0x180007b4f  cmp     eax, 4
0x180007b52  jb      loc_180007E93
0x180007b58  mov     dword ptr [rcx], 48534148h
0x180007b5e  mov     edx, dword ptr [rbp+57h+Source]; DestinationSize
0x180007b61  mov     rcx, [rbp+57h+var_58.pbData]
0x180007b65  mov     r9d, edx; SourceSize
0x180007b68  mov     r8, [rbp+57h+Source+8]; Source
0x180007b6c  add     rcx, 4; Destination
0x180007b70  call    memcpy_s
0x180007b75  test    eax, eax
0x180007b77  jz      short loc_180007BA8
0x180007b79  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007b80  mov     r8d, 80004005h
0x180007b86  mov     ebx, r8d
0x180007b89  jz      loc_180007EE0
0x180007b8f  lea     rax, aCbrMemcpySBlob_3; "CBR(memcpy_s(blobPrefixedSecret.pbData "...
0x180007b96  mov     [rsp+0B0h+var_88], rax
0x180007b9b  mov     dword ptr [rsp+0B0h+phKey], 1B2h
0x180007ba3  jmp     loc_180007ED4
0x180007ba8  mov     rcx, [rbp+57h+hBaseData]; hHash
0x180007bac  lea     r8, [rbp+57h+arg_0]; int *
0x180007bb0  lea     rdx, [rbp+57h+var_58]; struct _CRYPTOAPI_BLOB *
0x180007bb4  mov     [rbp+57h+arg_0], r15d
0x180007bb8  call    ?HashData@MdmCrypto@@CAJ_KAEBU_CRYPTOAPI_BLOB@@AEBH@Z; MdmCrypto::HashData(unsigned __int64,_CRYPTOAPI_BLOB const &,int const &)
0x180007bbd  mov     ebx, eax
0x180007bbf  test    eax, eax
0x180007bc1  jns     short loc_180007BE9
0x180007bc3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007bca  jz      loc_180007EE0
0x180007bd0  lea     rax, aChrHashdataHha; "CHR(HashData(hHash, blobPrefixedSecret,"...
0x180007bd7  mov     [rsp+0B0h+var_88], rax
0x180007bdc  mov     dword ptr [rsp+0B0h+phKey], 1B5h
0x180007be4  jmp     loc_180007A28
0x180007be9  mov     r8, [rbp+57h+hBaseData]; hBaseData
0x180007bed  lea     rax, [rbp+57h+hKey]
0x180007bf1  mov     rcx, [rbp+57h+hProv]; hProv
0x180007bf5  mov     r9d, 800000h; dwFlags
0x180007bfb  mov     edx, 6801h; Algid
0x180007c00  mov     [rsp+0B0h+phKey], rax; phKey
0x180007c05  call    cs:__imp_CryptDeriveKey
0x180007c0b  test    eax, eax
0x180007c0d  jnz     short loc_180007C4A
0x180007c0f  call    cs:__imp_GetLastError
0x180007c15  mov     ebx, eax
0x180007c17  test    eax, eax
0x180007c19  jle     short loc_180007C24
0x180007c1b  movzx   ebx, ax
0x180007c1e  or      ebx, 80070000h
0x180007c24  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007c2b  jz      loc_180007E88
0x180007c31  lea     rax, aCbrCryptderive; "CBR(CryptDeriveKey(hProv, ((3 << 13)|(4"...
0x180007c38  mov     [rsp+0B0h+var_88], rax
0x180007c3d  mov     dword ptr [rsp+0B0h+phKey], 1B9h
0x180007c45  jmp     loc_180007E79
0x180007c4a  mov     r8, [rbp+57h+hKey]; hKey
0x180007c4e  lea     rax, [rbp+57h+phHash]
0x180007c52  mov     rcx, [rbp+57h+hProv]; hProv
0x180007c56  xor     r9d, r9d; dwFlags
0x180007c59  mov     edx, 8009h; Algid
0x180007c5e  mov     [rsp+0B0h+phKey], rax; phHash
0x180007c63  call    cs:__imp_CryptCreateHash
0x180007c69  test    eax, eax
0x180007c6b  jnz     short loc_180007CA8
0x180007c6d  call    cs:__imp_GetLastError
0x180007c73  mov     ebx, eax
0x180007c75  test    eax, eax
0x180007c77  jle     short loc_180007C82
0x180007c79  movzx   ebx, ax
0x180007c7c  or      ebx, 80070000h
0x180007c82  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007c89  jz      loc_180007E88
0x180007c8f  lea     rax, aCbrCryptcreate_0; "CBR(CryptCreateHash(hProv, ((4 << 13) |"...
0x180007c96  mov     [rsp+0B0h+var_88], rax
0x180007c9b  mov     dword ptr [rsp+0B0h+phKey], 1C1h
0x180007ca3  jmp     loc_180007E79
0x180007ca8  mov     rcx, [rbp+57h+phHash]; hHash
0x180007cac  lea     r8, [rbp+57h+pbData]; pbData
0x180007cb0  xor     r9d, r9d; dwFlags
0x180007cb3  mov     dword ptr [rbp+57h+pbData], 800Ch
0x180007cba  lea     edx, [r9+5]; dwParam
0x180007cbe  call    cs:__imp_CryptSetHashParam
0x180007cc4  test    eax, eax
0x180007cc6  jnz     short loc_180007D03
0x180007cc8  call    cs:__imp_GetLastError
0x180007cce  mov     ebx, eax
0x180007cd0  test    eax, eax
0x180007cd2  jle     short loc_180007CDD
0x180007cd4  movzx   ebx, ax
0x180007cd7  or      ebx, 80070000h
0x180007cdd  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007ce4  jz      loc_180007E88
0x180007cea  lea     rax, aCbrCryptsethas; "CBR(CryptSetHashParam(hHMACHash, 0x0005"...
0x180007cf1  mov     [rsp+0B0h+var_88], rax
0x180007cf6  mov     dword ptr [rsp+0B0h+phKey], 1C9h
0x180007cfe  jmp     loc_180007E79
0x180007d03  mov     rcx, [rbp+57h+phHash]; hHash
0x180007d07  lea     r8, [rbp+57h+arg_0]; int *
0x180007d0b  mov     rdx, rsi; struct _CRYPTOAPI_BLOB *
0x180007d0e  mov     [rbp+57h+arg_0], r15d
0x180007d12  call    ?HashData@MdmCrypto@@CAJ_KAEBU_CRYPTOAPI_BLOB@@AEBH@Z; MdmCrypto::HashData(unsigned __int64,_CRYPTOAPI_BLOB const &,int const &)
0x180007d17  mov     ebx, eax
0x180007d19  test    eax, eax
0x180007d1b  jns     short loc_180007D43
0x180007d1d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007d24  jz      loc_180007EE0
0x180007d2a  lea     rax, aChrHashdataHhm; "CHR(HashData(hHMACHash, blobToHash, 0))"
0x180007d31  mov     [rsp+0B0h+var_88], rax
0x180007d36  mov     dword ptr [rsp+0B0h+phKey], 1CCh
0x180007d3e  jmp     loc_180007A28
0x180007d43  mov     rcx, [rbp+57h+phHash]; hHash
0x180007d47  xor     r8d, r8d; pbData
0x180007d4a  mov     r9, rdi; pdwDataLen
0x180007d4d  mov     [rdi], r15d
0x180007d50  mov     dword ptr [rsp+0B0h+phKey], r15d; dwFlags
0x180007d55  lea     esi, [r8+2]
0x180007d59  mov     edx, esi; dwParam
0x180007d5b  call    cs:__imp_CryptGetHashParam
0x180007d61  test    eax, eax
0x180007d63  jnz     short loc_180007DA0
0x180007d65  call    cs:__imp_GetLastError
0x180007d6b  mov     ebx, eax
0x180007d6d  test    eax, eax
0x180007d6f  jle     short loc_180007D7A
0x180007d71  movzx   ebx, ax
0x180007d74  or      ebx, 80070000h
0x180007d7a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007d81  jz      loc_180007E88
0x180007d87  lea     rax, aCbrCryptgethas_2; "CBR(CryptGetHashParam(hHMACHash, 0x0002"...
0x180007d8e  mov     [rsp+0B0h+var_88], rax
0x180007d93  mov     dword ptr [rsp+0B0h+phKey], 1D5h
0x180007d9b  jmp     loc_180007E79
0x180007da0  cmp     [rdi], r15d
0x180007da3  ja      short loc_180007DD4
0x180007da5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007dac  mov     r8d, 8000FFFFh
0x180007db2  mov     ebx, r8d
0x180007db5  jz      loc_180007EE0
0x180007dbb  lea     rax, aCbrPblobhmacha; "CBR(pblobHMACHash->cbData > 0)"
0x180007dc2  mov     [rsp+0B0h+var_88], rax
0x180007dc7  mov     dword ptr [rsp+0B0h+phKey], 1D8h
0x180007dcf  jmp     loc_180007ED4
0x180007dd4  mov     ecx, [rdi]; unsigned __int64
0x180007dd6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007ddd  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007de2  mov     [rdi+8], rax
0x180007de6  test    rax, rax
0x180007de9  jnz     short loc_180007E1A
0x180007deb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007df2  mov     r8d, 8007000Eh
0x180007df8  mov     ebx, r8d
0x180007dfb  jz      loc_180007EE0
0x180007e01  lea     rax, aCprPblobhmacha; "CPR(pblobHMACHash->pbData)"
0x180007e08  mov     [rsp+0B0h+var_88], rax
0x180007e0d  mov     dword ptr [rsp+0B0h+phKey], 1DBh
0x180007e15  jmp     loc_180007ED4
0x180007e1a  mov     r8d, [rdi]; Size
0x180007e1d  xor     edx, edx; Val
0x180007e1f  mov     rcx, rax; void *
0x180007e22  call    memset_0
0x180007e27  mov     r8, [rdi+8]; pbData
0x180007e2b  mov     r9, rdi; pdwDataLen
0x180007e2e  mov     rcx, [rbp+57h+phHash]; hHash
0x180007e32  mov     edx, esi; dwParam
0x180007e34  mov     dword ptr [rsp+0B0h+phKey], r15d; dwFlags
0x180007e39  call    cs:__imp_CryptGetHashParam
  ... truncated ...
```
