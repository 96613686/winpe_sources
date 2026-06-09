# UpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x180039624`
- end: `0x180039760`
- name: `?UpdateServiceStatus@@YAJKKK@Z`
- size: `316`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180038e40`
- `0x180038f10`
- `0x180039350`

## callees

- `0x18002e81c`
- `0x180039624`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800396db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800396db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039729`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396f9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800396ef`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800396ef`

## string_xrefs

- `0x180039676`: `Service status %d is not supported! Service status is not updated. hr = 0x%08x`
- `0x180039711`: `UpdateServiceStatus failed while trying to SetServiceStatus. hr = 0x%08x`
- `0x18003963a`: `UpdateServiceStatus has invalid service status handle!`
- `0x180039736`: `Failed to update service status to %d, error is 0x%08x`
- `0x180039742`: `Updated service status to %d`

## pseudocode

```c
__int64 __fastcall UpdateServiceStatus(DWORD a1, DWORD a2, DWORD a3)
{
  unsigned int v4; // ebx
  signed int LastError; // eax

  if ( !hServiceStatus )
  {
    v4 = -2147418113;
    LogLevelW(2u, L"UpdateServiceStatus has invalid service status handle!");
    return v4;
  }
  ServiceStatus.dwWin32ExitCode = a2;
  if ( a1 == 1 )
  {
    ServiceStatus.dwControlsAccepted = 0;
LABEL_12:
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    goto LABEL_13;
  }
  if ( a1 != 2 && a1 != 3 )
  {
    if ( a1 != 4 )
    {
      v4 = -2147023844;
      LogLevelW(2u, L"Service status %d is not supported! Service status is not updated. hr = 0x%08x", a1, 2147943452LL);
      return v4;
    }
    ServiceStatus.dwControlsAccepted = 5;
    goto LABEL_12;
  }
  ++ServiceStatus.dwCheckPoint;
  ServiceStatus.dwControlsAccepted = 0;
  ServiceStatus.dwWaitHint = a3;
LABEL_13:
  ServiceStatus.dwCurrentState = a1;
  v4 = 0;
  EnterCriticalSection(&gcsMedicReady);
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"UpdateServiceStatus failed while trying to SetServiceStatus. hr = 0x%08x", v4);
  }
  LeaveCriticalSection(&gcsMedicReady);
  if ( (v4 & 0x80000000) == 0 )
    LogLevelW(5u, L"Updated service status to %d", a1);
  else
    LogLevelW(2u, L"Failed to update service status to %d, error is 0x%08x", a1, v4);
  return v4;
}

```

## disassembly

```asm
0x180039624  mov     [rsp+arg_0], rbx
0x180039629  push    rdi
0x18003962a  sub     rsp, 20h
0x18003962e  cmp     cs:hServiceStatus, 0
0x180039636  mov     edi, ecx
0x180039638  jnz     short loc_180039655
0x18003963a  lea     rdx, aUpdateservices_0; "UpdateServiceStatus has invalid service"...
0x180039641  mov     ecx, 2; unsigned __int8
0x180039646  mov     ebx, 8000FFFFh
0x18003964b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180039650  jmp     loc_180039753
0x180039655  mov     eax, edi
0x180039657  mov     cs:ServiceStatus.dwWin32ExitCode, edx
0x18003965d  sub     eax, 1
0x180039660  jz      short loc_1800396B7
0x180039662  sub     eax, 1
0x180039665  jz      short loc_18003969E
0x180039667  sub     eax, 1
0x18003966a  jz      short loc_18003969E
0x18003966c  cmp     eax, 1
0x18003966f  jz      short loc_180039692
0x180039671  mov     ebx, 8007041Ch
0x180039676  lea     rdx, aServiceStatusD; "Service status %d is not supported! Ser"...
0x18003967d  mov     r8d, edi
0x180039680  mov     r9d, ebx
0x180039683  mov     ecx, 2; unsigned __int8
0x180039688  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003968d  jmp     loc_180039753
0x180039692  mov     cs:ServiceStatus.dwControlsAccepted, 5
0x18003969c  jmp     short loc_1800396C1
0x18003969e  inc     cs:ServiceStatus.dwCheckPoint
0x1800396a4  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x1800396ae  mov     cs:ServiceStatus.dwWaitHint, r8d
0x1800396b5  jmp     short loc_1800396CC
0x1800396b7  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x1800396c1  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x1800396cc  lea     rcx, ?gcsMedicReady@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800396d3  mov     cs:ServiceStatus.dwCurrentState, edi
0x1800396d9  xor     ebx, ebx
0x1800396db  call    cs:__imp_EnterCriticalSection
0x1800396e1  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800396e8  lea     rdx, ServiceStatus; lpServiceStatus
0x1800396ef  call    cs:__imp_SetServiceStatus
0x1800396f5  test    eax, eax
0x1800396f7  jnz     short loc_180039722
0x1800396f9  call    cs:__imp_GetLastError
0x1800396ff  mov     ebx, eax
0x180039701  test    eax, eax
0x180039703  jle     short loc_18003970E
0x180039705  movzx   ebx, ax
0x180039708  or      ebx, 80070000h
0x18003970e  mov     r8d, ebx
0x180039711  lea     rdx, aUpdateservices; "UpdateServiceStatus failed while trying"...
0x180039718  mov     ecx, 2; unsigned __int8
0x18003971d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180039722  lea     rcx, ?gcsMedicReady@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180039729  call    cs:__imp_LeaveCriticalSection
0x18003972f  mov     r8d, edi
0x180039732  test    ebx, ebx
0x180039734  jns     short loc_180039742
0x180039736  lea     rdx, aFailedToUpdate_0; "Failed to update service status to %d, "...
0x18003973d  jmp     loc_180039680
0x180039742  lea     rdx, aUpdatedService; "Updated service status to %d"
0x180039749  mov     ecx, 5; unsigned __int8
0x18003974e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180039753  mov     eax, ebx
0x180039755  mov     rbx, [rsp+28h+arg_0]
0x18003975a  add     rsp, 20h
0x18003975e  pop     rdi
0x18003975f  retn
```
