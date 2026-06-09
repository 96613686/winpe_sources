# FaxServiceMain(ulong,ushort * *)

- ea: `0x1400246b0`
- end: `0x140024d70`
- name: `?FaxServiceMain@@YAXKPEAPEAG@Z`
- size: `1728`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400240e0`
- `0x1400246b0`
- `0x140025000`
- `0x140025934`
- `0x140025a34`
- `0x140025b04`
- `0x140026388`
- `0x140049678`
- `0x14004ae64`
- `0x140069850`
- `0x14006998c`
- `0x140074cb4`
- `0x140074da0`
- `0x140074f18`
- `0x140075070`
- `0x140076574`
- `0x1400867cc`
- `0x140086ae4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002487c`
- `ADVAPI32!RegCloseKey` at `0x140024c2e`
- `ADVAPI32!RegCloseKey` at `0x14002487c`
- `ADVAPI32!RegCloseKey` at `0x140024c2e`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x140024951`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x140024951`
- `ADVAPI32!DeregisterEventSource` at `0x140024c78`
- `ADVAPI32!DeregisterEventSource` at `0x140024c78`
- `KERNEL32!GetLastError` at `0x14002474b`
- `KERNEL32!GetLastError` at `0x1400247c7`
- `KERNEL32!GetLastError` at `0x14002498d`
- `KERNEL32!GetLastError` at `0x140024a08`
- `KERNEL32!GetLastError` at `0x140024b27`
- `KERNEL32!GetLastError` at `0x140024bb1`
- `KERNEL32!GetLastError` at `0x140024ca0`
- `KERNEL32!GetLastError` at `0x14002474b`
- `KERNEL32!GetLastError` at `0x1400247c7`
- `KERNEL32!GetLastError` at `0x14002498d`
- `KERNEL32!GetLastError` at `0x140024a08`
- `KERNEL32!GetLastError` at `0x140024b27`
- `KERNEL32!GetLastError` at `0x140024bb1`
- `KERNEL32!GetLastError` at `0x140024ca0`
- `KERNEL32!WaitForSingleObject` at `0x140024b89`
- `KERNEL32!WaitForSingleObject` at `0x140024b89`
- `KERNEL32!DeleteCriticalSection` at `0x140024ce6`
- `KERNEL32!DeleteCriticalSection` at `0x140024ce6`
- `KERNEL32!SetProcessMitigationPolicy` at `0x140024720`
- `KERNEL32!SetProcessMitigationPolicy` at `0x140024720`
- `KERNEL32!SetErrorMode` at `0x140024778`
- `KERNEL32!SetErrorMode` at `0x140024789`
- `KERNEL32!SetErrorMode` at `0x140024778`
- `KERNEL32!SetErrorMode` at `0x140024789`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14002488f`
- `KERNEL32!SetUnhandledExceptionFilter` at `0x14002488f`
- `msvcrt!_wcsicmp` at `0x1400248b6`
- `msvcrt!_wcsicmp` at `0x1400248f4`
- `msvcrt!_wcsicmp` at `0x1400248b6`
- `msvcrt!_wcsicmp` at `0x1400248f4`

## string_xrefs

- `0x1400249c3`: `Software\Microsoft\Fax\Client\ServiceStartup`
- `0x140024ae3`: `RPCReady`
- `0x140024af1`: `RPCReady`

## pseudocode

