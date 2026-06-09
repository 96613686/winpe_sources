# CDiskProtection::s_SetPostUninstall(int)

- ea: `0x140014d2c`
- end: `0x140014efd`
- name: `?s_SetPostUninstall@CDiskProtection@@SAJH@Z`
- size: `465`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140007fd0`
- `0x140013794`

## callees

- `0x140014d2c`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140014ee4`
- `ADVAPI32!RegCloseKey` at `0x140014ee4`
- `ADVAPI32!RegCreateKeyExW` at `0x140014d8a`
- `ADVAPI32!RegCreateKeyExW` at `0x140014d8a`
- `ADVAPI32!RegSetValueExW` at `0x140014e49`
- `ADVAPI32!RegSetValueExW` at `0x140014e49`
- `KERNEL32!IsDebuggerPresent` at `0x140014dda`
- `KERNEL32!IsDebuggerPresent` at `0x140014e9b`
- `KERNEL32!IsDebuggerPresent` at `0x140014dda`
- `KERNEL32!IsDebuggerPresent` at `0x140014e9b`

## string_xrefs

- `0x140014db0`: `CDiskProtection::s_SetPostUninstall`
- `0x140014e71`: `CDiskProtection::s_SetPostUninstall`
- `0x140014e31`: `PostUninstall`
- `0x140014d4f`: `System\CurrentControlSet\Services\WMS\Parameters\`

## pseudocode

```c
__int64 __fastcall CDiskProtection::s_SetPostUninstall(int a1)
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  __int64 v3; // r9
  __int64 v4; // r8
  LSTATUS v5; // eax
  __int64 v7; // [rsp+30h] [rbp-38h]
  __int64 v8; // [rsp+38h] [rbp-30h]
  BOOL Data; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  Data = a1 != 0;
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x680u,
      L"CDiskProtection::s_SetPostUninstall",
      L"CBRAEx",
      L"err == 0L",
      v2);
    if ( IsDebuggerPresent() )
    {
      v3 = 1664;
LABEL_6:
      LODWORD(v8) = v2;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v3,
        L"CDiskProtection::s_SetPostUninstall",
        L"CBRAEx",
        L"err == 0L",
        v8);
      goto LABEL_16;
    }
    v4 = 1664;
  }
  else
  {
    v2 = 0;
    v5 = RegSetValueExW(hKey, L"PostUninstall", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v5 )
      goto LABEL_16;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    else
      v2 = v5;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x683u,
      L"CDiskProtection::s_SetPostUninstall",
      L"CBRAEx",
      L"err == 0L",
      v2);
    if ( IsDebuggerPresent() )
    {
      v3 = 1667;
      goto LABEL_6;
    }
    v4 = 1667;
  }
  LODWORD(v7) = v2;
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
    v4,
    L"CDiskProtection::s_SetPostUninstall",
    L"CBRAEx",
    L"err == 0L",
    v7);
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x140014d2c  mov     r11, rsp
0x140014d2f  mov     [r11+18h], rbx
0x140014d33  push    rbp
0x140014d34  push    rsi
0x140014d35  push    r14
0x140014d37  sub     rsp, 50h
0x140014d3b  xor     eax, eax
0x140014d3d  mov     qword ptr [r11-28h], 0
0x140014d45  test    ecx, ecx
0x140014d47  mov     qword ptr [r11+10h], 0
0x140014d4f  lea     rdx, ?s_szServiceParametersKey@CDiskProtection@@1QBGB; "System\\CurrentControlSet\\Services\\WM"...
0x140014d56  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140014d5d  setnz   al
0x140014d60  xor     r9d, r9d; lpClass
0x140014d63  mov     [rsp+68h+Data], eax
0x140014d67  xor     r8d, r8d; Reserved
0x140014d6a  lea     rax, [r11+10h]
0x140014d6e  mov     [r11-30h], rax
0x140014d72  mov     qword ptr [r11-38h], 0
0x140014d7a  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x140014d82  mov     [rsp+68h+dwOptions], 0; dwOptions
0x140014d8a  call    cs:__imp_RegCreateKeyExW
0x140014d90  mov     ebx, eax
0x140014d92  test    eax, eax
0x140014d94  jz      loc_140014E25
0x140014d9a  jle     short loc_140014DA5
0x140014d9c  movzx   ebx, ax
0x140014d9f  or      ebx, 80070000h
0x140014da5  lea     r14, aCbraex; "CBRAEx"
0x140014dac  mov     [rsp+68h+samDesired], ebx; int
0x140014db0  lea     rsi, aCdiskprotectio_107; "CDiskProtection::s_SetPostUninstall"
0x140014db7  mov     r9, r14; unsigned __int16 *
0x140014dba  lea     rbp, aErr0l; "err == 0L"
0x140014dc1  mov     r8, rsi; unsigned __int16 *
0x140014dc4  mov     edx, 680h; unsigned int
0x140014dc9  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x140014dce  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140014dd5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140014dda  call    cs:__imp_IsDebuggerPresent
0x140014de0  test    eax, eax
0x140014de2  jz      short loc_140014E1A
0x140014de4  mov     r9d, 680h
0x140014dea  mov     dword ptr [rsp+68h+var_30], ebx
0x140014dee  lea     r8, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140014df5  mov     [rsp+68h+var_38], rbp
0x140014dfa  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140014e01  mov     qword ptr [rsp+68h+samDesired], r14
0x140014e06  mov     ecx, 2; unsigned __int8
0x140014e0b  mov     qword ptr [rsp+68h+dwOptions], rsi
0x140014e10  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140014e15  jmp     loc_140014EDA
0x140014e1a  mov     r8d, 680h
0x140014e20  jmp     loc_140014EB6
0x140014e25  mov     rcx, [rsp+68h+hKey]; hKey
0x140014e2a  lea     rax, [rsp+68h+Data]
0x140014e2f  xor     ebx, ebx
0x140014e31  lea     rdx, ?s_szPostUninstallRegValueName@CDiskProtection@@1QBGB; "PostUninstall"
0x140014e38  xor     r8d, r8d; Reserved
0x140014e3b  lea     r9d, [rbx+4]; dwType
0x140014e3f  mov     [rsp+68h+samDesired], r9d; cbData
0x140014e44  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x140014e49  call    cs:__imp_RegSetValueExW
0x140014e4f  test    eax, eax
0x140014e51  jz      loc_140014EDA
0x140014e57  jg      short loc_140014E5D
0x140014e59  mov     ebx, eax
0x140014e5b  jmp     short loc_140014E66
0x140014e5d  movzx   ebx, ax
0x140014e60  or      ebx, 80070000h
0x140014e66  lea     r14, aCbraex; "CBRAEx"
0x140014e6d  mov     [rsp+68h+samDesired], ebx; int
0x140014e71  lea     rsi, aCdiskprotectio_107; "CDiskProtection::s_SetPostUninstall"
0x140014e78  mov     r9, r14; unsigned __int16 *
0x140014e7b  lea     rbp, aErr0l; "err == 0L"
0x140014e82  mov     r8, rsi; unsigned __int16 *
0x140014e85  mov     edx, 683h; unsigned int
0x140014e8a  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x140014e8f  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140014e96  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140014e9b  call    cs:__imp_IsDebuggerPresent
0x140014ea1  test    eax, eax
0x140014ea3  jz      short loc_140014EB0
0x140014ea5  mov     r9d, 683h
0x140014eab  jmp     loc_140014DEA
0x140014eb0  mov     r8d, 683h
0x140014eb6  mov     dword ptr [rsp+68h+var_38], ebx
0x140014eba  lea     rdx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140014ec1  mov     qword ptr [rsp+68h+samDesired], rbp
0x140014ec6  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140014ecd  mov     r9, rsi
0x140014ed0  mov     qword ptr [rsp+68h+dwOptions], r14
0x140014ed5  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140014eda  mov     rcx, [rsp+68h+hKey]; hKey
0x140014edf  test    rcx, rcx
0x140014ee2  jz      short loc_140014EEA
0x140014ee4  call    cs:__imp_RegCloseKey
0x140014eea  mov     eax, ebx
0x140014eec  mov     rbx, [rsp+68h+arg_10]
0x140014ef4  add     rsp, 50h
0x140014ef8  pop     r14
0x140014efa  pop     rsi
0x140014efb  pop     rbp
0x140014efc  retn
```
