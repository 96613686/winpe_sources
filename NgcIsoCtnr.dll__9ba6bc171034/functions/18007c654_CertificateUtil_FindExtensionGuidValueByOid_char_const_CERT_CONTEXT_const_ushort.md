# CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x18007c654`
- end: `0x18007c827`
- name: `?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `467`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18007bee0`
- `0x1800805c4`
- `0x180080754`

## callees

- `0x180007db4`
- `0x18007c600`
- `0x18007c654`
- `0x18007ce14`
- `0x18007d1b8`
- `0x18007d22c`
- `0x18007d2a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c77f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c77f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c811`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c811`
- `CRYPT32!CryptDecodeObjectEx` at `0x18007c775`
- `CRYPT32!CryptDecodeObjectEx` at `0x18007c775`

## string_xrefs

- `0x18007c692`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007c6ac`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007c6ce`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007c6fb`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007c727`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007c788`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007c7dc`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007c72e`: `%s: Extension was not found in the certificate. OID: %hs.`

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
      &stru_18009D3F8);
    v8 = (const unsigned __int16 *)&stru_18009D3F8;
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
0x18007c654  mov     rax, rsp
0x18007c657  mov     [rax+10h], rbx
0x18007c65b  push    rsi
0x18007c65c  push    rdi
0x18007c65d  push    r14
0x18007c65f  sub     rsp, 50h
0x18007c663  xor     esi, esi
0x18007c665  mov     qword ptr [rax-28h], 0
0x18007c66d  mov     dword ptr [rax+8], 0
0x18007c674  mov     rdi, r8
0x18007c677  mov     [rax+20h], rsi
0x18007c67b  mov     r14, rdx
0x18007c67e  mov     rbx, rcx
0x18007c681  test    rcx, rcx
0x18007c684  jnz     short loc_18007C6BD
0x18007c686  lea     r8, aPcszoid; "pcszOid"
0x18007c68d  mov     ebx, 80070057h
0x18007c692  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007c699  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007c6a0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c6a5  lea     rdx, aPcszoid; "pcszOid"
0x18007c6ac  lea     rcx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007c6b3  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007c6b8  jmp     loc_18007C804
0x18007c6bd  test    rdi, rdi
0x18007c6c0  jnz     short loc_18007C6EA
0x18007c6c2  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x18007c6c9  mov     ebx, 80070057h
0x18007c6ce  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007c6d5  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007c6dc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c6e1  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x18007c6e8  jmp     short loc_18007C6AC
0x18007c6ea  test    r14, r14
0x18007c6ed  jnz     short loc_18007C717
0x18007c6ef  lea     r8, stru_18009D3F8
0x18007c6f6  mov     ebx, 80070057h
0x18007c6fb  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007c702  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007c709  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c70e  lea     rdx, stru_18009D3F8; struct _CERT_CONTEXT *
0x18007c715  jmp     short loc_18007C6AC
0x18007c717  mov     [r8], rsi
0x18007c71a  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x18007c71f  test    rax, rax
0x18007c722  jnz     short loc_18007C744
0x18007c724  mov     r8, rbx
0x18007c727  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007c72e  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x18007c735  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007c73a  mov     ebx, 80092004h
0x18007c73f  jmp     loc_18007C804
0x18007c744  mov     r9d, [rax+10h]; cbEncoded
0x18007c748  lea     rcx, [rsp+68h+arg_0]
0x18007c74d  mov     r8, [rax+18h]; pbEncoded
0x18007c751  mov     edx, 19h; lpszStructType
0x18007c756  mov     [rsp+68h+pcbStructInfo], rcx; pcbStructInfo
0x18007c75b  lea     rcx, [rsp+68h+hMem]
0x18007c760  mov     [rsp+68h+pvStructInfo], rcx; pvStructInfo
0x18007c765  mov     ecx, [r14]; dwCertEncodingType
0x18007c768  mov     [rsp+68h+pDecodePara], rsi; pDecodePara
0x18007c76d  mov     [rsp+68h+dwFlags], 8000h; dwFlags
0x18007c775  call    cs:__imp_CryptDecodeObjectEx
0x18007c77b  test    eax, eax
0x18007c77d  jnz     short loc_18007C7B4
0x18007c77f  call    cs:__imp_GetLastError
0x18007c785  mov     r8d, eax
0x18007c788  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007c78f  lea     rcx, aSCryptdecodeob_0; "%s: CryptDecodeObjectEx failed with err"...
0x18007c796  mov     edi, eax
0x18007c798  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c79d  xor     ebx, ebx
0x18007c79f  test    edi, edi
0x18007c7a1  jz      short loc_18007C804
0x18007c7a3  jg      short loc_18007C7A9
0x18007c7a5  mov     ebx, edi
0x18007c7a7  jmp     short loc_18007C804
0x18007c7a9  movzx   ebx, di
0x18007c7ac  or      ebx, 80070000h
0x18007c7b2  jmp     short loc_18007C804
0x18007c7b4  mov     rcx, [rsp+68h+hMem]
0x18007c7b9  lea     r8, [rsp+68h+arg_18]; unsigned __int16 **
0x18007c7c1  mov     edx, [rcx]; unsigned int
0x18007c7c3  mov     rcx, [rcx+8]; unsigned __int8 *
0x18007c7c7  call    ?GuidStringFromByteArray@CertificateUtil@@CAJPEBEKPEAPEAG@Z; CertificateUtil::GuidStringFromByteArray(uchar const *,ulong,ushort * *)
0x18007c7cc  mov     ebx, eax
0x18007c7ce  test    eax, eax
0x18007c7d0  jns     short loc_18007C7F9
0x18007c7d2  mov     r9d, eax
0x18007c7d5  lea     r8, aCertificateuti_3; "CertificateUtil::GuidStringFromByteArra"...
0x18007c7dc  lea     rdx, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007c7e3  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18007c7ea  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c7ef  mov     rsi, [rsp+68h+arg_18]
0x18007c7f7  jmp     short loc_18007C804
0x18007c7f9  mov     rax, [rsp+68h+arg_18]
0x18007c801  mov     [rdi], rax
0x18007c804  mov     rcx, rsi; Block
0x18007c807  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c80c  mov     rcx, [rsp+68h+hMem]; hMem
0x18007c811  call    cs:__imp_LocalFree
0x18007c817  mov     eax, ebx
0x18007c819  mov     rbx, [rsp+68h+arg_8]
0x18007c81e  add     rsp, 50h
0x18007c822  pop     r14
0x18007c824  pop     rdi
0x18007c825  pop     rsi
0x18007c826  retn
```
