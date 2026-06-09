# CCritSec::~CCritSec(void)

- ea: `0x18000aa20`
- end: `0x18000aa27`
- name: `??1CCritSec@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180088870`
- `0x180088910`
- `0x180088c30`
- `0x180088c50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000aa20`

## pseudocode

```c
// attributes: thunk
void __stdcall CCritSec::~CCritSec(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000aa20  jmp     cs:__imp_DeleteCriticalSection
```
