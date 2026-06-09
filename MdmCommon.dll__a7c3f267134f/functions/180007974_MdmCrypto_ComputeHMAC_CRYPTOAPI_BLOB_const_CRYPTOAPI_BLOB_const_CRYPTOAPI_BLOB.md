# MdmCrypto::ComputeHMAC(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)

- ea: `0x180007974`
- end: `0x18000809b`
- name: `?ComputeHMAC@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@0PEAU2@@Z`
- size: `1831`
- prototype: `__int64 __fastcall(const struct _CRYPTOAPI_BLOB *, const struct _CRYPTOAPI_BLOB *, DWORD *pdwDataLen)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000685c`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x180001f6a`
- `0x180001fd4`
- `0x1800065c0`
- `0x180006698`
- `0x180007974`
- `0x1800080a4`
- `0x1800089b8`
- `0x180008a6c`
- `0x180008efc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007bc6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007f67`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007bc6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000803c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000803c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x180007fe3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x180007fe3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180007e0d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180007ef7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180007e0d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180007ef7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetHashParam` at `0x180007d64`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptSetHashParam` at `0x180007d64`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180007cfd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180007cfd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x180007c93`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDeriveKey` at `0x180007c93`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180008070`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180008070`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180007fce`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180008059`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180007fce`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180008059`

## string_xrefs

- `0x1800079fe`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180007a67`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180007f43`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180007fa4`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180007ad8`: `CHR(CreateHash(hProv, ((4 << 13) | (0) | 12), &hHash))`
- `0x180007d35`: `CBR(CryptCreateHash(hProv, ((4 << 13) | (0) | 9), hKey, 0, &hHMACHash))`

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
        "CPR(blobToHash.pbData)");
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
        "CBR(blobToHash.cbData > 0)");
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
      "CPR(pblobHMACHash)");
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
      v32);
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
        "CBR(blobUnprotectedSecret.cbData > 0)");
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
        "CPR(blobPrefixedSecret.pbData)");
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
        "CBR(memcpy_s(blobPrefixedSecret.pbData + c_cbCcpHmacPrefix, blobUnprotectedSecret.cbData, blobUnprotectedSecret."
        "pbData, blobUnprotectedSecret.cbData) == 0)");
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
                "CBR(pblobHMACHash->cbData > 0)");
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
                "CPR(pblobHMACHash->pbData)");
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
              "CBR(CryptGetHashParam(hHMACHash, 0x0002, pblobHMACHash->pbData, &pblobHMACHash->cbData, 0))");
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
              "CBR(CryptGetHashParam(hHMACHash, 0x0002, 0, &pblobHMACHash->cbData, 0))");
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
            "CBR(CryptSetHashParam(hHMACHash, 0x0005, (BYTE*)&hmacInfo, 0))");
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
          "CBR(CryptCreateHash(hProv, ((4 << 13) | (0) | 9), hKey, 0, &hHMACHash))");
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
        "CBR(CryptDeriveKey(hProv, ((3 << 13)|(4 << 9)|1), hHash, 0x00800000, &hKey))");
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
0x180007974  mov     [rsp-8+arg_8], rbx
0x180007979  mov     [rsp-8+arg_10], rsi
0x18000797e  push    rbp
0x18000797f  push    rdi
0x180007980  push    r12
0x180007982  push    r14
0x180007984  push    r15
0x180007986  lea     rbp, [rsp-37h]
0x18000798b  sub     rsp, 90h
0x180007992  xor     r15d, r15d
0x180007995  xorps   xmm0, xmm0
0x180007998  xor     eax, eax
0x18000799a  mov     [rbp+57h+hProv], r15
0x18000799e  xorps   xmm1, xmm1
0x1800079a1  mov     rdi, r8
0x1800079a4  mov     r14, rdx
0x1800079a7  mov     rsi, rcx
0x1800079aa  lea     r12d, [r15+1]
0x1800079ae  mov     [rbp+57h+hBaseData], r15
0x1800079b2  mov     [rbp+57h+phHash], r15
0x1800079b6  mov     [rbp+57h+hKey], r15
0x1800079ba  movups  xmmword ptr [rbp+57h+pbData], xmm0
0x1800079be  mov     [rbp+57h+var_28], rax
0x1800079c2  movups  [rbp+57h+var_38], xmm0
0x1800079c6  movups  xmmword ptr [rbp+57h+Source], xmm0
0x1800079ca  movups  xmmword ptr [rbp+57h+var_58.cbData], xmm1
0x1800079ce  cmp     [rcx+8], r15
0x1800079d2  jnz     short loc_180007A0F
0x1800079d4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x1800079db  mov     r8d, 80070057h
0x1800079e1  mov     ebx, r8d
0x1800079e4  jz      loc_180007F56
0x1800079ea  lea     rax, aCprBlobtohashP; "CPR(blobToHash.pbData)"
0x1800079f1  mov     [rsp+0B0h+var_88], rax
0x1800079f6  mov     dword ptr [rsp+0B0h+phKey], 194h
0x1800079fe  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180007a05  call    McTemplateU0dsqs_EventWriteTransfer
0x180007a0a  jmp     loc_180007F56
0x180007a0f  cmp     [rcx], r15d
0x180007a12  ja      short loc_180007A40
0x180007a14  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007a1b  mov     r8d, 80070057h
0x180007a21  mov     ebx, r8d
0x180007a24  jz      loc_180007F56
0x180007a2a  lea     rax, aCbrBlobtohashC; "CBR(blobToHash.cbData > 0)"
0x180007a31  mov     [rsp+0B0h+var_88], rax
0x180007a36  mov     dword ptr [rsp+0B0h+phKey], 195h
0x180007a3e  jmp     short loc_1800079FE
0x180007a40  test    rdi, rdi
0x180007a43  jnz     short loc_180007A80
0x180007a45  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007a4c  mov     r8d, 80070057h
0x180007a52  mov     ebx, r8d
0x180007a55  jz      loc_180007FEF
0x180007a5b  lea     rax, aCprPblobhmacha_0; "CPR(pblobHMACHash)"
0x180007a62  mov     [rsp+0B0h+var_88], rax
0x180007a67  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180007a6e  mov     dword ptr [rsp+0B0h+phKey], 196h
0x180007a76  call    McTemplateU0dsqs_EventWriteTransfer
0x180007a7b  jmp     loc_180007FC5
0x180007a80  lea     rcx, [rbp+57h+hProv]; unsigned __int64 *
0x180007a84  call    ?GetProvider@MdmCrypto@@CAJPEA_K@Z; MdmCrypto::GetProvider(unsigned __int64 *)
0x180007a89  mov     ebx, eax
0x180007a8b  test    eax, eax
0x180007a8d  jns     short loc_180007AB8
0x180007a8f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007a96  jz      loc_180007FB0
0x180007a9c  lea     rax, aChrGetprovider; "CHR(GetProvider(&hProv))"
0x180007aa3  mov     [rsp+0B0h+var_88], rax
0x180007aa8  mov     dword ptr [rsp+0B0h+phKey], 199h
0x180007ab0  mov     r8d, ebx
0x180007ab3  jmp     loc_180007FA4
0x180007ab8  mov     rcx, [rbp+57h+hProv]; unsigned __int64
0x180007abc  lea     r8, [rbp+57h+hBaseData]; unsigned __int64 *
0x180007ac0  call    ?CreateHash@MdmCrypto@@CAJ_KIPEA_K@Z; MdmCrypto::CreateHash(unsigned __int64,uint,unsigned __int64 *)
0x180007ac5  mov     ebx, eax
0x180007ac7  test    eax, eax
0x180007ac9  jns     short loc_180007AEE
0x180007acb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007ad2  jz      loc_180007FB0
0x180007ad8  lea     rax, aChrCreatehashH; "CHR(CreateHash(hProv, ((4 << 13) | (0) "...
0x180007adf  mov     [rsp+0B0h+var_88], rax
0x180007ae4  mov     dword ptr [rsp+0B0h+phKey], 19Ch
0x180007aec  jmp     short loc_180007AB0
0x180007aee  lea     rdx, [rbp+57h+Source]; struct _CRYPTOAPI_BLOB *
0x180007af2  mov     rcx, r14; struct _CRYPTOAPI_BLOB *
0x180007af5  call    ?UnprotectData@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@PEAU2@@Z; MdmCrypto::UnprotectData(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)
0x180007afa  mov     ebx, eax
0x180007afc  test    eax, eax
0x180007afe  jns     short loc_180007B23
0x180007b00  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007b07  jz      loc_180007FB0
0x180007b0d  lea     rax, aChrUnprotectda; "CHR(UnprotectData(blobSharedSecret, &bl"...
0x180007b14  mov     [rsp+0B0h+var_88], rax
0x180007b19  mov     dword ptr [rsp+0B0h+phKey], 19Fh
0x180007b21  jmp     short loc_180007AB0
0x180007b23  cmp     dword ptr [rbp+57h+Source], r15d
0x180007b27  ja      short loc_180007B58
0x180007b29  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007b30  mov     r8d, 8000FFFFh
0x180007b36  mov     ebx, r8d
0x180007b39  jz      loc_180007FB0
0x180007b3f  lea     rax, aCbrBlobunprote; "CBR(blobUnprotectedSecret.cbData > 0)"
0x180007b46  mov     [rsp+0B0h+var_88], rax
0x180007b4b  mov     dword ptr [rsp+0B0h+phKey], 1A2h
0x180007b53  jmp     loc_180007FA4
0x180007b58  mov     ecx, dword ptr [rbp+57h+Source]
0x180007b5b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007b62  add     ecx, 4; unsigned __int64
0x180007b65  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007b6a  mov     [rbp+57h+var_58.pbData], rax
0x180007b6e  mov     rcx, rax; void *
0x180007b71  test    rax, rax
0x180007b74  jnz     short loc_180007BA5
0x180007b76  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007b7d  mov     r8d, 8007000Eh
0x180007b83  mov     ebx, r8d
0x180007b86  jz      loc_180007FB0
0x180007b8c  lea     rax, aCprBlobprefixe; "CPR(blobPrefixedSecret.pbData)"
0x180007b93  mov     [rsp+0B0h+var_88], rax
0x180007b98  mov     dword ptr [rsp+0B0h+phKey], 1A6h
0x180007ba0  jmp     loc_180007FA4
0x180007ba5  mov     r8d, dword ptr [rbp+57h+Source]
0x180007ba9  xor     edx, edx; Val
0x180007bab  add     r8d, 4; Size
0x180007baf  call    memset_0
0x180007bb4  mov     eax, dword ptr [rbp+57h+Source]
0x180007bb7  mov     rcx, [rbp+57h+var_58.pbData]; void *
0x180007bbb  add     eax, 4
0x180007bbe  mov     [rbp+57h+var_58.cbData], eax
0x180007bc1  test    rcx, rcx
0x180007bc4  jnz     short loc_180007BDD
0x180007bc6  call    cs:__imp__o__errno
0x180007bcd  nop     dword ptr [rax+rax+00h]
0x180007bd2  mov     dword ptr [rax], 16h
0x180007bd8  jmp     loc_180007F79
0x180007bdd  cmp     eax, 4
0x180007be0  jb      loc_180007F5D
0x180007be6  mov     dword ptr [rcx], 48534148h
0x180007bec  mov     edx, dword ptr [rbp+57h+Source]; DestinationSize
0x180007bef  mov     rcx, [rbp+57h+var_58.pbData]
0x180007bf3  mov     r9d, edx; SourceSize
0x180007bf6  mov     r8, [rbp+57h+Source+8]; Source
0x180007bfa  add     rcx, 4; Destination
0x180007bfe  call    memcpy_s
0x180007c03  test    eax, eax
0x180007c05  jz      short loc_180007C36
0x180007c07  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007c0e  mov     r8d, 80004005h
0x180007c14  mov     ebx, r8d
0x180007c17  jz      loc_180007FB0
0x180007c1d  lea     rax, aCbrMemcpySBlob_3; "CBR(memcpy_s(blobPrefixedSecret.pbData "...
0x180007c24  mov     [rsp+0B0h+var_88], rax
0x180007c29  mov     dword ptr [rsp+0B0h+phKey], 1B2h
0x180007c31  jmp     loc_180007FA4
0x180007c36  mov     rcx, [rbp+57h+hBaseData]; hHash
0x180007c3a  lea     r8, [rbp+57h+arg_0]; int *
0x180007c3e  lea     rdx, [rbp+57h+var_58]; struct _CRYPTOAPI_BLOB *
0x180007c42  mov     [rbp+57h+arg_0], r15d
0x180007c46  call    ?HashData@MdmCrypto@@CAJ_KAEBU_CRYPTOAPI_BLOB@@AEBH@Z; MdmCrypto::HashData(unsigned __int64,_CRYPTOAPI_BLOB const &,int const &)
0x180007c4b  mov     ebx, eax
0x180007c4d  test    eax, eax
0x180007c4f  jns     short loc_180007C77
0x180007c51  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007c58  jz      loc_180007FB0
0x180007c5e  lea     rax, aChrHashdataHha; "CHR(HashData(hHash, blobPrefixedSecret,"...
0x180007c65  mov     [rsp+0B0h+var_88], rax
0x180007c6a  mov     dword ptr [rsp+0B0h+phKey], 1B5h
0x180007c72  jmp     loc_180007AB0
0x180007c77  mov     r8, [rbp+57h+hBaseData]; hBaseData
0x180007c7b  lea     rax, [rbp+57h+hKey]
0x180007c7f  mov     rcx, [rbp+57h+hProv]; hProv
0x180007c83  mov     r9d, 800000h; dwFlags
0x180007c89  mov     edx, 6801h; Algid
0x180007c8e  mov     [rsp+0B0h+phKey], rax; phKey
0x180007c93  call    cs:__imp_CryptDeriveKey
0x180007c9a  nop     dword ptr [rax+rax+00h]
0x180007c9f  test    eax, eax
0x180007ca1  jnz     short loc_180007CE4
0x180007ca3  call    cs:__imp_GetLastError
0x180007caa  nop     dword ptr [rax+rax+00h]
0x180007caf  mov     ebx, eax
0x180007cb1  test    eax, eax
0x180007cb3  jle     short loc_180007CBE
0x180007cb5  movzx   ebx, ax
0x180007cb8  or      ebx, 80070000h
0x180007cbe  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007cc5  jz      loc_180007F52
0x180007ccb  lea     rax, aCbrCryptderive; "CBR(CryptDeriveKey(hProv, ((3 << 13)|(4"...
0x180007cd2  mov     [rsp+0B0h+var_88], rax
0x180007cd7  mov     dword ptr [rsp+0B0h+phKey], 1B9h
0x180007cdf  jmp     loc_180007F43
0x180007ce4  mov     r8, [rbp+57h+hKey]; hKey
0x180007ce8  lea     rax, [rbp+57h+phHash]
0x180007cec  mov     rcx, [rbp+57h+hProv]; hProv
0x180007cf0  xor     r9d, r9d; dwFlags
0x180007cf3  mov     edx, 8009h; Algid
0x180007cf8  mov     [rsp+0B0h+phKey], rax; phHash
0x180007cfd  call    cs:__imp_CryptCreateHash
0x180007d04  nop     dword ptr [rax+rax+00h]
0x180007d09  test    eax, eax
0x180007d0b  jnz     short loc_180007D4E
0x180007d0d  call    cs:__imp_GetLastError
0x180007d14  nop     dword ptr [rax+rax+00h]
0x180007d19  mov     ebx, eax
0x180007d1b  test    eax, eax
0x180007d1d  jle     short loc_180007D28
0x180007d1f  movzx   ebx, ax
0x180007d22  or      ebx, 80070000h
0x180007d28  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007d2f  jz      loc_180007F52
0x180007d35  lea     rax, aCbrCryptcreate_0; "CBR(CryptCreateHash(hProv, ((4 << 13) |"...
0x180007d3c  mov     [rsp+0B0h+var_88], rax
0x180007d41  mov     dword ptr [rsp+0B0h+phKey], 1C1h
0x180007d49  jmp     loc_180007F43
0x180007d4e  mov     rcx, [rbp+57h+phHash]; hHash
0x180007d52  lea     r8, [rbp+57h+pbData]; pbData
0x180007d56  xor     r9d, r9d; dwFlags
0x180007d59  mov     dword ptr [rbp+57h+pbData], 800Ch
0x180007d60  lea     edx, [r9+5]; dwParam
0x180007d64  call    cs:__imp_CryptSetHashParam
0x180007d6b  nop     dword ptr [rax+rax+00h]
0x180007d70  test    eax, eax
0x180007d72  jnz     short loc_180007DB5
0x180007d74  call    cs:__imp_GetLastError
0x180007d7b  nop     dword ptr [rax+rax+00h]
0x180007d80  mov     ebx, eax
0x180007d82  test    eax, eax
0x180007d84  jle     short loc_180007D8F
0x180007d86  movzx   ebx, ax
0x180007d89  or      ebx, 80070000h
0x180007d8f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007d96  jz      loc_180007F52
0x180007d9c  lea     rax, aCbrCryptsethas; "CBR(CryptSetHashParam(hHMACHash, 0x0005"...
0x180007da3  mov     [rsp+0B0h+var_88], rax
0x180007da8  mov     dword ptr [rsp+0B0h+phKey], 1C9h
0x180007db0  jmp     loc_180007F43
0x180007db5  mov     rcx, [rbp+57h+phHash]; hHash
0x180007db9  lea     r8, [rbp+57h+arg_0]; int *
0x180007dbd  mov     rdx, rsi; struct _CRYPTOAPI_BLOB *
0x180007dc0  mov     [rbp+57h+arg_0], r15d
0x180007dc4  call    ?HashData@MdmCrypto@@CAJ_KAEBU_CRYPTOAPI_BLOB@@AEBH@Z; MdmCrypto::HashData(unsigned __int64,_CRYPTOAPI_BLOB const &,int const &)
0x180007dc9  mov     ebx, eax
0x180007dcb  test    eax, eax
0x180007dcd  jns     short loc_180007DF5
0x180007dcf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007dd6  jz      loc_180007FB0
0x180007ddc  lea     rax, aChrHashdataHhm; "CHR(HashData(hHMACHash, blobToHash, 0))"
0x180007de3  mov     [rsp+0B0h+var_88], rax
0x180007de8  mov     dword ptr [rsp+0B0h+phKey], 1CCh
0x180007df0  jmp     loc_180007AB0
0x180007df5  mov     rcx, [rbp+57h+phHash]; hHash
0x180007df9  xor     r8d, r8d; pbData
0x180007dfc  mov     r9, rdi; pdwDataLen
0x180007dff  mov     [rdi], r15d
0x180007e02  mov     dword ptr [rsp+0B0h+phKey], r15d; dwFlags
0x180007e07  lea     esi, [r8+2]
0x180007e0b  mov     edx, esi; dwParam
0x180007e0d  call    cs:__imp_CryptGetHashParam
0x180007e14  nop     dword ptr [rax+rax+00h]
0x180007e19  test    eax, eax
0x180007e1b  jnz     short loc_180007E5E
0x180007e1d  call    cs:__imp_GetLastError
0x180007e24  nop     dword ptr [rax+rax+00h]
0x180007e29  mov     ebx, eax
0x180007e2b  test    eax, eax
0x180007e2d  jle     short loc_180007E38
0x180007e2f  movzx   ebx, ax
0x180007e32  or      ebx, 80070000h
0x180007e38  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007e3f  jz      loc_180007F52
0x180007e45  lea     rax, aCbrCryptgethas_2; "CBR(CryptGetHashParam(hHMACHash, 0x0002"...
0x180007e4c  mov     [rsp+0B0h+var_88], rax
0x180007e51  mov     dword ptr [rsp+0B0h+phKey], 1D5h
0x180007e59  jmp     loc_180007F43
0x180007e5e  cmp     [rdi], r15d
0x180007e61  ja      short loc_180007E92
0x180007e63  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007e6a  mov     r8d, 8000FFFFh
0x180007e70  mov     ebx, r8d
0x180007e73  jz      loc_180007FB0
0x180007e79  lea     rax, aCbrPblobhmacha; "CBR(pblobHMACHash->cbData > 0)"
0x180007e80  mov     [rsp+0B0h+var_88], rax
0x180007e85  mov     dword ptr [rsp+0B0h+phKey], 1D8h
0x180007e8d  jmp     loc_180007FA4
0x180007e92  mov     ecx, [rdi]; unsigned __int64
0x180007e94  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007e9b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007ea0  mov     [rdi+8], rax
0x180007ea4  test    rax, rax
0x180007ea7  jnz     short loc_180007ED8
0x180007ea9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, r12b
0x180007eb0  mov     r8d, 8007000Eh
0x180007eb6  mov     ebx, r8d
0x180007eb9  jz      loc_180007FB0
0x180007ebf  lea     rax, aCprPblobhmacha; "CPR(pblobHMACHash->pbData)"
0x180007ec6  mov     [rsp+0B0h+var_88], rax
0x180007ecb  mov     dword ptr [rsp+0B0h+phKey], 1DBh
0x180007ed3  jmp     loc_180007FA4
0x180007ed8  mov     r8d, [rdi]; Size
  ... truncated ...
```
