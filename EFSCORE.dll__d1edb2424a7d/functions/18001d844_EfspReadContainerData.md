# EfspReadContainerData

- ea: `0x18001d844`
- end: `0x18001dc12`
- name: `EfspReadContainerData`
- size: `974`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c93c`

## callees

- `0x1800102f0`
- `0x18001d844`
- `0x180063698`
- `0x1800d87ac`
- `0x1800dddf0`
- `0x1800ddeb0`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d92c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d959`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d92c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d959`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbc3`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18001dbb9`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18001dbb9`
- `CRYPT32!CertCreateCertificateContext` at `0x18001da4c`
- `CRYPT32!CertCreateCertificateContext` at `0x18001da4c`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001da7a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001da7a`
- `CRYPT32!CertFreeCertificateContext` at `0x18001dae8`
- `CRYPT32!CertFreeCertificateContext` at `0x18001dae8`
- `CRYPTSP!CryptReleaseContext` at `0x18001db25`
- `CRYPTSP!CryptReleaseContext` at `0x18001db25`
- `CRYPTSP!CryptDestroyKey` at `0x18001daf7`
- `CRYPTSP!CryptDestroyKey` at `0x18001daf7`
- `CRYPTSP!CryptGetKeyParam` at `0x18001d94f`
- `CRYPTSP!CryptGetKeyParam` at `0x18001da25`
- `CRYPTSP!CryptGetKeyParam` at `0x18001d94f`
- `CRYPTSP!CryptGetKeyParam` at `0x18001da25`
- `CRYPTSP!CryptGetUserKey` at `0x18001d922`
- `CRYPTSP!CryptGetUserKey` at `0x18001d922`
- `CRYPTSP!CryptAcquireContextW` at `0x18001d8b9`
- `CRYPTSP!CryptAcquireContextW` at `0x18001d8b9`
- `EFSUTIL!EfsUtilCheckCurrentKeyCapabilities` at `0x18001da8e`
- `EFSUTIL!EfsUtilCheckCurrentKeyCapabilities` at `0x18001db65`
- `EFSUTIL!EfsUtilCheckCurrentKeyCapabilities` at `0x18001da8e`
- `EFSUTIL!EfsUtilCheckCurrentKeyCapabilities` at `0x18001db65`

## pseudocode

```c
__int64 __fastcall EfspReadContainerData(__int64 a1, const WCHAR *a2, _QWORD *a3)
{
  BYTE *p_pdwDataLen; // rbx
  const WCHAR *v5; // r8
  char v7; // r15
  DWORD LastError; // eax
  char v9; // r14
  unsigned int v10; // esi
  int v11; // r8d
  int v12; // eax
  unsigned __int64 v13; // rdi
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  BYTE *v18; // rax
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v20; // r14
  DWORD v21; // eax
  char v22; // r15
  int v23; // r8d
  int v24; // eax
  char v26; // di
  _BYTE *v27; // rax
  __int64 v28; // [rsp+0h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+30h] [rbp+0h] BYREF
  int v30; // [rsp+34h] [rbp+4h] BYREF
  HCRYPTKEY phUserKey; // [rsp+38h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+40h] [rbp+10h] BYREF
  HCRYPTPROV phProv; // [rsp+48h] [rbp+18h] BYREF
  __int64 v34; // [rsp+50h] [rbp+20h]
  __int128 pvData; // [rsp+58h] [rbp+28h] BYREF
  __int128 v36; // [rsp+68h] [rbp+38h]
  __int128 v37; // [rsp+78h] [rbp+48h]

  p_pdwDataLen = 0;
  v34 = a1;
  *a3 = 0;
  phProv = 0;
  v5 = *(const WCHAR **)(a1 + 8);
  v7 = 1;
  phUserKey = 0;
  pdwDataLen = 0;
  pcbData = 0;
  v30 = 0;
  pvData = 0;
  v36 = 0;
  v37 = 0;
  if ( !CryptAcquireContextW(&phProv, a2, v5, 1u, 0x40u) )
  {
    LastError = GetLastError();
    v9 = -85;
LABEL_3:
    v10 = LastError;
    v11 = LastError;
LABEL_4:
    v12 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v11, 10, v9);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v12, 10, v9);
    goto LABEL_32;
  }
  if ( !CryptGetUserKey(phProv, 1u, &phUserKey) )
  {
    LastError = GetLastError();
    v9 = -75;
    goto LABEL_3;
  }
  if ( !CryptGetKeyParam(phUserKey, 0x1Au, 0, &pdwDataLen, 0) )
  {
    LastError = GetLastError();
    v9 = -65;
    goto LABEL_3;
  }
  v13 = pdwDataLen;
  if ( !pdwDataLen
    || pdwDataLen > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)pdwDataLen + g_ulAdditionalProbeSize + 8 < pdwDataLen
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_53;
  }
  v14 = v13 + 23;
  if ( v13 + 23 <= v13 + 8 )
    v14 = 0xFFFFFFFFFFFFFF0LL;
  v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
  v16 = alloca(v15);
  v17 = alloca(v15);
  p_pdwDataLen = (BYTE *)&pdwDataLen;
  if ( &v28 == (__int64 *)-48LL || (pdwDataLen = 1801679955, (p_pdwDataLen = (BYTE *)&phUserKey) == 0) )
  {
LABEL_53:
    if ( v13 + 8 >= v13 )
    {
      v18 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
      p_pdwDataLen = v18;
      if ( v18 )
      {
        *(_DWORD *)v18 = 1885431112;
        p_pdwDataLen = v18 + 8;
      }
    }
  }
  if ( !p_pdwDataLen )
  {
    v10 = 8;
    v9 = -58;
    v11 = 8;
    goto LABEL_4;
  }
  if ( !CryptGetKeyParam(phUserKey, 0x1Au, p_pdwDataLen, &pdwDataLen, 0) )
  {
    LastError = GetLastError();
    v9 = -45;
    goto LABEL_3;
  }
  CertificateContext = CertCreateCertificateContext(0x10001u, p_pdwDataLen, pdwDataLen);
  v20 = CertificateContext;
  if ( !CertificateContext )
  {
    LastError = GetLastError();
    v9 = -32;
    goto LABEL_3;
  }
  v10 = 0;
  if ( CertGetCertificateContextProperty(CertificateContext, 0x13u, 0, &pcbData) )
    goto LABEL_31;
  v21 = EfsUtilCheckCurrentKeyCapabilities(v20, 1, &v30);
  v10 = v21;
  if ( v21 )
  {
    v22 = -10;
LABEL_29:
    v23 = v21;
LABEL_30:
    v24 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v23, 10, v22);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v24, 10, v22);
