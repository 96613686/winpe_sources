# CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x18007c830`
- end: `0x18007ca8e`
- name: `?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `606`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18007bee0`

## callees

- `0x180007db4`
- `0x1800084c8`
- `0x180008fdc`
- `0x18007c600`
- `0x18007c830`
- `0x18007d17c`
- `0x18007d1b8`
- `0x18007d22c`
- `0x18007d2a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ca20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ca20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007ca72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007ca72`
- `CRYPT32!CryptDecodeObjectEx` at `0x18007c958`
- `CRYPT32!CryptDecodeObjectEx` at `0x18007c958`
- `CRYPT32!CryptBinaryToStringW` at `0x18007c992`
- `CRYPT32!CryptBinaryToStringW` at `0x18007ca16`
- `CRYPT32!CryptBinaryToStringW` at `0x18007c992`
- `CRYPT32!CryptBinaryToStringW` at `0x18007ca16`

## string_xrefs

- `0x18007c867`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007c8a2`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007c8d2`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007c90d`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007c9cf`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007ca2f`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18007c914`: `%s: Extension was not found in the certificate. OID: %hs.`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindExtensionStrValueByOid(
        const char *a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // r14
  unsigned int v7; // edi
  const unsigned __int16 *v8; // rdx
  struct _CERT_EXTENSION *ExtensionByOid; // rax
  DWORD LastError; // eax
  const unsigned __int16 *v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int16 *v13; // rax
  int v14; // esi
  __int64 v15; // rdx
  HLOCAL hMem[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcchString; // [rsp+80h] [rbp+30h] BYREF
  DWORD pcbStructInfo; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  hMem[0] = 0;
  pcbStructInfo = 0;
  pcchString = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::FindExtensionStrValueByOid", L"pcszOid");
    v8 = L"pcszOid";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindExtensionStrValueByOid", v8);
    goto LABEL_24;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      L"ppszOutBuffer");
    v8 = L"ppszOutBuffer";
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      &stru_18009D3F8);
    v8 = (const unsigned __int16 *)&stru_18009D3F8;
    goto LABEL_3;
  }
  *a3 = 0;
  ExtensionByOid = CertificateUtil::FindExtensionByOid(a1, a2);
  if ( ExtensionByOid )
  {
    v7 = 0;
    if ( CryptDecodeObjectEx(
           a2->dwCertEncodingType,
           (LPCSTR)0x19,
           ExtensionByOid->Value.pbData,
           ExtensionByOid->Value.cbData,
           0x8000u,
           0,
           hMem,
           &pcbStructInfo) )
    {
      if ( CryptBinaryToStringW(*((const BYTE **)hMem[0] + 1), *(_DWORD *)hMem[0], 0x40000002u, 0, &pcchString) )
      {
        v12 = 2LL * (pcchString + 1);
        if ( !is_mul_ok(pcchString + 1, 2u) )
          v12 = -1;
        v13 = (unsigned __int16 *)operator new[](v12, (const struct std::nothrow_t *)std::nothrow);
        v3 = v13;
        if ( !v13 )
        {
          v7 = -2147024882;
          Logger::TraceCritical(
            L"%s: Out of memory. Allocation failed.",
            L"CertificateUtil::FindExtensionStrValueByOid");
          goto LABEL_24;
        }
        memset_0(v13, 0, 2LL * (pcchString + 1));
        if ( CryptBinaryToStringW(*((const BYTE **)hMem[0] + 1), *(_DWORD *)hMem[0], 0x40000002u, v3, &pcchString) )
        {
          v15 = pcchString;
          *a3 = v3;
          v3[v15] = 0;
          v3 = 0;
          goto LABEL_24;
        }
      }
      LastError = GetLastError();
      v11 = L"%s: CryptBinaryToStringW with error code: 0x%08x";
    }
    else
    {
      LastError = GetLastError();
      v11 = L"%s: CryptDecodeObjectEx with error code: 0x%08x";
    }
    v14 = LastError;
    Logger::TraceError(v11, L"CertificateUtil::FindExtensionStrValueByOid", LastError);
    if ( v14 )
    {
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      else
        v7 = v14;
    }
  }
  else
  {
    Logger::TraceVerbose(
      L"%s: Extension was not found in the certificate. OID: %hs.",
      L"CertificateUtil::FindExtensionStrValueByOid",
      a1);
    v7 = -2146885628;
  }
