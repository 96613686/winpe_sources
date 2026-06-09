# SetSuppressDeviceInstallUI(ESuppressDeviceInstall)

- ea: `0x140068ebc`
- end: `0x1400690b5`
- name: `?SetSuppressDeviceInstallUI@@YAJW4ESuppressDeviceInstall@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400221e0`
- `0x140045b90`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140068ebc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140069098`
- `ADVAPI32!RegCloseKey` at `0x140069098`
- `ADVAPI32!RegCreateKeyExW` at `0x140068f2f`
- `ADVAPI32!RegCreateKeyExW` at `0x140068f2f`
- `ADVAPI32!RegSetValueExW` at `0x140068ffb`
- `ADVAPI32!RegSetValueExW` at `0x140068ffb`
- `KERNEL32!IsDebuggerPresent` at `0x140068f82`
- `KERNEL32!IsDebuggerPresent` at `0x140069050`
- `KERNEL32!IsDebuggerPresent` at `0x140068f82`
- `KERNEL32!IsDebuggerPresent` at `0x140069050`

## string_xrefs

- `0x140068f5f`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x14006902d`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140068f02`: `Software\Policies\Microsoft\Windows\DeviceInstall\Settings`
- `0x140068ed9`: `SetSuppressDeviceInstallUI\n`
- `0x140068f55`: `SetSuppressDeviceInstallUI`
- `0x140069023`: `SetSuppressDeviceInstallUI`

## pseudocode

```c
__int64 __fastcall SetSuppressDeviceInstallUI(int a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // r8
  LSTATUS v6; // eax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-38h]
  PHKEY phkResult; // [rsp+38h] [rbp-30h]
  int Data; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  hKey = 0;
  Data = 0;
  DEBUGMSG(L"SetSuppressDeviceInstallUI\n");
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall\\Settings",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x6BAu,
      L"SetSuppressDeviceInstallUI",
      L"CBRAEx",
      L"err == 0L",
      v3);
    if ( IsDebuggerPresent() )
    {
      v4 = 1722;
LABEL_6:
      LODWORD(phkResult) = v3;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        v4,
        L"SetSuppressDeviceInstallUI",
        L"CBRAEx",
        L"err == 0L",
        phkResult);
      goto LABEL_18;
    }
    v5 = 1722;
