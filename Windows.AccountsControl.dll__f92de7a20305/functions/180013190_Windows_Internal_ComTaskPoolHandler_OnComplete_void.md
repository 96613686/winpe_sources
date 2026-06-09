# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x180013190`
- end: `0x1800131af`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180018c6c`
- `0x18002f554`
- `0x18003c3d0`
- `0x1800483f8`
- `0x180054438`
- `0x180054490`

## callees

- `0x180013190`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013199`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013199`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x1800131a3`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x1800131a3`

## pseudocode

```c
void __fastcall Windows::Internal::ComTaskPoolHandler::OnComplete(Windows::Internal::ComTaskPoolHandler *this)
{
  int v1; // ebx

  v1 = *((_DWORD *)this + 2);
  if ( GetCurrentThreadId() != v1 )
    SHTaskPoolAllowThreadReuse();
}

```

## disassembly

```asm
0x180013190  push    rbx
0x180013192  sub     rsp, 20h
0x180013196  mov     ebx, [rcx+8]
0x180013199  call    cs:__imp_GetCurrentThreadId
0x18001319f  cmp     eax, ebx
0x1800131a1  jz      short loc_1800131A9
0x1800131a3  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x1800131a9  add     rsp, 20h
0x1800131ad  pop     rbx
0x1800131ae  retn
```
