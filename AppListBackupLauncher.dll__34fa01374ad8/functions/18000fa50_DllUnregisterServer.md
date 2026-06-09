# DllUnregisterServer

- ea: `0x18000fa50`
- end: `0x18000fbf0`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002300`
- `0x180002de0`
- `0x18000d290`
- `0x18000fa50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000faab`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000faab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fbc4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000faff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fb70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000faff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fb70`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000fb2f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000fb95`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000fb2f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000fb95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fbb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fbb0`

## string_xrefs

- `0x18000fac0`: `CLSID\\%s`
- `0x18000fb62`: `CLSID`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT v0; // ebx
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
  v0 = StringFromCLSID(&CLSID_AppListBackupLauncher, &lpsz);
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
  return v0;
}

```

## disassembly

```asm
0x18000fa50  mov     [rsp-8+arg_0], rbx
0x18000fa55  mov     [rsp-8+arg_8], rsi
0x18000fa5a  push    rbp
0x18000fa5b  lea     rbp, [rsp-160h]
0x18000fa63  sub     rsp, 260h
0x18000fa6a  mov     rax, cs:__security_cookie
0x18000fa71  xor     rax, rsp
0x18000fa74  mov     [rbp+160h+var_10], rax
0x18000fa7b  xor     edx, edx; Val
0x18000fa7d  mov     [rsp+260h+hKey], 0
0x18000fa86  mov     r8d, 208h; Size
0x18000fa8c  lea     rcx, [rsp+260h+SubKey]; void *
0x18000fa91  call    memset_0
0x18000fa96  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x18000fa9b  mov     [rsp+260h+lpsz], 0
0x18000faa4  lea     rcx, CLSID_AppListBackupLauncher; rclsid
0x18000faab  call    cs:__imp_StringFromCLSID
0x18000fab1  mov     ebx, eax
0x18000fab3  test    eax, eax
0x18000fab5  js      loc_18000FBA6
0x18000fabb  mov     r9, [rsp+260h+lpsz]
0x18000fac0  lea     r8, aClsidS; "CLSID\\\\%s"
0x18000fac7  mov     edx, 104h; unsigned __int64
0x18000facc  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000fad1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fad6  mov     ebx, eax
0x18000fad8  test    eax, eax
0x18000fada  js      loc_18000FBA6
0x18000fae0  lea     rax, [rsp+260h+hKey]
0x18000fae5  mov     r9d, 2000000h; samDesired
0x18000faeb  xor     r8d, r8d; ulOptions
0x18000faee  mov     [rsp+260h+phkResult], rax; phkResult
0x18000faf3  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x18000faf8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000faff  call    cs:__imp_RegOpenKeyExW
0x18000fb05  mov     ebx, eax
0x18000fb07  mov     esi, 80070000h
0x18000fb0c  test    eax, eax
0x18000fb0e  jle     short loc_18000FB15
0x18000fb10  movzx   ebx, ax
0x18000fb13  or      ebx, esi
0x18000fb15  test    ebx, ebx
0x18000fb17  js      loc_18000FBA6
0x18000fb1d  mov     rcx, [rsp+260h+hKey]; hKey
0x18000fb22  lea     rdx, aInprocserver32; "InprocServer32"
0x18000fb29  xor     r9d, r9d; Reserved
0x18000fb2c  xor     r8d, r8d; samDesired
0x18000fb2f  call    cs:__imp_RegDeleteKeyExW
0x18000fb35  mov     ebx, eax
0x18000fb37  test    eax, eax
0x18000fb39  jle     short loc_18000FB40
0x18000fb3b  movzx   ebx, ax
0x18000fb3e  or      ebx, esi
0x18000fb40  test    ebx, ebx
0x18000fb42  js      short loc_18000FBA6
0x18000fb44  mov     rcx, [rsp+260h+hKey]; hKey
0x18000fb49  call    cs:__imp_RegCloseKey
0x18000fb4f  lea     rax, [rsp+260h+hKey]
0x18000fb54  mov     r9d, 2000000h; samDesired
0x18000fb5a  xor     r8d, r8d; ulOptions
0x18000fb5d  mov     [rsp+260h+phkResult], rax; phkResult
0x18000fb62  lea     rdx, aClsid; "CLSID"
0x18000fb69  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000fb70  call    cs:__imp_RegOpenKeyExW
0x18000fb76  mov     ebx, eax
0x18000fb78  test    eax, eax
0x18000fb7a  jle     short loc_18000FB81
0x18000fb7c  movzx   ebx, ax
0x18000fb7f  or      ebx, esi
0x18000fb81  test    ebx, ebx
0x18000fb83  js      short loc_18000FBA6
0x18000fb85  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x18000fb8a  xor     r9d, r9d; Reserved
0x18000fb8d  mov     rcx, [rsp+260h+hKey]; hKey
0x18000fb92  xor     r8d, r8d; samDesired
0x18000fb95  call    cs:__imp_RegDeleteKeyExW
0x18000fb9b  mov     ebx, eax
0x18000fb9d  test    eax, eax
0x18000fb9f  jle     short loc_18000FBA6
0x18000fba1  movzx   ebx, ax
0x18000fba4  or      ebx, esi
0x18000fba6  mov     rcx, [rsp+260h+hKey]; hKey
0x18000fbab  test    rcx, rcx
0x18000fbae  jz      short loc_18000FBBF
0x18000fbb0  call    cs:__imp_RegCloseKey
0x18000fbb6  mov     [rsp+260h+hKey], 0
0x18000fbbf  mov     rcx, [rsp+260h+lpsz]; pv
0x18000fbc4  call    cs:__imp_CoTaskMemFree
0x18000fbca  mov     eax, ebx
0x18000fbcc  mov     rcx, [rbp+160h+var_10]
0x18000fbd3  xor     rcx, rsp; StackCookie
0x18000fbd6  call    __security_check_cookie
0x18000fbdb  lea     r11, [rsp+260h+var_s0]
0x18000fbe3  mov     rbx, [r11+10h]
0x18000fbe7  mov     rsi, [r11+18h]
0x18000fbeb  mov     rsp, r11
0x18000fbee  pop     rbp
0x18000fbef  retn
```
