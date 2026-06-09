# AddSerializedCertificateToStore(uchar const *,ulong)

- ea: `0x1400599e4`
- end: `0x140059cb1`
- name: `?AddSerializedCertificateToStore@@YAJPEBEK@Z`
- size: `717`
- prototype: `__int64 __fastcall(BYTE *pbCertEncoded, DWORD cbCertEncoded)`
- caller_count: `9`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140003f48`
- `0x140026298`
- `0x14002aa70`
- `0x14004bcc8`
- `0x14004dfa0`
- `0x140051b60`
- `0x140055970`
- `0x140058260`
- `0x140058644`

## callees

- `0x1400599e4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140059a26`
- `KERNEL32!GetLastError` at `0x140059afe`
- `KERNEL32!GetLastError` at `0x140059bd6`
- `KERNEL32!GetLastError` at `0x140059a26`
- `KERNEL32!GetLastError` at `0x140059afe`
- `KERNEL32!GetLastError` at `0x140059bd6`
- `KERNEL32!IsDebuggerPresent` at `0x140059a81`
- `KERNEL32!IsDebuggerPresent` at `0x140059b59`
- `KERNEL32!IsDebuggerPresent` at `0x140059c31`
- `KERNEL32!IsDebuggerPresent` at `0x140059a81`
- `KERNEL32!IsDebuggerPresent` at `0x140059b59`
- `KERNEL32!IsDebuggerPresent` at `0x140059c31`
- `CRYPT32!CertCreateCertificateContext` at `0x140059aec`
- `CRYPT32!CertCreateCertificateContext` at `0x140059aec`
- `CRYPT32!CertCloseStore` at `0x140059c98`
- `CRYPT32!CertCloseStore` at `0x140059c98`
- `CRYPT32!CertAddCertificateContextToStore` at `0x140059bc8`
- `CRYPT32!CertAddCertificateContextToStore` at `0x140059bc8`
- `CRYPT32!CertOpenStore` at `0x140059a14`
- `CRYPT32!CertOpenStore` at `0x140059a14`
- `CRYPT32!CertFreeCertificateContext` at `0x140059c8d`
- `CRYPT32!CertFreeCertificateContext` at `0x140059c8d`

## string_xrefs

- `0x1400599f7`: `MultiPoint Services Certificates`
- `0x140059a56`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x140059b2e`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x140059c06`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`

## pseudocode

