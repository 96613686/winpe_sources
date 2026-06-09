# UpdateState(ulong)

- ea: `0x18000dbb0`
- end: `0x18000dc06`
- name: `?UpdateState@@YAXK@Z`
- size: `86`
- prototype: `void __fastcall(DWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x18000dc40`
- `0x18000dd00`

## callees

- `0x18000dbb0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000dbe9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000dbe9`

## pseudocode

```c
void __fastcall UpdateState(DWORD a1)
{
  if ( a1 != 1 )
  {
    if ( a1 == 2 || a1 == 3 )
    {
      ++ServiceStatus.dwCheckPoint;
      ServiceStatus.dwWaitHint = 60000;
      goto LABEL_6;
    }
    if ( a1 != 4 )
      return;
  }
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
LABEL_6:
  ServiceStatus.dwCurrentState = a1;
  SetServiceStatus(hServiceStatus, &ServiceStatus);
}

```

## disassembly

```asm
0x18000dbb0  sub     rsp, 28h
0x18000dbb4  mov     eax, ecx
0x18000dbb6  sub     eax, 1
0x18000dbb9  jz      short loc_18000DBCA
0x18000dbbb  sub     eax, 1
0x18000dbbe  jz      short loc_18000DBF4
0x18000dbc0  sub     eax, 1
0x18000dbc3  jz      short loc_18000DBF4
0x18000dbc5  cmp     eax, 1
0x18000dbc8  jnz     short loc_18000DBEF
0x18000dbca  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x18000dbd5  mov     cs:ServiceStatus.dwCurrentState, ecx
0x18000dbdb  lea     rdx, ServiceStatus; lpServiceStatus
0x18000dbe2  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18000dbe9  call    cs:__imp_SetServiceStatus
0x18000dbef  add     rsp, 28h
0x18000dbf3  retn
0x18000dbf4  inc     cs:ServiceStatus.dwCheckPoint
0x18000dbfa  mov     cs:ServiceStatus.dwWaitHint, 0EA60h
0x18000dc04  jmp     short loc_18000DBD5
```
