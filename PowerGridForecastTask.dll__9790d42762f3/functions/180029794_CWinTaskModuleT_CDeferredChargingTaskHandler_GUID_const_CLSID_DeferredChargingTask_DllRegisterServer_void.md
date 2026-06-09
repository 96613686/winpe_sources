# CWinTaskModuleT<CDeferredChargingTaskHandler,&_GUID const CLSID_DeferredChargingTask>::DllRegisterServer(void)

- ea: `0x180029794`
- end: `0x180029977`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCDeferredChargingTaskHandler@@$1?CLSID_DeferredChargingTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180030ac0`

## callees

- `0x1800268ef`
- `0x180029794`
- `0x18002edf0`
- `0x1800350e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800297fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800297fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002980b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002980b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002993f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002993f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180029830`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180029830`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800298eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029929`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800298eb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029929`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002989b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002989b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029954`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029954`

## string_xrefs

- `0x180029845`: `CLSID\\%s\InprocServer32`
- `0x180029914`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CDeferredChargingTaskHandler,&_GUID const CLSID_DeferredChargingTask>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_DeferredChargingTask, &lpsz);
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
0x180029794  push    rbp
0x180029796  push    rbx
0x180029797  push    rsi
0x180029798  push    rdi
0x180029799  lea     rbp, [rsp-398h]
0x1800297a1  sub     rsp, 498h
0x1800297a8  mov     rax, cs:__security_cookie
0x1800297af  xor     rax, rsp
0x1800297b2  mov     [rbp+3B0h+var_30], rax
0x1800297b9  mov     ebx, 208h
0x1800297be  lea     rcx, [rsp+4B0h+Filename]; void *
0x1800297c3  xor     edi, edi
0x1800297c5  mov     r8d, ebx; Size
0x1800297c8  xor     edx, edx; Val
0x1800297ca  mov     [rsp+4B0h+hKey], rdi
0x1800297cf  call    memset_0
0x1800297d4  mov     r8d, ebx; Size
0x1800297d7  lea     rcx, [rbp+3B0h+SubKey]; void *
0x1800297de  xor     edx, edx; Val
0x1800297e0  call    memset_0
0x1800297e5  mov     r8d, 104h; nSize
0x1800297eb  mov     [rsp+4B0h+lpsz], rdi
0x1800297f0  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x1800297f5  lea     rcx, cs:180000000h; hModule
0x1800297fc  call    cs:__imp_GetModuleFileNameW
0x180029802  mov     esi, 80070000h
0x180029807  test    eax, eax
0x180029809  jnz     short loc_180029824
0x18002980b  call    cs:__imp_GetLastError
0x180029811  mov     ebx, eax
0x180029813  test    eax, eax
0x180029815  jle     short loc_18002981C
0x180029817  movzx   ebx, ax
0x18002981a  or      ebx, esi
0x18002981c  test    ebx, ebx
0x18002981e  js      loc_18002993A
0x180029824  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180029829  lea     rcx, CLSID_DeferredChargingTask; rclsid
0x180029830  call    cs:__imp_StringFromCLSID
0x180029836  mov     ebx, eax
0x180029838  test    eax, eax
0x18002983a  js      loc_18002993A
0x180029840  mov     r9, [rsp+4B0h+lpsz]
0x180029845  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x18002984c  mov     edx, 104h; unsigned __int64
0x180029851  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180029858  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002985d  mov     ebx, eax
0x18002985f  test    eax, eax
0x180029861  js      loc_18002993A
0x180029867  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x18002986c  lea     rax, [rsp+4B0h+hKey]
0x180029871  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180029876  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x18002987d  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180029882  xor     r9d, r9d; lpClass
0x180029885  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x18002988d  xor     r8d, r8d; Reserved
0x180029890  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180029897  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x18002989b  call    cs:__imp_RegCreateKeyExW
0x1800298a1  mov     ebx, eax
0x1800298a3  test    eax, eax
0x1800298a5  jle     short loc_1800298AC
0x1800298a7  movzx   ebx, ax
0x1800298aa  or      ebx, esi
0x1800298ac  test    ebx, ebx
0x1800298ae  js      loc_18002993A
0x1800298b4  lea     rcx, [rsp+4B0h+Filename]
0x1800298b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800298bd  inc     rax
0x1800298c0  cmp     [rcx+rax*2], di
0x1800298c4  jnz     short loc_1800298BD
0x1800298c6  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800298cb  lea     eax, ds:2[rax*2]
0x1800298d2  mov     [rsp+4B0h+samDesired], eax; cbData
0x1800298d6  mov     r9d, 1; dwType
0x1800298dc  lea     rax, [rsp+4B0h+Filename]
0x1800298e1  xor     r8d, r8d; Reserved
0x1800298e4  xor     edx, edx; lpValueName
0x1800298e6  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800298eb  call    cs:__imp_RegSetValueExW
0x1800298f1  mov     ebx, eax
0x1800298f3  test    eax, eax
0x1800298f5  jle     short loc_1800298FC
0x1800298f7  movzx   ebx, ax
0x1800298fa  or      ebx, esi
0x1800298fc  test    ebx, ebx
0x1800298fe  js      short loc_18002993A
0x180029900  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180029905  lea     rax, Data; "Both"
0x18002990c  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180029914  lea     rdx, ValueName; "ThreadingModel"
0x18002991b  mov     r9d, 1; dwType
0x180029921  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180029926  xor     r8d, r8d; Reserved
0x180029929  call    cs:__imp_RegSetValueExW
0x18002992f  mov     ebx, eax
0x180029931  test    eax, eax
0x180029933  jle     short loc_18002993A
0x180029935  movzx   ebx, ax
0x180029938  or      ebx, esi
0x18002993a  mov     rcx, [rsp+4B0h+lpsz]; pv
0x18002993f  call    cs:__imp_CoTaskMemFree
0x180029945  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18002994a  mov     [rsp+4B0h+lpsz], rdi
0x18002994f  test    rcx, rcx
0x180029952  jz      short loc_18002995A
0x180029954  call    cs:__imp_RegCloseKey
0x18002995a  mov     eax, ebx
0x18002995c  mov     rcx, [rbp+3B0h+var_30]
0x180029963  xor     rcx, rsp; StackCookie
0x180029966  call    __security_check_cookie
0x18002996b  add     rsp, 498h
0x180029972  pop     rdi
0x180029973  pop     rsi
0x180029974  pop     rbx
0x180029975  pop     rbp
0x180029976  retn
```