```c
void __fastcall FaxServiceMain(unsigned int a1, unsigned __int16 **a2)
{
  DWORD LastError; // eax
  UINT v5; // eax
  DWORD v6; // eax
  __int64 v7; // rdx
  HKEY v8; // rax
  HKEY v9; // rbx
  unsigned int i; // ebx
  CMapDeviceId *v11; // rcx
  __int64 v12; // rdx
  DWORD v13; // eax
  HKEY v14; // rsi
  signed int v15; // eax
  unsigned int v16; // edx
  CMapDeviceId *v17; // rcx
  int v18; // edi
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int v23; // ebx
  CMapDeviceId *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  int RegistryDwordDefault; // eax
  CMapDeviceId *v28; // rcx
  DWORD v29; // eax
  DWORD v30; // eax
  int v31; // eax
  unsigned int v32; // ecx
  DWORD v33; // eax
  unsigned int j; // ebx
  unsigned int v35; // edx
  char v36; // [rsp+20h] [rbp-28h]
  int Data; // [rsp+60h] [rbp+18h] BYREF

  debugOpenLogFile();
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
  }
  Data = GetRedirectionPolicy();
  if ( !(unsigned int)SetProcessMitigationPolicy(16, &Data, 4)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, LastError);
  }
  v5 = SetErrorMode(0);
  SetErrorMode(v5 | 4);
  EncryptReceiptsPassword();
  if ( !(unsigned int)InitializeServiceGlobals() )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      v7 = 51;
LABEL_15:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v6);
      goto LABEL_86;
    }
    goto LABEL_86;
  }
  if ( !(unsigned int)InitializeFaxLibrariesGlobals() )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
    }
    goto LABEL_86;
  }
  v8 = (HKEY)OpenRegistryKey(-2147483646, L"Software\\Microsoft\\Fax", 1, 131097);
  v9 = v8;
  if ( v8 )
  {
    GetRegistryDwordEx(v8, L"UseDefaultFaultHandlingPolicy", &::Data);
    RegCloseKey(v9);
  }
  SetUnhandledExceptionFilter(FaxUnhandledExceptionFilter);
  for ( i = 1; i < a1; ++i )
  {
    if ( _wcsicmp(a2[i], L"/AlwaysRun") )
    {
      if ( _wcsicmp(a2[i], L"/DelaySuicide") )
        continue;
      g_bDelaySuicideAttempt = 1;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        continue;
      }
      v12 = 54;
    }
    else
    {
      g_bServiceCanSuicide = 0;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        continue;
      }
      v12 = 53;
    }
    WPP_SF_(*((_QWORD *)v11 + 2), v12, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
  }
  hServiceStatus = RegisterServiceCtrlHandlerW(L"Fax", FaxServiceCtrlHandler);
  if ( !hServiceStatus )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v13);
    }
    goto LABEL_86;
  }
  v14 = (HKEY)OpenRegistryKey(-2147483646, L"Software\\Microsoft\\Fax\\Client\\ServiceStartup", 1, 131103);
  if ( v14 )
  {
    v15 = UalOpenSession();
    if ( v15 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      v18 = 0;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids,
          (unsigned int)v15);
      }
    }
    else
    {
      v18 = 1;
    }
    v19 = ServiceStart((__int64)v17, v16);
    v23 = v19;
    if ( v19 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_77;
      }
      v25 = 58;
      v26 = v19;
LABEL_76:
      WPP_SF_d(*((_QWORD *)v24 + 2), v25, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v26);
LABEL_77:
      if ( v18 )
      {
        v31 = UalCloseSession();
        if ( v31 < 0
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            63,
            &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids,
            (unsigned int)v31);
        }
      }
      v32 = 1;
      if ( !v23 )
        v32 = 3;
      EndFaxSvc(v32, v20, v21, v22, v36);
      RegCloseKey(v14);
      goto LABEL_86;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
    }
    ReportServiceStatus(4u, v20, 0);
    Data = 0;
    RegistryDwordDefault = GetRegistryDwordDefault(v14, L"RPCReady", (BYTE *)&Data);
    if ( !(unsigned int)SetRegistryDword(v14, L"RPCReady", (Data & (unsigned int)-(RegistryDwordDefault != 0)) + 1) )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control )
      {
LABEL_71:
        if ( !WaitForSingleObject(g_hSCMServiceShutDownEvent, 0xFFFFFFFF)
          || WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_77;
        }
        v30 = GetLastError();
        v24 = WPP_GLOBAL_Control;
        v25 = 62;
        v26 = v30;
        goto LABEL_76;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_67:
        if ( v28 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 4) != 0 && *((_BYTE *)v28 + 25) >= 5u )
          WPP_SF_(*((_QWORD *)v28 + 2), 61, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
        goto LABEL_71;
      }
      v29 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v29);
    }
    v28 = WPP_GLOBAL_Control;
    goto LABEL_67;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = GetLastError();
    v7 = 56;
    goto LABEL_15;
  }
LABEL_86:
  FreeServiceGlobals();
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids);
  }
  if ( hEventLog )
  {
    if ( !DeregisterEventSource(hEventLog)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids, v33);
    }
    hEventLog = 0;
  }
  if ( byte_1400A78A8 )
  {
    DeleteCriticalSection(&stru_1400A7850);
    byte_1400A78A8 = 0;
  }
  for ( j = 0; j < dword_1400A787C; ++j )
    pMemFree(*((LPVOID *)gs_pFaxCategory + 2 * j));
  pMemFree(gs_pFaxCategory);
  gs_pFaxCategory = 0;
  dword_1400A787C = 0;
  HeapCleanup();
  HeapCleanup();
  ReportServiceStatus(1u, v35, 0);
}

```

