# NvAgentService::~NvAgentService(void)

- ea: `0x180005ad8`
- end: `0x180005b47`
- name: `??1NvAgentService@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(NvAgentService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x1800063a0`

## callees

- `0x180005ad8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b2a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005af4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005b3b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005af4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005b3b`
- `vmsif!VmsIfShutdownEventServer` at `0x180005b17`
- `vmsif!VmsIfShutdownEventServer` at `0x180005b17`

## pseudocode

```c
void __fastcall NvAgentService::~NvAgentService(NvAgentService *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v2 = (void *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v2 )
    UnregisterWaitEx(v2, 0);
  v3 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v3 )
    CloseHandle(v3);
  if ( *((_BYTE *)this + 32) )
  {
    VmsIfShutdownEventServer();
    *((_BYTE *)this + 32) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
    CloseHandle(v4);
  v5 = (void *)*((_QWORD *)this + 2);
  if ( v5 )
    UnregisterWaitEx(v5, 0);
}

```

## disassembly

```asm
0x180005ad8  push    rbx
0x180005ada  sub     rsp, 20h
0x180005ade  mov     rbx, rcx
0x180005ae1  mov     rcx, [rcx+10h]; WaitHandle
0x180005ae5  mov     qword ptr [rbx+10h], 0
0x180005aed  test    rcx, rcx
0x180005af0  jz      short loc_180005AFA
0x180005af2  xor     edx, edx; CompletionEvent
0x180005af4  call    cs:__imp_UnregisterWaitEx
0x180005afa  mov     rcx, [rbx+18h]; hObject
0x180005afe  mov     qword ptr [rbx+18h], 0
0x180005b06  test    rcx, rcx
0x180005b09  jz      short loc_180005B11
0x180005b0b  call    cs:__imp_CloseHandle
0x180005b11  cmp     byte ptr [rbx+20h], 0
0x180005b15  jz      short loc_180005B21
0x180005b17  call    cs:__imp_VmsIfShutdownEventServer
0x180005b1d  mov     byte ptr [rbx+20h], 0
0x180005b21  mov     rcx, [rbx+18h]; hObject
0x180005b25  test    rcx, rcx
0x180005b28  jz      short loc_180005B30
0x180005b2a  call    cs:__imp_CloseHandle
0x180005b30  mov     rcx, [rbx+10h]; WaitHandle
0x180005b34  test    rcx, rcx
0x180005b37  jz      short loc_180005B41
0x180005b39  xor     edx, edx; CompletionEvent
0x180005b3b  call    cs:__imp_UnregisterWaitEx
0x180005b41  add     rsp, 20h
0x180005b45  pop     rbx
0x180005b46  retn
```
