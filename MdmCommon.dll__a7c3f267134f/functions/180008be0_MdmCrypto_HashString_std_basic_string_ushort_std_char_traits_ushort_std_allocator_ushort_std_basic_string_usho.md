# MdmCrypto::HashString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180008be0`
- end: `0x180008ef5`
- name: `?HashString@MdmCrypto@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `789`
- prototype: `__int64 __fastcall(BYTE *pbData)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800030c0`
- `0x1800040d0`
- `0x1800050a0`
- `0x18000c6e8`

## callees

- `0x180001544`
- `0x1800015b8`
- `0x180001fd4`
- `0x1800065c0`
- `0x1800080a4`
- `0x1800089b8`
- `0x180008be0`
- `0x18001a388`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e2e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180008d36`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180008e1e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180008d36`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180008e1e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180008ed1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180008ed1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180008eba`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180008eba`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180008ccc`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180008ccc`

## string_xrefs

- `0x180008c67`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180008e9a`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcrypto.cpp`
- `0x180008c9b`: `CHR(CreateHash(hProv, ((4 << 13) | (0) | 12), &hHash))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MdmCrypto::HashString(BYTE *pbData, __int64 a2)
{
  char *v4; // rcx
  unsigned __int64 v5; // rdx
  int v6; // ecx
  int Provider; // ebx
  int v8; // ecx
  DWORD v9; // r8d
  signed int v10; // eax
  int v11; // ecx
  int v12; // ecx
  signed int v13; // eax
  int v14; // ecx
  unsigned __int8 *v15; // rax
  int v16; // ecx
  unsigned __int8 *v17; // rdi
  MdmBase64Coder *v18; // rcx
  signed int LastError; // eax
  unsigned __int64 v20; // rdx
  int v21; // ecx
  int v22; // ecx
  DWORD pdwDataLen; // [rsp+68h] [rbp+28h] BYREF
  HCRYPTHASH hHash; // [rsp+70h] [rbp+30h] BYREF
  HCRYPTPROV hProv; // [rsp+78h] [rbp+38h] BYREF

  hProv = 0;
  hHash = 0;
  pdwDataLen = 0;
  *(_QWORD *)(a2 + 16) = 0;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v4 = (char *)a2;
  else
    v4 = *(char **)a2;
  *(_WORD *)v4 = 0;
  Provider = MdmCrypto::GetProvider(&hProv);
  if ( Provider >= 0 )
  {
    Provider = MdmCrypto::CreateHash(hProv, v5, &hHash);
    if ( Provider >= 0 )
    {
      v9 = 2 * *((_DWORD *)pbData + 4);
      if ( *((_QWORD *)pbData + 3) > 7u )
        pbData = *(BYTE **)pbData;
      if ( CryptHashData(hHash, pbData, v9, 0) )
      {
        if ( CryptGetHashParam(hHash, 2u, 0, &pdwDataLen, 0) )
        {
          if ( pdwDataLen )
          {
            v15 = (unsigned __int8 *)operator new[](pdwDataLen, (const struct std::nothrow_t *)&std::nothrow);
            v17 = v15;
            if ( v15 )
            {
              memset_0(v15, 0, pdwDataLen);
              if ( CryptGetHashParam(hHash, 2u, v17, &pdwDataLen, 0) )
              {
                Provider = MdmBase64Coder::Encode(v18, v17, pdwDataLen, (char **)a2);
                if ( Provider < 0 && (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                  McTemplateU0dsqs_EventWriteTransfer(
                    v22,
                    v20,
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
                    v21,
                    v20,
                    Provider,
                    (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcrypto.cpp",
                    6,
                    "CBR(CryptGetHashParam(hHash, 0x0002, pbBuffer, &cbBuffer, 0))",
                    0,
                    0);
              }
              operator delete(v17, v20);
            }
            else
            {
              Provider = -2147024882;
              if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
                McTemplateU0dsqs_EventWriteTransfer(
                  v16,
                  v5,
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
                v12,
                v5,
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
          v13 = GetLastError();
          Provider = v13;
          if ( v13 > 0 )
            Provider = (unsigned __int16)v13 | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v14,
              v5,
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
        v10 = GetLastError();
        Provider = v10;
        if ( v10 > 0 )
          Provider = (unsigned __int16)v10 | 0x80070000;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v11,
            v5,
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
        v8,
        v5,
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
  operator delete(0, v5);
  return (unsigned int)Provider;
}

```

## disassembly

```asm
0x180008be0  mov     [rsp-18h+arg_0], rbx
0x180008be5  push    rbp
0x180008be6  push    rsi
0x180008be7  push    rdi
0x180008be8  mov     rbp, rsp
0x180008beb  sub     rsp, 40h
0x180008bef  mov     rsi, rdx
0x180008bf2  mov     rdi, rcx
0x180008bf5  mov     [rbp+hProv], 0
0x180008bfd  mov     [rbp+hHash], 0
0x180008c05  mov     [rbp+pdwDataLen], 0
0x180008c0c  mov     [rbp+var_10], 0
0x180008c14  mov     [rbp+var_8], 0
0x180008c1b  mov     qword ptr [rdx+10h], 0
0x180008c23  cmp     qword ptr [rdx+18h], 7
0x180008c28  jbe     short loc_180008C2F
0x180008c2a  mov     rcx, [rdx]
0x180008c2d  jmp     short loc_180008C32
0x180008c2f  mov     rcx, rsi
0x180008c32  xor     eax, eax
0x180008c34  mov     [rcx], ax
0x180008c37  lea     rcx, [rbp+hProv]; unsigned __int64 *
0x180008c3b  call    ?GetProvider@MdmCrypto@@CAJPEA_K@Z; MdmCrypto::GetProvider(unsigned __int64 *)
0x180008c40  mov     ebx, eax
0x180008c42  test    eax, eax
0x180008c44  jns     short loc_180008C7B
0x180008c46  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008c4d  jz      loc_180008EB1
0x180008c53  lea     rax, aChrGetprovider; "CHR(GetProvider(&hProv))"
0x180008c5a  mov     [rsp+40h+var_18], rax
0x180008c5f  mov     [rsp+40h+dwFlags], 3ECh
0x180008c67  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008c6e  mov     r8d, ebx
0x180008c71  call    McTemplateU0dsqs_EventWriteTransfer
0x180008c76  jmp     loc_180008EB1
0x180008c7b  lea     r8, [rbp+hHash]; unsigned __int64 *
0x180008c7f  mov     rcx, [rbp+hProv]; unsigned __int64
0x180008c83  call    ?CreateHash@MdmCrypto@@CAJ_KIPEA_K@Z; MdmCrypto::CreateHash(unsigned __int64,uint,unsigned __int64 *)
0x180008c88  mov     ebx, eax
0x180008c8a  test    eax, eax
0x180008c8c  jns     short loc_180008CB1
0x180008c8e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008c95  jz      loc_180008EB1
0x180008c9b  lea     rax, aChrCreatehashH; "CHR(CreateHash(hProv, ((4 << 13) | (0) "...
0x180008ca2  mov     [rsp+40h+var_18], rax
0x180008ca7  mov     [rsp+40h+dwFlags], 3EDh
0x180008caf  jmp     short loc_180008C67
0x180008cb1  mov     r8d, [rdi+10h]
0x180008cb5  add     r8d, r8d; dwDataLen
0x180008cb8  cmp     qword ptr [rdi+18h], 7
0x180008cbd  jbe     short loc_180008CC2
0x180008cbf  mov     rdi, [rdi]
0x180008cc2  xor     r9d, r9d; dwFlags
0x180008cc5  mov     rdx, rdi; pbData
0x180008cc8  mov     rcx, [rbp+hHash]; hHash
0x180008ccc  call    cs:__imp_CryptHashData
0x180008cd3  nop     dword ptr [rax+rax+00h]
0x180008cd8  test    eax, eax
0x180008cda  jnz     short loc_180008D1D
0x180008cdc  call    cs:__imp_GetLastError
0x180008ce3  nop     dword ptr [rax+rax+00h]
0x180008ce8  mov     ebx, eax
0x180008cea  test    eax, eax
0x180008cec  jle     short loc_180008CF7
0x180008cee  movzx   ebx, ax
0x180008cf1  or      ebx, 80070000h
0x180008cf7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008cfe  jz      loc_180008EB1
0x180008d04  lea     rax, aCbrCrypthashda; "CBR(CryptHashData(hHash, (PBYTE)wstrStr"...
0x180008d0b  mov     [rsp+40h+var_18], rax
0x180008d10  mov     [rsp+40h+dwFlags], 3F4h
0x180008d18  jmp     loc_180008C67
0x180008d1d  mov     [rsp+40h+dwFlags], 0; dwFlags
0x180008d25  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180008d29  xor     r8d, r8d; pbData
0x180008d2c  lea     ebx, [r8+2]
0x180008d30  mov     edx, ebx; dwParam
0x180008d32  mov     rcx, [rbp+hHash]; hHash
0x180008d36  call    cs:__imp_CryptGetHashParam
0x180008d3d  nop     dword ptr [rax+rax+00h]
0x180008d42  test    eax, eax
0x180008d44  jnz     short loc_180008D87
0x180008d46  call    cs:__imp_GetLastError
0x180008d4d  nop     dword ptr [rax+rax+00h]
0x180008d52  mov     ebx, eax
0x180008d54  test    eax, eax
0x180008d56  jle     short loc_180008D61
0x180008d58  movzx   ebx, ax
0x180008d5b  or      ebx, 80070000h
0x180008d61  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008d68  jz      loc_180008EB1
0x180008d6e  lea     rax, aCbrCryptgethas; "CBR(CryptGetHashParam(hHash, 0x0002, 0,"...
0x180008d75  mov     [rsp+40h+var_18], rax
0x180008d7a  mov     [rsp+40h+dwFlags], 3FCh
0x180008d82  jmp     loc_180008C67
0x180008d87  mov     eax, [rbp+pdwDataLen]
0x180008d8a  test    eax, eax
0x180008d8c  jnz     short loc_180008DB9
0x180008d8e  mov     ebx, 8000FFFFh
0x180008d93  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008d9a  jz      loc_180008EB1
0x180008da0  lea     rax, aCbrCbbuffer0; "CBR(cbBuffer > 0)"
0x180008da7  mov     [rsp+40h+var_18], rax
0x180008dac  mov     [rsp+40h+dwFlags], 3FDh
0x180008db4  jmp     loc_180008C67
0x180008db9  mov     rcx, rax; unsigned __int64
0x180008dbc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008dc3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008dc8  mov     rdi, rax
0x180008dcb  test    rax, rax
0x180008dce  jnz     short loc_180008DFB
0x180008dd0  mov     ebx, 8007000Eh
0x180008dd5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008ddc  jz      loc_180008EB1
0x180008de2  lea     rax, aCprPbbuffer; "CPR(pbBuffer)"
0x180008de9  mov     [rsp+40h+var_18], rax
0x180008dee  mov     [rsp+40h+dwFlags], 3FFh
0x180008df6  jmp     loc_180008C67
0x180008dfb  mov     r8d, [rbp+pdwDataLen]; Size
0x180008dff  xor     edx, edx; Val
0x180008e01  mov     rcx, rdi; void *
0x180008e04  call    memset_0
0x180008e09  mov     [rsp+40h+dwFlags], 0; dwFlags
0x180008e11  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180008e15  mov     r8, rdi; pbData
0x180008e18  mov     edx, ebx; dwParam
0x180008e1a  mov     rcx, [rbp+hHash]; hHash
0x180008e1e  call    cs:__imp_CryptGetHashParam
0x180008e25  nop     dword ptr [rax+rax+00h]
0x180008e2a  test    eax, eax
0x180008e2c  jnz     short loc_180008E68
0x180008e2e  call    cs:__imp_GetLastError
0x180008e35  nop     dword ptr [rax+rax+00h]
0x180008e3a  mov     ebx, eax
0x180008e3c  test    eax, eax
0x180008e3e  jle     short loc_180008E49
0x180008e40  movzx   ebx, ax
0x180008e43  or      ebx, 80070000h
0x180008e49  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008e50  jz      short loc_180008EA9
0x180008e52  lea     rax, aCbrCryptgethas_1; "CBR(CryptGetHashParam(hHash, 0x0002, pb"...
0x180008e59  mov     [rsp+40h+var_18], rax
0x180008e5e  mov     [rsp+40h+dwFlags], 406h
0x180008e66  jmp     short loc_180008E9A
0x180008e68  mov     r9, rsi
0x180008e6b  mov     r8d, [rbp+pdwDataLen]
0x180008e6f  mov     rdx, rdi
0x180008e72  call    ?Encode@MdmBase64Coder@@QEAAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmBase64Coder::Encode(uchar const *,ulong,std::wstring &)
0x180008e77  mov     ebx, eax
0x180008e79  test    eax, eax
0x180008e7b  jns     short loc_180008EA9
0x180008e7d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180008e84  jz      short loc_180008EA9
0x180008e86  lea     rax, aChrB64coderEnc_0; "CHR(b64coder.Encode(pbBuffer, cbBuffer,"...
0x180008e8d  mov     [rsp+40h+var_18], rax
0x180008e92  mov     [rsp+40h+dwFlags], 409h
0x180008e9a  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008ea1  mov     r8d, ebx
0x180008ea4  call    McTemplateU0dsqs_EventWriteTransfer
0x180008ea9  mov     rcx, rdi; void *
0x180008eac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008eb1  mov     rcx, [rbp+hHash]; hHash
0x180008eb5  test    rcx, rcx
0x180008eb8  jz      short loc_180008EC6
0x180008eba  call    cs:__imp_CryptDestroyHash
0x180008ec1  nop     dword ptr [rax+rax+00h]
0x180008ec6  mov     rcx, [rbp+hProv]; hProv
0x180008eca  test    rcx, rcx
0x180008ecd  jz      short loc_180008EDE
0x180008ecf  xor     edx, edx; dwFlags
0x180008ed1  call    cs:__imp_CryptReleaseContext
0x180008ed8  nop     dword ptr [rax+rax+00h]
0x180008edd  nop
0x180008ede  xor     ecx, ecx; void *
0x180008ee0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008ee5  mov     eax, ebx
0x180008ee7  mov     rbx, [rsp+40h+arg_0]
0x180008eec  add     rsp, 40h
0x180008ef0  pop     rdi
0x180008ef1  pop     rsi
0x180008ef2  pop     rbp
0x180008ef3  retn
```
