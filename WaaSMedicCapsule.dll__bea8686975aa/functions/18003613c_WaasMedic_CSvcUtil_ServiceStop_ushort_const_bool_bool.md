# WaasMedic::CSvcUtil::ServiceStop(ushort const *,bool,bool *)

- ea: `0x18003613c`
- end: `0x18003646b`
- name: `?ServiceStop@CSvcUtil@WaasMedic@@SAJPEBG_NPEA_N@Z`
- size: `815`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180030d34`
- `0x18003b8c0`

## callees

- `0x1800023b0`
- `0x180003bb0`
- `0x180016c9c`
- `0x18002543c`
- `0x180035090`
- `0x18003613c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800361f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003634f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800361f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003634f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800362fa`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800362fa`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800363a4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800363a4`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800361db`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003628d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180036308`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x1800361db`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18003628d`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180036308`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18003624e`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x18003624e`

## string_xrefs

- `0x180036185`: `Invalid pointer input for CSvcUtil::ServiceStop!`
- `0x18003621c`: `Failed to verify service state for %s! hr = 0x%08x`
- `0x1800361ad`: `Failed to open service %s! hr = 0x%08x`
- `0x1800362ac`: `Failed to query service status for %s! hr = 0x%08x`
- `0x18003626d`: `Failed to stop service for %s! hr = 0x%08x`
- `0x180036205`: `Failed to query service status! hr = 0x%08x`
- `0x180036364`: `Failed to query service status! hr = 0x%08x`
- `0x180036372`: `Failed to stop service within timeout! hr = 0x%08x`
- `0x1800363b5`: `SvcUtil: Error when attempting to stop service. Service name: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::CSvcUtil::ServiceStop(const unsigned __int16 *a1, char a2, bool *a3)
{
  unsigned int v5; // ebx
  int v6; // eax
  signed int LastError; // eax
  bool v8; // al
  signed int v9; // eax
  signed int v10; // eax
  DWORD dwCheckPoint; // r12d
  DWORD dwWaitHint; // esi
  signed int v13; // eax
  const struct _tlgProvider_t *v14; // rax
  int v15; // r9d
  SC_HANDLE hService; // [rsp+40h] [rbp-19h] BYREF
  const unsigned __int16 *v18; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int16 *v19; // [rsp+50h] [rbp-9h] BYREF
  __int64 v20; // [rsp+58h] [rbp-1h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp+7h] BYREF

  hService = 0;
  if ( !a1 )
  {
    v5 = -2147467261;
    LogLevelW(2u, L"Invalid pointer input for CSvcUtil::ServiceStop!", a3);
LABEL_48:
    LogLevelW(2u, L"SvcUtil: Error when attempting to stop service. Service name: [%s]. hr=0x%08X", a1, v5);
    v14 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v14 > 5u
      && (*((_QWORD *)v14 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v14 + 3) & 0x400000000000LL) == *((_QWORD *)v14 + 3) )
    {
      LODWORD(hService) = v5;
      v19 = &gc_pszVersionString;
      v18 = a1;
      v20 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v14,
        (unsigned int)byte_18008971D,
        0,
        v15,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&hService);
    }
    return v5;
  }
  v6 = WaasMedic::CSvcUtil::OpenNamedService(a1, 0xF01FFu, &hService);
  v5 = v6;
  if ( v6 < 0 )
  {
    LogLevelW(2u, L"Failed to open service %s! hr = 0x%08x", a1, (unsigned int)v6);
    goto LABEL_45;
  }
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( QueryServiceStatus(hService, &ServiceStatus) )
  {
    v8 = ServiceStatus.dwCurrentState == 4;
    v5 = 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"Failed to query service status! hr = 0x%08x", v5);
    v8 = 0;
    if ( (v5 & 0x80000000) != 0 )
    {
      LogLevelW(2u, L"Failed to verify service state for %s! hr = 0x%08x", a1, v5);
      goto LABEL_45;
    }
  }
  if ( v8 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( ControlService(hService, 1u, &ServiceStatus) )
    {
      if ( a2 )
      {
        if ( QueryServiceStatus(hService, &ServiceStatus) )
        {
          dwCheckPoint = ServiceStatus.dwCheckPoint;
          if ( ServiceStatus.dwWaitHint <= 0x927C0 )
          {
            dwWaitHint = 60000;
            if ( ServiceStatus.dwWaitHint > 0xEA60 )
              dwWaitHint = ServiceStatus.dwWaitHint;
          }
          else
          {
            dwWaitHint = 600000;
          }
          if ( ServiceStatus.dwCurrentState != 1 )
          {
            while ( 1 )
            {
              if ( !dwWaitHint )
              {
                v5 = -2147023843;
                LogLevelW(2u, L"Failed to stop service within timeout! hr = 0x%08x", 2147943453LL);
                goto LABEL_45;
              }
              if ( dwWaitHint < 0xBB8 )
                dwWaitHint = 3000;
              Sleep(0xBB8u);
              if ( !QueryServiceStatus(hService, &ServiceStatus) )
                break;
              if ( dwCheckPoint >= ServiceStatus.dwCheckPoint )
              {
                dwWaitHint -= 3000;
              }
              else
              {
                dwCheckPoint = ServiceStatus.dwCheckPoint;
                if ( ServiceStatus.dwWaitHint <= 0x927C0 )
                {
                  dwWaitHint = 60000;
                  if ( ServiceStatus.dwWaitHint > 0xEA60 )
                    dwWaitHint = ServiceStatus.dwWaitHint;
                }
                else
                {
                  dwWaitHint = 600000;
                }
              }
              if ( ServiceStatus.dwCurrentState == 1 )
                goto LABEL_45;
            }
            v13 = GetLastError();
            v5 = v13;
            if ( v13 > 0 )
              v5 = (unsigned __int16)v13 | 0x80070000;
            LogLevelW(2u, L"Failed to query service status! hr = 0x%08x", v5);
          }
        }
        else
        {
          v10 = GetLastError();
          v5 = v10;
          if ( v10 > 0 )
            v5 = (unsigned __int16)v10 | 0x80070000;
          LogLevelW(2u, L"Failed to query service status for %s! hr = 0x%08x", a1, v5);
        }
      }
      else
      {
        v5 = 0;
      }
    }
    else
    {
      v9 = GetLastError();
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      LogLevelW(2u, L"Failed to stop service for %s! hr = 0x%08x", a1, v5);
    }
  }
  else
  {
    LogLevelW(4u, L"Unable to stop %s as it was not running.", a1);
  }
LABEL_45:
  if ( hService )
    CloseServiceHandle(hService);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_48;
  return v5;
}

```