LABEL_17:
    LODWORD(lpSecurityAttributes) = v3;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      v5,
      L"SetSuppressDeviceInstallUI",
      L"CBRAEx",
      L"err == 0L",
      lpSecurityAttributes);
    goto LABEL_18;
  }
  v3 = 0;
  if ( a1 == 1 )
    Data = 1;
  v6 = RegSetValueExW(hKey, L"SuppressNewHWUI", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v6 )
  {
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    else
      v3 = v6;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x6C2u,
      L"SetSuppressDeviceInstallUI",
      L"CBRAEx",
      L"err == 0L",
      v3);
    if ( IsDebuggerPresent() )
    {
      v4 = 1730;
      goto LABEL_6;
    }
    v5 = 1730;
    goto LABEL_17;
  }
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x140068ebc  mov     rax, rsp
0x140068ebf  mov     [rax+8], rbx
0x140068ec3  mov     [rax+20h], rbp
0x140068ec7  push    rsi
0x140068ec8  push    rdi
0x140068ec9  push    r14
0x140068ecb  sub     rsp, 50h
0x140068ecf  mov     edi, ecx
0x140068ed1  mov     qword ptr [rax+18h], 0
0x140068ed9  lea     rcx, aSetsuppressdev_0; "SetSuppressDeviceInstallUI\n"
0x140068ee0  mov     dword ptr [rax+10h], 0
0x140068ee7  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140068eec  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x140068ef5  lea     rax, [rsp+68h+hKey]
0x140068efd  mov     [rsp+68h+phkResult], rax; phkResult
0x140068f02  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x140068f09  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140068f12  xor     r9d, r9d; lpClass
0x140068f15  mov     [rsp+68h+samDesired], 20006h; samDesired
0x140068f1d  xor     r8d, r8d; Reserved
0x140068f20  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140068f27  mov     [rsp+68h+dwOptions], 0; dwOptions
0x140068f2f  call    cs:__imp_RegCreateKeyExW
0x140068f35  mov     ebx, eax
0x140068f37  test    eax, eax
0x140068f39  jz      loc_140068FC9
0x140068f3f  jle     short loc_140068F4A
0x140068f41  movzx   ebx, ax
0x140068f44  or      ebx, 80070000h
0x140068f4a  lea     r14, aCbraex; "CBRAEx"
0x140068f51  mov     [rsp+68h+samDesired], ebx; int
0x140068f55  lea     rsi, aSetsuppressdev; "SetSuppressDeviceInstallUI"
0x140068f5c  mov     r9, r14; unsigned __int16 *
0x140068f5f  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140068f66  mov     r8, rsi; unsigned __int16 *
0x140068f69  lea     rbp, aErr0l; "err == 0L"
0x140068f70  mov     rcx, rdi; unsigned __int16 *
0x140068f73  mov     edx, 6BAh; unsigned int
0x140068f78  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x140068f7d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140068f82  call    cs:__imp_IsDebuggerPresent
0x140068f88  test    eax, eax
0x140068f8a  jz      short loc_140068FBE
0x140068f8c  mov     r9d, 6BAh
0x140068f92  mov     dword ptr [rsp+68h+phkResult], ebx
0x140068f96  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140068f9d  mov     [rsp+68h+lpSecurityAttributes], rbp
0x140068fa2  mov     r8, rdi
0x140068fa5  mov     qword ptr [rsp+68h+samDesired], r14
0x140068faa  mov     ecx, 2; unsigned __int8
0x140068faf  mov     qword ptr [rsp+68h+dwOptions], rsi
0x140068fb4  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140068fb9  jmp     loc_14006908B
0x140068fbe  mov     r8d, 6BAh
0x140068fc4  jmp     loc_14006906B
0x140068fc9  xor     ebx, ebx
0x140068fcb  cmp     edi, 1
0x140068fce  jnz     short loc_140068FD4
0x140068fd0  mov     [rsp+68h+Data], edi
0x140068fd4  mov     rcx, [rsp+68h+hKey]; hKey
0x140068fdc  lea     rax, [rsp+68h+Data]
0x140068fe1  mov     r9d, 4; dwType
0x140068fe7  lea     rdx, aSuppressnewhwu; "SuppressNewHWUI"
0x140068fee  mov     [rsp+68h+samDesired], r9d; cbData
0x140068ff3  xor     r8d, r8d; Reserved
0x140068ff6  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x140068ffb  call    cs:__imp_RegSetValueExW
0x140069001  test    eax, eax
0x140069003  jz      loc_14006908B
0x140069009  jg      short loc_14006900F
0x14006900b  mov     ebx, eax
0x14006900d  jmp     short loc_140069018
0x14006900f  movzx   ebx, ax
0x140069012  or      ebx, 80070000h
0x140069018  lea     r14, aCbraex; "CBRAEx"
0x14006901f  mov     [rsp+68h+samDesired], ebx; int
0x140069023  lea     rsi, aSetsuppressdev; "SetSuppressDeviceInstallUI"
0x14006902a  mov     r9, r14; unsigned __int16 *
0x14006902d  lea     rdi, aTermsrvWmsSrcC_22; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140069034  mov     r8, rsi; unsigned __int16 *
0x140069037  lea     rbp, aErr0l; "err == 0L"
0x14006903e  mov     rcx, rdi; unsigned __int16 *
0x140069041  mov     edx, 6C2h; unsigned int
0x140069046  mov     qword ptr [rsp+68h+dwOptions], rbp; unsigned __int16 *
0x14006904b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140069050  call    cs:__imp_IsDebuggerPresent
0x140069056  test    eax, eax
0x140069058  jz      short loc_140069065
0x14006905a  mov     r9d, 6C2h
0x140069060  jmp     loc_140068F92
0x140069065  mov     r8d, 6C2h
0x14006906b  mov     dword ptr [rsp+68h+lpSecurityAttributes], ebx
0x14006906f  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140069076  mov     qword ptr [rsp+68h+samDesired], rbp
0x14006907b  mov     r9, rsi
0x14006907e  mov     rdx, rdi
0x140069081  mov     qword ptr [rsp+68h+dwOptions], r14
0x140069086  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006908b  mov     rcx, [rsp+68h+hKey]; hKey
0x140069093  test    rcx, rcx
0x140069096  jz      short loc_14006909E
0x140069098  call    cs:__imp_RegCloseKey
0x14006909e  lea     r11, [rsp+68h+var_18]
0x1400690a3  mov     eax, ebx
0x1400690a5  mov     rbx, [r11+20h]
0x1400690a9  mov     rbp, [r11+38h]
0x1400690ad  mov     rsp, r11
0x1400690b0  pop     r14
0x1400690b2  pop     rdi
0x1400690b3  pop     rsi
0x1400690b4  retn
```
