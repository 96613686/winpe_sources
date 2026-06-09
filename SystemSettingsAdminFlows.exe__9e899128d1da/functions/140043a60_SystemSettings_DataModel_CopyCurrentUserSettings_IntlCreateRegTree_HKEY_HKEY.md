# SystemSettings::DataModel::CopyCurrentUserSettings::IntlCreateRegTree(HKEY__ *,HKEY__ *)

- ea: `0x140043a60`
- end: `0x140043c25`
- name: `?IntlCreateRegTree@CopyCurrentUserSettings@DataModel@SystemSettings@@CAKPEAUHKEY__@@0@Z`
- size: `453`
- prototype: `unsigned int __fastcall(HKEY, HKEY)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140043a60`
- `0x1400445f0`
- `0x1400446a4`

## callees

- `0x140005f30`
- `0x14000ed38`
- `0x14002c070`
- `0x1400438c8`
- `0x140043a60`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x140043b68`
- `KERNEL32!RegOpenKeyExW` at `0x140043b68`
- `KERNEL32!RegCreateKeyExW` at `0x140043b3e`
- `KERNEL32!RegCreateKeyExW` at `0x140043b3e`
- `KERNEL32!RegEnumKeyExW` at `0x140043bd2`
- `KERNEL32!RegEnumKeyExW` at `0x140043bd2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::IntlCreateRegTree(HKEY a1, HKEY a2)
{
  unsigned int RegTree; // ebx
  DWORD v5; // esi
  DWORD i; // edx
  HKEY *phkResult; // rax
  HKEY *v8; // rax
  HKEY v10; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchClass; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[256]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Class[264]; // [rsp+270h] [rbp+170h] BYREF

  cchClass = 0;
  cchName = 0;
  dwDisposition = 0;
  hKey = 0;
  v10 = 0;
  RegTree = SystemSettings::DataModel::CopyCurrentUserSettings::IntlCopyRegKeyValues(a1, a2);
  if ( !RegTree )
  {
    v5 = 0;
    for ( i = 0; ; i = v5 )
    {
      cchName = 256;
      cchClass = 256;
      RegTree = RegEnumKeyExW(a1, i, SubKey, &cchName, 0, Class, &cchClass, 0);
      if ( RegTree == 259 )
        break;
      if ( RegTree )
        goto LABEL_10;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
      if ( !RegCreateKeyExW(a2, SubKey, 0, Class, 0, 0xF003Fu, 0, phkResult, &dwDisposition) )
      {
        v8 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v10);
        RegTree = RegOpenKeyExW(a1, SubKey, 0, 0xF003Fu, v8);
        if ( RegTree )
          goto LABEL_10;
        RegTree = SystemSettings::DataModel::CopyCurrentUserSettings::IntlCreateRegTree(v10, hKey);
        if ( RegTree )
          goto LABEL_10;
      }
      ++v5;
    }
    RegTree = 0;
  }
LABEL_10:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v10);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return RegTree;
}

