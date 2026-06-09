# CWmsWebService::s_DeleteWebServiceLoopback(ushort *)

- ea: `0x14004c52c`
- end: `0x14004c72f`
- name: `?s_DeleteWebServiceLoopback@CWmsWebService@@CAJPEAG@Z`
- size: `515`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14004823c`

## callees

- `0x14004c52c`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14004c5e2`
- `ADVAPI32!RegCloseKey` at `0x14004c71a`
- `ADVAPI32!RegCloseKey` at `0x14004c5e2`
- `ADVAPI32!RegCloseKey` at `0x14004c71a`
- `ADVAPI32!RegCreateKeyExW` at `0x14004c586`
- `ADVAPI32!RegCreateKeyExW` at `0x14004c62f`
- `ADVAPI32!RegCreateKeyExW` at `0x14004c586`
- `ADVAPI32!RegCreateKeyExW` at `0x14004c62f`
- `ADVAPI32!RegDeleteTreeW` at `0x14004c5b3`
- `ADVAPI32!RegDeleteTreeW` at `0x14004c65b`
- `ADVAPI32!RegDeleteTreeW` at `0x14004c5b3`
- `ADVAPI32!RegDeleteTreeW` at `0x14004c65b`
- `KERNEL32!IsDebuggerPresent` at `0x14004c6b4`
- `KERNEL32!IsDebuggerPresent` at `0x14004c6b4`

## string_xrefs

