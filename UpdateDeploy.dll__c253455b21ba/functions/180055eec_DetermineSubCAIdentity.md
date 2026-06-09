# DetermineSubCAIdentity

- ea: `0x180055eec`
- end: `0x180056670`
- name: `DetermineSubCAIdentity`
- size: `1924`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180057254`

## callees

- `0x180003180`
- `0x18000dc6c`
- `0x18000dce4`
- `0x18000dd60`
- `0x1800110fc`
- `0x180055eec`
- `0x180057690`
- `0x18005779c`
- `0x1800581a8`
- `0x180058224`
- `0x180061960`
- `0x180061d54`
- `0x180069960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055ffa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005661f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005661f`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800562fc`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18005645a`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800562fc`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18005645a`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180055fd5`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180055fd5`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x1800563e5`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18005641e`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x1800563e5`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x18005641e`

## string_xrefs

- `0x180056281`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

## pseudocode

```c
__int64 __fastcall DetermineSubCAIdentity(__int64 a1, int a2, __int64 a3)
{
  __int64 v3; // r12
  signed int CertHashAlgorithm; // esi
  __int64 v5; // rcx
  signed int LastError; // ecx
  signed int v7; // eax
  signed int v8; // eax
  char IsEnabled; // al
  size_t v10; // r15
  __int64 v11; // rdi
  __int64 v12; // r13
  size_t v13; // r8
  unsigned int v14; // ebx
  char v15; // al
  __int64 v16; // rdi
  __int64 v17; // r12
  __int64 v18; // r13
  unsigned int v19; // ebx
  int v20; // eax
  size_t v21; // rdx
  __int64 v22; // r13
  unsigned int v23; // ebx
  int v24; // eax
  __int64 v25; // rbx
  _WORD *v26; // rbx
  DWORD v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rdi
  BYTE *v30; // rdx
  _WORD *v31; // rcx
  __int64 v32; // r8
  _WORD *v33; // rcx
  char v34; // al
  __int64 v35; // rdi
  __int64 *v36; // rax
  __int64 v37; // rbx
  struct _CTL_USAGE *v38; // rax
  struct _CTL_USAGE *v39; // rsi
  int v40; // ebx
  const struct std::nothrow_t *v41; // rdx
  WCHAR *v42; // rcx
  WCHAR *v43; // rbx
  WCHAR *v44; // rcx
  WCHAR *v45; // rdi
  PCERT_PUBLIC_KEY_INFO pInfo; // [rsp+28h] [rbp-69h]
  PCERT_PUBLIC_KEY_INFO pInfoa; // [rsp+28h] [rbp-69h]
  DWORD *pcbComputedHash; // [rsp+38h] [rbp-59h]
  char v50; // [rsp+48h] [rbp-49h]
  int v51; // [rsp+4Ch] [rbp-45h]
  PCNZWCH lpString2; // [rsp+50h] [rbp-41h] BYREF
  PCNZWCH lpString1; // [rsp+58h] [rbp-39h] BYREF
  __int64 v54; // [rsp+60h] [rbp-31h]
  size_t Size; // [rsp+68h] [rbp-29h]
  __int64 v56; // [rsp+70h] [rbp-21h]
  PCCERT_CONTEXT pCertContext; // [rsp+78h] [rbp-19h]
  void *lpMem; // [rsp+80h] [rbp-11h]
  __int64 v59; // [rsp+88h] [rbp-9h]
  __int64 v60; // [rsp+90h] [rbp-1h]
  DWORD pcbUsage; // [rsp+98h] [rbp+7h] BYREF
  DWORD v62; // [rsp+9Ch] [rbp+Bh] BYREF
  BYTE Buf2[16]; // [rsp+A0h] [rbp+Fh] BYREF
  __int128 v64; // [rsp+B0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v59 = a3;
  LODWORD(lpString2) = a2;
  v62 = 32;
  v3 = 0;
  lpMem = 0;
  CertHashAlgorithm = 0;
  *(_OWORD *)Buf2 = 0;
  v64 = 0;
  if ( !a1 )
  {
    CertHashAlgorithm = -2147467261;
    goto LABEL_84;
  }
  v5 = **(_QWORD **)(a1 + 16);
  v56 = v5;
  if ( *(_DWORD *)(v5 + 12) != 3 )
  {
    WUTrace(0, 0, 32, 1, 0, L"Cert chain length check failed, length=%d", *(_DWORD *)(v5 + 12));
    LODWORD(v3) = 1;
    goto LABEL_84;
  }
  v60 = *(_QWORD *)(*(_QWORD *)(v5 + 16) + 8LL);
  pCertContext = *(PCCERT_CONTEXT *)(v60 + 8);
  if ( !CryptHashPublicKeyInfo(0, 0x800Cu, 0, 1u, &pCertContext->pCertInfo->SubjectPublicKeyInfo, Buf2, &v62) )
  {
LABEL_6:
    LastError = GetLastError();
    v7 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v7 = LastError;
    if ( v7 >= 0 )
    {
      CertHashAlgorithm = -2147467259;
    }
    else
    {
      v8 = GetLastError();
      CertHashAlgorithm = (unsigned __int16)v8 | 0x80070000;
      if ( v8 <= 0 )
        CertHashAlgorithm = v8;
    }
    goto LABEL_84;
  }
  CertHashAlgorithm = -2145078525;
  if ( v62 != 32 )
    goto LABEL_84;
  v51 = 1;
  pcbUsage = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl);
  v10 = v62;
  v11 = 0;
  if ( IsEnabled )
  {
    v50 = 0;
    v12 = 2;
    LODWORD(lpString1) = v62;
    v13 = v62;
    Size = v62;
    do
    {
      v14 = 0;
      while ( 1 )
      {
        v54 = v14;
        if ( !memcmp(&qword_180092540[6 * v3 + 6 * v14], Buf2, v13) )
          break;
        ++v14;
        v13 = v10;
        if ( v14 >= 5 )
        {
          v15 = v50;
          goto LABEL_21;
        }
      }
      v51 = dword_180092530[12 * v11 + 12 * v54];
      v15 = 1;
      v50 = 1;
      pcbUsage = dword_180092534[12 * v11 + 12 * v54];
LABEL_21:
      v3 += 5;
      v11 += 5;
      v13 = v10;
      --v12;
    }
    while ( v12 );
    if ( !v15 )
    {
      v16 = 0;
      v17 = 0;
      v18 = 2;
      do
      {
        v19 = 0;
        while ( 1 )
        {
          v54 = v19;
          if ( !memcmp(&qword_1800921D0[6 * v17 + 6 * v19], Buf2, Size) )
            break;
          if ( ++v19 >= 9 )
            goto LABEL_29;
        }
        v20 = dword_1800921C0[12 * v16 + 12 * v54];
        pcbUsage = dword_1800921C4[12 * v16 + 12 * v54];
        v51 = v20;
LABEL_29:
        v17 += 9;
        v16 += 9;
        --v18;
      }
      while ( v18 );
      LODWORD(v10) = (_DWORD)lpString1;
    }
  }
  else
  {
    v21 = v62;
    v22 = 2;
    do
    {
      v23 = 0;
      while ( 1 )
      {
        Size = v23;
        if ( !memcmp(&qword_180092540[6 * v3 + 6 * v23], Buf2, v21) )
          break;
        ++v23;
        v21 = v10;
        if ( v23 >= 5 )
          goto LABEL_37;
      }
      v24 = dword_180092530[12 * v11 + 12 * Size];
      pcbUsage = dword_180092534[12 * v11 + 12 * Size];
      v51 = v24;
LABEL_37:
      v3 += 5;
      v11 += 5;
      v21 = v10;
      --v22;
    }
    while ( v22 );
  }
  LODWORD(v3) = v51;
  if ( v51 == 1 )
  {
    if ( !(_DWORD)lpString2 || !v59 )
      goto LABEL_46;
    v25 = 0;
    while ( *(_DWORD *)(v59 + 24 * v25 + 8) != 32
         || memcmp(*(const void **)(v59 + 24 * v25 + 16), Buf2, (unsigned int)v10) )
    {
      v25 = (unsigned int)(v25 + 1);
      if ( (unsigned int)v25 >= (unsigned int)lpString2 )
      {
        LODWORD(v3) = 1;
        goto LABEL_46;
      }
    }
    LODWORD(v3) = *(_DWORD *)(v59 + 24 * v25);
    v27 = *(_DWORD *)(v59 + 24 * v25 + 4);
    if ( (_DWORD)v3 == 1 )
    {
LABEL_46:
      v26 = SafeSusAllocArray((unsigned int)(2 * v10 + 1), 2u);
      if ( v26 )
      {
        v30 = Buf2;
        v31 = v26;
        if ( (_DWORD)v10 )
        {
          v32 = (unsigned int)v10;
          do
          {
            *v31 = word_18007E100[(unsigned __int64)*v30 >> 4];
            v33 = v31 + 1;
            v34 = *v30++;
            *v33 = word_18007E100[v34 & 0xF];
            v31 = v33 + 1;
            --v32;
          }
          while ( v32 );
        }
        *v31 = 0;
        LODWORD(pcbComputedHash) = v62;
        WUTrace(
          0,
          0,
          32,
          1,
          0,
          L"Hash of public key doesn't match the known values, cbKeyId=%d, rgbKeyId=%ws.",
          pcbComputedHash,
          v26);
        SusFree(v26);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE8,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\commonutil.cpp",
          v26 == 0 ? (const char *)0x8007000ELL : 0,
          (int)pInfo);
        LODWORD(pInfoa) = -2147024882;
        WUTrace(
          0,
          0,
          32,
          1,
          pInfoa,
          L"Hash of public key doesn't match the known values, but failed to get the hash as hex string.");
      }
      goto LABEL_84;
    }
  }
  else
  {
    v27 = pcbUsage;
  }
  if ( v27 )
  {
    v28 = 0;
    v29 = *(_QWORD *)(v60 + 40);
    if ( !*(_DWORD *)v29 )
    {
LABEL_53:
      WUTrace(0, 0, 32, 1, 0, L"EKU not found for SubCA");
      goto LABEL_84;
    }
    while ( CompareStringA(0x7Fu, 1u, "1.3.6.1.4.1.311.76.6.1", -1, *(PCNZCH *)(*(_QWORD *)(v29 + 8) + 8LL * v28), -1) != 2 )
    {
      if ( ++v28 >= *(_DWORD *)v29 )
        goto LABEL_53;
    }
    v35 = v56;
    pcbUsage = 0;
    v36 = *(__int64 **)(v56 + 16);
    v37 = *v36;
    if ( !CertGetEnhancedKeyUsage(*(PCCERT_CONTEXT *)(*v36 + 8), 0, 0, &pcbUsage) )
      goto LABEL_6;
    v38 = (struct _CTL_USAGE *)SusAlloc(pcbUsage);
    lpMem = v38;
    v39 = v38;
    if ( !v38 )
    {
      CertHashAlgorithm = -2147024882;
      goto LABEL_84;
    }
    if ( !CertGetEnhancedKeyUsage(*(PCCERT_CONTEXT *)(v37 + 8), 0, v38, &pcbUsage) )
      goto LABEL_6;
    v40 = 0;
    if ( !v39->cUsageIdentifier )
    {
LABEL_66:
      WUTrace(0, 0, 32, 1, 0, L"EKU not found for leaf cert");
      CertHashAlgorithm = -2145078525;
      goto LABEL_84;
    }
    while ( CompareStringA(0x7Fu, 1u, "1.3.6.1.4.1.311.76.6.1", -1, v39->rgpszUsageIdentifier[v40], -1) != 2 )
    {
      if ( ++v40 >= v39->cUsageIdentifier )
        goto LABEL_66;
    }
  }
  else
  {
    v35 = v56;
  }
  lpString1 = 0;
  lpString2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_FixIncorrectCryptoAlgoCheck_52146970>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_FixIncorrectCryptoAlgoCheck_52146970>::GetImpl'::`2'::impl) )
  {
    CertHashAlgorithm = GetCertHashAlgorithm(pCertContext, (wchar_t **)&lpString1);
    if ( CertHashAlgorithm < 0 )
      goto LABEL_70;
    v43 = (WCHAR *)lpString1;
    CertHashAlgorithm = VerifyHashAlgIsSHA256OrHigher(lpString1);
    if ( CertHashAlgorithm < 0 )
    {
LABEL_73:
      if ( !v43 )
        goto LABEL_84;
      v42 = v43;
LABEL_71:
      operator delete(v42, v41);
      goto LABEL_84;
    }
    CertHashAlgorithm = GetCertHashAlgorithm(*(PCCERT_CONTEXT *)(**(_QWORD **)(v35 + 16) + 8LL), (wchar_t **)&lpString2);
    if ( CertHashAlgorithm < 0 )
    {
      v44 = (WCHAR *)lpString2;
      if ( !lpString2 )
        goto LABEL_73;
LABEL_77:
      operator delete(v44, v41);
      goto LABEL_73;
    }
    v45 = (WCHAR *)lpString2;
    CertHashAlgorithm = VerifyHashAlgIsSHA256OrHigher(lpString2);
    if ( CertHashAlgorithm >= 0 )
      goto LABEL_79;
LABEL_93:
    if ( !v45 )
      goto LABEL_73;
    v44 = v45;
    goto LABEL_77;
  }
  CertHashAlgorithm = GetCertHashAlgorithm(pCertContext, (wchar_t **)&lpString1);
  if ( CertHashAlgorithm < 0 )
  {
LABEL_70:
    v42 = (WCHAR *)lpString1;
    if ( !lpString1 )
      goto LABEL_84;
    goto LABEL_71;
  }
  CertHashAlgorithm = GetCertHashAlgorithm(*(PCCERT_CONTEXT *)(**(_QWORD **)(v35 + 16) + 8LL), (wchar_t **)&lpString2);
  if ( CertHashAlgorithm < 0 )
  {
    if ( lpString2 )
      operator delete((void *)lpString2, v41);
    goto LABEL_70;
  }
  v43 = (WCHAR *)lpString1;
  v45 = (WCHAR *)lpString2;
  if ( CompareStringW(0x7Fu, 0, lpString1, -1, lpString2, -1) != 2 )
  {
    WUTrace(0, 0, 32, 1, 0, L"Inconsistent hash algorithm. Leaf:%ws, SubCA:%ws", v45, v43);
    CertHashAlgorithm = -2145078525;
    goto LABEL_93;
  }
