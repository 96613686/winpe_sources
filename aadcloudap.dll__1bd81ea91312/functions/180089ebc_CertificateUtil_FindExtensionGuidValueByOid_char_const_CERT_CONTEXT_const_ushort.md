# CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x180089ebc`
- end: `0x18008a090`
- name: `?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `468`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180089748`
- `0x180090378`
- `0x1800909c4`

## callees

- `0x180089e68`
- `0x180089ebc`
- `0x18008a684`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a06f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008a06f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089fe7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a07a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a07a`
- `CRYPT32!CryptDecodeObjectEx` at `0x180089fdd`
- `CRYPT32!CryptDecodeObjectEx` at `0x180089fdd`

## string_xrefs

- `0x180089efa`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180089f14`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180089f36`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180089f63`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180089f8f`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180089ff0`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18008a044`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x180089f96`: `%s: Extension was not found in the certificate. OID: %hs.`

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
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::FindExtensionGuidValueByOid", L"pcszOid");
    v8 = L"pcszOid";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindExtensionGuidValueByOid", v8);
    goto LABEL_18;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      L"ppszOutBuffer");
    v8 = L"ppszOutBuffer";
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindExtensionGuidValueByOid",
      &stru_1800C0A68);
    v8 = (const unsigned __int16 *)&stru_1800C0A68;
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
  free(v3);
  LocalFree(hMem[0]);
  return v7;
}

```

## disassembly

```asm
0x180089ebc  mov     rax, rsp
0x180089ebf  mov     [rax+10h], rbx
0x180089ec3  push    rsi
0x180089ec4  push    rdi
0x180089ec5  push    r14
0x180089ec7  sub     rsp, 50h
0x180089ecb  xor     esi, esi
0x180089ecd  mov     qword ptr [rax-28h], 0
0x180089ed5  mov     dword ptr [rax+8], 0
0x180089edc  mov     rdi, r8
0x180089edf  mov     [rax+20h], rsi
0x180089ee3  mov     r14, rdx
0x180089ee6  mov     rbx, rcx
0x180089ee9  test    rcx, rcx
0x180089eec  jnz     short loc_180089F25
0x180089eee  lea     r8, aPcszoid; "pcszOid"
0x180089ef5  mov     ebx, 80070057h
0x180089efa  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180089f01  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180089f08  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180089f0d  lea     rdx, aPcszoid; "pcszOid"
0x180089f14  lea     rcx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180089f1b  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180089f20  jmp     loc_18008A06C
0x180089f25  test    rdi, rdi
0x180089f28  jnz     short loc_180089F52
0x180089f2a  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x180089f31  mov     ebx, 80070057h
0x180089f36  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180089f3d  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180089f44  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180089f49  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x180089f50  jmp     short loc_180089F14
0x180089f52  test    r14, r14
0x180089f55  jnz     short loc_180089F7F
0x180089f57  lea     r8, stru_1800C0A68
0x180089f5e  mov     ebx, 80070057h
0x180089f63  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180089f6a  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180089f71  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180089f76  lea     rdx, stru_1800C0A68; struct _CERT_CONTEXT *
0x180089f7d  jmp     short loc_180089F14
0x180089f7f  mov     [r8], rsi
0x180089f82  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x180089f87  test    rax, rax
0x180089f8a  jnz     short loc_180089FAC
0x180089f8c  mov     r8, rbx
0x180089f8f  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180089f96  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x180089f9d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180089fa2  mov     ebx, 80092004h
0x180089fa7  jmp     loc_18008A06C
0x180089fac  mov     r9d, [rax+10h]; cbEncoded
0x180089fb0  lea     rcx, [rsp+68h+arg_0]
0x180089fb5  mov     r8, [rax+18h]; pbEncoded
0x180089fb9  mov     edx, 19h; lpszStructType
0x180089fbe  mov     [rsp+68h+pcbStructInfo], rcx; pcbStructInfo
0x180089fc3  lea     rcx, [rsp+68h+hMem]
0x180089fc8  mov     [rsp+68h+pvStructInfo], rcx; pvStructInfo
0x180089fcd  mov     ecx, [r14]; dwCertEncodingType
0x180089fd0  mov     [rsp+68h+pDecodePara], rsi; pDecodePara
0x180089fd5  mov     [rsp+68h+dwFlags], 8000h; dwFlags
0x180089fdd  call    cs:__imp_CryptDecodeObjectEx
0x180089fe3  test    eax, eax
0x180089fe5  jnz     short loc_18008A01C
0x180089fe7  call    cs:__imp_GetLastError
0x180089fed  mov     r8d, eax
0x180089ff0  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180089ff7  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x180089ffe  mov     edi, eax
0x18008a000  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008a005  xor     ebx, ebx
0x18008a007  test    edi, edi
0x18008a009  jz      short loc_18008A06C
0x18008a00b  jg      short loc_18008A011
0x18008a00d  mov     ebx, edi
0x18008a00f  jmp     short loc_18008A06C
0x18008a011  movzx   ebx, di
0x18008a014  or      ebx, 80070000h
0x18008a01a  jmp     short loc_18008A06C
0x18008a01c  mov     rcx, [rsp+68h+hMem]
0x18008a021  lea     r8, [rsp+68h+arg_18]; unsigned __int16 **
0x18008a029  mov     edx, [rcx]; unsigned int
0x18008a02b  mov     rcx, [rcx+8]; unsigned __int8 *
0x18008a02f  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x18008a034  mov     ebx, eax
0x18008a036  test    eax, eax
0x18008a038  jns     short loc_18008A061
0x18008a03a  mov     r9d, eax
0x18008a03d  lea     r8, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x18008a044  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18008a04b  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008a052  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008a057  mov     rsi, [rsp+68h+arg_18]
0x18008a05f  jmp     short loc_18008A06C
0x18008a061  mov     rax, [rsp+68h+arg_18]
0x18008a069  mov     [rdi], rax
0x18008a06c  mov     rcx, rsi; Block
0x18008a06f  call    cs:__imp_free
0x18008a075  mov     rcx, [rsp+68h+hMem]; hMem
0x18008a07a  call    cs:__imp_LocalFree
0x18008a080  mov     eax, ebx
0x18008a082  mov     rbx, [rsp+68h+arg_8]
0x18008a087  add     rsp, 50h
0x18008a08b  pop     r14
0x18008a08d  pop     rdi
0x18008a08e  pop     rsi
0x18008a08f  retn
```
