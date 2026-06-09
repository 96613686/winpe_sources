# Service::ReportStatus(ulong,ulong)

- ea: `0x180007eb8`
- end: `0x180007f25`
- name: `?ReportStatus@Service@@AEAAXKK@Z`
- size: `109`
- prototype: `void __fastcall(Service *this, DWORD, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180006670`
- `0x180007e10`

## callees

- `0x180007eb8`
- `0x180007f2c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007f0a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007f0a`

## string_xrefs

- `0x180007f14`: `SetServiceStatus`

## pseudocode

```c
void __fastcall Service::ReportStatus(Service *this, DWORD a2, DWORD a3)
{
  Service *v3; // rcx

  if ( g_service )
  {
    ServiceStatus.dwCurrentState = a2;
    ServiceStatus.dwWaitHint = a3;
    if ( a2 == 4 || a2 == 1 )
      ServiceStatus.dwCheckPoint = 0;
    else
      ServiceStatus.dwCheckPoint = dword_18000F248++;
    if ( !SetServiceStatus(g_service, &ServiceStatus) )
      Service::LogError(v3, L"SetServiceStatus");
  }
}

```

## disassembly

```asm
0x180007eb8  sub     rsp, 28h
0x180007ebc  mov     r9, cs:?g_service@@3VService@@A; Service g_service
0x180007ec3  test    r9, r9
0x180007ec6  jz      short loc_180007F20
0x180007ec8  mov     cs:ServiceStatus.dwCurrentState, edx
0x180007ece  mov     cs:ServiceStatus.dwWaitHint, r8d
0x180007ed5  cmp     edx, 4
0x180007ed8  jz      short loc_180007EF6
0x180007eda  cmp     edx, 1
0x180007edd  jz      short loc_180007EF6
0x180007edf  mov     ecx, cs:dword_18000F248
0x180007ee5  mov     cs:ServiceStatus.dwCheckPoint, ecx
0x180007eeb  lea     eax, [rcx+1]
0x180007eee  mov     cs:dword_18000F248, eax
0x180007ef4  jmp     short loc_180007F00
0x180007ef6  mov     cs:ServiceStatus.dwCheckPoint, 0
0x180007f00  lea     rdx, ServiceStatus; lpServiceStatus
0x180007f07  mov     rcx, r9; hServiceStatus
0x180007f0a  call    cs:__imp_SetServiceStatus
0x180007f10  test    eax, eax
0x180007f12  jnz     short loc_180007F20
0x180007f14  lea     rdx, aSetservicestat; "SetServiceStatus"
0x180007f1b  call    ?LogError@Service@@QEAAXPEBG@Z; Service::LogError(ushort const *)
0x180007f20  add     rsp, 28h
0x180007f24  retn
```
