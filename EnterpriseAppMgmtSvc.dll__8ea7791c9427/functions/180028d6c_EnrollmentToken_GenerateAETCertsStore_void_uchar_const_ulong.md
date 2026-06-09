# EnrollmentToken::GenerateAETCertsStore(void * *,uchar const *,ulong)

- ea: `0x180028d6c`
- end: `0x180028f4d`
- name: `?GenerateAETCertsStore@EnrollmentToken@@AEAAJPEAPEAXPEBEK@Z`
- size: `481`
- prototype: `int(EnrollmentToken *__hidden this, void **, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800290c0`

## callees

- `0x180002f70`
- `0x180006858`
- `0x180028940`
- `0x180028d6c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180028f32`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028f32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ee2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ee2`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x180028eaf`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x180028ed8`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x180028eaf`
- `CRYPT32!CertAddEncodedCertificateToStore` at `0x180028ed8`
- `CRYPT32!CertCloseStore` at `0x180028f1d`
- `CRYPT32!CertCloseStore` at `0x180028f1d`
- `CRYPT32!CertOpenStore` at `0x180028dc5`
- `CRYPT32!CertOpenStore` at `0x180028dc5`

## string_xrefs

- `0x180028efd`: `EnrollmentToken::GenerateAETCertsStore CertAddEncodedCertificateToStore Failed`
- `0x180028e85`: `EnrollmentToken::GenerateAETCertsStore Base64Decode Failed`
- `0x180028df1`: `EnrollmentToken::GenerateAETCertsStore CertOpenStore Failed`

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
0x180028d6c  mov     rax, rsp
0x180028d6f  mov     [rax+10h], rbx
0x180028d73  mov     [rax+18h], rbp
0x180028d77  mov     [rax+8], rcx
0x180028d7b  push    rsi
0x180028d7c  push    rdi
0x180028d7d  push    r14
0x180028d7f  sub     rsp, 30h
0x180028d83  mov     dword ptr [rax+8], 0
0x180028d8a  mov     r14d, r9d
0x180028d8d  mov     rbx, r8
0x180028d90  mov     rdi, rdx
0x180028d93  test    rdx, rdx
0x180028d96  jnz     short loc_180028DA2
0x180028d98  mov     ebx, 80070057h
0x180028d9d  jmp     loc_180028F38
0x180028da2  test    rbx, rbx
0x180028da5  jz      short loc_180028D98
0x180028da7  mov     qword ptr [rdx], 0
0x180028dae  mov     r9d, 2280h; dwFlags
0x180028db4  xor     edx, edx; dwEncodingType
0x180028db6  mov     [rsp+48h+pvPara], 0; pvPara
0x180028dbf  xor     r8d, r8d; hCryptProv
0x180028dc2  lea     ecx, [rdx+2]; lpszStoreProvider
0x180028dc5  call    cs:__imp_CertOpenStore
0x180028dcb  mov     rsi, rax
0x180028dce  test    rax, rax
0x180028dd1  jnz     short loc_180028E0E
0x180028dd3  call    cs:__imp_GetLastError
0x180028dd9  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180028de0  jz      short loc_180028E04
0x180028de2  test    eax, eax
0x180028de4  jle     short loc_180028DEE
0x180028de6  movzx   eax, ax
0x180028de9  or      eax, 80070000h
0x180028dee  mov     r9d, eax
0x180028df1  lea     r8, aEnrollmenttoke_5; "EnrollmentToken::GenerateAETCertsStore "...
0x180028df8  lea     rdx, EnterpriseAppMgmtSvcError
0x180028dff  call    McTemplateU0zq_EventWriteTransfer
0x180028e04  mov     ebx, 80004005h
0x180028e09  jmp     loc_180028F38
0x180028e0e  lea     r9, [rsp+48h+cbCertEncoded]; int *
0x180028e13  xor     r8d, r8d; unsigned __int8 *
0x180028e16  mov     edx, 504h; int
0x180028e1b  lea     rcx, aMiidvtccaqwgaw; "MIIDvTCCAqWgAwIBAgIQD2tVL56/kHsPZimpvfT"...
0x180028e22  call    ?Base64Decode@ATL@@YAHPEBDHPEAEPEAH@Z; ATL::Base64Decode(char const *,int,uchar *,int *)
0x180028e27  mov     ecx, [rsp+48h+cbCertEncoded]; unsigned __int64
0x180028e2b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028e32  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180028e37  mov     rbp, rax
0x180028e3a  test    rax, rax
0x180028e3d  jnz     short loc_180028E49
0x180028e3f  mov     ebx, 8007000Eh
0x180028e44  jmp     loc_180028F18
0x180028e49  lea     r9, [rsp+48h+cbCertEncoded]; int *
0x180028e4e  mov     r8, rbp; unsigned __int8 *
0x180028e51  mov     edx, 504h; int
0x180028e56  lea     rcx, aMiidvtccaqwgaw; "MIIDvTCCAqWgAwIBAgIQD2tVL56/kHsPZimpvfT"...
0x180028e5d  call    ?Base64Decode@ATL@@YAHPEBDHPEAEPEAH@Z; ATL::Base64Decode(char const *,int,uchar *,int *)
0x180028e62  test    eax, eax
0x180028e64  jnz     short loc_180028E8E
0x180028e66  call    cs:__imp_GetLastError
0x180028e6c  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180028e73  jz      loc_180028F13
0x180028e79  test    eax, eax
0x180028e7b  jle     short loc_180028E85
0x180028e7d  movzx   eax, ax
0x180028e80  or      eax, 80070000h
0x180028e85  lea     r8, aEnrollmenttoke_4; "EnrollmentToken::GenerateAETCertsStore "...
0x180028e8c  jmp     short loc_180028F04
0x180028e8e  mov     r9d, [rsp+48h+cbCertEncoded]; cbCertEncoded
0x180028e93  mov     r8, rbp; pbCertEncoded
0x180028e96  mov     [rsp+48h+ppCertContext], 0; ppCertContext
0x180028e9f  mov     edx, 10001h; dwCertEncodingType
0x180028ea4  mov     rcx, rsi; hCertStore
0x180028ea7  mov     dword ptr [rsp+48h+pvPara], 3; dwAddDisposition
0x180028eaf  call    cs:__imp_CertAddEncodedCertificateToStore
0x180028eb5  test    eax, eax
0x180028eb7  jz      short loc_180028EE2
0x180028eb9  mov     [rsp+48h+ppCertContext], 0; ppCertContext
0x180028ec2  mov     r9d, r14d; cbCertEncoded
0x180028ec5  mov     r8, rbx; pbCertEncoded
0x180028ec8  mov     dword ptr [rsp+48h+pvPara], 3; dwAddDisposition
0x180028ed0  mov     edx, 10001h; dwCertEncodingType
0x180028ed5  mov     rcx, rsi; hCertStore
0x180028ed8  call    cs:__imp_CertAddEncodedCertificateToStore
0x180028ede  test    eax, eax
0x180028ee0  jnz     short loc_180028F2A
0x180028ee2  call    cs:__imp_GetLastError
0x180028ee8  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits, 2
0x180028eef  jz      short loc_180028F13
0x180028ef1  test    eax, eax
0x180028ef3  jle     short loc_180028EFD
0x180028ef5  movzx   eax, ax
0x180028ef8  or      eax, 80070000h
0x180028efd  lea     r8, aEnrollmenttoke_0; "EnrollmentToken::GenerateAETCertsStore "...
0x180028f04  mov     r9d, eax
0x180028f07  lea     rdx, EnterpriseAppMgmtSvcError
0x180028f0e  call    McTemplateU0zq_EventWriteTransfer
0x180028f13  mov     ebx, 80004005h
0x180028f18  xor     edx, edx; dwFlags
0x180028f1a  mov     rcx, rsi; hCertStore
0x180028f1d  call    cs:__imp_CertCloseStore
0x180028f23  test    rbp, rbp
0x180028f26  jz      short loc_180028F38
0x180028f28  jmp     short loc_180028F2F
0x180028f2a  xor     ebx, ebx
0x180028f2c  mov     [rdi], rsi
0x180028f2f  mov     rcx, rbp
0x180028f32  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180028f38  mov     rbp, [rsp+48h+arg_10]
0x180028f3d  mov     eax, ebx
0x180028f3f  mov     rbx, [rsp+48h+arg_8]
0x180028f44  add     rsp, 30h
0x180028f48  pop     r14
0x180028f4a  pop     rdi
0x180028f4b  pop     rsi
0x180028f4c  retn
```
