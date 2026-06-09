# CommonUtil::UtilMicrosoftCertChainCheck

- ea: `0x140010bc4`
- end: `0x140010dc3`
- name: `CommonUtil::UtilMicrosoftCertChainCheck`
- size: `511`
- prototype: `__int64 __fastcall(void *, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400104e4`
- `0x1400108f8`

## callees

- `0x140003640`
- `0x14000536c`
- `0x140010bc4`

## import_xrefs

- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x140010c3d`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x140010cc1`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x140010d3a`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x140010c3d`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x140010cc1`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x140010d3a`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x140010bd8`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x140010bd8`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x140010bf2`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x140010bf2`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilMicrosoftCertChainCheck(void *a1, char a2)
{
  CRYPT_PROVIDER_DATA *v3; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  const CERT_CHAIN_CONTEXT *pChainContext; // r15
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  DWORD dwError; // ebx
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+20h] [rbp-38h] BYREF
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+30h] [rbp-28h] BYREF

  v3 = WTHelperProvDataFromStateData(a1);
  if ( !v3 )
    return 2147500037LL;
  ProvSignerFromChain = WTHelperGetProvSignerFromChain(v3, 0, 0, 0);
  if ( !ProvSignerFromChain )
    return 2147500037LL;
  pChainContext = ProvSignerFromChain->pChainContext;
  pPolicyPara.cbSize = 16;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  pPolicyPara.pvExtraPolicyPara = 0;
  pPolicyPara.dwFlags = 3840;
  pPolicyStatus.cbSize = 24;
  if ( !CertVerifyCertificateChainPolicy((LPCSTR)7, pChainContext, &pPolicyPara, &pPolicyStatus) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 2148098049LL;
    v7 = 11;
LABEL_24:
    WPP_SF_(v6[2], v7, &WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids);
    return 2148098049LL;
  }
  dwError = pPolicyStatus.dwError;
  if ( (pPolicyStatus.dwError & 0x80000000) == 0 )
    return dwError != 0 ? 0x8000FFFF : 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids,
      pPolicyStatus.dwError);
  pPolicyPara.dwFlags = 134912;
  if ( !CertVerifyCertificateChainPolicy((LPCSTR)7, pChainContext, &pPolicyPara, &pPolicyStatus) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 2148098049LL;
    v7 = 13;
    goto LABEL_24;
  }
  dwError = pPolicyStatus.dwError;
  if ( (pPolicyStatus.dwError & 0x80000000) == 0 )
    return dwError != 0 ? 0x8000FFFF : 0;
  if ( (a2 & 0x20) == 0 )
    goto LABEL_28;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids,
      pPolicyStatus.dwError);
  pPolicyPara.dwFlags = 69376;
  if ( !CertVerifyCertificateChainPolicy((LPCSTR)7, pChainContext, &pPolicyPara, &pPolicyStatus) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 2148098049LL;
    v7 = 15;
    goto LABEL_24;
  }
  dwError = pPolicyStatus.dwError;
  if ( (pPolicyStatus.dwError & 0x80000000) == 0 )
    return dwError != 0 ? 0x8000FFFF : 0;
LABEL_28:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids, dwError);
  return dwError;
}

