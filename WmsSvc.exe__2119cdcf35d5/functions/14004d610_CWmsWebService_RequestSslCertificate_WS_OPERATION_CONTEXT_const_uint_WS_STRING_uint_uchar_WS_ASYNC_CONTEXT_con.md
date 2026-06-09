# CWmsWebService::RequestSslCertificate(_WS_OPERATION_CONTEXT const *,uint *,_WS_STRING *,uint *,uchar * *,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x14004d610`
- end: `0x14004d971`
- name: `?RequestSslCertificate@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@PEAIPEAU_WS_STRING@@1PEAPEAEPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `865`
- prototype: `__int64 __fastcall(const struct _WS_OPERATION_CONTEXT *, unsigned int *, struct _WS_STRING *, unsigned int *, unsigned __int8 **ptr, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *error)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task`

## callees

- `0x1400016b8`
- `0x14004d610`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140063fd4`
- `0x140064dc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004d766`
- `KERNEL32!GetLastError` at `0x14004d82d`
- `KERNEL32!GetLastError` at `0x14004d766`
- `KERNEL32!GetLastError` at `0x14004d82d`
- `KERNEL32!IsDebuggerPresent` at `0x14004d69a`
- `KERNEL32!IsDebuggerPresent` at `0x14004d7c1`
- `KERNEL32!IsDebuggerPresent` at `0x14004d888`
- `KERNEL32!IsDebuggerPresent` at `0x14004d8f6`
- `KERNEL32!IsDebuggerPresent` at `0x14004d69a`
- `KERNEL32!IsDebuggerPresent` at `0x14004d7c1`
- `KERNEL32!IsDebuggerPresent` at `0x14004d888`
- `KERNEL32!IsDebuggerPresent` at `0x14004d8f6`
- `msvcrt!memcpy_s` at `0x14004d923`
- `msvcrt!memcpy_s` at `0x14004d923`
- `CRYPT32!CertFindCertificateInStore` at `0x14004d81f`
- `CRYPT32!CertFindCertificateInStore` at `0x14004d81f`
- `CRYPT32!CertCloseStore` at `0x14004d958`
- `CRYPT32!CertCloseStore` at `0x14004d958`
- `CRYPT32!CertOpenStore` at `0x14004d754`
- `CRYPT32!CertOpenStore` at `0x14004d754`
- `CRYPT32!CertFreeCertificateContext` at `0x14004d948`
- `CRYPT32!CertFreeCertificateContext` at `0x14004d948`
- `webservices!WsAlloc` at `0x14004d8b2`
- `webservices!WsAlloc` at `0x14004d8b2`
- `webservices!WsGetOperationContextProperty` at `0x14004d654`
- `webservices!WsGetOperationContextProperty` at `0x14004d654`

## string_xrefs

- `0x14004d73c`: `MultiPoint Services Certificates`
- `0x14004d66f`: `CWmsWebService::RequestSslCertificate`
- `0x14004d789`: `CWmsWebService::RequestSslCertificate`
- `0x14004d850`: `CWmsWebService::RequestSslCertificate`
- `0x14004d8c9`: `CWmsWebService::RequestSslCertificate`
- `0x14004d679`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointcertificaterequest.cpp`
- `0x14004d796`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointcertificaterequest.cpp`
- `0x14004d85d`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointcertificaterequest.cpp`
- `0x14004d8d3`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointcertificaterequest.cpp`

## pseudocode

