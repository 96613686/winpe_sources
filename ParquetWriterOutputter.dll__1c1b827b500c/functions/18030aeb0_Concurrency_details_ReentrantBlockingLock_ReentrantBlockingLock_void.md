# Concurrency::details::_ReentrantBlockingLock::~_ReentrantBlockingLock(void)

- ea: `0x18030aeb0`
- end: `0x18030aeb7`
- name: `??1_ReentrantBlockingLock@details@Concurrency@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x18030683c`
- `0x18030f750`
- `0x180310780`
- `0x180315924`
- `0x18031df2c`
- `0x18031fbd0`
- `0x18036a1ae`
- `0x18036a2e9`
- `0x18036a5b1`
- `0x18036a63c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18030aeb0`

## pseudocode

```c
// attributes: thunk
void __stdcall Concurrency::details::_ReentrantBlockingLock::~_ReentrantBlockingLock(
        LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18030aeb0  jmp     cs:__imp_DeleteCriticalSection
```
