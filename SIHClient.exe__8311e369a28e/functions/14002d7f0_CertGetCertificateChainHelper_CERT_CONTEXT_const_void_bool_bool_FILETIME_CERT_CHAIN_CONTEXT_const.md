# CertGetCertificateChainHelper(_CERT_CONTEXT const *,void *,bool,bool,_FILETIME *,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x14002d7f0`
- end: `0x14002dbb5`
- name: `?CertGetCertificateChainHelper@@YAJPEBU_CERT_CONTEXT@@PEAX_N2PEAU_FILETIME@@PEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `965`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, HCERTSTORE hAdditionalStore, char, char, struct _FILETIME *pTime, const struct _CERT_CHAIN_CONTEXT **ppChainContext)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002cbd8`
- `0x14002d280`

## callees

- `0x1400154b4`
- `0x14002d7f0`
- `0x14002dbbc`
- `0x14003261c`
- `0x140045dc0`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d94e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002daa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002dabb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d94e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002d967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002daa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002dabb`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x14002da46`
- `CRYPT32!CertCreateCertificateChainEngine` at `0x14002da46`
- `CRYPT32!CertFreeCertificateChain` at `0x14002da02`
- `CRYPT32!CertFreeCertificateChain` at `0x14002da59`
- `CRYPT32!CertFreeCertificateChain` at `0x14002dadb`
- `CRYPT32!CertFreeCertificateChain` at `0x14002db4a`
- `CRYPT32!CertFreeCertificateChain` at `0x14002db64`
- `CRYPT32!CertFreeCertificateChain` at `0x14002da02`
- `CRYPT32!CertFreeCertificateChain` at `0x14002da59`
- `CRYPT32!CertFreeCertificateChain` at `0x14002dadb`
- `CRYPT32!CertFreeCertificateChain` at `0x14002db4a`
- `CRYPT32!CertFreeCertificateChain` at `0x14002db64`
- `CRYPT32!CertGetCertificateChain` at `0x14002d944`
- `CRYPT32!CertGetCertificateChain` at `0x14002da94`
- `CRYPT32!CertGetCertificateChain` at `0x14002d944`
- `CRYPT32!CertGetCertificateChain` at `0x14002da94`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x14002da30`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x14002db8d`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x14002da30`
- `CRYPT32!CertFreeCertificateChainEngine` at `0x14002db8d`
- `CRYPT32!CertCloseStore` at `0x14002d9dc`
- `CRYPT32!CertCloseStore` at `0x14002db76`
- `CRYPT32!CertCloseStore` at `0x14002d9dc`
- `CRYPT32!CertCloseStore` at `0x14002db76`

## string_xrefs

- `0x14002d8e6`: `SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CertGetCertificateChainHelper(
        PCCERT_CONTEXT pCertContext,
        HCERTSTORE hAdditionalStore,
        char a3,
        char a4,
        struct _FILETIME *pTime,
        const struct _CERT_CHAIN_CONTEXT **ppChainContext)
{
  signed int SubCAStore; // ebx
  HKEY v11; // rcx
  const wchar_t *v12; // r8
  DWORD dwFlags; // esi
  signed int LastError; // eax
  signed int v15; // ecx
  signed int v16; // eax
  signed int v17; // eax
  signed int v18; // ecx
  signed int v19; // eax
  const CERT_CHAIN_CONTEXT *v20; // rcx
  PCCERT_CHAIN_CONTEXT v21; // rax
  const struct _CERT_CHAIN_CONTEXT *v22; // rax
  PCERT_CHAIN_PARA pChainPara; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v26; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v27[12]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pConfig[88]; // [rsp+C0h] [rbp-40h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext[2]; // [rsp+120h] [rbp+20h] BYREF
  HCERTSTORE hCertStore[2]; // [rsp+130h] [rbp+30h] BYREF
  HCERTCHAINENGINE hChainEngine[2]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v32[3]; // [rsp+150h] [rbp+50h] BYREF

  SubCAStore = 0;
  hChainEngine[0] = 0;
  hChainEngine[1] = 0;
  *(_OWORD *)hCertStore = 0u;
  v32[0] = "1.3.6.1.5.5.7.3.1";
  v32[1] = "1.3.6.1.4.1.311.10.3.3";
  v32[2] = "2.16.840.1.113730.4.1";
  memset((char *)v27 + 4, 0, 0x5Cu);
  v26 = 0;
  LODWORD(v27[0]) = 96;
  if ( a4 )
  {
    LODWORD(v27[1]) = 1;
    LODWORD(v27[2]) = 3;
    v27[3] = v32;
  }
  if ( a3 )
  {
    *(_QWORD *)&v26 = 0x200000010LL;
    *((_QWORD *)&v26 + 1) = "1.3.6.1.4.1.311.72.1.1";
    v27[10] = &v26;
  }
  dwFlags = 0x40000000;
  v25 = 0;
  ReadDwordPolicyAsBool(v11, L"SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate", v12, &v25);
  if ( v25 )
  {
    dwFlags = 0;
    WUTrace(0, 0, 32, 4, 0, L"CertGetCertificateChain - revocation checking was disabled by policy.");
  }
  if ( !CertGetCertificateChain(
          0,
          pCertContext,
          pTime,
          hAdditionalStore,
          (PCERT_CHAIN_PARA)v27,
          dwFlags,
          0,
          ppChainContext) )
  {
    LastError = GetLastError();
    v15 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v15 = LastError;
    if ( v15 >= 0 )
    {
      SubCAStore = -2147467259;
    }
    else
    {
      v16 = GetLastError();
      SubCAStore = (unsigned __int16)v16 | 0x80070000;
      if ( v16 <= 0 )
        SubCAStore = v16;
    }
    goto LABEL_36;
  }
  if ( ((*ppChainContext)->TrustStatus.dwErrorStatus & 4) == 0 )
    goto LABEL_42;
  memset(pConfig, 0, sizeof(pConfig));
  pChainContext[0] = 0;
  pChainContext[1] = 0;
  WUTrace(0, 0, 32, 4, 0, L"CertGetCertificateChain failed. Retrying with pinned SubCAs set.");
  if ( hCertStore[1] )
  {
    CertCloseStore(hCertStore[1], 0);
    hCertStore[1] = 0;
  }
  SubCAStore = CreateSubCAStore(&hCertStore[1]);
  if ( SubCAStore < 0 )
  {
    if ( pChainContext[1] )
      CertFreeCertificateChain(pChainContext[1]);
LABEL_37:
    LODWORD(pChainPara) = SubCAStore;
    WUTrace(0, 0, 32, 1, pChainPara, L"CertGetCertificateChain failed. SSL : %ws, StrongSign : %ws");
    goto LABEL_42;
  }
  *(_DWORD *)pConfig = 88;
  *(_DWORD *)&pConfig[48] = 0x2000;
  *(HCERTSTORE *)&pConfig[64] = hCertStore[1];
  *(_DWORD *)&pConfig[80] |= 1u;
  if ( hChainEngine[1] )
  {
    CertFreeCertificateChainEngine(hChainEngine[1]);
    hChainEngine[1] = 0;
  }
  if ( !CertCreateCertificateChainEngine((PCERT_CHAIN_ENGINE_CONFIG)pConfig, &hChainEngine[1]) )
    goto LABEL_27;
  if ( pChainContext[1] )
  {
    CertFreeCertificateChain(pChainContext[1]);
    pChainContext[1] = 0;
  }
  if ( !CertGetCertificateChain(
          hChainEngine[1],
          pCertContext,
          pTime,
          hAdditionalStore,
          (PCERT_CHAIN_PARA)v27,
          dwFlags,
          0,
          &pChainContext[1]) )
  {
LABEL_27:
    v17 = GetLastError();
    v18 = (unsigned __int16)v17 | 0x80070000;
    if ( v17 <= 0 )
      v18 = v17;
    if ( v18 >= 0 )
    {
      SubCAStore = -2147467259;
    }
    else
    {
      v19 = GetLastError();
      SubCAStore = (unsigned __int16)v19 | 0x80070000;
      if ( v19 <= 0 )
        SubCAStore = v19;
    }
    if ( pChainContext[1] )
      CertFreeCertificateChain(pChainContext[1]);
LABEL_36:
    if ( SubCAStore >= 0 )
      goto LABEL_42;
    goto LABEL_37;
  }
  v20 = pChainContext[1];
  v21 = pChainContext[1];
  if ( (pChainContext[1]->TrustStatus.dwInfoStatus & 0x2000) != 0 )
  {
    CertFreeCertificateChain(*ppChainContext);
    v22 = pChainContext[1];
    v20 = 0;
    pChainContext[1] = 0;
    *ppChainContext = v22;
    v21 = 0;
  }
  if ( v21 )
    CertFreeCertificateChain(v20);
LABEL_42:
  if ( hCertStore[1] )
  {
    CertCloseStore(hCertStore[1], 0);
    hCertStore[1] = 0;
  }
  if ( hChainEngine[1] )
    CertFreeCertificateChainEngine(hChainEngine[1]);
  return (unsigned int)SubCAStore;
}

