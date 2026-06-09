# DmGetTargetAik(ushort const *,targetAik *)

- ea: `0x18008aab0`
- end: `0x18008ac72`
- name: `?DmGetTargetAik@@YAJPEBGPEAW4targetAik@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum targetAik *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180087760`
- `0x18008aed0`

## callees

- `0x180007270`
- `0x180053c78`
- `0x18005427c`
- `0x180062728`
- `0x18008aab0`
- `0x18008b33c`

## import_xrefs

- `ncrypt!NCryptImportKey` at `0x18008ac0b`
- `ncrypt!NCryptImportKey` at `0x18008ac0b`
- `ncrypt!NCryptFreeObject` at `0x18008abbc`
- `ncrypt!NCryptFreeObject` at `0x18008abbc`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008ab97`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008ab97`
- `ncrypt!NCryptGetProperty` at `0x18008ab35`
- `ncrypt!NCryptGetProperty` at `0x18008ab35`

## pseudocode

```c
__int64 __fastcall DmGetTargetAik(wchar_t *a1, enum targetAik *a2)
{
  unsigned int v4; // ebx
  NCRYPT_HANDLE phKey; // [rsp+40h] [rbp+7h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+48h] [rbp+Fh] BYREF
  DWORD pcbResult; // [rsp+50h] [rbp+17h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+58h] [rbp+1Fh] BYREF
  __int64 v9; // [rsp+60h] [rbp+27h] BYREF
  BYTE pbData[4]; // [rsp+70h] [rbp+37h] BYREF
  int v11; // [rsp+74h] [rbp+3Bh]
  int v12; // [rsp+78h] [rbp+3Fh]

  if ( !a2 )
    return 2147942487LL;
  *(_DWORD *)a2 = 0;
  v9 = 0;
  pcbResult = 0;
  hObject = 0;
  if ( (int)DmGetWindowsAIKKeyFromProviderInternal(a1, 0, &hObject) < 0
    || NCryptGetProperty(hObject, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0) < 0 )
  {
    phKey = 0;
    *(_DWORD *)pbData = 1297371211;
    v12 = -2130706429;
    v11 = 12;
    phProvider = 0;
    if ( NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0) < 0
      || (phKey = 0, NCryptImportKey(phProvider, 0, L"PcpTpmPersistentKeyBlob", 0, &phKey, pbData, 0xCu, 0) < 0) )
    {
      v4 = 1;
    }
    else
    {
      *(_DWORD *)a2 = 2;
      v4 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v9);
    return v4;
  }
  else
  {
    *(_DWORD *)a2 = 1;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&v9);
    return 0;
  }
}

```

## disassembly

