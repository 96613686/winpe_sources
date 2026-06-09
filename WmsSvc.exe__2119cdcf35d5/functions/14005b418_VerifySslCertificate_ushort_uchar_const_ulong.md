# VerifySslCertificate(ushort *,uchar const *,ulong)

- ea: `0x14005b418`
- end: `0x14005b9cc`
- name: `?VerifySslCertificate@@YAJPEAGPEBEK@Z`
- size: `1460`
- prototype: `__int64 __fastcall(wchar_t *String1, const unsigned __int8 *, DWORD)`
- caller_count: `10`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x140003f48`
- `0x140026298`
- `0x14002aa70`
- `0x14004bcc8`
- `0x14004dfa0`
- `0x140050720`
- `0x140051b60`
- `0x140055970`
- `0x140058260`
- `0x140058644`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005a10c`
- `0x14005b418`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005b459`
- `KERNEL32!GetLastError` at `0x14005b5fb`
- `KERNEL32!GetLastError` at `0x14005b73d`
- `KERNEL32!GetLastError` at `0x14005b459`
- `KERNEL32!GetLastError` at `0x14005b5fb`
- `KERNEL32!GetLastError` at `0x14005b73d`
- `KERNEL32!IsDebuggerPresent` at `0x14005b4b4`
- `KERNEL32!IsDebuggerPresent` at `0x14005b579`
- `KERNEL32!IsDebuggerPresent` at `0x14005b652`
- `KERNEL32!IsDebuggerPresent` at `0x14005b6e1`
- `KERNEL32!IsDebuggerPresent` at `0x14005b794`
- `KERNEL32!IsDebuggerPresent` at `0x14005b80a`
- `KERNEL32!IsDebuggerPresent` at `0x14005b8c3`
- `KERNEL32!IsDebuggerPresent` at `0x14005b959`
- `KERNEL32!IsDebuggerPresent` at `0x14005b4b4`
- `KERNEL32!IsDebuggerPresent` at `0x14005b579`
- `KERNEL32!IsDebuggerPresent` at `0x14005b652`
- `KERNEL32!IsDebuggerPresent` at `0x14005b6e1`
- `KERNEL32!IsDebuggerPresent` at `0x14005b794`
- `KERNEL32!IsDebuggerPresent` at `0x14005b80a`
- `KERNEL32!IsDebuggerPresent` at `0x14005b8c3`
- `KERNEL32!IsDebuggerPresent` at `0x14005b959`
- `msvcrt!_strnicmp` at `0x14005b856`
- `msvcrt!_strnicmp` at `0x14005b856`
- `msvcrt!_wcsnicmp` at `0x14005b5bb`
- `msvcrt!_wcsnicmp` at `0x14005b5bb`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14005b5ed`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14005b72f`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14005b5ed`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14005b72f`
- `CRYPT32!CertCreateCertificateContext` at `0x14005b442`
- `CRYPT32!CertCreateCertificateContext` at `0x14005b442`
- `CRYPT32!CertFreeCertificateContext` at `0x14005b9b3`
- `CRYPT32!CertFreeCertificateContext` at `0x14005b9b3`
- `OLEAUT32!__imp_SysFreeString` at `0x14005b99d`
- `OLEAUT32!__imp_SysFreeString` at `0x14005b99d`
- `OLEAUT32!__imp_SysStringLen` at `0x14005b52f`
- `OLEAUT32!__imp_SysStringLen` at `0x14005b52f`

## string_xrefs

- `0x14005b47c`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005b54f`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005b61e`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005b6ba`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005b760`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005b7f2`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005b89b`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005b933`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`

## pseudocode

```c
__int64 __fastcall VerifySslCertificate(wchar_t *String1, const unsigned __int8 *a2, DWORD a3)
{
  const char ***v4; // r13
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v6; // r12
  signed int LastError; // eax
  signed int CertificateSubjectName; // ebx
  unsigned int v9; // r14d
  __int64 v10; // r9
  UINT v11; // eax
  signed int v12; // eax
  struct _CTL_USAGE *v13; // rax
  signed int v14; // eax
  __int64 v15; // r9
  __int64 v16; // r8
  unsigned __int16 *v18; // [rsp+20h] [rbp-78h]
  const unsigned __int16 *v19; // [rsp+28h] [rbp-70h]
  const unsigned __int16 *v20; // [rsp+28h] [rbp-70h]
  const unsigned __int16 *v21; // [rsp+30h] [rbp-68h]
  int v22; // [rsp+30h] [rbp-68h]
  int v23; // [rsp+38h] [rbp-60h]
  wchar_t *String2; // [rsp+40h] [rbp-58h] BYREF
  const CERT_CONTEXT *v25; // [rsp+48h] [rbp-50h]
  DWORD pcbUsage; // [rsp+B8h] [rbp+20h] BYREF

  String2 = 0;
  v4 = 0;
  pcbUsage = 0;
  CertificateContext = CertCreateCertificateContext(0x10001u, a2, a3);
  v25 = CertificateContext;
  v6 = CertificateContext;
  if ( !CertificateContext )
  {
    LastError = GetLastError();
    CertificateSubjectName = LastError;
    if ( LastError > 0 )
      CertificateSubjectName = (unsigned __int16)LastError | 0x80070000;
    v9 = 579;
    if ( CertificateSubjectName >= 0 )
      CertificateSubjectName = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x243u,
      L"VerifySslCertificate",
      L"CBRAEx",
      L"pCertContext != 0",
      CertificateSubjectName);
    if ( IsDebuggerPresent() )
    {
      v23 = CertificateSubjectName;
      v21 = L"pCertContext != 0";
      v19 = L"CBRAEx";
LABEL_8:
      v10 = v9;
LABEL_9:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        v10,
        L"VerifySslCertificate",
        v19,
        v21,
        v23);
      goto LABEL_55;
    }
    v22 = CertificateSubjectName;
    v20 = L"pCertContext != 0";
    v18 = L"CBRAEx";
