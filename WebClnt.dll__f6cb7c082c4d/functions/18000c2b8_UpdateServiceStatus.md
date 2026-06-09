# UpdateServiceStatus

- ea: `0x18000c2b8`
- end: `0x18000c2f6`
- name: `UpdateServiceStatus`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180025b10`
- `0x180025bf8`
- `0x180025f10`

## callees

- `0x18000c2b8`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c2eb`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c2eb`

## pseudocode

```c
BOOL __fastcall UpdateServiceStatus(DWORD a1)
{
  BOOL result; // eax

  result = 0;
  g_status.dwCurrentState = a1;
  if ( g_registeredService )
  {
    if ( a1 == 4 || a1 == 1 )
      *(_QWORD *)&g_status.dwCheckPoint = 0;
    return SetServiceStatus(g_hStatus, &g_status);
  }
  return result;
}

```

## disassembly

```asm
0x18000c2b8  sub     rsp, 28h
0x18000c2bc  xor     eax, eax
0x18000c2be  mov     cs:g_status.dwCurrentState, ecx
0x18000c2c4  cmp     cs:g_registeredService, eax
0x18000c2ca  jz      short loc_18000C2F1
0x18000c2cc  cmp     ecx, 4
0x18000c2cf  jz      short loc_18000C2D6
0x18000c2d1  cmp     ecx, 1
0x18000c2d4  jnz     short loc_18000C2DD
0x18000c2d6  mov     qword ptr cs:g_status.dwCheckPoint, rax
0x18000c2dd  mov     rcx, cs:g_hStatus; hServiceStatus
0x18000c2e4  lea     rdx, g_status; lpServiceStatus
0x18000c2eb  call    cs:__imp_SetServiceStatus
0x18000c2f1  add     rsp, 28h
0x18000c2f5  retn
```
