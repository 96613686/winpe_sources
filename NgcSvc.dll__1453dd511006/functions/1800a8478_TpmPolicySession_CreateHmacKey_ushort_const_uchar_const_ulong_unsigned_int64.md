# TpmPolicySession::CreateHmacKey(ushort const *,uchar const *,ulong,unsigned __int64 *)

- ea: `0x1800a8478`
- end: `0x1800a85fe`
- name: `?CreateHmacKey@TpmPolicySession@@YAJPEBGPEBEKPEA_K@Z`
- size: `390`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName, PBYTE pbInput, DWORD cbInput, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004f218`

## callees

- `0x18000782c`
- `0x18004f1b0`
- `0x18005bef0`
- `0x1800a8478`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x1800a8569`
- `ncrypt!NCryptSetProperty` at `0x1800a8595`
- `ncrypt!NCryptSetProperty` at `0x1800a8569`
- `ncrypt!NCryptSetProperty` at `0x1800a8595`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800a84b5`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800a84b5`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800a8513`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800a8513`
- `ncrypt!NCryptFinalizeKey` at `0x1800a85b1`
- `ncrypt!NCryptFinalizeKey` at `0x1800a85b1`

## string_xrefs

- `0x1800a84c5`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a8528`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c
__int64 __fastcall TpmPolicySession::CreateHmacKey(
        LPCWSTR pszKeyName,
        PBYTE pbInput,
        DWORD cbInput,
        NCRYPT_KEY_HANDLE *a4)
{
  SECURITY_STATUS v8; // eax
  unsigned int v9; // ebx
  SECURITY_STATUS v10; // eax
  __int64 v11; // rdx
  DWORD dwLegacyKeySpec; // [rsp+20h] [rbp-38h]
  DWORD dwLegacyKeySpeca; // [rsp+20h] [rbp-38h]
  BYTE pbInputa[8]; // [rsp+30h] [rbp-28h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-20h] BYREF
  NCRYPT_PROV_HANDLE phProvider[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]

  phProvider[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    phProvider,
    0);
  v8 = NCryptOpenStorageProvider(phProvider, L"Microsoft Platform Crypto Provider", 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
      (const char *)(unsigned int)v8,
      dwLegacyKeySpec);
    goto LABEL_15;
  }
  phKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phKey,
    0);
  v10 = NCryptCreatePersistedKey(phProvider[0], &phKey, L"HMAC-SHA256", pszKeyName, 0, 0);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = 34;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\lib\\tpmpolicysession.cpp",
      (const char *)(unsigned int)v10,
      dwLegacyKeySpeca);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    goto LABEL_15;
  }
  *(_DWORD *)pbInputa = 16;
  v10 = NCryptSetProperty(phKey, L"PCP_KEY_USAGE_POLICY", pbInputa, 4u, 0);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = 43;
    goto LABEL_5;
  }
  v10 = NCryptSetProperty(phKey, L"KeyDataBlob", pbInput, cbInput, 0);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = 51;
    goto LABEL_5;
  }
  v10 = NCryptFinalizeKey(phKey, 0);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = 56;
    goto LABEL_5;
  }
  if ( a4 )
  {
    *a4 = phKey;
    phKey = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  v9 = 0;
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(phProvider);
  return v9;
}

```

## disassembly

