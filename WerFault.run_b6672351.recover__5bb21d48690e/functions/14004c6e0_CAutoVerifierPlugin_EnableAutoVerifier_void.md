# CAutoVerifierPlugin::EnableAutoVerifier(void *)

- ea: `0x14004c6e0`
- end: `0x14004cc2e`
- name: `?EnableAutoVerifier@CAutoVerifierPlugin@@AEAAJPEAX@Z`
- size: `1358`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004d690`

## callees

- `0x14000551c`
- `0x140014ee4`
- `0x140014f14`
- `0x1400166ec`
- `0x14004c6e0`
- `0x14004cc34`
- `0x14004dba8`
- `0x14004e104`
- `0x14004e88c`
- `0x1400584c0`
- `0x140058c04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004ca82`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004ca9c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004cab6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004cad0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004ca82`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004ca9c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004cab6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004cad0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004c753`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004c769`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004c77f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004cbdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004cbf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004cc07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004c753`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004c769`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004c77f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004cbdb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004cbf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004cc07`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004c8c0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004c91a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004ca07`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004c8c0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004c91a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14004ca07`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  __int64 v19; // r8
  unsigned int i; // edi
  __int64 v21; // r12
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r9
  int v25; // eax
  CAutoVerifierPlugin *v26; // rcx
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY v28; // [rsp+58h] [rbp-8h] BYREF
  int v29; // [rsp+A8h] [rbp+48h] BYREF
  DWORD dwDisposition; // [rsp+B0h] [rbp+50h] BYREF
  HKEY v31; // [rsp+B8h] [rbp+58h] BYREF

  v28 = 0;
  v31 = 0;
  hKey = 0;
  dwDisposition = 0;
  v29 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    }
    if ( v31 )
      RegCloseKey(v31);
    return 2147942487LL;
  }
  v5 = CAutoVerifierPlugin::ValidateAutoverifier((CAutoVerifierPlugin *)this, &v29);
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
  if ( !v29 )
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
  v5 = CAutoVerifierPlugin::SetAutoverifierEnabledFlag(v8, 1);
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
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v28);
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
    || !v28 )
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
  v10 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v31);
  if ( RegCreateKeyExW(v28, this[93], 0, 0, 1u, 0x60002u, 0, v10, &dwDisposition) || !v31 )
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
  v12 = WerPluginAdjustAppContainerAccessToKey(v31, v11, 0x80010000);
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
  v13 = WerPluginWriteSettings((struct _AUTOVERIFIER_IPT_SETTINGS *)(this + 120), 0x15u, v31, 0);
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
  if ( RegCreateKeyExW(v31, L"Autoverifier", 0, 0, 1u, 0x60002u, 0, v16, &dwDisposition) || !hKey )
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
    v21 = 71LL * (int)i;
    if ( (unsigned int)_o__wcsicmp((char *)&this[v21 + 120] + 4, L"AutoVerifierFlags", v19)
      && (unsigned int)_o__wcsicmp((char *)&this[v21 + 120] + 4, L"AutoVerifierCount", v19)
      && (unsigned int)_o__wcsicmp((char *)&this[v21 + 120] + 4, L"AutoVerifierTimeDuration", v19)
      && (unsigned int)_o__wcsicmp((char *)&this[v21 + 120] + 4, L"AutoVerifierBucketID", v19) )
    {
      v25 = 0;
    }
    else
    {
      if ( HIDWORD(this[v21 + 190]) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v23, v22, v19, v24);
      v25 = 1;
    }
    HIDWORD(this[v21 + 190]) = v25;
  }
  v13 = WerPluginWriteSettings((struct _AUTOVERIFIER_IPT_SETTINGS *)(this + 120), 0x15u, hKey, 0);
  v5 = v13;
  if ( v13 >= 0 )
  {
    CAutoVerifierPlugin::EnableHKCULookupForIFEO(v26, 1);
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
  if ( v31 )
    RegCloseKey(v31);
  if ( v28 )
    RegCloseKey(v28);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14004c6e0  mov     [rsp-38h+arg_0], rbx
0x14004c6e5  push    rbp
0x14004c6e6  push    rsi
0x14004c6e7  push    rdi
0x14004c6e8  push    r12
0x14004c6ea  push    r13
0x14004c6ec  push    r14
0x14004c6ee  push    r15
0x14004c6f0  mov     rbp, rsp
0x14004c6f3  sub     rsp, 60h
0x14004c6f7  mov     rbx, rdx
0x14004c6fa  mov     r14, rcx
0x14004c6fd  xor     r15d, r15d
0x14004c700  mov     [rbp+var_8], r15
0x14004c704  mov     [rbp+arg_18], r15
0x14004c708  mov     ecx, r15d
0x14004c70b  mov     [rbp+hKey], rcx
0x14004c70f  mov     [rbp+dwDisposition], r15d
0x14004c713  mov     [rbp+arg_8], r15d
0x14004c717  test    rdx, rdx
0x14004c71a  jnz     short loc_14004C795
0x14004c71c  lea     rsi, WPP_GLOBAL_Control
0x14004c723  mov     rax, cs:WPP_GLOBAL_Control
0x14004c72a  cmp     rax, rsi
0x14004c72d  jz      short loc_14004C74E
0x14004c72f  lea     ebx, [rdx+1]
0x14004c732  test    [rax+1Ch], bl
0x14004c735  jz      short loc_14004C74E
0x14004c737  lea     edx, [rbx+34h]
0x14004c73a  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004c741  mov     rcx, [rax+10h]
0x14004c745  call    WPP_SF_
0x14004c74a  mov     rcx, [rbp+hKey]; hKey
0x14004c74e  test    rcx, rcx
0x14004c751  jz      short loc_14004C760
0x14004c753  call    cs:__imp_RegCloseKey
0x14004c75a  nop     dword ptr [rax+rax+00h]
0x14004c75f  nop
0x14004c760  mov     rcx, [rbp+arg_18]; hKey
0x14004c764  test    rcx, rcx
0x14004c767  jz      short loc_14004C776
0x14004c769  call    cs:__imp_RegCloseKey
0x14004c770  nop     dword ptr [rax+rax+00h]
0x14004c775  nop
0x14004c776  mov     rcx, [rbp+var_8]; hKey
0x14004c77a  test    rcx, rcx
0x14004c77d  jz      short loc_14004C78B
0x14004c77f  call    cs:__imp_RegCloseKey
0x14004c786  nop     dword ptr [rax+rax+00h]
0x14004c78b  mov     eax, 80070057h
0x14004c790  jmp     loc_14004CC15
0x14004c795  lea     rdx, [rbp+arg_8]; int *
0x14004c799  mov     rcx, r14; this
0x14004c79c  call    ?ValidateAutoverifier@CAutoVerifierPlugin@@AEAAJPEAH@Z; CAutoVerifierPlugin::ValidateAutoverifier(int *)
0x14004c7a1  mov     edi, eax
0x14004c7a3  test    eax, eax
0x14004c7a5  jns     short loc_14004C7D4
0x14004c7a7  lea     rsi, WPP_GLOBAL_Control
0x14004c7ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c7b5  cmp     rcx, rsi
0x14004c7b8  jz      loc_14004CBD2
0x14004c7be  mov     ebx, 1
0x14004c7c3  test    [rcx+1Ch], bl
0x14004c7c6  jz      loc_14004CBD2
0x14004c7cc  lea     edx, [rbx+35h]
0x14004c7cf  jmp     loc_14004CBC1
0x14004c7d4  cmp     [rbp+arg_8], r15d
0x14004c7d8  jnz     short loc_14004C808
0x14004c7da  mov     edi, 1
0x14004c7df  lea     rsi, WPP_GLOBAL_Control
0x14004c7e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c7ed  cmp     rcx, rsi
0x14004c7f0  jz      loc_14004CBD2
0x14004c7f6  test    byte ptr [rcx+1Ch], 4
0x14004c7fa  jz      loc_14004CBD2
0x14004c800  lea     edx, [rdi+36h]
0x14004c803  jmp     loc_14004CBC1
0x14004c808  mov     rdx, rbx; void *
0x14004c80b  mov     rcx, r14; this
0x14004c80e  call    ?PromptForEnableAutoVerifier@CAutoVerifierPlugin@@AEAAHPEAX@Z; CAutoVerifierPlugin::PromptForEnableAutoVerifier(void *)
0x14004c813  test    eax, eax
0x14004c815  jnz     short loc_14004C84D
0x14004c817  lea     rsi, WPP_GLOBAL_Control
0x14004c81e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c825  cmp     rcx, rsi
0x14004c828  jz      short loc_14004C843
0x14004c82a  test    byte ptr [rcx+1Ch], 4
0x14004c82e  jz      short loc_14004C843
0x14004c830  lea     edx, [rax+38h]
0x14004c833  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004c83a  mov     rcx, [rcx+10h]
0x14004c83e  call    WPP_SF_
0x14004c843  mov     edi, 1
0x14004c848  jmp     loc_14004CBD2
0x14004c84d  mov     ebx, 1
0x14004c852  mov     edx, ebx; unsigned int
0x14004c854  call    ?SetAutoverifierEnabledFlag@CAutoVerifierPlugin@@AEAAJK@Z; CAutoVerifierPlugin::SetAutoverifierEnabledFlag(ulong)
0x14004c859  mov     edi, eax
0x14004c85b  test    eax, eax
0x14004c85d  jns     short loc_14004C887
0x14004c85f  lea     rsi, WPP_GLOBAL_Control
0x14004c866  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c86d  cmp     rcx, rsi
0x14004c870  jz      loc_14004CBD2
0x14004c876  test    [rcx+1Ch], bl
0x14004c879  jz      loc_14004CBD2
0x14004c87f  lea     edx, [rbx+38h]
0x14004c882  jmp     loc_14004CBC1
0x14004c887  lea     rcx, [rbp+var_8]
0x14004c88b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004c890  mov     [rsp+60h+lpdwDisposition], r15; lpdwDisposition
0x14004c895  mov     [rsp+60h+phkResult], rax; phkResult
0x14004c89a  mov     [rsp+60h+lpSecurityAttributes], r15; lpSecurityAttributes
0x14004c89f  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x14004c8a7  mov     [rsp+60h+dwOptions], r15d; dwOptions
0x14004c8ac  xor     r9d, r9d; lpClass
0x14004c8af  xor     r8d, r8d; Reserved
0x14004c8b2  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\Windows NT\\Curren"...
0x14004c8b9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14004c8c0  call    cs:__imp_RegCreateKeyExW
0x14004c8c7  nop     dword ptr [rax+rax+00h]
0x14004c8cc  test    eax, eax
0x14004c8ce  jnz     loc_14004CB9F
0x14004c8d4  cmp     [rbp+var_8], r15
0x14004c8d8  jz      loc_14004CB9F
0x14004c8de  lea     rcx, [rbp+arg_18]
0x14004c8e2  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004c8e7  lea     rcx, [rbp+dwDisposition]
0x14004c8eb  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x14004c8f0  mov     [rsp+60h+phkResult], rax; phkResult
0x14004c8f5  mov     [rsp+60h+lpSecurityAttributes], r15; lpSecurityAttributes
0x14004c8fa  mov     r12d, 60002h
0x14004c900  mov     [rsp+60h+samDesired], r12d; samDesired
0x14004c905  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x14004c909  xor     r9d, r9d; lpClass
0x14004c90c  xor     r8d, r8d; Reserved
0x14004c90f  mov     rdx, [r14+2E8h]; lpSubKey
0x14004c916  mov     rcx, [rbp+var_8]; hKey
0x14004c91a  call    cs:__imp_RegCreateKeyExW
0x14004c921  nop     dword ptr [rax+rax+00h]
0x14004c926  test    eax, eax
0x14004c928  jnz     loc_14004CB7B
0x14004c92e  mov     rcx, [rbp+arg_18]; hKey
0x14004c932  test    rcx, rcx
0x14004c935  jz      loc_14004CB7B
0x14004c93b  mov     r8d, 80010000h; unsigned int
0x14004c941  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x14004c946  lea     rsi, WPP_GLOBAL_Control
0x14004c94d  test    eax, eax
0x14004c94f  jns     short loc_14004C97B
0x14004c951  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c958  cmp     rcx, rsi
0x14004c95b  jz      short loc_14004C97B
0x14004c95d  test    byte ptr [rcx+1Ch], 2
0x14004c961  jz      short loc_14004C97B
0x14004c963  mov     edx, 3Ch ; '<'
0x14004c968  mov     r9d, eax
0x14004c96b  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004c972  mov     rcx, [rcx+10h]
0x14004c976  call    WPP_SF_d
0x14004c97b  lea     r13, [r14+3C0h]
0x14004c982  xor     r9d, r9d; wchar_t *
0x14004c985  mov     r8, [rbp+arg_18]; HKEY
0x14004c989  lea     edx, [r9+15h]; unsigned int
0x14004c98d  mov     rcx, r13; struct _AUTOVERIFIER_IPT_SETTINGS *
0x14004c990  call    ?WerPluginWriteSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUHKEY__@@PEB_W@Z; WerPluginWriteSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,HKEY__ *,wchar_t const *)
0x14004c995  mov     edi, eax
0x14004c997  test    eax, eax
0x14004c999  jns     short loc_14004C9D1
0x14004c99b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c9a2  cmp     rcx, rsi
0x14004c9a5  jz      loc_14004CBD2
0x14004c9ab  test    [rcx+1Ch], bl
0x14004c9ae  jz      loc_14004CBD2
0x14004c9b4  mov     edx, 3Dh ; '='
0x14004c9b9  mov     r9d, eax
0x14004c9bc  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004c9c3  mov     rcx, [rcx+10h]
0x14004c9c7  call    WPP_SF_d
0x14004c9cc  jmp     loc_14004CBD2
0x14004c9d1  lea     rcx, [rbp+hKey]
0x14004c9d5  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14004c9da  lea     rcx, [rbp+dwDisposition]
0x14004c9de  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x14004c9e3  mov     [rsp+60h+phkResult], rax; phkResult
0x14004c9e8  mov     [rsp+60h+lpSecurityAttributes], r15; lpSecurityAttributes
0x14004c9ed  mov     [rsp+60h+samDesired], r12d; samDesired
0x14004c9f2  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x14004c9f6  xor     r9d, r9d; lpClass
0x14004c9f9  xor     r8d, r8d; Reserved
0x14004c9fc  lea     rdx, aAutoverifier; "Autoverifier"
0x14004ca03  mov     rcx, [rbp+arg_18]; hKey
0x14004ca07  call    cs:__imp_RegCreateKeyExW
0x14004ca0e  nop     dword ptr [rax+rax+00h]
0x14004ca13  test    eax, eax
0x14004ca15  jnz     loc_14004CB5E
0x14004ca1b  mov     rcx, [rbp+hKey]; hKey
0x14004ca1f  test    rcx, rcx
0x14004ca22  jz      loc_14004CB5E
0x14004ca28  mov     r8d, 80000002h; unsigned int
0x14004ca2e  call    ?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z; WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)
0x14004ca33  test    eax, eax
0x14004ca35  jns     short loc_14004CA61
0x14004ca37  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ca3e  cmp     rcx, rsi
0x14004ca41  jz      short loc_14004CA61
0x14004ca43  test    byte ptr [rcx+1Ch], 2
0x14004ca47  jz      short loc_14004CA61
0x14004ca49  mov     edx, 3Fh ; '?'
0x14004ca4e  mov     r9d, eax
0x14004ca51  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004ca58  mov     rcx, [rcx+10h]
0x14004ca5c  call    WPP_SF_d
0x14004ca61  mov     edi, r15d
0x14004ca64  movsxd  rax, edi
0x14004ca67  imul    r12, rax, 238h
0x14004ca6e  lea     r15, [r14+3C4h]
0x14004ca75  add     r15, r12
0x14004ca78  lea     rdx, aAutoverifierfl; "AutoVerifierFlags"
0x14004ca7f  mov     rcx, r15
0x14004ca82  call    cs:__imp__o__wcsicmp
0x14004ca89  nop     dword ptr [rax+rax+00h]
0x14004ca8e  test    eax, eax
0x14004ca90  jz      short loc_14004CAE8
0x14004ca92  lea     rdx, aAutoverifierco; "AutoVerifierCount"
0x14004ca99  mov     rcx, r15
0x14004ca9c  call    cs:__imp__o__wcsicmp
0x14004caa3  nop     dword ptr [rax+rax+00h]
0x14004caa8  test    eax, eax
0x14004caaa  jz      short loc_14004CAE8
0x14004caac  lea     rdx, aAutoverifierti; "AutoVerifierTimeDuration"
0x14004cab3  mov     rcx, r15
0x14004cab6  call    cs:__imp__o__wcsicmp
0x14004cabd  nop     dword ptr [rax+rax+00h]
0x14004cac2  test    eax, eax
0x14004cac4  jz      short loc_14004CAE8
0x14004cac6  lea     rdx, aAutoverifierbu; "AutoVerifierBucketID"
0x14004cacd  mov     rcx, r15
0x14004cad0  call    cs:__imp__o__wcsicmp
0x14004cad7  nop     dword ptr [rax+rax+00h]
0x14004cadc  xor     r15d, r15d
0x14004cadf  test    eax, eax
0x14004cae1  jz      short loc_14004CAEB
0x14004cae3  mov     eax, r15d
0x14004cae6  jmp     short loc_14004CAFC
0x14004cae8  xor     r15d, r15d
0x14004caeb  cmp     [r12+r14+5F4h], r15d
0x14004caf3  jz      short loc_14004CAFA
0x14004caf5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14004cafa  mov     eax, ebx
0x14004cafc  mov     [r12+r14+5F4h], eax
0x14004cb04  add     edi, ebx
0x14004cb06  cmp     edi, 15h
0x14004cb09  jb      loc_14004CA64
0x14004cb0f  xor     r9d, r9d; wchar_t *
0x14004cb12  mov     r8, [rbp+hKey]; HKEY
0x14004cb16  lea     edx, [r9+15h]; unsigned int
0x14004cb1a  mov     rcx, r13; struct _AUTOVERIFIER_IPT_SETTINGS *
0x14004cb1d  call    ?WerPluginWriteSettings@@YAJPEAU_AUTOVERIFIER_IPT_SETTINGS@@KPEAUHKEY__@@PEB_W@Z; WerPluginWriteSettings(_AUTOVERIFIER_IPT_SETTINGS *,ulong,HKEY__ *,wchar_t const *)
0x14004cb22  mov     edi, eax
0x14004cb24  test    eax, eax
0x14004cb26  jns     short loc_14004CB4B
0x14004cb28  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cb2f  cmp     rcx, rsi
0x14004cb32  jz      loc_14004CBD2
0x14004cb38  test    [rcx+1Ch], bl
0x14004cb3b  jz      loc_14004CBD2
0x14004cb41  mov     edx, 40h ; '@'
0x14004cb46  jmp     loc_14004C9B9
0x14004cb4b  mov     edx, ebx; int
0x14004cb4d  call    ?EnableHKCULookupForIFEO@CAutoVerifierPlugin@@AEAAJH@Z; CAutoVerifierPlugin::EnableHKCULookupForIFEO(int)
0x14004cb52  mov     [r14+3B8h], ebx
0x14004cb59  mov     edi, r15d
0x14004cb5c  jmp     short loc_14004CBD2
0x14004cb5e  mov     edi, 80004005h
0x14004cb63  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cb6a  cmp     rcx, rsi
0x14004cb6d  jz      short loc_14004CBD2
0x14004cb6f  test    [rcx+1Ch], bl
0x14004cb72  jz      short loc_14004CBD2
0x14004cb74  mov     edx, 3Eh ; '>'
0x14004cb79  jmp     short loc_14004CBC1
0x14004cb7b  mov     edi, 80004005h
0x14004cb80  lea     rsi, WPP_GLOBAL_Control
0x14004cb87  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cb8e  cmp     rcx, rsi
0x14004cb91  jz      short loc_14004CBD2
0x14004cb93  test    [rcx+1Ch], bl
0x14004cb96  jz      short loc_14004CBD2
0x14004cb98  mov     edx, 3Bh ; ';'
0x14004cb9d  jmp     short loc_14004CBC1
0x14004cb9f  mov     edi, 80004005h
0x14004cba4  lea     rsi, WPP_GLOBAL_Control
0x14004cbab  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cbb2  cmp     rcx, rsi
0x14004cbb5  jz      short loc_14004CBD2
0x14004cbb7  test    [rcx+1Ch], bl
0x14004cbba  jz      short loc_14004CBD2
0x14004cbbc  mov     edx, 3Ah ; ':'
0x14004cbc1  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
  ... truncated ...
```
