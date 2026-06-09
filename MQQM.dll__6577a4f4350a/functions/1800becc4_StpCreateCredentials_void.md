# StpCreateCredentials(void)

- ea: `0x1800becc4`
- end: `0x1800bef83`
- name: `?StpCreateCredentials@@YAXXZ`
- size: `703`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002cd84`

## callees

- `0x180004d91`
- `0x18000f35c`
- `0x18000f7e4`
- `0x1800bec44`
- `0x1800bec68`
- `0x1800becc4`
- `0x1800befe8`
- `0x1800d6e56`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800bed33`
- `KERNEL32!GetLastError` at `0x1800bed55`
- `KERNEL32!GetLastError` at `0x1800bedf4`
- `KERNEL32!GetLastError` at `0x1800bed33`
- `KERNEL32!GetLastError` at `0x1800bed55`
- `KERNEL32!GetLastError` at `0x1800bedf4`
- `Secur32!AcquireCredentialsHandleW` at `0x1800bee71`
- `Secur32!AcquireCredentialsHandleW` at `0x1800beee5`
- `Secur32!AcquireCredentialsHandleW` at `0x1800bee71`
- `Secur32!AcquireCredentialsHandleW` at `0x1800beee5`
- `CRYPT32!CertFindCertificateInStore` at `0x1800bedc6`
- `CRYPT32!CertFindCertificateInStore` at `0x1800bedc6`
- `CRYPT32!CertOpenStore` at `0x1800bed01`
- `CRYPT32!CertOpenStore` at `0x1800bed01`

## string_xrefs

- `0x1800bee68`: `Microsoft Unified Security Protocol Provider`
- `0x1800beedc`: `Microsoft Unified Security Protocol Provider`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void StpCreateCredentials(void)
{
  HCERTSTORE v0; // rbx
  DWORD LastError; // eax
  signed int v2; // eax
  DWORD v3; // eax
  unsigned int v4; // eax
  CSSPICredential *v5; // rcx
  unsigned int v6; // eax
  int v7; // edi
  SECURITY_INTEGER ptsExpiry; // [rsp+50h] [rbp-B0h] BYREF
  PCCERT_CONTEXT CertificateInStore; // [rsp+58h] [rbp-A8h] BYREF
  HCERTSTORE v10; // [rsp+60h] [rbp-A0h] BYREF
  int v11; // [rsp+68h] [rbp-98h]
  _QWORD pExceptionObject[4]; // [rsp+70h] [rbp-90h] BYREF
  int pAuthData; // [rsp+90h] [rbp-70h] BYREF
  int v14; // [rsp+94h] [rbp-6Ch]
  PCCERT_CONTEXT *p_CertificateInStore; // [rsp+98h] [rbp-68h]
  int v16; // [rsp+C8h] [rbp-38h]
  int v17; // [rsp+D8h] [rbp-28h]
  struct _SecHandle phCredential; // [rsp+E0h] [rbp-20h] BYREF

  v0 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x54000u, L"MSMQ\\MY");
  v10 = v0;
  v11 = 0;
  if ( !v0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_3e2c877ae73c3dd247d52809e2504ea0_Traceguids, LastError);
    }
    v2 = GetLastError();
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v2);
    pExceptionObject[0] = &bad_socket_error::`vftable';
    throw (socket_transport_exception *)pExceptionObject;
  }
  memset_0(&pAuthData, 0, 0x50u);
  pAuthData = 4;
  v16 = 0;
  v17 = 24;
  CertificateInStore = CertFindCertificateInStore(v0, 0, 0, 0, 0, 0);
  if ( CertificateInStore )
  {
    v14 = 1;
    p_CertificateInStore = &CertificateInStore;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      v3 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, WPP_3e2c877ae73c3dd247d52809e2504ea0_Traceguids, v3);
    }
    v14 = 0;
    p_CertificateInStore = 0;
  }
  phCredential = 0;
  ptsExpiry.QuadPart = 0;
  v4 = AcquireCredentialsHandleW(
         0,
         (LPWSTR)L"Microsoft Unified Security Protocol Provider",
         2u,
         0,
         &pAuthData,
         0,
         0,
         &phCredential,
         &ptsExpiry);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_3e2c877ae73c3dd247d52809e2504ea0_Traceguids, v4);
    v14 = 0;
    p_CertificateInStore = 0;
    v6 = AcquireCredentialsHandleW(
           0,
           (LPWSTR)L"Microsoft Unified Security Protocol Provider",
           2u,
           0,
           &pAuthData,
           0,
           0,
           &phCredential,
           &ptsExpiry);
    v7 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 13, WPP_3e2c877ae73c3dd247d52809e2504ea0_Traceguids, v6);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v7);
      pExceptionObject[0] = &bad_socket_error::`vftable';
      throw (socket_transport_exception *)pExceptionObject;
    }
  }
  CSSPICredential::free(v5);
  ::phCredential = phCredential;
  CCertificateContext::~CCertificateContext((CCertificateContext *)&CertificateInStore);
  CCertOpenStore::~CCertOpenStore((CCertOpenStore *)&v10);
}

