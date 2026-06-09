# DeveloperOptionsAdminFlowHandler::WriteRegistry(HKEY__ *,wchar_t const *,wchar_t const *,ulong)

- ea: `0x140065ea4`
- end: `0x140065f9e`
- name: `?WriteRegistry@DeveloperOptionsAdminFlowHandler@@CAJPEAUHKEY__@@PEB_W1K@Z`
- size: `250`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140020120`
- `0x140064c5c`

## callees

- `0x14000ed38`
- `0x14001f3f8`
- `0x14002c070`
- `0x140065ea4`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x140065ee6`
- `KERNEL32!RegOpenKeyExW` at `0x140065ee6`
- `KERNEL32!RegCreateKeyExW` at `0x140065f2d`
- `KERNEL32!RegCreateKeyExW` at `0x140065f2d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140065f59`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x140065f59`

## pseudocode

```c
__int64 __fastcall DeveloperOptionsAdminFlowHandler::WriteRegistry(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        int a4)
{
  HKEY *v7; // rax
  HKEY *v8; // rax
  unsigned int Key; // eax
  unsigned int v10; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-48h]
  HKEY hKeya[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int Data; // [rsp+88h] [rbp+20h] BYREF

  Data = a4;
  hKeya[0] = 0;
  v7 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKeya);
  if ( RegOpenKeyExW(hKey, lpSubKey, 0, 2u, v7)
    && (v8 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKeya),
        (Key = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 2u, 0, v8, 0)) != 0)
    || (Key = RegSetKeyValueW(hKeya[0], 0, lpValueName, 4u, &Data, 4u)) != 0 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x174,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\developeroptions\\developeroptionsadminflowhandler.cpp",
            (const char *)Key,
            phkResult);
  }
  else
  {
    v10 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKeya);
  return v10;
}

```

## disassembly

```asm
0x140065ea4  mov     rax, rsp
0x140065ea7  mov     [rax+8], rbx
0x140065eab  mov     [rax+10h], rsi
0x140065eaf  mov     [rax+20h], r9d
0x140065eb3  push    rdi
0x140065eb4  sub     rsp, 60h
0x140065eb8  mov     rdi, rcx
0x140065ebb  mov     qword ptr [rax-18h], 0
0x140065ec3  lea     rcx, [rax-18h]
0x140065ec7  mov     rsi, r8
0x140065eca  mov     rbx, rdx
0x140065ecd  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140065ed2  mov     r9d, 2; samDesired
0x140065ed8  mov     [rsp+68h+phkResult], rax; phkResult
0x140065edd  xor     r8d, r8d; ulOptions
0x140065ee0  mov     rdx, rbx; lpSubKey
0x140065ee3  mov     rcx, rdi; hKey
0x140065ee6  call    cs:__imp_RegOpenKeyExW
0x140065eec  test    eax, eax
0x140065eee  jz      short loc_140065F37
0x140065ef0  lea     rcx, [rsp+68h+hKey]
0x140065ef5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140065efa  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x140065f03  xor     r9d, r9d; lpClass
0x140065f06  mov     [rsp+68h+var_30], rax; phkResult
0x140065f0b  xor     r8d, r8d; Reserved
0x140065f0e  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140065f17  mov     rdx, rbx; lpSubKey
0x140065f1a  mov     [rsp+68h+samDesired], 2; samDesired
0x140065f22  mov     rcx, rdi; hKey
0x140065f25  mov     dword ptr [rsp+68h+phkResult], 0; dwOptions
0x140065f2d  call    cs:__imp_RegCreateKeyExW
0x140065f33  test    eax, eax
0x140065f35  jnz     short loc_140065F63
0x140065f37  mov     rcx, [rsp+68h+hKey]; hKey
0x140065f3c  lea     rax, [rsp+68h+Data]
0x140065f44  mov     r9d, 4; dwType
0x140065f4a  mov     r8, rsi; lpValueName
0x140065f4d  mov     [rsp+68h+samDesired], r9d; cbData
0x140065f52  xor     edx, edx; lpSubKey
0x140065f54  mov     [rsp+68h+phkResult], rax; unsigned int
0x140065f59  call    cs:__imp_RegSetKeyValueW
0x140065f5f  test    eax, eax
0x140065f61  jz      short loc_140065F80
0x140065f63  mov     rcx, [rsp+68h]; this
0x140065f68  lea     r8, aPcshellShellSy_32; "pcshell\\shell\\systemsettings\\adminfl"...
0x140065f6f  mov     r9d, eax; char *
0x140065f72  mov     edx, 174h; void *
0x140065f77  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140065f7c  mov     ebx, eax
0x140065f7e  jmp     short loc_140065F82
0x140065f80  xor     ebx, ebx
0x140065f82  lea     rcx, [rsp+68h+hKey]
0x140065f87  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140065f8c  mov     rsi, [rsp+68h+arg_8]
0x140065f91  mov     eax, ebx
0x140065f93  mov     rbx, [rsp+68h+arg_0]
0x140065f98  add     rsp, 60h
0x140065f9c  pop     rdi
0x140065f9d  retn
```
