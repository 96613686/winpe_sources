# CWmsWebServiceProxy::s_GetReplacementSslCertificate(ushort *,ulong,ushort *,ushort *,_CERT_CONTEXT const * *)

- ea: `0x140057ed8`
- end: `0x14005825a`
- name: `?s_GetReplacementSslCertificate@CWmsWebServiceProxy@@SAJPEAGK00PEAPEBU_CERT_CONTEXT@@@Z`
- size: `898`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x14002aa70`

## callees

- `0x1400016c4`
- `0x140057ed8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140076988`
- `0x140076b18`
- `0x140076c98`
- `0x140077448`
- `0x14007e010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140058140`
- `KERNEL32!GetLastError` at `0x140058140`
- `KERNEL32!IsDebuggerPresent` at `0x140057f52`
- `KERNEL32!IsDebuggerPresent` at `0x1400580c5`
- `KERNEL32!IsDebuggerPresent` at `0x140058194`
- `KERNEL32!IsDebuggerPresent` at `0x140058206`
- `KERNEL32!IsDebuggerPresent` at `0x140057f52`
- `KERNEL32!IsDebuggerPresent` at `0x1400580c5`
- `KERNEL32!IsDebuggerPresent` at `0x140058194`
- `KERNEL32!IsDebuggerPresent` at `0x140058206`
- `CRYPT32!CertCreateCertificateContext` at `0x140058132`
- `CRYPT32!CertCreateCertificateContext` at `0x140058132`
- `webservices!WsCall` at `0x14005804a`
- `webservices!WsCall` at `0x14005804a`

## string_xrefs

- `0x1400581e9`: `pWebServiceProxy`
- `0x140057f2e`: `termsrv\wms\src\devices\wmssvc\wmswebserviceproxy.cpp`
- `0x1400580ad`: `termsrv\wms\src\devices\wmssvc\wmswebserviceproxy.cpp`
- `0x140058163`: `termsrv\wms\src\devices\wmssvc\wmswebserviceproxy.cpp`
- `0x1400581e2`: `termsrv\wms\src\devices\wmssvc\wmswebserviceproxy.cpp`
- `0x140057f1d`: `CWmsWebServiceProxy::s_GetReplacementSslCertificate`
- `0x14005805c`: `CWmsWebServiceProxy::s_GetReplacementSslCertificate`
- `0x1400581d1`: `CWmsWebServiceProxy::s_GetReplacementSslCertificate`

## pseudocode

```c
__int64 __fastcall CWmsWebServiceProxy::s_GetReplacementSslCertificate(
        unsigned __int16 *a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        const struct _CERT_CONTEXT **p_cbCertEncoded)
{
  const struct _CERT_CONTEXT **v5; // r14
  int v10; // ebx
  CWebServiceProxy *v11; // rax
  CWebServiceProxy *v12; // r15
  WS_HEAP *v13; // r9
  WS_SERVICE_PROXY *v14; // rcx
  PCCERT_CONTEXT CertificateContext; // rdi
  HRESULT v16; // ebx
  unsigned int v17; // r12d
  bool v18; // zf
  const unsigned __int16 *v19; // rax
  signed int LastError; // eax
  WS_ASYNC_CONTEXT *asyncContext; // [rsp+30h] [rbp-40h]
  WS_ERROR *error; // [rsp+38h] [rbp-38h]
  DWORD cbCertEncoded; // [rsp+40h] [rbp-30h] BYREF
  BYTE *pbCertEncoded; // [rsp+48h] [rbp-28h] BYREF
  BYTE **p_pbCertEncoded; // [rsp+50h] [rbp-20h] BYREF
  void *arguments[3]; // [rsp+58h] [rbp-18h] BYREF

  v5 = p_cbCertEncoded;
  cbCertEncoded = 0;
  pbCertEncoded = 0;
  if ( !p_cbCertEncoded )
  {
    v10 = -2147467261;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceproxy.cpp",
      0x162u,
      L"CWmsWebServiceProxy::s_GetReplacementSslCertificate",
      L"CBRAEx",
      L"ppNewServerCert != 0",
      -2147467261);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceproxy.cpp",
        354,
        L"CWmsWebServiceProxy::s_GetReplacementSslCertificate",
        L"CBRAEx",
        L"ppNewServerCert != 0",
        -2147467261);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceproxy.cpp",
        354,
        L"CWmsWebServiceProxy::s_GetReplacementSslCertificate",
        L"CBRAEx",
        L"ppNewServerCert != 0",
        -2147467261);
    return (unsigned int)v10;
  }
  v11 = (CWebServiceProxy *)operator new(0x158u);
  if ( v11 )
  {
    v12 = CWebServiceProxy::CWebServiceProxy(v11);
    if ( v12 )
    {
      v10 = CWebServiceProxy::Initialize(v12, 2, a1, a2, L"/MultiPoint/IMultiPointServer", a3, a4);
      if ( v10 >= 0 )
      {
        v13 = (WS_HEAP *)*((_QWORD *)v12 + 2);
        v14 = (WS_SERVICE_PROXY *)*((_QWORD *)v12 + 39);
        p_pbCertEncoded = &pbCertEncoded;
        CertificateContext = 0;
        p_cbCertEncoded = (const struct _CERT_CONTEXT **)&cbCertEncoded;
        arguments[0] = &p_cbCertEncoded;
        arguments[1] = &p_pbCertEncoded;
        v16 = WsCall(v14, &stru_140089940, (const void **)arguments, v13, 0, 0, 0, *((WS_ERROR **)v12 + 1));
        CWebServiceProxy::LogError(v12, v16);
        CWebServiceProxy::HandleWebServiceErrorSilently(
          v12,
          L"CWmsWebServiceProxy::s_GetReplacementSslCertificate",
          v16);
        if ( cbCertEncoded )
        {
          if ( !pbCertEncoded )
          {
            v10 = -2147418113;
            v17 = 378;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceproxy.cpp",
              0x17Au,
              L"CWmsWebServiceProxy::s_GetReplacementSslCertificate",
              L"CBRAEx",
              L"pbNewServerCert != 0",
              -2147418113);
            v18 = !IsDebuggerPresent();
            v19 = L"pbNewServerCert != 0";
LABEL_12:
            if ( v18 )
            {
              LODWORD(asyncContext) = v10;
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceproxy.cpp",
                v17,
                L"CWmsWebServiceProxy::s_GetReplacementSslCertificate",
                L"CBRAEx",
                v19,
                asyncContext);
            }
            else
            {
              LODWORD(error) = v10;
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceproxy.cpp",
                v17,
                L"CWmsWebServiceProxy::s_GetReplacementSslCertificate",
                L"CBRAEx",
                v19,
                error);
            }
            goto LABEL_22;
          }
          CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, cbCertEncoded);
          if ( !CertificateContext )
          {
            LastError = GetLastError();
            v10 = LastError;
            if ( LastError > 0 )
              v10 = (unsigned __int16)LastError | 0x80070000;
            v17 = 381;
            if ( v10 >= 0 )
              v10 = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceproxy.cpp",
              0x17Du,
              L"CWmsWebServiceProxy::s_GetReplacementSslCertificate",
              L"CBRAEx",
              L"pCert != 0",
              v10);
            v18 = !IsDebuggerPresent();
            v19 = L"pCert != 0";
            goto LABEL_12;
          }
        }
        v10 = 0;
        *v5 = CertificateContext;
      }
