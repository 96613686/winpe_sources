# Microsoft::CoreUI::Dispatch::ThreadContext::get_IsCurrentThreadDispatchThread(void)

- ea: `0x18005d3d0`
- end: `0x18005d3ee`
- name: `?get_IsCurrentThreadDispatchThread@ThreadContext@Dispatch@CoreUI@Microsoft@@QEAA_NXZ`
- size: `30`
- prototype: `bool __fastcall(Microsoft::CoreUI::Dispatch::ThreadContext *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005cf60`
- `0x18005d200`
- `0x18005dc24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d3d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d3d9`

## pseudocode

```c
bool __fastcall Microsoft::CoreUI::Dispatch::ThreadContext::get_IsCurrentThreadDispatchThread(
        Microsoft::CoreUI::Dispatch::ThreadContext *this)
{
  return GetCurrentThreadId() == *((_DWORD *)this + 44);
}

```

## disassembly

```asm
0x18005d3d0  push    rbx
0x18005d3d2  sub     rsp, 20h
0x18005d3d6  mov     rbx, rcx
0x18005d3d9  call    cs:__imp_GetCurrentThreadId
0x18005d3df  cmp     eax, [rbx+0B0h]
0x18005d3e5  setz    al
0x18005d3e8  add     rsp, 20h
0x18005d3ec  pop     rbx
0x18005d3ed  retn
```
