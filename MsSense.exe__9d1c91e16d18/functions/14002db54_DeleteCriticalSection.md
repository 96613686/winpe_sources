# DeleteCriticalSection

- ea: `0x14002db54`
- end: `0x14002db5b`
- name: `DeleteCriticalSection`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14004ec4c`
- `0x140081b49`
- `0x140084464`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14002db54`

## pseudocode

```c
// attributes: thunk
void __stdcall DeleteCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  __imp_DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x14002db54  jmp     cs:__imp_DeleteCriticalSection
```
