# FontCacheServiceConfiguration::AreFontProvidersDisabled(void)

- ea: `0x1800b0e3c`
- end: `0x1800b0ef1`
- name: `?AreFontProvidersDisabled@FontCacheServiceConfiguration@@SA_NXZ`
- size: `181`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a7190`

## callees

- `0x180068da0`
- `0x1800b0e3c`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_IsPolicySetByMobileDeviceManager` at `0x1800b0e8e`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_IsPolicySetByMobileDeviceManager` at `0x1800b0e8e`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1800b0eb7`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1800b0eb7`

## string_xrefs

- `0x1800b0ed8`: `SYSTEM\CurrentControlSet\Services\FontCache\Parameters`

## pseudocode

```c
bool FontCacheServiceConfiguration::AreFontProvidersDisabled(void)
{
  int v1; // [rsp+30h] [rbp+10h] BYREF
  int v2; // [rsp+38h] [rbp+18h] BYREF

  v1 = 0;
  if ( (unsigned __int8)RegistryKey::TryGetNumber(
                          2147483650LL,
                          L"SOFTWARE\\Policies\\Microsoft\\Windows\\System",
                          L"EnableFontProviders",
                          &v1) )
    return v1 == 0;
  v2 = 0;
  if ( (int)PolicyManager_IsPolicySetByMobileDeviceManager(L"System", L"AllowFontProviders", &v2) >= 0 )
  {
    if ( v2 )
    {
      v1 = 0;
      if ( (int)PolicyManager_GetPolicyInt(L"System", L"AllowFontProviders", &v1) >= 0 )
        return v1 == 0;
    }
  }
  v1 = 0;
  RegistryKey::TryGetNumber(
    2147483650LL,
    L"SYSTEM\\CurrentControlSet\\Services\\FontCache\\Parameters",
    L"DisableFontProviders",
    &v1);
  return v1 != 0;
}

```

## disassembly

```asm
0x1800b0e3c  push    rbp
0x1800b0e3e  mov     rbp, rsp
0x1800b0e41  sub     rsp, 20h
0x1800b0e45  lea     r9, [rbp+arg_0]
0x1800b0e49  mov     [rbp+arg_0], 0
0x1800b0e50  lea     r8, ?EnableFontProvidersPolicyValueName@@3QB_WB; "EnableFontProviders"
0x1800b0e57  mov     ecx, 80000002h
0x1800b0e5c  lea     rdx, ?SystemGroupPolicyKey@@3QB_WB; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800b0e63  call    ?TryGetNumber@RegistryKey@@SA_NW4RegistryHive@@PEB_W1PEAI@Z; RegistryKey::TryGetNumber(RegistryHive,wchar_t const *,wchar_t const *,uint *)
0x1800b0e68  test    al, al
0x1800b0e6a  jz      short loc_1800B0E75
0x1800b0e6c  cmp     [rbp+arg_0], 0
0x1800b0e70  setz    al
0x1800b0e73  jmp     short loc_1800B0EEB
0x1800b0e75  lea     r8, [rbp+arg_8]
0x1800b0e79  mov     [rbp+arg_8], 0
0x1800b0e80  lea     rdx, aAllowfontprovi; "AllowFontProviders"
0x1800b0e87  lea     rcx, aSystem; "System"
0x1800b0e8e  call    cs:__imp_PolicyManager_IsPolicySetByMobileDeviceManager
0x1800b0e94  test    eax, eax
0x1800b0e96  js      short loc_1800B0EC1
0x1800b0e98  cmp     [rbp+arg_8], 0
0x1800b0e9c  jz      short loc_1800B0EC1
0x1800b0e9e  lea     r8, [rbp+arg_0]
0x1800b0ea2  mov     [rbp+arg_0], 0
0x1800b0ea9  lea     rdx, aAllowfontprovi; "AllowFontProviders"
0x1800b0eb0  lea     rcx, aSystem; "System"
0x1800b0eb7  call    cs:__imp_PolicyManager_GetPolicyInt
0x1800b0ebd  test    eax, eax
0x1800b0ebf  jns     short loc_1800B0E6C
0x1800b0ec1  lea     r9, [rbp+arg_0]
0x1800b0ec5  mov     [rbp+arg_0], 0
0x1800b0ecc  lea     r8, ?DisableFontProvidersValueName@@3QB_WB; "DisableFontProviders"
0x1800b0ed3  mov     ecx, 80000002h
0x1800b0ed8  lea     rdx, ?FontCacheServiceConfigurationKey@@3QB_WB; "SYSTEM\\CurrentControlSet\\Services\\Fo"...
0x1800b0edf  call    ?TryGetNumber@RegistryKey@@SA_NW4RegistryHive@@PEB_W1PEAI@Z; RegistryKey::TryGetNumber(RegistryHive,wchar_t const *,wchar_t const *,uint *)
0x1800b0ee4  cmp     [rbp+arg_0], 0
0x1800b0ee8  setnz   al
0x1800b0eeb  add     rsp, 20h
0x1800b0eef  pop     rbp
0x1800b0ef0  retn
```
