# DllUnregisterServer

- ea: `0x18000c750`
- end: `0x18000c8f0`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009758`
- `0x18000c750`
- `0x180010792`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c8c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c8c4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000c7ab`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000c7ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c849`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c8b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c849`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c8b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c7ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c870`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c7ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c870`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000c82f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000c895`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000c82f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000c895`

## string_xrefs

- `0x18000c862`: `CLSID`
- `0x18000c7c0`: `CLSID\\%s`

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
  v0 = StringFromCLSID(&CLSID_PITRTask, &lpsz);
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
0x18000c750  mov     [rsp-8+arg_0], rbx
0x18000c755  mov     [rsp-8+arg_8], rsi
0x18000c75a  push    rbp
0x18000c75b  lea     rbp, [rsp-160h]
0x18000c763  sub     rsp, 260h
0x18000c76a  mov     rax, cs:__security_cookie
0x18000c771  xor     rax, rsp
0x18000c774  mov     [rbp+160h+var_10], rax
0x18000c77b  xor     edx, edx; Val
0x18000c77d  mov     [rsp+260h+hKey], 0
0x18000c786  mov     r8d, 208h; Size
0x18000c78c  lea     rcx, [rsp+260h+SubKey]; void *
0x18000c791  call    memset_0
0x18000c796  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x18000c79b  mov     [rsp+260h+lpsz], 0
0x18000c7a4  lea     rcx, CLSID_PITRTask; rclsid
0x18000c7ab  call    cs:__imp_StringFromCLSID
0x18000c7b1  mov     ebx, eax
0x18000c7b3  test    eax, eax
0x18000c7b5  js      loc_18000C8A6
0x18000c7bb  mov     r9, [rsp+260h+lpsz]
0x18000c7c0  lea     r8, aClsidS; "CLSID\\\\%s"
0x18000c7c7  mov     edx, 104h; unsigned __int64
0x18000c7cc  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000c7d1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c7d6  mov     ebx, eax
0x18000c7d8  test    eax, eax
0x18000c7da  js      loc_18000C8A6
0x18000c7e0  lea     rax, [rsp+260h+hKey]
0x18000c7e5  mov     r9d, 2000000h; samDesired
0x18000c7eb  xor     r8d, r8d; ulOptions
0x18000c7ee  mov     [rsp+260h+phkResult], rax; phkResult
0x18000c7f3  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x18000c7f8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000c7ff  call    cs:__imp_RegOpenKeyExW
0x18000c805  mov     ebx, eax
0x18000c807  mov     esi, 80070000h
0x18000c80c  test    eax, eax
0x18000c80e  jle     short loc_18000C815
0x18000c810  movzx   ebx, ax
0x18000c813  or      ebx, esi
0x18000c815  test    ebx, ebx
0x18000c817  js      loc_18000C8A6
0x18000c81d  mov     rcx, [rsp+260h+hKey]; hKey
0x18000c822  lea     rdx, SubKey; "InprocServer32"
0x18000c829  xor     r9d, r9d; Reserved
0x18000c82c  xor     r8d, r8d; samDesired
0x18000c82f  call    cs:__imp_RegDeleteKeyExW
0x18000c835  mov     ebx, eax
0x18000c837  test    eax, eax
0x18000c839  jle     short loc_18000C840
0x18000c83b  movzx   ebx, ax
0x18000c83e  or      ebx, esi
0x18000c840  test    ebx, ebx
0x18000c842  js      short loc_18000C8A6
0x18000c844  mov     rcx, [rsp+260h+hKey]; hKey
0x18000c849  call    cs:__imp_RegCloseKey
0x18000c84f  lea     rax, [rsp+260h+hKey]
0x18000c854  mov     r9d, 2000000h; samDesired
0x18000c85a  xor     r8d, r8d; ulOptions
0x18000c85d  mov     [rsp+260h+phkResult], rax; phkResult
0x18000c862  lea     rdx, aClsid; "CLSID"
0x18000c869  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000c870  call    cs:__imp_RegOpenKeyExW
0x18000c876  mov     ebx, eax
0x18000c878  test    eax, eax
0x18000c87a  jle     short loc_18000C881
0x18000c87c  movzx   ebx, ax
0x18000c87f  or      ebx, esi
0x18000c881  test    ebx, ebx
0x18000c883  js      short loc_18000C8A6
0x18000c885  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x18000c88a  xor     r9d, r9d; Reserved
0x18000c88d  mov     rcx, [rsp+260h+hKey]; hKey
0x18000c892  xor     r8d, r8d; samDesired
0x18000c895  call    cs:__imp_RegDeleteKeyExW
0x18000c89b  mov     ebx, eax
0x18000c89d  test    eax, eax
0x18000c89f  jle     short loc_18000C8A6
0x18000c8a1  movzx   ebx, ax
0x18000c8a4  or      ebx, esi
0x18000c8a6  mov     rcx, [rsp+260h+hKey]; hKey
0x18000c8ab  test    rcx, rcx
0x18000c8ae  jz      short loc_18000C8BF
0x18000c8b0  call    cs:__imp_RegCloseKey
0x18000c8b6  mov     [rsp+260h+hKey], 0
0x18000c8bf  mov     rcx, [rsp+260h+lpsz]; pv
0x18000c8c4  call    cs:__imp_CoTaskMemFree
0x18000c8ca  mov     eax, ebx
0x18000c8cc  mov     rcx, [rbp+160h+var_10]
0x18000c8d3  xor     rcx, rsp; StackCookie
0x18000c8d6  call    __security_check_cookie
0x18000c8db  lea     r11, [rsp+260h+var_s0]
0x18000c8e3  mov     rbx, [r11+10h]
0x18000c8e7  mov     rsi, [r11+18h]
0x18000c8eb  mov     rsp, r11
0x18000c8ee  pop     rbp
0x18000c8ef  retn
```
