# CWmsWebService::s_DoesReplacementCertExist(_CERT_CONTEXT const * *)

- ea: `0x14004c738`
- end: `0x14004cbe3`
- name: `?s_DoesReplacementCertExist@CWmsWebService@@SAJPEAPEBU_CERT_CONTEXT@@@Z`
- size: `1195`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT **)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14002b2ac`
- `0x14002ba9c`
- `0x140047f10`
- `0x14004f150`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14004c738`
- `0x140059ec0`
- `0x14005ae70`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140064148`
- `0x14006440c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14004ca7e`
- `ADVAPI32!RegOpenKeyExW` at `0x14004ca7e`
- `ADVAPI32!RegGetValueW` at `0x14004c85e`
- `ADVAPI32!RegGetValueW` at `0x14004c9bf`
- `ADVAPI32!RegGetValueW` at `0x14004c85e`
- `ADVAPI32!RegGetValueW` at `0x14004c9bf`
- `ADVAPI32!RegCloseKey` at `0x14004cba3`
- `ADVAPI32!RegCloseKey` at `0x14004cba3`
- `ADVAPI32!RegDeleteValueW` at `0x14004cafb`
- `ADVAPI32!RegDeleteValueW` at `0x14004cafb`
- `KERNEL32!IsDebuggerPresent` at `0x14004c7bc`
- `KERNEL32!IsDebuggerPresent` at `0x14004c8b8`
- `KERNEL32!IsDebuggerPresent` at `0x14004c951`
- `KERNEL32!IsDebuggerPresent` at `0x14004cacd`
- `KERNEL32!IsDebuggerPresent` at `0x14004cb4e`
- `KERNEL32!IsDebuggerPresent` at `0x14004c7bc`
- `KERNEL32!IsDebuggerPresent` at `0x14004c8b8`
- `KERNEL32!IsDebuggerPresent` at `0x14004c951`
- `KERNEL32!IsDebuggerPresent` at `0x14004cacd`
- `KERNEL32!IsDebuggerPresent` at `0x14004cb4e`
- `CRYPT32!CertFreeCertificateContext` at `0x14004ca49`
- `CRYPT32!CertFreeCertificateContext` at `0x14004cbb9`
- `CRYPT32!CertFreeCertificateContext` at `0x14004ca49`
- `CRYPT32!CertFreeCertificateContext` at `0x14004cbb9`

## string_xrefs

- `0x14004c7a4`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004c8a1`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004c935`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004cab6`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004cb37`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004c77b`: `ppReplacementCert != 0`
- `0x14004c7c4`: `ppReplacementCert != 0`
- `0x14004c792`: `CWmsWebService::s_DoesReplacementCertExist`
- `0x14004c897`: `CWmsWebService::s_DoesReplacementCertExist`
- `0x14004c91f`: `CWmsWebService::s_DoesReplacementCertExist`
- `0x14004caac`: `CWmsWebService::s_DoesReplacementCertExist`
- `0x14004cb2d`: `CWmsWebService::s_DoesReplacementCertExist`
- `0x14004c8f3`: `CWmsWebService::s_DoesReplacementCertExist - Reg value %s does not exist.\n`
- `0x14004cb89`: `CWmsWebService::s_DoesReplacementCertExist - Replacement SSL cert with thumbprint %s is NOT present.\n`
- `0x14004ca3a`: `CWmsWebService::s_DoesReplacementCertExist - Replacement SSL cert with thumbprint %s has expired.\n`
- `0x14004cb75`: `CWmsWebService::s_DoesReplacementCertExist - Replacement SSL cert with thumbprint %s is present.\n`
- `0x14004c830`: `ReplacementSslCertificateThumbprint`

## pseudocode

