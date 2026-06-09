# CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x18001943c`
- end: `0x180019610`
- name: `?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `468`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180008360`
- `0x18001a0a4`

## callees

- `0x18000ae60`
- `0x18000af7c`
- `0x18000b32c`
- `0x18000b3c4`
- `0x18001943c`
- `0x18001995c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800195ef`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800195ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019567`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800195fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800195fa`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001955d`
- `CRYPT32!CryptDecodeObjectEx` at `0x18001955d`

## string_xrefs

- `0x18001947a`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180019494`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800194b6`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800194e3`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18001950f`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180019570`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x1800195c4`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180019516`: `%s: Extension was not found in the certificate. OID: %hs.`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindExtensionGuidValueByOid(
        const char *a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rsi
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // rdx
  struct _CERT_EXTENSION *ExtensionByOid; // rax
  __int64 LastError; // rdi
  int v11; // eax
  HLOCAL hMem[5]; // [rsp+40h] [rbp-28h] BYREF
  DWORD pcbStructInfo; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 *v15; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  hMem[0] = 0;
  pcbStructInfo = 0;
  v15 = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"CertificateUtil::FindExtensionGuidValueByOid",
      L"pcszOid");
    v8 = L"pcszOid";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindExtensionGuidValueByOid", v8);
    goto LABEL_18;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"CertificateUtil::FindExtensionGuidValueByOid",
      L"ppszOutBuffer");
    v8 = L"ppszOutBuffer";
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"CertificateUtil::FindExtensionGuidValueByOid",
      &stru_18001E5B8);
    v8 = (const unsigned __int16 *)&stru_18001E5B8;
    goto LABEL_3;
  }
  *a3 = 0;
  ExtensionByOid = CertificateUtil::FindExtensionByOid(a1, a2);
  if ( ExtensionByOid )
  {
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
      v11 = CertificateUtil::GuidStringFromByteArray(*((const unsigned __int8 **)hMem[0] + 1), *(_DWORD *)hMem[0], &v15);
      v7 = v11;
      if ( v11 >= 0 )
      {
        *a3 = v15;
      }
      else
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"CertificateUtil::FindExtensionGuidValueByOid",
          L"CertificateUtil::GuidStringFromByteArray",
          (unsigned int)v11);
        v3 = v15;
      }
    }
    else
    {
      LastError = GetLastError();
      Logger::TraceError(
        L"%s: CryptDecodeObjectEx failed with error code: 0x%08x",
        L"CertificateUtil::FindExtensionGuidValueByOid",
        LastError);
      v7 = 0;
      if ( (_DWORD)LastError )
      {
        if ( (int)LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        else
          v7 = LastError;
      }
    }
  }
  else
  {
    Logger::TraceVerbose(
      L"%s: Extension was not found in the certificate. OID: %hs.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      a1);
    v7 = -2146885628;
  }
LABEL_18:
  operator delete(v3);
  LocalFree(hMem[0]);
  return v7;
}

