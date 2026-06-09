# CWebServiceProxy::s_VerifyServerCert(_CERT_CONTEXT const *,void *)

- ea: `0x140077730`
- end: `0x140077955`
- name: `?s_VerifyServerCert@CWebServiceProxy@@CAJPEBU_CERT_CONTEXT@@PEAX@Z`
- size: `549`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *pvFindPara, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140077730`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140077815`
- `KERNEL32!GetLastError` at `0x140077875`
- `KERNEL32!GetLastError` at `0x140077815`
- `KERNEL32!GetLastError` at `0x140077875`
- `KERNEL32!IsDebuggerPresent` at `0x14007778c`
- `KERNEL32!IsDebuggerPresent` at `0x1400778cc`
- `KERNEL32!IsDebuggerPresent` at `0x14007778c`
- `KERNEL32!IsDebuggerPresent` at `0x1400778cc`
- `CRYPT32!CertFindCertificateInStore` at `0x140077863`
- `CRYPT32!CertFindCertificateInStore` at `0x140077863`
- `CRYPT32!CertCloseStore` at `0x140077930`
- `CRYPT32!CertCloseStore` at `0x140077930`
- `CRYPT32!CertOpenStore` at `0x140077807`
- `CRYPT32!CertOpenStore` at `0x140077807`
- `CRYPT32!CertFreeCertificateContext` at `0x14007793e`
- `CRYPT32!CertFreeCertificateContext` at `0x14007793e`

## string_xrefs

- `0x140077774`: `termsrv\wms\src\common\srcutils\cwebserviceproxy.cpp`
- `0x14007789f`: `termsrv\wms\src\common\srcutils\cwebserviceproxy.cpp`
- `0x140077768`: `CWebServiceProxy::s_VerifyServerCert`
- `0x140077898`: `CWebServiceProxy::s_VerifyServerCert`
- `0x1400777ef`: `MultiPoint Services Certificates`

## pseudocode

