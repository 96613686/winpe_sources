# CWinTaskModuleT<CTimeSyncTaskHandler,&_GUID const CLSID_TimeSyncTask>::DllRegisterServer(void)

- ea: `0x180002520`
- end: `0x180002703`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCTimeSyncTaskHandler@@$1?CLSID_TimeSyncTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002e40`

## callees

- `0x180001460`
- `0x180001d2a`
- `0x180001fd4`
- `0x180002520`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002588`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180002588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002597`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002677`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800026b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002677`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800026b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800026e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800026e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002627`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180002627`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800025bc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800025bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800026cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800026cb`

## string_xrefs

- `0x1800025d1`: `CLSID\\%s\InprocServer32`
- `0x1800026a0`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CTimeSyncTaskHandler,&_GUID const CLSID_TimeSyncTask>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_TimeSyncTask, &lpsz);
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
0x180002520  push    rbp
0x180002522  push    rbx
0x180002523  push    rsi
0x180002524  push    rdi
0x180002525  lea     rbp, [rsp-398h]
0x18000252d  sub     rsp, 498h
0x180002534  mov     rax, cs:__security_cookie
0x18000253b  xor     rax, rsp
0x18000253e  mov     [rbp+3B0h+var_30], rax
0x180002545  mov     ebx, 208h
0x18000254a  lea     rcx, [rsp+4B0h+Filename]; void *
0x18000254f  xor     edi, edi
0x180002551  mov     r8d, ebx; Size
0x180002554  xor     edx, edx; Val
0x180002556  mov     [rsp+4B0h+hKey], rdi
0x18000255b  call    memset_0
0x180002560  mov     r8d, ebx; Size
0x180002563  lea     rcx, [rbp+3B0h+SubKey]; void *
0x18000256a  xor     edx, edx; Val
0x18000256c  call    memset_0
0x180002571  mov     r8d, 104h; nSize
0x180002577  mov     [rsp+4B0h+lpsz], rdi
0x18000257c  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180002581  lea     rcx, cs:180000000h; hModule
0x180002588  call    cs:__imp_GetModuleFileNameW
0x18000258e  mov     esi, 80070000h
0x180002593  test    eax, eax
0x180002595  jnz     short loc_1800025B0
0x180002597  call    cs:__imp_GetLastError
0x18000259d  mov     ebx, eax
0x18000259f  test    eax, eax
0x1800025a1  jle     short loc_1800025A8
0x1800025a3  movzx   ebx, ax
0x1800025a6  or      ebx, esi
0x1800025a8  test    ebx, ebx
0x1800025aa  js      loc_1800026C6
0x1800025b0  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x1800025b5  lea     rcx, CLSID_TimeSyncTask; rclsid
0x1800025bc  call    cs:__imp_StringFromCLSID
0x1800025c2  mov     ebx, eax
0x1800025c4  test    eax, eax
0x1800025c6  js      loc_1800026C6
0x1800025cc  mov     r9, [rsp+4B0h+lpsz]
0x1800025d1  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x1800025d8  mov     edx, 104h; unsigned __int64
0x1800025dd  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x1800025e4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800025e9  mov     ebx, eax
0x1800025eb  test    eax, eax
0x1800025ed  js      loc_1800026C6
0x1800025f3  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x1800025f8  lea     rax, [rsp+4B0h+hKey]
0x1800025fd  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180002602  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180002609  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000260e  xor     r9d, r9d; lpClass
0x180002611  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x180002619  xor     r8d, r8d; Reserved
0x18000261c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002623  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x180002627  call    cs:__imp_RegCreateKeyExW
0x18000262d  mov     ebx, eax
0x18000262f  test    eax, eax
0x180002631  jle     short loc_180002638
0x180002633  movzx   ebx, ax
0x180002636  or      ebx, esi
0x180002638  test    ebx, ebx
0x18000263a  js      loc_1800026C6
0x180002640  lea     rcx, [rsp+4B0h+Filename]
0x180002645  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002649  inc     rax
0x18000264c  cmp     [rcx+rax*2], di
0x180002650  jnz     short loc_180002649
0x180002652  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180002657  lea     eax, ds:2[rax*2]
0x18000265e  mov     [rsp+4B0h+samDesired], eax; cbData
0x180002662  mov     r9d, 1; dwType
0x180002668  lea     rax, [rsp+4B0h+Filename]
0x18000266d  xor     r8d, r8d; Reserved
0x180002670  xor     edx, edx; lpValueName
0x180002672  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180002677  call    cs:__imp_RegSetValueExW
0x18000267d  mov     ebx, eax
0x18000267f  test    eax, eax
0x180002681  jle     short loc_180002688
0x180002683  movzx   ebx, ax
0x180002686  or      ebx, esi
0x180002688  test    ebx, ebx
0x18000268a  js      short loc_1800026C6
0x18000268c  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180002691  lea     rax, Data; "Both"
0x180002698  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x1800026a0  lea     rdx, ValueName; "ThreadingModel"
0x1800026a7  mov     r9d, 1; dwType
0x1800026ad  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800026b2  xor     r8d, r8d; Reserved
0x1800026b5  call    cs:__imp_RegSetValueExW
0x1800026bb  mov     ebx, eax
0x1800026bd  test    eax, eax
0x1800026bf  jle     short loc_1800026C6
0x1800026c1  movzx   ebx, ax
0x1800026c4  or      ebx, esi
0x1800026c6  mov     rcx, [rsp+4B0h+lpsz]; pv
0x1800026cb  call    cs:__imp_CoTaskMemFree
0x1800026d1  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800026d6  mov     [rsp+4B0h+lpsz], rdi
0x1800026db  test    rcx, rcx
0x1800026de  jz      short loc_1800026E6
0x1800026e0  call    cs:__imp_RegCloseKey
0x1800026e6  mov     eax, ebx
0x1800026e8  mov     rcx, [rbp+3B0h+var_30]
0x1800026ef  xor     rcx, rsp; StackCookie
0x1800026f2  call    __security_check_cookie
0x1800026f7  add     rsp, 498h
0x1800026fe  pop     rdi
0x1800026ff  pop     rsi
0x180002700  pop     rbx
0x180002701  pop     rbp
0x180002702  retn
```
