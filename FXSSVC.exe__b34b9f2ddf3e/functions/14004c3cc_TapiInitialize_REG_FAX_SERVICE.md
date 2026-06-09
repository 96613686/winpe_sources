# TapiInitialize(_REG_FAX_SERVICE *)

- ea: `0x14004c3cc`
- end: `0x14004cadd`
- name: `?TapiInitialize@@YAKPEAU_REG_FAX_SERVICE@@@Z`
- size: `1809`
- prototype: `__int64 __fastcall(struct _REG_FAX_SERVICE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400472a0`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004e68`
- `0x1400492fc`
- `0x14004c3cc`
- `0x14004e1cc`
- `0x14004e94c`
- `0x140065dbc`
- `0x140076554`
- `0x14007cba0`
- `0x14007d9e4`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14004c5d3`
- `KERNEL32!GetModuleFileNameW` at `0x14004c5d3`
- `KERNEL32!GetLastError` at `0x14004c494`
- `KERNEL32!GetLastError` at `0x14004c5f8`
- `KERNEL32!GetLastError` at `0x14004c85c`
- `KERNEL32!GetLastError` at `0x14004c927`
- `KERNEL32!GetLastError` at `0x14004c9bf`
- `KERNEL32!GetLastError` at `0x14004ca10`
- `KERNEL32!GetLastError` at `0x14004ca65`
- `KERNEL32!GetLastError` at `0x14004c494`
- `KERNEL32!GetLastError` at `0x14004c5f8`
- `KERNEL32!GetLastError` at `0x14004c85c`
- `KERNEL32!GetLastError` at `0x14004c927`
- `KERNEL32!GetLastError` at `0x14004c9bf`
- `KERNEL32!GetLastError` at `0x14004ca10`
- `KERNEL32!GetLastError` at `0x14004ca65`
- `KERNEL32!SetLastError` at `0x14004c5f2`
- `KERNEL32!SetLastError` at `0x14004c5f2`
- `KERNEL32!CloseHandle` at `0x14004c99d`
- `KERNEL32!CloseHandle` at `0x14004c99d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14004c45d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14004c45d`
- `KERNEL32!EnterCriticalSection` at `0x14004c46d`
- `KERNEL32!EnterCriticalSection` at `0x14004c46d`
- `KERNEL32!LeaveCriticalSection` at `0x14004c940`
- `KERNEL32!LeaveCriticalSection` at `0x14004ca79`
- `KERNEL32!LeaveCriticalSection` at `0x14004c940`
- `KERNEL32!LeaveCriticalSection` at `0x14004ca79`
- `KERNEL32!GetModuleHandleW` at `0x14004c4fd`
- `KERNEL32!GetModuleHandleW` at `0x14004c4fd`
- `KERNEL32!CreateIoCompletionPort` at `0x14004c482`
- `KERNEL32!CreateIoCompletionPort` at `0x14004c482`
- `msvcrt!_wsplitpath_s` at `0x14004c680`
- `msvcrt!_wsplitpath_s` at `0x14004c680`
- `TAPI32!lineShutdown` at `0x14004c950`
- `TAPI32!lineShutdown` at `0x14004c950`
- `TAPI32!lineNegotiateAPIVersion` at `0x14004c807`
- `TAPI32!lineNegotiateAPIVersion` at `0x14004c807`
- `TAPI32!lineInitializeExW` at `0x14004c535`
- `TAPI32!lineInitializeExW` at `0x14004c535`
- `TAPI32!lineSetAppPriorityW` at `0x14004c746`
- `TAPI32!lineSetAppPriorityW` at `0x14004c762`
- `TAPI32!lineSetAppPriorityW` at `0x14004c746`
- `TAPI32!lineSetAppPriorityW` at `0x14004c762`

## string_xrefs

- `0x14004c503`: `Microsoft Fax Server Service`

## pseudocode

