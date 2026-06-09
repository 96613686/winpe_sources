# CWinTaskModuleT<CWofTasksHandler,&_GUID const CLSID_WofTasks>::DllRegisterServer(void)

- ea: `0x180002fd0`
- end: `0x1800031b3`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCWofTasksHandler@@$1?CLSID_WofTasks@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x180002fd0`
- `0x180003850`
- `0x18000518e`
- `0x1800051c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003047`
- `KERNEL32!GetLastError` at `0x180003047`
- `KERNEL32!GetModuleFileNameW` at `0x180003038`
- `KERNEL32!GetModuleFileNameW` at `0x180003038`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000306c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000306c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000317b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000317b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003190`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003190`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800030d7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800030d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003127`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003165`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003127`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003165`

## string_xrefs

- `0x180003081`: `CLSID\\%s\InprocServer32`
- `0x180003150`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CWofTasksHandler,&_GUID const CLSID_WofTasks>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_WofTasks, &lpsz);
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
0x180002fd0  push    rbp
0x180002fd2  push    rbx
0x180002fd3  push    rsi
0x180002fd4  push    rdi
0x180002fd5  lea     rbp, [rsp-398h]
0x180002fdd  sub     rsp, 498h
0x180002fe4  mov     rax, cs:__security_cookie
0x180002feb  xor     rax, rsp
0x180002fee  mov     [rbp+3B0h+var_30], rax
0x180002ff5  mov     ebx, 208h
0x180002ffa  lea     rcx, [rsp+4B0h+Filename]; void *
0x180002fff  xor     edi, edi
0x180003001  mov     r8d, ebx; Size
0x180003004  xor     edx, edx; Val
0x180003006  mov     [rsp+4B0h+hKey], rdi
0x18000300b  call    memset_0
0x180003010  mov     r8d, ebx; Size
0x180003013  lea     rcx, [rbp+3B0h+SubKey]; void *
0x18000301a  xor     edx, edx; Val
0x18000301c  call    memset_0
0x180003021  mov     r8d, 104h; nSize
0x180003027  mov     [rsp+4B0h+lpsz], rdi
0x18000302c  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180003031  lea     rcx, cs:180000000h; hModule
0x180003038  call    cs:__imp_GetModuleFileNameW
0x18000303e  mov     esi, 80070000h
0x180003043  test    eax, eax
0x180003045  jnz     short loc_180003060
0x180003047  call    cs:__imp_GetLastError
0x18000304d  mov     ebx, eax
0x18000304f  test    eax, eax
0x180003051  jle     short loc_180003058
0x180003053  movzx   ebx, ax
0x180003056  or      ebx, esi
0x180003058  test    ebx, ebx
0x18000305a  js      loc_180003176
0x180003060  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180003065  lea     rcx, CLSID_WofTasks; rclsid
0x18000306c  call    cs:__imp_StringFromCLSID
0x180003072  mov     ebx, eax
0x180003074  test    eax, eax
0x180003076  js      loc_180003176
0x18000307c  mov     r9, [rsp+4B0h+lpsz]
0x180003081  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x180003088  mov     edx, 104h; unsigned __int64
0x18000308d  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180003094  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003099  mov     ebx, eax
0x18000309b  test    eax, eax
0x18000309d  js      loc_180003176
0x1800030a3  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x1800030a8  lea     rax, [rsp+4B0h+hKey]
0x1800030ad  mov     [rsp+4B0h+phkResult], rax; phkResult
0x1800030b2  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x1800030b9  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800030be  xor     r9d, r9d; lpClass
0x1800030c1  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x1800030c9  xor     r8d, r8d; Reserved
0x1800030cc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800030d3  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x1800030d7  call    cs:__imp_RegCreateKeyExW
0x1800030dd  mov     ebx, eax
0x1800030df  test    eax, eax
0x1800030e1  jle     short loc_1800030E8
0x1800030e3  movzx   ebx, ax
0x1800030e6  or      ebx, esi
0x1800030e8  test    ebx, ebx
0x1800030ea  js      loc_180003176
0x1800030f0  lea     rcx, [rsp+4B0h+Filename]
0x1800030f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800030f9  inc     rax
0x1800030fc  cmp     [rcx+rax*2], di
0x180003100  jnz     short loc_1800030F9
0x180003102  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180003107  lea     eax, ds:2[rax*2]
0x18000310e  mov     [rsp+4B0h+samDesired], eax; cbData
0x180003112  mov     r9d, 1; dwType
0x180003118  lea     rax, [rsp+4B0h+Filename]
0x18000311d  xor     r8d, r8d; Reserved
0x180003120  xor     edx, edx; lpValueName
0x180003122  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180003127  call    cs:__imp_RegSetValueExW
0x18000312d  mov     ebx, eax
0x18000312f  test    eax, eax
0x180003131  jle     short loc_180003138
0x180003133  movzx   ebx, ax
0x180003136  or      ebx, esi
0x180003138  test    ebx, ebx
0x18000313a  js      short loc_180003176
0x18000313c  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180003141  lea     rax, Data; "Both"
0x180003148  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180003150  lea     rdx, ValueName; "ThreadingModel"
0x180003157  mov     r9d, 1; dwType
0x18000315d  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180003162  xor     r8d, r8d; Reserved
0x180003165  call    cs:__imp_RegSetValueExW
0x18000316b  mov     ebx, eax
0x18000316d  test    eax, eax
0x18000316f  jle     short loc_180003176
0x180003171  movzx   ebx, ax
0x180003174  or      ebx, esi
0x180003176  mov     rcx, [rsp+4B0h+lpsz]; pv
0x18000317b  call    cs:__imp_CoTaskMemFree
0x180003181  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180003186  mov     [rsp+4B0h+lpsz], rdi
0x18000318b  test    rcx, rcx
0x18000318e  jz      short loc_180003196
0x180003190  call    cs:__imp_RegCloseKey
0x180003196  mov     eax, ebx
0x180003198  mov     rcx, [rbp+3B0h+var_30]
0x18000319f  xor     rcx, rsp; StackCookie
0x1800031a2  call    __security_check_cookie
0x1800031a7  add     rsp, 498h
0x1800031ae  pop     rdi
0x1800031af  pop     rsi
0x1800031b0  pop     rbx
0x1800031b1  pop     rbp
0x1800031b2  retn
```
