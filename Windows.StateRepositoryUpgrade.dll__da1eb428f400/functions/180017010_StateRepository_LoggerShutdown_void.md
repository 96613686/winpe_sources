# StateRepository::LoggerShutdown(void)

- ea: `0x180017010`
- end: `0x180017045`
- name: `?LoggerShutdown@StateRepository@@YAXXZ`
- size: `53`
- prototype: `void __fastcall(StateRepository *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180017010`
- `0x180017f84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001701f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001701f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017027`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017027`

## pseudocode

```c
void __fastcall StateRepository::LoggerShutdown(StateRepository *this)
{
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v3; // rcx

  if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x20) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    McTemplateU0qq_EventWriteTransfer(v3, RepositoryShutdown, CurrentProcessId, CurrentThreadId);
  }
}

```

## disassembly

```asm
0x180017010  push    rbx
0x180017012  sub     rsp, 20h
0x180017016  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 20h
0x18001701d  jz      short loc_18001703F
0x18001701f  call    cs:__imp_GetCurrentThreadId
0x180017025  mov     ebx, eax
0x180017027  call    cs:__imp_GetCurrentProcessId
0x18001702d  mov     r9d, ebx
0x180017030  lea     rdx, RepositoryShutdown
0x180017037  mov     r8d, eax
0x18001703a  call    McTemplateU0qq_EventWriteTransfer
0x18001703f  add     rsp, 20h
0x180017043  pop     rbx
0x180017044  retn
```
