# wil::critical_section::~critical_section(void)

- ea: `0x140003878`
- end: `0x14000387f`
- name: `??1critical_section@wil@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400094bb`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140003878`

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
0x140003878  jmp     cs:__imp_DeleteCriticalSection
```
