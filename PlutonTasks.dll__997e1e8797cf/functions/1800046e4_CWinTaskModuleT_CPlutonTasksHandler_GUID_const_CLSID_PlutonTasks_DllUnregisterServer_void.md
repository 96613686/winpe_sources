# CWinTaskModuleT<CPlutonTasksHandler,&_GUID const CLSID_PlutonTasks>::DllUnregisterServer(void)

- ea: `0x1800046e4`
- end: `0x180004884`
- name: `?DllUnregisterServer@?$CWinTaskModuleT@VCPlutonTasksHandler@@$1?CLSID_PlutonTasks@@3U_GUID@@B@@QEAAJXZ`
- size: `416`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009340`

## callees

- `0x180001e00`
- `0x180002858`
- `0x1800046e4`
- `0x180007d1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000473f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000473f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004858`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004858`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800047dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004844`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800047dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004844`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800047c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180004829`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800047c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180004829`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004793`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004804`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004793`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004804`

## string_xrefs

- `0x180004754`: `CLSID\\%s`
- `0x1800047f6`: `CLSID`

## pseudocode

```c
__int64 CWinTaskModuleT<CPlutonTasksHandler,&_GUID const CLSID_PlutonTasks>::DllUnregisterServer()
{
  int v0; // ebx
  LSTATUS v1; // eax
  LSTATUS v2; // eax
  LSTATUS v3; // eax
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  lpsz = 0;
  v0 = StringFromCLSID(&CLSID_PlutonTasks, &lpsz);
  if ( v0 >= 0 )
  {
    v0 = StringCchPrintfW(SubKey, 0x104u, L"CLSID\\\\%s", lpsz);
    if ( v0 >= 0 )
    {
      v1 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2000000u, &hKey);
      v0 = v1;
      if ( v1 > 0 )
        v0 = (unsigned __int16)v1 | 0x80070000;
      if ( v0 >= 0 )
      {
        v2 = RegDeleteKeyExW(hKey, L"InprocServer32", 0, 0);
        v0 = v2;
        if ( v2 > 0 )
          v0 = (unsigned __int16)v2 | 0x80070000;
        if ( v0 >= 0 )
        {
          RegCloseKey(hKey);
          v3 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x2000000u, &hKey);
          v0 = v3;
          if ( v3 > 0 )
            v0 = (unsigned __int16)v3 | 0x80070000;
          if ( v0 >= 0 )
          {
            v4 = RegDeleteKeyExW(hKey, lpsz, 0, 0);
            v0 = v4;
            if ( v4 > 0 )
              v0 = (unsigned __int16)v4 | 0x80070000;
          }
        }
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CoTaskMemFree(lpsz);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1800046e4  mov     [rsp-8+arg_0], rbx
0x1800046e9  mov     [rsp-8+arg_8], rsi
0x1800046ee  push    rbp
0x1800046ef  lea     rbp, [rsp-160h]
0x1800046f7  sub     rsp, 260h
0x1800046fe  mov     rax, cs:__security_cookie
0x180004705  xor     rax, rsp
0x180004708  mov     [rbp+160h+var_10], rax
0x18000470f  xor     edx, edx; Val
0x180004711  mov     [rsp+260h+hKey], 0
0x18000471a  mov     r8d, 208h; Size
0x180004720  lea     rcx, [rsp+260h+SubKey]; void *
0x180004725  call    memset_0
0x18000472a  lea     rdx, [rsp+260h+lpsz]; lplpsz
0x18000472f  mov     [rsp+260h+lpsz], 0
0x180004738  lea     rcx, CLSID_PlutonTasks; rclsid
0x18000473f  call    cs:__imp_StringFromCLSID
0x180004745  mov     ebx, eax
0x180004747  test    eax, eax
0x180004749  js      loc_18000483A
0x18000474f  mov     r9, [rsp+260h+lpsz]
0x180004754  lea     r8, aClsidS; "CLSID\\\\%s"
0x18000475b  mov     edx, 104h; unsigned __int64
0x180004760  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x180004765  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000476a  mov     ebx, eax
0x18000476c  test    eax, eax
0x18000476e  js      loc_18000483A
0x180004774  lea     rax, [rsp+260h+hKey]
0x180004779  mov     r9d, 2000000h; samDesired
0x18000477f  xor     r8d, r8d; ulOptions
0x180004782  mov     [rsp+260h+phkResult], rax; phkResult
0x180004787  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x18000478c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180004793  call    cs:__imp_RegOpenKeyExW
0x180004799  mov     ebx, eax
0x18000479b  mov     esi, 80070000h
0x1800047a0  test    eax, eax
0x1800047a2  jle     short loc_1800047A9
0x1800047a4  movzx   ebx, ax
0x1800047a7  or      ebx, esi
0x1800047a9  test    ebx, ebx
0x1800047ab  js      loc_18000483A
0x1800047b1  mov     rcx, [rsp+260h+hKey]; hKey
0x1800047b6  lea     rdx, SubKey; "InprocServer32"
0x1800047bd  xor     r9d, r9d; Reserved
0x1800047c0  xor     r8d, r8d; samDesired
0x1800047c3  call    cs:__imp_RegDeleteKeyExW
0x1800047c9  mov     ebx, eax
0x1800047cb  test    eax, eax
0x1800047cd  jle     short loc_1800047D4
0x1800047cf  movzx   ebx, ax
0x1800047d2  or      ebx, esi
0x1800047d4  test    ebx, ebx
0x1800047d6  js      short loc_18000483A
0x1800047d8  mov     rcx, [rsp+260h+hKey]; hKey
0x1800047dd  call    cs:__imp_RegCloseKey
0x1800047e3  lea     rax, [rsp+260h+hKey]
0x1800047e8  mov     r9d, 2000000h; samDesired
0x1800047ee  xor     r8d, r8d; ulOptions
0x1800047f1  mov     [rsp+260h+phkResult], rax; phkResult
0x1800047f6  lea     rdx, aClsid; "CLSID"
0x1800047fd  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180004804  call    cs:__imp_RegOpenKeyExW
0x18000480a  mov     ebx, eax
0x18000480c  test    eax, eax
0x18000480e  jle     short loc_180004815
0x180004810  movzx   ebx, ax
0x180004813  or      ebx, esi
0x180004815  test    ebx, ebx
0x180004817  js      short loc_18000483A
0x180004819  mov     rdx, [rsp+260h+lpsz]; lpSubKey
0x18000481e  xor     r9d, r9d; Reserved
0x180004821  mov     rcx, [rsp+260h+hKey]; hKey
0x180004826  xor     r8d, r8d; samDesired
0x180004829  call    cs:__imp_RegDeleteKeyExW
0x18000482f  mov     ebx, eax
0x180004831  test    eax, eax
0x180004833  jle     short loc_18000483A
0x180004835  movzx   ebx, ax
0x180004838  or      ebx, esi
0x18000483a  mov     rcx, [rsp+260h+hKey]; hKey
0x18000483f  test    rcx, rcx
0x180004842  jz      short loc_180004853
0x180004844  call    cs:__imp_RegCloseKey
0x18000484a  mov     [rsp+260h+hKey], 0
0x180004853  mov     rcx, [rsp+260h+lpsz]; pv
0x180004858  call    cs:__imp_CoTaskMemFree
0x18000485e  mov     eax, ebx
0x180004860  mov     rcx, [rbp+160h+var_10]
0x180004867  xor     rcx, rsp; StackCookie
0x18000486a  call    __security_check_cookie
0x18000486f  lea     r11, [rsp+260h+var_s0]
0x180004877  mov     rbx, [r11+10h]
0x18000487b  mov     rsi, [r11+18h]
0x18000487f  mov     rsp, r11
0x180004882  pop     rbp
0x180004883  retn
```
