# EnrollmentToken::GenerateAETCertsStore(void * *,uchar const *,ulong)

- ea: `0x18002b088`
- end: `0x18002b29d`
- name: `?GenerateAETCertsStore@EnrollmentToken@@AEAAJPEAPEAXPEBEK@Z`
- size: `533`
- prototype: `int(EnrollmentToken *__hidden this, void **, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002b428`

## callees

- `0x180002fc0`
- `0x180006ac0`
- `0x18002ac44`
- `0x18002b088`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002b27b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002b27b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b21f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b0f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b21f`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18002b1e0`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18002b20f`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18002b1e0`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x18002b20f`
- `CRYPT32!CertCloseStore` at `0x18002b260`
- `CRYPT32!CertCloseStore` at `0x18002b260`
- `CRYPT32!CertOpenStore` at `0x18002b0e1`
- `CRYPT32!CertOpenStore` at `0x18002b0e1`

## string_xrefs

- `0x18002b119`: `EnrollmentToken::GenerateAETCertsStore CertOpenStore Failed`
- `0x18002b240`: `EnrollmentToken::GenerateAETCertsStore CertAddEncodedCertificateToStore Failed`
- `0x18002b1b3`: `EnrollmentToken::GenerateAETCertsStore Base64Decode Failed`

## pseudocode

```c
__int64 __fastcall EnrollmentToken::GenerateAETCertsStore(
        EnrollmentToken *this,
        void **a2,
        const unsigned __int8 *a3,
        DWORD a4)
{
  unsigned int v7; // ebx
  HCERTSTORE v8; // rsi
  signed int v9; // eax
  __int64 v10; // rcx
  unsigned __int8 *v11; // rax
  BYTE *v12; // rbp
  signed int LastError; // eax
  __int64 v14; // rcx
  const wchar_t *v15; // r8
  DWORD cbCertEncoded; // [rsp+50h] [rbp+8h] BYREF
  int v18; // [rsp+54h] [rbp+Ch]

  v18 = HIDWORD(this);
  cbCertEncoded = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  *a2 = 0;
  v8 = CertOpenStore((LPCSTR)2, 0, 0, 0x2280u, 0);
  if ( v8 )
  {
    ATL::Base64Decode(
      "MIIDvTCCAqWgAwIBAgIQD2tVL56/kHsPZimpvfTYzjANBgkqhkiG9w0BAQsFADBkMQswCQYDVQQGEwJVUzEdMBsGA1UEChMUU3ltYW50ZWMgQ29ycG"
      "9yYXRpb24xNjA0BgNVBAMTLVN5bWFudGVjIEVudGVycHJpc2UgTW9iaWxlIFJvb3QgZm9yIE1pY3Jvc29mdDAeFw0xMjAzMTUwMDAwMDBaFw0zMjAz"
      "MTQyMzU5NTlaMGQxCzAJBgNVBAYTAlVTMR0wGwYDVQQKExRTeW1hbnRlYyBDb3Jwb3JhdGlvbjE2MDQGA1UEAxMtU3ltYW50ZWMgRW50ZXJwcmlzZS"
      "BNb2JpbGUgUm9vdCBmb3IgTWljcm9zb2Z0MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAtT2wcu6R6aVpnBFNevmz+j3ylJsjt6YD7GIY"
      "/IUSIv7BcX1Uk7mRfWL2yqg4FWX4dz3lgiA61LXRbo0GSb3fgg4khefveC0Y8uALaEY+JBDIV+4ObXGm07FWHNcp1bLqVAUKqDyhuCVSBwWg3+fc7l"
      "w7QbWrXDMy0s7r6Zb4QPQKujMd+FYDCYL1ZwfEwDTBXfxFu+o8mtV0cW3VhtPC/IW8VOuj1fJP1UWvV7zwIsCPokXIdTR33qFtN3Kzc40Ma1O6WeGo"
      "PoBX0l9Z7mh1z4Gco8pFjDfbBXI0HDIC+NX5LA3aWJ7EF7SbyZDEiFk/cZGQRBi+Iot5ki5CsIuXWwIDAQABo2swaTAPBgNVHRMBAf8EBTADAQH/MA"
      "4GA1UdDwEB/wQEAwIBBjAnBgNVHREEIDAepBwwGjEYMBYGA1UEAxMPTVBLSS0yMDQ4LTEtMTExMB0GA1UdDgQWBBRN7N8mBtwkEMC2mfTXOcdvGfgm"
      "KDANBgkqhkiG9w0BAQsFAAOCAQEAqVdZ0AFUFEavx3lUDGoqW9g6HYHkiKMxtPHzNfFGc1xDyf68omoZwL0vX8s4o21u6BRe8nh+RXrhu/Qum0Xr4B"
      "1QHDRbf5iKhg+H2uRkJnf8Cd8jQU8On/oO+kSF8CmXpJTi9EAtkRx29Khg3nGmsAXiT2nZGQuJOuD6qyv68bMy7fx8cGVe0HsRe53oWxpKdqR7UTms"
      "fakMdDjou1XfxM7ApyFauBufAcWnEP59+WoImQHR9jVQOOT2Q+QY2IBM7McE4mGMfUntz7Sl8fKQkgkINXOgIzLK6ZyeHL4LByx3XhdM2pyC4YAbpf"
      "Pa94i/vzkn+CT+sUvIl+3kEhQliA==",
      1284,
      0,
      (int *)&cbCertEncoded);
    v11 = (unsigned __int8 *)operator new[](cbCertEncoded, (const struct std::nothrow_t *)&std::nothrow);
    v12 = v11;
    if ( !v11 )
    {
      v7 = -2147024882;
      goto LABEL_25;
    }
    if ( (unsigned int)ATL::Base64Decode(
                         "MIIDvTCCAqWgAwIBAgIQD2tVL56/kHsPZimpvfTYzjANBgkqhkiG9w0BAQsFADBkMQswCQYDVQQGEwJVUzEdMBsGA1UEChM"
                         "UU3ltYW50ZWMgQ29ycG9yYXRpb24xNjA0BgNVBAMTLVN5bWFudGVjIEVudGVycHJpc2UgTW9iaWxlIFJvb3QgZm9yIE1pY3"
                         "Jvc29mdDAeFw0xMjAzMTUwMDAwMDBaFw0zMjAzMTQyMzU5NTlaMGQxCzAJBgNVBAYTAlVTMR0wGwYDVQQKExRTeW1hbnRlY"
                         "yBDb3Jwb3JhdGlvbjE2MDQGA1UEAxMtU3ltYW50ZWMgRW50ZXJwcmlzZSBNb2JpbGUgUm9vdCBmb3IgTWljcm9zb2Z0MIIB"
                         "IjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAtT2wcu6R6aVpnBFNevmz+j3ylJsjt6YD7GIY/IUSIv7BcX1Uk7mRfWL"
                         "2yqg4FWX4dz3lgiA61LXRbo0GSb3fgg4khefveC0Y8uALaEY+JBDIV+4ObXGm07FWHNcp1bLqVAUKqDyhuCVSBwWg3+fc7l"
                         "w7QbWrXDMy0s7r6Zb4QPQKujMd+FYDCYL1ZwfEwDTBXfxFu+o8mtV0cW3VhtPC/IW8VOuj1fJP1UWvV7zwIsCPokXIdTR33"
                         "qFtN3Kzc40Ma1O6WeGoPoBX0l9Z7mh1z4Gco8pFjDfbBXI0HDIC+NX5LA3aWJ7EF7SbyZDEiFk/cZGQRBi+Iot5ki5CsIuX"
                         "WwIDAQABo2swaTAPBgNVHRMBAf8EBTADAQH/MA4GA1UdDwEB/wQEAwIBBjAnBgNVHREEIDAepBwwGjEYMBYGA1UEAxMPTVB"
                         "LSS0yMDQ4LTEtMTExMB0GA1UdDgQWBBRN7N8mBtwkEMC2mfTXOcdvGfgmKDANBgkqhkiG9w0BAQsFAAOCAQEAqVdZ0AFUFE"
                         "avx3lUDGoqW9g6HYHkiKMxtPHzNfFGc1xDyf68omoZwL0vX8s4o21u6BRe8nh+RXrhu/Qum0Xr4B1QHDRbf5iKhg+H2uRkJ"
                         "nf8Cd8jQU8On/oO+kSF8CmXpJTi9EAtkRx29Khg3nGmsAXiT2nZGQuJOuD6qyv68bMy7fx8cGVe0HsRe53oWxpKdqR7UTms"
                         "fakMdDjou1XfxM7ApyFauBufAcWnEP59+WoImQHR9jVQOOT2Q+QY2IBM7McE4mGMfUntz7Sl8fKQkgkINXOgIzLK6ZyeHL4"
                         "LByx3XhdM2pyC4YAbpfPa94i/vzkn+CT+sUvIl+3kEhQliA==",
                         1284,
                         v11,
                         (int *)&cbCertEncoded) )
    {
      if ( CertAddEncodedCertificateToStore(v8, 0x10001u, v12, cbCertEncoded, 3u, 0)
        && CertAddEncodedCertificateToStore(v8, 0x10001u, a3, a4, 3u, 0) )
      {
        v7 = 0;
        *a2 = v8;
        goto LABEL_28;
      }
      LastError = GetLastError();
      if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) == 0 )
        goto LABEL_24;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v15 = L"EnrollmentToken::GenerateAETCertsStore CertAddEncodedCertificateToStore Failed";
    }
    else
    {
      LastError = GetLastError();
      if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) == 0 )
      {
LABEL_24:
        v7 = -2147467259;
LABEL_25:
        CertCloseStore(v8, 0);
        if ( !v12 )
          return v7;
LABEL_28:
        operator delete[](v12);
        return v7;
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v15 = L"EnrollmentToken::GenerateAETCertsStore Base64Decode Failed";
    }
    McTemplateU0zq_EventWriteTransfer(v14, EnterpriseAppMgmtSvcError, v15, (unsigned int)LastError);
    goto LABEL_24;
  }
  v9 = GetLastError();
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 2) != 0 )
  {
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    McTemplateU0zq_EventWriteTransfer(
      v10,
      EnterpriseAppMgmtSvcError,
      L"EnrollmentToken::GenerateAETCertsStore CertOpenStore Failed",
      (unsigned int)v9);
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x18002b088  mov     rax, rsp
0x18002b08b  mov     [rax+10h], rbx
0x18002b08f  mov     [rax+18h], rbp
0x18002b093  mov     [rax+8], rcx
0x18002b097  push    rsi
0x18002b098  push    rdi
0x18002b099  push    r14
0x18002b09b  sub     rsp, 30h
0x18002b09f  mov     dword ptr [rax+8], 0
0x18002b0a6  mov     r14d, r9d
0x18002b0a9  mov     rbx, r8
0x18002b0ac  mov     rdi, rdx
0x18002b0af  test    rdx, rdx
0x18002b0b2  jnz     short loc_18002B0BE
0x18002b0b4  mov     ebx, 80070057h
0x18002b0b9  jmp     loc_18002B287
0x18002b0be  test    rbx, rbx
0x18002b0c1  jz      short loc_18002B0B4
0x18002b0c3  mov     qword ptr [rdx], 0
0x18002b0ca  mov     r9d, 2280h; dwFlags
0x18002b0d0  xor     edx, edx; dwEncodingType
0x18002b0d2  mov     [rsp+48h+pvPara], 0; pvPara
0x18002b0db  xor     r8d, r8d; hCryptProv
0x18002b0de  lea     ecx, [rdx+2]; lpszStoreProvider
0x18002b0e1  call    cs:__imp_CertOpenStore
0x18002b0e8  nop     dword ptr [rax+rax+00h]
0x18002b0ed  mov     rsi, rax
0x18002b0f0  test    rax, rax
0x18002b0f3  jnz     short loc_18002B136
0x18002b0f5  call    cs:__imp_GetLastError
0x18002b0fc  nop     dword ptr [rax+rax+00h]
0x18002b101  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x18002b108  jz      short loc_18002B12C
0x18002b10a  test    eax, eax
0x18002b10c  jle     short loc_18002B116
0x18002b10e  movzx   eax, ax
0x18002b111  or      eax, 80070000h
0x18002b116  mov     r9d, eax
0x18002b119  lea     r8, aEnrollmenttoke_5; "EnrollmentToken::GenerateAETCertsStore "...
0x18002b120  lea     rdx, EnterpriseAppMgmtSvcError
0x18002b127  call    McTemplateU0zq_EventWriteTransfer
0x18002b12c  mov     ebx, 80004005h
0x18002b131  jmp     loc_18002B287
0x18002b136  lea     r9, [rsp+48h+cbCertEncoded]; int *
0x18002b13b  xor     r8d, r8d; unsigned __int8 *
0x18002b13e  mov     edx, 504h; int
0x18002b143  lea     rcx, aMiidvtccaqwgaw; "MIIDvTCCAqWgAwIBAgIQD2tVL56/kHsPZimpvfT"...
0x18002b14a  call    ?Base64Decode@ATL@@YAHPEBDHPEAEPEAH@Z; ATL::Base64Decode(char const *,int,uchar *,int *)
0x18002b14f  mov     ecx, [rsp+48h+cbCertEncoded]; unsigned __int64
0x18002b153  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002b15a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002b15f  mov     rbp, rax
0x18002b162  test    rax, rax
0x18002b165  jnz     short loc_18002B171
0x18002b167  mov     ebx, 8007000Eh
0x18002b16c  jmp     loc_18002B25B
0x18002b171  lea     r9, [rsp+48h+cbCertEncoded]; int *
0x18002b176  mov     r8, rbp; unsigned __int8 *
0x18002b179  mov     edx, 504h; int
0x18002b17e  lea     rcx, aMiidvtccaqwgaw; "MIIDvTCCAqWgAwIBAgIQD2tVL56/kHsPZimpvfT"...
0x18002b185  call    ?Base64Decode@ATL@@YAHPEBDHPEAEPEAH@Z; ATL::Base64Decode(char const *,int,uchar *,int *)
0x18002b18a  test    eax, eax
0x18002b18c  jnz     short loc_18002B1BF
0x18002b18e  call    cs:__imp_GetLastError
0x18002b195  nop     dword ptr [rax+rax+00h]
0x18002b19a  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x18002b1a1  jz      loc_18002B256
0x18002b1a7  test    eax, eax
0x18002b1a9  jle     short loc_18002B1B3
0x18002b1ab  movzx   eax, ax
0x18002b1ae  or      eax, 80070000h
0x18002b1b3  lea     r8, aEnrollmenttoke_4; "EnrollmentToken::GenerateAETCertsStore "...
0x18002b1ba  jmp     loc_18002B247
0x18002b1bf  mov     r9d, [rsp+48h+cbCertEncoded]; cbCertEncoded
0x18002b1c4  mov     r8, rbp; pbCertEncoded
0x18002b1c7  mov     [rsp+48h+ppCertContext], 0; ppCertContext
0x18002b1d0  mov     edx, 10001h; dwCertEncodingType
0x18002b1d5  mov     rcx, rsi; hCertStore
0x18002b1d8  mov     dword ptr [rsp+48h+pvPara], 3; dwAddDisposition
0x18002b1e0  call    cs:__imp_CertAddEncodedCertificateToStore
0x18002b1e7  nop     dword ptr [rax+rax+00h]
0x18002b1ec  test    eax, eax
0x18002b1ee  jz      short loc_18002B21F
0x18002b1f0  mov     [rsp+48h+ppCertContext], 0; ppCertContext
0x18002b1f9  mov     r9d, r14d; cbCertEncoded
0x18002b1fc  mov     r8, rbx; pbCertEncoded
0x18002b1ff  mov     dword ptr [rsp+48h+pvPara], 3; dwAddDisposition
0x18002b207  mov     edx, 10001h; dwCertEncodingType
0x18002b20c  mov     rcx, rsi; hCertStore
0x18002b20f  call    cs:__imp_CertAddEncodedCertificateToStore
0x18002b216  nop     dword ptr [rax+rax+00h]
0x18002b21b  test    eax, eax
0x18002b21d  jnz     short loc_18002B273
0x18002b21f  call    cs:__imp_GetLastError
0x18002b226  nop     dword ptr [rax+rax+00h]
0x18002b22b  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x18002b232  jz      short loc_18002B256
0x18002b234  test    eax, eax
0x18002b236  jle     short loc_18002B240
0x18002b238  movzx   eax, ax
0x18002b23b  or      eax, 80070000h
0x18002b240  lea     r8, aEnrollmenttoke_0; "EnrollmentToken::GenerateAETCertsStore "...
0x18002b247  mov     r9d, eax
0x18002b24a  lea     rdx, EnterpriseAppMgmtSvcError
0x18002b251  call    McTemplateU0zq_EventWriteTransfer
0x18002b256  mov     ebx, 80004005h
0x18002b25b  xor     edx, edx; dwFlags
0x18002b25d  mov     rcx, rsi; hCertStore
0x18002b260  call    cs:__imp_CertCloseStore
0x18002b267  nop     dword ptr [rax+rax+00h]
0x18002b26c  test    rbp, rbp
0x18002b26f  jz      short loc_18002B287
0x18002b271  jmp     short loc_18002B278
0x18002b273  xor     ebx, ebx
0x18002b275  mov     [rdi], rsi
0x18002b278  mov     rcx, rbp
0x18002b27b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002b282  nop     dword ptr [rax+rax+00h]
0x18002b287  mov     rbp, [rsp+48h+arg_10]
0x18002b28c  mov     eax, ebx
0x18002b28e  mov     rbx, [rsp+48h+arg_8]
0x18002b293  add     rsp, 30h
0x18002b297  pop     r14
0x18002b299  pop     rdi
0x18002b29a  pop     rsi
0x18002b29b  retn
```
