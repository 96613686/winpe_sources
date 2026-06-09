# DllUnregisterServer

- ea: `0x180003ac0`
- end: `0x180003c60`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003850`
- `0x180003ac0`
- `0x1800322d2`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003c34`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003b1b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003b1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003be0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003b6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003be0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180003b9f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180003c05`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180003b9f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180003c05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003bb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003c20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003bb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003c20`

## string_xrefs

- `0x180003bd2`: `CLSID`
- `0x180003b30`: `CLSID\\%s`

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
  v0 = StringFromCLSID(&CLSID_SetupCleanupTask, &lpsz);
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
0x180003ac0  mov     [rsp-8+arg_0], rbx
0x180003ac5  mov     [rsp-8+arg_8], rsi
0x180003aca  push    rbp
0x180003acb  lea     rbp, [rsp-160h]
0x180003ad3  sub     rsp, 260h
0x180003ada  mov     rax, cs:__security_cookie
0x180003ae1  xor     rax, rsp
0x180003ae4  mov     [rbp+160h+var_10], rax
0x180003aeb  xor     edx, edx; Val
0x180003aed  mov     [rsp+260h+hKey], 0
0x180003af6  mov     r8d, 208h; Size
0x180003afc  lea     rcx, [rsp+260h+SubKey]; void *
0x180003b01  call    memset_0
0x180003b06  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180003b0b  mov     [rsp+260h+lpsz], 0
0x180003b14  lea     rcx, CLSID_SetupCleanupTask; rclsid
0x180003b1b  call    cs:__imp_StringFromCLSID
0x180003b21  mov     ebx, eax
0x180003b23  test    eax, eax
0x180003b25  js      loc_180003C16
0x180003b2b  mov     r9, [rsp+260h+lpsz]
0x180003b30  lea     r8, aClsidS; "CLSID\\\\%s"
0x180003b37  mov     edx, 104h; unsigned __int64
0x180003b3c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180003b41  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003b46  mov     ebx, eax
0x180003b48  test    eax, eax
0x180003b4a  js      loc_180003C16
0x180003b50  lea     rax, [rsp+260h+hKey]
0x180003b55  mov     r9d, 2000000h; samDesired
0x180003b5b  xor     r8d, r8d; ulOptions
0x180003b5e  mov     [rsp+260h+phkResult], rax; phkResult
0x180003b63  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180003b68  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180003b6f  call    cs:__imp_RegOpenKeyExW
0x180003b75  mov     ebx, eax
0x180003b77  mov     esi, 80070000h
0x180003b7c  test    eax, eax
0x180003b7e  jle     short loc_180003B85
0x180003b80  movzx   ebx, ax
0x180003b83  or      ebx, esi
0x180003b85  test    ebx, ebx
0x180003b87  js      loc_180003C16
0x180003b8d  mov     rcx, [rsp+260h+hKey]; hKey
0x180003b92  lea     rdx, SubKey; "InprocServer32"
0x180003b99  xor     r9d, r9d; Reserved
0x180003b9c  xor     r8d, r8d; samDesired
0x180003b9f  call    cs:__imp_RegDeleteKeyExW
0x180003ba5  mov     ebx, eax
0x180003ba7  test    eax, eax
0x180003ba9  jle     short loc_180003BB0
0x180003bab  movzx   ebx, ax
0x180003bae  or      ebx, esi
0x180003bb0  test    ebx, ebx
0x180003bb2  js      short loc_180003C16
0x180003bb4  mov     rcx, [rsp+260h+hKey]; hKey
0x180003bb9  call    cs:__imp_RegCloseKey
0x180003bbf  lea     rax, [rsp+260h+hKey]
0x180003bc4  mov     r9d, 2000000h; samDesired
0x180003bca  xor     r8d, r8d; ulOptions
0x180003bcd  mov     [rsp+260h+phkResult], rax; phkResult
0x180003bd2  lea     rdx, aClsid; "CLSID"
0x180003bd9  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180003be0  call    cs:__imp_RegOpenKeyExW
0x180003be6  mov     ebx, eax
0x180003be8  test    eax, eax
0x180003bea  jle     short loc_180003BF1
0x180003bec  movzx   ebx, ax
0x180003bef  or      ebx, esi
0x180003bf1  test    ebx, ebx
0x180003bf3  js      short loc_180003C16
0x180003bf5  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180003bfa  xor     r9d, r9d; Reserved
0x180003bfd  mov     rcx, [rsp+260h+hKey]; hKey
0x180003c02  xor     r8d, r8d; samDesired
0x180003c05  call    cs:__imp_RegDeleteKeyExW
0x180003c0b  mov     ebx, eax
0x180003c0d  test    eax, eax
0x180003c0f  jle     short loc_180003C16
0x180003c11  movzx   ebx, ax
0x180003c14  or      ebx, esi
0x180003c16  mov     rcx, [rsp+260h+hKey]; hKey
0x180003c1b  test    rcx, rcx
0x180003c1e  jz      short loc_180003C2F
0x180003c20  call    cs:__imp_RegCloseKey
0x180003c26  mov     [rsp+260h+hKey], 0
0x180003c2f  mov     rcx, [rsp+260h+lpsz]; pv
0x180003c34  call    cs:__imp_CoTaskMemFree
0x180003c3a  mov     eax, ebx
0x180003c3c  mov     rcx, [rbp+160h+var_10]
0x180003c43  xor     rcx, rsp; StackCookie
0x180003c46  call    __security_check_cookie
0x180003c4b  lea     r11, [rsp+260h+var_s0]
0x180003c53  mov     rbx, [r11+10h]
0x180003c57  mov     rsi, [r11+18h]
0x180003c5b  mov     rsp, r11
0x180003c5e  pop     rbp
0x180003c5f  retn
```