```

## disassembly

```asm
0x18001943c  mov     rax, rsp
0x18001943f  mov     [rax+10h], rbx
0x180019443  push    rsi
0x180019444  push    rdi
0x180019445  push    r14
0x180019447  sub     rsp, 50h
0x18001944b  xor     esi, esi
0x18001944d  mov     qword ptr [rax-28h], 0
0x180019455  mov     dword ptr [rax+8], 0
0x18001945c  mov     rdi, r8
0x18001945f  mov     [rax+20h], rsi
0x180019463  mov     r14, rdx
0x180019466  mov     rbx, rcx
0x180019469  test    rcx, rcx
0x18001946c  jnz     short loc_1800194A5
0x18001946e  lea     r8, aPcszoid; "pcszOid"
0x180019475  mov     ebx, 80070057h
0x18001947a  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180019481  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x180019488  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001948d  lea     rdx, aPcszoid; "pcszOid"
0x180019494  lea     rcx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18001949b  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800194a0  jmp     loc_1800195EC
0x1800194a5  test    rdi, rdi
0x1800194a8  jnz     short loc_1800194D2
0x1800194aa  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x1800194b1  mov     ebx, 80070057h
0x1800194b6  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800194bd  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x1800194c4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800194c9  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x1800194d0  jmp     short loc_180019494
0x1800194d2  test    r14, r14
0x1800194d5  jnz     short loc_1800194FF
0x1800194d7  lea     r8, stru_18001E5B8
0x1800194de  mov     ebx, 80070057h
0x1800194e3  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800194ea  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x1800194f1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800194f6  lea     rdx, stru_18001E5B8; struct _CERT_CONTEXT *
0x1800194fd  jmp     short loc_180019494
0x1800194ff  mov     [r8], rsi
0x180019502  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x180019507  test    rax, rax
0x18001950a  jnz     short loc_18001952C
0x18001950c  mov     r8, rbx
0x18001950f  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180019516  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x18001951d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180019522  mov     ebx, 80092004h
0x180019527  jmp     loc_1800195EC
0x18001952c  mov     r9d, [rax+10h]; cbEncoded
0x180019530  lea     rcx, [rsp+68h+arg_0]
0x180019535  mov     r8, [rax+18h]; pbEncoded
0x180019539  mov     edx, 19h; lpszStructType
0x18001953e  mov     [rsp+68h+pcbStructInfo], rcx; pcbStructInfo
0x180019543  lea     rcx, [rsp+68h+hMem]
0x180019548  mov     [rsp+68h+pvStructInfo], rcx; pvStructInfo
0x18001954d  mov     ecx, [r14]; dwCertEncodingType
0x180019550  mov     [rsp+68h+pDecodePara], rsi; pDecodePara
0x180019555  mov     [rsp+68h+dwFlags], 8000h; dwFlags
0x18001955d  call    cs:__imp_CryptDecodeObjectEx
0x180019563  test    eax, eax
0x180019565  jnz     short loc_18001959C
0x180019567  call    cs:__imp_GetLastError
0x18001956d  mov     r8d, eax
0x180019570  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180019577  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x18001957e  mov     edi, eax
0x180019580  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180019585  xor     ebx, ebx
0x180019587  test    edi, edi
0x180019589  jz      short loc_1800195EC
0x18001958b  jg      short loc_180019591
0x18001958d  mov     ebx, edi
0x18001958f  jmp     short loc_1800195EC
0x180019591  movzx   ebx, di
0x180019594  or      ebx, 80070000h
0x18001959a  jmp     short loc_1800195EC
0x18001959c  mov     rcx, [rsp+68h+hMem]
0x1800195a1  lea     r8, [rsp+68h+arg_18]; unsigned __int16 **
0x1800195a9  mov     edx, [rcx]; unsigned int
0x1800195ab  mov     rcx, [rcx+8]; unsigned __int8 *
0x1800195af  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x1800195b4  mov     ebx, eax
0x1800195b6  test    eax, eax
0x1800195b8  jns     short loc_1800195E1
0x1800195ba  mov     r9d, eax
0x1800195bd  lea     r8, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x1800195c4  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x1800195cb  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800195d2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800195d7  mov     rsi, [rsp+68h+arg_18]
0x1800195df  jmp     short loc_1800195EC
0x1800195e1  mov     rax, [rsp+68h+arg_18]
0x1800195e9  mov     [rdi], rax
0x1800195ec  mov     rcx, rsi
0x1800195ef  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800195f5  mov     rcx, [rsp+68h+hMem]; hMem
0x1800195fa  call    cs:__imp_LocalFree
0x180019600  mov     eax, ebx
0x180019602  mov     rbx, [rsp+68h+arg_8]
0x180019607  add     rsp, 50h
0x18001960b  pop     r14
0x18001960d  pop     rdi
0x18001960e  pop     rsi
0x18001960f  retn
```