## disassembly

```asm
0x1400246b0  mov     [rsp+arg_0], rbx
0x1400246b5  mov     [rsp+arg_8], rsi
0x1400246ba  push    rdi
0x1400246bb  push    r12
0x1400246bd  push    r13
0x1400246bf  push    r14
0x1400246c1  push    r15
0x1400246c3  sub     rsp, 20h
0x1400246c7  mov     r14, rdx
0x1400246ca  mov     esi, ecx
0x1400246cc  call    debugOpenLogFile
0x1400246d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400246d8  lea     r12, WPP_GLOBAL_Control
0x1400246df  mov     r15d, 4
0x1400246e5  cmp     rcx, r12
0x1400246e8  jz      short loc_14002470A
0x1400246ea  test    [rcx+1Ch], r15b
0x1400246ee  jz      short loc_14002470A
0x1400246f0  cmp     byte ptr [rcx+19h], 5
0x1400246f4  jb      short loc_14002470A
0x1400246f6  mov     rcx, [rcx+10h]
0x1400246fa  lea     edx, [r15+2Ch]
0x1400246fe  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140024705  call    WPP_SF_
0x14002470a  call    ?GetRedirectionPolicy@@YA?AU_PROCESS_MITIGATION_REDIRECTION_TRUST_POLICY@@XZ; GetRedirectionPolicy(void)
0x14002470f  mov     r8, r15
0x140024712  mov     [rsp+48h+Data], eax
0x140024716  lea     rdx, [rsp+48h+Data]
0x14002471b  mov     ecx, 10h
0x140024720  call    cs:__imp_SetProcessMitigationPolicy
0x140024727  nop     dword ptr [rax+rax+00h]
0x14002472c  mov     r13b, 2
0x14002472f  test    eax, eax
0x140024731  jnz     short loc_140024776
0x140024733  mov     rax, cs:WPP_GLOBAL_Control
0x14002473a  cmp     rax, r12
0x14002473d  jz      short loc_140024776
0x14002473f  test    [rax+1Ch], r15b
0x140024743  jz      short loc_140024776
0x140024745  cmp     [rax+19h], r13b
0x140024749  jb      short loc_140024776
0x14002474b  call    cs:__imp_GetLastError
0x140024752  nop     dword ptr [rax+rax+00h]
0x140024757  mov     rcx, cs:WPP_GLOBAL_Control
0x14002475e  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140024765  mov     edx, 2Fh ; '/'
0x14002476a  mov     r9d, eax
0x14002476d  mov     rcx, [rcx+10h]
0x140024771  call    WPP_SF_d
0x140024776  xor     ecx, ecx; uMode
0x140024778  call    cs:__imp_SetErrorMode
0x14002477f  nop     dword ptr [rax+rax+00h]
0x140024784  or      eax, r15d
0x140024787  mov     ecx, eax; uMode
0x140024789  call    cs:__imp_SetErrorMode
0x140024790  nop     dword ptr [rax+rax+00h]
0x140024795  call    ?EncryptReceiptsPassword@@YAXXZ; EncryptReceiptsPassword(void)
0x14002479a  call    InitializeServiceGlobals
0x14002479f  test    eax, eax
0x1400247a1  jnz     short loc_1400247F7
0x1400247a3  mov     rax, cs:WPP_GLOBAL_Control
0x1400247aa  cmp     rax, r12
0x1400247ad  jz      loc_140024C3A
0x1400247b3  test    [rax+1Ch], r15b
0x1400247b7  jz      loc_140024C3A
0x1400247bd  cmp     [rax+19h], r13b
0x1400247c1  jb      loc_140024C3A
0x1400247c7  call    cs:__imp_GetLastError
0x1400247ce  nop     dword ptr [rax+rax+00h]
0x1400247d3  mov     edx, 33h ; '3'
0x1400247d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400247df  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400247e6  mov     r9d, eax
0x1400247e9  mov     rcx, [rcx+10h]
0x1400247ed  call    WPP_SF_d
0x1400247f2  jmp     loc_140024C3A
0x1400247f7  call    InitializeFaxLibrariesGlobals
0x1400247fc  test    eax, eax
0x1400247fe  jnz     short loc_14002483C
0x140024800  mov     rcx, cs:WPP_GLOBAL_Control
0x140024807  cmp     rcx, r12
0x14002480a  jz      loc_140024C3A
0x140024810  test    [rcx+1Ch], r15b
0x140024814  jz      loc_140024C3A
0x14002481a  cmp     [rcx+19h], r13b
0x14002481e  jb      loc_140024C3A
0x140024824  mov     rcx, [rcx+10h]
0x140024828  lea     edx, [rax+34h]
0x14002482b  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140024832  call    WPP_SF_
0x140024837  jmp     loc_140024C3A
0x14002483c  mov     r9d, 20019h
0x140024842  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x140024849  mov     r8d, 1
0x14002484f  mov     rcx, 0FFFFFFFF80000002h
0x140024856  call    OpenRegistryKey
0x14002485b  mov     rbx, rax
0x14002485e  test    rax, rax
0x140024861  jz      short loc_140024888
0x140024863  lea     r8, Data; lpData
0x14002486a  mov     rcx, rax; hKey
0x14002486d  lea     rdx, aUsedefaultfaul; "UseDefaultFaultHandlingPolicy"
0x140024874  call    GetRegistryDwordEx
0x140024879  mov     rcx, rbx; hKey
0x14002487c  call    cs:__imp_RegCloseKey
0x140024883  nop     dword ptr [rax+rax+00h]
0x140024888  lea     rcx, ?FaxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x14002488f  call    cs:__imp_SetUnhandledExceptionFilter
0x140024896  nop     dword ptr [rax+rax+00h]
0x14002489b  mov     ebx, 1
0x1400248a0  cmp     esi, ebx
0x1400248a2  jbe     loc_140024943
0x1400248a8  movsxd  rdi, ebx
0x1400248ab  lea     rdx, aAlwaysrun; "/AlwaysRun"
0x1400248b2  mov     rcx, [r14+rdi*8]; String1
0x1400248b6  call    cs:__imp__wcsicmp
0x1400248bd  nop     dword ptr [rax+rax+00h]
0x1400248c2  test    eax, eax
0x1400248c4  jnz     short loc_1400248E9
0x1400248c6  mov     cs:?g_bServiceCanSuicide@@3HA, eax; int g_bServiceCanSuicide
0x1400248cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400248d3  cmp     rcx, r12
0x1400248d6  jz      short loc_140024939
0x1400248d8  test    [rcx+1Ch], r15b
0x1400248dc  jz      short loc_140024939
0x1400248de  cmp     byte ptr [rcx+19h], 5
0x1400248e2  jb      short loc_140024939
0x1400248e4  lea     edx, [rax+35h]
0x1400248e7  jmp     short loc_140024929
0x1400248e9  mov     rcx, [r14+rdi*8]; String1
0x1400248ed  lea     rdx, aDelaysuicide; "/DelaySuicide"
0x1400248f4  call    cs:__imp__wcsicmp
0x1400248fb  nop     dword ptr [rax+rax+00h]
0x140024900  test    eax, eax
0x140024902  jnz     short loc_140024939
0x140024904  mov     cs:?g_bDelaySuicideAttempt@@3HA, 1; int g_bDelaySuicideAttempt
0x14002490e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024915  cmp     rcx, r12
0x140024918  jz      short loc_140024939
0x14002491a  test    [rcx+1Ch], r15b
0x14002491e  jz      short loc_140024939
0x140024920  cmp     byte ptr [rcx+19h], 5
0x140024924  jb      short loc_140024939
0x140024926  lea     edx, [rax+36h]
0x140024929  mov     rcx, [rcx+10h]
0x14002492d  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140024934  call    WPP_SF_
0x140024939  inc     ebx
0x14002493b  cmp     ebx, esi
0x14002493d  jb      loc_1400248A8
0x140024943  lea     rdx, ?FaxServiceCtrlHandler@@YAXK@Z; lpHandlerProc
0x14002494a  lea     rcx, SubsystemName; "Fax"
0x140024951  call    cs:__imp_RegisterServiceCtrlHandlerW
0x140024958  nop     dword ptr [rax+rax+00h]
0x14002495d  mov     cs:hServiceStatus, rax
0x140024964  test    rax, rax
0x140024967  jnz     short loc_1400249BD
0x140024969  mov     rax, cs:WPP_GLOBAL_Control
0x140024970  cmp     rax, r12
0x140024973  jz      loc_140024C3A
0x140024979  test    [rax+1Ch], r15b
0x14002497d  jz      loc_140024C3A
0x140024983  cmp     [rax+19h], r13b
0x140024987  jb      loc_140024C3A
0x14002498d  call    cs:__imp_GetLastError
0x140024994  nop     dword ptr [rax+rax+00h]
0x140024999  mov     rcx, cs:WPP_GLOBAL_Control
0x1400249a0  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400249a7  mov     edx, 37h ; '7'
0x1400249ac  mov     r9d, eax
0x1400249af  mov     rcx, [rcx+10h]
0x1400249b3  call    WPP_SF_d
0x1400249b8  jmp     loc_140024C3A
0x1400249bd  mov     r9d, 2001Fh
0x1400249c3  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Fax\\Client\\Servi"...
0x1400249ca  mov     r8d, 1
0x1400249d0  mov     rcx, 0FFFFFFFF80000002h
0x1400249d7  call    OpenRegistryKey
0x1400249dc  mov     rsi, rax
0x1400249df  test    rax, rax
0x1400249e2  jnz     short loc_140024A1C
0x1400249e4  mov     rax, cs:WPP_GLOBAL_Control
0x1400249eb  cmp     rax, r12
0x1400249ee  jz      loc_140024C3A
0x1400249f4  test    [rax+1Ch], r15b
0x1400249f8  jz      loc_140024C3A
0x1400249fe  cmp     [rax+19h], r13b
0x140024a02  jb      loc_140024C3A
0x140024a08  call    cs:__imp_GetLastError
0x140024a0f  nop     dword ptr [rax+rax+00h]
0x140024a14  lea     edx, [rsi+38h]
0x140024a17  jmp     loc_1400247D8
0x140024a1c  call    UalOpenSession
0x140024a21  test    eax, eax
0x140024a23  js      short loc_140024A2C
0x140024a25  mov     edi, 1
0x140024a2a  jmp     short loc_140024A5C
0x140024a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024a33  xor     edi, edi
0x140024a35  cmp     rcx, r12
0x140024a38  jz      short loc_140024A5C
0x140024a3a  test    [rcx+1Ch], r15b
0x140024a3e  jz      short loc_140024A5C
0x140024a40  cmp     [rcx+19h], r13b
0x140024a44  jb      short loc_140024A5C
0x140024a46  mov     rcx, [rcx+10h]
0x140024a4a  lea     edx, [rdi+39h]
0x140024a4d  mov     r9d, eax
0x140024a50  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140024a57  call    WPP_SF_d
0x140024a5c  call    ?ServiceStart@@YAKXZ; ServiceStart(void)
0x140024a61  mov     ebx, eax
0x140024a63  test    eax, eax
0x140024a65  jz      short loc_140024A98
0x140024a67  mov     rcx, cs:WPP_GLOBAL_Control
0x140024a6e  cmp     rcx, r12
0x140024a71  jz      loc_140024BDC
0x140024a77  test    [rcx+1Ch], r15b
0x140024a7b  jz      loc_140024BDC
0x140024a81  cmp     [rcx+19h], r13b
0x140024a85  jb      loc_140024BDC
0x140024a8b  mov     edx, 3Ah ; ':'
0x140024a90  mov     r9d, eax
0x140024a93  jmp     loc_140024BCC
0x140024a98  mov     rcx, cs:WPP_GLOBAL_Control
0x140024a9f  cmp     rcx, r12
0x140024aa2  jz      short loc_140024AC5
0x140024aa4  test    [rcx+1Ch], r15b
0x140024aa8  jz      short loc_140024AC5
0x140024aaa  cmp     byte ptr [rcx+19h], 5
0x140024aae  jb      short loc_140024AC5
0x140024ab0  mov     rcx, [rcx+10h]
0x140024ab4  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140024abb  mov     edx, 3Bh ; ';'
0x140024ac0  call    WPP_SF_
0x140024ac5  xor     r8d, r8d; unsigned int
0x140024ac8  mov     ecx, r15d; unsigned int
0x140024acb  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x140024ad0  xor     r9d, r9d
0x140024ad3  mov     [rsp+48h+Data], 0
0x140024adb  lea     r8, [rsp+48h+Data]; lpData
0x140024ae0  mov     rcx, rsi; hKey
0x140024ae3  lea     rdx, aRpcready; "RPCReady"
0x140024aea  call    GetRegistryDwordDefault
0x140024aef  neg     eax
0x140024af1  lea     rdx, aRpcready; "RPCReady"
0x140024af8  mov     rcx, rsi
0x140024afb  sbb     r8d, r8d
0x140024afe  and     r8d, [rsp+48h+Data]
0x140024b03  inc     r8d
0x140024b06  call    SetRegistryDword
0x140024b0b  test    eax, eax
0x140024b0d  jnz     short loc_140024B52
0x140024b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b16  cmp     rcx, r12
0x140024b19  jz      short loc_140024B7F
0x140024b1b  test    [rcx+1Ch], r15b
0x140024b1f  jz      short loc_140024B59
0x140024b21  cmp     [rcx+19h], r13b
0x140024b25  jb      short loc_140024B59
0x140024b27  call    cs:__imp_GetLastError
0x140024b2e  nop     dword ptr [rax+rax+00h]
0x140024b33  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b3a  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140024b41  mov     edx, 3Ch ; '<'
0x140024b46  mov     r9d, eax
0x140024b49  mov     rcx, [rcx+10h]
0x140024b4d  call    WPP_SF_d
0x140024b52  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b59  cmp     rcx, r12
0x140024b5c  jz      short loc_140024B7F
0x140024b5e  test    [rcx+1Ch], r15b
0x140024b62  jz      short loc_140024B7F
0x140024b64  cmp     byte ptr [rcx+19h], 5
0x140024b68  jb      short loc_140024B7F
0x140024b6a  mov     rcx, [rcx+10h]
0x140024b6e  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140024b75  mov     edx, 3Dh ; '='
0x140024b7a  call    WPP_SF_
0x140024b7f  mov     rcx, cs:?g_hSCMServiceShutDownEvent@@3PEAXEA; hHandle
0x140024b86  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140024b89  call    cs:__imp_WaitForSingleObject
0x140024b90  nop     dword ptr [rax+rax+00h]
0x140024b95  test    eax, eax
0x140024b97  jz      short loc_140024BDC
0x140024b99  mov     rax, cs:WPP_GLOBAL_Control
0x140024ba0  cmp     rax, r12
0x140024ba3  jz      short loc_140024BDC
0x140024ba5  test    [rax+1Ch], r15b
0x140024ba9  jz      short loc_140024BDC
0x140024bab  cmp     [rax+19h], r13b
0x140024baf  jb      short loc_140024BDC
0x140024bb1  call    cs:__imp_GetLastError
0x140024bb8  nop     dword ptr [rax+rax+00h]
0x140024bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140024bc4  mov     edx, 3Eh ; '>'
0x140024bc9  mov     r9d, eax
0x140024bcc  mov     rcx, [rcx+10h]
0x140024bd0  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140024bd7  call    WPP_SF_d
  ... truncated ...
```
