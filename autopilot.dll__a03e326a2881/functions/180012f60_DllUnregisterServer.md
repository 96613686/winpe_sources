# DllUnregisterServer

- ea: `0x180012f60`
- end: `0x180013100`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x180011224`
- `0x180012f60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800130d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800130d4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180012fbb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180012fbb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001300f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013080`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001300f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013080`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013059`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800130c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013059`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800130c0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001303f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800130a5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001303f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800130a5`

## string_xrefs

- `0x180012fd0`: `CLSID\\%s`
- `0x180013072`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_DetectHardwareChange, &lpsz);
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
0x180012f60  mov     [rsp-8+arg_0], rbx
0x180012f65  mov     [rsp-8+arg_8], rsi
0x180012f6a  push    rbp
0x180012f6b  lea     rbp, [rsp-160h]
0x180012f73  sub     rsp, 260h
0x180012f7a  mov     rax, cs:__security_cookie
0x180012f81  xor     rax, rsp
0x180012f84  mov     [rbp+160h+var_10], rax
0x180012f8b  xor     edx, edx; Val
0x180012f8d  mov     [rsp+260h+hKey], 0
0x180012f96  mov     r8d, 208h; Size
0x180012f9c  lea     rcx, [rsp+260h+SubKey]; void *
0x180012fa1  call    memset_0
0x180012fa6  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x180012fab  mov     [rsp+260h+lpsz], 0
0x180012fb4  lea     rcx, CLSID_DetectHardwareChange; rclsid
0x180012fbb  call    cs:__imp_StringFromCLSID
0x180012fc1  mov     ebx, eax
0x180012fc3  test    eax, eax
0x180012fc5  js      loc_1800130B6
0x180012fcb  mov     r9, [rsp+260h+lpsz]
0x180012fd0  lea     r8, aClsidS; "CLSID\\\\%s"
0x180012fd7  mov     edx, 104h; unsigned __int64
0x180012fdc  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180012fe1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012fe6  mov     ebx, eax
0x180012fe8  test    eax, eax
0x180012fea  js      loc_1800130B6
0x180012ff0  lea     rax, [rsp+260h+hKey]
0x180012ff5  mov     r9d, 2000000h; samDesired
0x180012ffb  xor     r8d, r8d; ulOptions
0x180012ffe  mov     [rsp+260h+phkResult], rax; phkResult
0x180013003  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180013008  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001300f  call    cs:__imp_RegOpenKeyExW
0x180013015  mov     ebx, eax
0x180013017  mov     esi, 80070000h
0x18001301c  test    eax, eax
0x18001301e  jle     short loc_180013025
0x180013020  movzx   ebx, ax
0x180013023  or      ebx, esi
0x180013025  test    ebx, ebx
0x180013027  js      loc_1800130B6
0x18001302d  mov     rcx, [rsp+260h+hKey]; hKey
0x180013032  lea     rdx, aInprocserver32; "InprocServer32"
0x180013039  xor     r9d, r9d; Reserved
0x18001303c  xor     r8d, r8d; samDesired
0x18001303f  call    cs:__imp_RegDeleteKeyExW
0x180013045  mov     ebx, eax
0x180013047  test    eax, eax
0x180013049  jle     short loc_180013050
0x18001304b  movzx   ebx, ax
0x18001304e  or      ebx, esi
0x180013050  test    ebx, ebx
0x180013052  js      short loc_1800130B6
0x180013054  mov     rcx, [rsp+260h+hKey]; hKey
0x180013059  call    cs:__imp_RegCloseKey
0x18001305f  lea     rax, [rsp+260h+hKey]
0x180013064  mov     r9d, 2000000h; samDesired
0x18001306a  xor     r8d, r8d; ulOptions
0x18001306d  mov     [rsp+260h+phkResult], rax; phkResult
0x180013072  lea     rdx, aClsid; "CLSID"
0x180013079  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180013080  call    cs:__imp_RegOpenKeyExW
0x180013086  mov     ebx, eax
0x180013088  test    eax, eax
0x18001308a  jle     short loc_180013091
0x18001308c  movzx   ebx, ax
0x18001308f  or      ebx, esi
0x180013091  test    ebx, ebx
0x180013093  js      short loc_1800130B6
0x180013095  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x18001309a  xor     r9d, r9d; Reserved
0x18001309d  mov     rcx, [rsp+260h+hKey]; hKey
0x1800130a2  xor     r8d, r8d; samDesired
0x1800130a5  call    cs:__imp_RegDeleteKeyExW
0x1800130ab  mov     ebx, eax
0x1800130ad  test    eax, eax
0x1800130af  jle     short loc_1800130B6
0x1800130b1  movzx   ebx, ax
0x1800130b4  or      ebx, esi
0x1800130b6  mov     rcx, [rsp+260h+hKey]; hKey
0x1800130bb  test    rcx, rcx
0x1800130be  jz      short loc_1800130CF
0x1800130c0  call    cs:__imp_RegCloseKey
0x1800130c6  mov     [rsp+260h+hKey], 0
0x1800130cf  mov     rcx, [rsp+260h+lpsz]; pv
0x1800130d4  call    cs:__imp_CoTaskMemFree
0x1800130da  mov     eax, ebx
0x1800130dc  mov     rcx, [rbp+160h+var_10]
0x1800130e3  xor     rcx, rsp; StackCookie
0x1800130e6  call    __security_check_cookie
0x1800130eb  lea     r11, [rsp+260h+var_s0]
0x1800130f3  mov     rbx, [r11+10h]
0x1800130f7  mov     rsi, [r11+18h]
0x1800130fb  mov     rsp, r11
0x1800130fe  pop     rbp
0x1800130ff  retn
```
