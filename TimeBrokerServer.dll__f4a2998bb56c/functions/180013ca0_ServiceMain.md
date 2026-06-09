# ServiceMain

- ea: `0x180013ca0`
- end: `0x180013e94`
- name: `ServiceMain`
- size: `500`
- prototype: `void __fastcall(__int64, LPCWSTR *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000bba0`
- `0x18000bbf0`
- `0x180011ea8`
- `0x180012dd0`
- `0x180013b40`
- `0x180013c40`
- `0x180013ca0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180013da3`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x180013da3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013d57`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013d57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d39`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180013d22`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180013d22`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, LPCWSTR *a2)
{
  char v3; // si
  int v4; // edi
  unsigned int LastError; // ebx
  int v6; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v7; // [rsp+44h] [rbp-35h] BYREF
  GUID SettingGuid; // [rsp+48h] [rbp-31h] BYREF
  char v9[32]; // [rsp+60h] [rbp-19h] BYREF
  unsigned int *v10; // [rsp+80h] [rbp+7h]
  __int64 v11; // [rsp+88h] [rbp+Fh]
  int *v12; // [rsp+90h] [rbp+17h]
  __int64 v13; // [rsp+98h] [rbp+1Fh]

  v3 = 1;
  SettingGuid = GUID_LOW_POWER_EPOCH;
  if ( (unsigned int)dword_180026058 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      a1,
      &byte_1800204EF);
  g_ServiceStatus.dwServiceType = 32;
  *(_QWORD *)&g_ServiceStatus.dwWin32ExitCode = 0;
  *(_QWORD *)&g_ServiceStatus.dwCurrentState = 2;
  g_ServiceStatus.dwCheckPoint = 0;
  g_ServiceHandle = RegisterServiceCtrlHandlerExW(*a2, TimeBrokerServiceCtrlHandler, 0);
  if ( !g_ServiceHandle )
  {
    v4 = 4096;
LABEL_5:
    LastError = GetLastError();
    goto LABEL_15;
  }
  UpdateState(2u);
  g_hStopEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_hStopEvent )
  {
    v4 = 0x2000;
    goto LABEL_5;
  }
  LastError = TimeBrokerInitialize();
  if ( LastError )
  {
    v4 = 12288;
  }
  else
  {
    g_ServiceStatus.dwControlsAccepted |= 0x241u;
    LastError = PowerSettingRegisterNotification(&SettingGuid, 1u, g_ServiceHandle, &g_hPowerHandle);
    if ( LastError )
    {
      v4 = 0x4000;
    }
    else
    {
      LastError = (*((__int64 (__fastcall **)(void **, LPCWSTR, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_pSvchostGlobals
                   + 26))(
                    &g_hWaitHandle,
                    *a2,
                    g_hStopEvent,
                    TimeBrokerStopCallback,
                    0,
                    24);
      if ( LastError )
      {
        v4 = 20480;
      }
      else
      {
        UpdateState(4u);
        v3 = 0;
        v4 = 0;
        LastError = 0;
      }
    }
  }
LABEL_15:
  if ( (unsigned int)dword_180026058 > 5 )
  {
    v6 = v4;
    v12 = &v6;
    v7 = LastError;
    v10 = &v7;
    v13 = 4;
    v11 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180026058, byte_180020481, 0, 0, 4, v9);
  }
  if ( v3 )
    ServiceCleanup(LastError, 0x42Au);
}

