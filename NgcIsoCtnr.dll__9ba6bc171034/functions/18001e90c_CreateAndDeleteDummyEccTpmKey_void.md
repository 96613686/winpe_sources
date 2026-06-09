# CreateAndDeleteDummyEccTpmKey(void)

- ea: `0x18001e90c`
- end: `0x18001ea14`
- name: `?CreateAndDeleteDummyEccTpmKey@@YAJXZ`
- size: `264`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ea1c`

## callees

- `0x18000d62c`
- `0x1800108e4`
- `0x180011174`
- `0x18001cb98`
- `0x18001e90c`
- `0x18002bfec`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x18001e9dd`
- `ncrypt!NCryptDeleteKey` at `0x18001e9dd`
- `ncrypt!NCryptFinalizeKey` at `0x18001e9ba`
- `ncrypt!NCryptFinalizeKey` at `0x18001e9ba`
- `ncrypt!NCryptSetProperty` at `0x18001e98c`
- `ncrypt!NCryptSetProperty` at `0x18001e98c`
- `ncrypt!NCryptCreatePersistedKey` at `0x18001e952`
- `ncrypt!NCryptCreatePersistedKey` at `0x18001e952`

## string_xrefs

- `0x18001e9a5`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x18001e9ef`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CreateAndDeleteDummyEccTpmKey(void)
{
  NCRYPT_PROV_HANDLE *v0; // rax
  SECURITY_STATUS v1; // eax
  unsigned int v2; // ebx
  __int64 v3; // rdx
  NCRYPT_KEY_HANDLE v4; // rcx
  SECURITY_STATUS v5; // eax
  DWORD dwLegacyKeySpec; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int pbInput; // [rsp+40h] [rbp+8h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp+10h] BYREF

  phKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phKey,
    0);
  v0 = (NCRYPT_PROV_HANDLE *)VsmUtils::Vtl0Tpm::Instance();
  v1 = NCryptCreatePersistedKey(*v0, &phKey, L"ECDSA_P256", L"//NgcEcckey//dummyKey", 0, 0x80u);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 400;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)v1,
      dwLegacyKeySpec);
    goto LABEL_11;
  }
  pbInput = 1;
  v1 = NCryptSetProperty(phKey, L"PCP_KEY_USAGE_POLICY", (PBYTE)&pbInput, 4u, 0);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 408;
    goto LABEL_5;
  }
  v1 = NCryptFinalizeKey(phKey, 0);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 412;
    goto LABEL_5;
  }
  v4 = phKey;
  phKey = 0;
  v5 = NCryptDeleteKey(v4, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1A0,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)v5,
      dwLegacyKeySpec);
  v2 = 0;
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  return v2;
}

```

## disassembly

```asm
0x18001e90c  push    rbx
0x18001e90e  sub     rsp, 30h
0x18001e912  mov     [rsp+38h+phKey], 0
0x18001e91b  xor     edx, edx
0x18001e91d  lea     rcx, [rsp+38h+phKey]
0x18001e922  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18001e927  call    ?Instance@Vtl0Tpm@VsmUtils@@SAAEAV12@XZ; VsmUtils::Vtl0Tpm::Instance(void)
0x18001e92c  mov     [rsp+38h+dwFlags], 80h; dwFlags
0x18001e934  mov     [rsp+38h+dwLegacyKeySpec], 0; dwLegacyKeySpec
0x18001e93c  lea     r9, pszKeyName; "//NgcEcckey//dummyKey"
0x18001e943  lea     r8, pszAlgId; "ECDSA_P256"
0x18001e94a  lea     rdx, [rsp+38h+phKey]; phKey
0x18001e94f  mov     rcx, [rax]; hProvider
0x18001e952  call    cs:__imp_NCryptCreatePersistedKey
0x18001e958  mov     ebx, eax
0x18001e95a  test    eax, eax
0x18001e95c  jns     short loc_18001E965
0x18001e95e  mov     edx, 190h
0x18001e963  jmp     short loc_18001E99D
0x18001e965  mov     [rsp+38h+pbInput], 1
0x18001e96d  mov     [rsp+38h+dwLegacyKeySpec], 0; int
0x18001e975  mov     r9d, 4; cbInput
0x18001e97b  lea     r8, [rsp+38h+pbInput]; pbInput
0x18001e980  lea     rdx, pszProperty; "PCP_KEY_USAGE_POLICY"
0x18001e987  mov     rcx, [rsp+38h+phKey]; hObject
0x18001e98c  call    cs:__imp_NCryptSetProperty
0x18001e992  mov     ebx, eax
0x18001e994  test    eax, eax
0x18001e996  jns     short loc_18001E9B3
0x18001e998  mov     edx, 198h; void *
0x18001e99d  mov     rcx, [rsp+38h]; this
0x18001e9a2  mov     r9d, eax; char *
0x18001e9a5  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18001e9ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9b1  jmp     short loc_18001EA02
0x18001e9b3  xor     edx, edx; dwFlags
0x18001e9b5  mov     rcx, [rsp+38h+phKey]; hKey
0x18001e9ba  call    cs:__imp_NCryptFinalizeKey
0x18001e9c0  mov     ebx, eax
0x18001e9c2  test    eax, eax
0x18001e9c4  jns     short loc_18001E9CD
0x18001e9c6  mov     edx, 19Ch
0x18001e9cb  jmp     short loc_18001E99D
0x18001e9cd  mov     rcx, [rsp+38h+phKey]; hKey
0x18001e9d2  mov     [rsp+38h+phKey], 0
0x18001e9db  xor     edx, edx; dwFlags
0x18001e9dd  call    cs:__imp_NCryptDeleteKey
0x18001e9e3  mov     rcx, [rsp+38h]; this
0x18001e9e8  test    eax, eax
0x18001e9ea  jns     short loc_18001EA00
0x18001e9ec  mov     r9d, eax; char *
0x18001e9ef  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18001e9f6  mov     edx, 1A0h; void *
0x18001e9fb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ea00  xor     ebx, ebx
0x18001ea02  lea     rcx, [rsp+38h+phKey]
0x18001ea07  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001ea0c  mov     eax, ebx
0x18001ea0e  add     rsp, 30h
0x18001ea12  pop     rbx
0x18001ea13  retn
```
