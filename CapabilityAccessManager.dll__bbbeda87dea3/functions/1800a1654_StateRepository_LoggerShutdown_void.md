# StateRepository::LoggerShutdown(void)

- ea: `0x1800a1654`
- end: `0x1800a1682`
- name: `?LoggerShutdown@StateRepository@@YAXXZ`
- size: `46`
- prototype: `void __fastcall(StateRepository *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a2048`

## callees

- `0x1800a1654`
- `0x1800a23a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a1663`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a1663`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a166b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a166b`

## pseudocode

```c
void __fastcall StateRepository::LoggerShutdown(StateRepository *this)
{
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx

  if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x20) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    McTemplateU0qq_EventWriteTransfer(v4, v3, CurrentProcessId, CurrentThreadId);
  }
}

```

## disassembly

```asm
0x1800a1654  push    rbx
0x1800a1656  sub     rsp, 20h
0x1800a165a  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 20h
0x1800a1661  jz      short loc_1800A167C
0x1800a1663  call    cs:__imp_GetCurrentThreadId
0x1800a1669  mov     ebx, eax
0x1800a166b  call    cs:__imp_GetCurrentProcessId
0x1800a1671  mov     r8d, eax
0x1800a1674  mov     r9d, ebx
0x1800a1677  call    McTemplateU0qq_EventWriteTransfer
0x1800a167c  add     rsp, 20h
0x1800a1680  pop     rbx
0x1800a1681  retn
```
