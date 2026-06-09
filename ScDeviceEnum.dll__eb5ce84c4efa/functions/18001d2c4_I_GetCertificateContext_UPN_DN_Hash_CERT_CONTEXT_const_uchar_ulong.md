# I_GetCertificateContext_UPN_DN_Hash(_CERT_CONTEXT const *,uchar *,ulong *)

- ea: `0x18001d2c4`
- end: `0x18001d5c2`
- name: `?I_GetCertificateContext_UPN_DN_Hash@@YAKPEBU_CERT_CONTEXT@@PEAEPEAK@Z`
- size: `766`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, unsigned __int8 *Destination, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001cf58`

## callees

- `0x18001cf88`
- `0x18001d150`
- `0x18001d25c`
- `0x18001d27c`
- `0x18001d2c4`
- `0x18001d5c8`
- `0x18001d648`
- `0x18001d684`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001d564`
- `msvcrt!memcpy_s` at `0x18001d564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d4d8`
- `CRYPT32!CertGetNameStringW` at `0x18001d308`
- `CRYPT32!CertGetNameStringW` at `0x18001d33d`
- `CRYPT32!CertGetNameStringW` at `0x18001d3a9`
- `CRYPT32!CertGetNameStringW` at `0x18001d308`
- `CRYPT32!CertGetNameStringW` at `0x18001d33d`
- `CRYPT32!CertGetNameStringW` at `0x18001d3a9`
- `CRYPT32!CertNameToStrW` at `0x18001d374`
- `CRYPT32!CertNameToStrW` at `0x18001d374`
- `CRYPTSP!CryptGetHashParam` at `0x18001d4ce`
- `CRYPTSP!CryptGetHashParam` at `0x18001d50d`
- `CRYPTSP!CryptGetHashParam` at `0x18001d4ce`
- `CRYPTSP!CryptGetHashParam` at `0x18001d50d`
- `CRYPTSP!CryptAcquireContextW` at `0x18001d43b`
- `CRYPTSP!CryptAcquireContextW` at `0x18001d43b`
- `CRYPTSP!CryptCreateHash` at `0x18001d46e`
- `CRYPTSP!CryptCreateHash` at `0x18001d46e`
- `CRYPTSP!CryptHashData` at `0x18001d4a0`
- `CRYPTSP!CryptHashData` at `0x18001d4a0`

## pseudocode

