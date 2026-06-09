# VerifySignature_WinCrypt

- ea: `0x140083dc4`
- end: `0x140084356`
- name: `VerifySignature_WinCrypt`
- size: `1426`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400c6120`

## callees

- `0x14003a0f4`
- `0x14003a5c0`
- `0x14007d1e0`
- `0x14007d210`
- `0x14007e034`
- `0x140083dc4`
- `0x140084850`
- `0x140084b14`

## import_xrefs

- `CRYPT32!CryptImportPublicKeyInfo` at `0x140083fa6`
- `CRYPT32!CryptImportPublicKeyInfo` at `0x140083fa6`
- `CRYPT32!CertFreeCertificateContext` at `0x140083ebb`
- `CRYPT32!CertFreeCertificateContext` at `0x140083f48`
- `CRYPT32!CertFreeCertificateContext` at `0x140084003`
- `CRYPT32!CertFreeCertificateContext` at `0x1400840cb`
- `CRYPT32!CertFreeCertificateContext` at `0x140084154`
- `CRYPT32!CertFreeCertificateContext` at `0x14008427c`
- `CRYPT32!CertFreeCertificateContext` at `0x1400842b5`
- `CRYPT32!CertFreeCertificateContext` at `0x1400842e9`
- `CRYPT32!CertFreeCertificateContext` at `0x14008431d`
- `CRYPT32!CertFreeCertificateContext` at `0x140083e6f`
- `CRYPT32!CertFreeCertificateContext` at `0x140083ebb`
- `CRYPT32!CertFreeCertificateContext` at `0x140083f48`
- `CRYPT32!CertFreeCertificateContext` at `0x140084003`
- `CRYPT32!CertFreeCertificateContext` at `0x1400840cb`
- `CRYPT32!CertFreeCertificateContext` at `0x140084154`
- `CRYPT32!CertFreeCertificateContext` at `0x14008427c`
- `CRYPT32!CertFreeCertificateContext` at `0x1400842b5`
- `CRYPT32!CertFreeCertificateContext` at `0x1400842e9`
- `CRYPT32!CertFreeCertificateContext` at `0x14008431d`
- `CRYPT32!CertCreateCertificateContext` at `0x140083e40`
- `CRYPT32!CertCreateCertificateContext` at `0x140083e40`
- `KERNEL32!GetLastError` at `0x140083e95`
- `KERNEL32!GetLastError` at `0x140083f13`
- `KERNEL32!GetLastError` at `0x140083fc2`
- `KERNEL32!GetLastError` at `0x14008407e`
- `KERNEL32!GetLastError` at `0x140084107`
- `KERNEL32!GetLastError` at `0x140084217`
- `KERNEL32!GetLastError` at `0x140083e95`
- `KERNEL32!GetLastError` at `0x140083f13`
- `KERNEL32!GetLastError` at `0x140083fc2`
- `KERNEL32!GetLastError` at `0x14008407e`
- `KERNEL32!GetLastError` at `0x140084107`
- `KERNEL32!GetLastError` at `0x140084217`
- `ADVAPI32!CryptReleaseContext` at `0x140083f3c`
- `ADVAPI32!CryptReleaseContext` at `0x140083ff7`
- `ADVAPI32!CryptReleaseContext` at `0x1400840bf`
- `ADVAPI32!CryptReleaseContext` at `0x140084148`
- `ADVAPI32!CryptReleaseContext` at `0x140084270`
- `ADVAPI32!CryptReleaseContext` at `0x1400842a9`
- `ADVAPI32!CryptReleaseContext` at `0x1400842dd`
- `ADVAPI32!CryptReleaseContext` at `0x140084311`
- `ADVAPI32!CryptReleaseContext` at `0x140083f3c`
- `ADVAPI32!CryptReleaseContext` at `0x140083ff7`
- `ADVAPI32!CryptReleaseContext` at `0x1400840bf`
- `ADVAPI32!CryptReleaseContext` at `0x140084148`
- `ADVAPI32!CryptReleaseContext` at `0x140084270`
- `ADVAPI32!CryptReleaseContext` at `0x1400842a9`
- `ADVAPI32!CryptReleaseContext` at `0x1400842dd`
- `ADVAPI32!CryptReleaseContext` at `0x140084311`
- `ADVAPI32!CryptVerifySignatureW` at `0x14008420b`
- `ADVAPI32!CryptVerifySignatureW` at `0x14008420b`
- `ADVAPI32!CryptHashData` at `0x1400840eb`
- `ADVAPI32!CryptHashData` at `0x1400840eb`
- `ADVAPI32!CryptCreateHash` at `0x140084062`
- `ADVAPI32!CryptCreateHash` at `0x140084062`
- `ADVAPI32!CryptDestroyHash` at `0x1400840a5`
- `ADVAPI32!CryptDestroyHash` at `0x14008412e`
- `ADVAPI32!CryptDestroyHash` at `0x140084256`
- `ADVAPI32!CryptDestroyHash` at `0x14008428f`
- `ADVAPI32!CryptDestroyHash` at `0x1400842c3`
- `ADVAPI32!CryptDestroyHash` at `0x1400842f7`
- `ADVAPI32!CryptDestroyHash` at `0x140084039`
- `ADVAPI32!CryptDestroyHash` at `0x1400840a5`
- `ADVAPI32!CryptDestroyHash` at `0x14008412e`
- `ADVAPI32!CryptDestroyHash` at `0x140084256`
- `ADVAPI32!CryptDestroyHash` at `0x14008428f`
- `ADVAPI32!CryptDestroyHash` at `0x1400842c3`
- `ADVAPI32!CryptDestroyHash` at `0x1400842f7`
- `ADVAPI32!CryptDestroyKey` at `0x140083fe9`
- `ADVAPI32!CryptDestroyKey` at `0x1400840b1`
- `ADVAPI32!CryptDestroyKey` at `0x14008413a`
- `ADVAPI32!CryptDestroyKey` at `0x140084262`
- `ADVAPI32!CryptDestroyKey` at `0x14008429b`
- `ADVAPI32!CryptDestroyKey` at `0x1400842cf`
- `ADVAPI32!CryptDestroyKey` at `0x140084303`
- `ADVAPI32!CryptDestroyKey` at `0x140083f7e`
- `ADVAPI32!CryptDestroyKey` at `0x140083fe9`
- `ADVAPI32!CryptDestroyKey` at `0x1400840b1`
- `ADVAPI32!CryptDestroyKey` at `0x14008413a`
- `ADVAPI32!CryptDestroyKey` at `0x140084262`
- `ADVAPI32!CryptDestroyKey` at `0x14008429b`
- `ADVAPI32!CryptDestroyKey` at `0x1400842cf`
- `ADVAPI32!CryptDestroyKey` at `0x140084303`
- `ADVAPI32!CryptAcquireContextA` at `0x140083ef7`
- `ADVAPI32!CryptAcquireContextA` at `0x140083ef7`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
bool __fastcall VerifySignature_WinCrypt(__int64 *a1, __int64 a2, __int64 a3)
{
  const CERT_CONTEXT *CertificateContext; // rcx
  DWORD LastError; // eax
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v12; // eax
  __int64 v13; // rdi
  __int64 v14; // rbx
  unsigned __int64 v15; // rsi
  size_t v16; // rcx
  BYTE *v17; // r8
  BOOL v18; // ebx
  DWORD v19; // eax
  bool v20; // bl
  __int64 v21; // rax
  const std::exception *v22; // [rsp+30h] [rbp-B8h] BYREF
  char v23; // [rsp+38h] [rbp-B0h]
  HCRYPTPROV *p_phProv; // [rsp+40h] [rbp-A8h]
  PCCERT_CONTEXT pCertContext; // [rsp+48h] [rbp-A0h] BYREF
  HCRYPTPROV phProv; // [rsp+50h] [rbp-98h] BYREF
  HCRYPTHASH phHash; // [rsp+58h] [rbp-90h] BYREF
  HCRYPTKEY phKey; // [rsp+60h] [rbp-88h] BYREF
  BYTE *pbSignature[2]; // [rsp+68h] [rbp-80h] BYREF
  BYTE *v30; // [rsp+78h] [rbp-70h]
  __int64 v31; // [rsp+80h] [rbp-68h]
  PCCERT_CONTEXT *p_pCertContext; // [rsp+88h] [rbp-60h]
  BOOL (__stdcall *v33)(PCCERT_CONTEXT); // [rsp+90h] [rbp-58h]
  __int64 v34; // [rsp+98h] [rbp-50h]
  HCRYPTKEY *p_phKey; // [rsp+A0h] [rbp-48h]
  BOOL (__stdcall *v36)(HCRYPTKEY); // [rsp+A8h] [rbp-40h]
  __int64 v37; // [rsp+B0h] [rbp-38h]
  HCRYPTHASH *p_phHash; // [rsp+B8h] [rbp-30h]
  BOOL (__stdcall *v39)(HCRYPTHASH); // [rsp+C0h] [rbp-28h]

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 54, WPP_fab25902b95537784195265cb25f9216_Traceguids);
  CertificateContext = CertCreateCertificateContext(0x10001u, *(const BYTE **)a2, *(_DWORD *)(a2 + 8) - *(_DWORD *)a2);
  pCertContext = CertificateContext;
  v31 = 0;
  p_pCertContext = &pCertContext;
  v33 = CertFreeCertificateContext;
  if ( !CertificateContext )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 55, WPP_fab25902b95537784195265cb25f9216_Traceguids, LastError);
      CertificateContext = pCertContext;
    }
    CertFreeCertificateContext(CertificateContext);
    return 0;
  }
  phProv = 0;
  v23 = 0;
  p_phProv = &phProv;
  if ( !CryptAcquireContextA(&phProv, 0, 0, 0x18u, 0xF0000040) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v8 = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 56, WPP_fab25902b95537784195265cb25f9216_Traceguids, v8);
    }
    CryptReleaseContext(phProv, 0);
    CertFreeCertificateContext(pCertContext);
    return 0;
  }
  phKey = 0;
  v34 = 0;
  p_phKey = &phKey;
  v36 = CryptDestroyKey;
  if ( !CryptImportPublicKeyInfo(phProv, 0x10001u, &pCertContext->pCertInfo->SubjectPublicKeyInfo, &phKey) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v9 = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 57, WPP_fab25902b95537784195265cb25f9216_Traceguids, v9);
    }
    CryptDestroyKey(phKey);
    CryptReleaseContext(phProv, 0);
    CertFreeCertificateContext(pCertContext);
    return 0;
  }
  phHash = 0;
  v37 = 0;
  p_phHash = &phHash;
  v39 = CryptDestroyHash;
  if ( !CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v10 = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 58, WPP_fab25902b95537784195265cb25f9216_Traceguids, v10);
    }
LABEL_23:
    CryptDestroyHash(phHash);
    CryptDestroyKey(phKey);
    CryptReleaseContext(phProv, 0);
    CertFreeCertificateContext(pCertContext);
    return 0;
  }
  if ( !CryptHashData(phHash, *(const BYTE **)a3, *(_DWORD *)(a3 + 8) - *(_DWORD *)a3, 0) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v12 = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 59, WPP_fab25902b95537784195265cb25f9216_Traceguids, v12);
    }
    goto LABEL_23;
  }
  try
  {
    v13 = *a1;
    v14 = a1[1];
    *(_OWORD *)pbSignature = 0;
    v30 = 0;
    v15 = v14 - v13;
    if ( v14 == v13 )
    {
      LODWORD(v17) = pbSignature[1];
    }
    else
    {
      if ( v15 > 0x7FFFFFFFFFFFFFFFLL )
        std::vector<CsProtocol::Device>::_Xlength();
      _mm_lfence();
      v16 = v14 - v13;
      if ( v15 < 0x1000 )
        v17 = (BYTE *)operator new(v16);
      else
        v17 = (BYTE *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v16);
      pbSignature[0] = v17;
      pbSignature[1] = v17;
      v30 = &v17[v15];
      while ( v14 != v13 )
        *v17++ = *(_BYTE *)--v14;
      pbSignature[1] = v17;
    }
    v18 = CryptVerifySignatureW(phHash, pbSignature[0], (_DWORD)v17 - LODWORD(pbSignature[0]), phKey, 0, 0);
    if ( !v18 )
    {
      v19 = GetLastError();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          (unsigned int)(v18 + 60),
          WPP_fab25902b95537784195265cb25f9216_Traceguids,
          v19);
    }
    v20 = v18;
    std::vector<unsigned char>::_Tidy(pbSignature);
  }
  catch ( std::bad_alloc )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 61, WPP_fab25902b95537784195265cb25f9216_Traceguids);
    CryptDestroyHash(phHash);
    CryptDestroyKey(phKey);
    CryptReleaseContext(phProv, 0);
    CertFreeCertificateContext(pCertContext);
    return 0;
  }
  catch ( const std::exception *v22 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v21 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v22 + 8LL))(v22);
      WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 62, WPP_fab25902b95537784195265cb25f9216_Traceguids, v21);
    }
    CryptDestroyHash(phHash);
    CryptDestroyKey(phKey);
    CryptReleaseContext(phProv, 0);
    CertFreeCertificateContext(pCertContext);
    return 0;
  }
  catch ( ... )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 63, WPP_fab25902b95537784195265cb25f9216_Traceguids);
    CryptDestroyHash(phHash);
    CryptDestroyKey(phKey);
    CryptReleaseContext(phProv, 0);
    CertFreeCertificateContext(pCertContext);
    return 0;
  }
  CryptDestroyHash(phHash);
  CryptDestroyKey(phKey);
  CryptReleaseContext(phProv, 0);
  CertFreeCertificateContext(pCertContext);
  return v20;
}

```

