# DllUnregisterServer

- ea: `0x180007160`
- end: `0x180007300`
- name: `DllUnregisterServer`
- size: `416`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001c00`
- `0x180002648`
- `0x180006850`
- `0x180007160`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072d4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800071bb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800071bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800072c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800072c0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000723f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800072a5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000723f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800072a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000720f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007280`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000720f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007280`

## string_xrefs

- `0x1800071d0`: `CLSID\\%s`
- `0x180007272`: `CLSID`

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
  v0 = StringFromCLSID(&CLSID_ExploitGuardNotificationTask, &lpsz);
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
0x180007160  mov     [rsp-8+arg_0], rbx
0x180007165  mov     [rsp-8+arg_8], rsi
0x18000716a  push    rbp
0x18000716b  lea     rbp, [rsp-160h]
0x180007173  sub     rsp, 260h
0x18000717a  mov     rax, cs:__security_cookie
0x180007181  xor     rax, rsp
0x180007184  mov     [rbp+160h+var_10], rax
0x18000718b  xor     edx, edx; Val
0x18000718d  mov     [rsp+260h+hKey], 0
0x180007196  mov     r8d, 208h; Size
0x18000719c  lea     rcx, [rsp+260h+SubKey]; void *
0x1800071a1  call    memset_0
0x1800071a6  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x1800071ab  mov     [rsp+260h+lpsz], 0
0x1800071b4  lea     rcx, CLSID_ExploitGuardNotificationTask; rclsid
0x1800071bb  call    cs:__imp_StringFromCLSID
0x1800071c1  mov     ebx, eax
0x1800071c3  test    eax, eax
0x1800071c5  js      loc_1800072B6
0x1800071cb  mov     r9, [rsp+260h+lpsz]
0x1800071d0  lea     r8, aClsidS; "CLSID\\\\%s"
0x1800071d7  mov     edx, 104h; unsigned __int64
0x1800071dc  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x1800071e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800071e6  mov     ebx, eax
0x1800071e8  test    eax, eax
0x1800071ea  js      loc_1800072B6
0x1800071f0  lea     rax, [rsp+260h+hKey]
0x1800071f5  mov     r9d, 2000000h; samDesired
0x1800071fb  xor     r8d, r8d; ulOptions
0x1800071fe  mov     [rsp+260h+phkResult], rax; phkResult
0x180007203  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x180007208  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000720f  call    cs:__imp_RegOpenKeyExW
0x180007215  mov     ebx, eax
0x180007217  mov     esi, 80070000h
0x18000721c  test    eax, eax
0x18000721e  jle     short loc_180007225
0x180007220  movzx   ebx, ax
0x180007223  or      ebx, esi
0x180007225  test    ebx, ebx
0x180007227  js      loc_1800072B6
0x18000722d  mov     rcx, [rsp+260h+hKey]; hKey
0x180007232  lea     rdx, SubKey; "InprocServer32"
0x180007239  xor     r9d, r9d; Reserved
0x18000723c  xor     r8d, r8d; samDesired
0x18000723f  call    cs:__imp_RegDeleteKeyExW
0x180007245  mov     ebx, eax
0x180007247  test    eax, eax
0x180007249  jle     short loc_180007250
0x18000724b  movzx   ebx, ax
0x18000724e  or      ebx, esi
0x180007250  test    ebx, ebx
0x180007252  js      short loc_1800072B6
0x180007254  mov     rcx, [rsp+260h+hKey]; hKey
0x180007259  call    cs:__imp_RegCloseKey
0x18000725f  lea     rax, [rsp+260h+hKey]
0x180007264  mov     r9d, 2000000h; samDesired
0x18000726a  xor     r8d, r8d; ulOptions
0x18000726d  mov     [rsp+260h+phkResult], rax; phkResult
0x180007272  lea     rdx, aClsid; "CLSID"
0x180007279  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180007280  call    cs:__imp_RegOpenKeyExW
0x180007286  mov     ebx, eax
0x180007288  test    eax, eax
0x18000728a  jle     short loc_180007291
0x18000728c  movzx   ebx, ax
0x18000728f  or      ebx, esi
0x180007291  test    ebx, ebx
0x180007293  js      short loc_1800072B6
0x180007295  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x18000729a  xor     r9d, r9d; Reserved
0x18000729d  mov     rcx, [rsp+260h+hKey]; hKey
0x1800072a2  xor     r8d, r8d; samDesired
0x1800072a5  call    cs:__imp_RegDeleteKeyExW
0x1800072ab  mov     ebx, eax
0x1800072ad  test    eax, eax
0x1800072af  jle     short loc_1800072B6
0x1800072b1  movzx   ebx, ax
0x1800072b4  or      ebx, esi
0x1800072b6  mov     rcx, [rsp+260h+hKey]; hKey
0x1800072bb  test    rcx, rcx
0x1800072be  jz      short loc_1800072CF
0x1800072c0  call    cs:__imp_RegCloseKey
0x1800072c6  mov     [rsp+260h+hKey], 0
0x1800072cf  mov     rcx, [rsp+260h+lpsz]; pv
0x1800072d4  call    cs:__imp_CoTaskMemFree
0x1800072da  mov     eax, ebx
0x1800072dc  mov     rcx, [rbp+160h+var_10]
0x1800072e3  xor     rcx, rsp; StackCookie
0x1800072e6  call    __security_check_cookie
0x1800072eb  lea     r11, [rsp+260h+var_s0]
0x1800072f3  mov     rbx, [r11+10h]
0x1800072f7  mov     rsi, [r11+18h]
0x1800072fb  mov     rsp, r11
0x1800072fe  pop     rbp
0x1800072ff  retn
```