```

## disassembly

```asm
0x180013ca0  push    rbp
0x180013ca2  push    rbx
0x180013ca3  push    rsi
0x180013ca4  push    rdi
0x180013ca5  lea     rbp, [rsp-3Fh]
0x180013caa  sub     rsp, 0B8h
0x180013cb1  mov     rax, cs:__security_cookie
0x180013cb8  xor     rax, rsp
0x180013cbb  mov     [rbp+57h+var_30], rax
0x180013cbf  movups  xmm0, xmmword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x180013cc6  mov     eax, cs:dword_180026058
0x180013ccc  mov     rdi, rdx
0x180013ccf  mov     esi, 1
0x180013cd4  movdqu  xmmword ptr [rbp+57h+SettingGuid.Data1], xmm0
0x180013cd9  cmp     eax, 5
0x180013cdc  jbe     short loc_180013CEA
0x180013cde  lea     rdx, byte_1800204EF
0x180013ce5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180013cea  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_ServiceStatus ...
0x180013cf4  lea     rdx, ?TimeBrokerServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180013cfb  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS g_ServiceStatus ...
0x180013d06  mov     ebx, 2
0x180013d0b  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, rbx; _SERVICE_STATUS g_ServiceStatus ...
0x180013d12  xor     r8d, r8d; lpContext
0x180013d15  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ServiceStatus ...
0x180013d1f  mov     rcx, [rdi]; lpServiceName
0x180013d22  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180013d28  mov     cs:?g_ServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_ServiceHandle
0x180013d2f  test    rax, rax
0x180013d32  jnz     short loc_180013D46
0x180013d34  mov     edi, 1000h
0x180013d39  call    cs:__imp_GetLastError
0x180013d3f  mov     ebx, eax
0x180013d41  jmp     loc_180013E10
0x180013d46  mov     ecx, ebx; unsigned int
0x180013d48  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x180013d4d  xor     r9d, r9d; lpName
0x180013d50  xor     r8d, r8d; bInitialState
0x180013d53  mov     edx, esi; bManualReset
0x180013d55  xor     ecx, ecx; lpEventAttributes
0x180013d57  call    cs:__imp_CreateEventW
0x180013d5d  mov     cs:?g_hStopEvent@@3PEAXEA, rax; void * g_hStopEvent
0x180013d64  test    rax, rax
0x180013d67  jnz     short loc_180013D70
0x180013d69  mov     edi, 2000h
0x180013d6e  jmp     short loc_180013D39
0x180013d70  call    ?TimeBrokerInitialize@@YAKXZ; TimeBrokerInitialize(void)
0x180013d75  mov     ebx, eax
0x180013d77  test    eax, eax
0x180013d79  jz      short loc_180013D85
0x180013d7b  mov     edi, 3000h
0x180013d80  jmp     loc_180013E10
0x180013d85  mov     r8, cs:?g_ServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; Recipient
0x180013d8c  lea     r9, ?g_hPowerHandle@@3PEAXEA; RegistrationHandle
0x180013d93  or      cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 241h; _SERVICE_STATUS g_ServiceStatus ...
0x180013d9d  lea     rcx, [rbp+57h+SettingGuid]; SettingGuid
0x180013da1  mov     edx, esi; Flags
0x180013da3  call    cs:__imp_PowerSettingRegisterNotification
0x180013da9  mov     ebx, eax
0x180013dab  test    eax, eax
0x180013dad  jz      short loc_180013DB6
0x180013daf  mov     edi, 4000h
0x180013db4  jmp     short loc_180013E10
0x180013db6  mov     rax, cs:?g_pSvchostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA_EX_V1@@EA; _SVCHOST_GLOBAL_DATA_EX_V1 * g_pSvchostGlobals
0x180013dbd  lea     r9, ?TimeBrokerStopCallback@@YAXPEAXE@Z; TimeBrokerStopCallback(void *,uchar)
0x180013dc4  mov     r8, cs:?g_hStopEvent@@3PEAXEA; void * g_hStopEvent
0x180013dcb  lea     rcx, ?g_hWaitHandle@@3PEAXEA; void * g_hWaitHandle
0x180013dd2  mov     rdx, [rdi]
0x180013dd5  mov     dword ptr [rsp+0D0h+var_A8], 18h
0x180013ddd  mov     rax, [rax+0D0h]
0x180013de4  mov     [rsp+0D0h+var_B0], 0
0x180013ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013df2  mov     ebx, eax
0x180013df4  test    eax, eax
0x180013df6  jz      short loc_180013DFF
0x180013df8  mov     edi, 5000h
0x180013dfd  jmp     short loc_180013E10
0x180013dff  mov     ecx, 4; unsigned int
0x180013e04  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x180013e09  xor     sil, sil
0x180013e0c  xor     edi, edi
0x180013e0e  xor     ebx, ebx
0x180013e10  mov     eax, cs:dword_180026058
0x180013e16  cmp     eax, 5
0x180013e19  jbe     short loc_180013E6B
0x180013e1b  lea     rax, [rbp+57h+var_90]
0x180013e1f  mov     [rbp+57h+var_90], edi
0x180013e22  mov     [rbp+57h+var_40], rax
0x180013e26  lea     rdx, byte_180020481
0x180013e2d  lea     rax, [rbp+57h+var_8C]
0x180013e31  mov     [rbp+57h+var_8C], ebx
0x180013e34  mov     [rbp+57h+var_50], rax
0x180013e38  lea     rcx, dword_180026058
0x180013e3f  lea     rax, [rbp+57h+var_70]
0x180013e43  mov     [rbp+57h+var_38], 4
0x180013e4b  mov     [rsp+0D0h+var_A8], rax
0x180013e50  xor     r9d, r9d
0x180013e53  xor     r8d, r8d
0x180013e56  mov     dword ptr [rsp+0D0h+var_B0], 4
0x180013e5e  mov     [rbp+57h+var_48], 4
0x180013e66  call    _tlgWriteTransfer_EventWriteTransfer
0x180013e6b  test    sil, sil
0x180013e6e  jz      short loc_180013E7C
0x180013e70  mov     edx, 42Ah; unsigned int
0x180013e75  mov     ecx, ebx; unsigned int
0x180013e77  call    ?ServiceCleanup@@YAXKK@Z; ServiceCleanup(ulong,ulong)
0x180013e7c  mov     rcx, [rbp+57h+var_30]
0x180013e80  xor     rcx, rsp; StackCookie
0x180013e83  call    __security_check_cookie
0x180013e88  add     rsp, 0B8h
0x180013e8f  pop     rdi
0x180013e90  pop     rsi
0x180013e91  pop     rbx
0x180013e92  pop     rbp
0x180013e93  retn
```
