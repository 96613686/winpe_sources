# CWinTaskModuleT<SettingsConfigTaskHandler,&_GUID const CLSID_SettingsConfigTaskHandler>::DllUnregisterServer(void)

- ea: `0x180005814`
- end: `0x1800059b4`
- name: `?DllUnregisterServer@?$CWinTaskModuleT@VSettingsConfigTaskHandler@@$1?CLSID_SettingsConfigTaskHandler@@3U_GUID@@B@@QEAAJXZ`
- size: `416`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b970`

## callees

- `0x1800021d0`
- `0x180002c18`
- `0x180005814`
- `0x180009f8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005988`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000586f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000586f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800058c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005934`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800058c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005934`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000590d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005974`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000590d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005974`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800058f3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180005959`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800058f3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180005959`

## string_xrefs

- `0x180005884`: `CLSID\\%s`
- `0x180005926`: `CLSID`

## pseudocode

```c
__int64 CWinTaskModuleT<SettingsConfigTaskHandler,&_GUID const CLSID_SettingsConfigTaskHandler>::DllUnregisterServer()
{
  int v0; // ebx
  LSTATUS v1; // eax
  LSTATUS v2; // eax
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  lpsz = 0;
  v0 = StringFromCLSID(&CLSID_SettingsConfigTaskHandler, &lpsz);
  if ( v0 >= 0 )
  {
    v0 = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\\\%s", lpsz);
    if ( v0 >= 0 )
    {
      v1 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2000000u, &hKey);
      v0 = v1;
      if ( v1 > 0 )
        v0 = (unsigned __int16)v1 | 0x80070000;
      if ( v0 >= 0 )
      {
        v2 = RegDeleteKeyExW(hKey, L"InprocServer32", 0, 0);
        v0 = v2;
        if ( v2 > 0 )
          v0 = (unsigned __int16)v2 | 0x80070000;
        if ( v0 >= 0 )
        {
          RegCloseKey(hKey);
          v3 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x2000000u, &hKey);
          v0 = v3;
          if ( v3 > 0 )
            v0 = (unsigned __int16)v3 | 0x80070000;
          if ( v0 >= 0 )
          {
            v4 = RegDeleteKeyExW(hKey, lpsz, 0, 0);
            v0 = v4;
            if ( v4 > 0 )
              v0 = (unsigned __int16)v4 | 0x80070000;
          }
        }
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CoTaskMemFree(lpsz);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180005814  mov     [rsp-8+arg_0], rbx
0x180005819  mov     [rsp-8+arg_8], rsi
0x18000581e  push    rbp
0x18000581f  lea     rbp, [rsp-160h]
0x180005827  sub     rsp, 260h
0x18000582e  mov     rax, cs:__security_cookie
0x180005835  xor     rax, rsp
0x180005838  mov     [rbp+160h+var_10], rax
0x18000583f  xor     edx, edx; Val
0x180005841  mov     [rsp+260h+hKey], 0
0x18000584a  mov     r8d, 208h; Size
0x180005850  lea     rcx, [rsp+260h+SubKey]; void *
0x180005855  call    memset_0
0x18000585a  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x18000585f  mov     [rsp+260h+lpsz], 0
0x180005868  lea     rcx, CLSID_SettingsConfigTaskHandler; rclsid
0x18000586f  call    cs:__imp_StringFromCLSID
0x180005875  mov     ebx, eax
0x180005877  test    eax, eax
0x180005879  js      loc_18000596A
0x18000587f  mov     r9, [rsp+260h+lpsz]
0x180005884  lea     r8, aClsidS; "CLSID\\\\%s"
0x18000588b  mov     edx, 104h; unsigned __int64
0x180005890  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180005895  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000589a  mov     ebx, eax
0x18000589c  test    eax, eax
0x18000589e  js      loc_18000596A
0x1800058a4  lea     rax, [rsp+260h+hKey]
0x1800058a9  mov     r9d, 2000000h; samDesired
0x1800058af  xor     r8d, r8d; ulOptions
0x1800058b2  mov     [rsp+260h+phkResult], rax; phkResult
0x1800058b7  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x1800058bc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800058c3  call    cs:__imp_RegOpenKeyExW
0x1800058c9  mov     ebx, eax
0x1800058cb  mov     esi, 80070000h
0x1800058d0  test    eax, eax
0x1800058d2  jle     short loc_1800058D9
0x1800058d4  movzx   ebx, ax
0x1800058d7  or      ebx, esi
0x1800058d9  test    ebx, ebx
0x1800058db  js      loc_18000596A
0x1800058e1  mov     rcx, [rsp+260h+hKey]; hKey
0x1800058e6  lea     rdx, SubKey; "InprocServer32"
0x1800058ed  xor     r9d, r9d; Reserved
0x1800058f0  xor     r8d, r8d; samDesired
0x1800058f3  call    cs:__imp_RegDeleteKeyExW
0x1800058f9  mov     ebx, eax
0x1800058fb  test    eax, eax
0x1800058fd  jle     short loc_180005904
0x1800058ff  movzx   ebx, ax
0x180005902  or      ebx, esi
0x180005904  test    ebx, ebx
0x180005906  js      short loc_18000596A
0x180005908  mov     rcx, [rsp+260h+hKey]; hKey
0x18000590d  call    cs:__imp_RegCloseKey
0x180005913  lea     rax, [rsp+260h+hKey]
0x180005918  mov     r9d, 2000000h; samDesired
0x18000591e  xor     r8d, r8d; ulOptions
0x180005921  mov     [rsp+260h+phkResult], rax; phkResult
0x180005926  lea     rdx, aClsid; "CLSID"
0x18000592d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180005934  call    cs:__imp_RegOpenKeyExW
0x18000593a  mov     ebx, eax
0x18000593c  test    eax, eax
0x18000593e  jle     short loc_180005945
0x180005940  movzx   ebx, ax
0x180005943  or      ebx, esi
0x180005945  test    ebx, ebx
0x180005947  js      short loc_18000596A
0x180005949  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x18000594e  xor     r9d, r9d; Reserved
0x180005951  mov     rcx, [rsp+260h+hKey]; hKey
0x180005956  xor     r8d, r8d; samDesired
0x180005959  call    cs:__imp_RegDeleteKeyExW
0x18000595f  mov     ebx, eax
0x180005961  test    eax, eax
0x180005963  jle     short loc_18000596A
0x180005965  movzx   ebx, ax
0x180005968  or      ebx, esi
0x18000596a  mov     rcx, [rsp+260h+hKey]; hKey
0x18000596f  test    rcx, rcx
0x180005972  jz      short loc_180005983
0x180005974  call    cs:__imp_RegCloseKey
0x18000597a  mov     [rsp+260h+hKey], 0
0x180005983  mov     rcx, [rsp+260h+lpsz]; pv
0x180005988  call    cs:__imp_CoTaskMemFree
0x18000598e  mov     eax, ebx
0x180005990  mov     rcx, [rbp+160h+var_10]
0x180005997  xor     rcx, rsp; StackCookie
0x18000599a  call    __security_check_cookie
0x18000599f  lea     r11, [rsp+260h+var_s0]
0x1800059a7  mov     rbx, [r11+10h]
0x1800059ab  mov     rsi, [r11+18h]
0x1800059af  mov     rsp, r11
0x1800059b2  pop     rbp
0x1800059b3  retn
```
