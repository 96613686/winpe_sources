# CertGetCertificateChainHelper(_CERT_CONTEXT const *,void *,bool,bool,_FILETIME *,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x180057a04`
- end: `0x180057d57`
- name: `?CertGetCertificateChainHelper@@YAJPEBU_CERT_CONTEXT@@PEAX_N2PEAU_FILETIME@@PEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `851`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, void *, __int64, __int64, struct _FILETIME *pTime, const struct _CERT_CHAIN_CONTEXT **ppChainContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005749c`

## callees

- `0x1800110fc`
- `0x18004ef48`
- `0x180057a04`
- `0x180057d60`
- `0x180061960`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057c55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057c6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057b2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057c55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057c6e`
- `CRYPT32!CertGetCertificateChain` at `0x180057b07`
- `CRYPT32!CertGetCertificateChain` at `0x180057c4b`
- `CRYPT32!CertGetCertificateChain` at `0x180057b07`
- `CRYPT32!CertGetCertificateChain` at `0x180057c4b`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180057bf3`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180057d27`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180057bf3`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x180057d27`
- `CRYPT32!CertCloseStore` at `0x180057b9e`
- `CRYPT32!CertCloseStore` at `0x180057d14`
- `CRYPT32!CertCloseStore` at `0x180057b9e`
- `CRYPT32!CertCloseStore` at `0x180057d14`
- `CRYPT32!CertFreeCertificateChain` at `0x180057bc4`
- `CRYPT32!CertFreeCertificateChain` at `0x180057c19`
- `CRYPT32!CertFreeCertificateChain` at `0x180057c8e`
- `CRYPT32!CertFreeCertificateChain` at `0x180057ce6`
- `CRYPT32!CertFreeCertificateChain` at `0x180057d02`
- `CRYPT32!CertFreeCertificateChain` at `0x180057bc4`
- `CRYPT32!CertFreeCertificateChain` at `0x180057c19`
- `CRYPT32!CertFreeCertificateChain` at `0x180057c8e`
- `CRYPT32!CertFreeCertificateChain` at `0x180057ce6`
- `CRYPT32!CertFreeCertificateChain` at `0x180057d02`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x180057c06`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x180057c06`

## string_xrefs

- `0x180057aab`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate`
- `0x180057aa4`: `DisableWindowsUpdateOnlineRevocation`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CertGetCertificateChainHelper(
        PCCERT_CONTEXT pCertContext,
        void *a2,
        __int64 a3,
        __int64 a4,
        struct _FILETIME *pTime,
        const struct _CERT_CHAIN_CONTEXT **ppChainContext)
{
  signed int SubCAStore; // ebx
  DWORD dwFlags; // esi
  HKEY v9; // rcx
  signed int LastError; // eax
  signed int v11; // ecx
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // ecx
  signed int v15; // eax
  const CERT_CHAIN_CONTEXT *v16; // rcx
  PCCERT_CHAIN_CONTEXT v17; // rax
  const struct _CERT_CHAIN_CONTEXT *v18; // rax
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  const char *v22; // [rsp+50h] [rbp-B0h]
  _BYTE pConfig[88]; // [rsp+60h] [rbp-A0h] BYREF
  struct _CERT_CHAIN_PARA pChainPara[3]; // [rsp+C0h] [rbp-40h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext[2]; // [rsp+120h] [rbp+20h] BYREF
  HCERTSTORE hCertStore[2]; // [rsp+130h] [rbp+30h] BYREF
  HCERTCHAINENGINE hChainEngine[2]; // [rsp+140h] [rbp+40h] BYREF

  SubCAStore = 0;
  hChainEngine[0] = 0;
  hChainEngine[1] = 0;
  *(_OWORD *)hCertStore = 0u;
  memset(pChainPara, 0, sizeof(pChainPara));
  pChainPara[0].cbSize = 96;
  v21[0] = 16;
  v21[1] = 2;
  v22 = "1.3.6.1.4.1.311.72.1.1";
  *(_QWORD *)&pChainPara[2].RequestedUsage.Usage.cUsageIdentifier = v21;
  dwFlags = 0x40000000;
  v20 = 0;
  ReadDwordPolicyAsBool(
    v9,
    L"SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate",
    L"DisableWindowsUpdateOnlineRevocation",
    &v20);
  if ( v20 )
  {
    dwFlags = 0;
    WUTrace(0, 0, 32, 4);
  }
  if ( !CertGetCertificateChain(0, pCertContext, pTime, 0, pChainPara, dwFlags, 0, ppChainContext) )
  {
    LastError = GetLastError();
    v11 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v11 = LastError;
    if ( v11 >= 0 )
    {
      SubCAStore = -2147467259;
    }
    else
    {
      v12 = GetLastError();
      SubCAStore = (unsigned __int16)v12 | 0x80070000;
      if ( v12 <= 0 )
        SubCAStore = v12;
    }
    goto LABEL_32;
  }
  if ( ((*ppChainContext)->TrustStatus.dwErrorStatus & 4) == 0 )
    goto LABEL_38;
  memset(pConfig, 0, sizeof(pConfig));
  pChainContext[0] = 0;
  pChainContext[1] = 0;
  WUTrace(0, 0, 32, 4);
  if ( hCertStore[1] )
  {
    CertCloseStore(hCertStore[1], 0);
    hCertStore[1] = 0;
  }
  SubCAStore = CreateSubCAStore(&hCertStore[1]);
  if ( SubCAStore < 0 )
  {
    if ( pChainContext[1] )
      CertFreeCertificateChain(pChainContext[1]);
LABEL_33:
    WUTrace(0, 0, 32, 1);
    goto LABEL_38;
  }
  *(_DWORD *)pConfig = 88;
  *(_DWORD *)&pConfig[48] = 0x2000;
  *(HCERTSTORE *)&pConfig[64] = hCertStore[1];
  *(_DWORD *)&pConfig[80] |= 1u;
  if ( hChainEngine[1] )
  {
    CertFreeCertificateChainEngine(hChainEngine[1]);
    hChainEngine[1] = 0;
  }
  if ( !CertCreateCertificateChainEngine((PCERT_CHAIN_ENGINE_CONFIG)pConfig, &hChainEngine[1]) )
    goto LABEL_23;
  if ( pChainContext[1] )
  {
    CertFreeCertificateChain(pChainContext[1]);
    pChainContext[1] = 0;
  }
  if ( !CertGetCertificateChain(hChainEngine[1], pCertContext, pTime, 0, pChainPara, dwFlags, 0, &pChainContext[1]) )
  {
LABEL_23:
    v13 = GetLastError();
    v14 = (unsigned __int16)v13 | 0x80070000;
    if ( v13 <= 0 )
      v14 = v13;
    if ( v14 >= 0 )
    {
      SubCAStore = -2147467259;
    }
    else
    {
      v15 = GetLastError();
      SubCAStore = (unsigned __int16)v15 | 0x80070000;
      if ( v15 <= 0 )
        SubCAStore = v15;
    }
    if ( pChainContext[1] )
      CertFreeCertificateChain(pChainContext[1]);
LABEL_32:
    if ( SubCAStore >= 0 )
      goto LABEL_38;
    goto LABEL_33;
  }
  v16 = pChainContext[1];
  v17 = pChainContext[1];
  if ( (pChainContext[1]->TrustStatus.dwInfoStatus & 0x2000) != 0 )
  {
    CertFreeCertificateChain(*ppChainContext);
    v18 = pChainContext[1];
    v16 = 0;
    pChainContext[1] = 0;
    *ppChainContext = v18;
    v17 = 0;
  }
  if ( v17 )
    CertFreeCertificateChain(v16);
LABEL_38:
  if ( hCertStore[1] )
  {
    CertCloseStore(hCertStore[1], 0);
    hCertStore[1] = 0;
  }
  if ( hChainEngine[1] )
    CertFreeCertificateChainEngine(hChainEngine[1]);
  return (unsigned int)SubCAStore;
}

