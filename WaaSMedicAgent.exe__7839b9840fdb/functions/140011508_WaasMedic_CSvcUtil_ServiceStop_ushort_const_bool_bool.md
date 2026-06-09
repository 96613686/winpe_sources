# WaasMedic::CSvcUtil::ServiceStop(ushort const *,bool,bool *)

- ea: `0x140011508`
- end: `0x1400116fd`
- name: `?ServiceStop@CSvcUtil@WaasMedic@@SAJPEBG_NPEA_N@Z`
- size: `501`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x140010f14`

## callees

- `0x140001fe0`
- `0x140002a30`
- `0x14000885c`
- `0x14000b470`
- `0x140011440`
- `0x140011508`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400115f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400115f3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001163a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001163a`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x14001157f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x14001157f`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1400115e9`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1400115e9`

## string_xrefs

- `0x140011553`: `Failed to open service %s! hr = 0x%08x`
- `0x1400115bb`: `Failed to verify service state for %s! hr = 0x%08x`
- `0x14001160b`: `Failed to stop service for %s! hr = 0x%08x`
- `0x1400115a1`: `Failed to query service status! hr = 0x%08x`
- `0x14001164b`: `SvcUtil: Error when attempting to stop service. Service name: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::CSvcUtil::ServiceStop(const unsigned __int16 *a1, __int64 a2, bool *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  bool v6; // al
  signed int v7; // eax
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r9
  SC_HANDLE hService; // [rsp+40h] [rbp+7h] BYREF
  const unsigned __int16 *v12; // [rsp+48h] [rbp+Fh] BYREF
  unsigned __int16 near **v13; // [rsp+50h] [rbp+17h] BYREF
  __int64 v14; // [rsp+58h] [rbp+1Fh] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp+27h] BYREF

  hService = 0;
  v3 = WaasMedic::CSvcUtil::OpenNamedService(a1, 0xF01FFu, &hService);
  v4 = v3;
  if ( v3 >= 0 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(hService, &ServiceStatus) )
    {
      v6 = ServiceStatus.dwCurrentState == 4;
      v4 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      LogLevelW(2u, L"Failed to query service status! hr = 0x%08x", v4);
      v6 = 0;
      if ( (v4 & 0x80000000) != 0 )
      {
        LogLevelW(2u, L"Failed to verify service state for %s! hr = 0x%08x", L"w32time", v4);
        goto LABEL_17;
      }
    }
    if ( v6 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      if ( ControlService(hService, 1u, &ServiceStatus) )
      {
        v4 = 0;
      }
      else
      {
        v7 = GetLastError();
        v4 = v7;
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
        LogLevelW(2u, L"Failed to stop service for %s! hr = 0x%08x", L"w32time", v4);
      }
    }
    else
    {
      LogLevelW(4u, L"Unable to stop %s as it was not running.", L"w32time");
    }
  }
  else
  {
    LogLevelW(2u, L"Failed to open service %s! hr = 0x%08x", L"w32time", (unsigned int)v3);
  }
LABEL_17:
  if ( hService )
    CloseServiceHandle(hService);
  if ( (v4 & 0x80000000) != 0 )
  {
    LogLevelW(2u, L"SvcUtil: Error when attempting to stop service. Service name: [%s]. hr=0x%08X", L"w32time", v4);
    v8 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v8 > 5u
      && (*((_QWORD *)v8 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v8 + 3) & 0x400000000000LL) == *((_QWORD *)v8 + 3) )
    {
      LODWORD(hService) = v4;
      v13 = &gc_pszVersionString;
      v12 = L"w32time";
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (__int64)&unk_14001A358,
        0x400000000000LL,
        v9,
        (__int64)&v14,
        (const unsigned __int16 **)&v13,
        &v12,
        (__int64)&hService);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140011508  mov     [rsp-8+arg_0], rbx
