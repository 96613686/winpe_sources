# ReportServiceStatus(ulong,ulong,ulong,ulong)

- ea: `0x18003a890`
- end: `0x18003a93d`
- name: `?ReportServiceStatus@@YAKKKKK@Z`
- size: `173`
- prototype: `unsigned int __fastcall(unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18003ad70`
- `0x18003b010`
- `0x18003b478`

## callees

- `0x180018194`
- `0x180019168`
- `0x18002c640`
- `0x18003a890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8e3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003a8d3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18003a8d3`

## pseudocode

```c
__int64 __fastcall ReportServiceStatus(DWORD a1, DWORD a2, DWORD a3)
{
  struct ServiceContext *v3; // rax
  DWORD LastError; // eax
  DWORD v5; // ebx
  DWORD v7; // [rsp+30h] [rbp-38h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-30h] BYREF

  ServiceStatus.dwServiceType = 32;
  *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
  ServiceStatus.dwWaitHint = 0;
  ServiceStatus.dwCurrentState = a1;
  ServiceStatus.dwControlsAccepted = a2;
  ServiceStatus.dwWin32ExitCode = a3;
  v3 = ServiceContext::Instance();
  if ( SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v3 + 1), &ServiceStatus) )
    return 0;
  LastError = GetLastError();
  v5 = LastError;
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    v7 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)qword_1800A9640,
      0,
      0,
      (__int64)&v7);
  }
  return v5;
}

```

## disassembly

```asm
0x18003a890  push    rbx
0x18003a892  sub     rsp, 60h
0x18003a896  mov     rax, cs:__security_cookie
0x18003a89d  xor     rax, rsp
0x18003a8a0  mov     [rsp+68h+var_10], rax
0x18003a8a5  xor     ebx, ebx
0x18003a8a7  mov     [rsp+68h+ServiceStatus.dwServiceType], 20h ; ' '
0x18003a8af  mov     qword ptr [rsp+68h+ServiceStatus.dwServiceSpecificExitCode], rbx
0x18003a8b4  mov     [rsp+68h+ServiceStatus.dwWaitHint], ebx
0x18003a8b8  mov     [rsp+68h+ServiceStatus.dwCurrentState], ecx
0x18003a8bc  mov     [rsp+68h+ServiceStatus.dwControlsAccepted], edx
0x18003a8c0  mov     [rsp+68h+ServiceStatus.dwWin32ExitCode], r8d
0x18003a8c5  call    ?Instance@ServiceContext@@SAAEAU1@XZ; ServiceContext::Instance(void)
0x18003a8ca  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18003a8cf  mov     rcx, [rax+8]; hServiceStatus
0x18003a8d3  call    cs:__imp_SetServiceStatus
0x18003a8da  nop     dword ptr [rax+rax+00h]
0x18003a8df  test    eax, eax
0x18003a8e1  jnz     short loc_18003A927
0x18003a8e3  call    cs:__imp_GetLastError
0x18003a8ea  nop     dword ptr [rax+rax+00h]
0x18003a8ef  mov     ecx, cs:dword_1800BE0B8
0x18003a8f5  mov     ebx, eax
0x18003a8f7  cmp     ecx, 2
0x18003a8fa  jbe     short loc_18003A923
0x18003a8fc  mov     [rsp+68h+var_38], eax
0x18003a900  lea     rdx, qword_1800A9640
0x18003a907  lea     rax, [rsp+68h+var_38]
0x18003a90c  xor     r9d, r9d
0x18003a90f  xor     r8d, r8d
0x18003a912  mov     [rsp+68h+var_48], rax
0x18003a917  lea     rcx, dword_1800BE0B8
0x18003a91e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003a923  mov     eax, ebx
0x18003a925  jmp     short loc_18003A929
0x18003a927  xor     eax, eax
0x18003a929  mov     rcx, [rsp+68h+var_10]
0x18003a92e  xor     rcx, rsp; StackCookie
0x18003a931  call    __security_check_cookie
0x18003a936  add     rsp, 60h
0x18003a93a  pop     rbx
0x18003a93b  retn
```
