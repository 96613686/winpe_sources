# CAutoVerifierPlugin::SetAutoverifierEnabledFlag(ulong)

- ea: `0x14004aca8`
- end: `0x14004aec0`
- name: `?SetAutoverifierEnabledFlag@CAutoVerifierPlugin@@AEAAJK@Z`
- size: `536`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140049240`
- `0x140049364`

## callees

- `0x140005468`
- `0x14001444c`
- `0x140014474`
- `0x14004aca8`
- `0x140054aa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004aea2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004aeb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004aea2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004aeb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004ae69`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14004ae69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004ad15`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004addc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004ad15`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004addc`

## string_xrefs

- `0x14004ace6`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins`

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
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
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
  v8 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v16);
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
0x14004aca8  mov     [rsp-10h+Data], edx
0x14004acac  mov     qword ptr [rsp-10h+dwDisposition], rcx
0x14004acb1  push    rbp
0x14004acb2  push    rbx
0x14004acb3  mov     rbp, rsp
0x14004acb6  sub     rsp, 58h
0x14004acba  lea     rcx, [rbp+hKey]
0x14004acbe  mov     [rbp+arg_18], 0
0x14004acc6  mov     [rbp+hKey], 0
0x14004acce  mov     [rbp+dwDisposition], 0
0x14004acd5  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004acda  lea     rcx, [rbp+dwDisposition]
0x14004acde  xor     r9d, r9d; lpClass
0x14004ace1  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x14004ace6  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows\\Windows E"...
0x14004aced  mov     [rsp+58h+phkResult], rax; phkResult
0x14004acf2  xor     r8d, r8d; Reserved
0x14004acf5  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14004acfe  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14004ad05  mov     [rsp+58h+samDesired], 60004h; samDesired
0x14004ad0d  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14004ad15  call    cs:__imp_RegCreateKeyExW
0x14004ad1b  test    eax, eax
0x14004ad1d  jz      short loc_14004AD57
0x14004ad1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ad26  lea     rbx, WPP_GLOBAL_Control
0x14004ad2d  cmp     rcx, rbx
0x14004ad30  jz      short loc_14004AD4D
0x14004ad32  test    byte ptr [rcx+1Ch], 1
0x14004ad36  jz      short loc_14004AD4D
0x14004ad38  mov     edx, 26h ; '&'
0x14004ad3d  mov     rcx, [rcx+10h]
0x14004ad41  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004ad48  call    WPP_SF_
0x14004ad4d  mov     ebx, 80004005h
0x14004ad52  jmp     loc_14004AE99
0x14004ad57  mov     rcx, [rbp+hKey]; hKey
0x14004ad5b  mov     r8d, 80000002h; unsigned int
0x14004ad61  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x14004ad66  lea     rbx, WPP_GLOBAL_Control
0x14004ad6d  test    eax, eax
0x14004ad6f  jns     short loc_14004AD9B
0x14004ad71  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ad78  cmp     rcx, rbx
0x14004ad7b  jz      short loc_14004AD9B
0x14004ad7d  test    byte ptr [rcx+1Ch], 2
0x14004ad81  jz      short loc_14004AD9B
0x14004ad83  mov     rcx, [rcx+10h]
0x14004ad87  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004ad8e  mov     edx, 27h ; '''
0x14004ad93  mov     r9d, eax
0x14004ad96  call    WPP_SF_d
0x14004ad9b  lea     rcx, [rbp+arg_18]
0x14004ad9f  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004ada4  lea     rcx, [rbp+dwDisposition]
0x14004ada8  xor     r9d, r9d; lpClass
0x14004adab  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x14004adb0  lea     rdx, aAutoverifier; "Autoverifier"
0x14004adb7  mov     rcx, [rbp+hKey]; hKey
0x14004adbb  xor     r8d, r8d; Reserved
0x14004adbe  mov     [rsp+58h+phkResult], rax; phkResult
0x14004adc3  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14004adcc  mov     [rsp+58h+samDesired], 60002h; samDesired
0x14004add4  mov     [rsp+58h+dwOptions], 1; dwOptions
0x14004addc  call    cs:__imp_RegCreateKeyExW
0x14004ade2  test    eax, eax
0x14004ade4  jz      short loc_14004AE0A
0x14004ade6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004aded  cmp     rcx, rbx
0x14004adf0  jz      loc_14004AD4D
0x14004adf6  test    byte ptr [rcx+1Ch], 1
0x14004adfa  jz      loc_14004AD4D
0x14004ae00  mov     edx, 28h ; '('
0x14004ae05  jmp     loc_14004AD3D
0x14004ae0a  mov     rcx, [rbp+hKey]; hKey
0x14004ae0e  mov     r8d, 80000002h; unsigned int
0x14004ae14  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x14004ae19  test    eax, eax
0x14004ae1b  jns     short loc_14004AE47
0x14004ae1d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ae24  cmp     rcx, rbx
0x14004ae27  jz      short loc_14004AE47
0x14004ae29  test    byte ptr [rcx+1Ch], 2
0x14004ae2d  jz      short loc_14004AE47
0x14004ae2f  mov     rcx, [rcx+10h]
0x14004ae33  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004ae3a  mov     edx, 29h ; ')'
0x14004ae3f  mov     r9d, eax
0x14004ae42  call    WPP_SF_d
0x14004ae47  mov     rcx, [rbp+arg_18]; hKey
0x14004ae4b  lea     rax, [rbp+Data]
0x14004ae4f  mov     r9d, 4; dwType
0x14004ae55  lea     rdx, aAutoverifieren; "AutoverifierEnabled"
0x14004ae5c  mov     [rsp+58h+samDesired], r9d; cbData
0x14004ae61  xor     r8d, r8d; Reserved
0x14004ae64  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x14004ae69  call    cs:__imp_RegSetValueExW
0x14004ae6f  test    eax, eax
0x14004ae71  jz      short loc_14004AE97
0x14004ae73  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ae7a  cmp     rcx, rbx
0x14004ae7d  jz      loc_14004AD4D
0x14004ae83  test    byte ptr [rcx+1Ch], 1
0x14004ae87  jz      loc_14004AD4D
0x14004ae8d  mov     edx, 2Ah ; '*'
0x14004ae92  jmp     loc_14004AD3D
0x14004ae97  xor     ebx, ebx
0x14004ae99  mov     rcx, [rbp+hKey]; hKey
0x14004ae9d  test    rcx, rcx
0x14004aea0  jz      short loc_14004AEA8
0x14004aea2  call    cs:__imp_RegCloseKey
0x14004aea8  mov     rcx, [rbp+arg_18]; hKey
0x14004aeac  test    rcx, rcx
0x14004aeaf  jz      short loc_14004AEB7
0x14004aeb1  call    cs:__imp_RegCloseKey
0x14004aeb7  mov     eax, ebx
0x14004aeb9  add     rsp, 58h
0x14004aebd  pop     rbx
0x14004aebe  pop     rbp
0x14004aebf  retn
```
