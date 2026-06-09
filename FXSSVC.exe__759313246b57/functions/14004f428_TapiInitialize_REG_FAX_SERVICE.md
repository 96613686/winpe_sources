# TapiInitialize(_REG_FAX_SERVICE *)

- ea: `0x14004f428`
- end: `0x14004fbbe`
- name: `?TapiInitialize@@YAKPEAU_REG_FAX_SERVICE@@@Z`
- size: `1942`
- prototype: `unsigned int __fastcall(struct _REG_FAX_SERVICE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140049f40`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004fe4`
- `0x14004c1a4`
- `0x14004f428`
- `0x1400513e4`
- `0x140051bb4`
- `0x14006998c`
- `0x14007b1dc`
- `0x140081d0c`
- `0x140082be8`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14004f653`
- `KERNEL32!GetModuleFileNameW` at `0x14004f653`
- `KERNEL32!GetLastError` at `0x14004f502`
- `KERNEL32!GetLastError` at `0x14004f684`
- `KERNEL32!GetLastError` at `0x14004f906`
- `KERNEL32!GetLastError` at `0x14004f9d7`
- `KERNEL32!GetLastError` at `0x14004fa87`
- `KERNEL32!GetLastError` at `0x14004fade`
- `KERNEL32!GetLastError` at `0x14004fb39`
- `KERNEL32!GetLastError` at `0x14004f502`
- `KERNEL32!GetLastError` at `0x14004f684`
- `KERNEL32!GetLastError` at `0x14004f906`
- `KERNEL32!GetLastError` at `0x14004f9d7`
- `KERNEL32!GetLastError` at `0x14004fa87`
- `KERNEL32!GetLastError` at `0x14004fade`
- `KERNEL32!GetLastError` at `0x14004fb39`
- `KERNEL32!SetLastError` at `0x14004f678`
- `KERNEL32!SetLastError` at `0x14004f678`
- `KERNEL32!CloseHandle` at `0x14004fa5f`
- `KERNEL32!CloseHandle` at `0x14004fa5f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14004f4b9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14004f4b9`
- `KERNEL32!EnterCriticalSection` at `0x14004f4cf`
- `KERNEL32!EnterCriticalSection` at `0x14004f4cf`
- `KERNEL32!LeaveCriticalSection` at `0x14004f9f6`
- `KERNEL32!LeaveCriticalSection` at `0x14004fb53`
- `KERNEL32!LeaveCriticalSection` at `0x14004f9f6`
- `KERNEL32!LeaveCriticalSection` at `0x14004fb53`
- `KERNEL32!GetModuleHandleW` at `0x14004f571`
- `KERNEL32!GetModuleHandleW` at `0x14004f571`
- `KERNEL32!CreateIoCompletionPort` at `0x14004f4ea`
- `KERNEL32!CreateIoCompletionPort` at `0x14004f4ea`
- `msvcrt!_wsplitpath_s` at `0x14004f712`
- `msvcrt!_wsplitpath_s` at `0x14004f712`
- `TAPI32!lineShutdown` at `0x14004fa0c`
- `TAPI32!lineShutdown` at `0x14004fa0c`
- `TAPI32!lineNegotiateAPIVersion` at `0x14004f8ab`
- `TAPI32!lineNegotiateAPIVersion` at `0x14004f8ab`
- `TAPI32!lineInitializeExW` at `0x14004f5af`
- `TAPI32!lineInitializeExW` at `0x14004f5af`
- `TAPI32!lineSetAppPriorityW` at `0x14004f7de`
- `TAPI32!lineSetAppPriorityW` at `0x14004f800`
- `TAPI32!lineSetAppPriorityW` at `0x14004f7de`
- `TAPI32!lineSetAppPriorityW` at `0x14004f800`

## string_xrefs