```

## disassembly

```asm
0x14002d7f0  push    rbp
0x14002d7f2  push    rbx
0x14002d7f3  push    rsi
0x14002d7f4  push    rdi
0x14002d7f5  push    r12
0x14002d7f7  push    r13
0x14002d7f9  push    r14
0x14002d7fb  push    r15
0x14002d7fd  lea     rbp, [rsp-78h]
0x14002d802  sub     rsp, 178h
0x14002d809  mov     rax, cs:__security_cookie
0x14002d810  xor     rax, rsp
0x14002d813  mov     [rbp+0B0h+var_48], rax
0x14002d817  mov     sil, r9b
0x14002d81a  mov     [rsp+1B0h+var_170], r9b
0x14002d81f  mov     r13b, r8b
0x14002d822  mov     r15, rdx
0x14002d825  mov     r14, rcx
0x14002d828  mov     r12, [rbp+0B0h+pTime]
0x14002d82f  mov     rdi, [rbp+0B0h+arg_28]
0x14002d836  xor     ebx, ebx
0x14002d838  xorps   xmm0, xmm0
0x14002d83b  movups  xmmword ptr [rbp+0B0h+hChainEngine], xmm0
0x14002d83f  mov     [rbp+0B0h+hChainEngine+8], rbx
0x14002d843  movups  xmmword ptr [rbp+0B0h+hCertStore], xmm0
0x14002d847  mov     [rbp+0B0h+hCertStore+8], rbx
0x14002d84b  lea     rax, a136155731; "1.3.6.1.5.5.7.3.1"
0x14002d852  mov     [rbp+0B0h+var_60], rax
0x14002d856  lea     rax, a1361413111033; "1.3.6.1.4.1.311.10.3.3"
0x14002d85d  mov     [rbp+0B0h+var_58], rax
0x14002d861  lea     rax, a21684011137304; "2.16.840.1.113730.4.1"
0x14002d868  mov     [rbp+0B0h+var_50], rax
0x14002d86c  xor     edx, edx; Val
0x14002d86e  lea     r8d, [rbx+5Ch]; Size
0x14002d872  lea     rcx, [rsp+1B0h+var_150+4]; void *
0x14002d877  call    memset
0x14002d87c  xorps   xmm0, xmm0
0x14002d87f  movups  [rsp+1B0h+var_168], xmm0
0x14002d884  mov     [rsp+1B0h+var_150.cbSize], 60h ; '`'
0x14002d88c  test    sil, sil
0x14002d88f  jz      short loc_14002D8AA
0x14002d891  mov     [rsp+1B0h+var_150.RequestedUsage.dwType], 1
0x14002d899  mov     [rsp+1B0h+var_150.RequestedUsage.Usage.cUsageIdentifier], 3
0x14002d8a1  lea     rax, [rbp+0B0h+var_60]
0x14002d8a5  mov     [rsp+1B0h+var_150.RequestedUsage.Usage.rgpszUsageIdentifier], rax
0x14002d8aa  test    r13b, r13b
0x14002d8ad  jz      short loc_14002D8D4
0x14002d8af  mov     dword ptr [rsp+1B0h+var_168], 10h
0x14002d8b7  mov     dword ptr [rsp+1B0h+var_168+4], 2
0x14002d8bf  lea     rax, a1361413117211; "1.3.6.1.4.1.311.72.1.1"
0x14002d8c6  mov     qword ptr [rsp+1B0h+var_168+8], rax
0x14002d8cb  lea     rax, [rsp+1B0h+var_168]
0x14002d8d0  mov     [rbp+0B0h+var_100], rax
0x14002d8d4  mov     esi, 40000000h
0x14002d8d9  mov     [rsp+1B0h+var_16C], 0
0x14002d8e1  lea     r9, [rsp+1B0h+var_16C]; int *
0x14002d8e6  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x14002d8ed  call    ?ReadDwordPolicyAsBool@@YAJPEAUHKEY__@@PEB_W1PEAH@Z; ReadDwordPolicyAsBool(HKEY__ *,wchar_t const *,wchar_t const *,int *)
0x14002d8f2  cmp     [rsp+1B0h+var_16C], 0
0x14002d8f7  jz      short loc_14002D91D
0x14002d8f9  xor     esi, esi
0x14002d8fb  lea     rax, aCertgetcertifi_3; "CertGetCertificateChain - revocation ch"...
0x14002d902  mov     qword ptr [rsp+1B0h+dwFlags], rax
0x14002d907  mov     [rsp+1B0h+pChainPara], rsi
0x14002d90c  xor     edx, edx
0x14002d90e  xor     ecx, ecx
0x14002d910  lea     r9d, [rsi+4]
0x14002d914  lea     r8d, [rsi+20h]
0x14002d918  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002d91d  mov     [rsp+1B0h+ppChainContext], rdi; ppChainContext
0x14002d922  mov     [rsp+1B0h+pvReserved], 0; pvReserved
0x14002d92b  mov     [rsp+1B0h+dwFlags], esi; dwFlags
0x14002d92f  lea     rax, [rsp+1B0h+var_150]
0x14002d934  mov     [rsp+1B0h+pChainPara], rax; pChainPara
0x14002d939  mov     r9, r15; hAdditionalStore
0x14002d93c  mov     r8, r12; pTime
0x14002d93f  mov     rdx, r14; pCertContext
0x14002d942  xor     ecx, ecx; hChainEngine
0x14002d944  call    cs:__imp_CertGetCertificateChain
0x14002d94a  test    eax, eax
0x14002d94c  jnz     short loc_14002D986
0x14002d94e  call    cs:__imp_GetLastError
0x14002d954  movzx   ecx, ax
0x14002d957  mov     edi, 80070000h
0x14002d95c  or      ecx, edi
0x14002d95e  test    eax, eax
0x14002d960  cmovle  ecx, eax
0x14002d963  test    ecx, ecx
0x14002d965  jns     short loc_14002D97C
0x14002d967  call    cs:__imp_GetLastError
0x14002d96d  movzx   ebx, ax
0x14002d970  or      ebx, edi
0x14002d972  test    eax, eax
0x14002d974  cmovle  ebx, eax
0x14002d977  jmp     loc_14002DAE1
0x14002d97c  mov     ebx, 80004005h
0x14002d981  jmp     loc_14002DAE1
0x14002d986  mov     rax, [rdi]
0x14002d989  test    byte ptr [rax+4], 4
0x14002d98d  jz      loc_14002DB6B
0x14002d993  xor     edx, edx; Val
0x14002d995  lea     r8d, [rdx+58h]; Size
0x14002d999  lea     rcx, [rbp+0B0h+pConfig]; void *
0x14002d99d  call    memset
0x14002d9a2  xorps   xmm0, xmm0
0x14002d9a5  movups  xmmword ptr [rbp+0B0h+pChainContext], xmm0
0x14002d9a9  xor     ebx, ebx
0x14002d9ab  mov     [rbp+0B0h+pChainContext+8], rbx
0x14002d9af  lea     rax, aCertgetcertifi_4; "CertGetCertificateChain failed. Retryin"...
0x14002d9b6  mov     qword ptr [rsp+1B0h+dwFlags], rax
0x14002d9bb  mov     [rsp+1B0h+pChainPara], rbx
0x14002d9c0  xor     edx, edx
0x14002d9c2  xor     ecx, ecx
0x14002d9c4  lea     r9d, [rbx+4]
0x14002d9c8  lea     r8d, [rbx+20h]
0x14002d9cc  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002d9d1  mov     rcx, [rbp+0B0h+hCertStore+8]; hCertStore
0x14002d9d5  test    rcx, rcx
0x14002d9d8  jz      short loc_14002D9E6
0x14002d9da  xor     edx, edx; dwFlags
0x14002d9dc  call    cs:__imp_CertCloseStore
0x14002d9e2  mov     [rbp+0B0h+hCertStore+8], rbx
0x14002d9e6  lea     rcx, [rbp+0B0h+hCertStore+8]; void **
0x14002d9ea  call    ?CreateSubCAStore@@YAJPEAPEAX@Z; CreateSubCAStore(void * *)
0x14002d9ef  mov     ebx, eax
0x14002d9f1  test    eax, eax
0x14002d9f3  jns     short loc_14002DA0D
0x14002d9f5  mov     rcx, [rbp+0B0h+pChainContext+8]; pChainContext
0x14002d9f9  test    rcx, rcx
0x14002d9fc  jz      loc_14002DAE9
0x14002da02  call    cs:__imp_CertFreeCertificateChain
0x14002da08  jmp     loc_14002DAE9
0x14002da0d  mov     [rbp+0B0h+pConfig.cbSize], 58h ; 'X'
0x14002da14  mov     [rbp+0B0h+pConfig.dwFlags], 2000h
0x14002da1b  mov     rax, [rbp+0B0h+hCertStore+8]
0x14002da1f  mov     [rbp+0B0h+pConfig.hExclusiveRoot], rax
0x14002da23  or      [rbp+0B0h+var_A0], 1
0x14002da27  mov     rcx, [rbp+0B0h+hChainEngine+8]; hChainEngine
0x14002da2b  test    rcx, rcx
0x14002da2e  jz      short loc_14002DA3E
0x14002da30  call    cs:__imp_CertFreeCertificateChainEngine
0x14002da36  mov     [rbp+0B0h+hChainEngine+8], 0
0x14002da3e  lea     rdx, [rbp+0B0h+hChainEngine+8]; phChainEngine
0x14002da42  lea     rcx, [rbp+0B0h+pConfig]; pConfig
0x14002da46  call    cs:__imp_CertCreateCertificateChainEngine
0x14002da4c  test    eax, eax
0x14002da4e  jz      short loc_14002DAA2
0x14002da50  mov     rcx, [rbp+0B0h+pChainContext+8]; pChainContext
0x14002da54  test    rcx, rcx
0x14002da57  jz      short loc_14002DA67
0x14002da59  call    cs:__imp_CertFreeCertificateChain
0x14002da5f  mov     [rbp+0B0h+pChainContext+8], 0
0x14002da67  lea     rax, [rbp+0B0h+pChainContext+8]
0x14002da6b  mov     [rsp+1B0h+ppChainContext], rax; ppChainContext
0x14002da70  mov     [rsp+1B0h+pvReserved], 0; pvReserved
0x14002da79  mov     [rsp+1B0h+dwFlags], esi; dwFlags
0x14002da7d  lea     rax, [rsp+1B0h+var_150]
0x14002da82  mov     [rsp+1B0h+pChainPara], rax; pChainPara
0x14002da87  mov     r9, r15; hAdditionalStore
0x14002da8a  mov     r8, r12; pTime
0x14002da8d  mov     rdx, r14; pCertContext
0x14002da90  mov     rcx, [rbp+0B0h+hChainEngine+8]; hChainEngine
0x14002da94  call    cs:__imp_CertGetCertificateChain
0x14002da9a  test    eax, eax
0x14002da9c  jnz     loc_14002DB37
0x14002daa2  call    cs:__imp_GetLastError
0x14002daa8  movzx   ecx, ax
0x14002daab  mov     edi, 80070000h
0x14002dab0  or      ecx, edi
0x14002dab2  test    eax, eax
0x14002dab4  cmovle  ecx, eax
0x14002dab7  test    ecx, ecx
0x14002dab9  jns     short loc_14002DACD
0x14002dabb  call    cs:__imp_GetLastError
0x14002dac1  movzx   ebx, ax
0x14002dac4  or      ebx, edi
0x14002dac6  test    eax, eax
0x14002dac8  cmovle  ebx, eax
0x14002dacb  jmp     short loc_14002DAD2
0x14002dacd  mov     ebx, 80004005h
0x14002dad2  mov     rcx, [rbp+0B0h+pChainContext+8]; pChainContext
0x14002dad6  test    rcx, rcx
0x14002dad9  jz      short loc_14002DAE1
0x14002dadb  call    cs:__imp_CertFreeCertificateChain
0x14002dae1  test    ebx, ebx
0x14002dae3  jns     loc_14002DB6B
0x14002dae9  lea     rdx, aYes_1; "Yes"
0x14002daf0  lea     rcx, aNo_1; "No"
0x14002daf7  mov     rax, rcx
0x14002dafa  test    r13b, r13b
0x14002dafd  cmovnz  rax, rdx
0x14002db01  cmp     [rsp+1B0h+var_170], 0
0x14002db06  cmovnz  rcx, rdx
0x14002db0a  mov     [rsp+1B0h+ppChainContext], rax
0x14002db0f  mov     [rsp+1B0h+pvReserved], rcx
0x14002db14  lea     rax, aCertgetcertifi_2; "CertGetCertificateChain failed. SSL : %"...
0x14002db1b  mov     qword ptr [rsp+1B0h+dwFlags], rax
0x14002db20  mov     dword ptr [rsp+1B0h+pChainPara], ebx
0x14002db24  xor     edx, edx
0x14002db26  xor     ecx, ecx
0x14002db28  lea     r9d, [rdx+1]
0x14002db2c  lea     r8d, [rdx+20h]
0x14002db30  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002db35  jmp     short loc_14002DB6B
0x14002db37  mov     rcx, [rbp+0B0h+pChainContext+8]
0x14002db3b  mov     rax, rcx
0x14002db3e  test    dword ptr [rcx+8], 2000h
0x14002db45  jz      short loc_14002DB5F
0x14002db47  mov     rcx, [rdi]; pChainContext
0x14002db4a  call    cs:__imp_CertFreeCertificateChain
0x14002db50  mov     rax, [rbp+0B0h+pChainContext+8]
0x14002db54  xor     ecx, ecx; pChainContext
0x14002db56  mov     [rbp+0B0h+pChainContext+8], rcx
0x14002db5a  mov     [rdi], rax
0x14002db5d  xor     eax, eax
0x14002db5f  test    rax, rax
0x14002db62  jz      short loc_14002DB6B
0x14002db64  call    cs:__imp_CertFreeCertificateChain
0x14002db6a  nop
0x14002db6b  mov     rcx, [rbp+0B0h+hCertStore+8]; hCertStore
0x14002db6f  test    rcx, rcx
0x14002db72  jz      short loc_14002DB84
0x14002db74  xor     edx, edx; dwFlags
0x14002db76  call    cs:__imp_CertCloseStore
0x14002db7c  mov     [rbp+0B0h+hCertStore+8], 0
0x14002db84  mov     rcx, [rbp+0B0h+hChainEngine+8]; hChainEngine
0x14002db88  test    rcx, rcx
0x14002db8b  jz      short loc_14002DB93
0x14002db8d  call    cs:__imp_CertFreeCertificateChainEngine
0x14002db93  mov     eax, ebx
0x14002db95  mov     rcx, [rbp+0B0h+var_48]
0x14002db99  xor     rcx, rsp; StackCookie
0x14002db9c  call    __security_check_cookie
0x14002dba1  add     rsp, 178h
0x14002dba8  pop     r15
0x14002dbaa  pop     r14
0x14002dbac  pop     r13
0x14002dbae  pop     r12
0x14002dbb0  pop     rdi
0x14002dbb1  pop     rsi
0x14002dbb2  pop     rbx
0x14002dbb3  pop     rbp
0x14002dbb4  retn
```
