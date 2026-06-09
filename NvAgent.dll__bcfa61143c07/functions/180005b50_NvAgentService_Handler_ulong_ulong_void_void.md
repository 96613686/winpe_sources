# NvAgentService::Handler(ulong,ulong,void *,void *)

- ea: `0x180005b50`
- end: `0x180005b6d`
- name: `?Handler@NvAgentService@@KAKKKPEAX0@Z`
- size: `29`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, NvAgentService *lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180005b50`
- `0x180005b74`

## pseudocode

```c
__int64 __fastcall NvAgentService::Handler(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        NvAgentService *lpContext)
{
  DWORD v4; // ecx

  v4 = dwControl - 1;
  if ( !v4 || v4 == 4 )
    NvAgentService::OnStop(lpContext);
  return 0;
}

```

## disassembly

```asm
0x180005b50  sub     rsp, 28h
0x180005b54  sub     ecx, 1
0x180005b57  jz      short loc_180005B5E
0x180005b59  cmp     ecx, 4
0x180005b5c  jnz     short loc_180005B66
0x180005b5e  mov     rcx, r9; this
0x180005b61  call    ?OnStop@NvAgentService@@IEAAXXZ; NvAgentService::OnStop(void)
0x180005b66  xor     eax, eax
0x180005b68  add     rsp, 28h
0x180005b6c  retn
```
