# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x180018300`
- end: `0x18001832c`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `44`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `14`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180037ff0`
- `0x180038048`
- `0x1800380a0`
- `0x1800380f8`
- `0x180038150`
- `0x1800381a8`
- `0x180038200`
- `0x180038258`
- `0x1800382b0`
- `0x18003e340`
- `0x180069fc0`
- `0x18006a018`
- `0x18006a070`
- `0x18006eaf0`

## callees

- `0x180018300`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018309`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018309`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180018319`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180018319`

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
0x180018300  push    rbx
0x180018302  sub     rsp, 20h
0x180018306  mov     ebx, [rcx+8]
0x180018309  call    cs:__imp_GetCurrentThreadId
0x180018310  nop     dword ptr [rax+rax+00h]
0x180018315  cmp     eax, ebx
0x180018317  jz      short loc_180018325
0x180018319  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x180018320  nop     dword ptr [rax+rax+00h]
0x180018325  add     rsp, 20h
0x180018329  pop     rbx
0x18001832a  retn
```