```

## disassembly

```asm
0x140043a60  mov     [rsp-8+arg_10], rbx
0x140043a65  mov     [rsp-8+arg_18], rsi
0x140043a6a  push    rbp
0x140043a6b  push    rdi
0x140043a6c  push    r14
0x140043a6e  lea     rbp, [rsp-390h]
0x140043a76  sub     rsp, 490h
0x140043a7d  mov     rax, cs:__security_cookie
0x140043a84  xor     rax, rsp
0x140043a87  mov     [rbp+3A0h+var_20], rax
0x140043a8e  mov     r14, rdx
0x140043a91  mov     rdi, rcx
0x140043a94  mov     [rsp+4A0h+cchClass], 0
0x140043a9c  mov     [rsp+4A0h+cchName], 0
0x140043aa4  mov     [rsp+4A0h+dwDisposition], 0
0x140043aac  mov     [rsp+4A0h+hKey], 0
0x140043ab5  mov     [rsp+4A0h+var_450], 0
0x140043abe  call    ?IntlCopyRegKeyValues@CopyCurrentUserSettings@DataModel@SystemSettings@@CAKPEAUHKEY__@@0@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlCopyRegKeyValues(HKEY__ *,HKEY__ *)
0x140043ac3  mov     ebx, eax
0x140043ac5  test    eax, eax
0x140043ac7  jnz     loc_140043BE7
0x140043acd  xor     esi, esi
0x140043acf  mov     [rsp+4A0h+phkResult], rsi
0x140043ad4  lea     rax, [rsp+4A0h+cchClass]
0x140043ad9  mov     [rsp+4A0h+lpSecurityAttributes], rax
0x140043ade  lea     rax, [rbp+3A0h+Class]
0x140043ae5  mov     qword ptr [rsp+4A0h+samDesired], rax
0x140043aea  mov     qword ptr [rsp+4A0h+dwOptions], rsi
0x140043aef  xor     edx, edx
0x140043af1  jmp     loc_140043BB5
0x140043af6  test    ebx, ebx
0x140043af8  jnz     loc_140043BE7
0x140043afe  lea     rcx, [rsp+4A0h+hKey]
0x140043b03  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140043b08  lea     rcx, [rsp+4A0h+dwDisposition]
0x140043b0d  mov     [rsp+4A0h+lpdwDisposition], rcx; lpdwDisposition
0x140043b12  mov     [rsp+4A0h+phkResult], rax; phkResult
0x140043b17  mov     [rsp+4A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140043b20  mov     [rsp+4A0h+samDesired], 0F003Fh; samDesired
0x140043b28  mov     [rsp+4A0h+dwOptions], ebx; dwOptions
0x140043b2c  lea     r9, [rbp+3A0h+Class]; lpClass
0x140043b33  xor     r8d, r8d; Reserved
0x140043b36  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x140043b3b  mov     rcx, r14; hKey
0x140043b3e  call    cs:__imp_RegCreateKeyExW
0x140043b44  test    eax, eax
0x140043b46  jnz     short loc_140043B89
0x140043b48  lea     rcx, [rsp+4A0h+var_450]
0x140043b4d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140043b52  mov     qword ptr [rsp+4A0h+dwOptions], rax; phkResult
0x140043b57  mov     r9d, 0F003Fh; samDesired
0x140043b5d  xor     r8d, r8d; ulOptions
0x140043b60  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x140043b65  mov     rcx, rdi; hKey
0x140043b68  call    cs:__imp_RegOpenKeyExW
0x140043b6e  mov     ebx, eax
0x140043b70  test    eax, eax
0x140043b72  jnz     short loc_140043BE7
0x140043b74  mov     rdx, [rsp+4A0h+hKey]; HKEY
0x140043b79  mov     rcx, [rsp+4A0h+var_450]; HKEY
0x140043b7e  call    ?IntlCreateRegTree@CopyCurrentUserSettings@DataModel@SystemSettings@@CAKPEAUHKEY__@@0@Z; SystemSettings::DataModel::CopyCurrentUserSettings::IntlCreateRegTree(HKEY__ *,HKEY__ *)
0x140043b83  mov     ebx, eax
0x140043b85  test    eax, eax
0x140043b87  jnz     short loc_140043BE7
0x140043b89  inc     esi
0x140043b8b  mov     [rsp+4A0h+phkResult], 0; lpftLastWriteTime
0x140043b94  lea     rax, [rsp+4A0h+cchClass]
0x140043b99  mov     [rsp+4A0h+lpSecurityAttributes], rax; lpcchClass
0x140043b9e  lea     rax, [rbp+3A0h+Class]
0x140043ba5  mov     qword ptr [rsp+4A0h+samDesired], rax; lpClass
0x140043baa  mov     qword ptr [rsp+4A0h+dwOptions], 0; lpReserved
0x140043bb3  mov     edx, esi; dwIndex
0x140043bb5  mov     [rsp+4A0h+cchName], 100h
0x140043bbd  mov     [rsp+4A0h+cchClass], 100h
0x140043bc5  lea     r9, [rsp+4A0h+cchName]; lpcchName
0x140043bca  lea     r8, [rsp+4A0h+SubKey]; lpName
0x140043bcf  mov     rcx, rdi; hKey
0x140043bd2  call    cs:__imp_RegEnumKeyExW
0x140043bd8  cmp     eax, 103h
0x140043bdd  mov     ebx, eax
0x140043bdf  jnz     loc_140043AF6
0x140043be5  xor     ebx, ebx
0x140043be7  lea     rcx, [rsp+4A0h+var_450]
0x140043bec  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140043bf1  nop
0x140043bf2  lea     rcx, [rsp+4A0h+hKey]
0x140043bf7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140043bfc  mov     eax, ebx
0x140043bfe  mov     rcx, [rbp+3A0h+var_20]
0x140043c05  xor     rcx, rsp; StackCookie
0x140043c08  call    __security_check_cookie
0x140043c0d  lea     r11, [rsp+4A0h+var_10]
0x140043c15  mov     rbx, [r11+30h]
0x140043c19  mov     rsi, [r11+38h]
0x140043c1d  mov     rsp, r11
0x140043c20  pop     r14
0x140043c22  pop     rdi
0x140043c23  pop     rbp
0x140043c24  retn
```
