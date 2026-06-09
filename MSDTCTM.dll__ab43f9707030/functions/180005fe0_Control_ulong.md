# Control(ulong)

- ea: `0x180005fe0`
- end: `0x180006212`
- name: `?Control@@YAXK@Z`
- size: `562`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005fe0`
- `0x180006220`
- `0x1800063b0`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006202`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180006202`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800060b1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800060b1`

## string_xrefs

- `0x180006061`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x1800060d7`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x18000611d`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x1800061a2`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x18000603c`: `CDtcService::ReportStatus IN`
- `0x18000604f`: `CDtcService::ReportStatus`
- `0x1800060bb`: `CDtcService::ReportStatus OUT ERROR`
- `0x180006101`: `CDtcService::ReportStatus OUT OK`
- `0x180006186`: `Service state set to %d`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
void __fastcall Control(DWORD dwControl)
{
  DWORD dwCurrentState; // edi
  CDtcService *v2; // rbx
  DWORD v3; // ecx
  DWORD v4; // ecx
  DWORD v5; // ecx
  DWORD v6; // eax
  int v7; // eax
  DWORD ThreadId; // [rsp+78h] [rbp+10h] BYREF

  dwCurrentState = ss.dwCurrentState;
  v2 = z_pService;
  if ( !*((_QWORD *)z_pService + 1) )
  {
    (*(void (__fastcall **)(CDtcService *))(*(_QWORD *)z_pService + 24LL))(z_pService);
    return;
  }
  v3 = dwControl - 1;
  if ( !v3 )
    goto LABEL_19;
  v4 = v3 - 1;
  if ( !v4 )
  {
    if ( !(*(unsigned int (__fastcall **)(CDtcService *))(*(_QWORD *)z_pService + 32LL))(z_pService) )
      dwCurrentState = 7;
    v2 = z_pService;
    goto LABEL_7;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v7 = (*(__int64 (__fastcall **)(CDtcService *))(*(_QWORD *)z_pService + 40LL))(z_pService);
    v2 = z_pService;
    if ( !v7 )
      dwCurrentState = 4;
    goto LABEL_7;
  }
  if ( v5 == 2 )
  {
LABEL_19:
    CDtcService::ReportStatus(z_pService, 3u, 0, 0, 0xDBBA0u, 0);
    ThreadId = 0;
    CreateThread(0, 0, StopThread, z_pService, 0, &ThreadId);
    return;
  }
LABEL_7:
  TraceStringInline(
    3,
    6,
    L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
    381,
    L"CDtcService::ReportStatus",
    0,
    L"CDtcService::ReportStatus IN");
  ss.dwServiceType = 16;
  *(_QWORD *)&ss.dwWin32ExitCode = 0;
  v6 = 5;
  if ( dwCurrentState == 2 )
    v6 = 0;
  ss.dwControlsAccepted = v6;
  ss.dwCurrentState = dwCurrentState;
  *(_QWORD *)&ss.dwCheckPoint = 0;
  if ( SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v2 + 7), &ss) )
  {
    if ( dwCurrentState != 4 )
      TraceStringInline(
        3,
        4,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
        415,
        L"CDtcService::ReportStatus",
        0,
        L"Service state set to %d",
        dwCurrentState);
    TraceStringInline(
      3,
      6,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
      418,
      L"CDtcService::ReportStatus",
      0,
      L"CDtcService::ReportStatus OUT OK");
  }
  else
  {
    TraceStringInline(
      3,
      6,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
      408,
      L"CDtcService::ReportStatus",
      0,
      L"CDtcService::ReportStatus OUT ERROR");
  }
}

