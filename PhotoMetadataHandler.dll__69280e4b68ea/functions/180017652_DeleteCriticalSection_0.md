# DeleteCriticalSection_0

- ea: `0x180017652`
- end: `0x180017658`
- name: `DeleteCriticalSection_0`
- size: `6`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001174c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017652`

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
0x180017652  jmp     cs:__imp_DeleteCriticalSection
```
