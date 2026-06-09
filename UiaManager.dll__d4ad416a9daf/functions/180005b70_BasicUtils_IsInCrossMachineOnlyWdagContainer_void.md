# BasicUtils::IsInCrossMachineOnlyWdagContainer(void)

- ea: `0x180005b70`
- end: `0x180005c19`
- name: `?IsInCrossMachineOnlyWdagContainer@BasicUtils@@CA_NXZ`
- size: `169`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005b08`

## callees

- `0x180005b70`
- `0x18002cdf4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005bea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005bea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005bb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005bb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005ba0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005ba0`

## pseudocode

```c
bool BasicUtils::IsInCrossMachineOnlyWdagContainer(void)
{
  bool v0; // bl
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\HVSI", 0, 0x20019u, &hKey) )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    Data = 0;
    cbData = 4;
    Type = 0;
    if ( !RegQueryValueExW(hKey, L"UIAutomationIsInRemoteOnlySession", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && cbData == 4 )
    {
      v0 = Data != 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v0;
  }
}

```

## disassembly

```asm
0x180005b70  push    rbp
0x180005b72  push    rbx
0x180005b73  mov     rbp, rsp
0x180005b76  sub     rsp, 38h
0x180005b7a  lea     rax, [rbp+hKey]
0x180005b7e  xor     ebx, ebx
0x180005b80  mov     r9d, 20019h; samDesired
0x180005b86  mov     [rbp+hKey], rbx
0x180005b8a  xor     r8d, r8d; ulOptions
0x180005b8d  mov     [rsp+38h+phkResult], rax; phkResult
0x180005b92  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\HVSI"
0x180005b99  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005ba0  call    cs:__imp_RegOpenKeyExW
0x180005ba6  mov     rcx, [rbp+hKey]; hKey
0x180005baa  test    eax, eax
0x180005bac  jz      short loc_180005BBD
0x180005bae  test    rcx, rcx
0x180005bb1  jz      short loc_180005BB9
0x180005bb3  call    cs:__imp_RegCloseKey
0x180005bb9  xor     al, al
0x180005bbb  jmp     short loc_180005C12
0x180005bbd  lea     rax, [rbp+cbData]
0x180005bc1  mov     [rbp+Data], ebx
0x180005bc4  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180005bc9  lea     r9, [rbp+Type]; lpType
0x180005bcd  lea     rax, [rbp+Data]
0x180005bd1  mov     [rbp+cbData], 4
0x180005bd8  xor     r8d, r8d; lpReserved
0x180005bdb  mov     [rsp+38h+phkResult], rax; lpData
0x180005be0  lea     rdx, ValueName; "UIAutomationIsInRemoteOnlySession"
0x180005be7  mov     [rbp+Type], ebx
0x180005bea  call    cs:__imp_RegQueryValueExW
0x180005bf0  test    eax, eax
0x180005bf2  jnz     short loc_180005C07
0x180005bf4  cmp     [rbp+Type], 4
0x180005bf8  jnz     short loc_180005C07
0x180005bfa  cmp     [rbp+cbData], 4
0x180005bfe  jnz     short loc_180005C07
0x180005c00  cmp     [rbp+Data], ebx
0x180005c03  jz      short loc_180005C07
0x180005c05  mov     bl, 1
0x180005c07  lea     rcx, [rbp+hKey]
0x180005c0b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180005c10  mov     al, bl
0x180005c12  add     rsp, 38h
0x180005c16  pop     rbx
0x180005c17  pop     rbp
0x180005c18  retn
```
