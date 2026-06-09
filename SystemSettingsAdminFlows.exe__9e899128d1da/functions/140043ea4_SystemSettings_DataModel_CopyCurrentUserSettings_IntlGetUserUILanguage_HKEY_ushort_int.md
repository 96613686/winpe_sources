# SystemSettings::DataModel::CopyCurrentUserSettings::IntlGetUserUILanguage(HKEY__ *,ushort *,int)

- ea: `0x140043ea4`
- end: `0x140043ff9`
- name: `?IntlGetUserUILanguage@CopyCurrentUserSettings@DataModel@SystemSettings@@CAHPEAUHKEY__@@PEAGH@Z`
- size: `341`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned __int16 *, int)`
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
- `0x1400260c0`
- `0x14002c070`
- `0x140043ea4`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x140043f26`
- `KERNEL32!RegOpenKeyExW` at `0x140043f26`
- `KERNEL32!RegQueryValueExW` at `0x140043f64`
- `KERNEL32!RegQueryValueExW` at `0x140043f9e`
- `KERNEL32!RegQueryValueExW` at `0x140043f64`
- `KERNEL32!RegQueryValueExW` at `0x140043f9e`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::IntlGetUserUILanguage(
        HKEY hKey,
        unsigned __int16 *a2)
{
  unsigned int v4; // edi
  HKEY *phkResult; // rax
  HKEY hKeya; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned __int16 Data[352]; // [rsp+40h] [rbp-C0h] BYREF

  hKeya = 0;
  Type = 0;
  cbData = 0;
  memset_0(Data, 0, 0x2BCu);
  *a2 = 0;
  v4 = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKeya);
  if ( !RegOpenKeyExW(hKey, L"Control Panel\\Desktop", 0, 0x20019u, phkResult) )
  {
    cbData = 700;
    if ( !RegQueryValueExW(hKeya, L"Control Panel\\Desktop", 0, &Type, (LPBYTE)Data, &cbData)
      || (cbData = 700, !RegQueryValueExW(hKeya, L"PreferredUILanguages", 0, &Type, (LPBYTE)Data, &cbData)) )
    {
      if ( Type == 7 && StringCchCopyW(a2, 0x15Eu, Data) >= 0 )
        v4 = 1;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
  return v4;
}

```

## disassembly

```asm
0x140043ea4  mov     [rsp-8+arg_10], rbx
0x140043ea9  push    rbp
0x140043eaa  push    rsi
0x140043eab  push    rdi
0x140043eac  lea     rbp, [rsp-210h]
0x140043eb4  sub     rsp, 310h
0x140043ebb  mov     rax, cs:__security_cookie
0x140043ec2  xor     rax, rsp
0x140043ec5  mov     [rbp+220h+var_20], rax
0x140043ecc  mov     rsi, rdx
0x140043ecf  mov     [rsp+320h+hKey], 0
0x140043ed8  mov     rbx, rcx
0x140043edb  mov     [rsp+320h+Type], 0
0x140043ee3  xor     edx, edx; Val
0x140043ee5  mov     [rsp+320h+cbData], 0
0x140043eed  lea     rcx, [rsp+320h+Data]; void *
0x140043ef2  mov     r8d, 2BCh; Size
0x140043ef8  call    memset_0
0x140043efd  xor     eax, eax
0x140043eff  lea     rcx, [rsp+320h+hKey]
0x140043f04  mov     [rsi], ax
0x140043f07  xor     edi, edi
0x140043f09  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140043f0e  mov     r9d, 20019h; samDesired
0x140043f14  mov     [rsp+320h+phkResult], rax; phkResult
0x140043f19  xor     r8d, r8d; ulOptions
0x140043f1c  lea     rdx, aControlPanelDe_1; "Control Panel\\Desktop"
0x140043f23  mov     rcx, rbx; hKey
0x140043f26  call    cs:__imp_RegOpenKeyExW
0x140043f2c  test    eax, eax
0x140043f2e  jnz     loc_140043FCB
0x140043f34  mov     rcx, [rsp+320h+hKey]; hKey
0x140043f39  lea     rax, [rsp+320h+cbData]
0x140043f3e  mov     [rsp+320h+lpcbData], rax; lpcbData
0x140043f43  lea     r9, [rsp+320h+Type]; lpType
0x140043f48  lea     rax, [rsp+320h+Data]
0x140043f4d  mov     [rsp+320h+cbData], 2BCh
0x140043f55  xor     r8d, r8d; lpReserved
0x140043f58  mov     [rsp+320h+phkResult], rax; lpData
0x140043f5d  lea     rdx, aControlPanelDe_1; "Control Panel\\Desktop"
0x140043f64  call    cs:__imp_RegQueryValueExW
0x140043f6a  test    eax, eax
0x140043f6c  jz      short loc_140043FA8
0x140043f6e  mov     rcx, [rsp+320h+hKey]; hKey
0x140043f73  lea     rax, [rsp+320h+cbData]
0x140043f78  mov     [rsp+320h+lpcbData], rax; lpcbData
0x140043f7d  lea     r9, [rsp+320h+Type]; lpType
0x140043f82  lea     rax, [rsp+320h+Data]
0x140043f87  mov     [rsp+320h+cbData], 2BCh
0x140043f8f  xor     r8d, r8d; lpReserved
0x140043f92  mov     [rsp+320h+phkResult], rax; lpData
0x140043f97  lea     rdx, aPreferreduilan; "PreferredUILanguages"
0x140043f9e  call    cs:__imp_RegQueryValueExW
0x140043fa4  test    eax, eax
0x140043fa6  jnz     short loc_140043FCB
0x140043fa8  cmp     [rsp+320h+Type], 7
0x140043fad  jnz     short loc_140043FCB
0x140043faf  lea     r8, [rsp+320h+Data]; unsigned __int16 *
0x140043fb4  mov     edx, 15Eh; unsigned __int64
0x140043fb9  mov     rcx, rsi; unsigned __int16 *
0x140043fbc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140043fc1  test    eax, eax
0x140043fc3  mov     ecx, 1
0x140043fc8  cmovns  edi, ecx
0x140043fcb  lea     rcx, [rsp+320h+hKey]
0x140043fd0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140043fd5  mov     eax, edi
0x140043fd7  mov     rcx, [rbp+220h+var_20]
0x140043fde  xor     rcx, rsp; StackCookie
0x140043fe1  call    __security_check_cookie
0x140043fe6  mov     rbx, [rsp+320h+arg_10]
0x140043fee  add     rsp, 310h
0x140043ff5  pop     rdi
0x140043ff6  pop     rsi
0x140043ff7  pop     rbp
0x140043ff8  retn
```
