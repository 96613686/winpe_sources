# VmlDebugSetDefaultTraceFilter(void)

- ea: `0x14000d65c`
- end: `0x14000d8fa`
- name: `?VmlDebugSetDefaultTraceFilter@@YAXXZ`
- size: `670`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400144a0`
- `0x140014ac0`

## callees

- `0x140002310`
- `0x1400079b8`
- `0x14000d65c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d6d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d70b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d814`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d6d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d70b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000d814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000d889`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000d8c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000d8d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000d889`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000d8c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000d8d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d74e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d77f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d7b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d7e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d861`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d8ba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d74e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d77f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d7b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d7e1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d861`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000d8ba`

## pseudocode

```c
void VmlDebugSetDefaultTraceFilter(void)
{
  __int64 i; // rcx
  int j; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-29h] BYREF
  int pvData; // [rsp+44h] [rbp-25h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-11h] BYREF
  volatile __int64 *v7; // [rsp+60h] [rbp-9h] BYREF
  WCHAR Value[12]; // [rsp+68h] [rbp-1h] BYREF

  g_TraceLevel = 2;
  for ( i = 0; i != 32; ++i )
    _InterlockedExchange64((volatile __int64 *)&(&g_TraceEnabled)[i], qword_140027DF0[i]);
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
          0,
          0x20019u,
          &hKey) )
  {
    pvData = 0;
    pcbData = 0;
    v7 = 0;
    hkey = 0;
    if ( !RegOpenKeyExW(hKey, L"VML", 0, 0x20019u, &hkey) )
    {
      pcbData = 4;
      RegGetValueW(hkey, 0, L"TraceFlags", 0x10u, 0, &pvData, &pcbData);
      pcbData = 4;
      RegGetValueW(hkey, 0, L"StopLevel", 0x10u, 0, &pvData, &pcbData);
      pcbData = 4;
      RegGetValueW(hkey, 0, L"DebugBreakEnabled", 0x10u, 0, &pvData, &pcbData);
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"TraceLevel", 0x10u, 0, &pvData, &pcbData) )
        g_TraceLevel = pvData;
      phkResult = 0;
      if ( !RegOpenKeyExW(hkey, L"TraceLevelsEnabled", 0, 0x20019u, &phkResult) )
      {
        for ( j = 0; j < 32; ++j )
        {
          swprintf_s<10>(Value, L"Trace%i", (unsigned int)j);
          pcbData = 8;
          if ( !RegGetValueW(phkResult, 0, Value, 0x40u, 0, &v7, &pcbData) )
            (&g_TraceEnabled)[j] = v7;
        }
      }
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    pcbData = 4;
    RegGetValueW(hKey, 0, L"ClientAssertMask", 0x10u, 0, &pvData, &pcbData);
    if ( hkey )
      RegCloseKey(hkey);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x14000d65c  push    rbp
0x14000d65e  push    rbx
0x14000d65f  push    rsi
0x14000d660  push    rdi
0x14000d661  push    r14
0x14000d663  push    r15
0x14000d665  lea     rbp, [rsp-2Fh]
0x14000d66a  sub     rsp, 98h
0x14000d671  mov     rax, cs:__security_cookie
0x14000d678  xor     rax, rsp
0x14000d67b  mov     [rbp+57h+var_40], rax
0x14000d67f  mov     eax, 2
0x14000d684  lea     rsi, __ImageBase
0x14000d68b  xor     edi, edi
0x14000d68d  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x14000d694  mov     ecx, edi
0x14000d696  mov     rax, ds:rva qword_140027DF0[rsi+rcx*8]
0x14000d69e  xchg    rax, rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8]; __int64 volatile near * volatile g_TraceEnabled ...
0x14000d6a6  inc     rcx
0x14000d6a9  cmp     rcx, 20h ; ' '
0x14000d6ad  jnz     short loc_14000D696
0x14000d6af  lea     rax, [rbp+57h+hKey]
0x14000d6b3  mov     [rbp+57h+hKey], rdi
0x14000d6b7  mov     ebx, 20019h
0x14000d6bc  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14000d6c1  mov     r9d, ebx; samDesired
0x14000d6c4  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14000d6cb  xor     r8d, r8d; ulOptions
0x14000d6ce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000d6d5  call    cs:__imp_RegOpenKeyExW
0x14000d6db  test    eax, eax
0x14000d6dd  jnz     loc_14000D8CF
0x14000d6e3  mov     rcx, [rbp+57h+hKey]; hKey
0x14000d6e7  lea     rax, [rbp+57h+hkey]
0x14000d6eb  mov     r9d, ebx; samDesired
0x14000d6ee  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14000d6f3  xor     r8d, r8d; ulOptions
0x14000d6f6  mov     [rbp+57h+var_7C], edi
0x14000d6f9  lea     rdx, ?g_VmlRegistryKeyName@Vml@@3QBGB; "VML"
0x14000d700  mov     [rbp+57h+var_80], edi
0x14000d703  mov     [rbp+57h+var_60], rdi
0x14000d707  mov     [rbp+57h+hkey], rdi
0x14000d70b  call    cs:__imp_RegOpenKeyExW
0x14000d711  mov     r14d, 4
0x14000d717  lea     r15d, [r14+0Ch]
0x14000d71b  test    eax, eax
0x14000d71d  jnz     loc_14000D88F
0x14000d723  mov     rcx, [rbp+57h+hkey]; hkey
0x14000d727  lea     rax, [rbp+57h+var_80]
0x14000d72b  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14000d730  lea     r8, Value; "TraceFlags"
0x14000d737  lea     rax, [rbp+57h+var_7C]
0x14000d73b  mov     [rbp+57h+var_80], r14d
0x14000d73f  mov     [rsp+0C0h+pvData], rax; pvData
0x14000d744  mov     r9d, r15d; dwFlags
0x14000d747  xor     edx, edx; lpSubKey
0x14000d749  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14000d74e  call    cs:__imp_RegGetValueW
0x14000d754  mov     rcx, [rbp+57h+hkey]; hkey
0x14000d758  lea     rax, [rbp+57h+var_80]
0x14000d75c  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14000d761  lea     r8, aStoplevel; "StopLevel"
0x14000d768  lea     rax, [rbp+57h+var_7C]
0x14000d76c  mov     [rbp+57h+var_80], r14d
0x14000d770  mov     [rsp+0C0h+pvData], rax; pvData
0x14000d775  mov     r9d, r15d; dwFlags
0x14000d778  xor     edx, edx; lpSubKey
0x14000d77a  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14000d77f  call    cs:__imp_RegGetValueW
0x14000d785  mov     rcx, [rbp+57h+hkey]; hkey
0x14000d789  lea     rax, [rbp+57h+var_80]
0x14000d78d  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14000d792  lea     r8, aDebugbreakenab; "DebugBreakEnabled"
0x14000d799  lea     rax, [rbp+57h+var_7C]
0x14000d79d  mov     [rbp+57h+var_80], r14d
0x14000d7a1  mov     [rsp+0C0h+pvData], rax; pvData
0x14000d7a6  mov     r9d, r15d; dwFlags
0x14000d7a9  xor     edx, edx; lpSubKey
0x14000d7ab  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14000d7b0  call    cs:__imp_RegGetValueW
0x14000d7b6  mov     rcx, [rbp+57h+hkey]; hkey
0x14000d7ba  lea     rax, [rbp+57h+var_80]
0x14000d7be  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14000d7c3  lea     r8, aTracelevel; "TraceLevel"
0x14000d7ca  lea     rax, [rbp+57h+var_7C]
0x14000d7ce  mov     [rbp+57h+var_80], r14d
0x14000d7d2  mov     [rsp+0C0h+pvData], rax; pvData
0x14000d7d7  mov     r9d, r15d; dwFlags
0x14000d7da  xor     edx, edx; lpSubKey
0x14000d7dc  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14000d7e1  call    cs:__imp_RegGetValueW
0x14000d7e7  test    eax, eax
0x14000d7e9  jnz     short loc_14000D7F6
0x14000d7eb  movzx   eax, word ptr [rbp+57h+var_7C]
0x14000d7ef  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x14000d7f6  mov     rcx, [rbp+57h+hkey]; hKey
0x14000d7fa  lea     rax, [rbp+57h+var_68]
0x14000d7fe  mov     r9d, ebx; samDesired
0x14000d801  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14000d806  xor     r8d, r8d; ulOptions
0x14000d809  mov     [rbp+57h+var_68], rdi
0x14000d80d  lea     rdx, SubKey; "TraceLevelsEnabled"
0x14000d814  call    cs:__imp_RegOpenKeyExW
0x14000d81a  test    eax, eax
0x14000d81c  jnz     short loc_14000D880
0x14000d81e  mov     ebx, edi
0x14000d820  mov     r8d, ebx
0x14000d823  lea     rdx, aTraceI; "Trace%i"
0x14000d82a  lea     rcx, [rbp+57h+Value]
0x14000d82e  call    ??$swprintf_s@$09@@YAHAEAY09GPEBGZZ; swprintf_s<10>(ushort (&)[10],ushort const *,...)
0x14000d833  mov     rcx, [rbp+57h+var_68]; hkey
0x14000d837  lea     rax, [rbp+57h+var_80]
0x14000d83b  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14000d840  lea     r8, [rbp+57h+Value]; lpValue
0x14000d844  lea     rax, [rbp+57h+var_60]
0x14000d848  mov     [rbp+57h+var_80], 8
0x14000d84f  mov     [rsp+0C0h+pvData], rax; pvData
0x14000d854  mov     r9d, 40h ; '@'; dwFlags
0x14000d85a  xor     edx, edx; lpSubKey
0x14000d85c  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14000d861  call    cs:__imp_RegGetValueW
0x14000d867  test    eax, eax
0x14000d869  jnz     short loc_14000D879
0x14000d86b  mov     rax, [rbp+57h+var_60]
0x14000d86f  mov     ecx, ebx
0x14000d871  mov     rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8], rax; __int64 volatile near * volatile g_TraceEnabled ...
0x14000d879  inc     ebx
0x14000d87b  cmp     ebx, 20h ; ' '
0x14000d87e  jl      short loc_14000D820
0x14000d880  mov     rcx, [rbp+57h+var_68]; hKey
0x14000d884  test    rcx, rcx
0x14000d887  jz      short loc_14000D88F
0x14000d889  call    cs:__imp_RegCloseKey
0x14000d88f  mov     rcx, [rbp+57h+hKey]; hkey
0x14000d893  lea     rax, [rbp+57h+var_80]
0x14000d897  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14000d89c  lea     r8, ?g_DvClientAssertsMaskName@@3QBGB; "ClientAssertMask"
0x14000d8a3  lea     rax, [rbp+57h+var_7C]
0x14000d8a7  mov     [rbp+57h+var_80], r14d
0x14000d8ab  mov     [rsp+0C0h+pvData], rax; pvData
0x14000d8b0  mov     r9d, r15d; dwFlags
0x14000d8b3  xor     edx, edx; lpSubKey
0x14000d8b5  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14000d8ba  call    cs:__imp_RegGetValueW
0x14000d8c0  mov     rcx, [rbp+57h+hkey]; hKey
0x14000d8c4  test    rcx, rcx
0x14000d8c7  jz      short loc_14000D8CF
0x14000d8c9  call    cs:__imp_RegCloseKey
0x14000d8cf  mov     rcx, [rbp+57h+hKey]; hKey
0x14000d8d3  test    rcx, rcx
0x14000d8d6  jz      short loc_14000D8DE
0x14000d8d8  call    cs:__imp_RegCloseKey
0x14000d8de  mov     rcx, [rbp+57h+var_40]
0x14000d8e2  xor     rcx, rsp; StackCookie
0x14000d8e5  call    __security_check_cookie
0x14000d8ea  add     rsp, 98h
0x14000d8f1  pop     r15
0x14000d8f3  pop     r14
0x14000d8f5  pop     rdi
0x14000d8f6  pop     rsi
0x14000d8f7  pop     rbx
0x14000d8f8  pop     rbp
0x14000d8f9  retn
```