```c
__int64 __fastcall I_GetCertificateContext_UPN_DN_Hash(
        PCCERT_CONTEXT pCertContext,
        unsigned __int8 *Destination,
        unsigned int *a3)
{
  DWORD NameStringW; // eax
  DWORD cchNameString; // esi
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD v10; // esi
  DWORD v11; // eax
  LPWSTR v12; // rsi
  DWORD LastError; // ebx
  int v14; // ebx
  rsize_t v15; // rdx
  BYTE *v17[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v18; // [rsp+40h] [rbp-29h]
  HCRYPTPROV phProv; // [rsp+48h] [rbp-21h] BYREF
  BYTE *pbData[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v21; // [rsp+60h] [rbp-9h]
  LPWSTR v22[2]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v23; // [rsp+78h] [rbp+Fh]
  LPWSTR pszNameString[2]; // [rsp+80h] [rbp+17h] BYREF
  __int64 v25; // [rsp+90h] [rbp+27h]
  char v26; // [rsp+98h] [rbp+2Fh] BYREF
  DWORD pdwDataLen; // [rsp+D0h] [rbp+67h] BYREF
  HCRYPTHASH phHash; // [rsp+E8h] [rbp+7Fh] BYREF

  *(_OWORD *)pszNameString = 0;
  v25 = 0;
  NameStringW = CertGetNameStringW(pCertContext, 8u, 0, 0, 0, 0);
  cchNameString = NameStringW;
  if ( NameStringW > 1 )
  {
    std::vector<unsigned char>::resize(pszNameString, 2LL * NameStringW);
    v8 = CertGetNameStringW(pCertContext, 8u, 0, 0, pszNameString[0], cchNameString);
    std::vector<unsigned char>::resize(pszNameString, 2LL * (v8 - 1));
  }
  *(_OWORD *)v22 = 0;
  v23 = 0;
  v9 = CertNameToStrW(pCertContext->dwCertEncodingType, &pCertContext->pCertInfo->Subject, 2u, 0, 0);
  v10 = v9;
  if ( v9 > 1 )
  {
    std::vector<unsigned char>::resize(v22, 2LL * v9);
    v11 = CertGetNameStringW(pCertContext, 4u, 0, 0, v22[0], v10);
    std::vector<unsigned char>::resize(v22, 2LL * (v11 - 1));
  }
  *(_OWORD *)pbData = 0;
  v21 = 0;
  std::vector<unsigned char>::_Construct<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>>(
    pbData,
    pszNameString[0],
    pszNameString[1]);
  v12 = v22[1];
  if ( (LPWSTR)(v21 - (unsigned __int64)pbData[0]) < (LPWSTR)((char *)pszNameString[1]
                                                            + (char *)v22[1]
                                                            - (char *)v22[0]
                                                            - (unsigned __int64)pszNameString[0]) )
    std::vector<unsigned char>::_Reallocate(pbData);
  std::vector<unsigned char>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>>(
    (unsigned int)pbData,
    (unsigned int)&v26,
    pbData[1],
    v22[0],
    (__int64)v12);
  phProv = 0;
  if ( CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000000) )
  {
    phHash = 0;
    if ( CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash)
      && CryptHashData(phHash, pbData[0], LODWORD(pbData[1]) - LODWORD(pbData[0]), 0) )
    {
      *(_OWORD *)v17 = 0;
      v18 = 0;
      pdwDataLen = 0;
      if ( CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
      {
        std::vector<unsigned char>::resize(v17, pdwDataLen);
        if ( CryptGetHashParam(phHash, 2u, v17[0], &pdwDataLen, 0) )
        {
          std::vector<unsigned char>::resize(v17, pdwDataLen);
          if ( Destination )
          {
            v14 = LODWORD(v17[1]) - LODWORD(v17[0]);
            v15 = *a3;
            if ( v15 < v17[1] - v17[0] )
            {
              std::vector<unsigned char>::_Tidy(v17);
              wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phHash);
              LastError = -2146435064;
              goto LABEL_22;
            }
            memcpy_s(Destination, v15, v17[0], v17[1] - v17[0]);
            *a3 = v14;
          }
          else
          {
            *a3 = LODWORD(v17[1]) - LODWORD(v17[0]);
          }
          std::vector<unsigned char>::_Tidy(v17);
          wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phHash);
          LastError = 0;
          goto LABEL_22;
        }
      }
      LastError = GetLastError();
      std::vector<unsigned char>::_Tidy(v17);
    }
    else
    {
      LastError = GetLastError();
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phHash);
  }
  else
  {
    LastError = GetLastError();
  }
LABEL_22:
  __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&phProv);
  std::vector<unsigned char>::_Tidy(pbData);
  std::vector<unsigned char>::_Tidy(v22);
  std::vector<unsigned char>::_Tidy(pszNameString);
  return LastError;
}

```

## disassembly