LABEL_11:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      v9,
      L"VerifySslCertificate",
      v18,
      v20,
      v22);
    goto LABEL_55;
  }
  CertificateSubjectName = GetCertificateSubjectName(CertificateContext, &String2);
  if ( CertificateSubjectName < 0 )
    goto LABEL_55;
  v11 = SysStringLen(String1);
  if ( !v11 )
  {
    v9 = 589;
    CertificateSubjectName = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x24Du,
      L"VerifySslCertificate",
      L"CBRA",
      L"cchRemoteHostName > 0",
      -2147467259);
    if ( IsDebuggerPresent() )
    {
      v23 = -2147467259;
      v21 = L"cchRemoteHostName > 0";
      v19 = L"CBRA";
      goto LABEL_8;
    }
    v22 = -2147467259;
    v20 = L"cchRemoteHostName > 0";
    v18 = L"CBRA";
    goto LABEL_11;
  }
  if ( _wcsnicmp(String1, String2, v11) )
  {
    DEBUGMSG(L"VerifySslCertificate - bstrRemoteHostName == %s, bstrSubjectName == %s\n", String1, String2);
    CertificateSubjectName = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x256u,
      L"VerifySslCertificate",
      L"CHRA",
      L"((HRESULT)0x80004005L)",
      -2147467259);
    if ( IsDebuggerPresent() )
    {
      v15 = 598;
      goto LABEL_48;
    }
    v16 = 598;