```c
__int64 __fastcall TapiInitialize(struct _REG_FAX_SERVICE *a1)
{
  __int64 FaxDevicesRegistry; // r14
  HANDLE IoCompletionPort; // rax
  DWORD LastError; // eax
  DWORD v4; // esi
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  HMODULE ModuleHandleW; // rax
  LONG v9; // eax
  DWORD ModuleFileNameW; // eax
  DWORD v11; // eax
  CMapDeviceId *v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  DWORD v15; // ebx
  __int64 v16; // rcx
  struct linedevcaps_tag *DevCaps; // rax
  struct linedevcaps_tag *v18; // rdi
  DWORD v19; // eax
  unsigned int i; // ebx
  __int64 v21; // rdx
  __int64 v22; // rax
  unsigned int v23; // eax
  DWORD v24; // eax
  DWORD v25; // eax
  __int64 v26; // rdx
  unsigned int j; // edi
  DWORD dwAPIVersion; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwNumDevs; // [rsp+54h] [rbp-ACh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  struct lineinitializeexparams_tag LineInitializeExParams; // [rsp+60h] [rbp-A0h] BYREF
  lineextensionid_tag ExtensionID; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[520]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Ext[256]; // [rsp+4A0h] [rbp+3A0h] BYREF
  wchar_t v36[256]; // [rsp+6A0h] [rbp+5A0h] BYREF

  memset(&LineInitializeExParams, 0, sizeof(LineInitializeExParams));
  FaxDevicesRegistry = 0;
  dwAPIVersion = 0;
  SystemTimeAsFileTime = 0;
  ExtensionID = 0;
  dwNumDevs = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  EnterCriticalSection(&g_CsLine);
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u);
  g_TapiCompletionPort = IoCompletionPort;
  if ( !IoCompletionPort )
  {
    LastError = GetLastError();
    v4 = LastError;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v6 = 124;
    v7 = LastError;
    goto LABEL_10;
  }
  *(_QWORD *)&LineInitializeExParams.dwTotalSize = 28;
  LineInitializeExParams.dwUsedSize = 0;
  LineInitializeExParams.dwOptions = 3;
  LineInitializeExParams.Handles.hEvent = IoCompletionPort;
  LineInitializeExParams.dwCompletionKey = -2147483647;
  dwAPIVersion = 0x20000;
  ModuleHandleW = GetModuleHandleW(0);
  v9 = lineInitializeExW(
         &g_hLineApp,
         ModuleHandleW,
         0,
         L"Microsoft Fax Server Service",
         &dwNumDevs,
         &dwAPIVersion,
         &LineInitializeExParams);
  v4 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        125,
        &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
        dwNumDevs,
        v9);
    }
    goto LABEL_74;
  }
  v7 = dwAPIVersion;
  if ( dwAPIVersion < 0x20000 )
  {
    v4 = -2147483636;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v6 = 126;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v7);
    goto LABEL_74;
  }
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x208u);
  if ( !ModuleFileNameW )
  {
    Filename[0] = 0;
    goto LABEL_26;
  }
  if ( ModuleFileNameW == 520 )
  {
    Filename[0] = 0;
    SetLastError(0x7Au);
LABEL_26:
    v11 = GetLastError();
    v4 = v11;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v13 = 127;
    goto LABEL_30;
  }
  Filename[519] = 0;
  v4 = 0;
  if ( _wsplitpath_s(Filename, 0, 0, 0, 0, v36, 0x100u, Ext, 0x100u) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
    }
    goto LABEL_74;
  }
  v14 = StringCchPrintfW(Filename, 0x208u, L"%s%s", v36, Ext);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        129,
        &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
        (unsigned int)v14);
    }
    goto LABEL_74;
  }
  lineSetAppPriorityW(Filename, 2u, 0, 0, 0, 1u);
  v11 = lineSetAppPriorityW(Filename, 0x10u, 0, 0, 0, 1u);
  if ( v11 )
  {
    v4 = v11;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v13 = 130;
LABEL_30:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v11);
    goto LABEL_74;
  }
  FaxDevicesRegistry = GetFaxDevicesRegistry();
  if ( !FaxDevicesRegistry
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
  }
  v15 = 0;
  if ( dwNumDevs )
  {
    while ( !lineNegotiateAPIVersion(g_hLineApp, v15, 0x10003u, 0x20000u, &dwAPIVersion, &ExtensionID) )
    {
      DevCaps = (struct linedevcaps_tag *)SmartLineGetDevCaps(v16, v15, dwAPIVersion);
      v18 = DevCaps;
      if ( DevCaps )
      {
        if ( !(unsigned int)AddNewDevice(v15, DevCaps, 1, (struct _REG_FAX_DEVICES *)FaxDevicesRegistry)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v19 = GetLastError();
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            132,
            &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
            v15,
            v19);
        }
        pMemFree(v18);
        goto LABEL_60;
      }
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = GetLastError();
        v26 = 133;
LABEL_92:
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v15, v25);
      }
LABEL_60:
      if ( ++v15 >= dwNumDevs )
        goto LABEL_61;
    }
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_60;
    }
    v25 = GetLastError();
    v26 = 134;
    goto LABEL_92;
  }
LABEL_61:
  for ( i = 0; i < *(_DWORD *)FaxDevicesRegistry; ++i )
  {
    v21 = 88LL * i;
    v22 = *(_QWORD *)(FaxDevicesRegistry + 8);
    if ( *(_DWORD *)(v21 + v22 + 60) && (*(_BYTE *)(v21 + v22 + 16) & 4) == 0 && !*(_DWORD *)(v21 + v22 + 56) )
      MoveDeviceRegIntoDeviceCache(
        *(unsigned int *)(v21 + v22 + 64),
        *(unsigned int *)(v21 + v22),
        *(_DWORD *)(v21 + v22 + 64) == g_dwManualAnswerDeviceId);
  }
  ((void (__fastcall *)(_QWORD))CleanOldDevicesFromDeviceCache)(SystemTimeAsFileTime);
  if ( (unsigned int)GetCountries() )
  {
    LeaveCriticalSection(&g_CsLine);
    goto LABEL_98;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 135, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
  }
  v4 = GetLastError();
  if ( !v4 )
    v4 = 31;
LABEL_74:
  LeaveCriticalSection(&g_CsLine);
  if ( g_hLineApp )
  {
    v23 = lineShutdown(g_hLineApp);
    if ( v23
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v23);
    }
    g_hLineApp = 0;
  }
  if ( g_TapiCompletionPort )
  {
    if ( !CloseHandle(g_TapiCompletionPort)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v24);
    }
    g_TapiCompletionPort = 0;
  }
LABEL_98:
  if ( FaxDevicesRegistry )
  {
    for ( j = 0; j < *(_DWORD *)FaxDevicesRegistry; ++j )
      pMemFree(*(LPVOID *)(88LL * j + *(_QWORD *)(FaxDevicesRegistry + 8) + 8));
    pMemFree(*(LPVOID *)(FaxDevicesRegistry + 8));
    pMemFree((LPVOID)FaxDevicesRegistry);
  }
  return v4;
}

```

