# DmDiagnoseEkAikMissingOld(int *,int *,int *)

- ea: `0x180087a20`
- end: `0x180087b83`
- name: `?DmDiagnoseEkAikMissingOld@@YAJPEAH00@Z`
- size: `355`
- prototype: `__int64 __fastcall(int *, int *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180053c78`
- `0x18005427c`
- `0x180062728`
- `0x180087a20`
- `0x18008b4d0`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x180087ad3`
- `ncrypt!NCryptFreeObject` at `0x180087ad3`
- `ncrypt!NCryptOpenStorageProvider` at `0x180087aa1`
- `ncrypt!NCryptOpenStorageProvider` at `0x180087aa1`
- `ncrypt!NCryptGetProperty` at `0x180087b42`
- `ncrypt!NCryptGetProperty` at `0x180087b42`
- `ncrypt!NCryptOpenKey` at `0x180087b0a`
- `ncrypt!NCryptOpenKey` at `0x180087b0a`
- `TpmCoreProvisioning!TpmGetEndorsementKeyCertificateState` at `0x180087a6a`
- `TpmCoreProvisioning!TpmGetEndorsementKeyCertificateState` at `0x180087a6a`

## pseudocode

```c
__int64 __fastcall DmDiagnoseEkAikMissingOld(int *a1, int *a2, int *a3)
{
  NCRYPT_HANDLE v6; // rcx
  NCRYPT_HANDLE hObject; // [rsp+30h] [rbp-20h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+38h] [rbp-18h] BYREF
  int v10; // [rsp+70h] [rbp+20h] BYREF
  DWORD pcbResult; // [rsp+88h] [rbp+38h] BYREF

  if ( !a1 || !a2 || !a3 )
    return 2147942487LL;
  v10 = 0;
  *a1 = 1;
  *a2 = 1;
  *a3 = 1;
  TpmGetEndorsementKeyCertificateState((enum TpmEKCertState *)&v10);
  *a1 = 0;
  hObject = 0;
  pcbResult = 0;
  phProvider = 0;
  if ( NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0) >= 0
    || (int)DmSetWindowsAIKPlatformStorageLocation(phProvider) >= 0
    || (hObject = 0, NCryptOpenKey(phProvider, &hObject, L"Windows AIK", 0, 0) >= 0) )
  {
    v6 = hObject;
    *a2 = 0;
    if ( NCryptGetProperty(v6, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0) >= 0 )
      *a3 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  return 0;
}

```

## disassembly

```asm
0x180087a20  mov     [rsp-18h+arg_8], rbx
0x180087a25  push    rbp
0x180087a26  push    rsi
0x180087a27  push    rdi
0x180087a28  mov     rbp, rsp
0x180087a2b  sub     rsp, 50h
0x180087a2f  mov     rdi, r8
0x180087a32  mov     rsi, rdx
0x180087a35  mov     rbx, rcx
0x180087a38  test    rcx, rcx
0x180087a3b  jz      loc_180087B70
0x180087a41  test    rdx, rdx
0x180087a44  jz      loc_180087B70
0x180087a4a  test    r8, r8
0x180087a4d  jz      loc_180087B70
0x180087a53  mov     eax, 1
0x180087a58  mov     [rbp+arg_0], 0
0x180087a5f  mov     [rcx], eax
0x180087a61  lea     rcx, [rbp+arg_0]
0x180087a65  mov     [rdx], eax
0x180087a67  mov     [r8], eax
0x180087a6a  call    cs:__imp_?TpmGetEndorsementKeyCertificateState@@YAJPEAW4TpmEKCertState@@@Z; TpmGetEndorsementKeyCertificateState(TpmEKCertState *)
0x180087a71  nop     dword ptr [rax+rax+00h]
0x180087a76  xor     r8d, r8d; dwFlags
0x180087a79  mov     dword ptr [rbx], 0
0x180087a7f  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180087a86  mov     [rbp+hObject], 0
0x180087a8e  lea     rcx, [rbp+phProvider]; phProvider
0x180087a92  mov     [rbp+pcbResult], 0
0x180087a99  mov     [rbp+phProvider], 0
0x180087aa1  call    cs:__imp_NCryptOpenStorageProvider
0x180087aa8  nop     dword ptr [rax+rax+00h]
0x180087aad  test    eax, eax
0x180087aaf  jns     short loc_180087B1A
0x180087ab1  mov     rcx, [rbp+phProvider]; hObject
0x180087ab5  call    ?DmSetWindowsAIKPlatformStorageLocation@@YAJ_K@Z; DmSetWindowsAIKPlatformStorageLocation(unsigned __int64)
0x180087aba  test    eax, eax
0x180087abc  jns     short loc_180087B1A
0x180087abe  mov     rbx, [rbp+hObject]
0x180087ac2  test    rbx, rbx
0x180087ac5  jz      short loc_180087AE8
0x180087ac7  lea     rcx, [rbp+var_10]; this
0x180087acb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180087ad0  mov     rcx, rbx; hObject
0x180087ad3  call    cs:__imp_NCryptFreeObject
0x180087ada  nop     dword ptr [rax+rax+00h]
0x180087adf  lea     rcx, [rbp+var_10]; this
0x180087ae3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180087ae8  mov     rcx, [rbp+phProvider]; hProvider
0x180087aec  lea     r8, pszKeyName; "Windows AIK"
0x180087af3  xor     r9d, r9d; dwLegacyKeySpec
0x180087af6  mov     [rbp+hObject], 0
0x180087afe  lea     rdx, [rbp+hObject]; phKey
0x180087b02  mov     [rsp+50h+dwFlags], 0; dwFlags
0x180087b0a  call    cs:__imp_NCryptOpenKey
0x180087b11  nop     dword ptr [rax+rax+00h]
0x180087b16  test    eax, eax
0x180087b18  js      short loc_180087B52
0x180087b1a  mov     rcx, [rbp+hObject]; hObject
0x180087b1e  lea     rax, [rbp+pcbResult]
0x180087b22  mov     [rsp+50h+var_28], 0; dwFlags
0x180087b2a  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180087b31  xor     r9d, r9d; cbOutput
0x180087b34  mov     qword ptr [rsp+50h+dwFlags], rax; pcbResult
0x180087b39  xor     r8d, r8d; pbOutput
0x180087b3c  mov     dword ptr [rsi], 0
0x180087b42  call    cs:__imp_NCryptGetProperty
0x180087b49  nop     dword ptr [rax+rax+00h]
0x180087b4e  test    eax, eax
0x180087b50  jns     short loc_180087B68
0x180087b52  lea     rcx, [rbp+hObject]
0x180087b56  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180087b5b  lea     rcx, [rbp+phProvider]
0x180087b5f  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180087b64  xor     eax, eax
0x180087b66  jmp     short loc_180087B75
0x180087b68  mov     dword ptr [rdi], 0
0x180087b6e  jmp     short loc_180087B52
0x180087b70  mov     eax, 80070057h
0x180087b75  mov     rbx, [rsp+50h+arg_8]
0x180087b7a  add     rsp, 50h
0x180087b7e  pop     rdi
0x180087b7f  pop     rsi
0x180087b80  pop     rbp
0x180087b81  retn
```
