# DllUnregisterServer

- ea: `0x18000c5a0`
- end: `0x18000c740`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001400`
- `0x180001f5e`
- `0x18000230c`
- `0x18000c5a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c699`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c700`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c699`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c700`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000c67f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000c6e5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000c67f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000c6e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c64f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c6c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c64f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c6c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c714`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c714`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000c5fb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000c5fb`

## string_xrefs

- `0x18000c610`: `CLSID\\%s`
- `0x18000c6b2`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_TempSignedLicenseExchangeTask, &lpsz);
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
0x18000c5a0  mov     [rsp-8+arg_0], rbx
0x18000c5a5  mov     [rsp-8+arg_8], rsi
0x18000c5aa  push    rbp
0x18000c5ab  lea     rbp, [rsp-160h]
0x18000c5b3  sub     rsp, 260h
0x18000c5ba  mov     rax, cs:__security_cookie
0x18000c5c1  xor     rax, rsp
0x18000c5c4  mov     [rbp+160h+var_10], rax
0x18000c5cb  xor     edx, edx; Val
0x18000c5cd  mov     [rsp+260h+hKey], 0
0x18000c5d6  mov     r8d, 208h; Size
0x18000c5dc  lea     rcx, [rsp+260h+SubKey]; void *
0x18000c5e1  call    memset_0
0x18000c5e6  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x18000c5eb  mov     [rsp+260h+lpsz], 0
0x18000c5f4  lea     rcx, CLSID_TempSignedLicenseExchangeTask; rclsid
0x18000c5fb  call    cs:__imp_StringFromCLSID
0x18000c601  mov     ebx, eax
0x18000c603  test    eax, eax
0x18000c605  js      loc_18000C6F6
0x18000c60b  mov     r9, [rsp+260h+lpsz]
0x18000c610  lea     r8, aClsidS; "CLSID\\\\%s"
0x18000c617  mov     edx, 104h; unsigned __int64
0x18000c61c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000c621  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c626  mov     ebx, eax
0x18000c628  test    eax, eax
0x18000c62a  js      loc_18000C6F6
0x18000c630  lea     rax, [rsp+260h+hKey]
0x18000c635  mov     r9d, 2000000h; samDesired
0x18000c63b  xor     r8d, r8d; ulOptions
0x18000c63e  mov     [rsp+260h+phkResult], rax; phkResult
0x18000c643  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x18000c648  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000c64f  call    cs:__imp_RegOpenKeyExW
0x18000c655  mov     ebx, eax
0x18000c657  mov     esi, 80070000h
0x18000c65c  test    eax, eax
0x18000c65e  jle     short loc_18000C665
0x18000c660  movzx   ebx, ax
0x18000c663  or      ebx, esi
0x18000c665  test    ebx, ebx
0x18000c667  js      loc_18000C6F6
0x18000c66d  mov     rcx, [rsp+260h+hKey]; hKey
0x18000c672  lea     rdx, aInprocserver32; "InprocServer32"
0x18000c679  xor     r9d, r9d; Reserved
0x18000c67c  xor     r8d, r8d; samDesired
0x18000c67f  call    cs:__imp_RegDeleteKeyExW
0x18000c685  mov     ebx, eax
0x18000c687  test    eax, eax
0x18000c689  jle     short loc_18000C690
0x18000c68b  movzx   ebx, ax
0x18000c68e  or      ebx, esi
0x18000c690  test    ebx, ebx
0x18000c692  js      short loc_18000C6F6
0x18000c694  mov     rcx, [rsp+260h+hKey]; hKey
0x18000c699  call    cs:__imp_RegCloseKey
0x18000c69f  lea     rax, [rsp+260h+hKey]
0x18000c6a4  mov     r9d, 2000000h; samDesired
0x18000c6aa  xor     r8d, r8d; ulOptions
0x18000c6ad  mov     [rsp+260h+phkResult], rax; phkResult
0x18000c6b2  lea     rdx, aClsid; "CLSID"
0x18000c6b9  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000c6c0  call    cs:__imp_RegOpenKeyExW
0x18000c6c6  mov     ebx, eax
0x18000c6c8  test    eax, eax
0x18000c6ca  jle     short loc_18000C6D1
0x18000c6cc  movzx   ebx, ax
0x18000c6cf  or      ebx, esi
0x18000c6d1  test    ebx, ebx
0x18000c6d3  js      short loc_18000C6F6
0x18000c6d5  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x18000c6da  xor     r9d, r9d; Reserved
0x18000c6dd  mov     rcx, [rsp+260h+hKey]; hKey
0x18000c6e2  xor     r8d, r8d; samDesired
0x18000c6e5  call    cs:__imp_RegDeleteKeyExW
0x18000c6eb  mov     ebx, eax
0x18000c6ed  test    eax, eax
0x18000c6ef  jle     short loc_18000C6F6
0x18000c6f1  movzx   ebx, ax
0x18000c6f4  or      ebx, esi
0x18000c6f6  mov     rcx, [rsp+260h+hKey]; hKey
0x18000c6fb  test    rcx, rcx
0x18000c6fe  jz      short loc_18000C70F
0x18000c700  call    cs:__imp_RegCloseKey
0x18000c706  mov     [rsp+260h+hKey], 0
0x18000c70f  mov     rcx, [rsp+260h+lpsz]; pv
0x18000c714  call    cs:__imp_CoTaskMemFree
0x18000c71a  mov     eax, ebx
0x18000c71c  mov     rcx, [rbp+160h+var_10]
0x18000c723  xor     rcx, rsp; StackCookie
0x18000c726  call    __security_check_cookie
0x18000c72b  lea     r11, [rsp+260h+var_s0]
0x18000c733  mov     rbx, [r11+10h]
0x18000c737  mov     rsi, [r11+18h]
0x18000c73b  mov     rsp, r11
0x18000c73e  pop     rbp
0x18000c73f  retn
```