- `0x14004f57d`: `Microsoft Fax Server Service`

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
  DWORD ModuleFileNameW; // eax
  DWORD v10; // eax
  CMapDeviceId *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  DWORD v14; // ebx
  __int64 v15; // rcx
  struct linedevcaps_tag *DevCaps; // rax
  struct linedevcaps_tag *v17; // rdi
  unsigned int i; // ebx
  __int64 v19; // rdx
  __int64 v20; // rax
  unsigned int v21; // eax
  DWORD v22; // eax
  __int64 v23; // rdx
  unsigned int j; // edi
  DWORD dwAPIVersion; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwNumDevs; // [rsp+54h] [rbp-ACh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  struct lineinitializeexparams_tag LineInitializeExParams; // [rsp+60h] [rbp-A0h] BYREF
  lineextensionid_tag ExtensionID; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[520]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Ext[256]; // [rsp+4A0h] [rbp+3A0h] BYREF
  wchar_t v33[256]; // [rsp+6A0h] [rbp+5A0h] BYREF

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
  v4 = lineInitializeExW(
         &g_hLineApp,
         ModuleHandleW,
         0,
         L"Microsoft Fax Server Service",
         &dwNumDevs,
         &dwAPIVersion,
         &LineInitializeExParams);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
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
    v10 = GetLastError();
    v4 = v10;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v12 = 127;
    goto LABEL_30;
  }
  Filename[519] = 0;
  v4 = 0;
  if ( _wsplitpath_s(Filename, 0, 0, 0, 0, v33, 0x100u, Ext, 0x100u) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
    }
    goto LABEL_74;
  }
  v13 = StringCchPrintfW(Filename, 0x208u, L"%s%s", v33, Ext);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        129,
        &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids,
        (unsigned int)v13);
    }
    goto LABEL_74;
  }
  lineSetAppPriorityW(Filename, 2u, 0, 0, 0, 1u);
  v10 = lineSetAppPriorityW(Filename, 0x10u, 0, 0, 0, 1u);
  if ( v10 )
  {
    v4 = v10;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v12 = 130;
LABEL_30:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v10);
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
  v14 = 0;
  if ( dwNumDevs )
  {
    while ( !lineNegotiateAPIVersion(g_hLineApp, v14, 0x10003u, 0x20000u, &dwAPIVersion, &ExtensionID) )
    {
      DevCaps = (struct linedevcaps_tag *)SmartLineGetDevCaps(v15, v14, dwAPIVersion);
      v17 = DevCaps;
      if ( DevCaps )
      {
        if ( !(unsigned int)AddNewDevice(v14, DevCaps, 1, (struct _REG_FAX_DEVICES *)FaxDevicesRegistry)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          GetLastError();
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
        }
        pMemFree(v17);
        goto LABEL_60;
      }
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        GetLastError();
        v23 = 133;
LABEL_92:
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
      }
LABEL_60:
      if ( ++v14 >= dwNumDevs )
        goto LABEL_61;
    }
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_60;
    }
    GetLastError();
    v23 = 134;
    goto LABEL_92;
  }
