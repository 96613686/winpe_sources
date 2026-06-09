# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::ClearAutoLoginData(void)

- ea: `0x180029040`
- end: `0x1800291fd`
- name: `?ClearAutoLoginData@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJXZ`
- size: `445`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180016698`
- `0x180017118`
- `0x1800179f8`
- `0x180017a88`
- `0x1800187d4`
- `0x180029040`
- `0x18002ecd8`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180029064`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180029064`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002917a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180029191`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800291a8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800291bf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002917a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180029191`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800291a8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800291bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002915a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002915a`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800290ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800290ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002910e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002910e`

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
0x180029040  mov     [rsp-8+arg_0], rsi
0x180029045  push    rbp
0x180029046  mov     rbp, rsp
0x180029049  sub     rsp, 60h
0x18002904d  xor     edx, edx
0x18002904f  mov     [rbp+var_20], 0
0x180029057  lea     rcx, [rbp+var_20]
0x18002905b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180029060  lea     rcx, [rbp+var_20]
0x180029064  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18002906b  nop     dword ptr [rax+rax+00h]
0x180029070  mov     esi, 80000000h
0x180029075  lea     ecx, [rax+rsi]
0x180029078  test    esi, ecx
0x18002907a  jnz     short loc_180029087
0x18002907c  cmp     eax, 80010117h
0x180029081  jnz     loc_1800291E6
0x180029087  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x18002908b  lea     rcx, [rbp+var_10]; this
0x18002908f  mov     [rbp+var_10], 0
0x180029093  mov     [rbp+var_E], 0
0x180029097  call    ?ImpersonateSID@AutoImpersonate@@QEAAJPEBG@Z; AutoImpersonate::ImpersonateSID(ushort const *)
0x18002909c  lea     ecx, [rax+rsi]
0x18002909f  test    esi, ecx
0x1800290a1  jnz     short loc_1800290AE
0x1800290a3  cmp     eax, 80010117h
0x1800290a8  jnz     loc_1800291DD
0x1800290ae  xor     edx, edx
0x1800290b0  mov     [rbp+phkResult], 0
0x1800290b8  lea     rcx, [rbp+phkResult]
0x1800290bc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800290c1  lea     rdx, [rbp+phkResult]; phkResult
0x1800290c5  mov     ecx, 2001Fh; samDesired
0x1800290ca  call    cs:__imp_RegOpenCurrentUser
0x1800290d1  nop     dword ptr [rax+rax+00h]
0x1800290d6  test    eax, eax
0x1800290d8  jnz     loc_1800291D4
0x1800290de  xor     edx, edx
0x1800290e0  mov     [rbp+hkey], 0
0x1800290e8  lea     rcx, [rbp+hkey]
0x1800290ec  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800290f1  mov     rcx, [rbp+phkResult]; hKey
0x1800290f5  lea     rax, [rbp+hkey]
0x1800290f9  mov     r9d, 2001Fh; samDesired
0x1800290ff  mov     [rsp+60h+var_40], rax; phkResult
0x180029104  xor     r8d, r8d; ulOptions
0x180029107  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002910e  call    cs:__imp_RegOpenKeyExW
0x180029115  nop     dword ptr [rax+rax+00h]
0x18002911a  test    eax, eax
0x18002911c  jnz     loc_1800291CB
0x180029122  mov     rcx, [rbp+hkey]; hkey
0x180029126  lea     r8, aAutologoniscon; "AutologonIsConnected"
0x18002912d  mov     [rbp+arg_8], eax
0x180029130  mov     r9d, 10h; dwFlags
0x180029136  lea     rax, [rbp+arg_10]
0x18002913a  mov     [rbp+arg_10], 4
0x180029141  mov     [rsp+60h+pcbData], rax; pcbData
0x180029146  xor     edx, edx; lpSubKey
0x180029148  lea     rax, [rbp+arg_8]
0x18002914c  mov     [rsp+60h+pvData], rax; pvData
0x180029151  mov     [rsp+60h+var_40], 0; pdwType
0x18002915a  call    cs:__imp_RegGetValueW
0x180029161  nop     dword ptr [rax+rax+00h]
0x180029166  test    eax, eax
0x180029168  jnz     short loc_18002916F
0x18002916a  cmp     [rbp+arg_8], eax
0x18002916d  jz      short loc_1800291CB
0x18002916f  mov     rcx, [rbp+hkey]; hKey
0x180029173  lea     rdx, aAutologonsigni; "AutologonSigninName"
0x18002917a  call    cs:__imp_RegDeleteValueW
0x180029181  nop     dword ptr [rax+rax+00h]
0x180029186  mov     rcx, [rbp+hkey]; hKey
0x18002918a  lea     rdx, aAutologonauthe; "AutologonAuthenticationBuffer"
0x180029191  call    cs:__imp_RegDeleteValueW
0x180029198  nop     dword ptr [rax+rax+00h]
0x18002919d  mov     rcx, [rbp+hkey]; hKey
0x1800291a1  lea     rdx, aAutologoniscon; "AutologonIsConnected"
0x1800291a8  call    cs:__imp_RegDeleteValueW
0x1800291af  nop     dword ptr [rax+rax+00h]
0x1800291b4  mov     rcx, [rbp+hkey]; hKey
0x1800291b8  lea     rdx, aAutologonprese; "AutologonPreserveOobeAutologonCredentia"...
0x1800291bf  call    cs:__imp_RegDeleteValueW
0x1800291c6  nop     dword ptr [rax+rax+00h]
0x1800291cb  lea     rcx, [rbp+hkey]
0x1800291cf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800291d4  lea     rcx, [rbp+phkResult]
0x1800291d8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800291dd  lea     rcx, [rbp+var_10]; this
0x1800291e1  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x1800291e6  lea     rcx, [rbp+var_20]
0x1800291ea  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800291ef  mov     rsi, [rsp+60h+arg_0]
0x1800291f4  xor     eax, eax
0x1800291f6  add     rsp, 60h
0x1800291fa  pop     rbp
0x1800291fb  retn
```
