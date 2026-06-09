# CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)

- ea: `0x18007bee0`
- end: `0x18007c078`
- name: `?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z`
- size: `408`
- prototype: `static int __high(const char *, const unsigned __int16 *, enum _CERT_OID_VALUE_TYPE, const struct _CERT_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18007c080`

## callees

- `0x180007db4`
- `0x18007bee0`
- `0x18007c654`
- `0x18007c830`
- `0x18007d1b8`
- `0x18007d2a4`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007c04c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007c04c`

## string_xrefs

- `0x18007bf0c`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007bf26`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007bf48`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007bf75`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007bfa7`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007bfd7`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007c02f`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18007bffe`: `CertificateUtil::FindExtensionGuidValueByOid`
- `0x18007c014`: `CertificateUtil::FindExtensionStrValueByOid`

## pseudocode

```c
__int64 __fastcall CertificateUtil::DoesExtensionWithValueExist(
        const char *a1,
        const WCHAR *a2,
        int a3,
        const struct _CERT_CONTEXT *a4,
        _DWORD *a5)
{
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdx
  _DWORD *v8; // rdi
  int ExtensionGuidValueByOid; // eax
  const unsigned __int16 *v10; // r8
  LPCWSTR lpString1; // [rsp+30h] [rbp+8h] BYREF

  lpString1 = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::DoesExtensionWithValueExist", L"pcszOid");
    v7 = L"pcszOid";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::DoesExtensionWithValueExist", v7);
    goto LABEL_21;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::DoesExtensionWithValueExist",
      L"pcszOidValue");
    v7 = L"pcszOidValue";
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v6 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::DoesExtensionWithValueExist",
      &stru_18009D3F8);
    v7 = (const unsigned __int16 *)&stru_18009D3F8;
    goto LABEL_3;
  }
  v8 = a5;
  if ( !a5 )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CertificateUtil::DoesExtensionWithValueExist", L"pbResult");
    v7 = L"pbResult";
    goto LABEL_3;
  }
  *a5 = 0;
  if ( a3 )
  {
    if ( a3 != 1 )
    {
      Logger::TraceError(L"%s: Unknown CERT_OID_VALUE_TYPE: %d.", L"CertificateUtil::DoesExtensionWithValueExist");
      v6 = -2147024809;
      goto LABEL_21;
    }
    ExtensionGuidValueByOid = CertificateUtil::FindExtensionGuidValueByOid(a1, a4, (unsigned __int16 **)&lpString1);
    v10 = L"CertificateUtil::FindExtensionGuidValueByOid";
  }
  else
  {
    ExtensionGuidValueByOid = CertificateUtil::FindExtensionStrValueByOid(a1, a4, (unsigned __int16 **)&lpString1);
    v10 = L"CertificateUtil::FindExtensionStrValueByOid";
  }
  v6 = ExtensionGuidValueByOid;
  if ( ExtensionGuidValueByOid == -2146885628 )
  {
    v6 = 0;
  }
  else if ( ExtensionGuidValueByOid >= 0 )
  {
    if ( !lstrcmpiW(lpString1, a2) )
      *v8 = 1;
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"CertificateUtil::DoesExtensionWithValueExist",
      v10,
      (unsigned int)ExtensionGuidValueByOid);
  }
LABEL_21:
  operator delete((void *)lpString1);
  return v6;
}

```

## disassembly

