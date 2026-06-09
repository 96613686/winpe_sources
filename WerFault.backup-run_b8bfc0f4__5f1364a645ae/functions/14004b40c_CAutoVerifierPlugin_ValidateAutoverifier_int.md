# CAutoVerifierPlugin::ValidateAutoverifier(int *)

- ea: `0x14004b40c`
- end: `0x14004b5dd`
- name: `?ValidateAutoverifier@CAutoVerifierPlugin@@AEAAJPEAH@Z`
- size: `465`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140049364`

## callees

- `0x140005468`
- `0x14001444c`
- `0x140048fbc`
- `0x1400490b8`
- `0x14004b40c`
- `0x1400549e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004b463`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004b5ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004b463`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004b5ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004b50b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004b50b`

## string_xrefs

- `0x14004b4dc`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins`

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
0x14004b40c  mov     [rsp+arg_0], rbx
0x14004b411  push    rdi
0x14004b412  sub     rsp, 50h
0x14004b416  mov     rax, rcx
0x14004b419  mov     rdi, rdx
0x14004b41c  xor     ecx, ecx
0x14004b41e  mov     [rsp+58h+hKey], rcx
0x14004b423  mov     [rsp+58h+dwDisposition], ecx
0x14004b427  test    rdx, rdx
0x14004b42a  jnz     short loc_14004B473
0x14004b42c  mov     r9, cs:WPP_GLOBAL_Control
0x14004b433  lea     rax, WPP_GLOBAL_Control
0x14004b43a  cmp     r9, rax
0x14004b43d  jz      short loc_14004B45E
0x14004b43f  test    byte ptr [r9+1Ch], 1
0x14004b444  jz      short loc_14004B45E
0x14004b446  mov     rcx, [r9+10h]
0x14004b44a  lea     edx, [rdi+1Eh]
0x14004b44d  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004b454  call    WPP_SF_
0x14004b459  mov     rcx, [rsp+58h+hKey]; hKey
0x14004b45e  test    rcx, rcx
0x14004b461  jz      short loc_14004B469
0x14004b463  call    cs:__imp_RegCloseKey
0x14004b469  mov     eax, 80070057h
0x14004b46e  jmp     loc_14004B5D2
0x14004b473  mov     rcx, rax; this
0x14004b476  call    ?CheckSettingsAndVersion@CAutoVerifierPlugin@@AEAAJPEAH@Z; CAutoVerifierPlugin::CheckSettingsAndVersion(int *)
0x14004b47b  mov     ebx, eax
0x14004b47d  test    eax, eax
0x14004b47f  jns     short loc_14004B4BC
0x14004b481  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b488  lea     rax, WPP_GLOBAL_Control
0x14004b48f  cmp     rcx, rax
0x14004b492  jz      loc_14004B5C0
0x14004b498  test    byte ptr [rcx+1Ch], 1
0x14004b49c  jz      loc_14004B5C0
0x14004b4a2  mov     edx, 1Fh
0x14004b4a7  mov     rcx, [rcx+10h]
0x14004b4ab  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004b4b2  call    WPP_SF_
0x14004b4b7  jmp     loc_14004B5C0
0x14004b4bc  cmp     dword ptr [rdi], 0
0x14004b4bf  jz      loc_14004B5BE
0x14004b4c5  lea     rcx, [rsp+58h+hKey]
0x14004b4ca  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004b4cf  lea     rcx, [rsp+58h+dwDisposition]
0x14004b4d4  xor     r9d, r9d; lpClass
0x14004b4d7  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x14004b4dc  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\Windows E"...
0x14004b4e3  mov     [rsp+58h+phkResult], rax; phkResult
0x14004b4e8  xor     r8d, r8d; Reserved
0x14004b4eb  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14004b4f4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14004b4fb  mov     [rsp+58h+samDesired], 5; samDesired
0x14004b503  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14004b50b  call    cs:__imp_RegCreateKeyExW
0x14004b511  test    eax, eax
0x14004b513  jz      short loc_14004B54A
0x14004b515  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b51c  lea     rax, WPP_GLOBAL_Control
0x14004b523  cmp     rcx, rax
0x14004b526  jz      short loc_14004B543
0x14004b528  test    byte ptr [rcx+1Ch], 1
0x14004b52c  jz      short loc_14004B543
0x14004b52e  mov     rcx, [rcx+10h]
0x14004b532  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004b539  mov     edx, 20h ; ' '
0x14004b53e  call    WPP_SF_
0x14004b543  mov     ebx, 80004005h
0x14004b548  jmp     short loc_14004B5C0
0x14004b54a  mov     rcx, [rsp+58h+hKey]; HKEY
0x14004b54f  xor     edx, edx; wchar_t *
0x14004b551  mov     qword ptr [rsp+58h+dwOptions], rdi; int *
0x14004b556  lea     r9d, [rdx+2]; unsigned int
0x14004b55a  call    ?CheckPluginLastPromptedTime@@YAJPEAUHKEY__@@PEB_W1KPEAH@Z; CheckPluginLastPromptedTime(HKEY__ *,wchar_t const *,wchar_t const *,ulong,int *)
0x14004b55f  mov     ebx, eax
0x14004b561  test    eax, eax
0x14004b563  jns     short loc_14004B588
0x14004b565  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b56c  lea     rax, WPP_GLOBAL_Control
0x14004b573  cmp     rcx, rax
0x14004b576  jz      short loc_14004B5C0
0x14004b578  test    byte ptr [rcx+1Ch], 1
0x14004b57c  jz      short loc_14004B5C0
0x14004b57e  mov     edx, 21h ; '!'
0x14004b583  jmp     loc_14004B4A7
0x14004b588  cmp     dword ptr [rdi], 0
0x14004b58b  jz      short loc_14004B5BE
0x14004b58d  mov     rdx, rdi; int *
0x14004b590  call    ?CheckForMonitoredApplications@CAutoVerifierPlugin@@AEAAJPEAH@Z; CAutoVerifierPlugin::CheckForMonitoredApplications(int *)
0x14004b595  mov     ebx, eax
0x14004b597  test    eax, eax
0x14004b599  jns     short loc_14004B5BE
0x14004b59b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b5a2  lea     rax, WPP_GLOBAL_Control
0x14004b5a9  cmp     rcx, rax
0x14004b5ac  jz      short loc_14004B5C0
0x14004b5ae  test    byte ptr [rcx+1Ch], 1
0x14004b5b2  jz      short loc_14004B5C0
0x14004b5b4  mov     edx, 22h ; '"'
0x14004b5b9  jmp     loc_14004B4A7
0x14004b5be  xor     ebx, ebx
0x14004b5c0  mov     rcx, [rsp+58h+hKey]; hKey
0x14004b5c5  test    rcx, rcx
0x14004b5c8  jz      short loc_14004B5D0
0x14004b5ca  call    cs:__imp_RegCloseKey
0x14004b5d0  mov     eax, ebx
0x14004b5d2  mov     rbx, [rsp+58h+arg_0]
0x14004b5d7  add     rsp, 50h
0x14004b5db  pop     rdi
0x14004b5dc  retn
```
