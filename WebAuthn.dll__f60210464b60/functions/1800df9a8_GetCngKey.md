# GetCngKey

- ea: `0x1800df9a8`
- end: `0x1800dfbfb`
- name: `GetCngKey`
- size: `595`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800df268`
- `0x1800df400`
- `0x1800e0144`
- `0x1800e0f3c`

## callees

- `0x1800df9a8`
- `0x1800dfd20`
- `0x1800dff80`
- `0x1800dffb0`
- `0x1800e1c64`
- `0x18013c064`
- `0x18013c090`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800dfb71`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800dfb71`
- `ncrypt!NCryptFreeObject` at `0x1800dfbb1`
- `ncrypt!NCryptFreeObject` at `0x1800dfbcc`
- `ncrypt!NCryptFreeObject` at `0x1800dfbb1`
- `ncrypt!NCryptFreeObject` at `0x1800dfbcc`
- `ncrypt!NCryptOpenKey` at `0x1800dfa21`
- `ncrypt!NCryptOpenKey` at `0x1800dfa21`
- `ncrypt!NCryptFinalizeKey` at `0x1800dfb87`
- `ncrypt!NCryptFinalizeKey` at `0x1800dfb87`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800dfacd`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800dfacd`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800df9f3`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800df9f3`
- `ncrypt!NCryptSetProperty` at `0x1800dfb1c`
- `ncrypt!NCryptSetProperty` at `0x1800dfb51`
- `ncrypt!NCryptSetProperty` at `0x1800dfb1c`
- `ncrypt!NCryptSetProperty` at `0x1800dfb51`
- `ncrypt!NCryptDeleteKey` at `0x1800dfa7e`
- `ncrypt!NCryptDeleteKey` at `0x1800dfa7e`

## string_xrefs

- `0x1800df9ff`: `NCryptOpenStorageProvider`
- `0x1800dfa6a`: `RegDeleteCredentialId`
- `0x1800dfad9`: `NCryptCreatePersistedKey`
- `0x1800dfa92`: `NCryptDeleteKey`
- `0x1800dfaa2`: `NCryptOpenKey`

## pseudocode

```c
__int64 __fastcall GetCngKey(LPCWSTR pszKeyName, __int64 a2, int a3, NCRYPT_KEY_HANDLE *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  const char *v10; // rcx
  DWORD CredentialIdFromNCryptKeyHandle; // eax
  char *v12; // rcx
  int v13; // eax
  DWORD v14; // edx
  NCRYPT_KEY_HANDLE v15; // rax
  NCRYPT_KEY_HANDLE phKey; // [rsp+30h] [rbp-40h] BYREF
  BYTE pbInput[8]; // [rsp+38h] [rbp-38h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+40h] [rbp-30h] BYREF
  _OWORD v20[2]; // [rsp+48h] [rbp-28h] BYREF

  phProvider = 0;
  phKey = 0;
  v8 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
  v9 = v8;
  if ( v8 )
  {
    v10 = "NCryptOpenStorageProvider";
    goto LABEL_25;
  }
  v8 = NCryptOpenKey(phProvider, &phKey, pszKeyName, 0, 0);
  v9 = v8;
  if ( !v8 )
  {
    if ( a3 >= 0 )
      goto LABEL_27;
    memset(v20, 0, sizeof(v20));
    CredentialIdFromNCryptKeyHandle = GetCredentialIdFromNCryptKeyHandle(a2, phKey, v20);
    if ( CredentialIdFromNCryptKeyHandle )
    {
      v12 = "GetCredentialIdFromNCryptKeyHandle";
    }
    else
    {
      CredentialIdFromNCryptKeyHandle = RegDeleteCredentialId(v20);
      if ( !CredentialIdFromNCryptKeyHandle )
        goto LABEL_10;
      v12 = "RegDeleteCredentialId";
    }
    PrintError(v12, CredentialIdFromNCryptKeyHandle);
LABEL_10:
    v8 = NCryptDeleteKey(phKey, 0);
    phKey = 0;
    v9 = v8;
    if ( v8 )
    {
      v10 = "NCryptDeleteKey";
      goto LABEL_25;
    }
    goto LABEL_14;
  }
  if ( !a3 )
  {
    v10 = "NCryptOpenKey";
    goto LABEL_25;
  }
LABEL_14:
  v8 = NCryptCreatePersistedKey(phProvider, &phKey, *(LPCWSTR *)(a2 + 32), pszKeyName, 0, 0);
  v9 = v8;
  if ( v8 )
  {
    v10 = "NCryptCreatePersistedKey";
    goto LABEL_25;
  }
  if ( !wcscmp_0(*(const wchar_t **)(a2 + 32), L"RSA") )
  {
    *(_DWORD *)pbInput = 2048;
    v8 = NCryptSetProperty(phKey, L"Length", pbInput, 4u, 0x80000000);
    v9 = v8;
    if ( v8 )
    {
      v10 = "NCryptSetProperty(NCRYPT_LENGTH_PROPERTY)";
      goto LABEL_25;
    }
  }
  *(_DWORD *)pbInput = 15;
  v8 = NCryptSetProperty(phKey, L"Export Policy", pbInput, 4u, 0x80000000);
  v9 = v8;
  if ( v8 )
  {
    v10 = "NCryptSetProperty(NCRYPT_EXPORT_POLICY_PROPERTY)";
    goto LABEL_25;
  }
  v13 = _o__wcsicmp(*(_QWORD *)(a2 + 32), L"RSA");
  v14 = 512;
  if ( v13 )
    v14 = 0;
  v8 = NCryptFinalizeKey(phKey, v14);
  v9 = v8;
  if ( !v8 )
  {
LABEL_27:
    v15 = phKey;
    goto LABEL_28;
  }
  v10 = "NCryptFinalizeKey";
LABEL_25:
  PrintStatus(v10, pszKeyName, v8);
  v15 = phKey;
  if ( phKey )
  {
    NCryptFreeObject(phKey);
    v15 = 0;
    phKey = 0;
  }
LABEL_28:
  if ( phProvider )
  {
    NCryptFreeObject(phProvider);
    v15 = phKey;
  }
  *a4 = v15;
  return v9;
}

