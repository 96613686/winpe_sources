# StateRepository::LoggerInitialized(void)

- ea: `0x180016fcc`
- end: `0x180017001`
- name: `?LoggerInitialized@StateRepository@@YAXXZ`
- size: `53`
- prototype: `void __fastcall(StateRepository *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016dcc`

## callees

- `0x180016fcc`
- `0x180017f84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016fdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016fdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016fe3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016fe3`

## pseudocode

```c
void __fastcall StateRepository::LoggerInitialized(StateRepository *this)
{
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v3; // rcx

  if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x20) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    McTemplateU0qq_EventWriteTransfer(v3, RepositoryInitialized, CurrentProcessId, CurrentThreadId);
  }
}

```

## disassembly

```asm
0x180016fcc  push    rbx
0x180016fce  sub     rsp, 20h
0x180016fd2  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 20h
0x180016fd9  jz      short loc_180016FFB
0x180016fdb  call    cs:__imp_GetCurrentThreadId
0x180016fe1  mov     ebx, eax
0x180016fe3  call    cs:__imp_GetCurrentProcessId
0x180016fe9  mov     r9d, ebx
0x180016fec  lea     rdx, RepositoryInitialized
0x180016ff3  mov     r8d, eax
0x180016ff6  call    McTemplateU0qq_EventWriteTransfer
0x180016ffb  add     rsp, 20h
0x180016fff  pop     rbx
0x180017000  retn
```
