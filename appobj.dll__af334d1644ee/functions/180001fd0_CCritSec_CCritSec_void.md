# CCritSec::~CCritSec(void)

- ea: `0x180001fd0`
- end: `0x180001fd7`
- name: `??1CCritSec@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001fd0`

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
0x180001fd0  jmp     cs:__imp_DeleteCriticalSection
```
