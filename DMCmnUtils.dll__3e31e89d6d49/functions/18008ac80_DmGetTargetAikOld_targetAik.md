# DmGetTargetAikOld(targetAik *)

- ea: `0x18008ac80`
- end: `0x18008aec2`
- name: `?DmGetTargetAikOld@@YAJPEAW4targetAik@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(enum targetAik *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180087840`
- `0x18008b100`

## callees

- `0x180007270`
- `0x180053c78`
- `0x18005427c`
- `0x180062728`
- `0x18008ac80`
- `0x18008b4d0`

## import_xrefs

- `ncrypt!NCryptImportKey` at `0x18008ae5b`
- `ncrypt!NCryptImportKey` at `0x18008ae5b`
- `ncrypt!NCryptFreeObject` at `0x18008ad1c`
- `ncrypt!NCryptFreeObject` at `0x18008ae0c`
- `ncrypt!NCryptFreeObject` at `0x18008ad1c`
- `ncrypt!NCryptFreeObject` at `0x18008ae0c`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008ace2`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008ade7`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008ace2`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008ade7`
- `ncrypt!NCryptGetProperty` at `0x18008ad85`
- `ncrypt!NCryptGetProperty` at `0x18008ad85`
- `ncrypt!NCryptOpenKey` at `0x18008ad53`
- `ncrypt!NCryptOpenKey` at `0x18008ad53`

## pseudocode

```c
__int64 __fastcall DmGetTargetAikOld(enum targetAik *a1)
{
  NCRYPT_HANDLE v3; // rbx
  unsigned int v4; // ebx
  NCRYPT_HANDLE hObject; // [rsp+40h] [rbp+7h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp+Fh] BYREF
  NCRYPT_HANDLE phKey; // [rsp+50h] [rbp+17h] BYREF
  DWORD pcbResult; // [rsp+58h] [rbp+1Fh] BYREF
  NCRYPT_PROV_HANDLE hProvider; // [rsp+60h] [rbp+27h] BYREF
  _BYTE v10[8]; // [rsp+68h] [rbp+2Fh] BYREF
  BYTE pbData[4]; // [rsp+70h] [rbp+37h] BYREF
  int v12; // [rsp+74h] [rbp+3Bh]
  int v13; // [rsp+78h] [rbp+3Fh]

  if ( !a1 )
    return 2147942487LL;
  *(_DWORD *)a1 = 0;
  hObject = 0;
  pcbResult = 0;
  phProvider = 0;
  if ( NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0) < 0
    || (int)DmSetWindowsAIKPlatformStorageLocation(phProvider) < 0
    || (hObject = 0, NCryptOpenKey(phProvider, &hObject, L"Windows AIK", 0, 0) < 0)
    || NCryptGetProperty(hObject, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0) < 0 )
  {
    phKey = 0;
    *(_DWORD *)pbData = 1297371211;
    v13 = -2130706429;
    v12 = 12;
    hProvider = 0;
    if ( NCryptOpenStorageProvider(&hProvider, L"Microsoft Platform Crypto Provider", 0) < 0 )
      goto LABEL_13;
    v3 = phKey;
    if ( phKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v10);
      NCryptFreeObject(v3);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v10);
    }
    phKey = 0;
    if ( NCryptImportKey(hProvider, 0, L"PcpTpmPersistentKeyBlob", 0, &phKey, pbData, 0xCu, 0) < 0 )
    {
LABEL_13:
      v4 = 1;
    }
    else
    {
      *(_DWORD *)a1 = 2;
      v4 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hProvider);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    return v4;
  }
  else
  {
    *(_DWORD *)a1 = 1;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hObject);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    return 0;
  }
}

```

## disassembly

