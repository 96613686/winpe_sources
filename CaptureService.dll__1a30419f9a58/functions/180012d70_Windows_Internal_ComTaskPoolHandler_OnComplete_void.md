# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x180012d70`
- end: `0x180012d8f`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001791c`
- `0x18001a140`

## callees

- `0x180012d70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012d79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012d79`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180012d83`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180012d83`

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
0x180012d70  push    rbx
0x180012d72  sub     rsp, 20h
0x180012d76  mov     ebx, [rcx+8]
0x180012d79  call    cs:__imp_GetCurrentThreadId
0x180012d7f  cmp     eax, ebx
0x180012d81  jz      short loc_180012D89
0x180012d83  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x180012d89  add     rsp, 20h
0x180012d8d  pop     rbx
0x180012d8e  retn
```