```

## disassembly

```asm
0x180057a04  mov     [rsp-8+arg_8], rbx
0x180057a09  mov     [rsp-8+arg_10], rsi
0x180057a0e  push    rbp
0x180057a0f  push    rdi
0x180057a10  push    r12
0x180057a12  push    r14
0x180057a14  push    r15
0x180057a16  lea     rbp, [rsp-60h]
0x180057a1b  sub     rsp, 160h
0x180057a22  mov     rax, cs:__security_cookie
0x180057a29  xor     rax, rsp
0x180057a2c  mov     [rbp+80h+var_30], rax
0x180057a30  mov     r14, rcx
0x180057a33  mov     r15, [rbp+80h+pTime]
0x180057a3a  mov     rdi, [rbp+80h+arg_28]
0x180057a41  xor     r12d, r12d
0x180057a44  mov     ebx, r12d
0x180057a47  xorps   xmm0, xmm0
0x180057a4a  movups  xmmword ptr [rbp+80h+hChainEngine], xmm0
0x180057a4e  mov     [rbp+80h+hChainEngine+8], r12
0x180057a52  movups  xmmword ptr [rbp+80h+hCertStore], xmm0
0x180057a56  mov     [rbp+80h+hCertStore+8], r12
0x180057a5a  lea     esi, [r12+60h]
0x180057a5f  mov     r8d, esi; Size
0x180057a62  xor     edx, edx; Val
0x180057a64  lea     rcx, [rbp+80h+var_C0]; void *
0x180057a68  call    memset
0x180057a6d  mov     [rbp+80h+var_C0.cbSize], esi
0x180057a70  mov     [rsp+180h+var_138], 10h
0x180057a78  mov     [rsp+180h+var_134], 2
0x180057a80  lea     rax, a1361413117211; "1.3.6.1.4.1.311.72.1.1"
0x180057a87  mov     [rsp+180h+var_130], rax
0x180057a8c  lea     rax, [rsp+180h+var_138]
0x180057a91  mov     [rbp+80h+var_70], rax
0x180057a95  mov     esi, 40000000h
0x180057a9a  mov     [rsp+180h+var_140], r12d
0x180057a9f  lea     r9, [rsp+180h+var_140]; int *
0x180057aa4  lea     r8, aDisablewindows; "DisableWindowsUpdateOnlineRevocation"
0x180057aab  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180057ab2  call    ?ReadDwordPolicyAsBool@@YAJPEAUHKEY__@@PEB_W1PEAH@Z; ReadDwordPolicyAsBool(HKEY__ *,wchar_t const *,wchar_t const *,int *)
0x180057ab7  cmp     [rsp+180h+var_140], r12d
0x180057abc  jz      short loc_180057AE5
0x180057abe  mov     esi, r12d
0x180057ac1  lea     rax, aCertgetcertifi_3; "CertGetCertificateChain - revocation ch"...
0x180057ac8  mov     qword ptr [rsp+180h+dwFlags], rax
0x180057acd  mov     [rsp+180h+pChainPara], r12
0x180057ad2  xor     edx, edx
0x180057ad4  xor     ecx, ecx
0x180057ad6  lea     r9d, [r12+4]
0x180057adb  lea     r8d, [r12+20h]
0x180057ae0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180057ae5  mov     [rsp+180h+ppChainContext], rdi; ppChainContext
0x180057aea  mov     [rsp+180h+pvReserved], r12; pvReserved
0x180057aef  mov     [rsp+180h+dwFlags], esi; dwFlags
0x180057af3  lea     rax, [rbp+80h+var_C0]
0x180057af7  mov     [rsp+180h+pChainPara], rax; pChainPara
0x180057afc  xor     r9d, r9d; hAdditionalStore
0x180057aff  mov     r8, r15; pTime
0x180057b02  mov     rdx, r14; pCertContext
0x180057b05  xor     ecx, ecx; hChainEngine
0x180057b07  call    cs:__imp_CertGetCertificateChain
0x180057b0d  test    eax, eax
0x180057b0f  jnz     short loc_180057B49
0x180057b11  call    cs:__imp_GetLastError
0x180057b17  movzx   ecx, ax
0x180057b1a  mov     edi, 80070000h
0x180057b1f  or      ecx, edi
0x180057b21  test    eax, eax
0x180057b23  cmovle  ecx, eax
0x180057b26  test    ecx, ecx
0x180057b28  jns     short loc_180057B3F
0x180057b2a  call    cs:__imp_GetLastError
0x180057b30  movzx   ebx, ax
0x180057b33  or      ebx, edi
0x180057b35  test    eax, eax
0x180057b37  cmovle  ebx, eax
0x180057b3a  jmp     loc_180057C94
0x180057b3f  mov     ebx, 80004005h
0x180057b44  jmp     loc_180057C94
0x180057b49  mov     rax, [rdi]
0x180057b4c  test    byte ptr [rax+4], 4
0x180057b50  jz      loc_180057D09
0x180057b56  xor     edx, edx; Val
0x180057b58  lea     r8d, [rdx+58h]; Size
0x180057b5c  lea     rcx, [rsp+180h+pConfig]; void *
0x180057b61  call    memset
0x180057b66  xorps   xmm0, xmm0
0x180057b69  movups  xmmword ptr [rbp+80h+pChainContext], xmm0
0x180057b6d  mov     [rbp+80h+pChainContext+8], r12
0x180057b71  lea     rax, aCertgetcertifi_4; "CertGetCertificateChain failed. Retryin"...
0x180057b78  mov     qword ptr [rsp+180h+dwFlags], rax
0x180057b7d  mov     [rsp+180h+pChainPara], r12
0x180057b82  xor     edx, edx
0x180057b84  xor     ecx, ecx
0x180057b86  lea     r9d, [rdx+4]
0x180057b8a  lea     r8d, [rdx+20h]
0x180057b8e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180057b93  mov     rcx, [rbp+80h+hCertStore+8]; hCertStore
0x180057b97  test    rcx, rcx
0x180057b9a  jz      short loc_180057BA8
0x180057b9c  xor     edx, edx; dwFlags
0x180057b9e  call    cs:__imp_CertCloseStore
0x180057ba4  mov     [rbp+80h+hCertStore+8], r12
0x180057ba8  lea     rcx, [rbp+80h+hCertStore+8]; void **
0x180057bac  call    ?CreateSubCAStore@@YAJPEAPEAX@Z; CreateSubCAStore(void * *)
0x180057bb1  mov     ebx, eax
0x180057bb3  test    eax, eax
0x180057bb5  jns     short loc_180057BCF
0x180057bb7  mov     rcx, [rbp+80h+pChainContext+8]; pChainContext
0x180057bbb  test    rcx, rcx
0x180057bbe  jz      loc_180057C98
0x180057bc4  call    cs:__imp_CertFreeCertificateChain
0x180057bca  jmp     loc_180057C98
0x180057bcf  mov     [rsp+180h+pConfig.cbSize], 58h ; 'X'
0x180057bd7  mov     [rbp+80h+pConfig.dwFlags], 2000h
0x180057bde  mov     rax, [rbp+80h+hCertStore+8]
0x180057be2  mov     [rbp+80h+pConfig.hExclusiveRoot], rax
0x180057be6  or      [rbp+80h+var_D0], 1
0x180057bea  mov     rcx, [rbp+80h+hChainEngine+8]; hChainEngine
0x180057bee  test    rcx, rcx
0x180057bf1  jz      short loc_180057BFD
0x180057bf3  call    cs:__imp_CertFreeCertificateChainEngine
0x180057bf9  mov     [rbp+80h+hChainEngine+8], r12
0x180057bfd  lea     rdx, [rbp+80h+hChainEngine+8]; phChainEngine
0x180057c01  lea     rcx, [rsp+180h+pConfig]; pConfig
0x180057c06  call    cs:__imp_CertCreateCertificateChainEngine
0x180057c0c  test    eax, eax
0x180057c0e  jz      short loc_180057C55
0x180057c10  mov     rcx, [rbp+80h+pChainContext+8]; pChainContext
0x180057c14  test    rcx, rcx
0x180057c17  jz      short loc_180057C23
0x180057c19  call    cs:__imp_CertFreeCertificateChain
0x180057c1f  mov     [rbp+80h+pChainContext+8], r12
0x180057c23  lea     rax, [rbp+80h+pChainContext+8]
0x180057c27  mov     [rsp+180h+ppChainContext], rax; ppChainContext
0x180057c2c  mov     [rsp+180h+pvReserved], r12; pvReserved
0x180057c31  mov     [rsp+180h+dwFlags], esi; dwFlags
0x180057c35  lea     rax, [rbp+80h+var_C0]
0x180057c39  mov     [rsp+180h+pChainPara], rax; pChainPara
0x180057c3e  xor     r9d, r9d; hAdditionalStore
0x180057c41  mov     r8, r15; pTime
0x180057c44  mov     rdx, r14; pCertContext
0x180057c47  mov     rcx, [rbp+80h+hChainEngine+8]; hChainEngine
0x180057c4b  call    cs:__imp_CertGetCertificateChain
0x180057c51  test    eax, eax
0x180057c53  jnz     short loc_180057CD3
0x180057c55  call    cs:__imp_GetLastError
0x180057c5b  movzx   ecx, ax
0x180057c5e  mov     edi, 80070000h
0x180057c63  or      ecx, edi
0x180057c65  test    eax, eax
0x180057c67  cmovle  ecx, eax
0x180057c6a  test    ecx, ecx
0x180057c6c  jns     short loc_180057C80
0x180057c6e  call    cs:__imp_GetLastError
0x180057c74  movzx   ebx, ax
0x180057c77  or      ebx, edi
0x180057c79  test    eax, eax
0x180057c7b  cmovle  ebx, eax
0x180057c7e  jmp     short loc_180057C85
0x180057c80  mov     ebx, 80004005h
0x180057c85  mov     rcx, [rbp+80h+pChainContext+8]; pChainContext
0x180057c89  test    rcx, rcx
0x180057c8c  jz      short loc_180057C94
0x180057c8e  call    cs:__imp_CertFreeCertificateChain
0x180057c94  test    ebx, ebx
0x180057c96  jns     short loc_180057D09
0x180057c98  lea     rax, aYes_3; "Yes"
0x180057c9f  mov     [rsp+180h+ppChainContext], rax
0x180057ca4  lea     rax, aNo_4; "No"
0x180057cab  mov     [rsp+180h+pvReserved], rax
0x180057cb0  lea     rax, aCertgetcertifi_2; "CertGetCertificateChain failed. SSL : %"...
0x180057cb7  mov     qword ptr [rsp+180h+dwFlags], rax
0x180057cbc  mov     dword ptr [rsp+180h+pChainPara], ebx
0x180057cc0  xor     edx, edx
0x180057cc2  xor     ecx, ecx
0x180057cc4  lea     r9d, [rdx+1]
0x180057cc8  lea     r8d, [rdx+20h]
0x180057ccc  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180057cd1  jmp     short loc_180057D09
0x180057cd3  mov     rcx, [rbp+80h+pChainContext+8]
0x180057cd7  mov     rax, rcx
0x180057cda  test    dword ptr [rcx+8], 2000h
0x180057ce1  jz      short loc_180057CFD
0x180057ce3  mov     rcx, [rdi]; pChainContext
0x180057ce6  call    cs:__imp_CertFreeCertificateChain
0x180057cec  mov     rax, [rbp+80h+pChainContext+8]
0x180057cf0  mov     rcx, r12; pChainContext
0x180057cf3  mov     [rbp+80h+pChainContext+8], rcx
0x180057cf7  mov     [rdi], rax
0x180057cfa  mov     rax, r12
0x180057cfd  test    rax, rax
0x180057d00  jz      short loc_180057D09
0x180057d02  call    cs:__imp_CertFreeCertificateChain
0x180057d08  nop
0x180057d09  mov     rcx, [rbp+80h+hCertStore+8]; hCertStore
0x180057d0d  test    rcx, rcx
0x180057d10  jz      short loc_180057D1E
0x180057d12  xor     edx, edx; dwFlags
0x180057d14  call    cs:__imp_CertCloseStore
0x180057d1a  mov     [rbp+80h+hCertStore+8], r12
0x180057d1e  mov     rcx, [rbp+80h+hChainEngine+8]; hChainEngine
0x180057d22  test    rcx, rcx
0x180057d25  jz      short loc_180057D2D
0x180057d27  call    cs:__imp_CertFreeCertificateChainEngine
0x180057d2d  mov     eax, ebx
0x180057d2f  mov     rcx, [rbp+80h+var_30]
0x180057d33  xor     rcx, rsp; StackCookie
0x180057d36  call    __security_check_cookie
0x180057d3b  lea     r11, [rsp+180h+var_20]
0x180057d43  mov     rbx, [r11+38h]
0x180057d47  mov     rsi, [r11+40h]
0x180057d4b  mov     rsp, r11
0x180057d4e  pop     r15
0x180057d50  pop     r14
0x180057d52  pop     r12
0x180057d54  pop     rdi
0x180057d55  pop     rbp
0x180057d56  retn
```
