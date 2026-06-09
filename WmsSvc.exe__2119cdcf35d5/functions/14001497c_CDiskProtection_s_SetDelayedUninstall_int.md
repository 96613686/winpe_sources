# CDiskProtection::s_SetDelayedUninstall(int)

- ea: `0x14001497c`
- end: `0x140014b4d`
- name: `?s_SetDelayedUninstall@CDiskProtection@@SAJH@Z`
- size: `465`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140007fd0`
- `0x14000c3b0`
- `0x140013794`

## callees

- `0x14001497c`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140014b34`
- `ADVAPI32!RegCloseKey` at `0x140014b34`
- `ADVAPI32!RegCreateKeyExW` at `0x1400149da`
- `ADVAPI32!RegCreateKeyExW` at `0x1400149da`
- `ADVAPI32!RegSetValueExW` at `0x140014a99`
- `ADVAPI32!RegSetValueExW` at `0x140014a99`
- `KERNEL32!IsDebuggerPresent` at `0x140014a2a`
- `KERNEL32!IsDebuggerPresent` at `0x140014aeb`
- `KERNEL32!IsDebuggerPresent` at `0x140014a2a`
- `KERNEL32!IsDebuggerPresent` at `0x140014aeb`

## string_xrefs

- `0x140014a00`: `CDiskProtection::s_SetDelayedUninstall`
- `0x140014ac1`: `CDiskProtection::s_SetDelayedUninstall`
- `0x140014a81`: `DelayedUninstall`
- `0x14001499f`: `System\CurrentControlSet\Services\WMS\Parameters\`

## pseudocode

```c
__int64 __fastcall CDiskProtection::s_SetDelayedUninstall(int a1)
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
      0x658u,
      L"CDiskProtection::s_SetDelayedUninstall",
      L"CBRAEx",
      L"err == 0L",
      v2);
    if ( IsDebuggerPresent() )
    {
      v3 = 1624;
LABEL_6:
      LODWORD(v8) = v2;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v3,
        L"CDiskProtection::s_SetDelayedUninstall",
        L"CBRAEx",
        L"err == 0L",
        v8);
      goto LABEL_16;
    }
    v4 = 1624;
  }
  else
  {
    v2 = 0;
    v5 = RegSetValueExW(hKey, L"DelayedUninstall", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v5 )
      goto LABEL_16;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    else
      v2 = v5;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x65Bu,
      L"CDiskProtection::s_SetDelayedUninstall",
      L"CBRAEx",
      L"err == 0L",
      v2);
    if ( IsDebuggerPresent() )
    {
      v3 = 1627;
      goto LABEL_6;
    }
    v4 = 1627;
  }
  LODWORD(v7) = v2;
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
    v4,
    L"CDiskProtection::s_SetDelayedUninstall",
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
0x14001497c  mov     r11, rsp
0x14001497f  mov     [r11+18h], rbx
0x140014983  push    rbp
0x140014984  push    rsi
0x140014985  push    r14
0x140014987  sub     rsp, 50h
0x14001498b  xor     eax, eax
0x14001498d  mov     qword ptr [r11-28h], 0
0x140014995  test    ecx, ecx
0x140014997  mov     qword ptr [r11+10h], 0
0x14001499f  lea     rdx, ?s_szServiceParametersKey@CDiskProtection@@1QBGB; "System\\CurrentControlSet\\Services\\WM"...
0x1400149a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400149ad  setnz   al
0x1400149b0  xor     r9d, r9d; lpClass
0x1400149b3  mov     [rsp+68h+Data], eax
0x1400149b7  xor     r8d, r8d; Reserved
0x1400149ba  lea     rax, [r11+10h]
0x1400149be  mov     [r11-30h], rax
0x1400149c2  mov     qword ptr [r11-38h], 0
0x1400149ca  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x1400149d2  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1400149da  call    cs:__imp_RegCreateKeyExW
0x1400149e0  mov     ebx, eax
0x1400149e2  test    eax, eax
0x1400149e4  jz      loc_140014A75
0x1400149ea  jle     short loc_1400149F5
0x1400149ec  movzx   ebx, ax
0x1400149ef  or      ebx, 80070000h
0x1400149f5  lea     r14, aCbraex; "CBRAEx"
0x1400149fc  mov     [rsp+68h+samDesired], ebx; int
0x140014a00  lea     rsi, aCdiskprotectio_180; "CDiskProtection::s_SetDelayedUninstall"
0x140014a07  mov     r9, r14; unsigned __int16 *
0x140014a0a  lea     rbp, aErr0l; "err == 0L"
0x140014a11  mov     r8, rsi; unsigned __int16 *
0x140014a14  mov     edx, 658h; unsigned int
0x140014a19  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x140014a1e  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140014a25  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140014a2a  call    cs:__imp_IsDebuggerPresent
0x140014a30  test    eax, eax
0x140014a32  jz      short loc_140014A6A
0x140014a34  mov     r9d, 658h
0x140014a3a  mov     dword ptr [rsp+68h+var_30], ebx
0x140014a3e  lea     r8, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140014a45  mov     [rsp+68h+var_38], rbp
0x140014a4a  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140014a51  mov     qword ptr [rsp+68h+samDesired], r14
0x140014a56  mov     ecx, 2; unsigned __int8
0x140014a5b  mov     qword ptr [rsp+68h+dwOptions], rsi
0x140014a60  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140014a65  jmp     loc_140014B2A
0x140014a6a  mov     r8d, 658h
0x140014a70  jmp     loc_140014B06
0x140014a75  mov     rcx, [rsp+68h+hKey]; hKey
0x140014a7a  lea     rax, [rsp+68h+Data]
0x140014a7f  xor     ebx, ebx
0x140014a81  lea     rdx, ?s_szDelayedUninstallRegValueName@CDiskProtection@@1QBGB; "DelayedUninstall"
0x140014a88  xor     r8d, r8d; Reserved
0x140014a8b  lea     r9d, [rbx+4]; dwType
0x140014a8f  mov     [rsp+68h+samDesired], r9d; cbData
0x140014a94  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x140014a99  call    cs:__imp_RegSetValueExW
0x140014a9f  test    eax, eax
0x140014aa1  jz      loc_140014B2A
0x140014aa7  jg      short loc_140014AAD
0x140014aa9  mov     ebx, eax
0x140014aab  jmp     short loc_140014AB6
0x140014aad  movzx   ebx, ax
0x140014ab0  or      ebx, 80070000h
0x140014ab6  lea     r14, aCbraex; "CBRAEx"
0x140014abd  mov     [rsp+68h+samDesired], ebx; int
0x140014ac1  lea     rsi, aCdiskprotectio_180; "CDiskProtection::s_SetDelayedUninstall"
0x140014ac8  mov     r9, r14; unsigned __int16 *
0x140014acb  lea     rbp, aErr0l; "err == 0L"
0x140014ad2  mov     r8, rsi; unsigned __int16 *
0x140014ad5  mov     edx, 65Bh; unsigned int
0x140014ada  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x140014adf  lea     rcx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140014ae6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140014aeb  call    cs:__imp_IsDebuggerPresent
0x140014af1  test    eax, eax
0x140014af3  jz      short loc_140014B00
0x140014af5  mov     r9d, 65Bh
0x140014afb  jmp     loc_140014A3A
0x140014b00  mov     r8d, 65Bh
0x140014b06  mov     dword ptr [rsp+68h+var_38], ebx
0x140014b0a  lea     rdx, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x140014b11  mov     qword ptr [rsp+68h+samDesired], rbp
0x140014b16  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140014b1d  mov     r9, rsi
0x140014b20  mov     qword ptr [rsp+68h+dwOptions], r14
0x140014b25  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140014b2a  mov     rcx, [rsp+68h+hKey]; hKey
0x140014b2f  test    rcx, rcx
0x140014b32  jz      short loc_140014B3A
0x140014b34  call    cs:__imp_RegCloseKey
0x140014b3a  mov     eax, ebx
0x140014b3c  mov     rbx, [rsp+68h+arg_10]
0x140014b44  add     rsp, 50h
0x140014b48  pop     r14
0x140014b4a  pop     rsi
0x140014b4b  pop     rbp
0x140014b4c  retn
```
