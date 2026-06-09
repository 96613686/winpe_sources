# CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x1800ab4b0`
- end: `0x1800ab70e`
- name: `?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `606`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x1800ab310`

## callees

- `0x18001ea7c`
- `0x1800325dc`
- `0x18004a8ec`
- `0x18004aa08`
- `0x18004d79c`
- `0x18005db30`
- `0x18005dd44`
- `0x1800606dc`
- `0x1800ab4b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab5e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab5e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab6a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab6f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab6f2`
- `CRYPT32!CryptBinaryToStringW` at `0x1800ab612`
- `CRYPT32!CryptBinaryToStringW` at `0x1800ab696`
- `CRYPT32!CryptBinaryToStringW` at `0x1800ab612`
- `CRYPT32!CryptBinaryToStringW` at `0x1800ab696`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800ab5d8`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800ab5d8`

## string_xrefs

- `0x1800ab4e7`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800ab522`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800ab552`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800ab58d`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800ab64f`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800ab6af`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x1800ab594`: `%s: Extension was not found in the certificate. OID: %hs.`

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
      &stru_1800EA828);
    v8 = (const unsigned __int16 *)&stru_1800EA828;
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
        v13 = (unsigned __int16 *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
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
0x1800ab4b0  mov     [rsp-28h+arg_8], rbx
0x1800ab4b5  push    rbp
0x1800ab4b6  push    rsi
0x1800ab4b7  push    rdi
0x1800ab4b8  push    r14
0x1800ab4ba  push    r15
0x1800ab4bc  mov     rbp, rsp
0x1800ab4bf  sub     rsp, 50h
0x1800ab4c3  xor     r14d, r14d
0x1800ab4c6  mov     [rbp+hMem], 0
0x1800ab4ce  mov     [rbp+arg_18], 0
0x1800ab4d5  mov     r15, r8
0x1800ab4d8  mov     [rbp+pcchString], r14d
0x1800ab4dc  mov     rsi, rdx
0x1800ab4df  mov     rbx, rcx
0x1800ab4e2  test    rcx, rcx
0x1800ab4e5  jnz     short loc_1800AB51D
0x1800ab4e7  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800ab4ee  mov     edi, 80070057h
0x1800ab4f3  mov     rdx, rbx
0x1800ab4f6  lea     r8, aPcszoid; "pcszOid"
0x1800ab4fd  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800ab504  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ab509  lea     rdx, aPcszoid; "pcszOid"
0x1800ab510  mov     rcx, rbx; unsigned __int16 *
0x1800ab513  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800ab518  jmp     loc_1800AB6E6
0x1800ab51d  test    r15, r15
0x1800ab520  jnz     short loc_1800AB54D
0x1800ab522  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800ab529  mov     edi, 80070057h
0x1800ab52e  mov     rdx, rbx
0x1800ab531  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x1800ab538  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800ab53f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ab544  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x1800ab54b  jmp     short loc_1800AB510
0x1800ab54d  test    rsi, rsi
0x1800ab550  jnz     short loc_1800AB57D
0x1800ab552  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800ab559  mov     edi, 80070057h
0x1800ab55e  mov     rdx, rbx
0x1800ab561  lea     r8, stru_1800EA828
0x1800ab568  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800ab56f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ab574  lea     rdx, stru_1800EA828; struct _CERT_CONTEXT *
0x1800ab57b  jmp     short loc_1800AB510
0x1800ab57d  mov     [r8], r14
0x1800ab580  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x1800ab585  test    rax, rax
0x1800ab588  jnz     short loc_1800AB5AA
0x1800ab58a  mov     r8, rbx
0x1800ab58d  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800ab594  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x1800ab59b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800ab5a0  mov     edi, 80092004h
0x1800ab5a5  jmp     loc_1800AB6E6
0x1800ab5aa  mov     r9d, [rax+10h]; cbEncoded
0x1800ab5ae  lea     rcx, [rbp+arg_18]
0x1800ab5b2  mov     r8, [rax+18h]; pbEncoded
0x1800ab5b6  xor     edi, edi
0x1800ab5b8  mov     [rsp+50h+pcbStructInfo], rcx; pcbStructInfo
0x1800ab5bd  lea     rcx, [rbp+hMem]
0x1800ab5c1  mov     [rsp+50h+pvStructInfo], rcx; pvStructInfo
0x1800ab5c6  mov     ecx, [rsi]; dwCertEncodingType
0x1800ab5c8  mov     [rsp+50h+pDecodePara], rdi; pDecodePara
0x1800ab5cd  lea     edx, [rdi+19h]; lpszStructType
0x1800ab5d0  mov     [rsp+50h+dwFlags], 8000h; dwFlags
0x1800ab5d8  call    cs:__imp_CryptDecodeObjectEx
0x1800ab5de  test    eax, eax
0x1800ab5e0  jnz     short loc_1800AB5F4
0x1800ab5e2  call    cs:__imp_GetLastError
0x1800ab5e8  lea     rcx, aSCryptdecodeob; "%s: CryptDecodeObjectEx with error code"...
0x1800ab5ef  jmp     loc_1800AB6AD
0x1800ab5f4  mov     rcx, [rbp+hMem]
0x1800ab5f8  lea     rax, [rbp+pcchString]
0x1800ab5fc  mov     ebx, 40000002h
0x1800ab601  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x1800ab606  xor     r9d, r9d; pszString
0x1800ab609  mov     r8d, ebx; dwFlags
0x1800ab60c  mov     edx, [rcx]; cbBinary
0x1800ab60e  mov     rcx, [rcx+8]; pbBinary
0x1800ab612  call    cs:__imp_CryptBinaryToStringW
0x1800ab618  test    eax, eax
0x1800ab61a  jz      loc_1800AB6A0
0x1800ab620  mov     ecx, [rbp+pcchString]
0x1800ab623  mov     eax, 2
0x1800ab628  inc     ecx
0x1800ab62a  mul     rcx
0x1800ab62d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ab634  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ab63b  cmovb   rax, rcx
0x1800ab63f  mov     rcx, rax; unsigned __int64
0x1800ab642  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800ab647  mov     r14, rax
0x1800ab64a  test    rax, rax
0x1800ab64d  jnz     short loc_1800AB669
0x1800ab64f  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800ab656  mov     edi, 8007000Eh
0x1800ab65b  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x1800ab662  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800ab667  jmp     short loc_1800AB6E6
0x1800ab669  mov     r8d, [rbp+pcchString]
0x1800ab66d  xor     edx, edx; Val
0x1800ab66f  inc     r8d
0x1800ab672  mov     rcx, r14; void *
0x1800ab675  add     r8, r8; Size
0x1800ab678  call    memset_0
0x1800ab67d  mov     rcx, [rbp+hMem]
0x1800ab681  lea     rax, [rbp+pcchString]
0x1800ab685  mov     r9, r14; pszString
0x1800ab688  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x1800ab68d  mov     r8d, ebx; dwFlags
0x1800ab690  mov     edx, [rcx]; cbBinary
0x1800ab692  mov     rcx, [rcx+8]; pbBinary
0x1800ab696  call    cs:__imp_CryptBinaryToStringW
0x1800ab69c  test    eax, eax
0x1800ab69e  jnz     short loc_1800AB6D6
0x1800ab6a0  call    cs:__imp_GetLastError
0x1800ab6a6  lea     rcx, aSCryptbinaryto; "%s: CryptBinaryToStringW with error cod"...
0x1800ab6ad  mov     esi, eax
0x1800ab6af  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x1800ab6b6  mov     r8d, eax
0x1800ab6b9  mov     rdx, rbx
0x1800ab6bc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ab6c1  test    esi, esi
0x1800ab6c3  jz      short loc_1800AB6E6
0x1800ab6c5  jg      short loc_1800AB6CB
0x1800ab6c7  mov     edi, esi
0x1800ab6c9  jmp     short loc_1800AB6E6
0x1800ab6cb  movzx   edi, si
0x1800ab6ce  or      edi, 80070000h
0x1800ab6d4  jmp     short loc_1800AB6E6
0x1800ab6d6  mov     edx, [rbp+pcchString]
0x1800ab6d9  xor     ecx, ecx
0x1800ab6db  mov     [r15], r14
0x1800ab6de  mov     [r14+rdx*2], cx
0x1800ab6e3  xor     r14d, r14d
0x1800ab6e6  mov     rcx, r14; Block
0x1800ab6e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ab6ee  mov     rcx, [rbp+hMem]; hMem
0x1800ab6f2  call    cs:__imp_LocalFree
0x1800ab6f8  mov     rbx, [rsp+50h+arg_8]
0x1800ab700  mov     eax, edi
0x1800ab702  add     rsp, 50h
0x1800ab706  pop     r15
0x1800ab708  pop     r14
0x1800ab70a  pop     rdi
0x1800ab70b  pop     rsi
0x1800ab70c  pop     rbp
0x1800ab70d  retn
```