0x14001150d  mov     [rsp-8+arg_8], r14
0x140011512  push    rbp
0x140011513  lea     rbp, [rsp-57h]
0x140011518  sub     rsp, 90h
0x14001151f  mov     rax, cs:__security_cookie
0x140011526  xor     rax, rsp
0x140011529  mov     [rbp+57h+var_10], rax
0x14001152d  lea     r8, [rbp+57h+hService]; struct SC_HANDLE__ **
0x140011531  mov     [rbp+57h+hService], 0
0x140011539  mov     edx, 0F01FFh; unsigned int
0x14001153e  call    ?OpenNamedService@CSvcUtil@WaasMedic@@SAJPEBGKPEAPEAUSC_HANDLE__@@@Z; WaasMedic::CSvcUtil::OpenNamedService(ushort const *,ulong,SC_HANDLE__ * *)
0x140011543  lea     r14, ServiceName; "w32time"
0x14001154a  mov     ebx, eax
0x14001154c  test    eax, eax
0x14001154e  jns     short loc_14001156C
0x140011550  mov     r9d, eax
0x140011553  lea     rdx, aFailedToOpenSe; "Failed to open service %s! hr = 0x%08x"
0x14001155a  mov     r8, r14
0x14001155d  mov     ecx, 2; unsigned __int8
0x140011562  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140011567  jmp     loc_14001162F
0x14001156c  mov     rcx, [rbp+57h+hService]; hService
0x140011570  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x140011574  xorps   xmm0, xmm0
0x140011577  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x14001157b  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x14001157f  call    cs:__imp_QueryServiceStatus
0x140011585  test    eax, eax
0x140011587  jnz     short loc_1400115C4
0x140011589  call    cs:__imp_GetLastError
0x14001158f  mov     ebx, eax
0x140011591  test    eax, eax
0x140011593  jle     short loc_14001159E
0x140011595  movzx   ebx, ax
0x140011598  or      ebx, 80070000h
0x14001159e  mov     r8d, ebx
0x1400115a1  lea     rdx, aFailedToQueryS; "Failed to query service status! hr = 0x"...
0x1400115a8  mov     ecx, 2; unsigned __int8
0x1400115ad  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1400115b2  xor     al, al
0x1400115b4  test    ebx, ebx
0x1400115b6  jns     short loc_1400115CD
0x1400115b8  mov     r9d, ebx
0x1400115bb  lea     rdx, aFailedToVerify; "Failed to verify service state for %s! "...
0x1400115c2  jmp     short loc_14001155A
0x1400115c4  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 4
0x1400115c8  setz    al
0x1400115cb  xor     ebx, ebx
0x1400115cd  test    al, al
0x1400115cf  jz      short loc_14001161B
0x1400115d1  mov     rcx, [rbp+57h+hService]; hService
0x1400115d5  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x1400115d9  xorps   xmm0, xmm0
0x1400115dc  mov     edx, 1; dwControl
0x1400115e1  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x1400115e5  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x1400115e9  call    cs:__imp_ControlService
0x1400115ef  test    eax, eax
0x1400115f1  jnz     short loc_140011617
0x1400115f3  call    cs:__imp_GetLastError
0x1400115f9  mov     ebx, eax
0x1400115fb  test    eax, eax
0x1400115fd  jle     short loc_140011608
0x1400115ff  movzx   ebx, ax
0x140011602  or      ebx, 80070000h
0x140011608  mov     r9d, ebx
0x14001160b  lea     rdx, aFailedToStopSe; "Failed to stop service for %s! hr = 0x%"...
0x140011612  jmp     loc_14001155A
0x140011617  xor     ebx, ebx
0x140011619  jmp     short loc_14001162F
0x14001161b  mov     r8, r14
0x14001161e  lea     rdx, aUnableToStopSA; "Unable to stop %s as it was not running"...
0x140011625  mov     ecx, 4; unsigned __int8
0x14001162a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14001162f  cmp     [rbp+57h+hService], 0
0x140011634  jz      short loc_140011640
0x140011636  mov     rcx, [rbp+57h+hService]; hSCObject
0x14001163a  call    cs:__imp_CloseServiceHandle
0x140011640  test    ebx, ebx
0x140011642  jns     loc_1400116DA
0x140011648  mov     r9d, ebx
0x14001164b  lea     rdx, aSvcutilErrorWh; "SvcUtil: Error when attempting to stop "...
0x140011652  mov     r8, r14
0x140011655  mov     ecx, 2; unsigned __int8
0x14001165a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14001165f  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x140011664  mov     ecx, [rax]
0x140011666  cmp     ecx, 5
0x140011669  jbe     short loc_1400116DA
0x14001166b  mov     rdx, [rax+18h]
0x14001166f  mov     r8, 400000000000h
0x140011679  mov     rcx, [rax+10h]
0x14001167d  test    r8, rcx
0x140011680  jz      short loc_1400116DA
0x140011682  mov     rcx, rdx
0x140011685  and     rcx, r8
0x140011688  cmp     rcx, rdx
0x14001168b  jnz     short loc_1400116DA
0x14001168d  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x140011694  mov     dword ptr [rbp+57h+hService], ebx
0x140011697  mov     [rbp+57h+var_40], rcx
0x14001169b  lea     rdx, unk_14001A358
0x1400116a2  lea     rcx, [rbp+57h+hService]
0x1400116a6  mov     [rbp+57h+var_48], r14
0x1400116aa  mov     [rsp+90h+var_58], rcx
0x1400116af  lea     rcx, [rbp+57h+var_48]
0x1400116b3  mov     [rsp+90h+var_60], rcx
0x1400116b8  lea     rcx, [rbp+57h+var_40]
0x1400116bc  mov     [rsp+90h+var_68], rcx
0x1400116c1  lea     rcx, [rbp+57h+var_38]
0x1400116c5  mov     [rsp+90h+var_70], rcx
0x1400116ca  mov     rcx, rax
0x1400116cd  mov     [rbp+57h+var_38], 1000000h
0x1400116d5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400116da  mov     eax, ebx
0x1400116dc  mov     rcx, [rbp+57h+var_10]
0x1400116e0  xor     rcx, rsp; StackCookie
0x1400116e3  call    __security_check_cookie
0x1400116e8  lea     r11, [rsp+90h+var_s0]
0x1400116f0  mov     rbx, [r11+10h]
0x1400116f4  mov     r14, [r11+18h]
0x1400116f8  mov     rsp, r11
0x1400116fb  pop     rbp
0x1400116fc  retn
```
