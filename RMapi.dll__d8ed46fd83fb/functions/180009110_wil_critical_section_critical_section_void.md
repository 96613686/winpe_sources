# wil::critical_section::~critical_section(void)

- ea: `0x180009110`
- end: `0x180009117`
- name: `??1critical_section@wil@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18002533d`
- `0x180025687`
- `0x180025a9e`
- `0x180025aee`
- `0x180025ce7`
- `0x180025e8b`
- `0x180025eef`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009110`

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
0x180009110  jmp     cs:__imp_DeleteCriticalSection
```
