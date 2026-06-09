# CWinTaskModuleT<CLanguageComponentsInstallerHandler,&_GUID const CLSID_LanguageComponentsInstaller>::DllRegisterServer(void)

- ea: `0x180015cd0`
- end: `0x180015eb3`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCLanguageComponentsInstallerHandler@@$1?CLSID_LanguageComponentsInstaller@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180022eb0`

## callees

- `0x180003520`
- `0x180004118`
- `0x180009c94`
- `0x180015cd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180015d38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180015d38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d47`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180015d6c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180015d6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015e7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015e7b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015dd7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015dd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015e90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015e90`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015e27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015e65`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015e27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015e65`

## string_xrefs

- `0x180015d81`: `CLSID\\%s\InprocServer32`
- `0x180015e50`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CLanguageComponentsInstallerHandler,&_GUID const CLSID_LanguageComponentsInstaller>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_LanguageComponentsInstaller, &lpsz);
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
0x180015cd0  push    rbp
0x180015cd2  push    rbx
0x180015cd3  push    rsi
0x180015cd4  push    rdi
0x180015cd5  lea     rbp, [rsp-398h]
0x180015cdd  sub     rsp, 498h
0x180015ce4  mov     rax, cs:__security_cookie
0x180015ceb  xor     rax, rsp
0x180015cee  mov     [rbp+3B0h+var_30], rax
0x180015cf5  mov     ebx, 208h
0x180015cfa  lea     rcx, [rsp+4B0h+Filename]; void *
0x180015cff  xor     edi, edi
0x180015d01  mov     r8d, ebx; Size
0x180015d04  xor     edx, edx; Val
0x180015d06  mov     [rsp+4B0h+hKey], rdi
0x180015d0b  call    memset_0
0x180015d10  mov     r8d, ebx; Size
0x180015d13  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180015d1a  xor     edx, edx; Val
0x180015d1c  call    memset_0
0x180015d21  mov     r8d, 104h; nSize
0x180015d27  mov     [rsp+4B0h+lpsz], rdi
0x180015d2c  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180015d31  lea     rcx, __ImageBase; hModule
0x180015d38  call    cs:__imp_GetModuleFileNameW
0x180015d3e  mov     esi, 80070000h
0x180015d43  test    eax, eax
0x180015d45  jnz     short loc_180015D60
0x180015d47  call    cs:__imp_GetLastError
0x180015d4d  mov     ebx, eax
0x180015d4f  test    eax, eax
0x180015d51  jle     short loc_180015D58
0x180015d53  movzx   ebx, ax
0x180015d56  or      ebx, esi
0x180015d58  test    ebx, ebx
0x180015d5a  js      loc_180015E76
0x180015d60  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180015d65  lea     rcx, CLSID_LanguageComponentsInstaller; rclsid
0x180015d6c  call    cs:__imp_StringFromCLSID
0x180015d72  mov     ebx, eax
0x180015d74  test    eax, eax
0x180015d76  js      loc_180015E76
0x180015d7c  mov     r9, [rsp+4B0h+lpsz]
0x180015d81  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180015d88  mov     edx, 104h; unsigned __int64
0x180015d8d  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180015d94  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015d99  mov     ebx, eax
0x180015d9b  test    eax, eax
0x180015d9d  js      loc_180015E76
0x180015da3  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180015da8  lea     rax, [rsp+4B0h+hKey]
0x180015dad  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180015db2  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180015db9  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180015dbe  xor     r9d, r9d; lpClass
0x180015dc1  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180015dc9  xor     r8d, r8d; Reserved
0x180015dcc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180015dd3  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180015dd7  call    cs:__imp_RegCreateKeyExW
0x180015ddd  mov     ebx, eax
0x180015ddf  test    eax, eax
0x180015de1  jle     short loc_180015DE8
0x180015de3  movzx   ebx, ax
0x180015de6  or      ebx, esi
0x180015de8  test    ebx, ebx
0x180015dea  js      loc_180015E76
0x180015df0  lea     rcx, [rsp+4B0h+Filename]
0x180015df5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015df9  inc     rax
0x180015dfc  cmp     [rcx+rax*2], di
0x180015e00  jnz     short loc_180015DF9
0x180015e02  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180015e07  lea     eax, ds:2[rax*2]
0x180015e0e  mov     [rsp+4B0h+samDesired], eax; cbData
0x180015e12  mov     r9d, 1; dwType
0x180015e18  lea     rax, [rsp+4B0h+Filename]
0x180015e1d  xor     r8d, r8d; Reserved
0x180015e20  xor     edx, edx; lpValueName
0x180015e22  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180015e27  call    cs:__imp_RegSetValueExW
0x180015e2d  mov     ebx, eax
0x180015e2f  test    eax, eax
0x180015e31  jle     short loc_180015E38
0x180015e33  movzx   ebx, ax
0x180015e36  or      ebx, esi
0x180015e38  test    ebx, ebx
0x180015e3a  js      short loc_180015E76
0x180015e3c  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180015e41  lea     rax, Data; "Both"
0x180015e48  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180015e50  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180015e57  mov     r9d, 1; dwType
0x180015e5d  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180015e62  xor     r8d, r8d; Reserved
0x180015e65  call    cs:__imp_RegSetValueExW
0x180015e6b  mov     ebx, eax
0x180015e6d  test    eax, eax
0x180015e6f  jle     short loc_180015E76
0x180015e71  movzx   ebx, ax
0x180015e74  or      ebx, esi
0x180015e76  mov     rcx, [rsp+4B0h+lpsz]; pv
0x180015e7b  call    cs:__imp_CoTaskMemFree
0x180015e81  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180015e86  mov     [rsp+4B0h+lpsz], rdi
0x180015e8b  test    rcx, rcx
0x180015e8e  jz      short loc_180015E96
0x180015e90  call    cs:__imp_RegCloseKey
0x180015e96  mov     eax, ebx
0x180015e98  mov     rcx, [rbp+3B0h+var_30]
0x180015e9f  xor     rcx, rsp; StackCookie
0x180015ea2  call    __security_check_cookie
0x180015ea7  add     rsp, 498h
0x180015eae  pop     rdi
0x180015eaf  pop     rsi
0x180015eb0  pop     rbx
0x180015eb1  pop     rbp
0x180015eb2  retn
```
