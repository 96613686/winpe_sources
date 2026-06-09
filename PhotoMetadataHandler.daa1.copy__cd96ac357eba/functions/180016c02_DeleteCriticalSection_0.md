# DeleteCriticalSection_0

- ea: `0x180016c02`
- end: `0x180016c08`
- name: `DeleteCriticalSection_0`
- size: `6`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180010fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016c02`

## pseudocode

```c
// attributes: thunk
void __stdcall DeleteCriticalSection_0(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180016c02  jmp     cs:__imp_DeleteCriticalSection
```
