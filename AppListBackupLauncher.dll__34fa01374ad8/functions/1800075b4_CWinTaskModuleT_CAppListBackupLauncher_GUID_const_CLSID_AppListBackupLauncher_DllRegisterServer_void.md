# CWinTaskModuleT<CAppListBackupLauncher,&_GUID const CLSID_AppListBackupLauncher>::DllRegisterServer(void)

- ea: `0x1800075b4`
- end: `0x180007797`
- name: `?DllRegisterServer@?$CWinTaskModuleT@VCAppListBackupLauncher@@$1?CLSID_AppListBackupLauncher@@3U_GUID@@B@@QEAAJXZ`
- size: `483`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fa40`

## callees

- `0x180002300`
- `0x180002de0`
- `0x1800075b4`
- `0x18000d290`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000761c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000761c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180007650`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180007650`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000775f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000775f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000762b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000762b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800076bb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800076bb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000770b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007749`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000770b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007749`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007774`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007774`

## string_xrefs

- `0x180007665`: `CLSID\\%s\InprocServer32`
- `0x180007734`: `ThreadingModel`

## pseudocode

```c
__int64 CWinTaskModuleT<CAppListBackupLauncher,&_GUID const CLSID_AppListBackupLauncher>::DllRegisterServer()
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
    v1 = StringFromCLSID(&CLSID_AppListBackupLauncher, &lpsz);
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
0x1800075b4  push    rbp
0x1800075b6  push    rbx
0x1800075b7  push    rsi
0x1800075b8  push    rdi
0x1800075b9  lea     rbp, [rsp-398h]
0x1800075c1  sub     rsp, 498h
0x1800075c8  mov     rax, cs:__security_cookie
0x1800075cf  xor     rax, rsp
0x1800075d2  mov     [rbp+3B0h+var_30], rax
0x1800075d9  mov     ebx, 208h
0x1800075de  lea     rcx, [rsp+4B0h+Filename]; void *
0x1800075e3  xor     edi, edi
0x1800075e5  mov     r8d, ebx; Size
0x1800075e8  xor     edx, edx; Val
0x1800075ea  mov     [rsp+4B0h+hKey], rdi
0x1800075ef  call    memset_0
0x1800075f4  mov     r8d, ebx; Size
0x1800075f7  lea     rcx, [rbp+3B0h+SubKey]; void *
0x1800075fe  xor     edx, edx; Val
0x180007600  call    memset_0
0x180007605  mov     r8d, 104h; nSize
0x18000760b  mov     [rsp+4B0h+lpsz], rdi
0x180007610  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x180007615  lea     rcx, cs:180000000h; hModule
0x18000761c  call    cs:__imp_GetModuleFileNameW
0x180007622  mov     esi, 80070000h
0x180007627  test    eax, eax
0x180007629  jnz     short loc_180007644
0x18000762b  call    cs:__imp_GetLastError
0x180007631  mov     ebx, eax
0x180007633  test    eax, eax
0x180007635  jle     short loc_18000763C
0x180007637  movzx   ebx, ax
0x18000763a  or      ebx, esi
0x18000763c  test    ebx, ebx
0x18000763e  js      loc_18000775A
0x180007644  lea     rdx, [rsp+4B0h+lpsz]; lplpsz
0x180007649  lea     rcx, CLSID_AppListBackupLauncher; rclsid
0x180007650  call    cs:__imp_StringFromCLSID
0x180007656  mov     ebx, eax
0x180007658  test    eax, eax
0x18000765a  js      loc_18000775A
0x180007660  mov     r9, [rsp+4B0h+lpsz]
0x180007665  lea     r8, aClsidSInprocse; "CLSID\\\\%s\\InprocServer32"
0x18000766c  mov     edx, 104h; unsigned __int64
0x180007671  lea     rcx, [rbp+3B0h+SubKey]; unsigned __int16 *
0x180007678  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000767d  mov     ebx, eax
0x18000767f  test    eax, eax
0x180007681  js      loc_18000775A
0x180007687  mov     [rsp+4B0h+lpdwDisposition], rdi; lpdwDisposition
0x18000768c  lea     rax, [rsp+4B0h+hKey]
0x180007691  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180007696  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x18000769d  mov     [rsp+4B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800076a2  xor     r9d, r9d; lpClass
0x1800076a5  mov     [rsp+4B0h+samDesired], 20006h; samDesired
0x1800076ad  xor     r8d, r8d; Reserved
0x1800076b0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800076b7  mov     [rsp+4B0h+dwOptions], edi; dwOptions
0x1800076bb  call    cs:__imp_RegCreateKeyExW
0x1800076c1  mov     ebx, eax
0x1800076c3  test    eax, eax
0x1800076c5  jle     short loc_1800076CC
0x1800076c7  movzx   ebx, ax
0x1800076ca  or      ebx, esi
0x1800076cc  test    ebx, ebx
0x1800076ce  js      loc_18000775A
0x1800076d4  lea     rcx, [rsp+4B0h+Filename]
0x1800076d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800076dd  inc     rax
0x1800076e0  cmp     [rcx+rax*2], di
0x1800076e4  jnz     short loc_1800076DD
0x1800076e6  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800076eb  lea     eax, ds:2[rax*2]
0x1800076f2  mov     [rsp+4B0h+samDesired], eax; cbData
0x1800076f6  mov     r9d, 1; dwType
0x1800076fc  lea     rax, [rsp+4B0h+Filename]
0x180007701  xor     r8d, r8d; Reserved
0x180007704  xor     edx, edx; lpValueName
0x180007706  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x18000770b  call    cs:__imp_RegSetValueExW
0x180007711  mov     ebx, eax
0x180007713  test    eax, eax
0x180007715  jle     short loc_18000771C
0x180007717  movzx   ebx, ax
0x18000771a  or      ebx, esi
0x18000771c  test    ebx, ebx
0x18000771e  js      short loc_18000775A
0x180007720  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180007725  lea     rax, Data; "Both"
0x18000772c  mov     [rsp+4B0h+samDesired], 0Ah; cbData
0x180007734  lea     rdx, ValueName; "ThreadingModel"
0x18000773b  mov     r9d, 1; dwType
0x180007741  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpData
0x180007746  xor     r8d, r8d; Reserved
0x180007749  call    cs:__imp_RegSetValueExW
0x18000774f  mov     ebx, eax
0x180007751  test    eax, eax
0x180007753  jle     short loc_18000775A
0x180007755  movzx   ebx, ax
0x180007758  or      ebx, esi
0x18000775a  mov     rcx, [rsp+4B0h+lpsz]; pv
0x18000775f  call    cs:__imp_CoTaskMemFree
0x180007765  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000776a  mov     [rsp+4B0h+lpsz], rdi
0x18000776f  test    rcx, rcx
0x180007772  jz      short loc_18000777A
0x180007774  call    cs:__imp_RegCloseKey
0x18000777a  mov     eax, ebx
0x18000777c  mov     rcx, [rbp+3B0h+var_30]
0x180007783  xor     rcx, rsp; StackCookie
0x180007786  call    __security_check_cookie
0x18000778b  add     rsp, 498h
0x180007792  pop     rdi
0x180007793  pop     rsi
0x180007794  pop     rbx
0x180007795  pop     rbp
0x180007796  retn
```
