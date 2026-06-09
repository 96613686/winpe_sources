# CAutoVerifierPlugin::SetAutoverifierEnabledFlag(ulong)

- ea: `0x14004e104`
- end: `0x14004e33b`
- name: `?SetAutoverifierEnabledFlag@CAutoVerifierPlugin@@AEAAJK@Z`
- size: `567`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004c5b4`
- `0x14004c6e0`

## callees

- `0x14000551c`
- `0x140014ee4`
- `0x140014f14`
- `0x14004e104`
- `0x1400584c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e310`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e325`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e310`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e325`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004e2d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004e2d1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004e171`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004e23e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004e171`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004e23e`

## string_xrefs

- `0x14004e142`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins`

## pseudocode

```c
__int64 __fastcall CAutoVerifierPlugin::SetAutoverifierEnabledFlag(CAutoVerifierPlugin *this, int a2)
{
  HKEY *phkResult; // rax
  enum _ACCESS_MODE v3; // edx
  CUserModeHangReport *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int v7; // eax
  HKEY *v8; // rax
  enum _ACCESS_MODE v9; // edx
  int v10; // eax
  DWORD dwDisposition; // [rsp+70h] [rbp+18h] BYREF
  int v13; // [rsp+74h] [rbp+1Ch]
  int Data; // [rsp+78h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+28h] BYREF
  HKEY v16; // [rsp+88h] [rbp+30h] BYREF

  Data = a2;
  v13 = HIDWORD(this);
  v16 = 0;
  hKey = 0;
  dwDisposition = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins",
         0,
         0,
         0,
         0x60004u,
         0,
         phkResult,
         &dwDisposition) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_6;
    }
    v5 = 38;
LABEL_5:
    WPP_SF_(*((_QWORD *)v4 + 2), v5, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
LABEL_6:
    v6 = -2147467259;
    goto LABEL_24;
  }
  v7 = WerPluginAdjustAppContainerAccessToKey(hKey, v3, 0x80000002);
  if ( v7 < 0
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids, (unsigned int)v7);
  }
  v8 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v16);
  if ( RegCreateKeyExW(hKey, L"Autoverifier", 0, 0, 1u, 0x60002u, 0, v8, &dwDisposition) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_6;
    }
    v5 = 40;
    goto LABEL_5;
  }
  v10 = WerPluginAdjustAppContainerAccessToKey(hKey, v9, 0x80000002);
  if ( v10 < 0
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids,
      (unsigned int)v10);
  }
  if ( RegSetValueExW(v16, L"AutoverifierEnabled", 0, 4u, (const BYTE *)&Data, 4u) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_6;
    }
    v5 = 42;
    goto LABEL_5;
  }
  v6 = 0;
LABEL_24:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v16 )
    RegCloseKey(v16);
  return v6;
}

```

## disassembly

