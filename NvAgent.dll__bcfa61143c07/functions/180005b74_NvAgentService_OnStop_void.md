# NvAgentService::OnStop(void)

- ea: `0x180005b74`
- end: `0x180005baa`
- name: `?OnStop@NvAgentService@@IEAAXXZ`
- size: `54`
- prototype: `void __fastcall(NvAgentService *this, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180005b50`

## callees

- `0x180005b74`
- `0x180005bb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180005ba3`
- `vmsif!VmsIfShutdownEventServer` at `0x180005b83`
- `vmsif!VmsIfShutdownEventServer` at `0x180005b83`

## pseudocode

```c
void __fastcall NvAgentService::OnStop(NvAgentService *this, __int64 a2, unsigned int a3)
{
  if ( *((_BYTE *)this + 32) )
  {
    VmsIfShutdownEventServer();
    *((_BYTE *)this + 32) = 0;
  }
  NvAgentService::SetStatus(this, 3u, a3);
  SetEvent(*((HANDLE *)this + 3));
}

```

## disassembly

```asm
0x180005b74  push    rbx
0x180005b76  sub     rsp, 20h
0x180005b7a  cmp     byte ptr [rcx+20h], 0
0x180005b7e  mov     rbx, rcx
0x180005b81  jz      short loc_180005B8D
0x180005b83  call    cs:__imp_VmsIfShutdownEventServer
0x180005b89  mov     byte ptr [rbx+20h], 0
0x180005b8d  mov     edx, 3; unsigned int
0x180005b92  mov     rcx, rbx; this
0x180005b95  call    ?SetStatus@NvAgentService@@IEAAXKK@Z; NvAgentService::SetStatus(ulong,ulong)
0x180005b9a  mov     rcx, [rbx+18h]
0x180005b9e  add     rsp, 20h
0x180005ba2  pop     rbx
0x180005ba3  jmp     cs:__imp_SetEvent
```
