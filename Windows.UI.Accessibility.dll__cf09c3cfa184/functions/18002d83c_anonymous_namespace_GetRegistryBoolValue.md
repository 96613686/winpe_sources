# _anonymous_namespace_::GetRegistryBoolValue

- ea: `0x18002d83c`
- end: `0x18002d8f9`
- name: `_anonymous_namespace_::GetRegistryBoolValue`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023638`

## callees

- `0x180028fc0`
- `0x18002c4f4`
- `0x18002d83c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d889`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d889`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d8c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d8c0`

## pseudocode

```c
char __fastcall anonymous_namespace_::GetRegistryBoolValue(__int64 a1, const WCHAR *a2, char a3)
{
  bool v4; // bl
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 Data; // [rsp+50h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  LOBYTE(Type) = a3;
  Data = a1;
  hKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKey,
    0);
  if ( RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
         0,
         0x20019u,
         hKey)
    || (Type = 0, LODWORD(Data) = 0, cbData = 4, RegQueryValueExW(hKey[0], a2, 0, &Type, (LPBYTE)&Data, &cbData))
    || Type != 4 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
    return 1;
  }
  else
  {
    v4 = (_DWORD)Data != 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
    return v4;
  }
}

```

## disassembly

```asm
0x18002d83c  mov     [rsp-8+arg_8], rbx
0x18002d841  mov     byte ptr [rsp-8+Type], r8b
0x18002d846  mov     [rsp-8+Data], rcx
0x18002d84b  push    rbp
0x18002d84c  mov     rbp, rsp
0x18002d84f  sub     rsp, 40h
0x18002d853  mov     rbx, rdx
0x18002d856  mov     [rbp+hKey], 0
0x18002d85e  xor     edx, edx
0x18002d860  lea     rcx, [rbp+hKey]
0x18002d864  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d869  lea     rax, [rbp+hKey]
0x18002d86d  mov     r9d, 20019h; samDesired
0x18002d873  xor     r8d, r8d; ulOptions
0x18002d876  mov     [rsp+40h+phkResult], rax; phkResult
0x18002d87b  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d882  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002d889  call    cs:__imp_RegOpenKeyExW
0x18002d88f  test    eax, eax
0x18002d891  jnz     short loc_18002D8E3
0x18002d893  mov     rcx, [rbp+hKey]; hKey
0x18002d897  lea     r9, [rbp+Type]; lpType
0x18002d89b  mov     [rbp+Type], eax
0x18002d89e  xor     r8d, r8d; lpReserved
0x18002d8a1  mov     dword ptr [rbp+Data], eax
0x18002d8a4  mov     rdx, rbx; lpValueName
0x18002d8a7  lea     rax, [rbp+cbData]
0x18002d8ab  mov     [rbp+cbData], 4
0x18002d8b2  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002d8b7  lea     rax, [rbp+Data]
0x18002d8bb  mov     [rsp+40h+phkResult], rax; lpData
0x18002d8c0  call    cs:__imp_RegQueryValueExW
0x18002d8c6  test    eax, eax
0x18002d8c8  jnz     short loc_18002D8E3
0x18002d8ca  cmp     [rbp+Type], 4
0x18002d8ce  jnz     short loc_18002D8E3
0x18002d8d0  cmp     dword ptr [rbp+Data], eax
0x18002d8d3  lea     rcx, [rbp+hKey]
0x18002d8d7  setnz   bl
0x18002d8da  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002d8df  mov     al, bl
0x18002d8e1  jmp     short loc_18002D8EE
0x18002d8e3  lea     rcx, [rbp+hKey]
0x18002d8e7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002d8ec  mov     al, 1
0x18002d8ee  mov     rbx, [rsp+40h+arg_8]
0x18002d8f3  add     rsp, 40h
0x18002d8f7  pop     rbp
0x18002d8f8  retn
```
