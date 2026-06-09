# CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)

- ea: `0x180007ef0`
- end: `0x1800081f2`
- name: `?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `770`
- prototype: `__int64 __fastcall(const char *, const struct _CERT_CONTEXT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180008360`

## callees

- `0x180007ef0`
- `0x18000ae60`
- `0x18000af7c`
- `0x18000b32c`
- `0x18000b3c4`
- `0x18000b448`
- `0x18000ede8`
- `0x180019bd8`
- `0x18001a342`
- `0x18001a380`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800081c1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800081c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008179`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800081cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800081cc`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800080a7`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800080a7`
- `CRYPT32!CryptBinaryToStringW` at `0x1800080e1`
- `CRYPT32!CryptBinaryToStringW` at `0x18000816f`
- `CRYPT32!CryptBinaryToStringW` at `0x1800080e1`
- `CRYPT32!CryptBinaryToStringW` at `0x18000816f`

## string_xrefs

- `0x180007f30`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180007f6b`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180007fb6`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180008058`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18000811f`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180008188`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x180008030`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x180008029`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x18000805f`: `%s: Extension was not found in the certificate. OID: %hs.`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindExtensionStrValueByOid(
        const char *a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v6; // r14
  unsigned int v7; // ebx
  __int64 v8; // r8
  unsigned int v9; // eax
  struct _CERT_EXTENSION *ExtensionByOid; // rax
  DWORD LastError; // eax
  const unsigned __int16 *v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int16 *v14; // rax
  int v15; // esi
  DWORD pcchString; // [rsp+40h] [rbp-78h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-70h] BYREF
  DWORD pcbStructInfo; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v20[16]; // [rsp+58h] [rbp-60h] BYREF
  const unsigned __int16 *v21; // [rsp+68h] [rbp-50h]
  __int64 v22; // [rsp+70h] [rbp-48h]
  const struct _CERT_CONTEXT *v23; // [rsp+78h] [rbp-40h]
  __int64 v24; // [rsp+80h] [rbp-38h]

  hMem = 0;
  pcbStructInfo = 0;
  pcchString = 0;
  v6 = 0;
  if ( a1 )
  {
    if ( a3 )
    {
      if ( a2 )
      {
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
                 &hMem,
                 &pcbStructInfo) )
          {
            if ( CryptBinaryToStringW(*((const BYTE **)hMem + 1), *(_DWORD *)hMem, 0x40000002u, 0, &pcchString) )
            {
              v13 = 2LL * (pcchString + 1);
              if ( !is_mul_ok(pcchString + 1, 2u) )
                v13 = -1;
              v14 = (unsigned __int16 *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
              v6 = v14;
              if ( !v14 )
              {
                v7 = -2147024882;
                Logger::TraceCritical(
                  L"%s: Out of memory. Allocation failed.",
                  L"CertificateUtil::FindExtensionStrValueByOid");
                goto LABEL_25;
              }
              memset_0(v14, 0, 2LL * (pcchString + 1));
              if ( CryptBinaryToStringW(*((const BYTE **)hMem + 1), *(_DWORD *)hMem, 0x40000002u, v6, &pcchString) )
              {
                v6[pcchString] = 0;
                *a3 = v6;
                v6 = 0;
                goto LABEL_25;
              }
            }
            LastError = GetLastError();
            v12 = L"%s: CryptBinaryToStringW with error code: 0x%08x";
          }
          else
          {
            LastError = GetLastError();
            v12 = L"%s: CryptDecodeObjectEx with error code: 0x%08x";
          }
          v15 = LastError;
          Logger::TraceError(v12, L"CertificateUtil::FindExtensionStrValueByOid", LastError);
          if ( v15 )
          {
            if ( v15 > 0 )
              v7 = (unsigned __int16)v15 | 0x80070000;
            else
              v7 = v15;
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
      }
      else
      {
        v7 = -2147024809;
        Logger::TraceError(
          (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
          L"CertificateUtil::FindExtensionStrValueByOid",
          &stru_18001E5B8);
        if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
        {
          v21 = L"CertificateUtil::FindExtensionStrValueByOid";
          v22 = 88;
          v23 = &stru_18001E5B8;
          v24 = 26;
          v9 = McGenEventWrite_EventWriteTransfer(
                 &UserDeviceRegistrationEventProvider_Context,
                 NullOrEmptyParameterFailureEvent,
                 v8,
                 3,
                 v20);
          if ( v9 )
            Logger::TraceError(
              L"%s: %s failed with win32 error code: 0x%08x.",
              L"Logger::WriteNullOrEmptyParameterFailureEvent",
              L"EventWriteNullOrEmptyParameterFailureEvent",
              v9);
        }
      }
    }
    else
    {
      v7 = -2147024809;
      Logger::TraceError(
        (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
        L"CertificateUtil::FindExtensionStrValueByOid",
        L"ppszOutBuffer");
      Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindExtensionStrValueByOid", L"ppszOutBuffer");
    }
  }
  else
  {
    v7 = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"CertificateUtil::FindExtensionStrValueByOid",
      L"pcszOid");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindExtensionStrValueByOid", L"pcszOid");
  }
LABEL_25:
  operator delete(v6);
  LocalFree(hMem);
  return v7;
}

```

## disassembly

```asm
0x180007ef0  push    rbx
0x180007ef2  push    rbp
0x180007ef3  push    rsi
0x180007ef4  push    rdi
0x180007ef5  push    r14
0x180007ef7  sub     rsp, 90h
0x180007efe  mov     rax, cs:__security_cookie
0x180007f05  xor     rax, rsp
0x180007f08  mov     [rsp+0B8h+var_30], rax
0x180007f10  xor     ebp, ebp
0x180007f12  mov     rsi, r8
0x180007f15  mov     [rsp+0B8h+hMem], rbp
0x180007f1a  mov     rdi, rdx
0x180007f1d  mov     [rsp+0B8h+var_68], ebp
0x180007f21  mov     rbx, rcx
0x180007f24  mov     [rsp+0B8h+pcchString], ebp
0x180007f28  mov     r14d, ebp
0x180007f2b  test    rcx, rcx
0x180007f2e  jnz     short loc_180007F66
0x180007f30  lea     rdi, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180007f37  mov     ebx, 80070057h
0x180007f3c  mov     rdx, rdi
0x180007f3f  lea     r8, aPcszoid; "pcszOid"
0x180007f46  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x180007f4d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180007f52  lea     rdx, aPcszoid; "pcszOid"
0x180007f59  mov     rcx, rdi; unsigned __int16 *
0x180007f5c  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180007f61  jmp     loc_1800081BE
0x180007f66  test    rsi, rsi
0x180007f69  jnz     short loc_180007FA1
0x180007f6b  lea     rdi, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180007f72  mov     ebx, 80070057h
0x180007f77  mov     rdx, rdi
0x180007f7a  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x180007f81  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x180007f88  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180007f8d  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x180007f94  mov     rcx, rdi; unsigned __int16 *
0x180007f97  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180007f9c  jmp     loc_1800081BE
0x180007fa1  test    rdi, rdi
0x180007fa4  jnz     loc_180008048
0x180007faa  lea     rsi, stru_18001E5B8
0x180007fb1  mov     ebx, 80070057h
0x180007fb6  lea     rdi, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180007fbd  mov     r8, rsi
0x180007fc0  mov     rdx, rdi
0x180007fc3  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x180007fca  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180007fcf  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180007fd6  jz      loc_1800081BE
0x180007fdc  lea     rax, [rsp+0B8h+var_60]
0x180007fe1  mov     [rsp+0B8h+var_50], rdi
0x180007fe6  mov     r9d, 3
0x180007fec  mov     qword ptr [rsp+0B8h+dwFlags], rax
0x180007ff1  lea     rdx, NullOrEmptyParameterFailureEvent
0x180007ff8  mov     [rsp+0B8h+var_48], 58h ; 'X'
0x180008001  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180008008  mov     [rsp+0B8h+var_40], rsi
0x18000800d  mov     [rsp+0B8h+var_38], 1Ah
0x180008019  call    McGenEventWrite_EventWriteTransfer
0x18000801e  test    eax, eax
0x180008020  jz      loc_1800081BE
0x180008026  mov     r9d, eax
0x180008029  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180008030  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x180008037  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000803e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008043  jmp     loc_1800081BE
0x180008048  mov     [r8], rbp
0x18000804b  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x180008050  test    rax, rax
0x180008053  jnz     short loc_180008075
0x180008055  mov     r8, rbx
0x180008058  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18000805f  lea     rcx, aSExtensionWasN; "%s: Extension was not found in the cert"...
0x180008066  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000806b  mov     ebx, 80092004h
0x180008070  jmp     loc_1800081BE
0x180008075  mov     r9d, [rax+10h]; cbEncoded
0x180008079  lea     rcx, [rsp+0B8h+var_68]
0x18000807e  mov     r8, [rax+18h]; pbEncoded
0x180008082  mov     edx, 19h; lpszStructType
0x180008087  mov     [rsp+0B8h+pcbStructInfo], rcx; pcbStructInfo
0x18000808c  mov     ebx, ebp
0x18000808e  lea     rcx, [rsp+0B8h+hMem]
0x180008093  mov     [rsp+0B8h+pvStructInfo], rcx; pvStructInfo
0x180008098  mov     ecx, [rdi]; dwCertEncodingType
0x18000809a  mov     [rsp+0B8h+pDecodePara], rbp; pDecodePara
0x18000809f  mov     [rsp+0B8h+dwFlags], 8000h; dwFlags
0x1800080a7  call    cs:__imp_CryptDecodeObjectEx
0x1800080ad  test    eax, eax
0x1800080af  jnz     short loc_1800080C3
0x1800080b1  call    cs:__imp_GetLastError
0x1800080b7  lea     rcx, aSCryptdecodeob; "%s: CryptDecodeObjectEx with error code"...
0x1800080be  jmp     loc_180008186
0x1800080c3  mov     rcx, [rsp+0B8h+hMem]
0x1800080c8  lea     rax, [rsp+0B8h+pcchString]
0x1800080cd  xor     r9d, r9d; pszString
0x1800080d0  mov     qword ptr [rsp+0B8h+dwFlags], rax; pcchString
0x1800080d5  mov     r8d, 40000002h; dwFlags
0x1800080db  mov     edx, [rcx]; cbBinary
0x1800080dd  mov     rcx, [rcx+8]; pbBinary
0x1800080e1  call    cs:__imp_CryptBinaryToStringW
0x1800080e7  test    eax, eax
0x1800080e9  jz      loc_180008179
0x1800080ef  mov     ecx, [rsp+0B8h+pcchString]
0x1800080f3  mov     eax, 2
0x1800080f8  inc     ecx
0x1800080fa  mul     rcx
0x1800080fd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180008104  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000810b  cmovb   rax, rcx
0x18000810f  mov     rcx, rax; unsigned __int64
0x180008112  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180008117  mov     r14, rax
0x18000811a  test    rax, rax
0x18000811d  jnz     short loc_18000813C
0x18000811f  lea     rdx, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x180008126  mov     ebx, 8007000Eh
0x18000812b  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x180008132  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180008137  jmp     loc_1800081BE
0x18000813c  mov     r8d, [rsp+0B8h+pcchString]
0x180008141  xor     edx, edx; Val
0x180008143  inc     r8d
0x180008146  mov     rcx, r14; void *
0x180008149  add     r8, r8; Size
0x18000814c  call    memset_0
0x180008151  mov     rcx, [rsp+0B8h+hMem]
0x180008156  lea     rax, [rsp+0B8h+pcchString]
0x18000815b  mov     r9, r14; pszString
0x18000815e  mov     qword ptr [rsp+0B8h+dwFlags], rax; pcchString
0x180008163  mov     r8d, 40000002h; dwFlags
0x180008169  mov     edx, [rcx]; cbBinary
0x18000816b  mov     rcx, [rcx+8]; pbBinary
0x18000816f  call    cs:__imp_CryptBinaryToStringW
0x180008175  test    eax, eax
0x180008177  jnz     short loc_1800081AF
0x180008179  call    cs:__imp_GetLastError
0x18000817f  lea     rcx, aSCryptbinaryto; "%s: CryptBinaryToStringW with error cod"...
0x180008186  mov     esi, eax
0x180008188  lea     rdi, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18000818f  mov     r8d, eax
0x180008192  mov     rdx, rdi
0x180008195  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000819a  test    esi, esi
0x18000819c  jz      short loc_1800081BE
0x18000819e  jg      short loc_1800081A4
0x1800081a0  mov     ebx, esi
0x1800081a2  jmp     short loc_1800081BE
0x1800081a4  movzx   ebx, si
0x1800081a7  or      ebx, 80070000h
0x1800081ad  jmp     short loc_1800081BE
0x1800081af  mov     ecx, [rsp+0B8h+pcchString]
0x1800081b3  mov     [r14+rcx*2], bp
0x1800081b8  mov     [rsi], r14
0x1800081bb  mov     r14, rbp
0x1800081be  mov     rcx, r14
0x1800081c1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800081c7  mov     rcx, [rsp+0B8h+hMem]; hMem
0x1800081cc  call    cs:__imp_LocalFree
0x1800081d2  mov     eax, ebx
0x1800081d4  mov     rcx, [rsp+0B8h+var_30]
0x1800081dc  xor     rcx, rsp; StackCookie
0x1800081df  call    __security_check_cookie
0x1800081e4  add     rsp, 90h
0x1800081eb  pop     r14
0x1800081ed  pop     rdi
0x1800081ee  pop     rsi
0x1800081ef  pop     rbp
0x1800081f0  pop     rbx
0x1800081f1  retn
```