## disassembly

```asm
0x18003613c  mov     [rsp-8+arg_8], rbx
0x180036141  mov     [rsp-8+arg_10], rsi
0x180036146  push    rbp
0x180036147  push    rdi
0x180036148  push    r12
0x18003614a  push    r13
0x18003614c  push    r14
0x18003614e  lea     rbp, [rsp-37h]
0x180036153  sub     rsp, 90h
0x18003615a  mov     rax, cs:__security_cookie
0x180036161  xor     rax, rsp
0x180036164  mov     [rbp+57h+var_30], rax
0x180036168  mov     [rbp+57h+hService], 0
0x180036170  mov     sil, dl
0x180036173  mov     r14, rcx
0x180036176  test    rcx, rcx
0x180036179  jnz     short loc_180036196
0x18003617b  lea     edi, [rcx+2]
0x18003617e  mov     ebx, 80004003h
0x180036183  mov     ecx, edi; unsigned __int8
0x180036185  lea     rdx, aInvalidPointer_7; "Invalid pointer input for CSvcUtil::Ser"...
0x18003618c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180036191  jmp     loc_1800363B2
0x180036196  lea     r8, [rbp+57h+hService]; struct SC_HANDLE__ **
0x18003619a  mov     edx, 0F01FFh; dwDesiredAccess
0x18003619f  call    ?OpenNamedService@CSvcUtil@WaasMedic@@SAJPEBGKPEAPEAUSC_HANDLE__@@@Z; WaasMedic::CSvcUtil::OpenNamedService(ushort const *,ulong,SC_HANDLE__ * *)
0x1800361a4  mov     ebx, eax
0x1800361a6  test    eax, eax
0x1800361a8  jns     short loc_1800361C8
0x1800361aa  mov     r9d, eax
0x1800361ad  lea     rdx, aFailedToOpenSe_0; "Failed to open service %s! hr = 0x%08x"
0x1800361b4  mov     edi, 2
0x1800361b9  mov     r8, r14
0x1800361bc  mov     ecx, edi; unsigned __int8
0x1800361be  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800361c3  jmp     loc_180036399
0x1800361c8  mov     rcx, [rbp+57h+hService]; hService
0x1800361cc  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x1800361d0  xorps   xmm0, xmm0
0x1800361d3  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x1800361d7  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800361db  call    cs:__imp_QueryServiceStatus
0x1800361e1  mov     edi, 2
0x1800361e6  mov     r12d, 80070000h
0x1800361ec  test    eax, eax
0x1800361ee  jnz     short loc_180036225
0x1800361f0  call    cs:__imp_GetLastError
0x1800361f6  mov     ebx, eax
0x1800361f8  test    eax, eax
0x1800361fa  jle     short loc_180036202
0x1800361fc  movzx   ebx, ax
0x1800361ff  or      ebx, r12d
0x180036202  mov     r8d, ebx
0x180036205  lea     rdx, aFailedToQueryS_0; "Failed to query service status! hr = 0x"...
0x18003620c  mov     ecx, edi; unsigned __int8
0x18003620e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180036213  xor     al, al
0x180036215  test    ebx, ebx
0x180036217  jns     short loc_18003622E
0x180036219  mov     r9d, ebx
0x18003621c  lea     rdx, aFailedToVerify; "Failed to verify service state for %s! "...
0x180036223  jmp     short loc_1800361B9
0x180036225  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 4
0x180036229  setz    al
0x18003622c  xor     ebx, ebx
0x18003622e  test    al, al
0x180036230  jz      loc_180036385
0x180036236  mov     rcx, [rbp+57h+hService]; hService
0x18003623a  lea     r8, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18003623e  xorps   xmm0, xmm0
0x180036241  mov     edx, 1; dwControl
0x180036246  movups  xmmword ptr [rbp+57h+ServiceStatus.dwServiceType], xmm0
0x18003624a  movups  xmmword ptr [rbp+57h+ServiceStatus.dwWin32ExitCode], xmm0
0x18003624e  call    cs:__imp_ControlService
0x180036254  test    eax, eax
0x180036256  jnz     short loc_180036279
0x180036258  call    cs:__imp_GetLastError
0x18003625e  mov     ebx, eax
0x180036260  test    eax, eax
0x180036262  jle     short loc_18003626A
0x180036264  movzx   ebx, ax
0x180036267  or      ebx, r12d
0x18003626a  mov     r9d, ebx
0x18003626d  lea     rdx, aFailedToStopSe_0; "Failed to stop service for %s! hr = 0x%"...
0x180036274  jmp     loc_1800361B9
0x180036279  test    sil, sil
0x18003627c  jnz     short loc_180036285
0x18003627e  xor     ebx, ebx
0x180036280  jmp     loc_180036399
0x180036285  mov     rcx, [rbp+57h+hService]; hService
0x180036289  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x18003628d  call    cs:__imp_QueryServiceStatus
0x180036293  test    eax, eax
0x180036295  jnz     short loc_1800362B8
0x180036297  call    cs:__imp_GetLastError
0x18003629d  mov     ebx, eax
0x18003629f  test    eax, eax
0x1800362a1  jle     short loc_1800362A9
0x1800362a3  movzx   ebx, ax
0x1800362a6  or      ebx, r12d
0x1800362a9  mov     r9d, ebx
0x1800362ac  lea     rdx, aFailedToQueryS; "Failed to query service status for %s! "...
0x1800362b3  jmp     loc_1800361B9
0x1800362b8  mov     eax, [rbp+57h+ServiceStatus.dwWaitHint]
0x1800362bb  mov     r13d, 0EA60h
0x1800362c1  mov     r12d, [rbp+57h+ServiceStatus.dwCheckPoint]
0x1800362c5  mov     ecx, 927C0h
0x1800362ca  cmp     eax, r13d
0x1800362cd  jbe     short loc_1800362D7
0x1800362cf  cmp     eax, ecx
0x1800362d1  jbe     short loc_1800362D7
0x1800362d3  mov     esi, ecx
0x1800362d5  jmp     short loc_1800362E0
0x1800362d7  cmp     eax, r13d
0x1800362da  mov     esi, r13d
0x1800362dd  cmova   esi, eax
0x1800362e0  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x1800362e4  jz      loc_180036399
0x1800362ea  mov     eax, 0BB8h
0x1800362ef  test    esi, esi
0x1800362f1  jz      short loc_18003636D
0x1800362f3  cmp     esi, eax
0x1800362f5  mov     ecx, eax; dwMilliseconds
0x1800362f7  cmovb   esi, eax
0x1800362fa  call    cs:__imp_Sleep
0x180036300  mov     rcx, [rbp+57h+hService]; hService
0x180036304  lea     rdx, [rbp+57h+ServiceStatus]; lpServiceStatus
0x180036308  call    cs:__imp_QueryServiceStatus
0x18003630e  test    eax, eax
0x180036310  jz      short loc_18003634F
0x180036312  cmp     r12d, [rbp+57h+ServiceStatus.dwCheckPoint]
0x180036316  jnb     short loc_18003633C
0x180036318  mov     eax, [rbp+57h+ServiceStatus.dwWaitHint]
0x18003631b  mov     r12d, [rbp+57h+ServiceStatus.dwCheckPoint]
0x18003631f  cmp     eax, r13d
0x180036322  jbe     short loc_180036331
0x180036324  mov     ecx, 927C0h
0x180036329  cmp     eax, ecx
0x18003632b  jbe     short loc_180036331
0x18003632d  mov     esi, ecx
0x18003632f  jmp     short loc_180036342
0x180036331  cmp     eax, r13d
0x180036334  mov     esi, r13d
0x180036337  cmova   esi, eax
0x18003633a  jmp     short loc_180036342
0x18003633c  add     esi, 0FFFFF448h
0x180036342  cmp     [rbp+57h+ServiceStatus.dwCurrentState], 1
0x180036346  mov     eax, 0BB8h
0x18003634b  jnz     short loc_1800362EF
0x18003634d  jmp     short loc_180036399
0x18003634f  call    cs:__imp_GetLastError
0x180036355  mov     ebx, eax
0x180036357  test    eax, eax
0x180036359  jle     short loc_180036364
0x18003635b  movzx   ebx, ax
0x18003635e  or      ebx, 80070000h
0x180036364  lea     rdx, aFailedToQueryS_0; "Failed to query service status! hr = 0x"...
0x18003636b  jmp     short loc_180036379
0x18003636d  mov     ebx, 8007041Dh
0x180036372  lea     rdx, aFailedToStopSe; "Failed to stop service within timeout! "...
0x180036379  mov     r8d, ebx
0x18003637c  mov     ecx, edi; unsigned __int8
0x18003637e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180036383  jmp     short loc_180036399
0x180036385  mov     r8, r14
0x180036388  lea     rdx, aUnableToStopSA; "Unable to stop %s as it was not running"...
0x18003638f  mov     ecx, 4; unsigned __int8
0x180036394  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180036399  cmp     [rbp+57h+hService], 0
0x18003639e  jz      short loc_1800363AA
0x1800363a0  mov     rcx, [rbp+57h+hService]; hSCObject
0x1800363a4  call    cs:__imp_CloseServiceHandle
0x1800363aa  test    ebx, ebx
0x1800363ac  jns     loc_180036441
0x1800363b2  mov     r9d, ebx
0x1800363b5  lea     rdx, aSvcutilErrorWh_0; "SvcUtil: Error when attempting to stop "...
0x1800363bc  mov     r8, r14
0x1800363bf  mov     ecx, edi; unsigned __int8
0x1800363c1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800363c6  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x1800363cb  mov     ecx, [rax]
0x1800363cd  cmp     ecx, 5
0x1800363d0  jbe     short loc_180036441
0x1800363d2  mov     rdx, [rax+18h]
0x1800363d6  mov     r8, 400000000000h
0x1800363e0  mov     rcx, [rax+10h]
0x1800363e4  test    r8, rcx
0x1800363e7  jz      short loc_180036441
0x1800363e9  mov     rcx, rdx
0x1800363ec  and     rcx, r8
0x1800363ef  cmp     rcx, rdx
0x1800363f2  jnz     short loc_180036441
0x1800363f4  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800363fb  mov     dword ptr [rbp+57h+hService], ebx
0x1800363fe  mov     [rbp+57h+var_60], rcx
0x180036402  lea     rdx, byte_18008971D
0x180036409  lea     rcx, [rbp+57h+hService]
0x18003640d  mov     [rbp+57h+var_68], r14
0x180036411  mov     [rsp+0B0h+var_78], rcx
0x180036416  lea     rcx, [rbp+57h+var_68]
0x18003641a  mov     [rsp+0B0h+var_80], rcx
0x18003641f  lea     rcx, [rbp+57h+var_60]
0x180036423  mov     [rsp+0B0h+var_88], rcx
0x180036428  lea     rcx, [rbp+57h+var_58]
0x18003642c  mov     [rsp+0B0h+var_90], rcx
0x180036431  mov     rcx, rax
0x180036434  mov     [rbp+57h+var_58], 1000000h
0x18003643c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180036441  mov     eax, ebx
0x180036443  mov     rcx, [rbp+57h+var_30]
0x180036447  xor     rcx, rsp; StackCookie
0x18003644a  call    __security_check_cookie
0x18003644f  lea     r11, [rsp+0B0h+var_20]
0x180036457  mov     rbx, [r11+38h]
0x18003645b  mov     rsi, [r11+40h]
0x18003645f  mov     rsp, r11
0x180036462  pop     r14
0x180036464  pop     r13
0x180036466  pop     r12
0x180036468  pop     rdi
0x180036469  pop     rbp
0x18003646a  retn
```