```

## disassembly

```asm
0x180005fe0  push    rbx
0x180005fe2  push    rsi
0x180005fe3  push    rdi
0x180005fe4  push    r14
0x180005fe6  sub     rsp, 48h
0x180005fea  mov     edi, cs:?ss@@3U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS ss ...
0x180005ff0  mov     rbx, cs:?z_pService@@3PEAVCDtcService@@EA; CDtcService * z_pService
0x180005ff7  cmp     qword ptr [rbx+8], 0
0x180005ffc  jnz     short loc_180006018
0x180005ffe  mov     rax, [rbx]
0x180006001  mov     rcx, rbx
0x180006004  mov     rax, [rax+18h]
0x180006008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000600d  nop
0x18000600e  add     rsp, 48h
0x180006012  pop     r14
0x180006014  pop     rdi
0x180006015  pop     rsi
0x180006016  pop     rbx
0x180006017  retn
0x180006018  sub     ecx, 1
0x18000601b  jz      loc_1800061BD
0x180006021  sub     ecx, 1
0x180006024  jz      loc_18000615D
0x18000602a  sub     ecx, 1
0x18000602d  jz      loc_180006135
0x180006033  cmp     ecx, 2
0x180006036  jz      loc_1800061BD
0x18000603c  lea     rax, aCdtcserviceRep_0; "CDtcService::ReportStatus IN"
0x180006043  mov     [rsp+68h+var_38], rax
0x180006048  xor     esi, esi
0x18000604a  mov     [rsp+68h+lpThreadId], rsi
0x18000604f  lea     r14, aCdtcserviceRep_2; "CDtcService::ReportStatus"
0x180006056  mov     qword ptr [rsp+68h+dwCreationFlags], r14
0x18000605b  mov     r9d, 17Dh
0x180006061  lea     r8, aComComplusDtcD_35; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x180006068  mov     edx, 6
0x18000606d  mov     ecx, 3
0x180006072  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180006077  mov     cs:?ss@@3U_SERVICE_STATUS@@A.dwServiceType, 10h; _SERVICE_STATUS ss ...
0x180006081  mov     qword ptr cs:?ss@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, rsi; _SERVICE_STATUS ss ...
0x180006088  mov     eax, 5
0x18000608d  cmp     edi, 2
0x180006090  cmovz   eax, esi
0x180006093  mov     cs:?ss@@3U_SERVICE_STATUS@@A.dwControlsAccepted, eax; _SERVICE_STATUS ss ...
0x180006099  mov     cs:?ss@@3U_SERVICE_STATUS@@A.dwCurrentState, edi; _SERVICE_STATUS ss ...
0x18000609f  mov     qword ptr cs:?ss@@3U_SERVICE_STATUS@@A.dwCheckPoint, rsi; _SERVICE_STATUS ss ...
0x1800060a6  lea     rdx, ?ss@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800060ad  mov     rcx, [rbx+38h]; hServiceStatus
0x1800060b1  call    cs:__imp_SetServiceStatus
0x1800060b7  test    eax, eax
0x1800060b9  jnz     short loc_1800060F8
0x1800060bb  lea     rax, aCdtcserviceRep; "CDtcService::ReportStatus OUT ERROR"
0x1800060c2  mov     [rsp+68h+var_38], rax
0x1800060c7  mov     [rsp+68h+lpThreadId], rsi
0x1800060cc  mov     qword ptr [rsp+68h+dwCreationFlags], r14
0x1800060d1  mov     r9d, 198h
0x1800060d7  lea     r8, aComComplusDtcD_35; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x1800060de  mov     edx, 6
0x1800060e3  mov     ecx, 3
0x1800060e8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800060ed  nop
0x1800060ee  add     rsp, 48h
0x1800060f2  pop     r14
0x1800060f4  pop     rdi
0x1800060f5  pop     rsi
0x1800060f6  pop     rbx
0x1800060f7  retn
0x1800060f8  cmp     edi, 4
0x1800060fb  jnz     loc_180006182
0x180006101  lea     rax, aCdtcserviceRep_1; "CDtcService::ReportStatus OUT OK"
0x180006108  mov     [rsp+68h+var_38], rax
0x18000610d  mov     [rsp+68h+lpThreadId], rsi
0x180006112  mov     qword ptr [rsp+68h+dwCreationFlags], r14
0x180006117  mov     r9d, 1A2h
0x18000611d  lea     r8, aComComplusDtcD_35; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x180006124  mov     edx, 6
0x180006129  mov     ecx, 3
0x18000612e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180006133  jmp     short loc_1800060EE
0x180006135  mov     rax, [rbx]
0x180006138  mov     rcx, rbx
0x18000613b  mov     rax, [rax+28h]
0x18000613f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006144  mov     rbx, cs:?z_pService@@3PEAVCDtcService@@EA; CDtcService * z_pService
0x18000614b  test    eax, eax
0x18000614d  jnz     loc_18000603C
0x180006153  mov     edi, 4
0x180006158  jmp     loc_18000603C
0x18000615d  mov     rax, [rbx]
0x180006160  mov     rcx, rbx
0x180006163  mov     rax, [rax+20h]
0x180006167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000616c  mov     ecx, 7
0x180006171  test    eax, eax
0x180006173  cmovz   edi, ecx
0x180006176  mov     rbx, cs:?z_pService@@3PEAVCDtcService@@EA; CDtcService * z_pService
0x18000617d  jmp     loc_18000603C
0x180006182  mov     [rsp+68h+var_30], edi
0x180006186  lea     rax, aServiceStateSe; "Service state set to %d"
0x18000618d  mov     [rsp+68h+var_38], rax
0x180006192  mov     [rsp+68h+lpThreadId], rsi
0x180006197  mov     qword ptr [rsp+68h+dwCreationFlags], r14
0x18000619c  mov     r9d, 19Fh
0x1800061a2  lea     r8, aComComplusDtcD_35; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x1800061a9  mov     edx, 4
0x1800061ae  mov     ecx, 3
0x1800061b3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800061b8  jmp     loc_180006101
0x1800061bd  xor     esi, esi
0x1800061bf  mov     dword ptr [rsp+68h+lpThreadId], esi; int
0x1800061c3  mov     [rsp+68h+dwCreationFlags], 0DBBA0h; unsigned int
0x1800061cb  xor     r9d, r9d; unsigned int
0x1800061ce  xor     r8d, r8d; unsigned int
0x1800061d1  mov     edx, 3; unsigned int
0x1800061d6  mov     rcx, rbx; this
0x1800061d9  call    ?ReportStatus@CDtcService@@QEAAJKKKKH@Z; CDtcService::ReportStatus(ulong,ulong,ulong,ulong,int)
0x1800061de  mov     [rsp+68h+ThreadId], esi
0x1800061e2  lea     rax, [rsp+68h+ThreadId]
0x1800061e7  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x1800061ec  mov     [rsp+68h+dwCreationFlags], esi; dwCreationFlags
0x1800061f0  mov     r9, cs:?z_pService@@3PEAVCDtcService@@EA; lpParameter
0x1800061f7  lea     r8, ?StopThread@@YAKPEAX@Z; lpStartAddress
0x1800061fe  xor     edx, edx; dwStackSize
0x180006200  xor     ecx, ecx; lpThreadAttributes
0x180006202  call    cs:__imp_CreateThread
0x180006208  jmp     loc_18000600E
0x18000620d  jmp     loc_18000600E
```