LABEL_61:
  for ( i = 0; i < *(_DWORD *)FaxDevicesRegistry; ++i )
  {
    v19 = 88LL * i;
    v20 = *(_QWORD *)(FaxDevicesRegistry + 8);
    if ( *(_DWORD *)(v19 + v20 + 60) && (*(_BYTE *)(v19 + v20 + 16) & 4) == 0 && !*(_DWORD *)(v19 + v20 + 56) )
      MoveDeviceRegIntoDeviceCache(
        *(unsigned int *)(v19 + v20 + 64),
        *(unsigned int *)(v19 + v20),
        *(_DWORD *)(v19 + v20 + 64) == g_dwManualAnswerDeviceId);
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
    v21 = lineShutdown(g_hLineApp);
    if ( v21
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v21);
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
      v22 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids, v22);
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
0x14004f428  push    rbp
0x14004f42a  push    rbx
0x14004f42b  push    rsi
0x14004f42c  push    rdi
0x14004f42d  push    r12
0x14004f42f  push    r13
0x14004f431  push    r14
0x14004f433  push    r15
0x14004f435  lea     rbp, [rsp-7B8h]
0x14004f43d  sub     rsp, 8B8h
0x14004f444  mov     rax, cs:__security_cookie
0x14004f44b  xor     rax, rsp
0x14004f44e  mov     [rbp+7F0h+var_50], rax
0x14004f455  xor     r15d, r15d
0x14004f458  xorps   xmm0, xmm0
0x14004f45b  movups  xmmword ptr [rsp+8F0h+LineInitializeExParams.dwTotalSize], xmm0
0x14004f460  mov     r14d, r15d
0x14004f463  mov     [rsp+8F0h+dwAPIVersion], r15d
0x14004f468  movups  xmmword ptr [rsp+8F0h+LineInitializeExParams.dwOptions], xmm0
0x14004f46d  mov     qword ptr [rsp+8F0h+SystemTimeAsFileTime.dwLowDateTime], r15
0x14004f472  movups  xmmword ptr [rbp+7F0h+ExtensionID.dwExtensionID0], xmm0
0x14004f476  mov     [rsp+8F0h+dwNumDevs], r15d
0x14004f47b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f482  lea     r13, WPP_GLOBAL_Control
0x14004f489  lea     rdi, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004f490  mov     r12b, 4
0x14004f493  cmp     rcx, r13
0x14004f496  jz      short loc_14004F4B4
0x14004f498  test    [rcx+1Ch], r12b
0x14004f49c  jz      short loc_14004F4B4
0x14004f49e  cmp     byte ptr [rcx+19h], 5
0x14004f4a2  jb      short loc_14004F4B4
0x14004f4a4  mov     rcx, [rcx+10h]
0x14004f4a8  lea     edx, [r15+7Bh]
0x14004f4ac  mov     r8, rdi
0x14004f4af  call    WPP_SF_
0x14004f4b4  lea     rcx, [rsp+8F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14004f4b9  call    cs:__imp_GetSystemTimeAsFileTime
0x14004f4c0  nop     dword ptr [rax+rax+00h]
0x14004f4c5  lea     rbx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CsLine
0x14004f4cc  mov     rcx, rbx; lpCriticalSection
0x14004f4cf  call    cs:__imp_EnterCriticalSection
0x14004f4d6  nop     dword ptr [rax+rax+00h]
0x14004f4db  mov     r9d, 1; NumberOfConcurrentThreads
0x14004f4e1  xor     r8d, r8d; CompletionKey
0x14004f4e4  xor     edx, edx; ExistingCompletionPort
0x14004f4e6  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x14004f4ea  call    cs:__imp_CreateIoCompletionPort
0x14004f4f1  nop     dword ptr [rax+rax+00h]
0x14004f4f6  mov     cs:?g_TapiCompletionPort@@3PEAXEA, rax; void * g_TapiCompletionPort
0x14004f4fd  test    rax, rax
0x14004f500  jnz     short loc_14004F544
0x14004f502  call    cs:__imp_GetLastError
0x14004f509  nop     dword ptr [rax+rax+00h]
0x14004f50e  mov     esi, eax
0x14004f510  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f517  cmp     rcx, r13
0x14004f51a  jz      short loc_14004F53C
0x14004f51c  test    [rcx+1Ch], r12b
0x14004f520  jz      short loc_14004F53C
0x14004f522  cmp     byte ptr [rcx+19h], 2
0x14004f526  jb      short loc_14004F53C
0x14004f528  mov     edx, 7Ch ; '|'
0x14004f52d  mov     r9d, eax
0x14004f530  mov     rcx, [rcx+10h]
0x14004f534  mov     r8, rdi
0x14004f537  call    WPP_SF_d
0x14004f53c  mov     rcx, rbx
0x14004f53f  jmp     loc_14004F9F6
0x14004f544  xor     ecx, ecx; lpModuleName
0x14004f546  mov     qword ptr [rsp+8F0h+LineInitializeExParams.dwTotalSize], 1Ch
0x14004f54f  mov     [rsp+8F0h+LineInitializeExParams.dwUsedSize], r15d
0x14004f554  mov     [rsp+8F0h+LineInitializeExParams.dwOptions], 3
0x14004f55c  mov     qword ptr [rsp+8F0h+LineInitializeExParams.Handles], rax
0x14004f561  mov     [rsp+8F0h+LineInitializeExParams.dwCompletionKey], 80000001h
0x14004f569  mov     [rsp+8F0h+dwAPIVersion], 20000h
0x14004f571  call    cs:__imp_GetModuleHandleW
0x14004f578  nop     dword ptr [rax+rax+00h]
0x14004f57d  lea     r9, szFriendlyAppName; "Microsoft Fax Server Service"
0x14004f584  xor     r8d, r8d; lpfnCallback
0x14004f587  mov     rdx, rax; hInstance
0x14004f58a  lea     rcx, ?g_hLineApp@@3KA; lphLineApp
0x14004f591  lea     rax, [rsp+8F0h+LineInitializeExParams]
0x14004f596  mov     [rsp+8F0h+lpLineInitializeExParams], rax; lpLineInitializeExParams
0x14004f59b  lea     rax, [rsp+8F0h+dwAPIVersion]
0x14004f5a0  mov     [rsp+8F0h+lpdwAPIVersion], rax; lpdwAPIVersion
0x14004f5a5  lea     rax, [rsp+8F0h+dwNumDevs]
0x14004f5aa  mov     [rsp+8F0h+lpdwNumDevs], rax; lpdwNumDevs
0x14004f5af  call    cs:__imp_lineInitializeExW
0x14004f5b6  nop     dword ptr [rax+rax+00h]
0x14004f5bb  mov     esi, eax
0x14004f5bd  test    eax, eax
0x14004f5bf  jz      short loc_14004F604
0x14004f5c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f5c8  cmp     rcx, r13
0x14004f5cb  jz      loc_14004F53C
0x14004f5d1  test    [rcx+1Ch], r12b
0x14004f5d5  jz      loc_14004F53C
0x14004f5db  cmp     byte ptr [rcx+19h], 2
0x14004f5df  jb      loc_14004F53C
0x14004f5e5  mov     r9d, [rsp+8F0h+dwNumDevs]
0x14004f5ea  mov     edx, 7Dh ; '}'
0x14004f5ef  mov     rcx, [rcx+10h]
0x14004f5f3  mov     r8, rdi
0x14004f5f6  mov     dword ptr [rsp+8F0h+lpdwNumDevs], eax
0x14004f5fa  call    WPP_SF_dd
0x14004f5ff  jmp     loc_14004F53C
0x14004f604  mov     r9d, [rsp+8F0h+dwAPIVersion]
0x14004f609  cmp     r9d, 20000h
0x14004f610  jnb     short loc_14004F645
0x14004f612  mov     esi, 8000000Ch
0x14004f617  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f61e  cmp     rcx, r13
0x14004f621  jz      loc_14004F53C
0x14004f627  test    [rcx+1Ch], r12b
0x14004f62b  jz      loc_14004F53C
0x14004f631  cmp     byte ptr [rcx+19h], 2
0x14004f635  jb      loc_14004F53C
0x14004f63b  mov     edx, 7Eh ; '~'
0x14004f640  jmp     loc_14004F530
0x14004f645  mov     ebx, 208h
0x14004f64a  lea     rdx, [rbp+7F0h+Filename]; lpFilename
0x14004f64e  mov     r8d, ebx; nSize
0x14004f651  xor     ecx, ecx; hModule
0x14004f653  call    cs:__imp_GetModuleFileNameW
0x14004f65a  nop     dword ptr [rax+rax+00h]
0x14004f65f  test    eax, eax
0x14004f661  jnz     short loc_14004F66A
0x14004f663  mov     [rbp+7F0h+Filename], r15w
0x14004f668  jmp     short loc_14004F684
0x14004f66a  cmp     eax, ebx
0x14004f66c  jnz     short loc_14004F6CF
0x14004f66e  mov     ecx, 7Ah ; 'z'; dwErrCode
0x14004f673  mov     [rbp+7F0h+Filename], r15w
0x14004f678  call    cs:__imp_SetLastError
0x14004f67f  nop     dword ptr [rax+rax+00h]
0x14004f684  call    cs:__imp_GetLastError
0x14004f68b  nop     dword ptr [rax+rax+00h]
0x14004f690  mov     esi, eax
0x14004f692  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f699  cmp     rcx, r13
0x14004f69c  jz      loc_14004F9EF
0x14004f6a2  test    [rcx+1Ch], r12b
0x14004f6a6  jz      loc_14004F9EF
0x14004f6ac  cmp     byte ptr [rcx+19h], 2
0x14004f6b0  jb      loc_14004F9EF
0x14004f6b6  mov     edx, 7Fh
0x14004f6bb  mov     rcx, [rcx+10h]
0x14004f6bf  mov     r9d, eax
0x14004f6c2  mov     r8, rdi
0x14004f6c5  call    WPP_SF_d
0x14004f6ca  jmp     loc_14004F9EF
0x14004f6cf  mov     [rbp+7F0h+var_452], r15w
0x14004f6d7  mov     ecx, 100h
0x14004f6dc  lea     rax, [rbp+7F0h+var_450]
0x14004f6e3  mov     [rsp+8F0h+ExtCount], rcx; ExtCount
0x14004f6e8  xor     r9d, r9d; Dir
0x14004f6eb  mov     [rsp+8F0h+Ext], rax; Ext
0x14004f6f0  xor     r8d, r8d; DriveCount
0x14004f6f3  mov     [rsp+8F0h+lpLineInitializeExParams], rcx; FilenameCount
0x14004f6f8  lea     rax, [rbp+7F0h+var_250]
0x14004f6ff  mov     [rsp+8F0h+lpdwAPIVersion], rax; Filename
0x14004f704  lea     rcx, [rbp+7F0h+Filename]; FullPath
0x14004f708  xor     edx, edx; Drive
0x14004f70a  mov     [rsp+8F0h+lpdwNumDevs], r15; DirCount
0x14004f70f  mov     esi, r15d
0x14004f712  call    cs:__imp__wsplitpath_s
0x14004f719  nop     dword ptr [rax+rax+00h]
0x14004f71e  test    eax, eax
0x14004f720  jz      short loc_14004F75C
0x14004f722  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f729  cmp     rcx, r13
0x14004f72c  jz      loc_14004F9EF
0x14004f732  test    [rcx+1Ch], r12b
0x14004f736  jz      loc_14004F9EF
0x14004f73c  cmp     byte ptr [rcx+19h], 2
0x14004f740  jb      loc_14004F9EF
0x14004f746  mov     rcx, [rcx+10h]
0x14004f74a  mov     edx, 80h
0x14004f74f  mov     r8, rdi
0x14004f752  call    WPP_SF_
0x14004f757  jmp     loc_14004F9EF
0x14004f75c  lea     rax, [rbp+7F0h+var_450]
0x14004f763  mov     rdx, rbx; unsigned __int64
0x14004f766  lea     r9, [rbp+7F0h+var_250]
0x14004f76d  mov     [rsp+8F0h+lpdwNumDevs], rax
0x14004f772  lea     r8, aSS_1; "%s%s"
0x14004f779  lea     rcx, [rbp+7F0h+Filename]; unsigned __int16 *
0x14004f77d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004f782  test    eax, eax
0x14004f784  jns     short loc_14004F7C3
0x14004f786  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f78d  cmp     rcx, r13
0x14004f790  jz      loc_14004F9EF
0x14004f796  test    [rcx+1Ch], r12b
0x14004f79a  jz      loc_14004F9EF
0x14004f7a0  cmp     byte ptr [rcx+19h], 2
0x14004f7a4  jb      loc_14004F9EF
0x14004f7aa  mov     rcx, [rcx+10h]
0x14004f7ae  mov     edx, 81h
0x14004f7b3  mov     r9d, eax
0x14004f7b6  mov     r8, rdi
0x14004f7b9  call    WPP_SF_d
0x14004f7be  jmp     loc_14004F9EF
0x14004f7c3  mov     ebx, 1
0x14004f7c8  lea     rcx, [rbp+7F0h+Filename]; lpszAppFilename
0x14004f7cc  mov     dword ptr [rsp+8F0h+lpdwAPIVersion], ebx; dwPriority
0x14004f7d0  xor     r9d, r9d; dwRequestMode
0x14004f7d3  xor     r8d, r8d; lpExtensionID
0x14004f7d6  mov     [rsp+8F0h+lpdwNumDevs], r15; lpszExtensionName
0x14004f7db  lea     edx, [rbx+1]; dwMediaMode
0x14004f7de  call    cs:__imp_lineSetAppPriorityW
0x14004f7e5  nop     dword ptr [rax+rax+00h]
0x14004f7ea  xor     r9d, r9d; dwRequestMode
0x14004f7ed  mov     dword ptr [rsp+8F0h+lpdwAPIVersion], ebx; dwPriority
0x14004f7f1  xor     r8d, r8d; lpExtensionID
0x14004f7f4  mov     [rsp+8F0h+lpdwNumDevs], r15; lpszExtensionName
0x14004f7f9  lea     edx, [rbx+0Fh]; dwMediaMode
0x14004f7fc  lea     rcx, [rbp+7F0h+Filename]; lpszAppFilename
0x14004f800  call    cs:__imp_lineSetAppPriorityW
0x14004f807  nop     dword ptr [rax+rax+00h]
0x14004f80c  test    eax, eax
0x14004f80e  jz      short loc_14004F840
0x14004f810  mov     esi, eax
0x14004f812  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f819  cmp     rcx, r13
0x14004f81c  jz      loc_14004F9EF
0x14004f822  test    [rcx+1Ch], r12b
0x14004f826  jz      loc_14004F9EF
0x14004f82c  cmp     byte ptr [rcx+19h], 2
0x14004f830  jb      loc_14004F9EF
0x14004f836  mov     edx, 82h
0x14004f83b  jmp     loc_14004F6BB
0x14004f840  call    GetFaxDevicesRegistry
0x14004f845  mov     r14, rax
0x14004f848  test    rax, rax
0x14004f84b  jnz     short loc_14004F876
0x14004f84d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f854  cmp     rcx, r13
0x14004f857  jz      short loc_14004F876
0x14004f859  test    [rcx+1Ch], r12b
0x14004f85d  jz      short loc_14004F876
0x14004f85f  cmp     byte ptr [rcx+19h], 2
0x14004f863  jb      short loc_14004F876
0x14004f865  mov     rcx, [rcx+10h]
0x14004f869  mov     edx, 83h
0x14004f86e  mov     r8, rdi
0x14004f871  call    WPP_SF_
0x14004f876  mov     ebx, r15d
0x14004f879  cmp     [rsp+8F0h+dwNumDevs], r15d
0x14004f87e  jbe     loc_14004F950
0x14004f884  mov     ecx, cs:?g_hLineApp@@3KA; hLineApp
0x14004f88a  lea     rax, [rbp+7F0h+ExtensionID]
0x14004f88e  mov     [rsp+8F0h+lpdwAPIVersion], rax; lpExtensionID
0x14004f893  mov     r9d, 20000h; dwAPIHighVersion
0x14004f899  lea     rax, [rsp+8F0h+dwAPIVersion]
0x14004f89e  mov     r8d, 10003h; dwAPILowVersion
0x14004f8a4  mov     edx, ebx; dwDeviceID
0x14004f8a6  mov     [rsp+8F0h+lpdwNumDevs], rax; lpdwAPIVersion
0x14004f8ab  call    cs:__imp_lineNegotiateAPIVersion
0x14004f8b2  nop     dword ptr [rax+rax+00h]
0x14004f8b7  test    eax, eax
0x14004f8b9  jnz     loc_14004FB15
0x14004f8bf  mov     r8d, [rsp+8F0h+dwAPIVersion]
0x14004f8c4  mov     edx, ebx
0x14004f8c6  call    SmartLineGetDevCaps
0x14004f8cb  mov     rdi, rax
0x14004f8ce  test    rax, rax
0x14004f8d1  jz      loc_14004FABA
0x14004f8d7  mov     r9, r14; struct _REG_FAX_DEVICES *
0x14004f8da  mov     r8d, 1; int
0x14004f8e0  mov     rdx, rax; struct linedevcaps_tag *
0x14004f8e3  mov     ecx, ebx; dwDeviceID
0x14004f8e5  call    ?AddNewDevice@@YAHKPEAUlinedevcaps_tag@@HPEAU_REG_FAX_DEVICES@@@Z; AddNewDevice(ulong,linedevcaps_tag *,int,_REG_FAX_DEVICES *)
0x14004f8ea  test    eax, eax
0x14004f8ec  jnz     short loc_14004F935
0x14004f8ee  mov     rax, cs:WPP_GLOBAL_Control
0x14004f8f5  cmp     rax, r13
0x14004f8f8  jz      short loc_14004F935
0x14004f8fa  test    [rax+1Ch], r12b
0x14004f8fe  jz      short loc_14004F935
0x14004f900  cmp     byte ptr [rax+19h], 3
0x14004f904  jb      short loc_14004F935
0x14004f906  call    cs:__imp_GetLastError
0x14004f90d  nop     dword ptr [rax+rax+00h]
0x14004f912  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f919  lea     r8, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004f920  mov     edx, 84h
0x14004f925  mov     dword ptr [rsp+8F0h+lpdwNumDevs], eax
0x14004f929  mov     r9d, ebx
0x14004f92c  mov     rcx, [rcx+10h]
0x14004f930  call    WPP_SF_dd
0x14004f935  mov     rcx, rdi; lpMem
0x14004f938  call    pMemFree
0x14004f93d  lea     rdi, WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids
0x14004f944  inc     ebx
0x14004f946  cmp     ebx, [rsp+8F0h+dwNumDevs]
0x14004f94a  jb      loc_14004F884
0x14004f950  mov     ebx, r15d
0x14004f953  cmp     [r14], r15d
  ... truncated ...
```
