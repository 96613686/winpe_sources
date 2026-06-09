# WaasMedic::CSvcUtil::ServiceStart(ushort const *)

- ea: `0x180035efc`
- end: `0x180036136`
- name: `?ServiceStart@CSvcUtil@WaasMedic@@SAJPEBG@Z`
- size: `570`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18004ca5c`

## callees

- `0x1800023b0`
- `0x180003bb0`
- `0x180016c9c`
- `0x18002543c`
- `0x180035090`
- `0x180035efc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ff0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180036128`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180036128`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180035f7e`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180035f7e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003604d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003604d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180035fe2`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180035fe2`

## string_xrefs

- `0x180035f5c`: `Failed to open service %s! hr = 0x%08x`
- `0x180036008`: `Failed to query service status! hr = 0x%08x`
- `0x180035fa8`: `Service %s was already running`
- `0x180035f2c`: `Invalid pointer input for CSvcUtil::ServiceStart!`
- `0x18003602e`: `Failed to start service with retries! hr = 0x%08x`
- `0x180035fc3`: `Failed to start service %s! hr = 0x%08x`
- `0x18003605e`: `SvcUtil: Error when attempting to start service. Service name: [%s]. hr=0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::CSvcUtil::ServiceStart(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  signed int LastError; // eax
  unsigned int i; // r14d
  signed int v6; // eax
  bool v7; // al
  bool v8; // zf
  const struct _tlgProvider_t *v9; // rax
  int v10; // r9d
  SC_HANDLE hService; // [rsp+40h] [rbp-19h] BYREF
  const unsigned __int16 *v13; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int16 *v14; // [rsp+50h] [rbp-9h] BYREF
  __int64 v15; // [rsp+58h] [rbp-1h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp+7h] BYREF

  hService = 0;
  if ( !a1 )
  {
    v2 = -2147467261;
    LogLevelW(2u, L"Invalid pointer input for CSvcUtil::ServiceStart!");
    goto LABEL_23;
  }
  v3 = WaasMedic::CSvcUtil::OpenNamedService(a1, 0xF01FFu, &hService);
  v2 = v3;
  if ( v3 < 0 )
  {
    LogLevelW(2u, L"Failed to open service %s! hr = 0x%08x", a1, (unsigned int)v3);
    goto LABEL_20;
  }
  if ( !StartServiceW(hService, 0, 0) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 == -2147023840 )
    {
      LogLevelW(4u, L"Service %s was already running", a1);
      v2 = 0;
    }
    else
    {
      LogLevelW(2u, L"Failed to start service %s! hr = 0x%08x", a1, v2);
    }
    goto LABEL_20;
  }
  for ( i = 0; ; ++i )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(hService, &ServiceStatus) )
    {
      v7 = ServiceStatus.dwCurrentState == 4;
      v2 = 0;
      goto LABEL_29;
    }
    v6 = GetLastError();
    v2 = v6;
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    LogLevelW(2u, L"Failed to query service status! hr = 0x%08x", v2);
    v7 = 0;
    if ( (v2 & 0x80000000) != 0 )
      break;
LABEL_29:
    if ( v7 )
      break;
    v8 = i == 10;
    if ( i >= 0xA )
      goto LABEL_18;
    Sleep(0xBB8u);
  }
  v8 = i == 10;
LABEL_18:
  if ( v8 )
  {
    v2 = -2147023843;
    LogLevelW(2u, L"Failed to start service with retries! hr = 0x%08x", 2147943453LL);
  }
LABEL_20:
  if ( hService )
    CloseServiceHandle(hService);
  if ( (v2 & 0x80000000) != 0 )
  {
LABEL_23:
    LogLevelW(2u, L"SvcUtil: Error when attempting to start service. Service name: [%s]. hr=0x%08x", a1, v2);
    v9 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v9 > 5u
      && (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v9 + 3) & 0x400000000000LL) == *((_QWORD *)v9 + 3) )
    {
      LODWORD(hService) = v2;
      v14 = &gc_pszVersionString;
      v13 = a1;
      v15 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v9,
        (unsigned int)byte_1800896C3,
        0,
        v10,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&v13,
        (__int64)&hService);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180035efc  push    rbp
