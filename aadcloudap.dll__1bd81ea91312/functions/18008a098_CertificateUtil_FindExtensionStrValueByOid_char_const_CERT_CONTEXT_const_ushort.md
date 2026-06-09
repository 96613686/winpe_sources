# CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x18008a098`
- end: `0x18008a2f7`
- name: `?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `607`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180089748`

## callees

- `0x180004a24`
- `0x180005f24`
- `0x180089e68`
- `0x18008a098`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a2d1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a1ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a1ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a288`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a2db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a2db`
- `CRYPT32!CryptBinaryToStringW` at `0x18008a1fa`
- `CRYPT32!CryptBinaryToStringW` at `0x18008a27e`
- `CRYPT32!CryptBinaryToStringW` at `0x18008a1fa`
- `CRYPT32!CryptBinaryToStringW` at `0x18008a27e`
- `CRYPT32!CryptDecodeObjectEx` at `0x18008a1c0`
- `CRYPT32!CryptDecodeObjectEx` at `0x18008a1c0`

## string_xrefs

- `0x18008a0cf`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18008a10a`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18008a13a`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18008a175`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18008a237`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18008a297`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18008a17c`: `%s: Extension was not found in the certificate. OID: %hs.`

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
  size_t v12; // rax
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
      &stru_1800C0A68);
    v8 = (const unsigned __int16 *)&stru_1800C0A68;
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
  free(v3);
  LocalFree(hMem[0]);
  return v7;
}

