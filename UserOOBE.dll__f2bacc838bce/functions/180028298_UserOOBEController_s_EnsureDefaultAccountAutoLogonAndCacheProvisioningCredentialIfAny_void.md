# UserOOBEController::s_EnsureDefaultAccountAutoLogonAndCacheProvisioningCredentialIfAny(void)

- ea: `0x180028298`
- end: `0x180028496`
- name: `?s_EnsureDefaultAccountAutoLogonAndCacheProvisioningCredentialIfAny@UserOOBEController@@CAJXZ`
- size: `510`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002abbc`

## callees

- `0x1800032b0`
- `0x180007134`
- `0x18000e270`
- `0x18001b61c`
- `0x180026084`
- `0x180028298`
- `0x1800287a0`
- `0x18002ca58`
- `0x180047bd0`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180028340`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180028353`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180028366`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180028379`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180028340`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180028353`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180028366`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180028379`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800283bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800283bb`

## string_xrefs

- `0x18002831f`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800283e7`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180028424`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002845b`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800282c9`: `UserOOBEController::s_EnsureDefaultAccountAutoLogonAndCacheProvisioningCredentialIfAny() starts shelving auto logon settings.`

## pseudocode

```c
__int64 UserOOBEController::s_EnsureDefaultAccountAutoLogonAndCacheProvisioningCredentialIfAny(void)
{
  bool IsStateSeparationEnabled; // al
  HKEY v1; // r8
  const unsigned __int16 *v2; // r9
  int v3; // eax
  int ValueW; // ebx
  bool v5; // sf
  int v7; // eax
  int v8; // eax
  int pdwType; // [rsp+20h] [rbp-258h]
  int pdwTypea; // [rsp+20h] [rbp-258h]
  DWORD pcbData[4]; // [rsp+40h] [rbp-238h] BYREF
  unsigned __int16 pvData[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( !UserOOBEController::s_HasAutoLogonOobeProvisioned() )
    return 0;
  UnattendLogW(
    0,
    L"UserOOBEController::s_EnsureDefaultAccountAutoLogonAndCacheProvisioningCredentialIfAny() starts shelving auto logon settings.");
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v2 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Winlogon";
  if ( !IsStateSeparationEnabled )
    v2 = L"SOFTWARE\\Microsoft\\Provisioning\\Winlogon";
  v3 = TransferUnattendXmlAutologonValues(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
         v1,
         v2,
         1,
         1);
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x350,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v3,
      pdwType);
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"AutoAdminLogon");
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"DefaultUserName");
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"DefaultPassword");
  SHDeleteValueW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"DefaultDomainName");
  pcbData[0] = 514;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
             L"DefaultAccountSAMName",
             2u,
             0,
             pvData,
             pcbData);
  if ( !ValueW )
    goto LABEL_9;
  pvData[0] = 0;
  v5 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
LABEL_9:
    v5 = ValueW < 0;
  }
  if ( v5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35A,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)ValueW,
      pdwTypea);
    return (unsigned int)ValueW;
  }
  v7 = SHRegSetString(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
         L"AutoAdminLogon",
         L"1");
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35D,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v7,
      pdwTypea);
  v8 = SHRegSetString(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
         L"DefaultUserName",
         pvData);
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35E,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v8,
      pdwTypea);
  return 0;
}

```

## disassembly

