# Windows::Internal::ComTaskPoolHandler::OnComplete(void)

- ea: `0x180005f90`
- end: `0x180005fb5`
- name: `?OnComplete@ComTaskPoolHandler@Internal@Windows@@QEAAXXZ`
- size: `37`
- prototype: `void __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f72c`
- `0x18002626c`
- `0x1800262c4`
- `0x18002fb20`
- `0x18002fb78`

## callees

- `0x180005f90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f99`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180005fa8`

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
0x180005f90  push    rbx
0x180005f92  sub     rsp, 20h
0x180005f96  mov     ebx, [rcx+8]
0x180005f99  call    cs:__imp_GetCurrentThreadId
0x180005f9f  cmp     eax, ebx
0x180005fa1  jz      short loc_180005FAF
0x180005fa3  add     rsp, 20h
0x180005fa7  pop     rbx
0x180005fa8  jmp     cs:__imp_SHTaskPoolAllowThreadReuse
0x180005faf  add     rsp, 20h
0x180005fb3  pop     rbx
0x180005fb4  retn
```
