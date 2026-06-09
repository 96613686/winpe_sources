# CWmsWebService::SetReplacementSslCertificate(_WS_OPERATION_CONTEXT const *,_WS_STRING,uint,uchar *,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x140051b60`
- end: `0x140051e68`
- name: `?SetReplacementSslCertificate@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@U_WS_STRING@@IPEAEPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `776`
- prototype: `__int64 __fastcall(const struct _WS_OPERATION_CONTEXT *, struct _WS_STRING *, DWORD, unsigned __int8 *, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, service_task`

## callees

- `0x1400016b8`
- `0x14004c43c`
- `0x14004d3dc`
- `0x140051b60`
- `0x1400599e4`
- `0x14005a300`
- `0x14005b418`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140063fd4`
- `0x140065070`
- `0x14007e010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140051bf7`
- `KERNEL32!GetLastError` at `0x140051bf7`
- `KERNEL32!IsDebuggerPresent` at `0x140051c4f`
- `KERNEL32!IsDebuggerPresent` at `0x140051d69`
- `KERNEL32!IsDebuggerPresent` at `0x140051c4f`
- `KERNEL32!IsDebuggerPresent` at `0x140051d69`
- `CRYPT32!CertCreateCertificateContext` at `0x140051be5`
- `CRYPT32!CertCreateCertificateContext` at `0x140051be5`
- `CRYPT32!CertFreeCertificateContext` at `0x140051e27`
- `CRYPT32!CertFreeCertificateContext` at `0x140051e27`
- `OLEAUT32!__imp_SysAllocString` at `0x140051d02`
- `OLEAUT32!__imp_SysAllocString` at `0x140051d02`
- `OLEAUT32!__imp_SysFreeString` at `0x140051e0f`
- `OLEAUT32!__imp_SysFreeString` at `0x140051e0f`
- `OLEAUT32!__imp_VariantInit` at `0x140051ba8`
- `OLEAUT32!__imp_VariantInit` at `0x140051d2a`
- `OLEAUT32!__imp_VariantInit` at `0x140051ba8`
- `OLEAUT32!__imp_VariantInit` at `0x140051d2a`
- `OLEAUT32!__imp_VariantClear` at `0x140051e19`
- `OLEAUT32!__imp_VariantClear` at `0x140051e19`

## string_xrefs

- `0x140051c1a`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140051d4d`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140051c11`: `CWmsWebService::SetReplacementSslCertificate`
- `0x140051d3b`: `CWmsWebService::SetReplacementSslCertificate`

## pseudocode

```c
__int64 __fastcall CWmsWebService::SetReplacementSslCertificate(
        const struct _WS_OPERATION_CONTEXT *a1,
        struct _WS_STRING *a2,
        DWORD a3,
        unsigned __int8 *a4,
        const struct _WS_ASYNC_CONTEXT *a5,
        struct _WS_ERROR *a6)
{
  OLECHAR *v7; // rsi
  const CERT_CONTEXT *v11; // rdi
  int CertificateThumbprint; // ebx
  const CERT_CONTEXT *CertificateContext; // rax
  signed int LastError; // eax
  int v15; // eax
  __int64 v16; // rax
  BSTR bstrString; // [rsp+40h] [rbp-49h] BYREF
  OLECHAR *psz; // [rsp+48h] [rbp-41h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-29h] BYREF
  VARIANTARG v22; // [rsp+80h] [rbp-9h]

  bstrString = 0;
  v7 = 0;
  psz = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  *(_OWORD *)Block = 0;
  v11 = 0;
  VariantInit(&pvarg);
  CertificateThumbprint = CWmsWebService::s_VerifyAdminAccess(a1, a6);
  if ( CertificateThumbprint >= 0 )
  {
    CertificateThumbprint = WsStringToBstr(a2, &bstrString);
    if ( CertificateThumbprint >= 0 )
    {
      CertificateContext = CertCreateCertificateContext(0x10001u, a4, a3);
      v11 = CertificateContext;
      if ( CertificateContext )
      {
        CertificateThumbprint = GetCertificateThumbprint(CertificateContext, (DWORD *)Block);
        if ( CertificateThumbprint >= 0 )
        {
          v15 = ConvertThumbprintBlobToString((struct _CRYPTOAPI_BLOB *)Block, &psz);
          v7 = psz;
          CertificateThumbprint = v15;
          if ( v15 >= 0 )
          {
            pvarg.vt = 8;
            pvarg.llVal = (LONGLONG)SysAllocString(psz);
            if ( pvarg.llVal )
            {
              CertificateThumbprint = VerifySslCertificate(bstrString, a4, a3);
              if ( CertificateThumbprint >= 0 )
              {
                CertificateThumbprint = AddSerializedCertificateToStore(a4, a3);
                if ( CertificateThumbprint >= 0 )
                {
                  v16 = *(_QWORD *)CWmsWebService::s_pISessionService;
                  v22 = pvarg;
                  CertificateThumbprint = (*(__int64 (__fastcall **)(struct ISessionService *, __int64, BSTR))(v16 + 200))(
                                            CWmsWebService::s_pISessionService,
                                            1,
                                            bstrString);
                }
              }
            }
            else
            {
              CertificateThumbprint = v7 != 0 ? -2147024882 : -2147024809;
              VariantInit(&pvarg);
              LOGASSERTHR(
                L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
                0x972u,
                L"CWmsWebService::SetReplacementSslCertificate",
                L"CHRA",
                L"hr",
                CertificateThumbprint);
              if ( IsDebuggerPresent() )
                DEBUGMSGLEVEL(
                  2u,
                  L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                  L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
                  2418,
                  L"CWmsWebService::SetReplacementSslCertificate",
                  L"CHRA",
                  L"hr",
                  v7 != 0 ? -2147024882 : -2147024809);
              else
                DEBUGMSGBOX(
                  L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                  L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
                  2418,
                  L"CWmsWebService::SetReplacementSslCertificate",
                  L"CHRA",
                  L"hr",
                  v7 != 0 ? -2147024882 : -2147024809);
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        CertificateThumbprint = LastError;
        if ( LastError > 0 )
          CertificateThumbprint = (unsigned __int16)LastError | 0x80070000;
        if ( CertificateThumbprint >= 0 )
          CertificateThumbprint = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
          0x965u,
          L"CWmsWebService::SetReplacementSslCertificate",
          L"CBRAEx",
          L"pNewCert != 0",
          CertificateThumbprint);
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
            2405,
            L"CWmsWebService::SetReplacementSslCertificate",
            L"CBRAEx",
            L"pNewCert != 0",
            CertificateThumbprint);
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
            2405,
            L"CWmsWebService::SetReplacementSslCertificate",
            L"CBRAEx",
            L"pNewCert != 0",
            CertificateThumbprint);
      }
    }
  }
  SysFreeString(bstrString);
  VariantClear(&pvarg);
  if ( v11 )
    CertFreeCertificateContext(v11);
  operator delete(Block[1]);
  operator delete(v7);
  if ( CertificateThumbprint < 0 && a6 )
    CWmsWebService::s_CreateWmsFault(CertificateThumbprint, a6);
  return (unsigned int)CertificateThumbprint;
}

```

## disassembly

```asm
0x140051b60  push    rbp
0x140051b62  push    rbx
0x140051b63  push    rsi
0x140051b64  push    rdi
0x140051b65  push    r13
0x140051b67  push    r14
0x140051b69  push    r15
0x140051b6b  lea     rbp, [rsp-17h]
0x140051b70  sub     rsp, 0A0h
0x140051b77  xorps   xmm0, xmm0
0x140051b7a  mov     [rbp+47h+bstrString], 0
0x140051b82  mov     rbx, rcx
0x140051b85  xor     eax, eax
0x140051b87  xor     esi, esi
0x140051b89  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x140051b8d  lea     rcx, [rbp+47h+pvarg]; pvarg
0x140051b91  mov     [rbp+47h+psz], rsi
0x140051b95  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x140051b99  mov     r14, r9
0x140051b9c  mov     r15d, r8d
0x140051b9f  movups  xmmword ptr [rbp+47h+Block], xmm0
0x140051ba3  mov     r13, rdx
0x140051ba6  xor     edi, edi
0x140051ba8  call    cs:__imp_VariantInit
0x140051bae  mov     rdx, [rbp+47h+arg_28]; struct _WS_ERROR *
0x140051bb2  mov     rcx, rbx; struct _WS_OPERATION_CONTEXT *
0x140051bb5  call    ?s_VerifyAdminAccess@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@PEAU_WS_ERROR@@@Z; CWmsWebService::s_VerifyAdminAccess(_WS_OPERATION_CONTEXT const *,_WS_ERROR *)
0x140051bba  mov     ebx, eax
0x140051bbc  test    eax, eax
0x140051bbe  js      loc_140051E0B
0x140051bc4  lea     rdx, [rbp+47h+bstrString]; unsigned __int16 **
0x140051bc8  mov     rcx, r13; struct _WS_STRING *
0x140051bcb  call    ?WsStringToBstr@@YAJPEBU_WS_STRING@@PEAPEAG@Z; WsStringToBstr(_WS_STRING const *,ushort * *)
0x140051bd0  mov     ebx, eax
0x140051bd2  test    eax, eax
0x140051bd4  js      loc_140051E0B
0x140051bda  mov     r8d, r15d; cbCertEncoded
0x140051bdd  mov     rdx, r14; pbCertEncoded
0x140051be0  mov     ecx, 10001h; dwCertEncodingType
0x140051be5  call    cs:__imp_CertCreateCertificateContext
0x140051beb  mov     rdi, rax
0x140051bee  test    rax, rax
0x140051bf1  jnz     loc_140051CC5
0x140051bf7  call    cs:__imp_GetLastError
0x140051bfd  mov     ebx, eax
0x140051bff  test    eax, eax
0x140051c01  jle     short loc_140051C0C
0x140051c03  movzx   ebx, ax
0x140051c06  or      ebx, 80070000h
0x140051c0c  mov     eax, 80004005h
0x140051c11  lea     r15, aCwmswebservice_52; "CWmsWebService::SetReplacementSslCertif"...
0x140051c18  test    ebx, ebx
0x140051c1a  lea     r14, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140051c21  mov     r13d, 965h
0x140051c27  lea     r9, aCbraex; "CBRAEx"
0x140051c2e  cmovns  ebx, eax
0x140051c31  mov     r8, r15; unsigned __int16 *
0x140051c34  lea     rax, aPnewcert0; "pNewCert != 0"
0x140051c3b  mov     [rsp+0D0h+var_A8], ebx; int
0x140051c3f  mov     edx, r13d; unsigned int
0x140051c42  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x140051c47  mov     rcx, r14; unsigned __int16 *
0x140051c4a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140051c4f  call    cs:__imp_IsDebuggerPresent
0x140051c55  test    eax, eax
0x140051c57  lea     rax, aPnewcert0; "pNewCert != 0"
0x140051c5e  jz      short loc_140051C96
0x140051c60  mov     [rsp+0D0h+var_98], ebx
0x140051c64  mov     [rsp+0D0h+var_A0], rax
0x140051c69  lea     rax, aCbraex; "CBRAEx"
0x140051c70  mov     qword ptr [rsp+0D0h+var_A8], rax
0x140051c75  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140051c7c  mov     r9d, r13d
0x140051c7f  mov     [rsp+0D0h+var_B0], r15
0x140051c84  mov     r8, r14
0x140051c87  mov     ecx, 2; unsigned __int8
0x140051c8c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140051c91  jmp     loc_140051E0B
0x140051c96  mov     dword ptr [rsp+0D0h+var_A0], ebx
0x140051c9a  mov     qword ptr [rsp+0D0h+var_A8], rax
0x140051c9f  lea     rax, aCbraex; "CBRAEx"
0x140051ca6  mov     r9, r15
0x140051ca9  mov     [rsp+0D0h+var_B0], rax
0x140051cae  mov     r8d, r13d
0x140051cb1  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140051cb8  mov     rdx, r14
0x140051cbb  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140051cc0  jmp     loc_140051E0B
0x140051cc5  lea     rdx, [rbp+47h+Block]; pcbData
0x140051cc9  mov     rcx, rax; pCertContext
0x140051ccc  call    ?GetCertificateThumbprint@@YAJPEBU_CERT_CONTEXT@@PEAU_CRYPTOAPI_BLOB@@@Z; GetCertificateThumbprint(_CERT_CONTEXT const *,_CRYPTOAPI_BLOB *)
0x140051cd1  mov     ebx, eax
0x140051cd3  test    eax, eax
0x140051cd5  js      loc_140051E0B
0x140051cdb  lea     rdx, [rbp+47h+psz]; unsigned __int16 **
0x140051cdf  lea     rcx, [rbp+47h+Block]; struct _CRYPTOAPI_BLOB *
0x140051ce3  call    ?ConvertThumbprintBlobToString@@YAJPEAU_CRYPTOAPI_BLOB@@PEAPEAG@Z; ConvertThumbprintBlobToString(_CRYPTOAPI_BLOB *,ushort * *)
0x140051ce8  mov     rsi, [rbp+47h+psz]
0x140051cec  mov     ebx, eax
0x140051cee  test    eax, eax
0x140051cf0  js      loc_140051E0B
0x140051cf6  mov     eax, 8
0x140051cfb  mov     rcx, rsi; psz
0x140051cfe  mov     word ptr [rbp+47h+pvarg], ax
0x140051d02  call    cs:__imp_SysAllocString
0x140051d08  mov     qword ptr [rbp+47h+pvarg+8], rax
0x140051d0c  test    rax, rax
0x140051d0f  jnz     loc_140051DA4
0x140051d15  mov     rax, rsi
0x140051d18  lea     rcx, [rbp+47h+pvarg]; pvarg
0x140051d1c  neg     rax
0x140051d1f  sbb     ebx, ebx
0x140051d21  and     ebx, 0FFFFFFB7h
0x140051d24  add     ebx, 80070057h
0x140051d2a  call    cs:__imp_VariantInit
0x140051d30  lea     rax, aHr; "hr"
0x140051d37  mov     [rsp+0D0h+var_A8], ebx; int
0x140051d3b  lea     r15, aCwmswebservice_52; "CWmsWebService::SetReplacementSslCertif"...
0x140051d42  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x140051d47  mov     r13d, 972h
0x140051d4d  lea     r14, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140051d54  mov     r8, r15; unsigned __int16 *
0x140051d57  lea     r9, aChra; "CHRA"
0x140051d5e  mov     edx, r13d; unsigned int
0x140051d61  mov     rcx, r14; unsigned __int16 *
0x140051d64  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140051d69  call    cs:__imp_IsDebuggerPresent
0x140051d6f  test    eax, eax
0x140051d71  lea     rax, aHr; "hr"
0x140051d78  jz      short loc_140051D8F
0x140051d7a  mov     [rsp+0D0h+var_98], ebx
0x140051d7e  mov     [rsp+0D0h+var_A0], rax
0x140051d83  lea     rax, aChra; "CHRA"
0x140051d8a  jmp     loc_140051C70
0x140051d8f  mov     dword ptr [rsp+0D0h+var_A0], ebx
0x140051d93  mov     qword ptr [rsp+0D0h+var_A8], rax
0x140051d98  lea     rax, aChra; "CHRA"
0x140051d9f  jmp     loc_140051CA6
0x140051da4  mov     rcx, [rbp+47h+bstrString]; String1
0x140051da8  mov     r8d, r15d; unsigned int
0x140051dab  mov     rdx, r14; unsigned __int8 *
0x140051dae  call    ?VerifySslCertificate@@YAJPEAGPEBEK@Z; VerifySslCertificate(ushort *,uchar const *,ulong)
0x140051db3  mov     ebx, eax
0x140051db5  test    eax, eax
0x140051db7  js      short loc_140051E0B
0x140051db9  mov     edx, r15d; cbCertEncoded
0x140051dbc  mov     rcx, r14; pbCertEncoded
0x140051dbf  call    ?AddSerializedCertificateToStore@@YAJPEBEK@Z; AddSerializedCertificateToStore(uchar const *,ulong)
0x140051dc4  mov     ebx, eax
0x140051dc6  test    eax, eax
0x140051dc8  js      short loc_140051E0B
0x140051dca  mov     rcx, cs:?s_pISessionService@CWmsWebService@@0PEAUISessionService@@EA; ISessionService * CWmsWebService::s_pISessionService
0x140051dd1  lea     rdx, [rbp+47h+var_50]
0x140051dd5  movups  xmm0, xmmword ptr [rbp+47h+pvarg]
0x140051dd9  mov     r9d, 5
0x140051ddf  mov     r8, [rbp+47h+bstrString]
0x140051de3  movsd   xmm1, qword ptr [rbp+47h+pvarg+10h]
0x140051de8  mov     rax, [rcx]
0x140051deb  mov     [rsp+0D0h+var_B0], rdx
0x140051df0  lea     edx, [r9-4]
0x140051df4  movaps  [rbp+47h+var_50], xmm0
0x140051df8  movsd   [rbp+47h+var_40], xmm1
0x140051dfd  mov     rax, [rax+0C8h]
0x140051e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140051e09  mov     ebx, eax
0x140051e0b  mov     rcx, [rbp+47h+bstrString]; bstrString
0x140051e0f  call    cs:__imp_SysFreeString
0x140051e15  lea     rcx, [rbp+47h+pvarg]; pvarg
0x140051e19  call    cs:__imp_VariantClear
0x140051e1f  test    rdi, rdi
0x140051e22  jz      short loc_140051E2D
0x140051e24  mov     rcx, rdi; pCertContext
0x140051e27  call    cs:__imp_CertFreeCertificateContext
0x140051e2d  mov     rcx, [rbp+47h+Block+8]; Block
0x140051e31  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140051e36  mov     rcx, rsi; Block
0x140051e39  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140051e3e  test    ebx, ebx
0x140051e40  jns     short loc_140051E54
0x140051e42  cmp     [rbp+47h+arg_28], 0
0x140051e47  jz      short loc_140051E54
0x140051e49  mov     rdx, [rbp+47h+arg_28]; struct _WS_ERROR *
0x140051e4d  mov     ecx, ebx; int
0x140051e4f  call    ?s_CreateWmsFault@CWmsWebService@@CAJJPEAU_WS_ERROR@@@Z; CWmsWebService::s_CreateWmsFault(long,_WS_ERROR *)
0x140051e54  mov     eax, ebx
0x140051e56  add     rsp, 0A0h
0x140051e5d  pop     r15
0x140051e5f  pop     r14
0x140051e61  pop     r13
0x140051e63  pop     rdi
0x140051e64  pop     rsi
0x140051e65  pop     rbx
0x140051e66  pop     rbp
0x140051e67  retn
```