LABEL_79:
  if ( v45 )
    operator delete(v45, v41);
  if ( v43 )
    operator delete(v43, v41);
  CertHashAlgorithm = 0;
LABEL_84:
  SusFree(lpMem);
  if ( CertHashAlgorithm < 0 )
  {
    LODWORD(pInfo) = CertHashAlgorithm;
    LODWORD(v3) = 0;
    WUTrace("DetermineSubCAIdentity", 1679, 32, 1, pInfo, L"Method failed");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180055eec  mov     rax, rsp
0x180055eef  mov     [rax+10h], rbx
0x180055ef3  mov     [rax+18h], rsi
0x180055ef7  mov     [rax+20h], rdi
0x180055efb  push    rbp
0x180055efc  push    r12
0x180055efe  push    r13
0x180055f00  push    r14
0x180055f02  push    r15
0x180055f04  lea     rbp, [rax-5Fh]
0x180055f08  sub     rsp, 0C0h
0x180055f0f  mov     rax, cs:__security_cookie
0x180055f16  xor     rax, rsp
0x180055f19  mov     [rbp+57h+var_28], rax
0x180055f1d  xor     r13d, r13d
0x180055f20  mov     [rbp+57h+var_60], r8
0x180055f24  mov     dword ptr [rbp+57h+lpString2], edx
0x180055f27  xorps   xmm0, xmm0
0x180055f2a  mov     [rbp+57h+var_4C], 20h ; ' '
0x180055f31  mov     r12d, r13d
0x180055f34  mov     [rbp+57h+lpMem], r13
0x180055f38  mov     esi, r13d
0x180055f3b  movups  xmmword ptr [rbp+57h+Buf2], xmm0
0x180055f3f  movups  [rbp+57h+var_38], xmm0
0x180055f43  test    rcx, rcx
0x180055f46  jnz     short loc_180055F52
0x180055f48  mov     esi, 80004003h
0x180055f4d  jmp     loc_180056557
0x180055f52  mov     rax, [rcx+10h]
0x180055f56  mov     r9d, 1; dwCertEncodingType
0x180055f5c  mov     rcx, [rax]
0x180055f5f  mov     [rbp+57h+var_78], rcx
0x180055f63  mov     eax, [rcx+0Ch]
0x180055f66  cmp     eax, 3
0x180055f69  jz      short loc_180055F98
0x180055f6b  mov     dword ptr [rsp+0E0h+pcbComputedHash], eax
0x180055f6f  lea     r8d, [r9+1Fh]
0x180055f73  lea     rax, aCertChainLengt; "Cert chain length check failed, length="...
0x180055f7a  xor     edx, edx
0x180055f7c  mov     [rsp+0E0h+pbComputedHash], rax
0x180055f81  xor     ecx, ecx
0x180055f83  mov     [rsp+0E0h+pInfo], r13
0x180055f88  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180055f8d  mov     r12d, 1
0x180055f93  jmp     loc_180056557
0x180055f98  mov     rax, [rcx+10h]
0x180055f9c  xor     r8d, r8d; dwFlags
0x180055f9f  lea     rcx, [rbp+57h+var_4C]
0x180055fa3  mov     edx, 800Ch; Algid
0x180055fa8  mov     [rsp+0E0h+pcbComputedHash], rcx; pcbComputedHash
0x180055fad  lea     rcx, [rbp+57h+Buf2]
0x180055fb1  mov     [rsp+0E0h+pbComputedHash], rcx; pbComputedHash
0x180055fb6  xor     ecx, ecx; hCryptProv
0x180055fb8  mov     rax, [rax+8]
0x180055fbc  mov     [rbp+57h+var_58], rax
0x180055fc0  mov     rax, [rax+8]
0x180055fc4  mov     [rbp+57h+pCertContext], rax
0x180055fc8  mov     rax, [rax+18h]
0x180055fcc  add     rax, 60h ; '`'
0x180055fd0  mov     [rsp+0E0h+pInfo], rax; int
0x180055fd5  call    cs:__imp_CryptHashPublicKeyInfo
0x180055fdb  test    eax, eax
0x180055fdd  jnz     short loc_180056019
0x180055fdf  call    cs:__imp_GetLastError
0x180055fe5  mov     ecx, eax
0x180055fe7  mov     ebx, 80070000h
0x180055fec  movzx   eax, ax
0x180055fef  or      eax, ebx
0x180055ff1  test    ecx, ecx
0x180055ff3  cmovle  eax, ecx
0x180055ff6  test    eax, eax
0x180055ff8  jns     short loc_18005600F
0x180055ffa  call    cs:__imp_GetLastError
0x180056000  movzx   esi, ax
0x180056003  or      esi, ebx
0x180056005  test    eax, eax
0x180056007  cmovle  esi, eax
0x18005600a  jmp     loc_180056557
0x18005600f  mov     esi, 80004005h
0x180056014  jmp     loc_180056557
0x180056019  cmp     [rbp+57h+var_4C], 20h ; ' '
0x18005601d  mov     esi, 8024B303h
0x180056022  jnz     loc_180056557
0x180056028  mov     [rbp+57h+var_9C], 1
0x18005602f  mov     [rbp+57h+pcbUsage], r13d
0x180056033  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x18005603a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x18005603f  mov     r15d, [rbp+57h+var_4C]
0x180056043  mov     rdi, r13
0x180056046  mov     r14d, 2
0x18005604c  test    al, al
0x18005604e  jz      loc_180056179
0x180056054  mov     [rbp+57h+var_A0], r13b
0x180056058  lea     rdx, qword_180092540
0x18005605f  mov     r13d, r14d
0x180056062  mov     dword ptr [rbp+57h+lpString1], r15d
0x180056066  mov     r8d, r15d; Size
0x180056069  mov     [rbp+57h+Size], r15
0x18005606d  xor     ebx, ebx
0x18005606f  mov     eax, ebx
0x180056071  mov     [rbp+57h+var_88], rax
0x180056075  add     rax, r12
0x180056078  lea     rcx, [rax+rax*2]
0x18005607c  shl     rcx, 4
0x180056080  add     rcx, rdx; Buf1
0x180056083  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180056087  call    memcmp
0x18005608c  test    eax, eax
0x18005608e  jz      short loc_1800560A6
0x180056090  inc     ebx
0x180056092  lea     rdx, qword_180092540
0x180056099  mov     r8, r15
0x18005609c  cmp     ebx, 5
0x18005609f  jb      short loc_18005606F
0x1800560a1  mov     al, [rbp+57h+var_A0]
0x1800560a4  jmp     short loc_1800560D4
0x1800560a6  mov     rax, [rbp+57h+var_88]
0x1800560aa  lea     rdx, __ImageBase
0x1800560b1  add     rax, rdi
0x1800560b4  lea     rcx, [rax+rax*2]
0x1800560b8  add     rcx, rcx
0x1800560bb  mov     eax, ds:rva dword_180092530[rdx+rcx*8]
0x1800560c2  mov     ecx, ds:rva dword_180092534[rdx+rcx*8]
0x1800560c9  mov     [rbp+57h+var_9C], eax
0x1800560cc  mov     al, 1
0x1800560ce  mov     [rbp+57h+var_A0], al
0x1800560d1  mov     [rbp+57h+pcbUsage], ecx
0x1800560d4  add     r12, 5
0x1800560d8  lea     rdx, qword_180092540
0x1800560df  add     rdi, 5
0x1800560e3  mov     r8, r15
0x1800560e6  sub     r13, 1
0x1800560ea  jnz     short loc_18005606D
0x1800560ec  xor     r13d, r13d
0x1800560ef  test    al, al
0x1800560f1  jnz     loc_180056203
0x1800560f7  mov     edi, r13d
0x1800560fa  lea     r15, __ImageBase
0x180056101  mov     r12d, r13d
0x180056104  mov     r13, r14
0x180056107  xor     ebx, ebx
0x180056109  mov     r8, [rbp+57h+Size]; Size
0x18005610d  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180056111  mov     eax, ebx
0x180056113  mov     [rbp+57h+var_88], rax
0x180056117  add     rax, r12
0x18005611a  lea     rcx, [rax+rax*2]
0x18005611e  shl     rcx, 4
0x180056122  lea     rax, qword_1800921D0
0x180056129  add     rcx, rax; Buf1
0x18005612c  call    memcmp
0x180056131  test    eax, eax
0x180056133  jz      short loc_18005613E
0x180056135  inc     ebx
0x180056137  cmp     ebx, 9
0x18005613a  jb      short loc_180056109
0x18005613c  jmp     short loc_180056162
0x18005613e  mov     rax, [rbp+57h+var_88]
0x180056142  add     rax, rdi
0x180056145  lea     rcx, [rax+rax*2]
0x180056149  add     rcx, rcx
0x18005614c  mov     eax, ds:rva dword_1800921C0[r15+rcx*8]
0x180056154  mov     ecx, ds:rva dword_1800921C4[r15+rcx*8]
0x18005615c  mov     [rbp+57h+pcbUsage], ecx
0x18005615f  mov     [rbp+57h+var_9C], eax
0x180056162  add     r12, 9
0x180056166  add     rdi, 9
0x18005616a  sub     r13, 1
0x18005616e  jnz     short loc_180056107
0x180056170  mov     r15d, dword ptr [rbp+57h+lpString1]
0x180056174  jmp     loc_180056200
0x180056179  mov     rdx, r15
0x18005617c  lea     r8, qword_180092540
0x180056183  mov     r13, r14
0x180056186  xor     ebx, ebx
0x180056188  mov     eax, ebx
0x18005618a  mov     [rbp+57h+Size], rax
0x18005618e  add     rax, r12
0x180056191  lea     rcx, [rax+rax*2]
0x180056195  shl     rcx, 4
0x180056199  add     rcx, r8; Buf1
0x18005619c  mov     r8, rdx; Size
0x18005619f  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1800561a3  call    memcmp
0x1800561a8  test    eax, eax
0x1800561aa  jz      short loc_1800561BF
0x1800561ac  inc     ebx
0x1800561ae  lea     r8, qword_180092540
0x1800561b5  mov     rdx, r15
0x1800561b8  cmp     ebx, 5
0x1800561bb  jb      short loc_180056188
0x1800561bd  jmp     short loc_1800561E8
0x1800561bf  mov     rax, [rbp+57h+Size]
0x1800561c3  lea     rdx, __ImageBase
0x1800561ca  add     rax, rdi
0x1800561cd  lea     rcx, [rax+rax*2]
0x1800561d1  add     rcx, rcx
0x1800561d4  mov     eax, ds:rva dword_180092530[rdx+rcx*8]
0x1800561db  mov     ecx, ds:rva dword_180092534[rdx+rcx*8]
0x1800561e2  mov     [rbp+57h+pcbUsage], ecx
0x1800561e5  mov     [rbp+57h+var_9C], eax
0x1800561e8  add     r12, 5
0x1800561ec  lea     r8, qword_180092540
0x1800561f3  add     rdi, 5
0x1800561f7  mov     rdx, r15
0x1800561fa  sub     r13, 1
0x1800561fe  jnz     short loc_180056186
0x180056200  xor     r13d, r13d
0x180056203  mov     r12d, [rbp+57h+var_9C]
0x180056207  cmp     r12d, 1
0x18005620b  jnz     loc_1800563C1
0x180056211  cmp     dword ptr [rbp+57h+lpString2], r13d
0x180056215  jbe     short loc_180056254
0x180056217  mov     r13, [rbp+57h+var_60]
0x18005621b  test    r13, r13
0x18005621e  jz      short loc_180056251
0x180056220  xor     ebx, ebx
0x180056222  mov     r12d, r15d
0x180056225  lea     rdi, [rbx+rbx*2]
0x180056229  cmp     dword ptr [r13+rdi*8+8], 20h ; ' '
0x18005622f  jnz     short loc_180056246
0x180056231  mov     rcx, [r13+rdi*8+10h]; Buf1
0x180056236  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18005623a  mov     r8, r12; Size
0x18005623d  call    memcmp
0x180056242  test    eax, eax
0x180056244  jz      short loc_1800562A7
0x180056246  inc     ebx
0x180056248  cmp     ebx, dword ptr [rbp+57h+lpString2]
0x18005624b  jb      short loc_180056225
0x18005624d  mov     r12d, [rbp+57h+var_9C]
0x180056251  xor     r13d, r13d
0x180056254  lea     ecx, ds:1[r15*2]; unsigned __int64
0x18005625c  mov     rdx, r14; unsigned __int64
0x18005625f  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180056264  mov     rbx, rax
0x180056267  neg     rax
0x18005626a  sbb     edi, edi
0x18005626c  not     edi
0x18005626e  and     edi, 8007000Eh
0x180056274  test    rbx, rbx
0x180056277  jnz     loc_180056338
0x18005627d  mov     rcx, [rbp+5Fh]; this
0x180056281  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180056288  mov     r9d, edi; char *
0x18005628b  mov     edx, 0E8h; void *
0x180056290  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056295  lea     rax, aHashOfPublicKe; "Hash of public key doesn't match the kn"...
0x18005629c  mov     [rsp+0E0h+pbComputedHash], rax
0x1800562a1  mov     dword ptr [rsp+0E0h+pInfo], edi
0x1800562a5  jmp     short loc_180056322
0x1800562a7  mov     r12d, [r13+rdi*8+0]
0x1800562ac  mov     eax, [r13+rdi*8+4]
0x1800562b1  cmp     r12d, 1
0x1800562b5  jz      short loc_180056251
0x1800562b7  xor     r13d, r13d
0x1800562ba  or      r15d, 0FFFFFFFFh
0x1800562be  test    eax, eax
0x1800562c0  jz      loc_180056497
0x1800562c6  mov     rdi, [rbp+57h+var_58]
0x1800562ca  mov     ebx, r13d
0x1800562cd  mov     rdi, [rdi+28h]
0x1800562d1  cmp     [rdi], r13d
0x1800562d4  jbe     short loc_180056311
0x1800562d6  mov     rax, [rdi+8]
0x1800562da  lea     r8, a1361413117661; "1.3.6.1.4.1.311.76.6.1"
0x1800562e1  mov     ecx, ebx
0x1800562e3  mov     edx, 1; dwCmpFlags
0x1800562e8  mov     dword ptr [rsp+0E0h+pbComputedHash], r15d; cchCount2
0x1800562ed  mov     r9d, r15d; cchCount1
0x1800562f0  mov     rax, [rax+rcx*8]
0x1800562f4  lea     ecx, [rdx+7Eh]; Locale
0x1800562f7  mov     [rsp+0E0h+pInfo], rax; lpString2
0x1800562fc  call    cs:__imp_CompareStringA
0x180056302  cmp     eax, r14d
0x180056305  jz      loc_1800563C9
0x18005630b  inc     ebx
0x18005630d  cmp     ebx, [rdi]
0x18005630f  jb      short loc_1800562D6
0x180056311  lea     rax, aEkuNotFoundFor_0; "EKU not found for SubCA"
0x180056318  mov     [rsp+0E0h+pbComputedHash], rax
0x18005631d  mov     [rsp+0E0h+pInfo], r13
0x180056322  xor     edx, edx
0x180056324  xor     ecx, ecx
0x180056326  lea     r9d, [rdx+1]
0x18005632a  lea     r8d, [rdx+20h]
0x18005632e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180056333  jmp     loc_180056557
0x180056338  lea     rdx, [rbp+57h+Buf2]
0x18005633c  mov     rcx, rbx
0x18005633f  test    r15d, r15d
0x180056342  jz      short loc_180056382
0x180056344  mov     r8d, r15d
0x180056347  lea     r9, __ImageBase
0x18005634e  movzx   eax, byte ptr [rdx]
0x180056351  shr     rax, 4
0x180056355  movzx   eax, ds:rva word_18007E100[r9+rax*2]
0x18005635e  mov     [rcx], ax
0x180056361  add     rcx, r14
0x180056364  movzx   eax, byte ptr [rdx]
  ... truncated ...
```