```

## disassembly

```asm
0x18008a098  mov     [rsp-28h+arg_8], rbx
0x18008a09d  push    rbp
0x18008a09e  push    rsi
0x18008a09f  push    rdi
0x18008a0a0  push    r14
0x18008a0a2  push    r15
0x18008a0a4  mov     rbp, rsp
0x18008a0a7  sub     rsp, 50h
0x18008a0ab  xor     r14d, r14d
0x18008a0ae  mov     [rbp+hMem], 0
0x18008a0b6  mov     [rbp+arg_18], 0
0x18008a0bd  mov     r15, r8
0x18008a0c0  mov     [rbp+pcchString], r14d
0x18008a0c4  mov     rsi, rdx
0x18008a0c7  mov     rbx, rcx
0x18008a0ca  test    rcx, rcx
0x18008a0cd  jnz     short loc_18008A105
0x18008a0cf  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18008a0d6  mov     edi, 80070057h
0x18008a0db  mov     rdx, rbx
0x18008a0de  lea     r8, aPcszoid; "pcszOid"
0x18008a0e5  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008a0ec  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008a0f1  lea     rdx, aPcszoid; "pcszOid"
0x18008a0f8  mov     rcx, rbx; unsigned __int16 *
0x18008a0fb  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18008a100  jmp     loc_18008A2CE
0x18008a105  test    r15, r15
0x18008a108  jnz     short loc_18008A135
0x18008a10a  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18008a111  mov     edi, 80070057h
0x18008a116  mov     rdx, rbx
0x18008a119  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x18008a120  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008a127  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008a12c  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x18008a133  jmp     short loc_18008A0F8
0x18008a135  test    rsi, rsi
0x18008a138  jnz     short loc_18008A165
0x18008a13a  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18008a141  mov     edi, 80070057h
0x18008a146  mov     rdx, rbx
0x18008a149  lea     r8, stru_1800C0A68
0x18008a150  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008a157  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008a15c  lea     rdx, stru_1800C0A68; struct _CERT_CONTEXT *
0x18008a163  jmp     short loc_18008A0F8
0x18008a165  mov     [r8], r14
0x18008a168  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x18008a16d  test    rax, rax
0x18008a170  jnz     short loc_18008A192
0x18008a172  mov     r8, rbx
0x18008a175  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18008a17c  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x18008a183  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18008a188  mov     edi, 80092004h
0x18008a18d  jmp     loc_18008A2CE
0x18008a192  mov     r9d, [rax+10h]; cbEncoded
0x18008a196  lea     rcx, [rbp+arg_18]
0x18008a19a  mov     r8, [rax+18h]; pbEncoded
0x18008a19e  xor     edi, edi
0x18008a1a0  mov     [rsp+50h+pcbStructInfo], rcx; pcbStructInfo
0x18008a1a5  lea     rcx, [rbp+hMem]
0x18008a1a9  mov     [rsp+50h+pvStructInfo], rcx; pvStructInfo
0x18008a1ae  mov     ecx, [rsi]; dwCertEncodingType
0x18008a1b0  mov     [rsp+50h+pDecodePara], rdi; pDecodePara
0x18008a1b5  lea     edx, [rdi+19h]; lpszStructType
0x18008a1b8  mov     [rsp+50h+dwFlags], 8000h; dwFlags
0x18008a1c0  call    cs:__imp_CryptDecodeObjectEx
0x18008a1c6  test    eax, eax
0x18008a1c8  jnz     short loc_18008A1DC
0x18008a1ca  call    cs:__imp_GetLastError
0x18008a1d0  lea     rcx, aSCryptdecodeob; "%s: CryptDecodeObjectEx with error code"...
0x18008a1d7  jmp     loc_18008A295
0x18008a1dc  mov     rcx, [rbp+hMem]
0x18008a1e0  lea     rax, [rbp+pcchString]
0x18008a1e4  mov     ebx, 40000002h
0x18008a1e9  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x18008a1ee  xor     r9d, r9d; pszString
0x18008a1f1  mov     r8d, ebx; dwFlags
0x18008a1f4  mov     edx, [rcx]; cbBinary
0x18008a1f6  mov     rcx, [rcx+8]; pbBinary
0x18008a1fa  call    cs:__imp_CryptBinaryToStringW
0x18008a200  test    eax, eax
0x18008a202  jz      loc_18008A288
0x18008a208  mov     ecx, [rbp+pcchString]
0x18008a20b  mov     eax, 2
0x18008a210  inc     ecx
0x18008a212  mul     rcx
0x18008a215  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008a21c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008a223  cmovb   rax, rcx
0x18008a227  mov     rcx, rax; unsigned __int64
0x18008a22a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008a22f  mov     r14, rax
0x18008a232  test    rax, rax
0x18008a235  jnz     short loc_18008A251
0x18008a237  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18008a23e  mov     edi, 8007000Eh
0x18008a243  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18008a24a  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18008a24f  jmp     short loc_18008A2CE
0x18008a251  mov     r8d, [rbp+pcchString]
0x18008a255  xor     edx, edx; Val
0x18008a257  inc     r8d
0x18008a25a  mov     rcx, r14; void *
0x18008a25d  add     r8, r8; Size
0x18008a260  call    memset_0
0x18008a265  mov     rcx, [rbp+hMem]
0x18008a269  lea     rax, [rbp+pcchString]
0x18008a26d  mov     r9, r14; pszString
0x18008a270  mov     qword ptr [rsp+50h+dwFlags], rax; pcchString
0x18008a275  mov     r8d, ebx; dwFlags
0x18008a278  mov     edx, [rcx]; cbBinary
0x18008a27a  mov     rcx, [rcx+8]; pbBinary
0x18008a27e  call    cs:__imp_CryptBinaryToStringW
0x18008a284  test    eax, eax
0x18008a286  jnz     short loc_18008A2BE
0x18008a288  call    cs:__imp_GetLastError
0x18008a28e  lea     rcx, aSCryptbinaryto; "%s: CryptBinaryToStringW with error cod"...
0x18008a295  mov     esi, eax
0x18008a297  lea     rbx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18008a29e  mov     r8d, eax
0x18008a2a1  mov     rdx, rbx
0x18008a2a4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008a2a9  test    esi, esi
0x18008a2ab  jz      short loc_18008A2CE
0x18008a2ad  jg      short loc_18008A2B3
0x18008a2af  mov     edi, esi
0x18008a2b1  jmp     short loc_18008A2CE
0x18008a2b3  movzx   edi, si
0x18008a2b6  or      edi, 80070000h
0x18008a2bc  jmp     short loc_18008A2CE
0x18008a2be  mov     edx, [rbp+pcchString]
0x18008a2c1  xor     ecx, ecx
0x18008a2c3  mov     [r15], r14
0x18008a2c6  mov     [r14+rdx*2], cx
0x18008a2cb  xor     r14d, r14d
0x18008a2ce  mov     rcx, r14; Block
0x18008a2d1  call    cs:__imp_free
0x18008a2d7  mov     rcx, [rbp+hMem]; hMem
0x18008a2db  call    cs:__imp_LocalFree
0x18008a2e1  mov     rbx, [rsp+50h+arg_8]
0x18008a2e9  mov     eax, edi
0x18008a2eb  add     rsp, 50h
0x18008a2ef  pop     r15
0x18008a2f1  pop     r14
0x18008a2f3  pop     rdi
0x18008a2f4  pop     rsi
0x18008a2f5  pop     rbp
0x18008a2f6  retn
```
