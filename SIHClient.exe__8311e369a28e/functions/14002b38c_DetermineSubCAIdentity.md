# DetermineSubCAIdentity

- ea: `0x14002b38c`
- end: `0x14002bb10`
- name: `DetermineSubCAIdentity`
- size: `1924`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14002cbd8`
- `0x14002cef0`

## callees

- `0x140008de4`
- `0x14000cdb8`
- `0x14000ce30`
- `0x14000ce9c`
- `0x1400154b4`
- `0x14002b38c`
- `0x14002d480`
- `0x14002d58c`
- `0x14002e004`
- `0x14002e080`
- `0x140045dc0`
- `0x140045de4`
- `0x14004d7c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b47f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b49a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b47f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b49a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14002babf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14002babf`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x14002b475`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x14002b475`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14002b885`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14002b8be`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14002b885`
- `CRYPT32!CertGetEnhancedKeyUsage` at `0x14002b8be`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x14002b79c`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x14002b8fa`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x14002b79c`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x14002b8fa`

## string_xrefs

- `0x14002b721`: `C:\__w\1\s\src\Client\lib\util\commonutil.cpp`

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
  char v49; // [rsp+48h] [rbp-49h]
  int v50; // [rsp+4Ch] [rbp-45h]
  PCNZWCH lpString2; // [rsp+50h] [rbp-41h] BYREF
  PCNZWCH lpString1; // [rsp+58h] [rbp-39h] BYREF
  __int64 v53; // [rsp+60h] [rbp-31h]
  size_t Size; // [rsp+68h] [rbp-29h]
  __int64 v55; // [rsp+70h] [rbp-21h]
  PCCERT_CONTEXT pCertContext; // [rsp+78h] [rbp-19h]
  void *lpMem; // [rsp+80h] [rbp-11h]
  __int64 v58; // [rsp+88h] [rbp-9h]
  __int64 v59; // [rsp+90h] [rbp-1h]
  DWORD pcbUsage; // [rsp+98h] [rbp+7h] BYREF
  DWORD pcbComputedHash; // [rsp+9Ch] [rbp+Bh] BYREF
  BYTE Buf2[16]; // [rsp+A0h] [rbp+Fh] BYREF
  __int128 v63; // [rsp+B0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v58 = a3;
  LODWORD(lpString2) = a2;
  pcbComputedHash = 32;
  v3 = 0;
  lpMem = 0;
  CertHashAlgorithm = 0;
  *(_OWORD *)Buf2 = 0;
  v63 = 0;
  if ( !a1 )
  {
    CertHashAlgorithm = -2147467261;
    goto LABEL_84;
  }
  v5 = **(_QWORD **)(a1 + 16);
  v55 = v5;
  if ( *(_DWORD *)(v5 + 12) != 3 )
  {
    WUTrace(0, 0, 32, 1, 0, L"Cert chain length check failed, length=%d");
    LODWORD(v3) = 1;
    goto LABEL_84;
  }
  v59 = *(_QWORD *)(*(_QWORD *)(v5 + 16) + 8LL);
  pCertContext = *(PCCERT_CONTEXT *)(v59 + 8);
  if ( !CryptHashPublicKeyInfo(
          0,
          0x800Cu,
          0,
          1u,
          &pCertContext->pCertInfo->SubjectPublicKeyInfo,
          Buf2,
          &pcbComputedHash) )
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
  if ( pcbComputedHash != 32 )
    goto LABEL_84;
  v50 = 1;
  pcbUsage = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl);
  v10 = pcbComputedHash;
  v11 = 0;
  if ( IsEnabled )
  {
    v49 = 0;
    v12 = 2;
    LODWORD(lpString1) = pcbComputedHash;
    v13 = pcbComputedHash;
    Size = pcbComputedHash;
    do
    {
      v14 = 0;
      while ( 1 )
      {
        v53 = v14;
        if ( !memcmp(&qword_14006A620[6 * v3 + 6 * v14], Buf2, v13) )
          break;
        ++v14;
        v13 = v10;
        if ( v14 >= 5 )
        {
          v15 = v49;
          goto LABEL_21;
        }
      }
      v50 = dword_14006A610[12 * v11 + 12 * v53];
      v15 = 1;
      v49 = 1;
      pcbUsage = dword_14006A614[12 * v11 + 12 * v53];
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
          v53 = v19;
          if ( !memcmp(&qword_14006A2B0[6 * v17 + 6 * v19], Buf2, Size) )
            break;
          if ( ++v19 >= 9 )
            goto LABEL_29;
        }
        v20 = dword_14006A2A0[12 * v16 + 12 * v53];
        pcbUsage = dword_14006A2A4[12 * v16 + 12 * v53];
        v50 = v20;
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
    v21 = pcbComputedHash;
    v22 = 2;
    do
    {
      v23 = 0;
      while ( 1 )
      {
        Size = v23;
        if ( !memcmp(&qword_14006A620[6 * v3 + 6 * v23], Buf2, v21) )
          break;
        ++v23;
        v21 = v10;
        if ( v23 >= 5 )
          goto LABEL_37;
      }
      v24 = dword_14006A610[12 * v11 + 12 * Size];
      pcbUsage = dword_14006A614[12 * v11 + 12 * Size];
      v50 = v24;
LABEL_37:
      v3 += 5;
      v11 += 5;
      v21 = v10;
      --v22;
    }
    while ( v22 );
  }
  LODWORD(v3) = v50;
  if ( v50 == 1 )
  {
    if ( !(_DWORD)lpString2 || !v58 )
      goto LABEL_46;
    v25 = 0;
    while ( *(_DWORD *)(v58 + 24 * v25 + 8) != 32
         || memcmp(*(const void **)(v58 + 24 * v25 + 16), Buf2, (unsigned int)v10) )
    {
      v25 = (unsigned int)(v25 + 1);
      if ( (unsigned int)v25 >= (unsigned int)lpString2 )
      {
        LODWORD(v3) = 1;
        goto LABEL_46;
      }
    }
    LODWORD(v3) = *(_DWORD *)(v58 + 24 * v25);
    v27 = *(_DWORD *)(v58 + 24 * v25 + 4);
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
            *v31 = word_140054740[(unsigned __int64)*v30 >> 4];
            v33 = v31 + 1;
            v34 = *v30++;
            *v33 = word_140054740[v34 & 0xF];
            v31 = v33 + 1;
            --v32;
          }
          while ( v32 );
        }
        *v31 = 0;
        WUTrace(0, 0, 32, 1, 0, L"Hash of public key doesn't match the known values, cbKeyId=%d, rgbKeyId=%ws.");
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
    v29 = *(_QWORD *)(v59 + 40);
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
    v35 = v55;
    pcbUsage = 0;
    v36 = *(__int64 **)(v55 + 16);
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
    v35 = v55;
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
    WUTrace(0, 0, 32, 1, 0, L"Inconsistent hash algorithm. Leaf:%ws, SubCA:%ws");
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
0x14002b38c  mov     rax, rsp
0x14002b38f  mov     [rax+10h], rbx
0x14002b393  mov     [rax+18h], rsi
0x14002b397  mov     [rax+20h], rdi
0x14002b39b  push    rbp
0x14002b39c  push    r12
0x14002b39e  push    r13
0x14002b3a0  push    r14
0x14002b3a2  push    r15
0x14002b3a4  lea     rbp, [rax-5Fh]
0x14002b3a8  sub     rsp, 0C0h
0x14002b3af  mov     rax, cs:__security_cookie
0x14002b3b6  xor     rax, rsp
0x14002b3b9  mov     [rbp+57h+var_28], rax
0x14002b3bd  xor     r13d, r13d
0x14002b3c0  mov     [rbp+57h+var_60], r8
0x14002b3c4  mov     dword ptr [rbp+57h+lpString2], edx
0x14002b3c7  xorps   xmm0, xmm0
0x14002b3ca  mov     [rbp+57h+var_4C], 20h ; ' '
0x14002b3d1  mov     r12d, r13d
0x14002b3d4  mov     [rbp+57h+lpMem], r13
0x14002b3d8  mov     esi, r13d
0x14002b3db  movups  xmmword ptr [rbp+57h+Buf2], xmm0
0x14002b3df  movups  [rbp+57h+var_38], xmm0
0x14002b3e3  test    rcx, rcx
0x14002b3e6  jnz     short loc_14002B3F2
0x14002b3e8  mov     esi, 80004003h
0x14002b3ed  jmp     loc_14002B9F7
0x14002b3f2  mov     rax, [rcx+10h]
0x14002b3f6  mov     r9d, 1; dwCertEncodingType
0x14002b3fc  mov     rcx, [rax]
0x14002b3ff  mov     [rbp+57h+var_78], rcx
0x14002b403  mov     eax, [rcx+0Ch]
0x14002b406  cmp     eax, 3
0x14002b409  jz      short loc_14002B438
0x14002b40b  mov     dword ptr [rsp+0E0h+pcbComputedHash], eax
0x14002b40f  lea     r8d, [r9+1Fh]
0x14002b413  lea     rax, aCertChainLengt; "Cert chain length check failed, length="...
0x14002b41a  xor     edx, edx
0x14002b41c  mov     [rsp+0E0h+pbComputedHash], rax
0x14002b421  xor     ecx, ecx
0x14002b423  mov     [rsp+0E0h+pInfo], r13
0x14002b428  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002b42d  mov     r12d, 1
0x14002b433  jmp     loc_14002B9F7
0x14002b438  mov     rax, [rcx+10h]
0x14002b43c  xor     r8d, r8d; dwFlags
0x14002b43f  lea     rcx, [rbp+57h+var_4C]
0x14002b443  mov     edx, 800Ch; Algid
0x14002b448  mov     [rsp+0E0h+pcbComputedHash], rcx; pcbComputedHash
0x14002b44d  lea     rcx, [rbp+57h+Buf2]
0x14002b451  mov     [rsp+0E0h+pbComputedHash], rcx; pbComputedHash
0x14002b456  xor     ecx, ecx; hCryptProv
0x14002b458  mov     rax, [rax+8]
0x14002b45c  mov     [rbp+57h+var_58], rax
0x14002b460  mov     rax, [rax+8]
0x14002b464  mov     [rbp+57h+pCertContext], rax
0x14002b468  mov     rax, [rax+18h]
0x14002b46c  add     rax, 60h ; '`'
0x14002b470  mov     [rsp+0E0h+pInfo], rax; int
0x14002b475  call    cs:__imp_CryptHashPublicKeyInfo
0x14002b47b  test    eax, eax
0x14002b47d  jnz     short loc_14002B4B9
0x14002b47f  call    cs:__imp_GetLastError
0x14002b485  mov     ecx, eax
0x14002b487  mov     ebx, 80070000h
0x14002b48c  movzx   eax, ax
0x14002b48f  or      eax, ebx
0x14002b491  test    ecx, ecx
0x14002b493  cmovle  eax, ecx
0x14002b496  test    eax, eax
0x14002b498  jns     short loc_14002B4AF
0x14002b49a  call    cs:__imp_GetLastError
0x14002b4a0  movzx   esi, ax
0x14002b4a3  or      esi, ebx
0x14002b4a5  test    eax, eax
0x14002b4a7  cmovle  esi, eax
0x14002b4aa  jmp     loc_14002B9F7
0x14002b4af  mov     esi, 80004005h
0x14002b4b4  jmp     loc_14002B9F7
0x14002b4b9  cmp     [rbp+57h+var_4C], 20h ; ' '
0x14002b4bd  mov     esi, 8024B303h
0x14002b4c2  jnz     loc_14002B9F7
0x14002b4c8  mov     [rbp+57h+var_9C], 1
0x14002b4cf  mov     [rbp+57h+pcbUsage], r13d
0x14002b4d3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x14002b4da  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x14002b4df  mov     r15d, [rbp+57h+var_4C]
0x14002b4e3  mov     rdi, r13
0x14002b4e6  mov     r14d, 2
0x14002b4ec  test    al, al
0x14002b4ee  jz      loc_14002B619
0x14002b4f4  mov     [rbp+57h+var_A0], r13b
0x14002b4f8  lea     rdx, qword_14006A620
0x14002b4ff  mov     r13d, r14d
0x14002b502  mov     dword ptr [rbp+57h+lpString1], r15d
0x14002b506  mov     r8d, r15d; Size
0x14002b509  mov     [rbp+57h+Size], r15
0x14002b50d  xor     ebx, ebx
0x14002b50f  mov     eax, ebx
0x14002b511  mov     [rbp+57h+var_88], rax
0x14002b515  add     rax, r12
0x14002b518  lea     rcx, [rax+rax*2]
0x14002b51c  shl     rcx, 4
0x14002b520  add     rcx, rdx; Buf1
0x14002b523  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14002b527  call    memcmp
0x14002b52c  test    eax, eax
0x14002b52e  jz      short loc_14002B546
0x14002b530  inc     ebx
0x14002b532  lea     rdx, qword_14006A620
0x14002b539  mov     r8, r15
0x14002b53c  cmp     ebx, 5
0x14002b53f  jb      short loc_14002B50F
0x14002b541  mov     al, [rbp+57h+var_A0]
0x14002b544  jmp     short loc_14002B574
0x14002b546  mov     rax, [rbp+57h+var_88]
0x14002b54a  lea     rdx, __ImageBase
0x14002b551  add     rax, rdi
0x14002b554  lea     rcx, [rax+rax*2]
0x14002b558  add     rcx, rcx
0x14002b55b  mov     eax, ds:rva dword_14006A610[rdx+rcx*8]
0x14002b562  mov     ecx, ds:rva dword_14006A614[rdx+rcx*8]
0x14002b569  mov     [rbp+57h+var_9C], eax
0x14002b56c  mov     al, 1
0x14002b56e  mov     [rbp+57h+var_A0], al
0x14002b571  mov     [rbp+57h+pcbUsage], ecx
0x14002b574  add     r12, 5
0x14002b578  lea     rdx, qword_14006A620
0x14002b57f  add     rdi, 5
0x14002b583  mov     r8, r15
0x14002b586  sub     r13, 1
0x14002b58a  jnz     short loc_14002B50D
0x14002b58c  xor     r13d, r13d
0x14002b58f  test    al, al
0x14002b591  jnz     loc_14002B6A3
0x14002b597  mov     edi, r13d
0x14002b59a  lea     r15, __ImageBase
0x14002b5a1  mov     r12d, r13d
0x14002b5a4  mov     r13, r14
0x14002b5a7  xor     ebx, ebx
0x14002b5a9  mov     r8, [rbp+57h+Size]; Size
0x14002b5ad  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14002b5b1  mov     eax, ebx
0x14002b5b3  mov     [rbp+57h+var_88], rax
0x14002b5b7  add     rax, r12
0x14002b5ba  lea     rcx, [rax+rax*2]
0x14002b5be  shl     rcx, 4
0x14002b5c2  lea     rax, qword_14006A2B0
0x14002b5c9  add     rcx, rax; Buf1
0x14002b5cc  call    memcmp
0x14002b5d1  test    eax, eax
0x14002b5d3  jz      short loc_14002B5DE
0x14002b5d5  inc     ebx
0x14002b5d7  cmp     ebx, 9
0x14002b5da  jb      short loc_14002B5A9
0x14002b5dc  jmp     short loc_14002B602
0x14002b5de  mov     rax, [rbp+57h+var_88]
0x14002b5e2  add     rax, rdi
0x14002b5e5  lea     rcx, [rax+rax*2]
0x14002b5e9  add     rcx, rcx
0x14002b5ec  mov     eax, ds:rva dword_14006A2A0[r15+rcx*8]
0x14002b5f4  mov     ecx, ds:rva dword_14006A2A4[r15+rcx*8]
0x14002b5fc  mov     [rbp+57h+pcbUsage], ecx
0x14002b5ff  mov     [rbp+57h+var_9C], eax
0x14002b602  add     r12, 9
0x14002b606  add     rdi, 9
0x14002b60a  sub     r13, 1
0x14002b60e  jnz     short loc_14002B5A7
0x14002b610  mov     r15d, dword ptr [rbp+57h+lpString1]
0x14002b614  jmp     loc_14002B6A0
0x14002b619  mov     rdx, r15
0x14002b61c  lea     r8, qword_14006A620
0x14002b623  mov     r13, r14
0x14002b626  xor     ebx, ebx
0x14002b628  mov     eax, ebx
0x14002b62a  mov     [rbp+57h+Size], rax
0x14002b62e  add     rax, r12
0x14002b631  lea     rcx, [rax+rax*2]
0x14002b635  shl     rcx, 4
0x14002b639  add     rcx, r8; Buf1
0x14002b63c  mov     r8, rdx; Size
0x14002b63f  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14002b643  call    memcmp
0x14002b648  test    eax, eax
0x14002b64a  jz      short loc_14002B65F
0x14002b64c  inc     ebx
0x14002b64e  lea     r8, qword_14006A620
0x14002b655  mov     rdx, r15
0x14002b658  cmp     ebx, 5
0x14002b65b  jb      short loc_14002B628
0x14002b65d  jmp     short loc_14002B688
0x14002b65f  mov     rax, [rbp+57h+Size]
0x14002b663  lea     rdx, __ImageBase
0x14002b66a  add     rax, rdi
0x14002b66d  lea     rcx, [rax+rax*2]
0x14002b671  add     rcx, rcx
0x14002b674  mov     eax, ds:rva dword_14006A610[rdx+rcx*8]
0x14002b67b  mov     ecx, ds:rva dword_14006A614[rdx+rcx*8]
0x14002b682  mov     [rbp+57h+pcbUsage], ecx
0x14002b685  mov     [rbp+57h+var_9C], eax
0x14002b688  add     r12, 5
0x14002b68c  lea     r8, qword_14006A620
0x14002b693  add     rdi, 5
0x14002b697  mov     rdx, r15
0x14002b69a  sub     r13, 1
0x14002b69e  jnz     short loc_14002B626
0x14002b6a0  xor     r13d, r13d
0x14002b6a3  mov     r12d, [rbp+57h+var_9C]
0x14002b6a7  cmp     r12d, 1
0x14002b6ab  jnz     loc_14002B861
0x14002b6b1  cmp     dword ptr [rbp+57h+lpString2], r13d
0x14002b6b5  jbe     short loc_14002B6F4
0x14002b6b7  mov     r13, [rbp+57h+var_60]
0x14002b6bb  test    r13, r13
0x14002b6be  jz      short loc_14002B6F1
0x14002b6c0  xor     ebx, ebx
0x14002b6c2  mov     r12d, r15d
0x14002b6c5  lea     rdi, [rbx+rbx*2]
0x14002b6c9  cmp     dword ptr [r13+rdi*8+8], 20h ; ' '
0x14002b6cf  jnz     short loc_14002B6E6
0x14002b6d1  mov     rcx, [r13+rdi*8+10h]; Buf1
0x14002b6d6  lea     rdx, [rbp+57h+Buf2]; Buf2
0x14002b6da  mov     r8, r12; Size
0x14002b6dd  call    memcmp
0x14002b6e2  test    eax, eax
0x14002b6e4  jz      short loc_14002B747
0x14002b6e6  inc     ebx
0x14002b6e8  cmp     ebx, dword ptr [rbp+57h+lpString2]
0x14002b6eb  jb      short loc_14002B6C5
0x14002b6ed  mov     r12d, [rbp+57h+var_9C]
0x14002b6f1  xor     r13d, r13d
0x14002b6f4  lea     ecx, ds:1[r15*2]; unsigned __int64
0x14002b6fc  mov     rdx, r14; unsigned __int64
0x14002b6ff  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x14002b704  mov     rbx, rax
0x14002b707  neg     rax
0x14002b70a  sbb     edi, edi
0x14002b70c  not     edi
0x14002b70e  and     edi, 8007000Eh
0x14002b714  test    rbx, rbx
0x14002b717  jnz     loc_14002B7D8
0x14002b71d  mov     rcx, [rbp+5Fh]; this
0x14002b721  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14002b728  mov     r9d, edi; char *
0x14002b72b  mov     edx, 0E8h; void *
0x14002b730  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002b735  lea     rax, aHashOfPublicKe; "Hash of public key doesn't match the kn"...
0x14002b73c  mov     [rsp+0E0h+pbComputedHash], rax
0x14002b741  mov     dword ptr [rsp+0E0h+pInfo], edi
0x14002b745  jmp     short loc_14002B7C2
0x14002b747  mov     r12d, [r13+rdi*8+0]
0x14002b74c  mov     eax, [r13+rdi*8+4]
0x14002b751  cmp     r12d, 1
0x14002b755  jz      short loc_14002B6F1
0x14002b757  xor     r13d, r13d
0x14002b75a  or      r15d, 0FFFFFFFFh
0x14002b75e  test    eax, eax
0x14002b760  jz      loc_14002B937
0x14002b766  mov     rdi, [rbp+57h+var_58]
0x14002b76a  mov     ebx, r13d
0x14002b76d  mov     rdi, [rdi+28h]
0x14002b771  cmp     [rdi], r13d
0x14002b774  jbe     short loc_14002B7B1
0x14002b776  mov     rax, [rdi+8]
0x14002b77a  lea     r8, String1; "1.3.6.1.4.1.311.76.6.1"
0x14002b781  mov     ecx, ebx
0x14002b783  mov     edx, 1; dwCmpFlags
0x14002b788  mov     dword ptr [rsp+0E0h+pbComputedHash], r15d; cchCount2
0x14002b78d  mov     r9d, r15d; cchCount1
0x14002b790  mov     rax, [rax+rcx*8]
0x14002b794  lea     ecx, [rdx+7Eh]; Locale
0x14002b797  mov     [rsp+0E0h+pInfo], rax; lpString2
0x14002b79c  call    cs:__imp_CompareStringA
0x14002b7a2  cmp     eax, r14d
0x14002b7a5  jz      loc_14002B869
0x14002b7ab  inc     ebx
0x14002b7ad  cmp     ebx, [rdi]
0x14002b7af  jb      short loc_14002B776
0x14002b7b1  lea     rax, aEkuNotFoundFor_0; "EKU not found for SubCA"
0x14002b7b8  mov     [rsp+0E0h+pbComputedHash], rax
0x14002b7bd  mov     [rsp+0E0h+pInfo], r13
0x14002b7c2  xor     edx, edx
0x14002b7c4  xor     ecx, ecx
0x14002b7c6  lea     r9d, [rdx+1]
0x14002b7ca  lea     r8d, [rdx+20h]
0x14002b7ce  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002b7d3  jmp     loc_14002B9F7
0x14002b7d8  lea     rdx, [rbp+57h+Buf2]
0x14002b7dc  mov     rcx, rbx
0x14002b7df  test    r15d, r15d
0x14002b7e2  jz      short loc_14002B822
0x14002b7e4  mov     r8d, r15d
0x14002b7e7  lea     r9, __ImageBase
0x14002b7ee  movzx   eax, byte ptr [rdx]
0x14002b7f1  shr     rax, 4
0x14002b7f5  movzx   eax, ds:rva word_140054740[r9+rax*2]
0x14002b7fe  mov     [rcx], ax
0x14002b801  add     rcx, r14
0x14002b804  movzx   eax, byte ptr [rdx]
  ... truncated ...
```
