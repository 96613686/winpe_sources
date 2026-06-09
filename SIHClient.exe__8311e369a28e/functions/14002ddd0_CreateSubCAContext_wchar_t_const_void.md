# CreateSubCAContext(wchar_t const *,void * *)

- ea: `0x14002ddd0`
- end: `0x14002df76`
- name: `?CreateSubCAContext@@YAJPEB_WPEAPEAX@Z`
- size: `422`
- prototype: `__int64 __fastcall(LPCWSTR pszString, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002dbbc`

## callees

- `0x14000cdb8`
- `0x14000ce30`
- `0x1400154b4`
- `0x14002ddd0`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002de41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002deb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002dee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002def7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002de41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002deb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002dee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002def7`
- `CRYPT32!CryptStringToBinaryW` at `0x14002de37`
- `CRYPT32!CryptStringToBinaryW` at `0x14002de8e`
- `CRYPT32!CryptStringToBinaryW` at `0x14002de37`
- `CRYPT32!CryptStringToBinaryW` at `0x14002de8e`
- `CRYPT32!CertCreateCertificateContext` at `0x14002dea5`
- `CRYPT32!CertCreateCertificateContext` at `0x14002dea5`
- `CRYPT32!CertFreeCertificateContext` at `0x14002df3b`
- `CRYPT32!CertFreeCertificateContext` at `0x14002df3b`
- `CRYPT32!CertAddCertificateContextToStore` at `0x14002ded9`
- `CRYPT32!CertAddCertificateContextToStore` at `0x14002ded9`

## string_xrefs

- `0x14002df14`: `CreateSubCAContext failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  DWORD *pcbBinary; // [rsp+20h] [rbp-58h]
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
  LODWORD(pcbBinary) = v3;
  WUTrace(0, 0, 32, 1, pcbBinary, L"CreateSubCAContext failed");
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
0x14002ddd0  mov     [rsp+arg_10], rbx
0x14002ddd5  mov     [rsp+arg_18], rbp
0x14002ddda  push    rsi
0x14002dddb  push    rdi
0x14002dddc  push    r12
0x14002ddde  push    r14
0x14002dde0  push    r15
0x14002dde2  sub     rsp, 50h
0x14002dde6  mov     rax, cs:__security_cookie
0x14002dded  xor     rax, rsp
0x14002ddf0  mov     [rsp+78h+var_30], rax
0x14002ddf5  xor     r12d, r12d
0x14002ddf8  mov     r15, rdx
0x14002ddfb  mov     edi, r12d
0x14002ddfe  mov     [rsp+78h+cbCertEncoded], r12d
0x14002de03  mov     ebx, r12d
0x14002de06  mov     ebp, r12d
0x14002de09  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14002de0d  mov     r14, rcx
0x14002de10  inc     rsi
0x14002de13  cmp     [rcx+rsi*2], r12w
0x14002de18  jnz     short loc_14002DE10
0x14002de1a  xor     r9d, r9d; pbBinary
0x14002de1d  mov     [rsp+78h+pdwFlags], r12; pdwFlags
0x14002de22  lea     rax, [rsp+78h+cbCertEncoded]
0x14002de27  mov     [rsp+78h+pdwSkip], r12; pdwSkip
0x14002de2c  mov     edx, esi; cchString
0x14002de2e  mov     [rsp+78h+pcbBinary], rax; pcbBinary
0x14002de33  lea     r8d, [r9+6]; dwFlags
0x14002de37  call    cs:__imp_CryptStringToBinaryW
0x14002de3d  test    eax, eax
0x14002de3f  jnz     short loc_14002DE51
0x14002de41  call    cs:__imp_GetLastError
0x14002de47  mov     esi, 80070000h
0x14002de4c  jmp     loc_14002DEE9
0x14002de51  mov     ecx, [rsp+78h+cbCertEncoded]; unsigned __int64
0x14002de55  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x14002de5a  mov     rbx, rax
0x14002de5d  test    rax, rax
0x14002de60  jnz     short loc_14002DE6C
0x14002de62  mov     edi, 80004003h
0x14002de67  jmp     loc_14002DF12
0x14002de6c  mov     [rsp+78h+pdwFlags], r12; pdwFlags
0x14002de71  lea     rax, [rsp+78h+cbCertEncoded]
0x14002de76  mov     [rsp+78h+pdwSkip], r12; pdwSkip
0x14002de7b  mov     r9, rbx; pbBinary
0x14002de7e  mov     r8d, 6; dwFlags
0x14002de84  mov     [rsp+78h+pcbBinary], rax; pcbBinary
0x14002de89  mov     edx, esi; cchString
0x14002de8b  mov     rcx, r14; pszString
0x14002de8e  call    cs:__imp_CryptStringToBinaryW
0x14002de94  test    eax, eax
0x14002de96  jz      short loc_14002DE41
0x14002de98  mov     r8d, [rsp+78h+cbCertEncoded]; cbCertEncoded
0x14002de9d  mov     rdx, rbx; pbCertEncoded
0x14002dea0  mov     ecx, 1; dwCertEncodingType
0x14002dea5  call    cs:__imp_CertCreateCertificateContext
0x14002deab  mov     rbp, rax
0x14002deae  mov     esi, 80070000h
0x14002deb3  test    rax, rax
0x14002deb6  jnz     short loc_14002DECC
0x14002deb8  call    cs:__imp_GetLastError
0x14002debe  movzx   edi, ax
0x14002dec1  or      edi, esi
0x14002dec3  test    eax, eax
0x14002dec5  cmovle  edi, eax
0x14002dec8  test    edi, edi
0x14002deca  js      short loc_14002DF12
0x14002decc  mov     rcx, [r15]; hCertStore
0x14002decf  xor     r9d, r9d; ppStoreContext
0x14002ded2  mov     rdx, rbp; pCertContext
0x14002ded5  lea     r8d, [r9+1]; dwAddDisposition
0x14002ded9  call    cs:__imp_CertAddCertificateContextToStore
0x14002dedf  test    eax, eax
0x14002dee1  jnz     short loc_14002DF0E
0x14002dee3  call    cs:__imp_GetLastError
0x14002dee9  movzx   ecx, ax
0x14002deec  or      ecx, esi
0x14002deee  test    eax, eax
0x14002def0  cmovle  ecx, eax
0x14002def3  test    ecx, ecx
0x14002def5  jns     short loc_14002DF09
0x14002def7  call    cs:__imp_GetLastError
0x14002defd  movzx   edi, ax
0x14002df00  or      edi, esi
0x14002df02  test    eax, eax
0x14002df04  cmovle  edi, eax
0x14002df07  jmp     short loc_14002DF0E
0x14002df09  mov     edi, 80004005h
0x14002df0e  test    edi, edi
0x14002df10  jns     short loc_14002DF33
0x14002df12  xor     edx, edx
0x14002df14  lea     rax, aCreatesubcacon; "CreateSubCAContext failed"
0x14002df1b  mov     [rsp+78h+pdwSkip], rax
0x14002df20  xor     ecx, ecx
0x14002df22  mov     dword ptr [rsp+78h+pcbBinary], edi
0x14002df26  lea     r9d, [rdx+1]
0x14002df2a  lea     r8d, [rdx+20h]
0x14002df2e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002df33  test    rbp, rbp
0x14002df36  jz      short loc_14002DF41
0x14002df38  mov     rcx, rbp; pCertContext
0x14002df3b  call    cs:__imp_CertFreeCertificateContext
0x14002df41  test    rbx, rbx
0x14002df44  jz      short loc_14002DF4E
0x14002df46  mov     rcx, rbx; lpMem
0x14002df49  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002df4e  mov     eax, edi
0x14002df50  mov     rcx, [rsp+78h+var_30]
0x14002df55  xor     rcx, rsp; StackCookie
0x14002df58  call    __security_check_cookie
0x14002df5d  lea     r11, [rsp+78h+var_28]
0x14002df62  mov     rbx, [r11+40h]
0x14002df66  mov     rbp, [r11+48h]
0x14002df6a  mov     rsp, r11
0x14002df6d  pop     r15
0x14002df6f  pop     r14
0x14002df71  pop     r12
0x14002df73  pop     rdi
0x14002df74  pop     rsi
0x14002df75  retn
```
