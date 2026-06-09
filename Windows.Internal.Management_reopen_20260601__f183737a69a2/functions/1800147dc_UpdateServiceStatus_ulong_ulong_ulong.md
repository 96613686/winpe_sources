# UpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x1800147dc`
- end: `0x180014873`
- name: `?UpdateServiceStatus@@YAXKKK@Z`
- size: `151`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180014500`
- `0x180014750`

## callees

- `0x1800147dc`
- `0x18001487c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014852`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180014842`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180014842`

## string_xrefs

- `0x180014862`: `UpdateServiceStatus`

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
    ServiceStatus.dwCheckPoint = dword_1800FEC40++;
  LastError = 0;
  if ( hServiceStatus && !SetServiceStatus(hServiceStatus, &ServiceStatus) )
    LastError = GetLastError();
  EnrollmentLogging::Write(L"UpdateServiceStatus", LastError);
}

```

## disassembly

```asm
0x1800147dc  push    rbx
0x1800147de  sub     rsp, 20h
0x1800147e2  xor     eax, eax
0x1800147e4  mov     cs:ServiceStatus.dwCurrentState, ecx
0x1800147ea  cmp     ecx, 2
0x1800147ed  mov     cs:ServiceStatus.dwWin32ExitCode, edx
0x1800147f3  mov     cs:ServiceStatus.dwWaitHint, r8d
0x1800147fa  setnz   al
0x1800147fd  mov     cs:ServiceStatus.dwControlsAccepted, eax
0x180014803  cmp     ecx, 4
0x180014806  jz      short loc_180014823
0x180014808  cmp     ecx, 1
0x18001480b  jz      short loc_180014823
0x18001480d  mov     eax, cs:dword_1800FEC40
0x180014813  mov     cs:ServiceStatus.dwCheckPoint, eax
0x180014819  inc     eax
0x18001481b  mov     cs:dword_1800FEC40, eax
0x180014821  jmp     short loc_18001482D
0x180014823  mov     cs:ServiceStatus.dwCheckPoint, 0
0x18001482d  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180014834  xor     ebx, ebx
0x180014836  test    rcx, rcx
0x180014839  jz      short loc_180014860
0x18001483b  lea     rdx, ServiceStatus; lpServiceStatus
0x180014842  call    cs:__imp_SetServiceStatus
0x180014849  nop     dword ptr [rax+rax+00h]
0x18001484e  test    eax, eax
0x180014850  jnz     short loc_180014860
0x180014852  call    cs:__imp_GetLastError
0x180014859  nop     dword ptr [rax+rax+00h]
0x18001485e  mov     ebx, eax
0x180014860  mov     edx, ebx; int
0x180014862  lea     rcx, aUpdateservices; "UpdateServiceStatus"
0x180014869  add     rsp, 20h
0x18001486d  pop     rbx
0x18001486e  jmp     ?Write@EnrollmentLogging@@SAXPEBGJ@Z; EnrollmentLogging::Write(ushort const *,long)
```
