# MdmCrypto::DecryptData(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)

- ea: `0x180008438`
- end: `0x1800088ff`
- name: `?DecryptData@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@0PEAU2@@Z`
- size: `1223`
- prototype: `__int64 __fastcall(const struct _CRYPTOAPI_BLOB *, const struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006b24`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x180001f6a`
- `0x180001fd4`
- `0x1800065c0`
- `0x180006698`
- `0x1800080a4`
- `0x180008154`
- `0x180008438`
- `0x180008908`
- `0x1800089b8`
- `0x180008a6c`
- `0x180008efc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800086b5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800087fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800086b5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800087fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088a8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18000884d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18000884d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800088dc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800088dc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800088c5`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x1800088c5`

## string_xrefs

- `0x180008838`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x1800085cf`: `CHR(CreateHash(hProv, ((4 << 13) | (0) | 12), &hHash))`

## pseudocode

```c
__int64 __fastcall MdmCrypto::DecryptData(
        const struct _CRYPTOAPI_BLOB *a1,
        const struct _CRYPTOAPI_BLOB *a2,
        struct _CRYPTOAPI_BLOB *a3)
{
  int Provider; // ebx
  int pbData; // ecx
  int v8; // r8d
  __int64 v9; // rdx
  __int64 v10; // r8
  BYTE *v11; // rcx
  unsigned int v12; // eax
  int v13; // ecx
  unsigned int v14; // r8d
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  BYTE *v18; // rax
  __int64 cbData; // rcx
  _BYTE *v20; // rcx
  __int64 v21; // rax
  char v23; // [rsp+20h] [rbp-40h]
  const char *v24; // [rsp+28h] [rbp-38h]
  HCRYPTPROV hProv; // [rsp+30h] [rbp-30h] BYREF
  HCRYPTKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  void *Source[2]; // [rsp+40h] [rbp-20h] BYREF
  struct _CRYPTOAPI_BLOB v28; // [rsp+50h] [rbp-10h] BYREF
  int v29; // [rsp+90h] [rbp+30h] BYREF
  HCRYPTHASH hHash; // [rsp+A8h] [rbp+48h] BYREF