```c
__int64 __fastcall CWmsWebService::RequestSslCertificate(
        const struct _WS_OPERATION_CONTEXT *a1,
        unsigned int *a2,
        struct _WS_STRING *a3,
        unsigned int *a4,
        unsigned __int8 **ptr,
        const struct _WS_ASYNC_CONTEXT *a6,
        struct _WS_ERROR *error)
{
  const CERT_CONTEXT *v7; // rbp
  HCERTSTORE v11; // r12
  unsigned __int16 *v12; // r13
  HRESULT OperationContextProperty; // eax
  signed int v14; // ebx
  __int64 v15; // r9
  __int64 v16; // r8
  int v17; // eax
  signed int v18; // eax
  unsigned int v19; // r15d
  bool v20; // zf
  const unsigned __int16 *v21; // rax
  PCCERT_CONTEXT CertificateInStore; // rax
  signed int LastError; // eax
  HRESULT v24; // eax
  WS_HEAP *heap; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int16 *v27; // [rsp+48h] [rbp-50h] BYREF

  v7 = 0;
  heap = 0;
  v11 = 0;
  v12 = 0;
  v27 = 0;
  OperationContextProperty = WsGetOperationContextProperty(a1, WS_OPERATION_CONTEXT_PROPERTY_HEAP, &heap, 8u, error);
  v14 = OperationContextProperty;
  if ( OperationContextProperty < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointcertificaterequest.cpp",
      0x48u,
      L"CWmsWebService::RequestSslCertificate",
      L"CHRA",
      L"hr",
      OperationContextProperty);
    if ( IsDebuggerPresent() )
    {
      v15 = 72;
LABEL_4:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointcertificaterequest.cpp",
        v15,
        L"CWmsWebService::RequestSslCertificate",
        L"CHRA",
        L"hr",
        v14);
      goto LABEL_31;
    }
    v16 = 72;
LABEL_7:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointcertificaterequest.cpp",
      v16,
      L"CWmsWebService::RequestSslCertificate",
      L"CHRA",
      L"hr",
      v14);
    goto LABEL_31;
  }
  v17 = ConvertThumbprintBlobToString(&CWmsWebService::s_SslCertificateThumbprint, &v27);
  v12 = v27;
  v14 = v17;
  if ( v17 >= 0 )
  {
    v14 = StringToWsString(heap, v27, a3);
    if ( v14 >= 0 )
    {
      v11 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"MultiPoint Services Certificates");
      if ( v11 )
      {
        CertificateInStore = CertFindCertificateInStore(
                               v11,
                               1u,
                               0,
                               0x10000u,
                               &CWmsWebService::s_SslCertificateThumbprint,
                               0);
        v7 = CertificateInStore;
        if ( CertificateInStore )
        {
          v24 = WsAlloc(heap, CertificateInStore->cbCertEncoded, (void **)ptr, error);
          v14 = v24;
          if ( v24 >= 0 )
          {
            memcpy_s(*ptr, v7->cbCertEncoded, v7->pbCertEncoded, v7->cbCertEncoded);
            *a2 = CWmsWebService::s_SslPort;
            *a4 = v7->cbCertEncoded;
            goto LABEL_31;
          }
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointcertificaterequest.cpp",
            0x5Du,
            L"CWmsWebService::RequestSslCertificate",
            L"CHRA",
            L"hr",
            v24);
          if ( IsDebuggerPresent() )
          {
            v15 = 93;
            goto LABEL_4;
          }
          v16 = 93;
          goto LABEL_7;
        }
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        v19 = 90;
        if ( v14 >= 0 )
          v14 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointcertificaterequest.cpp",
          0x5Au,
          L"CWmsWebService::RequestSslCertificate",
          L"CBRAEx",
          L"pCertContext",
          v14);
        v20 = !IsDebuggerPresent();
        v21 = L"pCertContext";
      }
      else
      {
        v18 = GetLastError();
        v14 = v18;
        if ( v18 > 0 )
          v14 = (unsigned __int16)v18 | 0x80070000;
        v19 = 87;
        if ( v14 >= 0 )
          v14 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointcertificaterequest.cpp",
          0x57u,
          L"CWmsWebService::RequestSslCertificate",
          L"CBRAEx",
          L"hCertStore != 0",
          v14);
        v20 = !IsDebuggerPresent();
        v21 = L"hCertStore != 0";
      }
      if ( v20 )
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointcertificaterequest.cpp",
          v19,
          L"CWmsWebService::RequestSslCertificate",
          L"CBRAEx",
          v21,
          v14);
      else
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointcertificaterequest.cpp",
          v19,
          L"CWmsWebService::RequestSslCertificate",
          L"CBRAEx",
          v21,
          v14);
    }
  }
LABEL_31:
  operator delete(v12);
  if ( v7 )
    CertFreeCertificateContext(v7);
  if ( v11 )
    CertCloseStore(v11, 0);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14004d610  mov     rax, rsp
0x14004d613  push    rbx
0x14004d614  push    rbp
0x14004d615  push    rsi
0x14004d616  push    rdi
0x14004d617  push    r12
0x14004d619  push    r13
0x14004d61b  push    r14
0x14004d61d  push    r15
0x14004d61f  sub     rsp, 58h
0x14004d623  mov     rsi, [rsp+98h+error]
0x14004d62b  xor     ebp, ebp
0x14004d62d  mov     r14, r9
0x14004d630  mov     [rax-58h], rbp
0x14004d634  mov     rdi, r8
0x14004d637  mov     [rax-78h], rsi
0x14004d63b  mov     r15, rdx
0x14004d63e  lea     r8, [rax-58h]; value
0x14004d642  xor     r12d, r12d
0x14004d645  lea     edx, [rbp+6]; id
0x14004d648  xor     r13d, r13d
0x14004d64b  mov     [rax-50h], r13
0x14004d64f  lea     r9d, [r12+8]; valueSize
0x14004d654  call    cs:__imp_WsGetOperationContextProperty
0x14004d65a  mov     ebx, eax
0x14004d65c  test    eax, eax
0x14004d65e  jns     loc_14004D700
0x14004d664  mov     dword ptr [rsp+98h+pPrevCertContext], eax; int
0x14004d668  lea     r15, aChra; "CHRA"
0x14004d66f  lea     rsi, aCwmswebservice_71; "CWmsWebService::RequestSslCertificate"
0x14004d676  mov     r9, r15; unsigned __int16 *
0x14004d679  lea     rdi, aTermsrvWmsSrcD_14; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004d680  mov     r8, rsi; unsigned __int16 *
0x14004d683  lea     r14, aHr; "hr"
0x14004d68a  mov     rcx, rdi; unsigned __int16 *
0x14004d68d  lea     edx, [rbp+48h]; unsigned int
0x14004d690  mov     [rsp+98h+pvPara], r14; unsigned __int16 *
0x14004d695  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004d69a  call    cs:__imp_IsDebuggerPresent
0x14004d6a0  test    eax, eax
0x14004d6a2  jz      short loc_14004D6D5
0x14004d6a4  lea     r9d, [r12+48h]
0x14004d6a9  mov     [rsp+98h+var_60], ebx
0x14004d6ad  mov     [rsp+98h+var_68], r14
0x14004d6b2  mov     [rsp+98h+pPrevCertContext], r15
0x14004d6b7  mov     r8, rdi
0x14004d6ba  mov     [rsp+98h+pvPara], rsi
0x14004d6bf  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14004d6c6  mov     ecx, 2; unsigned __int8
0x14004d6cb  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004d6d0  jmp     loc_14004D938
0x14004d6d5  mov     r8d, 48h ; 'H'
0x14004d6db  mov     dword ptr [rsp+98h+var_68], ebx
0x14004d6df  mov     [rsp+98h+pPrevCertContext], r14
0x14004d6e4  mov     [rsp+98h+pvPara], r15
0x14004d6e9  mov     r9, rsi
0x14004d6ec  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14004d6f3  mov     rdx, rdi
0x14004d6f6  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14004d6fb  jmp     loc_14004D938
0x14004d700  lea     rdx, [rsp+98h+var_50]; unsigned __int16 **
0x14004d705  lea     rcx, ?s_SslCertificateThumbprint@CWmsWebService@@0U_CRYPTOAPI_BLOB@@A; struct _CRYPTOAPI_BLOB *
0x14004d70c  call    ?ConvertThumbprintBlobToString@@YAJPEAU_CRYPTOAPI_BLOB@@PEAPEAG@Z; ConvertThumbprintBlobToString(_CRYPTOAPI_BLOB *,ushort * *)
0x14004d711  mov     r13, [rsp+98h+var_50]
0x14004d716  mov     ebx, eax
0x14004d718  test    eax, eax
0x14004d71a  js      loc_14004D938
0x14004d720  mov     rcx, [rsp+98h+heap]; struct _WS_HEAP *
0x14004d725  mov     r8, rdi; struct _WS_STRING *
0x14004d728  mov     rdx, r13; unsigned __int16 *
0x14004d72b  call    ?StringToWsString@@YAJPEAU_WS_HEAP@@PEAGPEAU_WS_STRING@@@Z; StringToWsString(_WS_HEAP *,ushort *,_WS_STRING *)
0x14004d730  mov     ebx, eax
0x14004d732  test    eax, eax
0x14004d734  js      loc_14004D938
0x14004d73a  xor     edx, edx; dwEncodingType
0x14004d73c  lea     rax, ?g_kszWmsCertStore@@3QBGB; "MultiPoint Services Certificates"
0x14004d743  mov     r9d, 28000h; dwFlags
0x14004d749  mov     [rsp+98h+pvPara], rax; pvPara
0x14004d74e  xor     r8d, r8d; hCryptProv
0x14004d751  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x14004d754  call    cs:__imp_CertOpenStore
0x14004d75a  mov     r12, rax
0x14004d75d  test    rax, rax
0x14004d760  jnz     loc_14004D7FE
0x14004d766  call    cs:__imp_GetLastError
0x14004d76c  mov     ebx, eax
0x14004d76e  test    eax, eax
0x14004d770  jle     short loc_14004D77B
0x14004d772  movzx   ebx, ax
0x14004d775  or      ebx, 80070000h
0x14004d77b  mov     eax, 80004005h
0x14004d780  lea     r14, aCbraex; "CBRAEx"
0x14004d787  test    ebx, ebx
0x14004d789  lea     rsi, aCwmswebservice_71; "CWmsWebService::RequestSslCertificate"
0x14004d790  mov     r15d, 57h ; 'W'
0x14004d796  lea     rdi, aTermsrvWmsSrcD_14; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004d79d  cmovns  ebx, eax
0x14004d7a0  mov     r9, r14; unsigned __int16 *
0x14004d7a3  lea     rax, aHcertstore0; "hCertStore != 0"
0x14004d7aa  mov     dword ptr [rsp+98h+pPrevCertContext], ebx; int
0x14004d7ae  mov     r8, rsi; unsigned __int16 *
0x14004d7b1  mov     [rsp+98h+pvPara], rax; unsigned __int16 *
0x14004d7b6  mov     edx, r15d; unsigned int
0x14004d7b9  mov     rcx, rdi; unsigned __int16 *
0x14004d7bc  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004d7c1  call    cs:__imp_IsDebuggerPresent
0x14004d7c7  test    eax, eax
0x14004d7c9  lea     rax, aHcertstore0; "hCertStore != 0"
0x14004d7d0  jz      short loc_14004D7E8
0x14004d7d2  mov     [rsp+98h+var_60], ebx
0x14004d7d6  mov     r9d, r15d
0x14004d7d9  mov     [rsp+98h+var_68], rax
0x14004d7de  mov     [rsp+98h+pPrevCertContext], r14
0x14004d7e3  jmp     loc_14004D6B7
0x14004d7e8  mov     dword ptr [rsp+98h+var_68], ebx
0x14004d7ec  mov     r8d, r15d
0x14004d7ef  mov     [rsp+98h+pPrevCertContext], rax
0x14004d7f4  mov     [rsp+98h+pvPara], r14
0x14004d7f9  jmp     loc_14004D6E9
0x14004d7fe  xor     r8d, r8d; dwFindFlags
0x14004d801  mov     [rsp+98h+pPrevCertContext], rbp; pPrevCertContext
0x14004d806  lea     rax, ?s_SslCertificateThumbprint@CWmsWebService@@0U_CRYPTOAPI_BLOB@@A; _CRYPTOAPI_BLOB CWmsWebService::s_SslCertificateThumbprint
0x14004d80d  mov     r9d, 10000h; dwFindType
0x14004d813  mov     rcx, r12; hCertStore
0x14004d816  mov     [rsp+98h+pvPara], rax; pvFindPara
0x14004d81b  lea     edx, [r8+1]; dwCertEncodingType
0x14004d81f  call    cs:__imp_CertFindCertificateInStore
0x14004d825  mov     rbp, rax
0x14004d828  test    rax, rax
0x14004d82b  jnz     short loc_14004D89C
0x14004d82d  call    cs:__imp_GetLastError
0x14004d833  mov     ebx, eax
0x14004d835  test    eax, eax
0x14004d837  jle     short loc_14004D842
0x14004d839  movzx   ebx, ax
0x14004d83c  or      ebx, 80070000h
0x14004d842  mov     eax, 80004005h
0x14004d847  lea     r14, aCbraex; "CBRAEx"
0x14004d84e  test    ebx, ebx
0x14004d850  lea     rsi, aCwmswebservice_71; "CWmsWebService::RequestSslCertificate"
0x14004d857  mov     r15d, 5Ah ; 'Z'
0x14004d85d  lea     rdi, aTermsrvWmsSrcD_14; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004d864  cmovns  ebx, eax
0x14004d867  mov     r9, r14; unsigned __int16 *
0x14004d86a  lea     rax, aPcertcontext; "pCertContext"
0x14004d871  mov     dword ptr [rsp+98h+pPrevCertContext], ebx; int
0x14004d875  mov     r8, rsi; unsigned __int16 *
0x14004d878  mov     [rsp+98h+pvPara], rax; unsigned __int16 *
0x14004d87d  mov     edx, r15d; unsigned int
0x14004d880  mov     rcx, rdi; unsigned __int16 *
0x14004d883  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004d888  call    cs:__imp_IsDebuggerPresent
0x14004d88e  test    eax, eax
0x14004d890  lea     rax, aPcertcontext; "pCertContext"
0x14004d897  jmp     loc_14004D7D0
0x14004d89c  mov     rdi, [rsp+98h+ptr]
0x14004d8a4  mov     r9, rsi; error
0x14004d8a7  mov     edx, [rax+10h]; size
0x14004d8aa  mov     r8, rdi; ptr
0x14004d8ad  mov     rcx, [rsp+98h+heap]; heap
0x14004d8b2  call    cs:__imp_WsAlloc
0x14004d8b8  mov     ebx, eax
0x14004d8ba  test    eax, eax
0x14004d8bc  jns     short loc_14004D916
0x14004d8be  mov     dword ptr [rsp+98h+pPrevCertContext], eax; int
0x14004d8c2  lea     r15, aChra; "CHRA"
0x14004d8c9  lea     rsi, aCwmswebservice_71; "CWmsWebService::RequestSslCertificate"
0x14004d8d0  mov     r9, r15; unsigned __int16 *
0x14004d8d3  lea     rdi, aTermsrvWmsSrcD_14; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004d8da  mov     r8, rsi; unsigned __int16 *
0x14004d8dd  lea     r14, aHr; "hr"
0x14004d8e4  mov     rcx, rdi; unsigned __int16 *
0x14004d8e7  mov     edx, 5Dh ; ']'; unsigned int
0x14004d8ec  mov     [rsp+98h+pvPara], r14; unsigned __int16 *
0x14004d8f1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004d8f6  call    cs:__imp_IsDebuggerPresent
0x14004d8fc  test    eax, eax
0x14004d8fe  jz      short loc_14004D90B
0x14004d900  mov     r9d, 5Dh ; ']'
0x14004d906  jmp     loc_14004D6A9
0x14004d90b  mov     r8d, 5Dh ; ']'
0x14004d911  jmp     loc_14004D6DB
0x14004d916  mov     edx, [rbp+10h]; DestinationSize
0x14004d919  mov     r8, [rbp+8]; Source
0x14004d91d  mov     r9d, edx; SourceSize
0x14004d920  mov     rcx, [rdi]; Destination
0x14004d923  call    cs:__imp_memcpy_s
0x14004d929  mov     eax, cs:?s_SslPort@CWmsWebService@@0KA; ulong CWmsWebService::s_SslPort
0x14004d92f  mov     [r15], eax
0x14004d932  mov     eax, [rbp+10h]
0x14004d935  mov     [r14], eax
0x14004d938  mov     rcx, r13; Block
0x14004d93b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004d940  test    rbp, rbp
0x14004d943  jz      short loc_14004D94E
0x14004d945  mov     rcx, rbp; pCertContext
0x14004d948  call    cs:__imp_CertFreeCertificateContext
0x14004d94e  test    r12, r12
0x14004d951  jz      short loc_14004D95E
0x14004d953  xor     edx, edx; dwFlags
0x14004d955  mov     rcx, r12; hCertStore
0x14004d958  call    cs:__imp_CertCloseStore
0x14004d95e  mov     eax, ebx
0x14004d960  add     rsp, 58h
0x14004d964  pop     r15
0x14004d966  pop     r14
0x14004d968  pop     r13
0x14004d96a  pop     r12
0x14004d96c  pop     rdi
0x14004d96d  pop     rsi
0x14004d96e  pop     rbp
0x14004d96f  pop     rbx
0x14004d970  retn
```