```

## disassembly

```asm
0x1800becc4  push    rbp
0x1800becc6  push    rbx
0x1800becc7  push    rsi
0x1800becc8  push    rdi
0x1800becc9  lea     rbp, [rsp-8]
0x1800becce  sub     rsp, 108h
0x1800becd5  mov     rax, cs:__security_cookie
0x1800becdc  xor     rax, rsp
0x1800becdf  mov     [rbp+20h+var_30], rax
0x1800bece3  lea     rax, aMsmqMy; "MSMQ\\MY"
0x1800becea  mov     [rsp+120h+pvPara], rax; pvPara
0x1800becef  mov     r9d, 54000h; dwFlags
0x1800becf5  xor     r8d, r8d; hCryptProv
0x1800becf8  lea     edx, [r8+1]; dwEncodingType
0x1800becfc  lea     edi, [rdx+9]
0x1800becff  mov     ecx, edi; lpszStoreProvider
0x1800bed01  call    cs:__imp_CertOpenStore
0x1800bed07  mov     rbx, rax
0x1800bed0a  mov     [rsp+120h+var_C0], rax
0x1800bed0f  xor     esi, esi
0x1800bed11  mov     [rsp+120h+var_B8], esi
0x1800bed15  test    rax, rax
0x1800bed18  jnz     short loc_1800BED91
0x1800bed1a  lea     rbx, WPP_GLOBAL_Control
0x1800bed21  mov     rax, cs:WPP_GLOBAL_Control
0x1800bed28  cmp     rax, rbx
0x1800bed2b  jz      short loc_1800BED55
0x1800bed2d  test    byte ptr [rax+6Ch], 1
0x1800bed31  jz      short loc_1800BED55
0x1800bed33  call    cs:__imp_GetLastError
0x1800bed39  mov     edx, edi
0x1800bed3b  mov     r9d, eax
0x1800bed3e  lea     r8, WPP_3e2c877ae73c3dd247d52809e2504ea0_Traceguids
0x1800bed45  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bed4c  mov     rcx, [rcx+60h]
0x1800bed50  call    WPP_SF_d
0x1800bed55  call    cs:__imp_GetLastError
0x1800bed5b  test    eax, eax
0x1800bed5d  jle     short loc_1800BED67
0x1800bed5f  movzx   eax, ax
0x1800bed62  or      eax, 80070000h
0x1800bed67  mov     edx, eax; unsigned int
0x1800bed69  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800bed6e  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800bed73  lea     rax, ??_7bad_socket_error@@6B@; const bad_socket_error::`vftable'
0x1800bed7a  mov     [rsp+120h+pExceptionObject], rax
0x1800bed7f  lea     rdx, _TI4?AVsocket_transport_exception@@; pThrowInfo
0x1800bed86  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800bed8b  call    _CxxThrowException_0
0x1800bed91  xor     edx, edx; Val
0x1800bed93  lea     r8d, [rdx+50h]; Size
0x1800bed97  lea     rcx, [rbp+20h+pAuthData]; void *
0x1800bed9b  call    memset_0
0x1800beda0  mov     [rbp+20h+pAuthData], 4
0x1800beda7  mov     [rbp+20h+var_58], esi
0x1800bedaa  mov     [rbp+20h+var_48], 18h
0x1800bedb1  mov     [rsp+120h+pPrevCertContext], rsi; pPrevCertContext
0x1800bedb6  mov     [rsp+120h+pvPara], rsi; pvFindPara
0x1800bedbb  xor     r9d, r9d; dwFindType
0x1800bedbe  xor     r8d, r8d; dwFindFlags
0x1800bedc1  xor     edx, edx; dwCertEncodingType
0x1800bedc3  mov     rcx, rbx; hCertStore
0x1800bedc6  call    cs:__imp_CertFindCertificateInStore
0x1800bedcc  mov     [rsp+120h+var_C8], rax
0x1800bedd1  lea     rbx, WPP_GLOBAL_Control
0x1800bedd8  mov     edi, 2
0x1800beddd  test    rax, rax
0x1800bede0  jnz     short loc_1800BEE20
0x1800bede2  mov     rax, cs:WPP_GLOBAL_Control
0x1800bede9  cmp     rax, rbx
0x1800bedec  jz      short loc_1800BEE17
0x1800bedee  test    [rax+6Ch], dil
0x1800bedf2  jz      short loc_1800BEE17
0x1800bedf4  call    cs:__imp_GetLastError
0x1800bedfa  lea     edx, [rdi+9]
0x1800bedfd  mov     r9d, eax
0x1800bee00  lea     r8, WPP_3e2c877ae73c3dd247d52809e2504ea0_Traceguids
0x1800bee07  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bee0e  mov     rcx, [rcx+60h]
0x1800bee12  call    WPP_SF_d
0x1800bee17  mov     [rbp+20h+var_8C], esi
0x1800bee1a  mov     [rbp+20h+var_88], rsi
0x1800bee1e  jmp     short loc_1800BEE30
0x1800bee20  mov     [rbp+20h+var_8C], 1
0x1800bee27  lea     rax, [rsp+120h+var_C8]
0x1800bee2c  mov     [rbp+20h+var_88], rax
0x1800bee30  xorps   xmm0, xmm0
0x1800bee33  movups  xmmword ptr [rbp+20h+var_40.dwLower], xmm0
0x1800bee37  mov     qword ptr [rsp+120h+var_D0], rsi
0x1800bee3c  lea     rax, [rsp+120h+var_D0]
0x1800bee41  mov     [rsp+120h+ptsExpiry], rax; ptsExpiry
0x1800bee46  lea     rax, [rbp+20h+var_40]
0x1800bee4a  mov     [rsp+120h+phCredential], rax; phCredential
0x1800bee4f  mov     [rsp+120h+pvGetKeyArgument], rsi; pvGetKeyArgument
0x1800bee54  mov     [rsp+120h+pPrevCertContext], rsi; pGetKeyFn
0x1800bee59  lea     rax, [rbp+20h+pAuthData]
0x1800bee5d  mov     [rsp+120h+pvPara], rax; pAuthData
0x1800bee62  xor     r9d, r9d; pvLogonId
0x1800bee65  mov     r8d, edi; fCredentialUse
0x1800bee68  lea     rdx, pszPackage; "Microsoft Unified Security Protocol Pro"...
0x1800bee6f  xor     ecx, ecx; pszPrincipal
0x1800bee71  call    cs:__imp_AcquireCredentialsHandleW
0x1800bee77  test    eax, eax
0x1800bee79  jz      loc_1800BEF45
0x1800bee7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bee86  cmp     rcx, rbx
0x1800bee89  jz      short loc_1800BEEA9
0x1800bee8b  test    byte ptr [rcx+6Ch], 1
0x1800bee8f  jz      short loc_1800BEEA9
0x1800bee91  mov     edx, 0Ch
0x1800bee96  mov     r9d, eax
0x1800bee99  lea     r8, WPP_3e2c877ae73c3dd247d52809e2504ea0_Traceguids
0x1800beea0  mov     rcx, [rcx+60h]
0x1800beea4  call    WPP_SF_d
0x1800beea9  mov     [rbp+20h+var_8C], esi
0x1800beeac  mov     [rbp+20h+var_88], rsi
0x1800beeb0  lea     rax, [rsp+120h+var_D0]
0x1800beeb5  mov     [rsp+120h+ptsExpiry], rax; ptsExpiry
0x1800beeba  lea     rax, [rbp+20h+var_40]
0x1800beebe  mov     [rsp+120h+phCredential], rax; phCredential
0x1800beec3  mov     [rsp+120h+pvGetKeyArgument], rsi; pvGetKeyArgument
0x1800beec8  mov     [rsp+120h+pPrevCertContext], rsi; pGetKeyFn
0x1800beecd  lea     rax, [rbp+20h+pAuthData]
0x1800beed1  mov     [rsp+120h+pvPara], rax; pAuthData
0x1800beed6  xor     r9d, r9d; pvLogonId
0x1800beed9  mov     r8d, edi; fCredentialUse
0x1800beedc  lea     rdx, pszPackage; "Microsoft Unified Security Protocol Pro"...
0x1800beee3  xor     ecx, ecx; pszPrincipal
0x1800beee5  call    cs:__imp_AcquireCredentialsHandleW
0x1800beeeb  mov     edi, eax
0x1800beeed  test    eax, eax
0x1800beeef  jz      short loc_1800BEF45
0x1800beef1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800beef8  cmp     rcx, rbx
0x1800beefb  jz      short loc_1800BEF1B
0x1800beefd  test    byte ptr [rcx+6Ch], 1
0x1800bef01  jz      short loc_1800BEF1B
0x1800bef03  mov     edx, 0Dh
0x1800bef08  mov     r9d, eax
0x1800bef0b  lea     r8, WPP_3e2c877ae73c3dd247d52809e2504ea0_Traceguids
0x1800bef12  mov     rcx, [rcx+60h]
0x1800bef16  call    WPP_SF_d
0x1800bef1b  mov     edx, edi; unsigned int
0x1800bef1d  lea     rcx, [rsp+120h+pExceptionObject]; this
0x1800bef22  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800bef27  lea     rax, ??_7bad_socket_error@@6B@; const bad_socket_error::`vftable'
0x1800bef2e  mov     [rsp+120h+pExceptionObject], rax
0x1800bef33  lea     rdx, _TI4?AVsocket_transport_exception@@; pThrowInfo
0x1800bef3a  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800bef3f  call    _CxxThrowException_0
0x1800bef45  call    ?free@CSSPICredential@@QEAAXXZ; CSSPICredential::free(void)
0x1800bef4a  movups  xmm0, xmmword ptr [rbp+20h+var_40.dwLower]
0x1800bef4e  movdqu  xmmword ptr cs:phCredential.dwLower, xmm0
0x1800bef56  lea     rcx, [rsp+120h+var_C8]; this
0x1800bef5b  call    ??1CCertificateContext@@QEAA@XZ; CCertificateContext::~CCertificateContext(void)
0x1800bef60  nop
0x1800bef61  lea     rcx, [rsp+120h+var_C0]; this
0x1800bef66  call    ??1CCertOpenStore@@QEAA@XZ; CCertOpenStore::~CCertOpenStore(void)
0x1800bef6b  mov     rcx, [rbp+20h+var_30]
0x1800bef6f  xor     rcx, rsp; StackCookie
0x1800bef72  call    __security_check_cookie
0x1800bef77  add     rsp, 108h
0x1800bef7e  pop     rdi
0x1800bef7f  pop     rsi
0x1800bef80  pop     rbx
0x1800bef81  pop     rbp
0x1800bef82  retn
```
