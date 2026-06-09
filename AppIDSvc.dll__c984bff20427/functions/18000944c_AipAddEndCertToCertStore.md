# AipAddEndCertToCertStore

- ea: `0x18000944c`
- end: `0x18000984b`
- name: `AipAddEndCertToCertStore`
- size: `1023`
- prototype: `__int64 __fastcall(CRYPT_PROVIDER_DATA *, BOOL, int, void *, BYTE **, DWORD *, FILETIME *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800090a0`

## callees

- `0x18000880c`
- `0x180008f00`
- `0x18000944c`
- `0x180009a24`
- `0x18000a044`
- `0x18000a5a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009554`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009819`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009828`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009819`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009828`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009610`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000963e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009683`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800096b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800096e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000971b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000974c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800097a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009610`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000963e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009683`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800096b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800096e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000971b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000974c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800097a8`
- `ntdll!RtlFreeHeap` at `0x1800097c2`
- `ntdll!RtlFreeHeap` at `0x18000980b`
- `ntdll!RtlFreeHeap` at `0x1800097c2`
- `ntdll!RtlFreeHeap` at `0x18000980b`
- `CRYPT32!CryptEncodeObject` at `0x18000954a`
- `CRYPT32!CryptEncodeObject` at `0x180009598`
- `CRYPT32!CryptEncodeObject` at `0x18000954a`
- `CRYPT32!CryptEncodeObject` at `0x180009598`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x180009504`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x180009504`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x180009519`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x180009519`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1800094a8`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x1800094a8`

## pseudocode

```c
__int64 __fastcall AipAddEndCertToCertStore(
        CRYPT_PROVIDER_DATA *a1,
        BOOL a2,
        int a3,
        void *a4,
        BYTE **a5,
        DWORD *a6,
        FILETIME *a7)
{
  FILETIME v8; // rbx
  BYTE *v9; // r12
  HKEY v10; // rsi
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_SGNR *v12; // r14
  DWORD ChainValidityPeriod; // edi
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  CRYPT_PROVIDER_CERT *v15; // r15
  BYTE *v16; // rax
  DWORD v17; // eax
  BYTE *v18; // r14
  __int64 v19; // rax
  DWORD pcbEncoded; // [rsp+48h] [rbp-41h] BYREF
  DWORD v22; // [rsp+4Ch] [rbp-3Dh] BYREF
  BYTE v23[8]; // [rsp+50h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-31h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-29h] BYREF
  FILETIME sftVerifyAsOf; // [rsp+68h] [rbp-21h]
  HKEY phkResult; // [rsp+70h] [rbp-19h] BYREF
  BYTE v28[8]; // [rsp+78h] [rbp-11h] BYREF
  BYTE v29[8]; // [rsp+80h] [rbp-9h] BYREF
  BYTE *lpData; // [rsp+88h] [rbp-1h] BYREF
  BOOL v31; // [rsp+E0h] [rbp+57h] BYREF
  int v32; // [rsp+E8h] [rbp+5Fh] BYREF

  v32 = a3;
  v31 = a2;
  pcbEncoded = 0;
  v8 = 0;
  phkResult = 0;
  sftVerifyAsOf = 0;
  hKey = 0;
  v9 = 0;
  v22 = 0;
  v10 = 0;
  lpData = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v23 = 0;
  *(_QWORD *)v28 = 0;
  *(_QWORD *)v29 = 0;
  ProvSignerFromChain = WTHelperGetProvSignerFromChain(a1, 0, a2, 0);
  v12 = ProvSignerFromChain;
  if ( !ProvSignerFromChain )
    goto LABEL_2;
  ChainValidityPeriod = AipGetChainValidityPeriod(ProvSignerFromChain, (FILETIME *)v28, (FILETIME *)v29);
  if ( !ChainValidityPeriod )
  {
    ChainValidityPeriod = RegOpenKeyTransactedW(
                            HKEY_LOCAL_MACHINE,
                            L"System\\CurrentControlSet\\Control\\AppID\\CertStore\\",
                            0,
                            0x20006u,
                            &phkResult,
                            a4,
                            0);
    if ( !ChainValidityPeriod )
    {
      ProvCertFromChain = WTHelperGetProvCertFromChain(v12, 0);
      v15 = ProvCertFromChain;
      if ( !ProvCertFromChain )
      {
LABEL_2:
        ChainValidityPeriod = 87;
        goto LABEL_34;
      }
      ChainValidityPeriod = 8;
      if ( !CryptEncodeObject(
              0x10001u,
              (LPCSTR)8,
              &ProvCertFromChain->pCert->pCertInfo->SubjectPublicKeyInfo,
              0,
              &pcbEncoded) )
        goto LABEL_7;
      v16 = (BYTE *)AiAlloc(pcbEncoded);
      v9 = v16;
      if ( !v16 )
        goto LABEL_34;
      if ( !CryptEncodeObject(0x10001u, (LPCSTR)8, &v15->pCert->pCertInfo->SubjectPublicKeyInfo, v16, &pcbEncoded) )
      {
LABEL_7:
        ChainValidityPeriod = GetLastError();
        goto LABEL_27;
      }
      if ( v31 )
      {
        sftVerifyAsOf = v12->sftVerifyAsOf;
        v8 = sftVerifyAsOf;
      }
      v17 = AipAddCertToCertStore(phkResult, (__int64)v15->pCert, &hKey, &v22, a4);
      v10 = hKey;
      ChainValidityPeriod = v17;
      if ( !v17 )
      {
        if ( v22 == 2 )
        {
LABEL_28:
          if ( a5 )
          {
            *a5 = v9;
            v9 = 0;
          }
          if ( a6 )
          {
            *a6 = pcbEncoded;
            pcbEncoded = 0;
          }
          if ( a7 )
            *a7 = v8;
          goto LABEL_34;
        }
        ChainValidityPeriod = RegSetValueExW(hKey, L"Untrusted", 0, 4u, Data, 4u);
        if ( ChainValidityPeriod )
          goto LABEL_34;
        ChainValidityPeriod = RegSetValueExW(v10, L"Unknown", 0, 4u, (const BYTE *)&v32, 4u);
        if ( ChainValidityPeriod )
          goto LABEL_34;
        ChainValidityPeriod = AipIsLifetimeSigningCert(v15->pCert);
        if ( ChainValidityPeriod )
          goto LABEL_34;
        ChainValidityPeriod = RegSetValueExW(v10, L"LifetimeSigning", 0, 4u, v23, 4u);
        if ( ChainValidityPeriod )
          goto LABEL_34;
        if ( v31 )
        {
          ChainValidityPeriod = RegSetValueExW(v10, L"TimeStampCert", 0, 4u, (const BYTE *)&v31, 4u);
          if ( ChainValidityPeriod )
            goto LABEL_34;
        }
        ChainValidityPeriod = RegSetValueExW(v10, L"PublicKey", 0, 3u, v9, pcbEncoded);
        if ( ChainValidityPeriod )
          goto LABEL_34;
        ChainValidityPeriod = RegSetValueExW(v10, L"NotBefore", 0, 0xBu, v28, 8u);
        if ( ChainValidityPeriod )
          goto LABEL_34;
        ChainValidityPeriod = RegSetValueExW(v10, L"NotAfter", 0, 0xBu, v29, 8u);
        if ( ChainValidityPeriod )
          goto LABEL_34;
        ChainValidityPeriod = AipCertGetPublisherName(v15->pCert, (__int64)&lpData);
        if ( ChainValidityPeriod )
          goto LABEL_34;
        v18 = lpData;
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)&lpData[2 * v19] );
        ChainValidityPeriod = RegSetValueExW(v10, L"PublisherName", 0, 1u, lpData, 2 * v19 + 2);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
LABEL_27:
        if ( ChainValidityPeriod )
          goto LABEL_34;
        goto LABEL_28;
      }
    }
  }
