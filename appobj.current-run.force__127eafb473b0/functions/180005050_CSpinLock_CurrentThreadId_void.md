# CSpinLock::_CurrentThreadId(void)

- ea: `0x180005050`
- end: `0x180005062`
- name: `?_CurrentThreadId@CSpinLock@@CAJXZ`
- size: `18`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005054`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005054`

## pseudocode

```c
__int64 CSpinLock::_CurrentThreadId(void)
{
  return GetCurrentThreadId() & 0xFFFFFFFC;
}

```

## disassembly

```asm
0x180005050  sub     rsp, 28h; private: static long CReaderWriterLock3::_CurrentThreadId(void)
0x180005054  call    cs:__imp_GetCurrentThreadId
0x18000505a  and     eax, 0FFFFFFFCh
0x18000505d  add     rsp, 28h
0x180005061  retn
```
