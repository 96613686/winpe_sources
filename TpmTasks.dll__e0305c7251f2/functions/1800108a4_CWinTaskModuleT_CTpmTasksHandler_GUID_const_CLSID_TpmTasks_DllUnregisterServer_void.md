# CWinTaskModuleT<CTpmTasksHandler,&_GUID const CLSID_TpmTasks>::DllUnregisterServer(void)

- ea: `0x1800108a4`
- end: `0x180010a44`
- name: `?DllUnregisterServer@?$CWinTaskModuleT@VCTpmTasksHandler@@$1?CLSID_TpmTasks@@3U_GUID@@B@@QEAAJXZ`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025490`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x1800108a4`
- `0x18001be20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001099d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001099d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a04`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180010983`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800109e9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180010983`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800109e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010953`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800109c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010953`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800109c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010a18`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800108ff`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800108ff`

## string_xrefs

- `0x1800109b6`: `CLSID`
- `0x180010914`: `CLSID\\%s`

## pseudocode

```c
__int64 CWinTaskModuleT<CTpmTasksHandler,&_GUID const CLSID_TpmTasks>::DllUnregisterServer()
{
  int v0; // ebx
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
  v0 = StringFromCLSID(&CLSID_TpmTasks, &lpsz);
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
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800108a4  mov     [rsp-8+arg_0], rbx
0x1800108a9  mov     [rsp-8+arg_8], rsi
0x1800108ae  push    rbp
0x1800108af  lea     rbp, [rsp-160h]
0x1800108b7  sub     rsp, 260h
0x1800108be  mov     rax, cs:__security_cookie
0x1800108c5  xor     rax, rsp
0x1800108c8  mov     [rbp+160h+var_10], rax
0x1800108cf  xor     edx, edx; Val
0x1800108d1  mov     [rsp+260h+hKey], 0
0x1800108da  mov     r8d, 208h; Size
0x1800108e0  lea     rcx, [rsp+260h+SubKey]; void *
0x1800108e5  call    memset_0
0x1800108ea  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x1800108ef  mov     [rsp+260h+lpsz], 0
0x1800108f8  lea     rcx, CLSID_TpmTasks; rclsid
0x1800108ff  call    cs:__imp_StringFromCLSID
0x180010905  mov     ebx, eax
0x180010907  test    eax, eax
0x180010909  js      loc_1800109FA
0x18001090f  mov     r9, [rsp+260h+lpsz]
0x180010914  lea     r8, aClsidS; "CLSID\\\\%s"
0x18001091b  mov     edx, 104h; unsigned __int64
0x180010920  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180010925  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001092a  mov     ebx, eax
0x18001092c  test    eax, eax
0x18001092e  js      loc_1800109FA
0x180010934  lea     rax, [rsp+260h+hKey]
0x180010939  mov     r9d, 2000000h; samDesired
0x18001093f  xor     r8d, r8d; ulOptions
0x180010942  mov     [rsp+260h+phkResult], rax; phkResult
0x180010947  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x18001094c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180010953  call    cs:__imp_RegOpenKeyExW
0x180010959  mov     ebx, eax
0x18001095b  mov     esi, 80070000h
0x180010960  test    eax, eax
0x180010962  jle     short loc_180010969
0x180010964  movzx   ebx, ax
0x180010967  or      ebx, esi
0x180010969  test    ebx, ebx
0x18001096b  js      loc_1800109FA
0x180010971  mov     rcx, [rsp+260h+hKey]; hKey
0x180010976  lea     rdx, SubKey; "InprocServer32"
0x18001097d  xor     r9d, r9d; Reserved
0x180010980  xor     r8d, r8d; samDesired
0x180010983  call    cs:__imp_RegDeleteKeyExW
0x180010989  mov     ebx, eax
0x18001098b  test    eax, eax
0x18001098d  jle     short loc_180010994
0x18001098f  movzx   ebx, ax
0x180010992  or      ebx, esi
0x180010994  test    ebx, ebx
0x180010996  js      short loc_1800109FA
0x180010998  mov     rcx, [rsp+260h+hKey]; hKey
0x18001099d  call    cs:__imp_RegCloseKey
0x1800109a3  lea     rax, [rsp+260h+hKey]
0x1800109a8  mov     r9d, 2000000h; samDesired
0x1800109ae  xor     r8d, r8d; ulOptions
0x1800109b1  mov     [rsp+260h+phkResult], rax; phkResult
0x1800109b6  lea     rdx, aClsid; "CLSID"
0x1800109bd  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800109c4  call    cs:__imp_RegOpenKeyExW
0x1800109ca  mov     ebx, eax
0x1800109cc  test    eax, eax
0x1800109ce  jle     short loc_1800109D5
0x1800109d0  movzx   ebx, ax
0x1800109d3  or      ebx, esi
0x1800109d5  test    ebx, ebx
0x1800109d7  js      short loc_1800109FA
0x1800109d9  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x1800109de  xor     r9d, r9d; Reserved
0x1800109e1  mov     rcx, [rsp+260h+hKey]; hKey
0x1800109e6  xor     r8d, r8d; samDesired
0x1800109e9  call    cs:__imp_RegDeleteKeyExW
0x1800109ef  mov     ebx, eax
0x1800109f1  test    eax, eax
0x1800109f3  jle     short loc_1800109FA
0x1800109f5  movzx   ebx, ax
0x1800109f8  or      ebx, esi
0x1800109fa  mov     rcx, [rsp+260h+hKey]; hKey
0x1800109ff  test    rcx, rcx
0x180010a02  jz      short loc_180010A13
0x180010a04  call    cs:__imp_RegCloseKey
0x180010a0a  mov     [rsp+260h+hKey], 0
0x180010a13  mov     rcx, [rsp+260h+lpsz]; pv
0x180010a18  call    cs:__imp_CoTaskMemFree
0x180010a1e  mov     eax, ebx
0x180010a20  mov     rcx, [rbp+160h+var_10]
0x180010a27  xor     rcx, rsp; StackCookie
0x180010a2a  call    __security_check_cookie
0x180010a2f  lea     r11, [rsp+260h+var_s0]
0x180010a37  mov     rbx, [r11+10h]
0x180010a3b  mov     rsi, [r11+18h]
0x180010a3f  mov     rsp, r11
0x180010a42  pop     rbp
0x180010a43  retn
```
