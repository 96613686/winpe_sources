# CabUtils::VerifyCertificateChainPolicy(_WINTRUST_DATA,ulong)

- ea: `0x18003ec48`
- end: `0x18003ee6d`
- name: `?VerifyCertificateChainPolicy@CabUtils@@CAJU_WINTRUST_DATA@@K@Z`
- size: `549`
- prototype: `__int64 __fastcall(struct _WINTRUST_DATA *__struct_ptr, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18003e7b0`

## callees

- `0x18000a6e0`
- `0x18000b2b4`
- `0x18001206c`
- `0x18001208c`
- `0x180017670`
- `0x180017cb4`
- `0x180028148`
- `0x18003ec48`

## import_xrefs

- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18003edb7`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x18003edb7`
- `CRYPT32!CertGetNameStringW` at `0x18003ed19`
- `CRYPT32!CertGetNameStringW` at `0x18003ed19`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18003ec95`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18003ec95`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x18003eccb`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x18003eccb`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18003ece8`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18003ed55`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18003ece8`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18003ed55`

## string_xrefs

- `0x18003eca8`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003ed3a`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`
- `0x18003eded`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\cabutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CabUtils::VerifyCertificateChainPolicy(struct _WINTRUST_DATA *a1, int a2)
{
  CRYPT_PROVIDER_DATA *v4; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_SGNR *v9; // rbx
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  unsigned int v11; // ebx
  DWORD dwErrorStatus; // esi
  unsigned int dwInfoStatus; // r14d
  DWORD dwError; // edi
  PCCERT_CHAIN_CONTEXT pChainContext; // rax
  unsigned __int64 v16; // rdx
  unsigned __int8 v17; // cl
  __int64 v18; // rcx
  __int64 v19; // rax
  int pszNameString; // [rsp+20h] [rbp-E0h]
  struct _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+68h] [rbp-98h] BYREF
  struct _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+78h] [rbp-88h] BYREF
  WCHAR v23[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  memset_0(v23, 0, 0x208u);
  v4 = WTHelperProvDataFromStateData(a1->hWVTStateData);
  if ( !v4 )
  {
    v6 = 672;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
             v5);
  }
  ProvSignerFromChain = WTHelperGetProvSignerFromChain(v4, 0, 0, 0);
  v9 = ProvSignerFromChain;
  if ( !ProvSignerFromChain )
  {
    v6 = 676;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
             v5);
  }
  ProvCertFromChain = WTHelperGetProvCertFromChain(ProvSignerFromChain, ProvSignerFromChain->csCertChain - 1);
  if ( !ProvCertFromChain )
  {
    v6 = 680;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
             v5);
  }
  if ( CertGetNameStringW(ProvCertFromChain->pCert, 4u, 0, 0, v23, 0x104u) != 1 || v23[0] )
  {
    if ( !WTHelperGetProvCertFromChain(v9, 0) )
    {
      v6 = 694;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
               v5);
    }
    dwErrorStatus = 0;
    dwInfoStatus = 8;
    dwError = 0;
    HIDWORD(pPolicyPara.pvExtraPolicyPara) = 0;
    memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
    pPolicyPara.cbSize = 16;
    pPolicyStatus.cbSize = 24;
    *(_QWORD *)&pPolicyPara.dwFlags = a2 | 0x40F00u;
    if ( CertVerifyCertificateChainPolicy((LPCSTR)7, v9->pChainContext, &pPolicyPara, &pPolicyStatus) )
    {
      pChainContext = v9->pChainContext;
      dwErrorStatus = pChainContext->TrustStatus.dwErrorStatus;
      dwInfoStatus = pChainContext->TrustStatus.dwInfoStatus;
      dwError = pPolicyStatus.dwError;
      if ( (dwInfoStatus & 8) == 0 && !pPolicyStatus.dwError )
        return 0;
    }
    v11 = -2135164393;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D7,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
      (const char *)0x80BBFA17LL,
      pszNameString);
    if ( MitigationTelemetryClass::IsEnabled(v17, v16) )
    {
      v19 = wil::details::static_lazy<MitigationTelemetryClass>::get(
              v18,
              _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_);
      MitigationTelemetryClass::MitigationCertVerificationFailed_(
        v19,
        dwErrorStatus,
        dwInfoStatus,
        dwError,
        0,
        2,
        v23,
        a2);
    }
  }
  else
  {
    v11 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B2,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\cabutils.cpp",
      (const char *)0x80070057LL,
      pszNameString);
  }
  return v11;
}