  hProv = 0;
  hHash = 0;
  hKey = 0;
  *(_OWORD *)Source = 0;
  v28 = 0;
  if ( !a1->pbData )
  {
    Provider = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_53;
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
      176,
      "CPR(blobEncrypted.pbData)");
    goto LABEL_51;
  }
  if ( !a1->cbData )
  {
    Provider = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_53;
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
      177,
      "CBR(blobEncrypted.cbData > 0)");
    goto LABEL_51;
  }
  if ( !a2->pbData )
  {
    Provider = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_53;
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
      178,
      "CPR(blobSharedSecret.pbData)");
    goto LABEL_51;
  }
  if ( !a2->cbData )
  {
    Provider = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_53;
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
      179,
      "CBR(blobSharedSecret.cbData > 0)");
    goto LABEL_51;
  }
  if ( a3 )
  {
    Provider = MdmCrypto::GetProvider(&hProv);
    if ( Provider >= 0 )
    {
      Provider = MdmCrypto::CreateHash(hProv, (int)a2, &hHash);
      if ( Provider >= 0 )
      {
        Provider = MdmCrypto::UnprotectData(a2, (struct _CRYPTOAPI_BLOB *)Source);
        if ( Provider >= 0 )
        {
          if ( LODWORD(Source[0]) )
          {
            v28.pbData = (BYTE *)operator new[](
                                   (unsigned int)(LODWORD(Source[0]) + 7),
                                   (const struct std::nothrow_t *)&std::nothrow);
            pbData = (int)v28.pbData;
            if ( v28.pbData )
            {
              memset_0(v28.pbData, 0, (unsigned int)(LODWORD(Source[0]) + 7));
              v11 = v28.pbData;
              v12 = LODWORD(Source[0]) + 7;
              v28.cbData = LODWORD(Source[0]) + 7;
              if ( v28.pbData )
              {
                if ( v12 >= 7 )
                {
                  *(_DWORD *)v28.pbData = 1380142661;
                  *((_WORD *)v11 + 2) = 20569;
                  v11[6] = 84;
                  if ( memcpy_s(v28.pbData + 7, LODWORD(Source[0]), Source[1], LODWORD(Source[0])) )
                  {
                    Provider = -2147467259;
                    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                      McTemplateU0dsqs_EventWriteTransfer(
                        v13,
                        (_DWORD)a2,
                        -2147467259,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
                        208,
                        "CBR(memcpy_s(blobPrefixedSecret.pbData + c_cbCcpEncryptPrefix, blobUnprotectedSecret.cbData, blo"
                        "bUnprotectedSecret.pbData, blobUnprotectedSecret.cbData) == 0)");
                    goto LABEL_51;
                  }
                  v29 = 0;
                  Provider = MdmCrypto::HashData(hHash, &v28, &v29);
                  if ( Provider >= 0 )
                  {
                    Provider = MdmCrypto::DeriveKey(hProv, hHash, v14, &hKey);
                    if ( Provider >= 0 )
                    {
                      Provider = MdmCrypto::Decrypt(hKey, a1, a3);
                      if ( Provider >= 0 || (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                        goto LABEL_51;
                      v24 = "CHR(Decrypt(hKey, blobEncrypted, pblobDecrypted))";
                      v23 = -37;
                    }
                    else
                    {
                      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                        goto LABEL_51;
                      v24 = "CHR(DeriveKey(hProv, hHash, ((3 << 13)|(3 << 9)|15), &hKey))";
                      v23 = -42;
                    }
                  }
                  else
                  {
                    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                      goto LABEL_51;
                    v24 = "CHR(HashData(hHash, blobPrefixedSecret, 0))";
                    v23 = -45;
                  }
                  goto LABEL_19;
                }
                memset_0(v28.pbData, 0, v12);
                *(_DWORD *)_o__errno(v16, v15, v17) = 34;
              }
              else
              {
                *(_DWORD *)_o__errno(0, v9, v10) = 22;
              }
              invalid_parameter_noinfo();
              v8 = -2147467259;
              Provider = -2147467259;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                goto LABEL_51;
              v24 = "CBR(memcpy_s(blobPrefixedSecret.pbData, c_cbCcpEncryptPrefix + blobUnprotectedSecret.cbData, c_szCcp"
                    "EncryptPrefix, c_cbCcpEncryptPrefix) == 0)";
              v23 = -53;
              goto LABEL_50;
            }
            Provider = -2147024882;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
              goto LABEL_51;
            v24 = "CPR(blobPrefixedSecret.pbData)";
            v23 = -60;
          }
          else
          {
            Provider = -2147418113;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
              goto LABEL_51;
            v24 = "CBR(blobUnprotectedSecret.cbData > 0)";
            v23 = -64;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
            goto LABEL_51;
          v24 = "CHR(UnprotectData(blobSharedSecret, &blobUnprotectedSecret))";
          v23 = -67;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_51;
        v24 = "CHR(CreateHash(hProv, ((4 << 13) | (0) | 12), &hHash))";
        v23 = -70;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_51;
      v24 = "CHR(GetProvider(&hProv))";
      v23 = -73;
    }
LABEL_19:
    v8 = Provider;
LABEL_50:
    McTemplateU0dsqs_EventWriteTransfer(
      pbData,
      (_DWORD)a2,
      v8,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
      v23,
      v24);
    goto LABEL_51;
  }
  Provider = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
    goto LABEL_53;
  McTemplateU0dsqs_EventWriteTransfer(
    (_DWORD)a1,
    (_DWORD)a2,
    -2147024809,
    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
    180,
    "CPR(pblobDecrypted)");
LABEL_51:
  if ( hKey )
    CryptDestroyKey(hKey);
LABEL_53:
  v18 = v28.pbData;
  if ( v28.pbData )
  {
    cbData = v28.cbData;
    if ( v28.cbData )
    {
      do
      {
        *v18++ = 0;
        --cbData;
      }
      while ( cbData );
    }
    operator delete(v28.pbData, (unsigned __int64)a2);
    v28.pbData = 0;
    v28.cbData = 0;
  }
  v20 = Source[1];
  if ( Source[1] )
  {
    v21 = LODWORD(Source[0]);
    if ( LODWORD(Source[0]) )
    {
      do
      {
        *v20++ = 0;
        --v21;
      }
      while ( v21 );
      v20 = Source[1];
    }
    LocalFree(v20);
    Source[1] = 0;
    LODWORD(Source[0]) = 0;
  }
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( hProv )
    CryptReleaseContext(hProv, 0);
  return (unsigned int)Provider;
}

```

## disassembly

```asm
0x180008438  mov     [rsp-28h+arg_8], rbx
0x18000843d  push    rbp
0x18000843e  push    rsi
0x18000843f  push    rdi
0x180008440  push    r14
0x180008442  push    r15
0x180008444  mov     rbp, rsp
0x180008447  sub     rsp, 60h
0x18000844b  xor     r15d, r15d
0x18000844e  xorps   xmm0, xmm0
0x180008451  xorps   xmm1, xmm1
0x180008454  mov     r14, r8
0x180008457  mov     rdi, rdx
0x18000845a  mov     rsi, rcx
0x18000845d  mov     [rbp+hProv], r15
0x180008461  mov     [rbp+hHash], r15
0x180008465  mov     [rbp+hKey], r15
0x180008469  movups  xmmword ptr [rbp+Source], xmm0
0x18000846d  movups  xmmword ptr [rbp+var_10.cbData], xmm1
0x180008471  cmp     [rcx+8], r15
0x180008475  jnz     short loc_1800084A6
0x180008477  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000847e  mov     r8d, 80070057h
0x180008484  mov     ebx, r8d
0x180008487  jz      loc_180008859
0x18000848d  lea     rax, aCprBlobencrypt_0; "CPR(blobEncrypted.pbData)"
0x180008494  mov     [rsp+60h+var_38], rax
0x180008499  mov     dword ptr [rsp+60h+var_40], 0B0h
0x1800084a1  jmp     loc_180008838
0x1800084a6  cmp     [rcx], r15d
0x1800084a9  ja      short loc_1800084DA
0x1800084ab  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800084b2  mov     r8d, 80070057h
0x1800084b8  mov     ebx, r8d
0x1800084bb  jz      loc_180008859
0x1800084c1  lea     rax, aCbrBlobencrypt; "CBR(blobEncrypted.cbData > 0)"
0x1800084c8  mov     [rsp+60h+var_38], rax
0x1800084cd  mov     dword ptr [rsp+60h+var_40], 0B1h
0x1800084d5  jmp     loc_180008838
0x1800084da  cmp     [rdx+8], r15
0x1800084de  jnz     short loc_18000850F
0x1800084e0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800084e7  mov     r8d, 80070057h
0x1800084ed  mov     ebx, r8d
0x1800084f0  jz      loc_180008859
0x1800084f6  lea     rax, aCprBlobshareds; "CPR(blobSharedSecret.pbData)"
0x1800084fd  mov     [rsp+60h+var_38], rax
0x180008502  mov     dword ptr [rsp+60h+var_40], 0B2h
0x18000850a  jmp     loc_180008838
0x18000850f  cmp     [rdx], r15d
0x180008512  ja      short loc_180008543
0x180008514  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000851b  mov     r8d, 80070057h
0x180008521  mov     ebx, r8d
0x180008524  jz      loc_180008859
0x18000852a  lea     rax, aCbrBlobshareds; "CBR(blobSharedSecret.cbData > 0)"
0x180008531  mov     [rsp+60h+var_38], rax
0x180008536  mov     dword ptr [rsp+60h+var_40], 0B3h
0x18000853e  jmp     loc_180008838
0x180008543  test    r14, r14
0x180008546  jnz     short loc_180008577
0x180008548  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000854f  mov     r8d, 80070057h
0x180008555  mov     ebx, r8d
0x180008558  jz      loc_180008859
0x18000855e  lea     rax, aCprPblobdecryp_0; "CPR(pblobDecrypted)"
0x180008565  mov     [rsp+60h+var_38], rax
0x18000856a  mov     dword ptr [rsp+60h+var_40], 0B4h
0x180008572  jmp     loc_180008838
0x180008577  lea     rcx, [rbp+hProv]; unsigned __int64 *
0x18000857b  call    ?GetProvider@MdmCrypto@@CAJPEA_K@Z; MdmCrypto::GetProvider(unsigned __int64 *)
0x180008580  mov     ebx, eax
0x180008582  test    eax, eax
0x180008584  jns     short loc_1800085AF
0x180008586  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000858d  jz      loc_180008844
0x180008593  lea     rax, aChrGetprovider; "CHR(GetProvider(&hProv))"
0x18000859a  mov     [rsp+60h+var_38], rax
0x18000859f  mov     dword ptr [rsp+60h+var_40], 0B7h
0x1800085a7  mov     r8d, ebx
0x1800085aa  jmp     loc_180008838
0x1800085af  mov     rcx, [rbp+hProv]; unsigned __int64
0x1800085b3  lea     r8, [rbp+hHash]; unsigned __int64 *
0x1800085b7  call    ?CreateHash@MdmCrypto@@CAJ_KIPEA_K@Z; MdmCrypto::CreateHash(unsigned __int64,uint,unsigned __int64 *)
0x1800085bc  mov     ebx, eax
0x1800085be  test    eax, eax
0x1800085c0  jns     short loc_1800085E5
0x1800085c2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800085c9  jz      loc_180008844
0x1800085cf  lea     rax, aChrCreatehashH; "CHR(CreateHash(hProv, ((4 << 13) | (0) "...
0x1800085d6  mov     [rsp+60h+var_38], rax
0x1800085db  mov     dword ptr [rsp+60h+var_40], 0BAh
0x1800085e3  jmp     short loc_1800085A7
0x1800085e5  lea     rdx, [rbp+Source]; struct _CRYPTOAPI_BLOB *
0x1800085e9  mov     rcx, rdi; struct _CRYPTOAPI_BLOB *
0x1800085ec  call    ?UnprotectData@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@PEAU2@@Z; MdmCrypto::UnprotectData(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)
0x1800085f1  mov     ebx, eax
0x1800085f3  test    eax, eax
0x1800085f5  jns     short loc_18000861A
0x1800085f7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800085fe  jz      loc_180008844
0x180008604  lea     rax, aChrUnprotectda; "CHR(UnprotectData(blobSharedSecret, &bl"...
0x18000860b  mov     [rsp+60h+var_38], rax
0x180008610  mov     dword ptr [rsp+60h+var_40], 0BDh
0x180008618  jmp     short loc_1800085A7
0x18000861a  cmp     dword ptr [rbp+Source], r15d
0x18000861e  ja      short loc_18000864B
0x180008620  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008627  mov     ebx, 8000FFFFh
0x18000862c  jz      loc_180008844
0x180008632  lea     rax, aCbrBlobunprote; "CBR(blobUnprotectedSecret.cbData > 0)"
0x180008639  mov     [rsp+60h+var_38], rax
0x18000863e  mov     dword ptr [rsp+60h+var_40], 0C0h
0x180008646  jmp     loc_1800085A7
0x18000864b  mov     ecx, dword ptr [rbp+Source]
0x18000864e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008655  add     ecx, 7; unsigned __int64
0x180008658  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000865d  mov     [rbp+var_10.pbData], rax
0x180008661  mov     rcx, rax; void *
0x180008664  test    rax, rax
0x180008667  jnz     short loc_180008694
0x180008669  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008670  mov     ebx, 8007000Eh
0x180008675  jz      loc_180008844
0x18000867b  lea     rax, aCprBlobprefixe; "CPR(blobPrefixedSecret.pbData)"
0x180008682  mov     [rsp+60h+var_38], rax
0x180008687  mov     dword ptr [rsp+60h+var_40], 0C4h
0x18000868f  jmp     loc_1800085A7
0x180008694  mov     r8d, dword ptr [rbp+Source]
0x180008698  xor     edx, edx; Val
0x18000869a  add     r8d, 7; Size
0x18000869e  call    memset_0
0x1800086a3  mov     eax, dword ptr [rbp+Source]
0x1800086a6  mov     rcx, [rbp+var_10.pbData]; void *
0x1800086aa  add     eax, 7
0x1800086ad  mov     [rbp+var_10.cbData], eax
0x1800086b0  test    rcx, rcx
0x1800086b3  jnz     short loc_1800086CC
0x1800086b5  call    cs:__imp__o__errno
0x1800086bc  nop     dword ptr [rax+rax+00h]
0x1800086c1  mov     dword ptr [rax], 16h
0x1800086c7  jmp     loc_18000880D
0x1800086cc  cmp     eax, 7
0x1800086cf  jb      loc_1800087F1
0x1800086d5  mov     rax, cs:qword_180023D20
0x1800086dc  mov     [rcx], eax
0x1800086de  movzx   eax, word ptr cs:qword_180023D20+4
0x1800086e5  mov     [rcx+4], ax
0x1800086e9  mov     al, byte ptr cs:qword_180023D20+6
0x1800086ef  mov     [rcx+6], al
0x1800086f2  mov     edx, dword ptr [rbp+Source]; DestinationSize
0x1800086f5  mov     rcx, [rbp+var_10.pbData]
0x1800086f9  mov     r9d, edx; SourceSize
0x1800086fc  mov     r8, [rbp+Source+8]; Source
0x180008700  add     rcx, 7; Destination
0x180008704  call    memcpy_s
0x180008709  test    eax, eax
0x18000870b  jz      short loc_18000873C
0x18000870d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008714  mov     r8d, 80004005h
0x18000871a  mov     ebx, r8d
0x18000871d  jz      loc_180008844
0x180008723  lea     rax, aCbrMemcpySBlob_4; "CBR(memcpy_s(blobPrefixedSecret.pbData "...
0x18000872a  mov     [rsp+60h+var_38], rax
0x18000872f  mov     dword ptr [rsp+60h+var_40], 0D0h
0x180008737  jmp     loc_180008838
0x18000873c  mov     rcx, [rbp+hHash]; hHash
0x180008740  lea     r8, [rbp+arg_0]; int *
0x180008744  lea     rdx, [rbp+var_10]; struct _CRYPTOAPI_BLOB *
0x180008748  mov     [rbp+arg_0], r15d
0x18000874c  call    ?HashData@MdmCrypto@@CAJ_KAEBU_CRYPTOAPI_BLOB@@AEBH@Z; MdmCrypto::HashData(unsigned __int64,_CRYPTOAPI_BLOB const &,int const &)
0x180008751  mov     ebx, eax
0x180008753  test    eax, eax
0x180008755  jns     short loc_18000877D
0x180008757  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000875e  jz      loc_180008844
0x180008764  lea     rax, aChrHashdataHha; "CHR(HashData(hHash, blobPrefixedSecret,"...
0x18000876b  mov     [rsp+60h+var_38], rax
0x180008770  mov     dword ptr [rsp+60h+var_40], 0D3h
0x180008778  jmp     loc_1800085A7
0x18000877d  mov     rdx, [rbp+hHash]; unsigned __int64
0x180008781  lea     r9, [rbp+hKey]; unsigned __int64 *
0x180008785  mov     rcx, [rbp+hProv]; unsigned __int64
0x180008789  call    ?DeriveKey@MdmCrypto@@CAJ_K0IPEA_K@Z; MdmCrypto::DeriveKey(unsigned __int64,unsigned __int64,uint,unsigned __int64 *)
0x18000878e  mov     ebx, eax
0x180008790  test    eax, eax
0x180008792  jns     short loc_1800087BA
0x180008794  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000879b  jz      loc_180008844
0x1800087a1  lea     rax, aChrDerivekeyHp; "CHR(DeriveKey(hProv, hHash, ((3 << 13)|"...
0x1800087a8  mov     [rsp+60h+var_38], rax
0x1800087ad  mov     dword ptr [rsp+60h+var_40], 0D6h
0x1800087b5  jmp     loc_1800085A7
0x1800087ba  mov     rcx, [rbp+hKey]; hKey
0x1800087be  mov     r8, r14; struct _CRYPTOAPI_BLOB *
0x1800087c1  mov     rdx, rsi; struct _CRYPTOAPI_BLOB *
0x1800087c4  call    ?Decrypt@MdmCrypto@@CAJ_KAEBU_CRYPTOAPI_BLOB@@PEAU2@@Z; MdmCrypto::Decrypt(unsigned __int64,_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)
0x1800087c9  mov     ebx, eax
0x1800087cb  test    eax, eax
0x1800087cd  jns     short loc_180008844
0x1800087cf  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800087d6  jz      short loc_180008844
0x1800087d8  lea     rax, aChrDecryptHkey; "CHR(Decrypt(hKey, blobEncrypted, pblobD"...
0x1800087df  mov     [rsp+60h+var_38], rax
0x1800087e4  mov     dword ptr [rsp+60h+var_40], 0DBh
0x1800087ec  jmp     loc_1800085A7
0x1800087f1  mov     r8d, eax; Size
0x1800087f4  xor     edx, edx; Val
0x1800087f6  call    memset_0
0x1800087fb  call    cs:__imp__o__errno
0x180008802  nop     dword ptr [rax+rax+00h]
0x180008807  mov     dword ptr [rax], 22h ; '"'
0x18000880d  call    _invalid_parameter_noinfo
0x180008812  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008819  mov     r8d, 80004005h
0x18000881f  mov     ebx, r8d
0x180008822  jz      short loc_180008844
0x180008824  lea     rax, aCbrMemcpySBlob_2; "CBR(memcpy_s(blobPrefixedSecret.pbData,"...
0x18000882b  mov     [rsp+60h+var_38], rax
0x180008830  mov     dword ptr [rsp+60h+var_40], 0CBh
0x180008838  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18000883f  call    McTemplateU0dsqs_EventWriteTransfer
0x180008844  mov     rcx, [rbp+hKey]; hKey
0x180008848  test    rcx, rcx
0x18000884b  jz      short loc_180008859
0x18000884d  call    cs:__imp_CryptDestroyKey
0x180008854  nop     dword ptr [rax+rax+00h]
0x180008859  mov     rax, [rbp+var_10.pbData]
0x18000885d  test    rax, rax
0x180008860  jz      short loc_180008887
0x180008862  mov     ecx, [rbp+var_10.cbData]
0x180008865  test    rcx, rcx
0x180008868  jz      short loc_180008876
0x18000886a  mov     [rax], r15b
0x18000886d  inc     rax
0x180008870  sub     rcx, 1
0x180008874  jnz     short loc_18000886A
0x180008876  mov     rcx, [rbp+var_10.pbData]; void *
0x18000887a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000887f  mov     [rbp+var_10.pbData], r15
0x180008883  mov     [rbp+var_10.cbData], r15d
0x180008887  mov     rcx, [rbp+Source+8]
0x18000888b  test    rcx, rcx
0x18000888e  jz      short loc_1800088BC
0x180008890  mov     eax, dword ptr [rbp+Source]
0x180008893  test    rax, rax
0x180008896  jz      short loc_1800088A8
0x180008898  mov     [rcx], r15b
0x18000889b  inc     rcx
0x18000889e  sub     rax, 1
0x1800088a2  jnz     short loc_180008898
0x1800088a4  mov     rcx, [rbp+Source+8]; hMem
0x1800088a8  call    cs:__imp_LocalFree
0x1800088af  nop     dword ptr [rax+rax+00h]
0x1800088b4  mov     [rbp+Source+8], r15
0x1800088b8  mov     dword ptr [rbp+Source], r15d
0x1800088bc  mov     rcx, [rbp+hHash]; hHash
0x1800088c0  test    rcx, rcx
0x1800088c3  jz      short loc_1800088D1
0x1800088c5  call    cs:__imp_CryptDestroyHash
0x1800088cc  nop     dword ptr [rax+rax+00h]
0x1800088d1  mov     rcx, [rbp+hProv]; hProv
0x1800088d5  test    rcx, rcx
0x1800088d8  jz      short loc_1800088E8
0x1800088da  xor     edx, edx; dwFlags
0x1800088dc  call    cs:__imp_CryptReleaseContext
0x1800088e3  nop     dword ptr [rax+rax+00h]
0x1800088e8  mov     eax, ebx
0x1800088ea  mov     rbx, [rsp+60h+arg_8]
0x1800088f2  add     rsp, 60h
0x1800088f6  pop     r15
0x1800088f8  pop     r14
0x1800088fa  pop     rdi
0x1800088fb  pop     rsi
0x1800088fc  pop     rbp
0x1800088fd  retn
```