```asm
0x14004e104  mov     [rsp-10h+Data], edx
0x14004e108  mov     qword ptr [rsp-10h+dwDisposition], rcx
0x14004e10d  push    rbp
0x14004e10e  push    rbx
0x14004e10f  mov     rbp, rsp
0x14004e112  sub     rsp, 58h
0x14004e116  lea     rcx, [rbp+hKey]
0x14004e11a  mov     [rbp+arg_18], 0
0x14004e122  mov     [rbp+hKey], 0
0x14004e12a  mov     [rbp+dwDisposition], 0
0x14004e131  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004e136  lea     rcx, [rbp+dwDisposition]
0x14004e13a  xor     r9d, r9d; lpClass
0x14004e13d  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x14004e142  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\Windows E"...
0x14004e149  mov     [rsp+58h+phkResult], rax; phkResult
0x14004e14e  xor     r8d, r8d; Reserved
0x14004e151  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14004e15a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14004e161  mov     [rsp+58h+samDesired], 60004h; samDesired
0x14004e169  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14004e171  call    cs:__imp_RegCreateKeyExW
0x14004e178  nop     dword ptr [rax+rax+00h]
0x14004e17d  test    eax, eax
0x14004e17f  jz      short loc_14004E1B9
0x14004e181  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e188  lea     rbx, WPP_GLOBAL_Control
0x14004e18f  cmp     rcx, rbx
0x14004e192  jz      short loc_14004E1AF
0x14004e194  test    byte ptr [rcx+1Ch], 1
0x14004e198  jz      short loc_14004E1AF
0x14004e19a  mov     edx, 26h ; '&'
0x14004e19f  mov     rcx, [rcx+10h]
0x14004e1a3  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004e1aa  call    WPP_SF_
0x14004e1af  mov     ebx, 80004005h
0x14004e1b4  jmp     loc_14004E307
0x14004e1b9  mov     rcx, [rbp+hKey]; hKey
0x14004e1bd  mov     r8d, 80000002h; unsigned int
0x14004e1c3  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x14004e1c8  lea     rbx, WPP_GLOBAL_Control
0x14004e1cf  test    eax, eax
0x14004e1d1  jns     short loc_14004E1FD
0x14004e1d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e1da  cmp     rcx, rbx
0x14004e1dd  jz      short loc_14004E1FD
0x14004e1df  test    byte ptr [rcx+1Ch], 2
0x14004e1e3  jz      short loc_14004E1FD
0x14004e1e5  mov     rcx, [rcx+10h]
0x14004e1e9  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004e1f0  mov     edx, 27h ; '''
0x14004e1f5  mov     r9d, eax
0x14004e1f8  call    WPP_SF_d
0x14004e1fd  lea     rcx, [rbp+arg_18]
0x14004e201  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004e206  lea     rcx, [rbp+dwDisposition]
0x14004e20a  xor     r9d, r9d; lpClass
0x14004e20d  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x14004e212  lea     rdx, aAutoverifier; "Autoverifier"
0x14004e219  mov     rcx, [rbp+hKey]; hKey
0x14004e21d  xor     r8d, r8d; Reserved
0x14004e220  mov     [rsp+58h+phkResult], rax; phkResult
0x14004e225  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14004e22e  mov     [rsp+58h+samDesired], 60002h; samDesired
0x14004e236  mov     [rsp+58h+dwOptions], 1; dwOptions
0x14004e23e  call    cs:__imp_RegCreateKeyExW
0x14004e245  nop     dword ptr [rax+rax+00h]
0x14004e24a  test    eax, eax
0x14004e24c  jz      short loc_14004E272
0x14004e24e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e255  cmp     rcx, rbx
0x14004e258  jz      loc_14004E1AF
0x14004e25e  test    byte ptr [rcx+1Ch], 1
0x14004e262  jz      loc_14004E1AF
0x14004e268  mov     edx, 28h ; '('
0x14004e26d  jmp     loc_14004E19F
0x14004e272  mov     rcx, [rbp+hKey]; hKey
0x14004e276  mov     r8d, 80000002h; unsigned int
0x14004e27c  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x14004e281  test    eax, eax
0x14004e283  jns     short loc_14004E2AF
0x14004e285  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e28c  cmp     rcx, rbx
0x14004e28f  jz      short loc_14004E2AF
0x14004e291  test    byte ptr [rcx+1Ch], 2
0x14004e295  jz      short loc_14004E2AF
0x14004e297  mov     rcx, [rcx+10h]
0x14004e29b  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004e2a2  mov     edx, 29h ; ')'
0x14004e2a7  mov     r9d, eax
0x14004e2aa  call    WPP_SF_d
0x14004e2af  mov     rcx, [rbp+arg_18]; hKey
0x14004e2b3  lea     rax, [rbp+Data]
0x14004e2b7  mov     r9d, 4; dwType
0x14004e2bd  lea     rdx, aAutoverifieren; "AutoverifierEnabled"
0x14004e2c4  mov     [rsp+58h+samDesired], r9d; cbData
0x14004e2c9  xor     r8d, r8d; Reserved
0x14004e2cc  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x14004e2d1  call    cs:__imp_RegSetValueExW
0x14004e2d8  nop     dword ptr [rax+rax+00h]
0x14004e2dd  test    eax, eax
0x14004e2df  jz      short loc_14004E305
0x14004e2e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e2e8  cmp     rcx, rbx
0x14004e2eb  jz      loc_14004E1AF
0x14004e2f1  test    byte ptr [rcx+1Ch], 1
0x14004e2f5  jz      loc_14004E1AF
0x14004e2fb  mov     edx, 2Ah ; '*'
0x14004e300  jmp     loc_14004E19F
0x14004e305  xor     ebx, ebx
0x14004e307  mov     rcx, [rbp+hKey]; hKey
0x14004e30b  test    rcx, rcx
0x14004e30e  jz      short loc_14004E31C
0x14004e310  call    cs:__imp_RegCloseKey
0x14004e317  nop     dword ptr [rax+rax+00h]
0x14004e31c  mov     rcx, [rbp+arg_18]; hKey
0x14004e320  test    rcx, rcx
0x14004e323  jz      short loc_14004E331
0x14004e325  call    cs:__imp_RegCloseKey
0x14004e32c  nop     dword ptr [rax+rax+00h]
0x14004e331  mov     eax, ebx
0x14004e333  add     rsp, 58h
0x14004e337  pop     rbx
0x14004e338  pop     rbp
0x14004e339  retn
```
