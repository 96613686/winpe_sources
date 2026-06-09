# CWinTaskModuleT<CReAgentTaskHandler,&_GUID const CLSID_ReAgentTaskHandler>::DllRegisterServer(void)

- ea: `0x180001cac`
- end: `0x180001e8f`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCReAgentTaskHandler@@$1?CLSID_ReAgentTaskHandler@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800023d0`

## callees

- `0x180001cac`
- `0x180002140`
- `0x180002616`
- `0x180002650`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001e57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180001e57`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180001d48`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180001d48`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180001d14`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180001d14`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001e03`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001e41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001e03`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180001e41`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180001db3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180001db3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d23`

## string_xrefs

- `0x180001d5d`: `CLSID\\%s\InprocServer32`
- `0x180001e2c`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CReAgentTaskHandler,&_GUID const CLSID_ReAgentTaskHandler>::DllRegisterServer()
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
  if ( GetModuleFileNameW((HMODULE)0x180000000LL, Filename, 0x104u) )
    goto LABEL_5;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_5:
    v1 = StringFromCLSID(&CLSID_ReAgentTaskHandler, &lpsz);
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
0x180001cac  push    rbp
0x180001cae  push    rbx
0x180001caf  push    rsi
0x180001cb0  push    rdi
0x180001cb1  lea     rbp, [rsp-398h]
0x180001cb9  sub     rsp, 498h
0x180001cc0  mov     rax, cs:__security_cookie
0x180001cc7  xor     rax, rsp
0x180001cca  mov     [rbp+3B0h+var_30], rax
0x180001cd1  mov     ebx, 208h
0x180001cd6  lea     rcx, [rsp+4B0h+Filename]; void *
0x180001cdb  xor     edi, edi
0x180001cdd  mov     r8d, ebx; Size
0x180001ce0  xor     edx, edx; Val
0x180001ce2  mov     [rsp+4B0h+hKey], rdi
0x180001ce7  call    memset_0
0x180001cec  mov     r8d, ebx; Size
0x180001cef  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180001cf6  xor     edx, edx; Val
0x180001cf8  call    memset_0
0x180001cfd  mov     r8d, 104h; nSize
0x180001d03  mov     [rsp+4B0h+lpsz], rdi
0x180001d08  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180001d0d  lea     rcx, cs:180000000h; hModule
0x180001d14  call    cs:__imp_GetModuleFileNameW
0x180001d1a  mov     esi, 80070000h
0x180001d1f  test    eax, eax
0x180001d21  jnz     short loc_180001D3C
0x180001d23  call    cs:__imp_GetLastError
0x180001d29  mov     ebx, eax
0x180001d2b  test    eax, eax
0x180001d2d  jle     short loc_180001D34
0x180001d2f  movzx   ebx, ax
0x180001d32  or      ebx, esi
0x180001d34  test    ebx, ebx
0x180001d36  js      loc_180001E52
0x180001d3c  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180001d41  lea     rcx, CLSID_ReAgentTaskHandler; rclsid
0x180001d48  call    cs:__imp_StringFromCLSID
0x180001d4e  mov     ebx, eax
0x180001d50  test    eax, eax
0x180001d52  js      loc_180001E52
0x180001d58  mov     r9, [rsp+4B0h+lpsz]
0x180001d5d  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180001d64  mov     edx, 104h; unsigned __int64
0x180001d69  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180001d70  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180001d75  mov     ebx, eax
0x180001d77  test    eax, eax
0x180001d79  js      loc_180001E52
0x180001d7f  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180001d84  lea     rax, [rsp+4B0h+hKey]
0x180001d89  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180001d8e  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180001d95  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180001d9a  xor     r9d, r9d; lpClass
0x180001d9d  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180001da5  xor     r8d, r8d; Reserved
0x180001da8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180001daf  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180001db3  call    cs:__imp_RegCreateKeyExW
0x180001db9  mov     ebx, eax
0x180001dbb  test    eax, eax
0x180001dbd  jle     short loc_180001DC4
0x180001dbf  movzx   ebx, ax
0x180001dc2  or      ebx, esi
0x180001dc4  test    ebx, ebx
0x180001dc6  js      loc_180001E52
0x180001dcc  lea     rcx, [rsp+4B0h+Filename]
0x180001dd1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001dd5  inc     rax
0x180001dd8  cmp     [rcx+rax*2], di
0x180001ddc  jnz     short loc_180001DD5
0x180001dde  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180001de3  lea     eax, ds:2[rax*2]
0x180001dea  mov     [rsp+4B0h+samDesired], eax; cbData
0x180001dee  mov     r9d, 1; dwType
0x180001df4  lea     rax, [rsp+4B0h+Filename]
0x180001df9  xor     r8d, r8d; Reserved
0x180001dfc  xor     edx, edx; lpValueName
0x180001dfe  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180001e03  call    cs:__imp_RegSetValueExW
0x180001e09  mov     ebx, eax
0x180001e0b  test    eax, eax
0x180001e0d  jle     short loc_180001E14
0x180001e0f  movzx   ebx, ax
0x180001e12  or      ebx, esi
0x180001e14  test    ebx, ebx
0x180001e16  js      short loc_180001E52
0x180001e18  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180001e1d  lea     rax, Data; "Both"
0x180001e24  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180001e2c  lea     rdx, ValueName; "ThreadingModel"
0x180001e33  mov     r9d, 1; dwType
0x180001e39  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180001e3e  xor     r8d, r8d; Reserved
0x180001e41  call    cs:__imp_RegSetValueExW
0x180001e47  mov     ebx, eax
0x180001e49  test    eax, eax
0x180001e4b  jle     short loc_180001E52
0x180001e4d  movzx   ebx, ax
0x180001e50  or      ebx, esi
0x180001e52  mov     rcx, [rsp+4B0h+lpsz]; pv
0x180001e57  call    cs:__imp_CoTaskMemFree
0x180001e5d  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180001e62  mov     [rsp+4B0h+lpsz], rdi
0x180001e67  test    rcx, rcx
0x180001e6a  jz      short loc_180001E72
0x180001e6c  call    cs:__imp_RegCloseKey
0x180001e72  mov     eax, ebx
0x180001e74  mov     rcx, [rbp+3B0h+var_30]
0x180001e7b  xor     rcx, rsp; StackCookie
0x180001e7e  call    __security_check_cookie
0x180001e83  add     rsp, 498h
0x180001e8a  pop     rdi
0x180001e8b  pop     rsi
0x180001e8c  pop     rbx
0x180001e8d  pop     rbp
0x180001e8e  retn
```
