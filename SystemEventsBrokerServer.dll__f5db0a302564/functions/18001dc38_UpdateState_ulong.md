# UpdateState(ulong)

- ea: `0x18001dc38`
- end: `0x18001dc8a`
- name: `?UpdateState@@YAXK@Z`
- size: `82`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x18001a830`

## callees

- `0x18001dc38`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001dc71`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001dc71`

## pseudocode

```c
void __fastcall UpdateState(DWORD a1)
{
  if ( a1 != 1 )
  {
    if ( a1 == 2 || a1 == 3 )
    {
      ++g_ServiceStatus.dwCheckPoint;
      ++g_ServiceStatus.dwWaitHint;
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
0x18001dc38  sub     rsp, 28h
0x18001dc3c  mov     eax, ecx
0x18001dc3e  sub     eax, 1
0x18001dc41  jz      short loc_18001DC52
0x18001dc43  sub     eax, 1
0x18001dc46  jz      short loc_18001DC7C
0x18001dc48  sub     eax, 1
0x18001dc4b  jz      short loc_18001DC7C
0x18001dc4d  cmp     eax, 1
0x18001dc50  jnz     short loc_18001DC77
0x18001dc52  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ServiceStatus ...
0x18001dc5d  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, ecx; _SERVICE_STATUS g_ServiceStatus ...
0x18001dc63  lea     rdx, ?g_ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18001dc6a  mov     rcx, cs:?g_ServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18001dc71  call    cs:__imp_SetServiceStatus
0x18001dc77  add     rsp, 28h
0x18001dc7b  retn
0x18001dc7c  inc     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint; _SERVICE_STATUS g_ServiceStatus ...
0x18001dc82  inc     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint; _SERVICE_STATUS g_ServiceStatus ...
0x18001dc88  jmp     short loc_18001DC5D
```
