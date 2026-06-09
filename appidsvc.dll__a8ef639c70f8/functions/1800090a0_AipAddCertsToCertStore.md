# AipAddCertsToCertStore

- ea: `0x1800090a0`
- end: `0x180009446`
- name: `AipAddCertsToCertStore`
- size: `934`
- prototype: `__int64 __fastcall(HANDLE hStateData, unsigned int, void *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a0f8`

## callees

- `0x180008de0`
- `0x180008f00`
- `0x1800090a0`
- `0x18000944c`
- `0x18000aa84`
- `0x18000c0a2`
- `0x18000c0e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009220`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000940d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009220`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000940d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000941e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000941e`
- `ntdll!NtCreateTransaction` at `0x180009157`
- `ntdll!NtCreateTransaction` at `0x180009157`
- `ntdll!NtCommitTransaction` at `0x1800092eb`
- `ntdll!NtCommitTransaction` at `0x1800092eb`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009165`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800092f9`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009165`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800092f9`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800091e6`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800091e6`
- `CRYPT32!CertFreeCertificateContext` at `0x18000924e`
- `CRYPT32!CertFreeCertificateContext` at `0x18000924e`
- `CRYPT32!CryptHashCertificate` at `0x180009391`
- `CRYPT32!CryptHashCertificate` at `0x180009391`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x1800091bf`
- `ADVAPI32!RegOpenKeyTransactedW` at `0x1800091bf`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18000934d`
- `WINTRUST!WTHelperGetProvCertFromChain` at `0x18000934d`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180009339`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180009339`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18000917d`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18000917d`

## pseudocode