## disassembly

```asm
0x14004c3cc  push    rbp
0x14004c3ce  push    rbx
0x14004c3cf  push    rsi
0x14004c3d0  push    rdi
0x14004c3d1  push    r12
0x14004c3d3  push    r13
0x14004c3d5  push    r14
0x14004c3d7  push    r15
0x14004c3d9  lea     rbp, [rsp-7B8h]
0x14004c3e1  sub     rsp, 8B8h
0x14004c3e8  mov     rax, cs:__security_cookie
0x14004c3ef  xor     rax, rsp
0x14004c3f2  mov     [rbp+7F0h+var_50], rax
0x14004c3f9  xor     r15d, r15d
0x14004c3fc  xorps   xmm0, xmm0
0x14004c3ff  movups  xmmword ptr [rsp+8F0h+LineInitializeExParams.dwTotalSize], xmm0
0x14004c404  mov     r14d, r15d
0x14004c407  mov     [rsp+8F0h+dwAPIVersion], r15d
0x14004c40c  movups  xmmword ptr [rsp+8F0h+LineInitializeExParams.dwOptions], xmm0
0x14004c411  mov     qword ptr [rsp+8F0h+SystemTimeAsFileTime.dwLowDateTime], r15
0x14004c416  movups  xmmword ptr [rbp+7F0h+ExtensionID.dwExtensionID0], xmm0
0x14004c41a  mov     [rsp+8F0h+dwNumDevs], r15d
0x14004c41f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c426  lea     r13, WPP_GLOBAL_Control
0x14004c42d  lea     rdi, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004c434  mov     r12b, 4
0x14004c437  cmp     rcx, r13
0x14004c43a  jz      short loc_14004C458
0x14004c43c  test    [rcx+1Ch], r12b
0x14004c440  jz      short loc_14004C458
0x14004c442  cmp     byte ptr [rcx+19h], 5
0x14004c446  jb      short loc_14004C458
0x14004c448  mov     rcx, [rcx+10h]
0x14004c44c  lea     edx, [r15+7Bh]
0x14004c450  mov     r8, rdi
0x14004c453  call    WPP_SF_
0x14004c458  lea     rcx, [rsp+8F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14004c45d  call    cs:__imp_GetSystemTimeAsFileTime
0x14004c463  lea     rbx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CsLine
0x14004c46a  mov     rcx, rbx; lpCriticalSection
0x14004c46d  call    cs:__imp_EnterCriticalSection
0x14004c473  mov     r9d, 1; NumberOfConcurrentThreads
0x14004c479  xor     r8d, r8d; CompletionKey
0x14004c47c  xor     edx, edx; ExistingCompletionPort
0x14004c47e  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x14004c482  call    cs:__imp_CreateIoCompletionPort
0x14004c488  mov     cs:?g_TapiCompletionPort@@3PEAXEA, rax; void * g_TapiCompletionPort
0x14004c48f  test    rax, rax
0x14004c492  jnz     short loc_14004C4D0
0x14004c494  call    cs:__imp_GetLastError
0x14004c49a  mov     esi, eax
0x14004c49c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c4a3  cmp     rcx, r13
0x14004c4a6  jz      short loc_14004C4C8
0x14004c4a8  test    [rcx+1Ch], r12b
0x14004c4ac  jz      short loc_14004C4C8
0x14004c4ae  cmp     byte ptr [rcx+19h], 2
0x14004c4b2  jb      short loc_14004C4C8
0x14004c4b4  mov     edx, 7Ch ; '|'
0x14004c4b9  mov     r9d, eax
0x14004c4bc  mov     rcx, [rcx+10h]
0x14004c4c0  mov     r8, rdi
0x14004c4c3  call    WPP_SF_d
0x14004c4c8  mov     rcx, rbx
0x14004c4cb  jmp     loc_14004C940
0x14004c4d0  xor     ecx, ecx; lpModuleName
0x14004c4d2  mov     qword ptr [rsp+8F0h+LineInitializeExParams.dwTotalSize], 1Ch
0x14004c4db  mov     [rsp+8F0h+LineInitializeExParams.dwUsedSize], r15d
0x14004c4e0  mov     [rsp+8F0h+LineInitializeExParams.dwOptions], 3
0x14004c4e8  mov     qword ptr [rsp+8F0h+LineInitializeExParams.Handles], rax
0x14004c4ed  mov     [rsp+8F0h+LineInitializeExParams.dwCompletionKey], 80000001h
0x14004c4f5  mov     [rsp+8F0h+dwAPIVersion], 20000h
0x14004c4fd  call    cs:__imp_GetModuleHandleW
0x14004c503  lea     r9, szFriendlyAppName; "Microsoft Fax Server Service"
0x14004c50a  xor     r8d, r8d; lpfnCallback
0x14004c50d  mov     rdx, rax; hInstance
0x14004c510  lea     rcx, ?g_hLineApp@@3KA; lphLineApp
0x14004c517  lea     rax, [rsp+8F0h+LineInitializeExParams]
0x14004c51c  mov     [rsp+8F0h+lpLineInitializeExParams], rax; lpLineInitializeExParams
0x14004c521  lea     rax, [rsp+8F0h+dwAPIVersion]
0x14004c526  mov     [rsp+8F0h+lpdwAPIVersion], rax; lpdwAPIVersion
0x14004c52b  lea     rax, [rsp+8F0h+dwNumDevs]
0x14004c530  mov     [rsp+8F0h+lpdwNumDevs], rax; lpdwNumDevs
0x14004c535  call    cs:__imp_lineInitializeExW
0x14004c53b  mov     esi, eax
0x14004c53d  test    eax, eax
0x14004c53f  jz      short loc_14004C584
0x14004c541  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c548  cmp     rcx, r13
0x14004c54b  jz      loc_14004C4C8
0x14004c551  test    [rcx+1Ch], r12b
0x14004c555  jz      loc_14004C4C8
0x14004c55b  cmp     byte ptr [rcx+19h], 2
0x14004c55f  jb      loc_14004C4C8
0x14004c565  mov     r9d, [rsp+8F0h+dwNumDevs]
0x14004c56a  mov     edx, 7Dh ; '}'
0x14004c56f  mov     rcx, [rcx+10h]
0x14004c573  mov     r8, rdi
0x14004c576  mov     dword ptr [rsp+8F0h+lpdwNumDevs], eax
0x14004c57a  call    WPP_SF_dd
0x14004c57f  jmp     loc_14004C4C8
0x14004c584  mov     r9d, [rsp+8F0h+dwAPIVersion]
0x14004c589  cmp     r9d, 20000h
0x14004c590  jnb     short loc_14004C5C5
0x14004c592  mov     esi, 8000000Ch
0x14004c597  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c59e  cmp     rcx, r13
0x14004c5a1  jz      loc_14004C4C8
0x14004c5a7  test    [rcx+1Ch], r12b
0x14004c5ab  jz      loc_14004C4C8
0x14004c5b1  cmp     byte ptr [rcx+19h], 2
0x14004c5b5  jb      loc_14004C4C8
0x14004c5bb  mov     edx, 7Eh ; '~'
0x14004c5c0  jmp     loc_14004C4BC
0x14004c5c5  mov     ebx, 208h
0x14004c5ca  lea     rdx, [rbp+7F0h+Filename]; lpFilename
0x14004c5ce  mov     r8d, ebx; nSize
0x14004c5d1  xor     ecx, ecx; hModule
0x14004c5d3  call    cs:__imp_GetModuleFileNameW
0x14004c5d9  test    eax, eax
0x14004c5db  jnz     short loc_14004C5E4
0x14004c5dd  mov     [rbp+7F0h+Filename], r15w
0x14004c5e2  jmp     short loc_14004C5F8
0x14004c5e4  cmp     eax, ebx
0x14004c5e6  jnz     short loc_14004C63D
0x14004c5e8  mov     ecx, 7Ah ; 'z'; dwErrCode
0x14004c5ed  mov     [rbp+7F0h+Filename], r15w
0x14004c5f2  call    cs:__imp_SetLastError
0x14004c5f8  call    cs:__imp_GetLastError
0x14004c5fe  mov     esi, eax
0x14004c600  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c607  cmp     rcx, r13
0x14004c60a  jz      loc_14004C939
0x14004c610  test    [rcx+1Ch], r12b
0x14004c614  jz      loc_14004C939
0x14004c61a  cmp     byte ptr [rcx+19h], 2
0x14004c61e  jb      loc_14004C939
0x14004c624  mov     edx, 7Fh
0x14004c629  mov     rcx, [rcx+10h]
0x14004c62d  mov     r9d, eax
0x14004c630  mov     r8, rdi
0x14004c633  call    WPP_SF_d
0x14004c638  jmp     loc_14004C939
0x14004c63d  mov     [rbp+7F0h+var_452], r15w
0x14004c645  mov     ecx, 100h
0x14004c64a  lea     rax, [rbp+7F0h+var_450]
0x14004c651  mov     [rsp+8F0h+ExtCount], rcx; ExtCount
0x14004c656  xor     r9d, r9d; Dir
0x14004c659  mov     [rsp+8F0h+Ext], rax; Ext
0x14004c65e  xor     r8d, r8d; DriveCount
0x14004c661  mov     [rsp+8F0h+lpLineInitializeExParams], rcx; FilenameCount
0x14004c666  lea     rax, [rbp+7F0h+var_250]
0x14004c66d  mov     [rsp+8F0h+lpdwAPIVersion], rax; Filename
0x14004c672  lea     rcx, [rbp+7F0h+Filename]; FullPath
0x14004c676  xor     edx, edx; Drive
0x14004c678  mov     [rsp+8F0h+lpdwNumDevs], r15; DirCount
0x14004c67d  mov     esi, r15d
0x14004c680  call    cs:__imp__wsplitpath_s
0x14004c686  test    eax, eax
0x14004c688  jz      short loc_14004C6C4
0x14004c68a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c691  cmp     rcx, r13
0x14004c694  jz      loc_14004C939
0x14004c69a  test    [rcx+1Ch], r12b
0x14004c69e  jz      loc_14004C939
0x14004c6a4  cmp     byte ptr [rcx+19h], 2
0x14004c6a8  jb      loc_14004C939
0x14004c6ae  mov     rcx, [rcx+10h]
0x14004c6b2  mov     edx, 80h
0x14004c6b7  mov     r8, rdi
0x14004c6ba  call    WPP_SF_
0x14004c6bf  jmp     loc_14004C939
0x14004c6c4  lea     rax, [rbp+7F0h+var_450]
0x14004c6cb  mov     rdx, rbx; unsigned __int64
0x14004c6ce  lea     r9, [rbp+7F0h+var_250]
0x14004c6d5  mov     [rsp+8F0h+lpdwNumDevs], rax
0x14004c6da  lea     r8, aSS_1; "%s%s"
0x14004c6e1  lea     rcx, [rbp+7F0h+Filename]; unsigned __int16 *
0x14004c6e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004c6ea  test    eax, eax
0x14004c6ec  jns     short loc_14004C72B
0x14004c6ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c6f5  cmp     rcx, r13
0x14004c6f8  jz      loc_14004C939
0x14004c6fe  test    [rcx+1Ch], r12b
0x14004c702  jz      loc_14004C939
0x14004c708  cmp     byte ptr [rcx+19h], 2
0x14004c70c  jb      loc_14004C939
0x14004c712  mov     rcx, [rcx+10h]
0x14004c716  mov     edx, 81h
0x14004c71b  mov     r9d, eax
0x14004c71e  mov     r8, rdi
0x14004c721  call    WPP_SF_d
0x14004c726  jmp     loc_14004C939
0x14004c72b  mov     ebx, 1
0x14004c730  lea     rcx, [rbp+7F0h+Filename]; lpszAppFilename
0x14004c734  mov     dword ptr [rsp+8F0h+lpdwAPIVersion], ebx; dwPriority
0x14004c738  xor     r9d, r9d; dwRequestMode
0x14004c73b  xor     r8d, r8d; lpExtensionID
0x14004c73e  mov     [rsp+8F0h+lpdwNumDevs], r15; lpszExtensionName
0x14004c743  lea     edx, [rbx+1]; dwMediaMode
0x14004c746  call    cs:__imp_lineSetAppPriorityW
0x14004c74c  xor     r9d, r9d; dwRequestMode
0x14004c74f  mov     dword ptr [rsp+8F0h+lpdwAPIVersion], ebx; dwPriority
0x14004c753  xor     r8d, r8d; lpExtensionID
0x14004c756  mov     [rsp+8F0h+lpdwNumDevs], r15; lpszExtensionName
0x14004c75b  lea     edx, [rbx+0Fh]; dwMediaMode
0x14004c75e  lea     rcx, [rbp+7F0h+Filename]; lpszAppFilename
0x14004c762  call    cs:__imp_lineSetAppPriorityW
0x14004c768  test    eax, eax
0x14004c76a  jz      short loc_14004C79C
0x14004c76c  mov     esi, eax
0x14004c76e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c775  cmp     rcx, r13
0x14004c778  jz      loc_14004C939
0x14004c77e  test    [rcx+1Ch], r12b
0x14004c782  jz      loc_14004C939
0x14004c788  cmp     byte ptr [rcx+19h], 2
0x14004c78c  jb      loc_14004C939
0x14004c792  mov     edx, 82h
0x14004c797  jmp     loc_14004C629
0x14004c79c  call    GetFaxDevicesRegistry
0x14004c7a1  mov     r14, rax
0x14004c7a4  test    rax, rax
0x14004c7a7  jnz     short loc_14004C7D2
0x14004c7a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c7b0  cmp     rcx, r13
0x14004c7b3  jz      short loc_14004C7D2
0x14004c7b5  test    [rcx+1Ch], r12b
0x14004c7b9  jz      short loc_14004C7D2
0x14004c7bb  cmp     byte ptr [rcx+19h], 2
0x14004c7bf  jb      short loc_14004C7D2
0x14004c7c1  mov     rcx, [rcx+10h]
0x14004c7c5  mov     edx, 83h
0x14004c7ca  mov     r8, rdi
0x14004c7cd  call    WPP_SF_
0x14004c7d2  mov     ebx, r15d
0x14004c7d5  cmp     [rsp+8F0h+dwNumDevs], r15d
0x14004c7da  jbe     loc_14004C8A0
0x14004c7e0  mov     ecx, cs:?g_hLineApp@@3KA; hLineApp
0x14004c7e6  lea     rax, [rbp+7F0h+ExtensionID]
0x14004c7ea  mov     [rsp+8F0h+lpdwAPIVersion], rax; lpExtensionID
0x14004c7ef  mov     r9d, 20000h; dwAPIHighVersion
0x14004c7f5  lea     rax, [rsp+8F0h+dwAPIVersion]
0x14004c7fa  mov     r8d, 10003h; dwAPILowVersion
0x14004c800  mov     edx, ebx; dwDeviceID
0x14004c802  mov     [rsp+8F0h+lpdwNumDevs], rax; lpdwAPIVersion
0x14004c807  call    cs:__imp_lineNegotiateAPIVersion
0x14004c80d  test    eax, eax
0x14004c80f  jnz     loc_14004CA41
0x14004c815  mov     r8d, [rsp+8F0h+dwAPIVersion]
0x14004c81a  mov     edx, ebx
0x14004c81c  call    SmartLineGetDevCaps
0x14004c821  mov     rdi, rax
0x14004c824  test    rax, rax
0x14004c827  jz      loc_14004C9EC
0x14004c82d  mov     r9, r14; struct _REG_FAX_DEVICES *
0x14004c830  mov     r8d, 1; int
0x14004c836  mov     rdx, rax; struct linedevcaps_tag *
0x14004c839  mov     ecx, ebx; dwDeviceID
0x14004c83b  call    ?AddNewDevice@@YAHKPEAUlinedevcaps_tag@@HPEAU_REG_FAX_DEVICES@@@Z; AddNewDevice(ulong,linedevcaps_tag *,int,_REG_FAX_DEVICES *)
0x14004c840  test    eax, eax
0x14004c842  jnz     short loc_14004C885
0x14004c844  mov     rax, cs:WPP_GLOBAL_Control
0x14004c84b  cmp     rax, r13
0x14004c84e  jz      short loc_14004C885
0x14004c850  test    [rax+1Ch], r12b
0x14004c854  jz      short loc_14004C885
0x14004c856  cmp     byte ptr [rax+19h], 3
0x14004c85a  jb      short loc_14004C885
0x14004c85c  call    cs:__imp_GetLastError
0x14004c862  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c869  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004c870  mov     edx, 84h
0x14004c875  mov     dword ptr [rsp+8F0h+lpdwNumDevs], eax
0x14004c879  mov     r9d, ebx
0x14004c87c  mov     rcx, [rcx+10h]
0x14004c880  call    WPP_SF_dd
0x14004c885  mov     rcx, rdi; lpMem
0x14004c888  call    pMemFree
0x14004c88d  lea     rdi, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004c894  inc     ebx
0x14004c896  cmp     ebx, [rsp+8F0h+dwNumDevs]
0x14004c89a  jb      loc_14004C7E0
0x14004c8a0  mov     ebx, r15d
0x14004c8a3  cmp     [r14], r15d
0x14004c8a6  jbe     short loc_14004C8E7
0x14004c8a8  mov     eax, ebx
0x14004c8aa  imul    rdx, rax, 58h ; 'X'
0x14004c8ae  mov     rax, [r14+8]
0x14004c8b2  cmp     [rdx+rax+3Ch], r15d
0x14004c8b7  jz      short loc_14004C8E0
0x14004c8b9  test    [rdx+rax+10h], r12b
0x14004c8be  jnz     short loc_14004C8E0
0x14004c8c0  cmp     [rdx+rax+38h], r15d
0x14004c8c5  jnz     short loc_14004C8E0
0x14004c8c7  mov     ecx, [rdx+rax+40h]
0x14004c8cb  mov     r8d, r15d
0x14004c8ce  cmp     ecx, cs:?g_dwManualAnswerDeviceId@@3KA; ulong g_dwManualAnswerDeviceId
0x14004c8d4  mov     edx, [rdx+rax]
  ... truncated ...
```