```c
__int64 __fastcall CWmsWebService::s_DoesReplacementCertExist(const struct _CERT_CONTEXT **a1)
{
  void *v1; // r12
  PCCERT_CONTEXT v2; // r14
  signed int v4; // ebx
  bool v5; // zf
  const unsigned __int16 *v6; // rax
  __int64 v7; // r9
  __int64 v8; // r8
  LSTATUS ValueW; // eax
  LSTATUS v10; // eax
  int CertificateContext; // eax
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  const unsigned __int16 *pvData; // [rsp+28h] [rbp-30h]
  LPDWORD pcbData; // [rsp+30h] [rbp-28h]
  const unsigned __int16 *pcbDataa; // [rsp+30h] [rbp-28h]
  int v18; // [rsp+38h] [rbp-20h]
  void *Block[2]; // [rsp+40h] [rbp-18h] BYREF
  DWORD v20; // [rsp+A0h] [rbp+48h] BYREF
  int v21; // [rsp+A8h] [rbp+50h] BYREF
  HKEY phkResult; // [rsp+B0h] [rbp+58h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+B8h] [rbp+60h] BYREF

  v1 = 0;
  v20 = 0;
  v2 = 0;
  v21 = 1;
  pCertContext = 0;
  phkResult = 0;
  *(_OWORD *)Block = 0;
  if ( !a1 )
  {
    v4 = -2147467261;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x763u,
      L"CWmsWebService::s_DoesReplacementCertExist",
      L"CBRAEx",
      L"ppReplacementCert != 0",
      -2147467261);
    v5 = !IsDebuggerPresent();
    v6 = L"ppReplacementCert != 0";
    if ( !v5 )
    {
      v18 = -2147467261;
      pcbDataa = L"ppReplacementCert != 0";
      v7 = 1891;
      pvData = L"CBRAEx";
LABEL_4:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        v7,
        L"CWmsWebService::s_DoesReplacementCertExist",
        pvData,
        pcbDataa,
        v18,
        Block[0],
        Block[1]);
      goto LABEL_44;
    }
    v8 = 1891;
    goto LABEL_6;
  }
  *a1 = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
             L"ReplacementSslCertificateThumbprint",
             2u,
             0,
             0,
             &v20);
  v4 = ValueW;
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      if ( ValueW > 0 )
        v4 = (unsigned __int16)ValueW | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        0x76Du,
        L"CWmsWebService::s_DoesReplacementCertExist",
        L"CBRAEx",
        L"(lr == 0L) || (lr == 2L)",
        v4);
      v5 = !IsDebuggerPresent();
      v6 = L"(lr == 0L) || (lr == 2L)";
      if ( !v5 )
      {
        v7 = 1901;
LABEL_13:
        v18 = v4;
        pcbDataa = v6;
        pvData = L"CBRAEx";
        goto LABEL_4;
      }
      v8 = 1901;
      goto LABEL_6;
    }
    DEBUGMSG(
      L"CWmsWebService::s_DoesReplacementCertExist - Reg value %s does not exist.\n",
      L"ReplacementSslCertificateThumbprint");
LABEL_43:
    v4 = 0;
    goto LABEL_44;
  }
  v1 = operator new(v20);
  if ( v1 )
  {
    v10 = RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
            L"ReplacementSslCertificateThumbprint",
            2u,
            0,
            v1,
            &v20);
    v4 = v10;
    if ( !v10 )
    {
      if ( (int)ConvertThumbprintStringToBlob((const unsigned __int16 *)v1, (struct _CRYPTOAPI_BLOB *)Block) >= 0
        && (CertificateContext = GetCertificateContext(Block, 0, &pCertContext),
            v2 = pCertContext,
            CertificateContext >= 0)
        && pCertContext )
      {
        v4 = IsCertExpired(pCertContext, &v21);
        if ( v4 < 0 )
          goto LABEL_44;
        if ( !v21 )
        {
          DEBUGMSG(
            L"CWmsWebService::s_DoesReplacementCertExist - Replacement SSL cert with thumbprint %s is present.\n",
            v1);
          *a1 = v2;
          v2 = 0;
          goto LABEL_44;
        }
        DEBUGMSG(
          L"CWmsWebService::s_DoesReplacementCertExist - Replacement SSL cert with thumbprint %s has expired.\n",
          v1);
        CertFreeCertificateContext(v2);
        v2 = 0;
        v4 = DeleteCert((struct _CRYPTOAPI_BLOB *)Block);
        if ( v4 < 0 )
          goto LABEL_44;
        v12 = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
                0,
                2u,
                &phkResult);
        v4 = v12;
        if ( v12 )
        {
          if ( v12 > 0 )
            v4 = (unsigned __int16)v12 | 0x80070000;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
            0x7A6u,
            L"CWmsWebService::s_DoesReplacementCertExist",
            L"CBRAEx",
            L"lr == 0L",
            v4);
          v5 = !IsDebuggerPresent();
          v6 = L"lr == 0L";
          if ( !v5 )
          {
            v7 = 1958;
            goto LABEL_13;
          }
          v8 = 1958;
LABEL_6:
          LODWORD(pcbData) = v4;
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
            v8,
            L"CWmsWebService::s_DoesReplacementCertExist",
            L"CBRAEx",
            v6,
            pcbData);
          goto LABEL_44;
        }
        v13 = RegDeleteValueW(phkResult, L"ReplacementSslCertificateThumbprint");
        v4 = v13;
        if ( v13 )
        {
          if ( v13 > 0 )
            v4 = (unsigned __int16)v13 | 0x80070000;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
            0x7A9u,
            L"CWmsWebService::s_DoesReplacementCertExist",
            L"CBRAEx",
            L"lr == 0L",
            v4);
          v5 = !IsDebuggerPresent();
          v6 = L"lr == 0L";
          if ( !v5 )
          {
            v7 = 1961;
            goto LABEL_13;
          }
          v8 = 1961;
          goto LABEL_6;
        }
      }
      else
      {
        DEBUGMSG(
          L"CWmsWebService::s_DoesReplacementCertExist - Replacement SSL cert with thumbprint %s is NOT present.\n",
          v1);
      }
      goto LABEL_43;
    }
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
  }
  else
  {
    v4 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      0x77Bu,
      L"CWmsWebService::s_DoesReplacementCertExist",
      L"CPR",
      L"pszThumbprint",
      -2147024882);
    if ( IsDebuggerPresent() )
    {
      v18 = -2147024882;
      v7 = 1915;
      pcbDataa = L"pszThumbprint";
      pvData = L"CPR";
      goto LABEL_4;
    }
    LODWORD(pcbData) = -2147024882;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      1915,
      L"CWmsWebService::s_DoesReplacementCertExist",
      L"CPR",
      L"pszThumbprint",
      pcbData);
  }
LABEL_44:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v2 )
    CertFreeCertificateContext(v2);
  operator delete(v1);
  operator delete(Block[1]);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14004c738  push    rbp
0x14004c73a  push    rbx
0x14004c73b  push    rsi
0x14004c73c  push    rdi
0x14004c73d  push    r12
0x14004c73f  push    r13
0x14004c741  push    r14
0x14004c743  push    r15
0x14004c745  mov     rbp, rsp
0x14004c748  sub     rsp, 58h
0x14004c74c  xor     r12d, r12d
0x14004c74f  mov     [rbp+arg_0], 0
0x14004c756  xor     r14d, r14d
0x14004c759  mov     [rbp+arg_8], 1
0x14004c760  mov     [rbp+pCertContext], r14
0x14004c764  xorps   xmm0, xmm0
0x14004c767  mov     [rbp+phkResult], r12
0x14004c76b  mov     rdi, rcx
0x14004c76e  movups  xmmword ptr [rbp+Block], xmm0
0x14004c772  test    rcx, rcx
0x14004c775  jnz     loc_14004C824
0x14004c77b  lea     rax, aPpreplacementc; "ppReplacementCert != 0"
0x14004c782  mov     ebx, 80004003h
0x14004c787  lea     r15, aCbraex; "CBRAEx"
0x14004c78e  mov     dword ptr [rsp+58h+pvData], ebx; int
0x14004c792  lea     rsi, aCwmswebservice_31; "CWmsWebService::s_DoesReplacementCertEx"...
0x14004c799  mov     [rsp+58h+pdwType], rax; unsigned __int16 *
0x14004c79e  mov     r13d, 763h
0x14004c7a4  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004c7ab  mov     r9, r15; unsigned __int16 *
0x14004c7ae  mov     r8, rsi; unsigned __int16 *
0x14004c7b1  mov     edx, r13d; unsigned int
0x14004c7b4  mov     rcx, rdi; unsigned __int16 *
0x14004c7b7  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004c7bc  call    cs:__imp_IsDebuggerPresent
0x14004c7c2  test    eax, eax
0x14004c7c4  lea     rax, aPpreplacementc; "ppReplacementCert != 0"
0x14004c7cb  jz      short loc_14004C7FC
0x14004c7cd  mov     [rsp+58h+var_20], ebx
0x14004c7d1  lea     ecx, [r12+2]; unsigned __int8
0x14004c7d6  mov     [rsp+58h+pcbData], rax
0x14004c7db  mov     r9d, r13d
0x14004c7de  mov     [rsp+58h+pvData], r15
0x14004c7e3  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14004c7ea  mov     [rsp+58h+pdwType], rsi
0x14004c7ef  mov     r8, rdi
0x14004c7f2  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004c7f7  jmp     loc_14004CB9A
0x14004c7fc  mov     r8d, r13d
0x14004c7ff  mov     dword ptr [rsp+58h+pcbData], ebx
0x14004c803  mov     [rsp+58h+pvData], rax
0x14004c808  mov     [rsp+58h+pdwType], r15
0x14004c80d  mov     r9, rsi
0x14004c810  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14004c817  mov     rdx, rdi
0x14004c81a  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14004c81f  jmp     loc_14004CB9A
0x14004c824  lea     rax, [rbp+arg_0]
0x14004c828  mov     [rcx], r12
0x14004c82b  mov     [rsp+58h+pcbData], rax; pcbData
0x14004c830  lea     rsi, aReplacementssl; "ReplacementSslCertificateThumbprint"
0x14004c837  mov     r13d, 2
0x14004c83d  mov     [rsp+58h+pvData], r12; pvData
0x14004c842  lea     r15, aSoftwareMicros_25; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x14004c849  mov     [rsp+58h+pdwType], r12; pdwType
0x14004c84e  mov     r9d, r13d; dwFlags
0x14004c851  mov     r8, rsi; lpValue
0x14004c854  mov     rdx, r15; lpSubKey
0x14004c857  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14004c85e  call    cs:__imp_RegGetValueW
0x14004c864  mov     ebx, eax
0x14004c866  test    eax, eax
0x14004c868  jz      loc_14004C8FF
0x14004c86e  cmp     eax, r13d
0x14004c871  jz      short loc_14004C8F0
0x14004c873  test    eax, eax
0x14004c875  jle     short loc_14004C880
0x14004c877  movzx   ebx, ax
0x14004c87a  or      ebx, 80070000h
0x14004c880  lea     rax, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x14004c887  mov     dword ptr [rsp+58h+pvData], ebx; int
0x14004c88b  lea     r15, aCbraex; "CBRAEx"
0x14004c892  mov     [rsp+58h+pdwType], rax; unsigned __int16 *
0x14004c897  lea     rsi, aCwmswebservice_31; "CWmsWebService::s_DoesReplacementCertEx"...
0x14004c89e  mov     r9, r15; unsigned __int16 *
0x14004c8a1  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004c8a8  mov     r8, rsi; unsigned __int16 *
0x14004c8ab  mov     rcx, rdi; unsigned __int16 *
0x14004c8ae  mov     edx, 76Dh; unsigned int
0x14004c8b3  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004c8b8  call    cs:__imp_IsDebuggerPresent
0x14004c8be  test    eax, eax
0x14004c8c0  lea     rax, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x14004c8c7  jz      short loc_14004C8E5
0x14004c8c9  mov     r9d, 76Dh
0x14004c8cf  mov     [rsp+58h+var_20], ebx
0x14004c8d3  mov     [rsp+58h+pcbData], rax
0x14004c8d8  mov     [rsp+58h+pvData], r15
0x14004c8dd  mov     ecx, r13d
0x14004c8e0  jmp     loc_14004C7E3
0x14004c8e5  mov     r8d, 76Dh
0x14004c8eb  jmp     loc_14004C7FF
0x14004c8f0  mov     rdx, rsi
0x14004c8f3  lea     rcx, aCwmswebservice_41; "CWmsWebService::s_DoesReplacementCertEx"...
0x14004c8fa  jmp     loc_14004CB93
0x14004c8ff  mov     ecx, [rbp+arg_0]; Size
0x14004c902  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004c907  mov     r12, rax
0x14004c90a  test    rax, rax
0x14004c90d  jnz     loc_14004C99C
0x14004c913  lea     rax, aPszthumbprint; "pszThumbprint"
0x14004c91a  mov     ebx, 8007000Eh
0x14004c91f  lea     rsi, aCwmswebservice_31; "CWmsWebService::s_DoesReplacementCertEx"...
0x14004c926  mov     dword ptr [rsp+58h+pvData], ebx; int
0x14004c92a  mov     r15d, 77Bh
0x14004c930  mov     [rsp+58h+pdwType], rax; unsigned __int16 *
0x14004c935  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004c93c  mov     r8, rsi; unsigned __int16 *
0x14004c93f  mov     edx, r15d; unsigned int
0x14004c942  lea     r9, aCpr; "CPR"
0x14004c949  mov     rcx, rdi; unsigned __int16 *
0x14004c94c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004c951  call    cs:__imp_IsDebuggerPresent
0x14004c957  test    eax, eax
0x14004c959  lea     rax, aPszthumbprint; "pszThumbprint"
0x14004c960  jz      short loc_14004C97F
0x14004c962  mov     [rsp+58h+var_20], ebx
0x14004c966  mov     r9d, r15d
0x14004c969  mov     [rsp+58h+pcbData], rax
0x14004c96e  lea     rax, aCpr; "CPR"
0x14004c975  mov     [rsp+58h+pvData], rax
0x14004c97a  jmp     loc_14004C8DD
0x14004c97f  mov     dword ptr [rsp+58h+pcbData], ebx
0x14004c983  mov     r8d, r15d
0x14004c986  mov     [rsp+58h+pvData], rax
0x14004c98b  lea     rax, aCpr; "CPR"
0x14004c992  mov     [rsp+58h+pdwType], rax
0x14004c997  jmp     loc_14004C80D
0x14004c99c  lea     rax, [rbp+arg_0]
0x14004c9a0  mov     r9d, r13d; dwFlags
0x14004c9a3  mov     [rsp+58h+pcbData], rax; pcbData
0x14004c9a8  mov     r8, rsi; lpValue
0x14004c9ab  mov     [rsp+58h+pvData], r12; pvData
0x14004c9b0  mov     rdx, r15; lpSubKey
0x14004c9b3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14004c9ba  mov     [rsp+58h+pdwType], r14; pdwType
0x14004c9bf  call    cs:__imp_RegGetValueW
0x14004c9c5  mov     ebx, eax
0x14004c9c7  test    eax, eax
0x14004c9c9  jz      short loc_14004C9DF
0x14004c9cb  jle     loc_14004CB9A
0x14004c9d1  movzx   ebx, ax
0x14004c9d4  or      ebx, 80070000h
0x14004c9da  jmp     loc_14004CB9A
0x14004c9df  lea     rdx, [rbp+Block]; struct _CRYPTOAPI_BLOB *
0x14004c9e3  mov     rcx, r12; unsigned __int16 *
0x14004c9e6  call    ?ConvertThumbprintStringToBlob@@YAJPEBGPEAU_CRYPTOAPI_BLOB@@@Z; ConvertThumbprintStringToBlob(ushort const *,_CRYPTOAPI_BLOB *)
0x14004c9eb  test    eax, eax
0x14004c9ed  js      loc_14004CB89
0x14004c9f3  lea     r8, [rbp+pCertContext]
0x14004c9f7  xor     edx, edx
0x14004c9f9  lea     rcx, [rbp+Block]
0x14004c9fd  call    ?GetCertificateContext@@YAJPEAU_CRYPTOAPI_BLOB@@W4EBehaviorOnCertMissing@@PEAPEBU_CERT_CONTEXT@@@Z; GetCertificateContext(_CRYPTOAPI_BLOB *,EBehaviorOnCertMissing,_CERT_CONTEXT const * *)
0x14004ca02  mov     r14, [rbp+pCertContext]
0x14004ca06  test    eax, eax
0x14004ca08  js      loc_14004CB89
0x14004ca0e  test    r14, r14
0x14004ca11  jz      loc_14004CB89
0x14004ca17  lea     rdx, [rbp+arg_8]; int *
0x14004ca1b  mov     rcx, r14; struct _CERT_CONTEXT *
0x14004ca1e  call    ?IsCertExpired@@YAJPEBU_CERT_CONTEXT@@PEAH@Z; IsCertExpired(_CERT_CONTEXT const *,int *)
0x14004ca23  mov     ebx, eax
0x14004ca25  test    eax, eax
0x14004ca27  js      loc_14004CB9A
0x14004ca2d  cmp     [rbp+arg_8], 0
0x14004ca31  mov     rdx, r12
0x14004ca34  jz      loc_14004CB75
0x14004ca3a  lea     rcx, aCwmswebservice_13; "CWmsWebService::s_DoesReplacementCertEx"...
0x14004ca41  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004ca46  mov     rcx, r14; pCertContext
0x14004ca49  call    cs:__imp_CertFreeCertificateContext
0x14004ca4f  lea     rcx, [rbp+Block]; pvFindPara
0x14004ca53  xor     r14d, r14d
0x14004ca56  call    ?DeleteCert@@YAJPEAU_CRYPTOAPI_BLOB@@@Z; DeleteCert(_CRYPTOAPI_BLOB *)
0x14004ca5b  mov     ebx, eax
0x14004ca5d  test    eax, eax
0x14004ca5f  js      loc_14004CB9A
0x14004ca65  lea     rax, [rbp+phkResult]
0x14004ca69  mov     r9d, r13d; samDesired
0x14004ca6c  xor     r8d, r8d; ulOptions
0x14004ca6f  mov     [rsp+58h+pdwType], rax; phkResult
0x14004ca74  mov     rdx, r15; lpSubKey
0x14004ca77  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004ca7e  call    cs:__imp_RegOpenKeyExW
0x14004ca84  mov     ebx, eax
0x14004ca86  test    eax, eax
0x14004ca88  jz      short loc_14004CAF4
0x14004ca8a  jle     short loc_14004CA95
0x14004ca8c  movzx   ebx, ax
0x14004ca8f  or      ebx, 80070000h
0x14004ca95  lea     rax, aLr0l; "lr == 0L"
0x14004ca9c  mov     dword ptr [rsp+58h+pvData], ebx; int
0x14004caa0  lea     r15, aCbraex; "CBRAEx"
0x14004caa7  mov     [rsp+58h+pdwType], rax; unsigned __int16 *
0x14004caac  lea     rsi, aCwmswebservice_31; "CWmsWebService::s_DoesReplacementCertEx"...
0x14004cab3  mov     r9, r15; unsigned __int16 *
0x14004cab6  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004cabd  mov     r8, rsi; unsigned __int16 *
0x14004cac0  mov     rcx, rdi; unsigned __int16 *
0x14004cac3  mov     edx, 7A6h; unsigned int
0x14004cac8  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004cacd  call    cs:__imp_IsDebuggerPresent
0x14004cad3  test    eax, eax
0x14004cad5  lea     rax, aLr0l; "lr == 0L"
0x14004cadc  jz      short loc_14004CAE9
0x14004cade  mov     r9d, 7A6h
0x14004cae4  jmp     loc_14004C8CF
0x14004cae9  mov     r8d, 7A6h
0x14004caef  jmp     loc_14004C7FF
0x14004caf4  mov     rcx, [rbp+phkResult]; hKey
0x14004caf8  mov     rdx, rsi; lpValueName
0x14004cafb  call    cs:__imp_RegDeleteValueW
0x14004cb01  mov     ebx, eax
0x14004cb03  test    eax, eax
0x14004cb05  jz      loc_14004CB98
0x14004cb0b  jle     short loc_14004CB16
0x14004cb0d  movzx   ebx, ax
0x14004cb10  or      ebx, 80070000h
0x14004cb16  lea     rax, aLr0l; "lr == 0L"
0x14004cb1d  mov     dword ptr [rsp+58h+pvData], ebx; int
0x14004cb21  lea     r15, aCbraex; "CBRAEx"
0x14004cb28  mov     [rsp+58h+pdwType], rax; unsigned __int16 *
0x14004cb2d  lea     rsi, aCwmswebservice_31; "CWmsWebService::s_DoesReplacementCertEx"...
0x14004cb34  mov     r9, r15; unsigned __int16 *
0x14004cb37  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004cb3e  mov     r8, rsi; unsigned __int16 *
0x14004cb41  mov     rcx, rdi; unsigned __int16 *
0x14004cb44  mov     edx, 7A9h; unsigned int
0x14004cb49  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004cb4e  call    cs:__imp_IsDebuggerPresent
0x14004cb54  test    eax, eax
0x14004cb56  lea     rax, aLr0l; "lr == 0L"
0x14004cb5d  jz      short loc_14004CB6A
0x14004cb5f  mov     r9d, 7A9h
0x14004cb65  jmp     loc_14004C8CF
0x14004cb6a  mov     r8d, 7A9h
0x14004cb70  jmp     loc_14004C7FF
0x14004cb75  lea     rcx, aCwmswebservice_2; "CWmsWebService::s_DoesReplacementCertEx"...
0x14004cb7c  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004cb81  mov     [rdi], r14
0x14004cb84  xor     r14d, r14d
0x14004cb87  jmp     short loc_14004CB9A
0x14004cb89  lea     rcx, aCwmswebservice_6; "CWmsWebService::s_DoesReplacementCertEx"...
0x14004cb90  mov     rdx, r12
0x14004cb93  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14004cb98  xor     ebx, ebx
0x14004cb9a  mov     rcx, [rbp+phkResult]; hKey
0x14004cb9e  test    rcx, rcx
0x14004cba1  jz      short loc_14004CBB1
0x14004cba3  call    cs:__imp_RegCloseKey
0x14004cba9  mov     [rbp+phkResult], 0
0x14004cbb1  test    r14, r14
0x14004cbb4  jz      short loc_14004CBBF
0x14004cbb6  mov     rcx, r14; pCertContext
0x14004cbb9  call    cs:__imp_CertFreeCertificateContext
0x14004cbbf  mov     rcx, r12; Block
0x14004cbc2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004cbc7  mov     rcx, [rbp+Block+8]; Block
0x14004cbcb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004cbd0  mov     eax, ebx
0x14004cbd2  add     rsp, 58h
0x14004cbd6  pop     r15
0x14004cbd8  pop     r14
0x14004cbda  pop     r13
0x14004cbdc  pop     r12
0x14004cbde  pop     rdi
0x14004cbdf  pop     rsi
0x14004cbe0  pop     rbx
0x14004cbe1  pop     rbp
0x14004cbe2  retn
```
