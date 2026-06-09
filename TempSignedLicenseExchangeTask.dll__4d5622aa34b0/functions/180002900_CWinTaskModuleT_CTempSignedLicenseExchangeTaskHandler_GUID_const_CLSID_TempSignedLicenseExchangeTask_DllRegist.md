# CWinTaskModuleT<CTempSignedLicenseExchangeTaskHandler,&_GUID const CLSID_TempSignedLicenseExchangeTask>::DllRegisterServer(void)

- ea: `0x180002900`
- end: `0x180002ae3`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCTempSignedLicenseExchangeTaskHandler@@$1?CLSID_TempSignedLicenseExchangeTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c590`

## callees

- `0x180001400`
- `0x180001f5e`
- `0x18000230c`
- `0x180002900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002977`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002ac0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002ac0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002a07`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002a07`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002a57`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002a95`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002a57`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002aab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002aab`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000299c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000299c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002968`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002968`

## string_xrefs

- `0x1800029b1`: `CLSID\\%s\InprocServer32`
- `0x180002a80`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CTempSignedLicenseExchangeTaskHandler,&_GUID const CLSID_TempSignedLicenseExchangeTask>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_TempSignedLicenseExchangeTask, &lpsz);
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
0x180002900  push    rbp
0x180002902  push    rbx
0x180002903  push    rsi
0x180002904  push    rdi
0x180002905  lea     rbp, [rsp-398h]
0x18000290d  sub     rsp, 498h
0x180002914  mov     rax, cs:__security_cookie
0x18000291b  xor     rax, rsp
0x18000291e  mov     [rbp+3B0h+var_30], rax
0x180002925  mov     ebx, 208h
0x18000292a  lea     rcx, [rsp+4B0h+Filename]; void *
0x18000292f  xor     edi, edi
0x180002931  mov     r8d, ebx; Size
0x180002934  xor     edx, edx; Val
0x180002936  mov     [rsp+4B0h+hKey], rdi
0x18000293b  call    memset_0
0x180002940  mov     r8d, ebx; Size
0x180002943  lea     rcx, [rbp+3B0h+SubKey]; void *
0x18000294a  xor     edx, edx; Val
0x18000294c  call    memset_0
0x180002951  mov     r8d, 104h; nSize
0x180002957  mov     [rsp+4B0h+lpsz], rdi
0x18000295c  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180002961  lea     rcx, cs:180000000h; hModule
0x180002968  call    cs:__imp_GetModuleFileNameW
0x18000296e  mov     esi, 80070000h
0x180002973  test    eax, eax
0x180002975  jnz     short loc_180002990
0x180002977  call    cs:__imp_GetLastError
0x18000297d  mov     ebx, eax
0x18000297f  test    eax, eax
0x180002981  jle     short loc_180002988
0x180002983  movzx   ebx, ax
0x180002986  or      ebx, esi
0x180002988  test    ebx, ebx
0x18000298a  js      loc_180002AA6
0x180002990  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180002995  lea     rcx, CLSID_TempSignedLicenseExchangeTask; rclsid
0x18000299c  call    cs:__imp_StringFromCLSID
0x1800029a2  mov     ebx, eax
0x1800029a4  test    eax, eax
0x1800029a6  js      loc_180002AA6
0x1800029ac  mov     r9, [rsp+4B0h+lpsz]
0x1800029b1  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x1800029b8  mov     edx, 104h; unsigned __int64
0x1800029bd  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x1800029c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800029c9  mov     ebx, eax
0x1800029cb  test    eax, eax
0x1800029cd  js      loc_180002AA6
0x1800029d3  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x1800029d8  lea     rax, [rsp+4B0h+hKey]
0x1800029dd  mov     [rsp+4B0h+phkResult], rax; phkResult
0x1800029e2  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x1800029e9  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800029ee  xor     r9d, r9d; lpClass
0x1800029f1  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x1800029f9  xor     r8d, r8d; Reserved
0x1800029fc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002a03  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180002a07  call    cs:__imp_RegCreateKeyExW
0x180002a0d  mov     ebx, eax
0x180002a0f  test    eax, eax
0x180002a11  jle     short loc_180002A18
0x180002a13  movzx   ebx, ax
0x180002a16  or      ebx, esi
0x180002a18  test    ebx, ebx
0x180002a1a  js      loc_180002AA6
0x180002a20  lea     rcx, [rsp+4B0h+Filename]
0x180002a25  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002a29  inc     rax
0x180002a2c  cmp     [rcx+rax*2], di
0x180002a30  jnz     short loc_180002A29
0x180002a32  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180002a37  lea     eax, ds:2[rax*2]
0x180002a3e  mov     [rsp+4B0h+samDesired], eax; cbData
0x180002a42  mov     r9d, 1; dwType
0x180002a48  lea     rax, [rsp+4B0h+Filename]
0x180002a4d  xor     r8d, r8d; Reserved
0x180002a50  xor     edx, edx; lpValueName
0x180002a52  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180002a57  call    cs:__imp_RegSetValueExW
0x180002a5d  mov     ebx, eax
0x180002a5f  test    eax, eax
0x180002a61  jle     short loc_180002A68
0x180002a63  movzx   ebx, ax
0x180002a66  or      ebx, esi
0x180002a68  test    ebx, ebx
0x180002a6a  js      short loc_180002AA6
0x180002a6c  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180002a71  lea     rax, Data; "Both"
0x180002a78  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180002a80  lea     rdx, ValueName; "ThreadingModel"
0x180002a87  mov     r9d, 1; dwType
0x180002a8d  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180002a92  xor     r8d, r8d; Reserved
0x180002a95  call    cs:__imp_RegSetValueExW
0x180002a9b  mov     ebx, eax
0x180002a9d  test    eax, eax
0x180002a9f  jle     short loc_180002AA6
0x180002aa1  movzx   ebx, ax
0x180002aa4  or      ebx, esi
0x180002aa6  mov     rcx, [rsp+4B0h+lpsz]; pv
0x180002aab  call    cs:__imp_CoTaskMemFree
0x180002ab1  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180002ab6  mov     [rsp+4B0h+lpsz], rdi
0x180002abb  test    rcx, rcx
0x180002abe  jz      short loc_180002AC6
0x180002ac0  call    cs:__imp_RegCloseKey
0x180002ac6  mov     eax, ebx
0x180002ac8  mov     rcx, [rbp+3B0h+var_30]
0x180002acf  xor     rcx, rsp; StackCookie
0x180002ad2  call    __security_check_cookie
0x180002ad7  add     rsp, 498h
0x180002ade  pop     rdi
0x180002adf  pop     rsi
0x180002ae0  pop     rbx
0x180002ae1  pop     rbp
0x180002ae2  retn
```
