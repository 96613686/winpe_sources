# CAutoVerifierPlugin::EnableAutoVerifier(void *)

- ea: `0x140049364`
- end: `0x140049863`
- name: `?EnableAutoVerifier@CAutoVerifierPlugin@@AEAAJPEAX@Z`
- size: `1279`
- prototype: `__int64 __fastcall(LPCWSTR *this, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004a280`

## callees

- `0x140005468`
- `0x14001444c`
- `0x140014474`
- `0x140015b40`
- `0x140049364`
- `0x14004986c`
- `0x14004a768`
- `0x14004aca8`
- `0x14004b40c`
- `0x140054aa0`
- `0x1400551c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400496e2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400496f6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004970a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004971e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400496e2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400496f6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004970a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004971e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400493d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400493e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400493f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049823`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049833`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049843`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400493d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400493e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400493f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049823`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049833`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049843`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140049532`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140049586`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004966d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140049532`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140049586`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004966d`

## pseudocode

```c
__int64 __fastcall CAutoVerifierPlugin::EnableAutoVerifier(LPCWSTR *this, void *a2)
{
  int v5; // edi
  CUserModeHangReport *v6; // rcx
  __int64 v7; // rdx
  CAutoVerifierPlugin *v8; // rcx
  HKEY *phkResult; // rax
  HKEY *v10; // rax
  enum _ACCESS_MODE v11; // edx
  int v12; // eax
  int v13; // eax
  CUserModeHangReport *v14; // rcx
  __int64 v15; // rdx
  HKEY *v16; // rax
  enum _ACCESS_MODE v17; // edx
  int v18; // eax
  unsigned int i; // edi
  __int64 v20; // r12
  __int64 v21; // rcx
  int v22; // eax
  CAutoVerifierPlugin *v23; // rcx
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY v25; // [rsp+58h] [rbp-8h] BYREF
  int v26; // [rsp+A8h] [rbp+48h] BYREF
  DWORD dwDisposition; // [rsp+B0h] [rbp+50h] BYREF
  HKEY v28; // [rsp+B8h] [rbp+58h] BYREF

  v25 = 0;
  v28 = 0;
  hKey = 0;
  dwDisposition = 0;
  v26 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    }
    if ( v28 )
      RegCloseKey(v28);
    return 2147942487LL;
  }
  v5 = CAutoVerifierPlugin::ValidateAutoverifier((CAutoVerifierPlugin *)this, &v26);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_69;
    }
    v7 = 54;
    goto LABEL_68;
  }
  if ( !v26 )
  {
    v5 = 1;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_69;
    }
    v7 = 55;
    goto LABEL_68;
  }
  if ( !(unsigned int)CAutoVerifierPlugin::PromptForEnableAutoVerifier((CAutoVerifierPlugin *)this, a2) )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    }
    v5 = 1;
    goto LABEL_69;
  }
  v5 = CAutoVerifierPlugin::SetAutoverifierEnabledFlag(v8, 1u);
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_69;
    }
    v7 = 57;
    goto LABEL_68;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v25);
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options",
         0,
         0,
         0,
         0xF003Fu,
         0,
         phkResult,
         0)
    || !v25 )
  {
    v5 = -2147467259;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_69;
    }
    v7 = 58;
LABEL_68:
    WPP_SF_(*((_QWORD *)v6 + 2), v7, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    goto LABEL_69;
  }
  v10 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v28);
  if ( RegCreateKeyExW(v25, this[93], 0, 0, 1u, 0x60002u, 0, v10, &dwDisposition) || !v28 )
  {
    v5 = -2147467259;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_69;
    }
    v7 = 59;
    goto LABEL_68;
  }
  v12 = WerPluginAdjustAppContainerAccessToKey(v28, v11, 0x80010000);
  if ( v12 < 0
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids,
      (unsigned int)v12);
  }
  v13 = WerPluginWriteSettings((struct _AUTOVERIFIER_IPT_SETTINGS *)(this + 120), 0x15u, v28, 0);
  v5 = v13;
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_69;
    }
    v15 = 61;
    goto LABEL_37;
  }
  v16 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(v28, L"Autoverifier", 0, 0, 1u, 0x60002u, 0, v16, &dwDisposition) || !hKey )
  {
    v5 = -2147467259;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_69;
    }
    v7 = 62;
    goto LABEL_68;
  }
  v18 = WerPluginAdjustAppContainerAccessToKey(hKey, v17, 0x80000002);
  if ( v18 < 0
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids,
      (unsigned int)v18);
  }
  for ( i = 0; i < 0x15; ++i )
  {
    v20 = 71LL * (int)i;
    if ( (unsigned int)_o__wcsicmp((char *)&this[v20 + 120] + 4, L"AutoVerifierFlags")
      && (unsigned int)_o__wcsicmp((char *)&this[v20 + 120] + 4, L"AutoVerifierCount")
      && (unsigned int)_o__wcsicmp((char *)&this[v20 + 120] + 4, L"AutoVerifierTimeDuration")
      && (unsigned int)_o__wcsicmp((char *)&this[v20 + 120] + 4, L"AutoVerifierBucketID") )
    {
      v22 = 0;
    }
    else
    {
      if ( HIDWORD(this[v20 + 190]) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v21);
      v22 = 1;
    }
    HIDWORD(this[v20 + 190]) = v22;
  }
  v13 = WerPluginWriteSettings((struct _AUTOVERIFIER_IPT_SETTINGS *)(this + 120), 0x15u, hKey, 0);
  v5 = v13;
  if ( v13 >= 0 )
  {
    CAutoVerifierPlugin::EnableHKCULookupForIFEO(v23, 1);
    *((_DWORD *)this + 238) = 1;
    v5 = 0;
    goto LABEL_69;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    goto LABEL_69;
  }
  v15 = 64;
LABEL_37:
  WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids, (unsigned int)v13);
LABEL_69:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v28 )
    RegCloseKey(v28);
  if ( v25 )
    RegCloseKey(v25);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140049364  mov     [rsp-38h+arg_0], rbx
0x140049369  push    rbp
0x14004936a  push    rsi
0x14004936b  push    rdi
0x14004936c  push    r12
0x14004936e  push    r13
0x140049370  push    r14
0x140049372  push    r15
0x140049374  mov     rbp, rsp
0x140049377  sub     rsp, 60h
0x14004937b  mov     rbx, rdx
0x14004937e  mov     r14, rcx
0x140049381  xor     r15d, r15d
0x140049384  mov     [rbp+var_8], r15
0x140049388  mov     [rbp+arg_18], r15
0x14004938c  mov     ecx, r15d
0x14004938f  mov     [rbp+hKey], rcx
0x140049393  mov     [rbp+dwDisposition], r15d
0x140049397  mov     [rbp+arg_8], r15d
0x14004939b  test    rdx, rdx
0x14004939e  jnz     short loc_140049407
0x1400493a0  lea     rsi, WPP_GLOBAL_Control
0x1400493a7  mov     rax, cs:WPP_GLOBAL_Control
0x1400493ae  cmp     rax, rsi
0x1400493b1  jz      short loc_1400493D2
0x1400493b3  lea     ebx, [rdx+1]
0x1400493b6  test    [rax+1Ch], bl
0x1400493b9  jz      short loc_1400493D2
0x1400493bb  lea     edx, [rbx+34h]
0x1400493be  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x1400493c5  mov     rcx, [rax+10h]
0x1400493c9  call    WPP_SF_
0x1400493ce  mov     rcx, [rbp+hKey]; hKey
0x1400493d2  test    rcx, rcx
0x1400493d5  jz      short loc_1400493DE
0x1400493d7  call    cs:__imp_RegCloseKey
0x1400493dd  nop
0x1400493de  mov     rcx, [rbp+arg_18]; hKey
0x1400493e2  test    rcx, rcx
0x1400493e5  jz      short loc_1400493EE
0x1400493e7  call    cs:__imp_RegCloseKey
0x1400493ed  nop
0x1400493ee  mov     rcx, [rbp+var_8]; hKey
0x1400493f2  test    rcx, rcx
0x1400493f5  jz      short loc_1400493FD
0x1400493f7  call    cs:__imp_RegCloseKey
0x1400493fd  mov     eax, 80070057h
0x140049402  jmp     loc_14004984B
0x140049407  lea     rdx, [rbp+arg_8]; int *
0x14004940b  mov     rcx, r14; this
0x14004940e  call    ?ValidateAutoverifier@CAutoVerifierPlugin@@AEAAJPEAH@Z; CAutoVerifierPlugin::ValidateAutoverifier(int *)
0x140049413  mov     edi, eax
0x140049415  test    eax, eax
0x140049417  jns     short loc_140049446
0x140049419  lea     rsi, WPP_GLOBAL_Control
0x140049420  mov     rcx, cs:WPP_GLOBAL_Control
0x140049427  cmp     rcx, rsi
0x14004942a  jz      loc_14004981A
0x140049430  mov     ebx, 1
0x140049435  test    [rcx+1Ch], bl
0x140049438  jz      loc_14004981A
0x14004943e  lea     edx, [rbx+35h]
0x140049441  jmp     loc_140049809
0x140049446  cmp     [rbp+arg_8], r15d
0x14004944a  jnz     short loc_14004947A
0x14004944c  mov     edi, 1
0x140049451  lea     rsi, WPP_GLOBAL_Control
0x140049458  mov     rcx, cs:WPP_GLOBAL_Control
0x14004945f  cmp     rcx, rsi
0x140049462  jz      loc_14004981A
0x140049468  test    byte ptr [rcx+1Ch], 4
0x14004946c  jz      loc_14004981A
0x140049472  lea     edx, [rdi+36h]
0x140049475  jmp     loc_140049809
0x14004947a  mov     rdx, rbx; void *
0x14004947d  mov     rcx, r14; this
0x140049480  call    ?PromptForEnableAutoVerifier@CAutoVerifierPlugin@@AEAAHPEAX@Z; CAutoVerifierPlugin::PromptForEnableAutoVerifier(void *)
0x140049485  test    eax, eax
0x140049487  jnz     short loc_1400494BF
0x140049489  lea     rsi, WPP_GLOBAL_Control
0x140049490  mov     rcx, cs:WPP_GLOBAL_Control
0x140049497  cmp     rcx, rsi
0x14004949a  jz      short loc_1400494B5
0x14004949c  test    byte ptr [rcx+1Ch], 4
0x1400494a0  jz      short loc_1400494B5
0x1400494a2  lea     edx, [rax+38h]
0x1400494a5  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x1400494ac  mov     rcx, [rcx+10h]
0x1400494b0  call    WPP_SF_
0x1400494b5  mov     edi, 1
0x1400494ba  jmp     loc_14004981A
0x1400494bf  mov     ebx, 1
0x1400494c4  mov     edx, ebx; unsigned int
0x1400494c6  call    ?SetAutoverifierEnabledFlag@CAutoVerifierPlugin@@AEAAJK@Z; CAutoVerifierPlugin::SetAutoverifierEnabledFlag(ulong)
0x1400494cb  mov     edi, eax
0x1400494cd  test    eax, eax
0x1400494cf  jns     short loc_1400494F9
0x1400494d1  lea     rsi, WPP_GLOBAL_Control
0x1400494d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400494df  cmp     rcx, rsi
0x1400494e2  jz      loc_14004981A
0x1400494e8  test    [rcx+1Ch], bl
0x1400494eb  jz      loc_14004981A
0x1400494f1  lea     edx, [rbx+38h]
0x1400494f4  jmp     loc_140049809
0x1400494f9  lea     rcx, [rbp+var_8]
0x1400494fd  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140049502  mov     [rsp+60h+lpdwDisposition], r15; lpdwDisposition
0x140049507  mov     [rsp+60h+phkResult], rax; phkResult
0x14004950c  mov     [rsp+60h+lpSecurityAttributes], r15; lpSecurityAttributes
0x140049511  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x140049519  mov     [rsp+60h+dwOptions], r15d; dwOptions
0x14004951e  xor     r9d, r9d; lpClass
0x140049521  xor     r8d, r8d; Reserved
0x140049524  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\Windows NT\\Curren"...
0x14004952b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140049532  call    cs:__imp_RegCreateKeyExW
0x140049538  test    eax, eax
0x14004953a  jnz     loc_1400497E7
0x140049540  cmp     [rbp+var_8], r15
0x140049544  jz      loc_1400497E7
0x14004954a  lea     rcx, [rbp+arg_18]
0x14004954e  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140049553  lea     rcx, [rbp+dwDisposition]
0x140049557  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x14004955c  mov     [rsp+60h+phkResult], rax; phkResult
0x140049561  mov     [rsp+60h+lpSecurityAttributes], r15; lpSecurityAttributes
0x140049566  mov     r12d, 60002h
0x14004956c  mov     [rsp+60h+samDesired], r12d; samDesired
0x140049571  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x140049575  xor     r9d, r9d; lpClass
0x140049578  xor     r8d, r8d; Reserved
0x14004957b  mov     rdx, [r14+2E8h]; lpSubKey
0x140049582  mov     rcx, [rbp+var_8]; hKey
0x140049586  call    cs:__imp_RegCreateKeyExW
0x14004958c  test    eax, eax
0x14004958e  jnz     loc_1400497C3
0x140049594  mov     rcx, [rbp+arg_18]; hKey
0x140049598  test    rcx, rcx
0x14004959b  jz      loc_1400497C3
0x1400495a1  mov     r8d, 80010000h; unsigned int
0x1400495a7  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x1400495ac  lea     rsi, WPP_GLOBAL_Control
0x1400495b3  test    eax, eax
0x1400495b5  jns     short loc_1400495E1
0x1400495b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400495be  cmp     rcx, rsi
0x1400495c1  jz      short loc_1400495E1
0x1400495c3  test    byte ptr [rcx+1Ch], 2
0x1400495c7  jz      short loc_1400495E1
0x1400495c9  mov     edx, 3Ch ; '<'
0x1400495ce  mov     r9d, eax
0x1400495d1  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x1400495d8  mov     rcx, [rcx+10h]
0x1400495dc  call    WPP_SF_d
0x1400495e1  lea     r13, [r14+3C0h]
0x1400495e8  xor     r9d, r9d; wchar_t *
0x1400495eb  mov     r8, [rbp+arg_18]; HKEY
0x1400495ef  lea     edx, [r9+15h]; unsigned int
0x1400495f3  mov     rcx, r13; struct _AUTOVERIFIER_IPT_SETTINGS *
0x1400495f6  call    ?WerPluginWriteSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUHKEY__@@PEB_W@Z; WerPluginWriteSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,HKEY__ *,wchar_t const *)
0x1400495fb  mov     edi, eax
0x1400495fd  test    eax, eax
0x1400495ff  jns     short loc_140049637
0x140049601  mov     rcx, cs:WPP_GLOBAL_Control
0x140049608  cmp     rcx, rsi
0x14004960b  jz      loc_14004981A
0x140049611  test    [rcx+1Ch], bl
0x140049614  jz      loc_14004981A
0x14004961a  mov     edx, 3Dh ; '='
0x14004961f  mov     r9d, eax
0x140049622  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x140049629  mov     rcx, [rcx+10h]
0x14004962d  call    WPP_SF_d
0x140049632  jmp     loc_14004981A
0x140049637  lea     rcx, [rbp+hKey]
0x14004963b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140049640  lea     rcx, [rbp+dwDisposition]
0x140049644  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x140049649  mov     [rsp+60h+phkResult], rax; phkResult
0x14004964e  mov     [rsp+60h+lpSecurityAttributes], r15; lpSecurityAttributes
0x140049653  mov     [rsp+60h+samDesired], r12d; samDesired
0x140049658  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x14004965c  xor     r9d, r9d; lpClass
0x14004965f  xor     r8d, r8d; Reserved
0x140049662  lea     rdx, aAutoverifier; "Autoverifier"
0x140049669  mov     rcx, [rbp+arg_18]; hKey
0x14004966d  call    cs:__imp_RegCreateKeyExW
0x140049673  test    eax, eax
0x140049675  jnz     loc_1400497A6
0x14004967b  mov     rcx, [rbp+hKey]; hKey
0x14004967f  test    rcx, rcx
0x140049682  jz      loc_1400497A6
0x140049688  mov     r8d, 80000002h; unsigned int
0x14004968e  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x140049693  test    eax, eax
0x140049695  jns     short loc_1400496C1
0x140049697  mov     rcx, cs:WPP_GLOBAL_Control
0x14004969e  cmp     rcx, rsi
0x1400496a1  jz      short loc_1400496C1
0x1400496a3  test    byte ptr [rcx+1Ch], 2
0x1400496a7  jz      short loc_1400496C1
0x1400496a9  mov     edx, 3Fh ; '?'
0x1400496ae  mov     r9d, eax
0x1400496b1  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x1400496b8  mov     rcx, [rcx+10h]
0x1400496bc  call    WPP_SF_d
0x1400496c1  mov     edi, r15d
0x1400496c4  movsxd  rax, edi
0x1400496c7  imul    r12, rax, 238h
0x1400496ce  lea     r15, [r14+3C4h]
0x1400496d5  add     r15, r12
0x1400496d8  lea     rdx, aAutoverifierfl; "AutoVerifierFlags"
0x1400496df  mov     rcx, r15
0x1400496e2  call    cs:__imp__o__wcsicmp
0x1400496e8  test    eax, eax
0x1400496ea  jz      short loc_140049730
0x1400496ec  lea     rdx, aAutoverifierco; "AutoVerifierCount"
0x1400496f3  mov     rcx, r15
0x1400496f6  call    cs:__imp__o__wcsicmp
0x1400496fc  test    eax, eax
0x1400496fe  jz      short loc_140049730
0x140049700  lea     rdx, aAutoverifierti; "AutoVerifierTimeDuration"
0x140049707  mov     rcx, r15
0x14004970a  call    cs:__imp__o__wcsicmp
0x140049710  test    eax, eax
0x140049712  jz      short loc_140049730
0x140049714  lea     rdx, aAutoverifierbu; "AutoVerifierBucketID"
0x14004971b  mov     rcx, r15
0x14004971e  call    cs:__imp__o__wcsicmp
0x140049724  xor     r15d, r15d
0x140049727  test    eax, eax
0x140049729  jz      short loc_140049733
0x14004972b  mov     eax, r15d
0x14004972e  jmp     short loc_140049744
0x140049730  xor     r15d, r15d
0x140049733  cmp     [r12+r14+5F4h], r15d
0x14004973b  jz      short loc_140049742
0x14004973d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140049742  mov     eax, ebx
0x140049744  mov     [r12+r14+5F4h], eax
0x14004974c  add     edi, ebx
0x14004974e  cmp     edi, 15h
0x140049751  jb      loc_1400496C4
0x140049757  xor     r9d, r9d; wchar_t *
0x14004975a  mov     r8, [rbp+hKey]; HKEY
0x14004975e  lea     edx, [r9+15h]; unsigned int
0x140049762  mov     rcx, r13; struct _AUTOVERIFIER_IPT_SETTINGS *
0x140049765  call    ?WerPluginWriteSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUHKEY__@@PEB_W@Z; WerPluginWriteSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,HKEY__ *,wchar_t const *)
0x14004976a  mov     edi, eax
0x14004976c  test    eax, eax
0x14004976e  jns     short loc_140049793
0x140049770  mov     rcx, cs:WPP_GLOBAL_Control
0x140049777  cmp     rcx, rsi
0x14004977a  jz      loc_14004981A
0x140049780  test    [rcx+1Ch], bl
0x140049783  jz      loc_14004981A
0x140049789  mov     edx, 40h ; '@'
0x14004978e  jmp     loc_14004961F
0x140049793  mov     edx, ebx; int
0x140049795  call    ?EnableHKCULookupForIFEO@CAutoVerifierPlugin@@AEAAJH@Z; CAutoVerifierPlugin::EnableHKCULookupForIFEO(int)
0x14004979a  mov     [r14+3B8h], ebx
0x1400497a1  mov     edi, r15d
0x1400497a4  jmp     short loc_14004981A
0x1400497a6  mov     edi, 80004005h
0x1400497ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400497b2  cmp     rcx, rsi
0x1400497b5  jz      short loc_14004981A
0x1400497b7  test    [rcx+1Ch], bl
0x1400497ba  jz      short loc_14004981A
0x1400497bc  mov     edx, 3Eh ; '>'
0x1400497c1  jmp     short loc_140049809
0x1400497c3  mov     edi, 80004005h
0x1400497c8  lea     rsi, WPP_GLOBAL_Control
0x1400497cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400497d6  cmp     rcx, rsi
0x1400497d9  jz      short loc_14004981A
0x1400497db  test    [rcx+1Ch], bl
0x1400497de  jz      short loc_14004981A
0x1400497e0  mov     edx, 3Bh ; ';'
0x1400497e5  jmp     short loc_140049809
0x1400497e7  mov     edi, 80004005h
0x1400497ec  lea     rsi, WPP_GLOBAL_Control
0x1400497f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400497fa  cmp     rcx, rsi
0x1400497fd  jz      short loc_14004981A
0x1400497ff  test    [rcx+1Ch], bl
0x140049802  jz      short loc_14004981A
0x140049804  mov     edx, 3Ah ; ':'
0x140049809  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x140049810  mov     rcx, [rcx+10h]
0x140049814  call    WPP_SF_
0x140049819  nop
0x14004981a  mov     rcx, [rbp+hKey]; hKey
0x14004981e  test    rcx, rcx
0x140049821  jz      short loc_14004982A
0x140049823  call    cs:__imp_RegCloseKey
0x140049829  nop
0x14004982a  mov     rcx, [rbp+arg_18]; hKey
0x14004982e  test    rcx, rcx
  ... truncated ...
```