- `0x14004c693`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x14004c689`: `CWmsWebService::s_DeleteWebServiceLoopback`

## pseudocode

```c
__int64 __fastcall CWmsWebService::s_DeleteWebServiceLoopback(LPCWSTR lpSubKey)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // r12d
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-58h]
  PHKEY phkResult; // [rsp+38h] [rbp-50h]
  HKEY hKey; // [rsp+98h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows MultiPoint Server\\Managed By Servers",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    v4 = 1399;
  }
  else
  {
    v5 = RegDeleteTreeW(hKey, lpSubKey);
    v3 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      v4 = 1402;
    }
    else
    {
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      v6 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows MultiPoint Server\\Managed Servers",
             0,
             0,
             0,
             0xF003Fu,
             0,
             &hKey,
             0);
      v3 = v6;
      if ( v6 )
      {
        if ( v6 > 0 )
          v3 = (unsigned __int16)v6 | 0x80070000;
        v4 = 1407;
      }
      else
      {
        v3 = 0;
        v7 = RegDeleteTreeW(hKey, lpSubKey);
        if ( !v7 )
          goto LABEL_23;
        if ( v7 > 0 )
          v3 = (unsigned __int16)v7 | 0x80070000;
        else
          v3 = v7;
        v4 = 1410;
      }
    }
  }
  LOGASSERTHR(
    L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
    v4,
    L"CWmsWebService::s_DeleteWebServiceLoopback",
    L"CBRAEx",
    L"err == 0L",
    v3);
  if ( IsDebuggerPresent() )
  {
    LODWORD(phkResult) = v3;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      v4,
      L"CWmsWebService::s_DeleteWebServiceLoopback",
      L"CBRAEx",
      L"err == 0L",
      phkResult);
  }
  else
  {
    LODWORD(lpSecurityAttributes) = v3;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      v4,
      L"CWmsWebService::s_DeleteWebServiceLoopback",
      L"CBRAEx",
      L"err == 0L",
      lpSecurityAttributes);
  }
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x14004c52c  mov     r11, rsp
0x14004c52f  push    rbx
0x14004c530  push    rbp
0x14004c531  push    rsi
0x14004c532  push    rdi
0x14004c533  push    r12
0x14004c535  push    r14
0x14004c537  sub     rsp, 58h
0x14004c53b  mov     qword ptr [r11-48h], 0
0x14004c543  lea     rax, [r11+10h]
0x14004c547  mov     [r11-50h], rax
0x14004c54b  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows MultiPoint"...
0x14004c552  mov     qword ptr [r11-58h], 0
0x14004c55a  mov     rdi, rcx
0x14004c55d  mov     esi, 0F003Fh
0x14004c562  mov     qword ptr [r11+10h], 0
0x14004c56a  mov     rbp, 0FFFFFFFF80000002h
0x14004c571  mov     [rsp+88h+samDesired], esi; samDesired
0x14004c575  xor     r9d, r9d; lpClass
0x14004c578  mov     [rsp+88h+dwOptions], 0; dwOptions
0x14004c580  xor     r8d, r8d; Reserved
0x14004c583  mov     rcx, rbp; hKey
0x14004c586  call    cs:__imp_RegCreateKeyExW
0x14004c58c  mov     ebx, eax
0x14004c58e  test    eax, eax
0x14004c590  jz      short loc_14004C5A8
0x14004c592  jle     short loc_14004C59D
0x14004c594  movzx   ebx, ax
0x14004c597  or      ebx, 80070000h
0x14004c59d  mov     r12d, 577h
0x14004c5a3  jmp     loc_14004C67E
0x14004c5a8  mov     rcx, [rsp+88h+hKey]; hKey
0x14004c5b0  mov     rdx, rdi; lpSubKey
0x14004c5b3  call    cs:__imp_RegDeleteTreeW
0x14004c5b9  mov     ebx, eax
0x14004c5bb  test    eax, eax
0x14004c5bd  jz      short loc_14004C5D5
0x14004c5bf  jle     short loc_14004C5CA
0x14004c5c1  movzx   ebx, ax
0x14004c5c4  or      ebx, 80070000h
0x14004c5ca  mov     r12d, 57Ah
0x14004c5d0  jmp     loc_14004C67E
0x14004c5d5  mov     rcx, [rsp+88h+hKey]; hKey
0x14004c5dd  test    rcx, rcx
0x14004c5e0  jz      short loc_14004C5F4
0x14004c5e2  call    cs:__imp_RegCloseKey
0x14004c5e8  mov     [rsp+88h+hKey], 0
0x14004c5f4  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x14004c5fd  lea     rax, [rsp+88h+hKey]
0x14004c605  mov     [rsp+88h+phkResult], rax; phkResult
0x14004c60a  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows MultiPoint"...
0x14004c611  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14004c61a  xor     r9d, r9d; lpClass
0x14004c61d  mov     [rsp+88h+samDesired], esi; samDesired
0x14004c621  xor     r8d, r8d; Reserved
0x14004c624  mov     rcx, rbp; hKey
0x14004c627  mov     [rsp+88h+dwOptions], 0; dwOptions
0x14004c62f  call    cs:__imp_RegCreateKeyExW
0x14004c635  mov     ebx, eax
0x14004c637  test    eax, eax
0x14004c639  jz      short loc_14004C64E
0x14004c63b  jle     short loc_14004C646
0x14004c63d  movzx   ebx, ax
0x14004c640  or      ebx, 80070000h
0x14004c646  mov     r12d, 57Fh
0x14004c64c  jmp     short loc_14004C67E
0x14004c64e  mov     rcx, [rsp+88h+hKey]; hKey
0x14004c656  mov     rdx, rdi; lpSubKey
0x14004c659  xor     ebx, ebx
0x14004c65b  call    cs:__imp_RegDeleteTreeW
0x14004c661  test    eax, eax
0x14004c663  jz      loc_14004C70D
0x14004c669  jg      short loc_14004C66F
0x14004c66b  mov     ebx, eax
0x14004c66d  jmp     short loc_14004C678
0x14004c66f  movzx   ebx, ax
0x14004c672  or      ebx, 80070000h
0x14004c678  mov     r12d, 582h
0x14004c67e  lea     r14, aCbraex; "CBRAEx"
0x14004c685  mov     [rsp+88h+samDesired], ebx; int
0x14004c689  lea     rsi, aCwmswebservice_82; "CWmsWebService::s_DeleteWebServiceLoopb"...
0x14004c690  mov     r9, r14; unsigned __int16 *
0x14004c693  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004c69a  mov     r8, rsi; unsigned __int16 *
0x14004c69d  lea     rbp, aErr0l; "err == 0L"
0x14004c6a4  mov     rcx, rdi; unsigned __int16 *
0x14004c6a7  mov     edx, r12d; unsigned int
0x14004c6aa  mov     qword ptr [rsp+88h+dwOptions], rbp; unsigned __int16 *
0x14004c6af  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14004c6b4  call    cs:__imp_IsDebuggerPresent
0x14004c6ba  test    eax, eax
0x14004c6bc  jz      short loc_14004C6EA
0x14004c6be  mov     dword ptr [rsp+88h+phkResult], ebx
0x14004c6c2  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14004c6c9  mov     [rsp+88h+lpSecurityAttributes], rbp
0x14004c6ce  mov     r9d, r12d
0x14004c6d1  mov     qword ptr [rsp+88h+samDesired], r14
0x14004c6d6  mov     r8, rdi
0x14004c6d9  mov     ecx, 2; unsigned __int8
0x14004c6de  mov     qword ptr [rsp+88h+dwOptions], rsi
0x14004c6e3  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14004c6e8  jmp     short loc_14004C70D
0x14004c6ea  mov     dword ptr [rsp+88h+lpSecurityAttributes], ebx
0x14004c6ee  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14004c6f5  mov     qword ptr [rsp+88h+samDesired], rbp
0x14004c6fa  mov     r9, rsi
0x14004c6fd  mov     r8d, r12d
0x14004c700  mov     qword ptr [rsp+88h+dwOptions], r14
0x14004c705  mov     rdx, rdi
0x14004c708  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14004c70d  mov     rcx, [rsp+88h+hKey]; hKey
0x14004c715  test    rcx, rcx
0x14004c718  jz      short loc_14004C720
0x14004c71a  call    cs:__imp_RegCloseKey
0x14004c720  mov     eax, ebx
0x14004c722  add     rsp, 58h
0x14004c726  pop     r14
0x14004c728  pop     r12
0x14004c72a  pop     rdi
0x14004c72b  pop     rsi
0x14004c72c  pop     rbp
0x14004c72d  pop     rbx
0x14004c72e  retn
```
