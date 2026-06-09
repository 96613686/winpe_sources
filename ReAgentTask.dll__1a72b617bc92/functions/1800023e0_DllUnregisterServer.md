# DllUnregisterServer

- ea: `0x1800023e0`
- end: `0x180002580`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002140`
- `0x1800023e0`
- `0x180002616`
- `0x180002650`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002554`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002554`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000243b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000243b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800024bf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002525`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800024bf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180002525`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000248f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002500`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000248f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002500`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800024d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002540`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800024d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002540`

## string_xrefs

- `0x180002450`: `CLSID\\%s`
- `0x1800024f2`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_ReAgentTaskHandler, &lpsz);
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
0x1800023e0  mov     [rsp-8+arg_0], rbx
0x1800023e5  mov     [rsp-8+arg_8], rsi
0x1800023ea  push    rbp
0x1800023eb  lea     rbp, [rsp-160h]
0x1800023f3  sub     rsp, 260h
0x1800023fa  mov     rax, cs:__security_cookie
0x180002401  xor     rax, rsp
0x180002404  mov     [rbp+160h+var_10], rax
0x18000240b  xor     edx, edx; Val
0x18000240d  mov     [rsp+260h+hKey], 0
0x180002416  mov     r8d, 208h; Size
0x18000241c  lea     rcx, [rsp+260h+SubKey]; void *
0x180002421  call    memset_0
0x180002426  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x18000242b  mov     [rsp+260h+lpsz], 0
0x180002434  lea     rcx, CLSID_ReAgentTaskHandler; rclsid
0x18000243b  call    cs:__imp_StringFromCLSID
0x180002441  mov     ebx, eax
0x180002443  test    eax, eax
0x180002445  js      loc_180002536
0x18000244b  mov     r9, [rsp+260h+lpsz]
0x180002450  lea     r8, aClsidS; "CLSID\\\\%s"
0x180002457  mov     edx, 104h; unsigned __int64
0x18000245c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180002461  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002466  mov     ebx, eax
0x180002468  test    eax, eax
0x18000246a  js      loc_180002536
0x180002470  lea     rax, [rsp+260h+hKey]
0x180002475  mov     r9d, 2000000h; samDesired
0x18000247b  xor     r8d, r8d; ulOptions
0x18000247e  mov     [rsp+260h+phkResult], rax; phkResult
0x180002483  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180002488  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000248f  call    cs:__imp_RegOpenKeyExW
0x180002495  mov     ebx, eax
0x180002497  mov     esi, 80070000h
0x18000249c  test    eax, eax
0x18000249e  jle     short loc_1800024A5
0x1800024a0  movzx   ebx, ax
0x1800024a3  or      ebx, esi
0x1800024a5  test    ebx, ebx
0x1800024a7  js      loc_180002536
0x1800024ad  mov     rcx, [rsp+260h+hKey]; hKey
0x1800024b2  lea     rdx, SubKey; "InprocServer32"
0x1800024b9  xor     r9d, r9d; Reserved
0x1800024bc  xor     r8d, r8d; samDesired
0x1800024bf  call    cs:__imp_RegDeleteKeyExW
0x1800024c5  mov     ebx, eax
0x1800024c7  test    eax, eax
0x1800024c9  jle     short loc_1800024D0
0x1800024cb  movzx   ebx, ax
0x1800024ce  or      ebx, esi
0x1800024d0  test    ebx, ebx
0x1800024d2  js      short loc_180002536
0x1800024d4  mov     rcx, [rsp+260h+hKey]; hKey
0x1800024d9  call    cs:__imp_RegCloseKey
0x1800024df  lea     rax, [rsp+260h+hKey]
0x1800024e4  mov     r9d, 2000000h; samDesired
0x1800024ea  xor     r8d, r8d; ulOptions
0x1800024ed  mov     [rsp+260h+phkResult], rax; phkResult
0x1800024f2  lea     rdx, aClsid; "CLSID"
0x1800024f9  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002500  call    cs:__imp_RegOpenKeyExW
0x180002506  mov     ebx, eax
0x180002508  test    eax, eax
0x18000250a  jle     short loc_180002511
0x18000250c  movzx   ebx, ax
0x18000250f  or      ebx, esi
0x180002511  test    ebx, ebx
0x180002513  js      short loc_180002536
0x180002515  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x18000251a  xor     r9d, r9d; Reserved
0x18000251d  mov     rcx, [rsp+260h+hKey]; hKey
0x180002522  xor     r8d, r8d; samDesired
0x180002525  call    cs:__imp_RegDeleteKeyExW
0x18000252b  mov     ebx, eax
0x18000252d  test    eax, eax
0x18000252f  jle     short loc_180002536
0x180002531  movzx   ebx, ax
0x180002534  or      ebx, esi
0x180002536  mov     rcx, [rsp+260h+hKey]; hKey
0x18000253b  test    rcx, rcx
0x18000253e  jz      short loc_18000254F
0x180002540  call    cs:__imp_RegCloseKey
0x180002546  mov     [rsp+260h+hKey], 0
0x18000254f  mov     rcx, [rsp+260h+lpsz]; pv
0x180002554  call    cs:__imp_CoTaskMemFree
0x18000255a  mov     eax, ebx
0x18000255c  mov     rcx, [rbp+160h+var_10]
0x180002563  xor     rcx, rsp; StackCookie
0x180002566  call    __security_check_cookie
0x18000256b  lea     r11, [rsp+260h+var_s0]
0x180002573  mov     rbx, [r11+10h]
0x180002577  mov     rsi, [r11+18h]
0x18000257b  mov     rsp, r11
0x18000257e  pop     rbp
0x18000257f  retn
```
