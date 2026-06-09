# CreateSubCAContext(wchar_t const *,void * *)

- ea: `0x180057f74`
- end: `0x18005811a`
- name: `?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z`
- size: `422`
- prototype: `__int64 __fastcall(LPCWSTR pszString, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180057d60`

## callees

- `0x18000dc6c`
- `0x18000dce4`
- `0x1800110fc`
- `0x180057f74`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057fe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005805c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005809b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057fe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005805c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058087`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005809b`
- `CRYPT32!CryptStringToBinaryW` at `0x180057fdb`
- `CRYPT32!CryptStringToBinaryW` at `0x180058032`
- `CRYPT32!CryptStringToBinaryW` at `0x180057fdb`
- `CRYPT32!CryptStringToBinaryW` at `0x180058032`
- `CRYPT32!CertFreeCertificateContext` at `0x1800580df`
- `CRYPT32!CertFreeCertificateContext` at `0x1800580df`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18005807d`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18005807d`
- `CRYPT32!CertCreateCertificateContext` at `0x180058049`
- `CRYPT32!CertCreateCertificateContext` at `0x180058049`

## string_xrefs

- `0x1800580b8`: `CreateSubCAContext failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CreateSubCAContext(LPCWSTR pszString, void **a2)
{
  signed int v3; // edi
  BYTE *v4; // rbx
  const CERT_CONTEXT *CertificateContext; // rbp
  __int64 v6; // rsi
  signed int v8; // eax
  signed int LastError; // eax
  signed int v10; // ecx
  signed int v11; // eax
  DWORD cbCertEncoded; // [rsp+40h] [rbp-38h] BYREF

  v3 = 0;
  cbCertEncoded = 0;
  v4 = 0;
  CertificateContext = 0;
  v6 = -1;
  do
    ++v6;
  while ( pszString[v6] );
  if ( !CryptStringToBinaryW(pszString, v6, 6u, 0, &cbCertEncoded, 0, 0) )
    goto LABEL_13;
  v4 = (BYTE *)SusAlloc(cbCertEncoded);
  if ( v4 )
  {
    if ( !CryptStringToBinaryW(pszString, v6, 6u, v4, &cbCertEncoded, 0, 0) )
    {
LABEL_13:
      LastError = GetLastError();
      v10 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v10 = LastError;
      if ( v10 >= 0 )
      {
        v3 = -2147467259;
      }
      else
      {
        v11 = GetLastError();
        v3 = (unsigned __int16)v11 | 0x80070000;
        if ( v11 <= 0 )
          v3 = v11;
      }
LABEL_20:
      if ( v3 >= 0 )
        goto LABEL_22;
      goto LABEL_21;
    }
    CertificateContext = CertCreateCertificateContext(1u, v4, cbCertEncoded);
    if ( CertificateContext )
      goto LABEL_29;
    v8 = GetLastError();
    v3 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v3 = v8;
    if ( v3 >= 0 )
    {
LABEL_29:
      if ( CertAddCertificateContextToStore(*a2, CertificateContext, 1u, 0) )
        goto LABEL_20;
      goto LABEL_13;
    }
  }
  else
  {
    v3 = -2147467261;
  }
LABEL_21:
  WUTrace(0, 0, 32, 1);
LABEL_22:
  if ( CertificateContext )
    CertFreeCertificateContext(CertificateContext);
  if ( v4 )
    SusFree(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180057f74  mov     [rsp+arg_10], rbx
0x180057f79  mov     [rsp+arg_18], rbp
0x180057f7e  push    rsi
0x180057f7f  push    rdi
0x180057f80  push    r12
0x180057f82  push    r14
0x180057f84  push    r15
0x180057f86  sub     rsp, 50h
0x180057f8a  mov     rax, cs:__security_cookie
0x180057f91  xor     rax, rsp
0x180057f94  mov     [rsp+78h+var_30], rax
0x180057f99  xor     r12d, r12d
0x180057f9c  mov     r15, rdx
0x180057f9f  mov     edi, r12d
0x180057fa2  mov     [rsp+78h+cbCertEncoded], r12d
0x180057fa7  mov     ebx, r12d
0x180057faa  mov     ebp, r12d
0x180057fad  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180057fb1  mov     r14, rcx
0x180057fb4  inc     rsi
0x180057fb7  cmp     [rcx+rsi*2], r12w
0x180057fbc  jnz     short loc_180057FB4
0x180057fbe  xor     r9d, r9d; pbBinary
0x180057fc1  mov     [rsp+78h+pdwFlags], r12; pdwFlags
0x180057fc6  lea     rax, [rsp+78h+cbCertEncoded]
0x180057fcb  mov     [rsp+78h+pdwSkip], r12; pdwSkip
0x180057fd0  mov     edx, esi; cchString
0x180057fd2  mov     [rsp+78h+pcbBinary], rax; pcbBinary
0x180057fd7  lea     r8d, [r9+6]; dwFlags
0x180057fdb  call    cs:__imp_CryptStringToBinaryW
0x180057fe1  test    eax, eax
0x180057fe3  jnz     short loc_180057FF5
0x180057fe5  call    cs:__imp_GetLastError
0x180057feb  mov     esi, 80070000h
0x180057ff0  jmp     loc_18005808D
0x180057ff5  mov     ecx, [rsp+78h+cbCertEncoded]; unsigned __int64
0x180057ff9  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x180057ffe  mov     rbx, rax
0x180058001  test    rax, rax
0x180058004  jnz     short loc_180058010
0x180058006  mov     edi, 80004003h
0x18005800b  jmp     loc_1800580B6
0x180058010  mov     [rsp+78h+pdwFlags], r12; pdwFlags
0x180058015  lea     rax, [rsp+78h+cbCertEncoded]
0x18005801a  mov     [rsp+78h+pdwSkip], r12; pdwSkip
0x18005801f  mov     r9, rbx; pbBinary
0x180058022  mov     r8d, 6; dwFlags
0x180058028  mov     [rsp+78h+pcbBinary], rax; pcbBinary
0x18005802d  mov     edx, esi; cchString
0x18005802f  mov     rcx, r14; pszString
0x180058032  call    cs:__imp_CryptStringToBinaryW
0x180058038  test    eax, eax
0x18005803a  jz      short loc_180057FE5
0x18005803c  mov     r8d, [rsp+78h+cbCertEncoded]; cbCertEncoded
0x180058041  mov     rdx, rbx; pbCertEncoded
0x180058044  mov     ecx, 1; dwCertEncodingType
0x180058049  call    cs:__imp_CertCreateCertificateContext
0x18005804f  mov     rbp, rax
0x180058052  mov     esi, 80070000h
0x180058057  test    rax, rax
0x18005805a  jnz     short loc_180058070
0x18005805c  call    cs:__imp_GetLastError
0x180058062  movzx   edi, ax
0x180058065  or      edi, esi
0x180058067  test    eax, eax
0x180058069  cmovle  edi, eax
0x18005806c  test    edi, edi
0x18005806e  js      short loc_1800580B6
0x180058070  mov     rcx, [r15]; hCertStore
0x180058073  xor     r9d, r9d; ppStoreContext
0x180058076  mov     rdx, rbp; pCertContext
0x180058079  lea     r8d, [r9+1]; dwAddDisposition
0x18005807d  call    cs:__imp_CertAddCertificateContextToStore
0x180058083  test    eax, eax
0x180058085  jnz     short loc_1800580B2
0x180058087  call    cs:__imp_GetLastError
0x18005808d  movzx   ecx, ax
0x180058090  or      ecx, esi
0x180058092  test    eax, eax
0x180058094  cmovle  ecx, eax
0x180058097  test    ecx, ecx
0x180058099  jns     short loc_1800580AD
0x18005809b  call    cs:__imp_GetLastError
0x1800580a1  movzx   edi, ax
0x1800580a4  or      edi, esi
0x1800580a6  test    eax, eax
0x1800580a8  cmovle  edi, eax
0x1800580ab  jmp     short loc_1800580B2
0x1800580ad  mov     edi, 80004005h
0x1800580b2  test    edi, edi
0x1800580b4  jns     short loc_1800580D7
0x1800580b6  xor     edx, edx
0x1800580b8  lea     rax, aCreatesubcacon; "CreateSubCAContext failed"
0x1800580bf  mov     [rsp+78h+pdwSkip], rax
0x1800580c4  xor     ecx, ecx
0x1800580c6  mov     dword ptr [rsp+78h+pcbBinary], edi
0x1800580ca  lea     r9d, [rdx+1]
0x1800580ce  lea     r8d, [rdx+20h]
0x1800580d2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800580d7  test    rbp, rbp
0x1800580da  jz      short loc_1800580E5
0x1800580dc  mov     rcx, rbp; pCertContext
0x1800580df  call    cs:__imp_CertFreeCertificateContext
0x1800580e5  test    rbx, rbx
0x1800580e8  jz      short loc_1800580F2
0x1800580ea  mov     rcx, rbx; lpMem
0x1800580ed  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800580f2  mov     eax, edi
0x1800580f4  mov     rcx, [rsp+78h+var_30]
0x1800580f9  xor     rcx, rsp; StackCookie
0x1800580fc  call    __security_check_cookie
0x180058101  lea     r11, [rsp+78h+var_28]
0x180058106  mov     rbx, [r11+40h]
0x18005810a  mov     rbp, [r11+48h]
0x18005810e  mov     rsp, r11
0x180058111  pop     r15
0x180058113  pop     r14
0x180058115  pop     r12
0x180058117  pop     rdi
0x180058118  pop     rsi
0x180058119  retn
```
