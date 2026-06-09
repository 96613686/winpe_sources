# UpdateState(ulong)

- ea: `0x180008334`
- end: `0x18000838a`
- name: `?UpdateState@@YAXK@Z`
- size: `86`
- prototype: `void __fastcall(DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180008240`

## callees

- `0x180008334`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000836d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000836d`

## pseudocode

```c
void __fastcall UpdateState(DWORD a1)
{
  if ( a1 != 1 )
  {
    if ( a1 == 2 || a1 == 3 )
    {
      ++g_ServiceStatus.dwCheckPoint;
      g_ServiceStatus.dwWaitHint += 1000;
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
0x180008334  sub     rsp, 28h
0x180008338  mov     eax, ecx
0x18000833a  sub     eax, 1
0x18000833d  jz      short loc_18000834E
0x18000833f  sub     eax, 1
0x180008342  jz      short loc_180008378
0x180008344  sub     eax, 1
0x180008347  jz      short loc_180008378
0x180008349  cmp     eax, 1
0x18000834c  jnz     short loc_180008373
0x18000834e  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ServiceStatus ...
0x180008359  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, ecx; _SERVICE_STATUS g_ServiceStatus ...
0x18000835f  lea     rdx, ?g_ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180008366  mov     rcx, cs:?g_ServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18000836d  call    cs:__imp_SetServiceStatus
0x180008373  add     rsp, 28h
0x180008377  retn
0x180008378  inc     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint; _SERVICE_STATUS g_ServiceStatus ...
0x18000837e  add     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 3E8h; _SERVICE_STATUS g_ServiceStatus ...
0x180008388  jmp     short loc_180008359
```
