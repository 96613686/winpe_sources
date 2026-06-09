# I_ReaderListCngPopulateCredsViaCertStore

- ea: `0x180016500`
- end: `0x180016952`
- name: `I_ReaderListCngPopulateCredsViaCertStore`
- size: `1106`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x1800135d0`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x1800157fc`
- `0x1800160c8`
- `0x180016500`
- `0x18001bfd4`
- `0x18001cc6c`
- `0x18001dd7c`
- `0x18001e020`
- `0x18001e0e0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001684b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800167b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001684b`
- `CRYPT32!CertCloseStore` at `0x1800168c0`
- `CRYPT32!CertCloseStore` at `0x1800168c0`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180016688`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180016760`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180016688`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180016760`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18001666a`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18001666a`
- `ncrypt!NCryptGetProperty` at `0x180016619`
- `ncrypt!NCryptGetProperty` at `0x180016619`

## pseudocode

```c
__int64 __fastcall I_ReaderListCngPopulateCredsViaCertStore(__int64 a1, unsigned __int16 *a2, _QWORD *a3, _DWORD *a4)
{
  int *p_pcbData; // rdi
  __int64 v7; // rcx
  DWORD LastError; // ebx
  unsigned int Property; // r12d
  _QWORD *v10; // rcx
  int v11; // edx
  NCRYPT_HANDLE v12; // rcx
  __int64 v13; // rcx
  const CERT_CONTEXT *v14; // r14
  const CERT_CONTEXT *v15; // rax
  unsigned __int64 v16; // rsi
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  int *v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rcx
  int v24; // edx
  __int64 v25; // rcx
  int *v26; // rcx
  char v27; // al
  __int64 v29; // [rsp+0h] [rbp-30h] BYREF
  DWORD *pcbResult; // [rsp+20h] [rbp-10h]
  DWORD pcbData; // [rsp+30h] [rbp+0h] BYREF
  BYTE pbOutput[8]; // [rsp+38h] [rbp+8h] BYREF
  _QWORD *v33; // [rsp+40h] [rbp+10h] BYREF
  __int64 v34; // [rsp+48h] [rbp+18h]
  unsigned __int16 *v35; // [rsp+50h] [rbp+20h]

  p_pcbData = 0;
  v35 = a2;
  pcbData = 0;
  v33 = 0;
  v34 = a1;
  *(_QWORD *)pbOutput = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  LastError = I_SetupNCryptStorageProvider(a3);
  if ( LastError )
  {
    Property = 0;
    WppTraceIndent(v7, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_51;
    }
    v11 = 149;
    LODWORD(pcbResult) = LastError;
    goto LABEL_10;
  }
  v12 = a3[17];
  pcbData = 8;
  Property = NCryptGetProperty(v12, L"SmartCardUserCertStore", pbOutput, 8u, &pcbData, 0x40u);
  if ( Property )
  {
    WppTraceIndent(v13, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_51;
    }
    v11 = 150;
    LODWORD(pcbResult) = Property;
LABEL_10:
    WPP_SF_sd(
      v10[2],
      v11,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      (char)pcbResult);
    goto LABEL_51;
  }
  v14 = 0;
  while ( 1 )
  {
    v15 = CertEnumCertificatesInStore(*(HCERTSTORE *)pbOutput, v14);
    v14 = v15;
    if ( !v15 )
    {
      a3[21] = *(_QWORD *)pbOutput;
      *(_QWORD *)pbOutput = 0;
      goto LABEL_51;
    }
    if ( !CertGetCertificateContextProperty(v15, 2u, 0, &pcbData) )
    {
      LastError = GetLastError();
      WppTraceIndent(v25, 2);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_51;
      }
      v24 = 151;
LABEL_49:
      WPP_SF_sd(v23[2], v24, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, LastError);
      goto LABEL_51;
    }
    if ( p_pcbData && *(p_pcbData - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    v16 = pcbData;
    p_pcbData = 0;
    if ( !pcbData
      || pcbData > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)pcbData + g_ulAdditionalProbeSize + 8 < pcbData
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_30;
    }
    v17 = v16 + 23;
    if ( v16 + 23 <= v16 + 8 )
      v17 = 0xFFFFFFFFFFFFFF0LL;
    v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
    v19 = alloca(v18);
    v20 = alloca(v18);
    p_pcbData = (int *)&pcbData;
    if ( &v29 == (__int64 *)-48LL || (pcbData = 1801679955, (p_pcbData = (int *)pbOutput) == 0) )
    {
LABEL_30:
      v18 = v16 + 8;
      if ( v16 + 8 >= v16 )
      {
        v21 = (int *)((__int64 (*)(void))g_pfnAllocate)();
        p_pcbData = v21;
        if ( v21 )
        {
          *v21 = 1885431112;
          p_pcbData = v21 + 2;
        }
      }
    }
    if ( !p_pcbData )
      break;
    if ( !CertGetCertificateContextProperty(v14, 2u, p_pcbData, &pcbData) )
    {
      LastError = GetLastError();
      WppTraceIndent(v22, 2);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_51;
      }
      v24 = 153;
      goto LABEL_49;
    }
    if ( !(unsigned int)I_ReaderListBuildCredFromCertContext(
                          v34,
                          v14,
                          *(const wchar_t **)p_pcbData,
                          p_pcbData[10],
                          &v33) )
    {
      I_ReaderListAddCredToList(v33, v35, a3 + 29);
      ++*a4;
      v33 = 0;
    }
  }
  WppTraceIndent(v18, 2);
  LastError = 8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
LABEL_51:
  v26 = *(int **)pbOutput;
  if ( *(_QWORD *)pbOutput )
    CertCloseStore(*(HCERTSTORE *)pbOutput, 0);
  if ( p_pcbData )
  {
    v26 = p_pcbData - 2;
    if ( *(p_pcbData - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  WppTraceIndent(v26, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v27 = LastError;
    if ( !LastError )
      v27 = Property;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      154,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v27);
  }
  if ( !LastError )
    return Property;
  return LastError;
}

```