```

## disassembly

```asm
0x1800df9a8  mov     [rsp-28h+arg_10], rbx
0x1800df9ad  push    rbp
0x1800df9ae  push    rsi
0x1800df9af  push    rdi
0x1800df9b0  push    r14
0x1800df9b2  push    r15
0x1800df9b4  mov     rbp, rsp
0x1800df9b7  sub     rsp, 70h
0x1800df9bb  mov     rax, cs:__security_cookie
0x1800df9c2  xor     rax, rsp
0x1800df9c5  mov     [rbp+var_8], rax
0x1800df9c9  mov     esi, r8d
0x1800df9cc  mov     [rbp+phProvider], 0
0x1800df9d4  mov     r14, rdx
0x1800df9d7  mov     [rbp+phKey], 0
0x1800df9df  mov     rdi, rcx
0x1800df9e2  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x1800df9e9  xor     r8d, r8d; dwFlags
0x1800df9ec  lea     rcx, [rbp+phProvider]; phProvider
0x1800df9f0  mov     r15, r9
0x1800df9f3  call    cs:__imp_NCryptOpenStorageProvider
0x1800df9f9  mov     ebx, eax
0x1800df9fb  test    eax, eax
0x1800df9fd  jz      short loc_1800DFA0B
0x1800df9ff  lea     rcx, aNcryptopenstor_0; "NCryptOpenStorageProvider"
0x1800dfa06  jmp     loc_1800DFB9A
0x1800dfa0b  mov     rcx, [rbp+phProvider]; hProvider
0x1800dfa0f  lea     rdx, [rbp+phKey]; phKey
0x1800dfa13  xor     r9d, r9d; dwLegacyKeySpec
0x1800dfa16  mov     [rsp+70h+dwFlags], 0; dwFlags
0x1800dfa1e  mov     r8, rdi; pszKeyName
0x1800dfa21  call    cs:__imp_NCryptOpenKey
0x1800dfa27  mov     ebx, eax
0x1800dfa29  test    eax, eax
0x1800dfa2b  jnz     short loc_1800DFA9E
0x1800dfa2d  test    esi, esi
0x1800dfa2f  jns     loc_1800DFBBF
0x1800dfa35  mov     rdx, [rbp+phKey]
0x1800dfa39  lea     r8, [rbp+var_28]
0x1800dfa3d  xorps   xmm0, xmm0
0x1800dfa40  mov     rcx, r14
0x1800dfa43  movups  [rbp+var_28], xmm0
0x1800dfa47  movups  [rbp+var_18], xmm0
0x1800dfa4b  call    GetCredentialIdFromNCryptKeyHandle
0x1800dfa50  test    eax, eax
0x1800dfa52  jz      short loc_1800DFA5D
0x1800dfa54  lea     rcx, aGetcredentiali; "GetCredentialIdFromNCryptKeyHandle"
0x1800dfa5b  jmp     short loc_1800DFA71
0x1800dfa5d  lea     rcx, [rbp+var_28]
0x1800dfa61  call    RegDeleteCredentialId
0x1800dfa66  test    eax, eax
0x1800dfa68  jz      short loc_1800DFA78
0x1800dfa6a  lea     rcx, aRegdeletecrede; "RegDeleteCredentialId"
0x1800dfa71  mov     edx, eax; dwErrId
0x1800dfa73  call    PrintError
0x1800dfa78  mov     rcx, [rbp+phKey]; hKey
0x1800dfa7c  xor     edx, edx; dwFlags
0x1800dfa7e  call    cs:__imp_NCryptDeleteKey
0x1800dfa84  mov     [rbp+phKey], 0
0x1800dfa8c  mov     ebx, eax
0x1800dfa8e  test    eax, eax
0x1800dfa90  jz      short loc_1800DFAAE
0x1800dfa92  lea     rcx, aNcryptdeleteke_0; "NCryptDeleteKey"
0x1800dfa99  jmp     loc_1800DFB9A
0x1800dfa9e  test    esi, esi
0x1800dfaa0  jnz     short loc_1800DFAAE
0x1800dfaa2  lea     rcx, aNcryptopenkey_0; "NCryptOpenKey"
0x1800dfaa9  jmp     loc_1800DFB9A
0x1800dfaae  mov     r8, [r14+20h]; pszAlgId
0x1800dfab2  lea     rdx, [rbp+phKey]; phKey
0x1800dfab6  mov     rcx, [rbp+phProvider]; hProvider
0x1800dfaba  mov     r9, rdi; pszKeyName
0x1800dfabd  mov     [rsp+70h+var_48], 0; dwFlags
0x1800dfac5  mov     [rsp+70h+dwFlags], 0; dwLegacyKeySpec
0x1800dfacd  call    cs:__imp_NCryptCreatePersistedKey
0x1800dfad3  mov     ebx, eax
0x1800dfad5  test    eax, eax
0x1800dfad7  jz      short loc_1800DFAE5
0x1800dfad9  lea     rcx, aNcryptcreatepe_0; "NCryptCreatePersistedKey"
0x1800dfae0  jmp     loc_1800DFB9A
0x1800dfae5  mov     rcx, [r14+20h]; String1
0x1800dfae9  lea     rdx, aRsa; "RSA"
0x1800dfaf0  call    wcscmp_0
0x1800dfaf5  mov     esi, 80000000h
0x1800dfafa  test    eax, eax
0x1800dfafc  jnz     short loc_1800DFB31
0x1800dfafe  mov     rcx, [rbp+phKey]; hObject
0x1800dfb02  lea     r9d, [rax+4]; cbInput
0x1800dfb06  lea     r8, [rbp+pbInput]; pbInput
0x1800dfb0a  mov     dword ptr [rbp+pbInput], 800h
0x1800dfb11  lea     rdx, aLength; "Length"
0x1800dfb18  mov     [rsp+70h+dwFlags], esi; dwFlags
0x1800dfb1c  call    cs:__imp_NCryptSetProperty
0x1800dfb22  mov     ebx, eax
0x1800dfb24  test    eax, eax
0x1800dfb26  jz      short loc_1800DFB31
0x1800dfb28  lea     rcx, aNcryptsetprope_1; "NCryptSetProperty(NCRYPT_LENGTH_PROPERT"...
0x1800dfb2f  jmp     short loc_1800DFB9A
0x1800dfb31  mov     rcx, [rbp+phKey]; hObject
0x1800dfb35  lea     r8, [rbp+pbInput]; pbInput
0x1800dfb39  mov     r9d, 4; cbInput
0x1800dfb3f  mov     dword ptr [rbp+pbInput], 0Fh
0x1800dfb46  lea     rdx, aExportPolicy; "Export Policy"
0x1800dfb4d  mov     [rsp+70h+dwFlags], esi; dwFlags
0x1800dfb51  call    cs:__imp_NCryptSetProperty
0x1800dfb57  mov     ebx, eax
0x1800dfb59  test    eax, eax
0x1800dfb5b  jz      short loc_1800DFB66
0x1800dfb5d  lea     rcx, aNcryptsetprope_0; "NCryptSetProperty(NCRYPT_EXPORT_POLICY_"...
0x1800dfb64  jmp     short loc_1800DFB9A
0x1800dfb66  mov     rcx, [r14+20h]
0x1800dfb6a  lea     rdx, aRsa; "RSA"
0x1800dfb71  call    cs:__imp__o__wcsicmp
0x1800dfb77  xor     ecx, ecx
0x1800dfb79  mov     edx, 200h
0x1800dfb7e  test    eax, eax
0x1800dfb80  cmovnz  edx, ecx; dwFlags
0x1800dfb83  mov     rcx, [rbp+phKey]; hKey
0x1800dfb87  call    cs:__imp_NCryptFinalizeKey
0x1800dfb8d  mov     ebx, eax
0x1800dfb8f  test    eax, eax
0x1800dfb91  jz      short loc_1800DFBBF
0x1800dfb93  lea     rcx, aNcryptfinalize_0; "NCryptFinalizeKey"
0x1800dfb9a  mov     r8d, eax
0x1800dfb9d  mov     rdx, rdi
0x1800dfba0  call    PrintStatus
0x1800dfba5  mov     rax, [rbp+phKey]
0x1800dfba9  test    rax, rax
0x1800dfbac  jz      short loc_1800DFBC3
0x1800dfbae  mov     rcx, rax; hObject
0x1800dfbb1  call    cs:__imp_NCryptFreeObject
0x1800dfbb7  xor     eax, eax
0x1800dfbb9  mov     [rbp+phKey], rax
0x1800dfbbd  jmp     short loc_1800DFBC3
0x1800dfbbf  mov     rax, [rbp+phKey]
0x1800dfbc3  mov     rcx, [rbp+phProvider]; hObject
0x1800dfbc7  test    rcx, rcx
0x1800dfbca  jz      short loc_1800DFBD6
0x1800dfbcc  call    cs:__imp_NCryptFreeObject
0x1800dfbd2  mov     rax, [rbp+phKey]
0x1800dfbd6  mov     [r15], rax
0x1800dfbd9  mov     eax, ebx
0x1800dfbdb  mov     rcx, [rbp+var_8]
0x1800dfbdf  xor     rcx, rsp; StackCookie
0x1800dfbe2  call    __security_check_cookie
0x1800dfbe7  mov     rbx, [rsp+70h+arg_10]
0x1800dfbef  add     rsp, 70h
0x1800dfbf3  pop     r15
0x1800dfbf5  pop     r14
0x1800dfbf7  pop     rdi
0x1800dfbf8  pop     rsi
0x1800dfbf9  pop     rbp
0x1800dfbfa  retn
```
