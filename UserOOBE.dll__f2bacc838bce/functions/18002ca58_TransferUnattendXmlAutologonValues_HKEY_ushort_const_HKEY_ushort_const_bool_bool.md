# TransferUnattendXmlAutologonValues(HKEY__ *,ushort const *,HKEY__ *,ushort const *,bool,bool)

- ea: `0x18002ca58`
- end: `0x18002cf61`
- name: `?TransferUnattendXmlAutologonValues@@YAJPEAUHKEY__@@PEBG01_N2@Z`
- size: `1289`
- prototype: `__int64 __usercall@<rax>(HKEY@<rcx>, const unsigned __int16 *@<rdx>, HKEY@<r8>, const unsigned __int16 *@<r9>, bool, bool)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180028298`
- `0x180029a78`
- `0x18002a480`

## callees

- `0x1800032b0`
- `0x18000d738`
- `0x18000e270`
- `0x180015478`
- `0x18001b5d4`
- `0x18001b61c`
- `0x18002ca58`
- `0x18002d020`
- `0x180047bd0`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002caf4`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cb9d`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cbb0`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cc52`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cc65`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cd07`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cd1d`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cd79`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cd8f`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002ce21`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002ce41`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cee5`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002caf4`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cb9d`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cbb0`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cc52`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cc65`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cd07`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cd1d`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cd79`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cd8f`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002ce21`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002ce41`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002cee5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cb32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cbf0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cca5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cdc9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ce81`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cb32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cbf0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cca5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002cdc9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002ce81`

## string_xrefs

- `0x18002cb53`: `shell\oobe\common\lib\autologon.cpp`
- `0x18002cba3`: `DefaultSID`
- `0x18002cbc8`: `DefaultSID`
- `0x18002cc1b`: `DefaultSID`
- `0x18002cc45`: `DefaultSID`
- `0x18002cad9`: `Transferring unattend.xml autologon values`
- `0x18002cef2`: `CachedDefaultPassword`
- `0x18002cf17`: `CachedDefaultPassword`

## pseudocode

```c
__int64 __fastcall TransferUnattendXmlAutologonValues(
        HKEY a1,
        const unsigned __int16 *a2,
        HKEY a3,
        const unsigned __int16 *a4,
        bool a5,
        bool a6)
{
  int ValueW; // eax
  int v11; // eax
  LSTATUS v12; // eax
  bool v13; // sf
  int v14; // eax
  LSTATUS v15; // eax
  bool v16; // sf
  int v17; // eax
  int v18; // eax
  LSTATUS v19; // eax
  bool v20; // sf
  int v21; // eax
  LSTATUS v22; // eax
  bool v23; // sf
  int v24; // eax
  int v25; // eax
  __int64 v26; // rdx
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  int pdwTypec; // [rsp+20h] [rbp-E0h]
  int pdwTyped; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v33; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 v34; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 pvData[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v36[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v37[264]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v38[264]; // [rsp+680h] [rbp+580h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8D8h] [rbp+7D8h]

  pcbData = 0;
  if ( !a5
    && ((int)SHRegGetBOOLWithREGSAM(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE",
               L"UnattendSetAutologon",
               (unsigned int)a4,
               (int *)&pcbData) < 0
     || !pcbData) )
  {
    return 2147549183LL;
  }
  UnattendLogW(0, L"Transferring unattend.xml autologon values", a3);
  SHDeleteValueW(HKEY_LOCAL_MACHINE, a4, L"DefaultUserName");
  pcbData = 514;
  ValueW = RegGetValueW(a1, a2, L"DefaultUserName", 2u, 0, pvData, &pcbData);
  if ( ValueW )
  {
    pvData[0] = 0;
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( ValueW >= 0 )
  {
    v11 = SHRegSetString(HKEY_LOCAL_MACHINE, a4, L"DefaultUserName", pvData);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)(unsigned int)v11,
        pdwType);
  }
  SHDeleteValueW(a1, a2, L"DefaultUserName");
  SHDeleteValueW(HKEY_LOCAL_MACHINE, a4, L"DefaultSID");
  pcbData = 514;
  v12 = RegGetValueW(a1, a2, L"DefaultSID", 2u, 0, v36, &pcbData);
  v13 = v12 < 0;
  if ( v12 )
  {
    v36[0] = 0;
    v13 = v12 < 0;
    if ( v12 > 0 )
      v13 = 1;
  }
  if ( !v13 )
  {
    v14 = SHRegSetString(HKEY_LOCAL_MACHINE, a4, L"DefaultSID", v36);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)(unsigned int)v14,
        pdwTypea);
  }
  SHDeleteValueW(a1, a2, L"DefaultSID");
  SHDeleteValueW(HKEY_LOCAL_MACHINE, a4, L"DefaultDomainName");
  pcbData = 514;
  v15 = RegGetValueW(a1, a2, L"DefaultDomainName", 2u, 0, v37, &pcbData);
  v16 = v15 < 0;
  if ( v15 )
  {
    v37[0] = 0;
    v16 = v15 < 0;
    if ( v15 > 0 )
      v16 = 1;
  }
  if ( !v16 )
  {
    v17 = SHRegSetString(HKEY_LOCAL_MACHINE, a4, L"DefaultDomainName", v37);
    if ( v17 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD1,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)(unsigned int)v17,
        pdwTypeb);
  }
  SHDeleteValueW(a1, a2, L"DefaultDomainName");
  SHDeleteValueW(HKEY_LOCAL_MACHINE, a4, L"AutoLogonCount");
  v33 = 0;
  if ( (int)SHRegGetDWORD(a1, a2, L"AutoLogonCount", &v33) >= 0 )
  {
    v18 = SHRegSetDWORD(HKEY_LOCAL_MACHINE, a4, L"AutoLogonCount", v33);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)(unsigned int)v18,
        pdwTypeb);
  }
  SHDeleteValueW(a1, a2, L"AutoLogonCount");
  SHDeleteValueW(HKEY_LOCAL_MACHINE, a4, L"AutoAdminLogon");
  pcbData = 4;
  v19 = RegGetValueW(a1, a2, L"AutoAdminLogon", 2u, 0, &v34, &pcbData);
  v20 = v19 < 0;
  if ( v19 )
  {
    v34 = 0;
    v20 = v19 < 0;
    if ( v19 > 0 )
      v20 = 1;
  }
  if ( !v20 )
  {
    v21 = SHRegSetString(HKEY_LOCAL_MACHINE, a4, L"AutoAdminLogon", &v34);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE1,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)(unsigned int)v21,
        pdwTypec);
  }
  SHDeleteValueW(a1, a2, L"AutoAdminLogon");
  if ( a6 )
  {
    SHDeleteValueW(HKEY_LOCAL_MACHINE, a4, L"DefaultPassword");
    pcbData = 514;
    v22 = RegGetValueW(a1, a2, L"DefaultPassword", 2u, 0, v38, &pcbData);
    v23 = v22 < 0;
    if ( v22 )
    {
      v38[0] = 0;
      v23 = v22 < 0;
      if ( v22 > 0 )
        v23 = 1;
    }
    if ( !v23 )
    {
      v24 = SHRegSetString(HKEY_LOCAL_MACHINE, a4, L"DefaultPassword", v38);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xEB,
          (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
          (const char *)(unsigned int)v24,
          pdwTyped);
    }
    SHDeleteValueW(a1, a2, L"DefaultPassword");
    return 0;
  }
  if ( a1 == HKEY_LOCAL_MACHINE )
  {
    v25 = _MoveLsaSecret(L"DefaultPassword", L"CachedDefaultPassword");
    if ( v25 < 0 )
    {
      v26 = 246;
LABEL_45:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"shell\\oobe\\common\\lib\\autologon.cpp",
        (const char *)(unsigned int)v25,
        pdwTypec);
    }
  }
  else
  {
    v25 = _MoveLsaSecret(L"CachedDefaultPassword", L"DefaultPassword");
    if ( v25 < 0 )
    {
      v26 = 250;
      goto LABEL_45;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002ca58  push    rbp
0x18002ca5a  push    rbx
0x18002ca5b  push    rsi
0x18002ca5c  push    rdi
0x18002ca5d  push    r12
0x18002ca5f  push    r13
0x18002ca61  push    r15
0x18002ca63  lea     rbp, [rsp-7A0h]
0x18002ca6b  sub     rsp, 8A0h
0x18002ca72  mov     rax, cs:__security_cookie
0x18002ca79  xor     rax, rsp
0x18002ca7c  mov     [rbp+7D0h+var_40], rax
0x18002ca83  cmp     [rbp+7D0h+arg_20], 0
0x18002ca8a  mov     rbx, r9
0x18002ca8d  mov     rsi, rdx
0x18002ca90  mov     [rsp+8D0h+var_890], 0
0x18002ca98  mov     rdi, rcx
0x18002ca9b  mov     r15, 0FFFFFFFF80000002h
0x18002caa2  jnz     short loc_18002CAD9
0x18002caa4  lea     rax, [rsp+8D0h+var_890]
0x18002caa9  mov     rcx, r15; HKEY
0x18002caac  lea     r8, aUnattendsetaut; "UnattendSetAutologon"
0x18002cab3  mov     [rsp+8D0h+pdwType], rax; int *
0x18002cab8  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002cabf  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18002cac4  test    eax, eax
0x18002cac6  js      short loc_18002CACF
0x18002cac8  cmp     [rsp+8D0h+var_890], 0
0x18002cacd  jnz     short loc_18002CAD9
0x18002cacf  mov     eax, 8000FFFFh
0x18002cad4  jmp     loc_18002CF40
0x18002cad9  lea     rdx, aTransferringUn; "Transferring unattend.xml autologon val"...
0x18002cae0  xor     ecx, ecx
0x18002cae2  call    UnattendLogW
0x18002cae7  lea     r8, aDefaultusernam; "DefaultUserName"
0x18002caee  mov     rdx, rbx; pszSubKey
0x18002caf1  mov     rcx, r15; hkey
0x18002caf4  call    cs:__imp_SHDeleteValueW
0x18002cafa  lea     rax, [rsp+8D0h+var_890]
0x18002caff  mov     [rsp+8D0h+var_890], 202h
0x18002cb07  mov     [rsp+8D0h+pcbData], rax; pcbData
0x18002cb0c  lea     r8, aDefaultusernam; "DefaultUserName"
0x18002cb13  lea     rax, [rsp+8D0h+var_880]
0x18002cb18  mov     r9d, 2; dwFlags
0x18002cb1e  mov     [rsp+8D0h+pvData], rax; pvData
0x18002cb23  mov     rdx, rsi; lpSubKey
0x18002cb26  mov     rcx, rdi; hkey
0x18002cb29  mov     [rsp+8D0h+pdwType], 0; int
0x18002cb32  call    cs:__imp_RegGetValueW
0x18002cb38  mov     r13d, 80070000h
0x18002cb3e  test    eax, eax
0x18002cb40  jz      short loc_18002CB53
0x18002cb42  xor     ecx, ecx
0x18002cb44  mov     [rsp+8D0h+var_880], cx
0x18002cb49  test    eax, eax
0x18002cb4b  jle     short loc_18002CB53
0x18002cb4d  movzx   eax, ax
0x18002cb50  or      eax, r13d
0x18002cb53  lea     r12, aShellOobeCommo; "shell\\oobe\\common\\lib\\autologon.cpp"
0x18002cb5a  test    eax, eax
0x18002cb5c  js      short loc_18002CB90
0x18002cb5e  lea     r9, [rsp+8D0h+var_880]; unsigned __int16 *
0x18002cb63  mov     rdx, rbx; unsigned __int16 *
0x18002cb66  lea     r8, aDefaultusernam; "DefaultUserName"
0x18002cb6d  mov     rcx, r15; HKEY
0x18002cb70  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002cb75  test    eax, eax
0x18002cb77  jns     short loc_18002CB90
0x18002cb79  mov     rcx, [rbp+7D8h]; this
0x18002cb80  mov     r9d, eax; char *
0x18002cb83  mov     r8, r12; unsigned int
0x18002cb86  mov     edx, 0C1h; void *
0x18002cb8b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002cb90  lea     r8, aDefaultusernam; "DefaultUserName"
0x18002cb97  mov     rdx, rsi; pszSubKey
0x18002cb9a  mov     rcx, rdi; hkey
0x18002cb9d  call    cs:__imp_SHDeleteValueW
0x18002cba3  lea     r8, aDefaultsid; "DefaultSID"
0x18002cbaa  mov     rdx, rbx; pszSubKey
0x18002cbad  mov     rcx, r15; hkey
0x18002cbb0  call    cs:__imp_SHDeleteValueW
0x18002cbb6  lea     rax, [rsp+8D0h+var_890]
0x18002cbbb  mov     [rsp+8D0h+var_890], 202h
0x18002cbc3  mov     [rsp+8D0h+pcbData], rax; pcbData
0x18002cbc8  lea     r8, aDefaultsid; "DefaultSID"
0x18002cbcf  lea     rax, [rbp+7D0h+var_670]
0x18002cbd6  mov     r9d, 2; dwFlags
0x18002cbdc  mov     [rsp+8D0h+pvData], rax; pvData
0x18002cbe1  mov     rdx, rsi; lpSubKey
0x18002cbe4  mov     rcx, rdi; hkey
0x18002cbe7  mov     [rsp+8D0h+pdwType], 0; int
0x18002cbf0  call    cs:__imp_RegGetValueW
0x18002cbf6  test    eax, eax
0x18002cbf8  jz      short loc_18002CC0F
0x18002cbfa  xor     ecx, ecx
0x18002cbfc  mov     [rbp+7D0h+var_670], cx
0x18002cc03  test    eax, eax
0x18002cc05  jle     short loc_18002CC0F
0x18002cc07  movzx   eax, ax
0x18002cc0a  or      eax, r13d
0x18002cc0d  test    eax, eax
0x18002cc0f  js      short loc_18002CC45
0x18002cc11  lea     r9, [rbp+7D0h+var_670]; unsigned __int16 *
0x18002cc18  mov     rdx, rbx; unsigned __int16 *
0x18002cc1b  lea     r8, aDefaultsid; "DefaultSID"
0x18002cc22  mov     rcx, r15; HKEY
0x18002cc25  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002cc2a  test    eax, eax
0x18002cc2c  jns     short loc_18002CC45
0x18002cc2e  mov     rcx, [rbp+7D8h]; this
0x18002cc35  mov     r9d, eax; char *
0x18002cc38  mov     r8, r12; unsigned int
0x18002cc3b  mov     edx, 0C9h; void *
0x18002cc40  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002cc45  lea     r8, aDefaultsid; "DefaultSID"
0x18002cc4c  mov     rdx, rsi; pszSubKey
0x18002cc4f  mov     rcx, rdi; hkey
0x18002cc52  call    cs:__imp_SHDeleteValueW
0x18002cc58  lea     r8, aDefaultdomainn; "DefaultDomainName"
0x18002cc5f  mov     rdx, rbx; pszSubKey
0x18002cc62  mov     rcx, r15; hkey
0x18002cc65  call    cs:__imp_SHDeleteValueW
0x18002cc6b  lea     rax, [rsp+8D0h+var_890]
0x18002cc70  mov     [rsp+8D0h+var_890], 202h
0x18002cc78  mov     [rsp+8D0h+pcbData], rax; pcbData
0x18002cc7d  lea     r8, aDefaultdomainn; "DefaultDomainName"
0x18002cc84  lea     rax, [rbp+7D0h+var_460]
0x18002cc8b  mov     r9d, 2; dwFlags
0x18002cc91  mov     [rsp+8D0h+pvData], rax; pvData
0x18002cc96  mov     rdx, rsi; lpSubKey
0x18002cc99  mov     rcx, rdi; hkey
0x18002cc9c  mov     [rsp+8D0h+pdwType], 0; int
0x18002cca5  call    cs:__imp_RegGetValueW
0x18002ccab  test    eax, eax
0x18002ccad  jz      short loc_18002CCC4
0x18002ccaf  xor     ecx, ecx
0x18002ccb1  mov     [rbp+7D0h+var_460], cx
0x18002ccb8  test    eax, eax
0x18002ccba  jle     short loc_18002CCC4
0x18002ccbc  movzx   eax, ax
0x18002ccbf  or      eax, r13d
0x18002ccc2  test    eax, eax
0x18002ccc4  js      short loc_18002CCFA
0x18002ccc6  lea     r9, [rbp+7D0h+var_460]; unsigned __int16 *
0x18002cccd  mov     rdx, rbx; unsigned __int16 *
0x18002ccd0  lea     r8, aDefaultdomainn; "DefaultDomainName"
0x18002ccd7  mov     rcx, r15; HKEY
0x18002ccda  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002ccdf  test    eax, eax
0x18002cce1  jns     short loc_18002CCFA
0x18002cce3  mov     rcx, [rbp+7D8h]; this
0x18002ccea  mov     r9d, eax; char *
0x18002cced  mov     r8, r12; unsigned int
0x18002ccf0  mov     edx, 0D1h; void *
0x18002ccf5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ccfa  lea     r8, aDefaultdomainn; "DefaultDomainName"
0x18002cd01  mov     rdx, rsi; pszSubKey
0x18002cd04  mov     rcx, rdi; hkey
0x18002cd07  call    cs:__imp_SHDeleteValueW
0x18002cd0d  lea     r13, aAutologoncount; "AutoLogonCount"
0x18002cd14  mov     rdx, rbx; pszSubKey
0x18002cd17  mov     r8, r13; pszValue
0x18002cd1a  mov     rcx, r15; hkey
0x18002cd1d  call    cs:__imp_SHDeleteValueW
0x18002cd23  lea     r9, [rsp+8D0h+var_88C]; unsigned int *
0x18002cd28  mov     [rsp+8D0h+var_88C], 0
0x18002cd30  mov     r8, r13; unsigned __int16 *
0x18002cd33  mov     rdx, rsi; unsigned __int16 *
0x18002cd36  mov     rcx, rdi; HKEY
0x18002cd39  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002cd3e  test    eax, eax
0x18002cd40  js      short loc_18002CD70
0x18002cd42  mov     r9d, [rsp+8D0h+var_88C]; unsigned int
0x18002cd47  mov     r8, r13; unsigned __int16 *
0x18002cd4a  mov     rdx, rbx; unsigned __int16 *
0x18002cd4d  mov     rcx, r15; HKEY
0x18002cd50  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002cd55  test    eax, eax
0x18002cd57  jns     short loc_18002CD70
0x18002cd59  mov     rcx, [rbp+7D8h]; this
0x18002cd60  mov     r9d, eax; char *
0x18002cd63  mov     r8, r12; unsigned int
0x18002cd66  mov     edx, 0D9h; void *
0x18002cd6b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002cd70  mov     r8, r13; pszValue
0x18002cd73  mov     rdx, rsi; pszSubKey
0x18002cd76  mov     rcx, rdi; hkey
0x18002cd79  call    cs:__imp_SHDeleteValueW
0x18002cd7f  lea     r13, aAutoadminlogon; "AutoAdminLogon"
0x18002cd86  mov     rdx, rbx; pszSubKey
0x18002cd89  mov     r8, r13; pszValue
0x18002cd8c  mov     rcx, r15; hkey
0x18002cd8f  call    cs:__imp_SHDeleteValueW
0x18002cd95  lea     rax, [rsp+8D0h+var_890]
0x18002cd9a  mov     [rsp+8D0h+var_890], 4
0x18002cda2  mov     [rsp+8D0h+pcbData], rax; pcbData
0x18002cda7  mov     r9d, 2; dwFlags
0x18002cdad  lea     rax, [rsp+8D0h+var_888]
0x18002cdb2  mov     r8, r13; lpValue
0x18002cdb5  mov     [rsp+8D0h+pvData], rax; pvData
0x18002cdba  mov     rdx, rsi; lpSubKey
0x18002cdbd  mov     rcx, rdi; hkey
0x18002cdc0  mov     [rsp+8D0h+pdwType], 0; int
0x18002cdc9  call    cs:__imp_RegGetValueW
0x18002cdcf  test    eax, eax
0x18002cdd1  jz      short loc_18002CDE8
0x18002cdd3  xor     ecx, ecx
0x18002cdd5  mov     [rsp+8D0h+var_888], cx
0x18002cdda  test    eax, eax
0x18002cddc  jle     short loc_18002CDE8
0x18002cdde  movzx   eax, ax
0x18002cde1  or      eax, 80070000h
0x18002cde6  test    eax, eax
0x18002cde8  js      short loc_18002CE18
0x18002cdea  lea     r9, [rsp+8D0h+var_888]; unsigned __int16 *
0x18002cdef  mov     r8, r13; unsigned __int16 *
0x18002cdf2  mov     rdx, rbx; unsigned __int16 *
0x18002cdf5  mov     rcx, r15; HKEY
0x18002cdf8  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002cdfd  test    eax, eax
0x18002cdff  jns     short loc_18002CE18
0x18002ce01  mov     rcx, [rbp+7D8h]; this
0x18002ce08  mov     r9d, eax; char *
0x18002ce0b  mov     r8, r12; unsigned int
0x18002ce0e  mov     edx, 0E1h; void *
0x18002ce13  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ce18  mov     r8, r13; pszValue
0x18002ce1b  mov     rdx, rsi; pszSubKey
0x18002ce1e  mov     rcx, rdi; hkey
0x18002ce21  call    cs:__imp_SHDeleteValueW
0x18002ce27  cmp     [rbp+7D0h+arg_28], 0
0x18002ce2e  jz      loc_18002CEED
0x18002ce34  lea     r8, aDefaultpasswor; "DefaultPassword"
0x18002ce3b  mov     rdx, rbx; pszSubKey
0x18002ce3e  mov     rcx, r15; hkey
0x18002ce41  call    cs:__imp_SHDeleteValueW
0x18002ce47  lea     rax, [rsp+8D0h+var_890]
0x18002ce4c  mov     [rsp+8D0h+var_890], 202h
0x18002ce54  mov     [rsp+8D0h+pcbData], rax; pcbData
0x18002ce59  lea     r8, aDefaultpasswor; "DefaultPassword"
0x18002ce60  lea     rax, [rbp+7D0h+var_250]
0x18002ce67  mov     r9d, 2; dwFlags
0x18002ce6d  mov     [rsp+8D0h+pvData], rax; pvData
0x18002ce72  mov     rdx, rsi; lpSubKey
0x18002ce75  mov     rcx, rdi; hkey
0x18002ce78  mov     [rsp+8D0h+pdwType], 0; int
0x18002ce81  call    cs:__imp_RegGetValueW
0x18002ce87  test    eax, eax
0x18002ce89  jz      short loc_18002CEA2
0x18002ce8b  xor     ecx, ecx
0x18002ce8d  mov     [rbp+7D0h+var_250], cx
0x18002ce94  test    eax, eax
0x18002ce96  jle     short loc_18002CEA2
0x18002ce98  movzx   eax, ax
0x18002ce9b  or      eax, 80070000h
0x18002cea0  test    eax, eax
0x18002cea2  js      short loc_18002CED8
0x18002cea4  lea     r9, [rbp+7D0h+var_250]; unsigned __int16 *
0x18002ceab  mov     rdx, rbx; unsigned __int16 *
0x18002ceae  lea     r8, aDefaultpasswor; "DefaultPassword"
0x18002ceb5  mov     rcx, r15; HKEY
0x18002ceb8  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002cebd  test    eax, eax
0x18002cebf  jns     short loc_18002CED8
0x18002cec1  mov     rcx, [rbp+7D8h]; this
0x18002cec8  mov     r9d, eax; char *
0x18002cecb  mov     r8, r12; unsigned int
0x18002cece  mov     edx, 0EBh; void *
0x18002ced3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ced8  lea     r8, aDefaultpasswor; "DefaultPassword"
0x18002cedf  mov     rdx, rsi; pszSubKey
0x18002cee2  mov     rcx, rdi; hkey
0x18002cee5  call    cs:__imp_SHDeleteValueW
0x18002ceeb  jmp     short loc_18002CF3E
0x18002ceed  cmp     rdi, r15
0x18002cef0  jnz     short loc_18002CF10
0x18002cef2  lea     rdx, aCacheddefaultp; "CachedDefaultPassword"
0x18002cef9  lea     rcx, aDefaultpasswor; "DefaultPassword"
0x18002cf00  call    ?_MoveLsaSecret@@YAJPEBG0@Z; _MoveLsaSecret(ushort const *,ushort const *)
0x18002cf05  test    eax, eax
0x18002cf07  jns     short loc_18002CF3E
0x18002cf09  mov     edx, 0F6h
0x18002cf0e  jmp     short loc_18002CF2C
0x18002cf10  lea     rdx, aDefaultpasswor; "DefaultPassword"
0x18002cf17  lea     rcx, aCacheddefaultp; "CachedDefaultPassword"
0x18002cf1e  call    ?_MoveLsaSecret@@YAJPEBG0@Z; _MoveLsaSecret(ushort const *,ushort const *)
0x18002cf23  test    eax, eax
0x18002cf25  jns     short loc_18002CF3E
0x18002cf27  mov     edx, 0FAh; void *
0x18002cf2c  mov     rcx, [rbp+7D8h]; this
0x18002cf33  mov     r9d, eax; char *
0x18002cf36  mov     r8, r12; unsigned int
0x18002cf39  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002cf3e  xor     eax, eax
0x18002cf40  mov     rcx, [rbp+7D0h+var_40]
0x18002cf47  xor     rcx, rsp; StackCookie
0x18002cf4a  call    __security_check_cookie
0x18002cf4f  add     rsp, 8A0h
0x18002cf56  pop     r15
0x18002cf58  pop     r13
  ... truncated ...
```
