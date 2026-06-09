# DllUnregisterServer

- ea: `0x180002e50`
- end: `0x180002ff0`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d2a`
- `0x180001fd4`
- `0x180002e50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002fb0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002fb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002eff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f70`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002eff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002f70`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002f2f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002f95`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002f2f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002f95`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180002eab`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180002eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002fc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002fc4`

## string_xrefs

- `0x180002ec0`: `CLSID\\%s`
- `0x180002f62`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_TimeSyncTask, &lpsz);
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
0x180002e50  mov     [rsp-8+arg_0], rbx
0x180002e55  mov     [rsp-8+arg_8], rsi
0x180002e5a  push    rbp
0x180002e5b  lea     rbp, [rsp-160h]
0x180002e63  sub     rsp, 260h
0x180002e6a  mov     rax, cs:__security_cookie
0x180002e71  xor     rax, rsp
0x180002e74  mov     [rbp+160h+var_10], rax
0x180002e7b  xor     edx, edx; Val
0x180002e7d  mov     [rsp+260h+hKey], 0
0x180002e86  mov     r8d, 208h; Size
0x180002e8c  lea     rcx, [rsp+260h+SubKey]; void *
0x180002e91  call    memset_0
0x180002e96  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180002e9b  mov     [rsp+260h+lpsz], 0
0x180002ea4  lea     rcx, CLSID_TimeSyncTask; rclsid
0x180002eab  call    cs:__imp_StringFromCLSID
0x180002eb1  mov     ebx, eax
0x180002eb3  test    eax, eax
0x180002eb5  js      loc_180002FA6
0x180002ebb  mov     r9, [rsp+260h+lpsz]
0x180002ec0  lea     r8, aClsidS; "CLSID\\\\%s"
0x180002ec7  mov     edx, 104h; unsigned __int64
0x180002ecc  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180002ed1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002ed6  mov     ebx, eax
0x180002ed8  test    eax, eax
0x180002eda  js      loc_180002FA6
0x180002ee0  lea     rax, [rsp+260h+hKey]
0x180002ee5  mov     r9d, 2000000h; samDesired
0x180002eeb  xor     r8d, r8d; ulOptions
0x180002eee  mov     [rsp+260h+phkResult], rax; phkResult
0x180002ef3  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180002ef8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002eff  call    cs:__imp_RegOpenKeyExW
0x180002f05  mov     ebx, eax
0x180002f07  mov     esi, 80070000h
0x180002f0c  test    eax, eax
0x180002f0e  jle     short loc_180002F15
0x180002f10  movzx   ebx, ax
0x180002f13  or      ebx, esi
0x180002f15  test    ebx, ebx
0x180002f17  js      loc_180002FA6
0x180002f1d  mov     rcx, [rsp+260h+hKey]; hKey
0x180002f22  lea     rdx, SubKey; "InprocServer32"
0x180002f29  xor     r9d, r9d; Reserved
0x180002f2c  xor     r8d, r8d; samDesired
0x180002f2f  call    cs:__imp_RegDeleteKeyExW
0x180002f35  mov     ebx, eax
0x180002f37  test    eax, eax
0x180002f39  jle     short loc_180002F40
0x180002f3b  movzx   ebx, ax
0x180002f3e  or      ebx, esi
0x180002f40  test    ebx, ebx
0x180002f42  js      short loc_180002FA6
0x180002f44  mov     rcx, [rsp+260h+hKey]; hKey
0x180002f49  call    cs:__imp_RegCloseKey
0x180002f4f  lea     rax, [rsp+260h+hKey]
0x180002f54  mov     r9d, 2000000h; samDesired
0x180002f5a  xor     r8d, r8d; ulOptions
0x180002f5d  mov     [rsp+260h+phkResult], rax; phkResult
0x180002f62  lea     rdx, aClsid; "CLSID"
0x180002f69  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002f70  call    cs:__imp_RegOpenKeyExW
0x180002f76  mov     ebx, eax
0x180002f78  test    eax, eax
0x180002f7a  jle     short loc_180002F81
0x180002f7c  movzx   ebx, ax
0x180002f7f  or      ebx, esi
0x180002f81  test    ebx, ebx
0x180002f83  js      short loc_180002FA6
0x180002f85  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180002f8a  xor     r9d, r9d; Reserved
0x180002f8d  mov     rcx, [rsp+260h+hKey]; hKey
0x180002f92  xor     r8d, r8d; samDesired
0x180002f95  call    cs:__imp_RegDeleteKeyExW
0x180002f9b  mov     ebx, eax
0x180002f9d  test    eax, eax
0x180002f9f  jle     short loc_180002FA6
0x180002fa1  movzx   ebx, ax
0x180002fa4  or      ebx, esi
0x180002fa6  mov     rcx, [rsp+260h+hKey]; hKey
0x180002fab  test    rcx, rcx
0x180002fae  jz      short loc_180002FBF
0x180002fb0  call    cs:__imp_RegCloseKey
0x180002fb6  mov     [rsp+260h+hKey], 0
0x180002fbf  mov     rcx, [rsp+260h+lpsz]; pv
0x180002fc4  call    cs:__imp_CoTaskMemFree
0x180002fca  mov     eax, ebx
0x180002fcc  mov     rcx, [rbp+160h+var_10]
0x180002fd3  xor     rcx, rsp; StackCookie
0x180002fd6  call    __security_check_cookie
0x180002fdb  lea     r11, [rsp+260h+var_s0]
0x180002fe3  mov     rbx, [r11+10h]
0x180002fe7  mov     rsi, [r11+18h]
0x180002feb  mov     rsp, r11
0x180002fee  pop     rbp
0x180002fef  retn
```
