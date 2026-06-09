# CSoftwareUpdates::SetWindowsUpdateNoAutoUpdateSetting(ulong)

- ea: `0x140031424`
- end: `0x1400315f2`
- name: `?SetWindowsUpdateNoAutoUpdateSetting@CSoftwareUpdates@@AEAAJK@Z`
- size: `462`
- prototype: `__int64 __fastcall(CSoftwareUpdates *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000b980`
- `0x140030474`
- `0x140030bc8`

## callees

- `0x140031424`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400315d9`
- `ADVAPI32!RegCloseKey` at `0x1400315d9`
- `ADVAPI32!RegCreateKeyExW` at `0x14003147f`
- `ADVAPI32!RegCreateKeyExW` at `0x14003147f`
- `ADVAPI32!RegSetValueExW` at `0x14003153e`
- `ADVAPI32!RegSetValueExW` at `0x14003153e`
- `KERNEL32!IsDebuggerPresent` at `0x1400314cf`
- `KERNEL32!IsDebuggerPresent` at `0x140031590`
- `KERNEL32!IsDebuggerPresent` at `0x1400314cf`
- `KERNEL32!IsDebuggerPresent` at `0x140031590`

## string_xrefs

- `0x1400314c3`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x1400314e3`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x140031584`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x1400315af`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x140031526`: `NoAutoUpdate`
- `0x1400314a5`: `CSoftwareUpdates::SetWindowsUpdateNoAutoUpdateSetting`
- `0x140031566`: `CSoftwareUpdates::SetWindowsUpdateNoAutoUpdateSetting`
- `0x14003144b`: `Software\Policies\Microsoft\Windows\WindowsUpdate\AU`

## pseudocode

```c
__int64 __fastcall CSoftwareUpdates::SetWindowsUpdateNoAutoUpdateSetting(CSoftwareUpdates *this, int a2)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // r8
  LSTATUS v6; // eax
  __int64 v8; // [rsp+30h] [rbp-38h]
  __int64 v9; // [rsp+38h] [rbp-30h]
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+78h] [rbp+10h] BYREF

  Data = a2;
  hKey = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows\\WindowsUpdate\\AU",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0x14Fu,
      L"CSoftwareUpdates::SetWindowsUpdateNoAutoUpdateSetting",
      L"CBRAEx",
      L"err == 0L",
      v3);
    if ( IsDebuggerPresent() )
    {
      v4 = 335;
LABEL_6:
      LODWORD(v9) = v3;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        v4,
        L"CSoftwareUpdates::SetWindowsUpdateNoAutoUpdateSetting",
        L"CBRAEx",
        L"err == 0L",
        v9);
      goto LABEL_16;
    }
    v5 = 335;
  }
  else
  {
    v3 = 0;
    v6 = RegSetValueExW(hKey, L"NoAutoUpdate", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v6 )
      goto LABEL_16;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    else
      v3 = v6;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0x152u,
      L"CSoftwareUpdates::SetWindowsUpdateNoAutoUpdateSetting",
      L"CBRAEx",
      L"err == 0L",
      v3);
    if ( IsDebuggerPresent() )
    {
      v4 = 338;
      goto LABEL_6;
    }
    v5 = 338;
  }
  LODWORD(v8) = v3;
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
    v5,
    L"CSoftwareUpdates::SetWindowsUpdateNoAutoUpdateSetting",
    L"CBRAEx",
    L"err == 0L",
    v8);
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x140031424  mov     r11, rsp
0x140031427  mov     [r11+18h], rbx
0x14003142b  mov     [rsp+Data], edx
0x14003142f  mov     [r11+8], rcx
0x140031433  push    rbp
0x140031434  push    rsi
0x140031435  push    r14
0x140031437  sub     rsp, 50h
0x14003143b  mov     qword ptr [r11-28h], 0
0x140031443  lea     rax, [r11+8]
0x140031447  mov     [r11-30h], rax
0x14003144b  lea     rdx, ?s_szAutomaticUpdatesRegKey@CSoftwareUpdates@@0QBGB; "Software\\Policies\\Microsoft\\Windows"...
0x140031452  mov     qword ptr [r11-38h], 0
0x14003145a  xor     r9d, r9d; lpClass
0x14003145d  mov     [rsp+68h+samDesired], 2; samDesired
0x140031465  xor     r8d, r8d; Reserved
0x140031468  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003146f  mov     [rsp+68h+dwOptions], 0; dwOptions
0x140031477  mov     qword ptr [r11+8], 0
0x14003147f  call    cs:__imp_RegCreateKeyExW
0x140031485  mov     ebx, eax
0x140031487  test    eax, eax
0x140031489  jz      loc_14003151A
0x14003148f  jle     short loc_14003149A
0x140031491  movzx   ebx, ax
0x140031494  or      ebx, 80070000h
0x14003149a  lea     r14, aCbraex; "CBRAEx"
0x1400314a1  mov     [rsp+68h+samDesired], ebx; int
0x1400314a5  lea     rsi, aCsoftwareupdat_4; "CSoftwareUpdates::SetWindowsUpdateNoAut"...
0x1400314ac  mov     r9, r14; unsigned __int16 *
0x1400314af  lea     rbp, aErr0l; "err == 0L"
0x1400314b6  mov     r8, rsi; unsigned __int16 *
0x1400314b9  mov     edx, 14Fh; unsigned int
0x1400314be  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x1400314c3  lea     rcx, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x1400314ca  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400314cf  call    cs:__imp_IsDebuggerPresent
0x1400314d5  test    eax, eax
0x1400314d7  jz      short loc_14003150F
0x1400314d9  mov     r9d, 14Fh
0x1400314df  mov     dword ptr [rsp+68h+var_30], ebx
0x1400314e3  lea     r8, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x1400314ea  mov     [rsp+68h+var_38], rbp
0x1400314ef  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400314f6  mov     qword ptr [rsp+68h+samDesired], r14
0x1400314fb  mov     ecx, 2; unsigned __int8
0x140031500  mov     qword ptr [rsp+68h+dwOptions], rsi
0x140031505  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14003150a  jmp     loc_1400315CF
0x14003150f  mov     r8d, 14Fh
0x140031515  jmp     loc_1400315AB
0x14003151a  mov     rcx, [rsp+68h+hKey]; hKey
0x14003151f  lea     rax, [rsp+68h+Data]
0x140031524  xor     ebx, ebx
0x140031526  lea     rdx, aNoautoupdate; "NoAutoUpdate"
0x14003152d  xor     r8d, r8d; Reserved
0x140031530  lea     r9d, [rbx+4]; dwType
0x140031534  mov     [rsp+68h+samDesired], r9d; cbData
0x140031539  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x14003153e  call    cs:__imp_RegSetValueExW
0x140031544  test    eax, eax
0x140031546  jz      loc_1400315CF
0x14003154c  jg      short loc_140031552
0x14003154e  mov     ebx, eax
0x140031550  jmp     short loc_14003155B
0x140031552  movzx   ebx, ax
0x140031555  or      ebx, 80070000h
0x14003155b  lea     r14, aCbraex; "CBRAEx"
0x140031562  mov     [rsp+68h+samDesired], ebx; int
0x140031566  lea     rsi, aCsoftwareupdat_4; "CSoftwareUpdates::SetWindowsUpdateNoAut"...
0x14003156d  mov     r9, r14; unsigned __int16 *
0x140031570  lea     rbp, aErr0l; "err == 0L"
0x140031577  mov     r8, rsi; unsigned __int16 *
0x14003157a  mov     edx, 152h; unsigned int
0x14003157f  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x140031584  lea     rcx, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x14003158b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140031590  call    cs:__imp_IsDebuggerPresent
0x140031596  test    eax, eax
0x140031598  jz      short loc_1400315A5
0x14003159a  mov     r9d, 152h
0x1400315a0  jmp     loc_1400314DF
0x1400315a5  mov     r8d, 152h
0x1400315ab  mov     dword ptr [rsp+68h+var_38], ebx
0x1400315af  lea     rdx, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x1400315b6  mov     qword ptr [rsp+68h+samDesired], rbp
0x1400315bb  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400315c2  mov     r9, rsi
0x1400315c5  mov     qword ptr [rsp+68h+dwOptions], r14
0x1400315ca  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400315cf  mov     rcx, [rsp+68h+hKey]; hKey
0x1400315d4  test    rcx, rcx
0x1400315d7  jz      short loc_1400315DF
0x1400315d9  call    cs:__imp_RegCloseKey
0x1400315df  mov     eax, ebx
0x1400315e1  mov     rbx, [rsp+68h+arg_10]
0x1400315e9  add     rsp, 50h
0x1400315ed  pop     r14
0x1400315ef  pop     rsi
0x1400315f0  pop     rbp
0x1400315f1  retn
```
