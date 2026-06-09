# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x180018b20`
- end: `0x180018b3f`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b118`
- `0x18001fb80`

## callees

- `0x180018b20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018b29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018b29`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180018b33`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180018b33`

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
0x180018b20  push    rbx
0x180018b22  sub     rsp, 20h
0x180018b26  mov     ebx, [rcx+8]
0x180018b29  call    cs:__imp_GetCurrentThreadId
0x180018b2f  cmp     eax, ebx
0x180018b31  jz      short loc_180018B39
0x180018b33  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x180018b39  add     rsp, 20h
0x180018b3d  pop     rbx
0x180018b3e  retn
```
