# CWinTaskModuleT<Microsoft::Windows::Autopilot::DetectHardwareChangeHandler,&_GUID const CLSID_DetectHardwareChange>::DllRegisterServer(void)

- ea: `0x18000c654`
- end: `0x18000c868`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VDetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@$1?CLSID_DetectHardwareChange@@3U_GUID@@B@@QEAAJXZ`
- size: `532`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800131b0`

## callees

- `0x1800045d0`
- `0x1800053c4`
- `0x18000c654`
- `0x180011220`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c6bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c6bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c823`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c823`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000c6fc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000c6fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c83e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c83e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c76d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c76d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c7c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c807`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c7c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c807`

## string_xrefs

- `0x18000c717`: `CLSID\\%s\InprocServer32`
- `0x18000c7f2`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<Microsoft::Windows::Autopilot::DetectHardwareChangeHandler,&_GUID const CLSID_DetectHardwareChange>::DllRegisterServer()
{
  signed int LastError; // eax
  int v1; // ebx
  LSTATUS v2; // eax
  __int64 v3; // rax
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  LPOLESTR lpsz; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  memset_0(Filename, 0, 0x208u);
  memset_0(SubKey, 0, 0x208u);
  lpsz = 0;
  if ( GetModuleFileNameW((HMODULE)&_ImageBase, Filename, 0x104u) )
    goto LABEL_5;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_5:
    v1 = StringFromCLSID(&CLSID_DetectHardwareChange, &lpsz);
    if ( v1 >= 0 )
    {
      v1 = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\\\%s\\InprocServer32", lpsz);
      if ( v1 >= 0 )
      {
        v2 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
        v1 = v2;
        if ( v2 > 0 )
          v1 = (unsigned __int16)v2 | 0x80070000;
        if ( v1 >= 0 )
        {
          v3 = -1;
          do
            ++v3;
          while ( Filename[v3] );
          v4 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)Filename, 2 * v3 + 2);
          v1 = v4;
          if ( v4 > 0 )
            v1 = (unsigned __int16)v4 | 0x80070000;
          if ( v1 >= 0 )
          {
            v5 = RegSetValueExW(hKey, L"ThreadingModel", 0, 1u, L"Both", 0xAu);
            v1 = v5;
            if ( v5 > 0 )
              v1 = (unsigned __int16)v5 | 0x80070000;
          }
        }
      }
    }
  }
  CoTaskMemFree(lpsz);
  lpsz = 0;
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000c654  push    rbp
0x18000c656  push    rbx
0x18000c657  push    rsi
0x18000c658  push    rdi
0x18000c659  lea     rbp, [rsp-398h]
0x18000c661  sub     rsp, 498h
0x18000c668  mov     rax, cs:__security_cookie
0x18000c66f  xor     rax, rsp
0x18000c672  mov     [rbp+3B0h+var_30], rax
0x18000c679  mov     ebx, 208h
0x18000c67e  lea     rcx, [rsp+4B0h+Filename]; void *
0x18000c683  xor     edi, edi
0x18000c685  mov     r8d, ebx; Size
0x18000c688  xor     edx, edx; Val
0x18000c68a  mov     [rsp+4B0h+hKey], rdi
0x18000c68f  call    memset_0
0x18000c694  mov     r8d, ebx; Size
0x18000c697  lea     rcx, [rbp+3B0h+SubKey]; void *
0x18000c69e  xor     edx, edx; Val
0x18000c6a0  call    memset_0
0x18000c6a5  mov     r8d, 104h; nSize
0x18000c6ab  mov     [rsp+4B0h+lpsz], rdi
0x18000c6b0  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x18000c6b5  lea     rcx, __ImageBase; hModule
0x18000c6bc  call    cs:__imp_GetModuleFileNameW
0x18000c6c3  nop     dword ptr [rax+rax+00h]
0x18000c6c8  mov     esi, 80070000h
0x18000c6cd  test    eax, eax
0x18000c6cf  jnz     short loc_18000C6F0
0x18000c6d1  call    cs:__imp_GetLastError
0x18000c6d8  nop     dword ptr [rax+rax+00h]
0x18000c6dd  mov     ebx, eax
0x18000c6df  test    eax, eax
0x18000c6e1  jle     short loc_18000C6E8
0x18000c6e3  movzx   ebx, ax
0x18000c6e6  or      ebx, esi
0x18000c6e8  test    ebx, ebx
0x18000c6ea  js      loc_18000C81E
0x18000c6f0  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x18000c6f5  lea     rcx, CLSID_DetectHardwareChange; rclsid
0x18000c6fc  call    cs:__imp_StringFromCLSID
0x18000c703  nop     dword ptr [rax+rax+00h]
0x18000c708  mov     ebx, eax
0x18000c70a  test    eax, eax
0x18000c70c  js      loc_18000C81E
0x18000c712  mov     r9, [rsp+4B0h+lpsz]
0x18000c717  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x18000c71e  mov     edx, 104h; unsigned __int64
0x18000c723  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x18000c72a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c72f  mov     ebx, eax
0x18000c731  test    eax, eax
0x18000c733  js      loc_18000C81E
0x18000c739  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x18000c73e  lea     rax, [rsp+4B0h+hKey]
0x18000c743  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000c748  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x18000c74f  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000c754  xor     r9d, r9d; lpClass
0x18000c757  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x18000c75f  xor     r8d, r8d; Reserved
0x18000c762  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000c769  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x18000c76d  call    cs:__imp_RegCreateKeyExW
0x18000c774  nop     dword ptr [rax+rax+00h]
0x18000c779  mov     ebx, eax
0x18000c77b  test    eax, eax
0x18000c77d  jle     short loc_18000C784
0x18000c77f  movzx   ebx, ax
0x18000c782  or      ebx, esi
0x18000c784  test    ebx, ebx
0x18000c786  js      loc_18000C81E
0x18000c78c  lea     rcx, [rsp+4B0h+Filename]
0x18000c791  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c795  inc     rax
0x18000c798  cmp     [rcx+rax*2], di
0x18000c79c  jnz     short loc_18000C795
0x18000c79e  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000c7a3  lea     eax, ds:2[rax*2]
0x18000c7aa  mov     [rsp+4B0h+samDesired], eax; cbData
0x18000c7ae  mov     r9d, 1; dwType
0x18000c7b4  lea     rax, [rsp+4B0h+Filename]
0x18000c7b9  xor     r8d, r8d; Reserved
0x18000c7bc  xor     edx, edx; lpValueName
0x18000c7be  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18000c7c3  call    cs:__imp_RegSetValueExW
0x18000c7ca  nop     dword ptr [rax+rax+00h]
0x18000c7cf  mov     ebx, eax
0x18000c7d1  test    eax, eax
0x18000c7d3  jle     short loc_18000C7DA
0x18000c7d5  movzx   ebx, ax
0x18000c7d8  or      ebx, esi
0x18000c7da  test    ebx, ebx
0x18000c7dc  js      short loc_18000C81E
0x18000c7de  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000c7e3  lea     rax, Data; "Both"
0x18000c7ea  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x18000c7f2  lea     rdx, ValueName; "ThreadingModel"
0x18000c7f9  mov     r9d, 1; dwType
0x18000c7ff  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18000c804  xor     r8d, r8d; Reserved
0x18000c807  call    cs:__imp_RegSetValueExW
0x18000c80e  nop     dword ptr [rax+rax+00h]
0x18000c813  mov     ebx, eax
0x18000c815  test    eax, eax
0x18000c817  jle     short loc_18000C81E
0x18000c819  movzx   ebx, ax
0x18000c81c  or      ebx, esi
0x18000c81e  mov     rcx, [rsp+4B0h+lpsz]; pv
0x18000c823  call    cs:__imp_CoTaskMemFree
0x18000c82a  nop     dword ptr [rax+rax+00h]
0x18000c82f  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000c834  mov     [rsp+4B0h+lpsz], rdi
0x18000c839  test    rcx, rcx
0x18000c83c  jz      short loc_18000C84A
0x18000c83e  call    cs:__imp_RegCloseKey
0x18000c845  nop     dword ptr [rax+rax+00h]
0x18000c84a  mov     eax, ebx
0x18000c84c  mov     rcx, [rbp+3B0h+var_30]
0x18000c853  xor     rcx, rsp; StackCookie
0x18000c856  call    __security_check_cookie
0x18000c85b  add     rsp, 498h
0x18000c862  pop     rdi
0x18000c863  pop     rsi
0x18000c864  pop     rbx
0x18000c865  pop     rbp
0x18000c866  retn
```
