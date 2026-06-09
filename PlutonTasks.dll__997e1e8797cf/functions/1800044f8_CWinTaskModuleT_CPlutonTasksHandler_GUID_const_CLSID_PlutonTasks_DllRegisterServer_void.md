# CWinTaskModuleT<CPlutonTasksHandler,&_GUID const CLSID_PlutonTasks>::DllRegisterServer(void)

- ea: `0x1800044f8`
- end: `0x1800046db`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCPlutonTasksHandler@@$1?CLSID_PlutonTasks@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009330`

## callees

- `0x180001e00`
- `0x180002858`
- `0x1800044f8`
- `0x180007d1c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004560`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004560`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180004594`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180004594`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800046a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800046a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000456f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000456f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800045ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800045ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800046b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800046b8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000464f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000468d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000464f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000468d`

## string_xrefs

- `0x1800045a9`: `CLSID\\%s\InprocServer32`
- `0x180004678`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CPlutonTasksHandler,&_GUID const CLSID_PlutonTasks>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_PlutonTasks, &lpsz);
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
0x1800044f8  push    rbp
0x1800044fa  push    rbx
0x1800044fb  push    rsi
0x1800044fc  push    rdi
0x1800044fd  lea     rbp, [rsp-398h]
0x180004505  sub     rsp, 498h
0x18000450c  mov     rax, cs:__security_cookie
0x180004513  xor     rax, rsp
0x180004516  mov     [rbp+3B0h+var_30], rax
0x18000451d  mov     ebx, 208h
0x180004522  lea     rcx, [rsp+4B0h+Filename]; void *
0x180004527  xor     edi, edi
0x180004529  mov     r8d, ebx; Size
0x18000452c  xor     edx, edx; Val
0x18000452e  mov     [rsp+4B0h+hKey], rdi
0x180004533  call    memset_0
0x180004538  mov     r8d, ebx; Size
0x18000453b  lea     rcx, [rbp+3B0h+SubKey]; void *
0x180004542  xor     edx, edx; Val
0x180004544  call    memset_0
0x180004549  mov     r8d, 104h; nSize
0x18000454f  mov     [rsp+4B0h+lpsz], rdi
0x180004554  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180004559  lea     rcx, cs:180000000h; hModule
0x180004560  call    cs:__imp_GetModuleFileNameW
0x180004566  mov     esi, 80070000h
0x18000456b  test    eax, eax
0x18000456d  jnz     short loc_180004588
0x18000456f  call    cs:__imp_GetLastError
0x180004575  mov     ebx, eax
0x180004577  test    eax, eax
0x180004579  jle     short loc_180004580
0x18000457b  movzx   ebx, ax
0x18000457e  or      ebx, esi
0x180004580  test    ebx, ebx
0x180004582  js      loc_18000469E
0x180004588  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x18000458d  lea     rcx, CLSID_PlutonTasks; rclsid
0x180004594  call    cs:__imp_StringFromCLSID
0x18000459a  mov     ebx, eax
0x18000459c  test    eax, eax
0x18000459e  js      loc_18000469E
0x1800045a4  mov     r9, [rsp+4B0h+lpsz]
0x1800045a9  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x1800045b0  mov     edx, 104h; unsigned __int64
0x1800045b5  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x1800045bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800045c1  mov     ebx, eax
0x1800045c3  test    eax, eax
0x1800045c5  js      loc_18000469E
0x1800045cb  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x1800045d0  lea     rax, [rsp+4B0h+hKey]
0x1800045d5  mov     [rsp+4B0h+phkResult], rax; phkResult
0x1800045da  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x1800045e1  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800045e6  xor     r9d, r9d; lpClass
0x1800045e9  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x1800045f1  xor     r8d, r8d; Reserved
0x1800045f4  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800045fb  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x1800045ff  call    cs:__imp_RegCreateKeyExW
0x180004605  mov     ebx, eax
0x180004607  test    eax, eax
0x180004609  jle     short loc_180004610
0x18000460b  movzx   ebx, ax
0x18000460e  or      ebx, esi
0x180004610  test    ebx, ebx
0x180004612  js      loc_18000469E
0x180004618  lea     rcx, [rsp+4B0h+Filename]
0x18000461d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004621  inc     rax
0x180004624  cmp     [rcx+rax*2], di
0x180004628  jnz     short loc_180004621
0x18000462a  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000462f  lea     eax, ds:2[rax*2]
0x180004636  mov     [rsp+4B0h+samDesired], eax; cbData
0x18000463a  mov     r9d, 1; dwType
0x180004640  lea     rax, [rsp+4B0h+Filename]
0x180004645  xor     r8d, r8d; Reserved
0x180004648  xor     edx, edx; lpValueName
0x18000464a  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18000464f  call    cs:__imp_RegSetValueExW
0x180004655  mov     ebx, eax
0x180004657  test    eax, eax
0x180004659  jle     short loc_180004660
0x18000465b  movzx   ebx, ax
0x18000465e  or      ebx, esi
0x180004660  test    ebx, ebx
0x180004662  js      short loc_18000469E
0x180004664  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180004669  lea     rax, Data; "Both"
0x180004670  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180004678  lea     rdx, ValueName; "ThreadingModel"
0x18000467f  mov     r9d, 1; dwType
0x180004685  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18000468a  xor     r8d, r8d; Reserved
0x18000468d  call    cs:__imp_RegSetValueExW
0x180004693  mov     ebx, eax
0x180004695  test    eax, eax
0x180004697  jle     short loc_18000469E
0x180004699  movzx   ebx, ax
0x18000469c  or      ebx, esi
0x18000469e  mov     rcx, [rsp+4B0h+lpsz]; pv
0x1800046a3  call    cs:__imp_CoTaskMemFree
0x1800046a9  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800046ae  mov     [rsp+4B0h+lpsz], rdi
0x1800046b3  test    rcx, rcx
0x1800046b6  jz      short loc_1800046BE
0x1800046b8  call    cs:__imp_RegCloseKey
0x1800046be  mov     eax, ebx
0x1800046c0  mov     rcx, [rbp+3B0h+var_30]
0x1800046c7  xor     rcx, rsp; StackCookie
0x1800046ca  call    __security_check_cookie
0x1800046cf  add     rsp, 498h
0x1800046d6  pop     rdi
0x1800046d7  pop     rsi
0x1800046d8  pop     rbx
0x1800046d9  pop     rbp
0x1800046da  retn
```
