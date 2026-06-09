# SetSBUpdateAttemptedInCurrentBootCycleRegistry(ulong)

- ea: `0x180039ec0`
- end: `0x180039f9e`
- name: `?SetSBUpdateAttemptedInCurrentBootCycleRegistry@@YAXK@Z`
- size: `222`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1800341b0`

## callees

- `0x18000e48c`
- `0x180024780`
- `0x180039ec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039f56`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180039f56`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180039f29`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180039f29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180039f84`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180039f84`

## string_xrefs

- `0x180039ef7`: `SYSTEM\CurrentControlSet\Control\SecureBoot\SBInstalledInCurrentBootCycle`
- `0x180039f40`: `SBUpdateType`
- `0x180039f67`: `SBUpdateType`

## pseudocode

```c
void __fastcall SetSBUpdateAttemptedInCurrentBootCycleRegistry(int a1)
{
  HKEY *phkResult; // rax
  int Data; // [rsp+68h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+28h] BYREF

  Data = 0;
  cbData = 4;
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  if ( !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\SBInstalledInCurrentBootCycle",
          0,
          0,
          1u,
          0xF003Fu,
          0,
          phkResult,
          0) )
  {
    RegQueryValueExW(hKey, L"SBUpdateType", 0, 0, (LPBYTE)&Data, &cbData);
    Data |= a1;
    RegSetValueExW(hKey, L"SBUpdateType", 0, 4u, (const BYTE *)&Data, 4u);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180039ec0  mov     [rsp-8+arg_0], rbx
0x180039ec5  push    rbp
0x180039ec6  mov     rbp, rsp
0x180039ec9  sub     rsp, 50h
0x180039ecd  mov     ebx, ecx
0x180039ecf  mov     [rbp+Data], 0
0x180039ed6  lea     rcx, [rbp+hKey]
0x180039eda  mov     [rbp+cbData], 4
0x180039ee1  mov     [rbp+hKey], 0
0x180039ee9  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180039eee  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180039ef7  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x180039efe  mov     [rsp+50h+phkResult], rax; phkResult
0x180039f03  xor     r9d, r9d; lpClass
0x180039f06  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180039f0f  xor     r8d, r8d; Reserved
0x180039f12  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x180039f1a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039f21  mov     [rsp+50h+dwOptions], 1; dwOptions
0x180039f29  call    cs:__imp_RegCreateKeyExW
0x180039f2f  test    eax, eax
0x180039f31  jnz     short loc_180039F8A
0x180039f33  mov     rcx, [rbp+hKey]; hKey
0x180039f37  lea     rax, [rbp+cbData]
0x180039f3b  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x180039f40  lea     rdx, aSbupdatetype; "SBUpdateType"
0x180039f47  lea     rax, [rbp+Data]
0x180039f4b  xor     r9d, r9d; lpType
0x180039f4e  xor     r8d, r8d; lpReserved
0x180039f51  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180039f56  call    cs:__imp_RegQueryValueExW
0x180039f5c  or      [rbp+Data], ebx
0x180039f5f  lea     rax, [rbp+Data]
0x180039f63  mov     rcx, [rbp+hKey]; hKey
0x180039f67  lea     rdx, aSbupdatetype; "SBUpdateType"
0x180039f6e  mov     [rsp+50h+samDesired], 4; cbData
0x180039f76  mov     r9d, 4; dwType
0x180039f7c  xor     r8d, r8d; Reserved
0x180039f7f  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x180039f84  call    cs:__imp_RegSetValueExW
0x180039f8a  lea     rcx, [rbp+hKey]
0x180039f8e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180039f93  mov     rbx, [rsp+50h+arg_0]
0x180039f98  add     rsp, 50h
0x180039f9c  pop     rbp
0x180039f9d  retn
```
