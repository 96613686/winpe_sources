# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::ClearAutoLoginData(void)

- ea: `0x18002a730`
- end: `0x18002a8bc`
- name: `?ClearAutoLoginData@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJXZ`
- size: `396`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180015f70`
- `0x1800169b8`
- `0x180017204`
- `0x180017284`
- `0x180019fb8`
- `0x18002a730`
- `0x180030068`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x18002a754`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18002a754`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002a7b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18002a7b4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a852`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a863`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a874`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a885`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a852`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a863`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a874`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a885`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a838`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a838`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a7f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a7f2`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::ClearAutoLoginData(
        EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this)
{
  int ActiveUserSid; // eax
  int v2; // eax
  unsigned __int16 *v4; // [rsp+40h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-18h] BYREF
  _BYTE v6[16]; // [rsp+50h] [rbp-10h] BYREF
  int pvData; // [rsp+78h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+20h] BYREF
  HKEY hkey; // [rsp+88h] [rbp+28h] BYREF

  v4 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v4,
    0);
  ActiveUserSid = DmGetActiveUserSid(&v4);
  if ( (int)(ActiveUserSid + 0x80000000) < 0 || ActiveUserSid == -2147417833 )
  {
    v6[0] = 0;
    v6[2] = 0;
    v2 = AutoImpersonate::ImpersonateSID((AutoImpersonate *)v6, v4);
    if ( ((v2 + 0x80000000) & 0x80000000) != 0 || v2 == -2147417833 )
    {
      phkResult = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      if ( !RegOpenCurrentUser(0x2001Fu, &phkResult) )
      {
        hkey = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hkey,
          0);
        if ( !RegOpenKeyExW(phkResult, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserOOBE", 0, 0x2001Fu, &hkey) )
        {
          pvData = 0;
          pcbData = 4;
          if ( RegGetValueW(hkey, 0, L"AutologonIsConnected", 0x10u, 0, &pvData, &pcbData) || pvData )
          {
            RegDeleteValueW(hkey, L"AutologonSigninName");
            RegDeleteValueW(hkey, L"AutologonAuthenticationBuffer");
            RegDeleteValueW(hkey, L"AutologonIsConnected");
            RegDeleteValueW(hkey, L"AutologonPreserveOobeAutologonCredentials");
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
    AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v6);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v4);
  return 0;
}

```

## disassembly

```asm
0x18002a730  mov     [rsp-8+arg_0], rsi
0x18002a735  push    rbp
0x18002a736  mov     rbp, rsp
0x18002a739  sub     rsp, 60h
0x18002a73d  xor     edx, edx
0x18002a73f  mov     [rbp+var_20], 0
0x18002a747  lea     rcx, [rbp+var_20]
0x18002a74b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002a750  lea     rcx, [rbp+var_20]
0x18002a754  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18002a75a  mov     esi, 80000000h
0x18002a75f  lea     ecx, [rax+rsi]
0x18002a762  test    esi, ecx
0x18002a764  jnz     short loc_18002A771
0x18002a766  cmp     eax, 80010117h
0x18002a76b  jnz     loc_18002A8A6
0x18002a771  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x18002a775  lea     rcx, [rbp+var_10]; this
0x18002a779  mov     [rbp+var_10], 0
0x18002a77d  mov     [rbp+var_E], 0
0x18002a781  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x18002a786  lea     ecx, [rax+rsi]
0x18002a789  test    esi, ecx
0x18002a78b  jnz     short loc_18002A798
0x18002a78d  cmp     eax, 80010117h
0x18002a792  jnz     loc_18002A89D
0x18002a798  xor     edx, edx
0x18002a79a  mov     [rbp+phkResult], 0
0x18002a7a2  lea     rcx, [rbp+phkResult]
0x18002a7a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002a7ab  lea     rdx, [rbp+phkResult]; phkResult
0x18002a7af  mov     ecx, 2001Fh; samDesired
0x18002a7b4  call    cs:__imp_RegOpenCurrentUser
0x18002a7ba  test    eax, eax
0x18002a7bc  jnz     loc_18002A894
0x18002a7c2  xor     edx, edx
0x18002a7c4  mov     [rbp+hkey], 0
0x18002a7cc  lea     rcx, [rbp+hkey]
0x18002a7d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002a7d5  mov     rcx, [rbp+phkResult]; hKey
0x18002a7d9  lea     rax, [rbp+hkey]
0x18002a7dd  mov     r9d, 2001Fh; samDesired
0x18002a7e3  mov     [rsp+60h+var_40], rax; phkResult
0x18002a7e8  xor     r8d, r8d; ulOptions
0x18002a7eb  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002a7f2  call    cs:__imp_RegOpenKeyExW
0x18002a7f8  test    eax, eax
0x18002a7fa  jnz     loc_18002A88B
0x18002a800  mov     rcx, [rbp+hkey]; hkey
0x18002a804  lea     r8, aAutologoniscon; "AutologonIsConnected"
0x18002a80b  mov     [rbp+arg_8], eax
0x18002a80e  mov     r9d, 10h; dwFlags
0x18002a814  lea     rax, [rbp+arg_10]
0x18002a818  mov     [rbp+arg_10], 4
0x18002a81f  mov     [rsp+60h+pcbData], rax; pcbData
0x18002a824  xor     edx, edx; lpSubKey
0x18002a826  lea     rax, [rbp+arg_8]
0x18002a82a  mov     [rsp+60h+pvData], rax; pvData
0x18002a82f  mov     [rsp+60h+var_40], 0; pdwType
0x18002a838  call    cs:__imp_RegGetValueW
0x18002a83e  test    eax, eax
0x18002a840  jnz     short loc_18002A847
0x18002a842  cmp     [rbp+arg_8], eax
0x18002a845  jz      short loc_18002A88B
0x18002a847  mov     rcx, [rbp+hkey]; hKey
0x18002a84b  lea     rdx, aAutologonsigni; "AutologonSigninName"
0x18002a852  call    cs:__imp_RegDeleteValueW
0x18002a858  mov     rcx, [rbp+hkey]; hKey
0x18002a85c  lea     rdx, aAutologonauthe; "AutologonAuthenticationBuffer"
0x18002a863  call    cs:__imp_RegDeleteValueW
0x18002a869  mov     rcx, [rbp+hkey]; hKey
0x18002a86d  lea     rdx, aAutologoniscon; "AutologonIsConnected"
0x18002a874  call    cs:__imp_RegDeleteValueW
0x18002a87a  mov     rcx, [rbp+hkey]; hKey
0x18002a87e  lea     rdx, aAutologonprese; "AutologonPreserveOobeAutologonCredentia"...
0x18002a885  call    cs:__imp_RegDeleteValueW
0x18002a88b  lea     rcx, [rbp+hkey]
0x18002a88f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a894  lea     rcx, [rbp+phkResult]
0x18002a898  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002a89d  lea     rcx, [rbp+var_10]; this
0x18002a8a1  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18002a8a6  lea     rcx, [rbp+var_20]
0x18002a8aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a8af  mov     rsi, [rsp+60h+arg_0]
0x18002a8b4  xor     eax, eax
0x18002a8b6  add     rsp, 60h
0x18002a8ba  pop     rbp
0x18002a8bb  retn
```
