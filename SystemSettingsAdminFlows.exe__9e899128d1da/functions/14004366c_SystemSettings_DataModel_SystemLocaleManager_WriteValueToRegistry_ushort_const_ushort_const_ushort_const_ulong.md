# SystemSettings::DataModel::SystemLocaleManager::WriteValueToRegistry(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x14004366c`
- end: `0x1400436f1`
- name: `?WriteValueToRegistry@SystemLocaleManager@DataModel@SystemSettings@@CAJPEBG00K@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, LPCVOID lpData, DWORD cbData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140043338`

## callees

- `0x14000ed38`
- `0x14002c070`
- `0x14004366c`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x1400436ad`
- `KERNEL32!RegOpenKeyExW` at `0x1400436ad`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400436ce`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400436ce`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::SystemLocaleManager::WriteValueToRegistry(
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        LPCVOID lpData,
        DWORD cbData)
{
  HKEY *phkResult; // rax
  HKEY hKey[7]; // [rsp+30h] [rbp-38h] BYREF

  hKey[0] = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 2u, phkResult) )
    RegSetKeyValueW(hKey[0], 0, lpValueName, 1u, lpData, cbData);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return 0;
}

```

## disassembly

```asm
0x14004366c  push    rbx
0x14004366e  push    rsi
0x14004366f  push    rdi
0x140043670  push    r14
0x140043672  sub     rsp, 48h
0x140043676  mov     ebx, r9d
0x140043679  mov     rdi, r8
0x14004367c  mov     rsi, rdx
0x14004367f  mov     r14, rcx
0x140043682  mov     [rsp+68h+hKey], 0
0x14004368b  lea     rcx, [rsp+68h+hKey]
0x140043690  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140043695  mov     [rsp+68h+phkResult], rax; phkResult
0x14004369a  mov     r9d, 2; samDesired
0x1400436a0  xor     r8d, r8d; ulOptions
0x1400436a3  mov     rdx, r14; lpSubKey
0x1400436a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400436ad  call    cs:__imp_RegOpenKeyExW
0x1400436b3  test    eax, eax
0x1400436b5  jnz     short loc_1400436D4
0x1400436b7  mov     [rsp+68h+cbData], ebx; cbData
0x1400436bb  mov     [rsp+68h+phkResult], rdi; lpData
0x1400436c0  lea     r9d, [rax+1]; dwType
0x1400436c4  mov     r8, rsi; lpValueName
0x1400436c7  xor     edx, edx; lpSubKey
0x1400436c9  mov     rcx, [rsp+68h+hKey]; hKey
0x1400436ce  call    cs:__imp_RegSetKeyValueW
0x1400436d4  lea     rcx, [rsp+68h+hKey]
0x1400436d9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400436de  xor     eax, eax
0x1400436e0  jmp     short loc_1400436E6
0x1400436e2  mov     eax, dword ptr [rsp+68h+hKey]
0x1400436e6  add     rsp, 48h
0x1400436ea  pop     r14
0x1400436ec  pop     rdi
0x1400436ed  pop     rsi
0x1400436ee  pop     rbx
0x1400436ef  retn
```
