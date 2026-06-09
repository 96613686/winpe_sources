# CStandardCollectorService::ServiceControlHandlerStatic(ulong,ulong,void *,void *)

- ea: `0x140007d00`
- end: `0x140007d43`
- name: `?ServiceControlHandlerStatic@CStandardCollectorService@@CAKKKPEAX0@Z`
- size: `67`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, char *lpContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x140007d00`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140007d35`
- `KERNEL32!SetEvent` at `0x140007d35`
- `ADVAPI32!SetServiceStatus` at `0x140007d21`
- `ADVAPI32!SetServiceStatus` at `0x140007d21`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CStandardCollectorService::ServiceControlHandlerStatic(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        char *lpContext)
{
  DWORD v5; // ecx
  SERVICE_STATUS_HANDLE v6; // rcx

  v5 = dwControl - 1;
  if ( !v5 || v5 == 4 )
  {
    v6 = *(SERVICE_STATUS_HANDLE *)lpContext;
    *((_DWORD *)lpContext + 3) = 3;
    SetServiceStatus(v6, (LPSERVICE_STATUS)(lpContext + 8));
    if ( *((int *)lpContext + 14) >= 0 )
      SetEvent(*((HANDLE *)lpContext + 6));
  }
  return 0;
}

```

## disassembly

```asm
0x140007d00  push    rbx
0x140007d02  sub     rsp, 20h
0x140007d06  mov     rbx, r9
0x140007d09  sub     ecx, 1
0x140007d0c  jz      short loc_140007D13
0x140007d0e  cmp     ecx, 4
0x140007d11  jnz     short loc_140007D3B
0x140007d13  mov     rcx, [r9]; hServiceStatus
0x140007d16  lea     rdx, [r9+8]; lpServiceStatus
0x140007d1a  mov     dword ptr [rdx+4], 3
0x140007d21  call    cs:__imp_SetServiceStatus
0x140007d27  mov     eax, [rbx+38h]
0x140007d2a  shr     eax, 1Fh
0x140007d2d  test    al, al
0x140007d2f  jnz     short loc_140007D3B
0x140007d31  mov     rcx, [rbx+30h]; hEvent
0x140007d35  call    cs:__imp_SetEvent
0x140007d3b  xor     eax, eax
0x140007d3d  add     rsp, 20h
0x140007d41  pop     rbx
0x140007d42  retn
```
