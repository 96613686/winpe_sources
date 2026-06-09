# CWPPLoggerGuidConfig::ReadTraceConfig(void)

- ea: `0x180013970`
- end: `0x180013d8c`
- name: `?ReadTraceConfig@CWPPLoggerGuidConfig@@QEAAJXZ`
- size: `1052`
- prototype: `__int64 __fastcall(CWPPLoggerGuidConfig *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e23c`
- `0x18001e494`
- `0x18001e834`

## callees

- `0x180003f30`
- `0x180013970`
- `0x180017b94`
- `0x18001a280`
- `0x18001ad5c`
- `0x180021188`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800139f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800139f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013a7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013ac3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013b0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013b74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013bb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013c08`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013c51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013c8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013cf3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013d31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013a7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013ac3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013b0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013b74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013bb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013c08`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013c51`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013c8f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013cf3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013d31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013d5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013d5c`

## string_xrefs

- `0x180013a0d`: `error %#x: RegOpenKeyEx(%S) failed`

## pseudocode

```c
__int64 __fastcall CWPPLoggerGuidConfig::ReadTraceConfig(CWPPLoggerGuidConfig *this)
{
  LSTATUS v2; // eax
  signed int v3; // edi
  bool v4; // zf
  int v5; // eax
  __int64 v6; // r9
  unsigned int v7; // eax
  HKEY v8; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ValueName[264]; // [rsp+50h] [rbp-B0h] BYREF

  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  hKey = 0;
  memset_0(ValueName, 0, 0x208u);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    _DbgPrintMessage(1, "error %#x: RegOpenKeyEx(%S) failed", v2, ValueName);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
  }
  else
  {
    v3 = 0;
    StringCbPrintfW(ValueName, 0x208u, L"Debug%s", *((_QWORD *)this + 2));
    cbData = 4;
    if ( !RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) && Type == 4
      || (cbData = 4, !RegQueryValueExW(hKey, L"Debug", 0, &Type, Data, &cbData)) && Type == 4 )
    {
      v4 = *(_DWORD *)Data == 0;
    }
    else
    {
      v4 = (unsigned int)CUtils::IsKernelDebuggerAttached() == 0;
    }
    *((_BYTE *)this + 32) = !v4;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"CaptureStackTrace", 0, &Type, Data, &cbData) || Type != 4 )
    {
      v5 = 0;
      *(_DWORD *)Data = 0;
    }
    else
    {
      v5 = *(_DWORD *)Data;
    }
    v6 = *((_QWORD *)this + 2);
    g_bCaptureObjectStackTrace = v5;
    StringCbPrintfW(ValueName, 0x208u, L"Debug%sFlags", v6);
    cbData = 4;
    if ( RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) || Type != 4 )
    {
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"DebugFlags", 0, &Type, Data, &cbData) || (v7 = *(_DWORD *)Data, Type != 4) )
        v7 = -2;
    }
    else
    {
      v7 = *(_DWORD *)Data;
    }
    v8 = hKey;
    *((_DWORD *)this + 6) = v7;
    g_DebugTraceComponent = v7;
    cbData = 4;
    RegQueryValueExW(v8, L"DebugFlagsEx", 0, &Type, Data, &cbData);
    StringCbPrintfW(ValueName, 0x208u, L"Debug%sLevel", *((_QWORD *)this + 2));
    cbData = 4;
    if ( (RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) || Type != 4)
      && ((cbData = 4, RegQueryValueExW(hKey, L"DebugLevel", 0, &Type, Data, &cbData)) || Type != 4) )
    {
      *((_DWORD *)this + 7) = 16574;
    }
    else
    {
      *((_DWORD *)this + 7) = *(_DWORD *)Data;
    }
    StringCbPrintfW(ValueName, 0x208u, L"Debug%sToDebugger", *((_QWORD *)this + 2));
    cbData = 4;
    *((_BYTE *)this + 33) = (!RegQueryValueExW(hKey, ValueName, 0, &Type, Data, &cbData) && Type == 4
                          || (cbData = 4, !RegQueryValueExW(hKey, L"DebugToDebugger", 0, &Type, Data, &cbData))
                          && Type == 4)
                         && *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013970  mov     [rsp-8+arg_8], rbx
0x180013975  mov     [rsp-8+arg_10], rdi
0x18001397a  push    rbp
0x18001397b  push    r14
0x18001397d  push    r15
0x18001397f  lea     rbp, [rsp-170h]
0x180013987  sub     rsp, 270h
0x18001398e  mov     rax, cs:__security_cookie
0x180013995  xor     rax, rsp
0x180013998  mov     [rbp+180h+var_20], rax
0x18001399f  mov     rbx, rcx
0x1800139a2  mov     [rsp+280h+Type], 0
0x1800139aa  mov     r15d, 208h
0x1800139b0  mov     dword ptr [rsp+280h+Data], 0
0x1800139b8  mov     r8d, r15d; Size
0x1800139bb  mov     [rsp+280h+cbData], 0
0x1800139c3  xor     edx, edx; Val
0x1800139c5  mov     [rsp+280h+hKey], 0
0x1800139ce  lea     rcx, [rsp+280h+ValueName]; void *
0x1800139d3  call    memset_0
0x1800139d8  lea     rax, [rsp+280h+hKey]
0x1800139dd  mov     r9d, 20019h; samDesired
0x1800139e3  xor     r8d, r8d; ulOptions
0x1800139e6  mov     [rsp+280h+phkResult], rax; phkResult
0x1800139eb  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x1800139f2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800139f9  call    cs:__imp_RegOpenKeyExW
0x1800139ff  mov     edi, eax
0x180013a01  test    eax, eax
0x180013a03  jz      short loc_180013A34
0x180013a05  lea     r9, [rsp+280h+ValueName]
0x180013a0a  mov     r8d, eax
0x180013a0d  lea     rdx, aErrorXRegopenk; "error %#x: RegOpenKeyEx(%S) failed"
0x180013a14  mov     ecx, 1; int
0x180013a19  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013a1e  test    edi, edi
0x180013a20  jle     loc_180013D52
0x180013a26  movzx   edi, di
0x180013a29  or      edi, 80070000h
0x180013a2f  jmp     loc_180013D52
0x180013a34  mov     r9, [rbx+10h]
0x180013a38  lea     r8, aDebugS; "Debug%s"
0x180013a3f  mov     rdx, r15; unsigned __int64
0x180013a42  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180013a47  xor     edi, edi
0x180013a49  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013a4e  mov     rcx, [rsp+280h+hKey]; hKey
0x180013a53  lea     rax, [rsp+280h+cbData]
0x180013a58  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180013a5d  lea     r14d, [rdi+4]
0x180013a61  lea     rax, [rsp+280h+Data]
0x180013a66  mov     [rsp+280h+cbData], r14d
0x180013a6b  lea     r9, [rsp+280h+Type]; lpType
0x180013a70  mov     [rsp+280h+phkResult], rax; lpData
0x180013a75  xor     r8d, r8d; lpReserved
0x180013a78  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x180013a7d  call    cs:__imp_RegQueryValueExW
0x180013a83  test    eax, eax
0x180013a85  jnz     short loc_180013A96
0x180013a87  cmp     [rsp+280h+Type], r14d
0x180013a8c  jnz     short loc_180013A96
0x180013a8e  xor     ecx, ecx
0x180013a90  cmp     dword ptr [rsp+280h+Data], ecx
0x180013a94  jmp     short loc_180013ADB
0x180013a96  mov     rcx, [rsp+280h+hKey]; hKey
0x180013a9b  lea     rax, [rsp+280h+cbData]
0x180013aa0  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180013aa5  lea     r9, [rsp+280h+Type]; lpType
0x180013aaa  lea     rax, [rsp+280h+Data]
0x180013aaf  mov     [rsp+280h+cbData], r14d
0x180013ab4  xor     r8d, r8d; lpReserved
0x180013ab7  mov     [rsp+280h+phkResult], rax; lpData
0x180013abc  lea     rdx, aDebug; "Debug"
0x180013ac3  call    cs:__imp_RegQueryValueExW
0x180013ac9  test    eax, eax
0x180013acb  jnz     short loc_180013AD4
0x180013acd  cmp     [rsp+280h+Type], r14d
0x180013ad2  jz      short loc_180013A8E
0x180013ad4  call    ?IsKernelDebuggerAttached@CUtils@@SAHXZ; CUtils::IsKernelDebuggerAttached(void)
0x180013ad9  test    eax, eax
0x180013adb  setnz   cl
0x180013ade  lea     rax, [rsp+280h+cbData]
0x180013ae3  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180013ae8  lea     r9, [rsp+280h+Type]; lpType
0x180013aed  mov     [rbx+20h], cl
0x180013af0  lea     rax, [rsp+280h+Data]
0x180013af5  mov     rcx, [rsp+280h+hKey]; hKey
0x180013afa  lea     rdx, aCapturestacktr; "CaptureStackTrace"
0x180013b01  xor     r8d, r8d; lpReserved
0x180013b04  mov     [rsp+280h+phkResult], rax; lpData
0x180013b09  mov     [rsp+280h+cbData], r14d
0x180013b0e  call    cs:__imp_RegQueryValueExW
0x180013b14  test    eax, eax
0x180013b16  jnz     short loc_180013B25
0x180013b18  cmp     [rsp+280h+Type], r14d
0x180013b1d  jnz     short loc_180013B25
0x180013b1f  mov     eax, dword ptr [rsp+280h+Data]
0x180013b23  jmp     short loc_180013B2B
0x180013b25  xor     eax, eax
0x180013b27  mov     dword ptr [rsp+280h+Data], eax
0x180013b2b  mov     r9, [rbx+10h]
0x180013b2f  lea     r8, aDebugSflags; "Debug%sFlags"
0x180013b36  mov     rdx, r15; unsigned __int64
0x180013b39  mov     cs:?g_bCaptureObjectStackTrace@@3HA, eax; int g_bCaptureObjectStackTrace
0x180013b3f  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180013b44  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013b49  mov     rcx, [rsp+280h+hKey]; hKey
0x180013b4e  lea     rax, [rsp+280h+cbData]
0x180013b53  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180013b58  lea     r9, [rsp+280h+Type]; lpType
0x180013b5d  lea     rax, [rsp+280h+Data]
0x180013b62  mov     [rsp+280h+cbData], r14d
0x180013b67  xor     r8d, r8d; lpReserved
0x180013b6a  mov     [rsp+280h+phkResult], rax; lpData
0x180013b6f  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x180013b74  call    cs:__imp_RegQueryValueExW
0x180013b7a  test    eax, eax
0x180013b7c  jnz     short loc_180013B8B
0x180013b7e  cmp     [rsp+280h+Type], r14d
0x180013b83  jnz     short loc_180013B8B
0x180013b85  mov     eax, dword ptr [rsp+280h+Data]
0x180013b89  jmp     short loc_180013BD2
0x180013b8b  mov     rcx, [rsp+280h+hKey]; hKey
0x180013b90  lea     rax, [rsp+280h+cbData]
0x180013b95  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180013b9a  lea     r9, [rsp+280h+Type]; lpType
0x180013b9f  lea     rax, [rsp+280h+Data]
0x180013ba4  mov     [rsp+280h+cbData], r14d
0x180013ba9  xor     r8d, r8d; lpReserved
0x180013bac  mov     [rsp+280h+phkResult], rax; lpData
0x180013bb1  lea     rdx, aDebugflags; "DebugFlags"
0x180013bb8  call    cs:__imp_RegQueryValueExW
0x180013bbe  test    eax, eax
0x180013bc0  jnz     short loc_180013BCD
0x180013bc2  mov     eax, dword ptr [rsp+280h+Data]
0x180013bc6  cmp     [rsp+280h+Type], r14d
0x180013bcb  jz      short loc_180013BD2
0x180013bcd  mov     eax, 0FFFFFFFEh
0x180013bd2  mov     rcx, [rsp+280h+hKey]; hKey
0x180013bd7  lea     r9, [rsp+280h+Type]; lpType
0x180013bdc  mov     [rbx+18h], eax
0x180013bdf  lea     rdx, aDebugflagsex; "DebugFlagsEx"
0x180013be6  mov     cs:?g_DebugTraceComponent@@3KA, eax; ulong g_DebugTraceComponent
0x180013bec  xor     r8d, r8d; lpReserved
0x180013bef  lea     rax, [rsp+280h+cbData]
0x180013bf4  mov     [rsp+280h+cbData], r14d
0x180013bf9  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180013bfe  lea     rax, [rsp+280h+Data]
0x180013c03  mov     [rsp+280h+phkResult], rax; lpData
0x180013c08  call    cs:__imp_RegQueryValueExW
0x180013c0e  mov     r9, [rbx+10h]
0x180013c12  lea     r8, aDebugSlevel; "Debug%sLevel"
0x180013c19  mov     rdx, r15; unsigned __int64
0x180013c1c  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180013c21  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013c26  mov     rcx, [rsp+280h+hKey]; hKey
0x180013c2b  lea     rax, [rsp+280h+cbData]
0x180013c30  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180013c35  lea     r9, [rsp+280h+Type]; lpType
0x180013c3a  lea     rax, [rsp+280h+Data]
0x180013c3f  mov     [rsp+280h+cbData], r14d
0x180013c44  xor     r8d, r8d; lpReserved
0x180013c47  mov     [rsp+280h+phkResult], rax; lpData
0x180013c4c  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x180013c51  call    cs:__imp_RegQueryValueExW
0x180013c57  test    eax, eax
0x180013c59  jnz     short loc_180013C62
0x180013c5b  cmp     [rsp+280h+Type], r14d
0x180013c60  jz      short loc_180013CA0
0x180013c62  mov     rcx, [rsp+280h+hKey]; hKey
0x180013c67  lea     rax, [rsp+280h+cbData]
0x180013c6c  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180013c71  lea     r9, [rsp+280h+Type]; lpType
0x180013c76  lea     rax, [rsp+280h+Data]
0x180013c7b  mov     [rsp+280h+cbData], r14d
0x180013c80  xor     r8d, r8d; lpReserved
0x180013c83  mov     [rsp+280h+phkResult], rax; lpData
0x180013c88  lea     rdx, aDebuglevel; "DebugLevel"
0x180013c8f  call    cs:__imp_RegQueryValueExW
0x180013c95  test    eax, eax
0x180013c97  jnz     short loc_180013CA9
0x180013c99  cmp     [rsp+280h+Type], r14d
0x180013c9e  jnz     short loc_180013CA9
0x180013ca0  mov     eax, dword ptr [rsp+280h+Data]
0x180013ca4  mov     [rbx+1Ch], eax
0x180013ca7  jmp     short loc_180013CB0
0x180013ca9  mov     dword ptr [rbx+1Ch], 40BEh
0x180013cb0  mov     r9, [rbx+10h]
0x180013cb4  lea     r8, aDebugStodebugg; "Debug%sToDebugger"
0x180013cbb  mov     rdx, r15; unsigned __int64
0x180013cbe  lea     rcx, [rsp+280h+ValueName]; unsigned __int16 *
0x180013cc3  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013cc8  mov     rcx, [rsp+280h+hKey]; hKey
0x180013ccd  lea     rax, [rsp+280h+cbData]
0x180013cd2  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180013cd7  lea     r9, [rsp+280h+Type]; lpType
0x180013cdc  lea     rax, [rsp+280h+Data]
0x180013ce1  mov     [rsp+280h+cbData], r14d
0x180013ce6  xor     r8d, r8d; lpReserved
0x180013ce9  mov     [rsp+280h+phkResult], rax; lpData
0x180013cee  lea     rdx, [rsp+280h+ValueName]; lpValueName
0x180013cf3  call    cs:__imp_RegQueryValueExW
0x180013cf9  test    eax, eax
0x180013cfb  jnz     short loc_180013D04
0x180013cfd  cmp     [rsp+280h+Type], r14d
0x180013d02  jz      short loc_180013D42
0x180013d04  mov     rcx, [rsp+280h+hKey]; hKey
0x180013d09  lea     rax, [rsp+280h+cbData]
0x180013d0e  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180013d13  lea     r9, [rsp+280h+Type]; lpType
0x180013d18  lea     rax, [rsp+280h+Data]
0x180013d1d  mov     [rsp+280h+cbData], r14d
0x180013d22  xor     r8d, r8d; lpReserved
0x180013d25  mov     [rsp+280h+phkResult], rax; lpData
0x180013d2a  lea     rdx, aDebugtodebugge; "DebugToDebugger"
0x180013d31  call    cs:__imp_RegQueryValueExW
0x180013d37  test    eax, eax
0x180013d39  jnz     short loc_180013D4E
0x180013d3b  cmp     [rsp+280h+Type], r14d
0x180013d40  jnz     short loc_180013D4E
0x180013d42  cmp     dword ptr [rsp+280h+Data], edi
0x180013d46  setnz   al
0x180013d49  mov     [rbx+21h], al
0x180013d4c  jmp     short loc_180013D52
0x180013d4e  mov     [rbx+21h], dil
0x180013d52  mov     rcx, [rsp+280h+hKey]; hKey
0x180013d57  test    rcx, rcx
0x180013d5a  jz      short loc_180013D62
0x180013d5c  call    cs:__imp_RegCloseKey
0x180013d62  mov     eax, edi
0x180013d64  mov     rcx, [rbp+180h+var_20]
0x180013d6b  xor     rcx, rsp; StackCookie
0x180013d6e  call    __security_check_cookie
0x180013d73  lea     r11, [rsp+280h+var_10]
0x180013d7b  mov     rbx, [r11+28h]
0x180013d7f  mov     rdi, [r11+30h]
0x180013d83  mov     rsp, r11
0x180013d86  pop     r15
0x180013d88  pop     r14
0x180013d8a  pop     rbp
0x180013d8b  retn
```
