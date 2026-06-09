# CWinTaskModuleT<CEcoScoreTaskHandler,&_GUID const CLSID_EcoScoreTask>::DllRegisterServer(void)

- ea: `0x180003ee0`
- end: `0x1800040c3`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCEcoScoreTaskHandler@@$1?CLSID_EcoScoreTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007a10`

## callees

- `0x180003ee0`
- `0x180006ed0`
- `0x180007c62`
- `0x180007c90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180003f48`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180003f48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000408b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000408b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003f7c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003f7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800040a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003fe7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003fe7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004037`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004075`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004037`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004075`

## string_xrefs

- `0x180003f91`: `CLSID\\%s\InprocServer32`
- `0x180004060`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CEcoScoreTaskHandler,&_GUID const CLSID_EcoScoreTask>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_EcoScoreTask, &lpsz);
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
0x180003ee0  push    rbp
0x180003ee2  push    rbx
0x180003ee3  push    rsi
0x180003ee4  push    rdi
0x180003ee5  lea     rbp, [rsp-398h]
0x180003eed  sub     rsp, 498h
0x180003ef4  mov     rax, cs:__security_cookie
0x180003efb  xor     rax, rsp
0x180003efe  mov     [rbp+3B0h+var_30], rax
0x180003f05  mov     ebx, 208h
0x180003f0a  lea     rcx, [rsp+4B0h+Filename]; void *
0x180003f0f  xor     edi, edi
0x180003f11  mov     r8d, ebx; Size
0x180003f14  xor     edx, edx; Val
0x180003f16  mov     [rsp+4B0h+hKey], rdi
0x180003f1b  call    memset_0
0x180003f20  mov     r8d, ebx; Size
0x180003f23  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180003f2a  xor     edx, edx; Val
0x180003f2c  call    memset_0
0x180003f31  mov     r8d, 104h; nSize
0x180003f37  mov     [rsp+4B0h+lpsz], rdi
0x180003f3c  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180003f41  lea     rcx, cs:180000000h; hModule
0x180003f48  call    cs:__imp_GetModuleFileNameW
0x180003f4e  mov     esi, 80070000h
0x180003f53  test    eax, eax
0x180003f55  jnz     short loc_180003F70
0x180003f57  call    cs:__imp_GetLastError
0x180003f5d  mov     ebx, eax
0x180003f5f  test    eax, eax
0x180003f61  jle     short loc_180003F68
0x180003f63  movzx   ebx, ax
0x180003f66  or      ebx, esi
0x180003f68  test    ebx, ebx
0x180003f6a  js      loc_180004086
0x180003f70  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180003f75  lea     rcx, CLSID_EcoScoreTask; rclsid
0x180003f7c  call    cs:__imp_StringFromCLSID
0x180003f82  mov     ebx, eax
0x180003f84  test    eax, eax
0x180003f86  js      loc_180004086
0x180003f8c  mov     r9, [rsp+4B0h+lpsz]
0x180003f91  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180003f98  mov     edx, 104h; unsigned __int64
0x180003f9d  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180003fa4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003fa9  mov     ebx, eax
0x180003fab  test    eax, eax
0x180003fad  js      loc_180004086
0x180003fb3  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180003fb8  lea     rax, [rsp+4B0h+hKey]
0x180003fbd  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180003fc2  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180003fc9  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180003fce  xor     r9d, r9d; lpClass
0x180003fd1  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180003fd9  xor     r8d, r8d; Reserved
0x180003fdc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180003fe3  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180003fe7  call    cs:__imp_RegCreateKeyExW
0x180003fed  mov     ebx, eax
0x180003fef  test    eax, eax
0x180003ff1  jle     short loc_180003FF8
0x180003ff3  movzx   ebx, ax
0x180003ff6  or      ebx, esi
0x180003ff8  test    ebx, ebx
0x180003ffa  js      loc_180004086
0x180004000  lea     rcx, [rsp+4B0h+Filename]
0x180004005  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004009  inc     rax
0x18000400c  cmp     [rcx+rax*2], di
0x180004010  jnz     short loc_180004009
0x180004012  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180004017  lea     eax, ds:2[rax*2]
0x18000401e  mov     [rsp+4B0h+samDesired], eax; cbData
0x180004022  mov     r9d, 1; dwType
0x180004028  lea     rax, [rsp+4B0h+Filename]
0x18000402d  xor     r8d, r8d; Reserved
0x180004030  xor     edx, edx; lpValueName
0x180004032  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180004037  call    cs:__imp_RegSetValueExW
0x18000403d  mov     ebx, eax
0x18000403f  test    eax, eax
0x180004041  jle     short loc_180004048
0x180004043  movzx   ebx, ax
0x180004046  or      ebx, esi
0x180004048  test    ebx, ebx
0x18000404a  js      short loc_180004086
0x18000404c  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180004051  lea     rax, Data; "Both"
0x180004058  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180004060  lea     rdx, ValueName; "ThreadingModel"
0x180004067  mov     r9d, 1; dwType
0x18000406d  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180004072  xor     r8d, r8d; Reserved
0x180004075  call    cs:__imp_RegSetValueExW
0x18000407b  mov     ebx, eax
0x18000407d  test    eax, eax
0x18000407f  jle     short loc_180004086
0x180004081  movzx   ebx, ax
0x180004084  or      ebx, esi
0x180004086  mov     rcx, [rsp+4B0h+lpsz]; pv
0x18000408b  call    cs:__imp_CoTaskMemFree
0x180004091  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180004096  mov     [rsp+4B0h+lpsz], rdi
0x18000409b  test    rcx, rcx
0x18000409e  jz      short loc_1800040A6
0x1800040a0  call    cs:__imp_RegCloseKey
0x1800040a6  mov     eax, ebx
0x1800040a8  mov     rcx, [rbp+3B0h+var_30]
0x1800040af  xor     rcx, rsp; StackCookie
0x1800040b2  call    __security_check_cookie
0x1800040b7  add     rsp, 498h
0x1800040be  pop     rdi
0x1800040bf  pop     rsi
0x1800040c0  pop     rbx
0x1800040c1  pop     rbp
0x1800040c2  retn
```
