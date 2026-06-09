# PerformNonNgcSign

- ea: `0x18005810c`
- end: `0x1800584d8`
- name: `PerformNonNgcSign`
- size: `972`
- prototype: `__int64 __usercall@<rax>(HANDLE hToken@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800584e0`

## callees

- `0x180005e34`
- `0x18000bf70`
- `0x1800326fc`
- `0x180056714`
- `0x18005810c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800581ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005822c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005828f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800582f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800581ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005822c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005828f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800582f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058452`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800581aa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800581aa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180058444`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180058444`
- `ncrypt!NCryptFreeObject` at `0x1800583fd`
- `ncrypt!NCryptFreeObject` at `0x1800583fd`
- `CRYPT32!CertFindCertificateInStore` at `0x180058281`
- `CRYPT32!CertFindCertificateInStore` at `0x180058281`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800582ed`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800582ed`
- `CRYPT32!CertFreeCertificateContext` at `0x18005841c`
- `CRYPT32!CertFreeCertificateContext` at `0x18005841c`
- `CRYPT32!CertCloseStore` at `0x180058433`
- `CRYPT32!CertCloseStore` at `0x180058433`
- `CRYPT32!CertOpenStore` at `0x18005821e`
- `CRYPT32!CertOpenStore` at `0x18005821e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180058407`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180058407`

## pseudocode

```c
__int64 __fastcall PerformNonNgcSign(HANDLE hToken, int a2, __int64 a3, __int64 a4, _DWORD *a5, _DWORD *a6, _QWORD *a7)
{
  const CERT_CONTEXT *CertificateInStore; // r14
  HCERTSTORE v11; // rdi
  int v12; // esi
  DWORD LastError; // eax
  unsigned int v14; // ebx
  struct _LIST_ENTRY *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // r9
  DWORD v19; // eax
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+30h] [rbp-20h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+38h] [rbp-18h] BYREF
  _DWORD pvFindPara[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v24; // [rsp+48h] [rbp-8h]
  DWORD pdwKeySpec; // [rsp+A0h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_qdq(WPP_GLOBAL_Control[1].Flink, 119, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, hToken, a2, a4);
  }
  CertificateInStore = 0;
  phCryptProvOrNCryptKey = 0;
  pdwKeySpec = 0;
  *a5 = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  pvFindPara[1] = 0;
  pvFindPara[0] = a2;
  *a6 = 0;
  v24 = a3;
  *a7 = 0;
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    v11 = 0;
    v12 = 0;
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v16 = 120;
LABEL_11:
        v17 = LastError;
LABEL_43:
        WPP_SF_d(v15[1].Flink, v16, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v17);
        goto LABEL_44;
      }
      goto LABEL_45;
    }
LABEL_44:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_45;
  }
  v12 = 1;
  v11 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x18000u, L"MY");
  if ( v11 )
  {
    CertificateInStore = CertFindCertificateInStore(v11, 0x10001u, 0, 0x10000u, pvFindPara, 0);
    if ( CertificateInStore )
    {
      if ( CryptAcquireCertificatePrivateKey(
             CertificateInStore,
             0x20000u,
             0,
             &phCryptProvOrNCryptKey,
             &pdwKeySpec,
             &pfCallerFreeProvOrNCryptKey) )
      {
        LastError = DoDummySign(pdwKeySpec, phCryptProvOrNCryptKey);
        v14 = LastError;
        if ( LastError )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v16 = 124;
            goto LABEL_11;
          }
        }
        else
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            LOBYTE(v18) = 0;
            WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 125, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v18);
            v15 = WPP_GLOBAL_Control;
          }
          v14 = 87;
          if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v15[1].Blink) & 0x2000) != 0
            && BYTE1(v15[1].Blink) >= 2u )
          {
            v16 = 126;
            v17 = 87;
            goto LABEL_43;
          }
        }
        goto LABEL_45;
      }
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v16 = 123;
          goto LABEL_11;
        }
        goto LABEL_45;
      }
    }
    else
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v16 = 122;
          goto LABEL_11;
        }
        goto LABEL_45;
      }
    }
    goto LABEL_44;
  }
  LastError = GetLastError();
  v14 = LastError;
  if ( !LastError )
    goto LABEL_44;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v16 = 121;
    goto LABEL_11;
  }
