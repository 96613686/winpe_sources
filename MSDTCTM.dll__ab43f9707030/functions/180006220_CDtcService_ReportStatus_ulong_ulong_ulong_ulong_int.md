# CDtcService::ReportStatus(ulong,ulong,ulong,ulong,int)

- ea: `0x180006220`
- end: `0x1800063a8`
- name: `?ReportStatus@CDtcService@@QEAAJKKKKH@Z`
- size: `392`
- prototype: `__int64 __fastcall(CDtcService *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005220`
- `0x180005fe0`
- `0x180006750`
- `0x1800160c4`
- `0x180083e40`

## callees

- `0x180006220`
- `0x1800063b0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800062cf`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800062cf`

## string_xrefs

- `0x18000624b`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x1800062eb`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x180006334`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x18000637d`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x18000622d`: `CDtcService::ReportStatus IN`
- `0x18000623c`: `CDtcService::ReportStatus`
- `0x1800062d9`: `CDtcService::ReportStatus OUT ERROR`
- `0x180006322`: `CDtcService::ReportStatus OUT OK`
- `0x180006371`: `Service state set to %d`

## pseudocode

```c
__int64 __fastcall CDtcService::ReportStatus(
        SERVICE_STATUS_HANDLE *this,
        DWORD a2,
        DWORD a3,
        DWORD a4,
        DWORD a5,
        int a6)
{
  DWORD v10; // ecx

  TraceStringInline(
    3,
    6,
    L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
    381,
    L"CDtcService::ReportStatus",
    0,
    L"CDtcService::ReportStatus IN");
  ss.dwServiceType = 16;
  if ( a6 )
  {
    ss.dwServiceSpecificExitCode = a3;
    ss.dwWin32ExitCode = 1066;
  }
  else
  {
    ss.dwServiceSpecificExitCode = 0;
    ss.dwWin32ExitCode = a3;
  }
  v10 = 5;
  ss.dwCurrentState = a2;
  ss.dwCheckPoint = a4;
  ss.dwWaitHint = a5;
  if ( a2 == 2 )
    v10 = 0;
  ss.dwControlsAccepted = v10;
  if ( SetServiceStatus(this[7], &ss) )
  {
    if ( a2 != 4 )
      TraceStringInline(
        3,
        4,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
        415,
        L"CDtcService::ReportStatus",
        0,
        L"Service state set to %d",
        a2);
    TraceStringInline(
      3,
      6,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
      418,
      L"CDtcService::ReportStatus",
      0,
      L"CDtcService::ReportStatus OUT OK");
    return 0;
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
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180006220  push    rbx
0x180006222  push    rbp
0x180006223  push    rsi
0x180006224  push    rdi
0x180006225  push    r14
0x180006227  push    r15
0x180006229  sub     rsp, 48h
0x18000622d  lea     rax, aCdtcserviceRep_0; "CDtcService::ReportStatus IN"
0x180006234  mov     esi, r9d
0x180006237  mov     [rsp+78h+var_48], rax
0x18000623c  lea     r15, aCdtcserviceRep_2; "CDtcService::ReportStatus"
0x180006243  mov     edi, r8d
0x180006246  mov     ebx, edx
0x180006248  mov     rbp, rcx
0x18000624b  lea     r8, aComComplusDtcD_35; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x180006252  xor     r14d, r14d
0x180006255  mov     r9d, 17Dh
0x18000625b  mov     [rsp+78h+var_50], r14
0x180006260  mov     edx, 6
0x180006265  mov     ecx, 3
0x18000626a  mov     [rsp+78h+var_58], r15
0x18000626f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180006274  mov     cs:?ss@@3U_SERVICE_STATUS@@A.dwServiceType, 10h; _SERVICE_STATUS ss ...
0x18000627e  cmp     [rsp+78h+arg_28], r14d
0x180006286  jnz     loc_180006358
0x18000628c  mov     cs:?ss@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, r14d; _SERVICE_STATUS ss ...
0x180006293  mov     cs:?ss@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, edi; _SERVICE_STATUS ss ...
0x180006299  mov     eax, [rsp+78h+arg_20]
0x1800062a0  lea     rdx, ?ss@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800062a7  mov     ecx, 5
0x1800062ac  mov     cs:?ss@@3U_SERVICE_STATUS@@A.dwCurrentState, ebx; _SERVICE_STATUS ss ...
0x1800062b2  mov     cs:?ss@@3U_SERVICE_STATUS@@A.dwCheckPoint, esi; _SERVICE_STATUS ss ...
0x1800062b8  cmp     ebx, 2
0x1800062bb  mov     cs:?ss@@3U_SERVICE_STATUS@@A.dwWaitHint, eax; _SERVICE_STATUS ss ...
0x1800062c1  cmovz   ecx, r14d
0x1800062c5  mov     cs:?ss@@3U_SERVICE_STATUS@@A.dwControlsAccepted, ecx; _SERVICE_STATUS ss ...
0x1800062cb  mov     rcx, [rbp+38h]; hServiceStatus
0x1800062cf  call    cs:__imp_SetServiceStatus
0x1800062d5  test    eax, eax
0x1800062d7  jnz     short loc_18000631D
0x1800062d9  lea     rax, aCdtcserviceRep; "CDtcService::ReportStatus OUT ERROR"
0x1800062e0  mov     r9d, 198h
0x1800062e6  mov     [rsp+78h+var_48], rax
0x1800062eb  lea     r8, aComComplusDtcD_35; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x1800062f2  mov     [rsp+78h+var_50], r14
0x1800062f7  mov     edx, 6
0x1800062fc  mov     ecx, 3
0x180006301  mov     [rsp+78h+var_58], r15
0x180006306  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000630b  mov     eax, 80004005h
0x180006310  add     rsp, 48h
0x180006314  pop     r15
0x180006316  pop     r14
0x180006318  pop     rdi
0x180006319  pop     rsi
0x18000631a  pop     rbp
0x18000631b  pop     rbx
0x18000631c  retn
0x18000631d  cmp     ebx, 4
0x180006320  jnz     short loc_18000636D
0x180006322  lea     rax, aCdtcserviceRep_1; "CDtcService::ReportStatus OUT OK"
0x180006329  mov     r9d, 1A2h
0x18000632f  mov     [rsp+78h+var_48], rax
0x180006334  lea     r8, aComComplusDtcD_35; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x18000633b  mov     [rsp+78h+var_50], r14
0x180006340  mov     edx, 6
0x180006345  mov     ecx, 3
0x18000634a  mov     [rsp+78h+var_58], r15
0x18000634f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180006354  xor     eax, eax
0x180006356  jmp     short loc_180006310
0x180006358  mov     cs:?ss@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, edi; _SERVICE_STATUS ss ...
0x18000635e  mov     cs:?ss@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 42Ah; _SERVICE_STATUS ss ...
0x180006368  jmp     loc_180006299
0x18000636d  mov     [rsp+78h+var_40], ebx
0x180006371  lea     rax, aServiceStateSe; "Service state set to %d"
0x180006378  mov     [rsp+78h+var_48], rax
0x18000637d  lea     r8, aComComplusDtcD_35; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x180006384  mov     [rsp+78h+var_50], r14
0x180006389  mov     r9d, 19Fh
0x18000638f  mov     edx, 4
0x180006394  mov     [rsp+78h+var_58], r15
0x180006399  mov     ecx, 3
0x18000639e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800063a3  jmp     loc_180006322
```
