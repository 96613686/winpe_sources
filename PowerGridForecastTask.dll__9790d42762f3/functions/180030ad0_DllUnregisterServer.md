# DllUnregisterServer

- ea: `0x180030ad0`
- end: `0x180030c70`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800268ef`
- `0x18002edf0`
- `0x180030ad0`
- `0x1800350e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030c44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030c44`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180030b2b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180030b2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030bc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030c30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030bc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030c30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030b7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030bf0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030b7f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030bf0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030baf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030c15`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030baf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180030c15`

## string_xrefs

- `0x180030b40`: `CLSID\\%s`
- `0x180030be2`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_DeferredChargingTask, &lpsz);
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
0x180030ad0  mov     [rsp-8+arg_0], rbx
0x180030ad5  mov     [rsp-8+arg_8], rsi
0x180030ada  push    rbp
0x180030adb  lea     rbp, [rsp-160h]
0x180030ae3  sub     rsp, 260h
0x180030aea  mov     rax, cs:__security_cookie
0x180030af1  xor     rax, rsp
0x180030af4  mov     [rbp+160h+var_10], rax
0x180030afb  xor     edx, edx; Val
0x180030afd  mov     [rsp+260h+hKey], 0
0x180030b06  mov     r8d, 208h; Size
0x180030b0c  lea     rcx, [rsp+260h+SubKey]; void *
0x180030b11  call    memset_0
0x180030b16  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180030b1b  mov     [rsp+260h+lpsz], 0
0x180030b24  lea     rcx, CLSID_DeferredChargingTask; rclsid
0x180030b2b  call    cs:__imp_StringFromCLSID
0x180030b31  mov     ebx, eax
0x180030b33  test    eax, eax
0x180030b35  js      loc_180030C26
0x180030b3b  mov     r9, [rsp+260h+lpsz]
0x180030b40  lea     r8, aClsidS; "CLSID\\\\%s"
0x180030b47  mov     edx, 104h; unsigned __int64
0x180030b4c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180030b51  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030b56  mov     ebx, eax
0x180030b58  test    eax, eax
0x180030b5a  js      loc_180030C26
0x180030b60  lea     rax, [rsp+260h+hKey]
0x180030b65  mov     r9d, 2000000h; samDesired
0x180030b6b  xor     r8d, r8d; ulOptions
0x180030b6e  mov     [rsp+260h+phkResult], rax; phkResult
0x180030b73  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180030b78  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180030b7f  call    cs:__imp_RegOpenKeyExW
0x180030b85  mov     ebx, eax
0x180030b87  mov     esi, 80070000h
0x180030b8c  test    eax, eax
0x180030b8e  jle     short loc_180030B95
0x180030b90  movzx   ebx, ax
0x180030b93  or      ebx, esi
0x180030b95  test    ebx, ebx
0x180030b97  js      loc_180030C26
0x180030b9d  mov     rcx, [rsp+260h+hKey]; hKey
0x180030ba2  lea     rdx, SubKey; "InprocServer32"
0x180030ba9  xor     r9d, r9d; Reserved
0x180030bac  xor     r8d, r8d; samDesired
0x180030baf  call    cs:__imp_RegDeleteKeyExW
0x180030bb5  mov     ebx, eax
0x180030bb7  test    eax, eax
0x180030bb9  jle     short loc_180030BC0
0x180030bbb  movzx   ebx, ax
0x180030bbe  or      ebx, esi
0x180030bc0  test    ebx, ebx
0x180030bc2  js      short loc_180030C26
0x180030bc4  mov     rcx, [rsp+260h+hKey]; hKey
0x180030bc9  call    cs:__imp_RegCloseKey
0x180030bcf  lea     rax, [rsp+260h+hKey]
0x180030bd4  mov     r9d, 2000000h; samDesired
0x180030bda  xor     r8d, r8d; ulOptions
0x180030bdd  mov     [rsp+260h+phkResult], rax; phkResult
0x180030be2  lea     rdx, aClsid; "CLSID"
0x180030be9  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180030bf0  call    cs:__imp_RegOpenKeyExW
0x180030bf6  mov     ebx, eax
0x180030bf8  test    eax, eax
0x180030bfa  jle     short loc_180030C01
0x180030bfc  movzx   ebx, ax
0x180030bff  or      ebx, esi
0x180030c01  test    ebx, ebx
0x180030c03  js      short loc_180030C26
0x180030c05  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180030c0a  xor     r9d, r9d; Reserved
0x180030c0d  mov     rcx, [rsp+260h+hKey]; hKey
0x180030c12  xor     r8d, r8d; samDesired
0x180030c15  call    cs:__imp_RegDeleteKeyExW
0x180030c1b  mov     ebx, eax
0x180030c1d  test    eax, eax
0x180030c1f  jle     short loc_180030C26
0x180030c21  movzx   ebx, ax
0x180030c24  or      ebx, esi
0x180030c26  mov     rcx, [rsp+260h+hKey]; hKey
0x180030c2b  test    rcx, rcx
0x180030c2e  jz      short loc_180030C3F
0x180030c30  call    cs:__imp_RegCloseKey
0x180030c36  mov     [rsp+260h+hKey], 0
0x180030c3f  mov     rcx, [rsp+260h+lpsz]; pv
0x180030c44  call    cs:__imp_CoTaskMemFree
0x180030c4a  mov     eax, ebx
0x180030c4c  mov     rcx, [rbp+160h+var_10]
0x180030c53  xor     rcx, rsp; StackCookie
0x180030c56  call    __security_check_cookie
0x180030c5b  lea     r11, [rsp+260h+var_s0]
0x180030c63  mov     rbx, [r11+10h]
0x180030c67  mov     rsi, [r11+18h]
0x180030c6b  mov     rsp, r11
0x180030c6e  pop     rbp
0x180030c6f  retn
```
