# NvAgentService::StopCallback(void *,uchar)

- ea: `0x180005c20`
- end: `0x180005c6b`
- name: `?StopCallback@NvAgentService@@CAXPEAXE@Z`
- size: `75`
- prototype: `void __fastcall(NvAgentService *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180005bb0`
- `0x180005c20`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c53`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005c3c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180005c3c`

## pseudocode

```c
void __fastcall NvAgentService::StopCallback(NvAgentService *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v2 )
    UnregisterWaitEx(v2, 0);
  v3 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v3 )
    CloseHandle(v3);
  NvAgentService::SetStatus((SERVICE_STATUS_HANDLE *)this, 1u);
}

```

## disassembly

```asm
0x180005c20  push    rbx
0x180005c22  sub     rsp, 20h
0x180005c26  mov     rbx, rcx
0x180005c29  mov     rcx, [rcx+10h]; WaitHandle
0x180005c2d  mov     qword ptr [rbx+10h], 0
0x180005c35  test    rcx, rcx
0x180005c38  jz      short loc_180005C42
0x180005c3a  xor     edx, edx; CompletionEvent
0x180005c3c  call    cs:__imp_UnregisterWaitEx
0x180005c42  mov     rcx, [rbx+18h]; hObject
0x180005c46  mov     qword ptr [rbx+18h], 0
0x180005c4e  test    rcx, rcx
0x180005c51  jz      short loc_180005C59
0x180005c53  call    cs:__imp_CloseHandle
0x180005c59  mov     edx, 1; unsigned int
0x180005c5e  mov     rcx, rbx; this
0x180005c61  add     rsp, 20h
0x180005c65  pop     rbx
0x180005c66  jmp     ?SetStatus@NvAgentService@@IEAAXKK@Z; NvAgentService::SetStatus(ulong,ulong)
```