```c
__int64 __fastcall AddSerializedCertificateToStore(BYTE *pbCertEncoded, DWORD cbCertEncoded)
{
  HCERTSTORE v4; // r15
  signed int v5; // eax
  signed int v6; // ebx
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v8; // r14
  signed int v9; // eax
  signed int LastError; // eax

  v4 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, L"MultiPoint Services Certificates");
  if ( v4 )
  {
    CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded, cbCertEncoded);
    v8 = CertificateContext;
    if ( CertificateContext )
    {
      v6 = 0;
      if ( !CertAddCertificateContextToStore(v4, CertificateContext, 3u, 0) )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
          0x2Bu,
          L"AddSerializedCertificateToStore",
          L"CBRAEx",
          L"fSuccess",
          v6);
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
            43,
            L"AddSerializedCertificateToStore",
            L"CBRAEx",
            L"fSuccess",
            v6);
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
            43,
            L"AddSerializedCertificateToStore",
            L"CBRAEx",
            L"fSuccess",
            v6);
      }
      CertFreeCertificateContext(v8);
    }
    else
    {
      v9 = GetLastError();
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        0x28u,
        L"AddSerializedCertificateToStore",
        L"CBRAEx",
        L"pCertContext != 0",
        v6);
      if ( IsDebuggerPresent() )
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
          40,
          L"AddSerializedCertificateToStore",
          L"CBRAEx",
          L"pCertContext != 0",
          v6);
      else
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
          40,
          L"AddSerializedCertificateToStore",
          L"CBRAEx",
          L"pCertContext != 0",
          v6);
    }
    CertCloseStore(v4, 0);
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x25u,
      L"AddSerializedCertificateToStore",
      L"CBRAEx",
      L"hCertStore != 0",
      v6);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        37,
        L"AddSerializedCertificateToStore",
        L"CBRAEx",
        L"hCertStore != 0",
        v6);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        37,
        L"AddSerializedCertificateToStore",
        L"CBRAEx",
        L"hCertStore != 0",
        v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400599e4  push    rbx
0x1400599e6  push    rbp
0x1400599e7  push    rsi
0x1400599e8  push    rdi
0x1400599e9  push    r12
0x1400599eb  push    r13
0x1400599ed  push    r14
0x1400599ef  push    r15
0x1400599f1  sub     rsp, 48h
0x1400599f5  mov     ebx, edx
0x1400599f7  lea     rax, ?g_kszWmsCertStore@@3QBGB; "MultiPoint Services Certificates"
0x1400599fe  xor     edx, edx; dwEncodingType
0x140059a00  mov     [rsp+88h+pvPara], rax; pvPara
0x140059a05  mov     rdi, rcx
0x140059a08  mov     r9d, 20000h; dwFlags
0x140059a0e  xor     r8d, r8d; hCryptProv
0x140059a11  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x140059a14  call    cs:__imp_CertOpenStore
0x140059a1a  mov     r15, rax
0x140059a1d  test    rax, rax
0x140059a20  jnz     loc_140059AE1
0x140059a26  call    cs:__imp_GetLastError
0x140059a2c  mov     ebx, eax
0x140059a2e  test    eax, eax
0x140059a30  jle     short loc_140059A3B
0x140059a32  movzx   ebx, ax
0x140059a35  or      ebx, 80070000h
0x140059a3b  mov     eax, 80004005h
0x140059a40  lea     rbp, aCbraex; "CBRAEx"
0x140059a47  test    ebx, ebx
0x140059a49  lea     rsi, aAddserializedc_1; "AddSerializedCertificateToStore"
0x140059a50  mov     r14d, 25h ; '%'
0x140059a56  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140059a5d  cmovns  ebx, eax
0x140059a60  lea     r15, aHcertstore0; "hCertStore != 0"
0x140059a67  mov     [rsp+88h+var_60], ebx; int
0x140059a6b  mov     r9, rbp; unsigned __int16 *
0x140059a6e  mov     r8, rsi; unsigned __int16 *
0x140059a71  mov     [rsp+88h+pvPara], r15; unsigned __int16 *
0x140059a76  mov     edx, r14d; unsigned int
0x140059a79  mov     rcx, rdi; unsigned __int16 *
0x140059a7c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140059a81  call    cs:__imp_IsDebuggerPresent
0x140059a87  test    eax, eax
0x140059a89  jz      short loc_140059AB9
0x140059a8b  mov     [rsp+88h+var_50], ebx
0x140059a8f  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140059a96  mov     [rsp+88h+var_58], r15
0x140059a9b  lea     ecx, [r14-23h]; unsigned __int8
0x140059a9f  mov     qword ptr [rsp+88h+var_60], rbp
0x140059aa4  mov     r9d, r14d
0x140059aa7  mov     r8, rdi
0x140059aaa  mov     [rsp+88h+pvPara], rsi
0x140059aaf  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140059ab4  jmp     loc_140059C9E
0x140059ab9  mov     dword ptr [rsp+88h+var_58], ebx
0x140059abd  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140059ac4  mov     qword ptr [rsp+88h+var_60], r15
0x140059ac9  mov     r9, rsi
0x140059acc  mov     r8d, r14d
0x140059acf  mov     [rsp+88h+pvPara], rbp
0x140059ad4  mov     rdx, rdi
0x140059ad7  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140059adc  jmp     loc_140059C9E
0x140059ae1  mov     r8d, ebx; cbCertEncoded
0x140059ae4  mov     rdx, rdi; pbCertEncoded
0x140059ae7  mov     ecx, 10001h; dwCertEncodingType
0x140059aec  call    cs:__imp_CertCreateCertificateContext
0x140059af2  mov     r14, rax
0x140059af5  test    rax, rax
0x140059af8  jnz     loc_140059BB9
0x140059afe  call    cs:__imp_GetLastError
0x140059b04  mov     ebx, eax
0x140059b06  test    eax, eax
0x140059b08  jle     short loc_140059B13
0x140059b0a  movzx   ebx, ax
0x140059b0d  or      ebx, 80070000h
0x140059b13  mov     eax, 80004005h
0x140059b18  lea     rbp, aCbraex; "CBRAEx"
0x140059b1f  test    ebx, ebx
0x140059b21  lea     rsi, aAddserializedc_1; "AddSerializedCertificateToStore"
0x140059b28  mov     r14d, 28h ; '('
0x140059b2e  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140059b35  cmovns  ebx, eax
0x140059b38  lea     r12, aPcertcontext0; "pCertContext != 0"
0x140059b3f  mov     [rsp+88h+var_60], ebx; int
0x140059b43  mov     r9, rbp; unsigned __int16 *
0x140059b46  mov     r8, rsi; unsigned __int16 *
0x140059b49  mov     [rsp+88h+pvPara], r12; unsigned __int16 *
0x140059b4e  mov     edx, r14d; unsigned int
0x140059b51  mov     rcx, rdi; unsigned __int16 *
0x140059b54  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140059b59  call    cs:__imp_IsDebuggerPresent
0x140059b5f  test    eax, eax
0x140059b61  jz      short loc_140059B91
0x140059b63  mov     [rsp+88h+var_50], ebx
0x140059b67  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140059b6e  mov     [rsp+88h+var_58], r12
0x140059b73  lea     ecx, [r14-26h]; unsigned __int8
0x140059b77  mov     qword ptr [rsp+88h+var_60], rbp
0x140059b7c  mov     r9d, r14d
0x140059b7f  mov     r8, rdi
0x140059b82  mov     [rsp+88h+pvPara], rsi
0x140059b87  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140059b8c  jmp     loc_140059C93
0x140059b91  mov     dword ptr [rsp+88h+var_58], ebx
0x140059b95  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140059b9c  mov     qword ptr [rsp+88h+var_60], r12
0x140059ba1  mov     r9, rsi
0x140059ba4  mov     r8d, r14d
0x140059ba7  mov     [rsp+88h+pvPara], rbp
0x140059bac  mov     rdx, rdi
0x140059baf  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140059bb4  jmp     loc_140059C93
0x140059bb9  xor     ebx, ebx
0x140059bbb  xor     r9d, r9d; ppStoreContext
0x140059bbe  mov     rdx, r14; pCertContext
0x140059bc1  mov     rcx, r15; hCertStore
0x140059bc4  lea     r8d, [rbx+3]; dwAddDisposition
0x140059bc8  call    cs:__imp_CertAddCertificateContextToStore
0x140059bce  test    eax, eax
0x140059bd0  jnz     loc_140059C8A
0x140059bd6  call    cs:__imp_GetLastError
0x140059bdc  mov     ebx, eax
0x140059bde  test    eax, eax
0x140059be0  jle     short loc_140059BEB
0x140059be2  movzx   ebx, ax
0x140059be5  or      ebx, 80070000h
0x140059beb  mov     eax, 80004005h
0x140059bf0  lea     rbp, aCbraex; "CBRAEx"
0x140059bf7  test    ebx, ebx
0x140059bf9  lea     rsi, aAddserializedc_1; "AddSerializedCertificateToStore"
0x140059c00  mov     r12d, 2Bh ; '+'
0x140059c06  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140059c0d  cmovns  ebx, eax
0x140059c10  lea     r13, aFsuccess; "fSuccess"
0x140059c17  mov     [rsp+88h+var_60], ebx; int
0x140059c1b  mov     r9, rbp; unsigned __int16 *
0x140059c1e  mov     r8, rsi; unsigned __int16 *
0x140059c21  mov     [rsp+88h+pvPara], r13; unsigned __int16 *
0x140059c26  mov     edx, r12d; unsigned int
0x140059c29  mov     rcx, rdi; unsigned __int16 *
0x140059c2c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140059c31  call    cs:__imp_IsDebuggerPresent
0x140059c37  test    eax, eax
0x140059c39  jz      short loc_140059C67
0x140059c3b  mov     [rsp+88h+var_50], ebx
0x140059c3f  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140059c46  mov     [rsp+88h+var_58], r13
0x140059c4b  lea     ecx, [r12-29h]; unsigned __int8
0x140059c50  mov     qword ptr [rsp+88h+var_60], rbp
0x140059c55  mov     r9d, r12d
0x140059c58  mov     r8, rdi
0x140059c5b  mov     [rsp+88h+pvPara], rsi
0x140059c60  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140059c65  jmp     short loc_140059C8A
0x140059c67  mov     dword ptr [rsp+88h+var_58], ebx
0x140059c6b  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140059c72  mov     qword ptr [rsp+88h+var_60], r13
0x140059c77  mov     r9, rsi
0x140059c7a  mov     r8d, r12d
0x140059c7d  mov     [rsp+88h+pvPara], rbp
0x140059c82  mov     rdx, rdi
0x140059c85  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140059c8a  mov     rcx, r14; pCertContext
0x140059c8d  call    cs:__imp_CertFreeCertificateContext
0x140059c93  xor     edx, edx; dwFlags
0x140059c95  mov     rcx, r15; hCertStore
0x140059c98  call    cs:__imp_CertCloseStore
0x140059c9e  mov     eax, ebx
0x140059ca0  add     rsp, 48h
0x140059ca4  pop     r15
0x140059ca6  pop     r14
0x140059ca8  pop     r13
0x140059caa  pop     r12
0x140059cac  pop     rdi
0x140059cad  pop     rsi
0x140059cae  pop     rbp
0x140059caf  pop     rbx
0x140059cb0  retn
```
