# MdmCrypto::HashString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180008a6c`
- end: `0x180008d50`
- name: `?HashString@MdmCrypto@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `740`
- prototype: `__int64 __fastcall(BYTE *pbData, _QWORD *)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800030c0`
- `0x1800040c0`
- `0x180005070`
- `0x18000c38c`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x180001fd4`
- `0x180006548`
- `0x180007fb4`
- `0x18000886c`
- `0x180008a6c`
- `0x180019e74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c9c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180008bb6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180008c92`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180008bb6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180008c92`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180008d33`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180008d33`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180008d22`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180008d22`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180008b58`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180008b58`

## string_xrefs

- `0x180008af3`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180008d02`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180008b27`: `CHR(CreateHash(hProv, ((4 << 13) | (0) | 12), &hHash))`

## pseudocode

```c
__int64 __fastcall MdmCrypto::HashString(BYTE *pbData, _QWORD *a2)
{
  _WORD *v4; // rcx
  int v5; // edx
  int v6; // ecx
  int Provider; // ebx
  int v8; // edx
  int v9; // ecx
  DWORD v10; // r8d
  signed int v11; // eax
  int v12; // edx
  int v13; // ecx
  int v14; // edx
  int v15; // ecx
  signed int v16; // eax
  int v17; // edx
  int v18; // ecx
  unsigned __int8 *v19; // rax
  int v20; // edx
  int v21; // ecx
  unsigned __int8 *v22; // rdi
  unsigned __int64 v23; // rcx
  signed int LastError; // eax
  int v25; // edx
  int v26; // ecx
  int v27; // edx
  int v28; // ecx
  DWORD pdwDataLen; // [rsp+68h] [rbp+28h] BYREF
  HCRYPTHASH hHash; // [rsp+70h] [rbp+30h] BYREF
  HCRYPTPROV hProv; // [rsp+78h] [rbp+38h] BYREF

  hProv = 0;
  hHash = 0;
  pdwDataLen = 0;
  a2[2] = 0;
  if ( a2[3] <= 7u )
    v4 = a2;
  else
    v4 = (_WORD *)*a2;
  *v4 = 0;
  Provider = MdmCrypto::GetProvider(&hProv, (int)a2);
  if ( Provider >= 0 )
  {
    Provider = MdmCrypto::CreateHash(hProv, v5, &hHash);
    if ( Provider >= 0 )
    {
      v10 = 2 * *((_DWORD *)pbData + 4);
      if ( *((_QWORD *)pbData + 3) > 7u )
        pbData = *(BYTE **)pbData;
      if ( CryptHashData(hHash, pbData, v10, 0) )
      {
        if ( CryptGetHashParam(hHash, 2u, 0, &pdwDataLen, 0) )
        {
          if ( pdwDataLen )
          {
            v19 = (unsigned __int8 *)operator new[](pdwDataLen, (const struct std::nothrow_t *)&std::nothrow);
            v22 = v19;
            if ( v19 )
            {
              memset_0(v19, 0, pdwDataLen);
              if ( CryptGetHashParam(hHash, 2u, v22, &pdwDataLen, 0) )
              {
                Provider = MdmBase64Coder::Encode(v23, v22, pdwDataLen, (__int64)a2);
                if ( Provider < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v28,
                    v27,
                    Provider,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
                    9,
                    "CHR(b64coder.Encode(pbBuffer, cbBuffer, wstrHash))",
                    0,
                    0);
              }
              else
              {
                LastError = GetLastError();
                Provider = LastError;
                if ( LastError > 0 )
                  Provider = (unsigned __int16)LastError | 0x80070000;
                if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v26,
                    v25,
                    Provider,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
                    6,
                    "CBR(CryptGetHashParam(hHash, 0x0002, pbBuffer, &cbBuffer, 0))",
                    0,
                    0);
              }
              operator delete(v22);
            }
            else
            {
              Provider = -2147024882;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v21,
                  v20,
                  -2147024882,
                  (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
                  255,
                  "CPR(pbBuffer)",
                  0,
                  0);
            }
          }
          else
          {
            Provider = -2147418113;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v15,
                v14,
                -2147418113,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
                253,
                "CBR(cbBuffer > 0)",
                0,
                0);
          }
        }
        else
        {
          v16 = GetLastError();
          Provider = v16;
          if ( v16 > 0 )
            Provider = (unsigned __int16)v16 | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v18,
              v17,
              Provider,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
              252,
              "CBR(CryptGetHashParam(hHash, 0x0002, 0, &cbBuffer, 0))",
              0,
              0);
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
            v13,
            v12,
            Provider,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
            244,
            "CBR(CryptHashData(hHash, (PBYTE)wstrString.c_str(), (DWORD)wstrString.length() * 2, 0))",
            0,
            0);
      }
    }
    else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v8,
        Provider,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
        237,
        "CHR(CreateHash(hProv, ((4 << 13) | (0) | 12), &hHash))",
        0,
        0);
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v6,
      v5,
      Provider,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
      236,
      "CHR(GetProvider(&hProv))",
      0,
      0);
  }
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( hProv )
    CryptReleaseContext(hProv, 0);
  operator delete(0);
  return (unsigned int)Provider;
}