```c
__int64 __fastcall CWebServiceProxy::s_VerifyServerCert(const struct _CERT_CONTEXT *pvFindPara, void *a2)
{
  signed int v3; // ebx
  const unsigned __int16 *v4; // r15
  unsigned int v5; // r14d
  HCERTSTORE v6; // rax
  void *v7; // r15
  signed int LastError; // eax
  const CERT_CONTEXT *CertificateInStore; // r14
  signed int v10; // eax

  if ( !pvFindPara )
  {
    v3 = -2147024809;
    v4 = L"pCertServer != 0";
    v5 = 440;
LABEL_3:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
      v5,
      L"CWebServiceProxy::s_VerifyServerCert",
      L"CBRAEx",
      v4,
      v3);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        v5,
        L"CWebServiceProxy::s_VerifyServerCert",
        L"CBRAEx",
        v4,
        v3);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        v5,
        L"CWebServiceProxy::s_VerifyServerCert",
        L"CBRAEx",
        v4,
        v3);
    return (unsigned int)v3;
  }
  v6 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"MultiPoint Services Certificates");
  v7 = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = L"hCertStoreWms != 0";
    v5 = 451;
    if ( v3 >= 0 )
      v3 = -2147467259;
    goto LABEL_3;
  }
  v3 = 0;
  CertificateInStore = CertFindCertificateInStore(v6, 0x10001u, 0, 0xD0000u, pvFindPara, 0);
  if ( !CertificateInStore )
  {
    v10 = GetLastError();
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
      0x1CFu,
      L"CWebServiceProxy::s_VerifyServerCert",
      L"CBRAEx",
      L"hCertMatching != 0",
      v3);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        463,
        L"CWebServiceProxy::s_VerifyServerCert",
        L"CBRAEx",
        L"hCertMatching != 0",
        v3);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\cwebserviceproxy.cpp",
        463,
        L"CWebServiceProxy::s_VerifyServerCert",
        L"CBRAEx",
        L"hCertMatching != 0",
        v3);
  }
  CertCloseStore(v7, 0);
  if ( CertificateInStore )
    CertFreeCertificateContext(CertificateInStore);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140077730  push    rbx
0x140077732  push    rbp
0x140077733  push    rsi
0x140077734  push    rdi
0x140077735  push    r13
0x140077737  push    r14
0x140077739  push    r15
0x14007773b  sub     rsp, 40h
0x14007773f  mov     rdi, rcx
0x140077742  test    rcx, rcx
0x140077745  jnz     loc_1400777ED
0x14007774b  mov     ebx, 80070057h
0x140077750  lea     r15, aPcertserver0; "pCertServer != 0"
0x140077757  mov     r14d, 1B8h
0x14007775d  lea     rbp, aCbraex; "CBRAEx"
0x140077764  mov     dword ptr [rsp+78h+pPrevCertContext], ebx; int
0x140077768  lea     rsi, aCwebservicepro_6; "CWebServiceProxy::s_VerifyServerCert"
0x14007776f  mov     [rsp+78h+pvPara], r15; unsigned __int16 *
0x140077774  lea     rdi, aTermsrvWmsSrcC_9; "termsrv\\wms\\src\\common\\srcutils\\cw"...
0x14007777b  mov     r9, rbp; unsigned __int16 *
0x14007777e  mov     r8, rsi; unsigned __int16 *
0x140077781  mov     rcx, rdi; unsigned __int16 *
0x140077784  mov     edx, r14d; unsigned int
0x140077787  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007778c  call    cs:__imp_IsDebuggerPresent
0x140077792  test    eax, eax
0x140077794  jz      short loc_1400777C5
0x140077796  mov     [rsp+78h+var_40], ebx
0x14007779a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400777a1  mov     [rsp+78h+var_48], r15
0x1400777a6  mov     r9d, r14d
0x1400777a9  mov     [rsp+78h+pPrevCertContext], rbp
0x1400777ae  mov     r8, rdi
0x1400777b1  mov     ecx, 2; unsigned __int8
0x1400777b6  mov     [rsp+78h+pvPara], rsi
0x1400777bb  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400777c0  jmp     loc_140077944
0x1400777c5  mov     dword ptr [rsp+78h+var_48], ebx
0x1400777c9  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400777d0  mov     [rsp+78h+pPrevCertContext], r15
0x1400777d5  mov     r9, rsi
0x1400777d8  mov     r8d, r14d
0x1400777db  mov     [rsp+78h+pvPara], rbp
0x1400777e0  mov     rdx, rdi
0x1400777e3  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400777e8  jmp     loc_140077944
0x1400777ed  xor     edx, edx; dwEncodingType
0x1400777ef  lea     rax, aMultipointServ_0; "MultiPoint Services Certificates"
0x1400777f6  mov     r9d, 28000h; dwFlags
0x1400777fc  mov     [rsp+78h+pvPara], rax; pvPara
0x140077801  xor     r8d, r8d; hCryptProv
0x140077804  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x140077807  call    cs:__imp_CertOpenStore
0x14007780d  mov     r15, rax
0x140077810  test    rax, rax
0x140077813  jnz     short loc_140077846
0x140077815  call    cs:__imp_GetLastError
0x14007781b  mov     ebx, eax
0x14007781d  test    eax, eax
0x14007781f  jle     short loc_14007782A
0x140077821  movzx   ebx, ax
0x140077824  or      ebx, 80070000h
0x14007782a  test    ebx, ebx
0x14007782c  lea     r15, aHcertstorewms0; "hCertStoreWms != 0"
0x140077833  mov     eax, 80004005h
0x140077838  mov     r14d, 1C3h
0x14007783e  cmovns  ebx, eax
0x140077841  jmp     loc_14007775D
0x140077846  xor     ebx, ebx
0x140077848  mov     r9d, 0D0000h; dwFindType
0x14007784e  mov     [rsp+78h+pPrevCertContext], rbx; pPrevCertContext
0x140077853  xor     r8d, r8d; dwFindFlags
0x140077856  mov     edx, 10001h; dwCertEncodingType
0x14007785b  mov     [rsp+78h+pvPara], rdi; pvFindPara
0x140077860  mov     rcx, r15; hCertStore
0x140077863  call    cs:__imp_CertFindCertificateInStore
0x140077869  mov     r14, rax
0x14007786c  test    rax, rax
0x14007786f  jnz     loc_14007792B
0x140077875  call    cs:__imp_GetLastError
0x14007787b  mov     ebx, eax
0x14007787d  test    eax, eax
0x14007787f  jle     short loc_14007788A
0x140077881  movzx   ebx, ax
0x140077884  or      ebx, 80070000h
0x14007788a  mov     eax, 80004005h
0x14007788f  lea     rbp, aCbraex; "CBRAEx"
0x140077896  test    ebx, ebx
0x140077898  lea     rsi, aCwebservicepro_6; "CWebServiceProxy::s_VerifyServerCert"
0x14007789f  lea     rdi, aTermsrvWmsSrcC_9; "termsrv\\wms\\src\\common\\srcutils\\cw"...
0x1400778a6  mov     r9, rbp; unsigned __int16 *
0x1400778a9  cmovns  ebx, eax
0x1400778ac  lea     r13, aHcertmatching0; "hCertMatching != 0"
0x1400778b3  mov     dword ptr [rsp+78h+pPrevCertContext], ebx; int
0x1400778b7  mov     r8, rsi; unsigned __int16 *
0x1400778ba  mov     edx, 1CFh; unsigned int
0x1400778bf  mov     [rsp+78h+pvPara], r13; unsigned __int16 *
0x1400778c4  mov     rcx, rdi; unsigned __int16 *
0x1400778c7  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400778cc  call    cs:__imp_IsDebuggerPresent
0x1400778d2  test    eax, eax
0x1400778d4  jz      short loc_140077905
0x1400778d6  mov     [rsp+78h+var_40], ebx
0x1400778da  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400778e1  mov     [rsp+78h+var_48], r13
0x1400778e6  mov     r9d, 1CFh
0x1400778ec  mov     [rsp+78h+pPrevCertContext], rbp
0x1400778f1  mov     r8, rdi
0x1400778f4  mov     ecx, 2; unsigned __int8
0x1400778f9  mov     [rsp+78h+pvPara], rsi
0x1400778fe  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140077903  jmp     short loc_14007792B
0x140077905  mov     dword ptr [rsp+78h+var_48], ebx
0x140077909  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140077910  mov     [rsp+78h+pPrevCertContext], r13
0x140077915  mov     r9, rsi
0x140077918  mov     r8d, 1CFh
0x14007791e  mov     [rsp+78h+pvPara], rbp
0x140077923  mov     rdx, rdi
0x140077926  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007792b  xor     edx, edx; dwFlags
0x14007792d  mov     rcx, r15; hCertStore
0x140077930  call    cs:__imp_CertCloseStore
0x140077936  test    r14, r14
0x140077939  jz      short loc_140077944
0x14007793b  mov     rcx, r14; pCertContext
0x14007793e  call    cs:__imp_CertFreeCertificateContext
0x140077944  mov     eax, ebx
0x140077946  add     rsp, 40h
0x14007794a  pop     r15
0x14007794c  pop     r14
0x14007794e  pop     r13
0x140077950  pop     rdi
0x140077951  pop     rsi
0x140077952  pop     rbp
0x140077953  pop     rbx
0x140077954  retn
```