LABEL_31:
    CertFreeCertificateContext(v20);
    goto LABEL_32;
  }
  if ( (v30 & 1) != 0 )
  {
    v26 = 0;
  }
  else
  {
    v21 = EfsUtilCheckCurrentKeyCapabilities(v20, 2, &v30);
    v10 = v21;
    if ( v21 )
    {
      v22 = 11;
      goto LABEL_29;
    }
    if ( (v30 & 6) == 0 )
      goto LABEL_31;
    v7 = 0;
    v26 = 1;
  }
  LODWORD(v36) = 1;
  DWORD2(v37) = 1;
  *(_QWORD *)&pvData = a2;
  *((_QWORD *)&pvData + 1) = *(_QWORD *)(v34 + 8);
  if ( !CertSetCertificateContextProperty(v20, 2u, 0, &pvData) )
  {
    v21 = GetLastError();
    v10 = v21;
    v22 = 44;
    goto LABEL_29;
  }
  v27 = wil::details::heap_allocator::allocate(0x18u);
  if ( !v27 )
  {
    v10 = 8;
    v22 = 52;
    v23 = 8;
    goto LABEL_30;
  }
  *(_QWORD *)v27 = v20;
  v27[8] = v7;
  v27[9] = v26;
  *((_QWORD *)v27 + 2) = 0;
  *a3 = v27;