```

## disassembly

```asm
0x180008a6c  mov     [rsp-18h+arg_0], rbx
0x180008a71  push    rbp
0x180008a72  push    rsi
0x180008a73  push    rdi
0x180008a74  mov     rbp, rsp
0x180008a77  sub     rsp, 40h
0x180008a7b  mov     rsi, rdx
0x180008a7e  mov     rdi, rcx
0x180008a81  mov     [rbp+hProv], 0
0x180008a89  mov     [rbp+hHash], 0
0x180008a91  mov     [rbp+pdwDataLen], 0
0x180008a98  mov     [rbp+var_10], 0
0x180008aa0  mov     [rbp+var_8], 0
0x180008aa7  mov     qword ptr [rdx+10h], 0
0x180008aaf  cmp     qword ptr [rdx+18h], 7
0x180008ab4  jbe     short loc_180008ABB
0x180008ab6  mov     rcx, [rdx]
0x180008ab9  jmp     short loc_180008ABE
0x180008abb  mov     rcx, rsi
0x180008abe  xor     eax, eax
0x180008ac0  mov     [rcx], ax
0x180008ac3  lea     rcx, [rbp+hProv]; unsigned __int64 *
0x180008ac7  call    ?GetProvider@MdmCrypto@@CAJPEA_K@Z; MdmCrypto::GetProvider(unsigned __int64 *)
0x180008acc  mov     ebx, eax
0x180008ace  test    eax, eax
0x180008ad0  jns     short loc_180008B07
0x180008ad2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008ad9  jz      loc_180008D19
0x180008adf  lea     rax, aChrGetprovider; "CHR(GetProvider(&hProv))"
0x180008ae6  mov     [rsp+40h+var_18], rax
0x180008aeb  mov     [rsp+40h+dwFlags], 3ECh
0x180008af3  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008afa  mov     r8d, ebx
0x180008afd  call    McTemplateU0dsqs_EventWriteTransfer
0x180008b02  jmp     loc_180008D19
0x180008b07  lea     r8, [rbp+hHash]; unsigned __int64 *
0x180008b0b  mov     rcx, [rbp+hProv]; unsigned __int64
0x180008b0f  call    ?CreateHash@MdmCrypto@@CAJ_KIPEA_K@Z; MdmCrypto::CreateHash(unsigned __int64,uint,unsigned __int64 *)
0x180008b14  mov     ebx, eax
0x180008b16  test    eax, eax
0x180008b18  jns     short loc_180008B3D
0x180008b1a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008b21  jz      loc_180008D19
0x180008b27  lea     rax, aChrCreatehashH; "CHR(CreateHash(hProv, ((4 << 13) | (0) "...
0x180008b2e  mov     [rsp+40h+var_18], rax
0x180008b33  mov     [rsp+40h+dwFlags], 3EDh
0x180008b3b  jmp     short loc_180008AF3
0x180008b3d  mov     r8d, [rdi+10h]
0x180008b41  add     r8d, r8d; dwDataLen
0x180008b44  cmp     qword ptr [rdi+18h], 7
0x180008b49  jbe     short loc_180008B4E
0x180008b4b  mov     rdi, [rdi]
0x180008b4e  xor     r9d, r9d; dwFlags
0x180008b51  mov     rdx, rdi; pbData
0x180008b54  mov     rcx, [rbp+hHash]; hHash
0x180008b58  call    cs:__imp_CryptHashData
0x180008b5e  test    eax, eax
0x180008b60  jnz     short loc_180008B9D
0x180008b62  call    cs:__imp_GetLastError
0x180008b68  mov     ebx, eax
0x180008b6a  test    eax, eax
0x180008b6c  jle     short loc_180008B77
0x180008b6e  movzx   ebx, ax
0x180008b71  or      ebx, 80070000h
0x180008b77  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008b7e  jz      loc_180008D19
0x180008b84  lea     rax, aCbrCrypthashda; "CBR(CryptHashData(hHash, (PBYTE)wstrStr"...
0x180008b8b  mov     [rsp+40h+var_18], rax
0x180008b90  mov     [rsp+40h+dwFlags], 3F4h
0x180008b98  jmp     loc_180008AF3
0x180008b9d  mov     [rsp+40h+dwFlags], 0; dwFlags
0x180008ba5  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180008ba9  xor     r8d, r8d; pbData
0x180008bac  lea     ebx, [r8+2]
0x180008bb0  mov     edx, ebx; dwParam
0x180008bb2  mov     rcx, [rbp+hHash]; hHash
0x180008bb6  call    cs:__imp_CryptGetHashParam
0x180008bbc  test    eax, eax
0x180008bbe  jnz     short loc_180008BFB
0x180008bc0  call    cs:__imp_GetLastError
0x180008bc6  mov     ebx, eax
0x180008bc8  test    eax, eax
0x180008bca  jle     short loc_180008BD5
0x180008bcc  movzx   ebx, ax
0x180008bcf  or      ebx, 80070000h
0x180008bd5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008bdc  jz      loc_180008D19
0x180008be2  lea     rax, aCbrCryptgethas; "CBR(CryptGetHashParam(hHash, 0x0002, 0,"...
0x180008be9  mov     [rsp+40h+var_18], rax
0x180008bee  mov     [rsp+40h+dwFlags], 3FCh
0x180008bf6  jmp     loc_180008AF3
0x180008bfb  mov     eax, [rbp+pdwDataLen]
0x180008bfe  test    eax, eax
0x180008c00  jnz     short loc_180008C2D
0x180008c02  mov     ebx, 8000FFFFh
0x180008c07  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008c0e  jz      loc_180008D19
0x180008c14  lea     rax, aCbrCbbuffer0; "CBR(cbBuffer > 0)"
0x180008c1b  mov     [rsp+40h+var_18], rax
0x180008c20  mov     [rsp+40h+dwFlags], 3FDh
0x180008c28  jmp     loc_180008AF3
0x180008c2d  mov     rcx, rax; unsigned __int64
0x180008c30  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008c37  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008c3c  mov     rdi, rax
0x180008c3f  test    rax, rax
0x180008c42  jnz     short loc_180008C6F
0x180008c44  mov     ebx, 8007000Eh
0x180008c49  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008c50  jz      loc_180008D19
0x180008c56  lea     rax, aCprPbbuffer; "CPR(pbBuffer)"
0x180008c5d  mov     [rsp+40h+var_18], rax
0x180008c62  mov     [rsp+40h+dwFlags], 3FFh
0x180008c6a  jmp     loc_180008AF3
0x180008c6f  mov     r8d, [rbp+pdwDataLen]; Size
0x180008c73  xor     edx, edx; Val
0x180008c75  mov     rcx, rdi; void *
0x180008c78  call    memset_0
0x180008c7d  mov     [rsp+40h+dwFlags], 0; dwFlags
0x180008c85  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180008c89  mov     r8, rdi; pbData
0x180008c8c  mov     edx, ebx; dwParam
0x180008c8e  mov     rcx, [rbp+hHash]; hHash
0x180008c92  call    cs:__imp_CryptGetHashParam
0x180008c98  test    eax, eax
0x180008c9a  jnz     short loc_180008CD0
0x180008c9c  call    cs:__imp_GetLastError
0x180008ca2  mov     ebx, eax
0x180008ca4  test    eax, eax
0x180008ca6  jle     short loc_180008CB1
0x180008ca8  movzx   ebx, ax
0x180008cab  or      ebx, 80070000h
0x180008cb1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008cb8  jz      short loc_180008D11
0x180008cba  lea     rax, aCbrCryptgethas_1; "CBR(CryptGetHashParam(hHash, 0x0002, pb"...
0x180008cc1  mov     [rsp+40h+var_18], rax
0x180008cc6  mov     [rsp+40h+dwFlags], 406h
0x180008cce  jmp     short loc_180008D02
0x180008cd0  mov     r9, rsi
0x180008cd3  mov     r8d, [rbp+pdwDataLen]
0x180008cd7  mov     rdx, rdi
0x180008cda  call    ?Encode@MdmBase64Coder@@QEAAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmBase64Coder::Encode(uchar const *,ulong,std::wstring &)
0x180008cdf  mov     ebx, eax
0x180008ce1  test    eax, eax
0x180008ce3  jns     short loc_180008D11
0x180008ce5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008cec  jz      short loc_180008D11
0x180008cee  lea     rax, aChrB64coderEnc_0; "CHR(b64coder.Encode(pbBuffer, cbBuffer,"...
0x180008cf5  mov     [rsp+40h+var_18], rax
0x180008cfa  mov     [rsp+40h+dwFlags], 409h
0x180008d02  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008d09  mov     r8d, ebx
0x180008d0c  call    McTemplateU0dsqs_EventWriteTransfer
0x180008d11  mov     rcx, rdi; void *
0x180008d14  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008d19  mov     rcx, [rbp+hHash]; hHash
0x180008d1d  test    rcx, rcx
0x180008d20  jz      short loc_180008D28
0x180008d22  call    cs:__imp_CryptDestroyHash
0x180008d28  mov     rcx, [rbp+hProv]; hProv
0x180008d2c  test    rcx, rcx
0x180008d2f  jz      short loc_180008D3A
0x180008d31  xor     edx, edx; dwFlags
0x180008d33  call    cs:__imp_CryptReleaseContext
0x180008d39  nop
0x180008d3a  xor     ecx, ecx; void *
0x180008d3c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008d41  mov     eax, ebx
0x180008d43  mov     rbx, [rsp+40h+arg_0]
0x180008d48  add     rsp, 40h
0x180008d4c  pop     rdi
0x180008d4d  pop     rsi
0x180008d4e  pop     rbp
0x180008d4f  retn
```
