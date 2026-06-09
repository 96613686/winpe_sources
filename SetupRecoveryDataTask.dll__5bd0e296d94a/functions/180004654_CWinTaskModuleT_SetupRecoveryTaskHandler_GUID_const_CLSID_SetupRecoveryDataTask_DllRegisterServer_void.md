# CWinTaskModuleT<SetupRecoveryTaskHandler,&_GUID const CLSID_SetupRecoveryDataTask>::DllRegisterServer(void)

- ea: `0x180004654`
- end: `0x180004837`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VSetupRecoveryTaskHandler@@$1?CLSID_SetupRecoveryDataTask@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b770`

## callees

- `0x180004654`
- `0x180009480`
- `0x18000c5e2`
- `0x18000c610`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800046bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800046bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800047ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800047ff`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800046f0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800046f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800047ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800047e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800047ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800047e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004814`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000475b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000475b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046cb`

## string_xrefs

- `0x180004705`: `CLSID\\%s\InprocServer32`
- `0x1800047d4`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<SetupRecoveryTaskHandler,&_GUID const CLSID_SetupRecoveryDataTask>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_SetupRecoveryDataTask, &lpsz);
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
0x180004654  push    rbp
0x180004656  push    rbx
0x180004657  push    rsi
0x180004658  push    rdi
0x180004659  lea     rbp, [rsp-398h]
0x180004661  sub     rsp, 498h
0x180004668  mov     rax, cs:__security_cookie
0x18000466f  xor     rax, rsp
0x180004672  mov     [rbp+3B0h+var_30], rax
0x180004679  mov     ebx, 208h
0x18000467e  lea     rcx, [rsp+4B0h+Filename]; void *
0x180004683  xor     edi, edi
0x180004685  mov     r8d, ebx; Size
0x180004688  xor     edx, edx; Val
0x18000468a  mov     [rsp+4B0h+hKey], rdi
0x18000468f  call    memset_0
0x180004694  mov     r8d, ebx; Size
0x180004697  lea     rcx, [rbp+3B0h+SubKey]; void *
0x18000469e  xor     edx, edx; Val
0x1800046a0  call    memset_0
0x1800046a5  mov     r8d, 104h; nSize
0x1800046ab  mov     [rsp+4B0h+lpsz], rdi
0x1800046b0  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x1800046b5  lea     rcx, cs:180000000h; hModule
0x1800046bc  call    cs:__imp_GetModuleFileNameW
0x1800046c2  mov     esi, 80070000h
0x1800046c7  test    eax, eax
0x1800046c9  jnz     short loc_1800046E4
0x1800046cb  call    cs:__imp_GetLastError
0x1800046d1  mov     ebx, eax
0x1800046d3  test    eax, eax
0x1800046d5  jle     short loc_1800046DC
0x1800046d7  movzx   ebx, ax
0x1800046da  or      ebx, esi
0x1800046dc  test    ebx, ebx
0x1800046de  js      loc_1800047FA
0x1800046e4  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x1800046e9  lea     rcx, CLSID_SetupRecoveryDataTask; rclsid
0x1800046f0  call    cs:__imp_StringFromCLSID
0x1800046f6  mov     ebx, eax
0x1800046f8  test    eax, eax
0x1800046fa  js      loc_1800047FA
0x180004700  mov     r9, [rsp+4B0h+lpsz]
0x180004705  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x18000470c  mov     edx, 104h; unsigned __int64
0x180004711  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180004718  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000471d  mov     ebx, eax
0x18000471f  test    eax, eax
0x180004721  js      loc_1800047FA
0x180004727  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x18000472c  lea     rax, [rsp+4B0h+hKey]
0x180004731  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180004736  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x18000473d  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180004742  xor     r9d, r9d; lpClass
0x180004745  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x18000474d  xor     r8d, r8d; Reserved
0x180004750  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180004757  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x18000475b  call    cs:__imp_RegCreateKeyExW
0x180004761  mov     ebx, eax
0x180004763  test    eax, eax
0x180004765  jle     short loc_18000476C
0x180004767  movzx   ebx, ax
0x18000476a  or      ebx, esi
0x18000476c  test    ebx, ebx
0x18000476e  js      loc_1800047FA
0x180004774  lea     rcx, [rsp+4B0h+Filename]
0x180004779  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000477d  inc     rax
0x180004780  cmp     [rcx+rax*2], di
0x180004784  jnz     short loc_18000477D
0x180004786  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000478b  lea     eax, ds:2[rax*2]
0x180004792  mov     [rsp+4B0h+samDesired], eax; cbData
0x180004796  mov     r9d, 1; dwType
0x18000479c  lea     rax, [rsp+4B0h+Filename]
0x1800047a1  xor     r8d, r8d; Reserved
0x1800047a4  xor     edx, edx; lpValueName
0x1800047a6  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800047ab  call    cs:__imp_RegSetValueExW
0x1800047b1  mov     ebx, eax
0x1800047b3  test    eax, eax
0x1800047b5  jle     short loc_1800047BC
0x1800047b7  movzx   ebx, ax
0x1800047ba  or      ebx, esi
0x1800047bc  test    ebx, ebx
0x1800047be  js      short loc_1800047FA
0x1800047c0  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800047c5  lea     rax, Data; "Both"
0x1800047cc  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x1800047d4  lea     rdx, ValueName; "ThreadingModel"
0x1800047db  mov     r9d, 1; dwType
0x1800047e1  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x1800047e6  xor     r8d, r8d; Reserved
0x1800047e9  call    cs:__imp_RegSetValueExW
0x1800047ef  mov     ebx, eax
0x1800047f1  test    eax, eax
0x1800047f3  jle     short loc_1800047FA
0x1800047f5  movzx   ebx, ax
0x1800047f8  or      ebx, esi
0x1800047fa  mov     rcx, [rsp+4B0h+lpsz]; pv
0x1800047ff  call    cs:__imp_CoTaskMemFree
0x180004805  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000480a  mov     [rsp+4B0h+lpsz], rdi
0x18000480f  test    rcx, rcx
0x180004812  jz      short loc_18000481A
0x180004814  call    cs:__imp_RegCloseKey
0x18000481a  mov     eax, ebx
0x18000481c  mov     rcx, [rbp+3B0h+var_30]
0x180004823  xor     rcx, rsp; StackCookie
0x180004826  call    __security_check_cookie
0x18000482b  add     rsp, 498h
0x180004832  pop     rdi
0x180004833  pop     rsi
0x180004834  pop     rbx
0x180004835  pop     rbp
0x180004836  retn
```