LABEL_34:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  if ( v10 )
    RegCloseKey(v10);
  if ( phkResult )
    RegCloseKey(phkResult);
  return ChainValidityPeriod;
}

```

## disassembly

```asm
0x18000944c  mov     rax, rsp
0x18000944f  mov     [rax+8], rbx
0x180009453  mov     [rax+18h], r8d
0x180009457  mov     [rax+10h], edx
0x18000945a  push    rbp
0x18000945b  push    rsi
0x18000945c  push    rdi
0x18000945d  push    r12
0x18000945f  push    r13
0x180009461  push    r14
0x180009463  push    r15
0x180009465  lea     rbp, [rax-47h]
0x180009469  sub     rsp, 90h
0x180009470  xor     edi, edi
0x180009472  mov     r13, r9
0x180009475  mov     r8d, edx; fCounterSigner
0x180009478  mov     [rbp+3Fh+pcbEncoded], edi
0x18000947b  mov     ebx, edi
0x18000947d  mov     [rbp+3Fh+var_58], rdi
0x180009481  xor     r9d, r9d; idxCounterSigner
0x180009484  mov     [rbp+3Fh+var_60], rbx
0x180009488  xor     edx, edx; idxSigner
0x18000948a  mov     [rbp+3Fh+hKey], rdi
0x18000948e  mov     r12d, edi
0x180009491  mov     [rbp+3Fh+var_7C], edi
0x180009494  mov     esi, edi
0x180009496  mov     [rbp+3Fh+lpData], rdi
0x18000949a  mov     dword ptr [rbp+3Fh+Data], edi
0x18000949d  mov     dword ptr [rbp+3Fh+var_78], edi
0x1800094a0  mov     qword ptr [rbp+3Fh+var_50], rdi
0x1800094a4  mov     qword ptr [rbp+3Fh+var_48], rdi
0x1800094a8  call    cs:__imp_WTHelperGetProvSignerFromChain
0x1800094ae  mov     r14, rax
0x1800094b1  test    rax, rax
0x1800094b4  jnz     short loc_1800094C0
0x1800094b6  mov     edi, 57h ; 'W'
0x1800094bb  jmp     loc_1800097F9
0x1800094c0  lea     r8, [rbp+3Fh+var_48]; FILETIME *
0x1800094c4  mov     rcx, r14; pSgnr
0x1800094c7  lea     rdx, [rbp+3Fh+var_50]; lpFileTime2
0x1800094cb  call    AipGetChainValidityPeriod
0x1800094d0  mov     edi, eax
0x1800094d2  test    eax, eax
0x1800094d4  jnz     loc_1800097F9
0x1800094da  mov     [rsp+30h], rbx; pExtendedParemeter
0x1800094df  lea     rax, [rbp+3Fh+var_58]
0x1800094e3  mov     [rsp+0C0h+hTransaction], r13; hTransaction
0x1800094e8  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\App"...
0x1800094ef  mov     r9d, 20006h; samDesired
0x1800094f5  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800094fa  xor     r8d, r8d; ulOptions
0x1800094fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009504  call    cs:__imp_RegOpenKeyTransactedW
0x18000950a  mov     edi, eax
0x18000950c  test    eax, eax
0x18000950e  jnz     loc_1800097F9
0x180009514  xor     edx, edx; idxCert
0x180009516  mov     rcx, r14; pSgnr
0x180009519  call    cs:__imp_WTHelperGetProvCertFromChain
0x18000951f  mov     r15, rax
0x180009522  test    rax, rax
0x180009525  jz      short loc_1800094B6
0x180009527  mov     rax, [rax+8]
0x18000952b  xor     r9d, r9d; pbEncoded
0x18000952e  mov     ecx, 10001h; dwCertEncodingType
0x180009533  mov     r8, [rax+18h]
0x180009537  lea     edi, [r9+8]
0x18000953b  lea     rax, [rbp+3Fh+pcbEncoded]
0x18000953f  add     r8, 60h ; '`'; pvStructInfo
0x180009543  mov     edx, edi; lpszStructType
0x180009545  mov     [rsp+0C0h+phkResult], rax; pcbEncoded
0x18000954a  call    cs:__imp_CryptEncodeObject
0x180009550  test    eax, eax
0x180009552  jnz     short loc_180009564
0x180009554  call    cs:__imp_GetLastError
0x18000955a  mov     edi, eax
0x18000955c  xor     r13d, r13d
0x18000955f  jmp     loc_1800097C8
0x180009564  mov     ecx, [rbp+3Fh+pcbEncoded]
0x180009567  call    AiAlloc
0x18000956c  mov     r12, rax
0x18000956f  test    rax, rax
0x180009572  jz      loc_1800097F9
0x180009578  mov     rax, [r15+8]
0x18000957c  mov     r9, r12; pbEncoded
0x18000957f  mov     rdx, rdi; lpszStructType
0x180009582  mov     ecx, 10001h; dwCertEncodingType
0x180009587  mov     r8, [rax+18h]
0x18000958b  lea     rax, [rbp+3Fh+pcbEncoded]
0x18000958f  add     r8, 60h ; '`'; pvStructInfo
0x180009593  mov     [rsp+0C0h+phkResult], rax; pcbEncoded
0x180009598  call    cs:__imp_CryptEncodeObject
0x18000959e  test    eax, eax
0x1800095a0  jz      short loc_180009554
0x1800095a2  cmp     [rbp+3Fh+arg_8], ebx
0x1800095a5  jz      short loc_1800095B9
0x1800095a7  mov     eax, [r14+8]
0x1800095ab  mov     dword ptr [rbp+3Fh+var_60+4], eax
0x1800095ae  mov     eax, [r14+4]
0x1800095b2  mov     dword ptr [rbp+3Fh+var_60], eax
0x1800095b5  mov     rbx, [rbp+3Fh+var_60]
0x1800095b9  mov     rdx, [r15+8]
0x1800095bd  lea     r9, [rbp+3Fh+var_7C]
0x1800095c1  mov     rcx, [rbp+3Fh+var_58]; hKey
0x1800095c5  lea     r8, [rbp+3Fh+hKey]
0x1800095c9  mov     [rsp+0C0h+phkResult], r13; HANDLE
0x1800095ce  call    AipAddCertToCertStore
0x1800095d3  mov     rsi, [rbp+3Fh+hKey]
0x1800095d7  xor     r13d, r13d
0x1800095da  mov     edi, eax
0x1800095dc  test    eax, eax
0x1800095de  jnz     loc_1800097F9
0x1800095e4  cmp     [rbp+3Fh+var_7C], 2
0x1800095e8  jz      loc_1800097CC
0x1800095ee  lea     r14d, [rax+4]
0x1800095f2  xor     r8d, r8d; Reserved
0x1800095f5  lea     rax, [rbp+3Fh+Data]
0x1800095f9  mov     dword ptr [rsp+0C0h+hTransaction], r14d; cbData
0x1800095fe  mov     r9d, r14d; dwType
0x180009601  mov     [rsp+0C0h+phkResult], rax; lpData
0x180009606  lea     rdx, aUntrusted; "Untrusted"
0x18000960d  mov     rcx, rsi; hKey
0x180009610  call    cs:__imp_RegSetValueExW
0x180009616  mov     edi, eax
0x180009618  test    eax, eax
0x18000961a  jnz     loc_1800097F9
0x180009620  lea     rax, [rbp+3Fh+arg_10]
0x180009624  mov     dword ptr [rsp+0C0h+hTransaction], r14d; cbData
0x180009629  mov     r9d, r14d; dwType
0x18000962c  mov     [rsp+0C0h+phkResult], rax; lpData
0x180009631  xor     r8d, r8d; Reserved
0x180009634  lea     rdx, aUnknown; "Unknown"
0x18000963b  mov     rcx, rsi; hKey
0x18000963e  call    cs:__imp_RegSetValueExW
0x180009644  mov     edi, eax
0x180009646  test    eax, eax
0x180009648  jnz     loc_1800097F9
0x18000964e  mov     rcx, [r15+8]; pCertContext
0x180009652  lea     rdx, [rbp+3Fh+var_78]
0x180009656  call    AipIsLifetimeSigningCert
0x18000965b  mov     edi, eax
0x18000965d  test    eax, eax
0x18000965f  jnz     loc_1800097F9
0x180009665  lea     rax, [rbp+3Fh+var_78]
0x180009669  mov     dword ptr [rsp+0C0h+hTransaction], r14d; cbData
0x18000966e  mov     r9d, r14d; dwType
0x180009671  mov     [rsp+0C0h+phkResult], rax; lpData
0x180009676  xor     r8d, r8d; Reserved
0x180009679  lea     rdx, aLifetimesignin; "LifetimeSigning"
0x180009680  mov     rcx, rsi; hKey
0x180009683  call    cs:__imp_RegSetValueExW
0x180009689  mov     edi, eax
0x18000968b  test    eax, eax
0x18000968d  jnz     loc_1800097F9
0x180009693  cmp     [rbp+3Fh+arg_8], r13d
0x180009697  jz      short loc_1800096C7
0x180009699  lea     rax, [rbp+3Fh+arg_8]
0x18000969d  mov     dword ptr [rsp+0C0h+hTransaction], r14d; cbData
0x1800096a2  mov     r9d, r14d; dwType
0x1800096a5  mov     [rsp+0C0h+phkResult], rax; lpData
0x1800096aa  xor     r8d, r8d; Reserved
0x1800096ad  lea     rdx, aTimestampcert; "TimeStampCert"
0x1800096b4  mov     rcx, rsi; hKey
0x1800096b7  call    cs:__imp_RegSetValueExW
0x1800096bd  mov     edi, eax
0x1800096bf  test    eax, eax
0x1800096c1  jnz     loc_1800097F9
0x1800096c7  mov     eax, [rbp+3Fh+pcbEncoded]
0x1800096ca  lea     rdx, aPublickey; "PublicKey"
0x1800096d1  mov     dword ptr [rsp+0C0h+hTransaction], eax; cbData
0x1800096d5  mov     r9d, 3; dwType
0x1800096db  xor     r8d, r8d; Reserved
0x1800096de  mov     [rsp+0C0h+phkResult], r12; lpData
0x1800096e3  mov     rcx, rsi; hKey
0x1800096e6  call    cs:__imp_RegSetValueExW
0x1800096ec  mov     edi, eax
0x1800096ee  test    eax, eax
0x1800096f0  jnz     loc_1800097F9
0x1800096f6  lea     rax, [rbp+3Fh+var_50]
0x1800096fa  mov     dword ptr [rsp+0C0h+hTransaction], 8; cbData
0x180009702  lea     r14d, [rdi+0Bh]
0x180009706  mov     [rsp+0C0h+phkResult], rax; lpData
0x18000970b  mov     r9d, r14d; dwType
0x18000970e  lea     rdx, aNotbefore; "NotBefore"
0x180009715  xor     r8d, r8d; Reserved
0x180009718  mov     rcx, rsi; hKey
0x18000971b  call    cs:__imp_RegSetValueExW
0x180009721  mov     edi, eax
0x180009723  test    eax, eax
0x180009725  jnz     loc_1800097F9
0x18000972b  lea     rax, [rbp+3Fh+var_48]
0x18000972f  mov     dword ptr [rsp+0C0h+hTransaction], 8; cbData
0x180009737  mov     r9d, r14d; dwType
0x18000973a  mov     [rsp+0C0h+phkResult], rax; lpData
0x18000973f  xor     r8d, r8d; Reserved
0x180009742  lea     rdx, aNotafter; "NotAfter"
0x180009749  mov     rcx, rsi; hKey
0x18000974c  call    cs:__imp_RegSetValueExW
0x180009752  mov     edi, eax
0x180009754  test    eax, eax
0x180009756  jnz     loc_1800097F9
0x18000975c  mov     rcx, [r15+8]; pCertContext
0x180009760  lea     rdx, [rbp+3Fh+lpData]; __int64
0x180009764  call    AipCertGetPublisherName
0x180009769  mov     edi, eax
0x18000976b  test    eax, eax
0x18000976d  jnz     loc_1800097F9
0x180009773  mov     r14, [rbp+3Fh+lpData]
0x180009777  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000977b  inc     rax
0x18000977e  cmp     [r14+rax*2], r13w
0x180009783  jnz     short loc_18000977B
0x180009785  lea     eax, ds:2[rax*2]
0x18000978c  mov     r9d, 1; dwType
0x180009792  mov     dword ptr [rsp+0C0h+hTransaction], eax; cbData
0x180009796  lea     rdx, aPublishername; "PublisherName"
0x18000979d  xor     r8d, r8d; Reserved
0x1800097a0  mov     [rsp+0C0h+phkResult], r14; lpData
0x1800097a5  mov     rcx, rsi; hKey
0x1800097a8  call    cs:__imp_RegSetValueExW
0x1800097ae  mov     rcx, gs:60h
0x1800097b7  mov     r8, r14; P
0x1800097ba  xor     edx, edx; Flags
0x1800097bc  mov     edi, eax
0x1800097be  mov     rcx, [rcx+30h]; HeapHandle
0x1800097c2  call    cs:__imp_RtlFreeHeap
0x1800097c8  test    edi, edi
0x1800097ca  jnz     short loc_1800097F9
0x1800097cc  mov     rax, [rbp+3Fh+arg_20]
0x1800097d0  test    rax, rax
0x1800097d3  jz      short loc_1800097DB
0x1800097d5  mov     [rax], r12
0x1800097d8  mov     r12, r13
0x1800097db  mov     rcx, [rbp+3Fh+arg_28]
0x1800097df  test    rcx, rcx
0x1800097e2  jz      short loc_1800097ED
0x1800097e4  mov     eax, [rbp+3Fh+pcbEncoded]
0x1800097e7  mov     [rcx], eax
0x1800097e9  mov     [rbp+3Fh+pcbEncoded], r13d
0x1800097ed  mov     rax, [rbp+3Fh+arg_30]
0x1800097f1  test    rax, rax
0x1800097f4  jz      short loc_1800097F9
0x1800097f6  mov     [rax], rbx
0x1800097f9  mov     rcx, gs:60h
0x180009802  mov     r8, r12; P
0x180009805  xor     edx, edx; Flags
0x180009807  mov     rcx, [rcx+30h]; HeapHandle
0x18000980b  call    cs:__imp_RtlFreeHeap
0x180009811  test    rsi, rsi
0x180009814  jz      short loc_18000981F
0x180009816  mov     rcx, rsi; hKey
0x180009819  call    cs:__imp_RegCloseKey
0x18000981f  mov     rcx, [rbp+3Fh+var_58]; hKey
0x180009823  test    rcx, rcx
0x180009826  jz      short loc_18000982E
0x180009828  call    cs:__imp_RegCloseKey
0x18000982e  mov     rbx, [rsp+0C0h+arg_0]
0x180009836  mov     eax, edi
0x180009838  add     rsp, 90h
0x18000983f  pop     r15
0x180009841  pop     r14
0x180009843  pop     r13
0x180009845  pop     r12
0x180009847  pop     rdi
0x180009848  pop     rsi
0x180009849  pop     rbp
0x18000984a  retn
```
