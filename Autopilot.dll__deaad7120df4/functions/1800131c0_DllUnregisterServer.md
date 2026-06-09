# DllUnregisterServer

- ea: `0x1800131c0`
- end: `0x180013391`
- name: `DllUnregisterServer`
- size: `465`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800045d0`
- `0x1800053c4`
- `0x180011220`
- `0x1800131c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001335e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001335e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001321b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001321b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013275`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800132f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013275`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800132f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800132cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013344`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800132cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013344`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800132ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180013323`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800132ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180013323`

## string_xrefs

- `0x180013236`: `CLSID\\%s`
- `0x1800132ea`: `CLSID`

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
0x1800131c0  mov     [rsp-8+arg_0], rbx
0x1800131c5  mov     [rsp-8+arg_8], rsi
0x1800131ca  push    rbp
0x1800131cb  lea     rbp, [rsp-160h]
0x1800131d3  sub     rsp, 260h
0x1800131da  mov     rax, cs:__security_cookie
0x1800131e1  xor     rax, rsp
0x1800131e4  mov     [rbp+160h+var_10], rax
0x1800131eb  xor     edx, edx; Val
0x1800131ed  mov     [rsp+260h+hKey], 0
0x1800131f6  mov     r8d, 208h; Size
0x1800131fc  lea     rcx, [rsp+260h+SubKey]; void *
0x180013201  call    memset_0
0x180013206  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x18001320b  mov     [rsp+260h+lpsz], 0
0x180013214  lea     rcx, CLSID_DetectHardwareChange; rclsid
0x18001321b  call    cs:__imp_StringFromCLSID
0x180013222  nop     dword ptr [rax+rax+00h]
0x180013227  mov     ebx, eax
0x180013229  test    eax, eax
0x18001322b  js      loc_18001333A
0x180013231  mov     r9, [rsp+260h+lpsz]
0x180013236  lea     r8, aClsidS; "CLSID\\\\%s"
0x18001323d  mov     edx, 104h; unsigned __int64
0x180013242  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180013247  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001324c  mov     ebx, eax
0x18001324e  test    eax, eax
0x180013250  js      loc_18001333A
0x180013256  lea     rax, [rsp+260h+hKey]
0x18001325b  mov     r9d, 2000000h; samDesired
0x180013261  xor     r8d, r8d; ulOptions
0x180013264  mov     [rsp+260h+phkResult], rax; phkResult
0x180013269  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x18001326e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180013275  call    cs:__imp_RegOpenKeyExW
0x18001327c  nop     dword ptr [rax+rax+00h]
0x180013281  mov     ebx, eax
0x180013283  mov     esi, 80070000h
0x180013288  test    eax, eax
0x18001328a  jle     short loc_180013291
0x18001328c  movzx   ebx, ax
0x18001328f  or      ebx, esi
0x180013291  test    ebx, ebx
0x180013293  js      loc_18001333A
0x180013299  mov     rcx, [rsp+260h+hKey]; hKey
0x18001329e  lea     rdx, aInprocserver32; "InprocServer32"
0x1800132a5  xor     r9d, r9d; Reserved
0x1800132a8  xor     r8d, r8d; samDesired
0x1800132ab  call    cs:__imp_RegDeleteKeyExW
0x1800132b2  nop     dword ptr [rax+rax+00h]
0x1800132b7  mov     ebx, eax
0x1800132b9  test    eax, eax
0x1800132bb  jle     short loc_1800132C2
0x1800132bd  movzx   ebx, ax
0x1800132c0  or      ebx, esi
0x1800132c2  test    ebx, ebx
0x1800132c4  js      short loc_18001333A
0x1800132c6  mov     rcx, [rsp+260h+hKey]; hKey
0x1800132cb  call    cs:__imp_RegCloseKey
0x1800132d2  nop     dword ptr [rax+rax+00h]
0x1800132d7  lea     rax, [rsp+260h+hKey]
0x1800132dc  mov     r9d, 2000000h; samDesired
0x1800132e2  xor     r8d, r8d; ulOptions
0x1800132e5  mov     [rsp+260h+phkResult], rax; phkResult
0x1800132ea  lea     rdx, aClsid; "CLSID"
0x1800132f1  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800132f8  call    cs:__imp_RegOpenKeyExW
0x1800132ff  nop     dword ptr [rax+rax+00h]
0x180013304  mov     ebx, eax
0x180013306  test    eax, eax
0x180013308  jle     short loc_18001330F
0x18001330a  movzx   ebx, ax
0x18001330d  or      ebx, esi
0x18001330f  test    ebx, ebx
0x180013311  js      short loc_18001333A
0x180013313  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x180013318  xor     r9d, r9d; Reserved
0x18001331b  mov     rcx, [rsp+260h+hKey]; hKey
0x180013320  xor     r8d, r8d; samDesired
0x180013323  call    cs:__imp_RegDeleteKeyExW
0x18001332a  nop     dword ptr [rax+rax+00h]
0x18001332f  mov     ebx, eax
0x180013331  test    eax, eax
0x180013333  jle     short loc_18001333A
0x180013335  movzx   ebx, ax
0x180013338  or      ebx, esi
0x18001333a  mov     rcx, [rsp+260h+hKey]; hKey
0x18001333f  test    rcx, rcx
0x180013342  jz      short loc_180013359
0x180013344  call    cs:__imp_RegCloseKey
0x18001334b  nop     dword ptr [rax+rax+00h]
0x180013350  mov     [rsp+260h+hKey], 0
0x180013359  mov     rcx, [rsp+260h+lpsz]; pv
0x18001335e  call    cs:__imp_CoTaskMemFree
0x180013365  nop     dword ptr [rax+rax+00h]
0x18001336a  mov     eax, ebx
0x18001336c  mov     rcx, [rbp+160h+var_10]
0x180013373  xor     rcx, rsp; StackCookie
0x180013376  call    __security_check_cookie
0x18001337b  lea     r11, [rsp+260h+var_s0]
0x180013383  mov     rbx, [r11+10h]
0x180013387  mov     rsi, [r11+18h]
0x18001338b  mov     rsp, r11
0x18001338e  pop     rbp
0x18001338f  retn
```
