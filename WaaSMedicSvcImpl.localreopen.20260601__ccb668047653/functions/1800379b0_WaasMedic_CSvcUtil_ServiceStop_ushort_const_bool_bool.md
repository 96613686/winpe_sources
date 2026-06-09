# WaasMedic::CSvcUtil::ServiceStop(ushort const *,bool,bool *)

- ea: `0x1800379b0`
- end: `0x180037ba6`
- name: `?ServiceStop@CSvcUtil@WaasMedic@@SAJPEBG_NPEA_N@Z`
- size: `502`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18002a0a0`

## callees

- `0x18000263c`
- `0x1800050a0`
- `0x18000d04c`
- `0x18002e81c`
- `0x1800378e8`
- `0x1800379b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a9b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180037ae2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180037ae2`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180037a27`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180037a27`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180037a91`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180037a91`

## string_xrefs

- `0x1800379fb`: `Failed to open service %s! hr = 0x%08x`
- `0x180037a63`: `Failed to verify service state for %s! hr = 0x%08x`
- `0x180037ab3`: `Failed to stop service for %s! hr = 0x%08x`
- `0x180037af3`: `SvcUtil: Error when attempting to stop service. Service name: [%s]. hr=0x%08X`
- `0x180037a49`: `Failed to query service status! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::CSvcUtil::ServiceStop(const unsigned __int16 *a1, __int64 a2, bool *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  bool v6; // al
  signed int v7; // eax
  __int64 v8; // rcx
  int v9; // r9d
  SC_HANDLE hService; // [rsp+40h] [rbp+7h] BYREF
  const WCHAR *v12; // [rsp+48h] [rbp+Fh] BYREF
  unsigned __int16 *v13; // [rsp+50h] [rbp+17h] BYREF
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
    v8 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v8 > 5u
      && (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v8 + 24) & 0x400000000000LL) == *(_QWORD *)(v8 + 24) )
    {
      LODWORD(hService) = v4;
      v13 = &gc_pszVersionString;
      v12 = L"w32time";
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)byte_180093F13,
        0,
        v9,
        (__int64)&v14,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&hService);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800379b0  mov     [rsp-8+arg_0], rbx