```

## disassembly

```asm
0x140010bc4  push    rbp
0x140010bc6  push    rbx
0x140010bc7  push    rdi
0x140010bc8  push    r13
0x140010bca  push    r14
0x140010bcc  push    r15
0x140010bce  mov     rbp, rsp
0x140010bd1  sub     rsp, 58h
0x140010bd5  mov     r14d, edx
0x140010bd8  call    cs:__imp_WTHelperProvDataFromStateData
0x140010bde  test    rax, rax
0x140010be1  jz      loc_140010DB0
0x140010be7  xor     r9d, r9d; idxCounterSigner
0x140010bea  xor     r8d, r8d; fCounterSigner
0x140010bed  xor     edx, edx; idxSigner
0x140010bef  mov     rcx, rax; pProvData
0x140010bf2  call    cs:__imp_WTHelperGetProvSignerFromChain
0x140010bf8  test    rax, rax
0x140010bfb  jz      loc_140010DB0
0x140010c01  mov     r15, [rax+38h]
0x140010c05  lea     r9, [rbp+pPolicyStatus]; pPolicyStatus
0x140010c09  xor     eax, eax
0x140010c0b  mov     [rbp+pPolicyPara.cbSize], 10h
0x140010c12  xorps   xmm0, xmm0
0x140010c15  mov     [rbp+pPolicyStatus.pvExtraPolicyStatus], rax
0x140010c19  movups  xmmword ptr [rbp+pPolicyStatus.cbSize], xmm0
0x140010c1d  lea     r8, [rbp+pPolicyPara]; pPolicyPara
0x140010c21  mov     [rbp+pPolicyPara.pvExtraPolicyPara], rax
0x140010c25  lea     r13d, [rax+7]
0x140010c29  mov     [rbp+pPolicyPara.dwFlags], 0F00h
0x140010c30  mov     ecx, r13d; pszPolicyOID
0x140010c33  mov     [rbp+pPolicyStatus.cbSize], 18h
0x140010c3a  mov     rdx, r15; pChainContext
0x140010c3d  call    cs:__imp_CertVerifyCertificateChainPolicy
0x140010c43  test    eax, eax
0x140010c45  jnz     short loc_140010C70
0x140010c47  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c4e  lea     rdi, WPP_GLOBAL_Control
0x140010c55  cmp     rcx, rdi
0x140010c58  jz      loc_140010D69
0x140010c5e  test    byte ptr [rcx+1Ch], 1
0x140010c62  jz      loc_140010D69
0x140010c68  lea     edx, [rax+0Bh]
0x140010c6b  jmp     loc_140010D59
0x140010c70  mov     ebx, [rbp+pPolicyStatus.dwError]
0x140010c73  test    ebx, ebx
0x140010c75  jns     loc_140010DA5
0x140010c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c82  lea     rdi, WPP_GLOBAL_Control
0x140010c89  cmp     rcx, rdi
0x140010c8c  jz      short loc_140010CAC
0x140010c8e  test    byte ptr [rcx+1Ch], 10h
0x140010c92  jz      short loc_140010CAC
0x140010c94  mov     rcx, [rcx+10h]
0x140010c98  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x140010c9f  mov     edx, 0Ch
0x140010ca4  mov     r9d, ebx
0x140010ca7  call    WPP_SF_d
0x140010cac  lea     r9, [rbp+pPolicyStatus]; pPolicyStatus
0x140010cb0  mov     [rbp+pPolicyPara.dwFlags], 20F00h
0x140010cb7  lea     r8, [rbp+pPolicyPara]; pPolicyPara
0x140010cbb  mov     rdx, r15; pChainContext
0x140010cbe  mov     rcx, r13; pszPolicyOID
0x140010cc1  call    cs:__imp_CertVerifyCertificateChainPolicy
0x140010cc7  test    eax, eax
0x140010cc9  jnz     short loc_140010CEA
0x140010ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x140010cd2  cmp     rcx, rdi
0x140010cd5  jz      loc_140010D69
0x140010cdb  test    byte ptr [rcx+1Ch], 1
0x140010cdf  jz      loc_140010D69
0x140010ce5  lea     edx, [rax+0Dh]
0x140010ce8  jmp     short loc_140010D59
0x140010cea  mov     ebx, [rbp+pPolicyStatus.dwError]
0x140010ced  test    ebx, ebx
0x140010cef  jns     loc_140010DA5
0x140010cf5  test    r14b, 20h
0x140010cf9  jz      short loc_140010D77
0x140010cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140010d02  cmp     rcx, rdi
0x140010d05  jz      short loc_140010D25
0x140010d07  test    byte ptr [rcx+1Ch], 10h
0x140010d0b  jz      short loc_140010D25
0x140010d0d  mov     rcx, [rcx+10h]
0x140010d11  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x140010d18  mov     edx, 0Eh
0x140010d1d  mov     r9d, ebx
0x140010d20  call    WPP_SF_d
0x140010d25  lea     r9, [rbp+pPolicyStatus]; pPolicyStatus
0x140010d29  mov     [rbp+pPolicyPara.dwFlags], 10F00h
0x140010d30  lea     r8, [rbp+pPolicyPara]; pPolicyPara
0x140010d34  mov     rdx, r15; pChainContext
0x140010d37  mov     rcx, r13; pszPolicyOID
0x140010d3a  call    cs:__imp_CertVerifyCertificateChainPolicy
0x140010d40  test    eax, eax
0x140010d42  jnz     short loc_140010D70
0x140010d44  mov     rcx, cs:WPP_GLOBAL_Control
0x140010d4b  cmp     rcx, rdi
0x140010d4e  jz      short loc_140010D69
0x140010d50  test    byte ptr [rcx+1Ch], 1
0x140010d54  jz      short loc_140010D69
0x140010d56  lea     edx, [rax+0Fh]
0x140010d59  mov     rcx, [rcx+10h]
0x140010d5d  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x140010d64  call    WPP_SF_
0x140010d69  mov     eax, 80096001h
0x140010d6e  jmp     short loc_140010DB5
0x140010d70  mov     ebx, [rbp+pPolicyStatus.dwError]
0x140010d73  test    ebx, ebx
0x140010d75  jns     short loc_140010DA5
0x140010d77  mov     rcx, cs:WPP_GLOBAL_Control
0x140010d7e  cmp     rcx, rdi
0x140010d81  jz      short loc_140010DA1
0x140010d83  test    byte ptr [rcx+1Ch], 1
0x140010d87  jz      short loc_140010DA1
0x140010d89  mov     rcx, [rcx+10h]
0x140010d8d  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x140010d94  mov     edx, 10h
0x140010d99  mov     r9d, ebx
0x140010d9c  call    WPP_SF_d
0x140010da1  mov     eax, ebx
0x140010da3  jmp     short loc_140010DB5
0x140010da5  neg     ebx
0x140010da7  sbb     eax, eax
0x140010da9  and     eax, 8000FFFFh
0x140010dae  jmp     short loc_140010DB5
0x140010db0  mov     eax, 80004005h
0x140010db5  add     rsp, 58h
0x140010db9  pop     r15
0x140010dbb  pop     r14
0x140010dbd  pop     r13
0x140010dbf  pop     rdi
0x140010dc0  pop     rbx
0x140010dc1  pop     rbp
0x140010dc2  retn
```
