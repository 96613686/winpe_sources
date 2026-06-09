# MdmCrypto::DecryptData(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)

- ea: `0x180008328`
- end: `0x1800087ca`
- name: `?DecryptData@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@0PEAU2@@Z`
- size: `1186`
- prototype: `__int64 __fastcall(const struct _CRYPTOAPI_BLOB *, const struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006aa0`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x180001f6a`
- `0x180001fd4`
- `0x180006548`
- `0x180006620`
- `0x180007fb4`
- `0x180008050`
- `0x180008328`
- `0x1800087d0`
- `0x18000886c`
- `0x180008910`
- `0x180008d58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800085a5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800086e5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800085a5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800086e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008786`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008786`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x180008731`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x180008731`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800087ae`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x1800087ae`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18000879d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18000879d`

## string_xrefs

- `0x18000871c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x1800084bf`: `CHR(CreateHash(hProv, ((4 << 13) | (0) | 12), &hHash))`

## pseudocode

```c
__int64 __fastcall MdmCrypto::DecryptData(
        const struct _CRYPTOAPI_BLOB *a1,
        const struct _CRYPTOAPI_BLOB *a2,
        struct _CRYPTOAPI_BLOB *a3)
{
  int Provider; // ebx
  int v7; // edx
  int pbData; // ecx
  int v9; // r8d
  BYTE *v10; // rcx
  unsigned int v11; // eax
  int v12; // edx
  int v13; // ecx
  unsigned int v14; // r8d
  BYTE *v15; // rax
  __int64 cbData; // rcx
  _BYTE *v17; // rcx
  __int64 v18; // rax
  char v20; // [rsp+20h] [rbp-40h]
  const char *v21; // [rsp+28h] [rbp-38h]
  HCRYPTPROV hProv; // [rsp+30h] [rbp-30h] BYREF
  HCRYPTKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  void *Source[2]; // [rsp+40h] [rbp-20h] BYREF
  struct _CRYPTOAPI_BLOB v25; // [rsp+50h] [rbp-10h] BYREF
  int v26; // [rsp+90h] [rbp+30h] BYREF
  HCRYPTHASH hHash; // [rsp+A8h] [rbp+48h] BYREF

