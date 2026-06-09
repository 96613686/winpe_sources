# CreateRandomKey(_LOCK_BOX_FILE_KEY *)

- ea: `0x140058cac`
- end: `0x140058ee1`
- name: `?CreateRandomKey@@YAJPEAT_LOCK_BOX_FILE_KEY@@@Z`
- size: `565`
- prototype: `__int64 __fastcall(PUCHAR pbOutput)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000e9e0`
- `0x140010270`

## callees

- `0x14000a420`
- `0x14002b430`
- `0x1400588f4`
- `0x1400589c4`
- `0x1400589e8`
- `0x140058cac`
- `0x1400594d0`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x140058cde`
- `bcrypt!BCryptGenRandom` at `0x140058cde`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140058d3e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140058d3e`
- `bcrypt!BCryptSetProperty` at `0x140058d8f`
- `bcrypt!BCryptSetProperty` at `0x140058d8f`
- `bcrypt!BCryptGetProperty` at `0x140058dda`
- `bcrypt!BCryptGetProperty` at `0x140058dda`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x140058e2e`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x140058e2e`
- `bcrypt!BCryptExportKey` at `0x140058e94`
- `bcrypt!BCryptExportKey` at `0x140058e94`

## string_xrefs

- `0x140058cea`: `onecore\ds\security\biometrics\service\trustlet\exe\crypto.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CreateRandomKey(PUCHAR pbOutput)
{
  NTSTATUS v2; // eax
  int v3; // eax
  unsigned int v4; // ebx
  NTSTATUS Property; // eax
  __int64 v6; // rdx
  NTSTATUS v7; // eax
  __int64 v8; // rdx
  int dwFlags; // [rsp+20h] [rbp-40h]
  int dwFlagsa; // [rsp+20h] [rbp-40h]
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-20h] BYREF
  PUCHAR pbKeyObject; // [rsp+48h] [rbp-18h] BYREF
  PUCHAR pbBuffer[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  ULONG pbOutputa; // [rsp+98h] [rbp+38h] BYREF
  ULONG pcbResult; // [rsp+A0h] [rbp+40h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+A8h] [rbp+48h] BYREF

  wil::make_unique_hlocal_secure<unsigned char [0]>(pbBuffer, 0x20u);
  v2 = BCryptGenRandom(0, pbBuffer[0], 0x20u, 2u);
  if ( v2 >= 0
    || (v3 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x12,
               (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
               (const char *)(unsigned int)v2,
               dwFlags),
        v4 = v3,
        v3 >= 0) )
  {
    phAlgorithm = 0;
    Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", 0, 0);
    if ( Property >= 0 )
    {
      Property = BCryptSetProperty(phAlgorithm, L"ChainingMode", (PUCHAR)L"ChainingModeCBC", 0x20u, 0);
      if ( Property >= 0 )
      {
        pbOutputa = 0;
        pcbResult = 0;
        Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutputa, 4u, &pcbResult, 0);
        if ( Property >= 0 )
        {
          wil::make_unique_hlocal_secure<unsigned char [0]>(&pbKeyObject, pbOutputa);
          phKey = 0;
          v7 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, pbKeyObject, pbOutputa, pbBuffer[0], 0x20u, 0);
          if ( v7 >= 0 )
          {
            v7 = BCryptExportKey(phKey, 0, L"KeyDataBlob", pbOutput, 0x40u, &pcbResult, 0);
            if ( v7 >= 0 )
            {
              wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
              wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbKeyObject);
              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
              v4 = 0;
              goto LABEL_18;
            }
            v8 = 81;
          }
          else
          {
            v8 = 71;
          }
          v4 = wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)v8,
                 (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
                 (const char *)(unsigned int)v7,
                 dwFlagsa);
          wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phKey);
          wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbKeyObject);
          goto LABEL_7;
        }
        v6 = 59;
      }
      else
      {
        v6 = 48;
      }
    }
    else
    {
      v6 = 40;
    }
    v4 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v6,
           (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
           (const char *)(unsigned int)Property,
           dwFlags);
LABEL_7:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    goto LABEL_18;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x20,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\crypto.cpp",
    (const char *)(unsigned int)v3,
    dwFlags);
LABEL_18:
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(pbBuffer);
  return v4;
}

```

