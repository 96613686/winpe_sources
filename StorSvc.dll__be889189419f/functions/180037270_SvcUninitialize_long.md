# SvcUninitialize(long)

- ea: `0x180037270`
- end: `0x1800372c2`
- name: `?SvcUninitialize@@YAJJ@Z`
- size: `82`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18003c380`
- `0x18003c730`

## callees

- `0x1800206d4`
- `0x180037270`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800372b3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800372b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180037292`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180037292`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180037285`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180037285`

## pseudocode

```c
__int64 __fastcall SvcUninitialize()
{
  StorageService *v0; // rcx

  v0 = qword_1800C08F0;
  if ( qword_1800C08F0 )
  {
    WaitForThreadpoolWorkCallbacks(qword_1800C08F0, 1);
    CloseThreadpoolWork(qword_1800C08F0);
    qword_1800C08F0 = 0;
  }
  if ( dword_1800C0908 )
    DeleteCriticalSection(&stru_1800C9B80);
  return StorageService::Deinit(v0);
}

```

## disassembly

```asm
0x180037270  sub     rsp, 28h
0x180037274  mov     rcx, cs:qword_1800C08F0; pwk
0x18003727b  test    rcx, rcx
0x18003727e  jz      short loc_1800372A3
0x180037280  mov     edx, 1; fCancelPendingCallbacks
0x180037285  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18003728b  mov     rcx, cs:qword_1800C08F0; pwk
0x180037292  call    cs:__imp_CloseThreadpoolWork
0x180037298  mov     cs:qword_1800C08F0, 0
0x1800372a3  cmp     cs:dword_1800C0908, 0
0x1800372aa  jz      short loc_1800372B9
0x1800372ac  lea     rcx, stru_1800C9B80; lpCriticalSection
0x1800372b3  call    cs:__imp_DeleteCriticalSection
0x1800372b9  add     rsp, 28h
0x1800372bd  jmp     ?Deinit@StorageService@@QEAAJXZ; StorageService::Deinit(void)
```
