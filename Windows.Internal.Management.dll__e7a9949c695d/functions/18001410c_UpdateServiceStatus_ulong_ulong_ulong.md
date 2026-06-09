# UpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x18001410c`
- end: `0x180014197`
- name: `?UpdateServiceStatus@@YAXKKK@Z`
- size: `139`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180013e70`
- `0x180014088`

## callees

- `0x18001410c`
- `0x1800141a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001417c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001417c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180014172`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180014172`

## string_xrefs

- `0x180014186`: `UpdateServiceStatus`

## pseudocode

```c
void __fastcall UpdateServiceStatus(DWORD a1, DWORD a2, DWORD a3)
{
  DWORD LastError; // ebx

  ServiceStatus.dwCurrentState = a1;
  ServiceStatus.dwWin32ExitCode = a2;
  ServiceStatus.dwWaitHint = a3;
  ServiceStatus.dwControlsAccepted = a1 != 2;
  if ( a1 == 4 || a1 == 1 )
    ServiceStatus.dwCheckPoint = 0;
  else
    ServiceStatus.dwCheckPoint = dword_1800FAB40++;
  LastError = 0;
  if ( hServiceStatus && !SetServiceStatus(hServiceStatus, &ServiceStatus) )
    LastError = GetLastError();
  EnrollmentLogging::Write(L"UpdateServiceStatus", LastError);
}

```

## disassembly

```asm
0x18001410c  push    rbx
0x18001410e  sub     rsp, 20h
0x180014112  xor     eax, eax
0x180014114  mov     cs:ServiceStatus.dwCurrentState, ecx
0x18001411a  cmp     ecx, 2
0x18001411d  mov     cs:ServiceStatus.dwWin32ExitCode, edx
0x180014123  mov     cs:ServiceStatus.dwWaitHint, r8d
0x18001412a  setnz   al
0x18001412d  mov     cs:ServiceStatus.dwControlsAccepted, eax
0x180014133  cmp     ecx, 4
0x180014136  jz      short loc_180014153
0x180014138  cmp     ecx, 1
0x18001413b  jz      short loc_180014153
0x18001413d  mov     eax, cs:dword_1800FAB40
0x180014143  mov     cs:ServiceStatus.dwCheckPoint, eax
0x180014149  inc     eax
0x18001414b  mov     cs:dword_1800FAB40, eax
0x180014151  jmp     short loc_18001415D
0x180014153  mov     cs:ServiceStatus.dwCheckPoint, 0
0x18001415d  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180014164  xor     ebx, ebx
0x180014166  test    rcx, rcx
0x180014169  jz      short loc_180014184
0x18001416b  lea     rdx, ServiceStatus; lpServiceStatus
0x180014172  call    cs:__imp_SetServiceStatus
0x180014178  test    eax, eax
0x18001417a  jnz     short loc_180014184
0x18001417c  call    cs:__imp_GetLastError
0x180014182  mov     ebx, eax
0x180014184  mov     edx, ebx; int
0x180014186  lea     rcx, aUpdateservices; "UpdateServiceStatus"
0x18001418d  add     rsp, 20h
0x180014191  pop     rbx
0x180014192  jmp     ?Write@EnrollmentLogging@@SAXPEBGJ@Z; EnrollmentLogging::Write(ushort const *,long)
```