```asm
0x18008aab0  mov     [rsp-8+arg_10], rbx
0x18008aab5  mov     [rsp-8+arg_18], rdi
0x18008aaba  push    rbp
0x18008aabb  lea     rbp, [rsp-57h]
0x18008aac0  sub     rsp, 90h
0x18008aac7  mov     rax, cs:__security_cookie
0x18008aace  xor     rax, rsp
0x18008aad1  mov     [rbp+57h+var_10], rax
0x18008aad5  mov     rdi, rdx
0x18008aad8  test    rdx, rdx
0x18008aadb  jnz     short loc_18008AAE7
0x18008aadd  mov     eax, 80070057h
0x18008aae2  jmp     loc_18008AC50
0x18008aae7  mov     dword ptr [rdx], 0
0x18008aaed  lea     r8, [rbp+57h+hObject]; unsigned __int64 *
0x18008aaf1  xor     edx, edx; int
0x18008aaf3  mov     [rbp+57h+var_30], 0
0x18008aafb  mov     [rbp+57h+var_40], 0
0x18008ab02  mov     [rbp+57h+hObject], 0
0x18008ab0a  call    ?DmGetWindowsAIKKeyFromProviderInternal@@YAJPEBGHPEA_K@Z; DmGetWindowsAIKKeyFromProviderInternal(ushort const *,int,unsigned __int64 *)
0x18008ab0f  test    eax, eax
0x18008ab11  js      short loc_18008AB64
0x18008ab13  mov     rcx, [rbp+57h+hObject]; hObject
0x18008ab17  lea     rax, [rbp+57h+var_40]
0x18008ab1b  mov     [rsp+90h+dwFlags], 0; dwFlags
0x18008ab23  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x18008ab2a  xor     r9d, r9d; cbOutput
0x18008ab2d  mov     [rsp+90h+pcbResult], rax; pcbResult
0x18008ab32  xor     r8d, r8d; pbOutput
0x18008ab35  call    cs:__imp_NCryptGetProperty
0x18008ab3c  nop     dword ptr [rax+rax+00h]
0x18008ab41  test    eax, eax
0x18008ab43  js      short loc_18008AB64
0x18008ab45  lea     rcx, [rbp+57h+hObject]
0x18008ab49  mov     dword ptr [rdi], 1
0x18008ab4f  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008ab54  lea     rcx, [rbp+57h+var_30]
0x18008ab58  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008ab5d  xor     eax, eax
0x18008ab5f  jmp     loc_18008AC50
0x18008ab64  xor     r8d, r8d; dwFlags
0x18008ab67  mov     [rbp+57h+phKey], 0
0x18008ab6f  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18008ab76  mov     dword ptr [rbp+57h+pbData], 4D54504Bh
0x18008ab7d  lea     rcx, [rbp+57h+phProvider]; phProvider
0x18008ab81  mov     [rbp+57h+var_18], 81000003h
0x18008ab88  mov     [rbp+57h+var_1C], 0Ch
0x18008ab8f  mov     [rbp+57h+phProvider], 0
0x18008ab97  call    cs:__imp_NCryptOpenStorageProvider
0x18008ab9e  nop     dword ptr [rax+rax+00h]
0x18008aba3  test    eax, eax
0x18008aba5  js      short loc_18008AC25
0x18008aba7  mov     rbx, [rbp+57h+phKey]
0x18008abab  test    rbx, rbx
0x18008abae  jz      short loc_18008ABD1
0x18008abb0  lea     rcx, [rbp+57h+var_28]; this
0x18008abb4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18008abb9  mov     rcx, rbx; hObject
0x18008abbc  call    cs:__imp_NCryptFreeObject
0x18008abc3  nop     dword ptr [rax+rax+00h]
0x18008abc8  lea     rcx, [rbp+57h+var_28]; this
0x18008abcc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18008abd1  mov     rcx, [rbp+57h+phProvider]; hProvider
0x18008abd5  lea     rax, [rbp+57h+pbData]
0x18008abd9  mov     [rsp+90h+var_58], 0; dwFlags
0x18008abe1  lea     r8, aPcptpmpersiste; "PcpTpmPersistentKeyBlob"
0x18008abe8  mov     [rsp+90h+cbData], 0Ch; cbData
0x18008abf0  xor     r9d, r9d; pParameterList
0x18008abf3  mov     qword ptr [rsp+90h+dwFlags], rax; pbData
0x18008abf8  xor     edx, edx; hImportKey
0x18008abfa  lea     rax, [rbp+57h+phKey]
0x18008abfe  mov     [rbp+57h+phKey], 0
0x18008ac06  mov     [rsp+90h+pcbResult], rax; phKey
0x18008ac0b  call    cs:__imp_NCryptImportKey
0x18008ac12  nop     dword ptr [rax+rax+00h]
0x18008ac17  test    eax, eax
0x18008ac19  js      short loc_18008AC25
0x18008ac1b  mov     dword ptr [rdi], 2
0x18008ac21  xor     ebx, ebx
0x18008ac23  jmp     short loc_18008AC2A
0x18008ac25  mov     ebx, 1
0x18008ac2a  lea     rcx, [rbp+57h+phKey]
0x18008ac2e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008ac33  lea     rcx, [rbp+57h+phProvider]
0x18008ac37  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008ac3c  lea     rcx, [rbp+57h+hObject]
0x18008ac40  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008ac45  lea     rcx, [rbp+57h+var_30]
0x18008ac49  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008ac4e  mov     eax, ebx
0x18008ac50  mov     rcx, [rbp+57h+var_10]
0x18008ac54  xor     rcx, rsp; StackCookie
0x18008ac57  call    __security_check_cookie
0x18008ac5c  lea     r11, [rsp+90h+var_s0]
0x18008ac64  mov     rbx, [r11+20h]
0x18008ac68  mov     rdi, [r11+28h]
0x18008ac6c  mov     rsp, r11
0x18008ac6f  pop     rbp
0x18008ac70  retn
```
