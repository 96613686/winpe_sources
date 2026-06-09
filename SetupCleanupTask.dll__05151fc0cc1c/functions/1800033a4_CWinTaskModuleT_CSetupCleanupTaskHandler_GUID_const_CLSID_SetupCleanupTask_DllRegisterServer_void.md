# CWinTaskModuleT<CSetupCleanupTaskHandler,&_GUID const CLSID_SetupCleanupTask>::DllRegisterServer(void)

- ea: `0x1800033a4`
- end: `0x180003587`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCSetupCleanupTaskHandler@@$1?CLSID_SetupCleanupTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180003ab0`

## callees

- `0x1800033a4`
- `0x180003850`
- `0x1800322d2`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000354f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000354f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003440`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003440`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000340c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000340c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800034fb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003539`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800034fb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003539`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003564`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003564`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800034ab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800034ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000341b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000341b`

## string_xrefs

- `0x180003455`: `CLSID\\%s\InprocServer32`
- `0x180003524`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CSetupCleanupTaskHandler,&_GUID const CLSID_SetupCleanupTask>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_SetupCleanupTask, &lpsz);
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
0x1800033a4  push    rbp
0x1800033a6  push    rbx
0x1800033a7  push    rsi
0x1800033a8  push    rdi
0x1800033a9  lea     rbp, [rsp-398h]
0x1800033b1  sub     rsp, 498h
0x1800033b8  mov     rax, cs:__security_cookie
0x1800033bf  xor     rax, rsp
0x1800033c2  mov     [rbp+3B0h+var_30], rax
0x1800033c9  mov     ebx, 208h
0x1800033ce  lea     rcx, [rsp+4B0h+Filename]; void *
0x1800033d3  xor     edi, edi
0x1800033d5  mov     r8d, ebx; Size
0x1800033d8  xor     edx, edx; Val
0x1800033da  mov     [rsp+4B0h+hKey], rdi
0x1800033df  call    memset_0
0x1800033e4  mov     r8d, ebx; Size
0x1800033e7  lea     rcx, [rbp+3B0h+SubKey]; void *
0x1800033ee  xor     edx, edx; Val
0x1800033f0  call    memset_0
0x1800033f5  mov     r8d, 104h; nSize
0x1800033fb  mov     [rsp+4B0h+lpsz], rdi
0x180003400  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180003405  lea     rcx, cs:180000000h; hModule
0x18000340c  call    cs:__imp_GetModuleFileNameW
0x180003412  mov     esi, 80070000h
0x180003417  test    eax, eax
0x180003419  jnz     short loc_180003434
0x18000341b  call    cs:__imp_GetLastError
0x180003421  mov     ebx, eax
0x180003423  test    eax, eax
0x180003425  jle     short loc_18000342C
0x180003427  movzx   ebx, ax
0x18000342a  or      ebx, esi
0x18000342c  test    ebx, ebx
0x18000342e  js      loc_18000354A
0x180003434  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180003439  lea     rcx, CLSID_SetupCleanupTask; rclsid
0x180003440  call    cs:__imp_StringFromCLSID
0x180003446  mov     ebx, eax
0x180003448  test    eax, eax
0x18000344a  js      loc_18000354A
0x180003450  mov     r9, [rsp+4B0h+lpsz]
0x180003455  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x18000345c  mov     edx, 104h; unsigned __int64
0x180003461  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180003468  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000346d  mov     ebx, eax
0x18000346f  test    eax, eax
0x180003471  js      loc_18000354A
0x180003477  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x18000347c  lea     rax, [rsp+4B0h+hKey]
0x180003481  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180003486  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x18000348d  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180003492  xor     r9d, r9d; lpClass
0x180003495  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x18000349d  xor     r8d, r8d; Reserved
0x1800034a0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800034a7  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x1800034ab  call    cs:__imp_RegCreateKeyExW
0x1800034b1  mov     ebx, eax
0x1800034b3  test    eax, eax
0x1800034b5  jle     short loc_1800034BC
0x1800034b7  movzx   ebx, ax
0x1800034ba  or      ebx, esi
0x1800034bc  test    ebx, ebx
0x1800034be  js      loc_18000354A
0x1800034c4  lea     rcx, [rsp+4B0h+Filename]
0x1800034c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800034cd  inc     rax
0x1800034d0  cmp     [rcx+rax*2], di
0x1800034d4  jnz     short loc_1800034CD
0x1800034d6  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800034db  lea     eax, ds:2[rax*2]
0x1800034e2  mov     [rsp+4B0h+samDesired], eax; cbData
0x1800034e6  mov     r9d, 1; dwType
0x1800034ec  lea     rax, [rsp+4B0h+Filename]
0x1800034f1  xor     r8d, r8d; Reserved
0x1800034f4  xor     edx, edx; lpValueName
0x1800034f6  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800034fb  call    cs:__imp_RegSetValueExW
0x180003501  mov     ebx, eax
0x180003503  test    eax, eax
0x180003505  jle     short loc_18000350C
0x180003507  movzx   ebx, ax
0x18000350a  or      ebx, esi
0x18000350c  test    ebx, ebx
0x18000350e  js      short loc_18000354A
0x180003510  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180003515  lea     rax, Data; "Both"
0x18000351c  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180003524  lea     rdx, ValueName; "ThreadingModel"
0x18000352b  mov     r9d, 1; dwType
0x180003531  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180003536  xor     r8d, r8d; Reserved
0x180003539  call    cs:__imp_RegSetValueExW
0x18000353f  mov     ebx, eax
0x180003541  test    eax, eax
0x180003543  jle     short loc_18000354A
0x180003545  movzx   ebx, ax
0x180003548  or      ebx, esi
0x18000354a  mov     rcx, [rsp+4B0h+lpsz]; pv
0x18000354f  call    cs:__imp_CoTaskMemFree
0x180003555  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000355a  mov     [rsp+4B0h+lpsz], rdi
0x18000355f  test    rcx, rcx
0x180003562  jz      short loc_18000356A
0x180003564  call    cs:__imp_RegCloseKey
0x18000356a  mov     eax, ebx
0x18000356c  mov     rcx, [rbp+3B0h+var_30]
0x180003573  xor     rcx, rsp; StackCookie
0x180003576  call    __security_check_cookie
0x18000357b  add     rsp, 498h
0x180003582  pop     rdi
0x180003583  pop     rsi
0x180003584  pop     rbx
0x180003585  pop     rbp
0x180003586  retn
```
