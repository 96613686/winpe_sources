# WSTrustCertificateTokenRequest::CryptXMLSignInternal(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,CryptoHelper::CertificateInfo const &,ushort const *,ushort const *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18005cec8`
- end: `0x18005d364`
- name: `?CryptXMLSignInternal@WSTrustCertificateTokenRequest@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBUCertificateInfo@CryptoHelper@@PEBG22AEAV23@@Z`
- size: `1180`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, __int64, HCRYPTXML phReference, HCRYPTXML, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005d5f4`

## callees

- `0x1800067f4`
- `0x1800090d0`
- `0x18001502c`
- `0x1800492bc`
- `0x18004b1b4`
- `0x18005c894`
- `0x18005cec8`
- `0x180071e14`
- `0x180076c3c`

## import_xrefs

- `CRYPT32!CryptFindOIDInfo` at `0x18005cf8b`
- `CRYPT32!CryptFindOIDInfo` at `0x18005cf8b`
- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x18005cf44`
- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x18005cfbb`
- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x18005cf44`
- `CRYPTXML!CryptXmlFindAlgorithmInfo` at `0x18005cfbb`
- `CRYPTXML!CryptXmlOpenToEncode` at `0x18005d08f`
- `CRYPTXML!CryptXmlOpenToEncode` at `0x18005d08f`
- `CRYPTXML!CryptXmlCreateReference` at `0x18005d0f5`
- `CRYPTXML!CryptXmlCreateReference` at `0x18005d15b`
- `CRYPTXML!CryptXmlCreateReference` at `0x18005d0f5`
- `CRYPTXML!CryptXmlCreateReference` at `0x18005d15b`
- `CRYPTXML!CryptXmlClose` at `0x18005d328`
- `CRYPTXML!CryptXmlClose` at `0x18005d328`
- `CRYPTXML!CryptXmlEncode` at `0x18005d207`
- `CRYPTXML!CryptXmlEncode` at `0x18005d207`
- `CRYPTXML!CryptXmlSign` at `0x18005d1b7`
- `CRYPTXML!CryptXmlSign` at `0x18005d1b7`

## string_xrefs

- `0x18005d2ae`: `http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3`
- `0x18005d022`: `http://www.w3.org/2001/10/xml-exc-c14n#`
- `0x18005cef3`: `/Envelope/Header/Security`
- `0x18005d2b5`: `<KeyInfo><o:SecurityTokenReference><o:Reference ValueType='%s' URI='#uuid-%s'/></o:SecurityTokenReference></KeyInfo>`

## pseudocode

