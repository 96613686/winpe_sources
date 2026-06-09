# UpdateState(ulong)

- ea: `0x180013c40`
- end: `0x180013c96`
- name: `?UpdateState@@YAXK@Z`
- size: `86`
- prototype: `void __fastcall(DWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180013b40`
- `0x180013ca0`

## callees

- `0x180013c40`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180013c79`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180013c79`

## pseudocode

```c
void __fastcall UpdateState(DWORD a1)
{
  if ( a1 != 1 )
  {
    if ( a1 == 2 || a1 == 3 )
    {
      ++g_ServiceStatus.dwCheckPoint;
      g_ServiceStatus.dwWaitHint = 200;
      goto LABEL_6;
    }
    if ( a1 != 4 )
      return;
  }
  *(_QWORD *)&g_ServiceStatus.dwCheckPoint = 0;
LABEL_6:
  g_ServiceStatus.dwCurrentState = a1;
  SetServiceStatus(g_ServiceHandle, &g_ServiceStatus);
}

```

## disassembly

```asm
0x180013c40  sub     rsp, 28h
0x180013c44  mov     eax, ecx
0x180013c46  sub     eax, 1
0x180013c49  jz      short loc_180013C5A
0x180013c4b  sub     eax, 1
0x180013c4e  jz      short loc_180013C84
0x180013c50  sub     eax, 1
0x180013c53  jz      short loc_180013C84
0x180013c55  cmp     eax, 1
0x180013c58  jnz     short loc_180013C7F
0x180013c5a  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ServiceStatus ...
0x180013c65  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, ecx; _SERVICE_STATUS g_ServiceStatus ...
0x180013c6b  lea     rdx, ?g_ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180013c72  mov     rcx, cs:?g_ServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180013c79  call    cs:__imp_SetServiceStatus
0x180013c7f  add     rsp, 28h
0x180013c83  retn
0x180013c84  inc     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint; _SERVICE_STATUS g_ServiceStatus ...
0x180013c8a  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0C8h; _SERVICE_STATUS g_ServiceStatus ...
0x180013c94  jmp     short loc_180013C65
```
