# LookForPublicKeyMatch

- ea: `0x180039060`
- end: `0x1800391bf`
- name: `LookForPublicKeyMatch`
- size: `351`
- prototype: `__int64 __fastcall(void *pvObject, PCERT_PUBLIC_KEY_INFO pPublicKey2)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800367d4`

## callees

- `0x1800340fc`
- `0x180034138`
- `0x180039060`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003912c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039122`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003912c`
- `CRYPT32!CryptQueryObject` at `0x180039103`
- `CRYPT32!CryptQueryObject` at `0x180039103`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180039170`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180039170`
- `CRYPT32!CertFreeCertificateContext` at `0x180039195`
- `CRYPT32!CertFreeCertificateContext` at `0x180039195`
- `CRYPT32!CertComparePublicKeyInfo` at `0x18003915f`
- `CRYPT32!CertComparePublicKeyInfo` at `0x18003915f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LookForPublicKeyMatch(void *pvObject, PCERT_PUBLIC_KEY_INFO pPublicKey2, _DWORD *a3)
{
  BOOL v5; // ebx
  unsigned int LastError; // ebx
  const CERT_CONTEXT *i; // rdx
  PCCERT_CONTEXT v8; // rax
  const CERT_CONTEXT *v9; // rdi
  DWORD v11; // [rsp+68h] [rbp+17h] BYREF
  HCERTSTORE hCertStore; // [rsp+70h] [rbp+1Fh] BYREF
  HCERTSTORE *p_hCertStore; // [rsp+78h] [rbp+27h] BYREF
  HCERTSTORE v14; // [rsp+80h] [rbp+2Fh] BYREF
  char v15; // [rsp+88h] [rbp+37h]
  DWORD dwCertEncodingType; // [rsp+C8h] [rbp+77h] BYREF
  DWORD v17; // [rsp+D0h] [rbp+7Fh] BYREF

  hCertStore = 0;
  dwCertEncodingType = 0;
  v11 = 0;
  v17 = 0;
  *a3 = 0;
  p_hCertStore = &hCertStore;
  v14 = 0;
  v15 = 1;
  v5 = CryptQueryObject(2u, pvObject, 0x3FFEu, 0xEu, 0, &dwCertEncodingType, &v11, &v17, &v14, 0, 0);
  __1__out_param_t_V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___details_wil__QEAA_XZ(&p_hCertStore);
  if ( v5 )
  {
    LastError = 0;
    for ( i = 0; ; i = v9 )
    {
      v8 = CertEnumCertificatesInStore(hCertStore, i);
      v9 = v8;
      if ( !v8 )
        break;
      if ( CertComparePublicKeyInfo(dwCertEncodingType, &v8->pCertInfo->SubjectPublicKeyInfo, pPublicKey2) )
      {
        *a3 = 1;
        SBServicingLogMessage((wchar_t *)L"LookForPublicKeyMatch: matchFound");
        CertFreeCertificateContext(v9);
        break;
      }
    }
  }
  else
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      LastError = GetLastError();
    SBServicingLogMessage((wchar_t *)L"LookForPublicKeyMatch: Failed CryptQueryObject2: 0x%08x", LastError);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hCertStore);
  return LastError;
}

```

## disassembly

