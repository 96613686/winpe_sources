# SetWindowsUEFICA2023CapableRegistry(ulong)

- ea: `0x18003a128`
- end: `0x18003a1bf`
- name: `?SetWindowsUEFICA2023CapableRegistry@@YAXK@Z`
- size: `151`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180057a18`

## callees

- `0x18000e48c`
- `0x180024780`
- `0x18003a128`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a17e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a17e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a1aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a1aa`

## pseudocode

```c
void __fastcall SetWindowsUEFICA2023CapableRegistry(int a1)
{
  HKEY *phkResult; // rax
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  Data = a1;
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing",
          0,
          0,
          0,
          0xF003Fu,
          0,
          phkResult,
          0) )
    RegSetValueExW(hKey, L"WindowsUEFICA2023Capable", 0, 4u, (const BYTE *)&Data, 4u);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18003a128  mov     [rsp+Data], ecx
0x18003a12c  sub     rsp, 58h
0x18003a130  lea     rcx, [rsp+58h+hKey]
0x18003a135  mov     [rsp+58h+hKey], 0
0x18003a13e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18003a143  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18003a14c  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x18003a153  mov     [rsp+58h+phkResult], rax; phkResult
0x18003a158  xor     r9d, r9d; lpClass
0x18003a15b  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003a164  xor     r8d, r8d; Reserved
0x18003a167  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18003a16f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003a176  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18003a17e  call    cs:__imp_RegCreateKeyExW
0x18003a184  test    eax, eax
0x18003a186  jnz     short loc_18003A1B0
0x18003a188  mov     rcx, [rsp+58h+hKey]; hKey
0x18003a18d  lea     r9d, [rax+4]; dwType
0x18003a191  lea     rax, [rsp+58h+Data]
0x18003a196  mov     [rsp+58h+samDesired], r9d; cbData
0x18003a19b  xor     r8d, r8d; Reserved
0x18003a19e  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18003a1a3  lea     rdx, aWindowsuefica2; "WindowsUEFICA2023Capable"
0x18003a1aa  call    cs:__imp_RegSetValueExW
0x18003a1b0  lea     rcx, [rsp+58h+hKey]
0x18003a1b5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003a1ba  add     rsp, 58h
0x18003a1be  retn
```
