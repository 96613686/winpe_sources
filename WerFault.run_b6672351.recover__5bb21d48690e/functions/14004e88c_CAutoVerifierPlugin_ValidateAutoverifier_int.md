# CAutoVerifierPlugin::ValidateAutoverifier(int *)

- ea: `0x14004e88c`
- end: `0x14004ea70`
- name: `?ValidateAutoverifier@CAutoVerifierPlugin@@AEAAJPEAH@Z`
- size: `484`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004c6e0`

## callees

- `0x14000551c`
- `0x140014ee4`
- `0x14004c30c`
- `0x14004c410`
- `0x14004e88c`
- `0x140058408`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e8e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004ea56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e8e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004ea56`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004e991`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004e991`

## string_xrefs

- `0x14004e962`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins`

## pseudocode

```c
__int64 __fastcall CAutoVerifierPlugin::ValidateAutoverifier(CAutoVerifierPlugin *this, int *a2)
{
  HKEY v4; // rcx
  int v6; // ebx
  CUserModeHangReport *v7; // rcx
  __int64 v8; // rdx
  HKEY *phkResult; // rax
  const wchar_t *v10; // r8
  CAutoVerifierPlugin *v11; // rcx
  DWORD dwDisposition; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v4 = 0;
  hKey = 0;
  dwDisposition = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
      v4 = hKey;
    }
    if ( v4 )
      RegCloseKey(v4);
    return 2147942487LL;
  }
  v6 = CAutoVerifierPlugin::CheckSettingsAndVersion(this, a2);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_29;
    }
    v8 = 31;
    goto LABEL_12;
  }
  if ( !*a2 )
    goto LABEL_28;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins",
         0,
         0,
         0,
         5u,
         0,
         phkResult,
         &dwDisposition) )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    }
    v6 = -2147467259;
    goto LABEL_29;
  }
  v6 = CheckPluginLastPromptedTime(hKey, 0, v10, 2u, a2);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_29;
    }
    v8 = 33;
    goto LABEL_12;
  }
  if ( !*a2 || (v6 = CAutoVerifierPlugin::CheckForMonitoredApplications(v11, a2), v6 >= 0) )
  {
LABEL_28:
    v6 = 0;
    goto LABEL_29;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    goto LABEL_29;
  }
  v8 = 34;
LABEL_12:
  WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14004e88c  mov     [rsp+arg_0], rbx
