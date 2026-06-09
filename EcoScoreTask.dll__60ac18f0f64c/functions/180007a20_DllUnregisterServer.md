# DllUnregisterServer

- ea: `0x180007a20`
- end: `0x180007bc0`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006ed0`
- `0x180007a20`
- `0x180007c62`
- `0x180007c90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b94`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180007a7b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180007a7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007b80`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007aff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007b65`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007aff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180007b65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007acf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007b40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007acf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007b40`

## string_xrefs

- `0x180007a90`: `CLSID\\%s`
- `0x180007b32`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_EcoScoreTask, &lpsz);
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
0x180007a20  mov     [rsp-8+arg_0], rbx
0x180007a25  mov     [rsp-8+arg_8], rsi
0x180007a2a  push    rbp
0x180007a2b  lea     rbp, [rsp-160h]
0x180007a33  sub     rsp, 260h
0x180007a3a  mov     rax, cs:__security_cookie
0x180007a41  xor     rax, rsp
0x180007a44  mov     [rbp+160h+var_10], rax
0x180007a4b  xor     edx, edx; Val
0x180007a4d  mov     [rsp+260h+hKey], 0
0x180007a56  mov     r8d, 208h; Size
0x180007a5c  lea     rcx, [rsp+260h+SubKey]; void *
0x180007a61  call    memset_0
0x180007a66  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180007a6b  mov     [rsp+260h+lpsz], 0
0x180007a74  lea     rcx, CLSID_EcoScoreTask; rclsid
0x180007a7b  call    cs:__imp_StringFromCLSID
0x180007a81  mov     ebx, eax
0x180007a83  test    eax, eax
0x180007a85  js      loc_180007B76
0x180007a8b  mov     r9, [rsp+260h+lpsz]
0x180007a90  lea     r8, aClsidS; "CLSID\\\\%s"
0x180007a97  mov     edx, 104h; unsigned __int64
0x180007a9c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180007aa1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007aa6  mov     ebx, eax
0x180007aa8  test    eax, eax
0x180007aaa  js      loc_180007B76
0x180007ab0  lea     rax, [rsp+260h+hKey]
0x180007ab5  mov     r9d, 2000000h; samDesired
0x180007abb  xor     r8d, r8d; ulOptions
0x180007abe  mov     [rsp+260h+phkResult], rax; phkResult
0x180007ac3  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180007ac8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180007acf  call    cs:__imp_RegOpenKeyExW
0x180007ad5  mov     ebx, eax
0x180007ad7  mov     esi, 80070000h
0x180007adc  test    eax, eax
0x180007ade  jle     short loc_180007AE5
0x180007ae0  movzx   ebx, ax
0x180007ae3  or      ebx, esi
0x180007ae5  test    ebx, ebx
0x180007ae7  js      loc_180007B76
0x180007aed  mov     rcx, [rsp+260h+hKey]; hKey
0x180007af2  lea     rdx, SubKey; "InprocServer32"
0x180007af9  xor     r9d, r9d; Reserved
0x180007afc  xor     r8d, r8d; samDesired
0x180007aff  call    cs:__imp_RegDeleteKeyExW
0x180007b05  mov     ebx, eax
0x180007b07  test    eax, eax
0x180007b09  jle     short loc_180007B10
0x180007b0b  movzx   ebx, ax
0x180007b0e  or      ebx, esi
0x180007b10  test    ebx, ebx
0x180007b12  js      short loc_180007B76
0x180007b14  mov     rcx, [rsp+260h+hKey]; hKey
0x180007b19  call    cs:__imp_RegCloseKey
0x180007b1f  lea     rax, [rsp+260h+hKey]
0x180007b24  mov     r9d, 2000000h; samDesired
0x180007b2a  xor     r8d, r8d; ulOptions
0x180007b2d  mov     [rsp+260h+phkResult], rax; phkResult
0x180007b32  lea     rdx, aClsid; "CLSID"
0x180007b39  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180007b40  call    cs:__imp_RegOpenKeyExW
0x180007b46  mov     ebx, eax
0x180007b48  test    eax, eax
0x180007b4a  jle     short loc_180007B51
0x180007b4c  movzx   ebx, ax
0x180007b4f  or      ebx, esi
0x180007b51  test    ebx, ebx
0x180007b53  js      short loc_180007B76
0x180007b55  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180007b5a  xor     r9d, r9d; Reserved
0x180007b5d  mov     rcx, [rsp+260h+hKey]; hKey
0x180007b62  xor     r8d, r8d; samDesired
0x180007b65  call    cs:__imp_RegDeleteKeyExW
0x180007b6b  mov     ebx, eax
0x180007b6d  test    eax, eax
0x180007b6f  jle     short loc_180007B76
0x180007b71  movzx   ebx, ax
0x180007b74  or      ebx, esi
0x180007b76  mov     rcx, [rsp+260h+hKey]; hKey
0x180007b7b  test    rcx, rcx
0x180007b7e  jz      short loc_180007B8F
0x180007b80  call    cs:__imp_RegCloseKey
0x180007b86  mov     [rsp+260h+hKey], 0
0x180007b8f  mov     rcx, [rsp+260h+lpsz]; pv
0x180007b94  call    cs:__imp_CoTaskMemFree
0x180007b9a  mov     eax, ebx
0x180007b9c  mov     rcx, [rbp+160h+var_10]
0x180007ba3  xor     rcx, rsp; StackCookie
0x180007ba6  call    __security_check_cookie
0x180007bab  lea     r11, [rsp+260h+var_s0]
0x180007bb3  mov     rbx, [r11+10h]
0x180007bb7  mov     rsi, [r11+18h]
0x180007bbb  mov     rsp, r11
0x180007bbe  pop     rbp
0x180007bbf  retn
```