```asm
0x180028298  mov     [rsp+arg_0], rbx
0x18002829d  mov     [rsp+arg_8], rbp
0x1800282a2  push    rsi
0x1800282a3  sub     rsp, 270h
0x1800282aa  mov     rax, cs:__security_cookie
0x1800282b1  xor     rax, rsp
0x1800282b4  mov     [rsp+278h+var_18], rax
0x1800282bc  call    ?s_HasAutoLogonOobeProvisioned@UserOOBEController@@CA_NXZ; UserOOBEController::s_HasAutoLogonOobeProvisioned(void)
0x1800282c1  test    al, al
0x1800282c3  jz      loc_18002846F
0x1800282c9  lea     rdx, aUseroobecontro; "UserOOBEController::s_EnsureDefaultAcco"...
0x1800282d0  xor     ecx, ecx
0x1800282d2  call    UnattendLogW
0x1800282d7  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x1800282dc  test    al, al
0x1800282de  mov     byte ptr [rsp+278h+pvData], 1; bool
0x1800282e3  lea     rcx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Provisioning\\Winl"...
0x1800282ea  mov     byte ptr [rsp+278h+pdwType], 1; int
0x1800282ef  lea     r9, aOsdataSoftware; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1800282f6  mov     rsi, 0FFFFFFFF80000002h
0x1800282fd  cmovz   r9, rcx; unsigned __int16 *
0x180028301  lea     rbp, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180028308  mov     rcx, rsi; HKEY
0x18002830b  mov     rdx, rbp; unsigned __int16 *
0x18002830e  call    ?TransferUnattendXmlAutologonValues@@YAJPEAUHKEY__@@PEBG01_N2@Z; TransferUnattendXmlAutologonValues(HKEY__ *,ushort const *,HKEY__ *,ushort const *,bool,bool)
0x180028313  test    eax, eax
0x180028315  jns     short loc_180028333
0x180028317  mov     rcx, [rsp+278h]; this
0x18002831f  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180028326  mov     r9d, eax; char *
0x180028329  mov     edx, 350h; void *
0x18002832e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028333  lea     r8, aAutoadminlogon; "AutoAdminLogon"
0x18002833a  mov     rdx, rbp; pszSubKey
0x18002833d  mov     rcx, rsi; hkey
0x180028340  call    cs:__imp_SHDeleteValueW
0x180028346  lea     r8, aDefaultusernam; "DefaultUserName"
0x18002834d  mov     rdx, rbp; pszSubKey
0x180028350  mov     rcx, rsi; hkey
0x180028353  call    cs:__imp_SHDeleteValueW
0x180028359  lea     r8, aDefaultpasswor; "DefaultPassword"
0x180028360  mov     rdx, rbp; pszSubKey
0x180028363  mov     rcx, rsi; hkey
0x180028366  call    cs:__imp_SHDeleteValueW
0x18002836c  lea     r8, aDefaultdomainn; "DefaultDomainName"
0x180028373  mov     rdx, rbp; pszSubKey
0x180028376  mov     rcx, rsi; hkey
0x180028379  call    cs:__imp_SHDeleteValueW
0x18002837f  lea     rax, [rsp+278h+var_238]
0x180028384  mov     [rsp+278h+var_238], 202h
0x18002838c  mov     [rsp+278h+pcbData], rax; pcbData
0x180028391  lea     r8, aDefaultaccount_0; "DefaultAccountSAMName"
0x180028398  lea     rax, [rsp+278h+var_228]
0x18002839d  mov     r9d, 2; dwFlags
0x1800283a3  mov     [rsp+278h+pvData], rax; pvData
0x1800283a8  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800283af  mov     rcx, rsi; hkey
0x1800283b2  mov     [rsp+278h+pdwType], 0; int
0x1800283bb  call    cs:__imp_RegGetValueW
0x1800283c1  mov     ebx, eax
0x1800283c3  test    eax, eax
0x1800283c5  jz      short loc_1800283DB
0x1800283c7  xor     eax, eax
0x1800283c9  mov     [rsp+278h+var_228], ax
0x1800283ce  test    ebx, ebx
0x1800283d0  jle     short loc_1800283DD
0x1800283d2  movzx   ebx, bx
0x1800283d5  or      ebx, 80070000h
0x1800283db  test    ebx, ebx
0x1800283dd  jns     short loc_1800283FF
0x1800283df  mov     rcx, [rsp+278h]; this
0x1800283e7  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800283ee  mov     r9d, ebx; char *
0x1800283f1  mov     edx, 35Ah; void *
0x1800283f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800283fb  mov     eax, ebx
0x1800283fd  jmp     short loc_180028471
0x1800283ff  lea     r9, a1; "1"
0x180028406  mov     rdx, rbp; unsigned __int16 *
0x180028409  lea     r8, aAutoadminlogon; "AutoAdminLogon"
0x180028410  mov     rcx, rsi; HKEY
0x180028413  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180028418  test    eax, eax
0x18002841a  jns     short loc_180028438
0x18002841c  mov     rcx, [rsp+278h]; this
0x180028424  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002842b  mov     r9d, eax; char *
0x18002842e  mov     edx, 35Dh; void *
0x180028433  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028438  lea     r9, [rsp+278h+var_228]; unsigned __int16 *
0x18002843d  mov     rdx, rbp; unsigned __int16 *
0x180028440  lea     r8, aDefaultusernam; "DefaultUserName"
0x180028447  mov     rcx, rsi; HKEY
0x18002844a  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002844f  test    eax, eax
0x180028451  jns     short loc_18002846F
0x180028453  mov     rcx, [rsp+278h]; this
0x18002845b  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180028462  mov     r9d, eax; char *
0x180028465  mov     edx, 35Eh; void *
0x18002846a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002846f  xor     eax, eax
0x180028471  mov     rcx, [rsp+278h+var_18]
0x180028479  xor     rcx, rsp; StackCookie
0x18002847c  call    __security_check_cookie
0x180028481  lea     r11, [rsp+278h+var_8]
0x180028489  mov     rbx, [r11+10h]
0x18002848d  mov     rbp, [r11+18h]
0x180028491  mov     rsp, r11
0x180028494  pop     rsi
0x180028495  retn
```
