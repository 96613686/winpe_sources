# CWinTaskModuleT<CPITRTaskHandler,&_GUID const CLSID_PITRTask>::DllRegisterServer(void)

- ea: `0x180004bd4`
- end: `0x180004db7`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCPITRTaskHandler@@$1?CLSID_PITRTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c740`

## callees

- `0x180004bd4`
- `0x180009758`
- `0x180010792`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004c3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004c3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d7f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180004c70`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180004c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d94`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004d2b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004d69`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004d2b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004d69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004cdb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004cdb`

## string_xrefs

- `0x180004c85`: `CLSID\\%s\InprocServer32`
- `0x180004d54`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CPITRTaskHandler,&_GUID const CLSID_PITRTask>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_PITRTask, &lpsz);
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
0x180004bd4  push    rbp
0x180004bd6  push    rbx
0x180004bd7  push    rsi
0x180004bd8  push    rdi
0x180004bd9  lea     rbp, [rsp-398h]
0x180004be1  sub     rsp, 498h
0x180004be8  mov     rax, cs:__security_cookie
0x180004bef  xor     rax, rsp
0x180004bf2  mov     [rbp+3B0h+var_30], rax
0x180004bf9  mov     ebx, 208h
0x180004bfe  lea     rcx, [rsp+4B0h+Filename]; void *
0x180004c03  xor     edi, edi
0x180004c05  mov     r8d, ebx; Size
0x180004c08  xor     edx, edx; Val
0x180004c0a  mov     [rsp+4B0h+hKey], rdi
0x180004c0f  call    memset_0
0x180004c14  mov     r8d, ebx; Size
0x180004c17  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180004c1e  xor     edx, edx; Val
0x180004c20  call    memset_0
0x180004c25  mov     r8d, 104h; nSize
0x180004c2b  mov     [rsp+4B0h+lpsz], rdi
0x180004c30  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180004c35  lea     rcx, cs:180000000h; hModule
0x180004c3c  call    cs:__imp_GetModuleFileNameW
0x180004c42  mov     esi, 80070000h
0x180004c47  test    eax, eax
0x180004c49  jnz     short loc_180004C64
0x180004c4b  call    cs:__imp_GetLastError
0x180004c51  mov     ebx, eax
0x180004c53  test    eax, eax
0x180004c55  jle     short loc_180004C5C
0x180004c57  movzx   ebx, ax
0x180004c5a  or      ebx, esi
0x180004c5c  test    ebx, ebx
0x180004c5e  js      loc_180004D7A
0x180004c64  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180004c69  lea     rcx, CLSID_PITRTask; rclsid
0x180004c70  call    cs:__imp_StringFromCLSID
0x180004c76  mov     ebx, eax
0x180004c78  test    eax, eax
0x180004c7a  js      loc_180004D7A
0x180004c80  mov     r9, [rsp+4B0h+lpsz]
0x180004c85  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180004c8c  mov     edx, 104h; unsigned __int64
0x180004c91  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180004c98  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004c9d  mov     ebx, eax
0x180004c9f  test    eax, eax
0x180004ca1  js      loc_180004D7A
0x180004ca7  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180004cac  lea     rax, [rsp+4B0h+hKey]
0x180004cb1  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180004cb6  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180004cbd  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180004cc2  xor     r9d, r9d; lpClass
0x180004cc5  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180004ccd  xor     r8d, r8d; Reserved
0x180004cd0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180004cd7  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180004cdb  call    cs:__imp_RegCreateKeyExW
0x180004ce1  mov     ebx, eax
0x180004ce3  test    eax, eax
0x180004ce5  jle     short loc_180004CEC
0x180004ce7  movzx   ebx, ax
0x180004cea  or      ebx, esi
0x180004cec  test    ebx, ebx
0x180004cee  js      loc_180004D7A
0x180004cf4  lea     rcx, [rsp+4B0h+Filename]
0x180004cf9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004cfd  inc     rax
0x180004d00  cmp     [rcx+rax*2], di
0x180004d04  jnz     short loc_180004CFD
0x180004d06  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180004d0b  lea     eax, ds:2[rax*2]
0x180004d12  mov     [rsp+4B0h+samDesired], eax; cbData
0x180004d16  mov     r9d, 1; dwType
0x180004d1c  lea     rax, [rsp+4B0h+Filename]
0x180004d21  xor     r8d, r8d; Reserved
0x180004d24  xor     edx, edx; lpValueName
0x180004d26  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180004d2b  call    cs:__imp_RegSetValueExW
0x180004d31  mov     ebx, eax
0x180004d33  test    eax, eax
0x180004d35  jle     short loc_180004D3C
0x180004d37  movzx   ebx, ax
0x180004d3a  or      ebx, esi
0x180004d3c  test    ebx, ebx
0x180004d3e  js      short loc_180004D7A
0x180004d40  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180004d45  lea     rax, Data; "Both"
0x180004d4c  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180004d54  lea     rdx, ValueName; "ThreadingModel"
0x180004d5b  mov     r9d, 1; dwType
0x180004d61  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180004d66  xor     r8d, r8d; Reserved
0x180004d69  call    cs:__imp_RegSetValueExW
0x180004d6f  mov     ebx, eax
0x180004d71  test    eax, eax
0x180004d73  jle     short loc_180004D7A
0x180004d75  movzx   ebx, ax
0x180004d78  or      ebx, esi
0x180004d7a  mov     rcx, [rsp+4B0h+lpsz]; pv
0x180004d7f  call    cs:__imp_CoTaskMemFree
0x180004d85  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180004d8a  mov     [rsp+4B0h+lpsz], rdi
0x180004d8f  test    rcx, rcx
0x180004d92  jz      short loc_180004D9A
0x180004d94  call    cs:__imp_RegCloseKey
0x180004d9a  mov     eax, ebx
0x180004d9c  mov     rcx, [rbp+3B0h+var_30]
0x180004da3  xor     rcx, rsp; StackCookie
0x180004da6  call    __security_check_cookie
0x180004dab  add     rsp, 498h
0x180004db2  pop     rdi
0x180004db3  pop     rsi
0x180004db4  pop     rbx
0x180004db5  pop     rbp
0x180004db6  retn
```
