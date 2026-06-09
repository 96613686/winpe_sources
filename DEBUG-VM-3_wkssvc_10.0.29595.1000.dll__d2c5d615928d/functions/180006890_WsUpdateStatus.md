# WsUpdateStatus

- ea: `0x180006890`
- end: `0x1800068ca`
- name: `WsUpdateStatus`
- size: `58`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x1800065c0`
- `0x180006e04`
- `0x18000a1c0`
- `0x18002d530`
- `0x18002db4c`

## callees

- `0x180006890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068ba`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800068b0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800068b0`

## pseudocode

```c
__int64 WsUpdateStatus()
{
  unsigned int v1; // ebx

  if ( !hServiceStatus )
    return 6;
  v1 = 0;
  if ( !SetServiceStatus(hServiceStatus, &WsGlobalData) )
    return GetLastError();
  return v1;
}

```

## disassembly

```asm
0x180006890  push    rbx
0x180006892  sub     rsp, 20h
0x180006896  mov     rcx, cs:hServiceStatus; hServiceStatus
0x18000689d  test    rcx, rcx
0x1800068a0  jnz     short loc_1800068A7
0x1800068a2  lea     eax, [rcx+6]
0x1800068a5  jmp     short loc_1800068C4
0x1800068a7  lea     rdx, WsGlobalData; lpServiceStatus
0x1800068ae  xor     ebx, ebx
0x1800068b0  call    cs:__imp_SetServiceStatus
0x1800068b6  test    eax, eax
0x1800068b8  jnz     short loc_1800068C2
0x1800068ba  call    cs:__imp_GetLastError
0x1800068c0  mov     ebx, eax
0x1800068c2  mov     eax, ebx
0x1800068c4  add     rsp, 20h
0x1800068c8  pop     rbx
0x1800068c9  retn
```
