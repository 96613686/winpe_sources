# I_ReaderListPopulateCredsViaCertStore

- ea: `0x180017544`
- end: `0x18001794e`
- name: `I_ReaderListPopulateCredsViaCertStore`
- size: `1034`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001317c`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x180014018`
- `0x1800157fc`
- `0x1800160c8`
- `0x180017544`
- `0x18001cc6c`
- `0x18001dd7c`
- `0x18001e020`
- `0x18001e0e0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001783b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001783b`
- `CRYPT32!CertCloseStore` at `0x1800178af`
- `CRYPT32!CertCloseStore` at `0x1800178af`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001767e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180017751`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001767e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180017751`
- `CRYPT32!CertFreeCertificateContext` at `0x1800178bd`
- `CRYPT32!CertFreeCertificateContext` at `0x1800178bd`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18001765e`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18001765e`
- `CRYPTSP!CryptGetProvParam` at `0x1800175ea`
- `CRYPTSP!CryptGetProvParam` at `0x1800175ea`

## pseudocode

```c
__int64 __fastcall I_ReaderListPopulateCredsViaCertStore(__int64 a1, __int64 a2, _DWORD *a3)
{
  const CERT_CONTEXT *v4; // r15
  int *p_pdwDataLen; // rbx
  LPVOID *v6; // r12
  HCRYPTPROV v9; // rcx
  DWORD LastError; // esi
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  int v13; // edx
  const CERT_CONTEXT *v14; // rax
  __int64 v15; // rdx
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  int *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  DWORD v25; // edi
  int *v26; // rcx
  __int64 v28; // [rsp+0h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+30h] [rbp+0h] BYREF
  BYTE pbData[8]; // [rsp+38h] [rbp+8h] BYREF
  LPVOID *v31; // [rsp+40h] [rbp+10h] BYREF
  _DWORD *v32; // [rsp+48h] [rbp+18h]

  v32 = a3;
  *(_QWORD *)pbData = 0;
  pdwDataLen = 0;
  v4 = 0;
  v31 = 0;
  p_pdwDataLen = 0;
  v6 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  v9 = *(_QWORD *)(a2 + 128);
  *a3 = 0;
  LastError = 8;
  pdwDataLen = 8;
  if ( CryptGetProvParam(v9, 0x2Au, pbData, &pdwDataLen, 0) )
  {
    while ( 1 )
    {
      v14 = CertEnumCertificatesInStore(*(HCERTSTORE *)pbData, v4);
      v4 = v14;
      if ( !v14 )
      {
        LastError = 0;
        *(_QWORD *)(a2 + 168) = *(_QWORD *)pbData;
        *(_DWORD *)(a2 + 148) = 1;
        *(_QWORD *)pbData = 0;
        goto LABEL_45;
      }
      if ( !CertGetCertificateContextProperty(v14, 2u, 0, &pdwDataLen) )
        break;
      if ( p_pdwDataLen && *(p_pdwDataLen - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      v16 = pdwDataLen;
      p_pdwDataLen = 0;
      if ( !pdwDataLen )
        goto LABEL_24;
      if ( pdwDataLen > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_24;
      v17 = pdwDataLen + g_ulAdditionalProbeSize + 8;
      if ( v17 < pdwDataLen || !(unsigned int)VerifyStackAvailable(v17, v15) )
        goto LABEL_24;
      v18 = v16 + 23;
      if ( v16 + 23 <= v16 + 8 )
        v18 = 0xFFFFFFFFFFFFFF0LL;
      v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
      v20 = alloca(v19);
      v21 = alloca(v19);
      p_pdwDataLen = (int *)&pdwDataLen;
      if ( &v28 == (__int64 *)-48LL || (pdwDataLen = 1801679955, (p_pdwDataLen = (int *)pbData) == 0) )
      {
LABEL_24:
        v19 = v16 + 8;
        if ( v16 + 8 >= v16 )
        {
          v22 = (int *)((__int64 (*)(void))g_pfnAllocate)();
          p_pdwDataLen = v22;
          if ( v22 )
          {
            *v22 = 1885431112;
            p_pdwDataLen = v22 + 2;
          }
        }
      }
      if ( !p_pdwDataLen )
      {
        WppTraceIndent(v19, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            102,
            &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent);
        }
        goto LABEL_45;
      }
      if ( !CertGetCertificateContextProperty(v4, 2u, p_pdwDataLen, &pdwDataLen) )
      {
        LastError = GetLastError();
        WppTraceIndent(v23, 2);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 103;
          goto LABEL_10;
        }
        goto LABEL_45;
      }
      if ( (unsigned int)I_ReaderListBuildCredFromCertContext(
                           a1,
                           v4,
                           *(const wchar_t **)p_pdwDataLen,
                           p_pdwDataLen[10],
                           &v31) )
      {
        v6 = v31;
      }
      else
      {
        I_ReaderListAddCredToList(v31, *(unsigned __int16 **)(a2 + 96), (__int64 *)(a2 + 232));
        ++*v32;
        v6 = 0;
        v31 = 0;
      }
    }
    LastError = GetLastError();
    WppTraceIndent(v24, 2);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 101;
      goto LABEL_10;
    }
  }
  else
  {
    LastError = GetLastError();
    WppTraceIndent(v11, 2);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 100;
LABEL_10:
      WPP_SF_sd(v12[2], v13, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, LastError);
    }
  }
LABEL_45:
  v25 = 0;
  v26 = *(int **)pbData;
  if ( !*v32 )
    v25 = LastError;
  if ( *(_QWORD *)pbData )
    CertCloseStore(*(HCERTSTORE *)pbData, 0);
  if ( v4 )
    CertFreeCertificateContext(v4);
  if ( v6 )
    I_FreeCredListItem(v6);
  if ( p_pdwDataLen )
  {
    v26 = p_pdwDataLen - 2;
    if ( *(p_pdwDataLen - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  WppTraceIndent(v26, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      104,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v25);
  }
  return v25;
}

```