LABEL_32:
  if ( phUserKey )
    CryptDestroyKey(phUserKey);
  if ( p_pdwDataLen && *((_DWORD *)p_pdwDataLen - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return v10;
}

```

## disassembly

```asm
0x18001d844  push    rbp
0x18001d846  push    rbx
0x18001d847  push    rsi
0x18001d848  push    rdi
0x18001d849  push    r12
0x18001d84b  push    r13
0x18001d84d  push    r14
0x18001d84f  push    r15
0x18001d851  sub     rsp, 0A8h
0x18001d858  lea     rbp, [rsp+30h]
0x18001d85d  mov     rax, cs:__security_cookie
0x18001d864  xor     rax, rbp
0x18001d867  mov     [rbp+0B0h+var_50], rax
0x18001d86b  xor     ebx, ebx
0x18001d86d  mov     [rbp+0B0h+var_90], rcx
0x18001d871  xorps   xmm0, xmm0
0x18001d874  mov     [r8], rbx
0x18001d877  mov     r12, r8
0x18001d87a  mov     [rbp+0B0h+phProv], 0
0x18001d882  mov     r8, [rcx+8]; szProvider
0x18001d886  mov     r13, rdx
0x18001d889  lea     r15d, [rbx+1]
0x18001d88d  mov     [rbp+0B0h+phUserKey], 0
0x18001d895  mov     r9d, r15d; dwProvType
0x18001d898  mov     [rbp+0B0h+pdwDataLen], ebx
0x18001d89b  lea     rcx, [rbp+0B0h+phProv]; phProv
0x18001d89f  mov     [rbp+0B0h+pcbData], ebx
0x18001d8a2  mov     [rbp+0B0h+var_AC], ebx
0x18001d8a5  movups  [rbp+0B0h+pvData], xmm0
0x18001d8a9  mov     [rsp+0E0h+dwFlags], 40h ; '@'; dwFlags
0x18001d8b1  movups  [rbp+0B0h+var_78], xmm0
0x18001d8b5  movups  [rbp+0B0h+var_68], xmm0
0x18001d8b9  call    cs:__imp_CryptAcquireContextW
0x18001d8bf  test    eax, eax
0x18001d8c1  jnz     short loc_18001D917
0x18001d8c3  call    cs:__imp_GetLastError
0x18001d8c9  mov     r14d, 11ABh
0x18001d8cf  mov     esi, eax
0x18001d8d1  mov     r8d, eax
0x18001d8d4  mov     rcx, cs:g_hPublisher
0x18001d8db  lea     rdx, EFS_API_ERROR
0x18001d8e2  mov     edi, 0Ah
0x18001d8e7  mov     [rsp+0E0h+dwFlags], r14d
0x18001d8ec  mov     r9d, edi
0x18001d8ef  call    fnEfsLogTrace1
0x18001d8f4  mov     rcx, cs:g_hPublisher
0x18001d8fb  lea     rdx, EFS_TRACE_ERROR
0x18001d902  mov     r9d, edi
0x18001d905  mov     [rsp+0E0h+dwFlags], r14d
0x18001d90a  mov     r8d, eax
0x18001d90d  call    fnEfsLogTrace1
0x18001d912  jmp     loc_18001DAEE
0x18001d917  mov     rcx, [rbp+0B0h+phProv]; hProv
0x18001d91b  lea     r8, [rbp+0B0h+phUserKey]; phUserKey
0x18001d91f  mov     edx, r15d; dwKeySpec
0x18001d922  call    cs:__imp_CryptGetUserKey
0x18001d928  test    eax, eax
0x18001d92a  jnz     short loc_18001D93A
0x18001d92c  call    cs:__imp_GetLastError
0x18001d932  mov     r14d, 11B5h
0x18001d938  jmp     short loc_18001D8CF
0x18001d93a  mov     rcx, [rbp+0B0h+phUserKey]; hKey
0x18001d93e  lea     r9, [rbp+0B0h+pdwDataLen]; pdwDataLen
0x18001d942  xor     r8d, r8d; pbData
0x18001d945  mov     [rsp+0E0h+dwFlags], ebx; dwFlags
0x18001d949  lea     esi, [r8+1Ah]
0x18001d94d  mov     edx, esi; dwParam
0x18001d94f  call    cs:__imp_CryptGetKeyParam
0x18001d955  test    eax, eax
0x18001d957  jnz     short loc_18001D96A
0x18001d959  call    cs:__imp_GetLastError
0x18001d95f  mov     r14d, 11BFh
0x18001d965  jmp     loc_18001D8CF
0x18001d96a  mov     edi, [rbp+0B0h+pdwDataLen]
0x18001d96d  test    rdi, rdi
0x18001d970  jz      short loc_18001D9D3
0x18001d972  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18001d979  ja      short loc_18001D9D3
0x18001d97b  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001d982  add     rcx, 8
0x18001d986  add     rcx, rdi
0x18001d989  cmp     rcx, rdi
0x18001d98c  jb      short loc_18001D9D3
0x18001d98e  call    VerifyStackAvailable
0x18001d993  test    eax, eax
0x18001d995  jz      short loc_18001D9D3
0x18001d997  lea     rax, [rdi+8]
0x18001d99b  lea     rcx, [rax+0Fh]
0x18001d99f  cmp     rcx, rax
0x18001d9a2  ja      short loc_18001D9AE
0x18001d9a4  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001d9ae  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001d9b2  mov     rax, rcx
0x18001d9b5  call    _alloca_probe
0x18001d9ba  sub     rsp, rcx
0x18001d9bd  lea     rbx, [rsp+0E0h+pdwDataLen]
0x18001d9c2  test    rbx, rbx
0x18001d9c5  jz      short loc_18001D9D3
0x18001d9c7  mov     dword ptr [rbx], 6B637453h
0x18001d9cd  add     rbx, 8
0x18001d9d1  jnz     short loc_18001D9FA
0x18001d9d3  lea     rcx, [rdi+8]
0x18001d9d7  cmp     rcx, rdi
0x18001d9da  jb      short loc_18001D9FA
0x18001d9dc  mov     rax, cs:g_pfnAllocate
0x18001d9e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9e8  mov     rbx, rax
0x18001d9eb  test    rax, rax
0x18001d9ee  jz      short loc_18001D9FA
0x18001d9f0  mov     dword ptr [rax], 70616548h
0x18001d9f6  add     rbx, 8
0x18001d9fa  test    rbx, rbx
0x18001d9fd  jnz     short loc_18001DA10
0x18001d9ff  lea     esi, [rbx+8]
0x18001da02  mov     r14d, 11C6h
0x18001da08  mov     r8d, esi
0x18001da0b  jmp     loc_18001D8D4
0x18001da10  mov     rcx, [rbp+0B0h+phUserKey]; hKey
0x18001da14  lea     r9, [rbp+0B0h+pdwDataLen]; pdwDataLen
0x18001da18  mov     r8, rbx; pbData
0x18001da1b  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x18001da23  mov     edx, esi; dwParam
0x18001da25  call    cs:__imp_CryptGetKeyParam
0x18001da2b  test    eax, eax
0x18001da2d  jnz     short loc_18001DA40
0x18001da2f  call    cs:__imp_GetLastError
0x18001da35  mov     r14d, 11D3h
0x18001da3b  jmp     loc_18001D8CF
0x18001da40  mov     r8d, [rbp+0B0h+pdwDataLen]; cbCertEncoded
0x18001da44  mov     rdx, rbx; pbCertEncoded
0x18001da47  mov     ecx, 10001h; dwCertEncodingType
0x18001da4c  call    cs:__imp_CertCreateCertificateContext
0x18001da52  mov     r14, rax
0x18001da55  test    rax, rax
0x18001da58  jnz     short loc_18001DA6B
0x18001da5a  call    cs:__imp_GetLastError
0x18001da60  mov     r14d, 11E0h
0x18001da66  jmp     loc_18001D8CF
0x18001da6b  xor     esi, esi
0x18001da6d  lea     r9, [rbp+0B0h+pcbData]; pcbData
0x18001da71  xor     r8d, r8d; pvData
0x18001da74  mov     rcx, r14; pCertContext
0x18001da77  lea     edx, [rsi+13h]; dwPropId
0x18001da7a  call    cs:__imp_CertGetCertificateContextProperty
0x18001da80  test    eax, eax
0x18001da82  jnz     short loc_18001DAE5
0x18001da84  lea     r8, [rbp+0B0h+var_AC]
0x18001da88  mov     edx, r15d
0x18001da8b  mov     rcx, r14
0x18001da8e  call    cs:__imp_EfsUtilCheckCurrentKeyCapabilities
0x18001da94  mov     esi, eax
0x18001da96  test    eax, eax
0x18001da98  jz      loc_18001DB4A
0x18001da9e  mov     r15d, 11F6h
0x18001daa4  mov     r8d, eax
0x18001daa7  mov     rcx, cs:g_hPublisher
0x18001daae  lea     rdx, EFS_API_ERROR
0x18001dab5  mov     edi, 0Ah
0x18001daba  mov     [rsp+0E0h+dwFlags], r15d
0x18001dabf  mov     r9d, edi
0x18001dac2  call    fnEfsLogTrace1
0x18001dac7  mov     rcx, cs:g_hPublisher
0x18001dace  lea     rdx, EFS_TRACE_ERROR
0x18001dad5  mov     r9d, edi
0x18001dad8  mov     [rsp+0E0h+dwFlags], r15d
0x18001dadd  mov     r8d, eax
0x18001dae0  call    fnEfsLogTrace1
0x18001dae5  mov     rcx, r14; pCertContext
0x18001dae8  call    cs:__imp_CertFreeCertificateContext
0x18001daee  mov     rcx, [rbp+0B0h+phUserKey]; hKey
0x18001daf2  test    rcx, rcx
0x18001daf5  jz      short loc_18001DAFD
0x18001daf7  call    cs:__imp_CryptDestroyKey
0x18001dafd  test    rbx, rbx
0x18001db00  jz      short loc_18001DB1A
0x18001db02  lea     rcx, [rbx-8]
0x18001db06  cmp     dword ptr [rcx], 70616548h
0x18001db0c  jnz     short loc_18001DB1A
0x18001db0e  mov     rax, cs:g_pfnFree
0x18001db15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db1a  mov     rcx, [rbp+0B0h+phProv]; hProv
0x18001db1e  test    rcx, rcx
0x18001db21  jz      short loc_18001DB2B
0x18001db23  xor     edx, edx; dwFlags
0x18001db25  call    cs:__imp_CryptReleaseContext
0x18001db2b  mov     eax, esi
0x18001db2d  mov     rcx, [rbp+0B0h+var_50]
0x18001db31  xor     rcx, rbp; StackCookie
0x18001db34  call    __security_check_cookie
0x18001db39  lea     rsp, [rbp+78h]
0x18001db3d  pop     r15
0x18001db3f  pop     r14
0x18001db41  pop     r13
0x18001db43  pop     r12
0x18001db45  pop     rdi
0x18001db46  pop     rsi
0x18001db47  pop     rbx
0x18001db48  pop     rbp
0x18001db49  retn
0x18001db4a  mov     eax, [rbp+0B0h+var_AC]
0x18001db4d  and     eax, r15d
0x18001db50  test    al, al
0x18001db52  jz      short loc_18001DB59
0x18001db54  xor     dil, dil
0x18001db57  jmp     short loc_18001DB8D
0x18001db59  lea     r8, [rbp+0B0h+var_AC]
0x18001db5d  mov     edx, 2
0x18001db62  mov     rcx, r14
0x18001db65  call    cs:__imp_EfsUtilCheckCurrentKeyCapabilities
0x18001db6b  mov     esi, eax
0x18001db6d  test    eax, eax
0x18001db6f  jz      short loc_18001DB7C
0x18001db71  mov     r15d, 120Bh
0x18001db77  jmp     loc_18001DAA4
0x18001db7c  mov     eax, [rbp+0B0h+var_AC]
0x18001db7f  test    al, 6
0x18001db81  jz      loc_18001DAE5
0x18001db87  xor     r15b, r15b
0x18001db8a  mov     dil, 1
0x18001db8d  mov     rax, [rbp+0B0h+var_90]
0x18001db91  lea     r9, [rbp+0B0h+pvData]; pvData
0x18001db95  xor     r8d, r8d; dwFlags
0x18001db98  mov     dword ptr [rbp+0B0h+var_78], 1
0x18001db9f  mov     rcx, r14; pCertContext
0x18001dba2  mov     dword ptr [rbp+0B0h+var_68+8], 1
0x18001dba9  mov     qword ptr [rbp+0B0h+pvData], r13
0x18001dbad  mov     rax, [rax+8]
0x18001dbb1  lea     edx, [r8+2]; dwPropId
0x18001dbb5  mov     qword ptr [rbp+0B0h+pvData+8], rax
0x18001dbb9  call    cs:__imp_CertSetCertificateContextProperty
0x18001dbbf  test    eax, eax
0x18001dbc1  jnz     short loc_18001DBD6
0x18001dbc3  call    cs:__imp_GetLastError
0x18001dbc9  mov     esi, eax
0x18001dbcb  mov     r15d, 122Ch
0x18001dbd1  jmp     loc_18001DAA4
0x18001dbd6  mov     ecx, 18h; unsigned __int64
0x18001dbdb  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18001dbe0  test    rax, rax
0x18001dbe3  jnz     short loc_18001DBF6
0x18001dbe5  lea     esi, [rax+8]
0x18001dbe8  mov     r15d, 1234h
0x18001dbee  mov     r8d, esi
0x18001dbf1  jmp     loc_18001DAA7
0x18001dbf6  mov     [rax], r14
0x18001dbf9  mov     [rax+8], r15b
0x18001dbfd  mov     [rax+9], dil
0x18001dc01  mov     qword ptr [rax+10h], 0
0x18001dc09  mov     [r12], rax
0x18001dc0d  jmp     loc_18001DAEE
```
