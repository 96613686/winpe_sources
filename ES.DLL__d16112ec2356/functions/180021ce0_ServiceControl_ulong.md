# ServiceControl(ulong)

- ea: `0x180021ce0`
- end: `0x180021db0`
- name: `?ServiceControl@@YAXK@Z`
- size: `208`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009034`
- `0x180021ce0`
- `0x180023f14`
- `0x18003ecb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021da3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021da3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180021d41`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180021d41`

## string_xrefs

- `0x180021d53`: `SetServiceStatus`
- `0x180021d5f`: `com\complus\src\events\tier2\service.cpp`

## pseudocode

```c
void __fastcall ServiceControl(DWORD dwControl)
{
  DWORD v1; // ecx

  v1 = dwControl - 1;
  if ( !v1 || v1 == 4 )
  {
    ReportStatusToSCM(3u, 0xBB8u);
    if ( g_hServiceStopEvent )
      SetEvent(g_hServiceStopEvent);
  }
  else
  {
    g_status.dwControlsAccepted = g_status.dwCurrentState != 2;
    g_status.dwWin32ExitCode = 0;
    g_status.dwWaitHint = 0;
    if ( g_status.dwCurrentState == 4 || g_status.dwCurrentState == 1 )
      g_status.dwCheckPoint = 0;
    else
      g_status.dwCheckPoint = ++dword_1800642F8;
    if ( !SetServiceStatus(g_statusHandle, &g_status) )
      InternalError_Win32(L"com\\complus\\src\\events\\tier2\\service.cpp", 0x172u, 0x11u, L"SetServiceStatus");
  }
}

```

## disassembly

```asm
0x180021ce0  sub     rsp, 38h
0x180021ce4  sub     ecx, 1
0x180021ce7  jz      loc_180021D88
0x180021ced  cmp     ecx, 4
0x180021cf0  jz      loc_180021D88
0x180021cf6  mov     ecx, cs:?g_status@@3U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS g_status ...
0x180021cfc  xor     eax, eax
0x180021cfe  cmp     ecx, 2
0x180021d01  setnz   al
0x180021d04  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwControlsAccepted, eax; _SERVICE_STATUS g_status ...
0x180021d0a  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwCurrentState, ecx; _SERVICE_STATUS g_status ...
0x180021d10  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS g_status ...
0x180021d1a  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwWaitHint, 0; _SERVICE_STATUS g_status ...
0x180021d24  cmp     ecx, 4
0x180021d27  jnz     short loc_180021D6D
0x180021d29  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_status ...
0x180021d33  lea     rdx, ?g_status@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180021d3a  mov     rcx, cs:?g_statusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180021d41  call    cs:__imp_SetServiceStatus
0x180021d47  test    eax, eax
0x180021d49  jz      short loc_180021D4D
0x180021d4b  jmp     short loc_180021DAB
0x180021d4d  mov     r8d, 11h; unsigned __int16
0x180021d53  lea     r9, aSetservicestat_0; "SetServiceStatus"
0x180021d5a  mov     edx, 172h; unsigned int
0x180021d5f  lea     rcx, aComComplusSrcE_8; "com\\complus\\src\\events\\tier2\\servi"...
0x180021d66  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x180021d6b  jmp     short loc_180021D4B
0x180021d6d  cmp     ecx, 1
0x180021d70  jz      short loc_180021D29
0x180021d72  mov     eax, cs:dword_1800642F8
0x180021d78  inc     eax
0x180021d7a  mov     cs:dword_1800642F8, eax
0x180021d80  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwCheckPoint, eax; _SERVICE_STATUS g_status ...
0x180021d86  jmp     short loc_180021D33
0x180021d88  mov     edx, 0BB8h; unsigned int
0x180021d8d  mov     ecx, 3; unsigned int
0x180021d92  call    ?ReportStatusToSCM@@YAXKK@Z; ReportStatusToSCM(ulong,ulong)
0x180021d97  mov     rcx, cs:?g_hServiceStopEvent@@3PEAXEA; hEvent
0x180021d9e  test    rcx, rcx
0x180021da1  jz      short loc_180021DA9
0x180021da3  call    cs:__imp_SetEvent
0x180021da9  jmp     short $+2
0x180021dab  add     rsp, 38h
0x180021daf  retn
0x180044d9e  push    rbp
0x180044da0  sub     rsp, 20h
0x180044da4  mov     rbp, rdx
0x180044da7  lea     rdx, [rbp+20h]; int *
0x180044dab  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180044db0  nop
0x180044db1  add     rsp, 20h
0x180044db5  pop     rbp
0x180044db6  retn
```