```asm
0x180039060  mov     r11, rsp
0x180039063  mov     [r11+8], rbx
0x180039067  mov     [r11+10h], rsi
0x18003906b  push    rbp
0x18003906c  push    rdi
0x18003906d  push    r14
0x18003906f  lea     rbp, [r11-5Fh]
0x180039073  sub     rsp, 90h
0x18003907a  mov     rsi, r8
0x18003907d  mov     r14, rdx
0x180039080  mov     [rbp+57h+hCertStore], 0
0x180039088  mov     [rbp+57h+dwCertEncodingType], 0
0x18003908f  mov     [rbp+57h+var_40], 0
0x180039096  mov     [rbp+57h+arg_18], 0
0x18003909d  mov     dword ptr [r8], 0
0x1800390a4  lea     rax, [rbp+57h+hCertStore]
0x1800390a8  mov     [rbp+57h+var_30], rax
0x1800390ac  mov     [rbp+57h+var_28], 0
0x1800390b4  mov     [rbp+57h+var_20], 1
0x1800390b8  mov     qword ptr [r11-58h], 0
0x1800390c0  mov     qword ptr [r11-60h], 0
0x1800390c8  lea     rax, [rbp+57h+var_28]
0x1800390cc  mov     [r11-68h], rax
0x1800390d0  lea     rax, [rbp+57h+arg_18]
0x1800390d4  mov     [r11-70h], rax
0x1800390d8  lea     rax, [rbp+57h+var_40]
0x1800390dc  mov     [r11-78h], rax
0x1800390e0  lea     rax, [rbp+57h+dwCertEncodingType]
0x1800390e4  mov     [r11-80h], rax
0x1800390e8  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x1800390f0  mov     r9d, 0Eh; dwExpectedFormatTypeFlags
0x1800390f6  mov     r8d, 3FFEh; dwExpectedContentTypeFlags
0x1800390fc  mov     rdx, rcx; pvObject
0x1800390ff  lea     ecx, [r9-0Ch]; dwObjectType
0x180039103  call    cs:__imp_CryptQueryObject
0x180039109  mov     ebx, eax
0x18003910b  lea     rcx, [rbp+57h+var_30]
0x18003910f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ
0x180039114  test    ebx, ebx
0x180039116  jnz     short loc_18003914B
0x180039118  call    cs:__imp_GetLastError
0x18003911e  test    eax, eax
0x180039120  jg      short loc_18003912C
0x180039122  call    cs:__imp_GetLastError
0x180039128  mov     ebx, eax
0x18003912a  jmp     short loc_18003913B
0x18003912c  call    cs:__imp_GetLastError
0x180039132  movzx   ebx, ax
0x180039135  or      ebx, 0C0070000h
0x18003913b  mov     edx, ebx
0x18003913d  lea     rcx, aLookforpublick_0; "LookForPublicKeyMatch: Failed CryptQuer"...
0x180039144  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180039149  jmp     short loc_18003919C
0x18003914b  xor     ebx, ebx
0x18003914d  xor     edx, edx
0x18003914f  jmp     short loc_18003916C
0x180039151  mov     rdx, [rdi+18h]
0x180039155  add     rdx, 60h ; '`'; pPublicKey1
0x180039159  mov     r8, r14; pPublicKey2
0x18003915c  mov     ecx, [rbp+57h+dwCertEncodingType]; dwCertEncodingType
0x18003915f  call    cs:__imp_CertComparePublicKeyInfo
0x180039165  test    eax, eax
0x180039167  jnz     short loc_180039180
0x180039169  mov     rdx, rdi; pPrevCertContext
0x18003916c  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x180039170  call    cs:__imp_CertEnumCertificatesInStore
0x180039176  test    rax, rax
0x180039179  mov     rdi, rax
0x18003917c  jnz     short loc_180039151
0x18003917e  jmp     short loc_18003919C
0x180039180  mov     dword ptr [rsi], 1
0x180039186  lea     rcx, aLookforpublick; "LookForPublicKeyMatch: matchFound"
0x18003918d  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180039192  mov     rcx, rdi; pCertContext
0x180039195  call    cs:__imp_CertFreeCertificateContext
0x18003919b  nop
0x18003919c  lea     rcx, [rbp+57h+hCertStore]
0x1800391a0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800391a5  mov     eax, ebx
0x1800391a7  lea     r11, [rsp+0A0h+var_10]
0x1800391af  mov     rbx, [r11+20h]
0x1800391b3  mov     rsi, [r11+28h]
0x1800391b7  mov     rsp, r11
0x1800391ba  pop     r14
0x1800391bc  pop     rdi
0x1800391bd  pop     rbp
0x1800391be  retn
```