```asm
0x18008ac80  mov     [rsp-8+arg_8], rbx
0x18008ac85  mov     [rsp-8+arg_10], rdi
0x18008ac8a  push    rbp
0x18008ac8b  lea     rbp, [rsp-57h]
0x18008ac90  sub     rsp, 90h
0x18008ac97  mov     rax, cs:__security_cookie
0x18008ac9e  xor     rax, rsp
0x18008aca1  mov     [rbp+57h+var_10], rax
0x18008aca5  mov     rdi, rcx
0x18008aca8  test    rcx, rcx
0x18008acab  jnz     short loc_18008ACB7
0x18008acad  mov     eax, 80070057h
0x18008acb2  jmp     loc_18008AEA0
0x18008acb7  mov     dword ptr [rcx], 0
0x18008acbd  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18008acc4  lea     rcx, [rbp+57h+phProvider]; phProvider
0x18008acc8  mov     [rbp+57h+hObject], 0
0x18008acd0  xor     r8d, r8d; dwFlags
0x18008acd3  mov     [rbp+57h+pcbResult], 0
0x18008acda  mov     [rbp+57h+phProvider], 0
0x18008ace2  call    cs:__imp_NCryptOpenStorageProvider
0x18008ace9  nop     dword ptr [rax+rax+00h]
0x18008acee  test    eax, eax
0x18008acf0  js      loc_18008ADB4
0x18008acf6  mov     rcx, [rbp+57h+phProvider]; hObject
0x18008acfa  call    ?DmSetWindowsAIKPlatformStorageLocation@@YAJ_K@Z; DmSetWindowsAIKPlatformStorageLocation(unsigned __int64)
0x18008acff  test    eax, eax
0x18008ad01  js      loc_18008ADB4
0x18008ad07  mov     rbx, [rbp+57h+hObject]
0x18008ad0b  test    rbx, rbx
0x18008ad0e  jz      short loc_18008AD31
0x18008ad10  lea     rcx, [rbp+57h+var_28]; this
0x18008ad14  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18008ad19  mov     rcx, rbx; hObject
0x18008ad1c  call    cs:__imp_NCryptFreeObject
0x18008ad23  nop     dword ptr [rax+rax+00h]
0x18008ad28  lea     rcx, [rbp+57h+var_28]; this
0x18008ad2c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18008ad31  mov     rcx, [rbp+57h+phProvider]; hProvider
0x18008ad35  lea     r8, pszKeyName; "Windows AIK"
0x18008ad3c  xor     r9d, r9d; dwLegacyKeySpec
0x18008ad3f  mov     [rbp+57h+hObject], 0
0x18008ad47  lea     rdx, [rbp+57h+hObject]; phKey
0x18008ad4b  mov     [rsp+90h+dwFlags], 0; dwFlags
0x18008ad53  call    cs:__imp_NCryptOpenKey
0x18008ad5a  nop     dword ptr [rax+rax+00h]
0x18008ad5f  test    eax, eax
0x18008ad61  js      short loc_18008ADB4
0x18008ad63  mov     rcx, [rbp+57h+hObject]; hObject
0x18008ad67  lea     rax, [rbp+57h+pcbResult]
0x18008ad6b  mov     [rsp+90h+var_68], 0; dwFlags
0x18008ad73  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x18008ad7a  xor     r9d, r9d; cbOutput
0x18008ad7d  mov     qword ptr [rsp+90h+dwFlags], rax; pcbResult
0x18008ad82  xor     r8d, r8d; pbOutput
0x18008ad85  call    cs:__imp_NCryptGetProperty
0x18008ad8c  nop     dword ptr [rax+rax+00h]
0x18008ad91  test    eax, eax
0x18008ad93  js      short loc_18008ADB4
0x18008ad95  lea     rcx, [rbp+57h+hObject]
0x18008ad99  mov     dword ptr [rdi], 1
0x18008ad9f  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008ada4  lea     rcx, [rbp+57h+phProvider]
0x18008ada8  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008adad  xor     eax, eax
0x18008adaf  jmp     loc_18008AEA0
0x18008adb4  xor     r8d, r8d; dwFlags
0x18008adb7  mov     [rbp+57h+phKey], 0
0x18008adbf  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18008adc6  mov     dword ptr [rbp+57h+pbData], 4D54504Bh
0x18008adcd  lea     rcx, [rbp+57h+hProvider]; phProvider
0x18008add1  mov     [rbp+57h+var_18], 81000003h
0x18008add8  mov     [rbp+57h+var_1C], 0Ch
0x18008addf  mov     [rbp+57h+hProvider], 0
0x18008ade7  call    cs:__imp_NCryptOpenStorageProvider
0x18008adee  nop     dword ptr [rax+rax+00h]
0x18008adf3  test    eax, eax
0x18008adf5  js      short loc_18008AE75
0x18008adf7  mov     rbx, [rbp+57h+phKey]
0x18008adfb  test    rbx, rbx
0x18008adfe  jz      short loc_18008AE21
0x18008ae00  lea     rcx, [rbp+57h+var_28]; this
0x18008ae04  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18008ae09  mov     rcx, rbx; hObject
0x18008ae0c  call    cs:__imp_NCryptFreeObject
0x18008ae13  nop     dword ptr [rax+rax+00h]
0x18008ae18  lea     rcx, [rbp+57h+var_28]; this
0x18008ae1c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18008ae21  mov     rcx, [rbp+57h+hProvider]; hProvider
0x18008ae25  lea     rax, [rbp+57h+pbData]
0x18008ae29  mov     [rsp+90h+var_58], 0; dwFlags
0x18008ae31  lea     r8, aPcptpmpersiste; "PcpTpmPersistentKeyBlob"
0x18008ae38  mov     [rsp+90h+cbData], 0Ch; cbData
0x18008ae40  xor     r9d, r9d; pParameterList
0x18008ae43  mov     qword ptr [rsp+90h+var_68], rax; pbData
0x18008ae48  xor     edx, edx; hImportKey
0x18008ae4a  lea     rax, [rbp+57h+phKey]
0x18008ae4e  mov     [rbp+57h+phKey], 0
0x18008ae56  mov     qword ptr [rsp+90h+dwFlags], rax; phKey
0x18008ae5b  call    cs:__imp_NCryptImportKey
0x18008ae62  nop     dword ptr [rax+rax+00h]
0x18008ae67  test    eax, eax
0x18008ae69  js      short loc_18008AE75
0x18008ae6b  mov     dword ptr [rdi], 2
0x18008ae71  xor     ebx, ebx
0x18008ae73  jmp     short loc_18008AE7A
0x18008ae75  mov     ebx, 1
0x18008ae7a  lea     rcx, [rbp+57h+phKey]
0x18008ae7e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008ae83  lea     rcx, [rbp+57h+hProvider]
0x18008ae87  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008ae8c  lea     rcx, [rbp+57h+hObject]
0x18008ae90  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008ae95  lea     rcx, [rbp+57h+phProvider]
0x18008ae99  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008ae9e  mov     eax, ebx
0x18008aea0  mov     rcx, [rbp+57h+var_10]
0x18008aea4  xor     rcx, rsp; StackCookie
0x18008aea7  call    __security_check_cookie
0x18008aeac  lea     r11, [rsp+90h+var_s0]
0x18008aeb4  mov     rbx, [r11+18h]
0x18008aeb8  mov     rdi, [r11+20h]
0x18008aebc  mov     rsp, r11
0x18008aebf  pop     rbp
0x18008aec0  retn
```