LABEL_22:
      (**(void (__fastcall ***)(CWebServiceProxy *, __int64))v12)(v12, 1);
      return (unsigned int)v10;
    }
  }
  v10 = -2147024882;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceproxy.cpp",
    0x166u,
    L"CWmsWebServiceProxy::s_GetReplacementSslCertificate",
    L"CPR",
    L"pWebServiceProxy",
    -2147024882);
  if ( IsDebuggerPresent() )
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceproxy.cpp",
      358,
      L"CWmsWebServiceProxy::s_GetReplacementSslCertificate",
      L"CPR",
      L"pWebServiceProxy",
      -2147024882);
  else
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceproxy.cpp",
      358,
      L"CWmsWebServiceProxy::s_GetReplacementSslCertificate",
      L"CPR",
      L"pWebServiceProxy",
      -2147024882);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140057ed8  push    rbp
0x140057eda  push    rbx
0x140057edb  push    rsi
0x140057edc  push    rdi
0x140057edd  push    r12
0x140057edf  push    r14
0x140057ee1  push    r15
0x140057ee3  mov     rbp, rsp
0x140057ee6  sub     rsp, 70h
0x140057eea  mov     r14, [rbp+arg_20]
0x140057eee  mov     rbx, r9
0x140057ef1  mov     [rbp+cbCertEncoded], 0
0x140057ef8  mov     rdi, r8
0x140057efb  mov     [rbp+pbCertEncoded], 0
0x140057f03  mov     esi, edx
0x140057f05  mov     r12, rcx
0x140057f08  test    r14, r14
0x140057f0b  jnz     loc_140057FA1
0x140057f11  mov     ebx, 80004003h
0x140057f16  lea     r14, aCbraex; "CBRAEx"
0x140057f1d  lea     rsi, aCwmswebservice_45; "CWmsWebServiceProxy::s_GetReplacementSs"...
0x140057f24  mov     [rsp+70h+callPropertyCount], ebx; int
0x140057f28  mov     r15d, 162h
0x140057f2e  lea     rdi, aTermsrvWmsSrcD_20; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140057f35  lea     r12, aPpnewservercer; "ppNewServerCert != 0"
0x140057f3c  mov     r9, r14; unsigned __int16 *
0x140057f3f  mov     r8, rsi; unsigned __int16 *
0x140057f42  mov     [rsp+70h+callProperties], r12; unsigned __int16 *
0x140057f47  mov     edx, r15d; unsigned int
0x140057f4a  mov     rcx, rdi; unsigned __int16 *
0x140057f4d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140057f52  call    cs:__imp_IsDebuggerPresent
0x140057f58  test    eax, eax
0x140057f5a  jz      short loc_140057F8B
0x140057f5c  mov     dword ptr [rsp+70h+error], ebx
0x140057f60  mov     r9d, r15d
0x140057f63  mov     [rsp+70h+asyncContext], r12
0x140057f68  mov     qword ptr [rsp+70h+callPropertyCount], r14
0x140057f6d  mov     r8, rdi
0x140057f70  mov     [rsp+70h+callProperties], rsi
0x140057f75  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140057f7c  mov     ecx, 2; unsigned __int8
0x140057f81  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140057f86  jmp     loc_140058249
0x140057f8b  mov     dword ptr [rsp+70h+asyncContext], ebx
0x140057f8f  mov     r8d, r15d
0x140057f92  mov     qword ptr [rsp+70h+callPropertyCount], r12
0x140057f97  mov     [rsp+70h+callProperties], r14
0x140057f9c  jmp     loc_140058237
0x140057fa1  mov     ecx, 158h; Size
0x140057fa6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140057fab  test    rax, rax
0x140057fae  jz      loc_1400581C5
0x140057fb4  mov     rcx, rax; this
0x140057fb7  call    ??0CWebServiceProxy@@QEAA@XZ; CWebServiceProxy::CWebServiceProxy(void)
0x140057fbc  mov     r15, rax
0x140057fbf  test    rax, rax
0x140057fc2  jz      loc_1400581C5
0x140057fc8  mov     [rsp+70h+asyncContext], rbx; unsigned __int16 *
0x140057fcd  lea     rax, aMultipointImul_2; "/MultiPoint/IMultiPointServer"
0x140057fd4  mov     qword ptr [rsp+70h+callPropertyCount], rdi; unsigned __int16 *
0x140057fd9  mov     r9d, esi; unsigned int
0x140057fdc  mov     r8, r12; unsigned __int16 *
0x140057fdf  mov     [rsp+70h+callProperties], rax; unsigned __int16 *
0x140057fe4  mov     edx, 2; int
0x140057fe9  mov     rcx, r15; this
0x140057fec  call    ?Initialize@CWebServiceProxy@@QEAAJHPEAGK000@Z; CWebServiceProxy::Initialize(int,ushort *,ulong,ushort *,ushort *,ushort *)
0x140057ff1  mov     ebx, eax
0x140057ff3  test    eax, eax
0x140057ff5  js      loc_1400581AD
0x140057ffb  mov     r9, [r15+10h]; heap
0x140057fff  lea     rax, [rbp+pbCertEncoded]
0x140058003  mov     rcx, [r15+138h]; serviceProxy
0x14005800a  lea     r8, [rbp+arguments]; arguments
0x14005800e  mov     [rbp+var_20], rax
0x140058012  lea     rdx, stru_140089940; operation
0x140058019  xor     edi, edi
0x14005801b  lea     rax, [rbp+cbCertEncoded]
0x14005801f  mov     [rbp+arg_20], rax
0x140058023  lea     rax, [rbp+arg_20]
0x140058027  mov     [rbp+arguments], rax
0x14005802b  lea     rax, [rbp+var_20]
0x14005802f  mov     [rbp+var_10], rax
0x140058033  mov     rax, [r15+8]
0x140058037  mov     [rsp+70h+error], rax; error
0x14005803c  mov     [rsp+70h+asyncContext], rdi; asyncContext
0x140058041  mov     [rsp+70h+callPropertyCount], edi; callPropertyCount
0x140058045  mov     [rsp+70h+callProperties], rdi; callProperties
0x14005804a  call    cs:__imp_WsCall
0x140058050  mov     edx, eax; int
0x140058052  mov     rcx, r15; this
0x140058055  mov     ebx, eax
0x140058057  call    ?LogError@CWebServiceProxy@@QEAAXJ@Z; CWebServiceProxy::LogError(long)
0x14005805c  lea     rsi, aCwmswebservice_45; "CWmsWebServiceProxy::s_GetReplacementSs"...
0x140058063  mov     r8d, ebx; int
0x140058066  mov     rdx, rsi; unsigned __int16 *
0x140058069  mov     rcx, r15; this
0x14005806c  call    ?HandleWebServiceErrorSilently@CWebServiceProxy@@QEAAXPEBGJ@Z; CWebServiceProxy::HandleWebServiceErrorSilently(ushort const *,long)
0x140058071  mov     r8d, [rbp+cbCertEncoded]; cbCertEncoded
0x140058075  test    r8d, r8d
0x140058078  jz      loc_1400581A8
0x14005807e  mov     rdx, [rbp+pbCertEncoded]; pbCertEncoded
0x140058082  test    rdx, rdx
0x140058085  jnz     loc_14005812D
0x14005808b  lea     rax, aPbnewservercer; "pbNewServerCert != 0"
0x140058092  mov     ebx, 8000FFFFh
0x140058097  lea     r14, aCbraex; "CBRAEx"
0x14005809e  mov     [rsp+70h+callPropertyCount], ebx; int
0x1400580a2  mov     r12d, 17Ah
0x1400580a8  mov     [rsp+70h+callProperties], rax; unsigned __int16 *
0x1400580ad  lea     rdi, aTermsrvWmsSrcD_20; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x1400580b4  mov     r9, r14; unsigned __int16 *
0x1400580b7  mov     edx, r12d; unsigned int
0x1400580ba  mov     rcx, rdi; unsigned __int16 *
0x1400580bd  mov     r8, rsi; unsigned __int16 *
0x1400580c0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400580c5  call    cs:__imp_IsDebuggerPresent
0x1400580cb  test    eax, eax
0x1400580cd  lea     rax, aPbnewservercer; "pbNewServerCert != 0"
0x1400580d4  jz      short loc_140058105
0x1400580d6  mov     dword ptr [rsp+70h+error], ebx
0x1400580da  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400580e1  mov     [rsp+70h+asyncContext], rax
0x1400580e6  mov     r9d, r12d
0x1400580e9  mov     qword ptr [rsp+70h+callPropertyCount], r14
0x1400580ee  mov     r8, rdi
0x1400580f1  mov     ecx, 2; unsigned __int8
0x1400580f6  mov     [rsp+70h+callProperties], rsi
0x1400580fb  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140058100  jmp     loc_1400581AD
0x140058105  mov     dword ptr [rsp+70h+asyncContext], ebx
0x140058109  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140058110  mov     qword ptr [rsp+70h+callPropertyCount], rax
0x140058115  mov     r9, rsi
0x140058118  mov     r8d, r12d
0x14005811b  mov     [rsp+70h+callProperties], r14
0x140058120  mov     rdx, rdi
0x140058123  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140058128  jmp     loc_1400581AD
0x14005812d  mov     ecx, 10001h; dwCertEncodingType
0x140058132  call    cs:__imp_CertCreateCertificateContext
0x140058138  mov     rdi, rax
0x14005813b  test    rax, rax
0x14005813e  jnz     short loc_1400581A8
0x140058140  call    cs:__imp_GetLastError
0x140058146  mov     ebx, eax
0x140058148  test    eax, eax
0x14005814a  jle     short loc_140058155
0x14005814c  movzx   ebx, ax
0x14005814f  or      ebx, 80070000h
0x140058155  mov     eax, 80004005h
0x14005815a  lea     r14, aCbraex; "CBRAEx"
0x140058161  test    ebx, ebx
0x140058163  lea     rdi, aTermsrvWmsSrcD_20; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005816a  mov     r12d, 17Dh
0x140058170  mov     r9, r14; unsigned __int16 *
0x140058173  cmovns  ebx, eax
0x140058176  mov     r8, rsi; unsigned __int16 *
0x140058179  lea     rax, aPcert0; "pCert != 0"
0x140058180  mov     [rsp+70h+callPropertyCount], ebx; int
0x140058184  mov     edx, r12d; unsigned int
0x140058187  mov     [rsp+70h+callProperties], rax; unsigned __int16 *
0x14005818c  mov     rcx, rdi; unsigned __int16 *
0x14005818f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140058194  call    cs:__imp_IsDebuggerPresent
0x14005819a  test    eax, eax
0x14005819c  lea     rax, aPcert0; "pCert != 0"
0x1400581a3  jmp     loc_1400580D4
0x1400581a8  xor     ebx, ebx
0x1400581aa  mov     [r14], rdi
0x1400581ad  mov     rax, [r15]
0x1400581b0  mov     edx, 1
0x1400581b5  mov     rcx, r15
0x1400581b8  mov     rax, [rax]
0x1400581bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400581c0  jmp     loc_140058249
0x1400581c5  mov     ebx, 8007000Eh
0x1400581ca  lea     r12, aCpr; "CPR"
0x1400581d1  lea     rsi, aCwmswebservice_45; "CWmsWebServiceProxy::s_GetReplacementSs"...
0x1400581d8  mov     [rsp+70h+callPropertyCount], ebx; int
0x1400581dc  mov     r14d, 166h
0x1400581e2  lea     rdi, aTermsrvWmsSrcD_20; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x1400581e9  lea     r15, aPwebservicepro; "pWebServiceProxy"
0x1400581f0  mov     r9, r12; unsigned __int16 *
0x1400581f3  mov     r8, rsi; unsigned __int16 *
0x1400581f6  mov     [rsp+70h+callProperties], r15; unsigned __int16 *
0x1400581fb  mov     edx, r14d; unsigned int
0x1400581fe  mov     rcx, rdi; unsigned __int16 *
0x140058201  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140058206  call    cs:__imp_IsDebuggerPresent
0x14005820c  test    eax, eax
0x14005820e  jz      short loc_140058226
0x140058210  mov     dword ptr [rsp+70h+error], ebx
0x140058214  mov     r9d, r14d
0x140058217  mov     [rsp+70h+asyncContext], r15
0x14005821c  mov     qword ptr [rsp+70h+callPropertyCount], r12
0x140058221  jmp     loc_140057F6D
0x140058226  mov     dword ptr [rsp+70h+asyncContext], ebx
0x14005822a  mov     r8d, r14d
0x14005822d  mov     qword ptr [rsp+70h+callPropertyCount], r15
0x140058232  mov     [rsp+70h+callProperties], r12
0x140058237  mov     r9, rsi
0x14005823a  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140058241  mov     rdx, rdi
0x140058244  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140058249  mov     eax, ebx
0x14005824b  add     rsp, 70h
0x14005824f  pop     r15
0x140058251  pop     r14
0x140058253  pop     r12
0x140058255  pop     rdi
0x140058256  pop     rsi
0x140058257  pop     rbx
0x140058258  pop     rbp
0x140058259  retn
```