```asm
0x1800a8478  push    rbp
0x1800a847a  push    rbx
0x1800a847b  push    rsi
0x1800a847c  push    rdi
0x1800a847d  push    r14
0x1800a847f  push    r15
0x1800a8481  mov     rbp, rsp
0x1800a8484  sub     rsp, 58h
0x1800a8488  mov     r14, rdx
0x1800a848b  mov     [rbp+phProvider], 0
0x1800a8493  mov     r15, rcx
0x1800a8496  xor     edx, edx
0x1800a8498  lea     rcx, [rbp+phProvider]
0x1800a849c  mov     rdi, r9
0x1800a849f  mov     esi, r8d
0x1800a84a2  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800a84a7  xor     r8d, r8d; dwFlags
0x1800a84aa  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x1800a84b1  lea     rcx, [rbp+phProvider]; phProvider
0x1800a84b5  call    cs:__imp_NCryptOpenStorageProvider
0x1800a84bb  mov     ebx, eax
0x1800a84bd  test    eax, eax
0x1800a84bf  jns     short loc_1800A84DE
0x1800a84c1  mov     rcx, [rbp+30h]; this
0x1800a84c5  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a84cc  mov     r9d, eax; char *
0x1800a84cf  mov     edx, 18h; void *
0x1800a84d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a84d9  jmp     loc_1800A85E6
0x1800a84de  xor     edx, edx
0x1800a84e0  mov     [rbp+phKey], 0
0x1800a84e8  lea     rcx, [rbp+phKey]
0x1800a84ec  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x1800a84f1  mov     rcx, [rbp+phProvider]; hProvider
0x1800a84f5  lea     r8, pszAlgId; "HMAC-SHA256"
0x1800a84fc  mov     r9, r15; pszKeyName
0x1800a84ff  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1800a8507  lea     rdx, [rbp+phKey]; phKey
0x1800a850b  mov     [rsp+58h+dwLegacyKeySpec], 0; int
0x1800a8513  call    cs:__imp_NCryptCreatePersistedKey
0x1800a8519  mov     ebx, eax
0x1800a851b  test    eax, eax
0x1800a851d  jns     short loc_1800A8545
0x1800a851f  mov     edx, 22h ; '"'; void *
0x1800a8524  mov     rcx, [rbp+30h]; this
0x1800a8528  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1800a852f  mov     r9d, eax; char *
0x1800a8532  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8537  lea     rcx, [rbp+phKey]
0x1800a853b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a8540  jmp     loc_1800A85E6
0x1800a8545  mov     rcx, [rbp+phKey]; hObject
0x1800a8549  lea     r8, [rbp+pbInput]; pbInput
0x1800a854d  mov     r9d, 4; cbInput
0x1800a8553  mov     dword ptr [rbp+pbInput], 10h
0x1800a855a  lea     rdx, aPcpKeyUsagePol; "PCP_KEY_USAGE_POLICY"
0x1800a8561  mov     [rsp+58h+dwLegacyKeySpec], 0; dwFlags
0x1800a8569  call    cs:__imp_NCryptSetProperty
0x1800a856f  mov     ebx, eax
0x1800a8571  test    eax, eax
0x1800a8573  jns     short loc_1800A857C
0x1800a8575  mov     edx, 2Bh ; '+'
0x1800a857a  jmp     short loc_1800A8524
0x1800a857c  mov     rcx, [rbp+phKey]; hObject
0x1800a8580  lea     rdx, aKeydatablob; "KeyDataBlob"
0x1800a8587  mov     r9d, esi; cbInput
0x1800a858a  mov     [rsp+58h+dwLegacyKeySpec], 0; dwFlags
0x1800a8592  mov     r8, r14; pbInput
0x1800a8595  call    cs:__imp_NCryptSetProperty
0x1800a859b  mov     ebx, eax
0x1800a859d  test    eax, eax
0x1800a859f  jns     short loc_1800A85AB
0x1800a85a1  mov     edx, 33h ; '3'
0x1800a85a6  jmp     loc_1800A8524
0x1800a85ab  mov     rcx, [rbp+phKey]; hKey
0x1800a85af  xor     edx, edx; dwFlags
0x1800a85b1  call    cs:__imp_NCryptFinalizeKey
0x1800a85b7  mov     ebx, eax
0x1800a85b9  test    eax, eax
0x1800a85bb  jns     short loc_1800A85C7
0x1800a85bd  mov     edx, 38h ; '8'
0x1800a85c2  jmp     loc_1800A8524
0x1800a85c7  test    rdi, rdi
0x1800a85ca  jz      short loc_1800A85DB
0x1800a85cc  mov     rax, [rbp+phKey]
0x1800a85d0  mov     [rdi], rax
0x1800a85d3  mov     [rbp+phKey], 0
0x1800a85db  lea     rcx, [rbp+phKey]
0x1800a85df  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a85e4  xor     ebx, ebx
0x1800a85e6  lea     rcx, [rbp+phProvider]
0x1800a85ea  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800a85ef  mov     eax, ebx
0x1800a85f1  add     rsp, 58h
0x1800a85f5  pop     r15
0x1800a85f7  pop     r14
0x1800a85f9  pop     rdi
0x1800a85fa  pop     rsi
0x1800a85fb  pop     rbx
0x1800a85fc  pop     rbp
0x1800a85fd  retn
```
