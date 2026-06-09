# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x180077420`
- end: `0x18007743f`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18007944c`
- `0x18007eba4`
- `0x180095014`
- `0x18009506c`
- `0x1800950c4`
- `0x18009acc0`
- `0x1800b98f8`
- `0x1800c737c`
- `0x1800cb0f8`

## callees

- `0x180077420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180077429`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180077429`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180077433`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180077433`

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
0x180077420  push    rbx
0x180077422  sub     rsp, 20h
0x180077426  mov     ebx, [rcx+8]
0x180077429  call    cs:__imp_GetCurrentThreadId
0x18007742f  cmp     eax, ebx
0x180077431  jz      short loc_180077439
0x180077433  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x180077439  add     rsp, 20h
0x18007743d  pop     rbx
0x18007743e  retn
```
