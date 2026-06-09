# CWinTaskModuleT<Microsoft::Windows::Autopilot::DetectHardwareChangeHandler,&_GUID const CLSID_DetectHardwareChange>::DllRegisterServer(void)

- ea: `0x18000c5f4`
- end: `0x18000c7d7`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VDetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@$1?CLSID_DetectHardwareChange@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012f50`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x18000c5f4`
- `0x180011224`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c65c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c65c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c79f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c79f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000c690`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000c690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c66b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c7b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c7b4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c6fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c6fb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c74b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c789`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c74b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c789`

## string_xrefs

- `0x18000c6a5`: `CLSID\\%s\InprocServer32`
- `0x18000c774`: `ThreadingModel`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000c5f4  push    rbp
0x18000c5f6  push    rbx
0x18000c5f7  push    rsi
0x18000c5f8  push    rdi
0x18000c5f9  lea     rbp, [rsp-398h]
0x18000c601  sub     rsp, 498h
0x18000c608  mov     rax, cs:__security_cookie
0x18000c60f  xor     rax, rsp
0x18000c612  mov     [rbp+3B0h+var_30], rax
0x18000c619  mov     ebx, 208h
0x18000c61e  lea     rcx, [rsp+4B0h+Filename]; void *
0x18000c623  xor     edi, edi
0x18000c625  mov     r8d, ebx; Size
0x18000c628  xor     edx, edx; Val
0x18000c62a  mov     [rsp+4B0h+hKey], rdi
0x18000c62f  call    memset_0
0x18000c634  mov     r8d, ebx; Size
0x18000c637  lea     rcx, [rbp+3B0h+SubKey]; void *
0x18000c63e  xor     edx, edx; Val
0x18000c640  call    memset_0
0x18000c645  mov     r8d, 104h; nSize
0x18000c64b  mov     [rsp+4B0h+lpsz], rdi
0x18000c650  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x18000c655  lea     rcx, __ImageBase; hModule
0x18000c65c  call    cs:__imp_GetModuleFileNameW
0x18000c662  mov     esi, 80070000h
0x18000c667  test    eax, eax
0x18000c669  jnz     short loc_18000C684
0x18000c66b  call    cs:__imp_GetLastError
0x18000c671  mov     ebx, eax
0x18000c673  test    eax, eax
0x18000c675  jle     short loc_18000C67C
0x18000c677  movzx   ebx, ax
0x18000c67a  or      ebx, esi
0x18000c67c  test    ebx, ebx
0x18000c67e  js      loc_18000C79A
0x18000c684  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x18000c689  lea     rcx, CLSID_DetectHardwareChange; rclsid
0x18000c690  call    cs:__imp_StringFromCLSID
0x18000c696  mov     ebx, eax
0x18000c698  test    eax, eax
0x18000c69a  js      loc_18000C79A
0x18000c6a0  mov     r9, [rsp+4B0h+lpsz]
0x18000c6a5  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x18000c6ac  mov     edx, 104h; unsigned __int64
0x18000c6b1  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x18000c6b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c6bd  mov     ebx, eax
0x18000c6bf  test    eax, eax
0x18000c6c1  js      loc_18000C79A
0x18000c6c7  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x18000c6cc  lea     rax, [rsp+4B0h+hKey]
0x18000c6d1  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000c6d6  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x18000c6dd  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000c6e2  xor     r9d, r9d; lpClass
0x18000c6e5  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x18000c6ed  xor     r8d, r8d; Reserved
0x18000c6f0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000c6f7  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x18000c6fb  call    cs:__imp_RegCreateKeyExW
0x18000c701  mov     ebx, eax
0x18000c703  test    eax, eax
0x18000c705  jle     short loc_18000C70C
0x18000c707  movzx   ebx, ax
0x18000c70a  or      ebx, esi
0x18000c70c  test    ebx, ebx
0x18000c70e  js      loc_18000C79A
0x18000c714  lea     rcx, [rsp+4B0h+Filename]
0x18000c719  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c71d  inc     rax
0x18000c720  cmp     [rcx+rax*2], di
0x18000c724  jnz     short loc_18000C71D
0x18000c726  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000c72b  lea     eax, ds:2[rax*2]
0x18000c732  mov     [rsp+4B0h+samDesired], eax; cbData
0x18000c736  mov     r9d, 1; dwType
0x18000c73c  lea     rax, [rsp+4B0h+Filename]
0x18000c741  xor     r8d, r8d; Reserved
0x18000c744  xor     edx, edx; lpValueName
0x18000c746  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18000c74b  call    cs:__imp_RegSetValueExW
0x18000c751  mov     ebx, eax
0x18000c753  test    eax, eax
0x18000c755  jle     short loc_18000C75C
0x18000c757  movzx   ebx, ax
0x18000c75a  or      ebx, esi
0x18000c75c  test    ebx, ebx
0x18000c75e  js      short loc_18000C79A
0x18000c760  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000c765  lea     rax, Data; "Both"
0x18000c76c  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x18000c774  lea     rdx, ValueName; "ThreadingModel"
0x18000c77b  mov     r9d, 1; dwType
0x18000c781  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18000c786  xor     r8d, r8d; Reserved
0x18000c789  call    cs:__imp_RegSetValueExW
0x18000c78f  mov     ebx, eax
0x18000c791  test    eax, eax
0x18000c793  jle     short loc_18000C79A
0x18000c795  movzx   ebx, ax
0x18000c798  or      ebx, esi
0x18000c79a  mov     rcx, [rsp+4B0h+lpsz]; pv
0x18000c79f  call    cs:__imp_CoTaskMemFree
0x18000c7a5  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000c7aa  mov     [rsp+4B0h+lpsz], rdi
0x18000c7af  test    rcx, rcx
0x18000c7b2  jz      short loc_18000C7BA
0x18000c7b4  call    cs:__imp_RegCloseKey
0x18000c7ba  mov     eax, ebx
0x18000c7bc  mov     rcx, [rbp+3B0h+var_30]
0x18000c7c3  xor     rcx, rsp; StackCookie
0x18000c7c6  call    __security_check_cookie
0x18000c7cb  add     rsp, 498h
0x18000c7d2  pop     rdi
0x18000c7d3  pop     rsi
0x18000c7d4  pop     rbx
0x18000c7d5  pop     rbp
0x18000c7d6  retn
```
