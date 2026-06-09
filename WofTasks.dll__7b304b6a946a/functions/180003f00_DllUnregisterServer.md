# DllUnregisterServer

- ea: `0x180003f00`
- end: `0x1800040a0`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003850`
- `0x180003f00`
- `0x18000518e`
- `0x1800051c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003f5b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003f5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004074`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004074`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003faf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004020`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003faf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004020`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ff9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004060`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ff9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004060`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180003fdf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180004045`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180003fdf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180004045`

## string_xrefs

- `0x180003f70`: `CLSID\\%s`
- `0x180004012`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_WofTasks, &lpsz);
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
0x180003f00  mov     [rsp-8+arg_0], rbx
0x180003f05  mov     [rsp-8+arg_8], rsi
0x180003f0a  push    rbp
0x180003f0b  lea     rbp, [rsp-160h]
0x180003f13  sub     rsp, 260h
0x180003f1a  mov     rax, cs:__security_cookie
0x180003f21  xor     rax, rsp
0x180003f24  mov     [rbp+160h+var_10], rax
0x180003f2b  xor     edx, edx; Val
0x180003f2d  mov     [rsp+260h+hKey], 0
0x180003f36  mov     r8d, 208h; Size
0x180003f3c  lea     rcx, [rsp+260h+SubKey]; void *
0x180003f41  call    memset_0
0x180003f46  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180003f4b  mov     [rsp+260h+lpsz], 0
0x180003f54  lea     rcx, CLSID_WofTasks; rclsid
0x180003f5b  call    cs:__imp_StringFromCLSID
0x180003f61  mov     ebx, eax
0x180003f63  test    eax, eax
0x180003f65  js      loc_180004056
0x180003f6b  mov     r9, [rsp+260h+lpsz]
0x180003f70  lea     r8, aClsidS; "CLSID\\\\%s"
0x180003f77  mov     edx, 104h; unsigned __int64
0x180003f7c  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180003f81  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003f86  mov     ebx, eax
0x180003f88  test    eax, eax
0x180003f8a  js      loc_180004056
0x180003f90  lea     rax, [rsp+260h+hKey]
0x180003f95  mov     r9d, 2000000h; samDesired
0x180003f9b  xor     r8d, r8d; ulOptions
0x180003f9e  mov     [rsp+260h+phkResult], rax; phkResult
0x180003fa3  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180003fa8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180003faf  call    cs:__imp_RegOpenKeyExW
0x180003fb5  mov     ebx, eax
0x180003fb7  mov     esi, 80070000h
0x180003fbc  test    eax, eax
0x180003fbe  jle     short loc_180003FC5
0x180003fc0  movzx   ebx, ax
0x180003fc3  or      ebx, esi
0x180003fc5  test    ebx, ebx
0x180003fc7  js      loc_180004056
0x180003fcd  mov     rcx, [rsp+260h+hKey]; hKey
0x180003fd2  lea     rdx, aInprocserver32; "InprocServer32"
0x180003fd9  xor     r9d, r9d; Reserved
0x180003fdc  xor     r8d, r8d; samDesired
0x180003fdf  call    cs:__imp_RegDeleteKeyExW
0x180003fe5  mov     ebx, eax
0x180003fe7  test    eax, eax
0x180003fe9  jle     short loc_180003FF0
0x180003feb  movzx   ebx, ax
0x180003fee  or      ebx, esi
0x180003ff0  test    ebx, ebx
0x180003ff2  js      short loc_180004056
0x180003ff4  mov     rcx, [rsp+260h+hKey]; hKey
0x180003ff9  call    cs:__imp_RegCloseKey
0x180003fff  lea     rax, [rsp+260h+hKey]
0x180004004  mov     r9d, 2000000h; samDesired
0x18000400a  xor     r8d, r8d; ulOptions
0x18000400d  mov     [rsp+260h+phkResult], rax; phkResult
0x180004012  lea     rdx, aClsid; "CLSID"
0x180004019  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180004020  call    cs:__imp_RegOpenKeyExW
0x180004026  mov     ebx, eax
0x180004028  test    eax, eax
0x18000402a  jle     short loc_180004031
0x18000402c  movzx   ebx, ax
0x18000402f  or      ebx, esi
0x180004031  test    ebx, ebx
0x180004033  js      short loc_180004056
0x180004035  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x18000403a  xor     r9d, r9d; Reserved
0x18000403d  mov     rcx, [rsp+260h+hKey]; hKey
0x180004042  xor     r8d, r8d; samDesired
0x180004045  call    cs:__imp_RegDeleteKeyExW
0x18000404b  mov     ebx, eax
0x18000404d  test    eax, eax
0x18000404f  jle     short loc_180004056
0x180004051  movzx   ebx, ax
0x180004054  or      ebx, esi
0x180004056  mov     rcx, [rsp+260h+hKey]; hKey
0x18000405b  test    rcx, rcx
0x18000405e  jz      short loc_18000406F
0x180004060  call    cs:__imp_RegCloseKey
0x180004066  mov     [rsp+260h+hKey], 0
0x18000406f  mov     rcx, [rsp+260h+lpsz]; pv
0x180004074  call    cs:__imp_CoTaskMemFree
0x18000407a  mov     eax, ebx
0x18000407c  mov     rcx, [rbp+160h+var_10]
0x180004083  xor     rcx, rsp; StackCookie
0x180004086  call    __security_check_cookie
0x18000408b  lea     r11, [rsp+260h+var_s0]
0x180004093  mov     rbx, [r11+10h]
0x180004097  mov     rsi, [r11+18h]
0x18000409b  mov     rsp, r11
0x18000409e  pop     rbp
0x18000409f  retn
```
