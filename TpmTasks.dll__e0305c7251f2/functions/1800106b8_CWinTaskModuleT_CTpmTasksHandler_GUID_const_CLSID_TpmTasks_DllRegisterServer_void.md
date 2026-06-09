# CWinTaskModuleT<CTpmTasksHandler,&_GUID const CLSID_TpmTasks>::DllRegisterServer(void)

- ea: `0x1800106b8`
- end: `0x18001089b`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCTpmTasksHandler@@$1?CLSID_TpmTasks@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025480`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x1800106b8`
- `0x18001be20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180010720`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180010720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001072f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001072f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800107bf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800107bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010878`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010878`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001080f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001084d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001080f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001084d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010863`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010863`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180010754`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180010754`

## string_xrefs

- `0x180010769`: `CLSID\\%s\InprocServer32`
- `0x180010838`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CTpmTasksHandler,&_GUID const CLSID_TpmTasks>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_TpmTasks, &lpsz);
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
0x1800106b8  push    rbp
0x1800106ba  push    rbx
0x1800106bb  push    rsi
0x1800106bc  push    rdi
0x1800106bd  lea     rbp, [rsp-398h]
0x1800106c5  sub     rsp, 498h
0x1800106cc  mov     rax, cs:__security_cookie
0x1800106d3  xor     rax, rsp
0x1800106d6  mov     [rbp+3B0h+var_30], rax
0x1800106dd  mov     ebx, 208h
0x1800106e2  lea     rcx, [rsp+4B0h+Filename]; void *
0x1800106e7  xor     edi, edi
0x1800106e9  mov     r8d, ebx; Size
0x1800106ec  xor     edx, edx; Val
0x1800106ee  mov     [rsp+4B0h+hKey], rdi
0x1800106f3  call    memset_0
0x1800106f8  mov     r8d, ebx; Size
0x1800106fb  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180010702  xor     edx, edx; Val
0x180010704  call    memset_0
0x180010709  mov     r8d, 104h; nSize
0x18001070f  mov     [rsp+4B0h+lpsz], rdi
0x180010714  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180010719  lea     rcx, __ImageBase; hModule
0x180010720  call    cs:__imp_GetModuleFileNameW
0x180010726  mov     esi, 80070000h
0x18001072b  test    eax, eax
0x18001072d  jnz     short loc_180010748
0x18001072f  call    cs:__imp_GetLastError
0x180010735  mov     ebx, eax
0x180010737  test    eax, eax
0x180010739  jle     short loc_180010740
0x18001073b  movzx   ebx, ax
0x18001073e  or      ebx, esi
0x180010740  test    ebx, ebx
0x180010742  js      loc_18001085E
0x180010748  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x18001074d  lea     rcx, CLSID_TpmTasks; rclsid
0x180010754  call    cs:__imp_StringFromCLSID
0x18001075a  mov     ebx, eax
0x18001075c  test    eax, eax
0x18001075e  js      loc_18001085E
0x180010764  mov     r9, [rsp+4B0h+lpsz]
0x180010769  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180010770  mov     edx, 104h; unsigned __int64
0x180010775  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x18001077c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010781  mov     ebx, eax
0x180010783  test    eax, eax
0x180010785  js      loc_18001085E
0x18001078b  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x180010790  lea     rax, [rsp+4B0h+hKey]
0x180010795  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18001079a  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x1800107a1  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800107a6  xor     r9d, r9d; lpClass
0x1800107a9  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x1800107b1  xor     r8d, r8d; Reserved
0x1800107b4  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800107bb  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x1800107bf  call    cs:__imp_RegCreateKeyExW
0x1800107c5  mov     ebx, eax
0x1800107c7  test    eax, eax
0x1800107c9  jle     short loc_1800107D0
0x1800107cb  movzx   ebx, ax
0x1800107ce  or      ebx, esi
0x1800107d0  test    ebx, ebx
0x1800107d2  js      loc_18001085E
0x1800107d8  lea     rcx, [rsp+4B0h+Filename]
0x1800107dd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800107e1  inc     rax
0x1800107e4  cmp     [rcx+rax*2], di
0x1800107e8  jnz     short loc_1800107E1
0x1800107ea  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800107ef  lea     eax, ds:2[rax*2]
0x1800107f6  mov     [rsp+4B0h+samDesired], eax; cbData
0x1800107fa  mov     r9d, 1; dwType
0x180010800  lea     rax, [rsp+4B0h+Filename]
0x180010805  xor     r8d, r8d; Reserved
0x180010808  xor     edx, edx; lpValueName
0x18001080a  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18001080f  call    cs:__imp_RegSetValueExW
0x180010815  mov     ebx, eax
0x180010817  test    eax, eax
0x180010819  jle     short loc_180010820
0x18001081b  movzx   ebx, ax
0x18001081e  or      ebx, esi
0x180010820  test    ebx, ebx
0x180010822  js      short loc_18001085E
0x180010824  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180010829  lea     rax, Data; "Both"
0x180010830  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180010838  lea     rdx, aThreadingmodel; "ThreadingModel"
0x18001083f  mov     r9d, 1; dwType
0x180010845  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18001084a  xor     r8d, r8d; Reserved
0x18001084d  call    cs:__imp_RegSetValueExW
0x180010853  mov     ebx, eax
0x180010855  test    eax, eax
0x180010857  jle     short loc_18001085E
0x180010859  movzx   ebx, ax
0x18001085c  or      ebx, esi
0x18001085e  mov     rcx, [rsp+4B0h+lpsz]; pv
0x180010863  call    cs:__imp_CoTaskMemFree
0x180010869  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18001086e  mov     [rsp+4B0h+lpsz], rdi
0x180010873  test    rcx, rcx
0x180010876  jz      short loc_18001087E
0x180010878  call    cs:__imp_RegCloseKey
0x18001087e  mov     eax, ebx
0x180010880  mov     rcx, [rbp+3B0h+var_30]
0x180010887  xor     rcx, rsp; StackCookie
0x18001088a  call    __security_check_cookie
0x18001088f  add     rsp, 498h
0x180010896  pop     rdi
0x180010897  pop     rsi
0x180010898  pop     rbx
0x180010899  pop     rbp
0x18001089a  retn
```