  hProv = 0;
  hHash = 0;
  hKey = 0;
  *(_OWORD *)Source = 0;
  v25 = 0;
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
      Provider = MdmCrypto::CreateHash(hProv, v7, &hHash);
      if ( Provider >= 0 )
      {
        Provider = MdmCrypto::UnprotectData(a2, (struct _CRYPTOAPI_BLOB *)Source);
        if ( Provider >= 0 )
        {
          if ( LODWORD(Source[0]) )
          {
            v25.pbData = (BYTE *)operator new[](
                                   (unsigned int)(LODWORD(Source[0]) + 7),
                                   (const struct std::nothrow_t *)&std::nothrow);
            pbData = (int)v25.pbData;
            if ( v25.pbData )
            {
              memset_0(v25.pbData, 0, (unsigned int)(LODWORD(Source[0]) + 7));
              v10 = v25.pbData;
              v11 = LODWORD(Source[0]) + 7;
              v25.cbData = LODWORD(Source[0]) + 7;
              if ( v25.pbData )
              {
                if ( v11 >= 7 )
                {
                  *(_DWORD *)v25.pbData = 1380142661;
                  *((_WORD *)v10 + 2) = 20569;
                  v10[6] = 84;
                  if ( memcpy_s(v25.pbData + 7, LODWORD(Source[0]), Source[1], LODWORD(Source[0])) )
                  {
                    Provider = -2147467259;
                    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                      McTemplateU0dsqs_EventWriteTransfer(
                        v13,
                        v12,
                        -2147467259,
                        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
                        208,
                        "CBR(memcpy_s(blobPrefixedSecret.pbData + c_cbCcpEncryptPrefix, blobUnprotectedSecret.cbData, blo"
                        "bUnprotectedSecret.pbData, blobUnprotectedSecret.cbData) == 0)");
                    goto LABEL_51;
                  }
                  v26 = 0;
                  Provider = MdmCrypto::HashData(hHash, &v25, &v26);
                  if ( Provider >= 0 )
                  {
                    Provider = MdmCrypto::DeriveKey(hProv, hHash, v14, &hKey);
                    if ( Provider >= 0 )
                    {
                      Provider = MdmCrypto::Decrypt(hKey, a1, a3);
                      if ( Provider >= 0 || (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                        goto LABEL_51;
                      v21 = "CHR(Decrypt(hKey, blobEncrypted, pblobDecrypted))";
                      v20 = -37;
                    }
                    else
                    {
                      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                        goto LABEL_51;
                      v21 = "CHR(DeriveKey(hProv, hHash, ((3 << 13)|(3 << 9)|15), &hKey))";
                      v20 = -42;
                    }
                  }
                  else
                  {
                    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                      goto LABEL_51;
                    v21 = "CHR(HashData(hHash, blobPrefixedSecret, 0))";
                    v20 = -45;
                  }
                  goto LABEL_19;
                }
                memset_0(v25.pbData, 0, v11);
                *(_DWORD *)_o__errno() = 34;
              }
              else
              {
                *(_DWORD *)_o__errno() = 22;
              }
              invalid_parameter_noinfo();
              v9 = -2147467259;
              Provider = -2147467259;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
                goto LABEL_51;
              v21 = "CBR(memcpy_s(blobPrefixedSecret.pbData, c_cbCcpEncryptPrefix + blobUnprotectedSecret.cbData, c_szCcp"
                    "EncryptPrefix, c_cbCcpEncryptPrefix) == 0)";
              v20 = -53;
              goto LABEL_50;
            }
            Provider = -2147024882;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
              goto LABEL_51;
            v21 = "CPR(blobPrefixedSecret.pbData)";
            v20 = -60;
          }
          else
          {
            Provider = -2147418113;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
              goto LABEL_51;
            v21 = "CBR(blobUnprotectedSecret.cbData > 0)";
            v20 = -64;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
            goto LABEL_51;
          v21 = "CHR(UnprotectData(blobSharedSecret, &blobUnprotectedSecret))";
          v20 = -67;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_51;
        v21 = "CHR(CreateHash(hProv, ((4 << 13) | (0) | 12), &hHash))";
        v20 = -70;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_51;
      v21 = "CHR(GetProvider(&hProv))";
      v20 = -73;
    }
LABEL_19:
    v9 = Provider;
LABEL_50:
    McTemplateU0dsqs_EventWriteTransfer(
      pbData,
      v7,
      v9,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
      v20,
      v21);
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
  v15 = v25.pbData;
  if ( v25.pbData )
  {
    cbData = v25.cbData;
    if ( v25.cbData )
    {
      do
      {
        *v15++ = 0;
        --cbData;
      }
      while ( cbData );
    }
    operator delete(v25.pbData);
    v25.pbData = 0;
    v25.cbData = 0;
  }
  v17 = Source[1];
  if ( Source[1] )
  {
    v18 = LODWORD(Source[0]);
    if ( LODWORD(Source[0]) )
    {
      do
      {
        *v17++ = 0;
        --v18;
      }
      while ( v18 );
      v17 = Source[1];
    }
    LocalFree(v17);
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
0x180008328  mov     [rsp-28h+arg_8], rbx
0x18000832d  push    rbp
0x18000832e  push    rsi
0x18000832f  push    rdi
0x180008330  push    r14
0x180008332  push    r15
0x180008334  mov     rbp, rsp
0x180008337  sub     rsp, 60h
0x18000833b  xor     r15d, r15d
0x18000833e  xorps   xmm0, xmm0
0x180008341  xorps   xmm1, xmm1
0x180008344  mov     r14, r8
0x180008347  mov     rdi, rdx
0x18000834a  mov     rsi, rcx
0x18000834d  mov     [rbp+hProv], r15
0x180008351  mov     [rbp+hHash], r15
0x180008355  mov     [rbp+hKey], r15
0x180008359  movups  xmmword ptr [rbp+Source], xmm0
0x18000835d  movups  xmmword ptr [rbp+var_10.cbData], xmm1
0x180008361  cmp     [rcx+8], r15
0x180008365  jnz     short loc_180008396
0x180008367  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000836e  mov     r8d, 80070057h
0x180008374  mov     ebx, r8d
0x180008377  jz      loc_180008737
0x18000837d  lea     rax, aCprBlobencrypt_0; "CPR(blobEncrypted.pbData)"
0x180008384  mov     [rsp+60h+var_38], rax
0x180008389  mov     dword ptr [rsp+60h+var_40], 0B0h
0x180008391  jmp     loc_18000871C
0x180008396  cmp     [rcx], r15d
0x180008399  ja      short loc_1800083CA
0x18000839b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800083a2  mov     r8d, 80070057h
0x1800083a8  mov     ebx, r8d
0x1800083ab  jz      loc_180008737
0x1800083b1  lea     rax, aCbrBlobencrypt; "CBR(blobEncrypted.cbData > 0)"
0x1800083b8  mov     [rsp+60h+var_38], rax
0x1800083bd  mov     dword ptr [rsp+60h+var_40], 0B1h
0x1800083c5  jmp     loc_18000871C
0x1800083ca  cmp     [rdx+8], r15
0x1800083ce  jnz     short loc_1800083FF
0x1800083d0  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800083d7  mov     r8d, 80070057h
0x1800083dd  mov     ebx, r8d
0x1800083e0  jz      loc_180008737
0x1800083e6  lea     rax, aCprBlobshareds; "CPR(blobSharedSecret.pbData)"
0x1800083ed  mov     [rsp+60h+var_38], rax
0x1800083f2  mov     dword ptr [rsp+60h+var_40], 0B2h
0x1800083fa  jmp     loc_18000871C
0x1800083ff  cmp     [rdx], r15d
0x180008402  ja      short loc_180008433
0x180008404  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000840b  mov     r8d, 80070057h
0x180008411  mov     ebx, r8d
0x180008414  jz      loc_180008737
0x18000841a  lea     rax, aCbrBlobshareds; "CBR(blobSharedSecret.cbData > 0)"
0x180008421  mov     [rsp+60h+var_38], rax
0x180008426  mov     dword ptr [rsp+60h+var_40], 0B3h
0x18000842e  jmp     loc_18000871C
0x180008433  test    r14, r14
0x180008436  jnz     short loc_180008467
0x180008438  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000843f  mov     r8d, 80070057h
0x180008445  mov     ebx, r8d
0x180008448  jz      loc_180008737
0x18000844e  lea     rax, aCprPblobdecryp_0; "CPR(pblobDecrypted)"
0x180008455  mov     [rsp+60h+var_38], rax
0x18000845a  mov     dword ptr [rsp+60h+var_40], 0B4h
0x180008462  jmp     loc_18000871C
0x180008467  lea     rcx, [rbp+hProv]; unsigned __int64 *
0x18000846b  call    ?GetProvider@MdmCrypto@@CAJPEA_K@Z; MdmCrypto::GetProvider(unsigned __int64 *)
0x180008470  mov     ebx, eax
0x180008472  test    eax, eax
0x180008474  jns     short loc_18000849F
0x180008476  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18000847d  jz      loc_180008728
0x180008483  lea     rax, aChrGetprovider; "CHR(GetProvider(&hProv))"
0x18000848a  mov     [rsp+60h+var_38], rax
0x18000848f  mov     dword ptr [rsp+60h+var_40], 0B7h
0x180008497  mov     r8d, ebx
0x18000849a  jmp     loc_18000871C
0x18000849f  mov     rcx, [rbp+hProv]; unsigned __int64
0x1800084a3  lea     r8, [rbp+hHash]; unsigned __int64 *
0x1800084a7  call    ?CreateHash@MdmCrypto@@CAJ_KIPEA_K@Z; MdmCrypto::CreateHash(unsigned __int64,uint,unsigned __int64 *)
0x1800084ac  mov     ebx, eax
0x1800084ae  test    eax, eax
0x1800084b0  jns     short loc_1800084D5
0x1800084b2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800084b9  jz      loc_180008728
0x1800084bf  lea     rax, aChrCreatehashH; "CHR(CreateHash(hProv, ((4 << 13) | (0) "...
0x1800084c6  mov     [rsp+60h+var_38], rax
0x1800084cb  mov     dword ptr [rsp+60h+var_40], 0BAh
0x1800084d3  jmp     short loc_180008497
0x1800084d5  lea     rdx, [rbp+Source]; struct _CRYPTOAPI_BLOB *
0x1800084d9  mov     rcx, rdi; struct _CRYPTOAPI_BLOB *
0x1800084dc  call    ?UnprotectData@MdmCrypto@@SAJAEBU_CRYPTOAPI_BLOB@@PEAU2@@Z; MdmCrypto::UnprotectData(_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)
0x1800084e1  mov     ebx, eax
0x1800084e3  test    eax, eax
0x1800084e5  jns     short loc_18000850A
0x1800084e7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800084ee  jz      loc_180008728
0x1800084f4  lea     rax, aChrUnprotectda; "CHR(UnprotectData(blobSharedSecret, &bl"...
0x1800084fb  mov     [rsp+60h+var_38], rax
0x180008500  mov     dword ptr [rsp+60h+var_40], 0BDh
0x180008508  jmp     short loc_180008497
0x18000850a  cmp     dword ptr [rbp+Source], r15d
0x18000850e  ja      short loc_18000853B
0x180008510  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008517  mov     ebx, 8000FFFFh
0x18000851c  jz      loc_180008728
0x180008522  lea     rax, aCbrBlobunprote; "CBR(blobUnprotectedSecret.cbData > 0)"
0x180008529  mov     [rsp+60h+var_38], rax
0x18000852e  mov     dword ptr [rsp+60h+var_40], 0C0h
0x180008536  jmp     loc_180008497
0x18000853b  mov     ecx, dword ptr [rbp+Source]
0x18000853e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008545  add     ecx, 7; unsigned __int64
0x180008548  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000854d  mov     [rbp+var_10.pbData], rax
0x180008551  mov     rcx, rax; void *
0x180008554  test    rax, rax
0x180008557  jnz     short loc_180008584
0x180008559  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008560  mov     ebx, 8007000Eh
0x180008565  jz      loc_180008728
0x18000856b  lea     rax, aCprBlobprefixe; "CPR(blobPrefixedSecret.pbData)"
0x180008572  mov     [rsp+60h+var_38], rax
0x180008577  mov     dword ptr [rsp+60h+var_40], 0C4h
0x18000857f  jmp     loc_180008497
0x180008584  mov     r8d, dword ptr [rbp+Source]
0x180008588  xor     edx, edx; Val
0x18000858a  add     r8d, 7; Size
0x18000858e  call    memset_0
0x180008593  mov     eax, dword ptr [rbp+Source]
0x180008596  mov     rcx, [rbp+var_10.pbData]; void *
0x18000859a  add     eax, 7
0x18000859d  mov     [rbp+var_10.cbData], eax
0x1800085a0  test    rcx, rcx
0x1800085a3  jnz     short loc_1800085B6
0x1800085a5  call    cs:__imp__o__errno
0x1800085ab  mov     dword ptr [rax], 16h
0x1800085b1  jmp     loc_1800086F1
0x1800085b6  cmp     eax, 7
0x1800085b9  jb      loc_1800086DB
0x1800085bf  mov     rax, cs:qword_180023D20
0x1800085c6  mov     [rcx], eax
0x1800085c8  movzx   eax, word ptr cs:qword_180023D20+4
0x1800085cf  mov     [rcx+4], ax
0x1800085d3  mov     al, byte ptr cs:qword_180023D20+6
0x1800085d9  mov     [rcx+6], al
0x1800085dc  mov     edx, dword ptr [rbp+Source]; DestinationSize
0x1800085df  mov     rcx, [rbp+var_10.pbData]
0x1800085e3  mov     r9d, edx; SourceSize
0x1800085e6  mov     r8, [rbp+Source+8]; Source
0x1800085ea  add     rcx, 7; Destination
0x1800085ee  call    memcpy_s
0x1800085f3  test    eax, eax
0x1800085f5  jz      short loc_180008626
0x1800085f7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800085fe  mov     r8d, 80004005h
0x180008604  mov     ebx, r8d
0x180008607  jz      loc_180008728
0x18000860d  lea     rax, aCbrMemcpySBlob_4; "CBR(memcpy_s(blobPrefixedSecret.pbData "...
0x180008614  mov     [rsp+60h+var_38], rax
0x180008619  mov     dword ptr [rsp+60h+var_40], 0D0h
0x180008621  jmp     loc_18000871C
0x180008626  mov     rcx, [rbp+hHash]; hHash
0x18000862a  lea     r8, [rbp+arg_0]; int *
0x18000862e  lea     rdx, [rbp+var_10]; struct _CRYPTOAPI_BLOB *
0x180008632  mov     [rbp+arg_0], r15d
0x180008636  call    ?HashData@MdmCrypto@@CAJ_KAEBU_CRYPTOAPI_BLOB@@AEBH@Z; MdmCrypto::HashData(unsigned __int64,_CRYPTOAPI_BLOB const &,int const &)
0x18000863b  mov     ebx, eax
0x18000863d  test    eax, eax
0x18000863f  jns     short loc_180008667
0x180008641  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008648  jz      loc_180008728
0x18000864e  lea     rax, aChrHashdataHha; "CHR(HashData(hHash, blobPrefixedSecret,"...
0x180008655  mov     [rsp+60h+var_38], rax
0x18000865a  mov     dword ptr [rsp+60h+var_40], 0D3h
0x180008662  jmp     loc_180008497
0x180008667  mov     rdx, [rbp+hHash]; unsigned __int64
0x18000866b  lea     r9, [rbp+hKey]; unsigned __int64 *
0x18000866f  mov     rcx, [rbp+hProv]; unsigned __int64
0x180008673  call    ?DeriveKey@MdmCrypto@@CAJ_K0IPEA_K@Z; MdmCrypto::DeriveKey(unsigned __int64,unsigned __int64,uint,unsigned __int64 *)
0x180008678  mov     ebx, eax
0x18000867a  test    eax, eax
0x18000867c  jns     short loc_1800086A4
0x18000867e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008685  jz      loc_180008728
0x18000868b  lea     rax, aChrDerivekeyHp; "CHR(DeriveKey(hProv, hHash, ((3 << 13)|"...
0x180008692  mov     [rsp+60h+var_38], rax
0x180008697  mov     dword ptr [rsp+60h+var_40], 0D6h
0x18000869f  jmp     loc_180008497
0x1800086a4  mov     rcx, [rbp+hKey]; hKey
0x1800086a8  mov     r8, r14; struct _CRYPTOAPI_BLOB *
0x1800086ab  mov     rdx, rsi; struct _CRYPTOAPI_BLOB *
0x1800086ae  call    ?Decrypt@MdmCrypto@@CAJ_KAEBU_CRYPTOAPI_BLOB@@PEAU2@@Z; MdmCrypto::Decrypt(unsigned __int64,_CRYPTOAPI_BLOB const &,_CRYPTOAPI_BLOB *)
0x1800086b3  mov     ebx, eax
0x1800086b5  test    eax, eax
0x1800086b7  jns     short loc_180008728
0x1800086b9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800086c0  jz      short loc_180008728
0x1800086c2  lea     rax, aChrDecryptHkey; "CHR(Decrypt(hKey, blobEncrypted, pblobD"...
0x1800086c9  mov     [rsp+60h+var_38], rax
0x1800086ce  mov     dword ptr [rsp+60h+var_40], 0DBh
0x1800086d6  jmp     loc_180008497
0x1800086db  mov     r8d, eax; Size
0x1800086de  xor     edx, edx; Val
0x1800086e0  call    memset_0
0x1800086e5  call    cs:__imp__o__errno
0x1800086eb  mov     dword ptr [rax], 22h ; '"'
0x1800086f1  call    _invalid_parameter_noinfo
0x1800086f6  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x1800086fd  mov     r8d, 80004005h
0x180008703  mov     ebx, r8d
0x180008706  jz      short loc_180008728
0x180008708  lea     rax, aCbrMemcpySBlob_2; "CBR(memcpy_s(blobPrefixedSecret.pbData,"...
0x18000870f  mov     [rsp+60h+var_38], rax
0x180008714  mov     dword ptr [rsp+60h+var_40], 0CBh
0x18000871c  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008723  call    McTemplateU0dsqs_EventWriteTransfer
0x180008728  mov     rcx, [rbp+hKey]; hKey
0x18000872c  test    rcx, rcx
0x18000872f  jz      short loc_180008737
0x180008731  call    cs:__imp_CryptDestroyKey
0x180008737  mov     rax, [rbp+var_10.pbData]
0x18000873b  test    rax, rax
0x18000873e  jz      short loc_180008765
0x180008740  mov     ecx, [rbp+var_10.cbData]
0x180008743  test    rcx, rcx
0x180008746  jz      short loc_180008754
0x180008748  mov     [rax], r15b
0x18000874b  inc     rax
0x18000874e  sub     rcx, 1
0x180008752  jnz     short loc_180008748
0x180008754  mov     rcx, [rbp+var_10.pbData]; void *
0x180008758  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000875d  mov     [rbp+var_10.pbData], r15
0x180008761  mov     [rbp+var_10.cbData], r15d
0x180008765  mov     rcx, [rbp+Source+8]
0x180008769  test    rcx, rcx
0x18000876c  jz      short loc_180008794
0x18000876e  mov     eax, dword ptr [rbp+Source]
0x180008771  test    rax, rax
0x180008774  jz      short loc_180008786
0x180008776  mov     [rcx], r15b
0x180008779  inc     rcx
0x18000877c  sub     rax, 1
0x180008780  jnz     short loc_180008776
0x180008782  mov     rcx, [rbp+Source+8]; hMem
0x180008786  call    cs:__imp_LocalFree
0x18000878c  mov     [rbp+Source+8], r15
0x180008790  mov     dword ptr [rbp+Source], r15d
0x180008794  mov     rcx, [rbp+hHash]; hHash
0x180008798  test    rcx, rcx
0x18000879b  jz      short loc_1800087A3
0x18000879d  call    cs:__imp_CryptDestroyHash
0x1800087a3  mov     rcx, [rbp+hProv]; hProv
0x1800087a7  test    rcx, rcx
0x1800087aa  jz      short loc_1800087B4
0x1800087ac  xor     edx, edx; dwFlags
0x1800087ae  call    cs:__imp_CryptReleaseContext
0x1800087b4  mov     eax, ebx
0x1800087b6  mov     rbx, [rsp+60h+arg_8]
0x1800087be  add     rsp, 60h
0x1800087c2  pop     r15
0x1800087c4  pop     r14
0x1800087c6  pop     rdi
0x1800087c7  pop     rsi
0x1800087c8  pop     rbp
0x1800087c9  retn
```