## disassembly

```asm
0x180016500  push    rbp
0x180016502  push    rbx
0x180016503  push    rsi
0x180016504  push    rdi
0x180016505  push    r12
0x180016507  push    r13
0x180016509  push    r14
0x18001650b  push    r15
0x18001650d  sub     rsp, 78h
0x180016511  lea     rbp, [rsp+30h]
0x180016516  mov     rax, cs:__security_cookie
0x18001651d  xor     rax, rbp
0x180016520  mov     [rbp+80h+var_50], rax
0x180016524  xor     edi, edi
0x180016526  mov     [rbp+80h+var_60], rdx
0x18001652a  xor     edx, edx
0x18001652c  mov     [rbp+80h+pcbData], edi
0x18001652f  mov     [rbp+80h+var_70], rdi
0x180016533  mov     r13, r9
0x180016536  mov     r15, r8
0x180016539  mov     [rbp+80h+var_68], rcx
0x18001653d  mov     qword ptr [rbp+80h+pbOutput], 0
0x180016545  call    WppTraceIndent
0x18001654a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016551  lea     r14, WPP_GLOBAL_Control
0x180016558  lea     esi, [rdi+2]
0x18001655b  cmp     rcx, r14
0x18001655e  jz      short loc_180016588
0x180016560  test    [rcx+1Ch], sil
0x180016564  jz      short loc_180016588
0x180016566  cmp     byte ptr [rcx+19h], 5
0x18001656a  jb      short loc_180016588
0x18001656c  mov     r9, cs:WPP_pszIndent
0x180016573  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001657a  mov     rcx, [rcx+10h]
0x18001657e  mov     edx, 94h
0x180016583  call    WPP_SF_s
0x180016588  mov     rcx, r15
0x18001658b  call    I_SetupNCryptStorageProvider
0x180016590  mov     ebx, eax
0x180016592  test    eax, eax
0x180016594  jz      short loc_1800165E9
0x180016596  xor     r12d, r12d
0x180016599  mov     edx, esi
0x18001659b  call    WppTraceIndent
0x1800165a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165a7  cmp     rcx, r14
0x1800165aa  jz      loc_1800168AE
0x1800165b0  test    byte ptr [rcx+1Ch], 1
0x1800165b4  jz      loc_1800168AE
0x1800165ba  cmp     [rcx+19h], sil
0x1800165be  jb      loc_1800168AE
0x1800165c4  mov     edx, 95h
0x1800165c9  mov     dword ptr [rsp+0B0h+pcbResult], ebx
0x1800165cd  mov     r9, cs:WPP_pszIndent
0x1800165d4  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800165db  mov     rcx, [rcx+10h]
0x1800165df  call    WPP_SF_sd
0x1800165e4  jmp     loc_1800168AE
0x1800165e9  mov     rcx, [r15+88h]; hObject
0x1800165f0  lea     rax, [rbp+80h+pcbData]
0x1800165f4  mov     [rsp+0B0h+dwFlags], 40h ; '@'; dwFlags
0x1800165fc  lea     r8, [rbp+80h+pbOutput]; pbOutput
0x180016600  mov     r9d, 8; cbOutput
0x180016606  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x18001660b  lea     rdx, aSmartcarduserc; "SmartCardUserCertStore"
0x180016612  mov     [rbp+80h+pcbData], 8
0x180016619  call    cs:__imp_NCryptGetProperty
0x18001661f  mov     r12d, eax
0x180016622  test    eax, eax
0x180016624  jz      short loc_180016660
0x180016626  mov     edx, esi
0x180016628  call    WppTraceIndent
0x18001662d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016634  cmp     rcx, r14
0x180016637  jz      loc_1800168AE
0x18001663d  test    byte ptr [rcx+1Ch], 1
0x180016641  jz      loc_1800168AE
0x180016647  cmp     [rcx+19h], sil
0x18001664b  jb      loc_1800168AE
0x180016651  mov     edx, 96h
0x180016656  mov     dword ptr [rsp+0B0h+pcbResult], r12d
0x18001665b  jmp     loc_1800165CD
0x180016660  xor     r14d, r14d
0x180016663  mov     rcx, qword ptr [rbp+80h+pbOutput]; hCertStore
0x180016667  mov     rdx, r14; pPrevCertContext
0x18001666a  call    cs:__imp_CertEnumCertificatesInStore
0x180016670  mov     r14, rax
0x180016673  test    rax, rax
0x180016676  jz      loc_18001689B
0x18001667c  lea     r9, [rbp+80h+pcbData]; pcbData
0x180016680  xor     r8d, r8d; pvData
0x180016683  mov     edx, esi; dwPropId
0x180016685  mov     rcx, rax; pCertContext
0x180016688  call    cs:__imp_CertGetCertificateContextProperty
0x18001668e  cmp     eax, 1
0x180016691  jnz     loc_18001684B
0x180016697  test    rdi, rdi
0x18001669a  jz      short loc_1800166B4
0x18001669c  lea     rcx, [rdi-8]
0x1800166a0  cmp     dword ptr [rcx], 70616548h
0x1800166a6  jnz     short loc_1800166B4
0x1800166a8  mov     rax, cs:g_pfnFree
0x1800166af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166b4  mov     esi, [rbp+80h+pcbData]
0x1800166b7  xor     edi, edi
0x1800166b9  test    rsi, rsi
0x1800166bc  jz      short loc_18001671F
0x1800166be  cmp     rsi, cs:g_ulMaxStackAllocSize
0x1800166c5  ja      short loc_18001671F
0x1800166c7  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800166ce  add     rcx, 8
0x1800166d2  add     rcx, rsi
0x1800166d5  cmp     rcx, rsi
0x1800166d8  jb      short loc_18001671F
0x1800166da  call    VerifyStackAvailable
0x1800166df  test    eax, eax
0x1800166e1  jz      short loc_18001671F
0x1800166e3  lea     rax, [rsi+8]
0x1800166e7  lea     rcx, [rax+0Fh]
0x1800166eb  cmp     rcx, rax
0x1800166ee  ja      short loc_1800166FA
0x1800166f0  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800166fa  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800166fe  mov     rax, rcx
0x180016701  call    _alloca_probe
0x180016706  sub     rsp, rcx
0x180016709  lea     rdi, [rsp+0B0h+pcbData]
0x18001670e  test    rdi, rdi
0x180016711  jz      short loc_18001671F
0x180016713  mov     dword ptr [rdi], 6B637453h
0x180016719  add     rdi, 8
0x18001671d  jnz     short loc_180016746
0x18001671f  lea     rcx, [rsi+8]
0x180016723  cmp     rcx, rsi
0x180016726  jb      short loc_180016746
0x180016728  mov     rax, cs:g_pfnAllocate
0x18001672f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016734  mov     rdi, rax
0x180016737  test    rax, rax
0x18001673a  jz      short loc_180016746
0x18001673c  mov     dword ptr [rax], 70616548h
0x180016742  add     rdi, 8
0x180016746  mov     esi, 2
0x18001674b  mov     edx, esi; dwPropId
0x18001674d  test    rdi, rdi
0x180016750  jz      loc_1800167F8
0x180016756  lea     r9, [rbp+80h+pcbData]; pcbData
0x18001675a  mov     r8, rdi; pvData
0x18001675d  mov     rcx, r14; pCertContext
0x180016760  call    cs:__imp_CertGetCertificateContextProperty
0x180016766  cmp     eax, 1
0x180016769  jnz     short loc_1800167B4
0x18001676b  mov     r9d, [rdi+28h]
0x18001676f  lea     rax, [rbp+80h+var_70]
0x180016773  mov     r8, [rdi]
0x180016776  mov     rdx, r14
0x180016779  mov     rcx, [rbp+80h+var_68]
0x18001677d  mov     [rsp+0B0h+pcbResult], rax
0x180016782  call    I_ReaderListBuildCredFromCertContext
0x180016787  test    eax, eax
0x180016789  jnz     loc_180016663
0x18001678f  mov     rdx, [rbp+80h+var_60]
0x180016793  lea     r8, [r15+0E8h]
0x18001679a  mov     rcx, [rbp+80h+var_70]
0x18001679e  call    I_ReaderListAddCredToList
0x1800167a3  inc     dword ptr [r13+0]
0x1800167a7  mov     [rbp+80h+var_70], 0
0x1800167af  jmp     loc_180016663
0x1800167b4  call    cs:__imp_GetLastError
0x1800167ba  mov     edx, esi
0x1800167bc  mov     ebx, eax
0x1800167be  call    WppTraceIndent
0x1800167c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167ca  lea     r14, WPP_GLOBAL_Control
0x1800167d1  cmp     rcx, r14
0x1800167d4  jz      loc_1800168B5
0x1800167da  test    byte ptr [rcx+1Ch], 1
0x1800167de  jz      loc_1800168B5
0x1800167e4  cmp     [rcx+19h], sil
0x1800167e8  jb      loc_1800168B5
0x1800167ee  mov     edx, 99h
0x1800167f3  jmp     loc_18001687E
0x1800167f8  call    WppTraceIndent
0x1800167fd  mov     ebx, 8
0x180016802  mov     rcx, cs:WPP_GLOBAL_Control
0x180016809  lea     r14, WPP_GLOBAL_Control
0x180016810  cmp     rcx, r14
0x180016813  jz      loc_1800168B5
0x180016819  test    byte ptr [rcx+1Ch], 1
0x18001681d  jz      loc_1800168B5
0x180016823  cmp     [rcx+19h], sil
0x180016827  jb      loc_1800168B5
0x18001682d  mov     r9, cs:WPP_pszIndent
0x180016834  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001683b  mov     rcx, [rcx+10h]
0x18001683f  mov     edx, 98h
0x180016844  call    WPP_SF_s
0x180016849  jmp     short loc_1800168B5
0x18001684b  call    cs:__imp_GetLastError
0x180016851  mov     edx, esi
0x180016853  mov     ebx, eax
0x180016855  call    WppTraceIndent
0x18001685a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016861  lea     r14, WPP_GLOBAL_Control
0x180016868  cmp     rcx, r14
0x18001686b  jz      short loc_1800168B5
0x18001686d  test    byte ptr [rcx+1Ch], 1
0x180016871  jz      short loc_1800168B5
0x180016873  cmp     [rcx+19h], sil
0x180016877  jb      short loc_1800168B5
0x180016879  mov     edx, 97h
0x18001687e  mov     r9, cs:WPP_pszIndent
0x180016885  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001688c  mov     rcx, [rcx+10h]
0x180016890  mov     dword ptr [rsp+0B0h+pcbResult], ebx
0x180016894  call    WPP_SF_sd
0x180016899  jmp     short loc_1800168B5
0x18001689b  mov     rax, qword ptr [rbp+80h+pbOutput]
0x18001689f  mov     [r15+0A8h], rax
0x1800168a6  mov     qword ptr [rbp+80h+pbOutput], 0
0x1800168ae  lea     r14, WPP_GLOBAL_Control
0x1800168b5  mov     rcx, qword ptr [rbp+80h+pbOutput]; hCertStore
0x1800168b9  test    rcx, rcx
0x1800168bc  jz      short loc_1800168C6
0x1800168be  xor     edx, edx; dwFlags
0x1800168c0  call    cs:__imp_CertCloseStore
0x1800168c6  test    rdi, rdi
0x1800168c9  jz      short loc_1800168E3
0x1800168cb  lea     rcx, [rdi-8]
0x1800168cf  cmp     dword ptr [rcx], 70616548h
0x1800168d5  jnz     short loc_1800168E3
0x1800168d7  mov     rax, cs:g_pfnFree
0x1800168de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168e3  mov     edx, 1
0x1800168e8  call    WppTraceIndent
0x1800168ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168f4  cmp     rcx, r14
0x1800168f7  jz      short loc_18001692D
0x1800168f9  test    [rcx+1Ch], sil
0x1800168fd  jz      short loc_18001692D
0x1800168ff  cmp     byte ptr [rcx+19h], 5
0x180016903  jb      short loc_18001692D
0x180016905  mov     r9, cs:WPP_pszIndent
0x18001690c  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180016913  mov     rcx, [rcx+10h]
0x180016917  test    ebx, ebx
0x180016919  mov     eax, ebx
0x18001691b  mov     edx, 9Ah
0x180016920  cmovz   eax, r12d
0x180016924  mov     dword ptr [rsp+0B0h+pcbResult], eax
0x180016928  call    WPP_SF_sd
0x18001692d  test    ebx, ebx
0x18001692f  cmovz   ebx, r12d
0x180016933  mov     eax, ebx
0x180016935  mov     rcx, [rbp+80h+var_50]
0x180016939  xor     rcx, rbp; StackCookie
0x18001693c  call    __security_check_cookie
0x180016941  lea     rsp, [rbp+48h]
0x180016945  pop     r15
0x180016947  pop     r14
0x180016949  pop     r13
0x18001694b  pop     r12
0x18001694d  pop     rdi
0x18001694e  pop     rsi
0x18001694f  pop     rbx
0x180016950  pop     rbp
0x180016951  retn
```
