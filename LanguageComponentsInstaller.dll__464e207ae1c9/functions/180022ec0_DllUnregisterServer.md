# DllUnregisterServer

- ea: `0x180022ec0`
- end: `0x180023060`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180004118`
- `0x180009c94`
- `0x180022ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180022f1b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180022f1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023034`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022f6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022fe0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022f6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022fe0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022fb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023020`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022fb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023020`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180022f9f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180023005`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180022f9f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180023005`

## string_xrefs

- `0x180022f30`: `CLSID\\%s`
- `0x180022fd2`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_LanguageComponentsInstaller, &lpsz);
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
0x180022ec0  mov     [rsp-8+arg_0], rbx
0x180022ec5  mov     [rsp-8+arg_8], rsi
0x180022eca  push    rbp
0x180022ecb  lea     rbp, [rsp-160h]
0x180022ed3  sub     rsp, 260h
0x180022eda  mov     rax, cs:__security_cookie
0x180022ee1  xor     rax, rsp
0x180022ee4  mov     [rbp+160h+var_10], rax
0x180022eeb  xor     edx, edx; Val
0x180022eed  mov     [rsp+260h+hKey], 0
0x180022ef6  mov     r8d, 208h; Size
0x180022efc  lea     rcx, [rsp+260h+SubKey]; void *
0x180022f01  call    memset_0
0x180022f06  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180022f0b  mov     [rsp+260h+lpsz], 0
0x180022f14  lea     rcx, CLSID_LanguageComponentsInstaller; rclsid
0x180022f1b  call    cs:__imp_StringFromCLSID
0x180022f21  mov     ebx, eax
0x180022f23  test    eax, eax
0x180022f25  js      loc_180023016
0x180022f2b  mov     r9, [rsp+260h+lpsz]
0x180022f30  lea     r8, aClsidS; "CLSID\\\\%s"
0x180022f37  mov     edx, 104h; unsigned __int64
0x180022f3c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180022f41  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022f46  mov     ebx, eax
0x180022f48  test    eax, eax
0x180022f4a  js      loc_180023016
0x180022f50  lea     rax, [rsp+260h+hKey]
0x180022f55  mov     r9d, 2000000h; samDesired
0x180022f5b  xor     r8d, r8d; ulOptions
0x180022f5e  mov     [rsp+260h+phkResult], rax; phkResult
0x180022f63  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180022f68  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180022f6f  call    cs:__imp_RegOpenKeyExW
0x180022f75  mov     ebx, eax
0x180022f77  mov     esi, 80070000h
0x180022f7c  test    eax, eax
0x180022f7e  jle     short loc_180022F85
0x180022f80  movzx   ebx, ax
0x180022f83  or      ebx, esi
0x180022f85  test    ebx, ebx
0x180022f87  js      loc_180023016
0x180022f8d  mov     rcx, [rsp+260h+hKey]; hKey
0x180022f92  lea     rdx, aInprocserver32; "InprocServer32"
0x180022f99  xor     r9d, r9d; Reserved
0x180022f9c  xor     r8d, r8d; samDesired
0x180022f9f  call    cs:__imp_RegDeleteKeyExW
0x180022fa5  mov     ebx, eax
0x180022fa7  test    eax, eax
0x180022fa9  jle     short loc_180022FB0
0x180022fab  movzx   ebx, ax
0x180022fae  or      ebx, esi
0x180022fb0  test    ebx, ebx
0x180022fb2  js      short loc_180023016
0x180022fb4  mov     rcx, [rsp+260h+hKey]; hKey
0x180022fb9  call    cs:__imp_RegCloseKey
0x180022fbf  lea     rax, [rsp+260h+hKey]
0x180022fc4  mov     r9d, 2000000h; samDesired
0x180022fca  xor     r8d, r8d; ulOptions
0x180022fcd  mov     [rsp+260h+phkResult], rax; phkResult
0x180022fd2  lea     rdx, aClsid; "CLSID"
0x180022fd9  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180022fe0  call    cs:__imp_RegOpenKeyExW
0x180022fe6  mov     ebx, eax
0x180022fe8  test    eax, eax
0x180022fea  jle     short loc_180022FF1
0x180022fec  movzx   ebx, ax
0x180022fef  or      ebx, esi
0x180022ff1  test    ebx, ebx
0x180022ff3  js      short loc_180023016
0x180022ff5  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180022ffa  xor     r9d, r9d; Reserved
0x180022ffd  mov     rcx, [rsp+260h+hKey]; hKey
0x180023002  xor     r8d, r8d; samDesired
0x180023005  call    cs:__imp_RegDeleteKeyExW
0x18002300b  mov     ebx, eax
0x18002300d  test    eax, eax
0x18002300f  jle     short loc_180023016
0x180023011  movzx   ebx, ax
0x180023014  or      ebx, esi
0x180023016  mov     rcx, [rsp+260h+hKey]; hKey
0x18002301b  test    rcx, rcx
0x18002301e  jz      short loc_18002302F
0x180023020  call    cs:__imp_RegCloseKey
0x180023026  mov     [rsp+260h+hKey], 0
0x18002302f  mov     rcx, [rsp+260h+lpsz]; pv
0x180023034  call    cs:__imp_CoTaskMemFree
0x18002303a  mov     eax, ebx
0x18002303c  mov     rcx, [rbp+160h+var_10]
0x180023043  xor     rcx, rsp; StackCookie
0x180023046  call    __security_check_cookie
0x18002304b  lea     r11, [rsp+260h+var_s0]
0x180023053  mov     rbx, [r11+10h]
0x180023057  mov     rsi, [r11+18h]
0x18002305b  mov     rsp, r11
0x18002305e  pop     rbp
0x18002305f  retn
```
