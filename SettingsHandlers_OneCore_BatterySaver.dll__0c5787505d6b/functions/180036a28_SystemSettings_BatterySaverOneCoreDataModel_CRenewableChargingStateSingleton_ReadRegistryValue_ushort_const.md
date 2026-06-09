# SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingStateSingleton::ReadRegistryValue(ushort const *)

- ea: `0x180036a28`
- end: `0x180036ac8`
- name: `?ReadRegistryValue@CRenewableChargingStateSingleton@BatterySaverOneCoreDataModel@SystemSettings@@AEBA_NPEBG@Z`
- size: `160`
- prototype: `bool __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingStateSingleton *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800361f0`
- `0x180036330`

## callees

- `0x18003459c`
- `0x180036a28`
- `0x1800394c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036aa5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036aa5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036a63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036a63`

## pseudocode

```c
bool __fastcall SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingStateSingleton::ReadRegistryValue(
        SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingStateSingleton *this,
        const unsigned __int16 *a2)
{
  bool v2; // bl
  HKEY *phkResult; // rax
  SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingStateSingleton *cbData; // [rsp+40h] [rbp+8h] BYREF
  const unsigned __int16 *Data; // [rsp+48h] [rbp+10h] BYREF
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Data = a2;
  cbData = this;
  v2 = 0;
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\REC", 0, 0x20019u, phkResult) )
  {
    Type = 0;
    LODWORD(Data) = 0;
    LODWORD(cbData) = 4;
    if ( !RegQueryValueExW(hKey, L"IsRECEnabled", 0, &Type, (LPBYTE)&Data, (LPDWORD)&cbData) )
      v2 = (_DWORD)Data != 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v2;
}

```

## disassembly

```asm
0x180036a28  mov     rax, rsp
0x180036a2b  mov     [rax+10h], rdx
0x180036a2f  mov     [rax+8], rcx
0x180036a33  push    rbx
0x180036a34  sub     rsp, 30h
0x180036a38  xor     ebx, ebx
0x180036a3a  lea     rcx, [rax+20h]
0x180036a3e  mov     [rax+20h], rbx
0x180036a42  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180036a47  mov     r9d, 20019h; samDesired
0x180036a4d  mov     [rsp+38h+phkResult], rax; phkResult
0x180036a52  xor     r8d, r8d; ulOptions
0x180036a55  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180036a5c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036a63  call    cs:__imp_RegOpenKeyExW
0x180036a69  test    eax, eax
0x180036a6b  jnz     short loc_180036AB6
0x180036a6d  mov     rcx, [rsp+38h+hKey]; hKey
0x180036a72  lea     rax, [rsp+38h+cbData]
0x180036a77  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180036a7c  lea     r9, [rsp+38h+Type]; lpType
0x180036a81  lea     rax, [rsp+38h+Data]
0x180036a86  mov     [rsp+38h+Type], ebx
0x180036a8a  xor     r8d, r8d; lpReserved
0x180036a8d  mov     [rsp+38h+phkResult], rax; lpData
0x180036a92  lea     rdx, aIsrecenabled; "IsRECEnabled"
0x180036a99  mov     dword ptr [rsp+38h+Data], ebx
0x180036a9d  mov     dword ptr [rsp+38h+cbData], 4
0x180036aa5  call    cs:__imp_RegQueryValueExW
0x180036aab  test    eax, eax
0x180036aad  jnz     short loc_180036AB6
0x180036aaf  cmp     dword ptr [rsp+38h+Data], ebx
0x180036ab3  setnz   bl
0x180036ab6  lea     rcx, [rsp+38h+hKey]
0x180036abb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180036ac0  mov     al, bl
0x180036ac2  add     rsp, 30h
0x180036ac6  pop     rbx
0x180036ac7  retn
```