LABEL_24:
  operator delete(v3);
  LocalFree(hMem[0]);
  return v7;
}

```

## disassembly

```asm
0x18007c830  mov     [rsp-28h+arg_8], rbx
0x18007c835  push    rbp
0x18007c836  push    rsi
0x18007c837  push    rdi
0x18007c838  push    r14
0x18007c83a  push    r15
0x18007c83c  mov     rbp, rsp
0x18007c83f  sub     rsp, 50h
0x18007c843  xor     r14d, r14d
0x18007c846  mov     [rbp+hMem], 0
0x18007c84e  mov     [rbp+arg_18], 0
0x18007c855  mov     r15, r8
0x18007c858  mov     [rbp+pcchString], r14d
0x18007c85c  mov     rsi, rdx
0x18007c85f  mov     rbx, rcx
0x18007c862  test    rcx, rcx
0x18007c865  jnz     short loc_18007C89D
0x18007c867  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007c86e  mov     edi, 80070057h
0x18007c873  mov     rdx, rbx
0x18007c876  lea     r8, aPcszoid; "pcszOid"
0x18007c87d  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007c884  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c889  lea     rdx, aPcszoid; "pcszOid"
0x18007c890  mov     rcx, rbx; unsigned __int16 *
0x18007c893  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007c898  jmp     loc_18007CA66
0x18007c89d  test    r15, r15
0x18007c8a0  jnz     short loc_18007C8CD
0x18007c8a2  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007c8a9  mov     edi, 80070057h
0x18007c8ae  mov     rdx, rbx
0x18007c8b1  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x18007c8b8  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007c8bf  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c8c4  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x18007c8cb  jmp     short loc_18007C890
0x18007c8cd  test    rsi, rsi
0x18007c8d0  jnz     short loc_18007C8FD
0x18007c8d2  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007c8d9  mov     edi, 80070057h
0x18007c8de  mov     rdx, rbx
0x18007c8e1  lea     r8, stru_18009D3F8
0x18007c8e8  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007c8ef  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c8f4  lea     rdx, stru_18009D3F8; struct _CERT_CONTEXT *
0x18007c8fb  jmp     short loc_18007C890
0x18007c8fd  mov     [r8], r14
0x18007c900  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x18007c905  test    rax, rax
0x18007c908  jnz     short loc_18007C92A
0x18007c90a  mov     r8, rbx
0x18007c90d  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007c914  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x18007c91b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007c920  mov     edi, 80092004h
0x18007c925  jmp     loc_18007CA66
0x18007c92a  mov     r9d, [rax+10h]; cbEncoded
0x18007c92e  lea     rcx, [rbp+arg_18]
0x18007c932  mov     r8, [rax+18h]; pbEncoded
0x18007c936  xor     edi, edi
0x18007c938  mov     [rsp+50h+pcbStructInfo], rcx; pcbStructInfo
0x18007c93d  lea     rcx, [rbp+hMem]
0x18007c941  mov     [rsp+50h+pvStructInfo], rcx; pvStructInfo
0x18007c946  mov     ecx, [rsi]; dwCertEncodingType
0x18007c948  mov     [rsp+50h+pDecodePara], rdi; pDecodePara
0x18007c94d  lea     edx, [rdi+19h]; lpszStructType
0x18007c950  mov     [rsp+50h+dwFlags], 8000h; dwFlags
0x18007c958  call    cs:__imp_CryptDecodeObjectEx
0x18007c95e  test    eax, eax
0x18007c960  jnz     short loc_18007C974
0x18007c962  call    cs:__imp_GetLastError
0x18007c968  lea     rcx, aSCryptdecodeob; "%s: CryptDecodeObjectEx with error code"...
0x18007c96f  jmp     loc_18007CA2D
0x18007c974  mov     rcx, [rbp+hMem]
0x18007c978  lea     rax, [rbp+pcchString]
0x18007c97c  mov     ebx, 40000002h
0x18007c981  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x18007c986  xor     r9d, r9d; pszString
0x18007c989  mov     r8d, ebx; dwFlags
0x18007c98c  mov     edx, [rcx]; cbBinary
0x18007c98e  mov     rcx, [rcx+8]; pbBinary
0x18007c992  call    cs:__imp_CryptBinaryToStringW
0x18007c998  test    eax, eax
0x18007c99a  jz      loc_18007CA20
0x18007c9a0  mov     ecx, [rbp+pcchString]
0x18007c9a3  mov     eax, 2
0x18007c9a8  inc     ecx
0x18007c9aa  mul     rcx
0x18007c9ad  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18007c9b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007c9bb  cmovb   rax, rcx
0x18007c9bf  mov     rcx, rax; unsigned __int64
0x18007c9c2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007c9c7  mov     r14, rax
0x18007c9ca  test    rax, rax
0x18007c9cd  jnz     short loc_18007C9E9
0x18007c9cf  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007c9d6  mov     edi, 8007000Eh
0x18007c9db  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18007c9e2  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18007c9e7  jmp     short loc_18007CA66
0x18007c9e9  mov     r8d, [rbp+pcchString]
0x18007c9ed  xor     edx, edx; Val
0x18007c9ef  inc     r8d
0x18007c9f2  mov     rcx, r14; void *
0x18007c9f5  add     r8, r8; Size
0x18007c9f8  call    memset_0
0x18007c9fd  mov     rcx, [rbp+hMem]
0x18007ca01  lea     rax, [rbp+pcchString]
0x18007ca05  mov     r9, r14; pszString
0x18007ca08  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x18007ca0d  mov     r8d, ebx; dwFlags
0x18007ca10  mov     edx, [rcx]; cbBinary
0x18007ca12  mov     rcx, [rcx+8]; pbBinary
0x18007ca16  call    cs:__imp_CryptBinaryToStringW
0x18007ca1c  test    eax, eax
0x18007ca1e  jnz     short loc_18007CA56
0x18007ca20  call    cs:__imp_GetLastError
0x18007ca26  lea     rcx, aSCryptbinaryto; "%s: CryptBinaryToStringW with error cod"...
0x18007ca2d  mov     esi, eax
0x18007ca2f  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007ca36  mov     r8d, eax
0x18007ca39  mov     rdx, rbx
0x18007ca3c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007ca41  test    esi, esi
0x18007ca43  jz      short loc_18007CA66
0x18007ca45  jg      short loc_18007CA4B
0x18007ca47  mov     edi, esi
0x18007ca49  jmp     short loc_18007CA66
0x18007ca4b  movzx   edi, si
0x18007ca4e  or      edi, 80070000h
0x18007ca54  jmp     short loc_18007CA66
0x18007ca56  mov     edx, [rbp+pcchString]
0x18007ca59  xor     ecx, ecx
0x18007ca5b  mov     [r15], r14
0x18007ca5e  mov     [r14+rdx*2], cx
0x18007ca63  xor     r14d, r14d
0x18007ca66  mov     rcx, r14; Block
0x18007ca69  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007ca6e  mov     rcx, [rbp+hMem]; hMem
0x18007ca72  call    cs:__imp_LocalFree
0x18007ca78  mov     rbx, [rsp+50h+arg_8]
0x18007ca80  mov     eax, edi
0x18007ca82  add     rsp, 50h
0x18007ca86  pop     r15
0x18007ca88  pop     r14
0x18007ca8a  pop     rdi
0x18007ca8b  pop     rsi
0x18007ca8c  pop     rbp
0x18007ca8d  retn
```