LABEL_53:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      v16,
      L"VerifySslCertificate",
      L"CHRA",
      L"((HRESULT)0x80004005L)",
      -2147467259);
    goto LABEL_54;
  }
  DEBUGMSG(L"VerifySslCertificate - bstrRemoteHostName == bstrSubjectName == %s\n", String1);
  if ( !CertGetEnhancedKeyUsage(v6, 2u, 0, &pcbUsage) )
  {
    v12 = GetLastError();
    CertificateSubjectName = v12;
    if ( v12 > 0 )
      CertificateSubjectName = (unsigned __int16)v12 | 0x80070000;
    if ( CertificateSubjectName >= 0 )
      CertificateSubjectName = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x25Eu,
      L"VerifySslCertificate",
      L"CBRAEx",
      L"fSuccess",
      CertificateSubjectName);
    if ( IsDebuggerPresent() )
    {
      v10 = 606;
LABEL_25:
      v23 = CertificateSubjectName;
      v21 = L"fSuccess";
LABEL_26:
      v19 = L"CBRAEx";
      goto LABEL_9;
    }
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      606,
      L"VerifySslCertificate",
      L"CBRAEx",
      L"fSuccess",
      CertificateSubjectName);
    goto LABEL_55;
  }
  v13 = (struct _CTL_USAGE *)operator new(pcbUsage);
  v4 = (const char ***)v13;
  if ( !v13 )
  {
    CertificateSubjectName = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x261u,
      L"VerifySslCertificate",
      L"CPR",
      L"pEku",
      -2147024882);
    if ( IsDebuggerPresent() )
    {
      v23 = -2147024882;
      v10 = 609;
      v21 = L"pEku";
      v19 = L"CPR";
      goto LABEL_9;
    }
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      609,
      L"VerifySslCertificate",
      L"CPR",
      L"pEku",
      -2147024882);
    goto LABEL_55;
  }
  if ( CertGetEnhancedKeyUsage(v6, 2u, v13, &pcbUsage) )
  {
    if ( *(_DWORD *)v4 != 1 )
    {
      CertificateSubjectName = -2147418113;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        0x266u,
        L"VerifySslCertificate",
        L"CBRAEx",
        L"pEku->cUsageIdentifier == 1",
        -2147418113);
      if ( IsDebuggerPresent() )
      {
        v23 = -2147418113;
        v10 = 614;
        v21 = L"pEku->cUsageIdentifier == 1";
        goto LABEL_26;
      }
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        614,
        L"VerifySslCertificate",
        L"CBRAEx",
        L"pEku->cUsageIdentifier == 1",
        -2147418113);
      goto LABEL_55;
    }
    if ( !_strnicmp("1.3.6.1.5.5.7.3.1", *v4[1], 0x12u) )
    {
      DEBUGMSG(L"VerifySslCertificate - Cert is only to be used for Server Authentication - good!\n");
      goto LABEL_55;
    }
    DEBUGMSG(L"VerifySslCertificate - Cert EKU = %S - BAD!\n", *v4[1]);
    CertificateSubjectName = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
      0x270u,
      L"VerifySslCertificate",
      L"CHRA",
      L"((HRESULT)0x80004005L)",
      -2147467259);
    if ( IsDebuggerPresent() )
    {
      v15 = 624;
LABEL_48:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
        v15,
        L"VerifySslCertificate",
        L"CHRA",
        L"((HRESULT)0x80004005L)",
        -2147467259);
LABEL_54:
      v6 = v25;
      goto LABEL_55;
    }
    v16 = 624;
    goto LABEL_53;
  }
  v14 = GetLastError();
  CertificateSubjectName = v14;
  if ( v14 > 0 )
    CertificateSubjectName = (unsigned __int16)v14 | 0x80070000;
  if ( CertificateSubjectName >= 0 )
    CertificateSubjectName = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
    0x264u,
    L"VerifySslCertificate",
    L"CBRAEx",
    L"fSuccess",
    CertificateSubjectName);
  if ( IsDebuggerPresent() )
  {
    v10 = 612;
    goto LABEL_25;
  }
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebserviceutils.cpp",
    612,
    L"VerifySslCertificate",
    L"CBRAEx",
    L"fSuccess",
    CertificateSubjectName);
LABEL_55:
  SysFreeString(String2);
  operator delete(v4);
  if ( v6 )
    CertFreeCertificateContext(v6);
  return (unsigned int)CertificateSubjectName;
}

