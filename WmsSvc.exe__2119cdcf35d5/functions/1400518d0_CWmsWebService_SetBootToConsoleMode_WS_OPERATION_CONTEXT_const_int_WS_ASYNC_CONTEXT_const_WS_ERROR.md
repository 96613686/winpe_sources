# CWmsWebService::SetBootToConsoleMode(_WS_OPERATION_CONTEXT const *,int,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x1400518d0`
- end: `0x140051ae9`
- name: `?SetBootToConsoleMode@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@HPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `537`
- prototype: `static int(const struct _WS_OPERATION_CONTEXT *, int, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x14004c43c`
- `0x14004d3dc`
- `0x1400518d0`
- `0x140053434`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006296c`
- `0x14007490c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140051945`
- `ADVAPI32!RegOpenKeyExW` at `0x140051945`
- `ADVAPI32!RegCloseKey` at `0x140051ad5`
- `ADVAPI32!RegCloseKey` at `0x140051ad5`
- `ADVAPI32!RegDeleteValueW` at `0x140051a83`
- `ADVAPI32!RegDeleteValueW` at `0x140051a83`
- `KERNEL32!IsDebuggerPresent` at `0x140051995`
- `KERNEL32!IsDebuggerPresent` at `0x140051995`

## string_xrefs

- `0x140051989`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x1400519a3`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x1400519d9`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140051a53`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14005196b`: `CWmsWebService::SetBootToConsoleMode`
- `0x140051a41`: `CWmsWebService::SetBootToConsoleMode`
- `0x140051a0c`: `CWmsWebService::SetBootToConsoleMode - Enabling boot to console mode.\n`
- `0x140051a35`: `CWmsWebService::SetBootToConsoleMode - HSBS special autologon is set, exiting without removing AutoAdminLogon.\n`
- `0x140051a6b`: `CWmsWebService::SetBootToConsoleMode - HSBS special autologon is not set.\n`
- `0x140051a92`: `CWmsWebService::SetBootToConsoleMode - Disabling boot to console mode.\n`

## pseudocode

```c
__int64 __fastcall CWmsWebService::SetBootToConsoleMode(
        const struct _WS_OPERATION_CONTEXT *a1,
        int a2,
        const struct _WS_ASYNC_CONTEXT *a3,
        struct _WS_ERROR *a4)
{
  HKEY v6; // rcx
  int IsHsbsSpecialAutologonEnabled; // ebx
  LSTATUS v8; // eax
  int *v9; // rdx
  const unsigned __int16 *v10; // r9
  int v12; // [rsp+40h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-30h] BYREF

  v12 = 0;
  hKey = 0;
  IsHsbsSpecialAutologonEnabled = CWmsWebService::s_VerifyAdminAccess(a1, a4);
  if ( IsHsbsSpecialAutologonEnabled < 0 )
    goto LABEL_17;
  IsHsbsSpecialAutologonEnabled = CWmsWebService::s_SetRegValueBool(
                                    v6,
                                    L"SOFTWARE\\Microsoft\\Windows MultiPoint Server",
                                    L"BootToConsoleMode",
                                    a2);
  if ( IsHsbsSpecialAutologonEnabled < 0 )
    goto LABEL_17;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinLogon", 0, 2u, &hKey);
  IsHsbsSpecialAutologonEnabled = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      IsHsbsSpecialAutologonEnabled = (unsigned __int16)v8 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      0x701u,
      L"CWmsWebService::SetBootToConsoleMode",
      L"CBRAEx",
      L"lr == 0L",
      IsHsbsSpecialAutologonEnabled);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        1793,
        L"CWmsWebService::SetBootToConsoleMode",
        L"CBRAEx",
        L"lr == 0L",
        IsHsbsSpecialAutologonEnabled);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
        1793,
        L"CWmsWebService::SetBootToConsoleMode",
        L"CBRAEx",
        L"lr == 0L",
        IsHsbsSpecialAutologonEnabled);
LABEL_16:
    if ( IsHsbsSpecialAutologonEnabled >= 0 )
      goto LABEL_19;
    goto LABEL_17;
  }
  if ( !a2 )
  {
    DEBUGMSG(L"CWmsWebService::SetBootToConsoleMode - Disabling boot to console mode.\n");
    IsHsbsSpecialAutologonEnabled = RegUtil::SetStringValue((RegUtil *)hKey, (HKEY)L"AutoAdminLogon", L"1", v10);
    goto LABEL_16;
  }
  DEBUGMSG(L"CWmsWebService::SetBootToConsoleMode - Enabling boot to console mode.\n");
  IsHsbsSpecialAutologonEnabled = PlatformUtils::IsHsbsSpecialAutologonEnabled((PlatformUtils *)&v12, v9);
  if ( IsHsbsSpecialAutologonEnabled < 0 )
  {
LABEL_17:
    if ( a4 )
      CWmsWebService::s_CreateWmsFault(IsHsbsSpecialAutologonEnabled, a4);
    goto LABEL_19;
  }
  if ( v12 )
  {
    IsHsbsSpecialAutologonEnabled = 0;
    DEBUGMSGLEVEL(
      4u,
      L"%s(%d) - %s - Test failed:  %s\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
      1803,
      L"CWmsWebService::SetBootToConsoleMode",
      L"CWmsWebService::SetBootToConsoleMode - HSBS special autologon is set, exiting without removing AutoAdminLogon.\n");
  }
  else
  {
    DEBUGMSG(L"CWmsWebService::SetBootToConsoleMode - HSBS special autologon is not set.\n");
    if ( RegDeleteValueW(hKey, L"AutoAdminLogon") == 2 )
      IsHsbsSpecialAutologonEnabled = 0;
  }
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)IsHsbsSpecialAutologonEnabled;
}

```

## disassembly

```asm
0x1400518d0  push    rbx
0x1400518d2  push    rsi
0x1400518d3  push    rdi
0x1400518d4  push    r12
0x1400518d6  push    r13
0x1400518d8  sub     rsp, 50h
0x1400518dc  mov     edi, edx
0x1400518de  mov     [rsp+78h+var_38], 0
0x1400518e6  mov     rdx, r9; struct _WS_ERROR *
0x1400518e9  mov     [rsp+78h+hKey], 0
0x1400518f2  mov     rsi, r9
0x1400518f5  call    ?s_VerifyAdminAccess@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@PEAU_WS_ERROR@@@Z; CWmsWebService::s_VerifyAdminAccess(_WS_OPERATION_CONTEXT const *,_WS_ERROR *)
0x1400518fa  mov     ebx, eax
0x1400518fc  test    eax, eax
0x1400518fe  js      loc_140051ABC
0x140051904  mov     r9d, edi; int
0x140051907  lea     r8, ?g_kszBootToConsoleMode@@3QBGB; "BootToConsoleMode"
0x14005190e  lea     rdx, aSoftwareMicros_28; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x140051915  call    ?s_SetRegValueBool@CWmsWebService@@CAJPEAUHKEY__@@PEBG1H@Z; CWmsWebService::s_SetRegValueBool(HKEY__ *,ushort const *,ushort const *,int)
0x14005191a  mov     ebx, eax
0x14005191c  test    eax, eax
0x14005191e  js      loc_140051ABC
0x140051924  lea     rax, [rsp+78h+hKey]
0x140051929  mov     r9d, 2; samDesired
0x14005192f  xor     r8d, r8d; ulOptions
0x140051932  mov     [rsp+78h+phkResult], rax; phkResult
0x140051937  lea     rdx, aSoftwareMicros_30; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14005193e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140051945  call    cs:__imp_RegOpenKeyExW
0x14005194b  mov     ebx, eax
0x14005194d  test    eax, eax
0x14005194f  jz      loc_140051A04
0x140051955  jle     short loc_140051960
0x140051957  movzx   ebx, ax
0x14005195a  or      ebx, 80070000h
0x140051960  lea     r13, aCbraex; "CBRAEx"
0x140051967  mov     [rsp+78h+var_50], ebx; int
0x14005196b  lea     rdi, aCwmswebservice_88; "CWmsWebService::SetBootToConsoleMode"
0x140051972  mov     r9, r13; unsigned __int16 *
0x140051975  lea     r12, aLr0l; "lr == 0L"
0x14005197c  mov     r8, rdi; unsigned __int16 *
0x14005197f  mov     edx, 701h; unsigned int
0x140051984  mov     [rsp+78h+phkResult], r12; unsigned __int16 *
0x140051989  lea     rcx, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140051990  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140051995  call    cs:__imp_IsDebuggerPresent
0x14005199b  test    eax, eax
0x14005199d  jz      short loc_1400519D5
0x14005199f  mov     [rsp+78h+var_40], ebx
0x1400519a3  lea     r8, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x1400519aa  mov     [rsp+78h+var_48], r12
0x1400519af  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400519b6  mov     qword ptr [rsp+78h+var_50], r13
0x1400519bb  mov     r9d, 701h
0x1400519c1  mov     ecx, 2; unsigned __int8
0x1400519c6  mov     [rsp+78h+phkResult], rdi
0x1400519cb  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400519d0  jmp     loc_140051AB8
0x1400519d5  mov     dword ptr [rsp+78h+var_48], ebx
0x1400519d9  lea     rdx, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x1400519e0  mov     qword ptr [rsp+78h+var_50], r12
0x1400519e5  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400519ec  mov     r9, rdi
0x1400519ef  mov     [rsp+78h+phkResult], r13
0x1400519f4  mov     r8d, 701h
0x1400519fa  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400519ff  jmp     loc_140051AB8
0x140051a04  test    edi, edi
0x140051a06  jz      loc_140051A92
0x140051a0c  lea     rcx, aCwmswebservice_76; "CWmsWebService::SetBootToConsoleMode - "...
0x140051a13  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140051a18  lea     rcx, [rsp+78h+var_38]; this
0x140051a1d  call    ?IsHsbsSpecialAutologonEnabled@PlatformUtils@@YAJPEAH@Z; PlatformUtils::IsHsbsSpecialAutologonEnabled(int *)
0x140051a22  mov     ebx, eax
0x140051a24  test    eax, eax
0x140051a26  js      loc_140051ABC
0x140051a2c  cmp     [rsp+78h+var_38], 0
0x140051a31  jz      short loc_140051A6B
0x140051a33  xor     ebx, ebx
0x140051a35  lea     rax, aCwmswebservice_33; "CWmsWebService::SetBootToConsoleMode - "...
0x140051a3c  mov     qword ptr [rsp+78h+var_50], rax
0x140051a41  lea     rdi, aCwmswebservice_88; "CWmsWebService::SetBootToConsoleMode"
0x140051a48  mov     r9d, 70Bh
0x140051a4e  mov     [rsp+78h+phkResult], rdi
0x140051a53  lea     r8, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140051a5a  lea     ecx, [rbx+4]; unsigned __int8
0x140051a5d  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140051a64  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140051a69  jmp     short loc_140051ACB
0x140051a6b  lea     rcx, aCwmswebservice_58; "CWmsWebService::SetBootToConsoleMode - "...
0x140051a72  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140051a77  mov     rcx, [rsp+78h+hKey]; hKey
0x140051a7c  lea     rdx, aAutoadminlogon_0; "AutoAdminLogon"
0x140051a83  call    cs:__imp_RegDeleteValueW
0x140051a89  cmp     eax, 2
0x140051a8c  jnz     short loc_140051ACB
0x140051a8e  xor     ebx, ebx
0x140051a90  jmp     short loc_140051ACB
0x140051a92  lea     rcx, aCwmswebservice_28; "CWmsWebService::SetBootToConsoleMode - "...
0x140051a99  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140051a9e  mov     rcx, [rsp+78h+hKey]; this
0x140051aa3  lea     r8, a1; "1"
0x140051aaa  lea     rdx, aAutoadminlogon_0; "AutoAdminLogon"
0x140051ab1  call    ?SetStringValue@RegUtil@@YAJPEAUHKEY__@@PEBG1@Z; RegUtil::SetStringValue(HKEY__ *,ushort const *,ushort const *)
0x140051ab6  mov     ebx, eax
0x140051ab8  test    ebx, ebx
0x140051aba  jns     short loc_140051ACB
0x140051abc  test    rsi, rsi
0x140051abf  jz      short loc_140051ACB
0x140051ac1  mov     rdx, rsi; struct _WS_ERROR *
0x140051ac4  mov     ecx, ebx; int
0x140051ac6  call    ?s_CreateWmsFault@CWmsWebService@@CAJJPEAU_WS_ERROR@@@Z; CWmsWebService::s_CreateWmsFault(long,_WS_ERROR *)
0x140051acb  mov     rcx, [rsp+78h+hKey]; hKey
0x140051ad0  test    rcx, rcx
0x140051ad3  jz      short loc_140051ADB
0x140051ad5  call    cs:__imp_RegCloseKey
0x140051adb  mov     eax, ebx
0x140051add  add     rsp, 50h
0x140051ae1  pop     r13
0x140051ae3  pop     r12
0x140051ae5  pop     rdi
0x140051ae6  pop     rsi
0x140051ae7  pop     rbx
0x140051ae8  retn
```