```c
__int64 __fastcall WSTrustCertificateTokenRequest::CryptXMLSignInternal(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        HCRYPTXML phReference,
        HCRYPTXML a6,
        __int64 a7)
{
  const CRYPT_XML_ALGORITHM_INFO *AlgorithmInfo; // rax
  const WCHAR *wszAlgorithmURI; // rdi
  __int64 v12; // rdx
  const WCHAR *v13; // rbx
  PCCRYPT_OID_INFO OIDInfo; // rax
  const CRYPT_XML_ALGORITHM_INFO *v15; // rax
  __int64 v16; // rax
  const CRYPT_XML_BLOB *pEncoded; // rcx
  HRESULT v18; // ebx
  __int64 v19; // rsi
  int v20; // r14d
  ULONG cProperty[2]; // [rsp+28h] [rbp-C1h]
  HCRYPTXML *phSignature; // [rsp+38h] [rbp-B1h]
  const wchar_t *pvFindBy; // [rsp+58h] [rbp-91h] BYREF
  __int64 v25; // [rsp+60h] [rbp-89h]
  const wchar_t *v26; // [rsp+68h] [rbp-81h] BYREF
  LPCCH pvCallbackState; // [rsp+70h] [rbp-79h] BYREF
  int cbMultiByte[2]; // [rsp+78h] [rbp-71h]
  __int64 v29; // [rsp+80h] [rbp-69h]
  int v30; // [rsp+88h] [rbp-61h]
  CRYPT_XML_ALGORITHM pDigestMethod; // [rsp+90h] [rbp-59h] BYREF
  CRYPT_XML_PROPERTY rgProperty; // [rsp+B0h] [rbp-39h] BYREF
  CRYPT_XML_ALGORITHM pCanonicalization; // [rsp+C8h] [rbp-21h] BYREF
  CRYPT_XML_ALGORITHM pSignatureMethod; // [rsp+E8h] [rbp-1h] BYREF
  __int64 v35; // [rsp+148h] [rbp+5Fh] BYREF
  HCRYPTXML hCryptXml; // [rsp+150h] [rbp+67h] BYREF

  v26 = L"/Envelope/Header/Security";
  hCryptXml = 0;
  pvCallbackState = 0;
  *(_QWORD *)cbMultiByte = 0;
  v29 = 0;
  v30 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
  AlgorithmInfo = CryptXmlFindAlgorithmInfo(3u, L"SHA1", 1u, 0);
  if ( AlgorithmInfo )
    wszAlgorithmURI = AlgorithmInfo->wszAlgorithmURI;
  else
    wszAlgorithmURI = 0;
  v12 = *(_QWORD *)(**(_QWORD **)(**(_QWORD **)(*(_QWORD *)a3 + 16LL) + 16LL) + 8LL);
  if ( v12 )
  {
    OIDInfo = CryptFindOIDInfo(1u, *(void **)(*(_QWORD *)(v12 + 24) + 96LL), 3u);
    v13 = 0;
    if ( OIDInfo )
    {
      pvFindBy = L"SHA1";
      v25 = *(_QWORD *)&OIDInfo[1].cbSize;
      v15 = CryptXmlFindAlgorithmInfo(4u, &pvFindBy, 2u, 0);
      if ( v15 )
      {
        v15->dwSignFlags |= 0x40u;
        v13 = v15->wszAlgorithmURI;
      }
    }
  }
  else
  {
    v13 = 0;
  }
  if ( wszAlgorithmURI && v13 )
  {
    phReference = 0;
    a6 = 0;
    LODWORD(pvFindBy) = 2;
    v16 = *a2;
    HIDWORD(pvFindBy) = 2 * *(_DWORD *)(*a2 - 16);
    v25 = v16;
    *(_QWORD *)&pSignatureMethod.cbSize = 32;
    pSignatureMethod.wszAlgorithm = v13;
    pSignatureMethod.Encoded = 0;
    *(_QWORD *)&pCanonicalization.cbSize = 32;
    pCanonicalization.wszAlgorithm = L"http://www.w3.org/2001/10/xml-exc-c14n#";
    pCanonicalization.Encoded = 0;
    *(_QWORD *)&pDigestMethod.cbSize = 32;
    pDigestMethod.wszAlgorithm = wszAlgorithmURI;
    pDigestMethod.Encoded = 0;
    rgProperty.dwPropId = CRYPT_XML_PROPERTY_SIGNATURE_LOCATION;
    rgProperty.pvValue = &v26;
    rgProperty.cbValue = 8;
    pEncoded = (const CRYPT_XML_BLOB *)&pvFindBy;
    if ( !HIDWORD(pvFindBy) )
      pEncoded = 0;
    v18 = CryptXmlOpenToEncode(0, 0, &base, &rgProperty, 1u, pEncoded, &hCryptXml);
    if ( v18 >= 0 )
    {
      v18 = CryptXmlCreateReference(hCryptXml, 0, 0, L"#_0", 0, &pDigestMethod, 1u, &rgTransform, &phReference);
      if ( v18 >= 0 )
      {
        v18 = CryptXmlCreateReference(hCryptXml, 0, 0, L"#_1", 0, &pDigestMethod, 1u, &rgTransform, &a6);
        if ( v18 >= 0 )
        {
          v18 = CryptXmlSign(
                  hCryptXml,
                  *(_QWORD *)(a3 + 8),
                  *(_DWORD *)(a3 + 16),
                  0,
                  CRYPT_XML_KEYINFO_SPEC_NONE,
                  0,
                  &pSignatureMethod,
                  &pCanonicalization);
          if ( v18 >= 0 )
          {
            v18 = CryptXmlEncode(
                    hCryptXml,
                    CRYPT_XML_CHARSET_UTF8,
                    &::rgProperty,
                    1u,
                    &pvCallbackState,
                    CryptXmlSignCallback);
            if ( v18 >= 0 )
            {
              v19 = a7;
              v18 = StringUtility::DecodeBytes(pvCallbackState, cbMultiByte[0]);
              if ( v18 >= 0 )
              {
                v20 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
                        v19,
                        L"</Signature>",
                        0);
                if ( v20 >= 0 )
                {
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                    &v35,
                    L"<KeyInfo><o:SecurityTokenReference><o:Reference ValueType='%s' URI='#uuid-%s'/></o:SecurityTokenRefe"
                     "rence></KeyInfo>",
                    L"http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3",
                    *(_QWORD *)(a1 + 160));
                  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Insert(
                    v19,
                    (unsigned int)v20,
                    v35);
                  goto LABEL_30;
                }
                v18 = -2147187518;
                LODWORD(phSignature) = 391;
              }
              else
              {
                LODWORD(phSignature) = 385;
              }
            }
            else
            {
              LODWORD(phSignature) = 381;
            }
          }
          else
          {
            LODWORD(phSignature) = 373;
          }
        }
        else
        {
          LODWORD(phSignature) = 362;
        }
      }
      else
      {
        LODWORD(phSignature) = 351;
      }
    }
    else
    {
      LODWORD(phSignature) = 340;
    }
  }
  else
  {
    v18 = -2147024809;
    LODWORD(phSignature) = 297;
  }
  cProperty[0] = v18;
  WPPTraceLogA(
    2,
    0,
    "%x 0x%08x %s:%u : %s:%ws",
    2,
    *(_QWORD *)cProperty,
    "wstrustcertificatetokenrequest.cpp",
    phSignature,
    "HRESULT",
    &base);
LABEL_30:
  if ( hCryptXml )
    CryptXmlClose(hCryptXml);
  ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
  ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(&pvCallbackState);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18005cec8  mov     rax, rsp
0x18005cecb  mov     [rax+8], rbx
0x18005cecf  mov     [rax+10h], rsi
0x18005ced3  mov     [rax+20h], r9
0x18005ced7  push    rbp
0x18005ced8  push    rdi
0x18005ced9  push    r13
0x18005cedb  push    r14
0x18005cedd  push    r15
0x18005cedf  lea     rbp, [rax-47h]
0x18005cee3  sub     rsp, 100h
0x18005ceea  mov     rsi, r8
0x18005ceed  mov     r14, rdx
0x18005cef0  mov     r15, rcx
0x18005cef3  lea     rax, aEnvelopeHeader; "/Envelope/Header/Security"
0x18005cefa  mov     [rsp+120h+var_C0], rax
0x18005ceff  mov     [rbp+3Fh+hCryptXml], 0
0x18005cf07  mov     [rbp+3Fh+pvCallbackState], 0
0x18005cf0f  mov     qword ptr [rbp+3Fh+cbMultiByte], 0
0x18005cf17  mov     [rbp+3Fh+var_A8], 0
0x18005cf1f  mov     [rbp+3Fh+var_A0], 0
0x18005cf26  lea     rcx, [rbp+3Fh+arg_10]; void *
0x18005cf2a  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005cf2f  nop
0x18005cf30  xor     r9d, r9d; dwFlags
0x18005cf33  lea     ebx, [r9+1]
0x18005cf37  mov     r8d, ebx; dwGroupId
0x18005cf3a  lea     rdx, aSha1; "SHA1"
0x18005cf41  lea     ecx, [rbx+2]; dwFindByType
0x18005cf44  call    cs:__imp_CryptXmlFindAlgorithmInfo
0x18005cf4a  test    rax, rax
0x18005cf4d  jz      short loc_18005CF55
0x18005cf4f  mov     rdi, [rax+8]
0x18005cf53  jmp     short loc_18005CF57
0x18005cf55  xor     edi, edi
0x18005cf57  mov     rax, [rsi]
0x18005cf5a  mov     rcx, [rax+10h]
0x18005cf5e  mov     rax, [rcx]
0x18005cf61  mov     rcx, [rax+10h]
0x18005cf65  mov     rax, [rcx]
0x18005cf68  mov     rdx, [rax+8]
0x18005cf6c  mov     r13d, 2
0x18005cf72  test    rdx, rdx
0x18005cf75  jnz     short loc_18005CF7B
0x18005cf77  xor     ebx, ebx
0x18005cf79  jmp     short loc_18005CFCE
0x18005cf7b  mov     rdx, [rdx+18h]
0x18005cf7f  mov     r8d, 3; dwGroupId
0x18005cf85  mov     rdx, [rdx+60h]; pvKey
0x18005cf89  mov     ecx, ebx; dwKeyType
0x18005cf8b  call    cs:__imp_CryptFindOIDInfo
0x18005cf91  xor     ebx, ebx
0x18005cf93  test    rax, rax
0x18005cf96  jz      short loc_18005CFCE
0x18005cf98  lea     rcx, aSha1; "SHA1"
0x18005cf9f  mov     [rsp+120h+pvFindBy], rcx
0x18005cfa4  mov     rax, [rax+30h]
0x18005cfa8  mov     [rsp+120h+var_C8], rax
0x18005cfad  xor     r9d, r9d; dwFlags
0x18005cfb0  mov     r8d, r13d; dwGroupId
0x18005cfb3  lea     rdx, [rsp+120h+pvFindBy]; pvFindBy
0x18005cfb8  lea     ecx, [rbx+4]; dwFindByType
0x18005cfbb  call    cs:__imp_CryptXmlFindAlgorithmInfo
0x18005cfc1  test    rax, rax
0x18005cfc4  jz      short loc_18005CFCE
0x18005cfc6  or      dword ptr [rax+30h], 40h
0x18005cfca  mov     rbx, [rax+8]
0x18005cfce  test    rdi, rdi
0x18005cfd1  jz      loc_18005D2D6
0x18005cfd7  test    rbx, rbx
0x18005cfda  jz      loc_18005D2D6
0x18005cfe0  mov     [rbp+3Fh+arg_20], 0
0x18005cfe8  mov     [rbp+3Fh+arg_28], 0
0x18005cff0  mov     dword ptr [rsp+120h+pvFindBy], r13d
0x18005cff5  mov     rax, [r14]
0x18005cff8  mov     edx, [rax-10h]
0x18005cffb  add     edx, edx
0x18005cffd  mov     dword ptr [rsp+120h+pvFindBy+4], edx
0x18005d001  mov     [rsp+120h+var_C8], rax
0x18005d006  mov     qword ptr [rbp+3Fh+pSignatureMethod.cbSize], 20h ; ' '
0x18005d00e  mov     [rbp+3Fh+pSignatureMethod.wszAlgorithm], rbx
0x18005d012  xorps   xmm0, xmm0
0x18005d015  movdqu  xmmword ptr [rbp+3Fh+pSignatureMethod.Encoded.dwCharset], xmm0
0x18005d01a  mov     qword ptr [rbp+3Fh+pCanonicalization.cbSize], 20h ; ' '
0x18005d022  lea     rax, aHttpWwwW3Org20_0; "http://www.w3.org/2001/10/xml-exc-c14n#"
0x18005d029  mov     [rbp+3Fh+pCanonicalization.wszAlgorithm], rax
0x18005d02d  movdqu  xmmword ptr [rbp+3Fh+pCanonicalization.Encoded.dwCharset], xmm0
0x18005d032  mov     qword ptr [rbp+3Fh+pDigestMethod.cbSize], 20h ; ' '
0x18005d03a  mov     [rbp+3Fh+pDigestMethod.wszAlgorithm], rdi
0x18005d03e  movdqu  xmmword ptr [rbp+3Fh+pDigestMethod.Encoded.dwCharset], xmm0
0x18005d043  mov     [rbp+3Fh+rgProperty.dwPropId], r13d
0x18005d047  lea     rax, [rsp+120h+var_C0]
0x18005d04c  mov     [rbp+3Fh+rgProperty.pvValue], rax
0x18005d050  mov     [rbp+3Fh+rgProperty.cbValue], 8
0x18005d057  lea     rcx, [rsp+120h+pvFindBy]
0x18005d05c  xor     eax, eax
0x18005d05e  test    edx, edx
0x18005d060  cmovz   rcx, rax
0x18005d064  lea     rax, [rbp+3Fh+hCryptXml]
0x18005d068  mov     [rsp+120h+phSignature], rax; phSignature
0x18005d06d  mov     [rsp+120h+pEncoded], rcx; pEncoded
0x18005d072  mov     r14d, 1
0x18005d078  mov     [rsp+120h+cProperty], r14d; cProperty
0x18005d07d  lea     r9, [rbp+3Fh+rgProperty]; rgProperty
0x18005d081  lea     rdi, base
0x18005d088  mov     r8, rdi; wszId
0x18005d08b  xor     edx, edx; dwFlags
0x18005d08d  xor     ecx, ecx; pConfig
0x18005d08f  call    cs:__imp_CryptXmlOpenToEncode
0x18005d095  mov     ebx, eax
0x18005d097  test    eax, eax
0x18005d099  jns     short loc_18005D0B9
0x18005d09b  mov     [rsp+120h+phReference], rdi
0x18005d0a0  lea     rax, aHresult; "HRESULT"
0x18005d0a7  mov     [rsp+120h+rgTransform], rax
0x18005d0ac  mov     dword ptr [rsp+120h+phSignature], 154h
0x18005d0b4  jmp     loc_18005D2FB
0x18005d0b9  lea     rax, [rbp+3Fh+arg_20]
0x18005d0bd  mov     [rsp+120h+phReference], rax; phReference
0x18005d0c2  lea     rax, rgTransform
0x18005d0c9  mov     [rsp+120h+rgTransform], rax; rgTransform
0x18005d0ce  mov     dword ptr [rsp+120h+phSignature], r14d; cTransform
0x18005d0d3  lea     rax, [rbp+3Fh+pDigestMethod]
0x18005d0d7  mov     [rsp+120h+pEncoded], rax; pDigestMethod
0x18005d0dc  mov     qword ptr [rsp+120h+cProperty], 0; wszType
0x18005d0e5  lea     r9, wszURI; "#_0"
0x18005d0ec  xor     r8d, r8d; wszId
0x18005d0ef  xor     edx, edx; dwFlags
0x18005d0f1  mov     rcx, [rbp+3Fh+hCryptXml]; hCryptXml
0x18005d0f5  call    cs:__imp_CryptXmlCreateReference
0x18005d0fb  mov     ebx, eax
0x18005d0fd  test    eax, eax
0x18005d0ff  jns     short loc_18005D11F
0x18005d101  mov     [rsp+120h+phReference], rdi
0x18005d106  lea     rax, aHresult; "HRESULT"
0x18005d10d  mov     [rsp+120h+rgTransform], rax
0x18005d112  mov     dword ptr [rsp+120h+phSignature], 15Fh
0x18005d11a  jmp     loc_18005D2FB
0x18005d11f  lea     rax, [rbp+3Fh+arg_28]
0x18005d123  mov     [rsp+120h+phReference], rax; phReference
0x18005d128  lea     rax, rgTransform
0x18005d12f  mov     [rsp+120h+rgTransform], rax; rgTransform
0x18005d134  mov     dword ptr [rsp+120h+phSignature], r14d; cTransform
0x18005d139  lea     rax, [rbp+3Fh+pDigestMethod]
0x18005d13d  mov     [rsp+120h+pEncoded], rax; pDigestMethod
0x18005d142  mov     qword ptr [rsp+120h+cProperty], 0; wszType
0x18005d14b  lea     r9, a1_0; "#_1"
0x18005d152  xor     r8d, r8d; wszId
0x18005d155  xor     edx, edx; dwFlags
0x18005d157  mov     rcx, [rbp+3Fh+hCryptXml]; hCryptXml
0x18005d15b  call    cs:__imp_CryptXmlCreateReference
0x18005d161  mov     ebx, eax
0x18005d163  test    eax, eax
0x18005d165  jns     short loc_18005D185
0x18005d167  mov     [rsp+120h+phReference], rdi
0x18005d16c  lea     rax, aHresult; "HRESULT"
0x18005d173  mov     [rsp+120h+rgTransform], rax
0x18005d178  mov     dword ptr [rsp+120h+phSignature], 16Ah
0x18005d180  jmp     loc_18005D2FB
0x18005d185  lea     rax, [rbp+3Fh+pCanonicalization]
0x18005d189  mov     [rsp+120h+rgTransform], rax; pCanonicalization
0x18005d18e  lea     rax, [rbp+3Fh+pSignatureMethod]
0x18005d192  mov     [rsp+120h+phSignature], rax; pSignatureMethod
0x18005d197  mov     [rsp+120h+pEncoded], 0; pvKeyInfoSpec
0x18005d1a0  mov     [rsp+120h+cProperty], 0; dwKeyInfoSpec
0x18005d1a8  xor     r9d, r9d; dwFlags
0x18005d1ab  mov     r8d, [rsi+10h]; dwKeySpec
0x18005d1af  mov     rdx, [rsi+8]; hKey
0x18005d1b3  mov     rcx, [rbp+3Fh+hCryptXml]; hSignature
0x18005d1b7  call    cs:__imp_CryptXmlSign
0x18005d1bd  mov     ebx, eax
0x18005d1bf  test    eax, eax
0x18005d1c1  jns     short loc_18005D1E1
0x18005d1c3  mov     [rsp+120h+phReference], rdi
0x18005d1c8  lea     rax, aHresult; "HRESULT"
0x18005d1cf  mov     [rsp+120h+rgTransform], rax
0x18005d1d4  mov     dword ptr [rsp+120h+phSignature], 175h
0x18005d1dc  jmp     loc_18005D2FB
0x18005d1e1  lea     rax, ?CryptXmlSignCallback@@YAJPEAXPEBEK@Z; CryptXmlSignCallback(void *,uchar const *,ulong)
0x18005d1e8  mov     [rsp+120h+pEncoded], rax; pfnWrite
0x18005d1ed  lea     rax, [rbp+3Fh+pvCallbackState]
0x18005d1f1  mov     qword ptr [rsp+120h+cProperty], rax; pvCallbackState
0x18005d1f6  mov     r9d, r14d; cProperty
0x18005d1f9  lea     r8, rgProperty; rgProperty
0x18005d200  mov     edx, r14d; dwCharset
0x18005d203  mov     rcx, [rbp+3Fh+hCryptXml]; hCryptXml
0x18005d207  call    cs:__imp_CryptXmlEncode
0x18005d20d  mov     ebx, eax
0x18005d20f  test    eax, eax
0x18005d211  jns     short loc_18005D231
0x18005d213  mov     [rsp+120h+phReference], rdi
0x18005d218  lea     rax, aHresult; "HRESULT"
0x18005d21f  mov     [rsp+120h+rgTransform], rax
0x18005d224  mov     dword ptr [rsp+120h+phSignature], 17Dh
0x18005d22c  jmp     loc_18005D2FB
0x18005d231  mov     r9d, 0FDE9h
0x18005d237  mov     rsi, [rbp+3Fh+arg_30]
0x18005d23b  mov     r8, rsi
0x18005d23e  mov     edx, [rbp+3Fh+cbMultiByte]; cbMultiByte
0x18005d241  mov     rcx, [rbp+3Fh+pvCallbackState]; lpMultiByteStr
0x18005d245  call    ?DecodeBytes@StringUtility@@SAJPEBDHAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@I@Z; StringUtility::DecodeBytes(char const *,int,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,uint)
0x18005d24a  mov     ebx, eax
0x18005d24c  test    eax, eax
0x18005d24e  jns     short loc_18005D26E
0x18005d250  mov     [rsp+120h+phReference], rdi
0x18005d255  lea     rax, aHresult; "HRESULT"
0x18005d25c  mov     [rsp+120h+rgTransform], rax
0x18005d261  mov     dword ptr [rsp+120h+phSignature], 181h
0x18005d269  jmp     loc_18005D2FB
0x18005d26e  xor     r8d, r8d
0x18005d271  lea     rdx, aSignature_0; "</Signature>"
0x18005d278  mov     rcx, rsi
0x18005d27b  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x18005d280  mov     r14d, eax
0x18005d283  test    eax, eax
0x18005d285  jns     short loc_18005D2A7
0x18005d287  mov     ebx, 800484C2h
0x18005d28c  mov     [rsp+120h+phReference], rdi
0x18005d291  lea     rax, aHresult; "HRESULT"
0x18005d298  mov     [rsp+120h+rgTransform], rax
0x18005d29d  mov     dword ptr [rsp+120h+phSignature], 187h
0x18005d2a5  jmp     short loc_18005D2FB
0x18005d2a7  mov     r9, [r15+0A0h]
0x18005d2ae  lea     r8, aHttpDocsOasisO_2; "http://docs.oasis-open.org/wss/2004/01/"...
0x18005d2b5  lea     rdx, aKeyinfoOSecuri; "<KeyInfo><o:SecurityTokenReference><o:R"...
0x18005d2bc  lea     rcx, [rbp+3Fh+arg_10]
0x18005d2c0  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18005d2c5  mov     r8, [rbp+3Fh+arg_10]
0x18005d2c9  mov     edx, r14d
0x18005d2cc  mov     rcx, rsi
0x18005d2cf  call    ?Insert@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Insert(int,ushort const *)
0x18005d2d4  jmp     short loc_18005D31F
0x18005d2d6  mov     ebx, 80070057h
0x18005d2db  lea     rdi, base
0x18005d2e2  mov     [rsp+120h+phReference], rdi
0x18005d2e7  lea     rax, aHresult; "HRESULT"
0x18005d2ee  mov     [rsp+120h+rgTransform], rax
0x18005d2f3  mov     dword ptr [rsp+120h+phSignature], 129h
0x18005d2fb  lea     rax, aOnecoreuapDsEx_44+21h; "wstrustcertificatetokenrequest.cpp"
0x18005d302  mov     [rsp+120h+pEncoded], rax
0x18005d307  mov     [rsp+120h+cProperty], ebx
0x18005d30b  mov     r9d, r13d
0x18005d30e  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18005d315  xor     edx, edx
0x18005d317  mov     ecx, r13d
0x18005d31a  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18005d31f  mov     rcx, [rbp+3Fh+hCryptXml]; hCryptXml
0x18005d323  test    rcx, rcx
0x18005d326  jz      short loc_18005D32F
0x18005d328  call    cs:__imp_CryptXmlClose
0x18005d32e  nop
0x18005d32f  mov     rcx, [rbp+3Fh+arg_10]
0x18005d333  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005d337  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18005d33c  nop
0x18005d33d  lea     rcx, [rbp+3Fh+pvCallbackState]
0x18005d341  call    ??1?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::~CAtlArray<uchar,ATL::CElementTraits<uchar>>(void)
0x18005d346  mov     eax, ebx
0x18005d348  lea     r11, [rsp+120h+var_20]
0x18005d350  mov     rbx, [r11+30h]
0x18005d354  mov     rsi, [r11+38h]
0x18005d358  mov     rsp, r11
0x18005d35b  pop     r15
0x18005d35d  pop     r14
0x18005d35f  pop     r13
0x18005d361  pop     rdi
0x18005d362  pop     rbp
0x18005d363  retn
```
