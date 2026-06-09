# DllUnregisterServer

- ea: `0x18000b780`
- end: `0x18000b920`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009480`
- `0x18000b780`
- `0x18000c5e2`
- `0x18000c610`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b8f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b8f4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000b7db`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000b7db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b82f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b8a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b82f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b8a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b879`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b8e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b879`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b8e0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000b85f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000b8c5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000b85f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000b8c5`

## string_xrefs

- `0x18000b892`: `CLSID`
- `0x18000b7f0`: `CLSID\\%s`

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
  v0 = StringFromCLSID(&CLSID_SetupRecoveryDataTask, &lpsz);
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
0x18000b780  mov     [rsp-8+arg_0], rbx
0x18000b785  mov     [rsp-8+arg_8], rsi
0x18000b78a  push    rbp
0x18000b78b  lea     rbp, [rsp-160h]
0x18000b793  sub     rsp, 260h
0x18000b79a  mov     rax, cs:__security_cookie
0x18000b7a1  xor     rax, rsp
0x18000b7a4  mov     [rbp+160h+var_10], rax
0x18000b7ab  xor     edx, edx; Val
0x18000b7ad  mov     [rsp+260h+hKey], 0
0x18000b7b6  mov     r8d, 208h; Size
0x18000b7bc  lea     rcx, [rsp+260h+SubKey]; void *
0x18000b7c1  call    memset_0
0x18000b7c6  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x18000b7cb  mov     [rsp+260h+lpsz], 0
0x18000b7d4  lea     rcx, CLSID_SetupRecoveryDataTask; rclsid
0x18000b7db  call    cs:__imp_StringFromCLSID
0x18000b7e1  mov     ebx, eax
0x18000b7e3  test    eax, eax
0x18000b7e5  js      loc_18000B8D6
0x18000b7eb  mov     r9, [rsp+260h+lpsz]
0x18000b7f0  lea     r8, aClsidS; "CLSID\\\\%s"
0x18000b7f7  mov     edx, 104h; unsigned __int64
0x18000b7fc  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x18000b801  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b806  mov     ebx, eax
0x18000b808  test    eax, eax
0x18000b80a  js      loc_18000B8D6
0x18000b810  lea     rax, [rsp+260h+hKey]
0x18000b815  mov     r9d, 2000000h; samDesired
0x18000b81b  xor     r8d, r8d; ulOptions
0x18000b81e  mov     [rsp+260h+phkResult], rax; phkResult
0x18000b823  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x18000b828  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000b82f  call    cs:__imp_RegOpenKeyExW
0x18000b835  mov     ebx, eax
0x18000b837  mov     esi, 80070000h
0x18000b83c  test    eax, eax
0x18000b83e  jle     short loc_18000B845
0x18000b840  movzx   ebx, ax
0x18000b843  or      ebx, esi
0x18000b845  test    ebx, ebx
0x18000b847  js      loc_18000B8D6
0x18000b84d  mov     rcx, [rsp+260h+hKey]; hKey
0x18000b852  lea     rdx, aInprocserver32; "InprocServer32"
0x18000b859  xor     r9d, r9d; Reserved
0x18000b85c  xor     r8d, r8d; samDesired
0x18000b85f  call    cs:__imp_RegDeleteKeyExW
0x18000b865  mov     ebx, eax
0x18000b867  test    eax, eax
0x18000b869  jle     short loc_18000B870
0x18000b86b  movzx   ebx, ax
0x18000b86e  or      ebx, esi
0x18000b870  test    ebx, ebx
0x18000b872  js      short loc_18000B8D6
0x18000b874  mov     rcx, [rsp+260h+hKey]; hKey
0x18000b879  call    cs:__imp_RegCloseKey
0x18000b87f  lea     rax, [rsp+260h+hKey]
0x18000b884  mov     r9d, 2000000h; samDesired
0x18000b88a  xor     r8d, r8d; ulOptions
0x18000b88d  mov     [rsp+260h+phkResult], rax; phkResult
0x18000b892  lea     rdx, aClsid; "CLSID"
0x18000b899  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000b8a0  call    cs:__imp_RegOpenKeyExW
0x18000b8a6  mov     ebx, eax
0x18000b8a8  test    eax, eax
0x18000b8aa  jle     short loc_18000B8B1
0x18000b8ac  movzx   ebx, ax
0x18000b8af  or      ebx, esi
0x18000b8b1  test    ebx, ebx
0x18000b8b3  js      short loc_18000B8D6
0x18000b8b5  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x18000b8ba  xor     r9d, r9d; Reserved
0x18000b8bd  mov     rcx, [rsp+260h+hKey]; hKey
0x18000b8c2  xor     r8d, r8d; samDesired
0x18000b8c5  call    cs:__imp_RegDeleteKeyExW
0x18000b8cb  mov     ebx, eax
0x18000b8cd  test    eax, eax
0x18000b8cf  jle     short loc_18000B8D6
0x18000b8d1  movzx   ebx, ax
0x18000b8d4  or      ebx, esi
0x18000b8d6  mov     rcx, [rsp+260h+hKey]; hKey
0x18000b8db  test    rcx, rcx
0x18000b8de  jz      short loc_18000B8EF
0x18000b8e0  call    cs:__imp_RegCloseKey
0x18000b8e6  mov     [rsp+260h+hKey], 0
0x18000b8ef  mov     rcx, [rsp+260h+lpsz]; pv
0x18000b8f4  call    cs:__imp_CoTaskMemFree
0x18000b8fa  mov     eax, ebx
0x18000b8fc  mov     rcx, [rbp+160h+var_10]
0x18000b903  xor     rcx, rsp; StackCookie
0x18000b906  call    __security_check_cookie
0x18000b90b  lea     r11, [rsp+260h+var_s0]
0x18000b913  mov     rbx, [r11+10h]
0x18000b917  mov     rsi, [r11+18h]
0x18000b91b  mov     rsp, r11
0x18000b91e  pop     rbp
0x18000b91f  retn
```
