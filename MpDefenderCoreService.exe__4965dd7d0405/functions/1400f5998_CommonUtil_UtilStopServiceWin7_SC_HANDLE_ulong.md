# CommonUtil::UtilStopServiceWin7(SC_HANDLE__ *,ulong)

- ea: `0x1400f5998`
- end: `0x1400f60dc`
- name: `?UtilStopServiceWin7@CommonUtil@@YAJPEAUSC_HANDLE__@@K@Z`
- size: `1860`
- prototype: `__int64 __fastcall(struct _QUERY_SERVICE_CONFIGW **this, struct SC_HANDLE__ *, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1400c49c8`

## callees

- `0x140015e60`
- `0x140016064`
- `0x1400160cc`
- `0x1400162c0`
- `0x140016e4c`
- `0x140017738`
- `0x140017990`
- `0x14003a130`
- `0x14003a5c0`
- `0x14007d210`
- `0x140085d38`
- `0x140085d94`
- `0x1400934f8`
- `0x1400bb460`
- `0x1400f5934`
- `0x1400f5998`
- `0x1400f6648`
- `0x1400f677c`
- `0x140166990`

## import_xrefs

- `KERNEL32!SleepEx` at `0x1400f5dea`
- `KERNEL32!SleepEx` at `0x1400f5dea`
- `KERNEL32!Sleep` at `0x1400f5dd7`
- `KERNEL32!Sleep` at `0x1400f5dd7`
- `ADVAPI32!NotifyServiceStatusChangeW` at `0x1400f5b9d`
- `ADVAPI32!NotifyServiceStatusChangeW` at `0x1400f5b9d`
- `ADVAPI32!GetServiceKeyNameW` at `0x1400f5abf`
- `ADVAPI32!GetServiceKeyNameW` at `0x1400f5abf`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f5c13`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f5d12`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f5e74`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f5efa`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f5f82`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f6007`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f5c13`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f5d12`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f5e74`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f5efa`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f5f82`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f6007`
- `ADVAPI32!CloseServiceHandle` at `0x1400f5ae2`
- `ADVAPI32!CloseServiceHandle` at `0x1400f6099`
- `ADVAPI32!CloseServiceHandle` at `0x1400f60a8`
- `ADVAPI32!CloseServiceHandle` at `0x1400f5ae2`
- `ADVAPI32!CloseServiceHandle` at `0x1400f6099`
- `ADVAPI32!CloseServiceHandle` at `0x1400f60a8`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilStopServiceWin7(struct _QUERY_SERVICE_CONFIGW **this, struct SC_HANDLE__ *a2)
{
  __int64 v2; // rsi
  char v4; // r15
  int v5; // eax
  struct SC_HANDLE__ *v6; // r8
  signed int ServiceConfig; // ebx
  CommonUtil *v8; // rcx
  struct SC_HANDLE__ *v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rdx
  struct SC_HANDLE__ **v12; // rbx
  unsigned __int64 v13; // r13
  LPWSTR v14; // r14
  signed int v15; // eax
  unsigned int v16; // edx
  struct _SERVICE_STATUS *v17; // r9
  __int64 v18; // rcx
  const wchar_t *v19; // rbx
  int v20; // eax
  LPWSTR lpDisplayName; // rax
  unsigned __int64 SystemTimeAsUlong64; // rax
  char v23; // r15
  unsigned __int64 v24; // r8
  DWORD v25; // ecx
  int v26; // r8d
  unsigned int v27; // edx
  unsigned int v28; // eax
  const wchar_t *v30; // [rsp+20h] [rbp-E0h]
  unsigned int v31; // [rsp+20h] [rbp-E0h]
  char v32; // [rsp+60h] [rbp-A0h]
  char v33; // [rsp+61h] [rbp-9Fh]
  _SERVICE_STATUS ServiceStatus; // [rsp+68h] [rbp-98h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+90h] [rbp-70h] BYREF
  DWORD pcbBytesNeeded; // [rsp+E0h] [rbp-20h] BYREF
  DWORD cchBuffer; // [rsp+E4h] [rbp-1Ch] BYREF
  SC_HANDLE hSCObject; // [rsp+E8h] [rbp-18h] BYREF
  SC_HANDLE hSCManager; // [rsp+F0h] [rbp-10h] BYREF
  void *v40; // [rsp+F8h] [rbp-8h] BYREF
  struct _QUERY_SERVICE_CONFIGW ServiceName[8]; // [rsp+100h] [rbp+0h] BYREF

  v2 = (unsigned int)a2;
  pcbBytesNeeded = (unsigned int)a2;
  memset(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  v33 = 0;
  v32 = 0;
  hSCManager = 0;
  v4 = 0;
  hSCObject = 0;
  v5 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCManager, (struct SC_HANDLE__ **)0x80000000LL, 0, 0, v30);
  ServiceConfig = v5;
  if ( v5 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        17,
        &WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids,
        (unsigned int)v5);
    goto LABEL_94;
  }
  v40 = 0;
  ServiceConfig = CommonUtil::UtilQueryServiceConfig((CommonUtil *)&v40, this, v6);
  if ( ServiceConfig < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v11 = 18;
LABEL_91:
      WPP_SF_d(
        *(_QWORD *)(v10 + 16),
        v11,
        &WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids,
        (unsigned int)ServiceConfig);
      goto LABEL_92;
    }
    goto LABEL_92;
  }
  if ( (*(_BYTE *)v40 & 2) != 0 || (*(_BYTE *)v40 & 1) != 0 )
  {
    v4 = 1;
    v33 = 1;
LABEL_21:
    if ( (_DWORD)v2 == -1 )
      v13 = -1;
    else
      v13 = CommonUtil::UtilGetSystemTimeAsUlong64(v8) + 10000 * v2;
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    v14 = (LPWSTR)L"<unknown>";
    while ( 1 )
    {
      if ( !v4 )
      {
        v15 = NotifyServiceStatusChangeW(hSCObject, 9u, &pNotifyBuffer);
        ServiceConfig = v15;
        if ( v15 )
        {
          if ( v15 > 0 )
            ServiceConfig = (unsigned __int16)v15 | 0x80070000;
          goto LABEL_92;
        }
      }
      ServiceConfig = CommonUtil::HrQueryServiceStatus(&ServiceStatus, (SC_HANDLE)this, v9);
      if ( ServiceConfig < 0 )
        break;
      v18 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v19 = CommonUtil::ServiceStateToString((CommonUtil *)ServiceStatus.dwCurrentState, v16);
        memset(ServiceName, 0, sizeof(ServiceName));
        cchBuffer = 0;
        if ( !QueryServiceConfigW((SC_HANDLE)this, ServiceName, 0x200u, &cchBuffer) )
        {
          HrGetLastFailure();
          ServiceName[0].lpDisplayName = (LPWSTR)L"<unknown>";
        }
        WPP_SF_SLSLLLLL(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          ServiceStatus.dwServiceType,
          (__int64)v19,
          ServiceStatus.dwControlsAccepted,
          ServiceStatus.dwWin32ExitCode,
          ServiceStatus.dwServiceSpecificExitCode,
          ServiceStatus.dwCheckPoint,
          ServiceStatus.dwWaitHint);
        v18 = WPP_GLOBAL_Control;
      }
      if ( ServiceStatus.dwCurrentState == 4 )
      {
        if ( (ServiceStatus.dwControlsAccepted & 1) == 0 )
        {
          ServiceConfig = -2147019873;
          if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control && (*(_BYTE *)(v18 + 28) & 1) != 0 )
          {
            memset(ServiceName, 0, sizeof(ServiceName));
            pcbBytesNeeded = 0;
            if ( QueryServiceConfigW((SC_HANDLE)this, ServiceName, 0x200u, &pcbBytesNeeded) )
            {
              LODWORD(v14) = ServiceName[0].lpDisplayName;
            }
            else
            {
              HrGetLastFailure();
              ServiceName[0].lpDisplayName = (LPWSTR)L"<unknown>";
            }
            WPP_SF_Sd(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              22,
              (unsigned int)&WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids,
              (_DWORD)v14,
              ServiceStatus.dwControlsAccepted);
          }
          goto LABEL_92;
        }
        v20 = CommonUtil::HrControlService((SC_HANDLE)this, (struct SC_HANDLE__ *)1, &ServiceStatus, v17);
        v32 = 1;
        ServiceConfig = v20;
        if ( v20 < 0 )
        {
          v18 = (unsigned int)(v20 + 2147023835);
          if ( (unsigned int)v18 > 1 && v20 != -2147023781 )
            goto LABEL_92;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            memset(ServiceName, 0, sizeof(ServiceName));
            cchBuffer = 0;
            if ( QueryServiceConfigW((SC_HANDLE)this, ServiceName, 0x200u, &cchBuffer) )
            {
              lpDisplayName = ServiceName[0].lpDisplayName;
            }
            else
            {
              HrGetLastFailure();
              lpDisplayName = (LPWSTR)L"<unknown>";
              ServiceName[0].lpDisplayName = (LPWSTR)L"<unknown>";
            }
            WPP_SF_dS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), (__int64)lpDisplayName);
          }
        }
      }
      else
      {
        if ( ServiceStatus.dwCurrentState == 1 )
        {
          ServiceConfig = 0;
          goto LABEL_92;
        }
        if ( ServiceStatus.dwCurrentState - 2 > 1 )
        {
          ServiceConfig = -2147019873;
          if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control && (*(_BYTE *)(v18 + 28) & 1) != 0 )
          {
            memset(ServiceName, 0, sizeof(ServiceName));
            pcbBytesNeeded = 0;
            if ( QueryServiceConfigW((SC_HANDLE)this, ServiceName, 0x200u, &pcbBytesNeeded) )
            {
              v14 = ServiceName[0].lpDisplayName;
            }
            else
            {
              HrGetLastFailure();
              ServiceName[0].lpDisplayName = (LPWSTR)L"<unknown>";
            }
            v28 = (unsigned int)CommonUtil::ServiceStateToString((CommonUtil *)ServiceStatus.dwCurrentState, v27);
            WPP_SF_SS(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              25,
              (unsigned int)&WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids,
              v28,
              (__int64)v14);
          }
          goto LABEL_92;
        }
        if ( v4 && v32 && ServiceStatus.dwCurrentState == 2 )
        {
          ServiceConfig = -2147019873;
          if ( (_UNKNOWN *)v18 != &WPP_GLOBAL_Control && (*(_BYTE *)(v18 + 28) & 2) != 0 )
          {
            memset(ServiceName, 0, sizeof(ServiceName));
            pcbBytesNeeded = 0;
            if ( QueryServiceConfigW((SC_HANDLE)this, ServiceName, 0x200u, &pcbBytesNeeded) )
            {
              v14 = ServiceName[0].lpDisplayName;
            }
            else
            {
              HrGetLastFailure();
              ServiceName[0].lpDisplayName = (LPWSTR)L"<unknown>";
            }
            WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, &WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids, v14);
          }
          goto LABEL_92;
        }
      }
      if ( pcbBytesNeeded == -1 )
      {
        LODWORD(v24) = -1;
      }
      else
      {
        SystemTimeAsUlong64 = CommonUtil::UtilGetSystemTimeAsUlong64((CommonUtil *)v18);
        v23 = SystemTimeAsUlong64;
        if ( SystemTimeAsUlong64 > v13 )
        {
          ServiceConfig = -2147023436;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            _mm_lfence();
            memset(ServiceName, 0, sizeof(ServiceName));
            pcbBytesNeeded = 0;
            if ( QueryServiceConfigW((SC_HANDLE)this, ServiceName, 0x200u, &pcbBytesNeeded) )
            {
              LODWORD(v14) = ServiceName[0].lpDisplayName;
            }
            else
            {
              HrGetLastFailure();
              ServiceName[0].lpDisplayName = (LPWSTR)L"<unknown>";
            }
            WPP_SF_Siid(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 26, v26, (_DWORD)v14, v23, v13, 180);
          }
          goto LABEL_92;
        }
        v4 = v33;
        v24 = (v13 - SystemTimeAsUlong64 + 9999) / 0x2710;
      }
      if ( v4 )
      {
        v25 = 250;
        if ( (unsigned int)v24 <= 0xF9 )
          v25 = v24;
        Sleep(v25);
      }
      else if ( !SleepEx(v24, 1) )
      {
        v10 = WPP_GLOBAL_Control;
        ServiceConfig = -2147023436;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v11 = 27;
          goto LABEL_91;
        }
        goto LABEL_92;
      }
    }
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v11 = 20;
      goto LABEL_91;
    }
    goto LABEL_92;
  }
  cchBuffer = 260;
  if ( !GetServiceKeyNameW(hSCManager, *((LPCWSTR *)v40 + 7), (LPWSTR)ServiceName, &cchBuffer) )
  {
    ServiceConfig = HrGetLastFailure();
    goto LABEL_92;
  }
  v12 = (struct SC_HANDLE__ **)hSCManager;
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  ServiceConfig = CommonUtil::HrOpenService(
                    (CommonUtil *)&hSCObject,
                    v12,
                    (struct SC_HANDLE__ *)ServiceName,
                    (const wchar_t *)4,
                    v31);
  if ( ServiceConfig >= 0 )
  {
    pNotifyBuffer.dwVersion = 2;
    pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)Microsoft::Applications::Events::NullLogManager::SetLevelFilter;
    pNotifyBuffer.pContext = 0;
    goto LABEL_21;
  }
  v10 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v11 = 19;
    goto LABEL_91;
  }