```asm
0x18007bee0  mov     [rsp+arg_8], rbx
0x18007bee5  mov     [rsp+arg_10], rsi
0x18007beea  push    rdi
0x18007beeb  sub     rsp, 20h
0x18007beef  mov     [rsp+28h+lpString1], 0
0x18007bef8  mov     rsi, rdx
0x18007befb  test    rcx, rcx
0x18007befe  jnz     short loc_18007BF37
0x18007bf00  lea     r8, aPcszoid; "pcszOid"
0x18007bf07  mov     ebx, 80070057h
0x18007bf0c  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007bf13  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007bf1a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007bf1f  lea     rdx, aPcszoid; "pcszOid"
0x18007bf26  lea     rcx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007bf2d  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007bf32  jmp     loc_18007C05C
0x18007bf37  test    rsi, rsi
0x18007bf3a  jnz     short loc_18007BF64
0x18007bf3c  lea     r8, aPcszoidvalue; "pcszOidValue"
0x18007bf43  mov     ebx, 80070057h
0x18007bf48  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007bf4f  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007bf56  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007bf5b  lea     rdx, aPcszoidvalue; "pcszOidValue"
0x18007bf62  jmp     short loc_18007BF26
0x18007bf64  test    r9, r9
0x18007bf67  jnz     short loc_18007BF91
0x18007bf69  lea     r8, stru_18009D3F8
0x18007bf70  mov     ebx, 80070057h
0x18007bf75  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007bf7c  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007bf83  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007bf88  lea     rdx, stru_18009D3F8
0x18007bf8f  jmp     short loc_18007BF26
0x18007bf91  mov     rdi, [rsp+28h+arg_20]
0x18007bf96  test    rdi, rdi
0x18007bf99  jnz     short loc_18007BFC6
0x18007bf9b  lea     r8, aPbresult; "pbResult"
0x18007bfa2  mov     ebx, 80070057h
0x18007bfa7  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007bfae  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007bfb5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007bfba  lea     rdx, aPbresult; "pbResult"
0x18007bfc1  jmp     loc_18007BF26
0x18007bfc6  mov     dword ptr [rdi], 0
0x18007bfcc  test    r8d, r8d
0x18007bfcf  jz      short loc_18007C007
0x18007bfd1  cmp     r8d, 1
0x18007bfd5  jz      short loc_18007BFF1
0x18007bfd7  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007bfde  lea     rcx, aSUnknownCertOi; "%s: Unknown CERT_OID_VALUE_TYPE: %d."
0x18007bfe5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007bfea  mov     ebx, 80070057h
0x18007bfef  jmp     short loc_18007C05C
0x18007bff1  lea     r8, [rsp+28h+lpString1]; unsigned __int16 **
0x18007bff6  mov     rdx, r9; struct _CERT_CONTEXT *
0x18007bff9  call    ?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x18007bffe  lea     r8, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x18007c005  jmp     short loc_18007C01B
0x18007c007  lea     r8, [rsp+28h+lpString1]; unsigned __int16 **
0x18007c00c  mov     rdx, r9; struct _CERT_CONTEXT *
0x18007c00f  call    ?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x18007c014  lea     r8, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18007c01b  mov     ebx, eax
0x18007c01d  cmp     eax, 80092004h
0x18007c022  jnz     short loc_18007C028
0x18007c024  xor     ebx, ebx
0x18007c026  jmp     short loc_18007C05C
0x18007c028  test    ebx, ebx
0x18007c02a  jns     short loc_18007C044
0x18007c02c  mov     r9d, ebx
0x18007c02f  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007c036  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x18007c03d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007c042  jmp     short loc_18007C05C
0x18007c044  mov     rcx, [rsp+28h+lpString1]; lpString1
0x18007c049  mov     rdx, rsi; lpString2
0x18007c04c  call    cs:__imp_lstrcmpiW
0x18007c052  test    eax, eax
0x18007c054  jnz     short loc_18007C05C
0x18007c056  mov     dword ptr [rdi], 1
0x18007c05c  mov     rcx, [rsp+28h+lpString1]; Block
0x18007c061  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c066  mov     rsi, [rsp+28h+arg_10]
0x18007c06b  mov     eax, ebx
0x18007c06d  mov     rbx, [rsp+28h+arg_8]
0x18007c072  add     rsp, 20h
0x18007c076  pop     rdi
0x18007c077  retn
```