## disassembly

```asm
0x140083dc4  mov     [rsp+arg_0], rbx
0x140083dc9  mov     [rsp+arg_18], rsi
0x140083dce  push    rdi
0x140083dcf  push    r12
0x140083dd1  push    r14
0x140083dd3  sub     rsp, 0D0h
0x140083dda  mov     rax, cs:__security_cookie
0x140083de1  xor     rax, rsp
0x140083de4  mov     [rsp+0E8h+var_20], rax
0x140083dec  mov     rdi, r8
0x140083def  mov     rsi, rdx
0x140083df2  mov     rbx, rcx
0x140083df5  lea     r12, WPP_GLOBAL_Control
0x140083dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140083e03  cmp     rcx, r12
0x140083e06  jz      short loc_140083E28
0x140083e08  test    byte ptr [rcx+1Ch], 4
0x140083e0c  jz      short loc_140083E28
0x140083e0e  mov     edx, 36h ; '6'
0x140083e13  lea     r14, WPP_fab25902b95537784195265cb25f9216_Traceguids
0x140083e1a  mov     r8, r14
0x140083e1d  mov     rcx, [rcx+10h]
0x140083e21  call    WPP_SF_
0x140083e26  jmp     short loc_140083E2F
0x140083e28  lea     r14, WPP_fab25902b95537784195265cb25f9216_Traceguids
0x140083e2f  mov     r8d, [rsi+8]
0x140083e33  sub     r8d, [rsi]; cbCertEncoded
0x140083e36  mov     rdx, [rsi]; pbCertEncoded
0x140083e39  mov     esi, 10001h
0x140083e3e  mov     ecx, esi; dwCertEncodingType
0x140083e40  call    cs:__imp_CertCreateCertificateContext
0x140083e46  mov     rcx, rax
0x140083e49  mov     [rsp+0E8h+pCertContext], rax
0x140083e4e  xorps   xmm0, xmm0
0x140083e51  xor     eax, eax
0x140083e53  movups  [rsp+0E8h+var_68], xmm0
0x140083e5b  mov     byte ptr [rsp+0E8h+var_68], al
0x140083e62  lea     rax, [rsp+0E8h+pCertContext]
0x140083e67  mov     qword ptr [rsp+0E8h+var_68+8], rax
0x140083e6f  mov     rax, cs:__imp_CertFreeCertificateContext
0x140083e76  mov     [rsp+0E8h+var_58], rax
0x140083e7e  test    rcx, rcx
0x140083e81  jnz     short loc_140083EC7
0x140083e83  mov     rax, cs:WPP_GLOBAL_Control
0x140083e8a  cmp     rax, r12
0x140083e8d  jz      short loc_140083EBB
0x140083e8f  test    byte ptr [rax+1Ch], 1
0x140083e93  jz      short loc_140083EBB
0x140083e95  call    cs:__imp_GetLastError
0x140083e9b  mov     edx, 37h ; '7'
0x140083ea0  mov     r9d, eax
0x140083ea3  mov     r8, r14
0x140083ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x140083ead  mov     rcx, [rcx+10h]
0x140083eb1  call    WPP_SF_d
0x140083eb6  mov     rcx, [rsp+0E8h+pCertContext]; pCertContext
0x140083ebb  call    cs:__imp_CertFreeCertificateContext
0x140083ec1  nop
0x140083ec2  jmp     loc_140084324
0x140083ec7  mov     [rsp+0E8h+phProv], 0
0x140083ed0  mov     [rsp+0E8h+var_B0], 0
0x140083ed5  lea     rax, [rsp+0E8h+phProv]
0x140083eda  mov     [rsp+0E8h+var_A8], rax
0x140083edf  mov     [rsp+0E8h+dwFlags], 0F0000040h; dwFlags
0x140083ee7  mov     r9d, 18h; dwProvType
0x140083eed  xor     r8d, r8d; szProvider
0x140083ef0  xor     edx, edx; szContainer
0x140083ef2  lea     rcx, [rsp+0E8h+phProv]; phProv
0x140083ef7  call    cs:__imp_CryptAcquireContextA
0x140083efd  test    eax, eax
0x140083eff  jnz     short loc_140083F54
0x140083f01  mov     rax, cs:WPP_GLOBAL_Control
0x140083f08  cmp     rax, r12
0x140083f0b  jz      short loc_140083F35
0x140083f0d  test    byte ptr [rax+1Ch], 1
0x140083f11  jz      short loc_140083F35
0x140083f13  call    cs:__imp_GetLastError
0x140083f19  mov     edx, 38h ; '8'
0x140083f1e  mov     r9d, eax
0x140083f21  mov     r8, r14
0x140083f24  mov     rcx, cs:WPP_GLOBAL_Control
0x140083f2b  mov     rcx, [rcx+10h]
0x140083f2f  call    WPP_SF_d
0x140083f34  nop
0x140083f35  xor     edx, edx; dwFlags
0x140083f37  mov     rcx, [rsp+0E8h+phProv]; hProv
0x140083f3c  call    cs:__imp_CryptReleaseContext
0x140083f42  nop
0x140083f43  mov     rcx, [rsp+0E8h+pCertContext]; pCertContext
0x140083f48  call    cs:__imp_CertFreeCertificateContext
0x140083f4e  nop
0x140083f4f  jmp     loc_140084324
0x140083f54  mov     [rsp+0E8h+phKey], 0
0x140083f5d  xorps   xmm0, xmm0
0x140083f60  xor     eax, eax
0x140083f62  movups  [rsp+0E8h+var_50], xmm0
0x140083f6a  mov     byte ptr [rsp+0E8h+var_50], al
0x140083f71  lea     rax, [rsp+0E8h+phKey]
0x140083f76  mov     qword ptr [rsp+0E8h+var_50+8], rax
0x140083f7e  mov     rax, cs:__imp_CryptDestroyKey
0x140083f85  mov     [rsp+0E8h+var_40], rax
0x140083f8d  mov     rax, [rsp+0E8h+pCertContext]
0x140083f92  mov     r8, [rax+18h]
0x140083f96  add     r8, 60h ; '`'; pInfo
0x140083f9a  lea     r9, [rsp+0E8h+phKey]; phKey
0x140083f9f  mov     edx, esi; dwCertEncodingType
0x140083fa1  mov     rcx, [rsp+0E8h+phProv]; hCryptProv
0x140083fa6  call    cs:__imp_CryptImportPublicKeyInfo
0x140083fac  test    eax, eax
0x140083fae  jnz     short loc_14008400F
0x140083fb0  mov     rax, cs:WPP_GLOBAL_Control
0x140083fb7  cmp     rax, r12
0x140083fba  jz      short loc_140083FE4
0x140083fbc  test    byte ptr [rax+1Ch], 1
0x140083fc0  jz      short loc_140083FE4
0x140083fc2  call    cs:__imp_GetLastError
0x140083fc8  mov     edx, 39h ; '9'
0x140083fcd  mov     r9d, eax
0x140083fd0  mov     r8, r14
0x140083fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140083fda  mov     rcx, [rcx+10h]
0x140083fde  call    WPP_SF_d
0x140083fe3  nop
0x140083fe4  mov     rcx, [rsp+0E8h+phKey]; hKey
0x140083fe9  call    cs:__imp_CryptDestroyKey
0x140083fef  nop
0x140083ff0  xor     edx, edx; dwFlags
0x140083ff2  mov     rcx, [rsp+0E8h+phProv]; hProv
0x140083ff7  call    cs:__imp_CryptReleaseContext
0x140083ffd  nop
0x140083ffe  mov     rcx, [rsp+0E8h+pCertContext]; pCertContext
0x140084003  call    cs:__imp_CertFreeCertificateContext
0x140084009  nop
0x14008400a  jmp     loc_140084324
0x14008400f  mov     [rsp+0E8h+phHash], 0
0x140084018  xorps   xmm0, xmm0
0x14008401b  xor     eax, eax
0x14008401d  movups  [rsp+0E8h+var_38], xmm0
0x140084025  mov     byte ptr [rsp+0E8h+var_38], al
0x14008402c  lea     rax, [rsp+0E8h+phHash]
0x140084031  mov     qword ptr [rsp+0E8h+var_38+8], rax
0x140084039  mov     rax, cs:__imp_CryptDestroyHash
0x140084040  mov     [rsp+0E8h+var_28], rax
0x140084048  lea     rax, [rsp+0E8h+phHash]
0x14008404d  mov     qword ptr [rsp+0E8h+dwFlags], rax; phHash
0x140084052  xor     r9d, r9d; dwFlags
0x140084055  xor     r8d, r8d; hKey
0x140084058  mov     edx, 800Ch; Algid
0x14008405d  mov     rcx, [rsp+0E8h+phProv]; hProv
0x140084062  call    cs:__imp_CryptCreateHash
0x140084068  test    eax, eax
0x14008406a  jnz     short loc_1400840D9
0x14008406c  mov     rax, cs:WPP_GLOBAL_Control
0x140084073  cmp     rax, r12
0x140084076  jz      short loc_1400840A0
0x140084078  test    byte ptr [rax+1Ch], 1
0x14008407c  jz      short loc_1400840A0
0x14008407e  call    cs:__imp_GetLastError
0x140084084  mov     edx, 3Ah ; ':'
0x140084089  mov     r9d, eax
0x14008408c  mov     r8, r14
0x14008408f  mov     rcx, cs:WPP_GLOBAL_Control
0x140084096  mov     rcx, [rcx+10h]
0x14008409a  call    WPP_SF_d
0x14008409f  nop
0x1400840a0  mov     rcx, [rsp+0E8h+phHash]; hHash
0x1400840a5  call    cs:__imp_CryptDestroyHash
0x1400840ab  nop
0x1400840ac  mov     rcx, [rsp+0E8h+phKey]; hKey
0x1400840b1  call    cs:__imp_CryptDestroyKey
0x1400840b7  nop
0x1400840b8  xor     edx, edx; dwFlags
0x1400840ba  mov     rcx, [rsp+0E8h+phProv]; hProv
0x1400840bf  call    cs:__imp_CryptReleaseContext
0x1400840c5  nop
0x1400840c6  mov     rcx, [rsp+0E8h+pCertContext]; pCertContext
0x1400840cb  call    cs:__imp_CertFreeCertificateContext
0x1400840d1  nop
0x1400840d2  xor     al, al
0x1400840d4  jmp     loc_140084326
0x1400840d9  mov     r8d, [rdi+8]
0x1400840dd  sub     r8d, [rdi]; dwDataLen
0x1400840e0  xor     r9d, r9d; dwFlags
0x1400840e3  mov     rdx, [rdi]; pbData
0x1400840e6  mov     rcx, [rsp+0E8h+phHash]; hHash
0x1400840eb  call    cs:__imp_CryptHashData
0x1400840f1  test    eax, eax
0x1400840f3  jnz     short loc_140084162
0x1400840f5  mov     rax, cs:WPP_GLOBAL_Control
0x1400840fc  cmp     rax, r12
0x1400840ff  jz      short loc_140084129
0x140084101  test    byte ptr [rax+1Ch], 1
0x140084105  jz      short loc_140084129
0x140084107  call    cs:__imp_GetLastError
0x14008410d  mov     edx, 3Bh ; ';'
0x140084112  mov     r9d, eax
0x140084115  mov     r8, r14
0x140084118  mov     rcx, cs:WPP_GLOBAL_Control
0x14008411f  mov     rcx, [rcx+10h]
0x140084123  call    WPP_SF_d
0x140084128  nop
0x140084129  mov     rcx, [rsp+0E8h+phHash]; hHash
0x14008412e  call    cs:__imp_CryptDestroyHash
0x140084134  nop
0x140084135  mov     rcx, [rsp+0E8h+phKey]; hKey
0x14008413a  call    cs:__imp_CryptDestroyKey
0x140084140  nop
0x140084141  xor     edx, edx; dwFlags
0x140084143  mov     rcx, [rsp+0E8h+phProv]; hProv
0x140084148  call    cs:__imp_CryptReleaseContext
0x14008414e  nop
0x14008414f  mov     rcx, [rsp+0E8h+pCertContext]; pCertContext
0x140084154  call    cs:__imp_CertFreeCertificateContext
0x14008415a  nop
0x14008415b  xor     al, al
0x14008415d  jmp     loc_140084326
0x140084162  mov     rdi, [rbx]
0x140084165  mov     rbx, [rbx+8]
0x140084169  xorps   xmm0, xmm0
0x14008416c  movdqu  xmmword ptr [rsp+0E8h+pbSignature], xmm0
0x140084172  mov     [rsp+0E8h+var_70], 0
0x14008417b  mov     rsi, rbx
0x14008417e  sub     rsi, rdi
0x140084181  jz      short loc_1400841E3
0x140084183  mov     rax, 7FFFFFFFFFFFFFFFh
0x14008418d  cmp     rsi, rax
0x140084190  ja      loc_14008434F
0x140084196  lfence
0x140084199  mov     rcx, rsi; Size
0x14008419c  cmp     rsi, 1000h
0x1400841a3  jb      short loc_1400841AF
0x1400841a5  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x1400841aa  mov     r8, rax
0x1400841ad  jmp     short loc_1400841B7
0x1400841af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400841b4  mov     r8, rax
0x1400841b7  mov     [rsp+0E8h+pbSignature], r8
0x1400841bc  mov     [rsp+0E8h+pbSignature+8], r8
0x1400841c1  lea     rax, [r8+rsi]
0x1400841c5  mov     [rsp+0E8h+var_70], rax
0x1400841ca  cmp     rbx, rdi
0x1400841cd  jz      short loc_1400841DC
0x1400841cf  dec     rbx
0x1400841d2  mov     al, [rbx]
0x1400841d4  mov     [r8], al
0x1400841d7  inc     r8
0x1400841da  jmp     short loc_1400841CA
0x1400841dc  mov     [rsp+0E8h+pbSignature+8], r8
0x1400841e1  jmp     short loc_1400841E8
0x1400841e3  mov     r8, [rsp+0E8h+pbSignature+8]
0x1400841e8  mov     rdx, [rsp+0E8h+pbSignature]; pbSignature
0x1400841ed  sub     r8d, edx; dwSigLen
0x1400841f0  mov     [rsp+0E8h+var_C0], 0; dwFlags
0x1400841f8  mov     qword ptr [rsp+0E8h+dwFlags], 0; szDescription
0x140084201  mov     r9, [rsp+0E8h+phKey]; hPubKey
0x140084206  mov     rcx, [rsp+0E8h+phHash]; hHash
0x14008420b  call    cs:__imp_CryptVerifySignatureW
0x140084211  mov     ebx, eax
0x140084213  test    eax, eax
0x140084215  jnz     short loc_140084241
0x140084217  call    cs:__imp_GetLastError
0x14008421d  mov     rcx, cs:WPP_GLOBAL_Control
0x140084224  cmp     rcx, r12
0x140084227  jz      short loc_140084241
0x140084229  test    byte ptr [rcx+1Ch], 1
0x14008422d  jz      short loc_140084241
0x14008422f  lea     edx, [rbx+3Ch]
0x140084232  mov     r9d, eax
0x140084235  mov     r8, r14
0x140084238  mov     rcx, [rcx+10h]
0x14008423c  call    WPP_SF_d
0x140084241  test    ebx, ebx
0x140084243  setnz   bl
0x140084246  lea     rcx, [rsp+0E8h+pbSignature]
0x14008424b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140084250  nop
0x140084251  mov     rcx, [rsp+0E8h+phHash]; hHash
0x140084256  call    cs:__imp_CryptDestroyHash
0x14008425c  nop
0x14008425d  mov     rcx, [rsp+0E8h+phKey]; hKey
0x140084262  call    cs:__imp_CryptDestroyKey
0x140084268  nop
0x140084269  xor     edx, edx; dwFlags
0x14008426b  mov     rcx, [rsp+0E8h+phProv]; hProv
0x140084270  call    cs:__imp_CryptReleaseContext
0x140084276  nop
0x140084277  mov     rcx, [rsp+0E8h+pCertContext]; pCertContext
0x14008427c  call    cs:__imp_CertFreeCertificateContext
0x140084282  nop
0x140084283  mov     al, bl
0x140084285  jmp     loc_140084326
0x14008428a  mov     rcx, [rsp+0E8h+phHash]; hHash
0x14008428f  call    cs:__imp_CryptDestroyHash
0x140084295  nop
0x140084296  mov     rcx, [rsp+0E8h+phKey]; hKey
0x14008429b  call    cs:__imp_CryptDestroyKey
0x1400842a1  nop
0x1400842a2  xor     edx, edx; dwFlags
0x1400842a4  mov     rcx, [rsp+0E8h+phProv]; hProv
0x1400842a9  call    cs:__imp_CryptReleaseContext
  ... truncated ...
```