0x1800379b5  mov     [rsp-8+arg_8], r14
0x1800379ba  push    rbp
0x1800379bb  lea     rbp, [rsp-57h]
0x1800379c0  sub     rsp, 90h
0x1800379c7  mov     rax, cs:__security_cookie
0x1800379ce  xor     rax, rsp
0x1800379d1  mov     [rbp+57h+var_10], rax
0x1800379d5  lea     r8, [rbp+57h+hService]; struct SC_HANDLE__ **
0x1800379d9  mov     [rbp+57h+hService], 0
0x1800379e1  mov     edx, 0F01FFh; unsigned int
0x1800379e6  call    ?OpenNamedService@CSvcUtil@WaasMedic@@SAJPEBGKPEAPEAUSC_HANDLE__@@@Z; WaasMedic::CSvcUtil::OpenNamedService(ushort const *,ulong,SC_HANDLE__ * *)
0x1800379eb  lea     r14, ServiceName; "w32time"
0x1800379f2  mov     ebx, eax
0x1800379f4  test    eax, eax
0x1800379f6  jns     short loc_180037A14
0x1800379f8  mov     r9d, eax
0x1800379fb  lea     rdx, aFailedToOpenSe; "Failed to open service %s! hr = 0x%08x"
0x180037a02  mov     r8, r14
0x180037a05  mov     ecx, 2; unsigned __int8
0x180037a0a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180037a0f  jmp     loc_180037AD7
0x180037a14  mov     rcx, [rbp+57h+hService]; hService
0x180037a18  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180037a1c  xorps   xmm0, xmm0
0x180037a1f  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180037a23  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x180037a27  call    cs:__imp_QueryServiceStatus
0x180037a2d  test    eax, eax
0x180037a2f  jnz     short loc_180037A6C
0x180037a31  call    cs:__imp_GetLastError
0x180037a37  mov     ebx, eax
0x180037a39  test    eax, eax
0x180037a3b  jle     short loc_180037A46
0x180037a3d  movzx   ebx, ax
0x180037a40  or      ebx, 80070000h
0x180037a46  mov     r8d, ebx
0x180037a49  lea     rdx, aFailedToQueryS; "Failed to query service status! hr = 0x"...
0x180037a50  mov     ecx, 2; unsigned __int8
0x180037a55  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180037a5a  xor     al, al
0x180037a5c  test    ebx, ebx
0x180037a5e  jns     short loc_180037A75
0x180037a60  mov     r9d, ebx
0x180037a63  lea     rdx, aFailedToVerify; "Failed to verify service state for %s! "...
0x180037a6a  jmp     short loc_180037A02
0x180037a6c  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 4
0x180037a70  setz    al
0x180037a73  xor     ebx, ebx
0x180037a75  test    al, al
0x180037a77  jz      short loc_180037AC3
0x180037a79  mov     rcx, [rbp+57h+hService]; hService
0x180037a7d  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180037a81  xorps   xmm0, xmm0
0x180037a84  mov     edx, 1; dwControl
0x180037a89  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180037a8d  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x180037a91  call    cs:__imp_ControlService
0x180037a97  test    eax, eax
0x180037a99  jnz     short loc_180037ABF
0x180037a9b  call    cs:__imp_GetLastError
0x180037aa1  mov     ebx, eax
0x180037aa3  test    eax, eax
0x180037aa5  jle     short loc_180037AB0
0x180037aa7  movzx   ebx, ax
0x180037aaa  or      ebx, 80070000h
0x180037ab0  mov     r9d, ebx
0x180037ab3  lea     rdx, aFailedToStopSe; "Failed to stop service for %s! hr = 0x%"...
0x180037aba  jmp     loc_180037A02
0x180037abf  xor     ebx, ebx
0x180037ac1  jmp     short loc_180037AD7
0x180037ac3  mov     r8, r14
0x180037ac6  lea     rdx, aUnableToStopSA; "Unable to stop %s as it was not running"...
0x180037acd  mov     ecx, 4; unsigned __int8
0x180037ad2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180037ad7  cmp     [rbp+57h+hService], 0
0x180037adc  jz      short loc_180037AE8
0x180037ade  mov     rcx, [rbp+57h+hService]; hSCObject
0x180037ae2  call    cs:__imp_CloseServiceHandle
0x180037ae8  test    ebx, ebx
0x180037aea  jns     loc_180037B83
0x180037af0  mov     r9d, ebx
0x180037af3  lea     rdx, aSvcutilErrorWh; "SvcUtil: Error when attempting to stop "...
0x180037afa  mov     r8, r14
0x180037afd  mov     ecx, 2; unsigned __int8
0x180037b02  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180037b07  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180037b0c  mov     rcx, [rax+8]
0x180037b10  mov     eax, [rcx]
0x180037b12  cmp     eax, 5
0x180037b15  jbe     short loc_180037B83
0x180037b17  mov     rdx, [rcx+18h]
0x180037b1b  mov     r8, 400000000000h
0x180037b25  mov     rax, [rcx+10h]
0x180037b29  test    r8, rax
0x180037b2c  jz      short loc_180037B83
0x180037b2e  mov     rax, rdx
0x180037b31  and     rax, r8
0x180037b34  cmp     rax, rdx
0x180037b37  jnz     short loc_180037B83
0x180037b39  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x180037b40  mov     dword ptr [rbp+57h+hService], ebx
0x180037b43  mov     [rbp+57h+var_40], rax
0x180037b47  lea     rdx, byte_180093F13
0x180037b4e  lea     rax, [rbp+57h+hService]
0x180037b52  mov     [rbp+57h+var_48], r14
0x180037b56  mov     [rsp+90h+var_58], rax
0x180037b5b  lea     rax, [rbp+57h+var_48]
0x180037b5f  mov     [rsp+90h+var_60], rax
0x180037b64  lea     rax, [rbp+57h+var_40]
0x180037b68  mov     [rsp+90h+var_68], rax
0x180037b6d  lea     rax, [rbp+57h+var_38]
0x180037b71  mov     [rsp+90h+var_70], rax
0x180037b76  mov     [rbp+57h+var_38], 1000000h
0x180037b7e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180037b83  mov     eax, ebx
0x180037b85  mov     rcx, [rbp+57h+var_10]
0x180037b89  xor     rcx, rsp; StackCookie
0x180037b8c  call    __security_check_cookie
0x180037b91  lea     r11, [rsp+90h+var_s0]
0x180037b99  mov     rbx, [r11+10h]
0x180037b9d  mov     r14, [r11+18h]
0x180037ba1  mov     rsp, r11
0x180037ba4  pop     rbp
0x180037ba5  retn
```