## disassembly

```asm
0x140058cac  push    rbp
0x140058cae  push    rbx
0x140058caf  push    rdi
0x140058cb0  push    r14
0x140058cb2  push    r15
0x140058cb4  mov     rbp, rsp
0x140058cb7  sub     rsp, 60h
0x140058cbb  mov     rdi, rcx
0x140058cbe  mov     r15d, 20h ; ' '
0x140058cc4  mov     edx, r15d
0x140058cc7  lea     rcx, [rbp+pbBuffer]
0x140058ccb  call    ??$make_unique_hlocal_secure@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure<uchar [0]>(unsigned __int64)
0x140058cd0  nop
0x140058cd1  lea     r9d, [r15-1Eh]; dwFlags
0x140058cd5  mov     r8d, r15d; cbBuffer
0x140058cd8  mov     rdx, [rbp+pbBuffer]; pbBuffer
0x140058cdc  xor     ecx, ecx; hAlgorithm
0x140058cde  call    cs:__imp_BCryptGenRandom
0x140058ce5  nop     dword ptr [rax+rax+00h]
0x140058cea  lea     r14, aOnecoreDsSecur_14; "onecore\\ds\\security\\biometrics\\serv"...
0x140058cf1  test    eax, eax
0x140058cf3  jns     short loc_140058D25
0x140058cf5  mov     rcx, [rbp+28h]; this
0x140058cf9  mov     r9d, eax; char *
0x140058cfc  mov     r8, r14; unsigned int
0x140058cff  lea     edx, [r15-0Eh]; void *
0x140058d03  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140058d08  mov     ebx, eax
0x140058d0a  test    eax, eax
0x140058d0c  jns     short loc_140058D25
0x140058d0e  mov     rcx, [rbp+28h]; this
0x140058d12  mov     r9d, eax; char *
0x140058d15  mov     r8, r14; unsigned int
0x140058d18  mov     edx, r15d; void *
0x140058d1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058d20  jmp     loc_140058EC9
0x140058d25  mov     [rbp+phAlgorithm], 0
0x140058d2d  xor     r9d, r9d; dwFlags
0x140058d30  xor     r8d, r8d; pszImplementation
0x140058d33  lea     rdx, aAes; "AES"
0x140058d3a  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140058d3e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140058d45  nop     dword ptr [rax+rax+00h]
0x140058d4a  test    eax, eax
0x140058d4c  jns     short loc_140058D72
0x140058d4e  mov     edx, 28h ; '('; void *
0x140058d53  mov     rcx, [rbp+28h]; this
0x140058d57  mov     r9d, eax; char *
0x140058d5a  mov     r8, r14; unsigned int
0x140058d5d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140058d62  mov     ebx, eax
0x140058d64  lea     rcx, [rbp+phAlgorithm]
0x140058d68  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140058d6d  jmp     loc_140058EC9
0x140058d72  mov     [rsp+60h+dwFlags], 0; dwFlags
0x140058d7a  mov     r9d, r15d; cbInput
0x140058d7d  lea     r8, pbInput; "ChainingModeCBC"
0x140058d84  lea     rdx, aChainingmode; "ChainingMode"
0x140058d8b  mov     rcx, [rbp+phAlgorithm]; hObject
0x140058d8f  call    cs:__imp_BCryptSetProperty
0x140058d96  nop     dword ptr [rax+rax+00h]
0x140058d9b  test    eax, eax
0x140058d9d  jns     short loc_140058DA6
0x140058d9f  mov     edx, 30h ; '0'
0x140058da4  jmp     short loc_140058D53
0x140058da6  mov     [rbp+pbOutput], 0
0x140058dad  mov     [rbp+pcbResult], 0
0x140058db4  mov     [rsp+60h+cbSecret], 0; dwFlags
0x140058dbc  lea     rax, [rbp+pcbResult]
0x140058dc0  mov     qword ptr [rsp+60h+dwFlags], rax; pcbResult
0x140058dc5  mov     r9d, 4; cbOutput
0x140058dcb  lea     r8, [rbp+pbOutput]; pbOutput
0x140058dcf  lea     rdx, aObjectlength; "ObjectLength"
0x140058dd6  mov     rcx, [rbp+phAlgorithm]; hObject
0x140058dda  call    cs:__imp_BCryptGetProperty
0x140058de1  nop     dword ptr [rax+rax+00h]
0x140058de6  test    eax, eax
0x140058de8  jns     short loc_140058DF4
0x140058dea  mov     edx, 3Bh ; ';'
0x140058def  jmp     loc_140058D53
0x140058df4  mov     edx, [rbp+pbOutput]
0x140058df7  lea     rcx, [rbp+pbKeyObject]
0x140058dfb  call    ??$make_unique_hlocal_secure@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure<uchar [0]>(unsigned __int64)
0x140058e00  mov     rax, [rbp+pbBuffer]
0x140058e04  mov     [rbp+phKey], 0
0x140058e0c  mov     [rsp+60h+var_30], 0; dwFlags
0x140058e14  mov     [rsp+60h+cbSecret], r15d; cbSecret
0x140058e19  mov     qword ptr [rsp+60h+dwFlags], rax; int
0x140058e1e  mov     r9d, [rbp+pbOutput]; cbKeyObject
0x140058e22  mov     r8, [rbp+pbKeyObject]; pbKeyObject
0x140058e26  lea     rdx, [rbp+phKey]; phKey
0x140058e2a  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140058e2e  call    cs:__imp_BCryptGenerateSymmetricKey
0x140058e35  nop     dword ptr [rax+rax+00h]
0x140058e3a  test    eax, eax
0x140058e3c  jns     short loc_140058E6B
0x140058e3e  mov     edx, 47h ; 'G'; void *
0x140058e43  mov     r8, r14; unsigned int
0x140058e46  mov     r9d, eax; char *
0x140058e49  mov     rcx, [rbp+28h]; this
0x140058e4d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140058e52  mov     ebx, eax
0x140058e54  lea     rcx, [rbp+phKey]
0x140058e58  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140058e5d  lea     rcx, [rbp+pbKeyObject]
0x140058e61  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x140058e66  jmp     loc_140058D64
0x140058e6b  mov     [rsp+60h+var_30], 0; dwFlags
0x140058e73  lea     rax, [rbp+pcbResult]
0x140058e77  mov     qword ptr [rsp+60h+cbSecret], rax; pcbResult
0x140058e7c  mov     [rsp+60h+dwFlags], 40h ; '@'; cbOutput
0x140058e84  mov     r9, rdi; pbOutput
0x140058e87  lea     r8, pszBlobType; "KeyDataBlob"
0x140058e8e  xor     edx, edx; hExportKey
0x140058e90  mov     rcx, [rbp+phKey]; hKey
0x140058e94  call    cs:__imp_BCryptExportKey
0x140058e9b  nop     dword ptr [rax+rax+00h]
0x140058ea0  test    eax, eax
0x140058ea2  jns     short loc_140058EAB
0x140058ea4  mov     edx, 51h ; 'Q'
0x140058ea9  jmp     short loc_140058E43
0x140058eab  lea     rcx, [rbp+phKey]
0x140058eaf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140058eb4  lea     rcx, [rbp+pbKeyObject]
0x140058eb8  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x140058ebd  nop
0x140058ebe  lea     rcx, [rbp+phAlgorithm]
0x140058ec2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140058ec7  xor     ebx, ebx
0x140058ec9  lea     rcx, [rbp+pbBuffer]
0x140058ecd  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x140058ed2  mov     eax, ebx
0x140058ed4  add     rsp, 60h
0x140058ed8  pop     r15
0x140058eda  pop     r14
0x140058edc  pop     rdi
0x140058edd  pop     rbx
0x140058ede  pop     rbp
0x140058edf  retn
```