LABEL_92:
  if ( v40 )
    operator delete(v40, (const struct std::nothrow_t *)0x40);
LABEL_94:
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  if ( hSCManager )
    CloseServiceHandle(hSCManager);
  return (unsigned int)ServiceConfig;
}

```

## disassembly

```asm
0x1400f5998  mov     [rsp-8+arg_10], rbx
0x1400f599d  mov     [rsp-8+arg_18], rsi
0x1400f59a2  push    rbp
0x1400f59a3  push    r12
0x1400f59a5  push    r13
0x1400f59a7  push    r14
0x1400f59a9  push    r15
0x1400f59ab  lea     rbp, [rsp-220h]
0x1400f59b3  sub     rsp, 320h
0x1400f59ba  mov     rax, cs:__security_cookie
0x1400f59c1  xor     rax, rsp
0x1400f59c4  mov     [rbp+240h+var_30], rax
0x1400f59cb  mov     esi, edx
0x1400f59cd  mov     r12, rcx
0x1400f59d0  xor     edx, edx; Val
0x1400f59d2  mov     [rbp+240h+pcbBytesNeeded], esi
0x1400f59d5  lea     rcx, [rbp+240h+pNotifyBuffer]; void *
0x1400f59d9  lea     r8d, [rdx+50h]; Size
0x1400f59dd  call    memset
0x1400f59e2  xor     r14d, r14d
0x1400f59e5  lea     rcx, [rbp+240h+hSCManager]; this
0x1400f59e9  xor     r9d, r9d; wchar_t *
0x1400f59ec  mov     [rsp+340h+var_2DF], r14b
0x1400f59f1  xor     r8d, r8d; unsigned int
0x1400f59f4  mov     [rsp+340h+var_2E0], r14b
0x1400f59f9  mov     edx, 80000000h; struct SC_HANDLE__ **
0x1400f59fe  mov     [rbp+240h+hSCManager], r14
0x1400f5a02  mov     r15b, r14b
0x1400f5a05  mov     [rbp+240h+hSCObject], r14
0x1400f5a09  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEB_W1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,wchar_t const *,wchar_t const *)
0x1400f5a0e  mov     ebx, eax
0x1400f5a10  test    eax, eax
0x1400f5a12  jns     short loc_1400F5A51
0x1400f5a14  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f5a1b  lea     rsi, WPP_GLOBAL_Control
0x1400f5a22  cmp     rcx, rsi
0x1400f5a25  jz      loc_1400F6090
0x1400f5a2b  test    byte ptr [rcx+1Ch], 1
0x1400f5a2f  jz      loc_1400F6090
0x1400f5a35  mov     rcx, [rcx+10h]
0x1400f5a39  lea     edx, [r14+11h]
0x1400f5a3d  mov     r9d, eax
0x1400f5a40  lea     r8, WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids
0x1400f5a47  call    WPP_SF_d
0x1400f5a4c  jmp     loc_1400F6090
0x1400f5a51  mov     rdx, r12; struct _QUERY_SERVICE_CONFIGW **
0x1400f5a54  mov     [rbp+240h+var_248], r14
0x1400f5a58  lea     rcx, [rbp+240h+var_248]; this
0x1400f5a5c  call    ?UtilQueryServiceConfig@CommonUtil@@YAJPEAPEAU_QUERY_SERVICE_CONFIGW@@PEAUSC_HANDLE__@@@Z; CommonUtil::UtilQueryServiceConfig(_QUERY_SERVICE_CONFIGW * *,SC_HANDLE__ *)
0x1400f5a61  mov     ebx, eax
0x1400f5a63  test    eax, eax
0x1400f5a65  jns     short loc_1400F5A92
0x1400f5a67  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f5a6e  lea     rsi, WPP_GLOBAL_Control
0x1400f5a75  cmp     rcx, rsi
0x1400f5a78  jz      loc_1400F607D
0x1400f5a7e  test    byte ptr [rcx+1Ch], 1
0x1400f5a82  jz      loc_1400F607D
0x1400f5a88  mov     edx, 12h
0x1400f5a8d  jmp     loc_1400F606A
0x1400f5a92  mov     rdx, [rbp+240h+var_248]
0x1400f5a96  test    byte ptr [rdx], 2
0x1400f5a99  jnz     loc_1400F5B47
0x1400f5a9f  test    byte ptr [rdx], 1
0x1400f5aa2  jnz     loc_1400F5B47
0x1400f5aa8  mov     rcx, [rbp+240h+hSCManager]; hSCManager
0x1400f5aac  lea     r9, [rbp+240h+cchBuffer]; lpcchBuffer
0x1400f5ab0  mov     [rbp+240h+cchBuffer], 104h
0x1400f5ab7  lea     r8, [rbp+240h+ServiceName]; lpServiceName
0x1400f5abb  mov     rdx, [rdx+38h]; lpDisplayName
0x1400f5abf  call    cs:__imp_GetServiceKeyNameW
0x1400f5ac5  test    eax, eax
0x1400f5ac7  jnz     short loc_1400F5AD5
0x1400f5ac9  call    HrGetLastFailure
0x1400f5ace  mov     ebx, eax
0x1400f5ad0  jmp     loc_1400F607D
0x1400f5ad5  mov     rcx, [rbp+240h+hSCObject]; hSCObject
0x1400f5ad9  mov     rbx, [rbp+240h+hSCManager]
0x1400f5add  test    rcx, rcx
0x1400f5ae0  jz      short loc_1400F5AE8
0x1400f5ae2  call    cs:__imp_CloseServiceHandle
0x1400f5ae8  mov     r9d, 4; wchar_t *
0x1400f5aee  lea     r8, [rbp+240h+ServiceName]; struct SC_HANDLE__ *
0x1400f5af2  mov     rdx, rbx; struct SC_HANDLE__ **
0x1400f5af5  lea     rcx, [rbp+240h+hSCObject]; this
0x1400f5af9  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEB_WK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,wchar_t const *,ulong)
0x1400f5afe  mov     ebx, eax
0x1400f5b00  test    eax, eax
0x1400f5b02  jns     short loc_1400F5B2F
0x1400f5b04  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f5b0b  lea     rsi, WPP_GLOBAL_Control
0x1400f5b12  cmp     rcx, rsi
0x1400f5b15  jz      loc_1400F607D
0x1400f5b1b  test    byte ptr [rcx+1Ch], 1
0x1400f5b1f  jz      loc_1400F607D
0x1400f5b25  mov     edx, 13h
0x1400f5b2a  jmp     loc_1400F606A
0x1400f5b2f  lea     rax, ?SetLevelFilter@NullLogManager@Events@Applications@Microsoft@@UEAAXEAEBV?$set@EU?$less@E@std@@V?$allocator@E@2@@std@@@Z; Microsoft::Applications::Events::NullLogManager::SetLevelFilter(uchar,std::set<uchar> const &)
0x1400f5b36  mov     [rbp+240h+pNotifyBuffer.dwVersion], 2
0x1400f5b3d  mov     [rbp+240h+pNotifyBuffer.pfnNotifyCallback], rax
0x1400f5b41  mov     [rbp+240h+pNotifyBuffer.pContext], r14
0x1400f5b45  jmp     short loc_1400F5B4F
0x1400f5b47  mov     r15b, 1
0x1400f5b4a  mov     [rsp+340h+var_2DF], r15b
0x1400f5b4f  or      ebx, 0FFFFFFFFh
0x1400f5b52  cmp     esi, ebx
0x1400f5b54  jnz     short loc_1400F5B5C
0x1400f5b56  or      r13, 0FFFFFFFFFFFFFFFFh
0x1400f5b5a  jmp     short loc_1400F5B6B
0x1400f5b5c  call    ?UtilGetSystemTimeAsUlong64@CommonUtil@@YA_KXZ; CommonUtil::UtilGetSystemTimeAsUlong64(void)
0x1400f5b61  imul    r13, rsi, 2710h
0x1400f5b68  add     r13, rax
0x1400f5b6b  xor     eax, eax
0x1400f5b6d  lea     rsi, WPP_GLOBAL_Control
0x1400f5b74  xorps   xmm0, xmm0
0x1400f5b77  mov     qword ptr [rsp+340h+ServiceStatus.dwServiceSpecificExitCode], rax
0x1400f5b7c  movups  xmmword ptr [rsp+340h+ServiceStatus.dwServiceType], xmm0
0x1400f5b81  mov     [rbp+240h+ServiceStatus.dwWaitHint], eax
0x1400f5b84  lea     r14, aUnknown_1; "<unknown>"
0x1400f5b8b  test    r15b, r15b
0x1400f5b8e  jnz     short loc_1400F5BAD
0x1400f5b90  mov     rcx, [rbp+240h+hSCObject]; hService
0x1400f5b94  lea     r8, [rbp+240h+pNotifyBuffer]; pNotifyBuffer
0x1400f5b98  mov     edx, 9; dwNotifyMask
0x1400f5b9d  call    cs:__imp_NotifyServiceStatusChangeW
0x1400f5ba3  mov     ebx, eax
0x1400f5ba5  test    eax, eax
0x1400f5ba7  jnz     loc_1400F5E1F
0x1400f5bad  mov     rdx, r12; hService
0x1400f5bb0  lea     rcx, [rsp+340h+ServiceStatus]; lpServiceStatus
0x1400f5bb5  call    ?HrQueryServiceStatus@CommonUtil@@YAJPEAU_SERVICE_STATUS@@PEAUSC_HANDLE__@@@Z; CommonUtil::HrQueryServiceStatus(_SERVICE_STATUS *,SC_HANDLE__ *)
0x1400f5bba  mov     ebx, eax
0x1400f5bbc  test    eax, eax
0x1400f5bbe  js      loc_1400F6053
0x1400f5bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f5bcb  cmp     rcx, rsi
0x1400f5bce  jz      loc_1400F5C7F
0x1400f5bd4  test    byte ptr [rcx+1Ch], 4
0x1400f5bd8  jz      loc_1400F5C7F
0x1400f5bde  mov     ecx, [rsp+340h+ServiceStatus.dwCurrentState]; this
0x1400f5be2  call    ?ServiceStateToString@CommonUtil@@YAPEB_WK@Z; CommonUtil::ServiceStateToString(ulong)
0x1400f5be7  xor     edx, edx; Val
0x1400f5be9  lea     rcx, [rbp+240h+ServiceName]; void *
0x1400f5bed  mov     r8d, 200h; Size
0x1400f5bf3  mov     rbx, rax
0x1400f5bf6  call    memset
0x1400f5bfb  lea     r9, [rbp+240h+cchBuffer]; pcbBytesNeeded
0x1400f5bff  mov     [rbp+240h+cchBuffer], 0
0x1400f5c06  mov     r8d, 200h; cbBufSize
0x1400f5c0c  lea     rdx, [rbp+240h+ServiceName]; lpServiceConfig
0x1400f5c10  mov     rcx, r12; hService
0x1400f5c13  call    cs:__imp_QueryServiceConfigW
0x1400f5c19  test    eax, eax
0x1400f5c1b  jnz     short loc_1400F5C2B
0x1400f5c1d  call    HrGetLastFailure
0x1400f5c22  mov     r9, r14
0x1400f5c25  mov     [rbp+240h+var_208], r14
0x1400f5c29  jmp     short loc_1400F5C2F
0x1400f5c2b  mov     r9, [rbp+240h+var_208]
0x1400f5c2f  mov     eax, [rbp+240h+ServiceStatus.dwWaitHint]
0x1400f5c32  mov     edx, 15h
0x1400f5c37  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f5c3e  mov     dword ptr [rsp+340h+var_2F0], eax; char
0x1400f5c42  mov     eax, [rsp+340h+ServiceStatus.dwCheckPoint]
0x1400f5c46  mov     dword ptr [rsp+340h+var_2F8], eax; char
0x1400f5c4a  mov     eax, [rsp+340h+ServiceStatus.dwServiceSpecificExitCode]
0x1400f5c4e  mov     rcx, [rcx+10h]; LoggerHandle
0x1400f5c52  mov     dword ptr [rsp+340h+var_300], eax; char
0x1400f5c56  mov     eax, [rsp+340h+ServiceStatus.dwWin32ExitCode]
0x1400f5c5a  mov     dword ptr [rsp+340h+var_308], eax; char
0x1400f5c5e  mov     eax, [rsp+340h+ServiceStatus.dwControlsAccepted]
0x1400f5c62  mov     dword ptr [rsp+340h+var_310], eax; char
0x1400f5c66  mov     eax, [rsp+340h+ServiceStatus.dwServiceType]
0x1400f5c6a  mov     [rsp+340h+var_318], rbx; __int64
0x1400f5c6f  mov     dword ptr [rsp+340h+var_320], eax; char
0x1400f5c73  call    WPP_SF_SLSLLLLL
0x1400f5c78  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1400f5c7f  mov     edx, [rsp+340h+ServiceStatus.dwCurrentState]
0x1400f5c83  cmp     edx, 4
0x1400f5c86  jnz     loc_1400F5D54
0x1400f5c8c  mov     eax, [rsp+340h+ServiceStatus.dwControlsAccepted]
0x1400f5c90  test    al, 1
0x1400f5c92  jz      loc_1400F5E33
0x1400f5c98  lea     r8, [rsp+340h+ServiceStatus]; lpServiceStatus
0x1400f5c9d  mov     edx, 1; this
0x1400f5ca2  mov     rcx, r12; hService
0x1400f5ca5  call    ?HrControlService@CommonUtil@@YAJPEAUSC_HANDLE__@@KPEAU_SERVICE_STATUS@@@Z; CommonUtil::HrControlService(SC_HANDLE__ *,ulong,_SERVICE_STATUS *)
0x1400f5caa  mov     [rsp+340h+var_2E0], 1
0x1400f5caf  mov     ebx, eax
0x1400f5cb1  test    eax, eax
0x1400f5cb3  jns     loc_1400F5D7E
0x1400f5cb9  lea     ecx, [rax+7FF8FBDBh]
0x1400f5cbf  cmp     ecx, 1
0x1400f5cc2  jbe     short loc_1400F5CCF
0x1400f5cc4  cmp     eax, 8007045Bh
0x1400f5cc9  jnz     loc_1400F607D
0x1400f5ccf  mov     rax, cs:WPP_GLOBAL_Control
0x1400f5cd6  cmp     rax, rsi
0x1400f5cd9  jz      loc_1400F5D7E
0x1400f5cdf  test    byte ptr [rax+1Ch], 2
0x1400f5ce3  jz      loc_1400F5D7E
0x1400f5ce9  xor     edx, edx; Val
0x1400f5ceb  lea     rcx, [rbp+240h+ServiceName]; void *
0x1400f5cef  mov     r8d, 200h; Size
0x1400f5cf5  call    memset
0x1400f5cfa  lea     r9, [rbp+240h+cchBuffer]; pcbBytesNeeded
0x1400f5cfe  mov     [rbp+240h+cchBuffer], 0
0x1400f5d05  mov     r8d, 200h; cbBufSize
0x1400f5d0b  lea     rdx, [rbp+240h+ServiceName]; lpServiceConfig
0x1400f5d0f  mov     rcx, r12; hService
0x1400f5d12  call    cs:__imp_QueryServiceConfigW
0x1400f5d18  test    eax, eax
0x1400f5d1a  jnz     short loc_1400F5D2A
0x1400f5d1c  call    HrGetLastFailure
0x1400f5d21  mov     rax, r14
0x1400f5d24  mov     [rbp+240h+var_208], rax
0x1400f5d28  jmp     short loc_1400F5D2E
0x1400f5d2a  mov     rax, [rbp+240h+var_208]
0x1400f5d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f5d35  lea     r8, WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids
0x1400f5d3c  mov     edx, 17h
0x1400f5d41  mov     qword ptr [rsp+340h+var_320], rax; __int64
0x1400f5d46  mov     r9d, ebx
0x1400f5d49  mov     rcx, [rcx+10h]; LoggerHandle
0x1400f5d4d  call    WPP_SF_dS
0x1400f5d52  jmp     short loc_1400F5D7E
0x1400f5d54  cmp     edx, 1
0x1400f5d57  jz      loc_1400F604F
0x1400f5d5d  lea     eax, [rdx-2]
0x1400f5d60  cmp     eax, 1
0x1400f5d63  ja      loc_1400F5FC6
0x1400f5d69  test    r15b, r15b
0x1400f5d6c  jz      short loc_1400F5D7E
0x1400f5d6e  cmp     [rsp+340h+var_2E0], 0
0x1400f5d73  jz      short loc_1400F5D7E
0x1400f5d75  cmp     edx, 2
0x1400f5d78  jz      loc_1400F5EB9
0x1400f5d7e  or      ebx, 0FFFFFFFFh
0x1400f5d81  cmp     [rbp+240h+pcbBytesNeeded], ebx
0x1400f5d84  jz      short loc_1400F5DBF
0x1400f5d86  call    ?UtilGetSystemTimeAsUlong64@CommonUtil@@YA_KXZ; CommonUtil::UtilGetSystemTimeAsUlong64(void)
0x1400f5d8b  mov     r15, rax
0x1400f5d8e  cmp     rax, r13
0x1400f5d91  ja      loc_1400F5F37
0x1400f5d97  mov     r15b, [rsp+340h+var_2DF]
0x1400f5d9c  mov     rcx, r13
0x1400f5d9f  sub     rcx, rax
0x1400f5da2  mov     rax, 346DC5D63886594Bh
0x1400f5dac  add     rcx, 270Fh
0x1400f5db3  mul     rcx
0x1400f5db6  mov     r8, rdx
0x1400f5db9  shr     r8, 0Bh
0x1400f5dbd  jmp     short loc_1400F5DC2
0x1400f5dbf  mov     r8d, ebx
0x1400f5dc2  test    r15b, r15b
0x1400f5dc5  jz      short loc_1400F5DE2
0x1400f5dc7  cmp     r8d, 0F9h
0x1400f5dce  mov     ecx, 0FAh
0x1400f5dd3  cmovbe  ecx, r8d; dwMilliseconds
0x1400f5dd7  call    cs:__imp_Sleep
0x1400f5ddd  jmp     loc_1400F5B8B
0x1400f5de2  mov     edx, 1; bAlertable
0x1400f5de7  mov     ecx, r8d; dwMilliseconds
0x1400f5dea  call    cs:__imp_SleepEx
0x1400f5df0  test    eax, eax
0x1400f5df2  jnz     loc_1400F5B8B
0x1400f5df8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f5dff  mov     ebx, 800705B4h
0x1400f5e04  cmp     rcx, rsi
0x1400f5e07  jz      loc_1400F607D
0x1400f5e0d  test    byte ptr [rcx+1Ch], 1
0x1400f5e11  jz      loc_1400F607D
0x1400f5e17  lea     edx, [rax+1Bh]
0x1400f5e1a  jmp     loc_1400F606A
0x1400f5e1f  jle     loc_1400F607D
0x1400f5e25  movzx   ebx, ax
0x1400f5e28  or      ebx, 80070000h
0x1400f5e2e  jmp     loc_1400F607D
0x1400f5e33  mov     ebx, 8007139Fh
0x1400f5e38  cmp     rcx, rsi
0x1400f5e3b  jz      loc_1400F607D
0x1400f5e41  test    byte ptr [rcx+1Ch], 1
0x1400f5e45  jz      loc_1400F607D
0x1400f5e4b  xor     edx, edx; Val
0x1400f5e4d  lea     rcx, [rbp+240h+ServiceName]; void *
0x1400f5e51  mov     r8d, 200h; Size
0x1400f5e57  call    memset
0x1400f5e5c  lea     r9, [rbp+240h+pcbBytesNeeded]; pcbBytesNeeded
0x1400f5e60  mov     [rbp+240h+pcbBytesNeeded], 0
0x1400f5e67  mov     r8d, 200h; cbBufSize
0x1400f5e6d  lea     rdx, [rbp+240h+ServiceName]; lpServiceConfig
0x1400f5e71  mov     rcx, r12; hService
0x1400f5e74  call    cs:__imp_QueryServiceConfigW
0x1400f5e7a  test    eax, eax
0x1400f5e7c  jnz     short loc_1400F5E89
0x1400f5e7e  call    HrGetLastFailure
0x1400f5e83  mov     [rbp+240h+var_208], r14
0x1400f5e87  jmp     short loc_1400F5E8D
0x1400f5e89  mov     r14, [rbp+240h+var_208]
0x1400f5e8d  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
