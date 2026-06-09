# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x18001f1dc`
- end: `0x18001f1fb`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f0e0`
- `0x18004c0e8`

## callees

- `0x18001f1dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f1e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f1e5`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x18001f1ef`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x18001f1ef`

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
0x18001f1dc  push    rbx
0x18001f1de  sub     rsp, 20h
0x18001f1e2  mov     ebx, [rcx+8]
0x18001f1e5  call    cs:__imp_GetCurrentThreadId
0x18001f1eb  cmp     eax, ebx
0x18001f1ed  jz      short loc_18001F1F5
0x18001f1ef  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x18001f1f5  add     rsp, 20h
0x18001f1f9  pop     rbx
0x18001f1fa  retn
```
