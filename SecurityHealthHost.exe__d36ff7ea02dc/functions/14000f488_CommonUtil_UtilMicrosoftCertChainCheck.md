# CommonUtil::UtilMicrosoftCertChainCheck

- ea: `0x14000f488`
- end: `0x14000f687`
- name: `CommonUtil::UtilMicrosoftCertChainCheck`
- size: `511`
- prototype: `__int64 __fastcall(void *, char)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ee14`
- `0x14000f1bc`

## callees

- `0x140003018`
- `0x140003040`
- `0x14000f488`

## import_xrefs

- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x14000f501`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x14000f585`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x14000f5fe`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x14000f501`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x14000f585`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x14000f5fe`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x14000f4b6`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x14000f4b6`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x14000f49c`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x14000f49c`

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
0x14000f488  push    rbp
0x14000f48a  push    rbx
0x14000f48b  push    rdi
0x14000f48c  push    r13
0x14000f48e  push    r14
0x14000f490  push    r15
0x14000f492  mov     rbp, rsp
0x14000f495  sub     rsp, 58h
0x14000f499  mov     r14d, edx
0x14000f49c  call    cs:__imp_WTHelperProvDataFromStateData
0x14000f4a2  test    rax, rax
0x14000f4a5  jz      loc_14000F674
0x14000f4ab  xor     r9d, r9d; idxCounterSigner
0x14000f4ae  xor     r8d, r8d; fCounterSigner
0x14000f4b1  xor     edx, edx; idxSigner
0x14000f4b3  mov     rcx, rax; pProvData
0x14000f4b6  call    cs:__imp_WTHelperGetProvSignerFromChain
0x14000f4bc  test    rax, rax
0x14000f4bf  jz      loc_14000F674
0x14000f4c5  mov     r15, [rax+38h]
0x14000f4c9  lea     r9, [rbp+pPolicyStatus]; pPolicyStatus
0x14000f4cd  xor     eax, eax
0x14000f4cf  mov     [rbp+pPolicyPara.cbSize], 10h
0x14000f4d6  xorps   xmm0, xmm0
0x14000f4d9  mov     [rbp+pPolicyStatus.pvExtraPolicyStatus], rax
0x14000f4dd  movups  xmmword ptr [rbp+pPolicyStatus.cbSize], xmm0
0x14000f4e1  lea     r8, [rbp+pPolicyPara]; pPolicyPara
0x14000f4e5  mov     [rbp+pPolicyPara.pvExtraPolicyPara], rax
0x14000f4e9  lea     r13d, [rax+7]
0x14000f4ed  mov     [rbp+pPolicyPara.dwFlags], 0F00h
0x14000f4f4  mov     ecx, r13d; pszPolicyOID
0x14000f4f7  mov     [rbp+pPolicyStatus.cbSize], 18h
0x14000f4fe  mov     rdx, r15; pChainContext
0x14000f501  call    cs:__imp_CertVerifyCertificateChainPolicy
0x14000f507  test    eax, eax
0x14000f509  jnz     short loc_14000F534
0x14000f50b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f512  lea     rdi, WPP_GLOBAL_Control
0x14000f519  cmp     rcx, rdi
0x14000f51c  jz      loc_14000F62D
0x14000f522  test    byte ptr [rcx+1Ch], 1
0x14000f526  jz      loc_14000F62D
0x14000f52c  lea     edx, [rax+0Bh]
0x14000f52f  jmp     loc_14000F61D
0x14000f534  mov     ebx, [rbp+pPolicyStatus.dwError]
0x14000f537  test    ebx, ebx
0x14000f539  jns     loc_14000F669
0x14000f53f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f546  lea     rdi, WPP_GLOBAL_Control
0x14000f54d  cmp     rcx, rdi
0x14000f550  jz      short loc_14000F570
0x14000f552  test    byte ptr [rcx+1Ch], 10h
0x14000f556  jz      short loc_14000F570
0x14000f558  mov     rcx, [rcx+10h]
0x14000f55c  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x14000f563  mov     edx, 0Ch
0x14000f568  mov     r9d, ebx
0x14000f56b  call    WPP_SF_d
0x14000f570  lea     r9, [rbp+pPolicyStatus]; pPolicyStatus
0x14000f574  mov     [rbp+pPolicyPara.dwFlags], 20F00h
0x14000f57b  lea     r8, [rbp+pPolicyPara]; pPolicyPara
0x14000f57f  mov     rdx, r15; pChainContext
0x14000f582  mov     rcx, r13; pszPolicyOID
0x14000f585  call    cs:__imp_CertVerifyCertificateChainPolicy
0x14000f58b  test    eax, eax
0x14000f58d  jnz     short loc_14000F5AE
0x14000f58f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f596  cmp     rcx, rdi
0x14000f599  jz      loc_14000F62D
0x14000f59f  test    byte ptr [rcx+1Ch], 1
0x14000f5a3  jz      loc_14000F62D
0x14000f5a9  lea     edx, [rax+0Dh]
0x14000f5ac  jmp     short loc_14000F61D
0x14000f5ae  mov     ebx, [rbp+pPolicyStatus.dwError]
0x14000f5b1  test    ebx, ebx
0x14000f5b3  jns     loc_14000F669
0x14000f5b9  test    r14b, 20h
0x14000f5bd  jz      short loc_14000F63B
0x14000f5bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f5c6  cmp     rcx, rdi
0x14000f5c9  jz      short loc_14000F5E9
0x14000f5cb  test    byte ptr [rcx+1Ch], 10h
0x14000f5cf  jz      short loc_14000F5E9
0x14000f5d1  mov     rcx, [rcx+10h]
0x14000f5d5  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x14000f5dc  mov     edx, 0Eh
0x14000f5e1  mov     r9d, ebx
0x14000f5e4  call    WPP_SF_d
0x14000f5e9  lea     r9, [rbp+pPolicyStatus]; pPolicyStatus
0x14000f5ed  mov     [rbp+pPolicyPara.dwFlags], 10F00h
0x14000f5f4  lea     r8, [rbp+pPolicyPara]; pPolicyPara
0x14000f5f8  mov     rdx, r15; pChainContext
0x14000f5fb  mov     rcx, r13; pszPolicyOID
0x14000f5fe  call    cs:__imp_CertVerifyCertificateChainPolicy
0x14000f604  test    eax, eax
0x14000f606  jnz     short loc_14000F634
0x14000f608  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f60f  cmp     rcx, rdi
0x14000f612  jz      short loc_14000F62D
0x14000f614  test    byte ptr [rcx+1Ch], 1
0x14000f618  jz      short loc_14000F62D
0x14000f61a  lea     edx, [rax+0Fh]
0x14000f61d  mov     rcx, [rcx+10h]
0x14000f621  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x14000f628  call    WPP_SF_
0x14000f62d  mov     eax, 80096001h
0x14000f632  jmp     short loc_14000F679
0x14000f634  mov     ebx, [rbp+pPolicyStatus.dwError]
0x14000f637  test    ebx, ebx
0x14000f639  jns     short loc_14000F669
0x14000f63b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f642  cmp     rcx, rdi
0x14000f645  jz      short loc_14000F665
0x14000f647  test    byte ptr [rcx+1Ch], 1
0x14000f64b  jz      short loc_14000F665
0x14000f64d  mov     rcx, [rcx+10h]
0x14000f651  lea     r8, WPP_adde249b3c3e3d6a586c05ab82af40e6_Traceguids
0x14000f658  mov     edx, 10h
0x14000f65d  mov     r9d, ebx
0x14000f660  call    WPP_SF_d
0x14000f665  mov     eax, ebx
0x14000f667  jmp     short loc_14000F679
0x14000f669  neg     ebx
0x14000f66b  sbb     eax, eax
0x14000f66d  and     eax, 8000FFFFh
0x14000f672  jmp     short loc_14000F679
0x14000f674  mov     eax, 80004005h
0x14000f679  add     rsp, 58h
0x14000f67d  pop     r15
0x14000f67f  pop     r14
0x14000f681  pop     r13
0x14000f683  pop     rdi
0x14000f684  pop     rbx
0x14000f685  pop     rbp
0x14000f686  retn
```