```c
__int64 __fastcall AipAddCertsToCertStore(HANDLE hStateData, unsigned int a2, void *a3, __int64 a4)
{
  const CERT_CONTEXT *v4; // r14
  void *v5; // r12
  NTSTATUS v9; // eax
  NTSTATUS v10; // edi
  unsigned int LastError; // ebx
  CRYPT_PROVIDER_DATA *v12; // rdi
  DWORD v13; // r15d
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rsi
  NTSTATUS v21; // eax
  NTSTATUS v22; // esi
  unsigned int v23; // esi
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_CERT *ProvCertFromChain; // rax
  DWORD pcbComputedHash; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v29; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  void *v32; // [rsp+78h] [rbp-88h]
  _QWORD v33[4]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v34; // [rsp+A0h] [rbp-60h]
  BYTE pbComputedHash[32]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v36[80]; // [rsp+D0h] [rbp-30h] BYREF

  v4 = 0;
  v32 = a3;
  v5 = a3;
  phkResult = 0;
  hKey = 0;
  v29 = 0;
  hObject = (HANDLE)-1LL;
  memset_0(v36, 0, sizeof(v36));
  v33[0] = 48;
  memset(&v33[1], 0, 24);
  v34 = 0;
  v9 = NtCreateTransaction(&hObject, 2031679, v33, 0, 0, 0, 0, 0, 0, 0, 0);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v12 = WTHelperProvDataFromStateData(hStateData);
    if ( v12 )
    {
      LastError = RegOpenKeyTransactedW(
                    HKEY_LOCAL_MACHINE,
                    L"System\\CurrentControlSet\\Control\\AppID\\CertChainStore\\",
                    0,
                    0x20006u,
                    &phkResult,
                    hObject,
                    0);
      if ( !LastError )
      {
        v13 = 0;
        if ( v12->chStores )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              v4 = CertEnumCertificatesInStore(v12->pahStores[v13], v4);
              if ( v4 )
                break;
              ++v13;
              v4 = 0;
              if ( v13 >= v12->chStores )
              {
                v5 = v32;
                goto LABEL_13;
              }
            }
            LastError = AipAddCertToCertStore(phkResult, (__int64)v4, &hKey, &v29, hObject);
            if ( LastError )
              break;
            RegCloseKey(hKey);
          }
          CertFreeCertificateContext(v4);
        }
        else
        {
LABEL_13:
          if ( a4 )
          {
            v14 = a4 + 8;
            v15 = a4;
            v16 = a4 + 32;
          }
          else
          {
            v14 = 0;
            v16 = 0;
            v15 = 0;
          }
          LastError = AipAddEndCertToCertStore(v12, 0, a2, hObject, v14, v15, v16);
          if ( !LastError )
          {
            if ( !v12->pasSigners->csCounterSigners
              || (!a4 ? (v18 = 0, v19 = 0, v20 = 0) : (v18 = a4 + 24, v19 = a4 + 16, v20 = a4 + 32),
                  (LastError = AipAddEndCertToCertStore(v12, 1, a2, hObject, v18, v19, v20)) == 0) )
            {
              LOBYTE(v17) = 1;
              v21 = NtCommitTransaction(hObject, v17);
              v22 = v21;
              if ( v21 >= 0 )
              {
                v23 = 0;
                while ( v23 != 1 || v12->pasSigners->csCounterSigners )
                {
                  ProvSignerFromChain = WTHelperGetProvSignerFromChain(v12, 0, v23 == 1, 0);
                  if ( !ProvSignerFromChain )
                    goto LABEL_38;
                  ProvCertFromChain = WTHelperGetProvCertFromChain(ProvSignerFromChain, 0);
                  if ( !ProvCertFromChain )
                    goto LABEL_38;
                  pcbComputedHash = 32;
                  if ( !CryptHashCertificate(
                          0,
                          0x8004u,
                          0,
                          ProvCertFromChain->pCert->pbCertEncoded,
                          ProvCertFromChain->pCert->cbCertEncoded,
                          pbComputedHash,
                          &pcbComputedHash) )
                  {
                    LastError = GetLastError();
                    break;
                  }
                  if ( pcbComputedHash )
                  {
                    do
                    {
                      RtlStringCchPrintfW(
                        &v36[2 * (_DWORD)v4],
                        80LL - (unsigned int)(2 * (_DWORD)v4),
                        L"%2.2x",
                        pbComputedHash[(unsigned int)v4]);
                      LODWORD(v4) = (_DWORD)v4 + 1;
                    }
                    while ( (unsigned int)v4 < pcbComputedHash );
                  }
                  AiUpdateDriverCertDataFromRegistry(v5, v36);
                  ++v23;
                  LODWORD(v4) = 0;
                  if ( v23 >= 2 )
                    break;
                }
              }
              else
              {
                LastError = RtlNtStatusToDosErrorNoTeb(v21);
                if ( LastError == 317 )
                  LastError = v22;
              }
            }
          }
        }
      }
    }
    else
    {
LABEL_38:
      LastError = 87;
    }
  }
  else
  {
    LastError = RtlNtStatusToDosErrorNoTeb(v9);
    if ( LastError == 317 )
      LastError = v10;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return LastError;
}

```

## disassembly

