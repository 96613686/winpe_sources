# wil::critical_section::~critical_section(void)

- ea: `0x180005fb4`
- end: `0x180005fbb`
- name: `??1critical_section@wil@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002fae4`
- `0x18002fca9`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005fb4`

## pseudocode

```c
// attributes: thunk
void __stdcall wil::critical_section::~critical_section(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180005fb4  jmp     cs:__imp_DeleteCriticalSection
```
