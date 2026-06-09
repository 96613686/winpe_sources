# CWinTaskModuleT<SettingsConfigTaskHandler,&_GUID const CLSID_SettingsConfigTaskHandler>::DllRegisterServer(void)

- ea: `0x180005628`
- end: `0x18000580b`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VSettingsConfigTaskHandler@@$1?CLSID_SettingsConfigTaskHandler@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b940`

## callees

- `0x1800021d0`
- `0x180002c18`
- `0x180005628`
- `0x180009f8c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180005690`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180005690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000569f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000569f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800057d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800057d3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800056c4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800056c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800057e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800057e8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000572f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000572f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000577f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800057bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000577f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800057bd`

## string_xrefs

- `0x1800056d9`: `CLSID\\%s\InprocServer32`
- `0x1800057a8`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<SettingsConfigTaskHandler,&_GUID const CLSID_SettingsConfigTaskHandler>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_SettingsConfigTaskHandler, &lpsz);
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
0x180005628  push    rbp
0x18000562a  push    rbx
0x18000562b  push    rsi
0x18000562c  push    rdi
0x18000562d  lea     rbp, [rsp-398h]
0x180005635  sub     rsp, 498h
0x18000563c  mov     rax, cs:__security_cookie
0x180005643  xor     rax, rsp
0x180005646  mov     [rbp+3B0h+var_30], rax
0x18000564d  mov     ebx, 208h
0x180005652  lea     rcx, [rsp+4B0h+Filename]; void *
0x180005657  xor     edi, edi
0x180005659  mov     r8d, ebx; Size
0x18000565c  xor     edx, edx; Val
0x18000565e  mov     [rsp+4B0h+hKey], rdi
0x180005663  call    memset_0
0x180005668  mov     r8d, ebx; Size
0x18000566b  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180005672  xor     edx, edx; Val
0x180005674  call    memset_0
0x180005679  mov     r8d, 104h; nSize
0x18000567f  mov     [rsp+4B0h+lpsz], rdi
0x180005684  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180005689  lea     rcx, __ImageBase; hModule
0x180005690  call    cs:__imp_GetModuleFileNameW
0x180005696  mov     esi, 80070000h
0x18000569b  test    eax, eax
0x18000569d  jnz     short loc_1800056B8
0x18000569f  call    cs:__imp_GetLastError
0x1800056a5  mov     ebx, eax
0x1800056a7  test    eax, eax
0x1800056a9  jle     short loc_1800056B0
0x1800056ab  movzx   ebx, ax
0x1800056ae  or      ebx, esi
0x1800056b0  test    ebx, ebx
0x1800056b2  js      loc_1800057CE
0x1800056b8  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x1800056bd  lea     rcx, CLSID_SettingsConfigTaskHandler; rclsid
0x1800056c4  call    cs:__imp_StringFromCLSID
0x1800056ca  mov     ebx, eax
0x1800056cc  test    eax, eax
0x1800056ce  js      loc_1800057CE
0x1800056d4  mov     r9, [rsp+4B0h+lpsz]
0x1800056d9  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x1800056e0  mov     edx, 104h; unsigned __int64
0x1800056e5  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x1800056ec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800056f1  mov     ebx, eax
0x1800056f3  test    eax, eax
0x1800056f5  js      loc_1800057CE
0x1800056fb  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180005700  lea     rax, [rsp+4B0h+hKey]
0x180005705  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000570a  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180005711  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180005716  xor     r9d, r9d; lpClass
0x180005719  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180005721  xor     r8d, r8d; Reserved
0x180005724  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000572b  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x18000572f  call    cs:__imp_RegCreateKeyExW
0x180005735  mov     ebx, eax
0x180005737  test    eax, eax
0x180005739  jle     short loc_180005740
0x18000573b  movzx   ebx, ax
0x18000573e  or      ebx, esi
0x180005740  test    ebx, ebx
0x180005742  js      loc_1800057CE
0x180005748  lea     rcx, [rsp+4B0h+Filename]
0x18000574d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005751  inc     rax
0x180005754  cmp     [rcx+rax*2], di
0x180005758  jnz     short loc_180005751
0x18000575a  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000575f  lea     eax, ds:2[rax*2]
0x180005766  mov     [rsp+4B0h+samDesired], eax; cbData
0x18000576a  mov     r9d, 1; dwType
0x180005770  lea     rax, [rsp+4B0h+Filename]
0x180005775  xor     r8d, r8d; Reserved
0x180005778  xor     edx, edx; lpValueName
0x18000577a  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18000577f  call    cs:__imp_RegSetValueExW
0x180005785  mov     ebx, eax
0x180005787  test    eax, eax
0x180005789  jle     short loc_180005790
0x18000578b  movzx   ebx, ax
0x18000578e  or      ebx, esi
0x180005790  test    ebx, ebx
0x180005792  js      short loc_1800057CE
0x180005794  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180005799  lea     rax, Data; "Both"
0x1800057a0  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x1800057a8  lea     rdx, ValueName; "ThreadingModel"
0x1800057af  mov     r9d, 1; dwType
0x1800057b5  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800057ba  xor     r8d, r8d; Reserved
0x1800057bd  call    cs:__imp_RegSetValueExW
0x1800057c3  mov     ebx, eax
0x1800057c5  test    eax, eax
0x1800057c7  jle     short loc_1800057CE
0x1800057c9  movzx   ebx, ax
0x1800057cc  or      ebx, esi
0x1800057ce  mov     rcx, [rsp+4B0h+lpsz]; pv
0x1800057d3  call    cs:__imp_CoTaskMemFree
0x1800057d9  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800057de  mov     [rsp+4B0h+lpsz], rdi
0x1800057e3  test    rcx, rcx
0x1800057e6  jz      short loc_1800057EE
0x1800057e8  call    cs:__imp_RegCloseKey
0x1800057ee  mov     eax, ebx
0x1800057f0  mov     rcx, [rbp+3B0h+var_30]
0x1800057f7  xor     rcx, rsp; StackCookie
0x1800057fa  call    __security_check_cookie
0x1800057ff  add     rsp, 498h
0x180005806  pop     rdi
0x180005807  pop     rsi
0x180005808  pop     rbx
0x180005809  pop     rbp
0x18000580a  retn
```