```asm
0x1800090a0  push    rbp
0x1800090a2  push    rbx
0x1800090a3  push    rsi
0x1800090a4  push    rdi
0x1800090a5  push    r12
0x1800090a7  push    r13
0x1800090a9  push    r14
0x1800090ab  push    r15
0x1800090ad  lea     rbp, [rsp-88h]
0x1800090b5  sub     rsp, 188h
0x1800090bc  mov     rax, cs:__security_cookie
0x1800090c3  xor     rax, rsp
0x1800090c6  mov     [rbp+0C0h+var_50], rax
0x1800090ca  xor     r14d, r14d
0x1800090cd  mov     [rsp+1C0h+var_148], r8
0x1800090d2  mov     r12, r8
0x1800090d5  mov     [rsp+1C0h+var_158], r14
0x1800090da  mov     r13d, edx
0x1800090dd  mov     [rsp+1C0h+hKey], r14
0x1800090e2  mov     rbx, rcx
0x1800090e5  mov     [rsp+1C0h+var_160], r14d
0x1800090ea  xor     edx, edx; Val
0x1800090ec  mov     [rsp+1C0h+pcbComputedHash], r14d
0x1800090f1  mov     r8d, 0A0h; Size
0x1800090f7  mov     [rsp+1C0h+hObject], 0FFFFFFFFFFFFFFFFh
0x180009100  lea     rcx, [rbp+0C0h+var_F0]; void *
0x180009104  mov     rsi, r9
0x180009107  call    memset_0
0x18000910c  mov     [rsp+1C0h+var_178], r14
0x180009111  lea     r8, [rbp+0C0h+var_140]
0x180009115  mov     [rsp+1C0h+var_180], r14
0x18000911a  lea     rcx, [rsp+1C0h+hObject]
0x18000911f  mov     [rsp+1C0h+var_188], r14d
0x180009124  xorps   xmm0, xmm0
0x180009127  mov     dword ptr [rsp+1C0h+pExtendedParemeter], r14d
0x18000912c  xor     r9d, r9d
0x18000912f  mov     dword ptr [rsp+1C0h+hTransaction], r14d
0x180009134  mov     edx, 1F003Fh
0x180009139  mov     [rsp+1C0h+phkResult], r14
0x18000913e  mov     [rbp+0C0h+var_140], 30h ; '0'
0x180009146  mov     [rbp+0C0h+var_128], r14
0x18000914a  mov     [rbp+0C0h+var_138], r14
0x18000914e  mov     [rbp+0C0h+var_130], r14
0x180009152  movdqu  [rbp+0C0h+var_120], xmm0
0x180009157  call    cs:__imp_NtCreateTransaction
0x18000915d  mov     edi, eax
0x18000915f  test    eax, eax
0x180009161  jns     short loc_18000917A
0x180009163  mov     ecx, eax; Status
0x180009165  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000916b  cmp     eax, 13Dh
0x180009170  mov     ebx, eax
0x180009172  cmovz   ebx, edi
0x180009175  jmp     loc_180009403
0x18000917a  mov     rcx, rbx; hStateData
0x18000917d  call    cs:__imp_WTHelperProvDataFromStateData
0x180009183  mov     rdi, rax
0x180009186  test    rax, rax
0x180009189  jz      loc_1800093FE
0x18000918f  mov     rax, [rsp+1C0h+hObject]
0x180009194  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\App"...
0x18000919b  mov     [rsp+1C0h+pExtendedParemeter], r14; pExtendedParemeter
0x1800091a0  mov     r9d, 20006h; samDesired
0x1800091a6  mov     [rsp+1C0h+hTransaction], rax; hTransaction
0x1800091ab  xor     r8d, r8d; ulOptions
0x1800091ae  lea     rax, [rsp+1C0h+var_158]
0x1800091b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800091ba  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800091bf  call    cs:__imp_RegOpenKeyTransactedW
0x1800091c5  mov     ebx, eax
0x1800091c7  test    eax, eax
0x1800091c9  jnz     loc_180009403
0x1800091cf  mov     r15d, r14d
0x1800091d2  cmp     [rdi+58h], r14d
0x1800091d6  jbe     short loc_180009239
0x1800091d8  mov     r12d, r15d
0x1800091db  mov     rcx, [rdi+60h]
0x1800091df  mov     rdx, r14; pPrevCertContext
0x1800091e2  mov     rcx, [rcx+r12*8]; hCertStore
0x1800091e6  call    cs:__imp_CertEnumCertificatesInStore
0x1800091ec  mov     r14, rax
0x1800091ef  test    rax, rax
0x1800091f2  jz      short loc_180009228
0x1800091f4  mov     rax, [rsp+1C0h+hObject]
0x1800091f9  lea     r9, [rsp+1C0h+var_160]
0x1800091fe  mov     rcx, [rsp+1C0h+var_158]; hKey
0x180009203  lea     r8, [rsp+1C0h+hKey]
0x180009208  mov     rdx, r14
0x18000920b  mov     [rsp+1C0h+phkResult], rax; HANDLE
0x180009210  call    AipAddCertToCertStore
0x180009215  mov     ebx, eax
0x180009217  test    eax, eax
0x180009219  jnz     short loc_18000924B
0x18000921b  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180009220  call    cs:__imp_RegCloseKey
0x180009226  jmp     short loc_1800091DB
0x180009228  inc     r15d
0x18000922b  xor     r14d, r14d
0x18000922e  cmp     r15d, [rdi+58h]
0x180009232  jb      short loc_1800091D8
0x180009234  mov     r12, [rsp+1C0h+var_148]
0x180009239  test    rsi, rsi
0x18000923c  jz      short loc_180009259
0x18000923e  lea     rax, [rsi+8]
0x180009242  mov     rdx, rsi
0x180009245  lea     rcx, [rsi+20h]
0x180009249  jmp     short loc_180009262
0x18000924b  mov     rcx, r14; pCertContext
0x18000924e  call    cs:__imp_CertFreeCertificateContext
0x180009254  jmp     loc_180009403
0x180009259  mov     rax, r14
0x18000925c  mov     rcx, r14
0x18000925f  mov     rdx, r14
0x180009262  mov     r9, [rsp+1C0h+hObject]
0x180009267  mov     r8d, r13d
0x18000926a  mov     [rsp+1C0h+pExtendedParemeter], rcx
0x18000926f  mov     rcx, rdi
0x180009272  mov     [rsp+1C0h+hTransaction], rdx
0x180009277  xor     edx, edx
0x180009279  mov     [rsp+1C0h+phkResult], rax
0x18000927e  call    AipAddEndCertToCertStore
0x180009283  mov     ebx, eax
0x180009285  test    eax, eax
0x180009287  jnz     loc_180009403
0x18000928d  mov     rax, [rdi+80h]
0x180009294  cmp     [rax+2Ch], r14d
0x180009298  jz      short loc_1800092E4
0x18000929a  test    rsi, rsi
0x18000929d  jz      short loc_1800092AD
0x18000929f  lea     rax, [rsi+18h]
0x1800092a3  lea     rcx, [rsi+10h]
0x1800092a7  add     rsi, 20h ; ' '
0x1800092ab  jmp     short loc_1800092B6
0x1800092ad  mov     rax, r14
0x1800092b0  mov     rcx, r14
0x1800092b3  mov     rsi, r14
0x1800092b6  mov     r9, [rsp+1C0h+hObject]
0x1800092bb  mov     r8d, r13d
0x1800092be  mov     [rsp+1C0h+pExtendedParemeter], rsi
0x1800092c3  mov     edx, 1
0x1800092c8  mov     [rsp+1C0h+hTransaction], rcx
0x1800092cd  mov     rcx, rdi
0x1800092d0  mov     [rsp+1C0h+phkResult], rax
0x1800092d5  call    AipAddEndCertToCertStore
0x1800092da  mov     ebx, eax
0x1800092dc  test    eax, eax
0x1800092de  jnz     loc_180009403
0x1800092e4  mov     rcx, [rsp+1C0h+hObject]
0x1800092e9  mov     dl, 1
0x1800092eb  call    cs:__imp_NtCommitTransaction
0x1800092f1  mov     esi, eax
0x1800092f3  test    eax, eax
0x1800092f5  jns     short loc_18000930E
0x1800092f7  mov     ecx, eax; Status
0x1800092f9  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800092ff  cmp     eax, 13Dh
0x180009304  mov     ebx, eax
0x180009306  cmovz   ebx, esi
0x180009309  jmp     loc_180009403
0x18000930e  mov     esi, r14d
0x180009311  cmp     esi, 1
0x180009314  jnz     short loc_180009327
0x180009316  mov     rax, [rdi+80h]
0x18000931d  cmp     [rax+2Ch], r14d
0x180009321  jz      loc_180009403
0x180009327  mov     r8d, r14d
0x18000932a  cmp     esi, 1
0x18000932d  mov     rcx, rdi; pProvData
0x180009330  setz    r8b; fCounterSigner
0x180009334  xor     r9d, r9d; idxCounterSigner
0x180009337  xor     edx, edx; idxSigner
0x180009339  call    cs:__imp_WTHelperGetProvSignerFromChain
0x18000933f  test    rax, rax
0x180009342  jz      loc_1800093FE
0x180009348  xor     edx, edx; idxCert
0x18000934a  mov     rcx, rax; pSgnr
0x18000934d  call    cs:__imp_WTHelperGetProvCertFromChain
0x180009353  test    rax, rax
0x180009356  jz      loc_1800093FE
0x18000935c  mov     [rsp+1C0h+pcbComputedHash], 20h ; ' '
0x180009364  xor     r8d, r8d; dwFlags
0x180009367  mov     r9, [rax+8]
0x18000936b  mov     edx, 8004h; Algid
0x180009370  lea     rax, [rsp+1C0h+pcbComputedHash]
0x180009375  xor     ecx, ecx; hCryptProv
0x180009377  mov     [rsp+1C0h+pExtendedParemeter], rax; pcbComputedHash
0x18000937c  lea     rax, [rbp+0C0h+pbComputedHash]
0x180009380  mov     [rsp+1C0h+hTransaction], rax; pbComputedHash
0x180009385  mov     eax, [r9+10h]
0x180009389  mov     r9, [r9+8]; pbEncoded
0x18000938d  mov     dword ptr [rsp+1C0h+phkResult], eax; cbEncoded
0x180009391  call    cs:__imp_CryptHashCertificate
0x180009397  test    eax, eax
0x180009399  jz      short loc_1800093F4
0x18000939b  cmp     [rsp+1C0h+pcbComputedHash], 0
0x1800093a0  jbe     short loc_1800093D5
0x1800093a2  mov     eax, r14d
0x1800093a5  lea     ecx, [r14+r14]
0x1800093a9  mov     edx, 50h ; 'P'
0x1800093ae  lea     r8, a22x; "%2.2x"
0x1800093b5  sub     rdx, rcx
0x1800093b8  movzx   r9d, [rbp+rax+0C0h+pbComputedHash]
0x1800093be  lea     rax, [rbp+0C0h+var_F0]
0x1800093c2  lea     rcx, [rax+rcx*2]
0x1800093c6  call    RtlStringCchPrintfW
0x1800093cb  inc     r14d
0x1800093ce  cmp     r14d, [rsp+1C0h+pcbComputedHash]
0x1800093d3  jb      short loc_1800093A2
0x1800093d5  lea     rdx, [rbp+0C0h+var_F0]
0x1800093d9  mov     rcx, r12; hDevice
0x1800093dc  call    AiUpdateDriverCertDataFromRegistry
0x1800093e1  inc     esi
0x1800093e3  mov     r14d, 0
0x1800093e9  cmp     esi, 2
0x1800093ec  jb      loc_180009311
0x1800093f2  jmp     short loc_180009403
0x1800093f4  call    cs:__imp_GetLastError
0x1800093fa  mov     ebx, eax
0x1800093fc  jmp     short loc_180009403
0x1800093fe  mov     ebx, 57h ; 'W'
0x180009403  mov     rcx, [rsp+1C0h+var_158]; hKey
0x180009408  test    rcx, rcx
0x18000940b  jz      short loc_180009413
0x18000940d  call    cs:__imp_RegCloseKey
0x180009413  mov     rcx, [rsp+1C0h+hObject]; hObject
0x180009418  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000941c  jz      short loc_180009424
0x18000941e  call    cs:__imp_CloseHandle
0x180009424  mov     eax, ebx
0x180009426  mov     rcx, [rbp+0C0h+var_50]
0x18000942a  xor     rcx, rsp; StackCookie
0x18000942d  call    __security_check_cookie
0x180009432  add     rsp, 188h
0x180009439  pop     r15
0x18000943b  pop     r14
0x18000943d  pop     r13
0x18000943f  pop     r12
0x180009441  pop     rdi
0x180009442  pop     rsi
0x180009443  pop     rbx
0x180009444  pop     rbp
0x180009445  retn
```