```

## disassembly

```asm
0x14005b418  mov     rax, rsp
0x14005b41b  push    rbx
0x14005b41c  push    rbp
0x14005b41d  push    rsi
0x14005b41e  push    rdi
0x14005b41f  push    r12
0x14005b421  push    r13
0x14005b423  push    r14
0x14005b425  push    r15
0x14005b427  sub     rsp, 58h
0x14005b42b  mov     rdi, rcx
0x14005b42e  mov     qword ptr [rax-58h], 0
0x14005b436  xor     r13d, r13d
0x14005b439  mov     ecx, 10001h; dwCertEncodingType
0x14005b43e  mov     [rax+20h], r13d
0x14005b442  call    cs:__imp_CertCreateCertificateContext
0x14005b448  mov     [rsp+98h+var_50], rax
0x14005b44d  mov     r12, rax
0x14005b450  test    rax, rax
0x14005b453  jnz     loc_14005B515
0x14005b459  call    cs:__imp_GetLastError
0x14005b45f  mov     ebx, eax
0x14005b461  test    eax, eax
0x14005b463  jle     short loc_14005B46E
0x14005b465  movzx   ebx, ax
0x14005b468  or      ebx, 80070000h
0x14005b46e  mov     ebp, 80004005h
0x14005b473  lea     rsi, aVerifysslcerti; "VerifySslCertificate"
0x14005b47a  test    ebx, ebx
0x14005b47c  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005b483  mov     r14d, 243h
0x14005b489  lea     r15, aPcertcontext0; "pCertContext != 0"
0x14005b490  cmovns  ebx, ebp
0x14005b493  mov     r8, rsi; unsigned __int16 *
0x14005b496  lea     rbp, aCbraex; "CBRAEx"
0x14005b49d  mov     [rsp+98h+var_70], ebx; int
0x14005b4a1  mov     r9, rbp; unsigned __int16 *
0x14005b4a4  mov     [rsp+98h+var_78], r15; unsigned __int16 *
0x14005b4a9  mov     edx, r14d; unsigned int
0x14005b4ac  mov     rcx, rdi; unsigned __int16 *
0x14005b4af  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005b4b4  call    cs:__imp_IsDebuggerPresent
0x14005b4ba  test    eax, eax
0x14005b4bc  jz      short loc_14005B4ED
0x14005b4be  mov     [rsp+98h+var_60], ebx
0x14005b4c2  mov     [rsp+98h+var_68], r15
0x14005b4c7  mov     qword ptr [rsp+98h+var_70], rbp
0x14005b4cc  mov     r9d, r14d
0x14005b4cf  mov     ecx, 2; unsigned __int8
0x14005b4d4  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005b4db  mov     [rsp+98h+var_78], rsi
0x14005b4e0  mov     r8, rdi
0x14005b4e3  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005b4e8  jmp     loc_14005B998
0x14005b4ed  mov     dword ptr [rsp+98h+var_68], ebx
0x14005b4f1  mov     qword ptr [rsp+98h+var_70], r15
0x14005b4f6  mov     [rsp+98h+var_78], rbp
0x14005b4fb  mov     r8d, r14d
0x14005b4fe  mov     r9, rsi
0x14005b501  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14005b508  mov     rdx, rdi
0x14005b50b  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14005b510  jmp     loc_14005B998
0x14005b515  lea     rdx, [rsp+98h+String2]; unsigned __int16 **
0x14005b51a  mov     rcx, r12; pCertContext
0x14005b51d  call    ?GetCertificateSubjectName@@YAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; GetCertificateSubjectName(_CERT_CONTEXT const *,ushort * *)
0x14005b522  mov     ebx, eax
0x14005b524  test    eax, eax
0x14005b526  js      loc_14005B998
0x14005b52c  mov     rcx, rdi; pbstr
0x14005b52f  call    cs:__imp_SysStringLen
0x14005b535  test    eax, eax
0x14005b537  jnz     short loc_14005B5B0
0x14005b539  mov     ebp, 80004005h
0x14005b53e  lea     rsi, aVerifysslcerti; "VerifySslCertificate"
0x14005b545  mov     r14d, 24Dh
0x14005b54b  mov     [rsp+98h+var_70], ebp; int
0x14005b54f  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005b556  mov     r8, rsi; unsigned __int16 *
0x14005b559  lea     r15, aCchremotehostn; "cchRemoteHostName > 0"
0x14005b560  mov     edx, r14d; unsigned int
0x14005b563  mov     rcx, rdi; unsigned __int16 *
0x14005b566  mov     [rsp+98h+var_78], r15; unsigned __int16 *
0x14005b56b  lea     r9, aCbra; "CBRA"
0x14005b572  mov     ebx, ebp
0x14005b574  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005b579  call    cs:__imp_IsDebuggerPresent
0x14005b57f  test    eax, eax
0x14005b581  lea     rax, aCbra; "CBRA"
0x14005b588  jz      short loc_14005B59D
0x14005b58a  mov     [rsp+98h+var_60], ebp
0x14005b58e  mov     [rsp+98h+var_68], r15
0x14005b593  mov     qword ptr [rsp+98h+var_70], rax
0x14005b598  jmp     loc_14005B4CC
0x14005b59d  mov     dword ptr [rsp+98h+var_68], ebp
0x14005b5a1  mov     qword ptr [rsp+98h+var_70], r15
0x14005b5a6  mov     [rsp+98h+var_78], rax
0x14005b5ab  jmp     loc_14005B4FB
0x14005b5b0  mov     rdx, [rsp+98h+String2]; String2
0x14005b5b5  mov     rcx, rdi; String1
0x14005b5b8  mov     r8d, eax; MaxCount
0x14005b5bb  call    cs:__imp__wcsnicmp
0x14005b5c1  mov     rdx, rdi
0x14005b5c4  test    eax, eax
0x14005b5c6  jnz     loc_14005B905
0x14005b5cc  lea     rcx, aVerifysslcerti_3; "VerifySslCertificate - bstrRemoteHostNa"...
0x14005b5d3  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14005b5d8  xor     r8d, r8d; pUsage
0x14005b5db  lea     r9, [rsp+98h+pcbUsage]; pcbUsage
0x14005b5e3  mov     rcx, r12; pCertContext
0x14005b5e6  lea     r14d, [r8+2]
0x14005b5ea  mov     edx, r14d; dwFlags
0x14005b5ed  call    cs:__imp_CertGetEnhancedKeyUsage
0x14005b5f3  test    eax, eax
0x14005b5f5  jnz     loc_14005B691
0x14005b5fb  call    cs:__imp_GetLastError
0x14005b601  mov     ebx, eax
0x14005b603  test    eax, eax
0x14005b605  jle     short loc_14005B610
0x14005b607  movzx   ebx, ax
0x14005b60a  or      ebx, 80070000h
0x14005b610  mov     ebp, 80004005h
0x14005b615  lea     rsi, aVerifysslcerti; "VerifySslCertificate"
0x14005b61c  test    ebx, ebx
0x14005b61e  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005b625  lea     r15, aFsuccess; "fSuccess"
0x14005b62c  mov     r8, rsi; unsigned __int16 *
0x14005b62f  cmovns  ebx, ebp
0x14005b632  mov     edx, 25Eh; unsigned int
0x14005b637  lea     rbp, aCbraex; "CBRAEx"
0x14005b63e  mov     [rsp+98h+var_70], ebx; int
0x14005b642  mov     r9, rbp; unsigned __int16 *
0x14005b645  mov     [rsp+98h+var_78], r15; unsigned __int16 *
0x14005b64a  mov     rcx, rdi; unsigned __int16 *
0x14005b64d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005b652  call    cs:__imp_IsDebuggerPresent
0x14005b658  test    eax, eax
0x14005b65a  jz      short loc_14005B678
0x14005b65c  mov     r9d, 25Eh
0x14005b662  mov     [rsp+98h+var_60], ebx
0x14005b666  mov     [rsp+98h+var_68], r15
0x14005b66b  mov     qword ptr [rsp+98h+var_70], rbp
0x14005b670  mov     ecx, r14d
0x14005b673  jmp     loc_14005B4D4
0x14005b678  mov     dword ptr [rsp+98h+var_68], ebx
0x14005b67c  mov     r8d, 25Eh
0x14005b682  mov     qword ptr [rsp+98h+var_70], r15
0x14005b687  mov     [rsp+98h+var_78], rbp
0x14005b68c  jmp     loc_14005B4FE
0x14005b691  mov     ecx, [rsp+98h+pcbUsage]; Size
0x14005b698  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005b69d  mov     r13, rax
0x14005b6a0  test    rax, rax
0x14005b6a3  jnz     short loc_14005B71E
0x14005b6a5  mov     ebx, 8007000Eh
0x14005b6aa  lea     rsi, aVerifysslcerti; "VerifySslCertificate"
0x14005b6b1  mov     ebp, 261h
0x14005b6b6  mov     [rsp+98h+var_70], ebx; int
0x14005b6ba  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005b6c1  mov     r8, rsi; unsigned __int16 *
0x14005b6c4  lea     r15, aPeku; "pEku"
0x14005b6cb  mov     edx, ebp; unsigned int
0x14005b6cd  mov     rcx, rdi; unsigned __int16 *
0x14005b6d0  mov     [rsp+98h+var_78], r15; unsigned __int16 *
0x14005b6d5  lea     r9, aCpr; "CPR"
0x14005b6dc  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005b6e1  call    cs:__imp_IsDebuggerPresent
0x14005b6e7  test    eax, eax
0x14005b6e9  lea     rax, aCpr; "CPR"
0x14005b6f0  jz      short loc_14005B708
0x14005b6f2  mov     [rsp+98h+var_60], ebx
0x14005b6f6  mov     r9d, ebp
0x14005b6f9  mov     [rsp+98h+var_68], r15
0x14005b6fe  mov     qword ptr [rsp+98h+var_70], rax
0x14005b703  jmp     loc_14005B670
0x14005b708  mov     dword ptr [rsp+98h+var_68], ebx
0x14005b70c  mov     r8d, ebp
0x14005b70f  mov     qword ptr [rsp+98h+var_70], r15
0x14005b714  mov     [rsp+98h+var_78], rax
0x14005b719  jmp     loc_14005B4FE
0x14005b71e  lea     r9, [rsp+98h+pcbUsage]; pcbUsage
0x14005b726  mov     r8, r13; pUsage
0x14005b729  mov     edx, r14d; dwFlags
0x14005b72c  mov     rcx, r12; pCertContext
0x14005b72f  call    cs:__imp_CertGetEnhancedKeyUsage
0x14005b735  test    eax, eax
0x14005b737  jnz     loc_14005B7C2
0x14005b73d  call    cs:__imp_GetLastError
0x14005b743  mov     ebx, eax
0x14005b745  test    eax, eax
0x14005b747  jle     short loc_14005B752
0x14005b749  movzx   ebx, ax
0x14005b74c  or      ebx, 80070000h
0x14005b752  mov     ebp, 80004005h
0x14005b757  lea     rsi, aVerifysslcerti; "VerifySslCertificate"
0x14005b75e  test    ebx, ebx
0x14005b760  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005b767  lea     r15, aFsuccess; "fSuccess"
0x14005b76e  mov     r8, rsi; unsigned __int16 *
0x14005b771  cmovns  ebx, ebp
0x14005b774  mov     edx, 264h; unsigned int
0x14005b779  lea     rbp, aCbraex; "CBRAEx"
0x14005b780  mov     [rsp+98h+var_70], ebx; int
0x14005b784  mov     r9, rbp; unsigned __int16 *
0x14005b787  mov     [rsp+98h+var_78], r15; unsigned __int16 *
0x14005b78c  mov     rcx, rdi; unsigned __int16 *
0x14005b78f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005b794  call    cs:__imp_IsDebuggerPresent
0x14005b79a  test    eax, eax
0x14005b79c  jz      short loc_14005B7A9
0x14005b79e  mov     r9d, 264h
0x14005b7a4  jmp     loc_14005B662
0x14005b7a9  mov     dword ptr [rsp+98h+var_68], ebx
0x14005b7ad  mov     r8d, 264h
0x14005b7b3  mov     qword ptr [rsp+98h+var_70], r15
0x14005b7b8  mov     [rsp+98h+var_78], rbp
0x14005b7bd  jmp     loc_14005B4FE
0x14005b7c2  cmp     dword ptr [r13+0], 1
0x14005b7c7  jz      short loc_14005B842
0x14005b7c9  lea     rax, aPekuCusageiden; "pEku->cUsageIdentifier == 1"
0x14005b7d0  mov     ebx, 8000FFFFh
0x14005b7d5  lea     rbp, aCbraex; "CBRAEx"
0x14005b7dc  mov     [rsp+98h+var_70], ebx; int
0x14005b7e0  lea     rsi, aVerifysslcerti; "VerifySslCertificate"
0x14005b7e7  mov     [rsp+98h+var_78], rax; unsigned __int16 *
0x14005b7ec  mov     r15d, 266h
0x14005b7f2  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005b7f9  mov     r9, rbp; unsigned __int16 *
0x14005b7fc  mov     r8, rsi; unsigned __int16 *
0x14005b7ff  mov     edx, r15d; unsigned int
0x14005b802  mov     rcx, rdi; unsigned __int16 *
0x14005b805  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005b80a  call    cs:__imp_IsDebuggerPresent
0x14005b810  test    eax, eax
0x14005b812  lea     rax, aPekuCusageiden; "pEku->cUsageIdentifier == 1"
0x14005b819  jz      short loc_14005B82C
0x14005b81b  mov     [rsp+98h+var_60], ebx
0x14005b81f  mov     r9d, r15d
0x14005b822  mov     [rsp+98h+var_68], rax
0x14005b827  jmp     loc_14005B66B
0x14005b82c  mov     dword ptr [rsp+98h+var_68], ebx
0x14005b830  mov     r8d, r15d
0x14005b833  mov     qword ptr [rsp+98h+var_70], rax
0x14005b838  mov     [rsp+98h+var_78], rbp
0x14005b83d  jmp     loc_14005B4FE
0x14005b842  mov     rdx, [r13+8]
0x14005b846  lea     rcx, a136155731; "1.3.6.1.5.5.7.3.1"
0x14005b84d  mov     r8d, 12h; MaxCount
0x14005b853  mov     rdx, [rdx]; String2
0x14005b856  call    cs:__imp__strnicmp
0x14005b85c  test    eax, eax
0x14005b85e  jnz     short loc_14005B871
0x14005b860  lea     rcx, aVerifysslcerti_2; "VerifySslCertificate - Cert is only to "...
0x14005b867  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14005b86c  jmp     loc_14005B998
0x14005b871  mov     rdx, [r13+8]
0x14005b875  lea     rcx, aVerifysslcerti_1; "VerifySslCertificate - Cert EKU = %S - "...
0x14005b87c  mov     rdx, [rdx]
0x14005b87f  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14005b884  mov     ebp, 80004005h
0x14005b889  lea     r12, aChra; "CHRA"
0x14005b890  lea     rsi, aVerifysslcerti; "VerifySslCertificate"
0x14005b897  mov     [rsp+98h+var_70], ebp; int
0x14005b89b  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005b8a2  mov     r9, r12; unsigned __int16 *
0x14005b8a5  lea     r15, aHresult0x80004; "((HRESULT)0x80004005L)"
0x14005b8ac  mov     r8, rsi; unsigned __int16 *
0x14005b8af  mov     rcx, rdi; unsigned __int16 *
0x14005b8b2  mov     [rsp+98h+var_78], r15; unsigned __int16 *
0x14005b8b7  mov     edx, 270h; unsigned int
0x14005b8bc  mov     ebx, ebp
0x14005b8be  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14005b8c3  call    cs:__imp_IsDebuggerPresent
0x14005b8c9  test    eax, eax
0x14005b8cb  jz      short loc_14005B8FD
0x14005b8cd  mov     r9d, 270h
0x14005b8d3  mov     ecx, r14d; unsigned __int8
0x14005b8d6  mov     [rsp+98h+var_60], ebp
0x14005b8da  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14005b8e1  mov     [rsp+98h+var_68], r15
0x14005b8e6  mov     r8, rdi
0x14005b8e9  mov     qword ptr [rsp+98h+var_70], r12
0x14005b8ee  mov     [rsp+98h+var_78], rsi
0x14005b8f3  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14005b8f8  jmp     loc_14005B993
0x14005b8fd  mov     r8d, 270h
0x14005b903  jmp     short loc_14005B973
0x14005b905  mov     r8, [rsp+98h+String2]
0x14005b90a  lea     rcx, aVerifysslcerti_0; "VerifySslCertificate - bstrRemoteHostNa"...
0x14005b911  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14005b916  mov     ebp, 80004005h
0x14005b91b  lea     r12, aChra; "CHRA"
0x14005b922  lea     rsi, aVerifysslcerti; "VerifySslCertificate"
0x14005b929  mov     [rsp+98h+var_70], ebp; int
0x14005b92d  mov     r14d, 256h
0x14005b933  lea     rdi, aTermsrvWmsSrcD_15; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14005b93a  lea     r15, aHresult0x80004; "((HRESULT)0x80004005L)"
0x14005b941  mov     r9, r12; unsigned __int16 *
0x14005b944  mov     r8, rsi; unsigned __int16 *
0x14005b947  mov     [rsp+98h+var_78], r15; unsigned __int16 *
  ... truncated ...
```
