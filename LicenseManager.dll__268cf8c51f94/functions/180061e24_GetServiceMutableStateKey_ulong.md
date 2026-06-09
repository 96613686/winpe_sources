# GetServiceMutableStateKey(ulong)

- ea: `0x180061e24`
- end: `0x180061ee5`
- name: `?GetServiceMutableStateKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `193`
- prototype: `__int64 __fastcall(PHKEY phkResult, REGSAM samDesired)`
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005914`
- `0x1800606f8`
- `0x18006118c`
- `0x180061cb4`
- `0x180061d48`
- `0x1800626ec`
- `0x18006547c`
- `0x180090be8`

## callees

- `0x180061e24`
- `0x180061eec`
- `0x180090f34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180061eb2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180061eb2`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x180061e67`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x180061e67`

## string_xrefs

- `0x180061ec4`: `onecoreuap\enduser\winstore\licensemanager\lib\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PHKEY __fastcall GetServiceMutableStateKey(PHKEY phkResult, REGSAM samDesired)
{
  unsigned int Key; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  if ( (unsigned int)GetServiceRegistryStateKey(ServiceStatusHandle, 1, samDesired, phkResult) )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      phkResult,
      0);
    Key = RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Store\\LicenseManager",
            0,
            0,
            0,
            samDesired,
            0,
            phkResult,
            0);
    if ( Key )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\registry.cpp",
        (const char *)Key,
        dwOptions);
  }
  return phkResult;
}

```

## disassembly

```asm
0x180061e24  mov     rax, rsp
0x180061e27  mov     [rax+10h], rbx
0x180061e2b  mov     [rax+8], rcx
0x180061e2f  push    rdi
0x180061e30  sub     rsp, 60h
0x180061e34  mov     edi, edx
0x180061e36  mov     rbx, rcx
0x180061e39  mov     dword ptr [rax-18h], 0
0x180061e40  mov     qword ptr [rcx], 0
0x180061e47  mov     dword ptr [rax-18h], 1
0x180061e4e  xor     edx, edx
0x180061e50  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180061e55  mov     r9, rbx
0x180061e58  mov     r8d, edi
0x180061e5b  mov     edx, 1
0x180061e60  mov     rcx, cs:ServiceStatusHandle
0x180061e67  call    cs:__imp_GetServiceRegistryStateKey
0x180061e6d  test    eax, eax
0x180061e6f  jz      short loc_180061ED6
0x180061e71  xor     edx, edx
0x180061e73  mov     rcx, rbx
0x180061e76  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180061e7b  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180061e84  mov     [rsp+68h+phkResult], rbx; phkResult
0x180061e89  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180061e92  mov     [rsp+68h+samDesired], edi; samDesired
0x180061e96  mov     [rsp+68h+dwOptions], 0; unsigned int
0x180061e9e  xor     r9d, r9d; lpClass
0x180061ea1  xor     r8d, r8d; Reserved
0x180061ea4  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180061eab  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180061eb2  call    cs:__imp_RegCreateKeyExW
0x180061eb8  test    eax, eax
0x180061eba  jz      short loc_180061ED6
0x180061ebc  mov     rcx, [rsp+68h]; this
0x180061ec1  mov     r9d, eax; char *
0x180061ec4  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\licensem"...
0x180061ecb  mov     edx, 0CAh; void *
0x180061ed0  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180061ed6  mov     rax, rbx
0x180061ed9  mov     rbx, [rsp+68h+arg_8]
0x180061ede  add     rsp, 60h
0x180061ee2  pop     rdi
0x180061ee3  retn
```