0x14004e891  push    rdi
0x14004e892  sub     rsp, 50h
0x14004e896  mov     rax, rcx
0x14004e899  mov     rdi, rdx
0x14004e89c  xor     ecx, ecx
0x14004e89e  mov     [rsp+58h+hKey], rcx
0x14004e8a3  mov     [rsp+58h+dwDisposition], ecx
0x14004e8a7  test    rdx, rdx
0x14004e8aa  jnz     short loc_14004E8F9
0x14004e8ac  mov     r9, cs:WPP_GLOBAL_Control
0x14004e8b3  lea     rax, WPP_GLOBAL_Control
0x14004e8ba  cmp     r9, rax
0x14004e8bd  jz      short loc_14004E8DE
0x14004e8bf  test    byte ptr [r9+1Ch], 1
0x14004e8c4  jz      short loc_14004E8DE
0x14004e8c6  mov     rcx, [r9+10h]
0x14004e8ca  lea     edx, [rdi+1Eh]
0x14004e8cd  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004e8d4  call    WPP_SF_
0x14004e8d9  mov     rcx, [rsp+58h+hKey]; hKey
0x14004e8de  test    rcx, rcx
0x14004e8e1  jz      short loc_14004E8EF
0x14004e8e3  call    cs:__imp_RegCloseKey
0x14004e8ea  nop     dword ptr [rax+rax+00h]
0x14004e8ef  mov     eax, 80070057h
0x14004e8f4  jmp     loc_14004EA64
0x14004e8f9  mov     rcx, rax; this
0x14004e8fc  call    ?CheckSettingsAndVersion@CAutoVerifierPlugin@@AEAAJPEAH@Z; CAutoVerifierPlugin::CheckSettingsAndVersion(int *)
0x14004e901  mov     ebx, eax
0x14004e903  test    eax, eax
0x14004e905  jns     short loc_14004E942
0x14004e907  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e90e  lea     rax, WPP_GLOBAL_Control
0x14004e915  cmp     rcx, rax
0x14004e918  jz      loc_14004EA4C
0x14004e91e  test    byte ptr [rcx+1Ch], 1
0x14004e922  jz      loc_14004EA4C
0x14004e928  mov     edx, 1Fh
0x14004e92d  mov     rcx, [rcx+10h]
0x14004e931  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004e938  call    WPP_SF_
0x14004e93d  jmp     loc_14004EA4C
0x14004e942  cmp     dword ptr [rdi], 0
0x14004e945  jz      loc_14004EA4A
0x14004e94b  lea     rcx, [rsp+58h+hKey]
0x14004e950  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004e955  lea     rcx, [rsp+58h+dwDisposition]
0x14004e95a  xor     r9d, r9d; lpClass
0x14004e95d  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x14004e962  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\Windows E"...
0x14004e969  mov     [rsp+58h+phkResult], rax; phkResult
0x14004e96e  xor     r8d, r8d; Reserved
0x14004e971  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14004e97a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14004e981  mov     [rsp+58h+samDesired], 5; samDesired
0x14004e989  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14004e991  call    cs:__imp_RegCreateKeyExW
0x14004e998  nop     dword ptr [rax+rax+00h]
0x14004e99d  test    eax, eax
0x14004e99f  jz      short loc_14004E9D6
0x14004e9a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e9a8  lea     rax, WPP_GLOBAL_Control
0x14004e9af  cmp     rcx, rax
0x14004e9b2  jz      short loc_14004E9CF
0x14004e9b4  test    byte ptr [rcx+1Ch], 1
0x14004e9b8  jz      short loc_14004E9CF
0x14004e9ba  mov     rcx, [rcx+10h]
0x14004e9be  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004e9c5  mov     edx, 20h ; ' '
0x14004e9ca  call    WPP_SF_
0x14004e9cf  mov     ebx, 80004005h
0x14004e9d4  jmp     short loc_14004EA4C
0x14004e9d6  mov     rcx, [rsp+58h+hKey]; HKEY
0x14004e9db  xor     edx, edx; wchar_t *
0x14004e9dd  mov     qword ptr [rsp+58h+dwOptions], rdi; int *
0x14004e9e2  lea     r9d, [rdx+2]; unsigned int
0x14004e9e6  call    ?CheckPluginLastPromptedTime@@YAJPEAUHKEY__@@PEB_W1KPEAH@Z; CheckPluginLastPromptedTime(HKEY__ *,wchar_t const *,wchar_t const *,ulong,int *)
0x14004e9eb  mov     ebx, eax
0x14004e9ed  test    eax, eax
0x14004e9ef  jns     short loc_14004EA14
0x14004e9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e9f8  lea     rax, WPP_GLOBAL_Control
0x14004e9ff  cmp     rcx, rax
0x14004ea02  jz      short loc_14004EA4C
0x14004ea04  test    byte ptr [rcx+1Ch], 1
0x14004ea08  jz      short loc_14004EA4C
0x14004ea0a  mov     edx, 21h ; '!'
0x14004ea0f  jmp     loc_14004E92D
0x14004ea14  cmp     dword ptr [rdi], 0
0x14004ea17  jz      short loc_14004EA4A
0x14004ea19  mov     rdx, rdi; int *
0x14004ea1c  call    ?CheckForMonitoredApplications@CAutoVerifierPlugin@@AEAAJPEAH@Z; CAutoVerifierPlugin::CheckForMonitoredApplications(int *)
0x14004ea21  mov     ebx, eax
0x14004ea23  test    eax, eax
0x14004ea25  jns     short loc_14004EA4A
0x14004ea27  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ea2e  lea     rax, WPP_GLOBAL_Control
0x14004ea35  cmp     rcx, rax
0x14004ea38  jz      short loc_14004EA4C
0x14004ea3a  test    byte ptr [rcx+1Ch], 1
0x14004ea3e  jz      short loc_14004EA4C
0x14004ea40  mov     edx, 22h ; '"'
0x14004ea45  jmp     loc_14004E92D
0x14004ea4a  xor     ebx, ebx
0x14004ea4c  mov     rcx, [rsp+58h+hKey]; hKey
0x14004ea51  test    rcx, rcx
0x14004ea54  jz      short loc_14004EA62
0x14004ea56  call    cs:__imp_RegCloseKey
0x14004ea5d  nop     dword ptr [rax+rax+00h]
0x14004ea62  mov     eax, ebx
0x14004ea64  mov     rbx, [rsp+58h+arg_0]
0x14004ea69  add     rsp, 50h
0x14004ea6d  pop     rdi
0x14004ea6e  retn
```