```asm
0x18001d2c4  mov     [rsp-8+arg_8], rbx
0x18001d2c9  push    rbp
0x18001d2ca  push    rsi
0x18001d2cb  push    rdi
0x18001d2cc  push    r14
0x18001d2ce  push    r15
0x18001d2d0  lea     rbp, [rsp-37h]
0x18001d2d5  sub     rsp, 0A0h
0x18001d2dc  mov     rdi, r8
0x18001d2df  mov     r14, rdx
0x18001d2e2  mov     rbx, rcx
0x18001d2e5  xorps   xmm0, xmm0
0x18001d2e8  movdqu  xmmword ptr [rbp+57h+var_40], xmm0
0x18001d2ed  xor     r15d, r15d
0x18001d2f0  mov     [rbp+57h+var_30], r15
0x18001d2f4  mov     [rsp+0C0h+cchNameString], r15d; cchNameString
0x18001d2f9  mov     [rsp+0C0h+pszNameString], r15; pszNameString
0x18001d2fe  xor     r9d, r9d; pvTypePara
0x18001d301  xor     r8d, r8d; dwFlags
0x18001d304  lea     edx, [r15+8]; dwType
0x18001d308  call    cs:__imp_CertGetNameStringW
0x18001d30e  mov     esi, eax
0x18001d310  cmp     eax, 1
0x18001d313  jbe     short loc_18001D352
0x18001d315  mov     edx, esi
0x18001d317  add     rdx, rdx
0x18001d31a  lea     rcx, [rbp+57h+var_40]
0x18001d31e  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18001d323  mov     [rsp+0C0h+cchNameString], esi; cchNameString
0x18001d327  mov     rax, [rbp+57h+var_40]
0x18001d32b  mov     [rsp+0C0h+pszNameString], rax; pszNameString
0x18001d330  xor     r9d, r9d; pvTypePara
0x18001d333  xor     r8d, r8d; dwFlags
0x18001d336  lea     edx, [r15+8]; dwType
0x18001d33a  mov     rcx, rbx; pCertContext
0x18001d33d  call    cs:__imp_CertGetNameStringW
0x18001d343  lea     edx, [rax-1]
0x18001d346  add     rdx, rdx
0x18001d349  lea     rcx, [rbp+57h+var_40]
0x18001d34d  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18001d352  xorps   xmm0, xmm0
0x18001d355  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x18001d35a  mov     [rbp+57h+var_48], r15
0x18001d35e  mov     rdx, [rbx+18h]
0x18001d362  add     rdx, 50h ; 'P'; pName
0x18001d366  mov     dword ptr [rsp+0C0h+pszNameString], r15d; csz
0x18001d36b  xor     r9d, r9d; psz
0x18001d36e  lea     r8d, [r9+2]; dwStrType
0x18001d372  mov     ecx, [rbx]; dwCertEncodingType
0x18001d374  call    cs:__imp_CertNameToStrW
0x18001d37a  mov     esi, eax
0x18001d37c  cmp     eax, 1
0x18001d37f  jbe     short loc_18001D3BE
0x18001d381  mov     edx, esi
0x18001d383  add     rdx, rdx
0x18001d386  lea     rcx, [rbp+57h+var_58]
0x18001d38a  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18001d38f  mov     [rsp+0C0h+cchNameString], esi; cchNameString
0x18001d393  mov     rax, [rbp+57h+var_58]
0x18001d397  mov     [rsp+0C0h+pszNameString], rax; pszNameString
0x18001d39c  xor     r9d, r9d; pvTypePara
0x18001d39f  xor     r8d, r8d; dwFlags
0x18001d3a2  lea     edx, [r9+4]; dwType
0x18001d3a6  mov     rcx, rbx; pCertContext
0x18001d3a9  call    cs:__imp_CertGetNameStringW
0x18001d3af  lea     edx, [rax-1]
0x18001d3b2  add     rdx, rdx
0x18001d3b5  lea     rcx, [rbp+57h+var_58]
0x18001d3b9  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18001d3be  xorps   xmm0, xmm0
0x18001d3c1  movdqu  xmmword ptr [rbp+57h+pbData], xmm0
0x18001d3c6  mov     [rbp+57h+var_60], r15
0x18001d3ca  mov     r8, [rbp+57h+var_40+8]
0x18001d3ce  mov     rdx, [rbp+57h+var_40]
0x18001d3d2  lea     rcx, [rbp+57h+pbData]
0x18001d3d6  call    ??$_Construct@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@@?$vector@EV?$allocator@E@std@@@std@@QEAAXV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0@Z; std::vector<uchar>::_Construct<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>)
0x18001d3db  nop
0x18001d3dc  mov     rsi, [rbp+57h+var_58+8]
0x18001d3e0  mov     rdx, rsi
0x18001d3e3  sub     rdx, [rbp+57h+var_58]
0x18001d3e7  sub     rdx, [rbp+57h+var_40]
0x18001d3eb  add     rdx, [rbp+57h+var_40+8]
0x18001d3ef  mov     rax, [rbp+57h+var_60]
0x18001d3f3  sub     rax, [rbp+57h+pbData]
0x18001d3f7  cmp     rax, rdx
0x18001d3fa  jnb     short loc_18001D405
0x18001d3fc  lea     rcx, [rbp+57h+pbData]
0x18001d400  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x18001d405  mov     [rsp+0C0h+pszNameString], rsi
0x18001d40a  mov     r9, [rbp+57h+var_58]
0x18001d40e  mov     r8, [rbp+57h+pbData+8]
0x18001d412  lea     rdx, [rbp+57h+var_28]
0x18001d416  lea     rcx, [rbp+57h+pbData]
0x18001d41a  call    ??$insert@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V21@1@Z; std::vector<uchar>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>)
0x18001d41f  nop
0x18001d420  mov     [rbp+57h+phProv], r15
0x18001d424  mov     dword ptr [rsp+0C0h+pszNameString], 0F0000000h; dwFlags
0x18001d42c  mov     r9d, 18h; dwProvType
0x18001d432  xor     r8d, r8d; szProvider
0x18001d435  xor     edx, edx; szContainer
0x18001d437  lea     rcx, [rbp+57h+phProv]; phProv
0x18001d43b  call    cs:__imp_CryptAcquireContextW
0x18001d441  test    eax, eax
0x18001d443  jnz     short loc_18001D452
0x18001d445  call    cs:__imp_GetLastError
0x18001d44b  mov     ebx, eax
0x18001d44d  jmp     loc_18001D582
0x18001d452  mov     [rbp+57h+phHash], r15
0x18001d456  lea     rax, [rbp+57h+phHash]
0x18001d45a  mov     [rsp+0C0h+pszNameString], rax; phHash
0x18001d45f  xor     r9d, r9d; dwFlags
0x18001d462  xor     r8d, r8d; hKey
0x18001d465  mov     edx, 800Ch; Algid
0x18001d46a  mov     rcx, [rbp+57h+phProv]; hProv
0x18001d46e  call    cs:__imp_CryptCreateHash
0x18001d474  test    eax, eax
0x18001d476  jnz     short loc_18001D48E
0x18001d478  call    cs:__imp_GetLastError
0x18001d47e  mov     ebx, eax
0x18001d480  lea     rcx, [rbp+57h+phHash]
0x18001d484  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyHash@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001d489  jmp     loc_18001D582
0x18001d48e  mov     r8d, dword ptr [rbp+57h+pbData+8]
0x18001d492  mov     rdx, [rbp+57h+pbData]; pbData
0x18001d496  sub     r8d, edx; dwDataLen
0x18001d499  xor     r9d, r9d; dwFlags
0x18001d49c  mov     rcx, [rbp+57h+phHash]; hHash
0x18001d4a0  call    cs:__imp_CryptHashData
0x18001d4a6  test    eax, eax
0x18001d4a8  jz      short loc_18001D478
0x18001d4aa  xorps   xmm0, xmm0
0x18001d4ad  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x18001d4b2  mov     [rbp+57h+var_80], r15
0x18001d4b6  mov     [rbp+57h+pdwDataLen], r15d
0x18001d4ba  mov     dword ptr [rsp+0C0h+pszNameString], r15d; dwFlags
0x18001d4bf  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18001d4c3  xor     r8d, r8d; pbData
0x18001d4c6  lea     edx, [r8+2]; dwParam
0x18001d4ca  mov     rcx, [rbp+57h+phHash]; hHash
0x18001d4ce  call    cs:__imp_CryptGetHashParam
0x18001d4d4  test    eax, eax
0x18001d4d6  jnz     short loc_18001D4EB
0x18001d4d8  call    cs:__imp_GetLastError
0x18001d4de  mov     ebx, eax
0x18001d4e0  lea     rcx, [rbp+57h+var_90]
0x18001d4e4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001d4e9  jmp     short loc_18001D480
0x18001d4eb  mov     edx, [rbp+57h+pdwDataLen]
0x18001d4ee  lea     rcx, [rbp+57h+var_90]
0x18001d4f2  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18001d4f7  mov     dword ptr [rsp+0C0h+pszNameString], r15d; dwFlags
0x18001d4fc  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18001d500  mov     r8, [rbp+57h+var_90]; pbData
0x18001d504  mov     edx, 2; dwParam
0x18001d509  mov     rcx, [rbp+57h+phHash]; hHash
0x18001d50d  call    cs:__imp_CryptGetHashParam
0x18001d513  test    eax, eax
0x18001d515  jz      short loc_18001D4D8
0x18001d517  mov     edx, [rbp+57h+pdwDataLen]
0x18001d51a  lea     rcx, [rbp+57h+var_90]
0x18001d51e  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18001d523  test    r14, r14
0x18001d526  jnz     short loc_18001D532
0x18001d528  mov     eax, dword ptr [rbp+57h+var_90+8]
0x18001d52b  sub     eax, dword ptr [rbp+57h+var_90]
0x18001d52e  mov     [rdi], eax
0x18001d530  jmp     short loc_18001D56C
0x18001d532  mov     rbx, [rbp+57h+var_90+8]
0x18001d536  mov     r8, [rbp+57h+var_90]; Source
0x18001d53a  sub     rbx, r8
0x18001d53d  mov     edx, [rdi]; DestinationSize
0x18001d53f  cmp     rdx, rbx
0x18001d542  jnb     short loc_18001D55E
0x18001d544  lea     rcx, [rbp+57h+var_90]
0x18001d548  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001d54d  nop
0x18001d54e  lea     rcx, [rbp+57h+phHash]
0x18001d552  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyHash@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001d557  mov     ebx, 80100008h
0x18001d55c  jmp     short loc_18001D582
0x18001d55e  mov     r9, rbx; SourceSize
0x18001d561  mov     rcx, r14; Destination
0x18001d564  call    cs:__imp_memcpy_s
0x18001d56a  mov     [rdi], ebx
0x18001d56c  lea     rcx, [rbp+57h+var_90]
0x18001d570  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001d575  nop
0x18001d576  lea     rcx, [rbp+57h+phHash]
0x18001d57a  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyHash@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyHash(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001d57f  mov     ebx, r15d
0x18001d582  lea     rcx, [rbp+57h+phProv]
0x18001d586  call    ??1?$unique_storage@U?$resource_policy@_KP6AX_K@_E$1?CryptReleaseContextNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d58b  nop
0x18001d58c  lea     rcx, [rbp+57h+pbData]
0x18001d590  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001d595  nop
0x18001d596  lea     rcx, [rbp+57h+var_58]
0x18001d59a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001d59f  nop
0x18001d5a0  lea     rcx, [rbp+57h+var_40]
0x18001d5a4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001d5a9  mov     eax, ebx
0x18001d5ab  mov     rbx, [rsp+0C0h+arg_8]
0x18001d5b3  add     rsp, 0A0h
0x18001d5ba  pop     r15
0x18001d5bc  pop     r14
0x18001d5be  pop     rdi
0x18001d5bf  pop     rsi
0x18001d5c0  pop     rbp
0x18001d5c1  retn
```
