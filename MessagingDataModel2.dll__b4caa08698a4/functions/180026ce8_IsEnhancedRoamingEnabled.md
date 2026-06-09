# _IsEnhancedRoamingEnabled

- ea: `0x180026ce8`
- end: `0x180026dfa`
- name: `_IsEnhancedRoamingEnabled`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026f90`

## callees

- `0x1800237bc`
- `0x1800267e8`
- `0x180026ce8`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026d87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026dbf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026d87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026dbf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026d46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026d46`

## string_xrefs

- `0x180026d18`: `Software\Qualcomm\RIL\Driver0\ERI`

## pseudocode

```c
__int64 IsEnhancedRoamingEnabled()
{
  unsigned int v0; // edi
  LSTATUS v1; // ebx
  HKEY *p_hKey; // [rsp+30h] [rbp-40h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-38h] BYREF
  char v5; // [rsp+40h] [rbp-30h]
  DWORD cbData; // [rsp+48h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-24h] BYREF
  BYTE v8[8]; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-18h] BYREF

  hKey = 0;
  p_hKey = &hKey;
  v0 = 1;
  phkResult = 0;
  v5 = 1;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Qualcomm\\RIL\\Driver0\\ERI", 0, 1u, &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v1
    || (*(_DWORD *)Data = 0, cbData = 4, RegQueryValueExW(hKey, L"Enabled", 0, 0, Data, &cbData))
    || !*(_DWORD *)Data
    || (*(_DWORD *)v8 = 0, cbData = 4, RegQueryValueExW(hKey, L"Algorithm", 0, 0, v8, &cbData))
    || *(_DWORD *)v8 != 2 )
  {
    v0 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v0;
}

```

## disassembly

```asm
0x180026ce8  mov     [rsp-8+arg_0], rbx
0x180026ced  mov     [rsp-8+arg_8], rdi
0x180026cf2  push    rbp
0x180026cf3  mov     rbp, rsp
0x180026cf6  sub     rsp, 70h
0x180026cfa  mov     rax, cs:__security_cookie
0x180026d01  xor     rax, rsp
0x180026d04  mov     [rbp+var_10], rax
0x180026d08  lea     rax, [rbp+hKey]
0x180026d0c  mov     [rbp+hKey], 0
0x180026d14  mov     [rbp+var_40], rax
0x180026d18  lea     rdx, SubKey; "Software\\Qualcomm\\RIL\\Driver0\\ERI"
0x180026d1f  mov     edi, 1
0x180026d24  mov     [rbp+var_38], 0
0x180026d2c  lea     rax, [rbp+var_38]
0x180026d30  mov     [rbp+var_30], dil
0x180026d34  mov     r9d, edi; samDesired
0x180026d37  mov     [rsp+70h+phkResult], rax; phkResult
0x180026d3c  xor     r8d, r8d; ulOptions
0x180026d3f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026d46  call    cs:__imp_RegOpenKeyExW
0x180026d4c  lea     rcx, [rbp+var_40]
0x180026d50  mov     ebx, eax
0x180026d52  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180026d57  test    ebx, ebx
0x180026d59  jnz     short loc_180026DCF
0x180026d5b  mov     rcx, [rbp+hKey]; hKey
0x180026d5f  lea     rax, [rbp+cbData]
0x180026d63  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180026d68  lea     rdx, ValueName; "Enabled"
0x180026d6f  mov     dword ptr [rbp+Data], ebx
0x180026d72  lea     rax, [rbp+Data]
0x180026d76  lea     ebx, [rdi+3]
0x180026d79  mov     [rsp+70h+phkResult], rax; lpData
0x180026d7e  xor     r9d, r9d; lpType
0x180026d81  mov     [rbp+cbData], ebx
0x180026d84  xor     r8d, r8d; lpReserved
0x180026d87  call    cs:__imp_RegQueryValueExW
0x180026d8d  test    eax, eax
0x180026d8f  jnz     short loc_180026DCF
0x180026d91  cmp     dword ptr [rbp+Data], eax
0x180026d94  jz      short loc_180026DCF
0x180026d96  mov     rcx, [rbp+hKey]; hKey
0x180026d9a  lea     rdx, aAlgorithm; "Algorithm"
0x180026da1  mov     dword ptr [rbp+var_20], eax
0x180026da4  xor     r9d, r9d; lpType
0x180026da7  lea     rax, [rbp+cbData]
0x180026dab  mov     [rbp+cbData], ebx
0x180026dae  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180026db3  xor     r8d, r8d; lpReserved
0x180026db6  lea     rax, [rbp+var_20]
0x180026dba  mov     [rsp+70h+phkResult], rax; lpData
0x180026dbf  call    cs:__imp_RegQueryValueExW
0x180026dc5  test    eax, eax
0x180026dc7  jnz     short loc_180026DCF
0x180026dc9  cmp     dword ptr [rbp+var_20], 2
0x180026dcd  jz      short loc_180026DD1
0x180026dcf  xor     edi, edi
0x180026dd1  lea     rcx, [rbp+hKey]
0x180026dd5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026dda  mov     eax, edi
0x180026ddc  mov     rcx, [rbp+var_10]
0x180026de0  xor     rcx, rsp; StackCookie
0x180026de3  call    __security_check_cookie
0x180026de8  lea     r11, [rsp+70h+var_s0]
0x180026ded  mov     rbx, [r11+10h]
0x180026df1  mov     rdi, [r11+18h]
0x180026df5  mov     rsp, r11
0x180026df8  pop     rbp
0x180026df9  retn
```