0x180035efe  push    rbx
0x180035eff  push    rdi
0x180035f00  push    r14
0x180035f02  lea     rbp, [rsp-3Fh]
0x180035f07  sub     rsp, 98h
0x180035f0e  mov     rax, cs:__security_cookie
0x180035f15  xor     rax, rsp
0x180035f18  mov     [rbp+57h+var_30], rax
0x180035f1c  mov     [rbp+57h+hService], 0
0x180035f24  mov     rdi, rcx
0x180035f27  test    rcx, rcx
0x180035f2a  jnz     short loc_180035F45
0x180035f2c  lea     rdx, aInvalidPointer_0; "Invalid pointer input for CSvcUtil::Ser"...
0x180035f33  mov     ebx, 80004003h
0x180035f38  lea     ecx, [rdi+2]; unsigned __int8
0x180035f3b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035f40  jmp     loc_18003605B
0x180035f45  lea     r8, [rbp+57h+hService]; struct SC_HANDLE__ **
0x180035f49  mov     edx, 0F01FFh; dwDesiredAccess
0x180035f4e  call    ?OpenNamedService@CSvcUtil@WaasMedic@@SAJPEBGKPEAPEAUSC_HANDLE__@@@Z; WaasMedic::CSvcUtil::OpenNamedService(ushort const *,ulong,SC_HANDLE__ * *)
0x180035f53  mov     ebx, eax
0x180035f55  test    eax, eax
0x180035f57  jns     short loc_180035F75
0x180035f59  mov     r9d, eax
0x180035f5c  lea     rdx, aFailedToOpenSe_0; "Failed to open service %s! hr = 0x%08x"
0x180035f63  mov     r8, rdi
0x180035f66  mov     ecx, 2; unsigned __int8
0x180035f6b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035f70  jmp     loc_180036042
0x180035f75  mov     rcx, [rbp+57h+hService]; hService
0x180035f79  xor     r8d, r8d; lpServiceArgVectors
0x180035f7c  xor     edx, edx; dwNumServiceArgs
0x180035f7e  call    cs:__imp_StartServiceW
0x180035f84  test    eax, eax
0x180035f86  jnz     short loc_180035FCC
0x180035f88  call    cs:__imp_GetLastError
0x180035f8e  mov     ebx, eax
0x180035f90  test    eax, eax
0x180035f92  jle     short loc_180035F9D
0x180035f94  movzx   ebx, ax
0x180035f97  or      ebx, 80070000h
0x180035f9d  mov     r8, rdi
0x180035fa0  cmp     ebx, 80070420h
0x180035fa6  jnz     short loc_180035FC0
0x180035fa8  lea     rdx, aServiceSWasAlr; "Service %s was already running"
0x180035faf  mov     ecx, 4; unsigned __int8
0x180035fb4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180035fb9  xor     ebx, ebx
0x180035fbb  jmp     loc_180036042
0x180035fc0  mov     r9d, ebx
0x180035fc3  lea     rdx, aFailedToStartS_0; "Failed to start service %s! hr = 0x%08x"
0x180035fca  jmp     short loc_180035F66
0x180035fcc  xor     r14d, r14d
0x180035fcf  mov     rcx, [rbp+57h+hService]; hService
0x180035fd3  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180035fd7  xorps   xmm0, xmm0
0x180035fda  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x180035fde  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x180035fe2  call    cs:__imp_QueryServiceStatus
0x180035fe8  test    eax, eax
0x180035fea  jnz     loc_180036108
0x180035ff0  call    cs:__imp_GetLastError
0x180035ff6  mov     ebx, eax
0x180035ff8  test    eax, eax
0x180035ffa  jle     short loc_180036005
0x180035ffc  movzx   ebx, ax
0x180035fff  or      ebx, 80070000h
0x180036005  mov     r8d, ebx
0x180036008  lea     rdx, aFailedToQueryS_0; "Failed to query service status! hr = 0x"...
0x18003600f  mov     ecx, 2; unsigned __int8
0x180036014  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180036019  xor     al, al
0x18003601b  test    ebx, ebx
0x18003601d  jns     loc_180036111
0x180036023  cmp     r14d, 0Ah
0x180036027  jnz     short loc_180036042
0x180036029  mov     ebx, 8007041Dh
0x18003602e  lea     rdx, aFailedToStartS; "Failed to start service with retries! h"...
0x180036035  mov     r8d, ebx
0x180036038  mov     ecx, 2; unsigned __int8
0x18003603d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180036042  cmp     [rbp+57h+hService], 0
0x180036047  jz      short loc_180036053
0x180036049  mov     rcx, [rbp+57h+hService]; hSCObject
0x18003604d  call    cs:__imp_CloseServiceHandle
0x180036053  test    ebx, ebx
0x180036055  jns     loc_1800360ED
0x18003605b  mov     r9d, ebx
0x18003605e  lea     rdx, aSvcutilErrorWh; "SvcUtil: Error when attempting to start"...
0x180036065  mov     r8, rdi
0x180036068  mov     ecx, 2; unsigned __int8
0x18003606d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180036072  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180036077  mov     ecx, [rax]
0x180036079  cmp     ecx, 5
0x18003607c  jbe     short loc_1800360ED
0x18003607e  mov     rdx, [rax+18h]
0x180036082  mov     r8, 400000000000h
0x18003608c  mov     rcx, [rax+10h]
0x180036090  test    r8, rcx
0x180036093  jz      short loc_1800360ED
0x180036095  mov     rcx, rdx
0x180036098  and     rcx, r8
0x18003609b  cmp     rcx, rdx
0x18003609e  jnz     short loc_1800360ED
0x1800360a0  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800360a7  mov     dword ptr [rbp+57h+hService], ebx
0x1800360aa  mov     [rbp+57h+var_60], rcx
0x1800360ae  lea     rdx, byte_1800896C3
0x1800360b5  lea     rcx, [rbp+57h+hService]
0x1800360b9  mov     [rbp+57h+var_68], rdi
0x1800360bd  mov     [rsp+0B0h+var_78], rcx
0x1800360c2  lea     rcx, [rbp+57h+var_68]
0x1800360c6  mov     [rsp+0B0h+var_80], rcx
0x1800360cb  lea     rcx, [rbp+57h+var_60]
0x1800360cf  mov     [rsp+0B0h+var_88], rcx
0x1800360d4  lea     rcx, [rbp+57h+var_58]
0x1800360d8  mov     [rsp+0B0h+var_90], rcx
0x1800360dd  mov     rcx, rax
0x1800360e0  mov     [rbp+57h+var_58], 1000000h
0x1800360e8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800360ed  mov     eax, ebx
0x1800360ef  mov     rcx, [rbp+57h+var_30]
0x1800360f3  xor     rcx, rsp; StackCookie
0x1800360f6  call    __security_check_cookie
0x1800360fb  add     rsp, 98h
0x180036102  pop     r14
0x180036104  pop     rdi
0x180036105  pop     rbx
0x180036106  pop     rbp
0x180036107  retn
0x180036108  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 4
0x18003610c  setz    al
0x18003610f  xor     ebx, ebx
0x180036111  test    al, al
0x180036113  jnz     loc_180036023
0x180036119  cmp     r14d, 0Ah
0x18003611d  jnb     loc_180036027
0x180036123  mov     ecx, 0BB8h; dwMilliseconds
0x180036128  call    cs:__imp_Sleep
0x18003612e  inc     r14d
0x180036131  jmp     loc_180035FCF
```
