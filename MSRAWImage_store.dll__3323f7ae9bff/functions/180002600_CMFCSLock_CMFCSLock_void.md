# CMFCSLock::~CMFCSLock(void)

- ea: `0x180002600`
- end: `0x180002607`
- name: `??1CMFCSLock@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800b2660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002600`

## pseudocode

```c
// attributes: thunk
void __stdcall CMFCSLock::~CMFCSLock(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180002600  jmp     cs:__imp_DeleteCriticalSection
```