```

## disassembly

```asm
0x18003ec48  mov     [rsp-8+arg_10], rbx
0x18003ec4d  mov     [rsp-8+arg_18], rsi
0x18003ec52  push    rbp
0x18003ec53  push    rdi
0x18003ec54  push    r12
0x18003ec56  push    r14
0x18003ec58  push    r15
0x18003ec5a  lea     rbp, [rsp-1B0h]
0x18003ec62  sub     rsp, 2B0h
0x18003ec69  mov     rax, cs:__security_cookie
0x18003ec70  xor     rax, rsp
0x18003ec73  mov     [rbp+1D0h+var_30], rax
0x18003ec7a  mov     r15d, edx
0x18003ec7d  mov     rbx, rcx
0x18003ec80  xor     edx, edx; Val
0x18003ec82  mov     r8d, 208h; Size
0x18003ec88  lea     rcx, [rbp+1D0h+var_240]; void *
0x18003ec8c  call    memset_0
0x18003ec91  mov     rcx, [rbx+38h]; hStateData
0x18003ec95  call    cs:__imp_WTHelperProvDataFromStateData
0x18003ec9b  xor     r12d, r12d
0x18003ec9e  test    rax, rax
0x18003eca1  jnz     short loc_18003ECC0
0x18003eca3  mov     edx, 2A0h; void *
0x18003eca8  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003ecaf  mov     rcx, [rbp+1D8h]; this
0x18003ecb6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003ecbb  jmp     loc_18003EE42
0x18003ecc0  xor     r9d, r9d; idxCounterSigner
0x18003ecc3  xor     r8d, r8d; fCounterSigner
0x18003ecc6  xor     edx, edx; idxSigner
0x18003ecc8  mov     rcx, rax; pProvData
0x18003eccb  call    cs:__imp_WTHelperGetProvSignerFromChain
0x18003ecd1  mov     rbx, rax
0x18003ecd4  test    rax, rax
0x18003ecd7  jnz     short loc_18003ECE0
0x18003ecd9  mov     edx, 2A4h
0x18003ecde  jmp     short loc_18003ECA8
0x18003ece0  mov     edx, [rax+0Ch]
0x18003ece3  dec     edx; idxCert
0x18003ece5  mov     rcx, rbx; pSgnr
0x18003ece8  call    cs:__imp_WTHelperGetProvCertFromChain
0x18003ecee  test    rax, rax
0x18003ecf1  jnz     short loc_18003ECFA
0x18003ecf3  mov     edx, 2A8h
0x18003ecf8  jmp     short loc_18003ECA8
0x18003ecfa  mov     [rsp+2D0h+cchNameString], 104h; cchNameString
0x18003ed02  lea     rcx, [rbp+1D0h+var_240]
0x18003ed06  mov     [rsp+2D0h+pszNameString], rcx; int
0x18003ed0b  xor     r9d, r9d; pvTypePara
0x18003ed0e  xor     r8d, r8d; dwFlags
0x18003ed11  lea     edx, [r9+4]; dwType
0x18003ed15  mov     rcx, [rax+8]; pCertContext
0x18003ed19  call    cs:__imp_CertGetNameStringW
0x18003ed1f  cmp     eax, 1
0x18003ed22  jnz     short loc_18003ED50
0x18003ed24  cmp     [rbp+1D0h+var_240], r12w
0x18003ed29  jnz     short loc_18003ED50
0x18003ed2b  mov     rcx, [rbp+1D8h]; this
0x18003ed32  mov     ebx, 80070057h
0x18003ed37  mov     r9d, ebx; char *
0x18003ed3a  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003ed41  mov     edx, 2B2h; void *
0x18003ed46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ed4b  jmp     loc_18003EE40
0x18003ed50  xor     edx, edx; idxCert
0x18003ed52  mov     rcx, rbx; pSgnr
0x18003ed55  call    cs:__imp_WTHelperGetProvCertFromChain
0x18003ed5b  test    rax, rax
0x18003ed5e  jnz     short loc_18003ED6A
0x18003ed60  mov     edx, 2B6h
0x18003ed65  jmp     loc_18003ECA8
0x18003ed6a  mov     esi, r12d
0x18003ed6d  mov     r14d, 8
0x18003ed73  mov     edi, r12d
0x18003ed76  mov     [rsp+2D0h+pPolicyPara.pvExtraPolicyPara], r12
0x18003ed7b  xorps   xmm0, xmm0
0x18003ed7e  xor     eax, eax
0x18003ed80  movups  xmmword ptr [rsp+2D0h+pPolicyStatus.cbSize], xmm0
0x18003ed85  mov     [rbp+1D0h+pPolicyStatus.pvExtraPolicyStatus], rax
0x18003ed89  mov     [rsp+2D0h+pPolicyPara.cbSize], 10h
0x18003ed91  mov     [rsp+2D0h+pPolicyStatus.cbSize], 18h
0x18003ed99  mov     eax, r15d
0x18003ed9c  or      eax, 40F00h
0x18003eda1  mov     [rsp+2D0h+pPolicyPara.dwFlags], eax
0x18003eda5  lea     r9, [rsp+2D0h+pPolicyStatus]; pPolicyStatus
0x18003edaa  lea     r8, [rsp+2D0h+pPolicyPara]; pPolicyPara
0x18003edaf  mov     rdx, [rbx+38h]; pChainContext
0x18003edb3  lea     ecx, [r14-1]; pszPolicyOID
0x18003edb7  call    cs:__imp_CertVerifyCertificateChainPolicy
0x18003edbd  test    eax, eax
0x18003edbf  jz      short loc_18003EDDE
0x18003edc1  mov     rax, [rbx+38h]
0x18003edc5  mov     esi, [rax+4]
0x18003edc8  mov     r14d, [rax+8]
0x18003edcc  mov     edi, [rsp+2D0h+pPolicyStatus.dwError]
0x18003edd0  test    r14b, 8
0x18003edd4  jnz     short loc_18003EDDE
0x18003edd6  test    edi, edi
0x18003edd8  jnz     short loc_18003EDDE
0x18003edda  xor     eax, eax
0x18003eddc  jmp     short loc_18003EE42
0x18003edde  mov     rcx, [rbp+1D8h]; this
0x18003ede5  mov     ebx, 80BBFA17h
0x18003edea  mov     r9d, ebx; char *
0x18003eded  lea     r8, aOnecoreBaseDia_17; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18003edf4  mov     edx, 2D7h; void *
0x18003edf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003edfe  nop
0x18003edff  call    ?IsEnabled@MitigationTelemetryClass@@SA_NE_K@Z; MitigationTelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18003ee04  test    al, al
0x18003ee06  jz      short loc_18003EE40
0x18003ee08  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_a44fdf97cbcc0b6240bb4609dde993dd_@@CA@XZ; _lambda_a44fdf97cbcc0b6240bb4609dde993dd_::_lambda_invoker_cdecl_(void)
0x18003ee0f  call    ?get@?$static_lazy@VMitigationTelemetryClass@@@details@wil@@QEAAPEAVMitigationTelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<MitigationTelemetryClass>::get(void (*)(void))
0x18003ee14  mov     [rsp+2D0h+var_298], r15d
0x18003ee19  lea     rcx, [rbp+1D0h+var_240]
0x18003ee1d  mov     [rsp+2D0h+var_2A0], rcx
0x18003ee22  mov     [rsp+2D0h+cchNameString], 2
0x18003ee2a  mov     dword ptr [rsp+2D0h+pszNameString], r12d
0x18003ee2f  mov     r9d, edi
0x18003ee32  mov     r8d, r14d
0x18003ee35  mov     edx, esi
0x18003ee37  mov     rcx, rax
0x18003ee3a  call    ?MitigationCertVerificationFailed_@MitigationTelemetryClass@@QEAAXKKKW4CertType@@W4CertChainPolicyType@@PEBGK@Z; MitigationTelemetryClass::MitigationCertVerificationFailed_(ulong,ulong,ulong,CertType,CertChainPolicyType,ushort const *,ulong)
0x18003ee3f  nop
0x18003ee40  mov     eax, ebx
0x18003ee42  mov     rcx, [rbp+1D0h+var_30]
0x18003ee49  xor     rcx, rsp; StackCookie
0x18003ee4c  call    __security_check_cookie
0x18003ee51  lea     r11, [rsp+2D0h+var_20]
0x18003ee59  mov     rbx, [r11+40h]
0x18003ee5d  mov     rsi, [r11+48h]
0x18003ee61  mov     rsp, r11
0x18003ee64  pop     r15
0x18003ee66  pop     r14
0x18003ee68  pop     r12
0x18003ee6a  pop     rdi
0x18003ee6b  pop     rbp
0x18003ee6c  retn
```