LABEL_45:
  if ( pfCallerFreeProvOrNCryptKey )
  {
    if ( pdwKeySpec == -1 )
      NCryptFreeObject(phCryptProvOrNCryptKey);
    else
      CryptReleaseContext(phCryptProvOrNCryptKey, 0);
    v15 = WPP_GLOBAL_Control;
  }
  if ( CertificateInStore )
  {
    CertFreeCertificateContext(CertificateInStore);
    v15 = WPP_GLOBAL_Control;
  }
  if ( v11 )
  {
    CertCloseStore(v11, 0);
    v15 = WPP_GLOBAL_Control;
  }
  if ( !v12 )
    goto LABEL_63;
  if ( RevertToSelf() )
    goto LABEL_62;
  if ( v14 )
    goto LABEL_62;
  v19 = GetLastError();
  v14 = v19;
  if ( !v19 )
    goto LABEL_62;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v14;
  if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 127, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v19);
LABEL_62:
    v15 = WPP_GLOBAL_Control;
  }
LABEL_63:
  if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v15[1].Blink) & 0x2000) != 0
    && BYTE1(v15[1].Blink) >= 6u )
  {
    WPP_SF_d(v15[1].Flink, 128, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x18005810c  mov     [rsp-38h+arg_0], rbx
0x180058111  push    rbp
0x180058112  push    rsi
0x180058113  push    rdi
0x180058114  push    r12
0x180058116  push    r13
0x180058118  push    r14
0x18005811a  push    r15
0x18005811c  mov     rbp, rsp
0x18005811f  sub     rsp, 50h
0x180058123  mov     rsi, r8
0x180058126  mov     ebx, edx
0x180058128  mov     rdi, rcx
0x18005812b  mov     rcx, cs:WPP_GLOBAL_Control
0x180058132  lea     r13, WPP_GLOBAL_Control
0x180058139  mov     r12d, 2000h
0x18005813f  cmp     rcx, r13
0x180058142  jz      short loc_180058171
0x180058144  test    [rcx+1Ch], r12d
0x180058148  jz      short loc_180058171
0x18005814a  cmp     byte ptr [rcx+19h], 6
0x18005814e  jb      short loc_180058171
0x180058150  mov     rcx, [rcx+10h]
0x180058154  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x18005815b  mov     [rsp+50h+pPrevCertContext], r9
0x180058160  mov     edx, 77h ; 'w'
0x180058165  mov     r9, rdi
0x180058168  mov     dword ptr [rsp+50h+pvPara], ebx
0x18005816c  call    WPP_SF_qdq
0x180058171  mov     rax, [rbp+arg_20]
0x180058175  xor     r15d, r15d
0x180058178  mov     rcx, rdi; hToken
0x18005817b  mov     [rbp+arg_8], r15d
0x18005817f  mov     r14d, r15d
0x180058182  mov     [rbp+phCryptProvOrNCryptKey], r15
0x180058186  mov     [rbp+pdwKeySpec], r15d
0x18005818a  mov     [rax], r15d
0x18005818d  mov     rax, [rbp+arg_28]
0x180058191  mov     [rbp+pfCallerFreeProvOrNCryptKey], r15d
0x180058195  mov     [rbp+var_C], r15d
0x180058199  mov     [rbp+pvFindPara], ebx
0x18005819c  mov     [rax], r15d
0x18005819f  mov     rax, [rbp+arg_30]
0x1800581a3  mov     [rbp+var_8], rsi
0x1800581a7  mov     [rax], r15
0x1800581aa  call    cs:__imp_ImpersonateLoggedOnUser
0x1800581b0  test    eax, eax
0x1800581b2  jnz     short loc_1800581FA
0x1800581b4  mov     edi, r15d
0x1800581b7  mov     esi, r15d
0x1800581ba  call    cs:__imp_GetLastError
0x1800581c0  mov     ebx, eax
0x1800581c2  test    eax, eax
0x1800581c4  jz      loc_1800583E6
0x1800581ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800581d1  cmp     rcx, r13
0x1800581d4  jz      loc_1800583ED
0x1800581da  test    [rcx+1Ch], r12d
0x1800581de  jz      loc_1800583ED
0x1800581e4  cmp     byte ptr [rcx+19h], 2
0x1800581e8  jb      loc_1800583ED
0x1800581ee  lea     edx, [r15+78h]
0x1800581f2  mov     r9d, eax
0x1800581f5  jmp     loc_1800583D6
0x1800581fa  lea     rax, aMy_0; "MY"
0x180058201  mov     esi, 1
0x180058206  mov     ebx, 10001h
0x18005820b  mov     [rsp+50h+pvPara], rax; pvPara
0x180058210  mov     r9d, 18000h; dwFlags
0x180058216  xor     r8d, r8d; hCryptProv
0x180058219  mov     edx, ebx; dwEncodingType
0x18005821b  lea     ecx, [rsi+9]; lpszStoreProvider
0x18005821e  call    cs:__imp_CertOpenStore
0x180058224  mov     rdi, rax
0x180058227  test    rax, rax
0x18005822a  jnz     short loc_180058265
0x18005822c  call    cs:__imp_GetLastError
0x180058232  mov     ebx, eax
0x180058234  test    eax, eax
0x180058236  jz      loc_1800583E6
0x18005823c  mov     rcx, cs:WPP_GLOBAL_Control
0x180058243  cmp     rcx, r13
0x180058246  jz      loc_1800583ED
0x18005824c  test    [rcx+1Ch], r12d
0x180058250  jz      loc_1800583ED
0x180058256  cmp     byte ptr [rcx+19h], 2
0x18005825a  jb      loc_1800583ED
0x180058260  lea     edx, [rsi+78h]
0x180058263  jmp     short loc_1800581F2
0x180058265  lea     rax, [rbp+pvFindPara]
0x180058269  mov     [rsp+50h+pPrevCertContext], r15; pPrevCertContext
0x18005826e  mov     r9d, 10000h; dwFindType
0x180058274  mov     [rsp+50h+pvPara], rax; pvFindPara
0x180058279  xor     r8d, r8d; dwFindFlags
0x18005827c  mov     edx, ebx; dwCertEncodingType
0x18005827e  mov     rcx, rdi; hCertStore
0x180058281  call    cs:__imp_CertFindCertificateInStore
0x180058287  mov     r14, rax
0x18005828a  test    rax, rax
0x18005828d  jnz     short loc_1800582CC
0x18005828f  call    cs:__imp_GetLastError
0x180058295  mov     ebx, eax
0x180058297  test    eax, eax
0x180058299  jz      loc_1800583E6
0x18005829f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800582a6  cmp     rcx, r13
0x1800582a9  jz      loc_1800583ED
0x1800582af  test    [rcx+1Ch], r12d
0x1800582b3  jz      loc_1800583ED
0x1800582b9  cmp     byte ptr [rcx+19h], 2
0x1800582bd  jb      loc_1800583ED
0x1800582c3  lea     edx, [r14+7Ah]
0x1800582c7  jmp     loc_1800581F2
0x1800582cc  lea     rax, [rbp+pfCallerFreeProvOrNCryptKey]
0x1800582d0  xor     r8d, r8d; pvParameters
0x1800582d3  mov     [rsp+50h+pPrevCertContext], rax; pfCallerFreeProvOrNCryptKey
0x1800582d8  lea     r9, [rbp+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x1800582dc  lea     rax, [rbp+pdwKeySpec]
0x1800582e0  mov     edx, 20000h; dwFlags
0x1800582e5  mov     rcx, r14; pCert
0x1800582e8  mov     [rsp+50h+pvPara], rax; pdwKeySpec
0x1800582ed  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x1800582f3  test    eax, eax
0x1800582f5  jnz     short loc_180058335
0x1800582f7  call    cs:__imp_GetLastError
0x1800582fd  mov     ebx, eax
0x1800582ff  test    eax, eax
0x180058301  jz      loc_1800583E6
0x180058307  mov     rcx, cs:WPP_GLOBAL_Control
0x18005830e  cmp     rcx, r13
0x180058311  jz      loc_1800583ED
0x180058317  test    [rcx+1Ch], r12d
0x18005831b  jz      loc_1800583ED
0x180058321  cmp     byte ptr [rcx+19h], 2
0x180058325  jb      loc_1800583ED
0x18005832b  mov     edx, 7Bh ; '{'
0x180058330  jmp     loc_1800581F2
0x180058335  mov     rdx, [rbp+phCryptProvOrNCryptKey]; hProv
0x180058339  lea     r9, [rbp+arg_8]
0x18005833d  mov     ecx, [rbp+pdwKeySpec]; dwKeySpec
0x180058340  mov     r8d, esi
0x180058343  call    DoDummySign
0x180058348  mov     ebx, eax
0x18005834a  test    eax, eax
0x18005834c  jz      short loc_180058378
0x18005834e  mov     rcx, cs:WPP_GLOBAL_Control
0x180058355  cmp     rcx, r13
0x180058358  jz      loc_1800583ED
0x18005835e  test    [rcx+1Ch], r12d
0x180058362  jz      loc_1800583ED
0x180058368  cmp     byte ptr [rcx+19h], 2
0x18005836c  jb      short loc_1800583ED
0x18005836e  mov     edx, 7Ch ; '|'
0x180058373  jmp     loc_1800581F2
0x180058378  mov     rcx, cs:WPP_GLOBAL_Control
0x18005837f  cmp     rcx, r13
0x180058382  jz      short loc_1800583B4
0x180058384  test    [rcx+1Ch], r12d
0x180058388  jz      short loc_1800583B4
0x18005838a  cmp     byte ptr [rcx+19h], 5
0x18005838e  jb      short loc_1800583B4
0x180058390  cmp     [rbp+arg_8], r15d
0x180058394  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x18005839b  mov     rcx, [rcx+10h]
0x18005839f  mov     edx, 7Dh ; '}'
0x1800583a4  setnz   r9b
0x1800583a8  call    WPP_SF_c
0x1800583ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800583b4  cmp     [rbp+arg_8], r15d
0x1800583b8  jnz     short loc_1800583ED
0x1800583ba  mov     ebx, 57h ; 'W'
0x1800583bf  cmp     rcx, r13
0x1800583c2  jz      short loc_1800583ED
0x1800583c4  test    [rcx+1Ch], r12d
0x1800583c8  jz      short loc_1800583ED
0x1800583ca  cmp     byte ptr [rcx+19h], 2
0x1800583ce  jb      short loc_1800583ED
0x1800583d0  lea     edx, [rbx+27h]
0x1800583d3  mov     r9d, ebx
0x1800583d6  mov     rcx, [rcx+10h]
0x1800583da  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x1800583e1  call    WPP_SF_d
0x1800583e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800583ed  cmp     [rbp+pfCallerFreeProvOrNCryptKey], r15d
0x1800583f1  jz      short loc_180058414
0x1800583f3  cmp     [rbp+pdwKeySpec], 0FFFFFFFFh
0x1800583f7  mov     rcx, [rbp+phCryptProvOrNCryptKey]; hProv
0x1800583fb  jnz     short loc_180058405
0x1800583fd  call    cs:__imp_NCryptFreeObject
0x180058403  jmp     short loc_18005840D
0x180058405  xor     edx, edx; dwFlags
0x180058407  call    cs:__imp_CryptReleaseContext
0x18005840d  mov     rcx, cs:WPP_GLOBAL_Control
0x180058414  test    r14, r14
0x180058417  jz      short loc_180058429
0x180058419  mov     rcx, r14; pCertContext
0x18005841c  call    cs:__imp_CertFreeCertificateContext
0x180058422  mov     rcx, cs:WPP_GLOBAL_Control
0x180058429  test    rdi, rdi
0x18005842c  jz      short loc_180058440
0x18005842e  xor     edx, edx; dwFlags
0x180058430  mov     rcx, rdi; hCertStore
0x180058433  call    cs:__imp_CertCloseStore
0x180058439  mov     rcx, cs:WPP_GLOBAL_Control
0x180058440  test    esi, esi
0x180058442  jz      short loc_180058495
0x180058444  call    cs:__imp_RevertToSelf
0x18005844a  test    eax, eax
0x18005844c  jnz     short loc_18005848E
0x18005844e  test    ebx, ebx
0x180058450  jnz     short loc_18005848E
0x180058452  call    cs:__imp_GetLastError
0x180058458  mov     ebx, eax
0x18005845a  test    eax, eax
0x18005845c  jz      short loc_18005848E
0x18005845e  mov     rcx, cs:WPP_GLOBAL_Control
0x180058465  cmp     rcx, r13
0x180058468  jz      short loc_1800584BE
0x18005846a  test    [rcx+1Ch], r12d
0x18005846e  jz      short loc_180058495
0x180058470  cmp     byte ptr [rcx+19h], 2
0x180058474  jb      short loc_180058495
0x180058476  mov     rcx, [rcx+10h]
0x18005847a  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x180058481  mov     edx, 7Fh
0x180058486  mov     r9d, eax
0x180058489  call    WPP_SF_d
0x18005848e  mov     rcx, cs:WPP_GLOBAL_Control
0x180058495  cmp     rcx, r13
0x180058498  jz      short loc_1800584BE
0x18005849a  test    [rcx+1Ch], r12d
0x18005849e  jz      short loc_1800584BE
0x1800584a0  cmp     byte ptr [rcx+19h], 6
0x1800584a4  jb      short loc_1800584BE
0x1800584a6  mov     rcx, [rcx+10h]
0x1800584aa  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x1800584b1  mov     edx, 80h
0x1800584b6  mov     r9d, ebx
0x1800584b9  call    WPP_SF_d
0x1800584be  mov     eax, ebx
0x1800584c0  mov     rbx, [rsp+50h+arg_0]
0x1800584c8  add     rsp, 50h
0x1800584cc  pop     r15
0x1800584ce  pop     r14
0x1800584d0  pop     r13
0x1800584d2  pop     r12
0x1800584d4  pop     rdi
0x1800584d5  pop     rsi
0x1800584d6  pop     rbp
0x1800584d7  retn
```