## disassembly

```asm
0x180017544  push    rbp
0x180017546  push    rbx
0x180017547  push    rsi
0x180017548  push    rdi
0x180017549  push    r12
0x18001754b  push    r13
0x18001754d  push    r14
0x18001754f  push    r15
0x180017551  sub     rsp, 68h
0x180017555  lea     rbp, [rsp+30h]
0x18001755a  mov     rax, cs:__security_cookie
0x180017561  xor     rax, rbp
0x180017564  mov     [rbp+70h+var_48], rax
0x180017568  xor     esi, esi
0x18001756a  mov     [rbp+70h+var_58], r8
0x18001756e  mov     r14, rdx
0x180017571  mov     qword ptr [rbp+70h+pbData], rsi
0x180017575  xor     edx, edx
0x180017577  mov     [rbp+70h+pdwDataLen], esi
0x18001757a  mov     r15d, esi
0x18001757d  mov     [rbp+70h+var_60], rsi
0x180017581  mov     ebx, esi
0x180017583  mov     r12d, esi
0x180017586  mov     rdi, r8
0x180017589  mov     r13, rcx
0x18001758c  call    WppTraceIndent
0x180017591  mov     rcx, cs:WPP_GLOBAL_Control
0x180017598  lea     rax, WPP_GLOBAL_Control
0x18001759f  cmp     rcx, rax
0x1800175a2  jz      short loc_1800175CA
0x1800175a4  test    byte ptr [rcx+1Ch], 2
0x1800175a8  jz      short loc_1800175CA
0x1800175aa  cmp     byte ptr [rcx+19h], 5
0x1800175ae  jb      short loc_1800175CA
0x1800175b0  mov     r9, cs:WPP_pszIndent
0x1800175b7  lea     edx, [rsi+63h]
0x1800175ba  mov     rcx, [rcx+10h]
0x1800175be  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800175c5  call    WPP_SF_s
0x1800175ca  mov     rcx, [r14+80h]; hProv
0x1800175d1  lea     r9, [rbp+70h+pdwDataLen]; pdwDataLen
0x1800175d5  mov     [rdi], esi
0x1800175d7  lea     r8, [rbp+70h+pbData]; pbData
0x1800175db  mov     esi, 8
0x1800175e0  mov     [rsp+0A0h+dwFlags], ebx; dwFlags
0x1800175e4  mov     [rbp+70h+pdwDataLen], esi
0x1800175e7  lea     edx, [rsi+22h]; dwParam
0x1800175ea  call    cs:__imp_CryptGetProvParam
0x1800175f0  cmp     eax, 1
0x1800175f3  jz      short loc_180017657
0x1800175f5  call    cs:__imp_GetLastError
0x1800175fb  mov     edx, 2
0x180017600  mov     esi, eax
0x180017602  call    WppTraceIndent
0x180017607  mov     rcx, cs:WPP_GLOBAL_Control
0x18001760e  lea     r14, WPP_GLOBAL_Control
0x180017615  cmp     rcx, r14
0x180017618  jz      loc_180017899
0x18001761e  test    byte ptr [rcx+1Ch], 1
0x180017622  jz      loc_180017899
0x180017628  cmp     byte ptr [rcx+19h], 2
0x18001762c  jb      loc_180017899
0x180017632  mov     edx, 64h ; 'd'
0x180017637  mov     r9, cs:WPP_pszIndent
0x18001763e  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180017645  mov     rcx, [rcx+10h]
0x180017649  mov     [rsp+0A0h+dwFlags], esi
0x18001764d  call    WPP_SF_sd
0x180017652  jmp     loc_180017899
0x180017657  mov     rcx, qword ptr [rbp+70h+pbData]; hCertStore
0x18001765b  mov     rdx, r15; pPrevCertContext
0x18001765e  call    cs:__imp_CertEnumCertificatesInStore
0x180017664  mov     r15, rax
0x180017667  test    rax, rax
0x18001766a  jz      loc_180017876
0x180017670  xor     r8d, r8d; pvData
0x180017673  lea     r9, [rbp+70h+pdwDataLen]; pcbData
0x180017677  mov     rcx, rax; pCertContext
0x18001767a  lea     edx, [r8+2]; dwPropId
0x18001767e  call    cs:__imp_CertGetCertificateContextProperty
0x180017684  cmp     eax, 1
0x180017687  jnz     loc_18001783B
0x18001768d  test    rbx, rbx
0x180017690  jz      short loc_1800176AA
0x180017692  lea     rcx, [rbx-8]
0x180017696  cmp     dword ptr [rcx], 70616548h
0x18001769c  jnz     short loc_1800176AA
0x18001769e  mov     rax, cs:g_pfnFree
0x1800176a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176aa  mov     edi, [rbp+70h+pdwDataLen]
0x1800176ad  xor     ebx, ebx
0x1800176af  test    rdi, rdi
0x1800176b2  jz      short loc_180017713
0x1800176b4  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800176bb  ja      short loc_180017713
0x1800176bd  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800176c4  add     rcx, rsi
0x1800176c7  add     rcx, rdi
0x1800176ca  cmp     rcx, rdi
0x1800176cd  jb      short loc_180017713
0x1800176cf  call    VerifyStackAvailable
0x1800176d4  test    eax, eax
0x1800176d6  jz      short loc_180017713
0x1800176d8  lea     rax, [rdi+8]
0x1800176dc  lea     rcx, [rax+0Fh]
0x1800176e0  cmp     rcx, rax
0x1800176e3  ja      short loc_1800176EF
0x1800176e5  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800176ef  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800176f3  mov     rax, rcx
0x1800176f6  call    _alloca_probe
0x1800176fb  sub     rsp, rcx
0x1800176fe  lea     rbx, [rsp+0A0h+pdwDataLen]
0x180017703  test    rbx, rbx
0x180017706  jz      short loc_180017713
0x180017708  mov     dword ptr [rbx], 6B637453h
0x18001770e  add     rbx, rsi
0x180017711  jnz     short loc_180017739
0x180017713  lea     rcx, [rdi+8]
0x180017717  cmp     rcx, rdi
0x18001771a  jb      short loc_180017739
0x18001771c  mov     rax, cs:g_pfnAllocate
0x180017723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017728  mov     rbx, rax
0x18001772b  test    rax, rax
0x18001772e  jz      short loc_180017739
0x180017730  mov     dword ptr [rax], 70616548h
0x180017736  add     rbx, rsi
0x180017739  mov     edx, 2; dwPropId
0x18001773e  test    rbx, rbx
0x180017741  jz      loc_1800177F1
0x180017747  lea     r9, [rbp+70h+pdwDataLen]; pcbData
0x18001774b  mov     r8, rbx; pvData
0x18001774e  mov     rcx, r15; pCertContext
0x180017751  call    cs:__imp_CertGetCertificateContextProperty
0x180017757  cmp     eax, 1
0x18001775a  jnz     short loc_1800177AA
0x18001775c  mov     r9d, [rbx+28h]
0x180017760  lea     rax, [rbp+70h+var_60]
0x180017764  mov     r8, [rbx]
0x180017767  mov     rdx, r15
0x18001776a  mov     rcx, r13
0x18001776d  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x180017772  call    I_ReaderListBuildCredFromCertContext
0x180017777  test    eax, eax
0x180017779  jz      short loc_180017784
0x18001777b  mov     r12, [rbp+70h+var_60]
0x18001777f  jmp     loc_180017657
0x180017784  mov     rdx, [r14+60h]
0x180017788  lea     r8, [r14+0E8h]
0x18001778f  mov     rcx, [rbp+70h+var_60]
0x180017793  call    I_ReaderListAddCredToList
0x180017798  mov     rdi, [rbp+70h+var_58]
0x18001779c  inc     dword ptr [rdi]
0x18001779e  xor     r12d, r12d
0x1800177a1  mov     [rbp+70h+var_60], r12
0x1800177a5  jmp     loc_180017657
0x1800177aa  call    cs:__imp_GetLastError
0x1800177b0  mov     edx, 2
0x1800177b5  mov     esi, eax
0x1800177b7  call    WppTraceIndent
0x1800177bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177c3  lea     r14, WPP_GLOBAL_Control
0x1800177ca  cmp     rcx, r14
0x1800177cd  jz      loc_180017899
0x1800177d3  test    byte ptr [rcx+1Ch], 1
0x1800177d7  jz      loc_180017899
0x1800177dd  cmp     byte ptr [rcx+19h], 2
0x1800177e1  jb      loc_180017899
0x1800177e7  mov     edx, 67h ; 'g'
0x1800177ec  jmp     loc_180017637
0x1800177f1  call    WppTraceIndent
0x1800177f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177fd  lea     r14, WPP_GLOBAL_Control
0x180017804  cmp     rcx, r14
0x180017807  jz      loc_180017899
0x18001780d  test    byte ptr [rcx+1Ch], 1
0x180017811  jz      loc_180017899
0x180017817  cmp     byte ptr [rcx+19h], 2
0x18001781b  jb      short loc_180017899
0x18001781d  mov     r9, cs:WPP_pszIndent
0x180017824  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001782b  mov     rcx, [rcx+10h]
0x18001782f  mov     edx, 66h ; 'f'
0x180017834  call    WPP_SF_s
0x180017839  jmp     short loc_180017899
0x18001783b  call    cs:__imp_GetLastError
0x180017841  mov     edx, 2
0x180017846  mov     esi, eax
0x180017848  call    WppTraceIndent
0x18001784d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017854  lea     r14, WPP_GLOBAL_Control
0x18001785b  cmp     rcx, r14
0x18001785e  jz      short loc_180017899
0x180017860  test    byte ptr [rcx+1Ch], 1
0x180017864  jz      short loc_180017899
0x180017866  cmp     byte ptr [rcx+19h], 2
0x18001786a  jb      short loc_180017899
0x18001786c  mov     edx, 65h ; 'e'
0x180017871  jmp     loc_180017637
0x180017876  mov     rax, qword ptr [rbp+70h+pbData]
0x18001787a  xor     esi, esi
0x18001787c  mov     [r14+0A8h], rax
0x180017883  mov     dword ptr [r14+94h], 1
0x18001788e  lea     r14, WPP_GLOBAL_Control
0x180017895  mov     qword ptr [rbp+70h+pbData], rsi
0x180017899  mov     rax, [rbp+70h+var_58]
0x18001789d  xor     edi, edi
0x18001789f  mov     rcx, qword ptr [rbp+70h+pbData]; hCertStore
0x1800178a3  cmp     [rax], edi
0x1800178a5  cmovbe  edi, esi
0x1800178a8  test    rcx, rcx
0x1800178ab  jz      short loc_1800178B5
0x1800178ad  xor     edx, edx; dwFlags
0x1800178af  call    cs:__imp_CertCloseStore
0x1800178b5  test    r15, r15
0x1800178b8  jz      short loc_1800178C3
0x1800178ba  mov     rcx, r15; pCertContext
0x1800178bd  call    cs:__imp_CertFreeCertificateContext
0x1800178c3  test    r12, r12
0x1800178c6  jz      short loc_1800178D0
0x1800178c8  mov     rcx, r12; lpMem
0x1800178cb  call    I_FreeCredListItem
0x1800178d0  test    rbx, rbx
0x1800178d3  jz      short loc_1800178ED
0x1800178d5  lea     rcx, [rbx-8]
0x1800178d9  cmp     dword ptr [rcx], 70616548h
0x1800178df  jnz     short loc_1800178ED
0x1800178e1  mov     rax, cs:g_pfnFree
0x1800178e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178ed  mov     edx, 1
0x1800178f2  call    WppTraceIndent
0x1800178f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178fe  cmp     rcx, r14
0x180017901  jz      short loc_18001792F
0x180017903  test    byte ptr [rcx+1Ch], 2
0x180017907  jz      short loc_18001792F
0x180017909  cmp     byte ptr [rcx+19h], 5
0x18001790d  jb      short loc_18001792F
0x18001790f  mov     r9, cs:WPP_pszIndent
0x180017916  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001791d  mov     rcx, [rcx+10h]
0x180017921  mov     edx, 68h ; 'h'
0x180017926  mov     [rsp+0A0h+dwFlags], edi
0x18001792a  call    WPP_SF_sd
0x18001792f  mov     eax, edi
0x180017931  mov     rcx, [rbp+70h+var_48]
0x180017935  xor     rcx, rbp; StackCookie
0x180017938  call    __security_check_cookie
0x18001793d  lea     rsp, [rbp+38h]
0x180017941  pop     r15
0x180017943  pop     r14
0x180017945  pop     r13
0x180017947  pop     r12
0x180017949  pop     rdi
0x18001794a  pop     rsi
0x18001794b  pop     rbx
0x18001794c  pop     rbp
0x18001794d  retn
```
