# SystemSettings::DataModel::CopyCurrentUserSettings::IntlGetUserUILangConfig(HKEY__ *,ushort *,ushort *,int)

- ea: `0x140043d64`
- end: `0x140043e9d`
- name: `?IntlGetUserUILangConfig@CopyCurrentUserSettings@DataModel@SystemSettings@@CAKPEAUHKEY__@@PEAG1H@Z`
- size: `313`
- prototype: `unsigned int __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int16 *Destination, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14004435c`
- `0x1400448c4`

## callees

- `0x140004e68`
- `0x140005f30`
- `0x14000ed38`
- `0x14002c070`
- `0x140043d64`
- `0x140044b60`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x140043de8`
- `KERNEL32!RegOpenKeyExW` at `0x140043e14`
- `KERNEL32!RegOpenKeyExW` at `0x140043de8`
- `KERNEL32!RegOpenKeyExW` at `0x140043e14`
- `KERNEL32!RegQueryValueExW` at `0x140043e4a`
- `KERNEL32!RegQueryValueExW` at `0x140043e4a`

## string_xrefs

- `0x140043dde`: `Control Panel\Desktop\LanguageConfigurationPending`
- `0x140043e0a`: `Control Panel\Desktop\LanguageConfiguration`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::IntlGetUserUILangConfig(
        HKEY hKey,
        LPCWSTR lpValueName,
        unsigned __int16 *Destination)
{
  DWORD v6; // ebx
  HKEY *phkResult; // rax
  HKEY *v8; // rax
  rsize_t v9; // rdx
  HKEY hKeya; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE Data[704]; // [rsp+40h] [rbp-C0h] BYREF

  hKeya = 0;
  Type = 0;
  cbData = 0;
  v6 = 0;
  memset_0(Data, 0, 0x2BCu);
  *Destination = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKeya);
  if ( !RegOpenKeyExW(hKey, L"Control Panel\\Desktop\\LanguageConfigurationPending", 0, 0x20019u, phkResult)
    || (v8 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKeya),
        !RegOpenKeyExW(hKey, L"Control Panel\\Desktop\\LanguageConfiguration", 0, 0x20019u, v8)) )
  {
    cbData = 700;
    if ( !RegQueryValueExW(hKeya, lpValueName, 0, &Type, Data, &cbData)
      && Type == 7
      && !memcpy_s_1(Destination, v9, Data, cbData) )
    {
      v6 = cbData;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
  return v6;
}

```

## disassembly

```asm
0x140043d64  push    rbp
0x140043d66  push    rbx
0x140043d67  push    rsi
0x140043d68  push    rdi
0x140043d69  push    r14
0x140043d6b  lea     rbp, [rsp-210h]
0x140043d73  sub     rsp, 310h
0x140043d7a  mov     rax, cs:__security_cookie
0x140043d81  xor     rax, rsp
0x140043d84  mov     [rbp+230h+var_30], rax
0x140043d8b  mov     rdi, r8
0x140043d8e  mov     [rsp+330h+hKey], 0
0x140043d97  mov     r14, rdx
0x140043d9a  mov     [rsp+330h+Type], 0
0x140043da2  mov     rsi, rcx
0x140043da5  mov     [rsp+330h+cbData], 0
0x140043dad  xor     edx, edx; Val
0x140043daf  lea     rcx, [rsp+330h+Data]; void *
0x140043db4  mov     r8d, 2BCh; Size
0x140043dba  xor     ebx, ebx
0x140043dbc  call    memset_0
0x140043dc1  xor     eax, eax
0x140043dc3  lea     rcx, [rsp+330h+hKey]
0x140043dc8  mov     [rdi], ax
0x140043dcb  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140043dd0  mov     r9d, 20019h; samDesired
0x140043dd6  mov     [rsp+330h+phkResult], rax; phkResult
0x140043ddb  xor     r8d, r8d; ulOptions
0x140043dde  lea     rdx, aControlPanelDe; "Control Panel\\Desktop\\LanguageConfigu"...
0x140043de5  mov     rcx, rsi; hKey
0x140043de8  call    cs:__imp_RegOpenKeyExW
0x140043dee  test    eax, eax
0x140043df0  jz      short loc_140043E1E
0x140043df2  lea     rcx, [rsp+330h+hKey]
0x140043df7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140043dfc  mov     r9d, 20019h; samDesired
0x140043e02  mov     [rsp+330h+phkResult], rax; phkResult
0x140043e07  xor     r8d, r8d; ulOptions
0x140043e0a  lea     rdx, aControlPanelDe_0; "Control Panel\\Desktop\\LanguageConfigu"...
0x140043e11  mov     rcx, rsi; hKey
0x140043e14  call    cs:__imp_RegOpenKeyExW
0x140043e1a  test    eax, eax
0x140043e1c  jnz     short loc_140043E74
0x140043e1e  mov     rcx, [rsp+330h+hKey]; hKey
0x140043e23  lea     rax, [rsp+330h+cbData]
0x140043e28  mov     [rsp+330h+lpcbData], rax; lpcbData
0x140043e2d  lea     r9, [rsp+330h+Type]; lpType
0x140043e32  lea     rax, [rsp+330h+Data]
0x140043e37  mov     [rsp+330h+cbData], 2BCh
0x140043e3f  xor     r8d, r8d; lpReserved
0x140043e42  mov     [rsp+330h+phkResult], rax; lpData
0x140043e47  mov     rdx, r14; lpValueName
0x140043e4a  call    cs:__imp_RegQueryValueExW
0x140043e50  test    eax, eax
0x140043e52  jnz     short loc_140043E74
0x140043e54  cmp     [rsp+330h+Type], 7
0x140043e59  jnz     short loc_140043E74
0x140043e5b  mov     r9d, [rsp+330h+cbData]; SourceSize
0x140043e60  lea     r8, [rsp+330h+Data]; Source
0x140043e65  mov     rcx, rdi; Destination
0x140043e68  call    memcpy_s_1
0x140043e6d  test    eax, eax
0x140043e6f  cmovz   ebx, [rsp+330h+cbData]
0x140043e74  lea     rcx, [rsp+330h+hKey]
0x140043e79  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140043e7e  mov     eax, ebx
0x140043e80  mov     rcx, [rbp+230h+var_30]
0x140043e87  xor     rcx, rsp; StackCookie
0x140043e8a  call    __security_check_cookie
0x140043e8f  add     rsp, 310h
0x140043e96  pop     r14
0x140043e98  pop     rdi
0x140043e99  pop     rsi
0x140043e9a  pop     rbx
0x140043e9b  pop     rbp
0x140043e9c  retn
```
