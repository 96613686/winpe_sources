# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x1800190ac`
- end: `0x1800190cb`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `14`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180038cf4`
- `0x180038d4c`
- `0x180038da4`
- `0x180038dfc`
- `0x180038e54`
- `0x180038eac`
- `0x180038f04`
- `0x180038f5c`
- `0x180038fb4`
- `0x18003e960`
- `0x180068dc8`
- `0x180068e20`
- `0x180068e78`
- `0x18006d6e0`

## callees

- `0x1800190ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800190b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800190b5`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x1800190bf`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x1800190bf`

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
0x1800190ac  push    rbx
0x1800190ae  sub     rsp, 20h
0x1800190b2  mov     ebx, [rcx+8]
0x1800190b5  call    cs:__imp_GetCurrentThreadId
0x1800190bb  cmp     eax, ebx
0x1800190bd  jz      short loc_1800190C5
0x1800190bf  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x1800190c5  add     rsp, 20h
0x1800190c9  pop     rbx
0x1800190ca  retn
```
